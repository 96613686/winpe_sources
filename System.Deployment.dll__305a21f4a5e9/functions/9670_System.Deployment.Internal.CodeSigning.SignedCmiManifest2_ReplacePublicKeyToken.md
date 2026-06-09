# System.Deployment.Internal.CodeSigning.SignedCmiManifest2::ReplacePublicKeyToken

- ea: `0x9670`
- end: `0x97a1`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest2::ReplacePublicKeyToken`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7a80`

## callees

- `0x5e90`
- `0x5ea0`
- `0x5f10`
- `0x9600`
- `0x9670`
- `0xa100`

## string_xrefs

- `0x9682`: `urn:schemas-microsoft-com:asm.v1`
- `0x96ad`: `publicKeyToken`
- `0x9791`: `publicKeyToken`

## pseudocode

```c

```

## disassembly

```asm
0x9670  ldarg.0
0x9671  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x9676  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x967b  stloc.0
0x967c  ldloc.0
0x967d  ldstr    aAsm// "asm"
0x9682  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x9687  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x968c  ldarg.0
0x968d  ldstr    aAsmAssemblyAsm// "asm:assembly/asm:assemblyIdentity"
0x9692  ldloc.0
0x9693  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x9698  isinst   [System.Xml]System.Xml.XmlElement
0x969d  stloc.1
0x969e  ldloc.1
0x969f  brtrue.s loc_96AC
0x96a1  ldc.i4   0x800B0003
0x96a6  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x96ab  throw
0x96ac  ldloc.1
0x96ad  ldstr    aPublickeytoken// "publicKeyToken"
0x96b2  callvirt instance bool [System.Xml]System.Xml.XmlElement::HasAttribute(string)
0x96b7  brtrue.s loc_96C4
0x96b9  ldc.i4   0x800B0003
0x96be  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x96c3  throw
0x96c4  ldarg.1
0x96c5  isinst   [mscorlib]System.Security.Cryptography.RSACryptoServiceProvider
0x96ca  brfalse.s loc_96F1
0x96cc  ldarg.1
0x96cd  castclass [mscorlib]System.Security.Cryptography.RSACryptoServiceProvider
0x96d2  ldarg.2
0x96d3  call     class [mscorlib]System.Security.Cryptography.RSACryptoServiceProvider System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetFixedRSACryptoServiceProvider(class [mscorlib]System.Security.Cryptography.RSACryptoServiceProvider oldCsp, bool useSha256)
0x96d8  ldc.i4.0
0x96d9  callvirt instance unsigned int8[] [mscorlib]System.Security.Cryptography.RSACryptoServiceProvider::ExportCspBlob(bool)
0x96de  stloc.2
0x96df  ldloc.2
0x96e0  brfalse.s loc_96E6
0x96e2  ldloc.2
0x96e3  ldlen
0x96e4  brtrue.s loc_971D
0x96e6  ldc.i4   0x80090003
0x96eb  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x96f0  throw
0x96f1  newobj   instance void [mscorlib]System.Security.Cryptography.RSACryptoServiceProvider::.ctor()
0x96f6  stloc.3
0x96f7  ldloc.3
0x96f8  ldarg.1
0x96f9  castclass [mscorlib]System.Security.Cryptography.RSA
0x96fe  ldc.i4.0
0x96ff  callvirt instance valuetype [mscorlib]System.Security.Cryptography.RSAParameters [mscorlib]System.Security.Cryptography.RSA::ExportParameters(bool)
0x9704  callvirt instance void [mscorlib]System.Security.Cryptography.RSA::ImportParameters(valuetype [mscorlib]System.Security.Cryptography.RSAParameters)
0x9709  ldloc.3
0x970a  ldc.i4.0
0x970b  callvirt instance unsigned int8[] [mscorlib]System.Security.Cryptography.RSACryptoServiceProvider::ExportCspBlob(bool)
0x9710  stloc.2
0x9711  leave.s  loc_971D
0x9713  ldloc.3
0x9714  brfalse.s loc_971C
0x9716  ldloc.3
0x9717  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x971c  endfinally
0x971d  ldloc.2
0x971e  dup
0x971f  stloc.s  5
0x9721  brfalse.s loc_9729
0x9723  ldloc.s  5
0x9725  ldlen
0x9726  conv.i4
0x9727  brtrue.s loc_972F
0x9729  ldc.i4.0
0x972a  conv.u
0x972b  stloc.s  4
0x972d  br.s     loc_973A
0x972f  ldloc.s  5
0x9731  ldc.i4.0
0x9732  ldelema  [mscorlib]System.Byte
0x9737  conv.u
0x9738  stloc.s  4
0x973a  ldloca.s 6
0x973c  initobj  CRYPT_DATA_BLOB
0x9742  ldloca.s 6
0x9744  ldloc.2
0x9745  ldlen
0x9746  conv.i4
0x9747  stfld    unsigned int32 CRYPT_DATA_BLOB::cbData
0x974c  ldloca.s 6
0x974e  ldloc.s  4
0x9750  newobj   instance void [mscorlib]System.IntPtr::.ctor(void*)
0x9755  stfld    native int CRYPT_DATA_BLOB::pbData
0x975a  ldloca.s 7
0x975c  initobj  [mscorlib]System.IntPtr
0x9762  ldloca.s 6
0x9764  ldloca.s 7
0x9766  call     int32 System.Deployment.Internal.CodeSigning.Win32::_AxlPublicKeyBlobToPublicKeyToken([in] valuetype CRYPT_DATA_BLOB& pCspPublicKeyBlob, [in] [out] native int& ppwszPublicKeyToken)
0x976b  stloc.s  8
0x976d  ldloc.s  8
0x976f  brfalse.s loc_9779
0x9771  ldloc.s  8
0x9773  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x9778  throw
0x9779  ldloc.s  7
0x977b  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringUni(native int)
0x9780  stloc.s  9
0x9782  call     native int System.Deployment.Internal.CodeSigning.Win32::GetProcessHeap()
0x9787  ldc.i4.0
0x9788  ldloc.s  7
0x978a  call     bool System.Deployment.Internal.CodeSigning.Win32::HeapFree([hasfieldmarshal] native int, [in] unsigned int32 hHeap, [in] native int dwFlags)
0x978f  pop
0x9790  ldloc.1
0x9791  ldstr    aPublickeytoken// "publicKeyToken"
0x9796  ldloc.s  9
0x9798  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x979d  ldnull
0x979e  stloc.s  5
0x97a0  ret
```
