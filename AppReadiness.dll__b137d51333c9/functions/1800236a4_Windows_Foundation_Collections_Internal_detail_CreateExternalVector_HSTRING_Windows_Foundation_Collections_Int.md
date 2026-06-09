# Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)

- ea: `0x1800236a4`
- end: `0x1800237cd`
- name: `??$CreateExternalVector@PEAUHSTRING__@@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@1234@@Z`
- size: `297`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180032450`
- `0x18005ac6c`
- `0x180070700`

## callees

- `0x1800236a4`
- `0x180027780`
- `0x18003e210`
- `0x180048b40`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023711`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023711`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800236fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800236fb`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180023727`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180023727`

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
0x1800236a4  mov     [rsp-8+arg_0], rbx
0x1800236a9  mov     [rsp-8+arg_10], rdi
0x1800236ae  push    rbp
0x1800236af  mov     rbp, rsp
0x1800236b2  sub     rsp, 60h
0x1800236b6  mov     rax, cs:__security_cookie
0x1800236bd  xor     rax, rsp
0x1800236c0  mov     [rbp+var_10], rax
0x1800236c4  mov     rdi, rdx
0x1800236c7  mov     qword ptr [rdx], 0
0x1800236ce  mov     [rbp+var_40], 0
0x1800236d6  lea     rcx, [rbp+var_40]
0x1800236da  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800236df  mov     [rbp+string], 0
0x1800236e7  lea     r9, [rbp+string]; string
0x1800236eb  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800236ef  mov     edx, 2Ch ; ','; length
0x1800236f4  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x1800236fb  call    cs:__imp_WindowsCreateStringReference
0x180023701  test    eax, eax
0x180023703  jns     short loc_180023718
0x180023705  xor     r9d, r9d; lpArguments
0x180023708  xor     r8d, r8d; nNumberOfArguments
0x18002370b  lea     edx, [r9+1]; dwExceptionFlags
0x18002370f  mov     ecx, eax; dwExceptionCode
0x180023711  call    cs:__imp_RaiseException
0x180023717  int     3; Trap to Debugger
0x180023718  lea     r8, [rbp+var_40]
0x18002371c  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180023723  mov     rcx, [rbp+string]
0x180023727  call    cs:__imp_RoGetActivationFactory
0x18002372d  mov     ebx, eax
0x18002372f  test    eax, eax
0x180023731  jns     short loc_180023755
0x180023733  mov     rcx, [rbp+var_40]
0x180023737  test    rcx, rcx
0x18002373a  jz      short loc_180023751
0x18002373c  mov     [rbp+var_40], 0
0x180023744  mov     rdx, [rcx]
0x180023747  mov     rax, [rdx+10h]
0x18002374b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023750  nop
0x180023751  mov     eax, ebx
0x180023753  jmp     short loc_1800237AF
0x180023755  mov     [rbp+var_38], 0
0x18002375d  mov     rbx, [rbp+var_40]
0x180023761  lea     rcx, [rbp+var_38]
0x180023765  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002376a  lea     rdx, [rbp+var_38]
0x18002376e  mov     rcx, rbx
0x180023771  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BNA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{208,{flat}}
0x180023776  mov     ebx, eax
0x180023778  lea     rcx, [rbp+var_38]
0x18002377c  test    eax, eax
0x18002377e  jns     short loc_180023790
0x180023780  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180023785  lea     rcx, [rbp+var_40]
0x180023789  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002378e  jmp     short loc_180023751
0x180023790  mov     rax, [rbp+var_38]
0x180023794  mov     [rbp+var_38], 0
0x18002379c  mov     [rdi], rax
0x18002379f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800237a4  lea     rcx, [rbp+var_40]
0x1800237a8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800237ad  xor     eax, eax
0x1800237af  mov     rcx, [rbp+var_10]
0x1800237b3  xor     rcx, rsp; StackCookie
0x1800237b6  call    __security_check_cookie
0x1800237bb  lea     r11, [rsp+60h+var_s0]
0x1800237c0  mov     rbx, [r11+10h]
0x1800237c4  mov     rdi, [r11+20h]
0x1800237c8  mov     rsp, r11
0x1800237cb  pop     rbp
0x1800237cc  retn
```
