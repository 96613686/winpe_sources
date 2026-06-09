# Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::.ctor

- ea: `0x1940`
- end: `0x19a9`
- name: `Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::.ctor`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xcb0`
- `0x2a70`

## callees

- `0x1940`

## pseudocode

```c

```

## disassembly

```asm
0x1940  ldarg.0
0x1941  ldc.i4.1
0x1942  stfld    int32 Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::successLogLimit
0x1947  ldarg.0
0x1948  ldc.i4.s 0xA
0x194a  stfld    int32 Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::errorLogLimit
0x194f  ldarg.0
0x1950  ldc.i4.5
0x1951  stfld    int32 Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::cancelLogLimit
0x1956  ldarg.0
0x1957  ldc.i4.5
0x1958  stfld    int32 Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::precheckFailureLogLimit
0x195d  ldarg.0
0x195e  ldc.i4.5
0x195f  stfld    int32 Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::updateCheckOnlyFailureLogLimit
0x1964  ldarg.0
0x1965  call     instance void [mscorlib]System.Object::.ctor()
0x196a  ldarg.0
0x196b  ldarg.1
0x196c  stfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::<Services>k__BackingField
0x1971  ldarg.0
0x1972  ldarg.2
0x1973  stfld    class Microsoft.VisualStudio.Setup.CommandLine Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::<CommandLine>k__BackingField
0x1978  ldarg.0
0x1979  ldarg.1
0x197a  ldc.i4.0
0x197b  call     T0x2B000010
0x1980  dup
0x1981  brtrue.s loc_1989
0x1983  pop
0x1984  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.FileSystem::Default
0x1989  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::<FileSystem>k__BackingField
0x198e  ldarg.0
0x198f  ldarg.1
0x1990  ldc.i4.0
0x1991  call     T0x2B000011
0x1996  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::<Logger>k__BackingField
0x199b  ldarg.0
0x199c  ldarg.1
0x199d  ldc.i4.0
0x199e  call     T0x2B000012
0x19a3  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::<Telemetry>k__BackingField
0x19a8  ret
```
