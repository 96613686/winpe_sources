# DynamicProviderTemplate<RegistryProvider>::GetAttributeObject(ushort const *,RegistryProvider * *)

- ea: `0x180048cb8`
- end: `0x180048efe`
- name: `?GetAttributeObject@?$DynamicProviderTemplate@VRegistryProvider@@@@QEAAJPEBGPEAPEAVRegistryProvider@@@Z`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180049a10`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x1800168c8`
- `0x18001b2ec`
- `0x18001c6f4`
- `0x18001ec48`
- `0x18001ec78`
- `0x180047540`
- `0x180048cb8`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048d37`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048df4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048d37`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048df4`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180048dad`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180048dad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048d4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048e08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048d4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048e08`

## string_xrefs

- `0x180048e32`: `onecore\base\flighting\flightsettings\broker\libs\ctac\DynamicProviderTemplate.h`
- `0x180048e97`: `onecore\base\flighting\flightsettings\broker\libs\ctac\DynamicProviderTemplate.h`

## pseudocode

```c
__int64 __fastcall DynamicProviderTemplate<RegistryProvider>::GetAttributeObject(
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
  v11 = Microsoft::WRL::Details::MakeAndInitialize<RegistryProvider,RegistryProvider,Windows::Data::Json::IJsonObject *>(
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
0x180048cb8  mov     [rsp-8+arg_18], rbx
0x180048cbd  push    rbp
0x180048cbe  push    rsi
0x180048cbf  push    rdi
0x180048cc0  push    r12
0x180048cc2  push    r13
0x180048cc4  push    r14
0x180048cc6  push    r15
0x180048cc8  lea     rbp, [rsp-27h]
0x180048ccd  sub     rsp, 90h
0x180048cd4  mov     rax, cs:__security_cookie
0x180048cdb  xor     rax, rsp
0x180048cde  mov     [rbp+57h+var_38], rax
0x180048ce2  mov     r12, r8
0x180048ce5  mov     rsi, rdx
0x180048ce8  mov     r14, rcx
0x180048ceb  xor     r13d, r13d
0x180048cee  mov     [rbp+57h+var_80], r13
0x180048cf2  mov     rbx, [rcx+10h]
0x180048cf6  mov     rax, [rbx]
0x180048cf9  mov     r15, [rax+40h]
0x180048cfd  lea     rcx, [rbp+57h+var_80]
0x180048d01  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180048d06  mov     [rbp+57h+length], r13d
0x180048d0a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180048d0e  mov     rcx, rdi
0x180048d11  inc     rcx; unsigned __int64
0x180048d14  cmp     [rsi+rcx*2], r13w
0x180048d19  jnz     short loc_180048D11
0x180048d1b  lea     rdx, [rbp+57h+length]; unsigned int *
0x180048d1f  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180048d24  test    eax, eax
0x180048d26  jns     short loc_180048D3D
0x180048d28  xor     r9d, r9d; lpArguments
0x180048d2b  xor     r8d, r8d; nNumberOfArguments
0x180048d2e  lea     edx, [r9+1]; dwExceptionFlags
0x180048d32  mov     ecx, 0C000000Dh; dwExceptionCode
0x180048d37  call    cs:__imp_RaiseException
0x180048d3d  lea     r9, [rbp+57h+string]; string
0x180048d41  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180048d45  mov     edx, [rbp+57h+length]; length
0x180048d48  mov     rcx, rsi; sourceString
0x180048d4b  call    cs:__imp_WindowsCreateStringReference
0x180048d51  lea     r8, [rbp+57h+var_80]
0x180048d55  mov     rdx, [rbp+57h+string]
0x180048d59  mov     rcx, rbx
0x180048d5c  mov     rax, r15
0x180048d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048d64  test    eax, eax
0x180048d66  jns     loc_180048E57
0x180048d6c  mov     [rbp+57h+string], r13
0x180048d70  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r13
0x180048d74  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r13
0x180048d78  mov     r8, rdi
0x180048d7b  mov     rdx, rsi
0x180048d7e  lea     rcx, [rbp+57h+string]
0x180048d82  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180048d87  mov     ebx, eax
0x180048d89  test    eax, eax
0x180048d8b  jns     short loc_180048D9A
0x180048d8d  mov     r9d, eax
0x180048d90  mov     edx, 37h ; '7'
0x180048d95  jmp     loc_180048E32
0x180048d9a  lea     rcx, [rbp+57h+string]
0x180048d9e  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180048da3  mov     edx, dword ptr [rbp+57h+hstringHeader.Reserved]; cchLength
0x180048da6  mov     rbx, [rbp+57h+string]
0x180048daa  mov     rcx, rbx; lpsz
0x180048dad  call    cs:__imp_CharLowerBuffW
0x180048db3  mov     r14, [r14+10h]
0x180048db7  mov     rax, [r14]
0x180048dba  mov     r15, [rax+40h]
0x180048dbe  lea     rcx, [rbp+57h+var_80]
0x180048dc2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180048dc7  mov     [rbp+57h+length], r13d
0x180048dcb  inc     rdi
0x180048dce  cmp     [rbx+rdi*2], r13w
0x180048dd3  jnz     short loc_180048DCB
0x180048dd5  lea     rdx, [rbp+57h+length]; unsigned int *
0x180048dd9  mov     rcx, rdi; unsigned __int64
0x180048ddc  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180048de1  test    eax, eax
0x180048de3  jns     short loc_180048DFA
0x180048de5  xor     r9d, r9d; lpArguments
0x180048de8  xor     r8d, r8d; nNumberOfArguments
0x180048deb  lea     edx, [r9+1]; dwExceptionFlags
0x180048def  mov     ecx, 0C000000Dh; dwExceptionCode
0x180048df4  call    cs:__imp_RaiseException
0x180048dfa  lea     r9, [rbp+57h+var_58]; string
0x180048dfe  lea     r8, [rbp+57h+var_50]; hstringHeader
0x180048e02  mov     edx, [rbp+57h+length]; length
0x180048e05  mov     rcx, rbx; sourceString
0x180048e08  call    cs:__imp_WindowsCreateStringReference
0x180048e0e  lea     r8, [rbp+57h+var_80]
0x180048e12  mov     rdx, [rbp+57h+var_58]
0x180048e16  mov     rcx, r14
0x180048e19  mov     rax, r15
0x180048e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e21  test    eax, eax
0x180048e23  jns     short loc_180048E4E
0x180048e25  mov     ebx, 80041122h
0x180048e2a  mov     r9d, ebx; char *
0x180048e2d  mov     edx, 3Eh ; '>'; void *
0x180048e32  lea     r8, aOnecoreBaseFli_62; "onecore\\base\\flighting\\flightsetting"...
0x180048e39  mov     rcx, [rbp+5Fh]; this
0x180048e3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048e42  nop
0x180048e43  lea     rcx, [rbp+57h+string]
0x180048e47  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180048e4c  jmp     short loc_180048ECC
0x180048e4e  lea     rcx, [rbp+57h+string]
0x180048e52  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180048e57  mov     [rbp+57h+var_88], r13
0x180048e5b  mov     rax, [rbp+57h+var_80]
0x180048e5f  mov     qword ptr [rbp+57h+length], rax
0x180048e63  lea     rcx, [rbp+57h+var_88]
0x180048e67  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180048e6c  lea     rdx, [rbp+57h+length]
0x180048e70  lea     rcx, [rbp+57h+var_88]
0x180048e74  call    ??$MakeAndInitialize@VRegistryProvider@@V1@PEAUIJsonObject@Json@Data@Windows@@@Details@WRL@Microsoft@@YAJPEAPEAVRegistryProvider@@$$QEAPEAUIJsonObject@Json@Data@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<RegistryProvider,RegistryProvider,Windows::Data::Json::IJsonObject *>(RegistryProvider * *,Windows::Data::Json::IJsonObject * &&)
0x180048e79  mov     ebx, eax
0x180048e7b  test    eax, eax
0x180048e7d  jns     short loc_180048EB4
0x180048e7f  mov     rcx, [rbp+5Fh]; this
0x180048e83  mov     [rsp+0C0h+var_98], rsi; char *
0x180048e88  lea     rax, aPropnameWs; "propName=%ws"
0x180048e8f  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180048e94  mov     r9d, ebx; char *
0x180048e97  lea     r8, aOnecoreBaseFli_62; "onecore\\base\\flighting\\flightsetting"...
0x180048e9e  mov     edx, 44h ; 'D'; void *
0x180048ea3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180048ea8  nop
0x180048ea9  lea     rcx, [rbp+57h+var_88]
0x180048ead  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180048eb2  jmp     short loc_180048ECC
0x180048eb4  mov     rax, [rbp+57h+var_88]
0x180048eb8  mov     [rbp+57h+var_88], r13
0x180048ebc  mov     [r12], rax
0x180048ec0  lea     rcx, [rbp+57h+var_88]
0x180048ec4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180048ec9  mov     ebx, r13d
0x180048ecc  lea     rcx, [rbp+57h+var_80]
0x180048ed0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180048ed5  mov     eax, ebx
0x180048ed7  mov     rcx, [rbp+57h+var_38]
0x180048edb  xor     rcx, rsp; StackCookie
0x180048ede  call    __security_check_cookie
0x180048ee3  mov     rbx, [rsp+0C0h+arg_18]
0x180048eeb  add     rsp, 90h
0x180048ef2  pop     r15
0x180048ef4  pop     r14
0x180048ef6  pop     r13
0x180048ef8  pop     r12
0x180048efa  pop     rdi
0x180048efb  pop     rsi
0x180048efc  pop     rbp
0x180048efd  retn
```
