# c_SeclCreateProcessWithLogonW(_SECL_SLI *,_SECL_SLRI *)

- ea: `0x180033c30`
- end: `0x180033d48`
- name: `?c_SeclCreateProcessWithLogonW@@YAKPEAU_SECL_SLI@@PEAU_SECL_SLRI@@@Z`
- size: `280`
- prototype: `unsigned int __fastcall(struct _SECL_SLI *, struct _SECL_SLRI *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002db2c`

## callees

- `0x180033c30`
- `0x180033d50`
- `0x1800352e4`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180033cd7`
- `RPCRT4!NdrClientCall3` at `0x180033cd7`
- `RPCRT4!RpcBindingFree` at `0x180033d38`
- `RPCRT4!RpcBindingFree` at `0x180033d38`
- `RPCRT4!RpcStringFreeW` at `0x180033d25`
- `RPCRT4!RpcStringFreeW` at `0x180033d25`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180033c98`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180033c98`
- `RPCRT4!RpcStringBindingComposeW` at `0x180033c7e`
- `RPCRT4!RpcStringBindingComposeW` at `0x180033c7e`

## string_xrefs

- `0x180033c60`: `Security=impersonation static false`

## pseudocode

```c
__int64 __fastcall c_SeclCreateProcessWithLogonW(struct _SECL_SLI *a1, struct _SECL_SLRI *a2)
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
        NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800676C0, 0, 0, Binding, a1, a2);
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
0x180033c30  mov     r11, rsp
0x180033c33  mov     [r11+10h], rdx
0x180033c37  mov     [r11+8], rcx
0x180033c3b  push    rbx
0x180033c3c  push    rsi
0x180033c3d  push    rdi
0x180033c3e  sub     rsp, 40h
0x180033c42  mov     rdi, rdx
0x180033c45  mov     rsi, rcx
0x180033c48  mov     qword ptr [r11-28h], 0
0x180033c50  mov     qword ptr [r11+20h], 0
0x180033c58  lea     rax, [r11-28h]
0x180033c5c  mov     [r11-30h], rax
0x180033c60  lea     rax, aSecurityImpers; "Security=impersonation static false"
0x180033c67  mov     [r11-38h], rax
0x180033c6b  lea     r9, aSeclogon_0; "SECLOGON"
0x180033c72  xor     r8d, r8d; NetworkAddr
0x180033c75  lea     rdx, aNcalrpc; "ncalrpc"
0x180033c7c  xor     ecx, ecx; ObjUuid
0x180033c7e  call    cs:__imp_RpcStringBindingComposeW
0x180033c84  mov     ebx, eax
0x180033c86  test    eax, eax
0x180033c88  jnz     loc_180033D18
0x180033c8e  lea     rdx, [rsp+58h+Binding]; Binding
0x180033c93  mov     rcx, [rsp+58h+StringBinding]; StringBinding
0x180033c98  call    cs:__imp_RpcBindingFromStringBindingW
0x180033c9e  mov     ebx, eax
0x180033ca0  test    eax, eax
0x180033ca2  jnz     short loc_180033D18
0x180033ca4  mov     rcx, [rsp+58h+Binding]; Binding
0x180033ca9  call    ?SetupLocalRPCSecurity@@YAKPEAX@Z; SetupLocalRPCSecurity(void *)
0x180033cae  mov     ebx, eax
0x180033cb0  test    eax, eax
0x180033cb2  jnz     short loc_180033D18
0x180033cb4  mov     [rsp+58h+arg_10], 1
0x180033cbc  mov     [rsp+58h+var_30], rdi
0x180033cc1  mov     [rsp+58h+var_38], rsi
0x180033cc6  mov     r9, [rsp+58h+Binding]
0x180033ccb  xor     r8d, r8d; pReturnValue
0x180033cce  xor     edx, edx; nProcNum
0x180033cd0  lea     rcx, stru_1800676C0; pProxyInfo
0x180033cd7  call    cs:__imp_NdrClientCall3
0x180033cdd  nop
0x180033cde  xor     ebx, ebx
0x180033ce0  jmp     short loc_180033D18
0x180033ce2  mov     ebx, eax
0x180033ce4  cmp     eax, 6BAh
0x180033ce9  jz      short loc_180033CF2
0x180033ceb  cmp     eax, 6B5h
0x180033cf0  jnz     short loc_180033D18
0x180033cf2  cmp     [rsp+58h+arg_10], 1
0x180033cf7  jnz     short loc_180033D18
0x180033cf9  call    ?StartSeclogonService@@YAKXZ; StartSeclogonService(void)
0x180033cfe  mov     ebx, eax
0x180033d00  test    eax, eax
0x180033d02  jnz     short loc_180033D18
0x180033d04  mov     [rsp+58h+arg_10], 0
0x180033d0c  mov     rdi, [rsp+58h+arg_8]
0x180033d11  mov     rsi, [rsp+58h+arg_0]
0x180033d16  jmp     short loc_180033CBC
0x180033d18  cmp     [rsp+58h+StringBinding], 0
0x180033d1e  jz      short loc_180033D2B
0x180033d20  lea     rcx, [rsp+58h+StringBinding]; String
0x180033d25  call    cs:__imp_RpcStringFreeW
0x180033d2b  cmp     [rsp+58h+Binding], 0
0x180033d31  jz      short loc_180033D3E
0x180033d33  lea     rcx, [rsp+58h+Binding]; Binding
0x180033d38  call    cs:__imp_RpcBindingFree
0x180033d3e  mov     eax, ebx
0x180033d40  add     rsp, 40h
0x180033d44  pop     rdi
0x180033d45  pop     rsi
0x180033d46  pop     rbx
0x180033d47  retn
```
