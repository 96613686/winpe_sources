# EtwReadThunk_0x04(_EVENT_TRACE_LOGFILEW *)

- ea: `0x180006c10`
- end: `0x180006c1a`
- name: `?EtwReadThunk_0x04@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@@Z`
- size: `10`
- prototype: `unsigned __int64 __fastcall(struct _EVENT_TRACE_LOGFILEW *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006bac`

## pseudocode

```c
__int64 __fastcall EtwReadThunk_0x04(struct _EVENT_TRACE_LOGFILEW *a1)
{
  return EtwReadThunk_Call(a1, 4);
}

```

## disassembly

```asm
0x180006c10  mov     edx, 4; unsigned __int64
0x180006c15  jmp     ?EtwReadThunk_Call@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@_K@Z; EtwReadThunk_Call(_EVENT_TRACE_LOGFILEW *,unsigned __int64)
```
