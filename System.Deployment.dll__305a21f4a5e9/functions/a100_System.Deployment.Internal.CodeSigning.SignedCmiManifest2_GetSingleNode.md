# System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode

- ea: `0xa100`
- end: `0xa136`
- name: `System.Deployment.Internal.CodeSigning.SignedCmiManifest2::GetSingleNode`
- size: `54`
- prototype: ``
- caller_count: `20`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x7b40`
- `0x7c80`
- `0x7e60`
- `0x8470`
- `0x8620`
- `0x86e0`
- `0x8e10`
- `0x8f90`
- `0x8fe0`
- `0x90d0`
- `0x91d0`
- `0x92e0`
- `0x9490`
- `0x95b0`
- `0x9670`
- `0x97b0`
- `0x9900`
- `0x9a50`
- `0x9d20`
- `0x9ea0`

## callees

- `0xa100`

## pseudocode

```c

```

## disassembly

```asm
0xa100  ldarg.2
0xa101  brtrue.s loc_A10C
0xa103  ldarg.0
0xa104  ldarg.1
0xa105  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0xa10a  br.s     loc_A114
0xa10c  ldarg.0
0xa10d  ldarg.1
0xa10e  ldarg.2
0xa10f  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa114  stloc.0
0xa115  ldloc.0
0xa116  brtrue.s loc_A11A
0xa118  ldnull
0xa119  ret
0xa11a  ldloc.0
0xa11b  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0xa120  ldc.i4.1
0xa121  ble.s    loc_A12E
0xa123  ldc.i4   0x80096001
0xa128  newobj   instance void [mscorlib]System.Security.Cryptography.CryptographicException::.ctor(int32)
0xa12d  throw
0xa12e  ldloc.0
0xa12f  ldc.i4.0
0xa130  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0xa135  ret
```
