# System.Deployment.Internal.CodeSigning.SignedCmiManifest::ReplacePublicKeyToken

- ea: `0x6bf0`
- end: `0x6ce4`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest::ReplacePublicKeyToken`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x60b0`

## callees

- `0x5e90`
- `0x5ea0`
- `0x5f10`
- `0x6bf0`

## string_xrefs

- `0x6c02`: `urn:schemas-microsoft-com:asm.v1`
- `0x6c2d`: `publicKeyToken`
- `0x6cd4`: `publicKeyToken`

## pseudocode

```c

```

## disassembly

```asm
0x6bf0  ldarg.0
0x6bf1  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x6bf6  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x6bfb  stloc.0
0x6bfc  ldloc.0
0x6bfd  ldstr    aAsm// "asm"
0x6c02  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x6c07  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x6c0c  ldarg.0
0x6c0d  ldstr    aAsmAssemblyAsm// "asm:assembly/asm:assemblyIdentity"
0x6c12  ldloc.0
0x6c13  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x6c18  isinst   [System.Xml]System.Xml.XmlElement
0x6c1d  stloc.1
0x6c1e  ldloc.1
0x6c1f  brtrue.s loc_6C2C
0x6c21  ldc.i4   0x800B0003
0x6c26  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x6c2b  throw
0x6c2c  ldloc.1
0x6c2d  ldstr    aPublickeytoken// "publicKeyToken"
0x6c32  callvirt instance bool [System.Xml]System.Xml.XmlElement::HasAttribute(string)
0x6c37  brtrue.s loc_6C44
0x6c39  ldc.i4   0x800B0003
0x6c3e  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x6c43  throw
0x6c44  ldarg.1
0x6c45  castclass [mscorlib]System.Security.Cryptography.RSACryptoServiceProvider
0x6c4a  ldc.i4.0
0x6c4b  callvirt instance unsigned int8[] [mscorlib]System.Security.Cryptography.RSACryptoServiceProvider::ExportCspBlob(bool)
0x6c50  stloc.2
0x6c51  ldloc.2
0x6c52  brfalse.s loc_6C58
0x6c54  ldloc.2
0x6c55  ldlen
0x6c56  brtrue.s loc_6C63
0x6c58  ldc.i4   0x80090003
0x6c5d  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x6c62  throw
0x6c63  ldloc.2
0x6c64  dup
0x6c65  stloc.s  4
0x6c67  brfalse.s loc_6C6F
0x6c69  ldloc.s  4
0x6c6b  ldlen
0x6c6c  conv.i4
0x6c6d  brtrue.s loc_6C74
0x6c6f  ldc.i4.0
0x6c70  conv.u
0x6c71  stloc.3
0x6c72  br.s     loc_6C7E
0x6c74  ldloc.s  4
0x6c76  ldc.i4.0
0x6c77  ldelema  [mscorlib]System.Byte
0x6c7c  conv.u
0x6c7d  stloc.3
0x6c7e  ldloca.s 5
0x6c80  initobj  CRYPT_DATA_BLOB
0x6c86  ldloca.s 5
0x6c88  ldloc.2
0x6c89  ldlen
0x6c8a  conv.i4
0x6c8b  stfld    unsigned int32 CRYPT_DATA_BLOB::cbData
0x6c90  ldloca.s 5
0x6c92  ldloc.3
0x6c93  newobj   instance void [mscorlib]System.IntPtr::.ctor(void*)
0x6c98  stfld    native int CRYPT_DATA_BLOB::pbData
0x6c9d  ldloca.s 6
0x6c9f  initobj  [mscorlib]System.IntPtr
0x6ca5  ldloca.s 5
0x6ca7  ldloca.s 6
0x6ca9  call     int32 System.Deployment.Internal.CodeSigning.Win32::_AxlPublicKeyBlobToPublicKeyToken([in] valuetype CRYPT_DATA_BLOB& pCspPublicKeyBlob, [in] [out] native int& ppwszPublicKeyToken)
0x6cae  stloc.s  7
0x6cb0  ldloc.s  7
0x6cb2  brfalse.s loc_6CBC
0x6cb4  ldloc.s  7
0x6cb6  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x6cbb  throw
0x6cbc  ldloc.s  6
0x6cbe  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringUni(native int)
0x6cc3  stloc.s  8
0x6cc5  call     native int System.Deployment.Internal.CodeSigning.Win32::GetProcessHeap()
0x6cca  ldc.i4.0
0x6ccb  ldloc.s  6
0x6ccd  call     bool System.Deployment.Internal.CodeSigning.Win32::HeapFree([hasfieldmarshal] native int, [in] unsigned int32 hHeap, [in] native int dwFlags)
0x6cd2  pop
0x6cd3  ldloc.1
0x6cd4  ldstr    aPublickeytoken// "publicKeyToken"
0x6cd9  ldloc.s  8
0x6cdb  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x6ce0  ldnull
0x6ce1  stloc.s  4
0x6ce3  ret
```
