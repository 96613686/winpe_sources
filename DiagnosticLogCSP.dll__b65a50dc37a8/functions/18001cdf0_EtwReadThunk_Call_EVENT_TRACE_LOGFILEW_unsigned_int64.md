# EtwReadThunk_Call(_EVENT_TRACE_LOGFILEW *,unsigned __int64)

- ea: `0x18001cdf0`
- end: `0x18001ce09`
- name: `?EtwReadThunk_Call@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@_K@Z`
- size: `25`
- prototype: `unsigned __int64 __fastcall(struct _EVENT_TRACE_LOGFILEW *, unsigned __int64)`
- caller_count: `256`
- callee_count: `1`
- tags: ``

## callers

- `0x18001bdf0`
- `0x18001be00`
- `0x18001be10`
- `0x18001be20`
- `0x18001be30`
- `0x18001be40`
- `0x18001be50`
- `0x18001be60`
- `0x18001be70`
- `0x18001be80`
- `0x18001be90`
- `0x18001bea0`
- `0x18001beb0`
- `0x18001bec0`
- `0x18001bed0`
- `0x18001bee0`
- `0x18001bef0`
- `0x18001bf00`
- `0x18001bf10`
- `0x18001bf20`
- `0x18001bf30`
- `0x18001bf40`
- `0x18001bf50`
- `0x18001bf60`
- `0x18001bf70`
- `0x18001bf80`
- `0x18001bf90`
- `0x18001bfa0`
- `0x18001bfb0`
- `0x18001bfc0`
- `0x18001bfd0`
- `0x18001bfe0`
- `0x18001bff0`
- `0x18001c000`
- `0x18001c010`
- `0x18001c020`
- `0x18001c030`
- `0x18001c040`
- `0x18001c050`
- `0x18001c060`
- `0x18001c070`
- `0x18001c080`
- `0x18001c090`
- `0x18001c0a0`
- `0x18001c0b0`
- `0x18001c0c0`
- `0x18001c0d0`
- `0x18001c0e0`
- `0x18001c0f0`
- `0x18001c100`

## callees

- `0x180039010`

## pseudocode

```c
__int64 __fastcall EtwReadThunk_Call(struct _EVENT_TRACE_LOGFILEW *a1, __int64 a2)
{
  return ((__int64 (__fastcall *)(struct _EVENT_TRACE_LOGFILEW *, _UNKNOWN *****************))(&off_180049648)[3 * a2 + 1])(
           a1,
           (&off_180049648)[3 * a2]);
}

```

## disassembly

```asm
0x18001cdf0  lea     rax, [rdx+rdx*2]
0x18001cdf4  lea     r8, off_180049648
0x18001cdfb  mov     rdx, [r8+rax*8]
0x18001cdff  mov     rax, [r8+rax*8+8]
0x18001ce04  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
