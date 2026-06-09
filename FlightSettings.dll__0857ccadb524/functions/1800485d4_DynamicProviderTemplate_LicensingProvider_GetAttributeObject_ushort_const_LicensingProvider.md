# DynamicProviderTemplate<LicensingProvider>::GetAttributeObject(ushort const *,LicensingProvider * *)

- ea: `0x1800485d4`
- end: `0x18004881a`
- name: `?GetAttributeObject@?$DynamicProviderTemplate@VLicensingProvider@@@@QEAAJPEBGPEAPEAVLicensingProvider@@@Z`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800496e0`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x1800168c8`
- `0x18001b2ec`
- `0x18001c6f4`
- `0x18001ec48`
- `0x18001ec78`
- `0x1800472d0`
- `0x1800485d4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048653`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048710`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048653`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048710`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x1800486c9`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x1800486c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048667`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048724`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048667`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048724`

## string_xrefs

- `0x18004874e`: `onecore\base\flighting\flightsettings\broker\libs\ctac\DynamicProviderTemplate.h`
- `0x1800487b3`: `onecore\base\flighting\flightsettings\broker\libs\ctac\DynamicProviderTemplate.h`

## pseudocode

```c
__int64 __fastcall DynamicProviderTemplate<LicensingProvider>::GetAttributeObject(
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
  v11 = Microsoft::WRL::Details::MakeAndInitialize<LicensingProvider,LicensingProvider,Windows::Data::Json::IJsonObject *>(
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
0x1800485d4  mov     [rsp-8+arg_18], rbx
0x1800485d9  push    rbp
0x1800485da  push    rsi
0x1800485db  push    rdi
0x1800485dc  push    r12
0x1800485de  push    r13
0x1800485e0  push    r14
0x1800485e2  push    r15
0x1800485e4  lea     rbp, [rsp-27h]
0x1800485e9  sub     rsp, 90h
0x1800485f0  mov     rax, cs:__security_cookie
0x1800485f7  xor     rax, rsp
0x1800485fa  mov     [rbp+57h+var_38], rax
0x1800485fe  mov     r12, r8
0x180048601  mov     rsi, rdx
0x180048604  mov     r14, rcx
0x180048607  xor     r13d, r13d
0x18004860a  mov     [rbp+57h+var_80], r13
0x18004860e  mov     rbx, [rcx+10h]
0x180048612  mov     rax, [rbx]
0x180048615  mov     r15, [rax+40h]
0x180048619  lea     rcx, [rbp+57h+var_80]
0x18004861d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180048622  mov     [rbp+57h+length], r13d
0x180048626  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004862a  mov     rcx, rdi
0x18004862d  inc     rcx; unsigned __int64
0x180048630  cmp     [rsi+rcx*2], r13w
0x180048635  jnz     short loc_18004862D
0x180048637  lea     rdx, [rbp+57h+length]; unsigned int *
0x18004863b  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180048640  test    eax, eax
0x180048642  jns     short loc_180048659
0x180048644  xor     r9d, r9d; lpArguments
0x180048647  xor     r8d, r8d; nNumberOfArguments
0x18004864a  lea     edx, [r9+1]; dwExceptionFlags
0x18004864e  mov     ecx, 0C000000Dh; dwExceptionCode
0x180048653  call    cs:__imp_RaiseException
0x180048659  lea     r9, [rbp+57h+string]; string
0x18004865d  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180048661  mov     edx, [rbp+57h+length]; length
0x180048664  mov     rcx, rsi; sourceString
0x180048667  call    cs:__imp_WindowsCreateStringReference
0x18004866d  lea     r8, [rbp+57h+var_80]
0x180048671  mov     rdx, [rbp+57h+string]
0x180048675  mov     rcx, rbx
0x180048678  mov     rax, r15
0x18004867b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048680  test    eax, eax
0x180048682  jns     loc_180048773
0x180048688  mov     [rbp+57h+string], r13
0x18004868c  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r13
0x180048690  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r13
0x180048694  mov     r8, rdi
0x180048697  mov     rdx, rsi
0x18004869a  lea     rcx, [rbp+57h+string]
0x18004869e  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800486a3  mov     ebx, eax
0x1800486a5  test    eax, eax
0x1800486a7  jns     short loc_1800486B6
0x1800486a9  mov     r9d, eax
0x1800486ac  mov     edx, 37h ; '7'
0x1800486b1  jmp     loc_18004874E
0x1800486b6  lea     rcx, [rbp+57h+string]
0x1800486ba  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x1800486bf  mov     edx, dword ptr [rbp+57h+hstringHeader.Reserved]; cchLength
0x1800486c2  mov     rbx, [rbp+57h+string]
0x1800486c6  mov     rcx, rbx; lpsz
0x1800486c9  call    cs:__imp_CharLowerBuffW
0x1800486cf  mov     r14, [r14+10h]
0x1800486d3  mov     rax, [r14]
0x1800486d6  mov     r15, [rax+40h]
0x1800486da  lea     rcx, [rbp+57h+var_80]
0x1800486de  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800486e3  mov     [rbp+57h+length], r13d
0x1800486e7  inc     rdi
0x1800486ea  cmp     [rbx+rdi*2], r13w
0x1800486ef  jnz     short loc_1800486E7
0x1800486f1  lea     rdx, [rbp+57h+length]; unsigned int *
0x1800486f5  mov     rcx, rdi; unsigned __int64
0x1800486f8  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800486fd  test    eax, eax
0x1800486ff  jns     short loc_180048716
0x180048701  xor     r9d, r9d; lpArguments
0x180048704  xor     r8d, r8d; nNumberOfArguments
0x180048707  lea     edx, [r9+1]; dwExceptionFlags
0x18004870b  mov     ecx, 0C000000Dh; dwExceptionCode
0x180048710  call    cs:__imp_RaiseException
0x180048716  lea     r9, [rbp+57h+var_58]; string
0x18004871a  lea     r8, [rbp+57h+var_50]; hstringHeader
0x18004871e  mov     edx, [rbp+57h+length]; length
0x180048721  mov     rcx, rbx; sourceString
0x180048724  call    cs:__imp_WindowsCreateStringReference
0x18004872a  lea     r8, [rbp+57h+var_80]
0x18004872e  mov     rdx, [rbp+57h+var_58]
0x180048732  mov     rcx, r14
0x180048735  mov     rax, r15
0x180048738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004873d  test    eax, eax
0x18004873f  jns     short loc_18004876A
0x180048741  mov     ebx, 80041122h
0x180048746  mov     r9d, ebx; char *
0x180048749  mov     edx, 3Eh ; '>'; void *
0x18004874e  lea     r8, aOnecoreBaseFli_62; "onecore\\base\\flighting\\flightsetting"...
0x180048755  mov     rcx, [rbp+5Fh]; this
0x180048759  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004875e  nop
0x18004875f  lea     rcx, [rbp+57h+string]
0x180048763  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180048768  jmp     short loc_1800487E8
0x18004876a  lea     rcx, [rbp+57h+string]
0x18004876e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180048773  mov     [rbp+57h+var_88], r13
0x180048777  mov     rax, [rbp+57h+var_80]
0x18004877b  mov     qword ptr [rbp+57h+length], rax
0x18004877f  lea     rcx, [rbp+57h+var_88]
0x180048783  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180048788  lea     rdx, [rbp+57h+length]
0x18004878c  lea     rcx, [rbp+57h+var_88]
0x180048790  call    ??$MakeAndInitialize@VLicensingProvider@@V1@PEAUIJsonObject@Json@Data@Windows@@@Details@WRL@Microsoft@@YAJPEAPEAVLicensingProvider@@$$QEAPEAUIJsonObject@Json@Data@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<LicensingProvider,LicensingProvider,Windows::Data::Json::IJsonObject *>(LicensingProvider * *,Windows::Data::Json::IJsonObject * &&)
0x180048795  mov     ebx, eax
0x180048797  test    eax, eax
0x180048799  jns     short loc_1800487D0
0x18004879b  mov     rcx, [rbp+5Fh]; this
0x18004879f  mov     [rsp+0C0h+var_98], rsi; char *
0x1800487a4  lea     rax, aPropnameWs; "propName=%ws"
0x1800487ab  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x1800487b0  mov     r9d, ebx; char *
0x1800487b3  lea     r8, aOnecoreBaseFli_62; "onecore\\base\\flighting\\flightsetting"...
0x1800487ba  mov     edx, 44h ; 'D'; void *
0x1800487bf  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800487c4  nop
0x1800487c5  lea     rcx, [rbp+57h+var_88]
0x1800487c9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800487ce  jmp     short loc_1800487E8
0x1800487d0  mov     rax, [rbp+57h+var_88]
0x1800487d4  mov     [rbp+57h+var_88], r13
0x1800487d8  mov     [r12], rax
0x1800487dc  lea     rcx, [rbp+57h+var_88]
0x1800487e0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800487e5  mov     ebx, r13d
0x1800487e8  lea     rcx, [rbp+57h+var_80]
0x1800487ec  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800487f1  mov     eax, ebx
0x1800487f3  mov     rcx, [rbp+57h+var_38]
0x1800487f7  xor     rcx, rsp; StackCookie
0x1800487fa  call    __security_check_cookie
0x1800487ff  mov     rbx, [rsp+0C0h+arg_18]
0x180048807  add     rsp, 90h
0x18004880e  pop     r15
0x180048810  pop     r14
0x180048812  pop     r13
0x180048814  pop     r12
0x180048816  pop     rdi
0x180048817  pop     rsi
0x180048818  pop     rbp
0x180048819  retn
```
