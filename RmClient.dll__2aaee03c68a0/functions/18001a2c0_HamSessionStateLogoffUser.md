# HamSessionStateLogoffUser

- ea: `0x18001a2c0`
- end: `0x18001a335`
- name: `HamSessionStateLogoffUser`
- size: `117`
- prototype: `CLIENT_CALL_RETURN __fastcall(_QWORD *, void *, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001a2c0`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18001a2db`
- `ntdll!RtlLengthSid` at `0x18001a2db`
- `RPCRT4!NdrClientCall3` at `0x18001a308`
- `RPCRT4!NdrClientCall3` at `0x18001a308`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001a31b`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001a31b`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HamSessionStateLogoffUser(_QWORD *a1, void *a2, int a3)
{
  ULONG v6; // [rsp+28h] [rbp-30h]

  v6 = RtlLengthSid(a2);
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001D4C0, 2u, 0, *a1, a2, v6, a3);
}

```

## disassembly

```asm
0x18001a2c0  mov     [rsp+arg_8], rbx
0x18001a2c5  mov     [rsp+arg_10], rsi
0x18001a2ca  push    rdi
0x18001a2cb  sub     rsp, 50h
0x18001a2cf  mov     edi, r8d
0x18001a2d2  mov     rbx, rdx
0x18001a2d5  mov     rsi, rcx
0x18001a2d8  mov     rcx, rdx; Sid
0x18001a2db  call    cs:__imp_RtlLengthSid
0x18001a2e1  mov     [rsp+58h+arg_0], 0
0x18001a2ea  mov     [rsp+58h+var_28], edi
0x18001a2ee  mov     [rsp+58h+var_30], eax
0x18001a2f2  mov     [rsp+58h+var_38], rbx
0x18001a2f7  mov     r9, [rsi]
0x18001a2fa  xor     r8d, r8d; pReturnValue
0x18001a2fd  lea     edx, [r8+2]; nProcNum
0x18001a301  lea     rcx, stru_18001D4C0; pProxyInfo
0x18001a308  call    cs:__imp_NdrClientCall3
0x18001a30e  mov     [rsp+58h+arg_0], rax
0x18001a313  mov     [rsp+58h+var_18], eax
0x18001a317  jmp     short loc_18001A325
0x18001a319  mov     ecx, eax; Status
0x18001a31b  call    cs:__imp_I_RpcMapWin32Status
0x18001a321  mov     [rsp+58h+var_18], eax
0x18001a325  mov     rbx, [rsp+58h+arg_8]
0x18001a32a  mov     rsi, [rsp+58h+arg_10]
0x18001a32f  add     rsp, 50h
0x18001a333  pop     rdi
0x18001a334  retn
0x18001b75e  push    rbp
0x18001b760  sub     rsp, 40h
0x18001b764  mov     rbp, rdx
0x18001b767  mov     rcx, [rcx]
0x18001b76a  mov     ecx, [rcx]; ExceptionCode
0x18001b76c  call    cs:__imp_RpcExceptionFilter
0x18001b772  nop
0x18001b773  add     rsp, 40h
0x18001b777  pop     rbp
0x18001b778  retn
```
