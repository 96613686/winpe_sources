# Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)

- ea: `0x180020d90`
- end: `0x180020eb9`
- name: `??$CreateExternalVector@PEAUHSTRING__@@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@1234@@Z`
- size: `297`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000217c`

## callees

- `0x18001d0a4`
- `0x180020d90`
- `0x18002cd20`
- `0x18005369c`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020dfd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020dfd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180020e13`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180020e13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020de7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020de7`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(
        __int64 a1,
        _QWORD *a2)
{
  HRESULT v3; // eax
  int ActivationFactory; // ebx
  __int64 v5; // rcx
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // [rsp+20h] [rbp-40h] BYREF
  __int64 v10; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-18h] BYREF

  *a2 = 0;
  v9 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
  string = 0;
  v3 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &hstringHeader, &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v9);
  if ( ActivationFactory < 0 )
  {
    v5 = v9;
    if ( v9 )
    {
      v9 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    return (unsigned int)ActivationFactory;
  }
  v10 = 0;
  v7 = v9;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{208,{flat}}(v7, &v10);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
    return (unsigned int)ActivationFactory;
  }
  v8 = v10;
  v10 = 0;
  *a2 = v8;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
  return 0;
}

```

## disassembly

```asm
0x180020d90  mov     [rsp-8+arg_0], rbx
0x180020d95  mov     [rsp-8+arg_10], rdi
0x180020d9a  push    rbp
0x180020d9b  mov     rbp, rsp
0x180020d9e  sub     rsp, 60h
0x180020da2  mov     rax, cs:__security_cookie
0x180020da9  xor     rax, rsp
0x180020dac  mov     [rbp+var_10], rax
0x180020db0  mov     rdi, rdx
0x180020db3  mov     qword ptr [rdx], 0
0x180020dba  mov     [rbp+var_40], 0
0x180020dc2  lea     rcx, [rbp+var_40]
0x180020dc6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020dcb  mov     [rbp+string], 0
0x180020dd3  lea     r9, [rbp+string]; string
0x180020dd7  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180020ddb  mov     edx, 2Ch ; ','; length
0x180020de0  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180020de7  call    cs:__imp_WindowsCreateStringReference
0x180020ded  test    eax, eax
0x180020def  jns     short loc_180020E04
0x180020df1  xor     r9d, r9d; lpArguments
0x180020df4  xor     r8d, r8d; nNumberOfArguments
0x180020df7  lea     edx, [r9+1]; dwExceptionFlags
0x180020dfb  mov     ecx, eax; dwExceptionCode
0x180020dfd  call    cs:__imp_RaiseException
0x180020e03  int     3; Trap to Debugger
0x180020e04  lea     r8, [rbp+var_40]
0x180020e08  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180020e0f  mov     rcx, [rbp+string]
0x180020e13  call    cs:__imp_RoGetActivationFactory
0x180020e19  mov     ebx, eax
0x180020e1b  test    eax, eax
0x180020e1d  jns     short loc_180020E41
0x180020e1f  mov     rcx, [rbp+var_40]
0x180020e23  test    rcx, rcx
0x180020e26  jz      short loc_180020E3D
0x180020e28  mov     [rbp+var_40], 0
0x180020e30  mov     rdx, [rcx]
0x180020e33  mov     rax, [rdx+10h]
0x180020e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e3c  nop
0x180020e3d  mov     eax, ebx
0x180020e3f  jmp     short loc_180020E9B
0x180020e41  mov     [rbp+var_38], 0
0x180020e49  mov     rbx, [rbp+var_40]
0x180020e4d  lea     rcx, [rbp+var_38]
0x180020e51  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020e56  lea     rdx, [rbp+var_38]
0x180020e5a  mov     rcx, rbx
0x180020e5d  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BNA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{208,{flat}}
0x180020e62  mov     ebx, eax
0x180020e64  lea     rcx, [rbp+var_38]
0x180020e68  test    eax, eax
0x180020e6a  jns     short loc_180020E7C
0x180020e6c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020e71  lea     rcx, [rbp+var_40]
0x180020e75  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020e7a  jmp     short loc_180020E3D
0x180020e7c  mov     rax, [rbp+var_38]
0x180020e80  mov     [rbp+var_38], 0
0x180020e88  mov     [rdi], rax
0x180020e8b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020e90  lea     rcx, [rbp+var_40]
0x180020e94  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020e99  xor     eax, eax
0x180020e9b  mov     rcx, [rbp+var_10]
0x180020e9f  xor     rcx, rsp; StackCookie
0x180020ea2  call    __security_check_cookie
0x180020ea7  lea     r11, [rsp+60h+var_s0]
0x180020eac  mov     rbx, [r11+10h]
0x180020eb0  mov     rdi, [r11+20h]
0x180020eb4  mov     rsp, r11
0x180020eb7  pop     rbp
0x180020eb8  retn
```
