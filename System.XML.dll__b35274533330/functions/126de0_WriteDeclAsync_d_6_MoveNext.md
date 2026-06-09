# <WriteDeclAsync>d__6::MoveNext

- ea: `0x126de0`
- end: `0x1270af`
- name: `<WriteDeclAsync>d__6::MoveNext`
- size: `719`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x21420`
- `0x41210`
- `0x41220`
- `0x41290`
- `0x126de0`

## string_xrefs

- `0x126eb2`: `http://www.w3.org/2000/xmlns/`
- `0x126f35`: `http://www.w3.org/2000/xmlns/`
- `0x126ead`: `xmlns`
- `0x126f25`: `xmlns`

## pseudocode

```c

```

## disassembly

```asm
0x126de0  ldarg.0
0x126de1  ldfld    int32 <WriteDeclAsync>d__6::<>1__state
0x126de6  stloc.0
0x126de7  ldloc.0
0x126de8  switch   loc_126E68, loc_126EF7, loc_126F7C, loc_126FF3, loc_12705C
0x126e01  ldarg.0
0x126e02  ldfld    class System.Xml.XmlRawWriter <WriteDeclAsync>d__6::rawWriter
0x126e07  brfalse  loc_126E90
0x126e0c  ldarg.0
0x126e0d  ldfld    class System.Xml.XmlRawWriter <WriteDeclAsync>d__6::rawWriter
0x126e12  ldarg.0
0x126e13  ldflda   valuetype Namespace <WriteDeclAsync>d__6::<>4__this
0x126e18  ldfld    string Namespace::prefix
0x126e1d  ldarg.0
0x126e1e  ldflda   valuetype Namespace <WriteDeclAsync>d__6::<>4__this
0x126e23  ldfld    string Namespace::namespaceUri
0x126e28  callvirt instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlRawWriter::WriteNamespaceDeclarationAsync(string prefix, string ns)
0x126e2d  ldc.i4.0
0x126e2e  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x126e33  stloc.2
0x126e34  ldloca.s 2
0x126e36  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x126e3b  stloc.1
0x126e3c  ldloca.s 1
0x126e3e  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x126e43  brtrue.s loc_126E84
0x126e45  ldarg.0
0x126e46  ldc.i4.0
0x126e47  dup
0x126e48  stloc.0
0x126e49  stfld    int32 <WriteDeclAsync>d__6::<>1__state
0x126e4e  ldarg.0
0x126e4f  ldloc.1
0x126e50  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteDeclAsync>d__6::<>u__1
0x126e55  ldarg.0
0x126e56  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteDeclAsync>d__6::<>t__builder
0x126e5b  ldloca.s 1
0x126e5d  ldarg.0
0x126e5e  call     T0x2B0002E0
0x126e63  leave    loc_1270AE
0x126e68  ldarg.0
0x126e69  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteDeclAsync>d__6::<>u__1
0x126e6e  stloc.1
0x126e6f  ldarg.0
0x126e70  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteDeclAsync>d__6::<>u__1
0x126e75  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x126e7b  ldarg.0
0x126e7c  ldc.i4.m1
0x126e7d  dup
0x126e7e  stloc.0
0x126e7f  stfld    int32 <WriteDeclAsync>d__6::<>1__state
0x126e84  ldloca.s 1
0x126e86  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x126e8b  br       loc_127080
0x126e90  ldarg.0
0x126e91  ldflda   valuetype Namespace <WriteDeclAsync>d__6::<>4__this
0x126e96  ldfld    string Namespace::prefix
0x126e9b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x126ea0  brtrue.s loc_126F1F
0x126ea2  ldarg.0
0x126ea3  ldfld    class System.Xml.XmlWriter <WriteDeclAsync>d__6::writer
0x126ea8  ldsfld   string [mscorlib]System.String::Empty
0x126ead  ldstr    aXmlns// "xmlns"
0x126eb2  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x126eb7  callvirt instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlWriter::WriteStartAttributeAsync(string prefix, string localName, string ns)
0x126ebc  ldc.i4.0
0x126ebd  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x126ec2  stloc.2
0x126ec3  ldloca.s 2
0x126ec5  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x126eca  stloc.3
0x126ecb  ldloca.s 3
0x126ecd  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x126ed2  brtrue.s loc_126F13
0x126ed4  ldarg.0
0x126ed5  ldc.i4.1
0x126ed6  dup
0x126ed7  stloc.0
0x126ed8  stfld    int32 <WriteDeclAsync>d__6::<>1__state
0x126edd  ldarg.0
0x126ede  ldloc.3
0x126edf  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteDeclAsync>d__6::<>u__1
0x126ee4  ldarg.0
0x126ee5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteDeclAsync>d__6::<>t__builder
0x126eea  ldloca.s 3
0x126eec  ldarg.0
0x126eed  call     T0x2B0002E0
0x126ef2  leave    loc_1270AE
0x126ef7  ldarg.0
0x126ef8  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteDeclAsync>d__6::<>u__1
0x126efd  stloc.3
0x126efe  ldarg.0
0x126eff  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteDeclAsync>d__6::<>u__1
0x126f04  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x126f0a  ldarg.0
0x126f0b  ldc.i4.m1
0x126f0c  dup
0x126f0d  stloc.0
0x126f0e  stfld    int32 <WriteDeclAsync>d__6::<>1__state
0x126f13  ldloca.s 3
0x126f15  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x126f1a  br       loc_126FA0
0x126f1f  ldarg.0
0x126f20  ldfld    class System.Xml.XmlWriter <WriteDeclAsync>d__6::writer
0x126f25  ldstr    aXmlns// "xmlns"
0x126f2a  ldarg.0
0x126f2b  ldflda   valuetype Namespace <WriteDeclAsync>d__6::<>4__this
0x126f30  ldfld    string Namespace::prefix
0x126f35  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2000/xmlns/"
0x126f3a  callvirt instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlWriter::WriteStartAttributeAsync(string prefix, string localName, string ns)
0x126f3f  ldc.i4.0
0x126f40  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x126f45  stloc.2
0x126f46  ldloca.s 2
0x126f48  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x126f4d  stloc.s  4
0x126f4f  ldloca.s 4
0x126f51  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x126f56  brtrue.s loc_126F99
0x126f58  ldarg.0
0x126f59  ldc.i4.2
0x126f5a  dup
0x126f5b  stloc.0
0x126f5c  stfld    int32 <WriteDeclAsync>d__6::<>1__state
0x126f61  ldarg.0
0x126f62  ldloc.s  4
0x126f64  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteDeclAsync>d__6::<>u__1
0x126f69  ldarg.0
0x126f6a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteDeclAsync>d__6::<>t__builder
0x126f6f  ldloca.s 4
0x126f71  ldarg.0
0x126f72  call     T0x2B0002E0
0x126f77  leave    loc_1270AE
0x126f7c  ldarg.0
0x126f7d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteDeclAsync>d__6::<>u__1
0x126f82  stloc.s  4
0x126f84  ldarg.0
0x126f85  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteDeclAsync>d__6::<>u__1
0x126f8a  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x126f90  ldarg.0
0x126f91  ldc.i4.m1
0x126f92  dup
0x126f93  stloc.0
0x126f94  stfld    int32 <WriteDeclAsync>d__6::<>1__state
0x126f99  ldloca.s 4
0x126f9b  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x126fa0  ldarg.0
0x126fa1  ldfld    class System.Xml.XmlWriter <WriteDeclAsync>d__6::writer
0x126fa6  ldarg.0
0x126fa7  ldflda   valuetype Namespace <WriteDeclAsync>d__6::<>4__this
0x126fac  ldfld    string Namespace::namespaceUri
0x126fb1  callvirt instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlWriter::WriteStringAsync(string text)
0x126fb6  ldc.i4.0
0x126fb7  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x126fbc  stloc.2
0x126fbd  ldloca.s 2
0x126fbf  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x126fc4  stloc.s  5
0x126fc6  ldloca.s 5
0x126fc8  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x126fcd  brtrue.s loc_127010
0x126fcf  ldarg.0
0x126fd0  ldc.i4.3
0x126fd1  dup
0x126fd2  stloc.0
0x126fd3  stfld    int32 <WriteDeclAsync>d__6::<>1__state
0x126fd8  ldarg.0
0x126fd9  ldloc.s  5
0x126fdb  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteDeclAsync>d__6::<>u__1
0x126fe0  ldarg.0
0x126fe1  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteDeclAsync>d__6::<>t__builder
0x126fe6  ldloca.s 5
0x126fe8  ldarg.0
0x126fe9  call     T0x2B0002E0
0x126fee  leave    loc_1270AE
0x126ff3  ldarg.0
0x126ff4  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteDeclAsync>d__6::<>u__1
0x126ff9  stloc.s  5
0x126ffb  ldarg.0
0x126ffc  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteDeclAsync>d__6::<>u__1
0x127001  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x127007  ldarg.0
0x127008  ldc.i4.m1
0x127009  dup
0x12700a  stloc.0
0x12700b  stfld    int32 <WriteDeclAsync>d__6::<>1__state
0x127010  ldloca.s 5
0x127012  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x127017  ldarg.0
0x127018  ldfld    class System.Xml.XmlWriter <WriteDeclAsync>d__6::writer
0x12701d  callvirt instance class [mscorlib]System.Threading.Tasks.Task System.Xml.XmlWriter::WriteEndAttributeAsync()
0x127022  ldc.i4.0
0x127023  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x127028  stloc.2
0x127029  ldloca.s 2
0x12702b  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x127030  stloc.s  6
0x127032  ldloca.s 6
0x127034  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x127039  brtrue.s loc_127079
0x12703b  ldarg.0
0x12703c  ldc.i4.4
0x12703d  dup
0x12703e  stloc.0
0x12703f  stfld    int32 <WriteDeclAsync>d__6::<>1__state
0x127044  ldarg.0
0x127045  ldloc.s  6
0x127047  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteDeclAsync>d__6::<>u__1
0x12704c  ldarg.0
0x12704d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteDeclAsync>d__6::<>t__builder
0x127052  ldloca.s 6
0x127054  ldarg.0
0x127055  call     T0x2B0002E0
0x12705a  leave.s  loc_1270AE
0x12705c  ldarg.0
0x12705d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteDeclAsync>d__6::<>u__1
0x127062  stloc.s  6
0x127064  ldarg.0
0x127065  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <WriteDeclAsync>d__6::<>u__1
0x12706a  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x127070  ldarg.0
0x127071  ldc.i4.m1
0x127072  dup
0x127073  stloc.0
0x127074  stfld    int32 <WriteDeclAsync>d__6::<>1__state
0x127079  ldloca.s 6
0x12707b  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x127080  leave.s  loc_12709B
0x127082  stloc.s  7
0x127084  ldarg.0
0x127085  ldc.i4.s 0xFE
0x127087  stfld    int32 <WriteDeclAsync>d__6::<>1__state
0x12708c  ldarg.0
0x12708d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteDeclAsync>d__6::<>t__builder
0x127092  ldloc.s  7
0x127094  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x127099  leave.s  loc_1270AE
0x12709b  ldarg.0
0x12709c  ldc.i4.s 0xFE
0x12709e  stfld    int32 <WriteDeclAsync>d__6::<>1__state
0x1270a3  ldarg.0
0x1270a4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <WriteDeclAsync>d__6::<>t__builder
0x1270a9  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x1270ae  ret
```
