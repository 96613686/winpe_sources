# EtwReadThunk_Call(_EVENT_TRACE_LOGFILEW *,unsigned __int64)

- ea: `0x18001bf00`
- end: `0x18001bf19`
- name: `?EtwReadThunk_Call@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@_K@Z`
- size: `25`
- prototype: `unsigned __int64 __fastcall(struct _EVENT_TRACE_LOGFILEW *, unsigned __int64)`
- caller_count: `256`
- callee_count: `1`
- tags: ``

## callers

- `0x18001af00`
- `0x18001af10`
- `0x18001af20`
- `0x18001af30`
- `0x18001af40`
- `0x18001af50`
- `0x18001af60`
- `0x18001af70`
- `0x18001af80`
- `0x18001af90`
- `0x18001afa0`
- `0x18001afb0`
- `0x18001afc0`
- `0x18001afd0`
- `0x18001afe0`
- `0x18001aff0`
- `0x18001b000`
- `0x18001b010`
- `0x18001b020`
- `0x18001b030`
- `0x18001b040`
- `0x18001b050`
- `0x18001b060`
- `0x18001b070`
- `0x18001b080`
- `0x18001b090`
- `0x18001b0a0`
- `0x18001b0b0`
- `0x18001b0c0`
- `0x18001b0d0`
- `0x18001b0e0`
- `0x18001b0f0`
- `0x18001b100`
- `0x18001b110`
- `0x18001b120`
- `0x18001b130`
- `0x18001b140`
- `0x18001b150`
- `0x18001b160`
- `0x18001b170`
- `0x18001b180`
- `0x18001b190`
- `0x18001b1a0`
- `0x18001b1b0`
- `0x18001b1c0`
- `0x18001b1d0`
- `0x18001b1e0`
- `0x18001b1f0`
- `0x18001b200`
- `0x18001b210`

## callees

- `0x180037010`

## pseudocode

```c
__int64 __fastcall EtwReadThunk_Call(struct _EVENT_TRACE_LOGFILEW *a1, __int64 a2)
{
  return ((__int64 (__fastcall *)(struct _EVENT_TRACE_LOGFILEW *, _UNKNOWN *****************))(&off_180047648)[3 * a2 + 1])(
           a1,
           (&off_180047648)[3 * a2]);
}

```

## disassembly

```asm
0x18001bf00  lea     rax, [rdx+rdx*2]
0x18001bf04  lea     r8, off_180047648
0x18001bf0b  mov     rdx, [r8+rax*8]
0x18001bf0f  mov     rax, [r8+rax*8+8]
0x18001bf14  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
