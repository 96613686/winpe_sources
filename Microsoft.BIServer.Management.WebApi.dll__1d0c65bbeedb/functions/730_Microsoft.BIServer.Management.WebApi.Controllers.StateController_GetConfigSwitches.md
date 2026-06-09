# Microsoft.BIServer.Management.WebApi.Controllers.StateController::GetConfigSwitches

- ea: `0x730`
- end: `0x779`
- name: `Microsoft.BIServer.Management.WebApi.Controllers.StateController::GetConfigSwitches`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xfd0`

## callees

- `0x730`

## pseudocode

```c

```

## disassembly

```asm
0x730  ldtoken  [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x735  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x73a  call     string[] [mscorlib]System.Enum::GetNames(class [mscorlib]System.Type)
0x73f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::.ctor()
0x744  stloc.0
0x745  stloc.1
0x746  ldc.i4.0
0x747  stloc.2
0x748  br.s     loc_771
0x74a  ldloc.1
0x74b  ldloc.2
0x74c  ldelem.ref
0x74d  stloc.3
0x74e  ldarg.0
0x74f  ldloc.3
0x750  ldloca.s 4
0x752  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0x757  brfalse.s loc_76D
0x759  ldloc.0
0x75a  ldloc.3
0x75b  ldloc.s  4
0x75d  ldsfld   string [mscorlib]System.Boolean::TrueString
0x762  ldc.i4.5
0x763  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x768  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::Add(var<u1>, !!T0)
0x76d  ldloc.2
0x76e  ldc.i4.1
0x76f  add
0x770  stloc.2
0x771  ldloc.2
0x772  ldloc.1
0x773  ldlen
0x774  conv.i4
0x775  blt.s    loc_74A
0x777  ldloc.0
0x778  ret
```
