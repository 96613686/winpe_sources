# c_SeclLogoffSecondaryUserFromSessionW(_SECL_SLI *,_SECL_LOGONSECONDARYUSERINTOSESSION_SLRI *)

- ea: `0x18005be60`
- end: `0x18005bf99`
- name: `?c_SeclLogoffSecondaryUserFromSessionW@@YAKPEAU_SECL_SLI@@PEAU_SECL_LOGONSECONDARYUSERINTOSESSION_SLRI@@@Z`
- size: `313`
- prototype: `unsigned int __fastcall(struct _SECL_SLI *, struct _SECL_LOGONSECONDARYUSERINTOSESSION_SLRI *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005c6a0`

## callees

- `0x1800378e4`
- `0x18003939c`
- `0x18005be60`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18005bf15`
- `RPCRT4!NdrClientCall3` at `0x18005bf15`
- `RPCRT4!RpcBindingFree` at `0x18005bf82`
- `RPCRT4!RpcBindingFree` at `0x18005bf82`
- `RPCRT4!RpcStringFreeW` at `0x18005bf69`
- `RPCRT4!RpcStringFreeW` at `0x18005bf69`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18005bece`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18005bece`
- `RPCRT4!RpcStringBindingComposeW` at `0x18005beae`
- `RPCRT4!RpcStringBindingComposeW` at `0x18005beae`

## string_xrefs

- `0x18005be90`: `Security=impersonation static false`

## pseudocode

```c
__int64 __fastcall c_SeclLogoffSecondaryUserFromSessionW(
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
        NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180075690, 2u, 0, Binding, a1, a2);
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
0x18005be60  mov     r11, rsp
0x18005be63  mov     [r11+10h], rdx
0x18005be67  mov     [r11+8], rcx
0x18005be6b  push    rbx
0x18005be6c  push    rsi
0x18005be6d  push    rdi
0x18005be6e  sub     rsp, 40h
0x18005be72  mov     rdi, rdx
0x18005be75  mov     rsi, rcx
0x18005be78  mov     qword ptr [r11-28h], 0
0x18005be80  mov     qword ptr [r11+20h], 0
0x18005be88  lea     rax, [r11-28h]
0x18005be8c  mov     [r11-30h], rax
0x18005be90  lea     rax, aSecurityImpers; "Security=impersonation static false"
0x18005be97  mov     [r11-38h], rax
0x18005be9b  lea     r9, aSeclogon_0; "SECLOGON"
0x18005bea2  xor     r8d, r8d; NetworkAddr
0x18005bea5  lea     rdx, aNcalrpc; "ncalrpc"
0x18005beac  xor     ecx, ecx; ObjUuid
0x18005beae  call    cs:__imp_RpcStringBindingComposeW
0x18005beb5  nop     dword ptr [rax+rax+00h]
0x18005beba  mov     ebx, eax
0x18005bebc  test    eax, eax
0x18005bebe  jnz     loc_18005BF5C
0x18005bec4  lea     rdx, [rsp+58h+Binding]; Binding
0x18005bec9  mov     rcx, [rsp+58h+StringBinding]; StringBinding
0x18005bece  call    cs:__imp_RpcBindingFromStringBindingW
0x18005bed5  nop     dword ptr [rax+rax+00h]
0x18005beda  mov     ebx, eax
0x18005bedc  test    eax, eax
0x18005bede  jnz     short loc_18005BF5C
0x18005bee0  mov     rcx, [rsp+58h+Binding]; Binding
0x18005bee5  call    ?SetupLocalRPCSecurity@@YAKPEAX@Z; SetupLocalRPCSecurity(void *)
0x18005beea  mov     ebx, eax
0x18005beec  test    eax, eax
0x18005beee  jnz     short loc_18005BF5C
0x18005bef0  mov     [rsp+58h+arg_10], 1
0x18005bef8  mov     [rsp+58h+var_30], rdi
0x18005befd  mov     [rsp+58h+var_38], rsi
0x18005bf02  mov     r9, [rsp+58h+Binding]
0x18005bf07  xor     r8d, r8d; pReturnValue
0x18005bf0a  lea     edx, [r8+2]; nProcNum
0x18005bf0e  lea     rcx, stru_180075690; pProxyInfo
0x18005bf15  call    cs:__imp_NdrClientCall3
0x18005bf1c  nop     dword ptr [rax+rax+00h]
0x18005bf21  nop
0x18005bf22  xor     ebx, ebx
0x18005bf24  jmp     short loc_18005BF5C
0x18005bf26  mov     ebx, eax
0x18005bf28  cmp     eax, 6BAh
0x18005bf2d  jz      short loc_18005BF36
0x18005bf2f  cmp     eax, 6B5h
0x18005bf34  jnz     short loc_18005BF5C
0x18005bf36  cmp     [rsp+58h+arg_10], 1
0x18005bf3b  jnz     short loc_18005BF5C
0x18005bf3d  call    ?StartSeclogonService@@YAKXZ; StartSeclogonService(void)
0x18005bf42  mov     ebx, eax
0x18005bf44  test    eax, eax
0x18005bf46  jnz     short loc_18005BF5C
0x18005bf48  mov     [rsp+58h+arg_10], 0
0x18005bf50  mov     rdi, [rsp+58h+arg_8]
0x18005bf55  mov     rsi, [rsp+58h+arg_0]
0x18005bf5a  jmp     short loc_18005BEF8
0x18005bf5c  cmp     [rsp+58h+StringBinding], 0
0x18005bf62  jz      short loc_18005BF75
0x18005bf64  lea     rcx, [rsp+58h+StringBinding]; String
0x18005bf69  call    cs:__imp_RpcStringFreeW
0x18005bf70  nop     dword ptr [rax+rax+00h]
0x18005bf75  cmp     [rsp+58h+Binding], 0
0x18005bf7b  jz      short loc_18005BF8E
0x18005bf7d  lea     rcx, [rsp+58h+Binding]; Binding
0x18005bf82  call    cs:__imp_RpcBindingFree
0x18005bf89  nop     dword ptr [rax+rax+00h]
0x18005bf8e  mov     eax, ebx
0x18005bf90  add     rsp, 40h
0x18005bf94  pop     rdi
0x18005bf95  pop     rsi
0x18005bf96  pop     rbx
0x18005bf97  retn
```
