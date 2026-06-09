# Microsoft.VisualStudio.Setup.RegistryInitializerEvaluator::Evaluate

- ea: `0x19760`
- end: `0x1984c`
- name: `Microsoft.VisualStudio.Setup.RegistryInitializerEvaluator::Evaluate`
- size: `236`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x41710`

## callees

- `0x196a0`
- `0x19760`
- `0x19850`
- `0x1cd00`
- `0x1cda0`
- `0x1ce70`
- `0x1cfd0`
- `0x3f1b0`

## string_xrefs

- `0x19761`: `services`
- `0x1976c`: `registryInitializer`

## pseudocode

```c

```

## disassembly

```asm
0x19760  ldarg.1
0x19761  ldstr    aServices// "services"
0x19766  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x1976b  ldarg.2
0x1976c  ldstr    aRegistryinitia// "registryInitializer"
0x19771  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x19776  ldarg.3
0x19777  ldstr    aProperties// "properties"
0x1977c  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x19781  ldarg.1
0x19782  ldc.i4.0
0x19783  call     T0x2B00004B
0x19788  stloc.0
0x19789  ldarg.3
0x1978a  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.VisualStudio.Setup.VariableCollection::ToDictionary()
0x1978f  dup
0x19790  brtrue.s loc_1979D
0x19792  pop
0x19793  ldsfld   class [mscorlib]System.StringComparer Microsoft.VisualStudio.Setup.VariableCollection::Comparer
0x19798  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x1979d  stloc.1
0x1979e  ldarg.2
0x1979f  isinst   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RegistryPropertyInitializer
0x197a4  stloc.2
0x197a5  ldloc.2
0x197a6  brtrue.s loc_197A9
0x197a8  ret
0x197a9  ldloc.0
0x197aa  brtrue.s loc_197AF
0x197ac  ldnull
0x197ad  br.s     loc_197BC
0x197af  ldloc.0
0x197b0  ldloc.2
0x197b1  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RegistryPropertyInitializer::get_Key()
0x197b6  ldloc.1
0x197b7  callvirt instance string Microsoft.VisualStudio.Setup.Services.IVariableResolver::ResolveVariables(string value, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> properties)
0x197bc  dup
0x197bd  brtrue.s loc_197C6
0x197bf  pop
0x197c0  ldloc.2
0x197c1  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RegistryPropertyInitializer::get_Key()
0x197c6  stloc.3
0x197c7  ldarg.0
0x197c8  ldloc.3
0x197c9  ldnull
0x197ca  ldarg.1
0x197cb  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey> Microsoft.VisualStudio.Setup.RegistryEvaluator::GetRegistryKeys(string registryKey, string chip, class [mscorlib]System.IServiceProvider services)
0x197d0  stloc.s  4
0x197d2  ldarg.0
0x197d3  ldarg.1
0x197d4  ldloc.2
0x197d5  ldloc.s  4
0x197d7  ldloc.1
0x197d8  call     instance string Microsoft.VisualStudio.Setup.RegistryInitializerEvaluator::GetRegistryInitializerValue(class [mscorlib]System.IServiceProvider, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.RegistryPropertyInitializer services, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey> initializer, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> keys)
0x197dd  stloc.s  5
0x197df  ldloc.s  5
0x197e1  brfalse.s loc_197F3
0x197e3  ldarg.3
0x197e4  ldloc.2
0x197e5  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PropertyInitializer::get_Property()
0x197ea  ldloc.s  5
0x197ec  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::set_Item(string name, string value)
0x197f1  leave.s  loc_1984B
0x197f3  ldarg.3
0x197f4  ldloc.2
0x197f5  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PropertyInitializer::get_Property()
0x197fa  callvirt instance bool Microsoft.VisualStudio.Setup.VariableCollection::Contains(string name)
0x197ff  brtrue.s loc_19814
0x19801  ldarg.3
0x19802  ldloc.2
0x19803  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PropertyInitializer::get_Property()
0x19808  ldloc.2
0x19809  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PropertyInitializer::get_DefaultValue()
0x1980e  ldc.i4.0
0x1980f  callvirt instance void Microsoft.VisualStudio.Setup.VariableCollection::Add(string name, string value, [opt] bool persist)
0x19814  leave.s  loc_1984B
0x19816  ldloc.s  4
0x19818  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey>::GetEnumerator()
0x1981d  stloc.s  6
0x1981f  br.s     loc_19833
0x19821  ldloc.s  6
0x19823  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey>::get_Current()
0x19828  dup
0x19829  brtrue.s loc_1982E
0x1982b  pop
0x1982c  br.s     loc_19833
0x1982e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19833  ldloc.s  6
0x19835  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1983a  brtrue.s loc_19821
0x1983c  leave.s  loc_1984A
0x1983e  ldloc.s  6
0x19840  brfalse.s loc_19849
0x19842  ldloc.s  6
0x19844  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19849  endfinally
0x1984a  endfinally
0x1984b  ret
```
