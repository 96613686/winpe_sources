# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::AppService,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppService *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppService *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppService *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppService *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppService *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppService *>,0> * *)

- ea: `0x1800b4a00`
- end: `0x1800b4c6d`
- name: `??$CreateExternalObjectVector@VAppService@StateRepository@Internal@Windows@@V?$AgileVector@PEAVAppService@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAppService@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAppService@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVAppService@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVAppService@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVAppService@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `621`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007c41c`
- `0x1801d2150`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x1800b4a00`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b4a68`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b4aaf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b4af6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b4b9d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b4a68`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b4aaf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b4af6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b4b9d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b4bb4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b4bb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b4a53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b4a9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b4ae1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b4b87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b4a53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b4a9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b4ae1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b4b87`

## string_xrefs

- `0x1800b4a93`: `Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.AppService>`
- `0x1800b4ada`: `Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.AppService>`
- `0x1800b4a4c`: `Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.AppService>`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::AppService,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::AppService *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::AppService *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::AppService *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x55u);
  v4 = v3 - 1;
  if ( v3 > 0x55 )
    v4 = 85;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.AppService>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v29 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x59u);
  v7 = v6 - 1;
  if ( v6 > 0x59 )
    v7 = 89;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.AppService>",
         v7,
         &v28,
         &v29);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x57u);
  v10 = v9 - 1;
  if ( v9 > 0x57 )
    v10 = 87;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.AppService>",
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
  v21 = GUID_ae655c6c_b973_45eb_aa3e_8b6467ff272f;
  v22 = GUID_6825a989_eecd_5fa9_8c07_6b7e4aaf8cd2;
  v23 = GUID_8b9ae10d_b29a_51cb_adfb_e94ad37480dd;
  v24 = GUID_f2239de4_75de_5d69_b523_07177727e395;
  v25 = GUID_cdae9f6a_2875_51a5_b70d_9e9904089dff;
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
0x1800b4a00  mov     [rsp-8+arg_0], rbx
0x1800b4a05  mov     [rsp-8+arg_10], rdi
0x1800b4a0a  push    rbp
0x1800b4a0b  lea     rbp, [rsp-30h]
0x1800b4a10  sub     rsp, 130h
0x1800b4a17  mov     rax, cs:__security_cookie
0x1800b4a1e  xor     rax, rsp
0x1800b4a21  mov     [rbp+30h+var_10], rax
0x1800b4a25  mov     rdi, rdx
0x1800b4a28  mov     [rbp+30h+string], 0
0x1800b4a30  mov     ebx, 55h ; 'U'
0x1800b4a35  mov     ecx, ebx; unsigned int
0x1800b4a37  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800b4a3c  lea     edx, [rax-1]
0x1800b4a3f  cmp     eax, ebx
0x1800b4a41  cmova   edx, ebx; length
0x1800b4a44  lea     r9, [rbp+30h+string]; string
0x1800b4a48  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x1800b4a4c  lea     rcx, aWindowsFoundat_122; "Windows.Foundation.Collections.IVector`"...
0x1800b4a53  call    cs:__imp_WindowsCreateStringReference
0x1800b4a59  test    eax, eax
0x1800b4a5b  jns     short loc_1800B4A6F
0x1800b4a5d  xor     r9d, r9d; lpArguments
0x1800b4a60  xor     r8d, r8d; nNumberOfArguments
0x1800b4a63  lea     edx, [rbx-54h]; dwExceptionFlags
0x1800b4a66  mov     ecx, eax; dwExceptionCode
0x1800b4a68  call    cs:__imp_RaiseException
0x1800b4a6e  int     3; Trap to Debugger
0x1800b4a6f  mov     [rbp+30h+var_58], 0
0x1800b4a77  mov     ebx, 59h ; 'Y'
0x1800b4a7c  mov     ecx, ebx; unsigned int
0x1800b4a7e  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800b4a83  lea     edx, [rax-1]
0x1800b4a86  cmp     eax, ebx
0x1800b4a88  cmova   edx, ebx; length
0x1800b4a8b  lea     r9, [rbp+30h+var_58]; string
0x1800b4a8f  lea     r8, [rbp+30h+var_70]; hstringHeader
0x1800b4a93  lea     rcx, aWindowsFoundat_87; "Windows.Foundation.Collections.IVectorV"...
0x1800b4a9a  call    cs:__imp_WindowsCreateStringReference
0x1800b4aa0  test    eax, eax
0x1800b4aa2  jns     short loc_1800B4AB6
0x1800b4aa4  xor     r9d, r9d; lpArguments
0x1800b4aa7  xor     r8d, r8d; nNumberOfArguments
0x1800b4aaa  lea     edx, [rbx-58h]; dwExceptionFlags
0x1800b4aad  mov     ecx, eax; dwExceptionCode
0x1800b4aaf  call    cs:__imp_RaiseException
0x1800b4ab5  int     3; Trap to Debugger
0x1800b4ab6  mov     [rbp+30h+var_38], 0
0x1800b4abe  mov     ebx, 57h ; 'W'
0x1800b4ac3  mov     ecx, ebx; unsigned int
0x1800b4ac5  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800b4aca  lea     edx, [rax-1]
0x1800b4acd  cmp     eax, ebx
0x1800b4acf  cmova   edx, ebx; length
0x1800b4ad2  lea     r9, [rbp+30h+var_38]; string
0x1800b4ad6  lea     r8, [rbp+30h+var_50]; hstringHeader
0x1800b4ada  lea     rcx, aWindowsFoundat_217; "Windows.Foundation.Collections.IIterato"...
0x1800b4ae1  call    cs:__imp_WindowsCreateStringReference
0x1800b4ae7  test    eax, eax
0x1800b4ae9  jns     short loc_1800B4AFD
0x1800b4aeb  xor     r9d, r9d; lpArguments
0x1800b4aee  xor     r8d, r8d; nNumberOfArguments
0x1800b4af1  lea     edx, [rbx-56h]; dwExceptionFlags
0x1800b4af4  mov     ecx, eax; dwExceptionCode
0x1800b4af6  call    cs:__imp_RaiseException
0x1800b4afc  int     3; Trap to Debugger
0x1800b4afd  mov     rax, [rbp+30h+string]
0x1800b4b01  mov     [rsp+130h+var_100], rax
0x1800b4b06  mov     rax, [rbp+30h+var_58]
0x1800b4b0a  mov     [rsp+130h+var_F8], rax
0x1800b4b0f  mov     rax, [rbp+30h+var_38]
0x1800b4b13  mov     [rsp+130h+var_F0], rax
0x1800b4b18  movups  xmm0, xmmword ptr cs:_GUID_ae655c6c_b973_45eb_aa3e_8b6467ff272f.Data1
0x1800b4b1f  movdqu  [rsp+130h+var_E8], xmm0
0x1800b4b25  movups  xmm1, xmmword ptr cs:_GUID_6825a989_eecd_5fa9_8c07_6b7e4aaf8cd2.Data1
0x1800b4b2c  movdqu  [rsp+130h+var_D8], xmm1
0x1800b4b32  movups  xmm0, xmmword ptr cs:_GUID_8b9ae10d_b29a_51cb_adfb_e94ad37480dd.Data1
0x1800b4b39  movdqu  [rsp+130h+var_C8], xmm0
0x1800b4b3f  movups  xmm1, xmmword ptr cs:_GUID_f2239de4_75de_5d69_b523_07177727e395.Data1
0x1800b4b46  movdqu  [rsp+130h+var_B8], xmm1
0x1800b4b4c  movups  xmm0, xmmword ptr cs:_GUID_cdae9f6a_2875_51a5_b70d_9e9904089dff.Data1
0x1800b4b53  movdqu  [rbp+30h+var_A8], xmm0
0x1800b4b58  mov     [rsp+130h+var_110], 0
0x1800b4b61  lea     rcx, [rsp+130h+var_110]
0x1800b4b66  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4b6b  mov     [rbp+30h+var_18], 0
0x1800b4b73  lea     r9, [rbp+30h+var_18]; string
0x1800b4b77  lea     r8, [rbp+30h+var_30]; hstringHeader
0x1800b4b7b  mov     edx, 2Ch ; ','; length
0x1800b4b80  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x1800b4b87  call    cs:__imp_WindowsCreateStringReference
0x1800b4b8d  test    eax, eax
0x1800b4b8f  jns     short loc_1800B4BA4
0x1800b4b91  xor     r9d, r9d; lpArguments
0x1800b4b94  xor     r8d, r8d; nNumberOfArguments
0x1800b4b97  lea     edx, [r9+1]; dwExceptionFlags
0x1800b4b9b  mov     ecx, eax; dwExceptionCode
0x1800b4b9d  call    cs:__imp_RaiseException
0x1800b4ba3  int     3; Trap to Debugger
0x1800b4ba4  lea     r8, [rsp+130h+var_110]
0x1800b4ba9  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x1800b4bb0  mov     rcx, [rbp+30h+var_18]
0x1800b4bb4  call    cs:__imp_RoGetActivationFactory
0x1800b4bba  mov     ebx, eax
0x1800b4bbc  test    eax, eax
0x1800b4bbe  jns     short loc_1800B4BE4
0x1800b4bc0  mov     rcx, [rsp+130h+var_110]
0x1800b4bc5  test    rcx, rcx
0x1800b4bc8  jz      short loc_1800B4BE0
0x1800b4bca  mov     [rsp+130h+var_110], 0
0x1800b4bd3  mov     rdx, [rcx]
0x1800b4bd6  mov     rax, [rdx+10h]
0x1800b4bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4bdf  nop
0x1800b4be0  mov     eax, ebx
0x1800b4be2  jmp     short loc_1800B4C4C
0x1800b4be4  mov     [rsp+130h+var_108], 0
0x1800b4bed  mov     rbx, [rsp+130h+var_110]
0x1800b4bf2  lea     rcx, [rsp+130h+var_108]
0x1800b4bf7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4bfc  lea     r8, [rsp+130h+var_108]
0x1800b4c01  lea     rdx, [rsp+130h+var_100]
0x1800b4c06  mov     rcx, rbx
0x1800b4c09  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x1800b4c0e  mov     ebx, eax
0x1800b4c10  lea     rcx, [rsp+130h+var_108]
0x1800b4c15  test    eax, eax
0x1800b4c17  jns     short loc_1800B4C2A
0x1800b4c19  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4c1e  lea     rcx, [rsp+130h+var_110]
0x1800b4c23  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4c28  jmp     short loc_1800B4BE0
0x1800b4c2a  mov     rax, [rsp+130h+var_108]
0x1800b4c2f  mov     [rsp+130h+var_108], 0
0x1800b4c38  mov     [rdi], rax
0x1800b4c3b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4c40  lea     rcx, [rsp+130h+var_110]
0x1800b4c45  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b4c4a  xor     eax, eax
0x1800b4c4c  mov     rcx, [rbp+30h+var_10]
0x1800b4c50  xor     rcx, rsp; StackCookie
0x1800b4c53  call    __security_check_cookie
0x1800b4c58  lea     r11, [rsp+130h+var_s0]
0x1800b4c60  mov     rbx, [r11+10h]
0x1800b4c64  mov     rdi, [r11+20h]
0x1800b4c68  mov     rsp, r11
0x1800b4c6b  pop     rbp
0x1800b4c6c  retn
```
