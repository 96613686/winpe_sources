# EtwReadThunk_0x1E(_EVENT_TRACE_LOGFILEW *)

- ea: `0x180009db0`
- end: `0x180009dba`
- name: `?EtwReadThunk_0x1E@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@@Z`
- size: `10`
- prototype: `unsigned __int64 __fastcall(struct _EVENT_TRACE_LOGFILEW *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000abd0`

## pseudocode

```c
__int64 __fastcall EtwReadThunk_0x1E(struct _EVENT_TRACE_LOGFILEW *a1)
{
  return EtwReadThunk_Call(a1, 30);
}

```

## disassembly

```asm
0x180009db0  mov     edx, 1Eh; unsigned __int64
0x180009db5  jmp     ?EtwReadThunk_Call@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@_K@Z; EtwReadThunk_Call(_EVENT_TRACE_LOGFILEW *,unsigned __int64)
```
