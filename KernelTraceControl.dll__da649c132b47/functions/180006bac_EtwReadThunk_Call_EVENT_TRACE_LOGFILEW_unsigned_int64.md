# EtwReadThunk_Call(_EVENT_TRACE_LOGFILEW *,unsigned __int64)

- ea: `0x180006bac`
- end: `0x180006bc7`
- name: `?EtwReadThunk_Call@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@_K@Z`
- size: `27`
- prototype: `unsigned __int64 __fastcall(struct _EVENT_TRACE_LOGFILEW *, unsigned __int64)`
- caller_count: `256`
- callee_count: `1`
- tags: ``

## callers

- `0x180006bd0`
- `0x180006be0`
- `0x180006bf0`
- `0x180006c00`
- `0x180006c10`
- `0x180006c20`
- `0x180006c30`
- `0x180006c40`
- `0x180006c50`
- `0x180006c60`
- `0x180006c70`
- `0x180006c80`
- `0x180006c90`
- `0x180006ca0`
- `0x180006cb0`
- `0x180006cc0`
- `0x180006cd0`
- `0x180006ce0`
- `0x180006cf0`
- `0x180006d00`
- `0x180006d10`
- `0x180006d20`
- `0x180006d30`
- `0x180006d40`
- `0x180006d50`
- `0x180006d60`
- `0x180006d70`
- `0x180006d80`
- `0x180006d90`
- `0x180006da0`
- `0x180006db0`
- `0x180006dc0`
- `0x180006dd0`
- `0x180006de0`
- `0x180006df0`
- `0x180006e00`
- `0x180006e10`
- `0x180006e20`
- `0x180006e30`
- `0x180006e40`
- `0x180006e50`
- `0x180006e60`
- `0x180006e70`
- `0x180006e80`
- `0x180006e90`
- `0x180006ea0`
- `0x180006eb0`
- `0x180006ec0`
- `0x180006ed0`
- `0x180006ee0`

## callees

- `0x180027910`

## pseudocode

```c
__int64 __fastcall EtwReadThunk_Call(struct _EVENT_TRACE_LOGFILEW *a1, __int64 a2)
{
  return ((__int64 (__fastcall *)(struct _EVENT_TRACE_LOGFILEW *, _UNKNOWN *****************))(&off_180037008)[3 * a2 + 1])(
           a1,
           (&off_180037008)[3 * a2]);
}

```

## disassembly

```asm
0x180006bac  lea     rax, [rdx+rdx*2]
0x180006bb0  lea     r8, off_180037008
0x180006bb7  mov     rdx, [r8+rax*8]
0x180006bbb  mov     rax, [r8+rax*8+8]
0x180006bc0  jmp     cs:__guard_dispatch_icall_fptr
```
