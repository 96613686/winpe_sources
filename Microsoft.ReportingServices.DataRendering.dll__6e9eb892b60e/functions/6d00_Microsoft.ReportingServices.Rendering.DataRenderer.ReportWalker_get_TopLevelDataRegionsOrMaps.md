# Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::get_TopLevelDataRegionsOrMaps

- ea: `0x6d00`
- end: `0x6d0c`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::get_TopLevelDataRegionsOrMaps`
- size: `12`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1cf0`
- `0x1d70`
- `0x1e90`
- `0x4a00`
- `0x7ad0`

## pseudocode

```c

```

## disassembly

```asm
0x6d00  ldarg.0
0x6d01  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Rendering.DataRenderer.ReportWalker::m_dataRegionsOrMaps
0x6d06  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x6d0b  ret
```
