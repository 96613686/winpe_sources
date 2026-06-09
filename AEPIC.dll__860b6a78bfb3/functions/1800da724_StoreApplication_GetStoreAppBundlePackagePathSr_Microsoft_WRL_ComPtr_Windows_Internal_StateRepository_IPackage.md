# StoreApplication::GetStoreAppBundlePackagePathSr(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &)

- ea: `0x1800da724`
- end: `0x1800daab3`
- name: `?GetStoreAppBundlePackagePathSr@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z`
- size: `911`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800db8b8`

## callees

- `0x180005890`
- `0x18000a2d4`
- `0x18000faf0`
- `0x18001082c`
- `0x1800252b0`
- `0x1800c97f0`
- `0x1800d5834`
- `0x1800d8684`
- `0x1800d8b3c`
- `0x1800da724`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800da7eb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800da7eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800da9e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800da9e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800da7d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800da7d2`

## string_xrefs

- `0x1800da7ac`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800da809`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800da848`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800da878`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800da8c5`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800da8f6`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800da9ce`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800daa06`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800daa1b`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800daa30`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall StoreApplication::GetStoreAppBundlePackagePathSr(__int64 a1, _QWORD *a2)
{
  int v4; // eax
  int v5; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64 *); // rbx
  int v8; // eax
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64, __int64, __int64 *); // rbx
  int v12; // eax
  int v13; // eax
  unsigned int i; // esi
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64, __int64 *); // rbx
  int v18; // eax
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, HSTRING *); // rbx
  int v22; // eax
  PCWSTR StringRawBuffer; // rax
  int v25; // [rsp+20h] [rbp-59h]
  __int64 v26; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v27; // [rsp+38h] [rbp-41h] BYREF
  __int64 v28; // [rsp+40h] [rbp-39h] BYREF
  __int64 v29; // [rsp+48h] [rbp-31h] BYREF
  __int64 v30; // [rsp+50h] [rbp-29h] BYREF
  HSTRING v31; // [rsp+58h] [rbp-21h] BYREF
  __int64 v32; // [rsp+60h] [rbp-19h] BYREF
  __int64 v33; // [rsp+68h] [rbp-11h] BYREF
  __int64 v34; // [rsp+70h] [rbp-9h] BYREF
  __int64 v35; // [rsp+78h] [rbp-1h] BYREF
  HSTRING string; // [rsp+88h] [rbp+Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v34 = a1;
  v30 = 0;
  v29 = 0;
  v33 = 0;
  v32 = 0;
  v26 = 0;
  v28 = 0;
  v35 = 0;
  v27 = 0;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    (HSTRING_HEADER *)&string,
    L"Windows.Internal.StateRepository.PackageLocation",
    0x31u,
    0x30u);
  v4 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>>(
         *(_QWORD *)&hstringHeader.Reserved.Reserved2[16],
         &v33);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5D2,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v4,
      v25);
  if ( WindowsCreateStringReference(L"Windows.Internal.StateRepository.Package", 0x28u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
         string,
         &v32);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5D7,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v5,
      v25);
  v6 = *a2;
  v7 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a2 + 72LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  v8 = v7(v6, &v30);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5DA,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v8,
      v25);
  v9 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 104LL))(*a2, &v35);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5DB,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v9,
      v25);
  v10 = v32;
  v11 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v32 + 216LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  v12 = v11(v10, v30, 8, &v26);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5E1,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v12,
      v25);
  v13 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v26 + 56LL))(v26, &v27);
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5E3,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v13,
      v25);
  for ( i = 0; ; ++i )
  {
    if ( i >= v27 )
    {
      std::wstring::wstring(a1, &pszFormat);
      goto LABEL_29;
    }
    v34 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v26 + 48LL))(v26, i, &v28);
    if ( v15 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x5E9,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v15,
        v25);
    v16 = v33;
    v17 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v33 + 96LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    v18 = v17(v16, v28, &v29);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x5EA,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v18,
        v25);
    v19 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 104LL))(v28, &v34);
    if ( v19 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x5EB,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v19,
        v25);
    if ( v34 == v35 )
      break;
  }
  v31 = 0;
  v20 = v29;
  v21 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v29 + 88LL);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &v31,
    0);
  v22 = v21(v20, &v31);
  if ( v22 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5F1,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v22,
      v25);
  StringRawBuffer = WindowsGetStringRawBuffer(v31, 0);
  std::wstring::wstring(a1, StringRawBuffer);
  Windows::Internal::String::~String((Windows::Internal::String *)&v31);
LABEL_29:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  return a1;
}

```

## disassembly

```asm
0x1800da724  mov     [rsp-8+arg_10], rbx
0x1800da729  push    rbp
0x1800da72a  push    rsi
0x1800da72b  push    rdi
0x1800da72c  push    r14
0x1800da72e  push    r15
0x1800da730  lea     rbp, [rsp-37h]
0x1800da735  sub     rsp, 0B0h
0x1800da73c  mov     rax, cs:__security_cookie
0x1800da743  xor     rax, rsp
0x1800da746  mov     [rbp+57h+var_28], rax
0x1800da74a  mov     rsi, rdx
0x1800da74d  mov     r14, rcx
0x1800da750  mov     [rbp+57h+var_60], rcx
0x1800da754  xor     r15d, r15d
0x1800da757  mov     [rbp+57h+var_80], r15
0x1800da75b  mov     [rbp+57h+var_88], r15
0x1800da75f  mov     [rbp+57h+var_68], r15
0x1800da763  mov     [rbp+57h+var_70], r15
0x1800da767  mov     [rbp+57h+var_A0], r15
0x1800da76b  mov     [rbp+57h+var_90], r15
0x1800da76f  mov     [rbp+57h+var_58], r15
0x1800da773  mov     [rbp+57h+var_98], r15d
0x1800da777  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], r15
0x1800da77b  lea     r9d, [r15+30h]; unsigned int
0x1800da77f  lea     r8d, [r15+31h]; unsigned int
0x1800da783  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_PackageLocation@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x1800da78a  lea     rcx, [rbp+57h+string]; hstringHeader
0x1800da78e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800da793  nop
0x1800da794  lea     rdx, [rbp+57h+var_68]
0x1800da798  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved+10h]
0x1800da79c  call    ??$GetActivationFactory@V?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>>)
0x1800da7a1  mov     rcx, [rbp+5Fh]; this
0x1800da7a5  test    eax, eax
0x1800da7a7  jns     short loc_1800DA7BE
0x1800da7a9  mov     r9d, eax; char *
0x1800da7ac  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800da7b3  mov     edx, 5D2h; void *
0x1800da7b8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800da7be  lea     r9, [rbp+57h+string]; string
0x1800da7c2  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800da7c6  mov     edx, 28h ; '('; length
0x1800da7cb  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x1800da7d2  call    cs:__imp_WindowsCreateStringReference
0x1800da7d8  test    eax, eax
0x1800da7da  jns     short loc_1800DA7F1
0x1800da7dc  xor     r9d, r9d; lpArguments
0x1800da7df  xor     r8d, r8d; nNumberOfArguments
0x1800da7e2  lea     edx, [r9+1]; dwExceptionFlags
0x1800da7e6  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800da7eb  call    cs:__imp_RaiseException
0x1800da7f1  lea     rdx, [rbp+57h+var_70]
0x1800da7f5  mov     rcx, [rbp+57h+string]
0x1800da7f9  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x1800da7fe  mov     rcx, [rbp+5Fh]; this
0x1800da802  test    eax, eax
0x1800da804  jns     short loc_1800DA81B
0x1800da806  mov     r9d, eax; char *
0x1800da809  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800da810  mov     edx, 5D7h; void *
0x1800da815  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800da81b  mov     rdi, [rsi]
0x1800da81e  mov     rax, [rdi]
0x1800da821  mov     rbx, [rax+48h]
0x1800da825  lea     rcx, [rbp+57h+var_80]
0x1800da829  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800da82e  lea     rdx, [rbp+57h+var_80]
0x1800da832  mov     rcx, rdi
0x1800da835  mov     rax, rbx
0x1800da838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da83d  mov     rcx, [rbp+5Fh]; this
0x1800da841  test    eax, eax
0x1800da843  jns     short loc_1800DA85A
0x1800da845  mov     r9d, eax; char *
0x1800da848  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800da84f  mov     edx, 5DAh; void *
0x1800da854  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800da85a  mov     rcx, [rsi]
0x1800da85d  mov     rax, [rcx]
0x1800da860  lea     rdx, [rbp+57h+var_58]
0x1800da864  mov     rax, [rax+68h]
0x1800da868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da86d  mov     rcx, [rbp+5Fh]; this
0x1800da871  test    eax, eax
0x1800da873  jns     short loc_1800DA88A
0x1800da875  mov     r9d, eax; char *
0x1800da878  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800da87f  mov     edx, 5DBh; void *
0x1800da884  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800da88a  mov     rdi, [rbp+57h+var_70]
0x1800da88e  mov     rax, [rdi]
0x1800da891  mov     rbx, [rax+0D8h]
0x1800da898  lea     rcx, [rbp+57h+var_A0]
0x1800da89c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800da8a1  lea     r9, [rbp+57h+var_A0]
0x1800da8a5  mov     r8d, 8
0x1800da8ab  mov     rdx, [rbp+57h+var_80]
0x1800da8af  mov     rcx, rdi
0x1800da8b2  mov     rax, rbx
0x1800da8b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da8ba  mov     rcx, [rbp+5Fh]; this
0x1800da8be  test    eax, eax
0x1800da8c0  jns     short loc_1800DA8D7
0x1800da8c2  mov     r9d, eax; char *
0x1800da8c5  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800da8cc  mov     edx, 5E1h; void *
0x1800da8d1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800da8d7  mov     rcx, [rbp+57h+var_A0]
0x1800da8db  mov     rax, [rcx]
0x1800da8de  lea     rdx, [rbp+57h+var_98]
0x1800da8e2  mov     rax, [rax+38h]
0x1800da8e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da8eb  mov     rcx, [rbp+5Fh]; this
0x1800da8ef  test    eax, eax
0x1800da8f1  jns     short loc_1800DA908
0x1800da8f3  mov     r9d, eax; char *
0x1800da8f6  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800da8fd  mov     edx, 5E3h; void *
0x1800da902  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800da908  mov     esi, r15d
0x1800da90b  cmp     esi, [rbp+57h+var_98]
0x1800da90e  jnb     loc_1800DAA42
0x1800da914  mov     [rbp+57h+var_60], r15
0x1800da918  mov     rcx, [rbp+57h+var_A0]
0x1800da91c  mov     rax, [rcx]
0x1800da91f  lea     r8, [rbp+57h+var_90]
0x1800da923  mov     edx, esi
0x1800da925  mov     rax, [rax+30h]
0x1800da929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da92e  mov     rcx, [rbp+5Fh]; this
0x1800da932  test    eax, eax
0x1800da934  js      loc_1800DAA2D
0x1800da93a  mov     rdi, [rbp+57h+var_68]
0x1800da93e  mov     rax, [rdi]
0x1800da941  mov     rbx, [rax+60h]
0x1800da945  lea     rcx, [rbp+57h+var_88]
0x1800da949  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800da94e  lea     r8, [rbp+57h+var_88]
0x1800da952  mov     rdx, [rbp+57h+var_90]
0x1800da956  mov     rcx, rdi
0x1800da959  mov     rax, rbx
0x1800da95c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da961  mov     rcx, [rbp+5Fh]; this
0x1800da965  test    eax, eax
0x1800da967  js      loc_1800DAA18
0x1800da96d  mov     rcx, [rbp+57h+var_90]
0x1800da971  mov     rax, [rcx]
0x1800da974  lea     rdx, [rbp+57h+var_60]
0x1800da978  mov     rax, [rax+68h]
0x1800da97c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da981  mov     rcx, [rbp+5Fh]; this
0x1800da985  test    eax, eax
0x1800da987  js      short loc_1800DAA03
0x1800da989  mov     rax, [rbp+57h+var_58]
0x1800da98d  cmp     [rbp+57h+var_60], rax
0x1800da991  jz      short loc_1800DA99A
0x1800da993  inc     esi
0x1800da995  jmp     loc_1800DA90B
0x1800da99a  mov     [rbp+57h+var_78], r15
0x1800da99e  mov     rdi, [rbp+57h+var_88]
0x1800da9a2  mov     rax, [rdi]
0x1800da9a5  mov     rbx, [rax+58h]
0x1800da9a9  xor     edx, edx
0x1800da9ab  lea     rcx, [rbp+57h+var_78]
0x1800da9af  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800da9b4  lea     rdx, [rbp+57h+var_78]
0x1800da9b8  mov     rcx, rdi
0x1800da9bb  mov     rax, rbx
0x1800da9be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da9c3  mov     rcx, [rbp+5Fh]; this
0x1800da9c7  test    eax, eax
0x1800da9c9  jns     short loc_1800DA9E0
0x1800da9cb  mov     r9d, eax; char *
0x1800da9ce  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800da9d5  mov     edx, 5F1h; void *
0x1800da9da  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800da9e0  xor     edx, edx; length
0x1800da9e2  mov     rcx, [rbp+57h+var_78]; string
0x1800da9e6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800da9ec  mov     rdx, rax
0x1800da9ef  mov     rcx, r14
0x1800da9f2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800da9f7  nop
0x1800da9f8  lea     rcx, [rbp+57h+var_78]; this
0x1800da9fc  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800daa01  jmp     short loc_1800DAA52
0x1800daa03  mov     r9d, eax; char *
0x1800daa06  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800daa0d  mov     edx, 5EBh; void *
0x1800daa12  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800daa18  mov     r9d, eax; char *
0x1800daa1b  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800daa22  mov     edx, 5EAh; void *
0x1800daa27  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800daa2d  mov     r9d, eax; char *
0x1800daa30  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800daa37  mov     edx, 5E9h; void *
0x1800daa3c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800daa42  lea     rdx, pszFormat
0x1800daa49  mov     rcx, r14
0x1800daa4c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800daa51  nop
0x1800daa52  lea     rcx, [rbp+57h+var_90]
0x1800daa56  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800daa5b  nop
0x1800daa5c  lea     rcx, [rbp+57h+var_A0]
0x1800daa60  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800daa65  nop
0x1800daa66  lea     rcx, [rbp+57h+var_70]
0x1800daa6a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800daa6f  nop
0x1800daa70  lea     rcx, [rbp+57h+var_68]
0x1800daa74  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800daa79  nop
0x1800daa7a  lea     rcx, [rbp+57h+var_88]
0x1800daa7e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800daa83  nop
0x1800daa84  lea     rcx, [rbp+57h+var_80]
0x1800daa88  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800daa8d  mov     rax, r14
0x1800daa90  mov     rcx, [rbp+57h+var_28]
0x1800daa94  xor     rcx, rsp; StackCookie
0x1800daa97  call    __security_check_cookie
0x1800daa9c  mov     rbx, [rsp+0D0h+arg_10]
0x1800daaa4  add     rsp, 0B0h
0x1800daaab  pop     r15
0x1800daaad  pop     r14
0x1800daaaf  pop     rdi
0x1800daab0  pop     rsi
0x1800daab1  pop     rbp
0x1800daab2  retn
```
