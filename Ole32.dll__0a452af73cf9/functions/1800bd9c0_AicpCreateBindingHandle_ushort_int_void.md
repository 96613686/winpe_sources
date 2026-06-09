# AicpCreateBindingHandle(ushort *,int,void * *)

- ea: `0x1800bd9c0`
- end: `0x1800bdb14`
- name: `?AicpCreateBindingHandle@@YAKPEAGHPEAPEAX@Z`
- size: `340`
- prototype: `unsigned int __fastcall(wchar_t *phLocalBinding, int pszUuid, void **bDynamicIdentityTracking)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180035eb4`

## callees

- `0x18005312c`
- `0x18005315c`
- `0x1800539a6`
- `0x1800bd9c0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800bda7b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800bda7b`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800bda3a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800bda3a`
- `RPCRT4!RpcBindingFree` at `0x1800bdafc`
- `RPCRT4!RpcBindingFree` at `0x1800bdafc`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800bda22`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800bda22`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800bdace`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800bdace`
- `RPCRT4!RpcStringFreeW` at `0x1800bda46`
- `RPCRT4!RpcStringFreeW` at `0x1800bda46`

## pseudocode

```c
__int64 __fastcall AicpCreateBindingHandle(wchar_t *phLocalBinding, int pszUuid, void **bDynamicIdentityTracking)
{
  void *v4; // rdi
  DWORD LastError_0; // ebx
  HLOCAL v6; // rax
  _RPC_SECURITY_QOS_V3_W SecurityQOS; // [rsp+40h] [rbp-30h] BYREF
  void *hLocalBinding; // [rsp+90h] [rbp+20h] BYREF
  unsigned int cbSid; // [rsp+98h] [rbp+28h] BYREF
  wchar_t *pszBinding; // [rsp+A8h] [rbp+38h] BYREF

  pszBinding = 0;
  cbSid = 0;
  hLocalBinding = 0;
  v4 = 0;
  memset(&SecurityQOS, 0, sizeof(SecurityQOS));
  LastError_0 = RpcStringBindingComposeW(
                  (RPC_WSTR)L"5f54ce7d-5b79-4175-8584-cb65313a0e98",
                  (RPC_WSTR)L"ncalrpc",
                  0,
                  0,
                  0,
                  &pszBinding);
  if ( !LastError_0 )
  {
    LastError_0 = RpcBindingFromStringBindingW(pszBinding, &hLocalBinding);
    RpcStringFreeW(&pszBinding);
    if ( !LastError_0 )
    {
      cbSid = 68;
      v6 = LocalAlloc_0(0x40u, 0x44u);
      v4 = v6;
      if ( v6 )
      {
        if ( CreateWellKnownSid(WinLocalSystemSid, 0, v6, &cbSid) )
        {
          SecurityQOS.Sid = v4;
          SecurityQOS.Version = 3;
          SecurityQOS.ImpersonationType = 3;
          SecurityQOS.Capabilities = 1;
          SecurityQOS.IdentityTracking = 1;
          LastError_0 = RpcBindingSetAuthInfoExW(hLocalBinding, 0, 6u, 0xAu, 0, 0, (RPC_SECURITY_QOS *)&SecurityQOS);
          if ( !LastError_0 )
          {
            *bDynamicIdentityTracking = hLocalBinding;
            hLocalBinding = 0;
          }
        }
        else
        {
          LastError_0 = GetLastError_0();
        }
      }
      else
      {
        LastError_0 = 8;
      }
    }
  }
  LocalFree_0(v4);
  if ( hLocalBinding )
    RpcBindingFree(&hLocalBinding);
  return LastError_0;
}

```

## disassembly

```asm
0x1800bd9c0  mov     r11, rsp
0x1800bd9c3  mov     [r11+18h], rbx
0x1800bd9c7  mov     [rsp-18h+cbSid], edx
0x1800bd9cb  mov     [r11+8], rcx
0x1800bd9cf  push    rbp
0x1800bd9d0  push    rsi
0x1800bd9d1  push    rdi
0x1800bd9d2  mov     rbp, rsp
0x1800bd9d5  sub     rsp, 70h
0x1800bd9d9  xor     eax, eax
0x1800bd9db  mov     [rbp+pszBinding], 0
0x1800bd9e3  xorps   xmm0, xmm0
0x1800bd9e6  mov     [rbp+SecurityQOS.Sid], rax
0x1800bd9ea  mov     [rbp+cbSid], eax
0x1800bd9ed  lea     rdx, ProtSeq; "ncalrpc"
0x1800bd9f4  lea     rax, [rbp+pszBinding]
0x1800bd9f8  mov     [rbp+hLocalBinding], 0
0x1800bda00  mov     rsi, phLocalBinding
0x1800bda03  mov     [r11-60h], rax
0x1800bda07  xor     edi, edi
0x1800bda09  lea     rcx, ObjUuid; "5f54ce7d-5b79-4175-8584-cb65313a0e98"
0x1800bda10  xor     r9d, r9d; Endpoint
0x1800bda13  mov     [r11-68h], rdi
0x1800bda17  xor     r8d, r8d; NetworkAddr
0x1800bda1a  movups  xmmword ptr [rbp+SecurityQOS.Version], xmm0
0x1800bda1e  movups  xmmword ptr [rbp+SecurityQOS.AdditionalSecurityInfoType], xmm0
0x1800bda22  call    cs:__imp_RpcStringBindingComposeW
0x1800bda28  mov     ebx, eax
0x1800bda2a  test    eax, eax
0x1800bda2c  jnz     $CleanExit_1
0x1800bda32  mov     rcx, [rbp+pszBinding]; StringBinding
0x1800bda36  lea     rdx, [rbp+hLocalBinding]; Binding
0x1800bda3a  call    cs:__imp_RpcBindingFromStringBindingW
0x1800bda40  lea     rcx, [rbp+pszBinding]; String
0x1800bda44  mov     ebx, eax
0x1800bda46  call    cs:__imp_RpcStringFreeW
0x1800bda4c  test    ebx, ebx
0x1800bda4e  jnz     $CleanExit_1
0x1800bda54  lea     edx, [rdi+44h]; uBytes
0x1800bda57  lea     ecx, [rdi+40h]; uFlags
0x1800bda5a  mov     [rbp+cbSid], edx
0x1800bda5d  call    LocalAlloc_0
0x1800bda62  mov     rdi, rax
0x1800bda65  test    rax, rax
0x1800bda68  jnz     short loc_1800BDA6F
0x1800bda6a  lea     ebx, [rax+8]
0x1800bda6d  jmp     short $CleanExit_1
0x1800bda6f  xor     edx, edx; DomainSid
0x1800bda71  lea     r9, [rbp+cbSid]; cbSid
0x1800bda75  mov     phLocalBinding, rdi; pSid
0x1800bda78  lea     ecx, [rdx+16h]; WellKnownSidType
0x1800bda7b  call    cs:__imp_CreateWellKnownSid
0x1800bda81  test    eax, eax
0x1800bda83  jnz     short loc_1800BDA8E
0x1800bda85  call    GetLastError_0
0x1800bda8a  mov     ebx, eax
0x1800bda8c  jmp     short $CleanExit_1
0x1800bda8e  mov     ecx, 3
0x1800bda93  mov     [rbp+SecurityQOS.Sid], rdi
0x1800bda97  mov     [rbp+SecurityQOS.Version], ecx
0x1800bda9a  xor     edx, edx; ServerPrincName
0x1800bda9c  mov     [rbp+SecurityQOS.ImpersonationType], ecx
0x1800bda9f  lea     eax, [rcx-2]
0x1800bdaa2  mov     [rbp+SecurityQOS.Capabilities], eax
0x1800bdaa5  lea     r9d, [rcx+7]; AuthnSvc
0x1800bdaa9  mov     [rbp+SecurityQOS.IdentityTracking], eax
0x1800bdaac  lea     r8d, [rcx+3]; AuthnLevel
0x1800bdab0  mov     rcx, [rbp+hLocalBinding]; Binding
0x1800bdab4  lea     rax, [rbp+SecurityQOS]
0x1800bdab8  mov     [rsp+70h+var_40], rax; SecurityQOS
0x1800bdabd  mov     [rsp+70h+AuthzSvc], 0; AuthzSvc
0x1800bdac5  mov     [rsp+70h+AuthIdentity], 0; AuthIdentity
0x1800bdace  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800bdad4  mov     ebx, eax
0x1800bdad6  test    eax, eax
0x1800bdad8  jnz     short $CleanExit_1
0x1800bdada  mov     rax, [rbp+hLocalBinding]
0x1800bdade  mov     [rsi], rax
0x1800bdae1  mov     [rbp+hLocalBinding], 0
0x1800bdae9  mov     rcx, rdi; hMem
0x1800bdaec  call    LocalFree_0
0x1800bdaf1  cmp     [rbp+hLocalBinding], 0
0x1800bdaf6  jz      short loc_1800BDB02
0x1800bdaf8  lea     rcx, [rbp+hLocalBinding]; Binding
0x1800bdafc  call    cs:__imp_RpcBindingFree
0x1800bdb02  mov     eax, ebx
0x1800bdb04  mov     rbx, [rsp+70h+arg_10]
0x1800bdb0c  add     rsp, 70h
0x1800bdb10  pop     rdi
0x1800bdb11  pop     rsi
0x1800bdb12  pop     rbp
0x1800bdb13  retn
```
