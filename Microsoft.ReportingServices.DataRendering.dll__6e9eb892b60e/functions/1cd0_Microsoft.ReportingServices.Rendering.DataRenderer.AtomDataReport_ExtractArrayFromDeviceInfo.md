# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::ExtractArrayFromDeviceInfo

- ea: `0x1cd0`
- end: `0x1cf0`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataReport::ExtractArrayFromDeviceInfo`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1bc0`

## callees

- `0x1cd0`
- `0x50d0`

## pseudocode

```c

```

## disassembly

```asm
0x1cd0  ldarg.0
0x1cd1  ldarg.1
0x1cd2  ldarg.2
0x1cd3  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.DataRendererBase::ExtractStringFromDeviceInfo(class [System]System.Collections.Specialized.NameValueCollection deviceInfo, string key)
0x1cd8  stloc.0
0x1cd9  ldloc.0
0x1cda  brtrue.s loc_1CDE
0x1cdc  ldnull
0x1cdd  ret
0x1cde  ldloc.0
0x1cdf  ldc.i4.1
0x1ce0  newarr   [mscorlib]System.Char
0x1ce5  dup
0x1ce6  ldc.i4.0
0x1ce7  ldc.i4.s 0x2C
0x1ce9  stelem.i2
0x1cea  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x1cef  ret
```
