# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::AppExtension,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppExtension *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppExtension *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppExtension *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppExtension *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppExtension *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppExtension *>,0> * *)

- ea: `0x18002f3ec`
- end: `0x18002f6ab`
- name: `??$CreateExternalObjectVector@VAppExtension@StateRepository@Internal@Windows@@V?$AgileVector@PEAVAppExtension@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAppExtension@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAppExtension@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVAppExtension@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAppExtension@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAppExtension@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `703`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002f290`
- `0x1800b9980`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x18002f3ec`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f66b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f67e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f691`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f6a4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f66b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f67e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f691`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f6a4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002f565`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002f565`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f43f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f478`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f4b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f547`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f43f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f478`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f4b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f547`

## string_xrefs

- `0x18002f438`: `Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.AppExtension>`
- `0x18002f471`: `Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.AppExtension>`
- `0x18002f4aa`: `Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.AppExtension>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::AppExtension,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppExtension *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppExtension *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppExtension *>,0>>(
        __int64 a1,
        _QWORD *a2)
{
  unsigned int v3; // eax
  UINT32 v4; // edx
  HRESULT v5; // eax
  unsigned int v6; // eax
  UINT32 v7; // edx
  HRESULT v8; // eax
  unsigned int v9; // eax
  UINT32 v10; // edx
  HRESULT v11; // eax
  HRESULT v12; // eax
  int ActivationFactory; // ebx
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v22; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v23[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v24; // [rsp+48h] [rbp-B8h]
  GUID v25; // [rsp+58h] [rbp-A8h]
  GUID v26; // [rsp+68h] [rbp-98h]
  GUID v27; // [rsp+78h] [rbp-88h]
  GUID v28; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v31; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v32; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v33; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v34; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v35; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v36; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x57u);
  v4 = v3 - 1;
  if ( v3 > 0x57 )
    v4 = 87;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.AppExtension>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Bu);
  v7 = v6 - 1;
  if ( v6 > 0x5B )
    v7 = 91;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.AppExtension>",
         v7,
         &v31,
         &v32);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v34 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x59u);
  v10 = v9 - 1;
  if ( v9 > 0x59 )
    v10 = 89;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.AppExtension>",
          v10,
          &v33,
          &v34);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v23[0] = string;
  v23[1] = v32;
  v23[2] = v34;
  v24 = GUID_44b8ea5c_b3ff_4e34_afaf_ebfa9cddaebe;
  v25 = GUID_1a472ac1_a630_527a_8775_845fa775ae66;
  v26 = GUID_6ee39249_1e54_55b9_9171_97e8c6778a96;
  v27 = GUID_cdc86650_cd73_5231_b226_53d54c5d91f6;
  v28 = GUID_ac99df1e_e2b9_50a2_bd98_14bae4bd6957;
  v21 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v36 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v35, &v36);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    JUMPOUT(0x18002F6AALL);
  }
  ActivationFactory = RoGetActivationFactory(v36, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v21);
  if ( ActivationFactory < 0 )
  {
    v20 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return (unsigned int)ActivationFactory;
  }
  v22 = 0;
  v14 = v21;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v14, v23, &v22);
  if ( ActivationFactory < 0 )
  {
    v18 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    return (unsigned int)ActivationFactory;
  }
  v15 = v22;
  v22 = 0;
  *a2 = v15;
  v16 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  return 0;
}

```

## disassembly

```asm
0x18002f3ec  mov     [rsp-8+arg_0], rbx
0x18002f3f1  mov     [rsp-8+arg_10], rdi
0x18002f3f6  push    rbp
0x18002f3f7  lea     rbp, [rsp-30h]
0x18002f3fc  sub     rsp, 130h
0x18002f403  mov     rax, cs:__security_cookie
0x18002f40a  xor     rax, rsp
0x18002f40d  mov     [rbp+30h+var_10], rax
0x18002f411  mov     rdi, rdx
0x18002f414  mov     [rbp+30h+string], 0
0x18002f41c  mov     ebx, 57h ; 'W'
0x18002f421  mov     ecx, ebx; unsigned int
0x18002f423  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002f428  lea     edx, [rax-1]
0x18002f42b  cmp     eax, ebx
0x18002f42d  cmova   edx, ebx; length
0x18002f430  lea     r9, [rbp+30h+string]; string
0x18002f434  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18002f438  lea     rcx, aWindowsFoundat_27; "Windows.Foundation.Collections.IVector`"...
0x18002f43f  call    cs:__imp_WindowsCreateStringReference
0x18002f445  test    eax, eax
0x18002f447  js      loc_18002F65F
0x18002f44d  mov     [rbp+30h+var_58], 0
0x18002f455  mov     ebx, 5Bh ; '['
0x18002f45a  mov     ecx, ebx; unsigned int
0x18002f45c  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002f461  lea     edx, [rax-1]
0x18002f464  cmp     eax, ebx
0x18002f466  cmova   edx, ebx; length
0x18002f469  lea     r9, [rbp+30h+var_58]; string
0x18002f46d  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18002f471  lea     rcx, aWindowsFoundat_206; "Windows.Foundation.Collections.IVectorV"...
0x18002f478  call    cs:__imp_WindowsCreateStringReference
0x18002f47e  test    eax, eax
0x18002f480  js      loc_18002F672
0x18002f486  mov     [rbp+30h+var_38], 0
0x18002f48e  mov     ebx, 59h ; 'Y'
0x18002f493  mov     ecx, ebx; unsigned int
0x18002f495  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002f49a  lea     edx, [rax-1]
0x18002f49d  cmp     eax, ebx
0x18002f49f  cmova   edx, ebx; length
0x18002f4a2  lea     r9, [rbp+30h+var_38]; string
0x18002f4a6  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18002f4aa  lea     rcx, aWindowsFoundat_22; "Windows.Foundation.Collections.IIterato"...
0x18002f4b1  call    cs:__imp_WindowsCreateStringReference
0x18002f4b7  test    eax, eax
0x18002f4b9  js      loc_18002F685
0x18002f4bf  mov     rax, [rbp+30h+string]
0x18002f4c3  mov     [rsp+130h+var_100], rax
0x18002f4c8  mov     rax, [rbp+30h+var_58]
0x18002f4cc  mov     [rsp+130h+var_F8], rax
0x18002f4d1  mov     rax, [rbp+30h+var_38]
0x18002f4d5  mov     [rsp+130h+var_F0], rax
0x18002f4da  movups  xmm0, xmmword ptr cs:_GUID_44b8ea5c_b3ff_4e34_afaf_ebfa9cddaebe.Data1
0x18002f4e1  movdqu  [rsp+130h+var_E8], xmm0
0x18002f4e7  movups  xmm1, xmmword ptr cs:_GUID_1a472ac1_a630_527a_8775_845fa775ae66.Data1
0x18002f4ee  movdqu  [rsp+130h+var_D8], xmm1
0x18002f4f4  movups  xmm0, xmmword ptr cs:_GUID_6ee39249_1e54_55b9_9171_97e8c6778a96.Data1
0x18002f4fb  movdqu  [rsp+130h+var_C8], xmm0
0x18002f501  movups  xmm1, xmmword ptr cs:_GUID_cdc86650_cd73_5231_b226_53d54c5d91f6.Data1
0x18002f508  movdqu  [rsp+130h+var_B8], xmm1
0x18002f50e  movups  xmm0, xmmword ptr cs:_GUID_ac99df1e_e2b9_50a2_bd98_14bae4bd6957.Data1
0x18002f515  movdqu  [rbp+30h+var_A8], xmm0
0x18002f51a  mov     [rsp+130h+var_110], 0
0x18002f523  lea     rcx, [rsp+130h+var_110]
0x18002f528  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002f52d  mov     [rbp+30h+var_18], 0
0x18002f535  lea     r9, [rbp+30h+var_18]; string
0x18002f539  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18002f53d  lea     edx, [rbx-2Dh]; length
0x18002f540  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18002f547  call    cs:__imp_WindowsCreateStringReference
0x18002f54d  test    eax, eax
0x18002f54f  js      loc_18002F698
0x18002f555  lea     r8, [rsp+130h+var_110]
0x18002f55a  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18002f561  mov     rcx, [rbp+30h+var_18]
0x18002f565  call    cs:__imp_RoGetActivationFactory
0x18002f56b  mov     ebx, eax
0x18002f56d  test    eax, eax
0x18002f56f  js      loc_18002F63D
0x18002f575  mov     [rsp+130h+var_108], 0
0x18002f57e  mov     rbx, [rsp+130h+var_110]
0x18002f583  lea     rcx, [rsp+130h+var_108]
0x18002f588  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002f58d  lea     r8, [rsp+130h+var_108]
0x18002f592  lea     rdx, [rsp+130h+var_100]
0x18002f597  mov     rcx, rbx
0x18002f59a  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18002f59f  mov     ebx, eax
0x18002f5a1  test    eax, eax
0x18002f5a3  js      short loc_18002F5F9
0x18002f5a5  mov     rax, [rsp+130h+var_108]
0x18002f5aa  mov     [rsp+130h+var_108], 0
0x18002f5b3  mov     [rdi], rax
0x18002f5b6  mov     rcx, [rsp+130h+var_110]
0x18002f5bb  test    rcx, rcx
0x18002f5be  jz      short loc_18002F5D6
0x18002f5c0  mov     [rsp+130h+var_110], 0
0x18002f5c9  mov     rax, [rcx]
0x18002f5cc  mov     rax, [rax+10h]
0x18002f5d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5d5  nop
0x18002f5d6  xor     eax, eax
0x18002f5d8  mov     rcx, [rbp+30h+var_10]
0x18002f5dc  xor     rcx, rsp; StackCookie
0x18002f5df  call    __security_check_cookie
0x18002f5e4  lea     r11, [rsp+130h+var_s0]
0x18002f5ec  mov     rbx, [r11+10h]
0x18002f5f0  mov     rdi, [r11+20h]
0x18002f5f4  mov     rsp, r11
0x18002f5f7  pop     rbp
0x18002f5f8  retn
0x18002f5f9  mov     rcx, [rsp+130h+var_108]
0x18002f5fe  test    rcx, rcx
0x18002f601  jz      short loc_18002F619
0x18002f603  mov     [rsp+130h+var_108], 0
0x18002f60c  mov     rdx, [rcx]
0x18002f60f  mov     rax, [rdx+10h]
0x18002f613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f618  nop
0x18002f619  mov     rcx, [rsp+130h+var_110]
0x18002f61e  test    rcx, rcx
0x18002f621  jz      short loc_18002F639
0x18002f623  mov     [rsp+130h+var_110], 0
0x18002f62c  mov     rax, [rcx]
0x18002f62f  mov     rax, [rax+10h]
0x18002f633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f638  nop
0x18002f639  mov     eax, ebx
0x18002f63b  jmp     short loc_18002F5D8
0x18002f63d  mov     rcx, [rsp+130h+var_110]
0x18002f642  test    rcx, rcx
0x18002f645  jz      short loc_18002F65D
0x18002f647  mov     [rsp+130h+var_110], 0
0x18002f650  mov     rdx, [rcx]
0x18002f653  mov     rax, [rdx+10h]
0x18002f657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f65c  nop
0x18002f65d  jmp     short loc_18002F639
0x18002f65f  xor     r9d, r9d; lpArguments
0x18002f662  xor     r8d, r8d; nNumberOfArguments
0x18002f665  lea     edx, [r9+1]; dwExceptionFlags
0x18002f669  mov     ecx, eax; dwExceptionCode
0x18002f66b  call    cs:__imp_RaiseException
0x18002f671  int     3; Trap to Debugger
0x18002f672  xor     r9d, r9d; lpArguments
0x18002f675  xor     r8d, r8d; nNumberOfArguments
0x18002f678  lea     edx, [r9+1]; dwExceptionFlags
0x18002f67c  mov     ecx, eax; dwExceptionCode
0x18002f67e  call    cs:__imp_RaiseException
0x18002f684  int     3; Trap to Debugger
0x18002f685  xor     r9d, r9d; lpArguments
0x18002f688  xor     r8d, r8d; nNumberOfArguments
0x18002f68b  lea     edx, [r9+1]; dwExceptionFlags
0x18002f68f  mov     ecx, eax; dwExceptionCode
0x18002f691  call    cs:__imp_RaiseException
0x18002f697  int     3; Trap to Debugger
0x18002f698  xor     r9d, r9d; lpArguments
0x18002f69b  xor     r8d, r8d; nNumberOfArguments
0x18002f69e  lea     edx, [r9+1]; dwExceptionFlags
0x18002f6a2  mov     ecx, eax; dwExceptionCode
0x18002f6a4  call    cs:__imp_RaiseException
```
