# ITRPC_HANDLE_bind

- ea: `0x180035a50`
- end: `0x180035bd9`
- name: `ITRPC_HANDLE_bind`
- size: `393`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180035a50`
- `0x1800720b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180035bbd`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180035bbd`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180035b13`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180035b13`
- `KERNEL32!GetLastError` at `0x180035bcb`
- `KERNEL32!GetLastError` at `0x180035bcb`
- `RPCRT4!RpcStringFreeW` at `0x180035baf`
- `RPCRT4!RpcStringFreeW` at `0x180035baf`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180035ad1`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180035ad1`
- `RPCRT4!RpcStringBindingComposeW` at `0x180035ab5`
- `RPCRT4!RpcStringBindingComposeW` at `0x180035ab5`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180035b6e`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180035b6e`

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
0x180035a50  mov     [rsp-8+arg_0], rbx
0x180035a55  push    rbp
0x180035a56  lea     rbp, [rsp-57h]
0x180035a5b  sub     rsp, 0B0h
0x180035a62  mov     rax, cs:__security_cookie
0x180035a69  xor     rax, rsp
0x180035a6c  mov     [rbp+57h+var_8], rax
0x180035a70  xor     ebx, ebx
0x180035a72  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180035a78  xor     eax, eax
0x180035a7a  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], ebx
0x180035a7d  xorps   xmm0, xmm0
0x180035a80  mov     [rbp+57h+var_18], rax
0x180035a84  lea     rax, [rbp+57h+String]
0x180035a88  mov     [rbp+57h+var_48], rbx
0x180035a8c  mov     [rsp+0B0h+StringBinding], rax; StringBinding
0x180035a91  lea     rdx, aNcalrpc; "ncalrpc"
0x180035a98  xor     r9d, r9d; Endpoint
0x180035a9b  mov     [rsp+0B0h+Options], rbx; Options
0x180035aa0  xor     r8d, r8d; NetworkAddr
0x180035aa3  mov     [rbp+57h+Binding], rbx
0x180035aa7  xor     ecx, ecx; ObjUuid
0x180035aa9  mov     [rbp+57h+String], rbx
0x180035aad  movups  xmmword ptr [rbp+57h+SecurityQOS.Version], xmm0
0x180035ab1  movups  [rbp+57h+var_28], xmm0
0x180035ab5  call    cs:__imp_RpcStringBindingComposeW
0x180035abc  nop     dword ptr [rax+rax+00h]
0x180035ac1  test    eax, eax
0x180035ac3  jnz     loc_180035B7A
0x180035ac9  mov     rcx, [rbp+57h+String]; StringBinding
0x180035acd  lea     rdx, [rbp+57h+Binding]; Binding
0x180035ad1  call    cs:__imp_RpcBindingFromStringBindingW
0x180035ad8  nop     dword ptr [rax+rax+00h]
0x180035add  test    eax, eax
0x180035adf  jnz     loc_180035B7A
0x180035ae5  lea     rax, [rbp+57h+var_48]
0x180035ae9  xor     r9d, r9d; nSubAuthority1
0x180035aec  mov     [rsp+0B0h+pSid], rax; pSid
0x180035af1  lea     r8d, [rbx+12h]; nSubAuthority0
0x180035af5  mov     [rsp+0B0h+nSubAuthority7], ebx; nSubAuthority7
0x180035af9  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180035afd  mov     [rsp+0B0h+nSubAuthority6], ebx; nSubAuthority6
0x180035b01  mov     dl, 1; nSubAuthorityCount
0x180035b03  mov     [rsp+0B0h+nSubAuthority5], ebx; nSubAuthority5
0x180035b07  mov     [rsp+0B0h+nSubAuthority4], ebx; nSubAuthority4
0x180035b0b  mov     dword ptr [rsp+0B0h+StringBinding], ebx; nSubAuthority3
0x180035b0f  mov     dword ptr [rsp+0B0h+Options], ebx; nSubAuthority2
0x180035b13  call    cs:__imp_AllocateAndInitializeSid
0x180035b1a  nop     dword ptr [rax+rax+00h]
0x180035b1f  test    eax, eax
0x180035b21  jz      loc_180035BCB
0x180035b27  mov     rcx, [rbp+57h+Binding]; Binding
0x180035b2b  lea     eax, [rbx+3]
0x180035b2e  mov     [rbp+57h+SecurityQOS.Version], eax
0x180035b31  lea     r9d, [rbx+0Ah]; AuthnSvc
0x180035b35  mov     qword ptr [rbp+57h+SecurityQOS.ImpersonationType], rax
0x180035b39  lea     r8d, [rbx+6]; AuthnLevel
0x180035b3d  mov     rax, [rbp+57h+var_48]
0x180035b41  xor     edx, edx; ServerPrincName
0x180035b43  mov     [rbp+57h+var_18], rax
0x180035b47  lea     rax, [rbp+57h+SecurityQOS]
0x180035b4b  mov     qword ptr [rsp+0B0h+nSubAuthority4], rax; SecurityQOS
0x180035b50  mov     dword ptr [rsp+0B0h+StringBinding], ebx; AuthzSvc
0x180035b54  mov     [rsp+0B0h+Options], rbx; AuthIdentity
0x180035b59  mov     qword ptr [rbp+57h+var_28+4], rbx
0x180035b5d  mov     dword ptr [rbp+57h+var_28+0Ch], ebx
0x180035b60  mov     [rbp+57h+SecurityQOS.Capabilities], 1
0x180035b67  mov     [rbp+57h+SecurityQOS.IdentityTracking], 1
0x180035b6e  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180035b75  nop     dword ptr [rax+rax+00h]
0x180035b7a  cmp     [rbp+57h+String], rbx
0x180035b7e  jnz     short loc_180035BAB
0x180035b80  mov     rcx, [rbp+57h+var_48]; pSid
0x180035b84  test    rcx, rcx
0x180035b87  jnz     short loc_180035BBD
0x180035b89  mov     rax, [rbp+57h+Binding]
0x180035b8d  mov     rcx, [rbp+57h+var_8]
0x180035b91  xor     rcx, rsp; StackCookie
0x180035b94  call    __security_check_cookie
0x180035b99  mov     rbx, [rsp+0B0h+arg_0]
0x180035ba1  add     rsp, 0B0h
0x180035ba8  pop     rbp
0x180035ba9  retn
0x180035bab  lea     rcx, [rbp+57h+String]; String
0x180035baf  call    cs:__imp_RpcStringFreeW
0x180035bb6  nop     dword ptr [rax+rax+00h]
0x180035bbb  jmp     short loc_180035B80
0x180035bbd  call    cs:__imp_FreeSid
0x180035bc4  nop     dword ptr [rax+rax+00h]
0x180035bc9  jmp     short loc_180035B89
0x180035bcb  call    cs:__imp_GetLastError
0x180035bd2  nop     dword ptr [rax+rax+00h]
0x180035bd7  jmp     short loc_180035B7A
```
