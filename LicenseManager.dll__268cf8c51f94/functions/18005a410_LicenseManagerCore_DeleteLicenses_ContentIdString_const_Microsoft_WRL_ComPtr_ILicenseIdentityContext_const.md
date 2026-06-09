# LicenseManagerCore::DeleteLicenses(ContentIdString const &,Microsoft::WRL::ComPtr<ILicenseIdentityContext> const &)

- ea: `0x18005a410`
- end: `0x18005a661`
- name: `?DeleteLicenses@LicenseManagerCore@@UEAAXAEBVContentIdString@@AEBV?$ComPtr@UILicenseIdentityContext@@@WRL@Microsoft@@@Z`
- size: `593`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004738`
- `0x180020abc`
- `0x18002aae8`
- `0x1800360f8`
- `0x1800593bc`
- `0x18005a410`
- `0x1800629dc`
- `0x180062a40`
- `0x180070320`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005a439`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005a439`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a46c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a46c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a58b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a58b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall LicenseManagerCore::DeleteLicenses(__int64 a1, _QWORD *a2, __int64 a3)
{
  unsigned __int16 *v6; // rbx
  LicenseManagerCore *v7; // rdi
  void (__fastcall *v8)(LicenseManagerCore *, _QWORD *, __int64, __int64 *); // rbx
  _QWORD *v9; // rdx
  int v10; // eax
  unsigned __int16 *v11; // rbx
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // r14
  __int64 (__fastcall *v15)(__int64, unsigned __int16 **); // r15
  int v16; // eax
  int v18; // [rsp+20h] [rbp-50h]
  __int64 v19; // [rsp+40h] [rbp-30h] BYREF
  __int64 *v20; // [rsp+48h] [rbp-28h] BYREF
  int v21[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v22; // [rsp+58h] [rbp-18h] BYREF
  _BYTE v23[16]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  __int64 v25; // [rsp+A0h] [rbp+30h] BYREF
  unsigned __int16 *v26; // [rsp+B8h] [rbp+48h] BYREF

  v6 = (unsigned __int16 *)(a1 + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  v26 = v6;
  LicenseManagerCore::ContentIdMap<KeyEntry>::find(a1 + 120, &v25, a2);
  if ( v25 != *(_QWORD *)(a1 + 128) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4C6,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
      (const char *)0x80073D02LL,
      v18);
  if ( v6 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v6);
  v19 = 0;
  v20 = 0;
  v7 = (LicenseManagerCore *)(a1 - 16);
  while ( 1 )
  {
    v8 = *(void (__fastcall **)(LicenseManagerCore *, _QWORD *, __int64, __int64 *))(*(_QWORD *)v7 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v20);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v19);
    *(_QWORD *)v21 = 0;
    v22 = 0;
    v9 = a2[3] <= 7u ? a2 : (_QWORD *)*a2;
    v8(v7, v9, a3, &v22);
    if ( !v19 )
      break;
    LODWORD(v25) = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v19 + 112LL))(v19, 2130706432, &v25);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4DB,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
        (const char *)(unsigned int)v10,
        (int)v21);
    if ( !(_DWORD)v25 )
      break;
    v11 = 0;
    v26 = 0;
    if ( v20 )
    {
      v12 = *v20;
      v26 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64 *, unsigned __int16 **))(v12 + 24))(v20, &v26);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4ED,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
          (const char *)(unsigned int)v13,
          (int)v21);
      LicenseManagerCore::DoRemoveLeaseDocumentWithId(v7, v26, -2143318013);
      v11 = v26;
    }
    v14 = v19;
    v15 = *(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v19 + 24LL);
    if ( v11 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v23);
      CoTaskMemFree(v11);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v23);
    }
    v26 = 0;
    v16 = v15(v14, &v26);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4F2,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\managercore.cpp",
        (const char *)(unsigned int)v16,
        (int)v21);
    LicenseManagerCore::DoRemoveKeyDocumentWithId(v7, v26, -2143318013);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((void **)&v26);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v20);
  return Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v19);
}

```

## disassembly

```asm
0x18005a410  mov     [rsp-28h+arg_8], rbx
0x18005a415  mov     [rsp-28h+arg_10], rsi
0x18005a41a  push    rbp
0x18005a41b  push    rdi
0x18005a41c  push    r12
0x18005a41e  push    r14
0x18005a420  push    r15
0x18005a422  mov     rbp, rsp
0x18005a425  sub     rsp, 70h
0x18005a429  mov     r12, r8
0x18005a42c  mov     rsi, rdx
0x18005a42f  mov     rdi, rcx
0x18005a432  lea     rbx, [rcx+30h]
0x18005a436  mov     rcx, rbx; lpCriticalSection
0x18005a439  call    cs:__imp_EnterCriticalSection
0x18005a43f  mov     [rbp+arg_18], rbx
0x18005a443  lea     rcx, [rdi+78h]
0x18005a447  mov     r8, rsi
0x18005a44a  lea     rdx, [rbp+arg_0]
0x18005a44e  call    ?find@?$ContentIdMap@UKeyEntry@@@LicenseManagerCore@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U?$pair@VContentIdString@@UKeyEntry@@@std@@@std@@@std@@@std@@AEBVContentIdString@@@Z; LicenseManagerCore::ContentIdMap<KeyEntry>::find(ContentIdString const &)
0x18005a453  mov     rax, [rdi+80h]
0x18005a45a  cmp     [rbp+arg_0], rax
0x18005a45e  jnz     loc_18005A645
0x18005a464  test    rbx, rbx
0x18005a467  jz      short loc_18005A472
0x18005a469  mov     rcx, rbx; lpCriticalSection
0x18005a46c  call    cs:__imp_LeaveCriticalSection
0x18005a472  mov     [rbp+var_30], 0
0x18005a47a  mov     [rbp+var_28], 0
0x18005a482  add     rdi, 0FFFFFFFFFFFFFFF0h
0x18005a486  mov     rax, [rdi]
0x18005a489  mov     rbx, [rax+30h]
0x18005a48d  lea     rcx, [rbp+var_28]
0x18005a491  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18005a496  lea     rcx, [rbp+var_30]
0x18005a49a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18005a49f  mov     qword ptr [rbp+var_20], 0
0x18005a4a7  mov     [rbp+var_18], 0
0x18005a4af  cmp     qword ptr [rsi+18h], 7
0x18005a4b4  jbe     short loc_18005A4BB
0x18005a4b6  mov     rdx, [rsi]
0x18005a4b9  jmp     short loc_18005A4BE
0x18005a4bb  mov     rdx, rsi
0x18005a4be  lea     rax, [rbp+var_28]
0x18005a4c2  mov     [rsp+70h+var_40], rax
0x18005a4c7  lea     rax, [rbp+var_30]
0x18005a4cb  mov     [rsp+70h+var_48], rax
0x18005a4d0  lea     rax, [rbp+var_20]
0x18005a4d4  mov     qword ptr [rsp+70h+var_50], rax; int
0x18005a4d9  lea     r9, [rbp+var_18]
0x18005a4dd  mov     r8, r12
0x18005a4e0  mov     rcx, rdi
0x18005a4e3  mov     rax, rbx
0x18005a4e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a4eb  mov     rcx, [rbp+var_30]
0x18005a4ef  test    rcx, rcx
0x18005a4f2  jz      loc_18005A619
0x18005a4f8  mov     dword ptr [rbp+arg_0], 0
0x18005a4ff  mov     rax, [rcx]
0x18005a502  lea     r8, [rbp+arg_0]
0x18005a506  mov     edx, 7F000000h
0x18005a50b  mov     rax, [rax+70h]
0x18005a50f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a514  mov     rcx, [rbp+28h]; this
0x18005a518  test    eax, eax
0x18005a51a  js      loc_18005A604
0x18005a520  cmp     dword ptr [rbp+arg_0], 0
0x18005a524  jz      loc_18005A619
0x18005a52a  xor     ebx, ebx
0x18005a52c  mov     [rbp+arg_18], rbx
0x18005a530  mov     rcx, [rbp+var_28]
0x18005a534  test    rcx, rcx
0x18005a537  jz      short loc_18005A56F
0x18005a539  mov     rax, [rcx]
0x18005a53c  mov     [rbp+arg_18], rbx
0x18005a540  lea     rdx, [rbp+arg_18]
0x18005a544  mov     rax, [rax+18h]
0x18005a548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a54d  mov     rcx, [rbp+28h]; this
0x18005a551  test    eax, eax
0x18005a553  js      loc_18005A5DA
0x18005a559  mov     r8d, 803F9003h; int
0x18005a55f  mov     rdx, [rbp+arg_18]; unsigned __int16 *
0x18005a563  mov     rcx, rdi; this
0x18005a566  call    ?DoRemoveLeaseDocumentWithId@LicenseManagerCore@@AEAAXPEBGJ@Z; LicenseManagerCore::DoRemoveLeaseDocumentWithId(ushort const *,long)
0x18005a56b  mov     rbx, [rbp+arg_18]
0x18005a56f  mov     r14, [rbp+var_30]
0x18005a573  mov     rax, [r14]
0x18005a576  mov     r15, [rax+18h]
0x18005a57a  test    rbx, rbx
0x18005a57d  jz      short loc_18005A59A
0x18005a57f  lea     rcx, [rbp+var_10]; this
0x18005a583  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18005a588  mov     rcx, rbx; pv
0x18005a58b  call    cs:__imp_CoTaskMemFree
0x18005a591  lea     rcx, [rbp+var_10]; this
0x18005a595  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18005a59a  mov     [rbp+arg_18], 0
0x18005a5a2  lea     rdx, [rbp+arg_18]
0x18005a5a6  mov     rcx, r14
0x18005a5a9  mov     rax, r15
0x18005a5ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a5b1  mov     rcx, [rbp+28h]; this
0x18005a5b5  test    eax, eax
0x18005a5b7  js      short loc_18005A5EF
0x18005a5b9  mov     r8d, 803F9003h; int
0x18005a5bf  mov     rdx, [rbp+arg_18]; unsigned __int16 *
0x18005a5c3  mov     rcx, rdi; this
0x18005a5c6  call    ?DoRemoveKeyDocumentWithId@LicenseManagerCore@@AEBAXPEBGJ@Z; LicenseManagerCore::DoRemoveKeyDocumentWithId(ushort const *,long)
0x18005a5cb  nop
0x18005a5cc  lea     rcx, [rbp+arg_18]
0x18005a5d0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005a5d5  jmp     loc_18005A486
0x18005a5da  mov     r9d, eax; char *
0x18005a5dd  lea     r8, aOnecoreuapEndu_17; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005a5e4  mov     edx, 4EDh; void *
0x18005a5e9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005a5ef  mov     r9d, eax; char *
0x18005a5f2  lea     r8, aOnecoreuapEndu_17; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005a5f9  mov     edx, 4F2h; void *
0x18005a5fe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005a604  mov     r9d, eax; char *
0x18005a607  lea     r8, aOnecoreuapEndu_17; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005a60e  mov     edx, 4DBh; void *
0x18005a613  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005a619  lea     rcx, [rbp+var_28]
0x18005a61d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18005a622  nop
0x18005a623  lea     rcx, [rbp+var_30]
0x18005a627  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18005a62c  lea     r11, [rsp+70h+var_s0]
0x18005a631  mov     rbx, [r11+38h]
0x18005a635  mov     rsi, [r11+40h]
0x18005a639  mov     rsp, r11
0x18005a63c  pop     r15
0x18005a63e  pop     r14
0x18005a640  pop     r12
0x18005a642  pop     rdi
0x18005a643  pop     rbp
0x18005a644  retn
0x18005a645  mov     rcx, [rbp+28h]; this
0x18005a649  mov     r9d, 80073D02h; char *
0x18005a64f  lea     r8, aOnecoreuapEndu_17; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005a656  mov     edx, 4C6h; void *
0x18005a65b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
