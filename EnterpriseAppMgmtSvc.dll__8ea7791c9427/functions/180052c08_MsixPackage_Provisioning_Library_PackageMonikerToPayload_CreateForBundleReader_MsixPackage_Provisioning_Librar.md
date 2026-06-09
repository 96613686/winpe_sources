# MsixPackage::Provisioning::Library::PackageMonikerToPayload::CreateForBundleReader(MsixPackage::Provisioning::Library::MsixProvisioningContext *,IAppxBundleReader *,MsixPackage::Provisioning::Library::PackageMonikerToPayload * *)

- ea: `0x180052c08`
- end: `0x18005317d`
- name: `?CreateForBundleReader@PackageMonikerToPayload@Library@Provisioning@MsixPackage@@SAJPEAVMsixProvisioningContext@234@PEAUIAppxBundleReader@@PEAPEAV1234@@Z`
- size: `1397`
- prototype: `__int64 __fastcall(struct MsixPackage::Provisioning::Library::MsixProvisioningContext *, struct IAppxBundleReader *, struct MsixPackage::Provisioning::Library::PackageMonikerToPayload **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180056d60`

## callees

- `0x18001bf0c`
- `0x180032ad0`
- `0x180039e9c`
- `0x180047338`
- `0x180052c08`
- `0x180054b84`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180052f9c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180052f9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052c8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052d90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052e42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052ea9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052f05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053006`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053084`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053110`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052c8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052d90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052e42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052ea9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052f05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053006`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053084`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053110`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052e9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052e9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052eb1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180052eb1`

## string_xrefs

- `0x180052c62`: `Failed to create payload adapter for package.`
- `0x180052d66`: `Failed to get manifest reader for bundle.`

## pseudocode

```c
__int64 __fastcall MsixPackage::Provisioning::Library::PackageMonikerToPayload::CreateForBundleReader(
        struct MsixPackage::Provisioning::Library::MsixProvisioningContext *a1,
        struct IAppxBundleReader *a2,
        struct MsixPackage::Provisioning::Library::PackageMonikerToPayload **a3)
{
  int v6; // ebx
  struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *v8; // rbx
  __int64 v9; // rdi
  HRESULT (__stdcall *GetManifest)(IAppxBundleReader *, IAppxBundleManifestReader **); // rdi
  __int64 v11; // rcx
  int v12; // edi
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64 *); // r14
  __int64 v15; // rcx
  __int64 v16; // r15
  __int64 (__fastcall *v17)(__int64, LPVOID *); // r12
  DWORD LastError; // edi
  unsigned __int64 v19; // r8
  int i; // edi
  struct IAppxBundleReaderVtbl *lpVtbl; // rax
  int v22; // r14d
  const char *v23; // [rsp+28h] [rbp-58h]
  LPVOID pv; // [rsp+30h] [rbp-50h] BYREF
  __int64 v25; // [rsp+38h] [rbp-48h] BYREF
  __int64 v26; // [rsp+40h] [rbp-40h] BYREF
  __int64 v27; // [rsp+48h] [rbp-38h] BYREF
  struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *v28; // [rsp+50h] [rbp-30h] BYREF
  void *Src[3]; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v30; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v26 = 0;
  v25 = 0;
  pv = 0;
  *a3 = 0;
  v28 = 0;
  v6 = MsixPackage::Provisioning::Library::CContainer<IAppxFile,MsixPackage::Provisioning::Library::PackageMonikerToPayload>::Make(&v28);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
      (const char *)(unsigned int)v6,
      (int)"Failed to create payload adapter for package.",
      v23);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v28 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v28 + 16LL))(v28);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    return (unsigned int)v6;
  }
  v8 = v28;
  *((_QWORD *)v28 + 6) = a1;
  *((_DWORD *)v8 + 30) = 1;
  v9 = *((_QWORD *)v8 + 16);
  *((_QWORD *)v8 + 16) = a2;
  if ( a2 )
    ((void (__fastcall *)(struct IAppxBundleReader *))a2->lpVtbl->AddRef)(a2);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  *((_DWORD *)v8 + 40) = 1;
  GetManifest = a2->lpVtbl->GetManifest;
  v11 = v26;
  v26 = 0;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  v12 = ((__int64 (__fastcall *)(struct IAppxBundleReader *, __int64 *))GetManifest)(a2, &v26);
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
      (const char *)(unsigned int)v12,
      (int)"Failed to get manifest reader for bundle.",
      v23);
    if ( pv )
      CoTaskMemFree(pv);
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v8 + 16LL))(v8);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    return (unsigned int)v12;
  }
  v13 = v26;
  v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 24LL);
  v15 = v25;
  v25 = 0;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  v12 = v14(v13, &v25);
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x97,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
      (const char *)(unsigned int)v12,
      (int)"Failed to get identity for bundle.",
      v23);
    if ( pv )
      CoTaskMemFree(pv);
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v8 + 16LL))(v8);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    return (unsigned int)v12;
  }
  v16 = v25;
  v17 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v25 + 72LL);
  if ( pv )
  {
    LastError = GetLastError();
    CoTaskMemFree(pv);
    SetLastError(LastError);
  }
  pv = 0;
  v12 = v17(v16, &pv);
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
      (const char *)(unsigned int)v12,
      (int)"Failed to get fullname for bundle.",
      v23);
    if ( pv )
      CoTaskMemFree(pv);
    (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v8 + 16LL))(v8);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    return (unsigned int)v12;
  }
  v30 = 7;
  Src[2] = 0;
  LOWORD(Src[0]) = 0;
  if ( *(_WORD *)pv )
  {
    v19 = -1;
    do
      ++v19;
    while ( *((_WORD *)pv + v19) );
  }
  else
  {
    v19 = 0;
  }
  std::wstring::assign(Src, (char *)pv, v19);
  std::wstring::assign((char *)v8 + 56, Src);
  if ( v30 >= 8 )
    operator delete(Src[0]);
  for ( i = 0; i <= 2; ++i )
  {
    lpVtbl = a2->lpVtbl;
    v27 = 0;
    v22 = ((__int64 (__fastcall *)(struct IAppxBundleReader *, _QWORD, __int64 *))lpVtbl->GetFootprintFile)(
            a2,
            (unsigned int)i,
            &v27);
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xA2,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
        (const char *)(unsigned int)v22,
        (int)"Failed to get bundle footprint file.",
        v23);
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      if ( pv )
        CoTaskMemFree(pv);
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v8 + 16LL))(v8);
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      return (unsigned int)v22;
    }
    v22 = MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Insert(
            v8,
            v27);
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xA4,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\packagemonikertopayload.cpp",
        (const char *)(unsigned int)v22,
        (int)"Failed to insert footprint file into unpack list.",
        v23);
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      if ( pv )
        CoTaskMemFree(pv);
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::PackageMonikerToPayload *))(*(_QWORD *)v8 + 16LL))(v8);
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      return (unsigned int)v22;
    }
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  *a3 = v8;
  if ( pv )
    CoTaskMemFree(pv);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  return 0;
}

```

## disassembly

```asm
0x180052c08  mov     [rsp-38h+arg_0], rbx
0x180052c0d  push    rbp
0x180052c0e  push    rsi
0x180052c0f  push    rdi
0x180052c10  push    r12
0x180052c12  push    r13
0x180052c14  push    r14
0x180052c16  push    r15
0x180052c18  mov     rbp, rsp
0x180052c1b  sub     rsp, 80h
0x180052c22  mov     rax, cs:__security_cookie
0x180052c29  xor     rax, rsp
0x180052c2c  mov     [rbp+var_8], rax
0x180052c30  mov     r13, r8
0x180052c33  mov     rsi, rdx
0x180052c36  mov     rdi, rcx
0x180052c39  xor     r15d, r15d
0x180052c3c  mov     [rbp+var_40], r15
0x180052c40  mov     [rbp+var_48], r15
0x180052c44  mov     [rbp+pv], r15
0x180052c48  mov     [r8], r15
0x180052c4b  mov     [rbp+var_30], r15
0x180052c4f  lea     rcx, [rbp+var_30]
0x180052c53  call    ?Make@?$CContainer@UIAppxFile@@VPackageMonikerToPayload@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@SAJPEAPEAVPackageMonikerToPayload@234@@Z; MsixPackage::Provisioning::Library::CContainer<IAppxFile,MsixPackage::Provisioning::Library::PackageMonikerToPayload>::Make(MsixPackage::Provisioning::Library::PackageMonikerToPayload * *)
0x180052c58  mov     ebx, eax
0x180052c5a  test    eax, eax
0x180052c5c  jns     short loc_180052CDC
0x180052c5e  mov     rcx, [rbp+38h]; this
0x180052c62  lea     rax, aFailedToCreate_16; "Failed to create payload adapter for pa"...
0x180052c69  mov     qword ptr [rsp+80h+var_60], rax; int
0x180052c6e  mov     r9d, ebx; char *
0x180052c71  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180052c78  mov     edx, 8Eh; void *
0x180052c7d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180052c82  nop
0x180052c83  mov     rcx, [rbp+pv]; pv
0x180052c87  test    rcx, rcx
0x180052c8a  jz      short loc_180052C93
0x180052c8c  call    cs:__imp_CoTaskMemFree
0x180052c92  nop
0x180052c93  mov     rcx, [rbp+var_30]
0x180052c97  test    rcx, rcx
0x180052c9a  jz      short loc_180052CA9
0x180052c9c  mov     rax, [rcx]
0x180052c9f  mov     rax, [rax+10h]
0x180052ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ca8  nop
0x180052ca9  mov     rcx, [rbp+var_48]
0x180052cad  test    rcx, rcx
0x180052cb0  jz      short loc_180052CBF
0x180052cb2  mov     rax, [rcx]
0x180052cb5  mov     rax, [rax+10h]
0x180052cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052cbe  nop
0x180052cbf  mov     rcx, [rbp+var_40]
0x180052cc3  test    rcx, rcx
0x180052cc6  jz      short loc_180052CD5
0x180052cc8  mov     rax, [rcx]
0x180052ccb  mov     rax, [rax+10h]
0x180052ccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052cd4  nop
0x180052cd5  mov     eax, ebx
0x180052cd7  jmp     loc_180053156
0x180052cdc  mov     rbx, [rbp+var_30]
0x180052ce0  mov     [rbx+30h], rdi
0x180052ce4  mov     r14d, 1
0x180052cea  mov     [rbx+78h], r14d
0x180052cee  mov     rdi, [rbx+80h]
0x180052cf5  mov     [rbx+80h], rsi
0x180052cfc  test    rsi, rsi
0x180052cff  jz      short loc_180052D10
0x180052d01  mov     rax, [rsi]
0x180052d04  mov     rcx, rsi
0x180052d07  mov     rax, [rax+8]
0x180052d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d10  test    rdi, rdi
0x180052d13  jz      short loc_180052D25
0x180052d15  mov     rax, [rdi]
0x180052d18  mov     rcx, rdi
0x180052d1b  mov     rax, [rax+10h]
0x180052d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d24  nop
0x180052d25  mov     [rbx+0A0h], r14d
0x180052d2c  mov     rax, [rsi]
0x180052d2f  mov     rdi, [rax+28h]
0x180052d33  mov     rcx, [rbp+var_40]
0x180052d37  mov     [rbp+var_40], r15
0x180052d3b  test    rcx, rcx
0x180052d3e  jz      short loc_180052D4D
0x180052d40  mov     rdx, [rcx]
0x180052d43  mov     rax, [rdx+10h]
0x180052d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d4c  nop
0x180052d4d  lea     rdx, [rbp+var_40]
0x180052d51  mov     rcx, rsi
0x180052d54  mov     rax, rdi
0x180052d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d5c  mov     edi, eax
0x180052d5e  test    eax, eax
0x180052d60  jns     short loc_180052DDA
0x180052d62  mov     rcx, [rbp+38h]; this
0x180052d66  lea     rax, aFailedToGetMan_5; "Failed to get manifest reader for bundl"...
0x180052d6d  mov     qword ptr [rsp+80h+var_60], rax; int
0x180052d72  mov     r9d, edi; char *
0x180052d75  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180052d7c  mov     edx, 96h; void *
0x180052d81  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180052d86  nop
0x180052d87  mov     rcx, [rbp+pv]; pv
0x180052d8b  test    rcx, rcx
0x180052d8e  jz      short loc_180052D97
0x180052d90  call    cs:__imp_CoTaskMemFree
0x180052d96  nop
0x180052d97  mov     rax, [rbx]
0x180052d9a  mov     rcx, rbx
0x180052d9d  mov     rax, [rax+10h]
0x180052da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052da6  nop
0x180052da7  mov     rcx, [rbp+var_48]
0x180052dab  test    rcx, rcx
0x180052dae  jz      short loc_180052DBD
0x180052db0  mov     rax, [rcx]
0x180052db3  mov     rax, [rax+10h]
0x180052db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052dbc  nop
0x180052dbd  mov     rcx, [rbp+var_40]
0x180052dc1  test    rcx, rcx
0x180052dc4  jz      short loc_180052DD3
0x180052dc6  mov     rax, [rcx]
0x180052dc9  mov     rax, [rax+10h]
0x180052dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052dd2  nop
0x180052dd3  mov     eax, edi
0x180052dd5  jmp     loc_180053156
0x180052dda  mov     rdi, [rbp+var_40]
0x180052dde  mov     rax, [rdi]
0x180052de1  mov     r14, [rax+18h]
0x180052de5  mov     rcx, [rbp+var_48]
0x180052de9  mov     [rbp+var_48], r15
0x180052ded  test    rcx, rcx
0x180052df0  jz      short loc_180052DFF
0x180052df2  mov     rdx, [rcx]
0x180052df5  mov     rax, [rdx+10h]
0x180052df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052dfe  nop
0x180052dff  lea     rdx, [rbp+var_48]
0x180052e03  mov     rcx, rdi
0x180052e06  mov     rax, r14
0x180052e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e0e  mov     edi, eax
0x180052e10  test    eax, eax
0x180052e12  jns     short loc_180052E8A
0x180052e14  mov     rcx, [rbp+38h]; this
0x180052e18  lea     rax, aFailedToGetIde; "Failed to get identity for bundle."
0x180052e1f  mov     qword ptr [rsp+80h+var_60], rax; int
0x180052e24  mov     r9d, edi; char *
0x180052e27  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180052e2e  mov     edx, 97h; void *
0x180052e33  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180052e38  nop
0x180052e39  mov     rcx, [rbp+pv]; pv
0x180052e3d  test    rcx, rcx
0x180052e40  jz      short loc_180052E49
0x180052e42  call    cs:__imp_CoTaskMemFree
0x180052e48  nop
0x180052e49  mov     rax, [rbx]
0x180052e4c  mov     rcx, rbx
0x180052e4f  mov     rax, [rax+10h]
0x180052e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e58  nop
0x180052e59  mov     rcx, [rbp+var_48]
0x180052e5d  test    rcx, rcx
0x180052e60  jz      short loc_180052E6F
0x180052e62  mov     rax, [rcx]
0x180052e65  mov     rax, [rax+10h]
0x180052e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e6e  nop
0x180052e6f  mov     rcx, [rbp+var_40]
0x180052e73  test    rcx, rcx
0x180052e76  jz      short loc_180052E85
0x180052e78  mov     rax, [rcx]
0x180052e7b  mov     rax, [rax+10h]
0x180052e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e84  nop
0x180052e85  jmp     loc_180052DD3
0x180052e8a  mov     r15, [rbp+var_48]
0x180052e8e  mov     rax, [r15]
0x180052e91  mov     r12, [rax+48h]
0x180052e95  mov     r14, [rbp+pv]
0x180052e99  test    r14, r14
0x180052e9c  jz      short loc_180052EB7
0x180052e9e  call    cs:__imp_GetLastError
0x180052ea4  mov     edi, eax
0x180052ea6  mov     rcx, r14; pv
0x180052ea9  call    cs:__imp_CoTaskMemFree
0x180052eaf  mov     ecx, edi; dwErrCode
0x180052eb1  call    cs:__imp_SetLastError
0x180052eb7  mov     [rbp+pv], 0
0x180052ebf  lea     rdx, [rbp+pv]
0x180052ec3  mov     rcx, r15
0x180052ec6  mov     rax, r12
0x180052ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ece  mov     edi, eax
0x180052ed0  xor     r15d, r15d
0x180052ed3  test    eax, eax
0x180052ed5  jns     short loc_180052F4D
0x180052ed7  mov     rcx, [rbp+38h]; this
0x180052edb  lea     rax, aFailedToGetFul; "Failed to get fullname for bundle."
0x180052ee2  mov     qword ptr [rsp+80h+var_60], rax; int
0x180052ee7  mov     r9d, edi; char *
0x180052eea  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180052ef1  mov     edx, 98h; void *
0x180052ef6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180052efb  nop
0x180052efc  mov     rcx, [rbp+pv]; pv
0x180052f00  test    rcx, rcx
0x180052f03  jz      short loc_180052F0C
0x180052f05  call    cs:__imp_CoTaskMemFree
0x180052f0b  nop
0x180052f0c  mov     rax, [rbx]
0x180052f0f  mov     rcx, rbx
0x180052f12  mov     rax, [rax+10h]
0x180052f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f1b  nop
0x180052f1c  mov     rcx, [rbp+var_48]
0x180052f20  test    rcx, rcx
0x180052f23  jz      short loc_180052F32
0x180052f25  mov     rax, [rcx]
0x180052f28  mov     rax, [rax+10h]
0x180052f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f31  nop
0x180052f32  mov     rcx, [rbp+var_40]
0x180052f36  test    rcx, rcx
0x180052f39  jz      short loc_180052F48
0x180052f3b  mov     rax, [rcx]
0x180052f3e  mov     rax, [rax+10h]
0x180052f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f47  nop
0x180052f48  jmp     loc_180052DD3
0x180052f4d  mov     rdx, [rbp+pv]; Src
0x180052f51  mov     [rbp+var_10], 7
0x180052f59  mov     [rbp+var_18], r15
0x180052f5d  mov     word ptr [rbp+Src], r15w
0x180052f62  cmp     [rdx], r15w
0x180052f66  jnz     short loc_180052F6D
0x180052f68  mov     r8, r15
0x180052f6b  jmp     short loc_180052F7B
0x180052f6d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180052f71  inc     r8
0x180052f74  cmp     [rdx+r8*2], r15w
0x180052f79  jnz     short loc_180052F71
0x180052f7b  lea     rcx, [rbp+Src]; void *
0x180052f7f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180052f84  lea     rcx, [rbx+38h]; void *
0x180052f88  lea     rdx, [rbp+Src]; Src
0x180052f8c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@$$QEAV12@@Z; std::wstring::assign(std::wstring &&)
0x180052f91  cmp     [rbp+var_10], 8
0x180052f96  jb      short loc_180052FA2
0x180052f98  mov     rcx, [rbp+Src]
0x180052f9c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180052fa2  mov     edi, r15d
0x180052fa5  mov     rax, [rsi]
0x180052fa8  mov     [rbp+var_38], r15
0x180052fac  lea     r8, [rbp+var_38]
0x180052fb0  mov     edx, edi
0x180052fb2  mov     rcx, rsi
0x180052fb5  mov     rax, [rax+18h]
0x180052fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052fbe  mov     r14d, eax
0x180052fc1  test    eax, eax
0x180052fc3  js      loc_1800530CC
0x180052fc9  mov     rdx, [rbp+var_38]
0x180052fcd  mov     rcx, rbx
0x180052fd0  call    ?Insert@?$CContainer@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@VMsixAdapterCollection@234@@Library@Provisioning@MsixPackage@@QEAAJPEAVMsixPackageAdapter@234@@Z; MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Insert(MsixPackage::Provisioning::Library::MsixPackageAdapter *)
0x180052fd5  mov     r14d, eax
0x180052fd8  test    eax, eax
0x180052fda  js      short loc_180053040
0x180052fdc  mov     rcx, [rbp+var_38]
0x180052fe0  test    rcx, rcx
0x180052fe3  jz      short loc_180052FF2
0x180052fe5  mov     rax, [rcx]
0x180052fe8  mov     rax, [rax+10h]
0x180052fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ff1  nop
0x180052ff2  inc     edi
0x180052ff4  cmp     edi, 2
0x180052ff7  jle     short loc_180052FA5
0x180052ff9  mov     [r13+0], rbx
0x180052ffd  mov     rcx, [rbp+pv]; pv
0x180053001  test    rcx, rcx
0x180053004  jz      short loc_18005300D
0x180053006  call    cs:__imp_CoTaskMemFree
0x18005300c  nop
0x18005300d  mov     rcx, [rbp+var_48]
0x180053011  test    rcx, rcx
0x180053014  jz      short loc_180053023
0x180053016  mov     rax, [rcx]
0x180053019  mov     rax, [rax+10h]
0x18005301d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053022  nop
  ... truncated ...
```
