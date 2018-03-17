Welcome to the SHA-Secure-Hash-Algorithm-in-Java wiki!


package test;

import java.security.MessageDigest;

import javax.xml.bind.DatatypeConverter;

public class EncryptDecrypt {
	public static String getHash(byte[] inputBytes,String algorithm)
	{
	String hashvalues="";
	try
	{
		MessageDigest messagedigest=MessageDigest.getInstance(algorithm);
		messagedigest.update(inputBytes);
	byte[] digestBytes=messagedigest.digest();
	hashvalues= DatatypeConverter.printHexBinary(digestBytes).toLowerCase();
	}
	catch(Exception e)
	{
	 
	}
	return hashvalues;
	}


	public static void main(String args[])
	{
	String something="test";
	System.out.println(getHash(something.getBytes(),"SHA-224"));
}
	}