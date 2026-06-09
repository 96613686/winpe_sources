# System.Deployment.Internal.CodeSigning.SignedCmiManifest::VerifyPublicKeyToken

- ea: `0x68d0`
- end: `0x6a7f`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest::VerifyPublicKeyToken`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6150`

## callees

- `0x5e90`
- `0x5ea0`
- `0x5f00`
- `0x68d0`
- `0x6cf0`
- `0x7340`

## string_xrefs

- `0x68f7`: `http://www.w3.org/2000/09/xmldsig#`
- `0x68e7`: `urn:schemas-microsoft-com:asm.v1`

## pseudocode

```c

```

## disassembly

```asm
0x68d0  ldarg.0
0x68d1  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_manifestDom
0x68d6  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x68db  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x68e0  stloc.0
0x68e1  ldloc.0
0x68e2  ldstr    aAsm// "asm"
0x68e7  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x68ec  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x68f1  ldloc.0
0x68f2  ldstr    aDs// "ds"
0x68f7  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/09/xmldsig#"
0x68fc  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x6901  ldarg.0
0x6902  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_manifestDom
0x6907  ldstr    aAsmAssemblyDsS_3// "asm:assembly/ds:Signature/ds:KeyInfo/ds"...
0x690c  ldloc.0
0x690d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x6912  isinst   [System.Xml]System.Xml.XmlElement
0x6917  stloc.1
0x6918  ldarg.0
0x6919  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_manifestDom
0x691e  ldstr    aAsmAssemblyDsS_4// "asm:assembly/ds:Signature/ds:KeyInfo/ds"...
0x6923  ldloc.0
0x6924  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x6929  isinst   [System.Xml]System.Xml.XmlElement
0x692e  stloc.2
0x692f  ldloc.1
0x6930  brfalse.s loc_6935
0x6932  ldloc.2
0x6933  brtrue.s loc_6940
0x6935  ldc.i4   0x800B0003
0x693a  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x693f  throw
0x6940  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x6945  ldloc.1
0x6946  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x694b  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x6950  stloc.3
0x6951  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x6956  ldloc.2
0x6957  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x695c  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x6961  stloc.s  4
0x6963  ldarg.0
0x6964  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest::m_manifestDom
0x6969  call     string System.Deployment.Internal.CodeSigning.SignedCmiManifest::GetPublicKeyToken(class [System.Xml]System.Xml.XmlDocument manifestDom)
0x696e  stloc.s  5
0x6970  ldloc.s  5
0x6972  call     unsigned int8[] System.Deployment.Internal.CodeSigning.SignedCmiManifest::HexStringToBytes(string hexString)
0x6977  stloc.s  6
0x6979  ldloc.3
0x697a  dup
0x697b  stloc.s  9
0x697d  brfalse.s loc_6985
0x697f  ldloc.s  9
0x6981  ldlen
0x6982  conv.i4
0x6983  brtrue.s loc_698B
0x6985  ldc.i4.0
0x6986  conv.u
0x6987  stloc.s  8
0x6989  br.s     loc_6996
0x698b  ldloc.s  9
0x698d  ldc.i4.0
0x698e  ldelema  [mscorlib]System.Byte
0x6993  conv.u
0x6994  stloc.s  8
0x6996  ldloc.s  4
0x6998  dup
0x6999  stloc.s  0xB
0x699b  brfalse.s loc_69A3
0x699d  ldloc.s  0xB
0x699f  ldlen
0x69a0  conv.i4
0x69a1  brtrue.s loc_69A9
0x69a3  ldc.i4.0
0x69a4  conv.u
0x69a5  stloc.s  0xA
0x69a7  br.s     loc_69B4
0x69a9  ldloc.s  0xB
0x69ab  ldc.i4.0
0x69ac  ldelema  [mscorlib]System.Byte
0x69b1  conv.u
0x69b2  stloc.s  0xA
0x69b4  ldloca.s 0xC
0x69b6  initobj  CRYPT_DATA_BLOB
0x69bc  ldloca.s 0xD
0x69be  initobj  CRYPT_DATA_BLOB
0x69c4  ldloca.s 0xE
0x69c6  initobj  [mscorlib]System.IntPtr
0x69cc  ldloca.s 0xC
0x69ce  ldloc.3
0x69cf  ldlen
0x69d0  conv.i4
0x69d1  stfld    unsigned int32 CRYPT_DATA_BLOB::cbData
0x69d6  ldloca.s 0xC
0x69d8  ldloc.s  8
0x69da  newobj   instance void [mscorlib]System.IntPtr::.ctor(void*)
0x69df  stfld    native int CRYPT_DATA_BLOB::pbData
0x69e4  ldloca.s 0xD
0x69e6  ldloc.s  4
0x69e8  ldlen
0x69e9  conv.i4
0x69ea  stfld    unsigned int32 CRYPT_DATA_BLOB::cbData
0x69ef  ldloca.s 0xD
0x69f1  ldloc.s  0xA
0x69f3  newobj   instance void [mscorlib]System.IntPtr::.ctor(void*)
0x69f8  stfld    native int CRYPT_DATA_BLOB::pbData
0x69fd  ldloca.s 0xC
0x69ff  ldloca.s 0xD
0x6a01  ldloca.s 0xE
0x6a03  call     int32 System.Deployment.Internal.CodeSigning.Win32::_AxlRSAKeyValueToPublicKeyToken([in] valuetype CRYPT_DATA_BLOB& pModulusBlob, [in] valuetype CRYPT_DATA_BLOB& pExponentBlob, [in] [out] native int& ppwszPublicKeyToken)
0x6a08  stloc.s  0xF
0x6a0a  ldloc.s  0xF
0x6a0c  brfalse.s loc_6A16
0x6a0e  ldloc.s  0xF
0x6a10  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x6a15  throw
0x6a16  ldloc.s  0xE
0x6a18  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringUni(native int)
0x6a1d  call     unsigned int8[] System.Deployment.Internal.CodeSigning.SignedCmiManifest::HexStringToBytes(string hexString)
0x6a22  stloc.s  7
0x6a24  call     native int System.Deployment.Internal.CodeSigning.Win32::GetProcessHeap()
0x6a29  ldc.i4.0
0x6a2a  ldloc.s  0xE
0x6a2c  call     bool System.Deployment.Internal.CodeSigning.Win32::HeapFree([hasfieldmarshal] native int, [in] unsigned int32 hHeap, [in] native int dwFlags)
0x6a31  pop
0x6a32  ldnull
0x6a33  stloc.s  0xB
0x6a35  ldnull
0x6a36  stloc.s  9
0x6a38  ldloc.s  6
0x6a3a  ldlen
0x6a3b  brfalse.s loc_6A47
0x6a3d  ldloc.s  6
0x6a3f  ldlen
0x6a40  conv.i4
0x6a41  ldloc.s  7
0x6a43  ldlen
0x6a44  conv.i4
0x6a45  beq.s    loc_6A52
0x6a47  ldc.i4   0x800B010B
0x6a4c  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x6a51  throw
0x6a52  ldc.i4.0
0x6a53  stloc.s  0x10
0x6a55  br.s     loc_6A74
0x6a57  ldloc.s  6
0x6a59  ldloc.s  0x10
0x6a5b  ldelem.u1
0x6a5c  ldloc.s  7
0x6a5e  ldloc.s  0x10
0x6a60  ldelem.u1
0x6a61  beq.s    loc_6A6E
0x6a63  ldc.i4   0x800B010B
0x6a68  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x6a6d  throw
0x6a6e  ldloc.s  0x10
0x6a70  ldc.i4.1
0x6a71  add
0x6a72  stloc.s  0x10
0x6a74  ldloc.s  0x10
0x6a76  ldloc.s  6
0x6a78  ldlen
0x6a79  conv.i4
0x6a7a  blt.s    loc_6A57
0x6a7c  ldloc.s  5
0x6a7e  ret
```
