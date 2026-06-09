# Microsoft.VisualStudio.Setup.CompositionRoot::CreateBITSDownloadEngines

- ea: `0x2420`
- end: `0x243e`
- name: `Microsoft.VisualStudio.Setup.CompositionRoot::CreateBITSDownloadEngines`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4de0`

## pseudocode

```c

```

## disassembly

```asm
0x2420  ldc.i4.2
0x2421  newarr   [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IDownloadEngine
0x2426  dup
0x2427  ldc.i4.0
0x2428  ldarg.0
0x2429  ldarg.1
0x242a  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.VisualStudio.Setup.BackgroundDownloadConstants::BitsTimeout
0x242f  newobj   instance void [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.Bits.BitsEngine::.ctor(class [mscorlib]System.IServiceProvider, valuetype [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.Bits.BG_JOB_PRIORITY, valuetype [mscorlib]System.TimeSpan)
0x2434  stelem.ref
0x2435  dup
0x2436  ldc.i4.1
0x2437  newobj   instance void [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.FileDownloadEngine::.ctor()
0x243c  stelem.ref
0x243d  ret
```
