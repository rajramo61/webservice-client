# How to generate client java code from WSDL?
1. This utility uses maven with CXF version 3.3.3 to generate the client lib
2. This utility does not support the old (not widely supported) Rpc/encoded wsdls as those are old format.
3. wsdl definition with ``<soap:body use="encoded" encodingStyle="http://schemas.xmlsoap.org/soap/encoding/"/>`` 
    tells us it is old fashioned wsdl
4. To handle the old wsdl with RPC encoding, use Java/RPC client or Axis1.x to generate client Java files.
5. If you don't need to use the RPC/encoded part then you can comment this part and use the current utility.


### Pre-config
1. Make sure Java is installed and JAVA_HOME is setup.
2. Make sure maven is installed and M2_HOME is setup 

### Steps to follow:
1. Put the WSDL file under src/main/resources directory
2. Update the pom.xml with WSDL details 
3. Run the following command to generate the sources.

    ``mvn generate-sources``
4. If you see "BUILD SUCCESS" message then you can find the generated files to location defined in pom.xml 
``<sourceRoot></sourceRoot>`` section
