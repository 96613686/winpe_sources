# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo *>,0> * *)

- ea: `0x18000e308`
- end: `0x18000e558`
- name: `??$CreateExternalObjectVector@VParentalControlsAppInfo@AppLimits@FamilySafety@Internal@Windows@@V?$AgileVector@PEAVParentalControlsAppInfo@AppLimits@FamilySafety@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVParentalControlsAppInfo@AppLimits@FamilySafety@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVParentalControlsAppInfo@AppLimits@FamilySafety@Internal@Windows@@@4785@$0A@@4Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVParentalControlsAppInfo@AppLimits@FamilySafety@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVParentalControlsAppInfo@AppLimits@FamilySafety@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVParentalControlsAppInfo@AppLimits@FamilySafety@Internal@Windows@@@4785@$0A@@1234@@Z`
- size: `592`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000f638`

## callees

- `0x1800032a0`
- `0x18000e308`
- `0x18000f8d4`
- `0x180011174`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e34c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e376`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e3a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e42e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e34c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e376`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e3a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e42e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000e44c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000e44c`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInfo *>,0>>(
        __int64 a1,
        _QWORD *a2)
{
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  HRESULT v6; // eax
  int v7; // edx
  unsigned int v8; // r8d
  HRESULT v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  HRESULT v12; // eax
  int v13; // edx
  unsigned int v14; // r8d
  int ActivationFactory; // ebx
  __int64 v16; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v23; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v24[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v25; // [rsp+48h] [rbp-B8h]
  GUID v26; // [rsp+58h] [rbp-A8h]
  GUID v27; // [rsp+68h] [rbp-98h]
  GUID v28; // [rsp+78h] [rbp-88h]
  GUID v29; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v32; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v33; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v34; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v35; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v36; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v37; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.FamilySafety.AppLimits.ParentalControlsAppInfo>",
         0x69u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
    __debugbreak();
  }
  v33 = 0;
  v6 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.FamilySafety.AppLimits.ParentalControlsAppInfo>",
         0x6Du,
         &v32,
         &v33);
  if ( v6 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v6, v7, v8);
    __debugbreak();
  }
  v35 = 0;
  v9 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.FamilySafety.AppLimits.ParentalControlsAppInfo>",
         0x6Bu,
         &v34,
         &v35);
  if ( v9 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
    JUMPOUT(0x18000E557LL);
  }
  v24[0] = string;
  v24[1] = v33;
  v24[2] = v35;
  v25 = GUID_c7cf95c9_573d_556a_b085_b33df5bb94a2;
  v26 = GUID_d7ceab21_3972_5aa9_852b_9025d6c88b5e;
  v27 = GUID_5c3866e6_065e_5a44_9a46_a0109c9fd7ce;
  v28 = GUID_a19beb37_4692_5d79_ac35_2d7dfd0337e7;
  v29 = GUID_8c8bb436_e30e_555b_a4af_d441648cdf22;
  v22 = 0;
  v37 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v36, &v37);
  if ( v12 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v12, v13, v14);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v37, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v22);
  if ( ActivationFactory < 0 )
  {
    v16 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return (unsigned int)ActivationFactory;
  }
  v23 = 0;
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v22, v24, &v23);
  if ( ActivationFactory < 0 )
  {
    v18 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    return (unsigned int)ActivationFactory;
  }
  v20 = v23;
  v23 = 0;
  *a2 = v20;
  v21 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  return 0;
}

```

## disassembly

```asm
0x18000e308  mov     [rsp-8+arg_0], rbx
0x18000e30d  mov     [rsp-8+arg_10], rdi
0x18000e312  push    rbp
0x18000e313  lea     rbp, [rsp-30h]
0x18000e318  sub     rsp, 130h
0x18000e31f  mov     rax, cs:__security_cookie
0x18000e326  xor     rax, rsp
0x18000e329  mov     [rbp+30h+var_10], rax
0x18000e32d  mov     rdi, rdx
0x18000e330  mov     [rbp+30h+string], 0
0x18000e338  lea     r9, [rbp+30h+string]; string
0x18000e33c  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18000e340  mov     edx, 69h ; 'i'; length
0x18000e345  lea     rcx, sourceString; "Windows.Foundation.Collections.IVector`"...
0x18000e34c  call    cs:__imp_WindowsCreateStringReference
0x18000e352  test    eax, eax
0x18000e354  js      loc_18000E540
0x18000e35a  mov     [rbp+30h+var_58], 0
0x18000e362  lea     r9, [rbp+30h+var_58]; string
0x18000e366  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18000e36a  mov     edx, 6Dh ; 'm'; length
0x18000e36f  lea     rcx, aWindowsFoundat_1; "Windows.Foundation.Collections.IVectorV"...
0x18000e376  call    cs:__imp_WindowsCreateStringReference
0x18000e37c  test    eax, eax
0x18000e37e  js      loc_18000E548
0x18000e384  mov     [rbp+30h+var_38], 0
0x18000e38c  lea     r9, [rbp+30h+var_38]; string
0x18000e390  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18000e394  mov     edx, 6Bh ; 'k'; length
0x18000e399  lea     rcx, aWindowsFoundat; "Windows.Foundation.Collections.IIterato"...
0x18000e3a0  call    cs:__imp_WindowsCreateStringReference
0x18000e3a6  test    eax, eax
0x18000e3a8  js      loc_18000E550
0x18000e3ae  mov     rax, [rbp+30h+string]
0x18000e3b2  mov     [rsp+130h+var_100], rax
0x18000e3b7  mov     rax, [rbp+30h+var_58]
0x18000e3bb  mov     [rsp+130h+var_F8], rax
0x18000e3c0  mov     rax, [rbp+30h+var_38]
0x18000e3c4  mov     [rsp+130h+var_F0], rax
0x18000e3c9  movups  xmm0, xmmword ptr cs:_GUID_c7cf95c9_573d_556a_b085_b33df5bb94a2.Data1
0x18000e3d0  movdqu  [rsp+130h+var_E8], xmm0
0x18000e3d6  movups  xmm1, xmmword ptr cs:_GUID_d7ceab21_3972_5aa9_852b_9025d6c88b5e.Data1
0x18000e3dd  movdqu  [rsp+130h+var_D8], xmm1
0x18000e3e3  movups  xmm0, xmmword ptr cs:_GUID_5c3866e6_065e_5a44_9a46_a0109c9fd7ce.Data1
0x18000e3ea  movdqu  [rsp+130h+var_C8], xmm0
0x18000e3f0  movups  xmm1, xmmword ptr cs:_GUID_a19beb37_4692_5d79_ac35_2d7dfd0337e7.Data1
0x18000e3f7  movdqu  [rsp+130h+var_B8], xmm1
0x18000e3fd  movups  xmm0, xmmword ptr cs:_GUID_8c8bb436_e30e_555b_a4af_d441648cdf22.Data1
0x18000e404  movdqu  [rbp+30h+var_A8], xmm0
0x18000e409  mov     [rsp+130h+var_110], 0
0x18000e412  mov     [rbp+30h+var_18], 0
0x18000e41a  lea     r9, [rbp+30h+var_18]; string
0x18000e41e  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18000e422  mov     edx, 2Ch ; ','; length
0x18000e427  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18000e42e  call    cs:__imp_WindowsCreateStringReference
0x18000e434  test    eax, eax
0x18000e436  js      loc_18000E538
0x18000e43c  lea     r8, [rsp+130h+var_110]
0x18000e441  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18000e448  mov     rcx, [rbp+30h+var_18]
0x18000e44c  call    cs:__imp_RoGetActivationFactory
0x18000e452  mov     ebx, eax
0x18000e454  test    eax, eax
0x18000e456  jns     short loc_18000E47F
0x18000e458  mov     rcx, [rsp+130h+var_110]
0x18000e45d  test    rcx, rcx
0x18000e460  jz      short loc_18000E478
0x18000e462  mov     [rsp+130h+var_110], 0
0x18000e46b  mov     rdx, [rcx]
0x18000e46e  mov     rax, [rdx+10h]
0x18000e472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e477  nop
0x18000e478  mov     eax, ebx
0x18000e47a  jmp     loc_18000E517
0x18000e47f  mov     [rsp+130h+var_108], 0
0x18000e488  lea     r8, [rsp+130h+var_108]
0x18000e48d  lea     rdx, [rsp+130h+var_100]
0x18000e492  mov     rcx, [rsp+130h+var_110]
0x18000e497  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18000e49c  mov     ebx, eax
0x18000e49e  test    eax, eax
0x18000e4a0  jns     short loc_18000E4E4
0x18000e4a2  mov     rcx, [rsp+130h+var_108]
0x18000e4a7  test    rcx, rcx
0x18000e4aa  jz      short loc_18000E4C2
0x18000e4ac  mov     [rsp+130h+var_108], 0
0x18000e4b5  mov     rdx, [rcx]
0x18000e4b8  mov     rax, [rdx+10h]
0x18000e4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4c1  nop
0x18000e4c2  mov     rcx, [rsp+130h+var_110]
0x18000e4c7  test    rcx, rcx
0x18000e4ca  jz      short loc_18000E4E2
0x18000e4cc  mov     [rsp+130h+var_110], 0
0x18000e4d5  mov     rax, [rcx]
0x18000e4d8  mov     rax, [rax+10h]
0x18000e4dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4e1  nop
0x18000e4e2  jmp     short loc_18000E478
0x18000e4e4  mov     rax, [rsp+130h+var_108]
0x18000e4e9  mov     [rsp+130h+var_108], 0
0x18000e4f2  mov     [rdi], rax
0x18000e4f5  mov     rcx, [rsp+130h+var_110]
0x18000e4fa  test    rcx, rcx
0x18000e4fd  jz      short loc_18000E515
0x18000e4ff  mov     [rsp+130h+var_110], 0
0x18000e508  mov     rax, [rcx]
0x18000e50b  mov     rax, [rax+10h]
0x18000e50f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e514  nop
0x18000e515  xor     eax, eax
0x18000e517  mov     rcx, [rbp+30h+var_10]
0x18000e51b  xor     rcx, rsp; StackCookie
0x18000e51e  call    __security_check_cookie
0x18000e523  lea     r11, [rsp+130h+var_s0]
0x18000e52b  mov     rbx, [r11+10h]
0x18000e52f  mov     rdi, [r11+20h]
0x18000e533  mov     rsp, r11
0x18000e536  pop     rbp
0x18000e537  retn
0x18000e538  mov     ecx, eax; this
0x18000e53a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000e53f  int     3; Trap to Debugger
0x18000e540  mov     ecx, eax; this
0x18000e542  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000e547  int     3; Trap to Debugger
0x18000e548  mov     ecx, eax; this
0x18000e54a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000e54f  int     3; Trap to Debugger
0x18000e550  mov     ecx, eax; this
0x18000e552  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
