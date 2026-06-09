# System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifyPublicKeyToken

- ea: `0x92e0`
- end: `0x948f`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest2::VerifyPublicKeyToken`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7b40`

## callees

- `0x5e90`
- `0x5ea0`
- `0x5f00`
- `0x92e0`
- `0x97b0`
- `0xa070`
- `0xa100`

## string_xrefs

- `0x9307`: `http://www.w3.org/2000/09/xmldsig#`
- `0x92f7`: `urn:schemas-microsoft-com:asm.v1`

## pseudocode

```c

```

## disassembly

```asm
0x92e0  ldarg.0
0x92e1  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_manifestDom
0x92e6  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x92eb  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x92f0  stloc.0
0x92f1  ldloc.0
0x92f2  ldstr    aAsm// "asm"
0x92f7  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x92fc  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x9301  ldloc.0
0x9302  ldstr    aDs// "ds"
0x9307  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/09/xmldsig#"
0x930c  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x9311  ldarg.0
0x9312  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_manifestDom
0x9317  ldstr    aAsmAssemblyDsS_3// "asm:assembly/ds:Signature/ds:KeyInfo/ds"...
0x931c  ldloc.0
0x931d  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x9322  isinst   [System.Xml]System.Xml.XmlElement
0x9327  stloc.1
0x9328  ldarg.0
0x9329  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_manifestDom
0x932e  ldstr    aAsmAssemblyDsS_4// "asm:assembly/ds:Signature/ds:KeyInfo/ds"...
0x9333  ldloc.0
0x9334  call     class [System.Xml]System.Xml.XmlNode System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode(class [System.Xml]System.Xml.XmlNode parentNode, string xPath, [opt] class [System.Xml]System.Xml.XmlNamespaceManager namespaceManager)
0x9339  isinst   [System.Xml]System.Xml.XmlElement
0x933e  stloc.2
0x933f  ldloc.1
0x9340  brfalse.s loc_9345
0x9342  ldloc.2
0x9343  brtrue.s loc_9350
0x9345  ldc.i4   0x800B0003
0x934a  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x934f  throw
0x9350  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x9355  ldloc.1
0x9356  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x935b  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x9360  stloc.3
0x9361  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x9366  ldloc.2
0x9367  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x936c  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x9371  stloc.s  4
0x9373  ldarg.0
0x9374  ldfld    class [System.Xml]System.Xml.XmlDocument System.Deployment.Internal.CodeSigning.SignedCmiManifest2::m_manifestDom
0x9379  call     string System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetPublicKeyToken(class [System.Xml]System.Xml.XmlDocument manifestDom)
0x937e  stloc.s  5
0x9380  ldloc.s  5
0x9382  call     unsigned int8[] System.Deployment.Internal.CodeSigning.SignedCmiManifest2::HexStringToBytes(string hexString)
0x9387  stloc.s  6
0x9389  ldloc.3
0x938a  dup
0x938b  stloc.s  9
0x938d  brfalse.s loc_9395
0x938f  ldloc.s  9
0x9391  ldlen
0x9392  conv.i4
0x9393  brtrue.s loc_939B
0x9395  ldc.i4.0
0x9396  conv.u
0x9397  stloc.s  8
0x9399  br.s     loc_93A6
0x939b  ldloc.s  9
0x939d  ldc.i4.0
0x939e  ldelema  [mscorlib]System.Byte
0x93a3  conv.u
0x93a4  stloc.s  8
0x93a6  ldloc.s  4
0x93a8  dup
0x93a9  stloc.s  0xB
0x93ab  brfalse.s loc_93B3
0x93ad  ldloc.s  0xB
0x93af  ldlen
0x93b0  conv.i4
0x93b1  brtrue.s loc_93B9
0x93b3  ldc.i4.0
0x93b4  conv.u
0x93b5  stloc.s  0xA
0x93b7  br.s     loc_93C4
0x93b9  ldloc.s  0xB
0x93bb  ldc.i4.0
0x93bc  ldelema  [mscorlib]System.Byte
0x93c1  conv.u
0x93c2  stloc.s  0xA
0x93c4  ldloca.s 0xC
0x93c6  initobj  CRYPT_DATA_BLOB
0x93cc  ldloca.s 0xD
0x93ce  initobj  CRYPT_DATA_BLOB
0x93d4  ldloca.s 0xE
0x93d6  initobj  [mscorlib]System.IntPtr
0x93dc  ldloca.s 0xC
0x93de  ldloc.3
0x93df  ldlen
0x93e0  conv.i4
0x93e1  stfld    unsigned int32 CRYPT_DATA_BLOB::cbData
0x93e6  ldloca.s 0xC
0x93e8  ldloc.s  8
0x93ea  newobj   instance void [mscorlib]System.IntPtr::.ctor(void*)
0x93ef  stfld    native int CRYPT_DATA_BLOB::pbData
0x93f4  ldloca.s 0xD
0x93f6  ldloc.s  4
0x93f8  ldlen
0x93f9  conv.i4
0x93fa  stfld    unsigned int32 CRYPT_DATA_BLOB::cbData
0x93ff  ldloca.s 0xD
0x9401  ldloc.s  0xA
0x9403  newobj   instance void [mscorlib]System.IntPtr::.ctor(void*)
0x9408  stfld    native int CRYPT_DATA_BLOB::pbData
0x940d  ldloca.s 0xC
0x940f  ldloca.s 0xD
0x9411  ldloca.s 0xE
0x9413  call     int32 System.Deployment.Internal.CodeSigning.Win32::_AxlRSAKeyValueToPublicKeyToken([in] valuetype CRYPT_DATA_BLOB& pModulusBlob, [in] valuetype CRYPT_DATA_BLOB& pExponentBlob, [in] [out] native int& ppwszPublicKeyToken)
0x9418  stloc.s  0xF
0x941a  ldloc.s  0xF
0x941c  brfalse.s loc_9426
0x941e  ldloc.s  0xF
0x9420  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x9425  throw
0x9426  ldloc.s  0xE
0x9428  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringUni(native int)
0x942d  call     unsigned int8[] System.Deployment.Internal.CodeSigning.SignedCmiManifest2::HexStringToBytes(string hexString)
0x9432  stloc.s  7
0x9434  call     native int System.Deployment.Internal.CodeSigning.Win32::GetProcessHeap()
0x9439  ldc.i4.0
0x943a  ldloc.s  0xE
0x943c  call     bool System.Deployment.Internal.CodeSigning.Win32::HeapFree([hasfieldmarshal] native int, [in] unsigned int32 hHeap, [in] native int dwFlags)
0x9441  pop
0x9442  ldnull
0x9443  stloc.s  0xB
0x9445  ldnull
0x9446  stloc.s  9
0x9448  ldloc.s  6
0x944a  ldlen
0x944b  brfalse.s loc_9457
0x944d  ldloc.s  6
0x944f  ldlen
0x9450  conv.i4
0x9451  ldloc.s  7
0x9453  ldlen
0x9454  conv.i4
0x9455  beq.s    loc_9462
0x9457  ldc.i4   0x800B010B
0x945c  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x9461  throw
0x9462  ldc.i4.0
0x9463  stloc.s  0x10
0x9465  br.s     loc_9484
0x9467  ldloc.s  6
0x9469  ldloc.s  0x10
0x946b  ldelem.u1
0x946c  ldloc.s  7
0x946e  ldloc.s  0x10
0x9470  ldelem.u1
0x9471  beq.s    loc_947E
0x9473  ldc.i4   0x800B010B
0x9478  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0x947d  throw
0x947e  ldloc.s  0x10
0x9480  ldc.i4.1
0x9481  add
0x9482  stloc.s  0x10
0x9484  ldloc.s  0x10
0x9486  ldloc.s  6
0x9488  ldlen
0x9489  conv.i4
0x948a  blt.s    loc_9467
0x948c  ldloc.s  5
0x948e  ret
```
