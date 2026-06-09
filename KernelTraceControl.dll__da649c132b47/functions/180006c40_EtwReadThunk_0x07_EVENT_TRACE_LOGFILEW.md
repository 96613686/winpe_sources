# EtwReadThunk_0x07(_EVENT_TRACE_LOGFILEW *)

- ea: `0x180006c40`
- end: `0x180006c4a`
- name: `?EtwReadThunk_0x07@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@@Z`
- size: `10`
- prototype: `unsigned __int64 __fastcall(struct _EVENT_TRACE_LOGFILEW *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006bac`

## pseudocode

```c
__int64 __fastcall EtwReadThunk_0x07(struct _EVENT_TRACE_LOGFILEW *a1)
{
  return EtwReadThunk_Call(a1, 7);
}

```

## disassembly

```asm
0x180006c40  mov     edx, 7; unsigned __int64
0x180006c45  jmp     ?EtwReadThunk_Call@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@_K@Z; EtwReadThunk_Call(_EVENT_TRACE_LOGFILEW *,unsigned __int64)
```
