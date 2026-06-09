# EtwReadThunk_0x0F(_EVENT_TRACE_LOGFILEW *)

- ea: `0x180009cc0`
- end: `0x180009cca`
- name: `?EtwReadThunk_0x0F@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@@Z`
- size: `10`
- prototype: `unsigned __int64 __fastcall(struct _EVENT_TRACE_LOGFILEW *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000abd0`

## pseudocode

```c
unsigned __int64 __fastcall EtwReadThunk_0x0F(struct _EVENT_TRACE_LOGFILEW *a1)
{
  return EtwReadThunk_Call(a1, 0xFu);
}

```

## disassembly

```asm
0x180009cc0  mov     edx, 0Fh; unsigned __int64
0x180009cc5  jmp     ?EtwReadThunk_Call@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@_K@Z; EtwReadThunk_Call(_EVENT_TRACE_LOGFILEW *,unsigned __int64)
```
