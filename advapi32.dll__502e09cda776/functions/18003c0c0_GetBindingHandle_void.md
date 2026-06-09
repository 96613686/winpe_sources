# GetBindingHandle(void * *)

- ea: `0x18003c0c0`
- end: `0x18003c27c`
- name: `?GetBindingHandle@@YAKPEAPEAX@Z`
- size: `444`
- prototype: `unsigned int __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003e0e4`

## callees

- `0x18003c0c0`
- `0x1800720b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003c21c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003c21c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003c199`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003c199`
- `KERNEL32!GetLastError` at `0x18003c1a9`
- `KERNEL32!GetLastError` at `0x18003c1a9`
- `RPCRT4!RpcBindingFree` at `0x18003c24c`
- `RPCRT4!RpcBindingFree` at `0x18003c24c`
- `RPCRT4!RpcStringFreeW` at `0x18003c232`
- `RPCRT4!RpcStringFreeW` at `0x18003c232`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18003c152`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18003c152`
- `RPCRT4!RpcStringBindingComposeW` at `0x18003c136`
- `RPCRT4!RpcStringBindingComposeW` at `0x18003c136`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18003c1f6`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18003c1f6`

## pseudocode

```c
RPC_STATUS __fastcall GetBindingHandle(void **a1)
{
  RPC_STATUS result; // eax
  DWORD LastError; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp+7h] BYREF
  RPC_WSTR String; // [rsp+68h] [rbp+Fh] BYREF
  PSID pSid; // [rsp+70h] [rbp+17h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+78h] [rbp+1Fh] BYREF
  __int128 v7; // [rsp+88h] [rbp+2Fh]
  PSID v8; // [rsp+98h] [rbp+3Fh]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A0h] [rbp+47h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  String = 0;
  v8 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid = 0;
  Binding = 0;
  SecurityQOS = 0;
  ghRpc = 0;
  v7 = 0;
  result = RpcStringBindingComposeW(
             (RPC_WSTR)L"8c7daf44-b6dc-11d1-9a4c-0020af6e7c57",
             (RPC_WSTR)L"ncalrpc",
             0,
             0,
             0,
             &String);
  if ( !result )
  {
    LastError = RpcBindingFromStringBindingW(String, &Binding);
    if ( !LastError )
    {
      if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
      {
        SecurityQOS.Version = 3;
        SecurityQOS.ImpersonationType = 3;
        v8 = pSid;
        SecurityQOS.Capabilities = 17;
        SecurityQOS.IdentityTracking = 1;
        LastError = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xAu, 0, 1u, &SecurityQOS);
        if ( !LastError )
          ghRpc = Binding;
      }
      else
      {
        LastError = GetLastError();
      }
    }
    if ( pSid )
      FreeSid(pSid);
    if ( String )
      RpcStringFreeW(&String);
    if ( LastError )
    {
      if ( Binding )
        RpcBindingFree(&Binding);
    }
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x18003c0c0  mov     [rsp-8+arg_0], rbx
0x18003c0c5  mov     [rsp-8+arg_8], rdi
0x18003c0ca  push    rbp
0x18003c0cb  lea     rbp, [rsp-57h]
0x18003c0d0  sub     rsp, 0B0h
0x18003c0d7  mov     rax, cs:__security_cookie
0x18003c0de  xor     rax, rsp
0x18003c0e1  mov     [rbp+57h+var_8], rax
0x18003c0e5  xor     edi, edi
0x18003c0e7  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18003c0ed  xor     eax, eax
0x18003c0ef  mov     [rbp+57h+String], rdi
0x18003c0f3  xorps   xmm0, xmm0
0x18003c0f6  mov     [rbp+57h+var_18], rax
0x18003c0fa  lea     rax, [rbp+57h+String]
0x18003c0fe  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x18003c101  mov     [rsp+0B0h+StringBinding], rax; StringBinding
0x18003c106  lea     rdx, aNcalrpc; "ncalrpc"
0x18003c10d  xor     r9d, r9d; Endpoint
0x18003c110  mov     [rsp+0B0h+Options], rdi; Options
0x18003c115  xor     r8d, r8d; NetworkAddr
0x18003c118  mov     [rbp+57h+var_40], rdi
0x18003c11c  lea     rcx, a8c7daf44B6dc11; "8c7daf44-b6dc-11d1-9a4c-0020af6e7c57"
0x18003c123  mov     [rbp+57h+Binding], rdi
0x18003c127  movups  xmmword ptr [rbp+57h+SecurityQOS.Version], xmm0
0x18003c12b  mov     cs:?ghRpc@@3PEAXEA, rdi; void * ghRpc
0x18003c132  movups  [rbp+57h+var_28], xmm0
0x18003c136  call    cs:__imp_RpcStringBindingComposeW
0x18003c13d  nop     dword ptr [rax+rax+00h]
0x18003c142  test    eax, eax
0x18003c144  jnz     loc_18003C25A
0x18003c14a  mov     rcx, [rbp+57h+String]; StringBinding
0x18003c14e  lea     rdx, [rbp+57h+Binding]; Binding
0x18003c152  call    cs:__imp_RpcBindingFromStringBindingW
0x18003c159  nop     dword ptr [rax+rax+00h]
0x18003c15e  mov     ebx, eax
0x18003c160  test    eax, eax
0x18003c162  jnz     loc_18003C213
0x18003c168  lea     rax, [rbp+57h+var_40]
0x18003c16c  xor     r9d, r9d; nSubAuthority1
0x18003c16f  mov     [rsp+0B0h+pSid], rax; pSid
0x18003c174  lea     ebx, [rdi+1]
0x18003c177  mov     [rsp+0B0h+nSubAuthority7], edi; nSubAuthority7
0x18003c17b  lea     r8d, [rdi+12h]; nSubAuthority0
0x18003c17f  mov     [rsp+0B0h+nSubAuthority6], edi; nSubAuthority6
0x18003c183  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18003c187  mov     [rsp+0B0h+nSubAuthority5], edi; nSubAuthority5
0x18003c18b  mov     dl, bl; nSubAuthorityCount
0x18003c18d  mov     [rsp+0B0h+nSubAuthority4], edi; nSubAuthority4
0x18003c191  mov     dword ptr [rsp+0B0h+StringBinding], edi; nSubAuthority3
0x18003c195  mov     dword ptr [rsp+0B0h+Options], edi; nSubAuthority2
0x18003c199  call    cs:__imp_AllocateAndInitializeSid
0x18003c1a0  nop     dword ptr [rax+rax+00h]
0x18003c1a5  test    eax, eax
0x18003c1a7  jnz     short loc_18003C1B9
0x18003c1a9  call    cs:__imp_GetLastError
0x18003c1b0  nop     dword ptr [rax+rax+00h]
0x18003c1b5  mov     ebx, eax
0x18003c1b7  jmp     short loc_18003C213
0x18003c1b9  mov     rcx, [rbp+57h+Binding]; Binding
0x18003c1bd  mov     eax, 3
0x18003c1c2  mov     [rbp+57h+SecurityQOS.Version], eax
0x18003c1c5  xor     edx, edx; ServerPrincName
0x18003c1c7  mov     [rbp+57h+SecurityQOS.ImpersonationType], eax
0x18003c1ca  mov     rax, [rbp+57h+var_40]
0x18003c1ce  mov     [rbp+57h+var_18], rax
0x18003c1d2  lea     rax, [rbp+57h+SecurityQOS]
0x18003c1d6  mov     qword ptr [rsp+0B0h+nSubAuthority4], rax; SecurityQOS
0x18003c1db  lea     r9d, [rdx+0Ah]; AuthnSvc
0x18003c1df  mov     dword ptr [rsp+0B0h+StringBinding], ebx; AuthzSvc
0x18003c1e3  lea     r8d, [rdx+6]; AuthnLevel
0x18003c1e7  mov     [rsp+0B0h+Options], rdi; AuthIdentity
0x18003c1ec  mov     [rbp+57h+SecurityQOS.Capabilities], 11h
0x18003c1f3  mov     [rbp+57h+SecurityQOS.IdentityTracking], ebx
0x18003c1f6  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18003c1fd  nop     dword ptr [rax+rax+00h]
0x18003c202  mov     ebx, eax
0x18003c204  test    eax, eax
0x18003c206  jnz     short loc_18003C213
0x18003c208  mov     rax, [rbp+57h+Binding]
0x18003c20c  mov     cs:?ghRpc@@3PEAXEA, rax; void * ghRpc
0x18003c213  mov     rcx, [rbp+57h+var_40]; pSid
0x18003c217  test    rcx, rcx
0x18003c21a  jz      short loc_18003C228
0x18003c21c  call    cs:__imp_FreeSid
0x18003c223  nop     dword ptr [rax+rax+00h]
0x18003c228  cmp     [rbp+57h+String], rdi
0x18003c22c  jz      short loc_18003C23E
0x18003c22e  lea     rcx, [rbp+57h+String]; String
0x18003c232  call    cs:__imp_RpcStringFreeW
0x18003c239  nop     dword ptr [rax+rax+00h]
0x18003c23e  test    ebx, ebx
0x18003c240  jz      short loc_18003C258
0x18003c242  cmp     [rbp+57h+Binding], rdi
0x18003c246  jz      short loc_18003C258
0x18003c248  lea     rcx, [rbp+57h+Binding]; Binding
0x18003c24c  call    cs:__imp_RpcBindingFree
0x18003c253  nop     dword ptr [rax+rax+00h]
0x18003c258  mov     eax, ebx
0x18003c25a  mov     rcx, [rbp+57h+var_8]
0x18003c25e  xor     rcx, rsp; StackCookie
0x18003c261  call    __security_check_cookie
0x18003c266  lea     r11, [rsp+0B0h+var_s0]
0x18003c26e  mov     rbx, [r11+10h]
0x18003c272  mov     rdi, [r11+18h]
0x18003c276  mov     rsp, r11
0x18003c279  pop     rbp
0x18003c27a  retn
```
