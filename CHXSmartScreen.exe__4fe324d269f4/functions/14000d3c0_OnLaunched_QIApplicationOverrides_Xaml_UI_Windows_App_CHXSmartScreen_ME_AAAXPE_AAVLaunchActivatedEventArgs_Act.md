# ?OnLaunched@?QIApplicationOverrides@Xaml@UI@Windows@@App@CHXSmartScreen@@ME$AAAXPE$AAVLaunchActivatedEventArgs@Activation@ApplicationModel@4@@Z

- ea: `0x14000d3c0`
- end: `0x14000da3d`
- name: `?OnLaunched@?QIApplicationOverrides@Xaml@UI@Windows@@App@CHXSmartScreen@@ME$AAAXPE$AAVLaunchActivatedEventArgs@Activation@ApplicationModel@4@@Z`
- size: `1661`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x14000da50`
- `0x1400107d0`

## callees

- `0x1400039b6`
- `0x1400086b0`
- `0x14000b010`
- `0x14000b5cc`
- `0x14000d3c0`
- `0x140011bf0`
- `0x140011cd0`
- `0x140011d5c`
- `0x140011de4`
- `0x140023f48`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `wincorlib!?__abi_cast_String_to_Object@__abi_details@@YAPE$AAVObject@Platform@@PE$AAVString@3@@Z` at `0x14000d6a0`
- `wincorlib!?__abi_cast_String_to_Object@__abi_details@@YAPE$AAVObject@Platform@@PE$AAVString@3@@Z` at `0x14000d89f`
- `wincorlib!?__abi_cast_String_to_Object@__abi_details@@YAPE$AAVObject@Platform@@PE$AAVString@3@@Z` at `0x14000d6a0`
- `wincorlib!?__abi_cast_String_to_Object@__abi_details@@YAPE$AAVObject@Platform@@PE$AAVString@3@@Z` at `0x14000d89f`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x14000d6b4`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x14000d8b3`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x14000d6b4`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x14000d8b3`
- `wincorlib!??BType@Platform@@SA?AVTypeName@Interop@Xaml@UI@Windows@@PE$AAV01@@Z` at `0x14000d6c8`
- `wincorlib!??BType@Platform@@SA?AVTypeName@Interop@Xaml@UI@Windows@@PE$AAV01@@Z` at `0x14000d8c7`
- `wincorlib!??BType@Platform@@SA?AVTypeName@Interop@Xaml@UI@Windows@@PE$AAV01@@Z` at `0x14000d6c8`
- `wincorlib!??BType@Platform@@SA?AVTypeName@Interop@Xaml@UI@Windows@@PE$AAV01@@Z` at `0x14000d8c7`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14000d522`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14000d522`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall _OnLaunched__QIApplicationOverrides_Xaml_UI_Windows__App_CHXSmartScreen__ME_AAAXPE_AAVLaunchActivatedEventArgs_Activation_ApplicationModel_4__Z(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, __int64 *, __int64 *))
{
  __int64 v4; // rsi
  __int64 v5; // r14
  unsigned int (__fastcall ***v6)(_QWORD, __int64 *, __int64 *); // rax
  unsigned int (__fastcall ***v7)(_QWORD, __int64 *, _QWORD *); // rbx
  __int64 v8; // rdi
  __int64 v9; // rax
  __int64 v10; // rbx
  int v11; // eax
  void *v12; // rax
  __int64 v13; // rbx
  int v14; // eax
  __int64 v15; // rbx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rbx
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rcx
  char v22; // r14
  __int64 v23; // rbx
  HSTRING v24; // r12
  __int64 v25; // r14
  __int64 v26; // r15
  __int128 *v27; // rax
  int v28; // eax
  __int64 v29; // r14
  __int64 v30; // rbx
  int v31; // eax
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rbx
  int v35; // eax
  int v36; // eax
  __int64 v37; // rbx
  __int64 QIContentControl_Controls_Xaml_UI_Windows__Content_ContentControl_2345_UE_AAAPE_AAVObject_Platform__XZ; // rax
  __int64 v39; // rcx
  char v40; // r14
  int v41; // eax
  __int64 v42; // r15
  HSTRING v43; // r12
  HSTRING v44; // rbx
  __int64 type_id; // r14
  __int128 *v46; // rax
  int v47; // eax
  int v48; // eax
  __int64 result; // rax
  __int128 v50; // [rsp+40h] [rbp-39h] BYREF
  __int64 v51; // [rsp+50h] [rbp-29h]
  __int64 v52; // [rsp+58h] [rbp-21h]
  HSTRING string[2]; // [rsp+60h] [rbp-19h] BYREF
  HSTRING v54; // [rsp+70h] [rbp-9h] BYREF
  int v55; // [rsp+7Ch] [rbp+3h]
  __int128 v56; // [rsp+80h] [rbp+7h] BYREF
  __int64 v57; // [rsp+90h] [rbp+17h] BYREF
  __int64 v58; // [rsp+98h] [rbp+1Fh] BYREF
  char v59[8]; // [rsp+A0h] [rbp+27h] BYREF

  v4 = 0;
  v51 = 0;
  v5 = ((__int64 (*)(void))Windows::UI::Xaml::Window::Current::get)();
  v57 = v5;
  v6 = (unsigned int (__fastcall ***)(_QWORD, __int64 *, __int64 *))Windows::UI::Xaml::IWindow::Content::get(v5);
  v7 = v6;
  v8 = 0;
  v58 = 0;
  if ( v6 && !(**v6)(v6, _uuidof__AVFrame_Controls_Xaml_UI_Windows__, &v58) )
    v8 = v58;
  v52 = v8;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  v52 = v8;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v7 )
    ((void (__fastcall *)(unsigned int (__fastcall ***)(_QWORD, __int64 *, _QWORD *)))(*v7)[2])(v7);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v8 )
  {
    v57 = 0;
    v36 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v8)(
            v8,
            _uuidof__AUIContentControl_Controls_Xaml_UI_Windows__,
            &v57);
    if ( v36 < 0 )
      __abi_WinRTraiseException(v36);
    v37 = v57;
    QIContentControl_Controls_Xaml_UI_Windows__Content_ContentControl_2345_UE_AAAPE_AAVObject_Platform__XZ = _get__QIContentControl_Controls_Xaml_UI_Windows__Content_ContentControl_2345_UE_AAAPE_AAVObject_Platform__XZ(v57);
    v39 = QIContentControl_Controls_Xaml_UI_Windows__Content_ContentControl_2345_UE_AAAPE_AAVObject_Platform__XZ;
    v58 = QIContentControl_Controls_Xaml_UI_Windows__Content_ContentControl_2345_UE_AAAPE_AAVObject_Platform__XZ;
    if ( QIContentControl_Controls_Xaml_UI_Windows__Content_ContentControl_2345_UE_AAAPE_AAVObject_Platform__XZ )
    {
      v40 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)QIContentControl_Controls_Xaml_UI_Windows__Content_ContentControl_2345_UE_AAAPE_AAVObject_Platform__XZ
                                      + 16LL))(QIContentControl_Controls_Xaml_UI_Windows__Content_ContentControl_2345_UE_AAAPE_AAVObject_Platform__XZ);
    }
    else
    {
      v40 = 1;
    }
    if ( v37 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    if ( v40 )
    {
      v57 = 0;
      v41 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v8)(
              v8,
              _uuidof__AUIFrame_Controls_Xaml_UI_Windows__,
              &v57);
      if ( v41 < 0 )
        __abi_WinRTraiseException(v41);
      v42 = v57;
      v43 = (HSTRING)Windows::UI::Xaml::Controls::INotifyEventArgs::Value::get(a2);
      v58 = (__int64)v43;
      v44 = (HSTRING)__abi_details::__abi_cast_String_to_Object(v43);
      string[0] = v44;
      type_id = __abi_make_type_id(&_abi_typedesc_CHXSmartScreen_MainPage);
      *(_QWORD *)&v50 = type_id;
      v46 = (__int128 *)Platform::Type::operator Windows::UI::Xaml::Interop::TypeName(&v54, type_id);
      v59[0] = 0;
      v56 = *v46;
      v47 = (*(__int64 (__fastcall **)(__int64, __int128 *, HSTRING, char *))(*(_QWORD *)v42 + 192LL))(
              v42,
              &v56,
              v44,
              v59);
      if ( v47 < 0 )
        __abi_WinRTraiseException(v47);
      WindowsDeleteString_0(v54);
      if ( type_id )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)type_id + 16LL))(type_id);
      if ( v44 )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v44 + 16LL))(v44);
      WindowsDeleteString_0(v43);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
    v34 = Windows::UI::Xaml::Window::Current::get(v39);
    *(_QWORD *)&v50 = v34;
    v48 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 160LL))(v34);
    if ( v48 < 0 )
      __abi_WinRTraiseException(v48);
  }
  else
  {
    v9 = Windows::UI::Xaml::Controls::Frame::Frame(0);
    v10 = v9;
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
      v8 = v10;
      v52 = v10;
    }
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v4 = 0;
    v58 = 0;
    if ( v8 )
    {
      v11 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v8)(
              v8,
              _uuidof__AUIFrame_Controls_Xaml_UI_Windows__,
              &v58);
      if ( v11 < 0 )
        __abi_WinRTraiseException(v11);
      v4 = v58;
    }
    v51 = v4;
    v12 = Platform::Details::Heap::Allocate(0x18u, 0x130u);
    *(_QWORD *)&v50 = CHXSmartScreen::App::OnNavigationFailed;
    DWORD2(v50) = 0;
    HIDWORD(v50) = v55;
    v13 = Windows::UI::Xaml::Navigation::NavigationFailedEventHandler::NavigationFailedEventHandler(v12, a1, &v50);
    v57 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v4 + 144LL))(v4, v13, &v57);
    if ( v14 < 0 )
      __abi_WinRTraiseException(v14);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v15 = 0;
    v57 = 0;
    if ( a2 )
    {
      v16 = (**a2)(a2, _uuidof__AUIActivatedEventArgs_Activation_ApplicationModel_Windows__, &v57);
      if ( v16 < 0 )
        __abi_WinRTraiseException(v16);
      v15 = v57;
    }
    LODWORD(v58) = 0;
    v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 56LL))(v15, &v58);
    if ( v17 < 0 )
      __abi_WinRTraiseException(v17);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v18 = 0;
    v57 = 0;
    if ( v8 )
    {
      v19 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v8)(
              v8,
              _uuidof__AUIContentControl_Controls_Xaml_UI_Windows__,
              &v57);
      if ( v19 < 0 )
        __abi_WinRTraiseException(v19);
      v18 = v57;
    }
    v20 = _get__QIContentControl_Controls_Xaml_UI_Windows__Content_ContentControl_2345_UE_AAAPE_AAVObject_Platform__XZ(v18);
    v21 = v20;
    v58 = v20;
    if ( v20 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    else
    {
      v22 = 1;
    }
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( v22 )
    {
      v23 = __abi_winrt_cast_use_helper(0, v8, _uuidof__AUIFrame_Controls_Xaml_UI_Windows__, v4);
      v24 = (HSTRING)Windows::UI::Xaml::Controls::INotifyEventArgs::Value::get(a2);
      v25 = __abi_details::__abi_cast_String_to_Object(v24);
      v57 = v25;
      v26 = __abi_make_type_id(&_abi_typedesc_CHXSmartScreen_MainPage);
      v58 = v26;
      v27 = (__int128 *)Platform::Type::operator Windows::UI::Xaml::Interop::TypeName(string, v26);
      v59[0] = 0;
      v50 = *v27;
      v28 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64, char *))(*(_QWORD *)v23 + 192LL))(
              v23,
              &v50,
              v25,
              v59);
      if ( v28 < 0 )
        __abi_WinRTraiseException(v28);
      WindowsDeleteString_0(string[0]);
      if ( v26 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      WindowsDeleteString_0(v24);
    }
    v29 = Windows::UI::Xaml::Window::Current::get(v21);
    v30 = 0;
    v57 = 0;
    if ( v8 )
    {
      v31 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v8)(
              v8,
              _uuidof__AVUIElement_Xaml_UI_Windows__,
              &v57);
      if ( v31 < 0 )
        __abi_WinRTraiseException(v31);
      v30 = v57;
    }
    v58 = v30;
    v32 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 72LL))(v29, v30);
    if ( v32 < 0 )
      __abi_WinRTraiseException(v32);
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v34 = Windows::UI::Xaml::Window::Current::get(v33);
    v35 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 160LL))(v34);
    if ( v35 < 0 )
      __abi_WinRTraiseException(v35);
  }
  result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  if ( v4 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v51 = 0;
  if ( v8 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return result;
}

```

## disassembly

```asm
0x14000d3c0  mov     [rsp-8+arg_10], rbx
0x14000d3c5  mov     [rsp-8+arg_18], rsi
0x14000d3ca  push    rbp
0x14000d3cb  push    rdi
0x14000d3cc  push    r12
0x14000d3ce  push    r14
0x14000d3d0  push    r15
0x14000d3d2  lea     rbp, [rsp-37h]
0x14000d3d7  sub     rsp, 0B0h
0x14000d3de  mov     rax, cs:__security_cookie
0x14000d3e5  xor     rax, rsp
0x14000d3e8  mov     [rbp+57h+var_28], rax
0x14000d3ec  mov     r12, rdx
0x14000d3ef  mov     r15, rcx
0x14000d3f2  xor     esi, esi
0x14000d3f4  mov     [rbp+57h+var_80], rsi
0x14000d3f8  call    ?get@Current@Window@Xaml@UI@Windows@@SAPE$AAV2345@XZ; Windows::UI::Xaml::Window::Current::get(void)
0x14000d3fd  mov     r14, rax
0x14000d400  mov     [rbp+57h+var_40], rax
0x14000d404  mov     rcx, rax
0x14000d407  call    ?get@Content@IWindow@Xaml@UI@Windows@@UE$AAAPE$AAVUIElement@345@XZ; Windows::UI::Xaml::IWindow::Content::get(void)
0x14000d40c  mov     rbx, rax
0x14000d40f  mov     [rbp+57h+var_A0], rax
0x14000d413  xor     edi, edi
0x14000d415  mov     [rbp+57h+var_38], rdi
0x14000d419  test    rax, rax
0x14000d41c  jz      short loc_14000D43F
0x14000d41e  mov     rcx, [rax]
0x14000d421  mov     rax, [rcx]
0x14000d424  lea     r8, [rbp+57h+var_38]
0x14000d428  lea     rdx, __uuidof_?AVFrame@Controls@Xaml@UI@Windows@@
0x14000d42f  mov     rcx, rbx
0x14000d432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d437  test    eax, eax
0x14000d439  jnz     short loc_14000D43F
0x14000d43b  mov     rdi, [rbp+57h+var_38]
0x14000d43f  mov     [rbp+57h+var_78], rdi
0x14000d443  test    rdi, rdi
0x14000d446  jz      short loc_14000D457
0x14000d448  mov     rax, [rdi]
0x14000d44b  mov     rcx, rdi
0x14000d44e  mov     rax, [rax+8]
0x14000d452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d457  mov     [rbp+57h+var_78], rdi
0x14000d45b  test    rdi, rdi
0x14000d45e  jz      short loc_14000D470
0x14000d460  mov     rax, [rdi]
0x14000d463  mov     rcx, rdi
0x14000d466  mov     rax, [rax+10h]
0x14000d46a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d46f  nop
0x14000d470  test    rbx, rbx
0x14000d473  jz      short loc_14000D485
0x14000d475  mov     rax, [rbx]
0x14000d478  mov     rcx, rbx
0x14000d47b  mov     rax, [rax+10h]
0x14000d47f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d484  nop
0x14000d485  test    r14, r14
0x14000d488  jz      short loc_14000D49A
0x14000d48a  mov     rax, [r14]
0x14000d48d  mov     rcx, r14
0x14000d490  mov     rax, [rax+10h]
0x14000d494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d499  nop
0x14000d49a  test    rdi, rdi
0x14000d49d  jnz     loc_14000D7E5
0x14000d4a3  mov     [rbp+57h+var_A0], rdi
0x14000d4a7  xor     ecx, ecx
0x14000d4a9  call    ??0Frame@Controls@Xaml@UI@Windows@@QE$AAA@XZ; Windows::UI::Xaml::Controls::Frame::Frame(void)
0x14000d4ae  mov     rbx, rax
0x14000d4b1  mov     [rbp+57h+var_A0], rax
0x14000d4b5  test    rax, rax
0x14000d4b8  jz      short loc_14000D4D0
0x14000d4ba  mov     rcx, [rax]
0x14000d4bd  mov     rax, [rcx+8]
0x14000d4c1  mov     rcx, rbx
0x14000d4c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d4c9  mov     rdi, rbx
0x14000d4cc  mov     [rbp+57h+var_78], rbx
0x14000d4d0  test    rbx, rbx
0x14000d4d3  jz      short loc_14000D4E4
0x14000d4d5  mov     rax, [rbx]
0x14000d4d8  mov     rcx, rbx
0x14000d4db  mov     rax, [rax+10h]
0x14000d4df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d4e4  xor     esi, esi
0x14000d4e6  mov     [rbp+57h+var_38], rsi
0x14000d4ea  test    rdi, rdi
0x14000d4ed  jz      short loc_14000D514
0x14000d4ef  mov     rax, [rdi]
0x14000d4f2  lea     r8, [rbp+57h+var_38]
0x14000d4f6  lea     rdx, __uuidof_?AUIFrame@Controls@Xaml@UI@Windows@@
0x14000d4fd  mov     rcx, rdi
0x14000d500  mov     rax, [rax]
0x14000d503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d508  test    eax, eax
0x14000d50a  js      loc_14000D9DD
0x14000d510  mov     rsi, [rbp+57h+var_38]
0x14000d514  mov     [rbp+57h+var_80], rsi
0x14000d518  mov     edx, 130h
0x14000d51d  mov     ecx, 18h
0x14000d522  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x14000d528  mov     [rbp+57h+var_A0], rax
0x14000d52c  lea     rcx, ?OnNavigationFailed@App@CHXSmartScreen@@AE$AAAXPE$AAVObject@Platform@@PE$AAVNavigationFailedEventArgs@Navigation@Xaml@UI@Windows@@@Z; CHXSmartScreen::App::OnNavigationFailed(Platform::Object *,Windows::UI::Xaml::Navigation::NavigationFailedEventArgs *)
0x14000d533  mov     qword ptr [rbp+57h+var_90], rcx
0x14000d537  mov     dword ptr [rbp+57h+var_90+8], 0
0x14000d53e  mov     ecx, [rbp+57h+var_54]
0x14000d541  mov     dword ptr [rbp+57h+var_90+0Ch], ecx
0x14000d544  lea     r8, [rbp+57h+var_90]
0x14000d548  mov     rdx, r15
0x14000d54b  mov     rcx, rax
0x14000d54e  call    ??$?0VApp@CHXSmartScreen@@P801@E$AAAXPE$AAVObject@Platform@@PE$AAVNavigationFailedEventArgs@Navigation@Xaml@UI@Windows@@@Z@NavigationFailedEventHandler@Navigation@Xaml@UI@Windows@@QE$AAA@PE$AAVApp@CHXSmartScreen@@P856@E$AAAXPE$AAVObject@Platform@@PE$AAVNavigationFailedEventArgs@1234@@ZW4CallbackContext@8@_N@Z; Windows::UI::Xaml::Navigation::NavigationFailedEventHandler::NavigationFailedEventHandler(CHXSmartScreen::App *,void (CHXSmartScreen::App::*)(Platform::Object *,Windows::UI::Xaml::Navigation::NavigationFailedEventArgs *),Platform::CallbackContext,bool)
0x14000d553  mov     rbx, rax
0x14000d556  mov     [rbp+57h+var_A0], rax
0x14000d55a  mov     [rbp+57h+var_40], 0
0x14000d562  mov     rcx, [rsi]
0x14000d565  mov     rax, [rcx+90h]
0x14000d56c  lea     r8, [rbp+57h+var_40]
0x14000d570  mov     rdx, rbx
0x14000d573  mov     rcx, rsi
0x14000d576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d57b  test    eax, eax
0x14000d57d  js      loc_14000D9E5
0x14000d583  test    rbx, rbx
0x14000d586  jz      short loc_14000D597
0x14000d588  mov     rax, [rbx]
0x14000d58b  mov     rcx, rbx
0x14000d58e  mov     rax, [rax+10h]
0x14000d592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d597  xor     ebx, ebx
0x14000d599  mov     [rbp+57h+var_40], rbx
0x14000d59d  test    r12, r12
0x14000d5a0  jz      short loc_14000D5C8
0x14000d5a2  mov     rax, [r12]
0x14000d5a6  lea     r8, [rbp+57h+var_40]
0x14000d5aa  lea     rdx, __uuidof_?AUIActivatedEventArgs@Activation@ApplicationModel@Windows@@
0x14000d5b1  mov     rcx, r12
0x14000d5b4  mov     rax, [rax]
0x14000d5b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d5bc  test    eax, eax
0x14000d5be  js      loc_14000D9ED
0x14000d5c4  mov     rbx, [rbp+57h+var_40]
0x14000d5c8  mov     [rbp+57h+var_A0], rbx
0x14000d5cc  mov     dword ptr [rbp+57h+var_38], 0
0x14000d5d3  mov     rax, [rbx]
0x14000d5d6  lea     rdx, [rbp+57h+var_38]
0x14000d5da  mov     rcx, rbx
0x14000d5dd  mov     rax, [rax+38h]
0x14000d5e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d5e6  test    eax, eax
0x14000d5e8  js      loc_14000D9F5
0x14000d5ee  mov     rax, [rbx]
0x14000d5f1  mov     rcx, rbx
0x14000d5f4  mov     rax, [rax+10h]
0x14000d5f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d5fd  xor     ebx, ebx
0x14000d5ff  mov     [rbp+57h+var_40], rbx
0x14000d603  test    rdi, rdi
0x14000d606  jz      short loc_14000D62D
0x14000d608  mov     rax, [rdi]
0x14000d60b  lea     r8, [rbp+57h+var_40]
0x14000d60f  lea     rdx, __uuidof_?AUIContentControl@Controls@Xaml@UI@Windows@@
0x14000d616  mov     rcx, rdi
0x14000d619  mov     rax, [rax]
0x14000d61c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d621  test    eax, eax
0x14000d623  js      loc_14000D9FD
0x14000d629  mov     rbx, [rbp+57h+var_40]
0x14000d62d  mov     [rbp+57h+var_A0], rbx
0x14000d631  mov     rcx, rbx
0x14000d634  call    ?get@?QIContentControl@Controls@Xaml@UI@Windows@@Content@ContentControl@2345@UE$AAAPE$AAVObject@Platform@@XZ
0x14000d639  mov     rcx, rax
0x14000d63c  mov     [rbp+57h+var_38], rax
0x14000d640  test    rax, rax
0x14000d643  jnz     short loc_14000D64A
0x14000d645  mov     r14b, 1
0x14000d648  jmp     short loc_14000D65A
0x14000d64a  xor     r14b, r14b
0x14000d64d  mov     rax, [rax]
0x14000d650  mov     rax, [rax+10h]
0x14000d654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d659  nop
0x14000d65a  test    rbx, rbx
0x14000d65d  jz      short loc_14000D66E
0x14000d65f  mov     rax, [rbx]
0x14000d662  mov     rcx, rbx
0x14000d665  mov     rax, [rax+10h]
0x14000d669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d66e  test    r14b, r14b
0x14000d671  jz      loc_14000D73C
0x14000d677  mov     r9, rsi
0x14000d67a  lea     r8, __uuidof_?AUIFrame@Controls@Xaml@UI@Windows@@
0x14000d681  mov     rdx, rdi
0x14000d684  xor     ecx, ecx
0x14000d686  call    ?__abi_winrt_cast_use_helper@@YAPE$AAVObject@Platform@@_NPEAXAEBU_GUID@@PEAU__abi_IUnknown@@@Z; __abi_winrt_cast_use_helper(bool,void *,_GUID const &,__abi_IUnknown *)
0x14000d68b  mov     rbx, rax
0x14000d68e  mov     rcx, r12
0x14000d691  call    ?get@Value@INotifyEventArgs@Controls@Xaml@UI@Windows@@UE$AAAPE$AAVString@Platform@@XZ; Windows::UI::Xaml::Controls::INotifyEventArgs::Value::get(void)
0x14000d696  mov     r12, rax
0x14000d699  mov     [rbp+57h+var_A0], rax
0x14000d69d  mov     rcx, rax
0x14000d6a0  call    cs:__imp_?__abi_cast_String_to_Object@__abi_details@@YAPE$AAVObject@Platform@@PE$AAVString@3@@Z; __abi_details::__abi_cast_String_to_Object(Platform::String *)
0x14000d6a6  mov     r14, rax
0x14000d6a9  mov     [rbp+57h+var_40], rax
0x14000d6ad  lea     rcx, __abi_typedesc_CHXSmartScreen_MainPage
0x14000d6b4  call    cs:__imp_?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z; __abi_make_type_id(__abi_type_descriptor const &)
0x14000d6ba  mov     r15, rax
0x14000d6bd  mov     [rbp+57h+var_38], rax
0x14000d6c1  mov     rdx, rax
0x14000d6c4  lea     rcx, [rbp+57h+string]
0x14000d6c8  call    cs:__imp_??BType@Platform@@SA?AVTypeName@Interop@Xaml@UI@Windows@@PE$AAV01@@Z; Platform::Type::operator Windows::UI::Xaml::Interop::TypeName(Platform::Type *)
0x14000d6ce  nop
0x14000d6cf  mov     [rbp+57h+var_30], 0
0x14000d6d3  movups  xmm0, xmmword ptr [rax]
0x14000d6d6  movdqu  [rbp+57h+var_90], xmm0
0x14000d6db  mov     rcx, [rbx]
0x14000d6de  mov     rax, [rcx+0C0h]
0x14000d6e5  lea     r9, [rbp+57h+var_30]
0x14000d6e9  mov     r8, r14
0x14000d6ec  lea     rdx, [rbp+57h+var_90]
0x14000d6f0  mov     rcx, rbx
0x14000d6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d6f8  test    eax, eax
0x14000d6fa  js      loc_14000DA05
0x14000d700  mov     rcx, [rbp+57h+string]; string
0x14000d704  call    WindowsDeleteString_0
0x14000d709  nop
0x14000d70a  test    r15, r15
0x14000d70d  jz      short loc_14000D71F
0x14000d70f  mov     rax, [r15]
0x14000d712  mov     rcx, r15
0x14000d715  mov     rax, [rax+10h]
0x14000d719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d71e  nop
0x14000d71f  test    r14, r14
0x14000d722  jz      short loc_14000D734
0x14000d724  mov     rax, [r14]
0x14000d727  mov     rcx, r14
0x14000d72a  mov     rax, [rax+10h]
0x14000d72e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d733  nop
0x14000d734  mov     rcx, r12; string
0x14000d737  call    WindowsDeleteString_0
0x14000d73c  call    ?get@Current@Window@Xaml@UI@Windows@@SAPE$AAV2345@XZ; Windows::UI::Xaml::Window::Current::get(void)
0x14000d741  mov     r14, rax
0x14000d744  mov     [rbp+57h+var_A0], rax
0x14000d748  xor     ebx, ebx
0x14000d74a  mov     [rbp+57h+var_40], rbx
0x14000d74e  test    rdi, rdi
0x14000d751  jz      short loc_14000D778
0x14000d753  mov     rcx, [rdi]
0x14000d756  mov     rax, [rcx]
0x14000d759  lea     r8, [rbp+57h+var_40]
0x14000d75d  lea     rdx, __uuidof_?AVUIElement@Xaml@UI@Windows@@
0x14000d764  mov     rcx, rdi
0x14000d767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d76c  test    eax, eax
0x14000d76e  js      loc_14000DA0D
0x14000d774  mov     rbx, [rbp+57h+var_40]
0x14000d778  mov     [rbp+57h+var_38], rbx
0x14000d77c  mov     rax, [r14]
0x14000d77f  mov     rdx, rbx
0x14000d782  mov     rcx, r14
0x14000d785  mov     rax, [rax+48h]
0x14000d789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d78e  test    eax, eax
0x14000d790  js      loc_14000DA15
0x14000d796  test    rbx, rbx
0x14000d799  jz      short loc_14000D7AB
0x14000d79b  mov     rax, [rbx]
0x14000d79e  mov     rcx, rbx
0x14000d7a1  mov     rax, [rax+10h]
0x14000d7a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d7aa  nop
0x14000d7ab  mov     rax, [r14]
0x14000d7ae  mov     rcx, r14
0x14000d7b1  mov     rax, [rax+10h]
0x14000d7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d7ba  call    ?get@Current@Window@Xaml@UI@Windows@@SAPE$AAV2345@XZ; Windows::UI::Xaml::Window::Current::get(void)
0x14000d7bf  mov     rbx, rax
0x14000d7c2  mov     [rbp+57h+var_A0], rax
0x14000d7c6  mov     rcx, [rax]
0x14000d7c9  mov     rax, [rcx+0A0h]
0x14000d7d0  mov     rcx, rbx
0x14000d7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d7d8  test    eax, eax
0x14000d7da  js      loc_14000DA1D
0x14000d7e0  jmp     loc_14000D96D
0x14000d7e5  mov     [rbp+57h+var_40], 0
0x14000d7ed  mov     rax, [rdi]
0x14000d7f0  lea     r8, [rbp+57h+var_40]
0x14000d7f4  lea     rdx, __uuidof_?AUIContentControl@Controls@Xaml@UI@Windows@@
0x14000d7fb  mov     rcx, rdi
0x14000d7fe  mov     rax, [rax]
0x14000d801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d806  test    eax, eax
0x14000d808  js      loc_14000DA25
0x14000d80e  mov     rbx, [rbp+57h+var_40]
0x14000d812  mov     [rbp+57h+var_A0], rbx
  ... truncated ...
```
