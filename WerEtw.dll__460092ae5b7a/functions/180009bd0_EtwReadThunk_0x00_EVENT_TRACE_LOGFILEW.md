# EtwReadThunk_0x00(_EVENT_TRACE_LOGFILEW *)

- ea: `0x180009bd0`
- end: `0x180009bd7`
- name: `?EtwReadThunk_0x00@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@@Z`
- size: `7`
- prototype: `unsigned __int64 __fastcall(struct _EVENT_TRACE_LOGFILEW *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000abd0`

## pseudocode

```c
unsigned __int64 __fastcall EtwReadThunk_0x00(struct _EVENT_TRACE_LOGFILEW *a1)
{
  return EtwReadThunk_Call(a1, 0);
}

```

## disassembly

```asm
0x180009bd0  xor     edx, edx; unsigned __int64
0x180009bd2  jmp     ?EtwReadThunk_Call@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@_K@Z; EtwReadThunk_Call(_EVENT_TRACE_LOGFILEW *,unsigned __int64)
```
