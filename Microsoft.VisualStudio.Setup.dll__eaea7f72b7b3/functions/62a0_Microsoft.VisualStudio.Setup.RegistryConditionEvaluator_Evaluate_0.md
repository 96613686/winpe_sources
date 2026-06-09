# Microsoft.VisualStudio.Setup.RegistryConditionEvaluator::Evaluate_0

- ea: `0x62a0`
- end: `0x6393`
- name: `Microsoft.VisualStudio.Setup.RegistryConditionEvaluator::Evaluate_0`
- size: `243`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x62a0`
- `0x63a0`
- `0x196a0`
- `0x3f1b0`

## string_xrefs

- `0x62a1`: `services`
- `0x62ac`: `registryInitializer`

## pseudocode

```c

```

## disassembly

```asm
0x62a0  ldarg.1
0x62a1  ldstr    aServices// "services"
0x62a6  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x62ab  ldarg.2
0x62ac  ldstr    aRegistryinitia// "registryInitializer"
0x62b1  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x62b6  ldarg.1
0x62b7  ldc.i4.0
0x62b8  call     T0x2B00004B
0x62bd  stloc.0
0x62be  ldarg.2
0x62bf  isinst   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RegistryPropertyInitializer
0x62c4  stloc.1
0x62c5  ldloc.1
0x62c6  brfalse  loc_6392
0x62cb  ldloc.0
0x62cc  brtrue.s loc_62D1
0x62ce  ldnull
0x62cf  br.s     loc_62DE
0x62d1  ldloc.0
0x62d2  ldloc.1
0x62d3  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RegistryPropertyInitializer::get_Key()
0x62d8  ldarg.3
0x62d9  callvirt instance string Microsoft.VisualStudio.Setup.Services.IVariableResolver::ResolveVariables(string value, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties)
0x62de  dup
0x62df  brtrue.s loc_62E8
0x62e1  pop
0x62e2  ldloc.1
0x62e3  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RegistryPropertyInitializer::get_Key()
0x62e8  stloc.2
0x62e9  ldarg.0
0x62ea  ldloc.2
0x62eb  ldnull
0x62ec  ldarg.1
0x62ed  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey> Microsoft.VisualStudio.Setup.RegistryEvaluator::GetRegistryKeys(string registryKey, string chip, class [mscorlib]System.IServiceProvider services)
0x62f2  stloc.3
0x62f3  ldarg.0
0x62f4  ldarg.1
0x62f5  ldloc.1
0x62f6  ldloc.3
0x62f7  ldarg.3
0x62f8  call     instance string Microsoft.VisualStudio.Setup.RegistryConditionEvaluator::GetRegistryInitializerValue(class [mscorlib]System.IServiceProvider, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RegistryPropertyInitializer services, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey> initializer, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> keys)
0x62fd  stloc.s  4
0x62ff  ldloc.s  4
0x6301  brfalse.s loc_6339
0x6303  ldarg.3
0x6304  brfalse.s loc_6324
0x6306  ldarg.3
0x6307  ldloc.1
0x6308  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PropertyInitializer::get_Property()
0x630d  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x6312  brfalse.s loc_6324
0x6314  ldarg.3
0x6315  ldloc.1
0x6316  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PropertyInitializer::get_Property()
0x631b  ldloc.s  4
0x631d  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x6322  leave.s  loc_6392
0x6324  ldarg.3
0x6325  brtrue.s loc_6329
0x6327  leave.s  loc_6392
0x6329  ldarg.3
0x632a  ldloc.1
0x632b  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PropertyInitializer::get_Property()
0x6330  ldloc.s  4
0x6332  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x6337  leave.s  loc_6392
0x6339  ldarg.3
0x633a  brfalse.s loc_635C
0x633c  ldarg.3
0x633d  ldloc.1
0x633e  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PropertyInitializer::get_Property()
0x6343  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::ContainsKey(var<u1>)
0x6348  brtrue.s loc_635C
0x634a  ldarg.3
0x634b  ldloc.1
0x634c  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PropertyInitializer::get_Property()
0x6351  ldloc.1
0x6352  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PropertyInitializer::get_DefaultValue()
0x6357  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::Add(var<u1>, !!T0)
0x635c  leave.s  loc_6392
0x635e  ldloc.3
0x635f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey>::GetEnumerator()
0x6364  stloc.s  5
0x6366  br.s     loc_637A
0x6368  ldloc.s  5
0x636a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey>::get_Current()
0x636f  dup
0x6370  brtrue.s loc_6375
0x6372  pop
0x6373  br.s     loc_637A
0x6375  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x637a  ldloc.s  5
0x637c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6381  brtrue.s loc_6368
0x6383  leave.s  loc_6391
0x6385  ldloc.s  5
0x6387  brfalse.s loc_6390
0x6389  ldloc.s  5
0x638b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6390  endfinally
0x6391  endfinally
0x6392  ret
```
