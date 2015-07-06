# lockss-maven

NOTE: This is _not_ finished work!  It is just enough to make it
possible to use IntelliJ IDEA better with sources as it can derive
much more automatically from Maven POM files than from Ant build
files.  Antlr G4 files are processed correctly.

A few dependencies could not be found as-is in Maven Central.  Use

    mvn install:install-file -Dfile=lockss/lib/oiosaml.java-21188-PATCHED.jar -DpomFile=poms/oiosaml.java-21188-PATCHED.pom
    mvn install:install-file -Dfile=lockss/lib/JoSQL-2.2.jar -DpomFile=poms/JoSQL-2.2.pom
    mvn install:install-file -Dfile=lockss/lib/javagnutar.jar -DpomFile=poms/javagnutar.pom
    mvn install:install-file -Dfile=lockss/lib/htmlparser-1.6p.jar -DpomFile=poms/htmlparser-1.6p.pom
    mvn install:install-file -Dfile=lockss/lib/JimiProClasses.jar -DpomFile=poms/JimiProClasses.pom
    mvn install:install-file -Dfile=lockss/lib/rdf-api-2001-01-19.jar -DpomFile=poms/rdf-api-2001-01-19.pom
    mvn install:install-file -Dfile=lockss/lib/PDFBox-0.7.3.jar -DpomFile=poms/PDFBox-0.7.3.pom
    mvn install:install-file -Dfile=lockss/lib/jetty-5.1.5L.jar -DpomFile=poms/jetty-5.1.5L.pom
    mvn install:install-file -Dfile=lockss/lib/heritrix-commons-3.1.0-p1.jar -DpomFile=poms/heritrix-commons-3.1.0-p1.pom

to install them to your local repository.

An Oracle 1.7 JDK or OpenJDK 1.7 is required (not JRE).  IBM 1.7 will not work with
the current keystore code.

Note: The antlr *.g4 files are explicitly pointed to to avoid emitting
a package line in addition to the one already present in the template.

Note: To update the lockss submodule, enter it and do

    cd lockss
    git svn fetch
    git push
    cd ..
    git push

/tra 2015-07-03
