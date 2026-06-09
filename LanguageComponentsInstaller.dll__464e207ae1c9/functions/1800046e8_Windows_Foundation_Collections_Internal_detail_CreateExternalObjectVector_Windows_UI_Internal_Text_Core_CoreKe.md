# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile,Windows::Foundation::Collections::Internal::Vector<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>> * *)

- ea: `0x1800046e8`
- end: `0x18000492c`
- name: `??$CreateExternalObjectVector@VCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@V?$Vector@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@U?$DefaultEqualityPredicate@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@4Collections@Foundation@6@U?$DefaultLifetimeTraits@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@4896@U?$DefaultVectorOptions@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@4896@@4Collections@Foundation@6@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@U?$DefaultEqualityPredicate@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@4Collections@Foundation@6@U?$DefaultLifetimeTraits@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@4896@U?$DefaultVectorOptions@PEAVCoreKeyboardInputProfile@Core@Text@Internal@UI@Windows@@@4896@@1234@@Z`
- size: `580`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007594`

## callees

- `0x180003520`
- `0x1800046e8`
- `0x180006898`
- `0x180008e9c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000472c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180004756`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180004780`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000480f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000472c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180004756`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180004780`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000480f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000482d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000482d`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile,Windows::Foundation::Collections::Internal::Vector<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Internal::Text::Core::CoreKeyboardInputProfile *>>>(
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
  HSTRING_HEADER v22; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING v23; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v24[3]; // [rsp+40h] [rbp-C0h] BYREF
  GUID v25; // [rsp+58h] [rbp-A8h]
  GUID v26; // [rsp+68h] [rbp-98h]
  GUID v27; // [rsp+78h] [rbp-88h]
  GUID v28; // [rsp+88h] [rbp-78h]
  GUID v29; // [rsp+98h] [rbp-68h]
  __int64 v30; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v31; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING string; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v34; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v35; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v36; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v37; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.UI.Internal.Text.Core.CoreKeyboardInputProfile>",
         0x60u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
    __debugbreak();
  }
  v35 = 0;
  v6 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.UI.Internal.Text.Core.CoreKeyboardInputProfile>",
         0x64u,
         &v34,
         &v35);
  if ( v6 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v6, v7, v8);
    __debugbreak();
  }
  v37 = 0;
  v9 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IIterator`1<Windows.UI.Internal.Text.Core.CoreKeyboardInputProfile>",
         0x62u,
         &v36,
         &v37);
  if ( v9 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
    JUMPOUT(0x18000492BLL);
  }
  v24[0] = string;
  v24[1] = v35;
  v24[2] = v37;
  v25 = GUID_29fc1d95_e12c_43d9_98a5_de79a87ea36b;
  v26 = GUID_cf2b1143_5f2e_5356_a8e6_e53783306cf8;
  v27 = GUID_84a72ca9_632c_547f_b395_5c46d2ab6089;
  v28 = GUID_ce216dbe_f0ce_5d36_8eed_eec8c854ee40;
  v29 = GUID_7e4ab94b_098c_5db8_a293_49779656f3e9;
  v30 = 0;
  v23 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v22, &v23);
  if ( v12 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v12, v13, v14);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v23, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v30);
  if ( ActivationFactory < 0 )
  {
    v16 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return (unsigned int)ActivationFactory;
  }
  v31 = 0;
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}(v30, v24, &v31);
  if ( ActivationFactory < 0 )
  {
    v18 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    return (unsigned int)ActivationFactory;
  }
  v20 = v31;
  v31 = 0;
  *a2 = v20;
  v21 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  return 0;
}

```

## disassembly

```asm
0x1800046e8  mov     [rsp-8+arg_0], rbx
0x1800046ed  mov     [rsp-8+arg_10], rdi
0x1800046f2  push    rbp
0x1800046f3  lea     rbp, [rsp-30h]
0x1800046f8  sub     rsp, 130h
0x1800046ff  mov     rax, cs:__security_cookie
0x180004706  xor     rax, rsp
0x180004709  mov     [rbp+30h+var_10], rax
0x18000470d  mov     rdi, rdx
0x180004710  mov     [rbp+30h+string], 0
0x180004718  lea     r9, [rbp+30h+string]; string
0x18000471c  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180004720  mov     edx, 60h ; '`'; length
0x180004725  lea     rcx, sourceString; "Windows.Foundation.Collections.IVector`"...
0x18000472c  call    cs:__imp_WindowsCreateStringReference
0x180004732  test    eax, eax
0x180004734  js      loc_180004914
0x18000473a  mov     [rbp+30h+var_38], 0
0x180004742  lea     r9, [rbp+30h+var_38]; string
0x180004746  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18000474a  mov     edx, 64h ; 'd'; length
0x18000474f  lea     rcx, aWindowsFoundat_0; "Windows.Foundation.Collections.IVectorV"...
0x180004756  call    cs:__imp_WindowsCreateStringReference
0x18000475c  test    eax, eax
0x18000475e  js      loc_18000491C
0x180004764  mov     [rbp+30h+var_18], 0
0x18000476c  lea     r9, [rbp+30h+var_18]; string
0x180004770  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180004774  mov     edx, 62h ; 'b'; length
0x180004779  lea     rcx, aWindowsFoundat_1; "Windows.Foundation.Collections.IIterato"...
0x180004780  call    cs:__imp_WindowsCreateStringReference
0x180004786  test    eax, eax
0x180004788  js      loc_180004924
0x18000478e  mov     rax, [rbp+30h+string]
0x180004792  mov     [rsp+130h+var_F0], rax
0x180004797  mov     rax, [rbp+30h+var_38]
0x18000479b  mov     [rsp+130h+var_E8], rax
0x1800047a0  mov     rax, [rbp+30h+var_18]
0x1800047a4  mov     [rsp+130h+var_E0], rax
0x1800047a9  movups  xmm0, xmmword ptr cs:_GUID_29fc1d95_e12c_43d9_98a5_de79a87ea36b.Data1
0x1800047b0  movdqu  [rsp+130h+var_D8], xmm0
0x1800047b6  movups  xmm1, xmmword ptr cs:_GUID_cf2b1143_5f2e_5356_a8e6_e53783306cf8.Data1
0x1800047bd  movdqu  [rsp+130h+var_C8], xmm1
0x1800047c3  movups  xmm0, xmmword ptr cs:_GUID_84a72ca9_632c_547f_b395_5c46d2ab6089.Data1
0x1800047ca  movdqu  [rsp+130h+var_B8], xmm0
0x1800047d0  movups  xmm1, xmmword ptr cs:_GUID_ce216dbe_f0ce_5d36_8eed_eec8c854ee40.Data1
0x1800047d7  movdqu  [rbp+30h+var_A8], xmm1
0x1800047dc  movups  xmm0, xmmword ptr cs:_GUID_7e4ab94b_098c_5db8_a293_49779656f3e9.Data1
0x1800047e3  movdqu  [rbp+30h+var_98], xmm0
0x1800047e8  mov     [rbp+30h+var_80], 0
0x1800047f0  mov     [rsp+130h+var_F8], 0
0x1800047f9  lea     r9, [rsp+130h+var_F8]; string
0x1800047fe  lea     r8, [rsp+130h+var_110]; hstringHeader
0x180004803  mov     edx, 2Ch ; ','; length
0x180004808  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18000480f  call    cs:__imp_WindowsCreateStringReference
0x180004815  test    eax, eax
0x180004817  js      loc_18000490C
0x18000481d  lea     r8, [rbp+30h+var_80]
0x180004821  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180004828  mov     rcx, [rsp+130h+var_F8]
0x18000482d  call    cs:__imp_RoGetActivationFactory
0x180004833  mov     ebx, eax
0x180004835  test    eax, eax
0x180004837  jns     short loc_18000485E
0x180004839  mov     rcx, [rbp+30h+var_80]
0x18000483d  test    rcx, rcx
0x180004840  jz      short loc_180004857
0x180004842  mov     [rbp+30h+var_80], 0
0x18000484a  mov     rdx, [rcx]
0x18000484d  mov     rax, [rdx+10h]
0x180004851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004856  nop
0x180004857  mov     eax, ebx
0x180004859  jmp     loc_1800048EB
0x18000485e  mov     [rbp+30h+var_78], 0
0x180004866  lea     r8, [rbp+30h+var_78]
0x18000486a  lea     rdx, [rsp+130h+var_F0]
0x18000486f  mov     rcx, [rbp+30h+var_80]
0x180004873  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x180004878  mov     ebx, eax
0x18000487a  test    eax, eax
0x18000487c  jns     short loc_1800048BC
0x18000487e  mov     rcx, [rbp+30h+var_78]
0x180004882  test    rcx, rcx
0x180004885  jz      short loc_18000489C
0x180004887  mov     [rbp+30h+var_78], 0
0x18000488f  mov     rdx, [rcx]
0x180004892  mov     rax, [rdx+10h]
0x180004896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000489b  nop
0x18000489c  mov     rcx, [rbp+30h+var_80]
0x1800048a0  test    rcx, rcx
0x1800048a3  jz      short loc_1800048BA
0x1800048a5  mov     [rbp+30h+var_80], 0
0x1800048ad  mov     rax, [rcx]
0x1800048b0  mov     rax, [rax+10h]
0x1800048b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048b9  nop
0x1800048ba  jmp     short loc_180004857
0x1800048bc  mov     rax, [rbp+30h+var_78]
0x1800048c0  mov     [rbp+30h+var_78], 0
0x1800048c8  mov     [rdi], rax
0x1800048cb  mov     rcx, [rbp+30h+var_80]
0x1800048cf  test    rcx, rcx
0x1800048d2  jz      short loc_1800048E9
0x1800048d4  mov     [rbp+30h+var_80], 0
0x1800048dc  mov     rax, [rcx]
0x1800048df  mov     rax, [rax+10h]
0x1800048e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048e8  nop
0x1800048e9  xor     eax, eax
0x1800048eb  mov     rcx, [rbp+30h+var_10]
0x1800048ef  xor     rcx, rsp; StackCookie
0x1800048f2  call    __security_check_cookie
0x1800048f7  lea     r11, [rsp+130h+var_s0]
0x1800048ff  mov     rbx, [r11+10h]
0x180004903  mov     rdi, [r11+20h]
0x180004907  mov     rsp, r11
0x18000490a  pop     rbp
0x18000490b  retn
0x18000490c  mov     ecx, eax; this
0x18000490e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180004913  int     3; Trap to Debugger
0x180004914  mov     ecx, eax; this
0x180004916  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18000491b  int     3; Trap to Debugger
0x18000491c  mov     ecx, eax; this
0x18000491e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180004923  int     3; Trap to Debugger
0x180004924  mov     ecx, eax; this
0x180004926  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
