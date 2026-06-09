# StoreApplication::GetStoreAppBundlePackagePath(Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &)

- ea: `0x1800da410`
- end: `0x1800da71d`
- name: `?GetStoreAppBundlePackagePath@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@@Z`
- size: `781`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800db734`

## callees

- `0x180005890`
- `0x180006914`
- `0x18000a2d4`
- `0x18000ea34`
- `0x18001082c`
- `0x1800108a8`
- `0x18001c5f0`
- `0x1800c97f0`
- `0x1800d59dc`
- `0x1800da410`
- `0x1800dac8c`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800da4fd`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800da4fd`

## string_xrefs

- `0x1800da477`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800da4bc`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800da567`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800da5a6`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800da60b`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800da63c`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800da686`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall StoreApplication::GetStoreAppBundlePackagePath(__int64 a1, __int64 *a2)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, __int64 **); // rbx
  int v5; // eax
  __int64 v6; // rax
  int v7; // eax
  const unsigned __int16 (*v8)[45]; // rdx
  int v9; // ebx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64 *); // rbx
  int v17; // eax
  __int64 StoreAppInstallLocationFromPackage; // rax
  int v20; // [rsp+20h] [rbp-59h]
  _BYTE v21[8]; // [rsp+30h] [rbp-49h] BYREF
  __int64 v22; // [rsp+38h] [rbp-41h] BYREF
  __int64 v23; // [rsp+40h] [rbp-39h] BYREF
  __int64 v24; // [rsp+48h] [rbp-31h] BYREF
  __int64 *v25; // [rsp+50h] [rbp-29h] BYREF
  int v26; // [rsp+58h] [rbp-21h]
  __int64 v27; // [rsp+60h] [rbp-19h] BYREF
  _QWORD v28[2]; // [rsp+68h] [rbp-11h] BYREF
  _QWORD *v29; // [rsp+78h] [rbp-1h] BYREF
  __int64 v30; // [rsp+80h] [rbp+7h] BYREF
  char v31; // [rsp+88h] [rbp+Fh]
  HSTRING string; // [rsp+98h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v28[1] = a1;
  v26 = 0;
  v25 = 0;
  v3 = *a2;
  v4 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)*a2 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  v5 = v4(v3, &v25);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x58E,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v5,
      v20);
  v28[0] = 0;
  v6 = *v25;
  v29 = v28;
  v30 = 0;
  v31 = 1;
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v6 + 104))(v25, &v30);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x592,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v7,
      v20);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&v29);
  v23 = 0;
  Windows::Internal::StringReference::StringReference(&string, v8);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  v23 = 0;
  v22 = 0;
  v9 = RoActivateInstance(string, &v22);
  if ( v9 >= 0 )
  {
    if ( !memcmp_0(&GUID_f7aad08d_0840_46f2_b5d8_cad47693a095, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v23 = v22;
    }
    else
    {
      v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v22)(
             v22,
             &GUID_f7aad08d_0840_46f2_b5d8_cad47693a095,
             &v23);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
  }
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x597,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v9,
      v20);
  v27 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v23 + 104LL))(v23, v28[0], 8, &v27);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x59D,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v10,
      v20);
  v21[0] = 0;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 7;
  *(_WORD *)a1 = 0;
  v26 = 1;
  v24 = 0;
  v11 = v27;
  v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  v13 = v12(v11, &v24);
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5A3,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v13,
      v20);
  v14 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v24 + 56LL))(v24, v21);
  if ( v14 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5A4,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v14,
      v20);
  if ( v21[0] )
  {
    v22 = 0;
    v15 = v24;
    v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    v17 = v16(v15, &v22);
    if ( v17 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x5A9,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v17,
        v20);
    StoreAppInstallLocationFromPackage = StoreApplication::GetStoreAppInstallLocationFromPackage(&v29, &v22);
    std::wstring::operator=(a1, StoreAppInstallLocationFromPackage);
    std::wstring::_Tidy_deallocate(&v29);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  Windows::Internal::String::~String((Windows::Internal::String *)v28);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  return a1;
}

```

## disassembly

```asm
0x1800da410  mov     [rsp-8+arg_10], rbx
0x1800da415  mov     [rsp-8+arg_18], rsi
0x1800da41a  push    rbp
0x1800da41b  push    rdi
0x1800da41c  push    r14
0x1800da41e  lea     rbp, [rsp-47h]
0x1800da423  sub     rsp, 0C0h
0x1800da42a  mov     rax, cs:__security_cookie
0x1800da431  xor     rax, rsp
0x1800da434  mov     [rbp+57h+var_18], rax
0x1800da438  mov     rsi, rcx
0x1800da43b  mov     [rbp+57h+var_60], rcx
0x1800da43f  xor     r14d, r14d
0x1800da442  mov     [rbp+57h+var_78], r14d
0x1800da446  mov     [rbp+57h+var_80], r14
0x1800da44a  mov     rdi, [rdx]
0x1800da44d  mov     rax, [rdi]
0x1800da450  mov     rbx, [rax+30h]
0x1800da454  lea     rcx, [rbp+57h+var_80]
0x1800da458  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800da45d  lea     rdx, [rbp+57h+var_80]
0x1800da461  mov     rcx, rdi
0x1800da464  mov     rax, rbx
0x1800da467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da46c  mov     rcx, [rbp+5Fh]; this
0x1800da470  test    eax, eax
0x1800da472  jns     short loc_1800DA489
0x1800da474  mov     r9d, eax; char *
0x1800da477  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800da47e  mov     edx, 58Eh; void *
0x1800da483  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800da489  mov     [rbp+57h+var_68], r14
0x1800da48d  mov     rcx, [rbp+57h+var_80]
0x1800da491  mov     rax, [rcx]
0x1800da494  lea     rdx, [rbp+57h+var_68]
0x1800da498  mov     [rbp+57h+var_58], rdx
0x1800da49c  mov     [rbp+57h+var_50], r14
0x1800da4a0  mov     [rbp+57h+var_48], 1
0x1800da4a4  lea     rdx, [rbp+57h+var_50]
0x1800da4a8  mov     rax, [rax+68h]
0x1800da4ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da4b1  mov     rcx, [rbp+5Fh]; this
0x1800da4b5  test    eax, eax
0x1800da4b7  jns     short loc_1800DA4CE
0x1800da4b9  mov     r9d, eax; char *
0x1800da4bc  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800da4c3  mov     edx, 592h; void *
0x1800da4c8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800da4ce  lea     rcx, [rbp+57h+var_58]
0x1800da4d2  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x1800da4d7  mov     [rbp+57h+var_90], r14
0x1800da4db  lea     rcx, [rbp+57h+string]; string
0x1800da4df  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x1800da4e4  lea     rcx, [rbp+57h+var_90]
0x1800da4e8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800da4ed  mov     [rbp+57h+var_90], r14
0x1800da4f1  mov     [rbp+57h+var_98], r14
0x1800da4f5  lea     rdx, [rbp+57h+var_98]
0x1800da4f9  mov     rcx, [rbp+57h+string]
0x1800da4fd  call    cs:__imp_RoActivateInstance
0x1800da503  mov     ebx, eax
0x1800da505  test    eax, eax
0x1800da507  js      short loc_1800DA55C
0x1800da509  mov     r8d, 10h; Size
0x1800da50f  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x1800da516  lea     rcx, _GUID_f7aad08d_0840_46f2_b5d8_cad47693a095; Buf1
0x1800da51d  call    memcmp_0
0x1800da522  test    eax, eax
0x1800da524  jnz     short loc_1800DA530
0x1800da526  mov     rax, [rbp+57h+var_98]
0x1800da52a  mov     [rbp+57h+var_90], rax
0x1800da52e  jmp     short loc_1800DA55C
0x1800da530  mov     rcx, [rbp+57h+var_98]
0x1800da534  mov     rax, [rcx]
0x1800da537  lea     r8, [rbp+57h+var_90]
0x1800da53b  lea     rdx, _GUID_f7aad08d_0840_46f2_b5d8_cad47693a095
0x1800da542  mov     rax, [rax]
0x1800da545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da54a  mov     ebx, eax
0x1800da54c  mov     rcx, [rbp+57h+var_98]
0x1800da550  mov     rax, [rcx]
0x1800da553  mov     rax, [rax+10h]
0x1800da557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da55c  mov     rcx, [rbp+5Fh]; this
0x1800da560  test    ebx, ebx
0x1800da562  jns     short loc_1800DA579
0x1800da564  mov     r9d, ebx; char *
0x1800da567  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800da56e  mov     edx, 597h; void *
0x1800da573  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800da579  mov     [rbp+57h+var_70], r14
0x1800da57d  mov     rcx, [rbp+57h+var_90]
0x1800da581  mov     rax, [rcx]
0x1800da584  lea     r9, [rbp+57h+var_70]
0x1800da588  mov     r8d, 8
0x1800da58e  mov     rdx, [rbp+57h+var_68]
0x1800da592  mov     rax, [rax+68h]
0x1800da596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da59b  mov     rcx, [rbp+5Fh]; this
0x1800da59f  test    eax, eax
0x1800da5a1  jns     short loc_1800DA5B8
0x1800da5a3  mov     r9d, eax; char *
0x1800da5a6  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800da5ad  mov     edx, 59Dh; void *
0x1800da5b2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800da5b8  mov     [rbp+57h+var_A0], r14b
0x1800da5bc  xorps   xmm0, xmm0
0x1800da5bf  movups  xmmword ptr [rsi], xmm0
0x1800da5c2  mov     [rsi+10h], r14
0x1800da5c6  mov     qword ptr [rsi+18h], 7
0x1800da5ce  mov     [rsi], r14w
0x1800da5d2  mov     [rbp+57h+var_78], 1
0x1800da5d9  mov     [rbp+57h+var_88], r14
0x1800da5dd  mov     rdi, [rbp+57h+var_70]
0x1800da5e1  mov     rax, [rdi]
0x1800da5e4  mov     rbx, [rax+30h]
0x1800da5e8  lea     rcx, [rbp+57h+var_88]
0x1800da5ec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800da5f1  lea     rdx, [rbp+57h+var_88]
0x1800da5f5  mov     rcx, rdi
0x1800da5f8  mov     rax, rbx
0x1800da5fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da600  mov     rcx, [rbp+5Fh]; this
0x1800da604  test    eax, eax
0x1800da606  jns     short loc_1800DA61D
0x1800da608  mov     r9d, eax; char *
0x1800da60b  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800da612  mov     edx, 5A3h; void *
0x1800da617  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800da61d  mov     rcx, [rbp+57h+var_88]
0x1800da621  mov     rax, [rcx]
0x1800da624  lea     rdx, [rbp+57h+var_A0]
0x1800da628  mov     rax, [rax+38h]
0x1800da62c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da631  mov     rcx, [rbp+5Fh]; this
0x1800da635  test    eax, eax
0x1800da637  jns     short loc_1800DA64E
0x1800da639  mov     r9d, eax; char *
0x1800da63c  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800da643  mov     edx, 5A4h; void *
0x1800da648  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800da64e  cmp     [rbp+57h+var_A0], r14b
0x1800da652  jz      short loc_1800DA6C4
0x1800da654  mov     [rbp+57h+var_98], r14
0x1800da658  mov     rdi, [rbp+57h+var_88]
0x1800da65c  mov     rax, [rdi]
0x1800da65f  mov     rbx, [rax+30h]
0x1800da663  lea     rcx, [rbp+57h+var_98]
0x1800da667  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800da66c  lea     rdx, [rbp+57h+var_98]
0x1800da670  mov     rcx, rdi
0x1800da673  mov     rax, rbx
0x1800da676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da67b  mov     rcx, [rbp+5Fh]; this
0x1800da67f  test    eax, eax
0x1800da681  jns     short loc_1800DA698
0x1800da683  mov     r9d, eax; char *
0x1800da686  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800da68d  mov     edx, 5A9h; void *
0x1800da692  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800da698  lea     rdx, [rbp+57h+var_98]
0x1800da69c  lea     rcx, [rbp+57h+var_58]
0x1800da6a0  call    ?GetStoreAppInstallLocationFromPackage@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@@Z; StoreApplication::GetStoreAppInstallLocationFromPackage(Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &)
0x1800da6a5  mov     rdx, rax
0x1800da6a8  mov     rcx, rsi
0x1800da6ab  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800da6b0  lea     rcx, [rbp+57h+var_58]
0x1800da6b4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800da6b9  nop
0x1800da6ba  lea     rcx, [rbp+57h+var_98]
0x1800da6be  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800da6c3  nop
0x1800da6c4  lea     rcx, [rbp+57h+var_88]
0x1800da6c8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800da6cd  nop
0x1800da6ce  lea     rcx, [rbp+57h+var_70]
0x1800da6d2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800da6d7  nop
0x1800da6d8  lea     rcx, [rbp+57h+var_90]
0x1800da6dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800da6e1  nop
0x1800da6e2  lea     rcx, [rbp+57h+var_68]; this
0x1800da6e6  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800da6eb  nop
0x1800da6ec  lea     rcx, [rbp+57h+var_80]
0x1800da6f0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800da6f5  mov     rax, rsi
0x1800da6f8  mov     rcx, [rbp+57h+var_18]
0x1800da6fc  xor     rcx, rsp; StackCookie
0x1800da6ff  call    __security_check_cookie
0x1800da704  lea     r11, [rsp+0D0h+var_10]
0x1800da70c  mov     rbx, [r11+30h]
0x1800da710  mov     rsi, [r11+38h]
0x1800da714  mov     rsp, r11
0x1800da717  pop     r14
0x1800da719  pop     rdi
0x1800da71a  pop     rbp
0x1800da71b  retn
```
