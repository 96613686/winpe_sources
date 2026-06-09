# GetBindingHandle(void * *)

- ea: `0x180037f10`
- end: `0x18003809b`
- name: `?GetBindingHandle@@YAKPEAPEAX@Z`
- size: `395`
- prototype: `unsigned int __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180039d28`

## callees

- `0x180037f10`
- `0x180065090`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003804e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003804e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180037fdd`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180037fdd`
- `KERNEL32!GetLastError` at `0x180037fe7`
- `KERNEL32!GetLastError` at `0x180037fe7`
- `RPCRT4!RpcBindingFree` at `0x180038072`
- `RPCRT4!RpcBindingFree` at `0x180038072`
- `RPCRT4!RpcStringFreeW` at `0x18003805e`
- `RPCRT4!RpcStringFreeW` at `0x18003805e`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180037f9c`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180037f9c`
- `RPCRT4!RpcStringBindingComposeW` at `0x180037f86`
- `RPCRT4!RpcStringBindingComposeW` at `0x180037f86`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18003802e`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18003802e`

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
0x180037f10  mov     [rsp-8+arg_0], rbx
0x180037f15  mov     [rsp-8+arg_8], rdi
0x180037f1a  push    rbp
0x180037f1b  lea     rbp, [rsp-57h]
0x180037f20  sub     rsp, 0B0h
0x180037f27  mov     rax, cs:__security_cookie
0x180037f2e  xor     rax, rsp
0x180037f31  mov     [rbp+57h+var_8], rax
0x180037f35  xor     edi, edi
0x180037f37  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180037f3d  xor     eax, eax
0x180037f3f  mov     [rbp+57h+String], rdi
0x180037f43  xorps   xmm0, xmm0
0x180037f46  mov     [rbp+57h+var_18], rax
0x180037f4a  lea     rax, [rbp+57h+String]
0x180037f4e  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x180037f51  mov     [rsp+0B0h+StringBinding], rax; StringBinding
0x180037f56  lea     rdx, aNcalrpc; "ncalrpc"
0x180037f5d  xor     r9d, r9d; Endpoint
0x180037f60  mov     [rsp+0B0h+Options], rdi; Options
0x180037f65  xor     r8d, r8d; NetworkAddr
0x180037f68  mov     [rbp+57h+var_40], rdi
0x180037f6c  lea     rcx, a8c7daf44B6dc11; "8c7daf44-b6dc-11d1-9a4c-0020af6e7c57"
0x180037f73  mov     [rbp+57h+Binding], rdi
0x180037f77  movups  xmmword ptr [rbp+57h+SecurityQOS.Version], xmm0
0x180037f7b  mov     cs:?ghRpc@@3PEAXEA, rdi; void * ghRpc
0x180037f82  movups  [rbp+57h+var_28], xmm0
0x180037f86  call    cs:__imp_RpcStringBindingComposeW
0x180037f8c  test    eax, eax
0x180037f8e  jnz     loc_18003807A
0x180037f94  mov     rcx, [rbp+57h+String]; StringBinding
0x180037f98  lea     rdx, [rbp+57h+Binding]; Binding
0x180037f9c  call    cs:__imp_RpcBindingFromStringBindingW
0x180037fa2  mov     ebx, eax
0x180037fa4  test    eax, eax
0x180037fa6  jnz     loc_180038045
0x180037fac  lea     rax, [rbp+57h+var_40]
0x180037fb0  xor     r9d, r9d; nSubAuthority1
0x180037fb3  mov     [rsp+0B0h+pSid], rax; pSid
0x180037fb8  lea     ebx, [rdi+1]
0x180037fbb  mov     [rsp+0B0h+nSubAuthority7], edi; nSubAuthority7
0x180037fbf  lea     r8d, [rdi+12h]; nSubAuthority0
0x180037fc3  mov     [rsp+0B0h+nSubAuthority6], edi; nSubAuthority6
0x180037fc7  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180037fcb  mov     [rsp+0B0h+nSubAuthority5], edi; nSubAuthority5
0x180037fcf  mov     dl, bl; nSubAuthorityCount
0x180037fd1  mov     [rsp+0B0h+nSubAuthority4], edi; nSubAuthority4
0x180037fd5  mov     dword ptr [rsp+0B0h+StringBinding], edi; nSubAuthority3
0x180037fd9  mov     dword ptr [rsp+0B0h+Options], edi; nSubAuthority2
0x180037fdd  call    cs:__imp_AllocateAndInitializeSid
0x180037fe3  test    eax, eax
0x180037fe5  jnz     short loc_180037FF1
0x180037fe7  call    cs:__imp_GetLastError
0x180037fed  mov     ebx, eax
0x180037fef  jmp     short loc_180038045
0x180037ff1  mov     rcx, [rbp+57h+Binding]; Binding
0x180037ff5  mov     eax, 3
0x180037ffa  mov     [rbp+57h+SecurityQOS.Version], eax
0x180037ffd  xor     edx, edx; ServerPrincName
0x180037fff  mov     [rbp+57h+SecurityQOS.ImpersonationType], eax
0x180038002  mov     rax, [rbp+57h+var_40]
0x180038006  mov     [rbp+57h+var_18], rax
0x18003800a  lea     rax, [rbp+57h+SecurityQOS]
0x18003800e  mov     qword ptr [rsp+0B0h+nSubAuthority4], rax; SecurityQOS
0x180038013  lea     r9d, [rdx+0Ah]; AuthnSvc
0x180038017  mov     dword ptr [rsp+0B0h+StringBinding], ebx; AuthzSvc
0x18003801b  lea     r8d, [rdx+6]; AuthnLevel
0x18003801f  mov     [rsp+0B0h+Options], rdi; AuthIdentity
0x180038024  mov     [rbp+57h+SecurityQOS.Capabilities], 11h
0x18003802b  mov     [rbp+57h+SecurityQOS.IdentityTracking], ebx
0x18003802e  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180038034  mov     ebx, eax
0x180038036  test    eax, eax
0x180038038  jnz     short loc_180038045
0x18003803a  mov     rax, [rbp+57h+Binding]
0x18003803e  mov     cs:?ghRpc@@3PEAXEA, rax; void * ghRpc
0x180038045  mov     rcx, [rbp+57h+var_40]; pSid
0x180038049  test    rcx, rcx
0x18003804c  jz      short loc_180038054
0x18003804e  call    cs:__imp_FreeSid
0x180038054  cmp     [rbp+57h+String], rdi
0x180038058  jz      short loc_180038064
0x18003805a  lea     rcx, [rbp+57h+String]; String
0x18003805e  call    cs:__imp_RpcStringFreeW
0x180038064  test    ebx, ebx
0x180038066  jz      short loc_180038078
0x180038068  cmp     [rbp+57h+Binding], rdi
0x18003806c  jz      short loc_180038078
0x18003806e  lea     rcx, [rbp+57h+Binding]; Binding
0x180038072  call    cs:__imp_RpcBindingFree
0x180038078  mov     eax, ebx
0x18003807a  mov     rcx, [rbp+57h+var_8]
0x18003807e  xor     rcx, rsp; StackCookie
0x180038081  call    __security_check_cookie
0x180038086  lea     r11, [rsp+0B0h+var_s0]
0x18003808e  mov     rbx, [r11+10h]
0x180038092  mov     rdi, [r11+18h]
0x180038096  mov     rsp, r11
0x180038099  pop     rbp
0x18003809a  retn
```
