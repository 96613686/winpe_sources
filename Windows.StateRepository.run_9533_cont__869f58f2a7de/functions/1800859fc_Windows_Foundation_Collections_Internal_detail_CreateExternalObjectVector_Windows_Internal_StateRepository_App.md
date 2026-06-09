# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *>,0> * *)

- ea: `0x1800859fc`
- end: `0x180085c69`
- name: `??$CreateExternalObjectVector@VAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@V?$AgileVector@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAppUriHandlerLauncherInfo@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `621`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180084ce0`
- `0x1800853e0`
- `0x18014b0c0`
- `0x1801d273c`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x1800859fc`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180085a64`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180085aab`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180085af2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180085b99`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180085a64`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180085aab`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180085af2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180085b99`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180085bb0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180085bb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180085a4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180085a96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180085add`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180085b83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180085a4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180085a96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180085add`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180085b83`

## string_xrefs

- `0x180085a8f`: `Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.AppUriHandlerLauncherInfo>`
- `0x180085a48`: `Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.AppUriHandlerLauncherInfo>`
- `0x180085ad6`: `Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.AppUriHandlerLauncherInfo>`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppUriHandlerLauncherInfo *>,0>>(
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
  __int64 v14; // rcx
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v19; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v20[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v21; // [rsp+48h] [rbp-B8h]
  GUID v22; // [rsp+58h] [rbp-A8h]
  GUID v23; // [rsp+68h] [rbp-98h]
  GUID v24; // [rsp+78h] [rbp-88h]
  GUID v25; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v28; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v29; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v30; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v31; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v32; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v33; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x64u);
  v4 = v3 - 1;
  if ( v3 > 0x64 )
    v4 = 100;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.AppUriHandlerLauncherInfo>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v29 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x68u);
  v7 = v6 - 1;
  if ( v6 > 0x68 )
    v7 = 104;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.AppUriHandlerLauncherInfo>",
         v7,
         &v28,
         &v29);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x66u);
  v10 = v9 - 1;
  if ( v9 > 0x66 )
    v10 = 102;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.AppUriHandlerLauncherInfo>",
          v10,
          &v30,
          &v31);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v20[0] = string;
  v20[1] = v29;
  v20[2] = v31;
  v21 = GUID_d814470d_0c54_4f90_9853_f51845a90be2;
  v22 = GUID_083e2667_5a27_5f40_bee2_e470c9902f4c;
  v23 = GUID_c338a4da_6bcb_54c1_aa44_9ee9087ca23b;
  v24 = GUID_f0990f7b_7ae4_5b95_af92_4c1e39dec69a;
  v25 = GUID_1cc0a786_0b43_5f29_9d0e_672c5a51616b;
  v18 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
  v33 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v32, &v33);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v33, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v18);
  if ( ActivationFactory < 0 )
  {
    v14 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return (unsigned int)ActivationFactory;
  }
  v19 = 0;
  v16 = v18;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v16, v20, &v19);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
    return (unsigned int)ActivationFactory;
  }
  v17 = v19;
  v19 = 0;
  *a2 = v17;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
  return 0;
}

```

## disassembly

```asm
0x1800859fc  mov     [rsp-8+arg_0], rbx
0x180085a01  mov     [rsp-8+arg_10], rdi
0x180085a06  push    rbp
0x180085a07  lea     rbp, [rsp-30h]
0x180085a0c  sub     rsp, 130h
0x180085a13  mov     rax, cs:__security_cookie
0x180085a1a  xor     rax, rsp
0x180085a1d  mov     [rbp+30h+var_10], rax
0x180085a21  mov     rdi, rdx
0x180085a24  mov     [rbp+30h+string], 0
0x180085a2c  mov     ebx, 64h ; 'd'
0x180085a31  mov     ecx, ebx; unsigned int
0x180085a33  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180085a38  lea     edx, [rax-1]
0x180085a3b  cmp     eax, ebx
0x180085a3d  cmova   edx, ebx; length
0x180085a40  lea     r9, [rbp+30h+string]; string
0x180085a44  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180085a48  lea     rcx, aWindowsFoundat_184; "Windows.Foundation.Collections.IVector`"...
0x180085a4f  call    cs:__imp_WindowsCreateStringReference
0x180085a55  test    eax, eax
0x180085a57  jns     short loc_180085A6B
0x180085a59  xor     r9d, r9d; lpArguments
0x180085a5c  xor     r8d, r8d; nNumberOfArguments
0x180085a5f  lea     edx, [rbx-63h]; dwExceptionFlags
0x180085a62  mov     ecx, eax; dwExceptionCode
0x180085a64  call    cs:__imp_RaiseException
0x180085a6a  int     3; Trap to Debugger
0x180085a6b  mov     [rbp+30h+var_58], 0
0x180085a73  mov     ebx, 68h ; 'h'
0x180085a78  mov     ecx, ebx; unsigned int
0x180085a7a  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180085a7f  lea     edx, [rax-1]
0x180085a82  cmp     eax, ebx
0x180085a84  cmova   edx, ebx; length
0x180085a87  lea     r9, [rbp+30h+var_58]; string
0x180085a8b  lea     r8, [rbp+30h+var_70]; hstringHeader
0x180085a8f  lea     rcx, aWindowsFoundat_92; "Windows.Foundation.Collections.IVectorV"...
0x180085a96  call    cs:__imp_WindowsCreateStringReference
0x180085a9c  test    eax, eax
0x180085a9e  jns     short loc_180085AB2
0x180085aa0  xor     r9d, r9d; lpArguments
0x180085aa3  xor     r8d, r8d; nNumberOfArguments
0x180085aa6  lea     edx, [rbx-67h]; dwExceptionFlags
0x180085aa9  mov     ecx, eax; dwExceptionCode
0x180085aab  call    cs:__imp_RaiseException
0x180085ab1  int     3; Trap to Debugger
0x180085ab2  mov     [rbp+30h+var_38], 0
0x180085aba  mov     ebx, 66h ; 'f'
0x180085abf  mov     ecx, ebx; unsigned int
0x180085ac1  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180085ac6  lea     edx, [rax-1]
0x180085ac9  cmp     eax, ebx
0x180085acb  cmova   edx, ebx; length
0x180085ace  lea     r9, [rbp+30h+var_38]; string
0x180085ad2  lea     r8, [rbp+30h+var_50]; hstringHeader
0x180085ad6  lea     rcx, aWindowsFoundat_32; "Windows.Foundation.Collections.IIterato"...
0x180085add  call    cs:__imp_WindowsCreateStringReference
0x180085ae3  test    eax, eax
0x180085ae5  jns     short loc_180085AF9
0x180085ae7  xor     r9d, r9d; lpArguments
0x180085aea  xor     r8d, r8d; nNumberOfArguments
0x180085aed  lea     edx, [rbx-65h]; dwExceptionFlags
0x180085af0  mov     ecx, eax; dwExceptionCode
0x180085af2  call    cs:__imp_RaiseException
0x180085af8  int     3; Trap to Debugger
0x180085af9  mov     rax, [rbp+30h+string]
0x180085afd  mov     [rsp+130h+var_100], rax
0x180085b02  mov     rax, [rbp+30h+var_58]
0x180085b06  mov     [rsp+130h+var_F8], rax
0x180085b0b  mov     rax, [rbp+30h+var_38]
0x180085b0f  mov     [rsp+130h+var_F0], rax
0x180085b14  movups  xmm0, xmmword ptr cs:_GUID_d814470d_0c54_4f90_9853_f51845a90be2.Data1
0x180085b1b  movdqu  [rsp+130h+var_E8], xmm0
0x180085b21  movups  xmm1, xmmword ptr cs:_GUID_083e2667_5a27_5f40_bee2_e470c9902f4c.Data1
0x180085b28  movdqu  [rsp+130h+var_D8], xmm1
0x180085b2e  movups  xmm0, xmmword ptr cs:_GUID_c338a4da_6bcb_54c1_aa44_9ee9087ca23b.Data1
0x180085b35  movdqu  [rsp+130h+var_C8], xmm0
0x180085b3b  movups  xmm1, xmmword ptr cs:_GUID_f0990f7b_7ae4_5b95_af92_4c1e39dec69a.Data1
0x180085b42  movdqu  [rsp+130h+var_B8], xmm1
0x180085b48  movups  xmm0, xmmword ptr cs:_GUID_1cc0a786_0b43_5f29_9d0e_672c5a51616b.Data1
0x180085b4f  movdqu  [rbp+30h+var_A8], xmm0
0x180085b54  mov     [rsp+130h+var_110], 0
0x180085b5d  lea     rcx, [rsp+130h+var_110]
0x180085b62  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180085b67  mov     [rbp+30h+var_18], 0
0x180085b6f  lea     r9, [rbp+30h+var_18]; string
0x180085b73  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180085b77  mov     edx, 2Ch ; ','; length
0x180085b7c  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180085b83  call    cs:__imp_WindowsCreateStringReference
0x180085b89  test    eax, eax
0x180085b8b  jns     short loc_180085BA0
0x180085b8d  xor     r9d, r9d; lpArguments
0x180085b90  xor     r8d, r8d; nNumberOfArguments
0x180085b93  lea     edx, [r9+1]; dwExceptionFlags
0x180085b97  mov     ecx, eax; dwExceptionCode
0x180085b99  call    cs:__imp_RaiseException
0x180085b9f  int     3; Trap to Debugger
0x180085ba0  lea     r8, [rsp+130h+var_110]
0x180085ba5  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180085bac  mov     rcx, [rbp+30h+var_18]
0x180085bb0  call    cs:__imp_RoGetActivationFactory
0x180085bb6  mov     ebx, eax
0x180085bb8  test    eax, eax
0x180085bba  jns     short loc_180085BE0
0x180085bbc  mov     rcx, [rsp+130h+var_110]
0x180085bc1  test    rcx, rcx
0x180085bc4  jz      short loc_180085BDC
0x180085bc6  mov     [rsp+130h+var_110], 0
0x180085bcf  mov     rdx, [rcx]
0x180085bd2  mov     rax, [rdx+10h]
0x180085bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085bdb  nop
0x180085bdc  mov     eax, ebx
0x180085bde  jmp     short loc_180085C48
0x180085be0  mov     [rsp+130h+var_108], 0
0x180085be9  mov     rbx, [rsp+130h+var_110]
0x180085bee  lea     rcx, [rsp+130h+var_108]
0x180085bf3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180085bf8  lea     r8, [rsp+130h+var_108]
0x180085bfd  lea     rdx, [rsp+130h+var_100]
0x180085c02  mov     rcx, rbx
0x180085c05  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x180085c0a  mov     ebx, eax
0x180085c0c  lea     rcx, [rsp+130h+var_108]
0x180085c11  test    eax, eax
0x180085c13  jns     short loc_180085C26
0x180085c15  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180085c1a  lea     rcx, [rsp+130h+var_110]
0x180085c1f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180085c24  jmp     short loc_180085BDC
0x180085c26  mov     rax, [rsp+130h+var_108]
0x180085c2b  mov     [rsp+130h+var_108], 0
0x180085c34  mov     [rdi], rax
0x180085c37  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180085c3c  lea     rcx, [rsp+130h+var_110]
0x180085c41  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180085c46  xor     eax, eax
0x180085c48  mov     rcx, [rbp+30h+var_10]
0x180085c4c  xor     rcx, rsp; StackCookie
0x180085c4f  call    __security_check_cookie
0x180085c54  lea     r11, [rsp+130h+var_s0]
0x180085c5c  mov     rbx, [r11+10h]
0x180085c60  mov     rdi, [r11+20h]
0x180085c64  mov     rsp, r11
0x180085c67  pop     rbp
0x180085c68  retn
```
