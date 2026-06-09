# SetHelperTokens(IBackgroundCopyJob *,int)

- ea: `0x14004f12c`
- end: `0x14004f4c9`
- name: `?SetHelperTokens@@YAJPEAUIBackgroundCopyJob@@H@Z`
- size: `925`
- prototype: `__int64 __fastcall(struct IBackgroundCopyJob *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004c794`

## callees

- `0x1400095b4`
- `0x14004f12c`
- `0x14004f5e4`
- `0x14005d010`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x14004f2cc`
- `DMCmnUtils!DmGetActiveUserSid` at `0x14004f2cc`
- `DMCmnUtils!DmRevertToSelf` at `0x14004f3d6`
- `DMCmnUtils!DmRevertToSelf` at `0x14004f3d6`
- `DMCmnUtils!DmImpersonate` at `0x14004f320`
- `DMCmnUtils!DmImpersonate` at `0x14004f320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004f2a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004f2a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004f2ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004f2ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004f18e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004f20e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004f270`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004f2b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004f2fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004f34e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004f3b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004f404`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004f46f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004f49a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004f18e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004f20e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004f270`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004f2b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004f2fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004f34e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004f3b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004f404`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004f46f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14004f49a`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x14004f1e0`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x14004f1e0`

## string_xrefs

- `0x14004f426`: `SetHelperTokens: Reverted succeeded`
- `0x14004f292`: `SetHelperTokens: Impersonating`
- `0x14004f370`: `SetHelperTokens: Impersonating succeeded`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SetHelperTokens(struct IBackgroundCopyJob *a1, int a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  HRESULT v6; // eax
  int v7; // eax
  HLOCAL v8; // rdi
  DWORD LastError; // ebx
  int ActiveUserSid; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  DWORD dwAuthnLevel; // [rsp+20h] [rbp-20h]
  DWORD dwAuthnLevela; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  IUnknown *pProxy; // [rsp+50h] [rbp+10h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp+20h] BYREF

  pProxy = 0;
  hMem = 0;
  v3 = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, GUID *, IUnknown **))a1->lpVtbl->QueryInterface)(
         a1,
         &GUID_9a2584c3_f7d2_457a_9a5e_22b67bffc7d2,
         &pProxy);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A2,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\bitshelper.cpp",
      (const char *)(unsigned int)v3,
      dwAuthnLevel);
    if ( hMem )
      LocalFree(hMem);
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    return v4;
  }
  v6 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0x40u);
  v4 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\bitshelper.cpp",
      (const char *)(unsigned int)v6,
      dwAuthnLevela);
    if ( hMem )
      LocalFree(hMem);
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    return v4;
  }
  if ( a2 )
  {
    v7 = ((__int64 (__fastcall *)(IUnknown *))pProxy->lpVtbl[1].Release)(pProxy);
    v4 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B6,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\bitshelper.cpp",
        (const char *)(unsigned int)v7,
        dwAuthnLevela);
      if ( hMem )
        LocalFree(hMem);
      if ( pProxy )
        ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
      return v4;
    }
  }
  else
  {
    LogTelemetryInfo(L"SetHelperTokens: Impersonating");
    v8 = hMem;
    if ( hMem )
    {
      LastError = GetLastError();
      LocalFree(v8);
      SetLastError(LastError);
    }
    hMem = 0;
    ActiveUserSid = DmGetActiveUserSid((unsigned __int16 **)&hMem);
    v4 = ActiveUserSid;
    if ( ActiveUserSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BB,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\bitshelper.cpp",
        (const char *)(unsigned int)ActiveUserSid,
        dwAuthnLevela);
      if ( hMem )
        LocalFree(hMem);
      if ( pProxy )
        ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
      return v4;
    }
    v11 = DmImpersonate((const unsigned __int16 *)hMem);
    v4 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BC,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\bitshelper.cpp",
        (const char *)(unsigned int)v11,
        dwAuthnLevela);
      if ( hMem )
        LocalFree(hMem);
      if ( pProxy )
        ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
      return v4;
    }
    LogTelemetryInfo(L"SetHelperTokens: Impersonating succeeded");
    v12 = ((__int64 (__fastcall *)(IUnknown *))pProxy->lpVtbl[1].Release)(pProxy);
    v4 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BE,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\bitshelper.cpp",
        (const char *)(unsigned int)v12,
        dwAuthnLevela);
      if ( hMem )
        LocalFree(hMem);
      if ( pProxy )
        ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
      return v4;
    }
    v13 = DmRevertToSelf();
    v4 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BF,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\bitshelper.cpp",
        (const char *)(unsigned int)v13,
        dwAuthnLevela);
      if ( hMem )
        LocalFree(hMem);
      if ( pProxy )
        ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
      return v4;
    }
    LogTelemetryInfo(L"SetHelperTokens: Reverted succeeded");
  }
  v14 = ((__int64 (__fastcall *)(IUnknown *, __int64))pProxy->lpVtbl[1].QueryInterface)(pProxy, 2);
  v4 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C3,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\cdndownload\\cdnengine\\lib\\bitshelper.cpp",
      (const char *)(unsigned int)v14,
      dwAuthnLevela);
    if ( hMem )
      LocalFree(hMem);
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    return v4;
  }
  if ( hMem )
    LocalFree(hMem);
  if ( pProxy )
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
  return 0;
}

```

## disassembly

```asm
0x14004f12c  mov     [rsp-8+arg_8], rbx
0x14004f131  mov     [rsp-8+arg_18], rdi
0x14004f136  push    rbp
0x14004f137  mov     rbp, rsp
0x14004f13a  sub     rsp, 40h
0x14004f13e  mov     edi, edx
0x14004f140  mov     [rbp+pProxy], 0
0x14004f148  mov     [rbp+hMem], 0
0x14004f150  mov     rax, [rcx]
0x14004f153  lea     r8, [rbp+pProxy]
0x14004f157  lea     rdx, _GUID_9a2584c3_f7d2_457a_9a5e_22b67bffc7d2
0x14004f15e  mov     rax, [rax]
0x14004f161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f166  mov     ebx, eax
0x14004f168  test    eax, eax
0x14004f16a  jns     short loc_14004F1B2
0x14004f16c  mov     rcx, [rbp+8]; this
0x14004f170  mov     r9d, eax; char *
0x14004f173  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x14004f17a  mov     edx, 1A2h; void *
0x14004f17f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004f184  nop
0x14004f185  mov     rcx, [rbp+hMem]; hMem
0x14004f189  test    rcx, rcx
0x14004f18c  jz      short loc_14004F195
0x14004f18e  call    cs:__imp_LocalFree
0x14004f194  nop
0x14004f195  mov     rcx, [rbp+pProxy]
0x14004f199  test    rcx, rcx
0x14004f19c  jz      short loc_14004F1AB
0x14004f19e  mov     rax, [rcx]
0x14004f1a1  mov     rax, [rax+10h]
0x14004f1a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f1aa  nop
0x14004f1ab  mov     eax, ebx
0x14004f1ad  jmp     loc_14004F4B9
0x14004f1b2  mov     [rsp+40h+dwCapabilities], 40h ; '@'; dwCapabilities
0x14004f1ba  mov     [rsp+40h+pAuthInfo], 0; pAuthInfo
0x14004f1c3  mov     [rsp+40h+dwImpLevel], 3; dwImpLevel
0x14004f1cb  mov     [rsp+40h+dwAuthnLevel], 0; int
0x14004f1d3  xor     r9d, r9d; pServerPrincName
0x14004f1d6  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x14004f1d9  mov     r8d, edx; dwAuthzSvc
0x14004f1dc  mov     rcx, [rbp+pProxy]; pProxy
0x14004f1e0  call    cs:__imp_CoSetProxyBlanket
0x14004f1e6  mov     ebx, eax
0x14004f1e8  test    eax, eax
0x14004f1ea  jns     short loc_14004F230
0x14004f1ec  mov     rcx, [rbp+8]; this
0x14004f1f0  mov     r9d, eax; char *
0x14004f1f3  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x14004f1fa  mov     edx, 1B0h; void *
0x14004f1ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004f204  nop
0x14004f205  mov     rcx, [rbp+hMem]; hMem
0x14004f209  test    rcx, rcx
0x14004f20c  jz      short loc_14004F215
0x14004f20e  call    cs:__imp_LocalFree
0x14004f214  nop
0x14004f215  mov     rcx, [rbp+pProxy]
0x14004f219  test    rcx, rcx
0x14004f21c  jz      short loc_14004F22B
0x14004f21e  mov     rax, [rcx]
0x14004f221  mov     rax, [rax+10h]
0x14004f225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f22a  nop
0x14004f22b  jmp     loc_14004F1AB
0x14004f230  test    edi, edi
0x14004f232  jz      short loc_14004F292
0x14004f234  mov     rcx, [rbp+pProxy]
0x14004f238  mov     rax, [rcx]
0x14004f23b  mov     rax, [rax+28h]
0x14004f23f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f244  mov     ebx, eax
0x14004f246  test    eax, eax
0x14004f248  jns     loc_14004F432
0x14004f24e  mov     rcx, [rbp+8]; this
0x14004f252  mov     r9d, eax; char *
0x14004f255  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x14004f25c  mov     edx, 1B6h; void *
0x14004f261  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004f266  nop
0x14004f267  mov     rcx, [rbp+hMem]; hMem
0x14004f26b  test    rcx, rcx
0x14004f26e  jz      short loc_14004F277
0x14004f270  call    cs:__imp_LocalFree
0x14004f276  nop
0x14004f277  mov     rcx, [rbp+pProxy]
0x14004f27b  test    rcx, rcx
0x14004f27e  jz      short loc_14004F28D
0x14004f280  mov     rax, [rcx]
0x14004f283  mov     rax, [rax+10h]
0x14004f287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f28c  nop
0x14004f28d  jmp     loc_14004F1AB
0x14004f292  lea     rcx, aSethelpertoken_1; "SetHelperTokens: Impersonating"
0x14004f299  call    ?LogTelemetryInfo@@YAXPEBGZZ; LogTelemetryInfo(ushort const *,...)
0x14004f29e  mov     rdi, [rbp+hMem]
0x14004f2a2  test    rdi, rdi
0x14004f2a5  jz      short loc_14004F2C0
0x14004f2a7  call    cs:__imp_GetLastError
0x14004f2ad  mov     ebx, eax
0x14004f2af  mov     rcx, rdi; hMem
0x14004f2b2  call    cs:__imp_LocalFree
0x14004f2b8  mov     ecx, ebx; dwErrCode
0x14004f2ba  call    cs:__imp_SetLastError
0x14004f2c0  mov     [rbp+hMem], 0
0x14004f2c8  lea     rcx, [rbp+hMem]
0x14004f2cc  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x14004f2d2  mov     ebx, eax
0x14004f2d4  test    eax, eax
0x14004f2d6  jns     short loc_14004F31C
0x14004f2d8  mov     rcx, [rbp+8]; this
0x14004f2dc  mov     r9d, eax; char *
0x14004f2df  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x14004f2e6  mov     edx, 1BBh; void *
0x14004f2eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004f2f0  nop
0x14004f2f1  mov     rcx, [rbp+hMem]; hMem
0x14004f2f5  test    rcx, rcx
0x14004f2f8  jz      short loc_14004F301
0x14004f2fa  call    cs:__imp_LocalFree
0x14004f300  nop
0x14004f301  mov     rcx, [rbp+pProxy]
0x14004f305  test    rcx, rcx
0x14004f308  jz      short loc_14004F317
0x14004f30a  mov     rax, [rcx]
0x14004f30d  mov     rax, [rax+10h]
0x14004f311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f316  nop
0x14004f317  jmp     loc_14004F1AB
0x14004f31c  mov     rcx, [rbp+hMem]
0x14004f320  call    cs:__imp_?DmImpersonate@@YAJPEBG@Z; DmImpersonate(ushort const *)
0x14004f326  mov     ebx, eax
0x14004f328  test    eax, eax
0x14004f32a  jns     short loc_14004F370
0x14004f32c  mov     rcx, [rbp+8]; this
0x14004f330  mov     r9d, eax; char *
0x14004f333  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x14004f33a  mov     edx, 1BCh; void *
0x14004f33f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004f344  nop
0x14004f345  mov     rcx, [rbp+hMem]; hMem
0x14004f349  test    rcx, rcx
0x14004f34c  jz      short loc_14004F355
0x14004f34e  call    cs:__imp_LocalFree
0x14004f354  nop
0x14004f355  mov     rcx, [rbp+pProxy]
0x14004f359  test    rcx, rcx
0x14004f35c  jz      short loc_14004F36B
0x14004f35e  mov     rax, [rcx]
0x14004f361  mov     rax, [rax+10h]
0x14004f365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f36a  nop
0x14004f36b  jmp     loc_14004F1AB
0x14004f370  lea     rcx, aSethelpertoken_0; "SetHelperTokens: Impersonating succeede"...
0x14004f377  call    ?LogTelemetryInfo@@YAXPEBGZZ; LogTelemetryInfo(ushort const *,...)
0x14004f37c  mov     rcx, [rbp+pProxy]
0x14004f380  mov     rax, [rcx]
0x14004f383  mov     rax, [rax+28h]
0x14004f387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f38c  mov     ebx, eax
0x14004f38e  test    eax, eax
0x14004f390  jns     short loc_14004F3D6
0x14004f392  mov     rcx, [rbp+8]; this
0x14004f396  mov     r9d, eax; char *
0x14004f399  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x14004f3a0  mov     edx, 1BEh; void *
0x14004f3a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004f3aa  nop
0x14004f3ab  mov     rcx, [rbp+hMem]; hMem
0x14004f3af  test    rcx, rcx
0x14004f3b2  jz      short loc_14004F3BB
0x14004f3b4  call    cs:__imp_LocalFree
0x14004f3ba  nop
0x14004f3bb  mov     rcx, [rbp+pProxy]
0x14004f3bf  test    rcx, rcx
0x14004f3c2  jz      short loc_14004F3D1
0x14004f3c4  mov     rax, [rcx]
0x14004f3c7  mov     rax, [rax+10h]
0x14004f3cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f3d0  nop
0x14004f3d1  jmp     loc_14004F1AB
0x14004f3d6  call    cs:__imp_?DmRevertToSelf@@YAJXZ; DmRevertToSelf(void)
0x14004f3dc  mov     ebx, eax
0x14004f3de  test    eax, eax
0x14004f3e0  jns     short loc_14004F426
0x14004f3e2  mov     rcx, [rbp+8]; this
0x14004f3e6  mov     r9d, eax; char *
0x14004f3e9  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x14004f3f0  mov     edx, 1BFh; void *
0x14004f3f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004f3fa  nop
0x14004f3fb  mov     rcx, [rbp+hMem]; hMem
0x14004f3ff  test    rcx, rcx
0x14004f402  jz      short loc_14004F40B
0x14004f404  call    cs:__imp_LocalFree
0x14004f40a  nop
0x14004f40b  mov     rcx, [rbp+pProxy]
0x14004f40f  test    rcx, rcx
0x14004f412  jz      short loc_14004F421
0x14004f414  mov     rax, [rcx]
0x14004f417  mov     rax, [rax+10h]
0x14004f41b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f420  nop
0x14004f421  jmp     loc_14004F1AB
0x14004f426  lea     rcx, aSethelpertoken; "SetHelperTokens: Reverted succeeded"
0x14004f42d  call    ?LogTelemetryInfo@@YAXPEBGZZ; LogTelemetryInfo(ushort const *,...)
0x14004f432  mov     rcx, [rbp+pProxy]
0x14004f436  mov     rax, [rcx]
0x14004f439  mov     edx, 2
0x14004f43e  mov     rax, [rax+18h]
0x14004f442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f447  mov     ebx, eax
0x14004f449  test    eax, eax
0x14004f44b  jns     short loc_14004F491
0x14004f44d  mov     rcx, [rbp+8]; this
0x14004f451  mov     r9d, eax; char *
0x14004f454  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\enterprisemgmt\\cdnd"...
0x14004f45b  mov     edx, 1C3h; void *
0x14004f460  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004f465  nop
0x14004f466  mov     rcx, [rbp+hMem]; hMem
0x14004f46a  test    rcx, rcx
0x14004f46d  jz      short loc_14004F476
0x14004f46f  call    cs:__imp_LocalFree
0x14004f475  nop
0x14004f476  mov     rcx, [rbp+pProxy]
0x14004f47a  test    rcx, rcx
0x14004f47d  jz      short loc_14004F48C
0x14004f47f  mov     rax, [rcx]
0x14004f482  mov     rax, [rax+10h]
0x14004f486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f48b  nop
0x14004f48c  jmp     loc_14004F1AB
0x14004f491  mov     rcx, [rbp+hMem]; hMem
0x14004f495  test    rcx, rcx
0x14004f498  jz      short loc_14004F4A1
0x14004f49a  call    cs:__imp_LocalFree
0x14004f4a0  nop
0x14004f4a1  mov     rcx, [rbp+pProxy]
0x14004f4a5  test    rcx, rcx
0x14004f4a8  jz      short loc_14004F4B7
0x14004f4aa  mov     rax, [rcx]
0x14004f4ad  mov     rax, [rax+10h]
0x14004f4b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004f4b6  nop
0x14004f4b7  xor     eax, eax
0x14004f4b9  mov     rbx, [rsp+40h+arg_8]
0x14004f4be  mov     rdi, [rsp+40h+arg_18]
0x14004f4c3  add     rsp, 40h
0x14004f4c7  pop     rbp
0x14004f4c8  retn
```
