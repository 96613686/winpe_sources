# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::DependencyGraph,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::DependencyGraph *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::DependencyGraph *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::DependencyGraph *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::DependencyGraph *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::DependencyGraph *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::DependencyGraph *>,0> * *)

- ea: `0x1800644ac`
- end: `0x18006476b`
- name: `??$CreateExternalObjectVector@VDependencyGraph@StateRepository@Internal@Windows@@V?$AgileVector@PEAVDependencyGraph@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVDependencyGraph@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVDependencyGraph@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVDependencyGraph@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVDependencyGraph@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVDependencyGraph@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `703`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180064350`
- `0x1801b0f90`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x1800644ac`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006472b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006473e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180064751`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180064764`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006472b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006473e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180064751`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180064764`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180064625`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180064625`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800644ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180064538`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180064571`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180064607`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800644ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180064538`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180064571`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180064607`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::DependencyGraph,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::DependencyGraph *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::DependencyGraph *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::DependencyGraph *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Au);
  v4 = v3 - 1;
  if ( v3 > 0x5A )
    v4 = 90;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.DependencyGraph>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Eu);
  v7 = v6 - 1;
  if ( v6 > 0x5E )
    v7 = 94;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.DependencyGraph>",
         v7,
         &v31,
         &v32);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v34 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Cu);
  v10 = v9 - 1;
  if ( v9 > 0x5C )
    v10 = 92;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.DependencyGraph>",
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
  v24 = GUID_79f51b1c_f79f_4c22_8bc2_a5b3875f4a63;
  v25 = GUID_2144b0c6_45d0_571e_a47b_96da54fb5c90;
  v26 = GUID_66d2ce49_2ebb_5cb4_8f27_ddbd019099a5;
  v27 = GUID_3e24d21f_87d0_5356_85f0_14631e5f1d0f;
  v28 = GUID_0bd9c873_f85f_57a6_a53e_801038354be7;
  v21 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v36 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v35, &v36);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    JUMPOUT(0x18006476ALL);
  }
  ActivationFactory = RoGetActivationFactory(v36, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v21);
  if ( ActivationFactory < 0 )
  {
    v18 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return (unsigned int)ActivationFactory;
  }
  v22 = 0;
  v14 = v21;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v14, v23, &v22);
  if ( ActivationFactory < 0 )
  {
    v19 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
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
0x1800644ac  mov     [rsp-8+arg_0], rbx
0x1800644b1  mov     [rsp-8+arg_10], rdi
0x1800644b6  push    rbp
0x1800644b7  lea     rbp, [rsp-30h]
0x1800644bc  sub     rsp, 130h
0x1800644c3  mov     rax, cs:__security_cookie
0x1800644ca  xor     rax, rsp
0x1800644cd  mov     [rbp+30h+var_10], rax
0x1800644d1  mov     rdi, rdx
0x1800644d4  mov     [rbp+30h+string], 0
0x1800644dc  mov     ebx, 5Ah ; 'Z'
0x1800644e1  mov     ecx, ebx; unsigned int
0x1800644e3  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800644e8  lea     edx, [rax-1]
0x1800644eb  cmp     eax, ebx
0x1800644ed  cmova   edx, ebx; length
0x1800644f0  lea     r9, [rbp+30h+string]; string
0x1800644f4  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x1800644f8  lea     rcx, aWindowsFoundat_52; "Windows.Foundation.Collections.IVector`"...
0x1800644ff  call    cs:__imp_WindowsCreateStringReference
0x180064505  test    eax, eax
0x180064507  js      loc_18006471F
0x18006450d  mov     [rbp+30h+var_58], 0
0x180064515  mov     ebx, 5Eh ; '^'
0x18006451a  mov     ecx, ebx; unsigned int
0x18006451c  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180064521  lea     edx, [rax-1]
0x180064524  cmp     eax, ebx
0x180064526  cmova   edx, ebx; length
0x180064529  lea     r9, [rbp+30h+var_58]; string
0x18006452d  lea     r8, [rbp+30h+var_70]; hstringHeader
0x180064531  lea     rcx, aWindowsFoundat_117; "Windows.Foundation.Collections.IVectorV"...
0x180064538  call    cs:__imp_WindowsCreateStringReference
0x18006453e  test    eax, eax
0x180064540  js      loc_180064732
0x180064546  mov     [rbp+30h+var_38], 0
0x18006454e  mov     ebx, 5Ch ; '\'
0x180064553  mov     ecx, ebx; unsigned int
0x180064555  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18006455a  lea     edx, [rax-1]
0x18006455d  cmp     eax, ebx
0x18006455f  cmova   edx, ebx; length
0x180064562  lea     r9, [rbp+30h+var_38]; string
0x180064566  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18006456a  lea     rcx, aWindowsFoundat_142; "Windows.Foundation.Collections.IIterato"...
0x180064571  call    cs:__imp_WindowsCreateStringReference
0x180064577  test    eax, eax
0x180064579  js      loc_180064745
0x18006457f  mov     rax, [rbp+30h+string]
0x180064583  mov     [rsp+130h+var_100], rax
0x180064588  mov     rax, [rbp+30h+var_58]
0x18006458c  mov     [rsp+130h+var_F8], rax
0x180064591  mov     rax, [rbp+30h+var_38]
0x180064595  mov     [rsp+130h+var_F0], rax
0x18006459a  movups  xmm0, xmmword ptr cs:_GUID_79f51b1c_f79f_4c22_8bc2_a5b3875f4a63.Data1
0x1800645a1  movdqu  [rsp+130h+var_E8], xmm0
0x1800645a7  movups  xmm1, xmmword ptr cs:_GUID_2144b0c6_45d0_571e_a47b_96da54fb5c90.Data1
0x1800645ae  movdqu  [rsp+130h+var_D8], xmm1
0x1800645b4  movups  xmm0, xmmword ptr cs:_GUID_66d2ce49_2ebb_5cb4_8f27_ddbd019099a5.Data1
0x1800645bb  movdqu  [rsp+130h+var_C8], xmm0
0x1800645c1  movups  xmm1, xmmword ptr cs:_GUID_3e24d21f_87d0_5356_85f0_14631e5f1d0f.Data1
0x1800645c8  movdqu  [rsp+130h+var_B8], xmm1
0x1800645ce  movups  xmm0, xmmword ptr cs:_GUID_0bd9c873_f85f_57a6_a53e_801038354be7.Data1
0x1800645d5  movdqu  [rbp+30h+var_A8], xmm0
0x1800645da  mov     [rsp+130h+var_110], 0
0x1800645e3  lea     rcx, [rsp+130h+var_110]
0x1800645e8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800645ed  mov     [rbp+30h+var_18], 0
0x1800645f5  lea     r9, [rbp+30h+var_18]; string
0x1800645f9  lea     r8, [rbp+30h+var_30]; hstringHeader
0x1800645fd  lea     edx, [rbx-30h]; length
0x180064600  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180064607  call    cs:__imp_WindowsCreateStringReference
0x18006460d  test    eax, eax
0x18006460f  js      loc_180064758
0x180064615  lea     r8, [rsp+130h+var_110]
0x18006461a  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180064621  mov     rcx, [rbp+30h+var_18]
0x180064625  call    cs:__imp_RoGetActivationFactory
0x18006462b  mov     ebx, eax
0x18006462d  test    eax, eax
0x18006462f  js      loc_1800646B9
0x180064635  mov     [rsp+130h+var_108], 0
0x18006463e  mov     rbx, [rsp+130h+var_110]
0x180064643  lea     rcx, [rsp+130h+var_108]
0x180064648  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006464d  lea     r8, [rsp+130h+var_108]
0x180064652  lea     rdx, [rsp+130h+var_100]
0x180064657  mov     rcx, rbx
0x18006465a  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18006465f  mov     ebx, eax
0x180064661  test    eax, eax
0x180064663  js      short loc_1800646DD
0x180064665  mov     rax, [rsp+130h+var_108]
0x18006466a  mov     [rsp+130h+var_108], 0
0x180064673  mov     [rdi], rax
0x180064676  mov     rcx, [rsp+130h+var_110]
0x18006467b  test    rcx, rcx
0x18006467e  jz      short loc_180064696
0x180064680  mov     [rsp+130h+var_110], 0
0x180064689  mov     rax, [rcx]
0x18006468c  mov     rax, [rax+10h]
0x180064690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064695  nop
0x180064696  xor     eax, eax
0x180064698  mov     rcx, [rbp+30h+var_10]
0x18006469c  xor     rcx, rsp; StackCookie
0x18006469f  call    __security_check_cookie
0x1800646a4  lea     r11, [rsp+130h+var_s0]
0x1800646ac  mov     rbx, [r11+10h]
0x1800646b0  mov     rdi, [r11+20h]
0x1800646b4  mov     rsp, r11
0x1800646b7  pop     rbp
0x1800646b8  retn
0x1800646b9  mov     rcx, [rsp+130h+var_110]
0x1800646be  test    rcx, rcx
0x1800646c1  jz      short loc_1800646D9
0x1800646c3  mov     [rsp+130h+var_110], 0
0x1800646cc  mov     rdx, [rcx]
0x1800646cf  mov     rax, [rdx+10h]
0x1800646d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800646d8  nop
0x1800646d9  mov     eax, ebx
0x1800646db  jmp     short loc_180064698
0x1800646dd  mov     rcx, [rsp+130h+var_108]
0x1800646e2  test    rcx, rcx
0x1800646e5  jz      short loc_1800646FD
0x1800646e7  mov     [rsp+130h+var_108], 0
0x1800646f0  mov     rdx, [rcx]
0x1800646f3  mov     rax, [rdx+10h]
0x1800646f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800646fc  nop
0x1800646fd  mov     rcx, [rsp+130h+var_110]
0x180064702  test    rcx, rcx
0x180064705  jz      short loc_18006471D
0x180064707  mov     [rsp+130h+var_110], 0
0x180064710  mov     rax, [rcx]
0x180064713  mov     rax, [rax+10h]
0x180064717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006471c  nop
0x18006471d  jmp     short loc_1800646D9
0x18006471f  xor     r9d, r9d; lpArguments
0x180064722  xor     r8d, r8d; nNumberOfArguments
0x180064725  lea     edx, [r9+1]; dwExceptionFlags
0x180064729  mov     ecx, eax; dwExceptionCode
0x18006472b  call    cs:__imp_RaiseException
0x180064731  int     3; Trap to Debugger
0x180064732  xor     r9d, r9d; lpArguments
0x180064735  xor     r8d, r8d; nNumberOfArguments
0x180064738  lea     edx, [r9+1]; dwExceptionFlags
0x18006473c  mov     ecx, eax; dwExceptionCode
0x18006473e  call    cs:__imp_RaiseException
0x180064744  int     3; Trap to Debugger
0x180064745  xor     r9d, r9d; lpArguments
0x180064748  xor     r8d, r8d; nNumberOfArguments
0x18006474b  lea     edx, [r9+1]; dwExceptionFlags
0x18006474f  mov     ecx, eax; dwExceptionCode
0x180064751  call    cs:__imp_RaiseException
0x180064757  int     3; Trap to Debugger
0x180064758  xor     r9d, r9d; lpArguments
0x18006475b  xor     r8d, r8d; nNumberOfArguments
0x18006475e  lea     edx, [r9+1]; dwExceptionFlags
0x180064762  mov     ecx, eax; dwExceptionCode
0x180064764  call    cs:__imp_RaiseException
```
