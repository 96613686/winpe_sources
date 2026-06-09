# DynamicProviderTemplate<PolicyProvider>::GetAttributeObject(ushort const *,PolicyProvider * *)

- ea: `0x180048820`
- end: `0x180048a66`
- name: `?GetAttributeObject@?$DynamicProviderTemplate@VPolicyProvider@@@@QEAAJPEBGPEAPEAVPolicyProvider@@@Z`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800497d0`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x1800168c8`
- `0x18001b2ec`
- `0x18001c6f4`
- `0x18001ec48`
- `0x18001ec78`
- `0x1800473a0`
- `0x180048820`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004889f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004895c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004889f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004895c`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180048915`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180048915`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800488b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048970`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800488b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048970`

## string_xrefs

- `0x18004899a`: `onecore\base\flighting\flightsettings\broker\libs\ctac\DynamicProviderTemplate.h`
- `0x1800489ff`: `onecore\base\flighting\flightsettings\broker\libs\ctac\DynamicProviderTemplate.h`

## pseudocode

```c
__int64 __fastcall DynamicProviderTemplate<PolicyProvider>::GetAttributeObject(__int64 a1, const WCHAR *a2, _QWORD *a3)
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
  v11 = Microsoft::WRL::Details::MakeAndInitialize<PolicyProvider,PolicyProvider,Windows::Data::Json::IJsonObject *>(
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
0x180048820  mov     [rsp-8+arg_18], rbx
0x180048825  push    rbp
0x180048826  push    rsi
0x180048827  push    rdi
0x180048828  push    r12
0x18004882a  push    r13
0x18004882c  push    r14
0x18004882e  push    r15
0x180048830  lea     rbp, [rsp-27h]
0x180048835  sub     rsp, 90h
0x18004883c  mov     rax, cs:__security_cookie
0x180048843  xor     rax, rsp
0x180048846  mov     [rbp+57h+var_38], rax
0x18004884a  mov     r12, r8
0x18004884d  mov     rsi, rdx
0x180048850  mov     r14, rcx
0x180048853  xor     r13d, r13d
0x180048856  mov     [rbp+57h+var_80], r13
0x18004885a  mov     rbx, [rcx+10h]
0x18004885e  mov     rax, [rbx]
0x180048861  mov     r15, [rax+40h]
0x180048865  lea     rcx, [rbp+57h+var_80]
0x180048869  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004886e  mov     [rbp+57h+length], r13d
0x180048872  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180048876  mov     rcx, rdi
0x180048879  inc     rcx; unsigned __int64
0x18004887c  cmp     [rsi+rcx*2], r13w
0x180048881  jnz     short loc_180048879
0x180048883  lea     rdx, [rbp+57h+length]; unsigned int *
0x180048887  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18004888c  test    eax, eax
0x18004888e  jns     short loc_1800488A5
0x180048890  xor     r9d, r9d; lpArguments
0x180048893  xor     r8d, r8d; nNumberOfArguments
0x180048896  lea     edx, [r9+1]; dwExceptionFlags
0x18004889a  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004889f  call    cs:__imp_RaiseException
0x1800488a5  lea     r9, [rbp+57h+string]; string
0x1800488a9  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800488ad  mov     edx, [rbp+57h+length]; length
0x1800488b0  mov     rcx, rsi; sourceString
0x1800488b3  call    cs:__imp_WindowsCreateStringReference
0x1800488b9  lea     r8, [rbp+57h+var_80]
0x1800488bd  mov     rdx, [rbp+57h+string]
0x1800488c1  mov     rcx, rbx
0x1800488c4  mov     rax, r15
0x1800488c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800488cc  test    eax, eax
0x1800488ce  jns     loc_1800489BF
0x1800488d4  mov     [rbp+57h+string], r13
0x1800488d8  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r13
0x1800488dc  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r13
0x1800488e0  mov     r8, rdi
0x1800488e3  mov     rdx, rsi
0x1800488e6  lea     rcx, [rbp+57h+string]
0x1800488ea  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800488ef  mov     ebx, eax
0x1800488f1  test    eax, eax
0x1800488f3  jns     short loc_180048902
0x1800488f5  mov     r9d, eax
0x1800488f8  mov     edx, 37h ; '7'
0x1800488fd  jmp     loc_18004899A
0x180048902  lea     rcx, [rbp+57h+string]
0x180048906  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18004890b  mov     edx, dword ptr [rbp+57h+hstringHeader.Reserved]; cchLength
0x18004890e  mov     rbx, [rbp+57h+string]
0x180048912  mov     rcx, rbx; lpsz
0x180048915  call    cs:__imp_CharLowerBuffW
0x18004891b  mov     r14, [r14+10h]
0x18004891f  mov     rax, [r14]
0x180048922  mov     r15, [rax+40h]
0x180048926  lea     rcx, [rbp+57h+var_80]
0x18004892a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004892f  mov     [rbp+57h+length], r13d
0x180048933  inc     rdi
0x180048936  cmp     [rbx+rdi*2], r13w
0x18004893b  jnz     short loc_180048933
0x18004893d  lea     rdx, [rbp+57h+length]; unsigned int *
0x180048941  mov     rcx, rdi; unsigned __int64
0x180048944  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180048949  test    eax, eax
0x18004894b  jns     short loc_180048962
0x18004894d  xor     r9d, r9d; lpArguments
0x180048950  xor     r8d, r8d; nNumberOfArguments
0x180048953  lea     edx, [r9+1]; dwExceptionFlags
0x180048957  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004895c  call    cs:__imp_RaiseException
0x180048962  lea     r9, [rbp+57h+var_58]; string
0x180048966  lea     r8, [rbp+57h+var_50]; hstringHeader
0x18004896a  mov     edx, [rbp+57h+length]; length
0x18004896d  mov     rcx, rbx; sourceString
0x180048970  call    cs:__imp_WindowsCreateStringReference
0x180048976  lea     r8, [rbp+57h+var_80]
0x18004897a  mov     rdx, [rbp+57h+var_58]
0x18004897e  mov     rcx, r14
0x180048981  mov     rax, r15
0x180048984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048989  test    eax, eax
0x18004898b  jns     short loc_1800489B6
0x18004898d  mov     ebx, 80041122h
0x180048992  mov     r9d, ebx; char *
0x180048995  mov     edx, 3Eh ; '>'; void *
0x18004899a  lea     r8, aOnecoreBaseFli_62; "onecore\\base\\flighting\\flightsetting"...
0x1800489a1  mov     rcx, [rbp+5Fh]; this
0x1800489a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800489aa  nop
0x1800489ab  lea     rcx, [rbp+57h+string]
0x1800489af  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800489b4  jmp     short loc_180048A34
0x1800489b6  lea     rcx, [rbp+57h+string]
0x1800489ba  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800489bf  mov     [rbp+57h+var_88], r13
0x1800489c3  mov     rax, [rbp+57h+var_80]
0x1800489c7  mov     qword ptr [rbp+57h+length], rax
0x1800489cb  lea     rcx, [rbp+57h+var_88]
0x1800489cf  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800489d4  lea     rdx, [rbp+57h+length]
0x1800489d8  lea     rcx, [rbp+57h+var_88]
0x1800489dc  call    ??$MakeAndInitialize@VPolicyProvider@@V1@PEAUIJsonObject@Json@Data@Windows@@@Details@WRL@Microsoft@@YAJPEAPEAVPolicyProvider@@$$QEAPEAUIJsonObject@Json@Data@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<PolicyProvider,PolicyProvider,Windows::Data::Json::IJsonObject *>(PolicyProvider * *,Windows::Data::Json::IJsonObject * &&)
0x1800489e1  mov     ebx, eax
0x1800489e3  test    eax, eax
0x1800489e5  jns     short loc_180048A1C
0x1800489e7  mov     rcx, [rbp+5Fh]; this
0x1800489eb  mov     [rsp+0C0h+var_98], rsi; char *
0x1800489f0  lea     rax, aPropnameWs; "propName=%ws"
0x1800489f7  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x1800489fc  mov     r9d, ebx; char *
0x1800489ff  lea     r8, aOnecoreBaseFli_62; "onecore\\base\\flighting\\flightsetting"...
0x180048a06  mov     edx, 44h ; 'D'; void *
0x180048a0b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180048a10  nop
0x180048a11  lea     rcx, [rbp+57h+var_88]
0x180048a15  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180048a1a  jmp     short loc_180048A34
0x180048a1c  mov     rax, [rbp+57h+var_88]
0x180048a20  mov     [rbp+57h+var_88], r13
0x180048a24  mov     [r12], rax
0x180048a28  lea     rcx, [rbp+57h+var_88]
0x180048a2c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180048a31  mov     ebx, r13d
0x180048a34  lea     rcx, [rbp+57h+var_80]
0x180048a38  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180048a3d  mov     eax, ebx
0x180048a3f  mov     rcx, [rbp+57h+var_38]
0x180048a43  xor     rcx, rsp; StackCookie
0x180048a46  call    __security_check_cookie
0x180048a4b  mov     rbx, [rsp+0C0h+arg_18]
0x180048a53  add     rsp, 90h
0x180048a5a  pop     r15
0x180048a5c  pop     r14
0x180048a5e  pop     r13
0x180048a60  pop     r12
0x180048a62  pop     rdi
0x180048a63  pop     rsi
0x180048a64  pop     rbp
0x180048a65  retn
```
