# EtwReadThunk_Call(_EVENT_TRACE_LOGFILEW *,unsigned __int64)

- ea: `0x18000abd0`
- end: `0x18000abe9`
- name: `?EtwReadThunk_Call@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@_K@Z`
- size: `25`
- prototype: `unsigned __int64 __fastcall(struct _EVENT_TRACE_LOGFILEW *, unsigned __int64)`
- caller_count: `256`
- callee_count: `1`
- tags: ``

## callers

- `0x180009bd0`
- `0x180009be0`
- `0x180009bf0`
- `0x180009c00`
- `0x180009c10`
- `0x180009c20`
- `0x180009c30`
- `0x180009c40`
- `0x180009c50`
- `0x180009c60`
- `0x180009c70`
- `0x180009c80`
- `0x180009c90`
- `0x180009ca0`
- `0x180009cb0`
- `0x180009cc0`
- `0x180009cd0`
- `0x180009ce0`
- `0x180009cf0`
- `0x180009d00`
- `0x180009d10`
- `0x180009d20`
- `0x180009d30`
- `0x180009d40`
- `0x180009d50`
- `0x180009d60`
- `0x180009d70`
- `0x180009d80`
- `0x180009d90`
- `0x180009da0`
- `0x180009db0`
- `0x180009dc0`
- `0x180009dd0`
- `0x180009de0`
- `0x180009df0`
- `0x180009e00`
- `0x180009e10`
- `0x180009e20`
- `0x180009e30`
- `0x180009e40`
- `0x180009e50`
- `0x180009e60`
- `0x180009e70`
- `0x180009e80`
- `0x180009e90`
- `0x180009ea0`
- `0x180009eb0`
- `0x180009ec0`
- `0x180009ed0`
- `0x180009ee0`

## callees

- `0x18002a010`

## pseudocode

```c
__int64 __fastcall EtwReadThunk_Call(struct _EVENT_TRACE_LOGFILEW *a1, __int64 a2)
{
  return ((__int64 (__fastcall *)(struct _EVENT_TRACE_LOGFILEW *, _UNKNOWN *****************))(&off_180035008)[3 * a2 + 1])(
           a1,
           (&off_180035008)[3 * a2]);
}

```

## disassembly

```asm
0x18000abd0  lea     rax, [rdx+rdx*2]
0x18000abd4  lea     r8, off_180035008
0x18000abdb  mov     rdx, [r8+rax*8]
0x18000abdf  mov     rax, [r8+rax*8+8]
0x18000abe4  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
