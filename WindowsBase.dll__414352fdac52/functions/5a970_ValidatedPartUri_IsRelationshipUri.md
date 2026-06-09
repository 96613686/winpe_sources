# ValidatedPartUri::IsRelationshipUri

- ea: `0x5a970`
- end: `0x5aa1c`
- name: `ValidatedPartUri::IsRelationshipUri`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x5a940`

## callees

- `0x2c100`
- `0x4a7c0`
- `0x5a8d0`
- `0x5a970`

## string_xrefs

- `0x5aa0a`: `NotAValidRelationshipPartUri`

## pseudocode

```c

```

## disassembly

```asm
0x5a970  ldc.i4.0
0x5a971  stloc.0
0x5a972  ldarg.0
0x5a973  call     instance string ValidatedPartUri::get_NormalizedPartUriString()
0x5a978  ldsfld   string ValidatedPartUri::_relationshipPartUpperCaseExtension
0x5a97d  ldc.i4.4
0x5a97e  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x5a983  brtrue.s loc_5A987
0x5a985  ldc.i4.0
0x5a986  ret
0x5a987  ldsfld   class [System]System.Uri ValidatedPartUri::_containerRelationshipNormalizedPartUri
0x5a98c  ldarg.0
0x5a98d  call     int32 System.IO.Packaging.PackUriHelper::ComparePartUri(class [System]System.Uri firstPartUri, class [System]System.Uri secondPartUri)
0x5a992  brtrue.s loc_5A996
0x5a994  ldc.i4.1
0x5a995  ret
0x5a996  ldarg.0
0x5a997  call     instance string ValidatedPartUri::get_NormalizedPartUriString()
0x5a99c  ldsfld   char[] ValidatedPartUri::_forwardSlashSeparator
0x5a9a1  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x5a9a6  stloc.1
0x5a9a7  ldloc.1
0x5a9a8  ldlen
0x5a9a9  conv.i4
0x5a9aa  ldc.i4.3
0x5a9ab  blt.s    loc_5A9DA
0x5a9ad  ldloc.1
0x5a9ae  ldloc.1
0x5a9af  ldlen
0x5a9b0  conv.i4
0x5a9b1  ldc.i4.1
0x5a9b2  sub
0x5a9b3  ldelem.ref
0x5a9b4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x5a9b9  ldsfld   string System.IO.Packaging.PackUriHelper::_relationshipPartExtensionName
0x5a9be  callvirt instance int32 [mscorlib]System.String::get_Length()
0x5a9c3  ble.s    loc_5A9DA
0x5a9c5  ldloc.1
0x5a9c6  ldloc.1
0x5a9c7  ldlen
0x5a9c8  conv.i4
0x5a9c9  ldc.i4.2
0x5a9ca  sub
0x5a9cb  ldelem.ref
0x5a9cc  ldsfld   string ValidatedPartUri::_relationshipPartUpperCaseSegmentName
0x5a9d1  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x5a9d6  ldc.i4.0
0x5a9d7  ceq
0x5a9d9  stloc.0
0x5a9da  ldloc.1
0x5a9db  ldlen
0x5a9dc  conv.i4
0x5a9dd  ldc.i4.3
0x5a9de  ble.s    loc_5AA1A
0x5a9e0  ldloc.0
0x5a9e1  brfalse.s loc_5AA1A
0x5a9e3  ldloc.1
0x5a9e4  ldloc.1
0x5a9e5  ldlen
0x5a9e6  conv.i4
0x5a9e7  ldc.i4.1
0x5a9e8  sub
0x5a9e9  ldelem.ref
0x5a9ea  ldsfld   string ValidatedPartUri::_relsrelsUpperCaseExtension
0x5a9ef  ldc.i4.4
0x5a9f0  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x5a9f5  brfalse.s loc_5AA1A
0x5a9f7  ldloc.1
0x5a9f8  ldloc.1
0x5a9f9  ldlen
0x5a9fa  conv.i4
0x5a9fb  ldc.i4.3
0x5a9fc  sub
0x5a9fd  ldelem.ref
0x5a9fe  ldsfld   string ValidatedPartUri::_relationshipPartUpperCaseSegmentName
0x5aa03  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x5aa08  brtrue.s loc_5AA1A
0x5aa0a  ldstr    aNotavalidrelat// "NotAValidRelationshipPartUri"
0x5aa0f  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x5aa14  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x5aa19  throw
0x5aa1a  ldloc.0
0x5aa1b  ret
```
