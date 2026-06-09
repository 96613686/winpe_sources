# MsixPackage::Provisioning::Library::PackageMonikerToPayload::CreateForBundleReader(MsixPackage::Provisioning::Library::MsixProvisioningContext *,IAppxBundleReader *,MsixPackage::Provisioning::Library::PackageMonikerToPayload * *)

- ea: `0x1800570c0`
- end: `0x18005767c`
- name: `?CreateForBundleReader@PackageMonikerToPayload@Library@Provisioning@MsixPackage@@SAJPEAVMsixProvisioningContext@234@PEAUIAppxBundleReader@@PEAPEAV1234@@Z`
- size: `1468`
- prototype: `__int64 __fastcall(struct MsixPackage::Provisioning::Library::MsixProvisioningContext *, struct IAppxBundleReader *, struct MsixPackage::Provisioning::Library::PackageMonikerToPayload **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005b444`

## callees

- `0x18001d160`
- `0x180035a84`
- `0x18003d4ec`
- `0x18004b384`
- `0x1800570c0`
- `0x180059118`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180057482`
- `msvcrt!??3@YAXPEAX@Z` at `0x180057482`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057148`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057252`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005730a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005737d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800573e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800574f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057576`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057608`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057148`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057252`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005730a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005737d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800573e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800574f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057576`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180057608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005736c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005736c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005738b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005738b`

## string_xrefs

- `0x18005711e`: `Failed to create payload adapter for package.`
- `0x180057228`: `Failed to get manifest reader for bundle.`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
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
  __int64 v19; // r8
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
  std::wstring::assign(Src, pv);
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
0x1800570c0  mov     [rsp-38h+arg_0], rbx
0x1800570c5  push    rbp
0x1800570c6  push    rsi
0x1800570c7  push    rdi
0x1800570c8  push    r12
0x1800570ca  push    r13
0x1800570cc  push    r14
0x1800570ce  push    r15
0x1800570d0  mov     rbp, rsp
0x1800570d3  sub     rsp, 80h
0x1800570da  mov     rax, cs:__security_cookie
0x1800570e1  xor     rax, rsp
0x1800570e4  mov     [rbp+var_8], rax
0x1800570e8  mov     r13, r8
0x1800570eb  mov     rsi, rdx
0x1800570ee  mov     rdi, rcx
0x1800570f1  xor     r15d, r15d
0x1800570f4  mov     [rbp+var_40], r15
0x1800570f8  mov     [rbp+var_48], r15
0x1800570fc  mov     [rbp+pv], r15
0x180057100  mov     [r8], r15
0x180057103  mov     [rbp+var_30], r15
0x180057107  lea     rcx, [rbp+var_30]
0x18005710b  call    ?Make@?$CContainer@UIAppxFile@@VPackageMonikerToPayload@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@SAJPEAPEAVPackageMonikerToPayload@234@@Z; MsixPackage::Provisioning::Library::CContainer<IAppxFile,MsixPackage::Provisioning::Library::PackageMonikerToPayload>::Make(MsixPackage::Provisioning::Library::PackageMonikerToPayload * *)
0x180057110  mov     ebx, eax
0x180057112  test    eax, eax
0x180057114  jns     loc_18005719E
0x18005711a  mov     rcx, [rbp+38h]; this
0x18005711e  lea     rax, aFailedToCreate_16; "Failed to create payload adapter for pa"...
0x180057125  mov     qword ptr [rsp+80h+var_60], rax; int
0x18005712a  mov     r9d, ebx; char *
0x18005712d  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180057134  mov     edx, 8Eh; void *
0x180057139  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005713e  nop
0x18005713f  mov     rcx, [rbp+pv]; pv
0x180057143  test    rcx, rcx
0x180057146  jz      short loc_180057155
0x180057148  call    cs:__imp_CoTaskMemFree
0x18005714f  nop     dword ptr [rax+rax+00h]
0x180057154  nop
0x180057155  mov     rcx, [rbp+var_30]
0x180057159  test    rcx, rcx
0x18005715c  jz      short loc_18005716B
0x18005715e  mov     rax, [rcx]
0x180057161  mov     rax, [rax+10h]
0x180057165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005716a  nop
0x18005716b  mov     rcx, [rbp+var_48]
0x18005716f  test    rcx, rcx
0x180057172  jz      short loc_180057181
0x180057174  mov     rax, [rcx]
0x180057177  mov     rax, [rax+10h]
0x18005717b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057180  nop
0x180057181  mov     rcx, [rbp+var_40]
0x180057185  test    rcx, rcx
0x180057188  jz      short loc_180057197
0x18005718a  mov     rax, [rcx]
0x18005718d  mov     rax, [rax+10h]
0x180057191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057196  nop
0x180057197  mov     eax, ebx
0x180057199  jmp     loc_180057654
0x18005719e  mov     rbx, [rbp+var_30]
0x1800571a2  mov     [rbx+30h], rdi
0x1800571a6  mov     r14d, 1
0x1800571ac  mov     [rbx+78h], r14d
0x1800571b0  mov     rdi, [rbx+80h]
0x1800571b7  mov     [rbx+80h], rsi
0x1800571be  test    rsi, rsi
0x1800571c1  jz      short loc_1800571D2
0x1800571c3  mov     rax, [rsi]
0x1800571c6  mov     rcx, rsi
0x1800571c9  mov     rax, [rax+8]
0x1800571cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800571d2  test    rdi, rdi
0x1800571d5  jz      short loc_1800571E7
0x1800571d7  mov     rax, [rdi]
0x1800571da  mov     rcx, rdi
0x1800571dd  mov     rax, [rax+10h]
0x1800571e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800571e6  nop
0x1800571e7  mov     [rbx+0A0h], r14d
0x1800571ee  mov     rax, [rsi]
0x1800571f1  mov     rdi, [rax+28h]
0x1800571f5  mov     rcx, [rbp+var_40]
0x1800571f9  mov     [rbp+var_40], r15
0x1800571fd  test    rcx, rcx
0x180057200  jz      short loc_18005720F
0x180057202  mov     rdx, [rcx]
0x180057205  mov     rax, [rdx+10h]
0x180057209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005720e  nop
0x18005720f  lea     rdx, [rbp+var_40]
0x180057213  mov     rcx, rsi
0x180057216  mov     rax, rdi
0x180057219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005721e  mov     edi, eax
0x180057220  test    eax, eax
0x180057222  jns     short loc_1800572A2
0x180057224  mov     rcx, [rbp+38h]; this
0x180057228  lea     rax, aFailedToGetMan_5; "Failed to get manifest reader for bundl"...
0x18005722f  mov     qword ptr [rsp+80h+var_60], rax; int
0x180057234  mov     r9d, edi; char *
0x180057237  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18005723e  mov     edx, 96h; void *
0x180057243  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180057248  nop
0x180057249  mov     rcx, [rbp+pv]; pv
0x18005724d  test    rcx, rcx
0x180057250  jz      short loc_18005725F
0x180057252  call    cs:__imp_CoTaskMemFree
0x180057259  nop     dword ptr [rax+rax+00h]
0x18005725e  nop
0x18005725f  mov     rax, [rbx]
0x180057262  mov     rcx, rbx
0x180057265  mov     rax, [rax+10h]
0x180057269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005726e  nop
0x18005726f  mov     rcx, [rbp+var_48]
0x180057273  test    rcx, rcx
0x180057276  jz      short loc_180057285
0x180057278  mov     rax, [rcx]
0x18005727b  mov     rax, [rax+10h]
0x18005727f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057284  nop
0x180057285  mov     rcx, [rbp+var_40]
0x180057289  test    rcx, rcx
0x18005728c  jz      short loc_18005729B
0x18005728e  mov     rax, [rcx]
0x180057291  mov     rax, [rax+10h]
0x180057295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005729a  nop
0x18005729b  mov     eax, edi
0x18005729d  jmp     loc_180057654
0x1800572a2  mov     rdi, [rbp+var_40]
0x1800572a6  mov     rax, [rdi]
0x1800572a9  mov     r14, [rax+18h]
0x1800572ad  mov     rcx, [rbp+var_48]
0x1800572b1  mov     [rbp+var_48], r15
0x1800572b5  test    rcx, rcx
0x1800572b8  jz      short loc_1800572C7
0x1800572ba  mov     rdx, [rcx]
0x1800572bd  mov     rax, [rdx+10h]
0x1800572c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800572c6  nop
0x1800572c7  lea     rdx, [rbp+var_48]
0x1800572cb  mov     rcx, rdi
0x1800572ce  mov     rax, r14
0x1800572d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800572d6  mov     edi, eax
0x1800572d8  test    eax, eax
0x1800572da  jns     short loc_180057358
0x1800572dc  mov     rcx, [rbp+38h]; this
0x1800572e0  lea     rax, aFailedToGetIde; "Failed to get identity for bundle."
0x1800572e7  mov     qword ptr [rsp+80h+var_60], rax; int
0x1800572ec  mov     r9d, edi; char *
0x1800572ef  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800572f6  mov     edx, 97h; void *
0x1800572fb  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180057300  nop
0x180057301  mov     rcx, [rbp+pv]; pv
0x180057305  test    rcx, rcx
0x180057308  jz      short loc_180057317
0x18005730a  call    cs:__imp_CoTaskMemFree
0x180057311  nop     dword ptr [rax+rax+00h]
0x180057316  nop
0x180057317  mov     rax, [rbx]
0x18005731a  mov     rcx, rbx
0x18005731d  mov     rax, [rax+10h]
0x180057321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057326  nop
0x180057327  mov     rcx, [rbp+var_48]
0x18005732b  test    rcx, rcx
0x18005732e  jz      short loc_18005733D
0x180057330  mov     rax, [rcx]
0x180057333  mov     rax, [rax+10h]
0x180057337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005733c  nop
0x18005733d  mov     rcx, [rbp+var_40]
0x180057341  test    rcx, rcx
0x180057344  jz      short loc_180057353
0x180057346  mov     rax, [rcx]
0x180057349  mov     rax, [rax+10h]
0x18005734d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057352  nop
0x180057353  jmp     loc_18005729B
0x180057358  mov     r15, [rbp+var_48]
0x18005735c  mov     rax, [r15]
0x18005735f  mov     r12, [rax+48h]
0x180057363  mov     r14, [rbp+pv]
0x180057367  test    r14, r14
0x18005736a  jz      short loc_180057397
0x18005736c  call    cs:__imp_GetLastError
0x180057373  nop     dword ptr [rax+rax+00h]
0x180057378  mov     edi, eax
0x18005737a  mov     rcx, r14; pv
0x18005737d  call    cs:__imp_CoTaskMemFree
0x180057384  nop     dword ptr [rax+rax+00h]
0x180057389  mov     ecx, edi; dwErrCode
0x18005738b  call    cs:__imp_SetLastError
0x180057392  nop     dword ptr [rax+rax+00h]
0x180057397  mov     [rbp+pv], 0
0x18005739f  lea     rdx, [rbp+pv]
0x1800573a3  mov     rcx, r15
0x1800573a6  mov     rax, r12
0x1800573a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800573ae  mov     edi, eax
0x1800573b0  xor     r15d, r15d
0x1800573b3  test    eax, eax
0x1800573b5  jns     short loc_180057433
0x1800573b7  mov     rcx, [rbp+38h]; this
0x1800573bb  lea     rax, aFailedToGetFul; "Failed to get fullname for bundle."
0x1800573c2  mov     qword ptr [rsp+80h+var_60], rax; int
0x1800573c7  mov     r9d, edi; char *
0x1800573ca  lea     r8, aOnecoreAdminAp_9; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800573d1  mov     edx, 98h; void *
0x1800573d6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800573db  nop
0x1800573dc  mov     rcx, [rbp+pv]; pv
0x1800573e0  test    rcx, rcx
0x1800573e3  jz      short loc_1800573F2
0x1800573e5  call    cs:__imp_CoTaskMemFree
0x1800573ec  nop     dword ptr [rax+rax+00h]
0x1800573f1  nop
0x1800573f2  mov     rax, [rbx]
0x1800573f5  mov     rcx, rbx
0x1800573f8  mov     rax, [rax+10h]
0x1800573fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057401  nop
0x180057402  mov     rcx, [rbp+var_48]
0x180057406  test    rcx, rcx
0x180057409  jz      short loc_180057418
0x18005740b  mov     rax, [rcx]
0x18005740e  mov     rax, [rax+10h]
0x180057412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057417  nop
0x180057418  mov     rcx, [rbp+var_40]
0x18005741c  test    rcx, rcx
0x18005741f  jz      short loc_18005742E
0x180057421  mov     rax, [rcx]
0x180057424  mov     rax, [rax+10h]
0x180057428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005742d  nop
0x18005742e  jmp     loc_18005729B
0x180057433  mov     rdx, [rbp+pv]; Src
0x180057437  mov     [rbp+var_10], 7
0x18005743f  mov     [rbp+var_18], r15
0x180057443  mov     word ptr [rbp+Src], r15w
0x180057448  cmp     [rdx], r15w
0x18005744c  jnz     short loc_180057453
0x18005744e  mov     r8, r15
0x180057451  jmp     short loc_180057461
0x180057453  or      r8, 0FFFFFFFFFFFFFFFFh
0x180057457  inc     r8
0x18005745a  cmp     [rdx+r8*2], r15w
0x18005745f  jnz     short loc_180057457
0x180057461  lea     rcx, [rbp+Src]; void *
0x180057465  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18005746a  lea     rcx, [rbx+38h]; void *
0x18005746e  lea     rdx, [rbp+Src]; Src
0x180057472  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@$$QEAV12@@Z; std::wstring::assign(std::wstring &&)
0x180057477  cmp     [rbp+var_10], 8
0x18005747c  jb      short loc_18005748E
0x18005747e  mov     rcx, [rbp+Src]
0x180057482  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180057489  nop     dword ptr [rax+rax+00h]
0x18005748e  mov     edi, r15d
0x180057491  mov     rax, [rsi]
0x180057494  mov     [rbp+var_38], r15
0x180057498  lea     r8, [rbp+var_38]
0x18005749c  mov     edx, edi
0x18005749e  mov     rcx, rsi
0x1800574a1  mov     rax, [rax+18h]
0x1800574a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800574aa  mov     r14d, eax
0x1800574ad  test    eax, eax
0x1800574af  js      loc_1800575C4
0x1800574b5  mov     rdx, [rbp+var_38]
0x1800574b9  mov     rcx, rbx
0x1800574bc  call    ?Insert@?$CContainer@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@VMsixAdapterCollection@234@@Library@Provisioning@MsixPackage@@QEAAJPEAVMsixPackageAdapter@234@@Z; MsixPackage::Provisioning::Library::CContainer<MsixPackage::Provisioning::Library::MsixPackageAdapter,MsixPackage::Provisioning::Library::MsixAdapterCollection>::Insert(MsixPackage::Provisioning::Library::MsixPackageAdapter *)
0x1800574c1  mov     r14d, eax
0x1800574c4  test    eax, eax
0x1800574c6  js      short loc_180057532
0x1800574c8  mov     rcx, [rbp+var_38]
0x1800574cc  test    rcx, rcx
0x1800574cf  jz      short loc_1800574DE
0x1800574d1  mov     rax, [rcx]
0x1800574d4  mov     rax, [rax+10h]
0x1800574d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800574dd  nop
0x1800574de  inc     edi
0x1800574e0  cmp     edi, 2
0x1800574e3  jle     short loc_180057491
0x1800574e5  mov     [r13+0], rbx
0x1800574e9  mov     rcx, [rbp+pv]; pv
0x1800574ed  test    rcx, rcx
0x1800574f0  jz      short loc_1800574FF
0x1800574f2  call    cs:__imp_CoTaskMemFree
  ... truncated ...
```
