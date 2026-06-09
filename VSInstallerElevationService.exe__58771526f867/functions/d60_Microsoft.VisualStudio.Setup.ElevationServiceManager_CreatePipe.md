# Microsoft.VisualStudio.Setup.ElevationServiceManager::CreatePipe

- ea: `0xd60`
- end: `0xdef`
- name: `Microsoft.VisualStudio.Setup.ElevationServiceManager::CreatePipe`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xc90`
- `0x1d30`

## callees

- `0xd60`
- `0xdf0`
- `0xf00`
- `0x1a80`

## string_xrefs

- `0xd84`: `Pipe {0} successfully created.`
- `0xda4`: `Failed to create pipe, trying again.`
- `0xdbe`: `Failed to create the pipe.`
- `0xdd0`: `Failed to create pipe after {0} tries.`

## pseudocode

```c

```

## disassembly

```asm
0xd60  ldc.i4.0
0xd61  stloc.0
0xd62  nop
0xd63  ldarg.0
0xd64  call     instance string Microsoft.VisualStudio.Setup.ElevationServiceManager::GeneratePipeName()
0xd69  stloc.2
0xd6a  ldarg.0
0xd6b  ldfld    class Microsoft.VisualStudio.Setup.Services.IPipeFactory Microsoft.VisualStudio.Setup.ElevationServiceManager::pipeFactory
0xd70  ldloc.2
0xd71  callvirt instance class Microsoft.VisualStudio.Setup.IPipe Microsoft.VisualStudio.Setup.Services.IPipeFactory::CreateServer(string pipeName)
0xd76  stloc.3
0xd77  ldarg.0
0xd78  ldloc.2
0xd79  call     instance void Microsoft.VisualStudio.Setup.ElevationServiceManager::SavePipeName(string pipeName)
0xd7e  ldarg.0
0xd7f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ElevationServiceManager::logger
0xd84  ldstr    aPipe0Successfu// "Pipe {0} successfully created."
0xd89  ldc.i4.1
0xd8a  newarr   [mscorlib]System.Object
0xd8f  dup
0xd90  ldc.i4.0
0xd91  ldloc.2
0xd92  stelem.ref
0xd93  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0xd98  ldloc.3
0xd99  stloc.s  4
0xd9b  leave.s  loc_DEC
0xd9d  pop
0xd9e  ldarg.0
0xd9f  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ElevationServiceManager::logger
0xda4  ldstr    aFailedToCreate// "Failed to create pipe, trying again."
0xda9  call     T0x2B000003
0xdae  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0xdb3  leave.s  loc_DB5
0xdb5  ldloc.0
0xdb6  ldc.i4.1
0xdb7  add
0xdb8  dup
0xdb9  stloc.0
0xdba  ldc.i4.s 0xA
0xdbc  blt.s    loc_D62
0xdbe  ldstr    aFailedToCreate_0// "Failed to create the pipe."
0xdc3  newobj   instance void [mscorlib]System.IO.IOException::.ctor(string)
0xdc8  stloc.1
0xdc9  ldarg.0
0xdca  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ElevationServiceManager::logger
0xdcf  ldloc.1
0xdd0  ldstr    aFailedToCreate_1// "Failed to create pipe after {0} tries."
0xdd5  ldc.i4.1
0xdd6  newarr   [mscorlib]System.Object
0xddb  dup
0xddc  ldc.i4.0
0xddd  ldc.i4.s 0xA
0xddf  box      [mscorlib]System.Int32
0xde4  stelem.ref
0xde5  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0xdea  ldloc.1
0xdeb  throw
0xdec  ldloc.s  4
0xdee  ret
```
