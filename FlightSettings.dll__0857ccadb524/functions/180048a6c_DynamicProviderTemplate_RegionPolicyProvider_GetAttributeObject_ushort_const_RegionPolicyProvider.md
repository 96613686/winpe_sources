# DynamicProviderTemplate<RegionPolicyProvider>::GetAttributeObject(ushort const *,RegionPolicyProvider * *)

- ea: `0x180048a6c`
- end: `0x180048cb2`
- name: `?GetAttributeObject@?$DynamicProviderTemplate@VRegionPolicyProvider@@@@QEAAJPEBGPEAPEAVRegionPolicyProvider@@@Z`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180049920`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x1800168c8`
- `0x18001b2ec`
- `0x18001c6f4`
- `0x18001ec48`
- `0x18001ec78`
- `0x180047470`
- `0x180048a6c`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048aeb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048ba8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048aeb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048ba8`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180048b61`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180048b61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048aff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048bbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048aff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048bbc`

## string_xrefs

- `0x180048be6`: `onecore\base\flighting\flightsettings\broker\libs\ctac\DynamicProviderTemplate.h`
- `0x180048c4b`: `onecore\base\flighting\flightsettings\broker\libs\ctac\DynamicProviderTemplate.h`

## pseudocode

```c
__int64 __fastcall DynamicProviderTemplate<RegionPolicyProvider>::GetAttributeObject(
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
  v11 = Microsoft::WRL::Details::MakeAndInitialize<RegionPolicyProvider,RegionPolicyProvider,Windows::Data::Json::IJsonObject *>(
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
0x180048a6c  mov     [rsp-8+arg_18], rbx
0x180048a71  push    rbp
0x180048a72  push    rsi
0x180048a73  push    rdi
0x180048a74  push    r12
0x180048a76  push    r13
0x180048a78  push    r14
0x180048a7a  push    r15
0x180048a7c  lea     rbp, [rsp-27h]
0x180048a81  sub     rsp, 90h
0x180048a88  mov     rax, cs:__security_cookie
0x180048a8f  xor     rax, rsp
0x180048a92  mov     [rbp+57h+var_38], rax
0x180048a96  mov     r12, r8
0x180048a99  mov     rsi, rdx
0x180048a9c  mov     r14, rcx
0x180048a9f  xor     r13d, r13d
0x180048aa2  mov     [rbp+57h+var_80], r13
0x180048aa6  mov     rbx, [rcx+10h]
0x180048aaa  mov     rax, [rbx]
0x180048aad  mov     r15, [rax+40h]
0x180048ab1  lea     rcx, [rbp+57h+var_80]
0x180048ab5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180048aba  mov     [rbp+57h+length], r13d
0x180048abe  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180048ac2  mov     rcx, rdi
0x180048ac5  inc     rcx; unsigned __int64
0x180048ac8  cmp     [rsi+rcx*2], r13w
0x180048acd  jnz     short loc_180048AC5
0x180048acf  lea     rdx, [rbp+57h+length]; unsigned int *
0x180048ad3  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180048ad8  test    eax, eax
0x180048ada  jns     short loc_180048AF1
0x180048adc  xor     r9d, r9d; lpArguments
0x180048adf  xor     r8d, r8d; nNumberOfArguments
0x180048ae2  lea     edx, [r9+1]; dwExceptionFlags
0x180048ae6  mov     ecx, 0C000000Dh; dwExceptionCode
0x180048aeb  call    cs:__imp_RaiseException
0x180048af1  lea     r9, [rbp+57h+string]; string
0x180048af5  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180048af9  mov     edx, [rbp+57h+length]; length
0x180048afc  mov     rcx, rsi; sourceString
0x180048aff  call    cs:__imp_WindowsCreateStringReference
0x180048b05  lea     r8, [rbp+57h+var_80]
0x180048b09  mov     rdx, [rbp+57h+string]
0x180048b0d  mov     rcx, rbx
0x180048b10  mov     rax, r15
0x180048b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b18  test    eax, eax
0x180048b1a  jns     loc_180048C0B
0x180048b20  mov     [rbp+57h+string], r13
0x180048b24  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r13
0x180048b28  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r13
0x180048b2c  mov     r8, rdi
0x180048b2f  mov     rdx, rsi
0x180048b32  lea     rcx, [rbp+57h+string]
0x180048b36  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180048b3b  mov     ebx, eax
0x180048b3d  test    eax, eax
0x180048b3f  jns     short loc_180048B4E
0x180048b41  mov     r9d, eax
0x180048b44  mov     edx, 37h ; '7'
0x180048b49  jmp     loc_180048BE6
0x180048b4e  lea     rcx, [rbp+57h+string]
0x180048b52  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180048b57  mov     edx, dword ptr [rbp+57h+hstringHeader.Reserved]; cchLength
0x180048b5a  mov     rbx, [rbp+57h+string]
0x180048b5e  mov     rcx, rbx; lpsz
0x180048b61  call    cs:__imp_CharLowerBuffW
0x180048b67  mov     r14, [r14+10h]
0x180048b6b  mov     rax, [r14]
0x180048b6e  mov     r15, [rax+40h]
0x180048b72  lea     rcx, [rbp+57h+var_80]
0x180048b76  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180048b7b  mov     [rbp+57h+length], r13d
0x180048b7f  inc     rdi
0x180048b82  cmp     [rbx+rdi*2], r13w
0x180048b87  jnz     short loc_180048B7F
0x180048b89  lea     rdx, [rbp+57h+length]; unsigned int *
0x180048b8d  mov     rcx, rdi; unsigned __int64
0x180048b90  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180048b95  test    eax, eax
0x180048b97  jns     short loc_180048BAE
0x180048b99  xor     r9d, r9d; lpArguments
0x180048b9c  xor     r8d, r8d; nNumberOfArguments
0x180048b9f  lea     edx, [r9+1]; dwExceptionFlags
0x180048ba3  mov     ecx, 0C000000Dh; dwExceptionCode
0x180048ba8  call    cs:__imp_RaiseException
0x180048bae  lea     r9, [rbp+57h+var_58]; string
0x180048bb2  lea     r8, [rbp+57h+var_50]; hstringHeader
0x180048bb6  mov     edx, [rbp+57h+length]; length
0x180048bb9  mov     rcx, rbx; sourceString
0x180048bbc  call    cs:__imp_WindowsCreateStringReference
0x180048bc2  lea     r8, [rbp+57h+var_80]
0x180048bc6  mov     rdx, [rbp+57h+var_58]
0x180048bca  mov     rcx, r14
0x180048bcd  mov     rax, r15
0x180048bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048bd5  test    eax, eax
0x180048bd7  jns     short loc_180048C02
0x180048bd9  mov     ebx, 80041122h
0x180048bde  mov     r9d, ebx; char *
0x180048be1  mov     edx, 3Eh ; '>'; void *
0x180048be6  lea     r8, aOnecoreBaseFli_62; "onecore\\base\\flighting\\flightsetting"...
0x180048bed  mov     rcx, [rbp+5Fh]; this
0x180048bf1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048bf6  nop
0x180048bf7  lea     rcx, [rbp+57h+string]
0x180048bfb  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180048c00  jmp     short loc_180048C80
0x180048c02  lea     rcx, [rbp+57h+string]
0x180048c06  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180048c0b  mov     [rbp+57h+var_88], r13
0x180048c0f  mov     rax, [rbp+57h+var_80]
0x180048c13  mov     qword ptr [rbp+57h+length], rax
0x180048c17  lea     rcx, [rbp+57h+var_88]
0x180048c1b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180048c20  lea     rdx, [rbp+57h+length]
0x180048c24  lea     rcx, [rbp+57h+var_88]
0x180048c28  call    ??$MakeAndInitialize@VRegionPolicyProvider@@V1@PEAUIJsonObject@Json@Data@Windows@@@Details@WRL@Microsoft@@YAJPEAPEAVRegionPolicyProvider@@$$QEAPEAUIJsonObject@Json@Data@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<RegionPolicyProvider,RegionPolicyProvider,Windows::Data::Json::IJsonObject *>(RegionPolicyProvider * *,Windows::Data::Json::IJsonObject * &&)
0x180048c2d  mov     ebx, eax
0x180048c2f  test    eax, eax
0x180048c31  jns     short loc_180048C68
0x180048c33  mov     rcx, [rbp+5Fh]; this
0x180048c37  mov     [rsp+0C0h+var_98], rsi; char *
0x180048c3c  lea     rax, aPropnameWs; "propName=%ws"
0x180048c43  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180048c48  mov     r9d, ebx; char *
0x180048c4b  lea     r8, aOnecoreBaseFli_62; "onecore\\base\\flighting\\flightsetting"...
0x180048c52  mov     edx, 44h ; 'D'; void *
0x180048c57  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180048c5c  nop
0x180048c5d  lea     rcx, [rbp+57h+var_88]
0x180048c61  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180048c66  jmp     short loc_180048C80
0x180048c68  mov     rax, [rbp+57h+var_88]
0x180048c6c  mov     [rbp+57h+var_88], r13
0x180048c70  mov     [r12], rax
0x180048c74  lea     rcx, [rbp+57h+var_88]
0x180048c78  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180048c7d  mov     ebx, r13d
0x180048c80  lea     rcx, [rbp+57h+var_80]
0x180048c84  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180048c89  mov     eax, ebx
0x180048c8b  mov     rcx, [rbp+57h+var_38]
0x180048c8f  xor     rcx, rsp; StackCookie
0x180048c92  call    __security_check_cookie
0x180048c97  mov     rbx, [rsp+0C0h+arg_18]
0x180048c9f  add     rsp, 90h
0x180048ca6  pop     r15
0x180048ca8  pop     r14
0x180048caa  pop     r13
0x180048cac  pop     r12
0x180048cae  pop     rdi
0x180048caf  pop     rsi
0x180048cb0  pop     rbp
0x180048cb1  retn
```
