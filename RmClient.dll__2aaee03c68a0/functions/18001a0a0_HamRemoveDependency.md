# HamRemoveDependency

- ea: `0x18001a0a0`
- end: `0x18001a0ea`
- name: `HamRemoveDependency`
- size: `74`
- prototype: `CLIENT_CALL_RETURN __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001a0a0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18001a0c8`
- `RPCRT4!NdrClientCall3` at `0x18001a0c8`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001a0db`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001a0db`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HamRemoveDependency(_QWORD *a1, __int64 a2, __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001DF70, 7u, 0, *a1, a2, a3);
}

```

## disassembly

```asm
0x18001a0a0  sub     rsp, 48h
0x18001a0a4  mov     [rsp+48h+arg_0], 0
0x18001a0ad  mov     [rsp+48h+var_20], r8
0x18001a0b2  mov     [rsp+48h+var_28], rdx
0x18001a0b7  mov     r9, [rcx]
0x18001a0ba  xor     r8d, r8d; pReturnValue
0x18001a0bd  lea     edx, [r8+7]; nProcNum
0x18001a0c1  lea     rcx, stru_18001DF70; pProxyInfo
0x18001a0c8  call    cs:__imp_NdrClientCall3
0x18001a0ce  mov     [rsp+48h+arg_0], rax
0x18001a0d3  mov     [rsp+48h+var_18], eax
0x18001a0d7  jmp     short loc_18001A0E5
0x18001a0d9  mov     ecx, eax; Status
0x18001a0db  call    cs:__imp_I_RpcMapWin32Status
0x18001a0e1  mov     [rsp+48h+var_18], eax
0x18001a0e5  add     rsp, 48h
0x18001a0e9  retn
0x18001ba86  push    rbp
0x18001ba88  sub     rsp, 30h
0x18001ba8c  mov     rbp, rdx
0x18001ba8f  mov     rcx, [rcx]
0x18001ba92  mov     ecx, [rcx]; ExceptionCode
0x18001ba94  call    cs:__imp_RpcExceptionFilter
0x18001ba9a  nop
0x18001ba9b  add     rsp, 30h
0x18001ba9f  pop     rbp
0x18001baa0  retn
```
