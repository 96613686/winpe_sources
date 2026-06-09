# c_SeclCreateProcessWithLogonW(_SECL_SLI *,_SECL_SLRI *)

- ea: `0x1800377a4`
- end: `0x1800378db`
- name: `?c_SeclCreateProcessWithLogonW@@YAKPEAU_SECL_SLI@@PEAU_SECL_SLRI@@@Z`
- size: `311`
- prototype: `unsigned int __fastcall(struct _SECL_SLI *, struct _SECL_SLRI *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800319bc`

## callees

- `0x1800377a4`
- `0x1800378e4`
- `0x18003939c`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180037857`
- `RPCRT4!NdrClientCall3` at `0x180037857`
- `RPCRT4!RpcBindingFree` at `0x1800378c4`
- `RPCRT4!RpcBindingFree` at `0x1800378c4`
- `RPCRT4!RpcStringFreeW` at `0x1800378ab`
- `RPCRT4!RpcStringFreeW` at `0x1800378ab`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180037812`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180037812`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800377f2`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800377f2`

## string_xrefs

- `0x1800377d4`: `Security=impersonation static false`

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
        NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180075690, 0, 0, Binding, a1, a2);
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
0x1800377a4  mov     r11, rsp
0x1800377a7  mov     [r11+10h], rdx
0x1800377ab  mov     [r11+8], rcx
0x1800377af  push    rbx
0x1800377b0  push    rsi
0x1800377b1  push    rdi
0x1800377b2  sub     rsp, 40h
0x1800377b6  mov     rdi, rdx
0x1800377b9  mov     rsi, rcx
0x1800377bc  mov     qword ptr [r11-28h], 0
0x1800377c4  mov     qword ptr [r11+20h], 0
0x1800377cc  lea     rax, [r11-28h]
0x1800377d0  mov     [r11-30h], rax
0x1800377d4  lea     rax, aSecurityImpers; "Security=impersonation static false"
0x1800377db  mov     [r11-38h], rax
0x1800377df  lea     r9, aSeclogon_0; "SECLOGON"
0x1800377e6  xor     r8d, r8d; NetworkAddr
0x1800377e9  lea     rdx, aNcalrpc; "ncalrpc"
0x1800377f0  xor     ecx, ecx; ObjUuid
0x1800377f2  call    cs:__imp_RpcStringBindingComposeW
0x1800377f9  nop     dword ptr [rax+rax+00h]
0x1800377fe  mov     ebx, eax
0x180037800  test    eax, eax
0x180037802  jnz     loc_18003789E
0x180037808  lea     rdx, [rsp+58h+Binding]; Binding
0x18003780d  mov     rcx, [rsp+58h+StringBinding]; StringBinding
0x180037812  call    cs:__imp_RpcBindingFromStringBindingW
0x180037819  nop     dword ptr [rax+rax+00h]
0x18003781e  mov     ebx, eax
0x180037820  test    eax, eax
0x180037822  jnz     short loc_18003789E
0x180037824  mov     rcx, [rsp+58h+Binding]; Binding
0x180037829  call    ?SetupLocalRPCSecurity@@YAKPEAX@Z; SetupLocalRPCSecurity(void *)
0x18003782e  mov     ebx, eax
0x180037830  test    eax, eax
0x180037832  jnz     short loc_18003789E
0x180037834  mov     [rsp+58h+arg_10], 1
0x18003783c  mov     [rsp+58h+var_30], rdi
0x180037841  mov     [rsp+58h+var_38], rsi
0x180037846  mov     r9, [rsp+58h+Binding]
0x18003784b  xor     r8d, r8d; pReturnValue
0x18003784e  xor     edx, edx; nProcNum
0x180037850  lea     rcx, stru_180075690; pProxyInfo
0x180037857  call    cs:__imp_NdrClientCall3
0x18003785e  nop     dword ptr [rax+rax+00h]
0x180037863  nop
0x180037864  xor     ebx, ebx
0x180037866  jmp     short loc_18003789E
0x180037868  mov     ebx, eax
0x18003786a  cmp     eax, 6BAh
0x18003786f  jz      short loc_180037878
0x180037871  cmp     eax, 6B5h
0x180037876  jnz     short loc_18003789E
0x180037878  cmp     [rsp+58h+arg_10], 1
0x18003787d  jnz     short loc_18003789E
0x18003787f  call    ?StartSeclogonService@@YAKXZ; StartSeclogonService(void)
0x180037884  mov     ebx, eax
0x180037886  test    eax, eax
0x180037888  jnz     short loc_18003789E
0x18003788a  mov     [rsp+58h+arg_10], 0
0x180037892  mov     rdi, [rsp+58h+arg_8]
0x180037897  mov     rsi, [rsp+58h+arg_0]
0x18003789c  jmp     short loc_18003783C
0x18003789e  cmp     [rsp+58h+StringBinding], 0
0x1800378a4  jz      short loc_1800378B7
0x1800378a6  lea     rcx, [rsp+58h+StringBinding]; String
0x1800378ab  call    cs:__imp_RpcStringFreeW
0x1800378b2  nop     dword ptr [rax+rax+00h]
0x1800378b7  cmp     [rsp+58h+Binding], 0
0x1800378bd  jz      short loc_1800378D0
0x1800378bf  lea     rcx, [rsp+58h+Binding]; Binding
0x1800378c4  call    cs:__imp_RpcBindingFree
0x1800378cb  nop     dword ptr [rax+rax+00h]
0x1800378d0  mov     eax, ebx
0x1800378d2  add     rsp, 40h
0x1800378d6  pop     rdi
0x1800378d7  pop     rsi
0x1800378d8  pop     rbx
0x1800378d9  retn
```
