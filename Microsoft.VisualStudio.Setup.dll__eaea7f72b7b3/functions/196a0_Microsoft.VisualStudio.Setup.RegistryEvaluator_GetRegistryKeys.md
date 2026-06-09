# Microsoft.VisualStudio.Setup.RegistryEvaluator::GetRegistryKeys

- ea: `0x196a0`
- end: `0x19736`
- name: `Microsoft.VisualStudio.Setup.RegistryEvaluator::GetRegistryKeys`
- size: `150`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x61d0`
- `0x62a0`
- `0x19760`

## callees

- `0x196a0`
- `0x3e960`

## string_xrefs

- `0x196a1`: `services`
- `0x196ac`: `registryKey`

## pseudocode

```c

```

## disassembly

```asm
0x196a0  ldarg.3
0x196a1  ldstr    aServices// "services"
0x196a6  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x196ab  ldarg.1
0x196ac  ldstr    aRegistrykey// "registryKey"
0x196b1  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x196b6  ldarg.3
0x196b7  ldc.i4.0
0x196b8  call     T0x2B00005B
0x196bd  dup
0x196be  brtrue.s loc_196C6
0x196c0  pop
0x196c1  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry Microsoft.VisualStudio.Setup.Services.WindowsRegistry::Default
0x196c6  stloc.0
0x196c7  ldarg.2
0x196c8  brfalse.s loc_196EB
0x196ca  ldarg.2
0x196cb  ldsfld   string Microsoft.VisualStudio.Setup.ChipConstants::X86
0x196d0  ldc.i4.5
0x196d1  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x196d6  brfalse.s loc_196EB
0x196d8  ldc.i4.1
0x196d9  newarr   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey
0x196de  dup
0x196df  ldc.i4.0
0x196e0  ldloc.0
0x196e1  ldarg.1
0x196e2  ldc.i4.1
0x196e3  ldc.i4.0
0x196e4  call     class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.Extensions::OpenKey(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry, string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryView, bool)
0x196e9  stelem.ref
0x196ea  ret
0x196eb  ldarg.2
0x196ec  brfalse.s loc_1972D
0x196ee  ldarg.2
0x196ef  ldsfld   string Microsoft.VisualStudio.Setup.ChipConstants::X64
0x196f4  ldc.i4.5
0x196f5  call     instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x196fa  brfalse.s loc_1972D
0x196fc  ldarg.3
0x196fd  ldc.i4.0
0x196fe  call     T0x2B000053
0x19703  dup
0x19704  brtrue.s loc_1970A
0x19706  pop
0x19707  ldc.i4.1
0x19708  br.s     loc_19712
0x1970a  callvirt instance bool Microsoft.VisualStudio.Setup.Services.IOperatingSystem::get_Is64Bit()
0x1970f  ldc.i4.0
0x19710  ceq
0x19712  brfalse.s loc_1971A
0x19714  call     T0x2B000105
0x19719  ret
0x1971a  ldc.i4.1
0x1971b  newarr   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey
0x19720  dup
0x19721  ldc.i4.0
0x19722  ldloc.0
0x19723  ldarg.1
0x19724  ldc.i4.2
0x19725  ldc.i4.0
0x19726  call     class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.Extensions::OpenKey(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry, string, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryView, bool)
0x1972b  stelem.ref
0x1972c  ret
0x1972d  ldloc.0
0x1972e  ldarg.1
0x1972f  ldc.i4.0
0x19730  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.Extensions::OpenKeys(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry, string, bool)
0x19735  ret
```
