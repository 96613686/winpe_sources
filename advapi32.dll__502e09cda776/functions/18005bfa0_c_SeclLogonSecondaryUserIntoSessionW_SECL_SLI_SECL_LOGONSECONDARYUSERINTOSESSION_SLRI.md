# c_SeclLogonSecondaryUserIntoSessionW(_SECL_SLI *,_SECL_LOGONSECONDARYUSERINTOSESSION_SLRI *)

- ea: `0x18005bfa0`
- end: `0x18005c0d9`
- name: `?c_SeclLogonSecondaryUserIntoSessionW@@YAKPEAU_SECL_SLI@@PEAU_SECL_LOGONSECONDARYUSERINTOSESSION_SLRI@@@Z`
- size: `313`
- prototype: `unsigned int __fastcall(struct _SECL_SLI *, struct _SECL_LOGONSECONDARYUSERINTOSESSION_SLRI *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005c7b0`

## callees

- `0x1800378e4`
- `0x18003939c`
- `0x18005bfa0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18005c055`
- `RPCRT4!NdrClientCall3` at `0x18005c055`
- `RPCRT4!RpcBindingFree` at `0x18005c0c2`
- `RPCRT4!RpcBindingFree` at `0x18005c0c2`
- `RPCRT4!RpcStringFreeW` at `0x18005c0a9`
- `RPCRT4!RpcStringFreeW` at `0x18005c0a9`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18005c00e`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18005c00e`
- `RPCRT4!RpcStringBindingComposeW` at `0x18005bfee`
- `RPCRT4!RpcStringBindingComposeW` at `0x18005bfee`

## string_xrefs

- `0x18005bfd0`: `Security=impersonation static false`

## pseudocode

```c
__int64 __fastcall c_SeclLogonSecondaryUserIntoSessionW(
        struct _SECL_SLI *a1,
        struct _SECL_LOGONSECONDARYUSERINTOSESSION_SLRI *a2)
{
  unsigned int v4; // ebx
  RPC_WSTR StringBinding[5]; // [rsp+30h] [rbp-28h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+78h] [rbp+20h] BYREF

  StringBinding[0] = 0;
  Binding = 0;
  v4 = RpcStringBindingComposeW(
         0,
         (RPC_WSTR)L"ncalrpc",
         0,
         (RPC_WSTR)L"SECLOGON",
         L"Security=impersonation static false",
         StringBinding);
  if ( !v4 )
  {
    v4 = RpcBindingFromStringBindingW(StringBinding[0], &Binding);
    if ( !v4 )
    {
      v4 = SetupLocalRPCSecurity(Binding);
      if ( !v4 )
      {
        NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180075690, 1u, 0, Binding, a1, a2);
        v4 = 0;
      }
    }
  }
  if ( StringBinding[0] )
    RpcStringFreeW(StringBinding);
  if ( Binding )
    RpcBindingFree(&Binding);
  return v4;
}

```

## disassembly

```asm
0x18005bfa0  mov     r11, rsp
0x18005bfa3  mov     [r11+10h], rdx
0x18005bfa7  mov     [r11+8], rcx
0x18005bfab  push    rbx
0x18005bfac  push    rsi
0x18005bfad  push    rdi
0x18005bfae  sub     rsp, 40h
0x18005bfb2  mov     rdi, rdx
0x18005bfb5  mov     rsi, rcx
0x18005bfb8  mov     qword ptr [r11-28h], 0
0x18005bfc0  mov     qword ptr [r11+20h], 0
0x18005bfc8  lea     rax, [r11-28h]
0x18005bfcc  mov     [r11-30h], rax
0x18005bfd0  lea     rax, aSecurityImpers; "Security=impersonation static false"
0x18005bfd7  mov     [r11-38h], rax
0x18005bfdb  lea     r9, aSeclogon_0; "SECLOGON"
0x18005bfe2  xor     r8d, r8d; NetworkAddr
0x18005bfe5  lea     rdx, aNcalrpc; "ncalrpc"
0x18005bfec  xor     ecx, ecx; ObjUuid
0x18005bfee  call    cs:__imp_RpcStringBindingComposeW
0x18005bff5  nop     dword ptr [rax+rax+00h]
0x18005bffa  mov     ebx, eax
0x18005bffc  test    eax, eax
0x18005bffe  jnz     loc_18005C09C
0x18005c004  lea     rdx, [rsp+58h+Binding]; Binding
0x18005c009  mov     rcx, [rsp+58h+StringBinding]; StringBinding
0x18005c00e  call    cs:__imp_RpcBindingFromStringBindingW
0x18005c015  nop     dword ptr [rax+rax+00h]
0x18005c01a  mov     ebx, eax
0x18005c01c  test    eax, eax
0x18005c01e  jnz     short loc_18005C09C
0x18005c020  mov     rcx, [rsp+58h+Binding]; Binding
0x18005c025  call    ?SetupLocalRPCSecurity@@YAKPEAX@Z; SetupLocalRPCSecurity(void *)
0x18005c02a  mov     ebx, eax
0x18005c02c  test    eax, eax
0x18005c02e  jnz     short loc_18005C09C
0x18005c030  mov     [rsp+58h+arg_10], 1
0x18005c038  mov     [rsp+58h+var_30], rdi
0x18005c03d  mov     [rsp+58h+var_38], rsi
0x18005c042  mov     r9, [rsp+58h+Binding]
0x18005c047  xor     r8d, r8d; pReturnValue
0x18005c04a  lea     edx, [r8+1]; nProcNum
0x18005c04e  lea     rcx, stru_180075690; pProxyInfo
0x18005c055  call    cs:__imp_NdrClientCall3
0x18005c05c  nop     dword ptr [rax+rax+00h]
0x18005c061  nop
0x18005c062  xor     ebx, ebx
0x18005c064  jmp     short loc_18005C09C
0x18005c066  mov     ebx, eax
0x18005c068  cmp     eax, 6BAh
0x18005c06d  jz      short loc_18005C076
0x18005c06f  cmp     eax, 6B5h
0x18005c074  jnz     short loc_18005C09C
0x18005c076  cmp     [rsp+58h+arg_10], 1
0x18005c07b  jnz     short loc_18005C09C
0x18005c07d  call    ?StartSeclogonService@@YAKXZ; StartSeclogonService(void)
0x18005c082  mov     ebx, eax
0x18005c084  test    eax, eax
0x18005c086  jnz     short loc_18005C09C
0x18005c088  mov     [rsp+58h+arg_10], 0
0x18005c090  mov     rdi, [rsp+58h+arg_8]
0x18005c095  mov     rsi, [rsp+58h+arg_0]
0x18005c09a  jmp     short loc_18005C038
0x18005c09c  cmp     [rsp+58h+StringBinding], 0
0x18005c0a2  jz      short loc_18005C0B5
0x18005c0a4  lea     rcx, [rsp+58h+StringBinding]; String
0x18005c0a9  call    cs:__imp_RpcStringFreeW
0x18005c0b0  nop     dword ptr [rax+rax+00h]
0x18005c0b5  cmp     [rsp+58h+Binding], 0
0x18005c0bb  jz      short loc_18005C0CE
0x18005c0bd  lea     rcx, [rsp+58h+Binding]; Binding
0x18005c0c2  call    cs:__imp_RpcBindingFree
0x18005c0c9  nop     dword ptr [rax+rax+00h]
0x18005c0ce  mov     eax, ebx
0x18005c0d0  add     rsp, 40h
0x18005c0d4  pop     rdi
0x18005c0d5  pop     rsi
0x18005c0d6  pop     rbx
0x18005c0d7  retn
```
