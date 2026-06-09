# AttributeFetcher::GetCallingProcessName(ushort * *)

- ea: `0x18003d678`
- end: `0x18003d9a3`
- name: `?GetCallingProcessName@AttributeFetcher@@CAJPEAPEAG@Z`
- size: `811`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003ffe8`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc6c`
- `0x18000cc8c`
- `0x18001146c`
- `0x18001c6f4`
- `0x18001ec78`
- `0x18003d678`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18003d8bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18003d8bd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18003d8fa`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18003d8fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d7c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d808`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d896`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d7c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d808`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d896`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d82b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d82b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003d6ed`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003d6ed`

## string_xrefs

- `0x18003d703`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`
- `0x18003d787`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`
- `0x18003d7f1`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`
- `0x18003d852`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`
- `0x18003d8ce`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`
- `0x18003d921`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributefetcher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall AttributeFetcher::GetCallingProcessName(unsigned __int16 **a1)
{
  __int64 v2; // rbx
  int ActivationFactory; // eax
  unsigned int LastError; // ebx
  __int64 v5; // rdi
  int (__fastcall *v6)(__int64, int *); // rbx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HSTRING *); // rbx
  int v12; // eax
  PCWSTR StringRawBuffer; // rax
  int v14; // eax
  unsigned __int16 *v15; // rax
  const char *v16; // r9
  LPWSTR FileNameW; // rax
  int v18; // eax
  unsigned __int16 *Reserved1; // rax
  int v21[2]; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING string; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+58h] [rbp-A8h]
  WCHAR Filename[520]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+498h] [rbp+398h]

  v24 = 0;
  v26 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.ApplicationModel.Package",
    0x21u,
    0x20u);
  v2 = v26;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
  ActivationFactory = RoGetActivationFactory(v2, &GUID_4e534bdf_2960_4878_97a4_9624deb72f2d, &v24);
  LastError = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    *(_QWORD *)v21 = 0;
    v5 = v24;
    v6 = *(int (__fastcall **)(__int64, int *))(*(_QWORD *)v24 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v21);
    if ( v6(v5, v21) < 0 )
    {
      if ( !GetModuleFileNameW(0, Filename, 0x208u) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x395,
                      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
                      v16);
        goto LABEL_7;
      }
      memset(&hstringHeader, 0, sizeof(hstringHeader));
      FileNameW = PathFindFileNameW(Filename);
      v18 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              &hstringHeader,
              FileNameW,
              -1);
      LastError = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x399,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
          (const char *)(unsigned int)v18,
          v21[0]);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
        goto LABEL_7;
      }
      Reserved1 = (unsigned __int16 *)hstringHeader.Reserved.Reserved1;
      memset(&hstringHeader, 0, sizeof(hstringHeader));
      *a1 = Reserved1;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
    }
    else
    {
      v23 = 0;
      v7 = *(_QWORD *)v21;
      v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(**(_QWORD **)v21 + 48LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
      v9 = v8(v7, &v23);
      LastError = v9;
      if ( v9 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x384,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
          (const char *)(unsigned int)v9,
          v21[0]);
LABEL_6:
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
LABEL_7:
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v21);
        goto LABEL_20;
      }
      string = 0;
      v10 = v23;
      v11 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v23 + 104LL);
      WindowsDeleteString(0);
      string = 0;
      v12 = v11(v10, &string);
      LastError = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x388,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
          (const char *)(unsigned int)v12,
          v21[0]);
LABEL_10:
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_6;
      }
      memset(&hstringHeader, 0, sizeof(hstringHeader));
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v14 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
              &hstringHeader,
              StringRawBuffer,
              -1);
      LastError = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x38C,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
          (const char *)(unsigned int)v14,
          v21[0]);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
        goto LABEL_10;
      }
      v15 = (unsigned __int16 *)hstringHeader.Reserved.Reserved1;
      memset(&hstringHeader, 0, sizeof(hstringHeader));
      *a1 = v15;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v21);
    LastError = 0;
    goto LABEL_20;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x37B,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributefetcher.cpp",
    (const char *)(unsigned int)ActivationFactory,
    v21[0]);
LABEL_20:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
  return LastError;
}

```

## disassembly

```asm
0x18003d678  mov     [rsp-8+arg_8], rbx
0x18003d67d  mov     [rsp-8+arg_10], rsi
0x18003d682  push    rbp
0x18003d683  push    rdi
0x18003d684  push    r14
0x18003d686  lea     rbp, [rsp-380h]
0x18003d68e  sub     rsp, 480h
0x18003d695  mov     rax, cs:__security_cookie
0x18003d69c  xor     rax, rsp
0x18003d69f  mov     [rbp+390h+var_20], rax
0x18003d6a6  mov     rsi, rcx
0x18003d6a9  xor     r14d, r14d
0x18003d6ac  mov     [rsp+490h+var_458], r14
0x18003d6b1  mov     [rsp+490h+var_438], r14
0x18003d6b6  lea     r9d, [r14+20h]; unsigned int
0x18003d6ba  lea     r8d, [r14+21h]; unsigned int
0x18003d6be  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Package@@3QBGB; "Windows.ApplicationModel.Package"
0x18003d6c5  lea     rcx, [rsp+490h+hstringHeader]; hstringHeader
0x18003d6ca  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003d6cf  mov     rbx, [rsp+490h+var_438]
0x18003d6d4  lea     rcx, [rsp+490h+var_458]
0x18003d6d9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003d6de  lea     r8, [rsp+490h+var_458]
0x18003d6e3  lea     rdx, _GUID_4e534bdf_2960_4878_97a4_9624deb72f2d
0x18003d6ea  mov     rcx, rbx
0x18003d6ed  call    cs:__imp_RoGetActivationFactory
0x18003d6f3  mov     ebx, eax
0x18003d6f5  test    eax, eax
0x18003d6f7  jns     short loc_18003D719
0x18003d6f9  mov     rcx, [rbp+398h]; this
0x18003d700  mov     r9d, eax; char *
0x18003d703  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x18003d70a  mov     edx, 37Bh; void *
0x18003d70f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d714  jmp     loc_18003D970
0x18003d719  mov     qword ptr [rsp+490h+var_470], r14; int
0x18003d71e  mov     rdi, [rsp+490h+var_458]
0x18003d723  mov     rax, [rdi]
0x18003d726  mov     rbx, [rax+30h]
0x18003d72a  lea     rcx, [rsp+490h+var_470]
0x18003d72f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003d734  lea     rdx, [rsp+490h+var_470]
0x18003d739  mov     rcx, rdi
0x18003d73c  mov     rax, rbx
0x18003d73f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d744  test    eax, eax
0x18003d746  js      loc_18003D8B0
0x18003d74c  mov     [rsp+490h+var_460], r14
0x18003d751  mov     rdi, qword ptr [rsp+490h+var_470]
0x18003d756  mov     rax, [rdi]
0x18003d759  mov     rbx, [rax+30h]
0x18003d75d  lea     rcx, [rsp+490h+var_460]
0x18003d762  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003d767  lea     rdx, [rsp+490h+var_460]
0x18003d76c  mov     rcx, rdi
0x18003d76f  mov     rax, rbx
0x18003d772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d777  mov     ebx, eax
0x18003d779  test    eax, eax
0x18003d77b  jns     short loc_18003D7B3
0x18003d77d  mov     rcx, [rbp+398h]; this
0x18003d784  mov     r9d, eax; char *
0x18003d787  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x18003d78e  mov     edx, 384h; void *
0x18003d793  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d798  nop
0x18003d799  lea     rcx, [rsp+490h+var_460]
0x18003d79e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003d7a3  nop
0x18003d7a4  lea     rcx, [rsp+490h+var_470]
0x18003d7a9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003d7ae  jmp     loc_18003D970
0x18003d7b3  mov     [rsp+490h+string], r14
0x18003d7b8  mov     rdi, [rsp+490h+var_460]
0x18003d7bd  mov     rax, [rdi]
0x18003d7c0  mov     rbx, [rax+68h]
0x18003d7c4  xor     ecx, ecx; string
0x18003d7c6  call    cs:__imp_WindowsDeleteString
0x18003d7cc  mov     [rsp+490h+string], r14
0x18003d7d1  lea     rdx, [rsp+490h+string]
0x18003d7d6  mov     rcx, rdi
0x18003d7d9  mov     rax, rbx
0x18003d7dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7e1  mov     ebx, eax
0x18003d7e3  test    eax, eax
0x18003d7e5  jns     short loc_18003D815
0x18003d7e7  mov     rcx, [rbp+398h]; this
0x18003d7ee  mov     r9d, eax; char *
0x18003d7f1  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x18003d7f8  mov     edx, 388h; void *
0x18003d7fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d802  nop
0x18003d803  mov     rcx, [rsp+490h+string]; string
0x18003d808  call    cs:__imp_WindowsDeleteString
0x18003d80e  mov     [rsp+490h+string], r14
0x18003d813  jmp     short loc_18003D799
0x18003d815  mov     qword ptr [rsp+490h+hstringHeader.Reserved], r14
0x18003d81a  mov     qword ptr [rsp+490h+hstringHeader.Reserved+8], r14
0x18003d81f  mov     qword ptr [rsp+490h+hstringHeader.Reserved+10h], r14
0x18003d824  xor     edx, edx; length
0x18003d826  mov     rcx, [rsp+490h+string]; string
0x18003d82b  call    cs:__imp_WindowsGetStringRawBuffer
0x18003d831  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003d835  mov     rdx, rax
0x18003d838  lea     rcx, [rsp+490h+hstringHeader]
0x18003d83d  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18003d842  mov     ebx, eax
0x18003d844  test    eax, eax
0x18003d846  jns     short loc_18003D86F
0x18003d848  mov     rcx, [rbp+398h]; this
0x18003d84f  mov     r9d, eax; char *
0x18003d852  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x18003d859  mov     edx, 38Ch; void *
0x18003d85e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d863  lea     rcx, [rsp+490h+hstringHeader]
0x18003d868  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003d86d  jmp     short loc_18003D803
0x18003d86f  mov     rax, qword ptr [rsp+490h+hstringHeader.Reserved]
0x18003d874  mov     qword ptr [rsp+490h+hstringHeader.Reserved], r14
0x18003d879  mov     qword ptr [rsp+490h+hstringHeader.Reserved+10h], r14
0x18003d87e  mov     qword ptr [rsp+490h+hstringHeader.Reserved+8], r14
0x18003d883  mov     [rsi], rax
0x18003d886  lea     rcx, [rsp+490h+hstringHeader]
0x18003d88b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003d890  nop
0x18003d891  mov     rcx, [rsp+490h+string]; string
0x18003d896  call    cs:__imp_WindowsDeleteString
0x18003d89c  mov     [rsp+490h+string], r14
0x18003d8a1  lea     rcx, [rsp+490h+var_460]
0x18003d8a6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003d8ab  jmp     loc_18003D963
0x18003d8b0  mov     r8d, 208h; nSize
0x18003d8b6  lea     rdx, [rsp+490h+Filename]; lpFilename
0x18003d8bb  xor     ecx, ecx; hModule
0x18003d8bd  call    cs:__imp_GetModuleFileNameW
0x18003d8c3  test    eax, eax
0x18003d8c5  jnz     short loc_18003D8E6
0x18003d8c7  mov     rcx, [rbp+398h]; this
0x18003d8ce  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x18003d8d5  mov     edx, 395h; void *
0x18003d8da  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003d8df  mov     ebx, eax
0x18003d8e1  jmp     loc_18003D7A4
0x18003d8e6  mov     qword ptr [rsp+490h+hstringHeader.Reserved], r14
0x18003d8eb  mov     qword ptr [rsp+490h+hstringHeader.Reserved+8], r14
0x18003d8f0  mov     qword ptr [rsp+490h+hstringHeader.Reserved+10h], r14
0x18003d8f5  lea     rcx, [rsp+490h+Filename]; pszPath
0x18003d8fa  call    cs:__imp_PathFindFileNameW
0x18003d900  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003d904  mov     rdx, rax
0x18003d907  lea     rcx, [rsp+490h+hstringHeader]
0x18003d90c  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18003d911  mov     ebx, eax
0x18003d913  test    eax, eax
0x18003d915  jns     short loc_18003D941
0x18003d917  mov     rcx, [rbp+398h]; this
0x18003d91e  mov     r9d, eax; char *
0x18003d921  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\flightsetting"...
0x18003d928  mov     edx, 399h; void *
0x18003d92d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d932  lea     rcx, [rsp+490h+hstringHeader]
0x18003d937  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003d93c  jmp     loc_18003D7A4
0x18003d941  mov     rax, qword ptr [rsp+490h+hstringHeader.Reserved]
0x18003d946  mov     qword ptr [rsp+490h+hstringHeader.Reserved], r14
0x18003d94b  mov     qword ptr [rsp+490h+hstringHeader.Reserved+10h], r14
0x18003d950  mov     qword ptr [rsp+490h+hstringHeader.Reserved+8], r14
0x18003d955  mov     [rsi], rax
0x18003d958  lea     rcx, [rsp+490h+hstringHeader]
0x18003d95d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003d962  nop
0x18003d963  lea     rcx, [rsp+490h+var_470]
0x18003d968  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003d96d  mov     ebx, r14d
0x18003d970  lea     rcx, [rsp+490h+var_458]
0x18003d975  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003d97a  mov     eax, ebx
0x18003d97c  mov     rcx, [rbp+390h+var_20]
0x18003d983  xor     rcx, rsp; StackCookie
0x18003d986  call    __security_check_cookie
0x18003d98b  lea     r11, [rsp+490h+var_10]
0x18003d993  mov     rbx, [r11+28h]
0x18003d997  mov     rsi, [r11+30h]
0x18003d99b  mov     rsp, r11
0x18003d99e  pop     r14
0x18003d9a0  pop     rdi
0x18003d9a1  pop     rbp
0x18003d9a2  retn
```
