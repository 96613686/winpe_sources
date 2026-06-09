# CreateMrtRandomAccessStreamReferenceInternal

- ea: `0x180009af8`
- end: `0x180009d52`
- name: `CreateMrtRandomAccessStreamReferenceInternal`
- size: `602`
- prototype: `__int64 __fastcall(PCWSTR sourceString, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a54c`

## callees

- `0x180001d60`
- `0x180006224`
- `0x1800071a4`
- `0x1800096e8`
- `0x180009af8`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009b5d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009be8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009b5d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009be8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180009b43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180009bfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180009b43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180009bfb`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180009b7e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180009b7e`

## string_xrefs

- `0x180009b8e`: `onecore\base\appmodel\staterepository\winrt\broker\lib\localize.cpp`
- `0x180009c1e`: `onecore\base\appmodel\staterepository\winrt\broker\lib\localize.cpp`
- `0x180009cae`: `onecore\base\appmodel\staterepository\winrt\broker\lib\localize.cpp`
- `0x180009cfc`: `onecore\base\appmodel\staterepository\winrt\broker\lib\localize.cpp`

## pseudocode

```c
__int64 __fastcall CreateMrtRandomAccessStreamReferenceInternal(PCWSTR sourceString, _QWORD *a2)
{
  HSTRING v4; // rbx
  int ActivationFactory; // eax
  int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING, __int64 *); // r15
  unsigned __int64 v9; // rbx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v13)(_QWORD, GUID *, __int64 *); // rdi
  int v14; // eax
  __int64 v16; // [rsp+20h] [rbp-50h] BYREF
  __int64 v17; // [rsp+28h] [rbp-48h] BYREF
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-40h] BYREF
  __int64 v19; // [rsp+38h] [rbp-38h] BYREF
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  *a2 = 0;
  v19 = 0;
  if ( WindowsCreateStringReference(L"Windows.Storage.StorageFile", 0x1Bu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v4 = string;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v19);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_5984c710_daf2_43c8_8bb4_a4d3eacfd03f, &v19);
  v6 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v7 = v19;
    v16 = 0;
    v8 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v19 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v16);
    v9 = -1;
    do
      ++v9;
    while ( sourceString[v9] );
    if ( v9 > 0xFFFFFFFF )
    {
      LODWORD(v9) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(sourceString, v9, &hstringHeader, &string);
    v10 = v8(v7, string, &v16);
    v6 = v10;
    if ( v10 >= 0 )
    {
      v18 = 0;
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v18);
      v11 = v16;
      v6 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(v16);
      if ( v6 < 0
        || (v6 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v11 + 64LL))(
                   v11,
                   &v18),
            v6 < 0) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCA,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\localize.cpp",
          (const char *)(unsigned int)v6,
          v16);
      }
      else
      {
        v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v18;
        v17 = 0;
        v13 = **v18;
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v17);
        v14 = v13(v12, &GUID_33ee3134_1dd6_4e3a_8067_d1c162e8642b, &v17);
        v6 = v14;
        if ( v14 >= 0 )
        {
          *a2 = v17;
          v17 = 0;
          Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v17);
          Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v18);
          Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v16);
          v6 = 0;
          goto LABEL_19;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCD,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\localize.cpp",
          (const char *)(unsigned int)v14,
          v16);
        Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v17);
      }
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v18);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC7,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\localize.cpp",
        (const char *)(unsigned int)v10,
        v16);
    }
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v16);
    goto LABEL_19;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC4,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\broker\\lib\\localize.cpp",
    (const char *)(unsigned int)ActivationFactory,
    v16);
LABEL_19:
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v19);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009af8  mov     [rsp-28h+arg_10], rbx
0x180009afd  mov     [rsp-28h+arg_18], rsi
0x180009b02  push    rbp
0x180009b03  push    rdi
0x180009b04  push    r12
0x180009b06  push    r14
0x180009b08  push    r15
0x180009b0a  mov     rbp, rsp
0x180009b0d  sub     rsp, 70h
0x180009b11  mov     rax, cs:__security_cookie
0x180009b18  xor     rax, rsp
0x180009b1b  mov     [rbp+var_10], rax
0x180009b1f  xor     r12d, r12d
0x180009b22  lea     r9, [rbp+string]; string
0x180009b26  mov     rsi, rdx
0x180009b29  mov     [rdx], r12
0x180009b2c  mov     r14, rcx
0x180009b2f  mov     [rbp+var_38], r12
0x180009b33  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180009b37  lea     edx, [r12+1Bh]; length
0x180009b3c  lea     rcx, ?RuntimeClass_Windows_Storage_StorageFile@@3QBGB; "Windows.Storage.StorageFile"
0x180009b43  call    cs:__imp_WindowsCreateStringReference
0x180009b49  test    eax, eax
0x180009b4b  jns     short loc_180009B63
0x180009b4d  xor     r9d, r9d; lpArguments
0x180009b50  lea     edx, [r12+1]; dwExceptionFlags
0x180009b55  xor     r8d, r8d; nNumberOfArguments
0x180009b58  mov     ecx, 0C000000Dh; dwExceptionCode
0x180009b5d  call    cs:__imp_RaiseException
0x180009b63  mov     rbx, [rbp+string]
0x180009b67  lea     rcx, [rbp+var_38]
0x180009b6b  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180009b70  lea     r8, [rbp+var_38]
0x180009b74  mov     rcx, rbx
0x180009b77  lea     rdx, _GUID_5984c710_daf2_43c8_8bb4_a4d3eacfd03f
0x180009b7e  call    cs:__imp_RoGetActivationFactory
0x180009b84  mov     ebx, eax
0x180009b86  test    eax, eax
0x180009b88  jns     short loc_180009BA7
0x180009b8a  mov     rcx, [rbp+28h]; this
0x180009b8e  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x180009b95  mov     r9d, eax; char *
0x180009b98  mov     edx, 0C4h; void *
0x180009b9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009ba2  jmp     loc_180009D22
0x180009ba7  mov     rdi, [rbp+var_38]
0x180009bab  lea     rcx, [rbp+var_50]
0x180009baf  mov     [rbp+var_50], r12
0x180009bb3  mov     rax, [rdi]
0x180009bb6  mov     r15, [rax+30h]
0x180009bba  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180009bbf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009bc3  inc     rbx
0x180009bc6  cmp     [r14+rbx*2], r12w
0x180009bcb  jnz     short loc_180009BC3
0x180009bcd  mov     eax, 0FFFFFFFFh
0x180009bd2  cmp     rbx, rax
0x180009bd5  jbe     short loc_180009BEE
0x180009bd7  xor     r9d, r9d; lpArguments
0x180009bda  xor     r8d, r8d; nNumberOfArguments
0x180009bdd  mov     ecx, 0C000000Dh; dwExceptionCode
0x180009be2  mov     ebx, eax
0x180009be4  lea     edx, [r9+1]; dwExceptionFlags
0x180009be8  call    cs:__imp_RaiseException
0x180009bee  lea     r9, [rbp+string]; string
0x180009bf2  mov     edx, ebx; length
0x180009bf4  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180009bf8  mov     rcx, r14; sourceString
0x180009bfb  call    cs:__imp_WindowsCreateStringReference
0x180009c01  mov     rdx, [rbp+string]
0x180009c05  lea     r8, [rbp+var_50]
0x180009c09  mov     rcx, rdi
0x180009c0c  mov     rax, r15
0x180009c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c14  mov     ebx, eax
0x180009c16  test    eax, eax
0x180009c18  jns     short loc_180009C37
0x180009c1a  mov     rcx, [rbp+28h]; this
0x180009c1e  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x180009c25  mov     r9d, eax; char *
0x180009c28  mov     edx, 0C7h; void *
0x180009c2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009c32  jmp     loc_180009D19
0x180009c37  lea     rcx, [rbp+var_40]
0x180009c3b  mov     [rbp+var_40], r12
0x180009c3f  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180009c44  mov     rdi, [rbp+var_50]
0x180009c48  mov     rcx, rdi
0x180009c4b  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)
0x180009c50  mov     ebx, eax
0x180009c52  test    eax, eax
0x180009c54  js      loc_180009CF8
0x180009c5a  mov     rax, [rdi]
0x180009c5d  lea     rdx, [rbp+var_40]
0x180009c61  mov     rcx, rdi
0x180009c64  mov     rax, [rax+40h]
0x180009c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c6d  mov     ebx, eax
0x180009c6f  test    eax, eax
0x180009c71  js      loc_180009CF8
0x180009c77  mov     rbx, [rbp+var_40]
0x180009c7b  lea     rcx, [rbp+var_48]
0x180009c7f  mov     [rbp+var_48], r12
0x180009c83  mov     rax, [rbx]
0x180009c86  mov     rdi, [rax]
0x180009c89  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180009c8e  lea     r8, [rbp+var_48]
0x180009c92  mov     rcx, rbx
0x180009c95  lea     rdx, _GUID_33ee3134_1dd6_4e3a_8067_d1c162e8642b
0x180009c9c  mov     rax, rdi
0x180009c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ca4  mov     ebx, eax
0x180009ca6  test    eax, eax
0x180009ca8  jns     short loc_180009CCD
0x180009caa  mov     rcx, [rbp+28h]; this
0x180009cae  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x180009cb5  mov     r9d, eax; char *
0x180009cb8  mov     edx, 0CDh; void *
0x180009cbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009cc2  lea     rcx, [rbp+var_48]
0x180009cc6  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180009ccb  jmp     short loc_180009D10
0x180009ccd  mov     rax, [rbp+var_48]
0x180009cd1  lea     rcx, [rbp+var_48]
0x180009cd5  mov     [rsi], rax
0x180009cd8  mov     [rbp+var_48], r12
0x180009cdc  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180009ce1  lea     rcx, [rbp+var_40]
0x180009ce5  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180009cea  lea     rcx, [rbp+var_50]
0x180009cee  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180009cf3  mov     ebx, r12d
0x180009cf6  jmp     short loc_180009D22
0x180009cf8  mov     rcx, [rbp+28h]; this
0x180009cfc  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x180009d03  mov     r9d, ebx; char *
0x180009d06  mov     edx, 0CAh; void *
0x180009d0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009d10  lea     rcx, [rbp+var_40]
0x180009d14  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180009d19  lea     rcx, [rbp+var_50]
0x180009d1d  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180009d22  lea     rcx, [rbp+var_38]
0x180009d26  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x180009d2b  mov     eax, ebx
0x180009d2d  mov     rcx, [rbp+var_10]
0x180009d31  xor     rcx, rsp; StackCookie
0x180009d34  call    __security_check_cookie
0x180009d39  lea     r11, [rsp+70h+var_s0]
0x180009d3e  mov     rbx, [r11+40h]
0x180009d42  mov     rsi, [r11+48h]
0x180009d46  mov     rsp, r11
0x180009d49  pop     r15
0x180009d4b  pop     r14
0x180009d4d  pop     r12
0x180009d4f  pop     rdi
0x180009d50  pop     rbp
0x180009d51  retn
```
