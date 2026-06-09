# <WriteProcessingInstructionAsync>d__139::MoveNext

- ea: `0x112900`
- end: `0x112c41`
- name: `<WriteProcessingInstructionAsync>d__139::MoveNext`
- size: `833`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x21390`
- `0x3e890`
- `0x3fb50`
- `0x41250`
- `0x62370`
- `0x112900`

## string_xrefs

- `0x112942`: `Xml_EmptyName`
- `0x1129b0`: `Xml_DupXmlDecl`
- `0x1129a9`: `Xml_CannotWriteXmlDecl`

## pseudocode

```c

```

## disassembly

```asm
0x112900  ldarg.0
0x112901  ldfld    int32 <WriteProcessingInstructionAsync>d__139::<>1__state
0x112906  stloc.0
0x112907  ldarg.0
0x112908  ldfld    class System.Xml.XmlWellFormedWriter <WriteProcessingInstructionAsync>d__139::<>4__this
0x11290d  stloc.1
0x11290e  ldloc.0
0x11290f  ldc.i4.4
0x112910  pop
0x112911  pop
0x112912  nop
0x112913  ldloc.0
0x112914  switch   loc_112A09, loc_112A82, loc_112AFF, loc_112B6C, loc_112BE1
0x11292d  ldarg.0
0x11292e  ldfld    string <WriteProcessingInstructionAsync>d__139::name
0x112933  brfalse.s loc_112942
0x112935  ldarg.0
0x112936  ldfld    string <WriteProcessingInstructionAsync>d__139::name
0x11293b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x112940  brtrue.s loc_112952
0x112942  ldstr    aXmlEmptyname// "Xml_EmptyName"
0x112947  call     string System.Xml.Res::GetString(string name)
0x11294c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x112951  throw
0x112952  ldloc.1
0x112953  ldarg.0
0x112954  ldfld    string <WriteProcessingInstructionAsync>d__139::name
0x112959  call     instance void System.Xml.XmlWellFormedWriter::CheckNCName(string ncname)
0x11295e  ldarg.0
0x11295f  ldfld    string <WriteProcessingInstructionAsync>d__139::text
0x112964  brtrue.s loc_112971
0x112966  ldarg.0
0x112967  ldsfld   string [mscorlib]System.String::Empty
0x11296c  stfld    string <WriteProcessingInstructionAsync>d__139::text
0x112971  ldarg.0
0x112972  ldfld    string <WriteProcessingInstructionAsync>d__139::name
0x112977  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11297c  ldc.i4.3
0x11297d  bne.un   loc_112B28
0x112982  ldarg.0
0x112983  ldfld    string <WriteProcessingInstructionAsync>d__139::name
0x112988  ldstr    aXml// "xml"
0x11298d  ldc.i4.5
0x11298e  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x112993  brtrue   loc_112B28
0x112998  ldloc.1
0x112999  ldfld    valuetype State System.Xml.XmlWellFormedWriter::currentState
0x11299e  brfalse.s loc_1129C0
0x1129a0  ldloc.1
0x1129a1  ldfld    valuetype System.Xml.ConformanceLevel System.Xml.XmlWellFormedWriter::conformanceLevel
0x1129a6  ldc.i4.2
0x1129a7  beq.s    loc_1129B0
0x1129a9  ldstr    aXmlCannotwrite// "Xml_CannotWriteXmlDecl"
0x1129ae  br.s     loc_1129B5
0x1129b0  ldstr    aXmlDupxmldecl// "Xml_DupXmlDecl"
0x1129b5  call     string System.Xml.Res::GetString(string name)
0x1129ba  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1129bf  throw
0x1129c0  ldloc.1
0x1129c1  ldc.i4.1
0x1129c2  stfld    bool System.Xml.XmlWellFormedWriter::xmlDeclFollows
0x1129c7  ldloc.1
0x1129c8  ldc.i4.2
0x1129c9  call     instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlWellFormedWriter::AdvanceStateAsync(valuetype Token token)
0x1129ce  ldc.i4.0
0x1129cf  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x1129d4  stloc.3
0x1129d5  ldloca.s 3
0x1129d7  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x1129dc  stloc.2
0x1129dd  ldloca.s 2
0x1129df  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x1129e4  brtrue.s loc_112A25
0x1129e6  ldarg.0
0x1129e7  ldc.i4.0
0x1129e8  dup
0x1129e9  stloc.0
0x1129ea  stfld    int32 <WriteProcessingInstructionAsync>d__139::<>1__state
0x1129ef  ldarg.0
0x1129f0  ldloc.2
0x1129f1  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteProcessingInstructionAsync>d__139::<>u__1
0x1129f6  ldarg.0
0x1129f7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteProcessingInstructionAsync>d__139::<>t__builder
0x1129fc  ldloca.s 2
0x1129fe  ldarg.0
0x1129ff  call     T0x2B000266
0x112a04  leave    loc_112C40
0x112a09  ldarg.0
0x112a0a  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteProcessingInstructionAsync>d__139::<>u__1
0x112a0f  stloc.2
0x112a10  ldarg.0
0x112a11  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteProcessingInstructionAsync>d__139::<>u__1
0x112a16  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x112a1c  ldarg.0
0x112a1d  ldc.i4.m1
0x112a1e  dup
0x112a1f  stloc.0
0x112a20  stfld    int32 <WriteProcessingInstructionAsync>d__139::<>1__state
0x112a25  ldloca.s 2
0x112a27  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x112a2c  ldloc.1
0x112a2d  ldfld    class System.Xml.XmlRawWriter System.Xml.XmlWellFormedWriter::rawWriter
0x112a32  brfalse.s loc_112AAB
0x112a34  ldloc.1
0x112a35  ldfld    class System.Xml.XmlRawWriter System.Xml.XmlWellFormedWriter::rawWriter
0x112a3a  ldarg.0
0x112a3b  ldfld    string <WriteProcessingInstructionAsync>d__139::text
0x112a40  callvirt instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlRawWriter::WriteXmlDeclarationAsync(string xmldecl)
0x112a45  ldc.i4.0
0x112a46  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x112a4b  stloc.3
0x112a4c  ldloca.s 3
0x112a4e  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x112a53  stloc.s  4
0x112a55  ldloca.s 4
0x112a57  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x112a5c  brtrue.s loc_112A9F
0x112a5e  ldarg.0
0x112a5f  ldc.i4.1
0x112a60  dup
0x112a61  stloc.0
0x112a62  stfld    int32 <WriteProcessingInstructionAsync>d__139::<>1__state
0x112a67  ldarg.0
0x112a68  ldloc.s  4
0x112a6a  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteProcessingInstructionAsync>d__139::<>u__1
0x112a6f  ldarg.0
0x112a70  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteProcessingInstructionAsync>d__139::<>t__builder
0x112a75  ldloca.s 4
0x112a77  ldarg.0
0x112a78  call     T0x2B000266
0x112a7d  leave    loc_112C40
0x112a82  ldarg.0
0x112a83  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteProcessingInstructionAsync>d__139::<>u__1
0x112a88  stloc.s  4
0x112a8a  ldarg.0
0x112a8b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteProcessingInstructionAsync>d__139::<>u__1
0x112a90  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x112a96  ldarg.0
0x112a97  ldc.i4.m1
0x112a98  dup
0x112a99  stloc.0
0x112a9a  stfld    int32 <WriteProcessingInstructionAsync>d__139::<>1__state
0x112a9f  ldloca.s 4
0x112aa1  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x112aa6  br       loc_112C05
0x112aab  ldloc.1
0x112aac  ldfld    class System.Xml.XmlWriter System.Xml.XmlWellFormedWriter::writer
0x112ab1  ldarg.0
0x112ab2  ldfld    string <WriteProcessingInstructionAsync>d__139::name
0x112ab7  ldarg.0
0x112ab8  ldfld    string <WriteProcessingInstructionAsync>d__139::text
0x112abd  callvirt instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlWriter::WriteProcessingInstructionAsync(string name, string text)
0x112ac2  ldc.i4.0
0x112ac3  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x112ac8  stloc.3
0x112ac9  ldloca.s 3
0x112acb  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x112ad0  stloc.s  5
0x112ad2  ldloca.s 5
0x112ad4  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x112ad9  brtrue.s loc_112B1C
0x112adb  ldarg.0
0x112adc  ldc.i4.2
0x112add  dup
0x112ade  stloc.0
0x112adf  stfld    int32 <WriteProcessingInstructionAsync>d__139::<>1__state
0x112ae4  ldarg.0
0x112ae5  ldloc.s  5
0x112ae7  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteProcessingInstructionAsync>d__139::<>u__1
0x112aec  ldarg.0
0x112aed  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteProcessingInstructionAsync>d__139::<>t__builder
0x112af2  ldloca.s 5
0x112af4  ldarg.0
0x112af5  call     T0x2B000266
0x112afa  leave    loc_112C40
0x112aff  ldarg.0
0x112b00  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteProcessingInstructionAsync>d__139::<>u__1
0x112b05  stloc.s  5
0x112b07  ldarg.0
0x112b08  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteProcessingInstructionAsync>d__139::<>u__1
0x112b0d  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x112b13  ldarg.0
0x112b14  ldc.i4.m1
0x112b15  dup
0x112b16  stloc.0
0x112b17  stfld    int32 <WriteProcessingInstructionAsync>d__139::<>1__state
0x112b1c  ldloca.s 5
0x112b1e  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x112b23  br       loc_112C05
0x112b28  ldloc.1
0x112b29  ldc.i4.2
0x112b2a  call     instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlWellFormedWriter::AdvanceStateAsync(valuetype Token token)
0x112b2f  ldc.i4.0
0x112b30  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x112b35  stloc.3
0x112b36  ldloca.s 3
0x112b38  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x112b3d  stloc.s  6
0x112b3f  ldloca.s 6
0x112b41  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x112b46  brtrue.s loc_112B89
0x112b48  ldarg.0
0x112b49  ldc.i4.3
0x112b4a  dup
0x112b4b  stloc.0
0x112b4c  stfld    int32 <WriteProcessingInstructionAsync>d__139::<>1__state
0x112b51  ldarg.0
0x112b52  ldloc.s  6
0x112b54  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteProcessingInstructionAsync>d__139::<>u__1
0x112b59  ldarg.0
0x112b5a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteProcessingInstructionAsync>d__139::<>t__builder
0x112b5f  ldloca.s 6
0x112b61  ldarg.0
0x112b62  call     T0x2B000266
0x112b67  leave    loc_112C40
0x112b6c  ldarg.0
0x112b6d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteProcessingInstructionAsync>d__139::<>u__1
0x112b72  stloc.s  6
0x112b74  ldarg.0
0x112b75  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteProcessingInstructionAsync>d__139::<>u__1
0x112b7a  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x112b80  ldarg.0
0x112b81  ldc.i4.m1
0x112b82  dup
0x112b83  stloc.0
0x112b84  stfld    int32 <WriteProcessingInstructionAsync>d__139::<>1__state
0x112b89  ldloca.s 6
0x112b8b  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x112b90  ldloc.1
0x112b91  ldfld    class System.Xml.XmlWriter System.Xml.XmlWellFormedWriter::writer
0x112b96  ldarg.0
0x112b97  ldfld    string <WriteProcessingInstructionAsync>d__139::name
0x112b9c  ldarg.0
0x112b9d  ldfld    string <WriteProcessingInstructionAsync>d__139::text
0x112ba2  callvirt instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlWriter::WriteProcessingInstructionAsync(string name, string text)
0x112ba7  ldc.i4.0
0x112ba8  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x112bad  stloc.3
0x112bae  ldloca.s 3
0x112bb0  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x112bb5  stloc.s  7
0x112bb7  ldloca.s 7
0x112bb9  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x112bbe  brtrue.s loc_112BFE
0x112bc0  ldarg.0
0x112bc1  ldc.i4.4
0x112bc2  dup
0x112bc3  stloc.0
0x112bc4  stfld    int32 <WriteProcessingInstructionAsync>d__139::<>1__state
0x112bc9  ldarg.0
0x112bca  ldloc.s  7
0x112bcc  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteProcessingInstructionAsync>d__139::<>u__1
0x112bd1  ldarg.0
0x112bd2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteProcessingInstructionAsync>d__139::<>t__builder
0x112bd7  ldloca.s 7
0x112bd9  ldarg.0
0x112bda  call     T0x2B000266
0x112bdf  leave.s  loc_112C40
0x112be1  ldarg.0
0x112be2  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteProcessingInstructionAsync>d__139::<>u__1
0x112be7  stloc.s  7
0x112be9  ldarg.0
0x112bea  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteProcessingInstructionAsync>d__139::<>u__1
0x112bef  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x112bf5  ldarg.0
0x112bf6  ldc.i4.m1
0x112bf7  dup
0x112bf8  stloc.0
0x112bf9  stfld    int32 <WriteProcessingInstructionAsync>d__139::<>1__state
0x112bfe  ldloca.s 7
0x112c00  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x112c05  leave.s  loc_112C12
0x112c07  pop
0x112c08  ldloc.1
0x112c09  ldc.i4.s 0x10
0x112c0b  stfld    valuetype State System.Xml.XmlWellFormedWriter::currentState
0x112c10  rethrow
0x112c12  leave.s  loc_112C2D
0x112c14  stloc.s  8
0x112c16  ldarg.0
0x112c17  ldc.i4.s 0xFE
0x112c19  stfld    int32 <WriteProcessingInstructionAsync>d__139::<>1__state
0x112c1e  ldarg.0
0x112c1f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteProcessingInstructionAsync>d__139::<>t__builder
0x112c24  ldloc.s  8
0x112c26  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x112c2b  leave.s  loc_112C40
0x112c2d  ldarg.0
0x112c2e  ldc.i4.s 0xFE
0x112c30  stfld    int32 <WriteProcessingInstructionAsync>d__139::<>1__state
0x112c35  ldarg.0
0x112c36  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteProcessingInstructionAsync>d__139::<>t__builder
0x112c3b  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x112c40  ret
```
