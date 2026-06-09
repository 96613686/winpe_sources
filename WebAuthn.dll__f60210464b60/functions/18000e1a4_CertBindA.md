# CertBindA

- ea: `0x18000e1a4`
- end: `0x18000e338`
- name: `CertBindA`
- size: `404`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000e09c`

## callees

- `0x18000e1a4`
- `0x18000e340`
- `0x18013c090`

## import_xrefs

- `RPCRT4!RpcBindingFromStringBindingA` at `0x18000e22c`
- `RPCRT4!RpcBindingFromStringBindingA` at `0x18000e22c`
- `RPCRT4!RpcBindingFree` at `0x18000e2ee`
- `RPCRT4!RpcBindingFree` at `0x18000e2ee`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000e2d8`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x18000e2d8`
- `RPCRT4!RpcStringBindingComposeA` at `0x18000e214`
- `RPCRT4!RpcStringBindingComposeA` at `0x18000e214`
- `RPCRT4!RpcStringFreeA` at `0x18000e302`
- `RPCRT4!RpcStringFreeA` at `0x18000e302`
- `RPCRT4!RpcEpResolveBinding` at `0x18000e247`
- `RPCRT4!RpcEpResolveBinding` at `0x18000e247`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000e311`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000e311`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000e288`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000e288`

## pseudocode

```c
__int64 __fastcall CertBindA(__int64 a1, RPC_BINDING_HANDLE *a2)
{
  unsigned int v3; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp-19h] BYREF
  RPC_CSTR String; // [rsp+68h] [rbp-11h] BYREF
  PSID pSid; // [rsp+70h] [rbp-9h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+78h] [rbp-1h] BYREF
  __int128 v9; // [rsp+88h] [rbp+Fh]
  PSID v10; // [rsp+98h] [rbp+1Fh]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A0h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  String = 0;
  Binding = 0;
  SecurityQOS = 0;
  v10 = 0;
  v9 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSid = 0;
  WaitForCryptService();
  v3 = RpcStringBindingComposeA(0, (RPC_CSTR)"ncalrpc", 0, (RPC_CSTR)"keysvc", 0, &String);
  if ( !v3 )
  {
    v3 = RpcBindingFromStringBindingA(String, &Binding);
    if ( !v3 )
    {
      v3 = RpcEpResolveBinding(Binding, qword_18014CF80);
      if ( !v3 )
      {
        if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x14u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
        {
          SecurityQOS.Version = 3;
          SecurityQOS.ImpersonationType = 3;
          v10 = pSid;
          v9 = 0u;
          SecurityQOS.Capabilities = 1;
          SecurityQOS.IdentityTracking = 1;
          v3 = RpcBindingSetAuthInfoExW(Binding, 0, 4u, 0xAu, 0, 0, &SecurityQOS);
          if ( !v3 )
            goto LABEL_9;
        }
        else
        {
          v3 = 14;
        }
      }
    }
  }
  if ( Binding )
  {
    RpcBindingFree(&Binding);
    Binding = 0;
  }
LABEL_9:
  if ( String )
    RpcStringFreeA(&String);
  if ( pSid )
    FreeSid(pSid);
  *a2 = Binding;
  return v3;
}

```

## disassembly

```asm
0x18000e1a4  push    rbp
0x18000e1a6  push    rbx
0x18000e1a7  push    rsi
0x18000e1a8  push    rdi
0x18000e1a9  lea     rbp, [rsp-3Fh]
0x18000e1ae  sub     rsp, 0B8h
0x18000e1b5  mov     rax, cs:__security_cookie
0x18000e1bc  xor     rax, rsp
0x18000e1bf  mov     [rbp+57h+var_28], rax
0x18000e1c3  xor     esi, esi
0x18000e1c5  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18000e1cb  xorps   xmm0, xmm0
0x18000e1ce  mov     [rbp+57h+String], rsi
0x18000e1d2  xor     eax, eax
0x18000e1d4  mov     [rbp+57h+Binding], rsi
0x18000e1d8  movups  xmmword ptr [rbp+57h+SecurityQOS.Version], xmm0
0x18000e1dc  mov     [rbp+57h+var_38], rax
0x18000e1e0  mov     rdi, rdx
0x18000e1e3  movups  [rbp+57h+var_48], xmm0
0x18000e1e7  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x18000e1ea  mov     [rbp+57h+var_60], rsi
0x18000e1ee  call    WaitForCryptService
0x18000e1f3  lea     rax, [rbp+57h+String]
0x18000e1f7  xor     r8d, r8d; NetworkAddr
0x18000e1fa  mov     [rsp+0D0h+StringBinding], rax; StringBinding
0x18000e1ff  lea     r9, Endpoint; "keysvc"
0x18000e206  lea     rdx, ProtSeq; "ncalrpc"
0x18000e20d  mov     [rsp+0D0h+Options], rsi; Options
0x18000e212  xor     ecx, ecx; ObjUuid
0x18000e214  call    cs:__imp_RpcStringBindingComposeA
0x18000e21a  mov     ebx, eax
0x18000e21c  test    eax, eax
0x18000e21e  jnz     loc_18000E2E4
0x18000e224  mov     rcx, [rbp+57h+String]; StringBinding
0x18000e228  lea     rdx, [rbp+57h+Binding]; Binding
0x18000e22c  call    cs:__imp_RpcBindingFromStringBindingA
0x18000e232  mov     ebx, eax
0x18000e234  test    eax, eax
0x18000e236  jnz     loc_18000E2E4
0x18000e23c  mov     rcx, [rbp+57h+Binding]; Binding
0x18000e240  lea     rdx, qword_18014CF80; IfSpec
0x18000e247  call    cs:__imp_RpcEpResolveBinding
0x18000e24d  mov     ebx, eax
0x18000e24f  test    eax, eax
0x18000e251  jnz     loc_18000E2E4
0x18000e257  lea     rax, [rbp+57h+var_60]
0x18000e25b  xor     r9d, r9d; nSubAuthority1
0x18000e25e  mov     [rsp+0D0h+pSid], rax; pSid
0x18000e263  lea     ebx, [rsi+1]
0x18000e266  mov     [rsp+0D0h+nSubAuthority7], esi; nSubAuthority7
0x18000e26a  lea     r8d, [rsi+14h]; nSubAuthority0
0x18000e26e  mov     [rsp+0D0h+nSubAuthority6], esi; nSubAuthority6
0x18000e272  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18000e276  mov     [rsp+0D0h+nSubAuthority5], esi; nSubAuthority5
0x18000e27a  mov     dl, bl; nSubAuthorityCount
0x18000e27c  mov     [rsp+0D0h+nSubAuthority4], esi; nSubAuthority4
0x18000e280  mov     dword ptr [rsp+0D0h+StringBinding], esi; nSubAuthority3
0x18000e284  mov     dword ptr [rsp+0D0h+Options], esi; nSubAuthority2
0x18000e288  call    cs:__imp_AllocateAndInitializeSid
0x18000e28e  test    eax, eax
0x18000e290  jnz     short loc_18000E297
0x18000e292  lea     ebx, [rsi+0Eh]
0x18000e295  jmp     short loc_18000E2E4
0x18000e297  mov     rcx, [rbp+57h+Binding]; Binding
0x18000e29b  mov     eax, 3
0x18000e2a0  mov     [rbp+57h+SecurityQOS.Version], eax
0x18000e2a3  xor     edx, edx; ServerPrincName
0x18000e2a5  mov     [rbp+57h+SecurityQOS.ImpersonationType], eax
0x18000e2a8  mov     rax, [rbp+57h+var_60]
0x18000e2ac  mov     [rbp+57h+var_38], rax
0x18000e2b0  lea     rax, [rbp+57h+SecurityQOS]
0x18000e2b4  mov     qword ptr [rsp+0D0h+nSubAuthority4], rax; SecurityQOS
0x18000e2b9  lea     r9d, [rdx+0Ah]; AuthnSvc
0x18000e2bd  mov     dword ptr [rsp+0D0h+StringBinding], esi; AuthzSvc
0x18000e2c1  lea     r8d, [rdx+4]; AuthnLevel
0x18000e2c5  mov     [rsp+0D0h+Options], rsi; AuthIdentity
0x18000e2ca  mov     qword ptr [rbp+57h+var_48], rsi
0x18000e2ce  mov     [rbp+57h+SecurityQOS.Capabilities], ebx
0x18000e2d1  mov     [rbp+57h+SecurityQOS.IdentityTracking], ebx
0x18000e2d4  mov     qword ptr [rbp+57h+var_48+8], rsi
0x18000e2d8  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000e2de  mov     ebx, eax
0x18000e2e0  test    eax, eax
0x18000e2e2  jz      short loc_18000E2F8
0x18000e2e4  cmp     [rbp+57h+Binding], rsi
0x18000e2e8  jz      short loc_18000E2F8
0x18000e2ea  lea     rcx, [rbp+57h+Binding]; Binding
0x18000e2ee  call    cs:__imp_RpcBindingFree
0x18000e2f4  mov     [rbp+57h+Binding], rsi
0x18000e2f8  cmp     [rbp+57h+String], rsi
0x18000e2fc  jz      short loc_18000E308
0x18000e2fe  lea     rcx, [rbp+57h+String]; String
0x18000e302  call    cs:__imp_RpcStringFreeA
0x18000e308  mov     rcx, [rbp+57h+var_60]; pSid
0x18000e30c  test    rcx, rcx
0x18000e30f  jz      short loc_18000E317
0x18000e311  call    cs:__imp_FreeSid
0x18000e317  mov     rax, [rbp+57h+Binding]
0x18000e31b  mov     [rdi], rax
0x18000e31e  mov     eax, ebx
0x18000e320  mov     rcx, [rbp+57h+var_28]
0x18000e324  xor     rcx, rsp; StackCookie
0x18000e327  call    __security_check_cookie
0x18000e32c  add     rsp, 0B8h
0x18000e333  pop     rdi
0x18000e334  pop     rsi
0x18000e335  pop     rbx
0x18000e336  pop     rbp
0x18000e337  retn
```
