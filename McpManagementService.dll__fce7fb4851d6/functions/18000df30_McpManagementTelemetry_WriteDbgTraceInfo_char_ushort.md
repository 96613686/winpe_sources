# McpManagementTelemetry::WriteDbgTraceInfo(char *,ushort *,...)

- ea: `0x18000df30`
- end: `0x18000df73`
- name: `?WriteDbgTraceInfo@McpManagementTelemetry@@SAXPEADPEAGZZ`
- size: `67`
- prototype: `void(char *, unsigned __int16 *, ...)`
- caller_count: `18`
- callee_count: `3`
- tags: ``

## callers

- `0x180007980`
- `0x18000e708`
- `0x18000ed30`
- `0x180021a20`
- `0x180021b1c`
- `0x1800222c8`
- `0x18002243c`
- `0x180022580`
- `0x180022790`
- `0x180022c58`
- `0x180022d9c`
- `0x180022e80`
- `0x1800230d0`
- `0x180024aec`
- `0x180024bcc`
- `0x180024ca0`
- `0x180024de0`
- `0x1800268a0`

## callees

- `0x18000a010`
- `0x18000df30`
- `0x18000df7c`

## pseudocode

```c
void McpManagementTelemetry::WriteDbgTraceInfo(char *a1, unsigned __int16 *a2, ...)
{
  va_list va; // [rsp+50h] [rbp+18h] BYREF

  va_start(va, a2);
  if ( McpManagementTelemetry::IsEnabled((unsigned __int8)a1, (unsigned __int64)a2) )
    McpManagementTelemetry::WriteDbgTraceMsg(1, a1, a2, va);
}

```

## disassembly

```asm
0x18000df30  mov     [rsp+arg_8], rdx
0x18000df35  mov     qword ptr [rsp+arg_10], r8
0x18000df3a  mov     [rsp+arg_18], r9
0x18000df3f  push    rbx
0x18000df40  sub     rsp, 30h
0x18000df44  mov     rbx, rcx
0x18000df47  call    ?IsEnabled@McpManagementTelemetry@@SA_NE_K@Z; McpManagementTelemetry::IsEnabled(uchar,unsigned __int64)
0x18000df4c  test    al, al
0x18000df4e  jz      short loc_18000DF6D
0x18000df50  mov     r8, [rsp+38h+arg_8]; unsigned __int16 *
0x18000df55  lea     r9, [rsp+38h+arg_10]; char *
0x18000df5a  mov     rdx, rbx; char *
0x18000df5d  mov     [rsp+38h+var_18], 0
0x18000df66  mov     cl, 1; bool
0x18000df68  call    ?WriteDbgTraceMsg@McpManagementTelemetry@@SAX_NPEADPEAG1@Z; McpManagementTelemetry::WriteDbgTraceMsg(bool,char *,ushort *,char *)
0x18000df6d  add     rsp, 30h
0x18000df71  pop     rbx
0x18000df72  retn
```
