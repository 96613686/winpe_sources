# Windows::Internal::ApplicationModel::Sync::AddOperation::s_IsCountrySupportedForYahoo(bool *)

- ea: `0x18005f0ac`
- end: `0x18005f20c`
- name: `?s_IsCountrySupportedForYahoo@AddOperation@Sync@ApplicationModel@Internal@Windows@@CAJPEA_N@Z`
- size: `352`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18005ccfc`

## callees

- `0x180006eac`
- `0x180011ffc`
- `0x180054e14`
- `0x18005f0ac`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005f101`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005f101`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f14c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f18c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f1dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f14c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f18c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005f1dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005f19a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005f19a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005f0e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005f0e8`
- `msvcrt!_wcsicmp` at `0x18005f1c6`
- `msvcrt!_wcsicmp` at `0x18005f1c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::ApplicationModel::Sync::AddOperation::s_IsCountrySupportedForYahoo(bool *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, HSTRING *); // rbx
  int v6; // eax
  const wchar_t *StringRawBuffer; // rdi
  int i; // ebx
  bool v9; // cl
  HSTRING v11; // [rsp+20h] [rbp-48h] BYREF
  __int64 v12; // [rsp+28h] [rbp-40h] BYREF
  wchar_t *String2; // [rsp+30h] [rbp-38h]
  HSTRING string; // [rsp+38h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  *a1 = 0;
  v12 = 0;
  if ( WindowsCreateStringReference(L"Windows.Globalization.GeographicRegion", 0x26u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v2 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Globalization::IGeographicRegion>>(
         string,
         &v12);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v11 = 0;
    v4 = v12;
    v5 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v12 + 72LL);
    WindowsDeleteString(0);
    v11 = 0;
    v6 = v5(v4, &v11);
    v3 = v6;
    if ( v6 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(v11, 0);
      String2 = L"392";
      for ( i = 0; ; i = 1 )
      {
        v9 = 1;
        if ( i )
          break;
        if ( !_wcsicmp(StringRawBuffer, String2) )
        {
          v9 = 0;
          break;
        }
      }
      *a1 = v9;
      WindowsDeleteString(v11);
      v3 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C9,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
        (const char *)(unsigned int)v6,
        (int)v11);
      WindowsDeleteString(v11);
    }
    v11 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C6,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\mailcontactscalendarsyncuiapilib\\addoperation.cpp",
      (const char *)(unsigned int)v2,
      (int)v11);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
  return v3;
}

```

## disassembly

```asm
0x18005f0ac  push    rbp
0x18005f0ae  push    rbx
0x18005f0af  push    rsi
0x18005f0b0  push    rdi
0x18005f0b1  mov     rbp, rsp
0x18005f0b4  sub     rsp, 68h
0x18005f0b8  mov     rax, cs:__security_cookie
0x18005f0bf  xor     rax, rsp
0x18005f0c2  mov     [rbp+var_10], rax
0x18005f0c6  mov     rsi, rcx
0x18005f0c9  mov     byte ptr [rcx], 0
0x18005f0cc  mov     [rbp+var_40], 0
0x18005f0d4  lea     r9, [rbp+string]; string
0x18005f0d8  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18005f0dc  mov     edx, 26h ; '&'; length
0x18005f0e1  lea     rcx, ?RuntimeClass_Windows_Globalization_GeographicRegion@@3QBGB; "Windows.Globalization.GeographicRegion"
0x18005f0e8  call    cs:__imp_WindowsCreateStringReference
0x18005f0ee  test    eax, eax
0x18005f0f0  jns     short loc_18005F107
0x18005f0f2  xor     r9d, r9d; lpArguments
0x18005f0f5  xor     r8d, r8d; nNumberOfArguments
0x18005f0f8  lea     edx, [r9+1]; dwExceptionFlags
0x18005f0fc  mov     ecx, 0C000000Dh; dwExceptionCode
0x18005f101  call    cs:__imp_RaiseException
0x18005f107  lea     rdx, [rbp+var_40]
0x18005f10b  mov     rcx, [rbp+string]
0x18005f10f  call    ??$ActivateInstance@V?$ComPtr@UIGeographicRegion@Globalization@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIGeographicRegion@Globalization@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Globalization::IGeographicRegion>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Globalization::IGeographicRegion>>)
0x18005f114  mov     ebx, eax
0x18005f116  test    eax, eax
0x18005f118  jns     short loc_18005F137
0x18005f11a  mov     rcx, [rbp+20h]; this
0x18005f11e  mov     r9d, eax; char *
0x18005f121  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005f128  mov     edx, 2C6h; void *
0x18005f12d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f132  jmp     loc_18005F1EC
0x18005f137  mov     [rbp+var_48], 0
0x18005f13f  mov     rdi, [rbp+var_40]
0x18005f143  mov     rax, [rdi]
0x18005f146  mov     rbx, [rax+48h]
0x18005f14a  xor     ecx, ecx; string
0x18005f14c  call    cs:__imp_WindowsDeleteString
0x18005f152  mov     [rbp+var_48], 0
0x18005f15a  lea     rdx, [rbp+var_48]
0x18005f15e  mov     rcx, rdi
0x18005f161  mov     rax, rbx
0x18005f164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f169  mov     ebx, eax
0x18005f16b  test    eax, eax
0x18005f16d  jns     short loc_18005F194
0x18005f16f  mov     rcx, [rbp+20h]; this
0x18005f173  mov     r9d, eax; char *
0x18005f176  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\accountscontrol\\api"...
0x18005f17d  mov     edx, 2C9h; void *
0x18005f182  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f187  nop
0x18005f188  mov     rcx, [rbp+var_48]; string
0x18005f18c  call    cs:__imp_WindowsDeleteString
0x18005f192  jmp     short loc_18005F1E4
0x18005f194  xor     edx, edx; length
0x18005f196  mov     rcx, [rbp+var_48]; string
0x18005f19a  call    cs:__imp_WindowsGetStringRawBuffer
0x18005f1a0  mov     rdi, rax
0x18005f1a3  lea     rax, a392; "392"
0x18005f1aa  mov     [rbp+String2], rax
0x18005f1ae  xor     ebx, ebx
0x18005f1b0  mov     cl, 1
0x18005f1b2  cmp     ebx, 1
0x18005f1b5  jnb     short loc_18005F1D6
0x18005f1b7  test    cl, cl
0x18005f1b9  jz      short loc_18005F1D4
0x18005f1bb  movsxd  rdx, ebx
0x18005f1be  mov     rdx, [rbp+rdx*8+String2]; String2
0x18005f1c3  mov     rcx, rdi; String1
0x18005f1c6  call    cs:__imp__wcsicmp
0x18005f1cc  test    eax, eax
0x18005f1ce  jz      short loc_18005F1D4
0x18005f1d0  inc     ebx
0x18005f1d2  jmp     short loc_18005F1B0
0x18005f1d4  xor     cl, cl
0x18005f1d6  mov     [rsi], cl
0x18005f1d8  mov     rcx, [rbp+var_48]; string
0x18005f1dc  call    cs:__imp_WindowsDeleteString
0x18005f1e2  xor     ebx, ebx
0x18005f1e4  mov     [rbp+var_48], 0
0x18005f1ec  lea     rcx, [rbp+var_40]
0x18005f1f0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005f1f5  mov     eax, ebx
0x18005f1f7  mov     rcx, [rbp+var_10]
0x18005f1fb  xor     rcx, rsp; StackCookie
0x18005f1fe  call    __security_check_cookie
0x18005f203  add     rsp, 68h
0x18005f207  pop     rdi
0x18005f208  pop     rsi
0x18005f209  pop     rbx
0x18005f20a  pop     rbp
0x18005f20b  retn
```
