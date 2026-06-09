# MsixPackage::Provisioning::Library::MsixProvisioningManager::IsFlatBundle(IAppxBundleFactory *,ushort const *,bool &)

- ea: `0x180038350`
- end: `0x180038aba`
- name: `?IsFlatBundle@MsixProvisioningManager@Library@Provisioning@MsixPackage@@AEAAJPEAUIAppxBundleFactory@@PEBGAEA_N@Z`
- size: `1898`
- prototype: `int(MsixPackage::Provisioning::Library::MsixProvisioningManager *__hidden this, struct IAppxBundleFactory *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18003764c`

## callees

- `0x18000cfe8`
- `0x180038350`
- `0x180039e9c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800383df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038a9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800383df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038a9e`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18003838a`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18003838a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x180038410`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x180038410`

## string_xrefs

- `0x1800383ae`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180038438`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x1800384ad`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003852b`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180038746`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x1800387e8`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180038916`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x1800389b8`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x180038429`: `Failed to open '%ws'.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningManager::IsFlatBundle(
        MsixPackage::Provisioning::Library::MsixProvisioningManager *this,
        struct IAppxBundleFactory *a2,
        const unsigned __int16 *a3,
        bool *a4)
{
  HRESULT v7; // ebx
  struct IAppxBundleFactoryVtbl *lpVtbl; // rax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // [rsp+20h] [rbp-50h]
  IStream *ppstm; // [rsp+30h] [rbp-40h] BYREF
  PWSTR ppszPathOut; // [rsp+38h] [rbp-38h] BYREF
  __int64 v19; // [rsp+40h] [rbp-30h] BYREF
  __int64 v20; // [rsp+48h] [rbp-28h] BYREF
  __int64 v21; // [rsp+50h] [rbp-20h] BYREF
  __int64 v22; // [rsp+58h] [rbp-18h] BYREF
  __int64 v23; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  MsixPackage::Provisioning::Library::MsixProvisioningManager *v25; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v26; // [rsp+B8h] [rbp+48h] BYREF

  v25 = this;
  *a4 = 0;
  ppstm = 0;
  ppszPathOut = 0;
  v7 = PathAllocCanonicalize(a3, 1u, &ppszPathOut);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x320,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)v7,
      (int)"Failed to canonicalize '%ws'.",
      (const char *)a3);
LABEL_3:
    if ( ppszPathOut )
      LocalFree(ppszPathOut);
    return (unsigned int)v7;
  }
  ppstm = 0;
  v7 = SHCreateStreamOnFileW(ppszPathOut, 0, &ppstm);
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x328,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
      (const char *)(unsigned int)v7,
      (int)"Failed to open '%ws'.",
      (const char *)ppszPathOut);
    if ( ppstm )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
    goto LABEL_3;
  }
  lpVtbl = a2->lpVtbl;
  v21 = 0;
  if ( ((int (__fastcall *)(struct IAppxBundleFactory *, IStream *, __int64 *))lpVtbl->CreateBundleReader)(
         a2,
         ppstm,
         &v21) >= 0 )
  {
    v20 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 40LL))(v21, &v20);
    v7 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x32F,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
        (const char *)(unsigned int)v10,
        v16);
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      if ( v21 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      if ( ppstm )
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
      goto LABEL_3;
    }
    v19 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 32LL))(v20, &v19);
    v7 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x332,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
        (const char *)(unsigned int)v11,
        v16);
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      if ( v21 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      if ( ppstm )
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
      goto LABEL_3;
    }
    LODWORD(v25) = 0;
    while ( (*(int (__fastcall **)(__int64, MsixPackage::Provisioning::Library::MsixProvisioningManager **))(*(_QWORD *)v19 + 32LL))(
              v19,
              &v25) >= 0
         && (_DWORD)v25 )
    {
      v22 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 24LL))(v19, &v22);
      v7 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x338,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
          (const char *)(unsigned int)v12,
          v16);
        if ( v22 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        if ( v19 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        if ( v21 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        if ( ppstm )
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
        goto LABEL_3;
      }
      v23 = 0;
      if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v22)(
             v22,
             &GUID_44c2acbc_b2cf_4ccb_bbdb_9c6da8c3bc9e,
             &v23) < 0 )
      {
        v26 = 0;
        v14 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 48LL))(v22, &v26);
        v7 = v14;
        if ( v14 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x34A,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
            (const char *)(unsigned int)v14,
            v16);
          if ( v23 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          if ( v22 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          if ( v19 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          if ( v20 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          if ( v21 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          if ( ppstm )
            (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
          goto LABEL_3;
        }
        if ( !v26 )
        {
          *a4 = 1;
          if ( v23 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          if ( v22 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          if ( v19 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          if ( v20 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          if ( v21 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          if ( ppstm )
            (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
          goto LABEL_128;
        }
      }
      else
      {
        LODWORD(v26) = 0;
        v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 24LL))(v23, &v26);
        v7 = v13;
        if ( v13 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x33E,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
            (const char *)(unsigned int)v13,
            v16);
          if ( v23 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          if ( v22 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          if ( v19 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          if ( v20 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          if ( v21 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          if ( ppstm )
            (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
          goto LABEL_3;
        }
        if ( (_DWORD)v26 )
        {
          *a4 = 1;
          if ( v23 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          if ( v22 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          if ( v19 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          if ( v20 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          if ( v21 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          if ( ppstm )
            (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
          goto LABEL_128;
        }
      }
      v15 = (*(__int64 (__fastcall **)(__int64, MsixPackage::Provisioning::Library::MsixProvisioningManager **))(*(_QWORD *)v19 + 40LL))(
              v19,
              &v25);
      v7 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x353,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningmanager.cpp",
          (const char *)(unsigned int)v15,
          v16);
        if ( v23 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        if ( v22 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        if ( v19 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        if ( v21 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        if ( ppstm )
          (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
        goto LABEL_3;
      }
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( ppstm )
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)ppstm + 16LL))(ppstm);
LABEL_128:
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
  return 0;
}

```

## disassembly

```asm
0x180038350  mov     [rsp-28h+arg_8], rbx
0x180038355  mov     [rsp-28h+arg_0], rcx
0x18003835a  push    rbp
0x18003835b  push    rsi
0x18003835c  push    rdi
0x18003835d  push    r14
0x18003835f  push    r15
0x180038361  mov     rbp, rsp
0x180038364  sub     rsp, 70h
0x180038368  mov     rsi, r9
0x18003836b  mov     rdi, r8
0x18003836e  mov     r14, rdx
0x180038371  xor     r15d, r15d
0x180038374  mov     [r9], r15b
0x180038377  mov     [rbp+ppstm], r15
0x18003837b  mov     [rbp+ppszPathOut], r15
0x18003837f  lea     r8, [rbp+ppszPathOut]; ppszPathOut
0x180038383  lea     edx, [r15+1]; dwFlags
0x180038387  mov     rcx, rdi; pszPathIn
0x18003838a  call    cs:__imp_PathAllocCanonicalize
0x180038390  mov     ebx, eax
0x180038392  test    eax, eax
0x180038394  jns     short loc_1800383EC
0x180038396  mov     rcx, [rbp+28h]; this
0x18003839a  mov     [rsp+70h+var_48], rdi; char *
0x18003839f  lea     rax, aFailedToCanoni; "Failed to canonicalize '%ws'."
0x1800383a6  mov     qword ptr [rsp+70h+var_50], rax; int
0x1800383ab  mov     r9d, ebx; char *
0x1800383ae  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800383b5  mov     edx, 320h; void *
0x1800383ba  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800383bf  nop
0x1800383c0  mov     rcx, [rbp+ppstm]
0x1800383c4  test    rcx, rcx
0x1800383c7  jz      short loc_1800383D6
0x1800383c9  mov     rax, [rcx]
0x1800383cc  mov     rax, [rax+10h]
0x1800383d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800383d5  nop
0x1800383d6  mov     rcx, [rbp+ppszPathOut]; hMem
0x1800383da  test    rcx, rcx
0x1800383dd  jz      short loc_1800383E5
0x1800383df  call    cs:__imp_LocalFree
0x1800383e5  mov     eax, ebx
0x1800383e7  jmp     loc_180038AA6
0x1800383ec  mov     rcx, [rbp+ppstm]
0x1800383f0  mov     [rbp+ppstm], r15
0x1800383f4  test    rcx, rcx
0x1800383f7  jz      short loc_180038406
0x1800383f9  mov     rax, [rcx]
0x1800383fc  mov     rax, [rax+10h]
0x180038400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038405  nop
0x180038406  lea     r8, [rbp+ppstm]; ppstm
0x18003840a  xor     edx, edx; grfMode
0x18003840c  mov     rcx, [rbp+ppszPathOut]; pszFile
0x180038410  call    cs:__imp_SHCreateStreamOnFileW
0x180038416  mov     ebx, eax
0x180038418  test    eax, eax
0x18003841a  jns     short loc_180038465
0x18003841c  mov     rcx, [rbp+28h]; this
0x180038420  mov     rdx, [rbp+ppszPathOut]
0x180038424  mov     [rsp+70h+var_48], rdx; char *
0x180038429  lea     rax, aFailedToOpenWs; "Failed to open '%ws'."
0x180038430  mov     qword ptr [rsp+70h+var_50], rax; int
0x180038435  mov     r9d, ebx; char *
0x180038438  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003843f  mov     edx, 328h; void *
0x180038444  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180038449  nop
0x18003844a  mov     rcx, [rbp+ppstm]
0x18003844e  test    rcx, rcx
0x180038451  jz      short loc_180038460
0x180038453  mov     rax, [rcx]
0x180038456  mov     rax, [rax+10h]
0x18003845a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003845f  nop
0x180038460  jmp     loc_1800383D6
0x180038465  mov     rax, [r14]
0x180038468  mov     [rbp+var_20], r15
0x18003846c  lea     r8, [rbp+var_20]
0x180038470  mov     rdx, [rbp+ppstm]
0x180038474  mov     rcx, r14
0x180038477  mov     rax, [rax+20h]
0x18003847b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038480  test    eax, eax
0x180038482  js      loc_180038A69
0x180038488  mov     [rbp+var_28], r15
0x18003848c  mov     rcx, [rbp+var_20]
0x180038490  mov     rax, [rcx]
0x180038493  lea     rdx, [rbp+var_28]
0x180038497  mov     rax, [rax+28h]
0x18003849b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384a0  mov     ebx, eax
0x1800384a2  test    eax, eax
0x1800384a4  jns     short loc_180038506
0x1800384a6  mov     rcx, [rbp+28h]; this
0x1800384aa  mov     r9d, eax; char *
0x1800384ad  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800384b4  mov     edx, 32Fh; void *
0x1800384b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800384be  nop
0x1800384bf  mov     rcx, [rbp+var_28]
0x1800384c3  test    rcx, rcx
0x1800384c6  jz      short loc_1800384D5
0x1800384c8  mov     rax, [rcx]
0x1800384cb  mov     rax, [rax+10h]
0x1800384cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384d4  nop
0x1800384d5  mov     rcx, [rbp+var_20]
0x1800384d9  test    rcx, rcx
0x1800384dc  jz      short loc_1800384EB
0x1800384de  mov     rax, [rcx]
0x1800384e1  mov     rax, [rax+10h]
0x1800384e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384ea  nop
0x1800384eb  mov     rcx, [rbp+ppstm]
0x1800384ef  test    rcx, rcx
0x1800384f2  jz      short loc_180038501
0x1800384f4  mov     rax, [rcx]
0x1800384f7  mov     rax, [rax+10h]
0x1800384fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038500  nop
0x180038501  jmp     loc_1800383D6
0x180038506  mov     [rbp+var_30], r15
0x18003850a  mov     rcx, [rbp+var_28]
0x18003850e  mov     rax, [rcx]
0x180038511  lea     rdx, [rbp+var_30]
0x180038515  mov     rax, [rax+20h]
0x180038519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003851e  mov     ebx, eax
0x180038520  test    eax, eax
0x180038522  jns     short loc_18003859A
0x180038524  mov     rcx, [rbp+28h]; this
0x180038528  mov     r9d, eax; char *
0x18003852b  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180038532  mov     edx, 332h; void *
0x180038537  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003853c  nop
0x18003853d  mov     rcx, [rbp+var_30]
0x180038541  test    rcx, rcx
0x180038544  jz      short loc_180038553
0x180038546  mov     rax, [rcx]
0x180038549  mov     rax, [rax+10h]
0x18003854d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038552  nop
0x180038553  mov     rcx, [rbp+var_28]
0x180038557  test    rcx, rcx
0x18003855a  jz      short loc_180038569
0x18003855c  mov     rax, [rcx]
0x18003855f  mov     rax, [rax+10h]
0x180038563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038568  nop
0x180038569  mov     rcx, [rbp+var_20]
0x18003856d  test    rcx, rcx
0x180038570  jz      short loc_18003857F
0x180038572  mov     rax, [rcx]
0x180038575  mov     rax, [rax+10h]
0x180038579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003857e  nop
0x18003857f  mov     rcx, [rbp+ppstm]
0x180038583  test    rcx, rcx
0x180038586  jz      short loc_180038595
0x180038588  mov     rax, [rcx]
0x18003858b  mov     rax, [rax+10h]
0x18003858f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038594  nop
0x180038595  jmp     loc_1800383D6
0x18003859a  mov     dword ptr [rbp+arg_0], r15d
0x18003859e  mov     rcx, [rbp+var_30]
0x1800385a2  mov     rax, [rcx]
0x1800385a5  lea     rdx, [rbp+arg_0]
0x1800385a9  mov     rax, [rax+20h]
0x1800385ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800385b2  test    eax, eax
0x1800385b4  js      loc_180038A3D
0x1800385ba  cmp     dword ptr [rbp+arg_0], r15d
0x1800385be  jz      loc_180038A3D
0x1800385c4  mov     [rbp+var_18], r15
0x1800385c8  mov     rcx, [rbp+var_30]
0x1800385cc  mov     rax, [rcx]
0x1800385cf  lea     rdx, [rbp+var_18]
0x1800385d3  mov     rax, [rax+18h]
0x1800385d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800385dc  mov     ebx, eax
0x1800385de  test    eax, eax
0x1800385e0  js      loc_1800389B1
0x1800385e6  mov     [rbp+var_10], r15
0x1800385ea  mov     rcx, [rbp+var_18]
0x1800385ee  mov     rax, [rcx]
0x1800385f1  lea     r8, [rbp+var_10]
0x1800385f5  lea     rdx, _GUID_44c2acbc_b2cf_4ccb_bbdb_9c6da8c3bc9e
0x1800385fc  mov     rax, [rax]
0x1800385ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038604  test    eax, eax
0x180038606  js      loc_1800386C4
0x18003860c  mov     dword ptr [rbp+arg_18], r15d
0x180038610  mov     rcx, [rbp+var_10]
0x180038614  mov     rax, [rcx]
0x180038617  lea     rdx, [rbp+arg_18]
0x18003861b  mov     rax, [rax+18h]
0x18003861f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038624  mov     ebx, eax
0x180038626  test    eax, eax
0x180038628  js      loc_18003873F
0x18003862e  cmp     dword ptr [rbp+arg_18], r15d
0x180038632  jz      loc_1800386F0
0x180038638  mov     byte ptr [rsi], 1
0x18003863b  mov     rcx, [rbp+var_10]
0x18003863f  test    rcx, rcx
0x180038642  jz      short loc_180038651
0x180038644  mov     rax, [rcx]
0x180038647  mov     rax, [rax+10h]
0x18003864b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038650  nop
0x180038651  mov     rcx, [rbp+var_18]
0x180038655  test    rcx, rcx
0x180038658  jz      short loc_180038667
0x18003865a  mov     rax, [rcx]
0x18003865d  mov     rax, [rax+10h]
0x180038661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038666  nop
0x180038667  mov     rcx, [rbp+var_30]
0x18003866b  test    rcx, rcx
0x18003866e  jz      short loc_18003867D
0x180038670  mov     rax, [rcx]
0x180038673  mov     rax, [rax+10h]
0x180038677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003867c  nop
0x18003867d  mov     rcx, [rbp+var_28]
0x180038681  test    rcx, rcx
0x180038684  jz      short loc_180038693
0x180038686  mov     rax, [rcx]
0x180038689  mov     rax, [rax+10h]
0x18003868d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038692  nop
0x180038693  mov     rcx, [rbp+var_20]
0x180038697  test    rcx, rcx
0x18003869a  jz      short loc_1800386A9
0x18003869c  mov     rax, [rcx]
0x18003869f  mov     rax, [rax+10h]
0x1800386a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800386a8  nop
0x1800386a9  mov     rcx, [rbp+ppstm]
0x1800386ad  test    rcx, rcx
0x1800386b0  jz      short loc_1800386BF
0x1800386b2  mov     rax, [rcx]
0x1800386b5  mov     rax, [rax+10h]
0x1800386b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800386be  nop
0x1800386bf  jmp     loc_180038A95
0x1800386c4  mov     [rbp+arg_18], r15
0x1800386c8  mov     rcx, [rbp+var_18]
0x1800386cc  mov     rax, [rcx]
0x1800386cf  lea     rdx, [rbp+arg_18]
0x1800386d3  mov     rax, [rax+30h]
0x1800386d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800386dc  mov     ebx, eax
0x1800386de  test    eax, eax
0x1800386e0  js      loc_18003890F
0x1800386e6  cmp     [rbp+arg_18], r15
0x1800386ea  jz      loc_180038883
0x1800386f0  mov     rcx, [rbp+var_30]
0x1800386f4  mov     rax, [rcx]
0x1800386f7  lea     rdx, [rbp+arg_0]
0x1800386fb  mov     rax, [rax+28h]
0x1800386ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038704  mov     ebx, eax
0x180038706  test    eax, eax
0x180038708  js      loc_1800387E1
0x18003870e  mov     rcx, [rbp+var_10]
0x180038712  test    rcx, rcx
0x180038715  jz      short loc_180038724
0x180038717  mov     rax, [rcx]
0x18003871a  mov     rax, [rax+10h]
0x18003871e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038723  nop
0x180038724  mov     rcx, [rbp+var_18]
0x180038728  test    rcx, rcx
0x18003872b  jz      short loc_18003873A
0x18003872d  mov     rax, [rcx]
0x180038730  mov     rax, [rax+10h]
0x180038734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038739  nop
0x18003873a  jmp     loc_18003859E
0x18003873f  mov     rcx, [rbp+28h]; this
0x180038743  mov     r9d, ebx; char *
0x180038746  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003874d  mov     edx, 33Eh; void *
0x180038752  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038757  nop
0x180038758  mov     rcx, [rbp+var_10]
0x18003875c  test    rcx, rcx
0x18003875f  jz      short loc_18003876E
0x180038761  mov     rax, [rcx]
0x180038764  mov     rax, [rax+10h]
0x180038768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003876d  nop
0x18003876e  mov     rcx, [rbp+var_18]
0x180038772  test    rcx, rcx
  ... truncated ...
```
