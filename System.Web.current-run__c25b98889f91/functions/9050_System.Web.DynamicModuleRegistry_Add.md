# System.Web.DynamicModuleRegistry::Add

- ea: `0x9050`
- end: `0x90f3`
- name: `System.Web.DynamicModuleRegistry::Add`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10760`

## callees

- `0x9050`
- `0x9130`
- `0x9190`
- `0x34fa0`

## string_xrefs

- `0x907b`: `DynamicModuleRegistry_TypeIsNotIHttpModule`
- `0x90ba`: `DynamicModuleRegistry_ModulesAlreadyInitialized`

## pseudocode

```c

```

## disassembly

```asm
0x9050  ldarg.1
0x9051  ldnull
0x9052  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x9057  brfalse.s loc_9064
0x9059  ldstr    aModuletype// "moduleType"
0x905e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9063  throw
0x9064  ldtoken  System.Web.IHttpModule
0x9069  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x906e  ldarg.1
0x906f  callvirt instance bool [mscorlib]System.Type::IsAssignableFrom(class [mscorlib]System.Type)
0x9074  brtrue.s loc_90A1
0x9076  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x907b  ldstr    aDynamicmoduler// "DynamicModuleRegistry_TypeIsNotIHttpMod"...
0x9080  call     string System.Web.SR::GetString(string name)
0x9085  ldc.i4.1
0x9086  newarr   [mscorlib]System.Object
0x908b  dup
0x908c  ldc.i4.0
0x908d  ldarg.1
0x908e  stelem.ref
0x908f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9094  stloc.0
0x9095  ldloc.0
0x9096  ldstr    aModuletype// "moduleType"
0x909b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x90a0  throw
0x90a1  ldarg.0
0x90a2  ldfld    object System.Web.DynamicModuleRegistry::_lockObj
0x90a7  stloc.1
0x90a8  ldc.i4.0
0x90a9  stloc.2
0x90aa  ldloc.1
0x90ab  ldloca.s 2
0x90ad  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x90b2  ldarg.0
0x90b3  ldfld    bool System.Web.DynamicModuleRegistry::_entriesReadonly
0x90b8  brfalse.s loc_90CA
0x90ba  ldstr    aDynamicmoduler_0// "DynamicModuleRegistry_ModulesAlreadyIni"...
0x90bf  call     string System.Web.SR::GetString(string name)
0x90c4  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x90c9  throw
0x90ca  ldarg.0
0x90cb  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype System.Web.DynamicModuleRegistryEntry> System.Web.DynamicModuleRegistry::_entries
0x90d0  ldarg.1
0x90d1  call     string System.Web.DynamicModuleRegistry::MakeUniqueModuleName(class [mscorlib]System.Type moduleType)
0x90d6  ldarg.1
0x90d7  callvirt instance string [mscorlib]System.Type::get_AssemblyQualifiedName()
0x90dc  newobj   instance void System.Web.DynamicModuleRegistryEntry::.ctor(string name, string type)
0x90e1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype System.Web.DynamicModuleRegistryEntry>::Add(var<u1>)
0x90e6  leave.s  loc_90F2
0x90e8  ldloc.2
0x90e9  brfalse.s loc_90F1
0x90eb  ldloc.1
0x90ec  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x90f1  endfinally
0x90f2  ret
```
