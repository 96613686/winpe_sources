# McpManagementTelemetry::WriteDbgTraceWarning(char *,ushort *,...)

- ea: `0x180022000`
- end: `0x180022043`
- name: `?WriteDbgTraceWarning@McpManagementTelemetry@@SAXPEADPEAGZZ`
- size: `67`
- prototype: `void(char *, unsigned __int16 *, ...)`
- caller_count: `24`
- callee_count: `3`
- tags: ``

## callers

- `0x180021be4`
- `0x180021d44`
- `0x1800222c8`
- `0x180022790`
- `0x180022c58`
- `0x1800230d0`
- `0x18002341c`
- `0x1800234cc`
- `0x180023538`
- `0x1800235d0`
- `0x180023a40`
- `0x180024370`
- `0x1800244d0`
- `0x1800245e0`
- `0x180024aec`
- `0x180024de0`
- `0x180025ba0`
- `0x180025d00`
- `0x180025e60`
- `0x180026070`
- `0x1800261d0`
- `0x180026330`
- `0x180026630`
- `0x1800268a0`

## callees

- `0x18000a010`
- `0x18000df7c`
- `0x180022000`

## pseudocode

```c
void McpManagementTelemetry::WriteDbgTraceWarning(char *a1, unsigned __int16 *a2, ...)
{
  va_list va; // [rsp+50h] [rbp+18h] BYREF

  va_start(va, a2);
  if ( McpManagementTelemetry::IsEnabled((unsigned __int8)a1, (unsigned __int64)a2) )
    McpManagementTelemetry::WriteDbgTraceMsg(0, a1, a2, va);
}

```

## disassembly

```asm
0x180022000  mov     [rsp+arg_8], rdx
0x180022005  mov     qword ptr [rsp+arg_10], r8
0x18002200a  mov     [rsp+arg_18], r9
0x18002200f  push    rbx
0x180022010  sub     rsp, 30h
0x180022014  mov     rbx, rcx
0x180022017  call    ?IsEnabled@McpManagementTelemetry@@SA_NE_K@Z; McpManagementTelemetry::IsEnabled(uchar,unsigned __int64)
0x18002201c  test    al, al
0x18002201e  jz      short loc_18002203D
0x180022020  mov     r8, [rsp+38h+arg_8]; unsigned __int16 *
0x180022025  lea     r9, [rsp+38h+arg_10]; char *
0x18002202a  mov     rdx, rbx; char *
0x18002202d  mov     [rsp+38h+var_18], 0
0x180022036  xor     ecx, ecx; bool
0x180022038  call    ?WriteDbgTraceMsg@McpManagementTelemetry@@SAX_NPEADPEAG1@Z; McpManagementTelemetry::WriteDbgTraceMsg(bool,char *,ushort *,char *)
0x18002203d  add     rsp, 30h
0x180022041  pop     rbx
0x180022042  retn
```
