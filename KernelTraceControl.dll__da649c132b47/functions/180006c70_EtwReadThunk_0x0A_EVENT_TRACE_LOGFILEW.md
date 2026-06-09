# EtwReadThunk_0x0A(_EVENT_TRACE_LOGFILEW *)

- ea: `0x180006c70`
- end: `0x180006c7a`
- name: `?EtwReadThunk_0x0A@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@@Z`
- size: `10`
- prototype: `unsigned __int64 __fastcall(struct _EVENT_TRACE_LOGFILEW *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006bac`

## pseudocode

```c
__int64 __fastcall EtwReadThunk_0x0A(struct _EVENT_TRACE_LOGFILEW *a1)
{
  return EtwReadThunk_Call(a1, 10);
}

```

## disassembly

```asm
0x180006c70  mov     edx, 0Ah; unsigned __int64
0x180006c75  jmp     ?EtwReadThunk_Call@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@_K@Z; EtwReadThunk_Call(_EVENT_TRACE_LOGFILEW *,unsigned __int64)
```
