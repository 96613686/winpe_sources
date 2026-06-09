# Windows::Internal::CapabilityAccess::Private::IsXboxAppCategoryGame(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180044b9c`
- end: `0x180044f43`
- name: `?IsXboxAppCategoryGame@Private@CapabilityAccess@Internal@Windows@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `935`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006fa20`

## callees

- `0x1800094c0`
- `0x18001f5f4`
- `0x18002392c`
- `0x180029408`
- `0x18003e4f0`
- `0x18003e53c`
- `0x18003e660`
- `0x18003e6d8`
- `0x180044b9c`
- `0x180045f78`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180044d35`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180044e38`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180044e6d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180044d35`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180044e38`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180044e6d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180044d56`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180044d56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044d1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044e21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044e56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044d1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044e21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044e56`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall Windows::Internal::CapabilityAccess::Private::IsXboxAppCategoryGame(
        __int64 a1,
        const unsigned __int16 *a2)
{
  __int64 *v3; // rax
  int v4; // eax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, HSTRING, __int64); // rbx
  const unsigned __int16 *v7; // rax
  char v8; // si
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *); // rbx
  int v13; // eax
  HSTRING v14; // rbx
  int ActivationFactory; // eax
  const unsigned __int16 *v16; // rdx
  __int64 *v17; // rax
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64 *); // rbx
  int v21; // eax
  __int64 v22; // rbx
  int (__fastcall *v23)(__int64, __int64, __int64, HSTRING, HSTRING, _BYTE *); // r14
  HSTRING v24; // rdi
  int v26; // [rsp+20h] [rbp-69h]
  _BYTE v27[8]; // [rsp+40h] [rbp-49h] BYREF
  int v28[2]; // [rsp+48h] [rbp-41h] BYREF
  int v29; // [rsp+50h] [rbp-39h] BYREF
  __int64 v30; // [rsp+58h] [rbp-31h] BYREF
  __int64 v31; // [rsp+60h] [rbp-29h] BYREF
  __int64 v32; // [rsp+68h] [rbp-21h] BYREF
  __int64 v33; // [rsp+70h] [rbp-19h] BYREF
  __int64 v34; // [rsp+78h] [rbp-11h] BYREF
  HSTRING v35; // [rsp+80h] [rbp-9h] BYREF
  HSTRING_HEADER v36; // [rsp+88h] [rbp-1h] BYREF
  HSTRING string; // [rsp+A0h] [rbp+17h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v34 = 0;
  v3 = (__int64 *)Windows::Internal::StringReference::StringReference(&v35, (const unsigned __int16 (*)[41])a2);
  v4 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
         *v3,
         (__int64)&v34);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x40A,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v4,
      v26);
  *(_QWORD *)v28 = 0;
  v5 = v34;
  v6 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, __int64))(*(_QWORD *)v34 + 504LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v28);
  v7 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)&v35, v7);
  v8 = 1;
  v9 = v6(v5, 0, v35, 1);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x411,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v9,
      (int)v28);
  v29 = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v28 + 56LL))(*(_QWORD *)v28, &v29);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x416,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v10,
      (int)v28);
  if ( v29 != 1 )
  {
    v8 = 0;
LABEL_26:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v28);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    return v8;
  }
  v32 = 0;
  v11 = *(_QWORD *)v28;
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)v28 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  v13 = v12(v11, 0, &v32);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x41D,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v13,
      (int)v28);
  v31 = 0;
  if ( WindowsCreateStringReference(L"Windows.Internal.StateRepository.PackagePolicy", 0x2Eu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v14 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  ActivationFactory = RoGetActivationFactory(v14, &GUID_93b105c2_0759_4c56_b8da_6e8f72ac464e, &v31);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x422,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)v28);
  v33 = 0;
  v30 = 0;
  v17 = (__int64 *)Windows::Internal::StringReference::StringReference(&v35, (const unsigned __int16 (*)[38])v16);
  v18 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics>>(
          *v17,
          (__int64)&v33);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x429,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v18,
      (int)v28);
  v19 = v33;
  v20 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 112LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  v21 = v20(v19, &v30);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x42A,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v21,
      (int)v28);
  v27[0] = 0;
  v22 = v31;
  v23 = *(int (__fastcall **)(__int64, __int64, __int64, HSTRING, HSTRING, _BYTE *))(*(_QWORD *)v31 + 256LL);
  if ( WindowsCreateStringReference(L"game", 4u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v24 = string;
  if ( WindowsCreateStringReference(L"AppCategory", 0xBu, &v36, &v35) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  if ( v23(v22, v30, v32, v35, v24, v27) >= 0 && v27[0] )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    goto LABEL_26;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v28);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
  return 0;
}

```

## disassembly

```asm
0x180044b9c  mov     [rsp-8+arg_8], rbx
0x180044ba1  mov     [rsp-8+arg_10], rsi
0x180044ba6  push    rbp
0x180044ba7  push    rdi
0x180044ba8  push    r14
0x180044baa  lea     rbp, [rsp-47h]
0x180044baf  sub     rsp, 0D0h
0x180044bb6  mov     rax, cs:__security_cookie
0x180044bbd  xor     rax, rsp
0x180044bc0  mov     [rbp+57h+var_20], rax
0x180044bc4  mov     rsi, rcx
0x180044bc7  mov     [rbp+57h+var_68], 0
0x180044bcf  lea     rcx, [rbp+57h+var_60]; string
0x180044bd3  call    ??$?0$0CJ@@StringReference@Internal@Windows@@QEAA@AEAY0CJ@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[41])
0x180044bd8  lea     rdx, [rbp+57h+var_68]
0x180044bdc  mov     rcx, [rax]
0x180044bdf  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x180044be4  mov     rcx, [rbp+5Fh]; this
0x180044be8  test    eax, eax
0x180044bea  jns     short loc_180044C01
0x180044bec  mov     r9d, eax; char *
0x180044bef  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180044bf6  mov     edx, 40Ah; void *
0x180044bfb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180044c01  mov     qword ptr [rbp+57h+var_98], 0
0x180044c09  mov     rdi, [rbp+57h+var_68]
0x180044c0d  mov     rax, [rdi]
0x180044c10  mov     rbx, [rax+1F8h]
0x180044c17  lea     rcx, [rbp+57h+var_98]
0x180044c1b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044c20  mov     rcx, rsi
0x180044c23  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180044c28  mov     rdx, rax; unsigned __int16 *
0x180044c2b  lea     rcx, [rbp+57h+var_60]; this
0x180044c2f  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180044c34  lea     rax, [rbp+57h+var_98]
0x180044c38  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x180044c3d  mov     esi, 1
0x180044c42  mov     r9d, esi
0x180044c45  mov     r8, [rbp+57h+var_60]
0x180044c49  xor     edx, edx
0x180044c4b  mov     rcx, rdi
0x180044c4e  mov     rax, rbx
0x180044c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c56  mov     rcx, [rbp+5Fh]; this
0x180044c5a  test    eax, eax
0x180044c5c  jns     short loc_180044C73
0x180044c5e  mov     r9d, eax; char *
0x180044c61  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180044c68  mov     edx, 411h; void *
0x180044c6d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180044c73  mov     [rbp+57h+var_90], 0
0x180044c7a  mov     rcx, qword ptr [rbp+57h+var_98]
0x180044c7e  mov     rax, [rcx]
0x180044c81  lea     rdx, [rbp+57h+var_90]
0x180044c85  mov     rax, [rax+38h]
0x180044c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c8e  mov     rcx, [rbp+5Fh]; this
0x180044c92  test    eax, eax
0x180044c94  jns     short loc_180044CAB
0x180044c96  mov     r9d, eax; char *
0x180044c99  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180044ca0  mov     edx, 416h; void *
0x180044ca5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180044cab  cmp     [rbp+57h+var_90], esi
0x180044cae  jz      short loc_180044CB8
0x180044cb0  xor     sil, sil
0x180044cb3  jmp     loc_180044ECA
0x180044cb8  mov     [rbp+57h+var_78], 0
0x180044cc0  mov     rdi, qword ptr [rbp+57h+var_98]
0x180044cc4  mov     rax, [rdi]
0x180044cc7  mov     rbx, [rax+30h]
0x180044ccb  lea     rcx, [rbp+57h+var_78]
0x180044ccf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044cd4  lea     r8, [rbp+57h+var_78]
0x180044cd8  xor     edx, edx
0x180044cda  mov     rcx, rdi
0x180044cdd  mov     rax, rbx
0x180044ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044ce5  mov     rcx, [rbp+5Fh]; this
0x180044ce9  test    eax, eax
0x180044ceb  jns     short loc_180044D02
0x180044ced  mov     r9d, eax; char *
0x180044cf0  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180044cf7  mov     edx, 41Dh; void *
0x180044cfc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180044d02  mov     [rbp+57h+var_80], 0
0x180044d0a  lea     r9, [rbp+57h+string]; string
0x180044d0e  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180044d12  mov     edx, 2Eh ; '.'; length
0x180044d17  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_PackagePolicy@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180044d1e  call    cs:__imp_WindowsCreateStringReference
0x180044d24  test    eax, eax
0x180044d26  jns     short loc_180044D3B
0x180044d28  xor     r9d, r9d; lpArguments
0x180044d2b  xor     r8d, r8d; nNumberOfArguments
0x180044d2e  mov     edx, esi; dwExceptionFlags
0x180044d30  mov     ecx, 0C000000Dh; dwExceptionCode
0x180044d35  call    cs:__imp_RaiseException
0x180044d3b  mov     rbx, [rbp+57h+string]
0x180044d3f  lea     rcx, [rbp+57h+var_80]
0x180044d43  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044d48  lea     r8, [rbp+57h+var_80]
0x180044d4c  lea     rdx, _GUID_93b105c2_0759_4c56_b8da_6e8f72ac464e
0x180044d53  mov     rcx, rbx
0x180044d56  call    cs:__imp_RoGetActivationFactory
0x180044d5c  mov     rcx, [rbp+5Fh]; this
0x180044d60  test    eax, eax
0x180044d62  jns     short loc_180044D79
0x180044d64  mov     r9d, eax; char *
0x180044d67  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180044d6e  mov     edx, 422h; void *
0x180044d73  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180044d79  mov     [rbp+57h+var_70], 0
0x180044d81  mov     [rbp+57h+var_88], 0
0x180044d89  lea     rcx, [rbp+57h+var_60]; string
0x180044d8d  call    ??$?0$0CG@@StringReference@Internal@Windows@@QEAA@AEAY0CG@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[38])
0x180044d92  lea     rdx, [rbp+57h+var_70]
0x180044d96  mov     rcx, [rax]
0x180044d99  call    ??$GetActivationFactory@V?$ComPtr@UIUserStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUserStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics>>)
0x180044d9e  mov     rcx, [rbp+5Fh]; this
0x180044da2  test    eax, eax
0x180044da4  jns     short loc_180044DBB
0x180044da6  mov     r9d, eax; char *
0x180044da9  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180044db0  mov     edx, 429h; void *
0x180044db5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180044dbb  mov     rdi, [rbp+57h+var_70]
0x180044dbf  mov     rax, [rdi]
0x180044dc2  mov     rbx, [rax+70h]
0x180044dc6  lea     rcx, [rbp+57h+var_88]
0x180044dca  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044dcf  lea     rdx, [rbp+57h+var_88]
0x180044dd3  mov     rcx, rdi
0x180044dd6  mov     rax, rbx
0x180044dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044dde  mov     rcx, [rbp+5Fh]; this
0x180044de2  test    eax, eax
0x180044de4  jns     short loc_180044DFB
0x180044de6  mov     r9d, eax; char *
0x180044de9  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180044df0  mov     edx, 42Ah; void *
0x180044df5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180044dfb  mov     [rbp+57h+var_A0], 0
0x180044dff  mov     rbx, [rbp+57h+var_80]
0x180044e03  mov     rax, [rbx]
0x180044e06  mov     r14, [rax+100h]
0x180044e0d  lea     r9, [rbp+57h+string]; string
0x180044e11  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180044e15  mov     edx, 4; length
0x180044e1a  lea     rcx, sourceString; "game"
0x180044e21  call    cs:__imp_WindowsCreateStringReference
0x180044e27  test    eax, eax
0x180044e29  jns     short loc_180044E3E
0x180044e2b  xor     r9d, r9d; lpArguments
0x180044e2e  xor     r8d, r8d; nNumberOfArguments
0x180044e31  mov     edx, esi; dwExceptionFlags
0x180044e33  mov     ecx, 0C000000Dh; dwExceptionCode
0x180044e38  call    cs:__imp_RaiseException
0x180044e3e  mov     rdi, [rbp+57h+string]
0x180044e42  lea     r9, [rbp+57h+var_60]; string
0x180044e46  lea     r8, [rbp+57h+var_58]; hstringHeader
0x180044e4a  mov     edx, 0Bh; length
0x180044e4f  lea     rcx, aAppcategory; "AppCategory"
0x180044e56  call    cs:__imp_WindowsCreateStringReference
0x180044e5c  test    eax, eax
0x180044e5e  jns     short loc_180044E73
0x180044e60  xor     r9d, r9d; lpArguments
0x180044e63  xor     r8d, r8d; nNumberOfArguments
0x180044e66  mov     edx, esi; dwExceptionFlags
0x180044e68  mov     ecx, 0C000000Dh; dwExceptionCode
0x180044e6d  call    cs:__imp_RaiseException
0x180044e73  lea     rax, [rbp+57h+var_A0]
0x180044e77  mov     [rsp+0E0h+var_B8], rax
0x180044e7c  mov     qword ptr [rsp+0E0h+var_C0], rdi
0x180044e81  mov     r9, [rbp+57h+var_60]
0x180044e85  mov     r8, [rbp+57h+var_78]
0x180044e89  mov     rdx, [rbp+57h+var_88]
0x180044e8d  mov     rcx, rbx
0x180044e90  mov     rax, r14
0x180044e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e98  test    eax, eax
0x180044e9a  js      short loc_180044EE2
0x180044e9c  cmp     [rbp+57h+var_A0], 0
0x180044ea0  jz      short loc_180044EE2
0x180044ea2  lea     rcx, [rbp+57h+var_88]
0x180044ea6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044eab  nop
0x180044eac  lea     rcx, [rbp+57h+var_70]
0x180044eb0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044eb5  nop
0x180044eb6  lea     rcx, [rbp+57h+var_80]
0x180044eba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044ebf  nop
0x180044ec0  lea     rcx, [rbp+57h+var_78]
0x180044ec4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044ec9  nop
0x180044eca  lea     rcx, [rbp+57h+var_98]
0x180044ece  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044ed3  nop
0x180044ed4  lea     rcx, [rbp+57h+var_68]
0x180044ed8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044edd  mov     al, sil
0x180044ee0  jmp     short loc_180044F1F
0x180044ee2  lea     rcx, [rbp+57h+var_88]
0x180044ee6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044eeb  nop
0x180044eec  lea     rcx, [rbp+57h+var_70]
0x180044ef0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044ef5  nop
0x180044ef6  lea     rcx, [rbp+57h+var_80]
0x180044efa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044eff  nop
0x180044f00  lea     rcx, [rbp+57h+var_78]
0x180044f04  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044f09  nop
0x180044f0a  lea     rcx, [rbp+57h+var_98]
0x180044f0e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044f13  nop
0x180044f14  lea     rcx, [rbp+57h+var_68]
0x180044f18  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180044f1d  xor     al, al
0x180044f1f  mov     rcx, [rbp+57h+var_20]
0x180044f23  xor     rcx, rsp; StackCookie
0x180044f26  call    __security_check_cookie
0x180044f2b  lea     r11, [rsp+0E0h+var_10]
0x180044f33  mov     rbx, [r11+28h]
0x180044f37  mov     rsi, [r11+30h]
0x180044f3b  mov     rsp, r11
0x180044f3e  pop     r14
0x180044f40  pop     rdi
0x180044f41  pop     rbp
0x180044f42  retn
```
