# EtwReadThunk_0x1C(_EVENT_TRACE_LOGFILEW *)

- ea: `0x180009d90`
- end: `0x180009d9a`
- name: `?EtwReadThunk_0x1C@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@@Z`
- size: `10`
- prototype: `unsigned __int64 __fastcall(struct _EVENT_TRACE_LOGFILEW *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000abd0`

## pseudocode

```c
__int64 __fastcall EtwReadThunk_0x1C(struct _EVENT_TRACE_LOGFILEW *a1)
{
  return EtwReadThunk_Call(a1, 28);
}

```

## disassembly

```asm
0x180009d90  mov     edx, 1Ch; unsigned __int64
0x180009d95  jmp     ?EtwReadThunk_Call@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@_K@Z; EtwReadThunk_Call(_EVENT_TRACE_LOGFILEW *,unsigned __int64)
```
