# EtwReadThunk_0x0D(_EVENT_TRACE_LOGFILEW *)

- ea: `0x180009ca0`
- end: `0x180009caa`
- name: `?EtwReadThunk_0x0D@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@@Z`
- size: `10`
- prototype: `unsigned __int64 __fastcall(struct _EVENT_TRACE_LOGFILEW *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000abd0`

## pseudocode

```c
unsigned __int64 __fastcall EtwReadThunk_0x0D(struct _EVENT_TRACE_LOGFILEW *a1)
{
  return EtwReadThunk_Call(a1, 0xDu);
}

```

## disassembly

```asm
0x180009ca0  mov     edx, 0Dh; unsigned __int64
0x180009ca5  jmp     ?EtwReadThunk_Call@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@_K@Z; EtwReadThunk_Call(_EVENT_TRACE_LOGFILEW *,unsigned __int64)
```
