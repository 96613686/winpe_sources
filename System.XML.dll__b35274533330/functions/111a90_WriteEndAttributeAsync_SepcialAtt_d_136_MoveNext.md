# <WriteEndAttributeAsync_SepcialAtt>d__136::MoveNext

- ea: `0x111a90`
- end: `0x112607`
- name: `<WriteEndAttributeAsync_SepcialAtt>d__136::MoveNext`
- size: `2935`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config`

## callees

- `0x211b0`
- `0x21420`
- `0x21430`
- `0x21440`
- `0x3e110`
- `0x41210`
- `0x41220`
- `0x622f0`
- `0x62370`
- `0x110810`
- `0x110c10`
- `0x110ea0`
- `0x110f80`
- `0x111a90`

## string_xrefs

- `0x111ebf`: `http://www.w3.org/XML/1998/namespace`
- `0x1122e6`: `http://www.w3.org/XML/1998/namespace`
- `0x11246d`: `http://www.w3.org/XML/1998/namespace`
- `0x111d35`: `http://www.w3.org/2000/xmlns/`
- `0x111eb2`: `http://www.w3.org/2000/xmlns/`
- `0x1120fe`: `http://www.w3.org/2000/xmlns/`
- `0x111d30`: `xmlns`
- `0x1120f3`: `xmlns`
- `0x111ea1`: `Xml_PrefixForEmptyNs`
- `0x1122bc`: `Xml_InvalidXmlSpace`
- `0x111edd`: `Xml_CanNotBindToReservedNamespace`

## pseudocode

```c

```

## disassembly

```asm
0x111a90  ldarg.0
0x111a91  ldfld    int32 <WriteEndAttributeAsync_SepcialAtt>d__136::<>1__state
0x111a96  stloc.0
0x111a97  ldarg.0
0x111a98  ldfld    class System.Xml.XmlWellFormedWriter <WriteEndAttributeAsync_SepcialAtt>d__136::<>4__this
0x111a9d  stloc.1
0x111a9e  ldloc.0
0x111a9f  ldc.i4.s 0x13
0x111aa1  pop
0x111aa2  pop
0x111aa3  nop
0x111aa4  ldloc.0
0x111aa5  switch   loc_111BA4, loc_111C17, loc_111C84, loc_111CFC, loc_111D7D, loc_111DF0, loc_111E5D, loc_111F69, loc_111FDC, loc_11204A, loc_1120C4, loc_112147, loc_1121BB, loc_112229, loc_11232F, loc_1123A3, loc_112411, loc_1124B6, loc_11252A, loc_112595
0x111afa  ldloc.1
0x111afb  ldfld    valuetype SpecialAttribute System.Xml.XmlWellFormedWriter::specAttr
0x111b00  stloc.3
0x111b01  ldloc.3
0x111b02  ldc.i4.1
0x111b03  sub
0x111b04  switch   loc_111B1E, loc_111E8D, loc_112259, loc_11243A
0x111b19  br       loc_1125B9
0x111b1e  ldloc.1
0x111b1f  ldfld    class AttributeValueCache System.Xml.XmlWellFormedWriter::attrValueCache
0x111b24  callvirt instance string AttributeValueCache::get_StringValue()
0x111b29  stloc.2
0x111b2a  ldloc.1
0x111b2b  ldsfld   string [mscorlib]System.String::Empty
0x111b30  ldloc.2
0x111b31  call     instance bool System.Xml.XmlWellFormedWriter::PushNamespaceExplicit(string prefix, string ns)
0x111b36  brfalse  loc_111E81
0x111b3b  ldloc.1
0x111b3c  ldfld    class System.Xml.XmlRawWriter System.Xml.XmlWellFormedWriter::rawWriter
0x111b41  brfalse  loc_111D25
0x111b46  ldloc.1
0x111b47  ldfld    class System.Xml.XmlRawWriter System.Xml.XmlWellFormedWriter::rawWriter
0x111b4c  callvirt instance bool System.Xml.XmlRawWriter::get_SupportsNamespaceDeclarationInChunks()
0x111b51  brfalse  loc_111CAD
0x111b56  ldloc.1
0x111b57  ldfld    class System.Xml.XmlRawWriter System.Xml.XmlWellFormedWriter::rawWriter
0x111b5c  ldsfld   string [mscorlib]System.String::Empty
0x111b61  callvirt instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlRawWriter::WriteStartNamespaceDeclarationAsync(string prefix)
0x111b66  ldc.i4.0
0x111b67  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x111b6c  stloc.s  5
0x111b6e  ldloca.s 5
0x111b70  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x111b75  stloc.s  4
0x111b77  ldloca.s 4
0x111b79  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x111b7e  brtrue.s loc_111BC1
0x111b80  ldarg.0
0x111b81  ldc.i4.0
0x111b82  dup
0x111b83  stloc.0
0x111b84  stfld    int32 <WriteEndAttributeAsync_SepcialAtt>d__136::<>1__state
0x111b89  ldarg.0
0x111b8a  ldloc.s  4
0x111b8c  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteEndAttributeAsync_SepcialAtt>d__136::<>u__1
0x111b91  ldarg.0
0x111b92  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteEndAttributeAsync_SepcialAtt>d__136::<>t__builder
0x111b97  ldloca.s 4
0x111b99  ldarg.0
0x111b9a  call     T0x2B000263
0x111b9f  leave    loc_112606
0x111ba4  ldarg.0
0x111ba5  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteEndAttributeAsync_SepcialAtt>d__136::<>u__1
0x111baa  stloc.s  4
0x111bac  ldarg.0
0x111bad  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteEndAttributeAsync_SepcialAtt>d__136::<>u__1
0x111bb2  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x111bb8  ldarg.0
0x111bb9  ldc.i4.m1
0x111bba  dup
0x111bbb  stloc.0
0x111bbc  stfld    int32 <WriteEndAttributeAsync_SepcialAtt>d__136::<>1__state
0x111bc1  ldloca.s 4
0x111bc3  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x111bc8  ldloc.1
0x111bc9  ldfld    class AttributeValueCache System.Xml.XmlWellFormedWriter::attrValueCache
0x111bce  ldloc.1
0x111bcf  ldfld    class System.Xml.XmlRawWriter System.Xml.XmlWellFormedWriter::rawWriter
0x111bd4  callvirt instance class [mscorlib]System.Threading.Tasks.Task AttributeValueCache::ReplayAsync(class System.Xml.XmlWriter writer)
0x111bd9  ldc.i4.0
0x111bda  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x111bdf  stloc.s  5
0x111be1  ldloca.s 5
0x111be3  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x111be8  stloc.s  6
0x111bea  ldloca.s 6
0x111bec  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x111bf1  brtrue.s loc_111C34
0x111bf3  ldarg.0
0x111bf4  ldc.i4.1
0x111bf5  dup
0x111bf6  stloc.0
0x111bf7  stfld    int32 <WriteEndAttributeAsync_SepcialAtt>d__136::<>1__state
0x111bfc  ldarg.0
0x111bfd  ldloc.s  6
0x111bff  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteEndAttributeAsync_SepcialAtt>d__136::<>u__1
0x111c04  ldarg.0
0x111c05  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteEndAttributeAsync_SepcialAtt>d__136::<>t__builder
0x111c0a  ldloca.s 6
0x111c0c  ldarg.0
0x111c0d  call     T0x2B000263
0x111c12  leave    loc_112606
0x111c17  ldarg.0
0x111c18  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteEndAttributeAsync_SepcialAtt>d__136::<>u__1
0x111c1d  stloc.s  6
0x111c1f  ldarg.0
0x111c20  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteEndAttributeAsync_SepcialAtt>d__136::<>u__1
0x111c25  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x111c2b  ldarg.0
0x111c2c  ldc.i4.m1
0x111c2d  dup
0x111c2e  stloc.0
0x111c2f  stfld    int32 <WriteEndAttributeAsync_SepcialAtt>d__136::<>1__state
0x111c34  ldloca.s 6
0x111c36  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x111c3b  ldloc.1
0x111c3c  ldfld    class System.Xml.XmlRawWriter System.Xml.XmlWellFormedWriter::rawWriter
0x111c41  callvirt instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlRawWriter::WriteEndNamespaceDeclarationAsync()
0x111c46  ldc.i4.0
0x111c47  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x111c4c  stloc.s  5
0x111c4e  ldloca.s 5
0x111c50  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x111c55  stloc.s  7
0x111c57  ldloca.s 7
0x111c59  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x111c5e  brtrue.s loc_111CA1
0x111c60  ldarg.0
0x111c61  ldc.i4.2
0x111c62  dup
0x111c63  stloc.0
0x111c64  stfld    int32 <WriteEndAttributeAsync_SepcialAtt>d__136::<>1__state
0x111c69  ldarg.0
0x111c6a  ldloc.s  7
0x111c6c  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteEndAttributeAsync_SepcialAtt>d__136::<>u__1
0x111c71  ldarg.0
0x111c72  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteEndAttributeAsync_SepcialAtt>d__136::<>t__builder
0x111c77  ldloca.s 7
0x111c79  ldarg.0
0x111c7a  call     T0x2B000263
0x111c7f  leave    loc_112606
0x111c84  ldarg.0
0x111c85  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteEndAttributeAsync_SepcialAtt>d__136::<>u__1
0x111c8a  stloc.s  7
0x111c8c  ldarg.0
0x111c8d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteEndAttributeAsync_SepcialAtt>d__136::<>u__1
0x111c92  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x111c98  ldarg.0
0x111c99  ldc.i4.m1
0x111c9a  dup
0x111c9b  stloc.0
0x111c9c  stfld    int32 <WriteEndAttributeAsync_SepcialAtt>d__136::<>1__state
0x111ca1  ldloca.s 7
0x111ca3  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x111ca8  br       loc_111E81
0x111cad  ldloc.1
0x111cae  ldfld    class System.Xml.XmlRawWriter System.Xml.XmlWellFormedWriter::rawWriter
0x111cb3  ldsfld   string [mscorlib]System.String::Empty
0x111cb8  ldloc.2
0x111cb9  callvirt instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlRawWriter::WriteNamespaceDeclarationAsync(string prefix, string ns)
0x111cbe  ldc.i4.0
0x111cbf  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x111cc4  stloc.s  5
0x111cc6  ldloca.s 5
0x111cc8  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x111ccd  stloc.s  8
0x111ccf  ldloca.s 8
0x111cd1  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x111cd6  brtrue.s loc_111D19
0x111cd8  ldarg.0
0x111cd9  ldc.i4.3
0x111cda  dup
0x111cdb  stloc.0
0x111cdc  stfld    int32 <WriteEndAttributeAsync_SepcialAtt>d__136::<>1__state
0x111ce1  ldarg.0
0x111ce2  ldloc.s  8
0x111ce4  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteEndAttributeAsync_SepcialAtt>d__136::<>u__1
0x111ce9  ldarg.0
0x111cea  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteEndAttributeAsync_SepcialAtt>d__136::<>t__builder
0x111cef  ldloca.s 8
0x111cf1  ldarg.0
0x111cf2  call     T0x2B000263
0x111cf7  leave    loc_112606
0x111cfc  ldarg.0
0x111cfd  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteEndAttributeAsync_SepcialAtt>d__136::<>u__1
0x111d02  stloc.s  8
0x111d04  ldarg.0
0x111d05  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteEndAttributeAsync_SepcialAtt>d__136::<>u__1
0x111d0a  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x111d10  ldarg.0
0x111d11  ldc.i4.m1
0x111d12  dup
0x111d13  stloc.0
0x111d14  stfld    int32 <WriteEndAttributeAsync_SepcialAtt>d__136::<>1__state
0x111d19  ldloca.s 8
0x111d1b  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x111d20  br       loc_111E81
0x111d25  ldloc.1
0x111d26  ldfld    class System.Xml.XmlWriter System.Xml.XmlWellFormedWriter::writer
0x111d2b  ldsfld   string [mscorlib]System.String::Empty
0x111d30  ldstr    aXmlns// "xmlns"
0x111d35  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x111d3a  callvirt instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlWriter::WriteStartAttributeAsync(string prefix, string localName, string ns)
0x111d3f  ldc.i4.0
0x111d40  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x111d45  stloc.s  5
0x111d47  ldloca.s 5
0x111d49  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x111d4e  stloc.s  9
0x111d50  ldloca.s 9
0x111d52  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x111d57  brtrue.s loc_111D9A
0x111d59  ldarg.0
0x111d5a  ldc.i4.4
0x111d5b  dup
0x111d5c  stloc.0
0x111d5d  stfld    int32 <WriteEndAttributeAsync_SepcialAtt>d__136::<>1__state
0x111d62  ldarg.0
0x111d63  ldloc.s  9
0x111d65  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteEndAttributeAsync_SepcialAtt>d__136::<>u__1
0x111d6a  ldarg.0
0x111d6b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteEndAttributeAsync_SepcialAtt>d__136::<>t__builder
0x111d70  ldloca.s 9
0x111d72  ldarg.0
0x111d73  call     T0x2B000263
0x111d78  leave    loc_112606
0x111d7d  ldarg.0
0x111d7e  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteEndAttributeAsync_SepcialAtt>d__136::<>u__1
0x111d83  stloc.s  9
0x111d85  ldarg.0
0x111d86  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteEndAttributeAsync_SepcialAtt>d__136::<>u__1
0x111d8b  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x111d91  ldarg.0
0x111d92  ldc.i4.m1
0x111d93  dup
0x111d94  stloc.0
0x111d95  stfld    int32 <WriteEndAttributeAsync_SepcialAtt>d__136::<>1__state
0x111d9a  ldloca.s 9
0x111d9c  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x111da1  ldloc.1
0x111da2  ldfld    class AttributeValueCache System.Xml.XmlWellFormedWriter::attrValueCache
0x111da7  ldloc.1
0x111da8  ldfld    class System.Xml.XmlWriter System.Xml.XmlWellFormedWriter::writer
0x111dad  callvirt instance class [mscorlib]System.Threading.Tasks.Task AttributeValueCache::ReplayAsync(class System.Xml.XmlWriter writer)
0x111db2  ldc.i4.0
0x111db3  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x111db8  stloc.s  5
0x111dba  ldloca.s 5
0x111dbc  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x111dc1  stloc.s  0xA
0x111dc3  ldloca.s 0xA
0x111dc5  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x111dca  brtrue.s loc_111E0D
0x111dcc  ldarg.0
0x111dcd  ldc.i4.5
0x111dce  dup
0x111dcf  stloc.0
0x111dd0  stfld    int32 <WriteEndAttributeAsync_SepcialAtt>d__136::<>1__state
0x111dd5  ldarg.0
0x111dd6  ldloc.s  0xA
0x111dd8  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteEndAttributeAsync_SepcialAtt>d__136::<>u__1
0x111ddd  ldarg.0
0x111dde  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteEndAttributeAsync_SepcialAtt>d__136::<>t__builder
0x111de3  ldloca.s 0xA
0x111de5  ldarg.0
0x111de6  call     T0x2B000263
0x111deb  leave    loc_112606
0x111df0  ldarg.0
0x111df1  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteEndAttributeAsync_SepcialAtt>d__136::<>u__1
0x111df6  stloc.s  0xA
0x111df8  ldarg.0
0x111df9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteEndAttributeAsync_SepcialAtt>d__136::<>u__1
0x111dfe  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x111e04  ldarg.0
0x111e05  ldc.i4.m1
0x111e06  dup
0x111e07  stloc.0
0x111e08  stfld    int32 <WriteEndAttributeAsync_SepcialAtt>d__136::<>1__state
0x111e0d  ldloca.s 0xA
0x111e0f  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x111e14  ldloc.1
0x111e15  ldfld    class System.Xml.XmlWriter System.Xml.XmlWellFormedWriter::writer
0x111e1a  callvirt instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlWriter::WriteEndAttributeAsync()
0x111e1f  ldc.i4.0
0x111e20  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x111e25  stloc.s  5
0x111e27  ldloca.s 5
0x111e29  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x111e2e  stloc.s  0xB
0x111e30  ldloca.s 0xB
0x111e32  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x111e37  brtrue.s loc_111E7A
0x111e39  ldarg.0
0x111e3a  ldc.i4.6
0x111e3b  dup
0x111e3c  stloc.0
0x111e3d  stfld    int32 <WriteEndAttributeAsync_SepcialAtt>d__136::<>1__state
  ... truncated ...
```
