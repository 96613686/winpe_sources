# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::Storage::Cloud::CloudStoreItemName,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreItemName *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreItemName *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreItemName *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreItemName *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreItemName *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreItemName *>,0> * *)

- ea: `0x1800640e0`
- end: `0x18006439b`
- name: `??$CreateExternalObjectVector@VCloudStoreItemName@Cloud@Storage@Internal@Windows@@V?$AgileVector@PEAVCloudStoreItemName@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreItemName@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreItemName@Cloud@Storage@Internal@Windows@@@4785@$0A@@4Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVCloudStoreItemName@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreItemName@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreItemName@Cloud@Storage@Internal@Windows@@@4785@$0A@@1234@@Z`
- size: `699`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800584e8`

## callees

- `0x18000f4b4`
- `0x180063ba0`
- `0x1800640e0`
- `0x1801201a0`
- `0x180195360`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006435b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006436e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180064381`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180064394`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006435b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006436e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180064381`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180064394`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180064259`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180064259`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180064133`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006416c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800641a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006423b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180064133`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006416c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800641a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006423b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::Storage::Cloud::CloudStoreItemName,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreItemName *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreItemName *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreItemName *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Bu);
  v4 = v3 - 1;
  if ( v3 > 0x5B )
    v4 = 91;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.Storage.Cloud.CloudStoreItemName>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Fu);
  v7 = v6 - 1;
  if ( v6 > 0x5F )
    v7 = 95;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.Storage.Cloud.CloudStoreItemName>",
         v7,
         &v31,
         &v32);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v34 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Du);
  v10 = v9 - 1;
  if ( v9 > 0x5D )
    v10 = 93;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.Storage.Cloud.CloudStoreItemName>",
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
  v24 = GUID_3dc7015b_6cc9_499b_9287_69f34ef4d08c;
  v25 = GUID_b7b425d3_5e23_575b_8533_d35de452efb3;
  v26 = GUID_76b75d27_6a01_5372_9740_ed3fe8565aac;
  v27 = GUID_34a9e6ff_d4e5_5490_a244_370a6ca6a18e;
  v28 = GUID_f98d73c2_aac9_5a51_8c00_b8f214ae9248;
  v21 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v36 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v35, &v36);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    JUMPOUT(0x18006439ALL);
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
0x1800640e0  mov     [rsp-8+arg_0], rbx
0x1800640e5  mov     [rsp-8+arg_10], rdi
0x1800640ea  push    rbp
0x1800640eb  lea     rbp, [rsp-30h]
0x1800640f0  sub     rsp, 130h
0x1800640f7  mov     rax, cs:__security_cookie
0x1800640fe  xor     rax, rsp
0x180064101  mov     [rbp+30h+var_10], rax
0x180064105  mov     rdi, rdx
0x180064108  mov     [rbp+30h+string], 0
0x180064110  mov     ebx, 5Bh ; '['
0x180064115  mov     ecx, ebx; unsigned int
0x180064117  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18006411c  lea     edx, [rax-1]
0x18006411f  cmp     eax, ebx
0x180064121  cmova   edx, ebx; length
0x180064124  lea     r9, [rbp+30h+string]; string
0x180064128  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18006412c  lea     rcx, aWindowsFoundat_3; "Windows.Foundation.Collections.IVector`"...
0x180064133  call    cs:__imp_WindowsCreateStringReference
0x180064139  test    eax, eax
0x18006413b  js      loc_18006434F
0x180064141  mov     [rbp+30h+var_58], 0
0x180064149  mov     ebx, 5Fh ; '_'
0x18006414e  mov     ecx, ebx; unsigned int
0x180064150  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180064155  lea     edx, [rax-1]
0x180064158  cmp     eax, ebx
0x18006415a  cmova   edx, ebx; length
0x18006415d  lea     r9, [rbp+30h+var_58]; string
0x180064161  lea     r8, [rbp+30h+var_70]; hstringHeader
0x180064165  lea     rcx, aWindowsFoundat_4; "Windows.Foundation.Collections.IVectorV"...
0x18006416c  call    cs:__imp_WindowsCreateStringReference
0x180064172  test    eax, eax
0x180064174  js      loc_180064362
0x18006417a  mov     [rbp+30h+var_38], 0
0x180064182  mov     ebx, 5Dh ; ']'
0x180064187  mov     ecx, ebx; unsigned int
0x180064189  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18006418e  lea     edx, [rax-1]
0x180064191  cmp     eax, ebx
0x180064193  cmova   edx, ebx; length
0x180064196  lea     r9, [rbp+30h+var_38]; string
0x18006419a  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18006419e  lea     rcx, aWindowsFoundat_2; "Windows.Foundation.Collections.IIterato"...
0x1800641a5  call    cs:__imp_WindowsCreateStringReference
0x1800641ab  test    eax, eax
0x1800641ad  js      loc_180064375
0x1800641b3  mov     rax, [rbp+30h+string]
0x1800641b7  mov     [rsp+130h+var_100], rax
0x1800641bc  mov     rax, [rbp+30h+var_58]
0x1800641c0  mov     [rsp+130h+var_F8], rax
0x1800641c5  mov     rax, [rbp+30h+var_38]
0x1800641c9  mov     [rsp+130h+var_F0], rax
0x1800641ce  movups  xmm0, xmmword ptr cs:_GUID_3dc7015b_6cc9_499b_9287_69f34ef4d08c.Data1
0x1800641d5  movdqu  [rsp+130h+var_E8], xmm0
0x1800641db  movups  xmm1, xmmword ptr cs:_GUID_b7b425d3_5e23_575b_8533_d35de452efb3.Data1
0x1800641e2  movdqu  [rsp+130h+var_D8], xmm1
0x1800641e8  movups  xmm0, xmmword ptr cs:_GUID_76b75d27_6a01_5372_9740_ed3fe8565aac.Data1
0x1800641ef  movdqu  [rsp+130h+var_C8], xmm0
0x1800641f5  movups  xmm1, xmmword ptr cs:_GUID_34a9e6ff_d4e5_5490_a244_370a6ca6a18e.Data1
0x1800641fc  movdqu  [rsp+130h+var_B8], xmm1
0x180064202  movups  xmm0, xmmword ptr cs:_GUID_f98d73c2_aac9_5a51_8c00_b8f214ae9248.Data1
0x180064209  movdqu  [rbp+30h+var_A8], xmm0
0x18006420e  mov     [rsp+130h+var_110], 0
0x180064217  lea     rcx, [rsp+130h+var_110]
0x18006421c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180064221  mov     [rbp+30h+var_18], 0
0x180064229  lea     r9, [rbp+30h+var_18]; string
0x18006422d  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180064231  lea     edx, [rbx-31h]; length
0x180064234  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18006423b  call    cs:__imp_WindowsCreateStringReference
0x180064241  test    eax, eax
0x180064243  js      loc_180064388
0x180064249  lea     r8, [rsp+130h+var_110]
0x18006424e  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180064255  mov     rcx, [rbp+30h+var_18]
0x180064259  call    cs:__imp_RoGetActivationFactory
0x18006425f  mov     ebx, eax
0x180064261  test    eax, eax
0x180064263  js      short loc_1800642CA
0x180064265  mov     [rsp+130h+var_108], 0
0x18006426e  mov     rbx, [rsp+130h+var_110]
0x180064273  lea     rcx, [rsp+130h+var_108]
0x180064278  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006427d  lea     r8, [rsp+130h+var_108]
0x180064282  lea     rdx, [rsp+130h+var_100]
0x180064287  mov     rcx, rbx
0x18006428a  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18006428f  mov     ebx, eax
0x180064291  test    eax, eax
0x180064293  js      short loc_18006430D
0x180064295  mov     rax, [rsp+130h+var_108]
0x18006429a  mov     [rsp+130h+var_108], 0
0x1800642a3  mov     [rdi], rax
0x1800642a6  mov     rcx, [rsp+130h+var_110]
0x1800642ab  test    rcx, rcx
0x1800642ae  jz      short loc_1800642C6
0x1800642b0  mov     [rsp+130h+var_110], 0
0x1800642b9  mov     rax, [rcx]
0x1800642bc  mov     rax, [rax+10h]
0x1800642c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800642c5  nop
0x1800642c6  xor     eax, eax
0x1800642c8  jmp     short loc_1800642EC
0x1800642ca  mov     rcx, [rsp+130h+var_110]
0x1800642cf  test    rcx, rcx
0x1800642d2  jz      short loc_1800642EA
0x1800642d4  mov     [rsp+130h+var_110], 0
0x1800642dd  mov     rdx, [rcx]
0x1800642e0  mov     rax, [rdx+10h]
0x1800642e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800642e9  nop
0x1800642ea  mov     eax, ebx
0x1800642ec  mov     rcx, [rbp+30h+var_10]
0x1800642f0  xor     rcx, rsp; StackCookie
0x1800642f3  call    __security_check_cookie
0x1800642f8  lea     r11, [rsp+130h+var_s0]
0x180064300  mov     rbx, [r11+10h]
0x180064304  mov     rdi, [r11+20h]
0x180064308  mov     rsp, r11
0x18006430b  pop     rbp
0x18006430c  retn
0x18006430d  mov     rcx, [rsp+130h+var_108]
0x180064312  test    rcx, rcx
0x180064315  jz      short loc_18006432D
0x180064317  mov     [rsp+130h+var_108], 0
0x180064320  mov     rdx, [rcx]
0x180064323  mov     rax, [rdx+10h]
0x180064327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006432c  nop
0x18006432d  mov     rcx, [rsp+130h+var_110]
0x180064332  test    rcx, rcx
0x180064335  jz      short loc_18006434D
0x180064337  mov     [rsp+130h+var_110], 0
0x180064340  mov     rax, [rcx]
0x180064343  mov     rax, [rax+10h]
0x180064347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006434c  nop
0x18006434d  jmp     short loc_1800642EA
0x18006434f  xor     r9d, r9d; lpArguments
0x180064352  xor     r8d, r8d; nNumberOfArguments
0x180064355  lea     edx, [r9+1]; dwExceptionFlags
0x180064359  mov     ecx, eax; dwExceptionCode
0x18006435b  call    cs:__imp_RaiseException
0x180064361  int     3; Trap to Debugger
0x180064362  xor     r9d, r9d; lpArguments
0x180064365  xor     r8d, r8d; nNumberOfArguments
0x180064368  lea     edx, [r9+1]; dwExceptionFlags
0x18006436c  mov     ecx, eax; dwExceptionCode
0x18006436e  call    cs:__imp_RaiseException
0x180064374  int     3; Trap to Debugger
0x180064375  xor     r9d, r9d; lpArguments
0x180064378  xor     r8d, r8d; nNumberOfArguments
0x18006437b  lea     edx, [r9+1]; dwExceptionFlags
0x18006437f  mov     ecx, eax; dwExceptionCode
0x180064381  call    cs:__imp_RaiseException
0x180064387  int     3; Trap to Debugger
0x180064388  xor     r9d, r9d; lpArguments
0x18006438b  xor     r8d, r8d; nNumberOfArguments
0x18006438e  lea     edx, [r9+1]; dwExceptionFlags
0x180064392  mov     ecx, eax; dwExceptionCode
0x180064394  call    cs:__imp_RaiseException
```
