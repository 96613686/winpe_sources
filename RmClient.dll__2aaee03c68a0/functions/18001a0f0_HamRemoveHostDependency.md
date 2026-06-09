# HamRemoveHostDependency

- ea: `0x18001a0f0`
- end: `0x18001a13a`
- name: `HamRemoveHostDependency`
- size: `74`
- prototype: `CLIENT_CALL_RETURN __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001a0f0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18001a118`
- `RPCRT4!NdrClientCall3` at `0x18001a118`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001a12b`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001a12b`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HamRemoveHostDependency(_QWORD *a1, __int64 a2, __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001DF70, 9u, 0, *a1, a2, a3);
}

```

## disassembly

```asm
0x18001a0f0  sub     rsp, 48h
0x18001a0f4  mov     [rsp+48h+arg_0], 0
0x18001a0fd  mov     [rsp+48h+var_20], r8
0x18001a102  mov     [rsp+48h+var_28], rdx
0x18001a107  mov     r9, [rcx]
0x18001a10a  xor     r8d, r8d; pReturnValue
0x18001a10d  lea     edx, [r8+9]; nProcNum
0x18001a111  lea     rcx, stru_18001DF70; pProxyInfo
0x18001a118  call    cs:__imp_NdrClientCall3
0x18001a11e  mov     [rsp+48h+arg_0], rax
0x18001a123  mov     [rsp+48h+var_18], eax
0x18001a127  jmp     short loc_18001A135
0x18001a129  mov     ecx, eax; Status
0x18001a12b  call    cs:__imp_I_RpcMapWin32Status
0x18001a131  mov     [rsp+48h+var_18], eax
0x18001a135  add     rsp, 48h
0x18001a139  retn
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
