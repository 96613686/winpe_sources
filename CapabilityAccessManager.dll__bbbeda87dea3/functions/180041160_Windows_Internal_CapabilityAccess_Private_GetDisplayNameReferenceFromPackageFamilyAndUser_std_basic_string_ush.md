# Windows::Internal::CapabilityAccess::Private::GetDisplayNameReferenceFromPackageFamilyAndUser(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180041160`
- end: `0x180041574`
- name: `?GetDisplayNameReferenceFromPackageFamilyAndUser@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@0@Z`
- size: `1044`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180041a88`
- `0x18008dc00`

## callees

- `0x1800094c0`
- `0x18001649c`
- `0x18001f5f4`
- `0x18002392c`
- `0x18003e588`
- `0x18003e624`
- `0x180041160`
- `0x180042514`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004131e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180041436`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004131e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180041436`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004133f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180041457`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004133f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180041457`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800413b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800414cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041531`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800413b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800414cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180041531`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004151b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004151b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180041307`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004141f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180041307`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004141f`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::GetDisplayNameReferenceFromPackageFamilyAndUser(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rbx
  _QWORD *v5; // rax
  int v6; // eax
  __int64 v7; // rsi
  __int64 (__fastcall *v8)(__int64, __int64, __int64 *); // rdi
  int v9; // eax
  int v10; // eax
  __int64 v11; // rsi
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *); // rdi
  int v13; // eax
  HSTRING v14; // rbx
  int ActivationFactory; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  int v21; // eax
  HSTRING v22; // rdi
  int v23; // eax
  __int64 v24; // rsi
  __int64 (__fastcall *v25)(__int64, __int64, __int64 *); // rdi
  int v26; // eax
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, HSTRING *); // rbx
  int v29; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v32; // [rsp+20h] [rbp-60h] BYREF
  __int64 v33; // [rsp+28h] [rbp-58h] BYREF
  HSTRING v34; // [rsp+30h] [rbp-50h] BYREF
  int v35; // [rsp+38h] [rbp-48h] BYREF
  __int64 v36; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v37[2]; // [rsp+48h] [rbp-38h] BYREF
  HSTRING string; // [rsp+58h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v37[0] = a1;
  Windows::Internal::CapabilityAccess::Private::GetPackageFromFamilyNameAndUser(v37, a3, a2);
  v4 = v37[0];
  if ( !v37[0] )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x699,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)0x80070490LL,
      v32);
  v36 = 0;
  v35 = 0;
  v33 = 0;
  v5 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                   &string,
                   L"Windows.Internal.StateRepository.Application");
  v6 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(
         *v5,
         &v33);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6A1,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v6,
      v32);
  v32 = 0;
  v7 = v33;
  v8 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v33 + 144LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  v9 = v8(v7, v4, &v32);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6A4,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v9,
      v32);
  v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v32 + 56LL))(v32, &v35);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6A6,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v10,
      v32);
  v11 = v32;
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v32 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
  v13 = v12(v11, 0, &v36);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6A7,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v13,
      v32);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
  v34 = 0;
  if ( v35 == 1 )
  {
    v33 = 0;
    v32 = 0;
    if ( WindowsCreateStringReference(
           L"Windows.Internal.StateRepository.MrtApplication",
           0x2Fu,
           &hstringHeader,
           &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v14 = string;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    ActivationFactory = RoGetActivationFactory(v14, &GUID_f7e80409_27e5_4514_805f_a431c4ce3b96, &v33);
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6B3,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v32);
    v16 = v33;
    v17 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v33 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    v18 = v17(v16, v36, &v32);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6B4,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)(unsigned int)v18,
        v32);
    v19 = v32;
    v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 80LL);
    WindowsDeleteString(v34);
    v34 = 0;
    v21 = v20(v19, &v34);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6B5,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)(unsigned int)v21,
        v32);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
  }
  else
  {
    v32 = 0;
    v33 = 0;
    if ( WindowsCreateStringReference(L"Windows.Internal.StateRepository.MrtPackage", 0x2Bu, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v22 = string;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    v23 = RoGetActivationFactory(v22, &GUID_ede4711a_0c90_4d5b_acf3_58af696d9425, &v32);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6BD,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)(unsigned int)v23,
        v32);
    v24 = v32;
    v25 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v32 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    v26 = v25(v24, v4, &v33);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6BE,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)(unsigned int)v26,
        v32);
    v27 = v33;
    v28 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 80LL);
    WindowsDeleteString(v34);
    v34 = 0;
    v29 = v28(v27, &v34);
    if ( v29 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6BF,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)(unsigned int)v29,
        v32);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v34, 0);
  std::wstring::wstring(a1, StringRawBuffer);
  WindowsDeleteString(v34);
  v34 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v37);
  return a1;
}

```

## disassembly

```asm
0x180041160  mov     [rsp-28h+arg_18], rbx
0x180041165  push    rbp
0x180041166  push    rsi
0x180041167  push    rdi
0x180041168  push    r14
0x18004116a  push    r15
0x18004116c  mov     rbp, rsp
0x18004116f  sub     rsp, 80h
0x180041176  mov     rax, cs:__security_cookie
0x18004117d  xor     rax, rsp
0x180041180  mov     [rbp+var_8], rax
0x180041184  mov     rax, r8
0x180041187  mov     r14, rcx
0x18004118a  mov     [rbp+var_38], rcx
0x18004118e  xor     r15d, r15d
0x180041191  mov     r8, rdx
0x180041194  mov     rdx, rax
0x180041197  lea     rcx, [rbp+var_38]
0x18004119b  call    ?GetPackageFromFamilyNameAndUser@Private@CapabilityAccess@Internal@Windows@@YA?AV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Windows::Internal::CapabilityAccess::Private::GetPackageFromFamilyNameAndUser(std::wstring const &,std::wstring const &)
0x1800411a0  nop
0x1800411a1  mov     rcx, [rbp+28h]; this
0x1800411a5  mov     rbx, [rbp+var_38]
0x1800411a9  test    rbx, rbx
0x1800411ac  jnz     short loc_1800411C6
0x1800411ae  mov     r9d, 80070490h; char *
0x1800411b4  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800411bb  mov     edx, 699h; void *
0x1800411c0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800411c6  mov     [rbp+var_40], r15
0x1800411ca  mov     [rbp+var_48], r15d
0x1800411ce  mov     [rbp+var_58], r15
0x1800411d2  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x1800411d9  lea     rcx, [rbp+string]; string
0x1800411dd  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x1800411e2  lea     rdx, [rbp+var_58]
0x1800411e6  mov     rcx, [rax]
0x1800411e9  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>)
0x1800411ee  mov     rcx, [rbp+28h]; this
0x1800411f2  test    eax, eax
0x1800411f4  jns     short loc_18004120B
0x1800411f6  mov     r9d, eax; char *
0x1800411f9  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180041200  mov     edx, 6A1h; void *
0x180041205  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004120b  mov     [rbp+var_60], r15
0x18004120f  mov     rsi, [rbp+var_58]
0x180041213  mov     rax, [rsi]
0x180041216  mov     rdi, [rax+90h]
0x18004121d  lea     rcx, [rbp+var_60]
0x180041221  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041226  lea     r8, [rbp+var_60]
0x18004122a  mov     rdx, rbx
0x18004122d  mov     rcx, rsi
0x180041230  mov     rax, rdi
0x180041233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041238  mov     rcx, [rbp+28h]; this
0x18004123c  test    eax, eax
0x18004123e  jns     short loc_180041255
0x180041240  mov     r9d, eax; char *
0x180041243  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x18004124a  mov     edx, 6A4h; void *
0x18004124f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180041255  mov     rcx, [rbp+var_60]
0x180041259  mov     rax, [rcx]
0x18004125c  lea     rdx, [rbp+var_48]
0x180041260  mov     rax, [rax+38h]
0x180041264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041269  mov     rcx, [rbp+28h]; this
0x18004126d  test    eax, eax
0x18004126f  jns     short loc_180041286
0x180041271  mov     r9d, eax; char *
0x180041274  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x18004127b  mov     edx, 6A6h; void *
0x180041280  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180041286  mov     rsi, [rbp+var_60]
0x18004128a  mov     rax, [rsi]
0x18004128d  mov     rdi, [rax+30h]
0x180041291  lea     rcx, [rbp+var_40]
0x180041295  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004129a  lea     r8, [rbp+var_40]
0x18004129e  xor     edx, edx
0x1800412a0  mov     rcx, rsi
0x1800412a3  mov     rax, rdi
0x1800412a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800412ab  mov     rcx, [rbp+28h]; this
0x1800412af  test    eax, eax
0x1800412b1  jns     short loc_1800412C8
0x1800412b3  mov     r9d, eax; char *
0x1800412b6  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800412bd  mov     edx, 6A7h; void *
0x1800412c2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800412c8  lea     rcx, [rbp+var_60]
0x1800412cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800412d1  nop
0x1800412d2  lea     rcx, [rbp+var_58]
0x1800412d6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800412db  mov     [rbp+var_50], r15
0x1800412df  mov     edi, 1
0x1800412e4  cmp     [rbp+var_48], edi
0x1800412e7  jnz     loc_180041403
0x1800412ed  mov     [rbp+var_58], r15
0x1800412f1  mov     [rbp+var_60], r15
0x1800412f5  lea     r9, [rbp+string]; string
0x1800412f9  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800412fd  lea     edx, [rdi+2Eh]; length
0x180041300  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_MrtApplication@@3QBGB; "Windows.Internal.StateRepository.MrtApp"...
0x180041307  call    cs:__imp_WindowsCreateStringReference
0x18004130d  test    eax, eax
0x18004130f  jns     short loc_180041324
0x180041311  xor     r9d, r9d; lpArguments
0x180041314  xor     r8d, r8d; nNumberOfArguments
0x180041317  mov     edx, edi; dwExceptionFlags
0x180041319  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004131e  call    cs:__imp_RaiseException
0x180041324  mov     rbx, [rbp+string]
0x180041328  lea     rcx, [rbp+var_58]
0x18004132c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041331  lea     r8, [rbp+var_58]
0x180041335  lea     rdx, _GUID_f7e80409_27e5_4514_805f_a431c4ce3b96
0x18004133c  mov     rcx, rbx
0x18004133f  call    cs:__imp_RoGetActivationFactory
0x180041345  mov     rcx, [rbp+28h]; this
0x180041349  test    eax, eax
0x18004134b  jns     short loc_180041362
0x18004134d  mov     r9d, eax; char *
0x180041350  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180041357  mov     edx, 6B3h; void *
0x18004135c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180041362  mov     rdi, [rbp+var_58]
0x180041366  mov     rax, [rdi]
0x180041369  mov     rbx, [rax+50h]
0x18004136d  lea     rcx, [rbp+var_60]
0x180041371  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041376  lea     r8, [rbp+var_60]
0x18004137a  mov     rdx, [rbp+var_40]
0x18004137e  mov     rcx, rdi
0x180041381  mov     rax, rbx
0x180041384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041389  mov     rcx, [rbp+28h]; this
0x18004138d  test    eax, eax
0x18004138f  jns     short loc_1800413A6
0x180041391  mov     r9d, eax; char *
0x180041394  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x18004139b  mov     edx, 6B4h; void *
0x1800413a0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800413a6  mov     rdi, [rbp+var_60]
0x1800413aa  mov     rax, [rdi]
0x1800413ad  mov     rbx, [rax+50h]
0x1800413b1  mov     rcx, [rbp+var_50]; string
0x1800413b5  call    cs:__imp_WindowsDeleteString
0x1800413bb  mov     [rbp+var_50], r15
0x1800413bf  lea     rdx, [rbp+var_50]
0x1800413c3  mov     rcx, rdi
0x1800413c6  mov     rax, rbx
0x1800413c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413ce  mov     rcx, [rbp+28h]; this
0x1800413d2  test    eax, eax
0x1800413d4  jns     short loc_1800413EB
0x1800413d6  mov     r9d, eax; char *
0x1800413d9  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800413e0  mov     edx, 6B5h; void *
0x1800413e5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800413eb  lea     rcx, [rbp+var_60]
0x1800413ef  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800413f4  nop
0x1800413f5  lea     rcx, [rbp+var_58]
0x1800413f9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800413fe  jmp     loc_180041515
0x180041403  mov     [rbp+var_60], r15
0x180041407  mov     [rbp+var_58], r15
0x18004140b  lea     r9, [rbp+string]; string
0x18004140f  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180041413  mov     edx, 2Bh ; '+'; length
0x180041418  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_MrtPackage@@3QBGB; "Windows.Internal.StateRepository.MrtPac"...
0x18004141f  call    cs:__imp_WindowsCreateStringReference
0x180041425  test    eax, eax
0x180041427  jns     short loc_18004143C
0x180041429  xor     r9d, r9d; lpArguments
0x18004142c  xor     r8d, r8d; nNumberOfArguments
0x18004142f  mov     edx, edi; dwExceptionFlags
0x180041431  mov     ecx, 0C000000Dh; dwExceptionCode
0x180041436  call    cs:__imp_RaiseException
0x18004143c  mov     rdi, [rbp+string]
0x180041440  lea     rcx, [rbp+var_60]
0x180041444  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041449  lea     r8, [rbp+var_60]
0x18004144d  lea     rdx, _GUID_ede4711a_0c90_4d5b_acf3_58af696d9425
0x180041454  mov     rcx, rdi
0x180041457  call    cs:__imp_RoGetActivationFactory
0x18004145d  mov     rcx, [rbp+28h]; this
0x180041461  test    eax, eax
0x180041463  jns     short loc_18004147A
0x180041465  mov     r9d, eax; char *
0x180041468  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x18004146f  mov     edx, 6BDh; void *
0x180041474  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004147a  mov     rsi, [rbp+var_60]
0x18004147e  mov     rax, [rsi]
0x180041481  mov     rdi, [rax+50h]
0x180041485  lea     rcx, [rbp+var_58]
0x180041489  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004148e  lea     r8, [rbp+var_58]
0x180041492  mov     rdx, rbx
0x180041495  mov     rcx, rsi
0x180041498  mov     rax, rdi
0x18004149b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800414a0  mov     rcx, [rbp+28h]; this
0x1800414a4  test    eax, eax
0x1800414a6  jns     short loc_1800414BD
0x1800414a8  mov     r9d, eax; char *
0x1800414ab  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800414b2  mov     edx, 6BEh; void *
0x1800414b7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800414bd  mov     rdi, [rbp+var_58]
0x1800414c1  mov     rax, [rdi]
0x1800414c4  mov     rbx, [rax+50h]
0x1800414c8  mov     rcx, [rbp+var_50]; string
0x1800414cc  call    cs:__imp_WindowsDeleteString
0x1800414d2  mov     [rbp+var_50], r15
0x1800414d6  lea     rdx, [rbp+var_50]
0x1800414da  mov     rcx, rdi
0x1800414dd  mov     rax, rbx
0x1800414e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800414e5  mov     rcx, [rbp+28h]; this
0x1800414e9  test    eax, eax
0x1800414eb  jns     short loc_180041502
0x1800414ed  mov     r9d, eax; char *
0x1800414f0  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800414f7  mov     edx, 6BFh; void *
0x1800414fc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180041502  lea     rcx, [rbp+var_58]
0x180041506  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004150b  nop
0x18004150c  lea     rcx, [rbp+var_60]
0x180041510  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041515  xor     edx, edx; length
0x180041517  mov     rcx, [rbp+var_50]; string
0x18004151b  call    cs:__imp_WindowsGetStringRawBuffer
0x180041521  mov     rdx, rax
0x180041524  mov     rcx, r14
0x180041527  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004152c  nop
0x18004152d  mov     rcx, [rbp+var_50]; string
0x180041531  call    cs:__imp_WindowsDeleteString
0x180041537  mov     [rbp+var_50], r15
0x18004153b  lea     rcx, [rbp+var_40]
0x18004153f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041544  nop
0x180041545  lea     rcx, [rbp+var_38]
0x180041549  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004154e  mov     rax, r14
0x180041551  mov     rcx, [rbp+var_8]
0x180041555  xor     rcx, rsp; StackCookie
0x180041558  call    __security_check_cookie
0x18004155d  mov     rbx, [rsp+80h+arg_18]
0x180041565  add     rsp, 80h
0x18004156c  pop     r15
0x18004156e  pop     r14
0x180041570  pop     rdi
0x180041571  pop     rsi
0x180041572  pop     rbp
0x180041573  retn
```
