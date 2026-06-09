# KeyMachine::DoLeasesMatch(Microsoft::WRL::ComPtr<IStoredLeaseDocument> const &,Microsoft::WRL::ComPtr<IStoredLeaseDocument> const &)

- ea: `0x1800415c4`
- end: `0x1800418a7`
- name: `?DoLeasesMatch@KeyMachine@@KA_NAEBV?$ComPtr@UIStoredLeaseDocument@@@WRL@Microsoft@@0@Z`
- size: `739`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180042c70`

## callees

- `0x180004738`
- `0x18002aae8`
- `0x1800415c4`
- `0x1800593bc`
- `0x18005b560`
- `0x1800629dc`
- `0x180062a40`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004180b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004180b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800417b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041820`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041830`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800417b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041820`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041830`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
bool __fastcall KeyMachine::DoLeasesMatch(__int64 **a1, _QWORD *a2)
{
  int v5; // eax
  int v6; // eax
  char v7; // bl
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  __int64 *v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, LPVOID *); // rsi
  void *v17; // rbx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-40h]
  int v22; // [rsp+30h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-28h] BYREF
  __int64 v24; // [rsp+40h] [rbp-20h] BYREF
  __int64 v25; // [rsp+48h] [rbp-18h] BYREF
  LPCWCH lpString1; // [rsp+50h] [rbp-10h] BYREF
  _BYTE v27[8]; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  int v29; // [rsp+90h] [rbp+30h] BYREF
  int v30; // [rsp+A0h] [rbp+40h] BYREF
  int v31; // [rsp+A8h] [rbp+48h] BYREF

  if ( !*a1 )
    return !*a2;
  if ( !*a2 )
    return 0;
  v25 = 0;
  v24 = 0;
  v5 = Microsoft::WRL::ComPtr<ILicenseInstance>::As<IUnknown>(a1, &v25);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1BE,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
      (const char *)(unsigned int)v5,
      bIgnoreCase);
  v6 = Microsoft::WRL::ComPtr<ILicenseInstance>::As<IUnknown>(a2, &v24);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1BF,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
      (const char *)(unsigned int)v6,
      bIgnoreCase);
  if ( v25 != v24 )
  {
    v30 = 0;
    v29 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64 *, int *))(**a1 + 120))(*a1, &v30);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C7,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        (const char *)(unsigned int)v8,
        bIgnoreCase);
    v9 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a2 + 120LL))(*a2, &v29);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C8,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        (const char *)(unsigned int)v9,
        bIgnoreCase);
    if ( v30 != v29 )
      goto LABEL_38;
    v22 = 0;
    v31 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64 *, int *))(**a1 + 152))(*a1, &v22);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CF,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        (const char *)(unsigned int)v10,
        bIgnoreCase);
    v11 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a2 + 152LL))(*a2, &v31);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1D0,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        (const char *)(unsigned int)v11,
        bIgnoreCase);
    if ( v22 != v31 )
    {
LABEL_38:
      v7 = 0;
      goto LABEL_39;
    }
    lpString1 = 0;
    pv = 0;
    v12 = *a1;
    v13 = **a1;
    lpString1 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64 *, LPCWCH *))(v13 + 144))(v12, &lpString1);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1D7,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        (const char *)(unsigned int)v14,
        bIgnoreCase);
    v15 = *a2;
    v16 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)*a2 + 144LL);
    v17 = pv;
    if ( pv )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v27);
      CoTaskMemFree(v17);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v27);
    }
    pv = 0;
    v18 = v16(v15, &pv);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1D8,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        (const char *)(unsigned int)v18,
        bIgnoreCase);
    v7 = 1;
    if ( CompareStringOrdinal(lpString1, -1, (LPCWCH)pv, -1, 1) == 2 )
    {
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpString1);
      goto LABEL_39;
    }
    if ( pv )
      CoTaskMemFree(pv);
    if ( lpString1 )
      CoTaskMemFree((LPVOID)lpString1);
    v19 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v25;
    if ( v25 )
    {
      v25 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return 0;
  }
  v7 = 1;
LABEL_39:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
  return v7;
}

```

## disassembly

```asm
0x1800415c4  push    rbp
0x1800415c6  push    rbx
0x1800415c7  push    rsi
0x1800415c8  push    rdi
0x1800415c9  push    r14
0x1800415cb  mov     rbp, rsp
0x1800415ce  sub     rsp, 60h
0x1800415d2  mov     rbx, rdx
0x1800415d5  mov     rdi, rcx
0x1800415d8  xor     r14d, r14d
0x1800415db  cmp     [rcx], r14
0x1800415de  jnz     short loc_1800415F2
0x1800415e0  cmp     [rdx], r14
0x1800415e3  jnz     loc_18004186B
0x1800415e9  lea     eax, [r14+1]
0x1800415ed  jmp     loc_18004186D
0x1800415f2  cmp     [rdx], r14
0x1800415f5  jz      loc_18004186B
0x1800415fb  mov     [rbp+var_18], r14
0x1800415ff  mov     [rbp+var_20], r14
0x180041603  lea     rdx, [rbp+var_18]
0x180041607  call    ??$As@UIUnknown@@@?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ILicenseInstance>::As<IUnknown>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IUnknown>>)
0x18004160c  mov     rcx, [rbp+28h]; this
0x180041610  test    eax, eax
0x180041612  jns     short loc_180041629
0x180041614  mov     r9d, eax; char *
0x180041617  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x18004161e  mov     edx, 1BEh; void *
0x180041623  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180041629  lea     rdx, [rbp+var_20]
0x18004162d  mov     rcx, rbx
0x180041630  call    ??$As@UIUnknown@@@?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ILicenseInstance>::As<IUnknown>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IUnknown>>)
0x180041635  mov     rcx, [rbp+28h]; this
0x180041639  test    eax, eax
0x18004163b  jns     short loc_180041652
0x18004163d  mov     r9d, eax; char *
0x180041640  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x180041647  mov     edx, 1BFh; void *
0x18004164c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180041652  mov     rax, [rbp+var_20]
0x180041656  cmp     [rbp+var_18], rax
0x18004165a  jnz     short loc_180041666
0x18004165c  mov     ebx, 1
0x180041661  jmp     loc_180041890
0x180041666  mov     [rbp+arg_10], r14d
0x18004166a  mov     [rbp+arg_0], r14d
0x18004166e  mov     rcx, [rdi]
0x180041671  mov     rax, [rcx]
0x180041674  lea     rdx, [rbp+arg_10]
0x180041678  mov     rax, [rax+78h]
0x18004167c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041681  mov     rcx, [rbp+28h]; this
0x180041685  test    eax, eax
0x180041687  jns     short loc_18004169E
0x180041689  mov     r9d, eax; char *
0x18004168c  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x180041693  mov     edx, 1C7h; void *
0x180041698  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004169e  mov     rcx, [rbx]
0x1800416a1  mov     rax, [rcx]
0x1800416a4  lea     rdx, [rbp+arg_0]
0x1800416a8  mov     rax, [rax+78h]
0x1800416ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416b1  mov     rcx, [rbp+28h]; this
0x1800416b5  test    eax, eax
0x1800416b7  jns     short loc_1800416CE
0x1800416b9  mov     r9d, eax; char *
0x1800416bc  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800416c3  mov     edx, 1C8h; void *
0x1800416c8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800416ce  mov     eax, [rbp+arg_0]
0x1800416d1  cmp     [rbp+arg_10], eax
0x1800416d4  jnz     loc_18004188D
0x1800416da  mov     [rbp+var_30], r14d
0x1800416de  mov     [rbp+arg_18], r14d
0x1800416e2  mov     rcx, [rdi]
0x1800416e5  mov     rax, [rcx]
0x1800416e8  lea     rdx, [rbp+var_30]
0x1800416ec  mov     rax, [rax+98h]
0x1800416f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416f8  mov     rcx, [rbp+28h]; this
0x1800416fc  test    eax, eax
0x1800416fe  jns     short loc_180041715
0x180041700  mov     r9d, eax; char *
0x180041703  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x18004170a  mov     edx, 1CFh; void *
0x18004170f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180041715  mov     rcx, [rbx]
0x180041718  mov     rax, [rcx]
0x18004171b  lea     rdx, [rbp+arg_18]
0x18004171f  mov     rax, [rax+98h]
0x180041726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004172b  mov     rcx, [rbp+28h]; this
0x18004172f  test    eax, eax
0x180041731  jns     short loc_180041748
0x180041733  mov     r9d, eax; char *
0x180041736  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x18004173d  mov     edx, 1D0h; void *
0x180041742  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180041748  mov     eax, [rbp+arg_18]
0x18004174b  cmp     [rbp+var_30], eax
0x18004174e  jnz     loc_18004188D
0x180041754  mov     [rbp+lpString1], r14
0x180041758  mov     [rbp+pv], r14
0x18004175c  mov     rcx, [rdi]
0x18004175f  mov     rax, [rcx]
0x180041762  mov     [rbp+lpString1], r14
0x180041766  lea     rdx, [rbp+lpString1]
0x18004176a  mov     rax, [rax+90h]
0x180041771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041776  mov     rcx, [rbp+28h]; this
0x18004177a  test    eax, eax
0x18004177c  jns     short loc_180041793
0x18004177e  mov     r9d, eax; char *
0x180041781  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x180041788  mov     edx, 1D7h; void *
0x18004178d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180041793  mov     rdi, [rbx]
0x180041796  mov     rax, [rdi]
0x180041799  mov     rsi, [rax+90h]
0x1800417a0  mov     rbx, [rbp+pv]
0x1800417a4  test    rbx, rbx
0x1800417a7  jz      short loc_1800417C4
0x1800417a9  lea     rcx, [rbp+var_8]; this
0x1800417ad  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800417b2  mov     rcx, rbx; pv
0x1800417b5  call    cs:__imp_CoTaskMemFree
0x1800417bb  lea     rcx, [rbp+var_8]; this
0x1800417bf  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800417c4  mov     [rbp+pv], r14
0x1800417c8  lea     rdx, [rbp+pv]
0x1800417cc  mov     rcx, rdi
0x1800417cf  mov     rax, rsi
0x1800417d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417d7  mov     rcx, [rbp+28h]; this
0x1800417db  test    eax, eax
0x1800417dd  jns     short loc_1800417F4
0x1800417df  mov     r9d, eax; char *
0x1800417e2  lea     r8, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800417e9  mov     edx, 1D8h; void *
0x1800417ee  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800417f4  mov     ebx, 1
0x1800417f9  mov     [rsp+60h+bIgnoreCase], ebx; bIgnoreCase
0x1800417fd  or      edx, 0FFFFFFFFh; cchCount1
0x180041800  mov     r9d, edx; cchCount2
0x180041803  mov     r8, [rbp+pv]; lpString2
0x180041807  mov     rcx, [rbp+lpString1]; lpString1
0x18004180b  call    cs:__imp_CompareStringOrdinal
0x180041811  nop
0x180041812  cmp     eax, 2
0x180041815  jz      short loc_180041878
0x180041817  mov     rcx, [rbp+pv]; pv
0x18004181b  test    rcx, rcx
0x18004181e  jz      short loc_180041827
0x180041820  call    cs:__imp_CoTaskMemFree
0x180041826  nop
0x180041827  mov     rcx, [rbp+lpString1]; pv
0x18004182b  test    rcx, rcx
0x18004182e  jz      short loc_180041837
0x180041830  call    cs:__imp_CoTaskMemFree
0x180041836  nop
0x180041837  mov     rcx, [rbp+var_20]
0x18004183b  test    rcx, rcx
0x18004183e  jz      short loc_180041851
0x180041840  mov     [rbp+var_20], r14
0x180041844  mov     rax, [rcx]
0x180041847  mov     rax, [rax+10h]
0x18004184b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041850  nop
0x180041851  mov     rcx, [rbp+var_18]
0x180041855  test    rcx, rcx
0x180041858  jz      short loc_18004186B
0x18004185a  mov     [rbp+var_18], r14
0x18004185e  mov     rax, [rcx]
0x180041861  mov     rax, [rax+10h]
0x180041865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004186a  nop
0x18004186b  xor     al, al
0x18004186d  add     rsp, 60h
0x180041871  pop     r14
0x180041873  pop     rdi
0x180041874  pop     rsi
0x180041875  pop     rbx
0x180041876  pop     rbp
0x180041877  retn
0x180041878  lea     rcx, [rbp+pv]
0x18004187c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180041881  nop
0x180041882  lea     rcx, [rbp+lpString1]
0x180041886  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18004188b  jmp     short loc_180041890
0x18004188d  mov     bl, r14b
0x180041890  lea     rcx, [rbp+var_20]
0x180041894  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180041899  nop
0x18004189a  lea     rcx, [rbp+var_18]
0x18004189e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800418a3  mov     al, bl
0x1800418a5  jmp     short loc_18004186D
```
