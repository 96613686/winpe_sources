# ITRPC_HANDLE_bind

- ea: `0x180032190`
- end: `0x1800322ee`
- name: `ITRPC_HANDLE_bind`
- size: `350`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180032190`
- `0x180065090`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800322de`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800322de`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180032247`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180032247`
- `KERNEL32!GetLastError` at `0x1800322e6`
- `KERNEL32!GetLastError` at `0x1800322e6`
- `RPCRT4!RpcStringFreeW` at `0x1800322d6`
- `RPCRT4!RpcStringFreeW` at `0x1800322d6`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18003220b`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18003220b`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800321f5`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800321f5`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18003229c`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18003229c`

## pseudocode

```c
RPC_BINDING_HANDLE ITRPC_HANDLE_bind()
{
  RPC_WSTR String; // [rsp+60h] [rbp+7h] BYREF
  PSID pSid; // [rsp+68h] [rbp+Fh] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+70h] [rbp+17h] BYREF
  RPC_SECURITY_QOS SecurityQOS[2]; // [rsp+78h] [rbp+1Fh] BYREF
  PSID v5; // [rsp+98h] [rbp+3Fh]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A0h] [rbp+47h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v5 = 0;
  pSid = 0;
  Binding = 0;
  String = 0;
  memset(SecurityQOS, 0, sizeof(SecurityQOS));
  if ( !RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, 0, 0, &String)
    && !RpcBindingFromStringBindingW(String, &Binding) )
  {
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
    {
      *(_QWORD *)&SecurityQOS[0].Version = 0x100000003LL;
      *(_OWORD *)&SecurityQOS[0].ImpersonationType = 3u;
      v5 = pSid;
      SecurityQOS[1].ImpersonationType = 0;
      SecurityQOS[0].IdentityTracking = 1;
      RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xAu, 0, 0, SecurityQOS);
    }
    else
    {
      GetLastError();
    }
  }
  if ( String )
    RpcStringFreeW(&String);
  if ( pSid )
    FreeSid(pSid);
  return Binding;
}

```

## disassembly

```asm
0x180032190  mov     [rsp-8+arg_0], rbx
0x180032195  push    rbp
0x180032196  lea     rbp, [rsp-57h]
0x18003219b  sub     rsp, 0B0h
0x1800321a2  mov     rax, cs:__security_cookie
0x1800321a9  xor     rax, rsp
0x1800321ac  mov     [rbp+57h+var_8], rax
0x1800321b0  xor     ebx, ebx
0x1800321b2  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800321b8  xor     eax, eax
0x1800321ba  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], ebx
0x1800321bd  xorps   xmm0, xmm0
0x1800321c0  mov     [rbp+57h+var_18], rax
0x1800321c4  lea     rax, [rbp+57h+String]
0x1800321c8  mov     [rbp+57h+var_48], rbx
0x1800321cc  mov     [rsp+0B0h+StringBinding], rax; StringBinding
0x1800321d1  lea     rdx, aNcalrpc; "ncalrpc"
0x1800321d8  xor     r9d, r9d; Endpoint
0x1800321db  mov     [rsp+0B0h+Options], rbx; Options
0x1800321e0  xor     r8d, r8d; NetworkAddr
0x1800321e3  mov     [rbp+57h+Binding], rbx
0x1800321e7  xor     ecx, ecx; ObjUuid
0x1800321e9  mov     [rbp+57h+String], rbx
0x1800321ed  movups  xmmword ptr [rbp+57h+SecurityQOS.Version], xmm0
0x1800321f1  movups  [rbp+57h+var_28], xmm0
0x1800321f5  call    cs:__imp_RpcStringBindingComposeW
0x1800321fb  test    eax, eax
0x1800321fd  jnz     loc_1800322A2
0x180032203  mov     rcx, [rbp+57h+String]; StringBinding
0x180032207  lea     rdx, [rbp+57h+Binding]; Binding
0x18003220b  call    cs:__imp_RpcBindingFromStringBindingW
0x180032211  test    eax, eax
0x180032213  jnz     loc_1800322A2
0x180032219  lea     rax, [rbp+57h+var_48]
0x18003221d  xor     r9d, r9d; nSubAuthority1
0x180032220  mov     [rsp+0B0h+pSid], rax; pSid
0x180032225  lea     r8d, [rbx+12h]; nSubAuthority0
0x180032229  mov     [rsp+0B0h+nSubAuthority7], ebx; nSubAuthority7
0x18003222d  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180032231  mov     [rsp+0B0h+nSubAuthority6], ebx; nSubAuthority6
0x180032235  mov     dl, 1; nSubAuthorityCount
0x180032237  mov     [rsp+0B0h+nSubAuthority5], ebx; nSubAuthority5
0x18003223b  mov     [rsp+0B0h+nSubAuthority4], ebx; nSubAuthority4
0x18003223f  mov     dword ptr [rsp+0B0h+StringBinding], ebx; nSubAuthority3
0x180032243  mov     dword ptr [rsp+0B0h+Options], ebx; nSubAuthority2
0x180032247  call    cs:__imp_AllocateAndInitializeSid
0x18003224d  test    eax, eax
0x18003224f  jz      loc_1800322E6
0x180032255  mov     rcx, [rbp+57h+Binding]; Binding
0x180032259  lea     eax, [rbx+3]
0x18003225c  mov     [rbp+57h+SecurityQOS.Version], eax
0x18003225f  lea     r9d, [rbx+0Ah]; AuthnSvc
0x180032263  mov     qword ptr [rbp+57h+SecurityQOS.ImpersonationType], rax
0x180032267  lea     r8d, [rbx+6]; AuthnLevel
0x18003226b  mov     rax, [rbp+57h+var_48]
0x18003226f  xor     edx, edx; ServerPrincName
0x180032271  mov     [rbp+57h+var_18], rax
0x180032275  lea     rax, [rbp+57h+SecurityQOS]
0x180032279  mov     qword ptr [rsp+0B0h+nSubAuthority4], rax; SecurityQOS
0x18003227e  mov     dword ptr [rsp+0B0h+StringBinding], ebx; AuthzSvc
0x180032282  mov     [rsp+0B0h+Options], rbx; AuthIdentity
0x180032287  mov     qword ptr [rbp+57h+var_28+4], rbx
0x18003228b  mov     dword ptr [rbp+57h+var_28+0Ch], ebx
0x18003228e  mov     [rbp+57h+SecurityQOS.Capabilities], 1
0x180032295  mov     [rbp+57h+SecurityQOS.IdentityTracking], 1
0x18003229c  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800322a2  cmp     [rbp+57h+String], rbx
0x1800322a6  jnz     short loc_1800322D2
0x1800322a8  mov     rcx, [rbp+57h+var_48]; pSid
0x1800322ac  test    rcx, rcx
0x1800322af  jnz     short loc_1800322DE
0x1800322b1  mov     rax, [rbp+57h+Binding]
0x1800322b5  mov     rcx, [rbp+57h+var_8]
0x1800322b9  xor     rcx, rsp; StackCookie
0x1800322bc  call    __security_check_cookie
0x1800322c1  mov     rbx, [rsp+0B0h+arg_0]
0x1800322c9  add     rsp, 0B0h
0x1800322d0  pop     rbp
0x1800322d1  retn
0x1800322d2  lea     rcx, [rbp+57h+String]; String
0x1800322d6  call    cs:__imp_RpcStringFreeW
0x1800322dc  jmp     short loc_1800322A8
0x1800322de  call    cs:__imp_FreeSid
0x1800322e4  jmp     short loc_1800322B1
0x1800322e6  call    cs:__imp_GetLastError
0x1800322ec  jmp     short loc_1800322A2
```
