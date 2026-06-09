# DynamicProviderTemplate<WmiProvider>::GetAttributeObject(ushort const *,WmiProvider * *)

- ea: `0x18004939c`
- end: `0x1800495e2`
- name: `?GetAttributeObject@?$DynamicProviderTemplate@VWmiProvider@@@@QEAAJPEBGPEAPEAVWmiProvider@@@Z`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180049d30`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x1800168c8`
- `0x18001b2ec`
- `0x18001c6f4`
- `0x18001ec48`
- `0x18001ec78`
- `0x1800477b0`
- `0x18004939c`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004941b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800494d8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004941b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800494d8`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180049491`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180049491`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004942f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800494ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004942f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800494ec`

## string_xrefs

- `0x180049516`: `onecore\base\flighting\flightsettings\broker\libs\ctac\DynamicProviderTemplate.h`
- `0x18004957b`: `onecore\base\flighting\flightsettings\broker\libs\ctac\DynamicProviderTemplate.h`

## pseudocode

```c
__int64 __fastcall DynamicProviderTemplate<WmiProvider>::GetAttributeObject(__int64 a1, const WCHAR *a2, _QWORD *a3)
{
  __int64 v6; // rbx
  int (__fastcall *v7)(__int64, HSTRING, __int64 *); // r15
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rcx
  int v10; // eax
  int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rdx
  const WCHAR *v14; // rbx
  __int64 v15; // r14
  int (__fastcall *v16)(__int64, HSTRING, __int64 *); // r15
  __int64 v17; // rax
  int v19; // [rsp+20h] [rbp-49h]
  UINT32 length[2]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v21; // [rsp+38h] [rbp-31h] BYREF
  __int64 v22; // [rsp+40h] [rbp-29h] BYREF
  HSTRING string; // [rsp+48h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-19h] BYREF
  HSTRING v25; // [rsp+68h] [rbp-1h] BYREF
  HSTRING_HEADER v26; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v22 = 0;
  v6 = *(_QWORD *)(a1 + 16);
  v7 = *(int (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v6 + 64LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
  length[0] = 0;
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  if ( (int)ULongLongToUInt(v9, length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(a2, length[0], &hstringHeader, &string);
  if ( v7(v6, string, &v22) < 0 )
  {
    string = 0;
    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = 0u;
    v10 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
            &string,
            a2,
            -1);
    v11 = v10;
    if ( v10 < 0 )
    {
      v12 = (unsigned int)v10;
      v13 = 55;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\DynamicProviderTemplate.h",
        (const char *)v12,
        v19);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
      goto LABEL_19;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&string);
    v14 = (const WCHAR *)string;
    CharLowerBuffW((LPWSTR)string, (DWORD)hstringHeader.Reserved.Reserved1);
    v15 = *(_QWORD *)(a1 + 16);
    v16 = *(int (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v15 + 64LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
    length[0] = 0;
    do
      ++v8;
    while ( v14[v8] );
    if ( (int)ULongLongToUInt(v8, length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(v14, length[0], &v26, &v25);
    if ( v16(v15, v25, &v22) < 0 )
    {
      v11 = -2147217118;
      v12 = 2147750178LL;
      v13 = 62;
      goto LABEL_14;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&string);
  }
  v21 = 0;
  *(_QWORD *)length = v22;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v21);
  v11 = Microsoft::WRL::Details::MakeAndInitialize<WmiProvider,WmiProvider,Windows::Data::Json::IJsonObject *>(
          &v21,
          length);
  if ( v11 >= 0 )
  {
    v17 = v21;
    v21 = 0;
    *a3 = v17;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v21);
    v11 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x44,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\DynamicProviderTemplate.h",
      (const char *)(unsigned int)v11,
      (int)"propName=%ws",
      (const char *)a2);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v21);
  }
LABEL_19:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18004939c  mov     [rsp-8+arg_18], rbx
0x1800493a1  push    rbp
0x1800493a2  push    rsi
0x1800493a3  push    rdi
0x1800493a4  push    r12
0x1800493a6  push    r13
0x1800493a8  push    r14
0x1800493aa  push    r15
0x1800493ac  lea     rbp, [rsp-27h]
0x1800493b1  sub     rsp, 90h
0x1800493b8  mov     rax, cs:__security_cookie
0x1800493bf  xor     rax, rsp
0x1800493c2  mov     [rbp+57h+var_38], rax
0x1800493c6  mov     r12, r8
0x1800493c9  mov     rsi, rdx
0x1800493cc  mov     r14, rcx
0x1800493cf  xor     r13d, r13d
0x1800493d2  mov     [rbp+57h+var_80], r13
0x1800493d6  mov     rbx, [rcx+10h]
0x1800493da  mov     rax, [rbx]
0x1800493dd  mov     r15, [rax+40h]
0x1800493e1  lea     rcx, [rbp+57h+var_80]
0x1800493e5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800493ea  mov     [rbp+57h+length], r13d
0x1800493ee  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800493f2  mov     rcx, rdi
0x1800493f5  inc     rcx; unsigned __int64
0x1800493f8  cmp     [rsi+rcx*2], r13w
0x1800493fd  jnz     short loc_1800493F5
0x1800493ff  lea     rdx, [rbp+57h+length]; unsigned int *
0x180049403  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180049408  test    eax, eax
0x18004940a  jns     short loc_180049421
0x18004940c  xor     r9d, r9d; lpArguments
0x18004940f  xor     r8d, r8d; nNumberOfArguments
0x180049412  lea     edx, [r9+1]; dwExceptionFlags
0x180049416  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004941b  call    cs:__imp_RaiseException
0x180049421  lea     r9, [rbp+57h+string]; string
0x180049425  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180049429  mov     edx, [rbp+57h+length]; length
0x18004942c  mov     rcx, rsi; sourceString
0x18004942f  call    cs:__imp_WindowsCreateStringReference
0x180049435  lea     r8, [rbp+57h+var_80]
0x180049439  mov     rdx, [rbp+57h+string]
0x18004943d  mov     rcx, rbx
0x180049440  mov     rax, r15
0x180049443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049448  test    eax, eax
0x18004944a  jns     loc_18004953B
0x180049450  mov     [rbp+57h+string], r13
0x180049454  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r13
0x180049458  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r13
0x18004945c  mov     r8, rdi
0x18004945f  mov     rdx, rsi
0x180049462  lea     rcx, [rbp+57h+string]
0x180049466  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18004946b  mov     ebx, eax
0x18004946d  test    eax, eax
0x18004946f  jns     short loc_18004947E
0x180049471  mov     r9d, eax
0x180049474  mov     edx, 37h ; '7'
0x180049479  jmp     loc_180049516
0x18004947e  lea     rcx, [rbp+57h+string]
0x180049482  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180049487  mov     edx, dword ptr [rbp+57h+hstringHeader.Reserved]; cchLength
0x18004948a  mov     rbx, [rbp+57h+string]
0x18004948e  mov     rcx, rbx; lpsz
0x180049491  call    cs:__imp_CharLowerBuffW
0x180049497  mov     r14, [r14+10h]
0x18004949b  mov     rax, [r14]
0x18004949e  mov     r15, [rax+40h]
0x1800494a2  lea     rcx, [rbp+57h+var_80]
0x1800494a6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800494ab  mov     [rbp+57h+length], r13d
0x1800494af  inc     rdi
0x1800494b2  cmp     [rbx+rdi*2], r13w
0x1800494b7  jnz     short loc_1800494AF
0x1800494b9  lea     rdx, [rbp+57h+length]; unsigned int *
0x1800494bd  mov     rcx, rdi; unsigned __int64
0x1800494c0  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800494c5  test    eax, eax
0x1800494c7  jns     short loc_1800494DE
0x1800494c9  xor     r9d, r9d; lpArguments
0x1800494cc  xor     r8d, r8d; nNumberOfArguments
0x1800494cf  lea     edx, [r9+1]; dwExceptionFlags
0x1800494d3  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800494d8  call    cs:__imp_RaiseException
0x1800494de  lea     r9, [rbp+57h+var_58]; string
0x1800494e2  lea     r8, [rbp+57h+var_50]; hstringHeader
0x1800494e6  mov     edx, [rbp+57h+length]; length
0x1800494e9  mov     rcx, rbx; sourceString
0x1800494ec  call    cs:__imp_WindowsCreateStringReference
0x1800494f2  lea     r8, [rbp+57h+var_80]
0x1800494f6  mov     rdx, [rbp+57h+var_58]
0x1800494fa  mov     rcx, r14
0x1800494fd  mov     rax, r15
0x180049500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049505  test    eax, eax
0x180049507  jns     short loc_180049532
0x180049509  mov     ebx, 80041122h
0x18004950e  mov     r9d, ebx; char *
0x180049511  mov     edx, 3Eh ; '>'; void *
0x180049516  lea     r8, aOnecoreBaseFli_62; "onecore\\base\\flighting\\flightsetting"...
0x18004951d  mov     rcx, [rbp+5Fh]; this
0x180049521  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049526  nop
0x180049527  lea     rcx, [rbp+57h+string]
0x18004952b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180049530  jmp     short loc_1800495B0
0x180049532  lea     rcx, [rbp+57h+string]
0x180049536  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004953b  mov     [rbp+57h+var_88], r13
0x18004953f  mov     rax, [rbp+57h+var_80]
0x180049543  mov     qword ptr [rbp+57h+length], rax
0x180049547  lea     rcx, [rbp+57h+var_88]
0x18004954b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180049550  lea     rdx, [rbp+57h+length]
0x180049554  lea     rcx, [rbp+57h+var_88]
0x180049558  call    ??$MakeAndInitialize@VWmiProvider@@V1@PEAUIJsonObject@Json@Data@Windows@@@Details@WRL@Microsoft@@YAJPEAPEAVWmiProvider@@$$QEAPEAUIJsonObject@Json@Data@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<WmiProvider,WmiProvider,Windows::Data::Json::IJsonObject *>(WmiProvider * *,Windows::Data::Json::IJsonObject * &&)
0x18004955d  mov     ebx, eax
0x18004955f  test    eax, eax
0x180049561  jns     short loc_180049598
0x180049563  mov     rcx, [rbp+5Fh]; this
0x180049567  mov     [rsp+0C0h+var_98], rsi; char *
0x18004956c  lea     rax, aPropnameWs; "propName=%ws"
0x180049573  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180049578  mov     r9d, ebx; char *
0x18004957b  lea     r8, aOnecoreBaseFli_62; "onecore\\base\\flighting\\flightsetting"...
0x180049582  mov     edx, 44h ; 'D'; void *
0x180049587  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004958c  nop
0x18004958d  lea     rcx, [rbp+57h+var_88]
0x180049591  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180049596  jmp     short loc_1800495B0
0x180049598  mov     rax, [rbp+57h+var_88]
0x18004959c  mov     [rbp+57h+var_88], r13
0x1800495a0  mov     [r12], rax
0x1800495a4  lea     rcx, [rbp+57h+var_88]
0x1800495a8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800495ad  mov     ebx, r13d
0x1800495b0  lea     rcx, [rbp+57h+var_80]
0x1800495b4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800495b9  mov     eax, ebx
0x1800495bb  mov     rcx, [rbp+57h+var_38]
0x1800495bf  xor     rcx, rsp; StackCookie
0x1800495c2  call    __security_check_cookie
0x1800495c7  mov     rbx, [rsp+0C0h+arg_18]
0x1800495cf  add     rsp, 90h
0x1800495d6  pop     r15
0x1800495d8  pop     r14
0x1800495da  pop     r13
0x1800495dc  pop     r12
0x1800495de  pop     rdi
0x1800495df  pop     rsi
0x1800495e0  pop     rbp
0x1800495e1  retn
```
