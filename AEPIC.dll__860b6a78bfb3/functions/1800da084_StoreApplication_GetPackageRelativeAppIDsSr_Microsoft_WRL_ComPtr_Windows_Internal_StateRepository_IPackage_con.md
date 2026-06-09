# StoreApplication::GetPackageRelativeAppIDsSr(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &,std::vector<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &)

- ea: `0x1800da084`
- end: `0x1800da409`
- name: `?GetPackageRelativeAppIDsSr@StoreApplication@@SAXAEBV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@AEAV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z`
- size: `901`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800dd87c`

## callees

- `0x180005890`
- `0x18000a2d4`
- `0x18000faf0`
- `0x18001082c`
- `0x18001c5f0`
- `0x1800252b0`
- `0x1800c30d4`
- `0x1800c97f0`
- `0x1800cea08`
- `0x1800d8684`
- `0x1800d904c`
- `0x1800da084`
- `0x1800e02ec`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800da2ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800da30d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800da2ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800da30d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800da0fe`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800da0fe`

## string_xrefs

- `0x1800da113`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800da169`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800da1a7`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800da1f4`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800da24f`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800da2bb`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall StoreApplication::GetPackageRelativeAppIDsSr(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rbx
  int ActivationFactory; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, __int64 *); // rbx
  int v8; // eax
  int v9; // eax
  unsigned int i; // esi
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  int v17; // eax
  PCWSTR StringRawBuffer; // rdx
  PCWSTR v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 result; // rax
  signed int LastError; // eax
  unsigned int v25; // edx
  const char *v26; // rcx
  int v27; // [rsp+20h] [rbp-128h]
  __int64 v28; // [rsp+30h] [rbp-118h] BYREF
  HSTRING string; // [rsp+38h] [rbp-110h] BYREF
  unsigned int v30; // [rsp+40h] [rbp-108h] BYREF
  HSTRING v31; // [rsp+48h] [rbp-100h] BYREF
  __int64 v32; // [rsp+50h] [rbp-F8h] BYREF
  __int64 v33; // [rsp+58h] [rbp-F0h] BYREF
  void **v34; // [rsp+60h] [rbp-E8h] BYREF
  const char *v35; // [rsp+68h] [rbp-E0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-D0h] BYREF
  __int64 v37; // [rsp+90h] [rbp-B8h]
  _BYTE v38[32]; // [rsp+98h] [rbp-B0h] BYREF
  _BYTE v39[40]; // [rsp+B8h] [rbp-90h] BYREF
  _BYTE v40[64]; // [rsp+E0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v33 = 0;
  v37 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.Application",
    0x2Du,
    0x2Cu);
  v4 = v37;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v33);
  try
  {
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x453,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v27);
    v32 = 0;
    v6 = v33;
    v7 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v33 + 144LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    v8 = v7(v6, *a1, &v32);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x456,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v8,
        v27);
    v30 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v32 + 56LL))(v32, &v30);
    if ( v9 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x459,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
        (const char *)(unsigned int)v9,
        v27);
    for ( i = 0; i < v30; ++i )
    {
      v28 = 0;
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v32 + 48LL))(v32, i, &v28);
      if ( v11 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x45F,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
          (const char *)(unsigned int)v11,
          v27);
      string = 0;
      v12 = v28;
      v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v28 + 224LL);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
        &string,
        0);
      v14 = v13(v12, &string);
      if ( v14 >= 0 )
      {
        v31 = 0;
        v15 = v28;
        v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v28 + 392LL);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
          &v31,
          0);
        v17 = v16(v15, &v31);
        if ( v17 >= 0 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          std::wstring::wstring(v38, StringRawBuffer);
          v19 = WindowsGetStringRawBuffer(v31, 0);
          std::wstring::wstring(&hstringHeader, v19);
          v20 = Utility::ToLower(v39, &hstringHeader);
          v21 = std::make_pair<std::wstring &,std::wstring>(v40, v38, v20);
          std::vector<std::pair<std::wstring,std::wstring>>::push_back(a2, v21);
          std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(v40);
          std::wstring::_Tidy_deallocate(v39);
          std::wstring::_Tidy_deallocate(&hstringHeader);
          std::wstring::_Tidy_deallocate(v38);
          Windows::Internal::String::~String((Windows::Internal::String *)&v31);
          Windows::Internal::String::~String((Windows::Internal::String *)&string);
        }
        else
        {
          if ( v17 != -2147024809 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x472,
              (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
              (const char *)(unsigned int)v17,
              v27);
          Windows::Internal::String::~String((Windows::Internal::String *)&v31);
          Windows::Internal::String::~String((Windows::Internal::String *)&string);
        }
      }
      else
      {
        if ( v14 != -2147024809 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x465,
            (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
            (const char *)(unsigned int)v14,
            v27);
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
      }
      v22 = v28;
      if ( v28 )
      {
        v28 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    result = Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  }
  catch ( std::exception v34 )
  {
    LastError = GetLastError();
    v25 = LastError;
    if ( LastError > 0 )
      v25 = (unsigned __int16)LastError | 0x80070000;
    v26 = "Unknown exception";
    if ( v35 )
      v26 = v35;
    AslLogCallPrintf(1, "StoreApplication::GetPackageRelativeAppIDsSr", 1156, "Exception: 0x%08x %s", v25, v26);
    v34 = &std::exception::`vftable';
    return o___std_exception_destroy_0(&v35);
  }
  catch ( ... )
  {
    return AslLogCallPrintf(1, "StoreApplication::GetPackageRelativeAppIDsSr", 1161, "Exception: [0x%08x]", -2147024322);
  }
  return result;
}

```

## disassembly

```asm
0x1800da084  mov     [rsp+arg_10], rbx
0x1800da089  push    rsi
0x1800da08a  push    rdi
0x1800da08b  push    r14
0x1800da08d  sub     rsp, 130h
0x1800da094  mov     rax, cs:__security_cookie
0x1800da09b  xor     rax, rsp
0x1800da09e  mov     [rsp+148h+var_28], rax
0x1800da0a6  mov     r14, rdx
0x1800da0a9  mov     rsi, rcx
0x1800da0ac  mov     [rsp+148h+var_F0], 0
0x1800da0b5  mov     [rsp+148h+var_B8], 0
0x1800da0c1  mov     r9d, 2Ch ; ','; unsigned int
0x1800da0c7  lea     r8d, [r9+1]; unsigned int
0x1800da0cb  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x1800da0d2  lea     rcx, [rsp+148h+hstringHeader]; hstringHeader
0x1800da0d7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800da0dc  nop
0x1800da0dd  mov     rbx, [rsp+148h+var_B8]
0x1800da0e5  lea     rcx, [rsp+148h+var_F0]
0x1800da0ea  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800da0ef  lea     r8, [rsp+148h+var_F0]
0x1800da0f4  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x1800da0fb  mov     rcx, rbx
0x1800da0fe  call    cs:__imp_RoGetActivationFactory
0x1800da104  mov     rcx, [rsp+148h]; this
0x1800da10c  test    eax, eax
0x1800da10e  jns     short loc_1800DA125
0x1800da110  mov     r9d, eax; char *
0x1800da113  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800da11a  mov     edx, 453h; void *
0x1800da11f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800da125  mov     [rsp+148h+var_F8], 0
0x1800da12e  mov     rdi, [rsp+148h+var_F0]
0x1800da133  mov     rax, [rdi]
0x1800da136  mov     rbx, [rax+90h]
0x1800da13d  lea     rcx, [rsp+148h+var_F8]
0x1800da142  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800da147  lea     r8, [rsp+148h+var_F8]
0x1800da14c  mov     rdx, [rsi]
0x1800da14f  mov     rcx, rdi
0x1800da152  mov     rax, rbx
0x1800da155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da15a  mov     rcx, [rsp+148h]; this
0x1800da162  test    eax, eax
0x1800da164  jns     short loc_1800DA17A
0x1800da166  mov     r9d, eax; char *
0x1800da169  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800da170  mov     edx, 456h; void *
0x1800da175  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800da17a  mov     [rsp+148h+var_108], 0
0x1800da182  mov     rcx, [rsp+148h+var_F8]
0x1800da187  mov     rax, [rcx]
0x1800da18a  lea     rdx, [rsp+148h+var_108]
0x1800da18f  mov     rax, [rax+38h]
0x1800da193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da198  mov     rcx, [rsp+148h]; this
0x1800da1a0  test    eax, eax
0x1800da1a2  jns     short loc_1800DA1B8
0x1800da1a4  mov     r9d, eax; char *
0x1800da1a7  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800da1ae  mov     edx, 459h; void *
0x1800da1b3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800da1b8  xor     esi, esi
0x1800da1ba  cmp     esi, [rsp+148h+var_108]
0x1800da1be  jnb     loc_1800DA3CB
0x1800da1c4  mov     [rsp+148h+var_118], 0
0x1800da1cd  mov     rcx, [rsp+148h+var_F8]
0x1800da1d2  mov     rax, [rcx]
0x1800da1d5  lea     r8, [rsp+148h+var_118]
0x1800da1da  mov     edx, esi
0x1800da1dc  mov     rax, [rax+30h]
0x1800da1e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da1e5  mov     rcx, [rsp+148h]; this
0x1800da1ed  test    eax, eax
0x1800da1ef  jns     short loc_1800DA205
0x1800da1f1  mov     r9d, eax; char *
0x1800da1f4  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800da1fb  mov     edx, 45Fh; void *
0x1800da200  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800da205  mov     [rsp+148h+string], 0
0x1800da20e  mov     rdi, [rsp+148h+var_118]
0x1800da213  mov     rax, [rdi]
0x1800da216  mov     rbx, [rax+0E0h]
0x1800da21d  xor     edx, edx
0x1800da21f  lea     rcx, [rsp+148h+string]
0x1800da224  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800da229  lea     rdx, [rsp+148h+string]
0x1800da22e  mov     rcx, rdi
0x1800da231  mov     rax, rbx
0x1800da234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da239  test    eax, eax
0x1800da23b  jns     short loc_1800DA271
0x1800da23d  cmp     eax, 80070057h
0x1800da242  jz      short loc_1800DA261
0x1800da244  mov     rcx, [rsp+148h]; this
0x1800da24c  mov     r9d, eax; char *
0x1800da24f  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800da256  mov     edx, 465h; void *
0x1800da25b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800da261  lea     rcx, [rsp+148h+string]; this
0x1800da266  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800da26b  nop
0x1800da26c  jmp     loc_1800DA3A4
0x1800da271  mov     [rsp+148h+var_100], 0
0x1800da27a  mov     rdi, [rsp+148h+var_118]
0x1800da27f  mov     rax, [rdi]
0x1800da282  mov     rbx, [rax+188h]
0x1800da289  xor     edx, edx
0x1800da28b  lea     rcx, [rsp+148h+var_100]
0x1800da290  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800da295  lea     rdx, [rsp+148h+var_100]
0x1800da29a  mov     rcx, rdi
0x1800da29d  mov     rax, rbx
0x1800da2a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da2a5  test    eax, eax
0x1800da2a7  jns     short loc_1800DA2E8
0x1800da2a9  cmp     eax, 80070057h
0x1800da2ae  jz      short loc_1800DA2CD
0x1800da2b0  mov     rcx, [rsp+148h]; this
0x1800da2b8  mov     r9d, eax; char *
0x1800da2bb  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800da2c2  mov     edx, 472h; void *
0x1800da2c7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800da2cd  lea     rcx, [rsp+148h+var_100]; this
0x1800da2d2  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800da2d7  nop
0x1800da2d8  lea     rcx, [rsp+148h+string]; this
0x1800da2dd  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800da2e2  nop
0x1800da2e3  jmp     loc_1800DA3A4
0x1800da2e8  xor     edx, edx; length
0x1800da2ea  mov     rcx, [rsp+148h+string]; string
0x1800da2ef  call    cs:__imp_WindowsGetStringRawBuffer
0x1800da2f5  mov     rdx, rax
0x1800da2f8  lea     rcx, [rsp+148h+var_B0]
0x1800da300  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800da305  nop
0x1800da306  xor     edx, edx; length
0x1800da308  mov     rcx, [rsp+148h+var_100]; string
0x1800da30d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800da313  mov     rdx, rax
0x1800da316  lea     rcx, [rsp+148h+hstringHeader]
0x1800da31b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800da320  nop
0x1800da321  lea     rdx, [rsp+148h+hstringHeader]
0x1800da326  lea     rcx, [rsp+148h+var_90]
0x1800da32e  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800da333  nop
0x1800da334  mov     r8, rax
0x1800da337  lea     rdx, [rsp+148h+var_B0]
0x1800da33f  lea     rcx, [rsp+148h+var_68]
0x1800da347  call    ??$make_pair@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@YA?AU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@0@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV20@@Z; std::make_pair<std::wstring &,std::wstring>(std::wstring &,std::wstring &&)
0x1800da34c  nop
0x1800da34d  mov     rdx, rax
0x1800da350  mov     rcx, r14
0x1800da353  call    ?push_back@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAX$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@2@@Z; std::vector<std::pair<std::wstring,std::wstring>>::push_back(std::pair<std::wstring,std::wstring> &&)
0x1800da358  nop
0x1800da359  lea     rcx, [rsp+148h+var_68]
0x1800da361  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(void)
0x1800da366  nop
0x1800da367  lea     rcx, [rsp+148h+var_90]
0x1800da36f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800da374  nop
0x1800da375  lea     rcx, [rsp+148h+hstringHeader]
0x1800da37a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800da37f  nop
0x1800da380  lea     rcx, [rsp+148h+var_B0]
0x1800da388  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800da38d  nop
0x1800da38e  lea     rcx, [rsp+148h+var_100]; this
0x1800da393  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800da398  nop
0x1800da399  lea     rcx, [rsp+148h+string]; this
0x1800da39e  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800da3a3  nop
0x1800da3a4  mov     rcx, [rsp+148h+var_118]
0x1800da3a9  test    rcx, rcx
0x1800da3ac  jz      short loc_1800DA3C4
0x1800da3ae  mov     [rsp+148h+var_118], 0
0x1800da3b7  mov     rax, [rcx]
0x1800da3ba  mov     rax, [rax+10h]
0x1800da3be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da3c3  nop
0x1800da3c4  inc     esi
0x1800da3c6  jmp     loc_1800DA1BA
0x1800da3cb  lea     rcx, [rsp+148h+var_F8]
0x1800da3d0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800da3d5  nop
0x1800da3d6  lea     rcx, [rsp+148h+var_F0]
0x1800da3db  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800da3e0  nop
0x1800da3e1  jmp     short loc_1800DA3E5
0x1800da3e3  jmp     short $+2
0x1800da3e5  mov     rcx, [rsp+148h+var_28]
0x1800da3ed  xor     rcx, rsp; StackCookie
0x1800da3f0  call    __security_check_cookie
0x1800da3f5  mov     rbx, [rsp+148h+arg_10]
0x1800da3fd  add     rsp, 130h
0x1800da404  pop     r14
0x1800da406  pop     rdi
0x1800da407  pop     rsi
0x1800da408  retn
```
