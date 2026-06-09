# Microsoft.VisualStudio.Setup.Engine::TryDisableWindowsUpdate

- ea: `0xc400`
- end: `0xc4b0`
- name: `Microsoft.VisualStudio.Setup.Engine::TryDisableWindowsUpdate`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xc2e0`

## callees

- `0x9fe0`
- `0xc400`
- `0xf480`
- `0x3e930`
- `0x3e940`

## string_xrefs

- `0xc439`: `Windows update service is stopped.`
- `0xc456`: `Windows update service is already stopped.`
- `0xc493`: `Could not stop the windows update service. Error - {0}`

## pseudocode

```c

```

## disassembly

```asm
0xc400  ldarg.0
0xc401  call     instance void Microsoft.VisualStudio.Setup.Engine::Initialize()
0xc406  ldc.i4.0
0xc407  stloc.0
0xc408  ldarg.0
0xc409  call     bool Microsoft.VisualStudio.Setup.Extensions::InDownloadOnlyMode(class Microsoft.VisualStudio.Setup.IEngineContext engine)
0xc40e  brtrue.s loc_C465
0xc410  ldarg.2
0xc411  brtrue.s loc_C465
0xc413  ldarg.0
0xc414  ldfld    class Microsoft.VisualStudio.Setup.Services.IOperatingSystem Microsoft.VisualStudio.Setup.Engine::operatingSystem
0xc419  callvirt instance bool Microsoft.VisualStudio.Setup.Services.IOperatingSystem::AreUpdatesOFF()
0xc41e  brtrue.s loc_C44A
0xc420  ldarg.0
0xc421  ldfld    class Microsoft.VisualStudio.Setup.Services.IOperatingSystem Microsoft.VisualStudio.Setup.Engine::operatingSystem
0xc426  callvirt instance void Microsoft.VisualStudio.Setup.Services.IOperatingSystem::StopUpdates()
0xc42b  ldc.i4.1
0xc42c  stloc.0
0xc42d  ldarg.0
0xc42e  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Engine::logger
0xc433  dup
0xc434  brtrue.s loc_C439
0xc436  pop
0xc437  br.s     loc_C465
0xc439  ldstr    aWindowsUpdateS// "Windows update service is stopped."
0xc43e  call     T0x2B000003
0xc443  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0xc448  br.s     loc_C465
0xc44a  ldarg.0
0xc44b  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Engine::logger
0xc450  dup
0xc451  brtrue.s loc_C456
0xc453  pop
0xc454  br.s     loc_C465
0xc456  ldstr    aWindowsUpdateS_0// "Windows update service is already stopp"...
0xc45b  call     T0x2B000003
0xc460  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0xc465  leave.s  loc_C4AE
0xc467  stloc.1
0xc468  ldarg.1
0xc469  brfalse.s loc_C487
0xc46b  ldarg.1
0xc46c  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0xc471  dup
0xc472  brtrue.s loc_C477
0xc474  pop
0xc475  br.s     loc_C487
0xc477  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::WINDOWSUPDATESTOPFAILEDPROPERTY
0xc47c  ldc.i4.1
0xc47d  box      [mscorlib]System.Boolean
0xc482  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0xc487  ldarg.0
0xc488  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Engine::logger
0xc48d  dup
0xc48e  brtrue.s loc_C493
0xc490  pop
0xc491  br.s     loc_C4AC
0xc493  ldstr    aCouldNotStopTh// "Could not stop the windows update servi"...
0xc498  ldc.i4.1
0xc499  newarr   [mscorlib]System.Object
0xc49e  dup
0xc49f  ldc.i4.0
0xc4a0  ldloc.1
0xc4a1  callvirt instance string [mscorlib]System.Object::ToString()
0xc4a6  stelem.ref
0xc4a7  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0xc4ac  leave.s  loc_C4AE
0xc4ae  ldloc.0
0xc4af  ret
```
