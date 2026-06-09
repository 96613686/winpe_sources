# Microsoft.VisualStudio.Setup.ElevationRequest::op_Equality

- ea: `0xc40`
- end: `0xc53`
- name: `Microsoft.VisualStudio.Setup.ElevationRequest::op_Equality`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xc30`

## callees

- `0xc40`
- `0xd30`

## pseudocode

```c

```

## disassembly

```asm
0xc40  ldarg.0
0xc41  ldarg.1
0xc42  beq.s    loc_C51
0xc44  ldarg.0
0xc45  brfalse.s loc_C4F
0xc47  ldarg.0
0xc48  ldarg.1
0xc49  callvirt instance bool Microsoft.VisualStudio.Setup.ElevationRequest::Equals(class Microsoft.VisualStudio.Setup.ElevationRequest other)
0xc4e  ret
0xc4f  ldc.i4.0
0xc50  ret
0xc51  ldc.i4.1
0xc52  ret
```
