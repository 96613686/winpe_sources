# DynamicProviderTemplate<UpdatePolicyProvider>::GetAttributeObject(ushort const *,UpdatePolicyProvider * *)

- ea: `0x180049150`
- end: `0x180049396`
- name: `?GetAttributeObject@?$DynamicProviderTemplate@VUpdatePolicyProvider@@@@QEAAJPEBGPEAPEAVUpdatePolicyProvider@@@Z`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180049c10`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x1800168c8`
- `0x18001b2ec`
- `0x18001c6f4`
- `0x18001ec48`
- `0x18001ec78`
- `0x1800476e0`
- `0x180049150`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800491cf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004928c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800491cf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004928c`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180049245`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180049245`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800491e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800492a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800491e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800492a0`

## string_xrefs

- `0x1800492ca`: `onecore\base\flighting\flightsettings\broker\libs\ctac\DynamicProviderTemplate.h`
- `0x18004932f`: `onecore\base\flighting\flightsettings\broker\libs\ctac\DynamicProviderTemplate.h`

## pseudocode

```c
__int64 __fastcall DynamicProviderTemplate<UpdatePolicyProvider>::GetAttributeObject(
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
  v11 = Microsoft::WRL::Details::MakeAndInitialize<UpdatePolicyProvider,UpdatePolicyProvider,Windows::Data::Json::IJsonObject *>(
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
0x180049150  mov     [rsp-8+arg_18], rbx
0x180049155  push    rbp
0x180049156  push    rsi
0x180049157  push    rdi
0x180049158  push    r12
0x18004915a  push    r13
0x18004915c  push    r14
0x18004915e  push    r15
0x180049160  lea     rbp, [rsp-27h]
0x180049165  sub     rsp, 90h
0x18004916c  mov     rax, cs:__security_cookie
0x180049173  xor     rax, rsp
0x180049176  mov     [rbp+57h+var_38], rax
0x18004917a  mov     r12, r8
0x18004917d  mov     rsi, rdx
0x180049180  mov     r14, rcx
0x180049183  xor     r13d, r13d
0x180049186  mov     [rbp+57h+var_80], r13
0x18004918a  mov     rbx, [rcx+10h]
0x18004918e  mov     rax, [rbx]
0x180049191  mov     r15, [rax+40h]
0x180049195  lea     rcx, [rbp+57h+var_80]
0x180049199  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004919e  mov     [rbp+57h+length], r13d
0x1800491a2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800491a6  mov     rcx, rdi
0x1800491a9  inc     rcx; unsigned __int64
0x1800491ac  cmp     [rsi+rcx*2], r13w
0x1800491b1  jnz     short loc_1800491A9
0x1800491b3  lea     rdx, [rbp+57h+length]; unsigned int *
0x1800491b7  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800491bc  test    eax, eax
0x1800491be  jns     short loc_1800491D5
0x1800491c0  xor     r9d, r9d; lpArguments
0x1800491c3  xor     r8d, r8d; nNumberOfArguments
0x1800491c6  lea     edx, [r9+1]; dwExceptionFlags
0x1800491ca  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800491cf  call    cs:__imp_RaiseException
0x1800491d5  lea     r9, [rbp+57h+string]; string
0x1800491d9  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800491dd  mov     edx, [rbp+57h+length]; length
0x1800491e0  mov     rcx, rsi; sourceString
0x1800491e3  call    cs:__imp_WindowsCreateStringReference
0x1800491e9  lea     r8, [rbp+57h+var_80]
0x1800491ed  mov     rdx, [rbp+57h+string]
0x1800491f1  mov     rcx, rbx
0x1800491f4  mov     rax, r15
0x1800491f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800491fc  test    eax, eax
0x1800491fe  jns     loc_1800492EF
0x180049204  mov     [rbp+57h+string], r13
0x180049208  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r13
0x18004920c  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r13
0x180049210  mov     r8, rdi
0x180049213  mov     rdx, rsi
0x180049216  lea     rcx, [rbp+57h+string]
0x18004921a  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18004921f  mov     ebx, eax
0x180049221  test    eax, eax
0x180049223  jns     short loc_180049232
0x180049225  mov     r9d, eax
0x180049228  mov     edx, 37h ; '7'
0x18004922d  jmp     loc_1800492CA
0x180049232  lea     rcx, [rbp+57h+string]
0x180049236  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18004923b  mov     edx, dword ptr [rbp+57h+hstringHeader.Reserved]; cchLength
0x18004923e  mov     rbx, [rbp+57h+string]
0x180049242  mov     rcx, rbx; lpsz
0x180049245  call    cs:__imp_CharLowerBuffW
0x18004924b  mov     r14, [r14+10h]
0x18004924f  mov     rax, [r14]
0x180049252  mov     r15, [rax+40h]
0x180049256  lea     rcx, [rbp+57h+var_80]
0x18004925a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004925f  mov     [rbp+57h+length], r13d
0x180049263  inc     rdi
0x180049266  cmp     [rbx+rdi*2], r13w
0x18004926b  jnz     short loc_180049263
0x18004926d  lea     rdx, [rbp+57h+length]; unsigned int *
0x180049271  mov     rcx, rdi; unsigned __int64
0x180049274  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180049279  test    eax, eax
0x18004927b  jns     short loc_180049292
0x18004927d  xor     r9d, r9d; lpArguments
0x180049280  xor     r8d, r8d; nNumberOfArguments
0x180049283  lea     edx, [r9+1]; dwExceptionFlags
0x180049287  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004928c  call    cs:__imp_RaiseException
0x180049292  lea     r9, [rbp+57h+var_58]; string
0x180049296  lea     r8, [rbp+57h+var_50]; hstringHeader
0x18004929a  mov     edx, [rbp+57h+length]; length
0x18004929d  mov     rcx, rbx; sourceString
0x1800492a0  call    cs:__imp_WindowsCreateStringReference
0x1800492a6  lea     r8, [rbp+57h+var_80]
0x1800492aa  mov     rdx, [rbp+57h+var_58]
0x1800492ae  mov     rcx, r14
0x1800492b1  mov     rax, r15
0x1800492b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800492b9  test    eax, eax
0x1800492bb  jns     short loc_1800492E6
0x1800492bd  mov     ebx, 80041122h
0x1800492c2  mov     r9d, ebx; char *
0x1800492c5  mov     edx, 3Eh ; '>'; void *
0x1800492ca  lea     r8, aOnecoreBaseFli_62; "onecore\\base\\flighting\\flightsetting"...
0x1800492d1  mov     rcx, [rbp+5Fh]; this
0x1800492d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800492da  nop
0x1800492db  lea     rcx, [rbp+57h+string]
0x1800492df  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800492e4  jmp     short loc_180049364
0x1800492e6  lea     rcx, [rbp+57h+string]
0x1800492ea  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800492ef  mov     [rbp+57h+var_88], r13
0x1800492f3  mov     rax, [rbp+57h+var_80]
0x1800492f7  mov     qword ptr [rbp+57h+length], rax
0x1800492fb  lea     rcx, [rbp+57h+var_88]
0x1800492ff  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180049304  lea     rdx, [rbp+57h+length]
0x180049308  lea     rcx, [rbp+57h+var_88]
0x18004930c  call    ??$MakeAndInitialize@VUpdatePolicyProvider@@V1@PEAUIJsonObject@Json@Data@Windows@@@Details@WRL@Microsoft@@YAJPEAPEAVUpdatePolicyProvider@@$$QEAPEAUIJsonObject@Json@Data@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<UpdatePolicyProvider,UpdatePolicyProvider,Windows::Data::Json::IJsonObject *>(UpdatePolicyProvider * *,Windows::Data::Json::IJsonObject * &&)
0x180049311  mov     ebx, eax
0x180049313  test    eax, eax
0x180049315  jns     short loc_18004934C
0x180049317  mov     rcx, [rbp+5Fh]; this
0x18004931b  mov     [rsp+0C0h+var_98], rsi; char *
0x180049320  lea     rax, aPropnameWs; "propName=%ws"
0x180049327  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18004932c  mov     r9d, ebx; char *
0x18004932f  lea     r8, aOnecoreBaseFli_62; "onecore\\base\\flighting\\flightsetting"...
0x180049336  mov     edx, 44h ; 'D'; void *
0x18004933b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180049340  nop
0x180049341  lea     rcx, [rbp+57h+var_88]
0x180049345  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004934a  jmp     short loc_180049364
0x18004934c  mov     rax, [rbp+57h+var_88]
0x180049350  mov     [rbp+57h+var_88], r13
0x180049354  mov     [r12], rax
0x180049358  lea     rcx, [rbp+57h+var_88]
0x18004935c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180049361  mov     ebx, r13d
0x180049364  lea     rcx, [rbp+57h+var_80]
0x180049368  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004936d  mov     eax, ebx
0x18004936f  mov     rcx, [rbp+57h+var_38]
0x180049373  xor     rcx, rsp; StackCookie
0x180049376  call    __security_check_cookie
0x18004937b  mov     rbx, [rsp+0C0h+arg_18]
0x180049383  add     rsp, 90h
0x18004938a  pop     r15
0x18004938c  pop     r14
0x18004938e  pop     r13
0x180049390  pop     r12
0x180049392  pop     rdi
0x180049393  pop     rsi
0x180049394  pop     rbp
0x180049395  retn
```
