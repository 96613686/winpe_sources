# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<IInspectable,Windows::Foundation::Collections::Internal::AgileVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0> * *)

- ea: `0x180032618`
- end: `0x1800328b1`
- name: `??$CreateExternalObjectVector@UIInspectable@@V?$AgileVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@$0A@@1234@@Z`
- size: `665`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180032340`

## callees

- `0x18000ce94`
- `0x180011188`
- `0x180032618`
- `0x180201e50`
- `0x180210488`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800327f0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180032803`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180032816`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180032829`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800327f0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180032803`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180032816`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180032829`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003266b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800326a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800326dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180032773`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003266b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800326a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800326dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180032773`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180032791`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180032791`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<IInspectable,Windows::Foundation::Collections::Internal::AgileVector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,0>>(
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
  __int64 v18; // rcx
  __int64 v19; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v21[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v22; // [rsp+48h] [rbp-B8h]
  GUID v23; // [rsp+58h] [rbp-A8h]
  GUID v24; // [rsp+68h] [rbp-98h]
  GUID v25; // [rsp+78h] [rbp-88h]
  GUID v26; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v29; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v30; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v31; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v32; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v33; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v34; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x30u);
  v4 = v3 - 1;
  if ( v3 > 0x30 )
    v4 = 48;
  v5 = WindowsCreateStringReference(L"Windows.Foundation.Collections.IVector`1<Object>", v4, &hstringHeader, &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v30 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x34u);
  v7 = v6 - 1;
  if ( v6 > 0x34 )
    v7 = 52;
  v8 = WindowsCreateStringReference(L"Windows.Foundation.Collections.IVectorView`1<Object>", v7, &v29, &v30);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x32u);
  v10 = v9 - 1;
  if ( v9 > 0x32 )
    v10 = 50;
  v11 = WindowsCreateStringReference(L"Windows.Foundation.Collections.IIterator`1<Object>", v10, &v31, &v32);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v21[0] = string;
  v21[1] = v30;
  v21[2] = v32;
  v22 = GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90;
  v23 = GUID_b32bdca4_5e52_5b27_bc5d_d66a1a268c2a;
  v24 = GUID_a6487363_b074_5c60_ab16_866dce4ee54d;
  v25 = GUID_092b849b_60b1_52be_a44a_6fe8e933cbe4;
  v26 = GUID_44a94f2d_04f8_5091_b336_be7892dd10be;
  v19 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  v34 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v33, &v34);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v34, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v19);
  if ( ActivationFactory < 0 )
  {
    v14 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return (unsigned int)ActivationFactory;
  }
  v20 = 0;
  v16 = v19;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v16, v21, &v20);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
    return (unsigned int)ActivationFactory;
  }
  v17 = v20;
  v20 = 0;
  *a2 = v17;
  v18 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return 0;
}

```

## disassembly

```asm
0x180032618  mov     [rsp-8+arg_0], rbx
0x18003261d  mov     [rsp-8+arg_10], rdi
0x180032622  push    rbp
0x180032623  lea     rbp, [rsp-30h]
0x180032628  sub     rsp, 130h
0x18003262f  mov     rax, cs:__security_cookie
0x180032636  xor     rax, rsp
0x180032639  mov     [rbp+30h+var_10], rax
0x18003263d  mov     rdi, rdx
0x180032640  mov     [rbp+30h+string], 0
0x180032648  mov     ebx, 30h ; '0'
0x18003264d  mov     ecx, ebx; unsigned int
0x18003264f  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180032654  lea     edx, [rax-1]
0x180032657  cmp     eax, ebx
0x180032659  cmova   edx, ebx; length
0x18003265c  lea     r9, [rbp+30h+string]; string
0x180032660  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180032664  lea     rcx, aWindowsFoundat_34; "Windows.Foundation.Collections.IVector`"...
0x18003266b  call    cs:__imp_WindowsCreateStringReference
0x180032671  test    eax, eax
0x180032673  js      loc_1800327E4
0x180032679  mov     [rbp+30h+var_58], 0
0x180032681  mov     ebx, 34h ; '4'
0x180032686  mov     ecx, ebx; unsigned int
0x180032688  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18003268d  lea     edx, [rax-1]
0x180032690  cmp     eax, ebx
0x180032692  cmova   edx, ebx; length
0x180032695  lea     r9, [rbp+30h+var_58]; string
0x180032699  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18003269d  lea     rcx, aWindowsFoundat_68; "Windows.Foundation.Collections.IVectorV"...
0x1800326a4  call    cs:__imp_WindowsCreateStringReference
0x1800326aa  test    eax, eax
0x1800326ac  js      loc_1800327F7
0x1800326b2  mov     [rbp+30h+var_38], 0
0x1800326ba  mov     ebx, 32h ; '2'
0x1800326bf  mov     ecx, ebx; unsigned int
0x1800326c1  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800326c6  lea     edx, [rax-1]
0x1800326c9  cmp     eax, ebx
0x1800326cb  cmova   edx, ebx; length
0x1800326ce  lea     r9, [rbp+30h+var_38]; string
0x1800326d2  lea     r8, [rbp+30h+var_50]; hstringHeader
0x1800326d6  lea     rcx, aWindowsFoundat_35; "Windows.Foundation.Collections.IIterato"...
0x1800326dd  call    cs:__imp_WindowsCreateStringReference
0x1800326e3  test    eax, eax
0x1800326e5  js      loc_18003280A
0x1800326eb  mov     rax, [rbp+30h+string]
0x1800326ef  mov     [rsp+130h+var_100], rax
0x1800326f4  mov     rax, [rbp+30h+var_58]
0x1800326f8  mov     [rsp+130h+var_F8], rax
0x1800326fd  mov     rax, [rbp+30h+var_38]
0x180032701  mov     [rsp+130h+var_F0], rax
0x180032706  movups  xmm0, xmmword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data1
0x18003270d  movdqu  [rsp+130h+var_E8], xmm0
0x180032713  movups  xmm1, xmmword ptr cs:_GUID_b32bdca4_5e52_5b27_bc5d_d66a1a268c2a.Data1
0x18003271a  movdqu  [rsp+130h+var_D8], xmm1
0x180032720  movups  xmm0, xmmword ptr cs:_GUID_a6487363_b074_5c60_ab16_866dce4ee54d.Data1
0x180032727  movdqu  [rsp+130h+var_C8], xmm0
0x18003272d  movups  xmm1, xmmword ptr cs:_GUID_092b849b_60b1_52be_a44a_6fe8e933cbe4.Data1
0x180032734  movdqu  [rsp+130h+var_B8], xmm1
0x18003273a  movups  xmm0, xmmword ptr cs:_GUID_44a94f2d_04f8_5091_b336_be7892dd10be.Data1
0x180032741  movdqu  [rbp+30h+var_A8], xmm0
0x180032746  mov     [rsp+130h+var_110], 0
0x18003274f  lea     rcx, [rsp+130h+var_110]
0x180032754  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032759  mov     [rbp+30h+var_18], 0
0x180032761  lea     r9, [rbp+30h+var_18]; string
0x180032765  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180032769  lea     edx, [rbx-6]; length
0x18003276c  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180032773  call    cs:__imp_WindowsCreateStringReference
0x180032779  test    eax, eax
0x18003277b  js      loc_18003281D
0x180032781  lea     r8, [rsp+130h+var_110]
0x180032786  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18003278d  mov     rcx, [rbp+30h+var_18]
0x180032791  call    cs:__imp_RoGetActivationFactory
0x180032797  mov     ebx, eax
0x180032799  test    eax, eax
0x18003279b  jns     loc_180032830
0x1800327a1  mov     rcx, [rsp+130h+var_110]
0x1800327a6  test    rcx, rcx
0x1800327a9  jz      short loc_1800327C1
0x1800327ab  mov     [rsp+130h+var_110], 0
0x1800327b4  mov     rdx, [rcx]
0x1800327b7  mov     rax, [rdx+10h]
0x1800327bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800327c0  nop
0x1800327c1  mov     eax, ebx
0x1800327c3  mov     rcx, [rbp+30h+var_10]
0x1800327c7  xor     rcx, rsp; StackCookie
0x1800327ca  call    __security_check_cookie
0x1800327cf  lea     r11, [rsp+130h+var_s0]
0x1800327d7  mov     rbx, [r11+10h]
0x1800327db  mov     rdi, [r11+20h]
0x1800327df  mov     rsp, r11
0x1800327e2  pop     rbp
0x1800327e3  retn
0x1800327e4  xor     r9d, r9d; lpArguments
0x1800327e7  xor     r8d, r8d; nNumberOfArguments
0x1800327ea  lea     edx, [r9+1]; dwExceptionFlags
0x1800327ee  mov     ecx, eax; dwExceptionCode
0x1800327f0  call    cs:__imp_RaiseException
0x1800327f6  int     3; Trap to Debugger
0x1800327f7  xor     r9d, r9d; lpArguments
0x1800327fa  xor     r8d, r8d; nNumberOfArguments
0x1800327fd  lea     edx, [r9+1]; dwExceptionFlags
0x180032801  mov     ecx, eax; dwExceptionCode
0x180032803  call    cs:__imp_RaiseException
0x180032809  int     3; Trap to Debugger
0x18003280a  xor     r9d, r9d; lpArguments
0x18003280d  xor     r8d, r8d; nNumberOfArguments
0x180032810  lea     edx, [r9+1]; dwExceptionFlags
0x180032814  mov     ecx, eax; dwExceptionCode
0x180032816  call    cs:__imp_RaiseException
0x18003281c  int     3; Trap to Debugger
0x18003281d  xor     r9d, r9d; lpArguments
0x180032820  xor     r8d, r8d; nNumberOfArguments
0x180032823  lea     edx, [r9+1]; dwExceptionFlags
0x180032827  mov     ecx, eax; dwExceptionCode
0x180032829  call    cs:__imp_RaiseException
0x18003282f  int     3; Trap to Debugger
0x180032830  mov     [rsp+130h+var_108], 0
0x180032839  mov     rbx, [rsp+130h+var_110]
0x18003283e  lea     rcx, [rsp+130h+var_108]
0x180032843  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180032848  lea     r8, [rsp+130h+var_108]
0x18003284d  lea     rdx, [rsp+130h+var_100]
0x180032852  mov     rcx, rbx
0x180032855  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18003285a  mov     ebx, eax
0x18003285c  test    eax, eax
0x18003285e  js      short loc_180032898
0x180032860  mov     rax, [rsp+130h+var_108]
0x180032865  mov     [rsp+130h+var_108], 0
0x18003286e  mov     [rdi], rax
0x180032871  mov     rcx, [rsp+130h+var_110]
0x180032876  test    rcx, rcx
0x180032879  jz      short loc_180032891
0x18003287b  mov     [rsp+130h+var_110], 0
0x180032884  mov     rax, [rcx]
0x180032887  mov     rax, [rax+10h]
0x18003288b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032890  nop
0x180032891  xor     eax, eax
0x180032893  jmp     loc_1800327C3
0x180032898  lea     rcx, [rsp+130h+var_108]
0x18003289d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800328a2  lea     rcx, [rsp+130h+var_110]
0x1800328a7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800328ac  jmp     loc_1800327C1
```
