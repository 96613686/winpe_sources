# EtwReadThunk_0x05(_EVENT_TRACE_LOGFILEW *)

- ea: `0x180009c20`
- end: `0x180009c2a`
- name: `?EtwReadThunk_0x05@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@@Z`
- size: `10`
- prototype: `unsigned __int64 __fastcall(struct _EVENT_TRACE_LOGFILEW *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000abd0`

## pseudocode

```c
__int64 __fastcall EtwReadThunk_0x05(struct _EVENT_TRACE_LOGFILEW *a1)
{
  return EtwReadThunk_Call(a1, 5);
}

```

## disassembly

```asm
0x180009c20  mov     edx, 5; unsigned __int64
0x180009c25  jmp     ?EtwReadThunk_Call@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@_K@Z; EtwReadThunk_Call(_EVENT_TRACE_LOGFILEW *,unsigned __int64)
```
