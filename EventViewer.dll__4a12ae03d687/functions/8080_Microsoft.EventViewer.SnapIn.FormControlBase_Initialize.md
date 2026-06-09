# Microsoft.EventViewer.SnapIn.FormControlBase::Initialize

- ea: `0x8080`
- end: `0x8097`
- name: `Microsoft.EventViewer.SnapIn.FormControlBase::Initialize`
- size: `23`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4b80`
- `0x5400`
- `0x9620`

## callees

- `0x8080`

## pseudocode

```c

```

## disassembly

```asm
0x8080  ldarg.0
0x8081  ldarg.1
0x8082  stfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x8087  ldarg.0
0x8088  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x808d  brfalse.s loc_8096
0x808f  ldarg.0
0x8090  ldc.i4.1
0x8091  stfld    bool Microsoft.EventViewer.SnapIn.FormControlBase::viewIsActive
0x8096  ret
```
