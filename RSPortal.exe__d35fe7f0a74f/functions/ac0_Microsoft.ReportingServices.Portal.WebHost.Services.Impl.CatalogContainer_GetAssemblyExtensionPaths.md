# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CatalogContainer::GetAssemblyExtensionPaths

- ea: `0xac0`
- end: `0xb99`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CatalogContainer::GetAssemblyExtensionPaths`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xa00`

## callees

- `0xa90`
- `0xac0`

## pseudocode

```c

```

## disassembly

```asm
0xac0  ldstr    aBin// "bin"
0xac5  call     string Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CatalogContainer::GetStandardizedPathName(string path)
0xaca  stloc.0
0xacb  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xad0  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0xad5  stloc.1
0xad6  ldarg.0
0xad7  ldfld    class [mscorlib]System.Func`2<string, bool> Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CatalogContainer::DirectoryExists
0xadc  ldloc.0
0xadd  callvirt instance var<u1> class [mscorlib]System.Func`2<string, bool>::Invoke(void)
0xae2  brfalse.s loc_AEC
0xae4  ldloc.1
0xae5  ldloc.0
0xae6  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xaeb  pop
0xaec  ldarg.1
0xaed  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xaf2  brtrue   loc_B97
0xaf7  ldarg.1
0xaf8  ldc.i4.1
0xaf9  newarr   [mscorlib]System.Char
0xafe  dup
0xaff  ldc.i4.0
0xb00  ldc.i4.s 0x3B
0xb02  stelem.i2
0xb03  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xb08  ldsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__8_0
0xb0d  dup
0xb0e  brtrue.s loc_B27
0xb10  pop
0xb11  ldsfld   class <>c <>c::<>9
0xb16  ldftn    instance string <>c::<GetAssemblyExtensionPaths>b__8_0(string p)
0xb1c  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0xb21  dup
0xb22  stsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__8_0
0xb27  call     T0x2B000002
0xb2c  ldsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__8_1
0xb31  dup
0xb32  brtrue.s loc_B4B
0xb34  pop
0xb35  ldsfld   class <>c <>c::<>9
0xb3a  ldftn    instance bool <>c::<GetAssemblyExtensionPaths>b__8_1(string p)
0xb40  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0xb45  dup
0xb46  stsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__8_1
0xb4b  call     T0x2B000003
0xb50  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0xb55  stloc.2
0xb56  br.s     loc_B83
0xb58  ldloc.2
0xb59  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0xb5e  call     string Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CatalogContainer::GetStandardizedPathName(string path)
0xb63  stloc.3
0xb64  ldarg.0
0xb65  ldfld    class [mscorlib]System.Func`2<string, bool> Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CatalogContainer::DirectoryExists
0xb6a  ldloc.3
0xb6b  callvirt instance var<u1> class [mscorlib]System.Func`2<string, bool>::Invoke(void)
0xb70  brfalse.s loc_B83
0xb72  ldloc.1
0xb73  ldloc.3
0xb74  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0xb79  brtrue.s loc_B83
0xb7b  ldloc.1
0xb7c  ldloc.3
0xb7d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xb82  pop
0xb83  ldloc.2
0xb84  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xb89  brtrue.s loc_B58
0xb8b  leave.s  loc_B97
0xb8d  ldloc.2
0xb8e  brfalse.s loc_B96
0xb90  ldloc.2
0xb91  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb96  endfinally
0xb97  ldloc.1
0xb98  ret
```
