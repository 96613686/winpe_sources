# DynamicProviderTemplate<StoreAppProvider>::GetAttributeObject(ushort const *,StoreAppProvider * *)

- ea: `0x180048f04`
- end: `0x18004914a`
- name: `?GetAttributeObject@?$DynamicProviderTemplate@VStoreAppProvider@@@@QEAAJPEBGPEAPEAVStoreAppProvider@@@Z`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180049b00`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x1800168c8`
- `0x18001b2ec`
- `0x18001c6f4`
- `0x18001ec48`
- `0x18001ec78`
- `0x180047610`
- `0x180048f04`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048f83`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180049040`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048f83`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180049040`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180048ff9`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180048ff9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048f97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180049054`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048f97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180049054`

## string_xrefs

- `0x18004907e`: `onecore\base\flighting\flightsettings\broker\libs\ctac\DynamicProviderTemplate.h`
- `0x1800490e3`: `onecore\base\flighting\flightsettings\broker\libs\ctac\DynamicProviderTemplate.h`

## pseudocode

```c
__int64 __fastcall DynamicProviderTemplate<StoreAppProvider>::GetAttributeObject(
        __int64 a1,
        const WCHAR *a2,
        _QWORD *a3)
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
  v11 = Microsoft::WRL::Details::MakeAndInitialize<StoreAppProvider,StoreAppProvider,Windows::Data::Json::IJsonObject *>(
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
0x180048f04  mov     [rsp-8+arg_18], rbx
0x180048f09  push    rbp
0x180048f0a  push    rsi
0x180048f0b  push    rdi
0x180048f0c  push    r12
0x180048f0e  push    r13
0x180048f10  push    r14
0x180048f12  push    r15
0x180048f14  lea     rbp, [rsp-27h]
0x180048f19  sub     rsp, 90h
0x180048f20  mov     rax, cs:__security_cookie
0x180048f27  xor     rax, rsp
0x180048f2a  mov     [rbp+57h+var_38], rax
0x180048f2e  mov     r12, r8
0x180048f31  mov     rsi, rdx
0x180048f34  mov     r14, rcx
0x180048f37  xor     r13d, r13d
0x180048f3a  mov     [rbp+57h+var_80], r13
0x180048f3e  mov     rbx, [rcx+10h]
0x180048f42  mov     rax, [rbx]
0x180048f45  mov     r15, [rax+40h]
0x180048f49  lea     rcx, [rbp+57h+var_80]
0x180048f4d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180048f52  mov     [rbp+57h+length], r13d
0x180048f56  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180048f5a  mov     rcx, rdi
0x180048f5d  inc     rcx; unsigned __int64
0x180048f60  cmp     [rsi+rcx*2], r13w
0x180048f65  jnz     short loc_180048F5D
0x180048f67  lea     rdx, [rbp+57h+length]; unsigned int *
0x180048f6b  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180048f70  test    eax, eax
0x180048f72  jns     short loc_180048F89
0x180048f74  xor     r9d, r9d; lpArguments
0x180048f77  xor     r8d, r8d; nNumberOfArguments
0x180048f7a  lea     edx, [r9+1]; dwExceptionFlags
0x180048f7e  mov     ecx, 0C000000Dh; dwExceptionCode
0x180048f83  call    cs:__imp_RaiseException
0x180048f89  lea     r9, [rbp+57h+string]; string
0x180048f8d  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180048f91  mov     edx, [rbp+57h+length]; length
0x180048f94  mov     rcx, rsi; sourceString
0x180048f97  call    cs:__imp_WindowsCreateStringReference
0x180048f9d  lea     r8, [rbp+57h+var_80]
0x180048fa1  mov     rdx, [rbp+57h+string]
0x180048fa5  mov     rcx, rbx
0x180048fa8  mov     rax, r15
0x180048fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048fb0  test    eax, eax
0x180048fb2  jns     loc_1800490A3
0x180048fb8  mov     [rbp+57h+string], r13
0x180048fbc  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r13
0x180048fc0  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r13
0x180048fc4  mov     r8, rdi
0x180048fc7  mov     rdx, rsi
0x180048fca  lea     rcx, [rbp+57h+string]
0x180048fce  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180048fd3  mov     ebx, eax
0x180048fd5  test    eax, eax
0x180048fd7  jns     short loc_180048FE6
0x180048fd9  mov     r9d, eax
0x180048fdc  mov     edx, 37h ; '7'
0x180048fe1  jmp     loc_18004907E
0x180048fe6  lea     rcx, [rbp+57h+string]
0x180048fea  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180048fef  mov     edx, dword ptr [rbp+57h+hstringHeader.Reserved]; cchLength
0x180048ff2  mov     rbx, [rbp+57h+string]
0x180048ff6  mov     rcx, rbx; lpsz
0x180048ff9  call    cs:__imp_CharLowerBuffW
0x180048fff  mov     r14, [r14+10h]
0x180049003  mov     rax, [r14]
0x180049006  mov     r15, [rax+40h]
0x18004900a  lea     rcx, [rbp+57h+var_80]
0x18004900e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180049013  mov     [rbp+57h+length], r13d
0x180049017  inc     rdi
0x18004901a  cmp     [rbx+rdi*2], r13w
0x18004901f  jnz     short loc_180049017
0x180049021  lea     rdx, [rbp+57h+length]; unsigned int *
0x180049025  mov     rcx, rdi; unsigned __int64
0x180049028  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18004902d  test    eax, eax
0x18004902f  jns     short loc_180049046
0x180049031  xor     r9d, r9d; lpArguments
0x180049034  xor     r8d, r8d; nNumberOfArguments
0x180049037  lea     edx, [r9+1]; dwExceptionFlags
0x18004903b  mov     ecx, 0C000000Dh; dwExceptionCode
0x180049040  call    cs:__imp_RaiseException
0x180049046  lea     r9, [rbp+57h+var_58]; string
0x18004904a  lea     r8, [rbp+57h+var_50]; hstringHeader
0x18004904e  mov     edx, [rbp+57h+length]; length
0x180049051  mov     rcx, rbx; sourceString
0x180049054  call    cs:__imp_WindowsCreateStringReference
0x18004905a  lea     r8, [rbp+57h+var_80]
0x18004905e  mov     rdx, [rbp+57h+var_58]
0x180049062  mov     rcx, r14
0x180049065  mov     rax, r15
0x180049068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004906d  test    eax, eax
0x18004906f  jns     short loc_18004909A
0x180049071  mov     ebx, 80041122h
0x180049076  mov     r9d, ebx; char *
0x180049079  mov     edx, 3Eh ; '>'; void *
0x18004907e  lea     r8, aOnecoreBaseFli_62; "onecore\\base\\flighting\\flightsetting"...
0x180049085  mov     rcx, [rbp+5Fh]; this
0x180049089  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004908e  nop
0x18004908f  lea     rcx, [rbp+57h+string]
0x180049093  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180049098  jmp     short loc_180049118
0x18004909a  lea     rcx, [rbp+57h+string]
0x18004909e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800490a3  mov     [rbp+57h+var_88], r13
0x1800490a7  mov     rax, [rbp+57h+var_80]
0x1800490ab  mov     qword ptr [rbp+57h+length], rax
0x1800490af  lea     rcx, [rbp+57h+var_88]
0x1800490b3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800490b8  lea     rdx, [rbp+57h+length]
0x1800490bc  lea     rcx, [rbp+57h+var_88]
0x1800490c0  call    ??$MakeAndInitialize@VStoreAppProvider@@V1@PEAUIJsonObject@Json@Data@Windows@@@Details@WRL@Microsoft@@YAJPEAPEAVStoreAppProvider@@$$QEAPEAUIJsonObject@Json@Data@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<StoreAppProvider,StoreAppProvider,Windows::Data::Json::IJsonObject *>(StoreAppProvider * *,Windows::Data::Json::IJsonObject * &&)
0x1800490c5  mov     ebx, eax
0x1800490c7  test    eax, eax
0x1800490c9  jns     short loc_180049100
0x1800490cb  mov     rcx, [rbp+5Fh]; this
0x1800490cf  mov     [rsp+0C0h+var_98], rsi; char *
0x1800490d4  lea     rax, aPropnameWs; "propName=%ws"
0x1800490db  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x1800490e0  mov     r9d, ebx; char *
0x1800490e3  lea     r8, aOnecoreBaseFli_62; "onecore\\base\\flighting\\flightsetting"...
0x1800490ea  mov     edx, 44h ; 'D'; void *
0x1800490ef  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800490f4  nop
0x1800490f5  lea     rcx, [rbp+57h+var_88]
0x1800490f9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800490fe  jmp     short loc_180049118
0x180049100  mov     rax, [rbp+57h+var_88]
0x180049104  mov     [rbp+57h+var_88], r13
0x180049108  mov     [r12], rax
0x18004910c  lea     rcx, [rbp+57h+var_88]
0x180049110  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180049115  mov     ebx, r13d
0x180049118  lea     rcx, [rbp+57h+var_80]
0x18004911c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180049121  mov     eax, ebx
0x180049123  mov     rcx, [rbp+57h+var_38]
0x180049127  xor     rcx, rsp; StackCookie
0x18004912a  call    __security_check_cookie
0x18004912f  mov     rbx, [rsp+0C0h+arg_18]
0x180049137  add     rsp, 90h
0x18004913e  pop     r15
0x180049140  pop     r14
0x180049142  pop     r13
0x180049144  pop     r12
0x180049146  pop     rdi
0x180049147  pop     rsi
0x180049148  pop     rbp
0x180049149  retn
```
