# Microsoft.VisualStudio.Setup.UpdateConfigurationScheduler::GetUsers

- ea: `0x1c800`
- end: `0x1c8bf`
- name: `Microsoft.VisualStudio.Setup.UpdateConfigurationScheduler::GetUsers`
- size: `191`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1c4c0`
- `0x1c5b0`

## callees

- `0x1c6e0`
- `0x1c800`
- `0x49250`

## string_xrefs

- `0x1c870`: `Failed to get profile list from registry.`
- `0x1c898`: `Failed to open ProfileList key.`

## pseudocode

```c

```

## disassembly

```asm
0x1c800  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Security.Principal.SecurityIdentifier>::.ctor()
0x1c805  stloc.0
0x1c806  ldarg.0
0x1c807  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry Microsoft.VisualStudio.Setup.UpdateConfigurationScheduler::registry
0x1c80c  ldc.i4.2
0x1c80d  ldc.i4.0
0x1c80e  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry::OpenBaseKey(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryHive, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryView)
0x1c813  stloc.1
0x1c814  ldloc.1
0x1c815  brtrue.s loc_1C81A
0x1c817  ldnull
0x1c818  br.s     loc_1C826
0x1c81a  ldloc.1
0x1c81b  ldsfld   string Microsoft.VisualStudio.Setup.UpdateConfigurationScheduler::ProfileKey
0x1c820  ldc.i4.0
0x1c821  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::OpenSubKey(string, bool)
0x1c826  stloc.2
0x1c827  ldloc.2
0x1c828  brfalse.s loc_1C88C
0x1c82a  ldloc.2
0x1c82b  callvirt instance string[] [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::GetSubKeyNames()
0x1c830  stloc.3
0x1c831  ldc.i4.0
0x1c832  stloc.s  4
0x1c834  br.s     loc_1C859
0x1c836  ldloc.3
0x1c837  ldloc.s  4
0x1c839  ldelem.ref
0x1c83a  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(string)
0x1c83f  stloc.s  5
0x1c841  ldarg.0
0x1c842  ldloc.s  5
0x1c844  call     instance bool Microsoft.VisualStudio.Setup.UpdateConfigurationScheduler::IsValidSidForUpdateConfiguration(class [mscorlib]System.Security.Principal.SecurityIdentifier sid)
0x1c849  brfalse.s loc_1C853
0x1c84b  ldloc.0
0x1c84c  ldloc.s  5
0x1c84e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Security.Principal.SecurityIdentifier>::Add(var<u1>)
0x1c853  ldloc.s  4
0x1c855  ldc.i4.1
0x1c856  add
0x1c857  stloc.s  4
0x1c859  ldloc.s  4
0x1c85b  ldloc.3
0x1c85c  ldlen
0x1c85d  conv.i4
0x1c85e  blt.s    loc_1C836
0x1c860  leave.s  loc_1C8BD
0x1c862  stloc.s  6
0x1c864  ldarg.0
0x1c865  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::get_Logger()
0x1c86a  dup
0x1c86b  brtrue.s loc_1C870
0x1c86d  pop
0x1c86e  br.s     loc_1C88A
0x1c870  ldstr    aFailedToGetPro// "Failed to get profile list from registr"...
0x1c875  ldc.i4.1
0x1c876  newarr   [mscorlib]System.Object
0x1c87b  dup
0x1c87c  ldc.i4.0
0x1c87d  ldloc.s  6
0x1c87f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1c884  stelem.ref
0x1c885  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x1c88a  leave.s  loc_1C8BD
0x1c88c  ldarg.0
0x1c88d  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Services.ScheduledTask.SchedulerBase::get_Logger()
0x1c892  dup
0x1c893  brtrue.s loc_1C898
0x1c895  pop
0x1c896  leave.s  loc_1C8BD
0x1c898  ldstr    aFailedToOpenPr// "Failed to open ProfileList key."
0x1c89d  call     T0x2B000003
0x1c8a2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x1c8a7  leave.s  loc_1C8BD
0x1c8a9  ldloc.2
0x1c8aa  brfalse.s loc_1C8B2
0x1c8ac  ldloc.2
0x1c8ad  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c8b2  endfinally
0x1c8b3  ldloc.1
0x1c8b4  brfalse.s loc_1C8BC
0x1c8b6  ldloc.1
0x1c8b7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c8bc  endfinally
0x1c8bd  ldloc.0
0x1c8be  ret
```
