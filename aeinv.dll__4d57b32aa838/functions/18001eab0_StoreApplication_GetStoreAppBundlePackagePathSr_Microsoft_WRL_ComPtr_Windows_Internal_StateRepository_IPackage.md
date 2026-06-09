# StoreApplication::GetStoreAppBundlePackagePathSr(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &)

- ea: `0x18001eab0`
- end: `0x18001ef9a`
- name: `?GetStoreAppBundlePackagePathSr@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z`
- size: `1258`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001bb78`

## callees

- `0x18000a39c`
- `0x18001d31c`
- `0x18001eab0`
- `0x18001f1b4`
- `0x18001f218`
- `0x18001f27c`
- `0x1800293b0`
- `0x1800404c4`
- `0x180053948`
- `0x180059920`
- `0x1800679f8`
- `0x180130010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x18001ebaf`
- `KERNEL32!RaiseException` at `0x18001ebaf`
- `KERNEL32!SetLastError` at `0x18001eb9a`
- `KERNEL32!SetLastError` at `0x18001ef87`
- `KERNEL32!SetLastError` at `0x18001eb9a`
- `KERNEL32!SetLastError` at `0x18001ef87`

## string_xrefs

- `0x18001eb58`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18001ebce`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18001ec0d`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18001ec3d`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18001ec8a`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18001ecbb`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18001ed97`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18001ee71`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18001ee86`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`
- `0x18001ee9b`: `onecore\internal\base\inc\appcompat\inventory\storeapplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall StoreApplication::GetStoreAppBundlePackagePathSr(__int64 a1, _QWORD *a2)
{
  int StringReference; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int v7; // eax
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64 *); // rbx
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64, __int64, __int64 *); // rbx
  int v15; // eax
  int v16; // eax
  unsigned int i; // esi
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, __int64, __int64 *); // rbx
  int v21; // eax
  int v22; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, HSTRING *); // rbx
  int v25; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rdx
  int v40; // [rsp+28h] [rbp-69h]
  __int64 v41; // [rsp+38h] [rbp-59h] BYREF
  __int64 v42; // [rsp+40h] [rbp-51h] BYREF
  __int64 v43; // [rsp+48h] [rbp-49h] BYREF
  __int64 v44; // [rsp+50h] [rbp-41h] BYREF
  __int64 v45; // [rsp+58h] [rbp-39h] BYREF
  __int64 v46; // [rsp+60h] [rbp-31h] BYREF
  unsigned int v47; // [rsp+68h] [rbp-29h] BYREF
  HSTRING string; // [rsp+70h] [rbp-21h] BYREF
  __int64 v49; // [rsp+78h] [rbp-19h] BYREF
  _QWORD v50[4]; // [rsp+80h] [rbp-11h] BYREF
  __int64 v51; // [rsp+B0h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]

  v50[2] = -2;
  v49 = a1;
  v44 = 0;
  v43 = 0;
  v46 = 0;
  v45 = 0;
  v41 = 0;
  v42 = 0;
  v50[0] = 0;
  v47 = 0;
  v51 = 0;
  if ( !g_ApiWindowsCreateStringReference )
  {
    SetLastError(0x32u);
    StringReference = -2147467263;
    goto LABEL_60;
  }
  StringReference = g_ApiWindowsCreateStringReference();
  if ( StringReference < 0 )
  {
LABEL_60:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v5, v6);
    JUMPOUT(0x18001EF99LL);
  }
  v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>>(
         v51,
         &v46);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5D2,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v7,
      v40);
  if ( g_ApiWindowsCreateStringReference )
  {
    if ( (int)g_ApiWindowsCreateStringReference() >= 0 )
      goto LABEL_10;
  }
  else
  {
    SetLastError(0x32u);
  }
  RaiseException(0xC000000D, 1u, 0, 0);
LABEL_10:
  v8 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
         v50[3],
         &v45);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5D7,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v8,
      v40);
  v9 = *a2;
  v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a2 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v44);
  v11 = v10(v9, &v44);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5DA,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v11,
      v40);
  v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*a2 + 104LL))(*a2, v50);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5DB,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v12,
      v40);
  v13 = v45;
  v14 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v45 + 216LL);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v41);
  v15 = v14(v13, v44, 8, &v41);
  if ( v15 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5E1,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v15,
      v40);
  v16 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v41 + 56LL))(v41, &v47);
  if ( v16 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5E3,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
      (const char *)(unsigned int)v16,
      v40);
  for ( i = 0; i < v47; ++i )
  {
    v49 = 0;
    v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v41 + 48LL))(v41, i, &v42);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x5E9,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
        (const char *)(unsigned int)v18,
        v40);
    v19 = v46;
    v20 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v46 + 96LL);
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v43);
    v21 = v20(v19, v42, &v43);
    if ( v21 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x5EA,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
        (const char *)(unsigned int)v21,
        v40);
    v22 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 104LL))(v42, &v49);
    if ( v22 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x5EB,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
        (const char *)(unsigned int)v22,
        v40);
    if ( v49 == v50[0] )
    {
      string = 0;
      v23 = v43;
      v24 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v43 + 88LL);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &string,
        0);
      v25 = v24(v23, &string);
      if ( v25 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x5F1,
          (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeapplication.cpp",
          (const char *)(unsigned int)v25,
          v40);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      std::wstring::wstring(a1, StringRawBuffer);
      if ( string )
        WindowsDeleteString(string);
      v27 = v42;
      if ( v42 )
      {
        v42 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      }
      v28 = v41;
      if ( v41 )
      {
        v41 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
      v29 = v45;
      if ( v45 )
      {
        v45 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
      v30 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
      v31 = v43;
      if ( v43 )
      {
        v43 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      }
      v32 = v44;
      if ( v44 )
      {
        v44 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      }
      return a1;
    }
  }
  std::wstring::wstring(a1, &byte_1801389F0);
  v33 = v42;
  if ( v42 )
  {
    v42 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  }
  v34 = v41;
  if ( v41 )
  {
    v41 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  v35 = v45;
  if ( v45 )
  {
    v45 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  }
  v36 = v46;
  if ( v46 )
  {
    v46 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  }
  v37 = v43;
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  }
  v38 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  return a1;
}

```

## disassembly

```asm
0x18001eab0  mov     rax, rsp
0x18001eab3  push    rbp
0x18001eab4  push    rsi
0x18001eab5  push    rdi
0x18001eab6  push    r14
0x18001eab8  push    r15
0x18001eaba  lea     rbp, [rax-5Fh]
0x18001eabe  sub     rsp, 0C0h
0x18001eac5  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFEh
0x18001eacd  mov     [rax+18h], rbx
0x18001ead1  mov     rax, cs:__security_cookie
0x18001ead8  xor     rax, rsp
0x18001eadb  mov     [rbp+57h+var_30], rax
0x18001eadf  mov     rsi, rdx
0x18001eae2  mov     r14, rcx
0x18001eae5  mov     [rbp+57h+var_70], rcx
0x18001eae9  xor     r15d, r15d
0x18001eaec  mov     [rbp+57h+var_98], r15
0x18001eaf0  mov     [rbp+57h+var_A0], r15
0x18001eaf4  mov     [rbp+57h+var_88], r15
0x18001eaf8  mov     [rbp+57h+var_90], r15
0x18001eafc  mov     [rbp+57h+var_B0], r15
0x18001eb00  mov     [rbp+57h+var_A8], r15
0x18001eb04  mov     [rbp+57h+var_68], r15
0x18001eb08  mov     [rbp+57h+var_80], r15d
0x18001eb0c  mov     [rbp+57h+var_38], r15
0x18001eb10  mov     rax, cs:?g_ApiWindowsCreateStringReference@@3P6A_JXZEA; __int64 (*g_ApiWindowsCreateStringReference)(void)
0x18001eb17  test    rax, rax
0x18001eb1a  jz      loc_18001EF82
0x18001eb20  lea     r9, [rbp+57h+var_38]
0x18001eb24  lea     r8, [rbp+57h+var_50]
0x18001eb28  lea     edx, [r15+30h]
0x18001eb2c  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_PackageLocation@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18001eb33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb38  test    eax, eax
0x18001eb3a  js      loc_18001EF92
0x18001eb40  lea     rdx, [rbp+57h+var_88]
0x18001eb44  mov     rcx, [rbp+57h+var_38]
0x18001eb48  call    ??$GetActivationFactory@V?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>>)
0x18001eb4d  mov     rcx, [rbp+5Fh]; this
0x18001eb51  test    eax, eax
0x18001eb53  jns     short loc_18001EB6A
0x18001eb55  mov     r9d, eax; char *
0x18001eb58  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x18001eb5f  mov     edx, 5D2h; void *
0x18001eb64  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001eb6a  mov     rax, cs:?g_ApiWindowsCreateStringReference@@3P6A_JXZEA; __int64 (*g_ApiWindowsCreateStringReference)(void)
0x18001eb71  test    rax, rax
0x18001eb74  jz      short loc_18001EB95
0x18001eb76  lea     r9, [rbp+57h+var_50]
0x18001eb7a  lea     r8, [rbp+57h+var_48]
0x18001eb7e  mov     edx, 28h ; '('
0x18001eb83  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18001eb8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb8f  test    eax, eax
0x18001eb91  js      short loc_18001EBA0
0x18001eb93  jmp     short loc_18001EBB6
0x18001eb95  mov     ecx, 32h ; '2'; dwErrCode
0x18001eb9a  call    cs:__imp_SetLastError
0x18001eba0  xor     r9d, r9d; lpArguments
0x18001eba3  xor     r8d, r8d; nNumberOfArguments
0x18001eba6  lea     edx, [r9+1]; dwExceptionFlags
0x18001ebaa  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001ebaf  call    cs:__imp_RaiseException
0x18001ebb5  nop
0x18001ebb6  lea     rdx, [rbp+57h+var_90]
0x18001ebba  mov     rcx, [rbp+57h+var_50]
0x18001ebbe  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x18001ebc3  mov     rcx, [rbp+5Fh]; this
0x18001ebc7  test    eax, eax
0x18001ebc9  jns     short loc_18001EBE0
0x18001ebcb  mov     r9d, eax; char *
0x18001ebce  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x18001ebd5  mov     edx, 5D7h; void *
0x18001ebda  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001ebe0  mov     rdi, [rsi]
0x18001ebe3  mov     rax, [rdi]
0x18001ebe6  mov     rbx, [rax+48h]
0x18001ebea  lea     rcx, [rbp+57h+var_98]
0x18001ebee  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18001ebf3  lea     rdx, [rbp+57h+var_98]
0x18001ebf7  mov     rcx, rdi
0x18001ebfa  mov     rax, rbx
0x18001ebfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec02  mov     rcx, [rbp+5Fh]; this
0x18001ec06  test    eax, eax
0x18001ec08  jns     short loc_18001EC1F
0x18001ec0a  mov     r9d, eax; char *
0x18001ec0d  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x18001ec14  mov     edx, 5DAh; void *
0x18001ec19  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001ec1f  mov     rcx, [rsi]
0x18001ec22  mov     rax, [rcx]
0x18001ec25  lea     rdx, [rbp+57h+var_68]
0x18001ec29  mov     rax, [rax+68h]
0x18001ec2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec32  mov     rcx, [rbp+5Fh]; this
0x18001ec36  test    eax, eax
0x18001ec38  jns     short loc_18001EC4F
0x18001ec3a  mov     r9d, eax; char *
0x18001ec3d  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x18001ec44  mov     edx, 5DBh; void *
0x18001ec49  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001ec4f  mov     rdi, [rbp+57h+var_90]
0x18001ec53  mov     rax, [rdi]
0x18001ec56  mov     rbx, [rax+0D8h]
0x18001ec5d  lea     rcx, [rbp+57h+var_B0]
0x18001ec61  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18001ec66  lea     r9, [rbp+57h+var_B0]
0x18001ec6a  mov     r8d, 8
0x18001ec70  mov     rdx, [rbp+57h+var_98]
0x18001ec74  mov     rcx, rdi
0x18001ec77  mov     rax, rbx
0x18001ec7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec7f  mov     rcx, [rbp+5Fh]; this
0x18001ec83  test    eax, eax
0x18001ec85  jns     short loc_18001EC9C
0x18001ec87  mov     r9d, eax; char *
0x18001ec8a  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x18001ec91  mov     edx, 5E1h; void *
0x18001ec96  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001ec9c  mov     rcx, [rbp+57h+var_B0]
0x18001eca0  mov     rax, [rcx]
0x18001eca3  lea     rdx, [rbp+57h+var_80]
0x18001eca7  mov     rax, [rax+38h]
0x18001ecab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecb0  mov     rcx, [rbp+5Fh]; this
0x18001ecb4  test    eax, eax
0x18001ecb6  jns     short loc_18001ECCD
0x18001ecb8  mov     r9d, eax; char *
0x18001ecbb  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x18001ecc2  mov     edx, 5E3h; void *
0x18001ecc7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001eccd  mov     esi, r15d
0x18001ecd0  cmp     esi, [rbp+57h+var_80]
0x18001ecd3  jnb     loc_18001EEAD
0x18001ecd9  mov     [rbp+57h+var_70], r15
0x18001ecdd  mov     rcx, [rbp+57h+var_B0]
0x18001ece1  mov     rax, [rcx]
0x18001ece4  lea     r8, [rbp+57h+var_A8]
0x18001ece8  mov     edx, esi
0x18001ecea  mov     rax, [rax+30h]
0x18001ecee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecf3  mov     rcx, [rbp+5Fh]; this
0x18001ecf7  test    eax, eax
0x18001ecf9  js      loc_18001EE98
0x18001ecff  mov     rdi, [rbp+57h+var_88]
0x18001ed03  mov     rax, [rdi]
0x18001ed06  mov     rbx, [rax+60h]
0x18001ed0a  lea     rcx, [rbp+57h+var_A0]
0x18001ed0e  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x18001ed13  lea     r8, [rbp+57h+var_A0]
0x18001ed17  mov     rdx, [rbp+57h+var_A8]
0x18001ed1b  mov     rcx, rdi
0x18001ed1e  mov     rax, rbx
0x18001ed21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed26  mov     rcx, [rbp+5Fh]; this
0x18001ed2a  test    eax, eax
0x18001ed2c  js      loc_18001EE83
0x18001ed32  mov     rcx, [rbp+57h+var_A8]
0x18001ed36  mov     rax, [rcx]
0x18001ed39  lea     rdx, [rbp+57h+var_70]
0x18001ed3d  mov     rax, [rax+68h]
0x18001ed41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed46  mov     rcx, [rbp+5Fh]; this
0x18001ed4a  test    eax, eax
0x18001ed4c  js      loc_18001EE6E
0x18001ed52  mov     rax, [rbp+57h+var_68]
0x18001ed56  cmp     [rbp+57h+var_70], rax
0x18001ed5a  jz      short loc_18001ED63
0x18001ed5c  inc     esi
0x18001ed5e  jmp     loc_18001ECD0
0x18001ed63  mov     [rbp+57h+string], r15
0x18001ed67  mov     rdi, [rbp+57h+var_A0]
0x18001ed6b  mov     rax, [rdi]
0x18001ed6e  mov     rbx, [rax+58h]
0x18001ed72  xor     edx, edx
0x18001ed74  lea     rcx, [rbp+57h+string]
0x18001ed78  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18001ed7d  lea     rdx, [rbp+57h+string]
0x18001ed81  mov     rcx, rdi
0x18001ed84  mov     rax, rbx
0x18001ed87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed8c  mov     rcx, [rbp+5Fh]; this
0x18001ed90  test    eax, eax
0x18001ed92  jns     short loc_18001EDA9
0x18001ed94  mov     r9d, eax; char *
0x18001ed97  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x18001ed9e  mov     edx, 5F1h; void *
0x18001eda3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001eda9  xor     edx, edx; length
0x18001edab  mov     rcx, [rbp+57h+string]; string
0x18001edaf  call    WindowsGetStringRawBuffer
0x18001edb4  mov     rdx, rax
0x18001edb7  mov     rcx, r14
0x18001edba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001edbf  nop
0x18001edc0  mov     rcx, [rbp+57h+string]; string
0x18001edc4  test    rcx, rcx
0x18001edc7  jz      short loc_18001EDCF
0x18001edc9  call    WindowsDeleteString
0x18001edce  nop
0x18001edcf  mov     rcx, [rbp+57h+var_A8]
0x18001edd3  test    rcx, rcx
0x18001edd6  jz      short loc_18001EDE9
0x18001edd8  mov     [rbp+57h+var_A8], r15
0x18001eddc  mov     rax, [rcx]
0x18001eddf  mov     rax, [rax+10h]
0x18001ede3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ede8  nop
0x18001ede9  mov     rcx, [rbp+57h+var_B0]
0x18001eded  test    rcx, rcx
0x18001edf0  jz      short loc_18001EE03
0x18001edf2  mov     [rbp+57h+var_B0], r15
0x18001edf6  mov     rax, [rcx]
0x18001edf9  mov     rax, [rax+10h]
0x18001edfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee02  nop
0x18001ee03  mov     rcx, [rbp+57h+var_90]
0x18001ee07  test    rcx, rcx
0x18001ee0a  jz      short loc_18001EE1D
0x18001ee0c  mov     [rbp+57h+var_90], r15
0x18001ee10  mov     rax, [rcx]
0x18001ee13  mov     rax, [rax+10h]
0x18001ee17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee1c  nop
0x18001ee1d  mov     rcx, [rbp+57h+var_88]
0x18001ee21  test    rcx, rcx
0x18001ee24  jz      short loc_18001EE37
0x18001ee26  mov     [rbp+57h+var_88], r15
0x18001ee2a  mov     rax, [rcx]
0x18001ee2d  mov     rax, [rax+10h]
0x18001ee31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee36  nop
0x18001ee37  mov     rcx, [rbp+57h+var_A0]
0x18001ee3b  test    rcx, rcx
0x18001ee3e  jz      short loc_18001EE51
0x18001ee40  mov     [rbp+57h+var_A0], r15
0x18001ee44  mov     rax, [rcx]
0x18001ee47  mov     rax, [rax+10h]
0x18001ee4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee50  nop
0x18001ee51  mov     rcx, [rbp+57h+var_98]
0x18001ee55  test    rcx, rcx
0x18001ee58  jz      loc_18001EF5C
0x18001ee5e  mov     [rbp+57h+var_98], r15
0x18001ee62  mov     rax, [rcx]
0x18001ee65  mov     rax, [rax+10h]
0x18001ee69  jmp     loc_18001EF56
0x18001ee6e  mov     r9d, eax; char *
0x18001ee71  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x18001ee78  mov     edx, 5EBh; void *
0x18001ee7d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001ee83  mov     r9d, eax; char *
0x18001ee86  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x18001ee8d  mov     edx, 5EAh; void *
0x18001ee92  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001ee98  mov     r9d, eax; char *
0x18001ee9b  lea     r8, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\appcompat"...
0x18001eea2  mov     edx, 5E9h; void *
0x18001eea7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001eead  lea     rdx, byte_1801389F0
0x18001eeb4  mov     rcx, r14
0x18001eeb7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001eebc  nop
0x18001eebd  mov     rcx, [rbp+57h+var_A8]
0x18001eec1  test    rcx, rcx
0x18001eec4  jz      short loc_18001EED7
0x18001eec6  mov     [rbp+57h+var_A8], r15
0x18001eeca  mov     rax, [rcx]
0x18001eecd  mov     rax, [rax+10h]
0x18001eed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eed6  nop
0x18001eed7  mov     rcx, [rbp+57h+var_B0]
0x18001eedb  test    rcx, rcx
0x18001eede  jz      short loc_18001EEF1
0x18001eee0  mov     [rbp+57h+var_B0], r15
0x18001eee4  mov     rax, [rcx]
0x18001eee7  mov     rax, [rax+10h]
0x18001eeeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eef0  nop
0x18001eef1  mov     rcx, [rbp+57h+var_90]
0x18001eef5  test    rcx, rcx
0x18001eef8  jz      short loc_18001EF0B
0x18001eefa  mov     [rbp+57h+var_90], r15
0x18001eefe  mov     rax, [rcx]
0x18001ef01  mov     rax, [rax+10h]
0x18001ef05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef0a  nop
0x18001ef0b  mov     rcx, [rbp+57h+var_88]
0x18001ef0f  test    rcx, rcx
0x18001ef12  jz      short loc_18001EF25
0x18001ef14  mov     [rbp+57h+var_88], r15
0x18001ef18  mov     rax, [rcx]
0x18001ef1b  mov     rax, [rax+10h]
0x18001ef1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef24  nop
0x18001ef25  mov     rcx, [rbp+57h+var_A0]
0x18001ef29  test    rcx, rcx
0x18001ef2c  jz      short loc_18001EF3F
  ... truncated ...
```
