# DynamicProviderTemplate<FileVerProvider>::GetAttributeObject(ushort const *,FileVerProvider * *)

- ea: `0x180048388`
- end: `0x1800485ce`
- name: `?GetAttributeObject@?$DynamicProviderTemplate@VFileVerProvider@@@@QEAAJPEBGPEAPEAVFileVerProvider@@@Z`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800495f0`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x1800168c8`
- `0x18001b2ec`
- `0x18001c6f4`
- `0x18001ec48`
- `0x18001ec78`
- `0x180047200`
- `0x180048388`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048407`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800484c4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180048407`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800484c4`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18004847d`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18004847d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004841b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800484d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004841b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800484d8`

## string_xrefs

- `0x180048502`: `onecore\base\flighting\flightsettings\broker\libs\ctac\DynamicProviderTemplate.h`
- `0x180048567`: `onecore\base\flighting\flightsettings\broker\libs\ctac\DynamicProviderTemplate.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DynamicProviderTemplate<FileVerProvider>::GetAttributeObject(
        __int64 a1,
        const WCHAR *a2,
        FileVerProvider **a3)
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
  FileVerProvider *v17; // rax
  int v19; // [rsp+20h] [rbp-49h]
  UINT32 length[2]; // [rsp+30h] [rbp-39h] BYREF
  FileVerProvider *v21; // [rsp+38h] [rbp-31h] BYREF
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
  v11 = Microsoft::WRL::Details::MakeAndInitialize<FileVerProvider,FileVerProvider,Windows::Data::Json::IJsonObject *>(
          &v21,
          (struct Windows::Data::Json::IJsonObject **)length);
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
0x180048388  mov     [rsp-8+arg_18], rbx
0x18004838d  push    rbp
0x18004838e  push    rsi
0x18004838f  push    rdi
0x180048390  push    r12
0x180048392  push    r13
0x180048394  push    r14
0x180048396  push    r15
0x180048398  lea     rbp, [rsp-27h]
0x18004839d  sub     rsp, 90h
0x1800483a4  mov     rax, cs:__security_cookie
0x1800483ab  xor     rax, rsp
0x1800483ae  mov     [rbp+57h+var_38], rax
0x1800483b2  mov     r12, r8
0x1800483b5  mov     rsi, rdx
0x1800483b8  mov     r14, rcx
0x1800483bb  xor     r13d, r13d
0x1800483be  mov     [rbp+57h+var_80], r13
0x1800483c2  mov     rbx, [rcx+10h]
0x1800483c6  mov     rax, [rbx]
0x1800483c9  mov     r15, [rax+40h]
0x1800483cd  lea     rcx, [rbp+57h+var_80]
0x1800483d1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800483d6  mov     [rbp+57h+length], r13d
0x1800483da  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800483de  mov     rcx, rdi
0x1800483e1  inc     rcx; unsigned __int64
0x1800483e4  cmp     [rsi+rcx*2], r13w
0x1800483e9  jnz     short loc_1800483E1
0x1800483eb  lea     rdx, [rbp+57h+length]; unsigned int *
0x1800483ef  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800483f4  test    eax, eax
0x1800483f6  jns     short loc_18004840D
0x1800483f8  xor     r9d, r9d; lpArguments
0x1800483fb  xor     r8d, r8d; nNumberOfArguments
0x1800483fe  lea     edx, [r9+1]; dwExceptionFlags
0x180048402  mov     ecx, 0C000000Dh; dwExceptionCode
0x180048407  call    cs:__imp_RaiseException
0x18004840d  lea     r9, [rbp+57h+string]; string
0x180048411  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180048415  mov     edx, [rbp+57h+length]; length
0x180048418  mov     rcx, rsi; sourceString
0x18004841b  call    cs:__imp_WindowsCreateStringReference
0x180048421  lea     r8, [rbp+57h+var_80]
0x180048425  mov     rdx, [rbp+57h+string]
0x180048429  mov     rcx, rbx
0x18004842c  mov     rax, r15
0x18004842f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048434  test    eax, eax
0x180048436  jns     loc_180048527
0x18004843c  mov     [rbp+57h+string], r13
0x180048440  mov     qword ptr [rbp+57h+hstringHeader.Reserved], r13
0x180048444  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r13
0x180048448  mov     r8, rdi
0x18004844b  mov     rdx, rsi
0x18004844e  lea     rcx, [rbp+57h+string]
0x180048452  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180048457  mov     ebx, eax
0x180048459  test    eax, eax
0x18004845b  jns     short loc_18004846A
0x18004845d  mov     r9d, eax
0x180048460  mov     edx, 37h ; '7'
0x180048465  jmp     loc_180048502
0x18004846a  lea     rcx, [rbp+57h+string]
0x18004846e  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x180048473  mov     edx, dword ptr [rbp+57h+hstringHeader.Reserved]; cchLength
0x180048476  mov     rbx, [rbp+57h+string]
0x18004847a  mov     rcx, rbx; lpsz
0x18004847d  call    cs:__imp_CharLowerBuffW
0x180048483  mov     r14, [r14+10h]
0x180048487  mov     rax, [r14]
0x18004848a  mov     r15, [rax+40h]
0x18004848e  lea     rcx, [rbp+57h+var_80]
0x180048492  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180048497  mov     [rbp+57h+length], r13d
0x18004849b  inc     rdi
0x18004849e  cmp     [rbx+rdi*2], r13w
0x1800484a3  jnz     short loc_18004849B
0x1800484a5  lea     rdx, [rbp+57h+length]; unsigned int *
0x1800484a9  mov     rcx, rdi; unsigned __int64
0x1800484ac  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800484b1  test    eax, eax
0x1800484b3  jns     short loc_1800484CA
0x1800484b5  xor     r9d, r9d; lpArguments
0x1800484b8  xor     r8d, r8d; nNumberOfArguments
0x1800484bb  lea     edx, [r9+1]; dwExceptionFlags
0x1800484bf  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800484c4  call    cs:__imp_RaiseException
0x1800484ca  lea     r9, [rbp+57h+var_58]; string
0x1800484ce  lea     r8, [rbp+57h+var_50]; hstringHeader
0x1800484d2  mov     edx, [rbp+57h+length]; length
0x1800484d5  mov     rcx, rbx; sourceString
0x1800484d8  call    cs:__imp_WindowsCreateStringReference
0x1800484de  lea     r8, [rbp+57h+var_80]
0x1800484e2  mov     rdx, [rbp+57h+var_58]
0x1800484e6  mov     rcx, r14
0x1800484e9  mov     rax, r15
0x1800484ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800484f1  test    eax, eax
0x1800484f3  jns     short loc_18004851E
0x1800484f5  mov     ebx, 80041122h
0x1800484fa  mov     r9d, ebx; char *
0x1800484fd  mov     edx, 3Eh ; '>'; void *
0x180048502  lea     r8, aOnecoreBaseFli_62; "onecore\\base\\flighting\\flightsetting"...
0x180048509  mov     rcx, [rbp+5Fh]; this
0x18004850d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048512  nop
0x180048513  lea     rcx, [rbp+57h+string]
0x180048517  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004851c  jmp     short loc_18004859C
0x18004851e  lea     rcx, [rbp+57h+string]
0x180048522  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180048527  mov     [rbp+57h+var_88], r13
0x18004852b  mov     rax, [rbp+57h+var_80]
0x18004852f  mov     qword ptr [rbp+57h+length], rax
0x180048533  lea     rcx, [rbp+57h+var_88]
0x180048537  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18004853c  lea     rdx, [rbp+57h+length]
0x180048540  lea     rcx, [rbp+57h+var_88]
0x180048544  call    ??$MakeAndInitialize@VFileVerProvider@@V1@PEAUIJsonObject@Json@Data@Windows@@@Details@WRL@Microsoft@@YAJPEAPEAVFileVerProvider@@$$QEAPEAUIJsonObject@Json@Data@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<FileVerProvider,FileVerProvider,Windows::Data::Json::IJsonObject *>(FileVerProvider * *,Windows::Data::Json::IJsonObject * &&)
0x180048549  mov     ebx, eax
0x18004854b  test    eax, eax
0x18004854d  jns     short loc_180048584
0x18004854f  mov     rcx, [rbp+5Fh]; this
0x180048553  mov     [rsp+0C0h+var_98], rsi; char *
0x180048558  lea     rax, aPropnameWs; "propName=%ws"
0x18004855f  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180048564  mov     r9d, ebx; char *
0x180048567  lea     r8, aOnecoreBaseFli_62; "onecore\\base\\flighting\\flightsetting"...
0x18004856e  mov     edx, 44h ; 'D'; void *
0x180048573  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180048578  nop
0x180048579  lea     rcx, [rbp+57h+var_88]
0x18004857d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180048582  jmp     short loc_18004859C
0x180048584  mov     rax, [rbp+57h+var_88]
0x180048588  mov     [rbp+57h+var_88], r13
0x18004858c  mov     [r12], rax
0x180048590  lea     rcx, [rbp+57h+var_88]
0x180048594  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180048599  mov     ebx, r13d
0x18004859c  lea     rcx, [rbp+57h+var_80]
0x1800485a0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800485a5  mov     eax, ebx
0x1800485a7  mov     rcx, [rbp+57h+var_38]
0x1800485ab  xor     rcx, rsp; StackCookie
0x1800485ae  call    __security_check_cookie
0x1800485b3  mov     rbx, [rsp+0C0h+arg_18]
0x1800485bb  add     rsp, 90h
0x1800485c2  pop     r15
0x1800485c4  pop     r14
0x1800485c6  pop     r13
0x1800485c8  pop     r12
0x1800485ca  pop     rdi
0x1800485cb  pop     rsi
0x1800485cc  pop     rbp
0x1800485cd  retn
```
