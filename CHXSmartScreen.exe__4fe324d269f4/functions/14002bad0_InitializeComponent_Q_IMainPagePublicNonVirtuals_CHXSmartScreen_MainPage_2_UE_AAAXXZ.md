# ?InitializeComponent@?Q__IMainPagePublicNonVirtuals@CHXSmartScreen@@MainPage@2@UE$AAAXXZ

- ea: `0x14002bad0`
- end: `0x14002be7b`
- name: `?InitializeComponent@?Q__IMainPagePublicNonVirtuals@CHXSmartScreen@@MainPage@2@UE$AAAXXZ`
- size: `939`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14000e070`
- `0x1400147a0`

## callees

- `0x14000285c`
- `0x1400039aa`
- `0x1400086b0`
- `0x1400149a4`
- `0x14002aed8`
- `0x14002bad0`
- `0x140031960`
- `0x140035010`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall _InitializeComponent__Q__IMainPagePublicNonVirtuals_CHXSmartScreen__MainPage_2_UE_AAAXXZ(__int64 a1)
{
  HRESULT v2; // eax
  __int64 v3; // rcx
  __int64 v4; // r8
  void **v5; // r9
  HSTRING v6; // rbx
  void **v7; // r9
  int ActivationFactoryByPCWSTR; // eax
  int v9; // eax
  int v10; // eax
  HSTRING v11; // r14
  HRESULT v12; // eax
  __int64 (__fastcall ***Name)(_QWORD, __int64 *, HSTRING *); // rax
  __int64 (__fastcall ***v14)(_QWORD, __int64 *, HSTRING *); // rsi
  HSTRING v15; // rbx
  int v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  HSTRING v19; // r14
  HRESULT v20; // eax
  __int64 (__fastcall ***v21)(_QWORD, __int64 *, HSTRING *); // rax
  __int64 (__fastcall ***v22)(_QWORD, __int64 *, HSTRING *); // rsi
  HSTRING v23; // rbx
  int v24; // eax
  __int64 v25; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-40h] BYREF
  HSTRING string; // [rsp+58h] [rbp-28h] BYREF
  HSTRING v28; // [rsp+60h] [rbp-20h] BYREF
  __int64 v29; // [rsp+68h] [rbp-18h] BYREF
  int v30; // [rsp+70h] [rbp-10h]
  int v31; // [rsp+74h] [rbp-Ch]

  if ( !*(_BYTE *)(a1 + 368) )
  {
    *(_BYTE *)(a1 + 368) = 1;
    v28 = 0;
    string = 0;
    v2 = WindowsCreateStringReference_0(L"ms-appx:///MainPage.xaml", 0x18u, &hstringHeader, &string);
    if ( v2 < 0 )
      __abi_WinRTraiseException(v2);
    v6 = (HSTRING)Windows::Foundation::Uri::Uri(v3, (__int64)string, v4, v5);
    v28 = v6;
    v29 = 0x45FEF7B406499997LL;
    v30 = 2004181943;
    v31 = 1254872017;
    string = 0;
    ActivationFactoryByPCWSTR = __winRT::__getActivationFactoryByPCWSTR(
                                  (__winRT *)L"Windows.UI.Xaml.Application",
                                  &v29,
                                  (struct Platform::Guid *)&string,
                                  v7);
    if ( ActivationFactoryByPCWSTR < 0 )
      __abi_WinRTraiseException(ActivationFactoryByPCWSTR);
    v9 = (*(__int64 (__fastcall **)(HSTRING, __int64, HSTRING, _QWORD))(*(_QWORD *)string + 72LL))(string, a1, v6, 0);
    if ( v9 < 0 )
      __abi_WinRTraiseException(v9);
    if ( string )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string + 16LL))(string);
    if ( v6 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v6 + 16LL))(v6);
    string = 0;
    v10 = (**(__int64 (__fastcall ***)(__int64, __int64 *, HSTRING *))a1)(
            a1,
            _uuidof__AUIFrameworkElement_Xaml_UI_Windows__,
            &string);
    if ( v10 < 0 )
      __abi_WinRTraiseException(v10);
    v11 = string;
    v28 = 0;
    v12 = WindowsCreateStringReference_0(L"m_GetFocusButton", 0x10u, &hstringHeader, &v28);
    if ( v12 < 0 )
      __abi_WinRTraiseException(v12);
    Name = (__int64 (__fastcall ***)(_QWORD, __int64 *, HSTRING *))Windows::UI::Xaml::IFrameworkElement::FindName(
                                                                     v11,
                                                                     v28);
    v14 = Name;
    v15 = 0;
    v28 = 0;
    if ( Name )
    {
      v16 = (**Name)(Name, _uuidof__AVButton_Controls_Xaml_UI_Windows__, &v28);
      if ( v16 < 0 )
        __abi_WinRTraiseException(v16);
      v15 = v28;
    }
    v29 = (__int64)v15;
    if ( v15 != *(HSTRING *)(a1 + 376) )
    {
      if ( v15 )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v15 + 8LL))(v15);
      v17 = *(_QWORD *)(a1 + 376);
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      *(_QWORD *)(a1 + 376) = v15;
    }
    if ( v15 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v15 + 16LL))(v15);
    if ( v14 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64 *, HSTRING *)))(*v14)[2])(v14);
    if ( v11 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v11 + 16LL))(v11);
    v28 = 0;
    v18 = (**(__int64 (__fastcall ***)(__int64, __int64 *, HSTRING *))a1)(
            a1,
            _uuidof__AUIFrameworkElement_Xaml_UI_Windows__,
            &v28);
    if ( v18 < 0 )
      __abi_WinRTraiseException(v18);
    v19 = v28;
    v29 = (__int64)v28;
    string = 0;
    v20 = WindowsCreateStringReference_0(L"smartScreenWebView", 0x12u, &hstringHeader, &string);
    if ( v20 < 0 )
      __abi_WinRTraiseException(v20);
    v21 = (__int64 (__fastcall ***)(_QWORD, __int64 *, HSTRING *))Windows::UI::Xaml::IFrameworkElement::FindName(
                                                                    v19,
                                                                    string);
    v22 = v21;
    v23 = 0;
    string = 0;
    if ( v21 )
    {
      v24 = (**v21)(v21, _uuidof__AVWebView_Controls_Xaml_UI_Windows__, &string);
      if ( v24 < 0 )
        __abi_WinRTraiseException(v24);
      v23 = string;
    }
    if ( v23 != *(HSTRING *)(a1 + 384) )
    {
      if ( v23 )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v23 + 8LL))(v23);
      v25 = *(_QWORD *)(a1 + 384);
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      *(_QWORD *)(a1 + 384) = v23;
    }
    if ( v23 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v23 + 16LL))(v23);
    if ( v22 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, __int64 *, HSTRING *)))(*v22)[2])(v22);
    if ( v19 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v19 + 16LL))(v19);
  }
}

```

## disassembly

```asm
0x14002bad0  mov     [rsp-18h+arg_8], rbx
0x14002bad5  mov     [rsp-18h+arg_10], rsi
0x14002bada  push    rbp
0x14002badb  push    rdi
0x14002badc  push    r14
0x14002bade  mov     rbp, rsp
0x14002bae1  sub     rsp, 80h
0x14002bae8  mov     rax, cs:__security_cookie
0x14002baef  xor     rax, rsp
0x14002baf2  mov     [rbp+var_8], rax
0x14002baf6  mov     rdi, rcx
0x14002baf9  cmp     byte ptr [rcx+170h], 0
0x14002bb00  jnz     loc_14002BE0F
0x14002bb06  mov     byte ptr [rcx+170h], 1
0x14002bb0d  mov     [rbp+var_20], 0
0x14002bb15  mov     [rbp+string], 0
0x14002bb1d  lea     r9, [rbp+string]; string
0x14002bb21  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14002bb25  mov     edx, 18h; length
0x14002bb2a  lea     rcx, aMsAppxMainpage; "ms-appx:///MainPage.xaml"
0x14002bb31  call    WindowsCreateStringReference_0
0x14002bb36  test    eax, eax
0x14002bb38  js      loc_14002BE3B
0x14002bb3e  mov     rdx, [rbp+string]
0x14002bb42  call    ??0Uri@Foundation@Windows@@QE$AAA@PE$AAVString@Platform@@@Z; Windows::Foundation::Uri::Uri(Platform::String *)
0x14002bb47  mov     rbx, rax
0x14002bb4a  mov     [rbp+var_20], rax
0x14002bb4e  mov     dword ptr [rbp+var_18], 6499997h
0x14002bb55  mov     dword ptr [rbp+var_18+4], 45FEF7B4h
0x14002bb5c  mov     [rbp+var_10], 777563B7h
0x14002bb63  mov     [rbp+var_C], 4ACBD3D1h
0x14002bb6a  mov     [rbp+string], 0
0x14002bb72  lea     r8, [rbp+string]; struct Platform::Guid *
0x14002bb76  lea     rdx, [rbp+var_18]; void *
0x14002bb7a  lea     rcx, aWindowsUiXamlA_0; "Windows.UI.Xaml.Application"
0x14002bb81  call    ?__getActivationFactoryByPCWSTR@__winRT@@YAJPEAXAEAVGuid@Platform@@PEAPEAX@Z; __winRT::__getActivationFactoryByPCWSTR(void *,Platform::Guid &,void * *)
0x14002bb86  test    eax, eax
0x14002bb88  js      loc_14002BE43
0x14002bb8e  mov     rcx, [rbp+string]
0x14002bb92  mov     rax, [rcx]
0x14002bb95  xor     r9d, r9d
0x14002bb98  mov     r8, rbx
0x14002bb9b  mov     rdx, rdi
0x14002bb9e  mov     rax, [rax+48h]
0x14002bba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bba7  test    eax, eax
0x14002bba9  js      loc_14002BE4B
0x14002bbaf  mov     rcx, [rbp+string]
0x14002bbb3  test    rcx, rcx
0x14002bbb6  jz      short loc_14002BBC5
0x14002bbb8  mov     rax, [rcx]
0x14002bbbb  mov     rax, [rax+10h]
0x14002bbbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bbc4  nop
0x14002bbc5  test    rbx, rbx
0x14002bbc8  jz      short loc_14002BBD9
0x14002bbca  mov     rax, [rbx]
0x14002bbcd  mov     rcx, rbx
0x14002bbd0  mov     rax, [rax+10h]
0x14002bbd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bbd9  mov     [rbp+string], 0
0x14002bbe1  mov     rax, [rdi]
0x14002bbe4  lea     r8, [rbp+string]
0x14002bbe8  lea     rdx, __uuidof_?AUIFrameworkElement@Xaml@UI@Windows@@
0x14002bbef  mov     rcx, rdi
0x14002bbf2  mov     rax, [rax]
0x14002bbf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bbfa  test    eax, eax
0x14002bbfc  js      loc_14002BE53
0x14002bc02  mov     r14, [rbp+string]
0x14002bc06  mov     [rbp+var_50], r14
0x14002bc0a  mov     [rbp+var_20], 0
0x14002bc12  lea     r9, [rbp+var_20]; string
0x14002bc16  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14002bc1a  mov     edx, 10h; length
0x14002bc1f  lea     rcx, aMGetfocusbutto; "m_GetFocusButton"
0x14002bc26  call    WindowsCreateStringReference_0
0x14002bc2b  test    eax, eax
0x14002bc2d  js      loc_14002BE5B
0x14002bc33  mov     rdx, [rbp+var_20]
0x14002bc37  mov     rcx, r14
0x14002bc3a  call    ?FindName@IFrameworkElement@Xaml@UI@Windows@@UE$AAAPE$AAVObject@Platform@@PE$AAVString@6@@Z; Windows::UI::Xaml::IFrameworkElement::FindName(Platform::String *)
0x14002bc3f  mov     rsi, rax
0x14002bc42  mov     [rbp+var_48], rax
0x14002bc46  xor     ebx, ebx
0x14002bc48  mov     [rbp+var_20], rbx
0x14002bc4c  test    rax, rax
0x14002bc4f  jz      short loc_14002BC76
0x14002bc51  mov     rcx, [rax]
0x14002bc54  mov     rax, [rcx]
0x14002bc57  lea     r8, [rbp+var_20]
0x14002bc5b  lea     rdx, __uuidof_?AVButton@Controls@Xaml@UI@Windows@@
0x14002bc62  mov     rcx, rsi
0x14002bc65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bc6a  test    eax, eax
0x14002bc6c  js      loc_14002BE63
0x14002bc72  mov     rbx, [rbp+var_20]
0x14002bc76  mov     [rbp+var_18], rbx
0x14002bc7a  cmp     rbx, [rdi+178h]
0x14002bc81  jz      short loc_14002BCB6
0x14002bc83  test    rbx, rbx
0x14002bc86  jz      short loc_14002BC97
0x14002bc88  mov     rax, [rbx]
0x14002bc8b  mov     rcx, rbx
0x14002bc8e  mov     rax, [rax+8]
0x14002bc92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bc97  mov     rcx, [rdi+178h]
0x14002bc9e  test    rcx, rcx
0x14002bca1  jz      short loc_14002BCAF
0x14002bca3  mov     rax, [rcx]
0x14002bca6  mov     rax, [rax+10h]
0x14002bcaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bcaf  mov     [rdi+178h], rbx
0x14002bcb6  test    rbx, rbx
0x14002bcb9  jz      short loc_14002BCCB
0x14002bcbb  mov     rax, [rbx]
0x14002bcbe  mov     rcx, rbx
0x14002bcc1  mov     rax, [rax+10h]
0x14002bcc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bcca  nop
0x14002bccb  test    rsi, rsi
0x14002bcce  jz      short loc_14002BCE0
0x14002bcd0  mov     rax, [rsi]
0x14002bcd3  mov     rcx, rsi
0x14002bcd6  mov     rax, [rax+10h]
0x14002bcda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bcdf  nop
0x14002bce0  test    r14, r14
0x14002bce3  jz      short loc_14002BCF4
0x14002bce5  mov     rax, [r14]
0x14002bce8  mov     rcx, r14
0x14002bceb  mov     rax, [rax+10h]
0x14002bcef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bcf4  mov     [rbp+var_20], 0
0x14002bcfc  mov     rax, [rdi]
0x14002bcff  lea     r8, [rbp+var_20]
0x14002bd03  lea     rdx, __uuidof_?AUIFrameworkElement@Xaml@UI@Windows@@
0x14002bd0a  mov     rcx, rdi
0x14002bd0d  mov     rax, [rax]
0x14002bd10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bd15  test    eax, eax
0x14002bd17  js      loc_14002BE6B
0x14002bd1d  mov     r14, [rbp+var_20]
0x14002bd21  mov     [rbp+var_18], r14
0x14002bd25  mov     [rbp+string], 0
0x14002bd2d  lea     r9, [rbp+string]; string
0x14002bd31  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14002bd35  mov     edx, 12h; length
0x14002bd3a  lea     rcx, aSmartscreenweb; "smartScreenWebView"
0x14002bd41  call    WindowsCreateStringReference_0
0x14002bd46  test    eax, eax
0x14002bd48  js      loc_14002BE73
0x14002bd4e  mov     rdx, [rbp+string]
0x14002bd52  mov     rcx, r14
0x14002bd55  call    ?FindName@IFrameworkElement@Xaml@UI@Windows@@UE$AAAPE$AAVObject@Platform@@PE$AAVString@6@@Z; Windows::UI::Xaml::IFrameworkElement::FindName(Platform::String *)
0x14002bd5a  mov     rsi, rax
0x14002bd5d  mov     [rbp+var_48], rax
0x14002bd61  xor     ebx, ebx
0x14002bd63  mov     [rbp+string], rbx
0x14002bd67  test    rax, rax
0x14002bd6a  jz      short loc_14002BD91
0x14002bd6c  mov     rcx, [rax]
0x14002bd6f  mov     rax, [rcx]
0x14002bd72  lea     r8, [rbp+string]
0x14002bd76  lea     rdx, __uuidof_?AVWebView@Controls@Xaml@UI@Windows@@
0x14002bd7d  mov     rcx, rsi
0x14002bd80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bd85  test    eax, eax
0x14002bd87  js      loc_14002BE33
0x14002bd8d  mov     rbx, [rbp+string]
0x14002bd91  mov     [rbp+var_50], rbx
0x14002bd95  cmp     rbx, [rdi+180h]
0x14002bd9c  jz      short loc_14002BDD1
0x14002bd9e  test    rbx, rbx
0x14002bda1  jz      short loc_14002BDB2
0x14002bda3  mov     rax, [rbx]
0x14002bda6  mov     rcx, rbx
0x14002bda9  mov     rax, [rax+8]
0x14002bdad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bdb2  mov     rcx, [rdi+180h]
0x14002bdb9  test    rcx, rcx
0x14002bdbc  jz      short loc_14002BDCA
0x14002bdbe  mov     rax, [rcx]
0x14002bdc1  mov     rax, [rax+10h]
0x14002bdc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bdca  mov     [rdi+180h], rbx
0x14002bdd1  test    rbx, rbx
0x14002bdd4  jz      short loc_14002BDE6
0x14002bdd6  mov     rax, [rbx]
0x14002bdd9  mov     rcx, rbx
0x14002bddc  mov     rax, [rax+10h]
0x14002bde0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bde5  nop
0x14002bde6  test    rsi, rsi
0x14002bde9  jz      short loc_14002BDFB
0x14002bdeb  mov     rax, [rsi]
0x14002bdee  mov     rcx, rsi
0x14002bdf1  mov     rax, [rax+10h]
0x14002bdf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bdfa  nop
0x14002bdfb  test    r14, r14
0x14002bdfe  jz      short loc_14002BE0F
0x14002be00  mov     rax, [r14]
0x14002be03  mov     rcx, r14
0x14002be06  mov     rax, [rax+10h]
0x14002be0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002be0f  mov     rcx, [rbp+var_8]
0x14002be13  xor     rcx, rsp; StackCookie
0x14002be16  call    __security_check_cookie
0x14002be1b  lea     r11, [rsp+80h+var_s0]
0x14002be23  mov     rbx, [r11+28h]
0x14002be27  mov     rsi, [r11+30h]
0x14002be2b  mov     rsp, r11
0x14002be2e  pop     r14
0x14002be30  pop     rdi
0x14002be31  pop     rbp
0x14002be32  retn
0x14002be33  mov     ecx, eax; int
0x14002be35  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x14002be3b  mov     ecx, eax; int
0x14002be3d  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x14002be43  mov     ecx, eax; int
0x14002be45  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x14002be4b  mov     ecx, eax; int
0x14002be4d  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x14002be53  mov     ecx, eax; int
0x14002be55  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x14002be5b  mov     ecx, eax; int
0x14002be5d  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x14002be63  mov     ecx, eax; int
0x14002be65  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x14002be6b  mov     ecx, eax; int
0x14002be6d  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x14002be73  mov     ecx, eax; int
0x14002be75  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
