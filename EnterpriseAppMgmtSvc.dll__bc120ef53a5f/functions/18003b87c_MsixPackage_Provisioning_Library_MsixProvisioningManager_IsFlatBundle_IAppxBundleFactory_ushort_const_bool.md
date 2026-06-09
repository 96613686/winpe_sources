# MsixPackage::Provisioning::Library::MsixProvisioningManager::IsFlatBundle(IAppxBundleFactory *,ushort const *,bool &)

- ea: `0x18003b87c`
- end: `0x18003bfff`
- name: `?IsFlatBundle@MsixProvisioningManager@Library@Provisioning@MsixPackage@@AEAAJPEAUIAppxBundleFactory@@PEBGAEA_N@Z`
- size: `1923`
- prototype: `int(MsixPackage::Provisioning::Library::MsixProvisioningManager *__hidden this, struct IAppxBundleFactory *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18003aa78`

## callees

- `0x18000d3dc`
- `0x18003b87c`
- `0x18003d4ec`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b911`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bfdc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b911`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003bfdc`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18003b8b6`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18003b8b6`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x18003b948`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x18003b948`

## string_xrefs

- `0x18003b8e0`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003b976`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003b9eb`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003ba69`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003bc84`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003bd26`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003be54`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003bef6`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningmanager.cpp`
- `0x18003b967`: `Failed to open '%ws'.`

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
0x18003b87c  mov     [rsp-28h+arg_8], rbx
0x18003b881  mov     [rsp-28h+arg_0], rcx
0x18003b886  push    rbp
0x18003b887  push    rsi
0x18003b888  push    rdi
0x18003b889  push    r14
0x18003b88b  push    r15
0x18003b88d  mov     rbp, rsp
0x18003b890  sub     rsp, 70h
0x18003b894  mov     rsi, r9
0x18003b897  mov     rdi, r8
0x18003b89a  mov     r14, rdx
0x18003b89d  xor     r15d, r15d
0x18003b8a0  mov     [r9], r15b
0x18003b8a3  mov     [rbp+ppstm], r15
0x18003b8a7  mov     [rbp+ppszPathOut], r15
0x18003b8ab  lea     r8, [rbp+ppszPathOut]; ppszPathOut
0x18003b8af  lea     edx, [r15+1]; dwFlags
0x18003b8b3  mov     rcx, rdi; pszPathIn
0x18003b8b6  call    cs:__imp_PathAllocCanonicalize
0x18003b8bd  nop     dword ptr [rax+rax+00h]
0x18003b8c2  mov     ebx, eax
0x18003b8c4  test    eax, eax
0x18003b8c6  jns     short loc_18003B924
0x18003b8c8  mov     rcx, [rbp+28h]; this
0x18003b8cc  mov     [rsp+70h+var_48], rdi; char *
0x18003b8d1  lea     rax, aFailedToCanoni; "Failed to canonicalize '%ws'."
0x18003b8d8  mov     qword ptr [rsp+70h+var_50], rax; int
0x18003b8dd  mov     r9d, ebx; char *
0x18003b8e0  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003b8e7  mov     edx, 320h; void *
0x18003b8ec  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003b8f1  nop
0x18003b8f2  mov     rcx, [rbp+ppstm]
0x18003b8f6  test    rcx, rcx
0x18003b8f9  jz      short loc_18003B908
0x18003b8fb  mov     rax, [rcx]
0x18003b8fe  mov     rax, [rax+10h]
0x18003b902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b907  nop
0x18003b908  mov     rcx, [rbp+ppszPathOut]; hMem
0x18003b90c  test    rcx, rcx
0x18003b90f  jz      short loc_18003B91D
0x18003b911  call    cs:__imp_LocalFree
0x18003b918  nop     dword ptr [rax+rax+00h]
0x18003b91d  mov     eax, ebx
0x18003b91f  jmp     loc_18003BFEA
0x18003b924  mov     rcx, [rbp+ppstm]
0x18003b928  mov     [rbp+ppstm], r15
0x18003b92c  test    rcx, rcx
0x18003b92f  jz      short loc_18003B93E
0x18003b931  mov     rax, [rcx]
0x18003b934  mov     rax, [rax+10h]
0x18003b938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b93d  nop
0x18003b93e  lea     r8, [rbp+ppstm]; ppstm
0x18003b942  xor     edx, edx; grfMode
0x18003b944  mov     rcx, [rbp+ppszPathOut]; pszFile
0x18003b948  call    cs:__imp_SHCreateStreamOnFileW
0x18003b94f  nop     dword ptr [rax+rax+00h]
0x18003b954  mov     ebx, eax
0x18003b956  test    eax, eax
0x18003b958  jns     short loc_18003B9A3
0x18003b95a  mov     rcx, [rbp+28h]; this
0x18003b95e  mov     rdx, [rbp+ppszPathOut]
0x18003b962  mov     [rsp+70h+var_48], rdx; char *
0x18003b967  lea     rax, aFailedToOpenWs; "Failed to open '%ws'."
0x18003b96e  mov     qword ptr [rsp+70h+var_50], rax; int
0x18003b973  mov     r9d, ebx; char *
0x18003b976  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003b97d  mov     edx, 328h; void *
0x18003b982  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003b987  nop
0x18003b988  mov     rcx, [rbp+ppstm]
0x18003b98c  test    rcx, rcx
0x18003b98f  jz      short loc_18003B99E
0x18003b991  mov     rax, [rcx]
0x18003b994  mov     rax, [rax+10h]
0x18003b998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b99d  nop
0x18003b99e  jmp     loc_18003B908
0x18003b9a3  mov     rax, [r14]
0x18003b9a6  mov     [rbp+var_20], r15
0x18003b9aa  lea     r8, [rbp+var_20]
0x18003b9ae  mov     rdx, [rbp+ppstm]
0x18003b9b2  mov     rcx, r14
0x18003b9b5  mov     rax, [rax+20h]
0x18003b9b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b9be  test    eax, eax
0x18003b9c0  js      loc_18003BFA7
0x18003b9c6  mov     [rbp+var_28], r15
0x18003b9ca  mov     rcx, [rbp+var_20]
0x18003b9ce  mov     rax, [rcx]
0x18003b9d1  lea     rdx, [rbp+var_28]
0x18003b9d5  mov     rax, [rax+28h]
0x18003b9d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b9de  mov     ebx, eax
0x18003b9e0  test    eax, eax
0x18003b9e2  jns     short loc_18003BA44
0x18003b9e4  mov     rcx, [rbp+28h]; this
0x18003b9e8  mov     r9d, eax; char *
0x18003b9eb  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003b9f2  mov     edx, 32Fh; void *
0x18003b9f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b9fc  nop
0x18003b9fd  mov     rcx, [rbp+var_28]
0x18003ba01  test    rcx, rcx
0x18003ba04  jz      short loc_18003BA13
0x18003ba06  mov     rax, [rcx]
0x18003ba09  mov     rax, [rax+10h]
0x18003ba0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba12  nop
0x18003ba13  mov     rcx, [rbp+var_20]
0x18003ba17  test    rcx, rcx
0x18003ba1a  jz      short loc_18003BA29
0x18003ba1c  mov     rax, [rcx]
0x18003ba1f  mov     rax, [rax+10h]
0x18003ba23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba28  nop
0x18003ba29  mov     rcx, [rbp+ppstm]
0x18003ba2d  test    rcx, rcx
0x18003ba30  jz      short loc_18003BA3F
0x18003ba32  mov     rax, [rcx]
0x18003ba35  mov     rax, [rax+10h]
0x18003ba39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba3e  nop
0x18003ba3f  jmp     loc_18003B908
0x18003ba44  mov     [rbp+var_30], r15
0x18003ba48  mov     rcx, [rbp+var_28]
0x18003ba4c  mov     rax, [rcx]
0x18003ba4f  lea     rdx, [rbp+var_30]
0x18003ba53  mov     rax, [rax+20h]
0x18003ba57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba5c  mov     ebx, eax
0x18003ba5e  test    eax, eax
0x18003ba60  jns     short loc_18003BAD8
0x18003ba62  mov     rcx, [rbp+28h]; this
0x18003ba66  mov     r9d, eax; char *
0x18003ba69  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003ba70  mov     edx, 332h; void *
0x18003ba75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ba7a  nop
0x18003ba7b  mov     rcx, [rbp+var_30]
0x18003ba7f  test    rcx, rcx
0x18003ba82  jz      short loc_18003BA91
0x18003ba84  mov     rax, [rcx]
0x18003ba87  mov     rax, [rax+10h]
0x18003ba8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba90  nop
0x18003ba91  mov     rcx, [rbp+var_28]
0x18003ba95  test    rcx, rcx
0x18003ba98  jz      short loc_18003BAA7
0x18003ba9a  mov     rax, [rcx]
0x18003ba9d  mov     rax, [rax+10h]
0x18003baa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003baa6  nop
0x18003baa7  mov     rcx, [rbp+var_20]
0x18003baab  test    rcx, rcx
0x18003baae  jz      short loc_18003BABD
0x18003bab0  mov     rax, [rcx]
0x18003bab3  mov     rax, [rax+10h]
0x18003bab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003babc  nop
0x18003babd  mov     rcx, [rbp+ppstm]
0x18003bac1  test    rcx, rcx
0x18003bac4  jz      short loc_18003BAD3
0x18003bac6  mov     rax, [rcx]
0x18003bac9  mov     rax, [rax+10h]
0x18003bacd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bad2  nop
0x18003bad3  jmp     loc_18003B908
0x18003bad8  mov     dword ptr [rbp+arg_0], r15d
0x18003badc  mov     rcx, [rbp+var_30]
0x18003bae0  mov     rax, [rcx]
0x18003bae3  lea     rdx, [rbp+arg_0]
0x18003bae7  mov     rax, [rax+20h]
0x18003baeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003baf0  test    eax, eax
0x18003baf2  js      loc_18003BF7B
0x18003baf8  cmp     dword ptr [rbp+arg_0], r15d
0x18003bafc  jz      loc_18003BF7B
0x18003bb02  mov     [rbp+var_18], r15
0x18003bb06  mov     rcx, [rbp+var_30]
0x18003bb0a  mov     rax, [rcx]
0x18003bb0d  lea     rdx, [rbp+var_18]
0x18003bb11  mov     rax, [rax+18h]
0x18003bb15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb1a  mov     ebx, eax
0x18003bb1c  test    eax, eax
0x18003bb1e  js      loc_18003BEEF
0x18003bb24  mov     [rbp+var_10], r15
0x18003bb28  mov     rcx, [rbp+var_18]
0x18003bb2c  mov     rax, [rcx]
0x18003bb2f  lea     r8, [rbp+var_10]
0x18003bb33  lea     rdx, _GUID_44c2acbc_b2cf_4ccb_bbdb_9c6da8c3bc9e
0x18003bb3a  mov     rax, [rax]
0x18003bb3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb42  test    eax, eax
0x18003bb44  js      loc_18003BC02
0x18003bb4a  mov     dword ptr [rbp+arg_18], r15d
0x18003bb4e  mov     rcx, [rbp+var_10]
0x18003bb52  mov     rax, [rcx]
0x18003bb55  lea     rdx, [rbp+arg_18]
0x18003bb59  mov     rax, [rax+18h]
0x18003bb5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb62  mov     ebx, eax
0x18003bb64  test    eax, eax
0x18003bb66  js      loc_18003BC7D
0x18003bb6c  cmp     dword ptr [rbp+arg_18], r15d
0x18003bb70  jz      loc_18003BC2E
0x18003bb76  mov     byte ptr [rsi], 1
0x18003bb79  mov     rcx, [rbp+var_10]
0x18003bb7d  test    rcx, rcx
0x18003bb80  jz      short loc_18003BB8F
0x18003bb82  mov     rax, [rcx]
0x18003bb85  mov     rax, [rax+10h]
0x18003bb89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb8e  nop
0x18003bb8f  mov     rcx, [rbp+var_18]
0x18003bb93  test    rcx, rcx
0x18003bb96  jz      short loc_18003BBA5
0x18003bb98  mov     rax, [rcx]
0x18003bb9b  mov     rax, [rax+10h]
0x18003bb9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bba4  nop
0x18003bba5  mov     rcx, [rbp+var_30]
0x18003bba9  test    rcx, rcx
0x18003bbac  jz      short loc_18003BBBB
0x18003bbae  mov     rax, [rcx]
0x18003bbb1  mov     rax, [rax+10h]
0x18003bbb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbba  nop
0x18003bbbb  mov     rcx, [rbp+var_28]
0x18003bbbf  test    rcx, rcx
0x18003bbc2  jz      short loc_18003BBD1
0x18003bbc4  mov     rax, [rcx]
0x18003bbc7  mov     rax, [rax+10h]
0x18003bbcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbd0  nop
0x18003bbd1  mov     rcx, [rbp+var_20]
0x18003bbd5  test    rcx, rcx
0x18003bbd8  jz      short loc_18003BBE7
0x18003bbda  mov     rax, [rcx]
0x18003bbdd  mov     rax, [rax+10h]
0x18003bbe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbe6  nop
0x18003bbe7  mov     rcx, [rbp+ppstm]
0x18003bbeb  test    rcx, rcx
0x18003bbee  jz      short loc_18003BBFD
0x18003bbf0  mov     rax, [rcx]
0x18003bbf3  mov     rax, [rax+10h]
0x18003bbf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbfc  nop
0x18003bbfd  jmp     loc_18003BFD3
0x18003bc02  mov     [rbp+arg_18], r15
0x18003bc06  mov     rcx, [rbp+var_18]
0x18003bc0a  mov     rax, [rcx]
0x18003bc0d  lea     rdx, [rbp+arg_18]
0x18003bc11  mov     rax, [rax+30h]
0x18003bc15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc1a  mov     ebx, eax
0x18003bc1c  test    eax, eax
0x18003bc1e  js      loc_18003BE4D
0x18003bc24  cmp     [rbp+arg_18], r15
0x18003bc28  jz      loc_18003BDC1
0x18003bc2e  mov     rcx, [rbp+var_30]
0x18003bc32  mov     rax, [rcx]
0x18003bc35  lea     rdx, [rbp+arg_0]
0x18003bc39  mov     rax, [rax+28h]
0x18003bc3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc42  mov     ebx, eax
0x18003bc44  test    eax, eax
0x18003bc46  js      loc_18003BD1F
0x18003bc4c  mov     rcx, [rbp+var_10]
0x18003bc50  test    rcx, rcx
0x18003bc53  jz      short loc_18003BC62
0x18003bc55  mov     rax, [rcx]
0x18003bc58  mov     rax, [rax+10h]
0x18003bc5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc61  nop
0x18003bc62  mov     rcx, [rbp+var_18]
0x18003bc66  test    rcx, rcx
0x18003bc69  jz      short loc_18003BC78
0x18003bc6b  mov     rax, [rcx]
0x18003bc6e  mov     rax, [rax+10h]
0x18003bc72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc77  nop
0x18003bc78  jmp     loc_18003BADC
0x18003bc7d  mov     rcx, [rbp+28h]; this
0x18003bc81  mov     r9d, ebx; char *
0x18003bc84  lea     r8, aOnecoreAdminAp_6; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003bc8b  mov     edx, 33Eh; void *
0x18003bc90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bc95  nop
0x18003bc96  mov     rcx, [rbp+var_10]
0x18003bc9a  test    rcx, rcx
0x18003bc9d  jz      short loc_18003BCAC
0x18003bc9f  mov     rax, [rcx]
0x18003bca2  mov     rax, [rax+10h]
0x18003bca6  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
