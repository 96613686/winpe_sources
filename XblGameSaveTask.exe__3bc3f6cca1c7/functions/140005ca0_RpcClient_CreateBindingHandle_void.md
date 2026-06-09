# RpcClient::CreateBindingHandle(void * *)

- ea: `0x140005ca0`
- end: `0x140005eb7`
- name: `?CreateBindingHandle@RpcClient@@IEAAKPEAPEAX@Z`
- size: `535`
- prototype: `int __fastcall(RpcClient *this, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400057f8`

## callees

- `0x140004704`
- `0x140005ca0`
- `0x140005fb0`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x140005da3`
- `RPCRT4!RpcBindingFree` at `0x140005e38`
- `RPCRT4!RpcBindingFree` at `0x140005e7f`
- `RPCRT4!RpcBindingFree` at `0x140005da3`
- `RPCRT4!RpcBindingFree` at `0x140005e38`
- `RPCRT4!RpcBindingFree` at `0x140005e7f`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x140005d35`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x140005d35`
- `RPCRT4!RpcStringBindingComposeW` at `0x140005d0d`
- `RPCRT4!RpcStringBindingComposeW` at `0x140005d0d`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x140005e11`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x140005e11`
- `RPCRT4!RpcStringFreeW` at `0x140005d5c`
- `RPCRT4!RpcStringFreeW` at `0x140005e48`
- `RPCRT4!RpcStringFreeW` at `0x140005e8f`
- `RPCRT4!RpcStringFreeW` at `0x140005d5c`
- `RPCRT4!RpcStringFreeW` at `0x140005e48`
- `RPCRT4!RpcStringFreeW` at `0x140005e8f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140005d74`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140005d74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005e51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005ea4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005e51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140005ea4`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140005db7`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140005db7`

## string_xrefs

- `0x140005d86`: `onecoreuap\xbox\ConnectedStorage\common\rpcclient.h`
- `0x140005dc5`: `onecoreuap\xbox\ConnectedStorage\common\rpcclient.h`

## pseudocode

```c
int __fastcall RpcClient::CreateBindingHandle(RpcClient *this, void **a2)
{
  void *v4; // rbx
  char *v5; // rcx
  unsigned int v6; // eax
  unsigned int v7; // r8d
  unsigned int v9; // eax
  unsigned int v10; // r8d
  int LastError; // ebx
  HLOCAL v12; // rax
  const char *v13; // r9
  const char *v14; // r9
  int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // r8d
  int v18; // edi
  RPC_BINDING_HANDLE v19; // rax
  unsigned int Options; // [rsp+20h] [rbp-50h]
  unsigned int Optionsa; // [rsp+20h] [rbp-50h]
  RPC_SECURITY_QOS SecurityQOS; // [rsp+40h] [rbp-30h] BYREF
  __int128 v23; // [rsp+50h] [rbp-20h]
  void *v24; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  DWORD cbSid; // [rsp+A0h] [rbp+30h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+A8h] [rbp+38h] BYREF
  RPC_WSTR String; // [rsp+B0h] [rbp+40h] BYREF

  *a2 = 0;
  v4 = 0;
  String = 0;
  Binding = 0;
  SecurityQOS = 0;
  v24 = 0;
  v23 = 0;
  cbSid = 0;
  if ( !*((_QWORD *)this + 1) )
  {
    v5 = (char *)this + 16;
    if ( *((_QWORD *)v5 + 3) > 7u )
      v5 = *(char **)v5;
    v6 = RpcStringBindingComposeW((RPC_WSTR)v5, (RPC_WSTR)L"ncalrpc", 0, 0, 0, &String);
    if ( v6 )
      return wil::details::in1diag3::Return_Win32(retaddr, (void *)0x69, v7, (const char *)v6, Options);
    v9 = RpcBindingFromStringBindingW(String, &Binding);
    if ( v9 )
    {
      LastError = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x73, v10, (const char *)v9, Options);
LABEL_8:
      if ( String )
        RpcStringFreeW(&String);
      return LastError;
    }
    cbSid = 68;
    v12 = LocalAlloc(0x40u, 0x44u);
    v4 = v12;
    if ( !v12 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x85,
                    (unsigned int)"onecoreuap\\xbox\\ConnectedStorage\\common\\rpcclient.h",
                    v13);
      if ( Binding )
        RpcBindingFree(&Binding);
      goto LABEL_8;
    }
    if ( !CreateWellKnownSid(WinLocalSystemSid, 0, v12, &cbSid) )
    {
      v15 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x8B,
              (unsigned int)"onecoreuap\\xbox\\ConnectedStorage\\common\\rpcclient.h",
              v14);
LABEL_18:
      v18 = v15;
      if ( Binding )
        RpcBindingFree(&Binding);
      if ( String )
        RpcStringFreeW(&String);
      LocalFree(v4);
      return v18;
    }
    v24 = v4;
    SecurityQOS.Version = 3;
    SecurityQOS.ImpersonationType = 3;
    SecurityQOS.Capabilities = 1;
    SecurityQOS.IdentityTracking = 1;
    v16 = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xAu, 0, 0, &SecurityQOS);
    if ( v16 )
    {
      v15 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x9D, v17, (const char *)v16, Optionsa);
      goto LABEL_18;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)this + 1, (signed __int64)Binding, 0) )
    {
      v19 = Binding;
    }
    else
    {
      v19 = 0;
      Binding = 0;
    }
    if ( v19 )
      RpcBindingFree(&Binding);
    if ( String )
      RpcStringFreeW(&String);
  }
  *a2 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
    LocalFree(v4);
  return 0;
}

```

## disassembly

```asm
0x140005ca0  push    rbp
0x140005ca2  push    rbx
0x140005ca3  push    rsi
0x140005ca4  push    rdi
0x140005ca5  push    r14
0x140005ca7  mov     rbp, rsp
0x140005caa  sub     rsp, 70h
0x140005cae  xor     r14d, r14d
0x140005cb1  xor     eax, eax
0x140005cb3  xorps   xmm0, xmm0
0x140005cb6  mov     [rdx], r14
0x140005cb9  mov     rsi, rdx
0x140005cbc  mov     rdi, rcx
0x140005cbf  mov     ebx, r14d
0x140005cc2  mov     [rbp+String], r14
0x140005cc6  mov     [rbp+Binding], r14
0x140005cca  movups  xmmword ptr [rbp+var_30.Version], xmm0
0x140005cce  mov     [rbp+var_10], rax
0x140005cd2  movups  [rbp+var_20], xmm0
0x140005cd6  mov     [rbp+cbSid], r14d
0x140005cda  cmp     [rcx+8], r14
0x140005cde  jnz     loc_140005E95
0x140005ce4  add     rcx, 10h
0x140005ce8  cmp     qword ptr [rcx+18h], 7
0x140005ced  jbe     short loc_140005CF2
0x140005cef  mov     rcx, [rcx]; ObjUuid
0x140005cf2  lea     rax, [rbp+String]
0x140005cf6  xor     r9d, r9d; Endpoint
0x140005cf9  mov     [rsp+70h+StringBinding], rax; StringBinding
0x140005cfe  lea     rdx, ProtSeq; "ncalrpc"
0x140005d05  xor     r8d, r8d; NetworkAddr
0x140005d08  mov     [rsp+70h+Options], r14; unsigned int
0x140005d0d  call    cs:__imp_RpcStringBindingComposeW
0x140005d13  test    eax, eax
0x140005d15  jz      short loc_140005D2D
0x140005d17  mov     rcx, [rbp+28h]; this
0x140005d1b  mov     r9d, eax; char *
0x140005d1e  mov     edx, 69h ; 'i'; void *
0x140005d23  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140005d28  jmp     loc_140005EAC
0x140005d2d  mov     rcx, [rbp+String]; StringBinding
0x140005d31  lea     rdx, [rbp+Binding]; Binding
0x140005d35  call    cs:__imp_RpcBindingFromStringBindingW
0x140005d3b  test    eax, eax
0x140005d3d  jz      short loc_140005D69
0x140005d3f  mov     rcx, [rbp+28h]; this
0x140005d43  mov     r9d, eax; char *
0x140005d46  mov     edx, 73h ; 's'; void *
0x140005d4b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140005d50  mov     ebx, eax
0x140005d52  cmp     [rbp+String], r14
0x140005d56  jz      short loc_140005D62
0x140005d58  lea     rcx, [rbp+String]; String
0x140005d5c  call    cs:__imp_RpcStringFreeW
0x140005d62  mov     eax, ebx
0x140005d64  jmp     loc_140005EAC
0x140005d69  mov     edx, 44h ; 'D'; uBytes
0x140005d6e  mov     [rbp+cbSid], edx
0x140005d71  lea     ecx, [rdx-4]; uFlags
0x140005d74  call    cs:__imp_LocalAlloc
0x140005d7a  mov     rbx, rax
0x140005d7d  test    rax, rax
0x140005d80  jnz     short loc_140005DAB
0x140005d82  mov     rcx, [rbp+28h]; this
0x140005d86  lea     r8, aOnecoreuapXbox; "onecoreuap\\xbox\\ConnectedStorage\\com"...
0x140005d8d  mov     edx, 85h; void *
0x140005d92  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005d97  mov     ebx, eax
0x140005d99  cmp     [rbp+Binding], r14
0x140005d9d  jz      short loc_140005D52
0x140005d9f  lea     rcx, [rbp+Binding]; Binding
0x140005da3  call    cs:__imp_RpcBindingFree
0x140005da9  jmp     short loc_140005D52
0x140005dab  xor     edx, edx; DomainSid
0x140005dad  lea     r9, [rbp+cbSid]; cbSid
0x140005db1  mov     r8, rbx; pSid
0x140005db4  lea     ecx, [rdx+16h]; WellKnownSidType
0x140005db7  call    cs:__imp_CreateWellKnownSid
0x140005dbd  test    eax, eax
0x140005dbf  jnz     short loc_140005DD8
0x140005dc1  mov     rcx, [rbp+28h]; this
0x140005dc5  lea     r8, aOnecoreuapXbox; "onecoreuap\\xbox\\ConnectedStorage\\com"...
0x140005dcc  mov     edx, 8Bh; void *
0x140005dd1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005dd6  jmp     short loc_140005E2C
0x140005dd8  mov     ecx, 3
0x140005ddd  mov     [rbp+var_10], rbx
0x140005de1  mov     [rbp+var_30.Version], ecx
0x140005de4  xor     edx, edx; ServerPrincName
0x140005de6  mov     [rbp+var_30.ImpersonationType], ecx
0x140005de9  lea     eax, [rcx-2]
0x140005dec  mov     [rbp+var_30.Capabilities], eax
0x140005def  lea     r9d, [rcx+7]; AuthnSvc
0x140005df3  mov     [rbp+var_30.IdentityTracking], eax
0x140005df6  lea     r8d, [rcx+3]; AuthnLevel
0x140005dfa  mov     rcx, [rbp+Binding]; Binding
0x140005dfe  lea     rax, [rbp+var_30]
0x140005e02  mov     [rsp+70h+SecurityQOS], rax; SecurityQOS
0x140005e07  mov     dword ptr [rsp+70h+StringBinding], r14d; AuthzSvc
0x140005e0c  mov     [rsp+70h+Options], r14; unsigned int
0x140005e11  call    cs:__imp_RpcBindingSetAuthInfoExW
0x140005e17  test    eax, eax
0x140005e19  jz      short loc_140005E5B
0x140005e1b  mov     rcx, [rbp+28h]; this
0x140005e1f  mov     r9d, eax; char *
0x140005e22  mov     edx, 9Dh; void *
0x140005e27  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140005e2c  mov     edi, eax
0x140005e2e  cmp     [rbp+Binding], r14
0x140005e32  jz      short loc_140005E3E
0x140005e34  lea     rcx, [rbp+Binding]; Binding
0x140005e38  call    cs:__imp_RpcBindingFree
0x140005e3e  cmp     [rbp+String], r14
0x140005e42  jz      short loc_140005E4E
0x140005e44  lea     rcx, [rbp+String]; String
0x140005e48  call    cs:__imp_RpcStringFreeW
0x140005e4e  mov     rcx, rbx; hMem
0x140005e51  call    cs:__imp_LocalFree
0x140005e57  mov     eax, edi
0x140005e59  jmp     short loc_140005EAC
0x140005e5b  mov     rcx, [rbp+Binding]
0x140005e5f  xor     eax, eax
0x140005e61  lock cmpxchg [rdi+8], rcx
0x140005e67  jnz     short loc_140005E72
0x140005e69  mov     rax, r14
0x140005e6c  mov     [rbp+Binding], rax
0x140005e70  jmp     short loc_140005E76
0x140005e72  mov     rax, [rbp+Binding]
0x140005e76  test    rax, rax
0x140005e79  jz      short loc_140005E85
0x140005e7b  lea     rcx, [rbp+Binding]; Binding
0x140005e7f  call    cs:__imp_RpcBindingFree
0x140005e85  cmp     [rbp+String], r14
0x140005e89  jz      short loc_140005E95
0x140005e8b  lea     rcx, [rbp+String]; String
0x140005e8f  call    cs:__imp_RpcStringFreeW
0x140005e95  mov     rax, [rdi+8]
0x140005e99  mov     [rsi], rax
0x140005e9c  test    rbx, rbx
0x140005e9f  jz      short loc_140005EAA
0x140005ea1  mov     rcx, rbx; hMem
0x140005ea4  call    cs:__imp_LocalFree
0x140005eaa  xor     eax, eax
0x140005eac  add     rsp, 70h
0x140005eb0  pop     r14
0x140005eb2  pop     rdi
0x140005eb3  pop     rsi
0x140005eb4  pop     rbx
0x140005eb5  pop     rbp
0x140005eb6  retn
```
