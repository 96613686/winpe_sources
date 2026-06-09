# System.Deployment.Internal.CodeSigning.SignedCmiManifest::TimestampSignedLicenseDom

- ea: `0x7080`
- end: `0x71c2`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest::TimestampSignedLicenseDom`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6f50`

## callees

- `0x5e90`
- `0x5ea0`
- `0x5eb0`
- `0x7080`

## string_xrefs

- `0x70aa`: `http://www.w3.org/2000/09/xmldsig#`
- `0x718e`: `http://www.w3.org/2000/09/xmldsig#`
- `0x70ba`: `http://schemas.microsoft.com/windows/pki/2005/Authenticode`
- `0x716a`: `http://schemas.microsoft.com/windows/pki/2005/Authenticode`

## pseudocode

```c

```

## disassembly

```asm
0x7080  ldloca.s 0
0x7082  initobj  CRYPT_DATA_BLOB
0x7088  ldarg.0
0x7089  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x708e  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x7093  stloc.1
0x7094  ldloc.1
0x7095  ldstr    aR// "r"
0x709a  ldstr    aUrnMpegMpeg212// "urn:mpeg:mpeg21:2003:01-REL-R-NS"
0x709f  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x70a4  ldloc.1
0x70a5  ldstr    aDs// "ds"
0x70aa  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/09/xmldsig#"
0x70af  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x70b4  ldloc.1
0x70b5  ldstr    aAs// "as"
0x70ba  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/windows/pk"...
0x70bf  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x70c4  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x70c9  ldarg.0
0x70ca  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x70cf  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x70d4  stloc.2
0x70d5  ldloc.2
0x70d6  dup
0x70d7  stloc.s  8
0x70d9  brfalse.s loc_70E1
0x70db  ldloc.s  8
0x70dd  ldlen
0x70de  conv.i4
0x70df  brtrue.s loc_70E7
0x70e1  ldc.i4.0
0x70e2  conv.u
0x70e3  stloc.s  7
0x70e5  br.s     loc_70F2
0x70e7  ldloc.s  8
0x70e9  ldc.i4.0
0x70ea  ldelema  [mscorlib]System.Byte
0x70ef  conv.u
0x70f0  stloc.s  7
0x70f2  ldloca.s 9
0x70f4  initobj  CRYPT_DATA_BLOB
0x70fa  ldloca.s 0xA
0x70fc  ldloc.s  7
0x70fe  call     instance void [mscorlib]System.IntPtr::.ctor(void*)
0x7103  ldloca.s 9
0x7105  ldloc.2
0x7106  ldlen
0x7107  conv.i4
0x7108  stfld    unsigned int32 CRYPT_DATA_BLOB::cbData
0x710d  ldloca.s 9
0x710f  ldloc.s  0xA
0x7111  stfld    native int CRYPT_DATA_BLOB::pbData
0x7116  ldloca.s 9
0x7118  ldarg.1
0x7119  ldloca.s 0
0x711b  call     int32 System.Deployment.Internal.CodeSigning.Win32::CertTimestampAuthenticodeLicense([in] valuetype CRYPT_DATA_BLOB& pSignedLicenseBlob, [in] string pwszTimestampURI, [in] [out] valuetype CRYPT_DATA_BLOB& pTimestampSignatureBlob)
0x7120  stloc.s  0xB
0x7122  ldloc.s  0xB
0x7124  brfalse.s loc_712E
0x7126  ldloc.s  0xB
0x7128  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x712d  throw
0x712e  ldnull
0x712f  stloc.s  8
0x7131  ldloc.0
0x7132  ldfld    unsigned int32 CRYPT_DATA_BLOB::cbData
0x7137  newarr   [mscorlib]System.Byte
0x713c  stloc.3
0x713d  ldloc.0
0x713e  ldfld    native int CRYPT_DATA_BLOB::pbData
0x7143  ldloc.3
0x7144  ldc.i4.0
0x7145  ldloc.3
0x7146  ldlen
0x7147  conv.i4
0x7148  call     void [mscorlib]System.Runtime.InteropServices.Marshal::Copy(native int, unsigned int8[], int32, int32)
0x714d  call     native int System.Deployment.Internal.CodeSigning.Win32::GetProcessHeap()
0x7152  ldc.i4.0
0x7153  ldloc.0
0x7154  ldfld    native int CRYPT_DATA_BLOB::pbData
0x7159  call     bool System.Deployment.Internal.CodeSigning.Win32::HeapFree([hasfieldmarshal] native int, [in] unsigned int32 hHeap, [in] native int dwFlags)
0x715e  pop
0x715f  ldarg.0
0x7160  ldstr    aAs// "as"
0x7165  ldstr    aTimestamp// "Timestamp"
0x716a  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/windows/pk"...
0x716f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string, string)
0x7174  stloc.s  4
0x7176  ldloc.s  4
0x7178  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x717d  ldloc.3
0x717e  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x7183  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x7188  ldarg.0
0x7189  ldstr    aObject// "Object"
0x718e  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/09/xmldsig#"
0x7193  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0x7198  stloc.s  5
0x719a  ldloc.s  5
0x719c  ldloc.s  4
0x719e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x71a3  pop
0x71a4  ldarg.0
0x71a5  ldstr    aRLicenseRIssue_0// "r:license/r:issuer/ds:Signature"
0x71aa  ldloc.1
0x71ab  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x71b0  isinst   [System.Xml]System.Xml.XmlElement
0x71b5  stloc.s  6
0x71b7  ldloc.s  6
0x71b9  ldloc.s  5
0x71bb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x71c0  pop
0x71c1  ret
```
