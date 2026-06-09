# ?OnActivated@?QIApplicationOverrides@Xaml@UI@Windows@@App@CHXSmartScreen@@ME$AAAXPE$AAUIActivatedEventArgs@Activation@ApplicationModel@4@@Z

- ea: `0x14000c784`
- end: `0x14000d09c`
- name: `?OnActivated@?QIApplicationOverrides@Xaml@UI@Windows@@App@CHXSmartScreen@@ME$AAAXPE$AAUIActivatedEventArgs@Activation@ApplicationModel@4@@Z`
- size: `2328`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000d0b0`
- `0x140010440`

## callees

- `0x14000285c`
- `0x1400039b6`
- `0x140005944`
- `0x1400086b0`
- `0x14000b010`
- `0x14000b5cc`
- `0x14000b720`
- `0x14000b750`
- `0x14000c280`
- `0x14000c784`
- `0x140011d5c`
- `0x140011de4`
- `0x140012284`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000c9d4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000c9d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000c895`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000c895`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x14000ce61`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x14000ce61`
- `wincorlib!??BType@Platform@@SA?AVTypeName@Interop@Xaml@UI@Windows@@PE$AAV01@@Z` at `0x14000ce7a`
- `wincorlib!??BType@Platform@@SA?AVTypeName@Interop@Xaml@UI@Windows@@PE$AAV01@@Z` at `0x14000ce7a`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14000cd5b`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14000cd5b`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall _OnActivated__QIApplicationOverrides_Xaml_UI_Windows__App_CHXSmartScreen__ME_AAAXPE_AAUIActivatedEventArgs_Activation_ApplicationModel_4__Z(
        __int64 a1,
        HSTRING a2)
{
  HSTRING v2; // r12
  __int64 v3; // r13
  char v4; // bl
  int v5; // eax
  __int64 (__fastcall **v6)(HSTRING, __int64 *, struct _RTL_CRITICAL_SECTION **); // rax
  int v7; // eax
  struct _RTL_CRITICAL_SECTION *v8; // rbx
  __int64 v9; // rcx
  int v10; // eax
  struct _RTL_CRITICAL_SECTION *v11; // r14
  __int64 v12; // rcx
  char v13; // si
  struct _RTL_CRITICAL_SECTION *DebugInfo; // rsi
  __int64 v15; // rax
  __int64 v16; // rbx
  __int64 v17; // r15
  int v18; // eax
  int v19; // eax
  __int64 v20; // xmm6_8
  void **v21; // r9
  int ActivationFactoryByPCWSTR; // eax
  int v23; // eax
  void **v24; // r9
  int v25; // eax
  int v26; // eax
  __int64 v27; // rax
  void **v28; // r9
  __int64 v29; // rsi
  __int64 v30; // r15
  int v31; // eax
  int v32; // eax
  struct _RTL_CRITICAL_SECTION *v33; // rax
  struct _RTL_CRITICAL_SECTION *v34; // r14
  __int64 v35; // rbx
  int v36; // eax
  HSTRING v37; // r14
  int v38; // eax
  __int64 v39; // rbx
  int v40; // eax
  int v41; // eax
  struct _RTL_CRITICAL_SECTION *v42; // r14
  HSTRING type_id; // r15
  __int128 *v44; // rax
  int v45; // eax
  __int64 v46; // rcx
  __int64 v47; // r14
  struct _RTL_CRITICAL_SECTION *v48; // rbx
  int v49; // eax
  int v50; // eax
  __int64 v51; // rbx
  int v52; // eax
  __int64 result; // rax
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp-C8h] BYREF
  HSTRING v55; // [rsp+38h] [rbp-C0h]
  struct _RTL_CRITICAL_SECTION *v56; // [rsp+40h] [rbp-B8h] BYREF
  struct _RTL_CRITICAL_SECTION *v57; // [rsp+48h] [rbp-B0h] BYREF
  char v58[16]; // [rsp+50h] [rbp-A8h] BYREF
  __int128 v59; // [rsp+60h] [rbp-98h] BYREF
  __int64 v60; // [rsp+70h] [rbp-88h] BYREF
  int v61; // [rsp+78h] [rbp-80h]
  int v62; // [rsp+7Ch] [rbp-7Ch]
  __int64 v63; // [rsp+80h] [rbp-78h] BYREF
  int v64; // [rsp+88h] [rbp-70h]
  int v65; // [rsp+8Ch] [rbp-6Ch]
  struct _EVENT_DATA_DESCRIPTOR string[2]; // [rsp+90h] [rbp-68h] BYREF

  v2 = a2;
  v3 = a1;
  *(_QWORD *)&v59 = a1;
  v55 = a2;
  v4 = 0;
  LODWORD(v56) = 0;
  v5 = (*(__int64 (__fastcall **)(HSTRING, struct _RTL_CRITICAL_SECTION **))(*(_QWORD *)a2 + 48LL))(a2, &v56);
  if ( v5 < 0 )
    __abi_WinRTraiseException(v5);
  v6 = *(__int64 (__fastcall ***)(HSTRING, __int64 *, struct _RTL_CRITICAL_SECTION **))v2;
  if ( (_DWORD)v56 == 4 )
  {
    v56 = 0;
    v7 = (*v6)(v2, _uuidof__AVProtocolActivatedEventArgs_Activation_ApplicationModel_Windows__, &v56);
    if ( v7 < 0 )
      __abi_WinRTraiseException(v7);
    v8 = v56;
    lpCriticalSection = v56;
    if ( v56 != *(struct _RTL_CRITICAL_SECTION **)(v3 + 160) )
    {
      if ( v56 )
        ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v56->DebugInfo->CriticalSection)(v56);
      v9 = *(_QWORD *)(v3 + 160);
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      *(_QWORD *)(v3 + 160) = v8;
    }
LABEL_44:
    if ( v8 )
      ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v8->DebugInfo->ProcessLocksList.Flink)(v8);
    goto LABEL_46;
  }
  LODWORD(v56) = 0;
  v10 = ((__int64 (__fastcall *)(HSTRING, struct _RTL_CRITICAL_SECTION **))v6[6])(v2, &v56);
  if ( v10 < 0 )
    __abi_WinRTraiseException(v10);
  if ( (_DWORD)v56 == 1009 )
  {
    lpCriticalSection = (LPCRITICAL_SECTION)(v3 + 112);
    EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 112));
    v11 = (struct _RTL_CRITICAL_SECTION *)(v3 + 152);
    v56 = (struct _RTL_CRITICAL_SECTION *)(v3 + 152);
    if ( *(_QWORD *)(v3 + 152) )
    {
      v12 = Windows::ApplicationModel::Core::ICoreApplicationView::CoreWindow::get(v11->DebugInfo);
      v57 = (struct _RTL_CRITICAL_SECTION *)v12;
      v4 = 1;
      if ( v12 )
      {
        v13 = 1;
        goto LABEL_18;
      }
    }
    else
    {
      v12 = (__int64)v57;
    }
    v13 = 0;
LABEL_18:
    if ( (v4 & 1) != 0 && v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    if ( v13 )
    {
      try
      {
        DebugInfo = (struct _RTL_CRITICAL_SECTION *)v11->DebugInfo;
        if ( v11->DebugInfo )
          ((void (__fastcall *)(PRTL_CRITICAL_SECTION_DEBUG))DebugInfo->DebugInfo->CriticalSection)(v11->DebugInfo);
        v57 = DebugInfo;
        v60 = 0;
        v15 = Windows::Foundation::Collections::ValueSet::ValueSet();
        v16 = v15;
        v60 = v15;
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
        v60 = v16;
        if ( v16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        v17 = Windows::ApplicationModel::Core::ICoreApplicationView::CoreWindow::get(DebugInfo);
        v63 = v17;
        v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 48LL))(v17, v16);
        if ( v18 < 0 )
          __abi_WinRTraiseException(v18);
        if ( v17 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
        if ( v16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        if ( DebugInfo )
          ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))DebugInfo->DebugInfo->ProcessLocksList.Flink)(DebugInfo);
      }
      catch ( Platform::Exception __gc * )
      {
        if ( (unsigned int)dword_14004BBC8 > 5 )
          tlgWriteTransfer_EventWriteTransfer((int)&dword_14004BBC8, (int)&byte_14003E429, 0, 0, 2u, string);
        v3 = v59;
        v2 = v55;
        v11 = v56;
      }
    }
    LeaveCriticalSection(lpCriticalSection);
    v56 = 0;
    v19 = (**(__int64 (__fastcall ***)(HSTRING, __int64 *, struct _RTL_CRITICAL_SECTION **))v2)(
            v2,
            _uuidof__AVProtocolForResultsActivatedEventArgs_Activation_ApplicationModel_Windows__,
            &v56);
    if ( v19 < 0 )
      __abi_WinRTraiseException(v19);
    v8 = v56;
    v63 = (__int64)v56;
    if ( v56 != (struct _RTL_CRITICAL_SECTION *)v11->DebugInfo )
    {
      if ( v56 )
        ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v56->DebugInfo->CriticalSection)(v56);
      if ( v11->DebugInfo )
        (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)v11->DebugInfo + 16LL))(v11->DebugInfo);
      v11->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)v8;
    }
    goto LABEL_44;
  }
LABEL_46:
  v20 = *(_QWORD *)Windows::Foundation::Size::Size((Windows::Foundation::Size *)&v63, 900.0, 900.0);
  v60 = 0x4E138C41A28D7594LL;
  v61 = 1683036567;
  v62 = -941330567;
  v56 = 0;
  ActivationFactoryByPCWSTR = __winRT::__getActivationFactoryByPCWSTR(
                                (__winRT *)L"Windows.UI.ViewManagement.ApplicationView",
                                &v60,
                                (struct Platform::Guid *)&v56,
                                v21);
  if ( ActivationFactoryByPCWSTR < 0 )
    __abi_WinRTraiseException(ActivationFactoryByPCWSTR);
  v23 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64))v56->DebugInfo[1].ProcessLocksList.Blink)(
          v56,
          v20);
  if ( v23 < 0 )
    __abi_WinRTraiseException(v23);
  if ( v56 )
    ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v56->DebugInfo->ProcessLocksList.Flink)(v56);
  v63 = 0x4E138C41A28D7594LL;
  v64 = 1683036567;
  v65 = -941330567;
  v56 = 0;
  v25 = __winRT::__getActivationFactoryByPCWSTR(
          (__winRT *)L"Windows.UI.ViewManagement.ApplicationView",
          &v63,
          (struct Platform::Guid *)&v56,
          v24);
  if ( v25 < 0 )
    __abi_WinRTraiseException(v25);
  v26 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, __int64))v56->DebugInfo[1].CriticalSection)(v56, 1);
  if ( v26 < 0 )
    __abi_WinRTraiseException(v26);
  if ( v56 )
    ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v56->DebugInfo->ProcessLocksList.Flink)(v56);
  v63 = 0;
  v27 = Windows::UI::Xaml::Controls::Frame::Frame(0);
  v29 = v27;
  v63 = v27;
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
  v63 = v29;
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  v30 = 0;
  v57 = 0;
  if ( v29 )
  {
    v31 = (**(__int64 (__fastcall ***)(__int64, __int64 *, struct _RTL_CRITICAL_SECTION **))v29)(
            v29,
            _uuidof__AUIFrameworkElement_Xaml_UI_Windows__,
            &v57);
    if ( v31 < 0 )
      __abi_WinRTraiseException(v31);
    v30 = (__int64)v57;
  }
  v60 = v30;
  *(_QWORD *)&v59 = 0x4A920A4C75B40847LL;
  *((_QWORD *)&v59 + 1) = 0xED7A5FC963FD6595uLL;
  v56 = 0;
  v32 = __winRT::__getActivationFactoryByPCWSTR(
          (__winRT *)L"Windows.Globalization.ApplicationLanguages",
          &v59,
          (struct Platform::Guid *)&v56,
          v28);
  if ( v32 < 0 )
    __abi_WinRTraiseException(v32);
  v33 = (struct _RTL_CRITICAL_SECTION *)Windows::UI::Xaml::IWindow::Content::get(v56);
  v34 = v33;
  lpCriticalSection = v33;
  if ( v33 )
    ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v33->DebugInfo->CriticalSection)(v33);
  lpCriticalSection = v34;
  if ( v34 )
  {
    ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v34->DebugInfo->ProcessLocksList.Flink)(v34);
    ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v34->DebugInfo->CriticalSection)(v34);
    ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v34->DebugInfo->ProcessLocksList.Flink)(v34);
  }
  if ( v56 )
    ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v56->DebugInfo->ProcessLocksList.Flink)(v56);
  lpCriticalSection = v34;
  v55 = (HSTRING)Windows::Foundation::Collections::IVectorView<Platform::String __gc *>::GetAt(v34, 0);
  _set__QIFrameworkElement_Xaml_UI_Windows__Language_FrameworkElement_234_UE_AAAXPE_AAVString_Platform___Z(v30, v55);
  WindowsDeleteString_0(v55);
  if ( v34 )
    ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v34->DebugInfo->ProcessLocksList.Flink)(v34);
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  v35 = 0;
  v57 = 0;
  if ( v29 )
  {
    v36 = (**(__int64 (__fastcall ***)(__int64, __int64 *, struct _RTL_CRITICAL_SECTION **))v29)(
            v29,
            _uuidof__AUIFrame_Controls_Xaml_UI_Windows__,
            &v57);
    if ( v36 < 0 )
      __abi_WinRTraiseException(v36);
    v35 = (__int64)v57;
  }
  v60 = v35;
  v55 = (HSTRING)Platform::Details::Heap::Allocate(0x18u, 0x130u);
  *(_QWORD *)&v59 = CHXSmartScreen::App::OnNavigationFailed;
  DWORD2(v59) = 0;
  HIDWORD(v59) = string[0].Reserved;
  v37 = (HSTRING)Windows::UI::Xaml::Navigation::NavigationFailedEventHandler::NavigationFailedEventHandler(
                   v55,
                   v3,
                   &v59);
  v55 = v37;
  lpCriticalSection = 0;
  v38 = (*(__int64 (__fastcall **)(__int64, HSTRING, LPCRITICAL_SECTION *))(*(_QWORD *)v35 + 144LL))(
          v35,
          v37,
          &lpCriticalSection);
  if ( v38 < 0 )
    __abi_WinRTraiseException(v38);
  if ( v37 )
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v37 + 16LL))(v37);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  v39 = 0;
  v57 = 0;
  if ( v29 )
  {
    v40 = (**(__int64 (__fastcall ***)(__int64, __int64 *, struct _RTL_CRITICAL_SECTION **))v29)(
            v29,
            _uuidof__AUIFrame_Controls_Xaml_UI_Windows__,
            &v57);
    if ( v40 < 0 )
      __abi_WinRTraiseException(v40);
    v39 = (__int64)v57;
  }
  v60 = v39;
  v56 = 0;
  v41 = (**(__int64 (__fastcall ***)(HSTRING, __int64 *, struct _RTL_CRITICAL_SECTION **))v2)(
          v2,
          _uuidof__AVProtocolForResultsActivatedEventArgs_Activation_ApplicationModel_Windows__,
          &v56);
  if ( v41 < 0 )
    __abi_WinRTraiseException(v41);
  v42 = v56;
  lpCriticalSection = v56;
  type_id = (HSTRING)__abi_make_type_id(&_abi_typedesc_CHXSmartScreen_MainPage);
  v55 = type_id;
  v44 = (__int128 *)Platform::Type::operator Windows::UI::Xaml::Interop::TypeName(string, type_id);
  v58[0] = 0;
  v59 = *v44;
  v45 = (*(__int64 (__fastcall **)(__int64, __int128 *, struct _RTL_CRITICAL_SECTION *, char *))(*(_QWORD *)v39 + 192LL))(
          v39,
          &v59,
          v42,
          v58);
  if ( v45 < 0 )
    __abi_WinRTraiseException(v45);
  WindowsDeleteString_0((HSTRING)string[0].Ptr);
  if ( type_id )
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)type_id + 16LL))(type_id);
  if ( v42 )
    ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v42->DebugInfo->ProcessLocksList.Flink)(v42);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  if ( v58[0] )
  {
    v47 = Windows::UI::Xaml::Window::Current::get(v46);
    v60 = v47;
    v48 = 0;
    v57 = 0;
    if ( v29 )
    {
      v49 = (**(__int64 (__fastcall ***)(__int64, __int64 *, struct _RTL_CRITICAL_SECTION **))v29)(
              v29,
              _uuidof__AVUIElement_Xaml_UI_Windows__,
              &v57);
      if ( v49 < 0 )
        __abi_WinRTraiseException(v49);
      v48 = v57;
    }
    lpCriticalSection = v48;
    v50 = (*(__int64 (__fastcall **)(__int64, struct _RTL_CRITICAL_SECTION *))(*(_QWORD *)v47 + 72LL))(v47, v48);
    if ( v50 < 0 )
      __abi_WinRTraiseException(v50);
    if ( v48 )
      ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v48->DebugInfo->ProcessLocksList.Flink)(v48);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  }
  v51 = Windows::UI::Xaml::Window::Current::get(v46);
  v60 = v51;
  v52 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v51 + 160LL))(v51);
  if ( v52 < 0 )
    __abi_WinRTraiseException(v52);
  result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  if ( v29 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  return result;
}

```

## disassembly

```asm
0x14000c784  mov     rax, rsp
0x14000c787  mov     [rax+18h], rbx
0x14000c78b  push    rsi
0x14000c78c  push    r12
0x14000c78e  push    r13
0x14000c790  push    r14
0x14000c792  push    r15
0x14000c794  sub     rsp, 0D0h
0x14000c79b  movaps  xmmword ptr [rax-38h], xmm6
0x14000c79f  mov     rax, cs:__security_cookie
0x14000c7a6  xor     rax, rsp
0x14000c7a9  mov     [rsp+0F8h+var_48], rax
0x14000c7b1  mov     r12, rdx
0x14000c7b4  mov     r13, rcx
0x14000c7b7  mov     qword ptr [rsp+0F8h+var_98], rcx
0x14000c7bc  mov     [rsp+0F8h+var_C0], rdx
0x14000c7c1  xor     ebx, ebx
0x14000c7c3  mov     dword ptr [rsp+0F8h+var_B8], ebx
0x14000c7c7  mov     dword ptr [rsp+0F8h+var_B8], ebx
0x14000c7cb  mov     rax, [rdx]
0x14000c7ce  lea     rdx, [rsp+0F8h+var_B8]
0x14000c7d3  mov     rcx, r12
0x14000c7d6  mov     rax, [rax+30h]
0x14000c7da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c7df  test    eax, eax
0x14000c7e1  js      loc_14000D004
0x14000c7e7  mov     rax, [r12]
0x14000c7eb  mov     rcx, r12
0x14000c7ee  cmp     dword ptr [rsp+0F8h+var_B8], 4
0x14000c7f3  jnz     short loc_14000C861
0x14000c7f5  mov     [rsp+0F8h+var_B8], rbx
0x14000c7fa  lea     r8, [rsp+0F8h+var_B8]
0x14000c7ff  lea     rdx, __uuidof_?AVProtocolActivatedEventArgs@Activation@ApplicationModel@Windows@@
0x14000c806  mov     rax, [rax]
0x14000c809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c80e  test    eax, eax
0x14000c810  js      loc_14000D00C
0x14000c816  mov     rbx, [rsp+0F8h+var_B8]
0x14000c81b  mov     [rsp+0F8h+lpCriticalSection], rbx
0x14000c820  cmp     rbx, [r13+0A0h]
0x14000c827  jz      short loc_14000C85C
0x14000c829  test    rbx, rbx
0x14000c82c  jz      short loc_14000C83D
0x14000c82e  mov     rax, [rbx]
0x14000c831  mov     rcx, rbx
0x14000c834  mov     rax, [rax+8]
0x14000c838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c83d  mov     rcx, [r13+0A0h]
0x14000c844  test    rcx, rcx
0x14000c847  jz      short loc_14000C855
0x14000c849  mov     rax, [rcx]
0x14000c84c  mov     rax, [rax+10h]
0x14000c850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c855  mov     [r13+0A0h], rbx
0x14000c85c  jmp     loc_14000CA43
0x14000c861  mov     dword ptr [rsp+0F8h+var_B8], ebx
0x14000c865  lea     rdx, [rsp+0F8h+var_B8]
0x14000c86a  mov     rax, [rax+30h]
0x14000c86e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c873  test    eax, eax
0x14000c875  js      loc_14000D014
0x14000c87b  cmp     dword ptr [rsp+0F8h+var_B8], 3F1h
0x14000c883  jnz     loc_14000CA57
0x14000c889  lea     rax, [r13+70h]
0x14000c88d  mov     [rsp+0F8h+lpCriticalSection], rax
0x14000c892  mov     rcx, rax; lpCriticalSection
0x14000c895  call    cs:__imp_EnterCriticalSection
0x14000c89b  lea     r14, [r13+98h]
0x14000c8a2  mov     [rsp+0F8h+var_B8], r14
0x14000c8a7  cmp     [r14], rbx
0x14000c8aa  jz      short loc_14000C8CB
0x14000c8ac  mov     rcx, [r14]
0x14000c8af  call    ?get@CoreWindow@ICoreApplicationView@Core@ApplicationModel@Windows@@UE$AAAPE$AAV13UI@5@XZ; Windows::ApplicationModel::Core::ICoreApplicationView::CoreWindow::get(void)
0x14000c8b4  mov     rcx, rax
0x14000c8b7  mov     [rsp+0F8h+var_B0], rax
0x14000c8bc  mov     ebx, 1
0x14000c8c1  test    rax, rax
0x14000c8c4  jz      short loc_14000C8D0
0x14000c8c6  mov     sil, bl
0x14000c8c9  jmp     short loc_14000C8D3
0x14000c8cb  mov     rcx, [rsp+0F8h+var_B0]
0x14000c8d0  xor     sil, sil
0x14000c8d3  test    bl, 1
0x14000c8d6  jz      short loc_14000C8E9
0x14000c8d8  test    rcx, rcx
0x14000c8db  jz      short loc_14000C8E9
0x14000c8dd  mov     rax, [rcx]
0x14000c8e0  mov     rax, [rax+10h]
0x14000c8e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c8e9  test    sil, sil
0x14000c8ec  jz      loc_14000C9CF
0x14000c8f2  mov     rsi, [r14]
0x14000c8f5  test    rsi, rsi
0x14000c8f8  jz      short loc_14000C909
0x14000c8fa  mov     rax, [rsi]
0x14000c8fd  mov     rcx, rsi
0x14000c900  mov     rax, [rax+8]
0x14000c904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c909  mov     [rsp+0F8h+var_B0], rsi
0x14000c90e  mov     [rsp+0F8h+var_88], 0
0x14000c917  call    ??0ValueSet@Collections@Foundation@Windows@@QE$AAA@XZ; Windows::Foundation::Collections::ValueSet::ValueSet(void)
0x14000c91c  mov     rbx, rax
0x14000c91f  mov     [rsp+0F8h+var_88], rax
0x14000c924  test    rax, rax
0x14000c927  jz      short loc_14000C938
0x14000c929  mov     rcx, [rax]
0x14000c92c  mov     rax, [rcx+8]
0x14000c930  mov     rcx, rbx
0x14000c933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c938  mov     [rsp+0F8h+var_88], rbx
0x14000c93d  test    rbx, rbx
0x14000c940  jz      short loc_14000C952
0x14000c942  mov     rax, [rbx]
0x14000c945  mov     rcx, rbx
0x14000c948  mov     rax, [rax+10h]
0x14000c94c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c951  nop
0x14000c952  mov     rcx, rsi
0x14000c955  call    ?get@CoreWindow@ICoreApplicationView@Core@ApplicationModel@Windows@@UE$AAAPE$AAV13UI@5@XZ; Windows::ApplicationModel::Core::ICoreApplicationView::CoreWindow::get(void)
0x14000c95a  mov     r15, rax
0x14000c95d  mov     [rsp+0F8h+var_78], rax
0x14000c965  mov     rcx, [rax]
0x14000c968  mov     rax, [rcx+30h]
0x14000c96c  mov     rdx, rbx
0x14000c96f  mov     rcx, r15
0x14000c972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c977  test    eax, eax
0x14000c979  js      loc_14000D01C
0x14000c97f  test    r15, r15
0x14000c982  jz      short loc_14000C994
0x14000c984  mov     rax, [r15]
0x14000c987  mov     rcx, r15
0x14000c98a  mov     rax, [rax+10h]
0x14000c98e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c993  nop
0x14000c994  test    rbx, rbx
0x14000c997  jz      short loc_14000C9A9
0x14000c999  mov     rax, [rbx]
0x14000c99c  mov     rcx, rbx
0x14000c99f  mov     rax, [rax+10h]
0x14000c9a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c9a8  nop
0x14000c9a9  test    rsi, rsi
0x14000c9ac  jz      short loc_14000C9BE
0x14000c9ae  mov     rax, [rsi]
0x14000c9b1  mov     rcx, rsi
0x14000c9b4  mov     rax, [rax+10h]
0x14000c9b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c9bd  nop
0x14000c9be  jmp     short loc_14000C9CF
0x14000c9c0  mov     r13, qword ptr [rsp+0F8h+var_98]
0x14000c9c5  mov     r12, [rsp+0F8h+var_C0]
0x14000c9ca  mov     r14, [rsp+0F8h+var_B8]
0x14000c9cf  mov     rcx, [rsp+0F8h+lpCriticalSection]; lpCriticalSection
0x14000c9d4  call    cs:__imp_LeaveCriticalSection
0x14000c9da  mov     [rsp+0F8h+var_B8], 0
0x14000c9e3  mov     rax, [r12]
0x14000c9e7  lea     r8, [rsp+0F8h+var_B8]
0x14000c9ec  lea     rdx, __uuidof_?AVProtocolForResultsActivatedEventArgs@Activation@ApplicationModel@Windows@@
0x14000c9f3  mov     rcx, r12
0x14000c9f6  mov     rax, [rax]
0x14000c9f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c9fe  test    eax, eax
0x14000ca00  js      loc_14000D024
0x14000ca06  mov     rbx, [rsp+0F8h+var_B8]
0x14000ca0b  mov     [rsp+0F8h+var_78], rbx
0x14000ca13  cmp     rbx, [r14]
0x14000ca16  jz      short loc_14000CA43
0x14000ca18  test    rbx, rbx
0x14000ca1b  jz      short loc_14000CA2C
0x14000ca1d  mov     rax, [rbx]
0x14000ca20  mov     rcx, rbx
0x14000ca23  mov     rax, [rax+8]
0x14000ca27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ca2c  mov     rcx, [r14]
0x14000ca2f  test    rcx, rcx
0x14000ca32  jz      short loc_14000CA40
0x14000ca34  mov     rax, [rcx]
0x14000ca37  mov     rax, [rax+10h]
0x14000ca3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ca40  mov     [r14], rbx
0x14000ca43  test    rbx, rbx
0x14000ca46  jz      short loc_14000CA57
0x14000ca48  mov     rax, [rbx]
0x14000ca4b  mov     rcx, rbx
0x14000ca4e  mov     rax, [rax+10h]
0x14000ca52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ca57  movss   xmm1, cs:__real@44610000; float
0x14000ca5f  movaps  xmm2, xmm1; float
0x14000ca62  lea     rcx, [rsp+0F8h+var_78]; this
0x14000ca6a  call    ??0Size@Foundation@Windows@@QEAA@MM@Z; Windows::Foundation::Size::Size(float,float)
0x14000ca6f  movsd   xmm6, qword ptr [rax]
0x14000ca73  mov     ebx, 0A28D7594h
0x14000ca78  mov     dword ptr [rsp+0F8h+var_88], ebx
0x14000ca7c  mov     dword ptr [rsp+0F8h+var_88+4], 4E138C41h
0x14000ca84  mov     [rsp+0F8h+var_80], 64511997h
0x14000ca8c  mov     [rsp+0F8h+var_7C], 0C7E46F79h
0x14000ca94  mov     [rsp+0F8h+var_B8], 0
0x14000ca9d  lea     r8, [rsp+0F8h+var_B8]; struct Platform::Guid *
0x14000caa2  lea     rdx, [rsp+0F8h+var_88]; void *
0x14000caa7  lea     rcx, aWindowsUiViewm_0; "Windows.UI.ViewManagement.ApplicationVi"...
0x14000caae  call    ?__getActivationFactoryByPCWSTR@__winRT@@YAJPEAXAEAVGuid@Platform@@PEAPEAX@Z; __winRT::__getActivationFactoryByPCWSTR(void *,Platform::Guid &,void * *)
0x14000cab3  test    eax, eax
0x14000cab5  js      loc_14000D02C
0x14000cabb  mov     rcx, [rsp+0F8h+var_B8]
0x14000cac0  mov     rax, [rcx]
0x14000cac3  movq    rdx, xmm6
0x14000cac8  mov     rax, [rax+48h]
0x14000cacc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cad1  test    eax, eax
0x14000cad3  js      loc_14000D034
0x14000cad9  mov     rcx, [rsp+0F8h+var_B8]
0x14000cade  test    rcx, rcx
0x14000cae1  jz      short loc_14000CAEF
0x14000cae3  mov     rax, [rcx]
0x14000cae6  mov     rax, [rax+10h]
0x14000caea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000caef  mov     dword ptr [rsp+0F8h+var_78], ebx
0x14000caf6  mov     dword ptr [rsp+0F8h+var_78+4], 4E138C41h
0x14000cb01  mov     [rsp+0F8h+var_70], 64511997h
0x14000cb0c  mov     [rsp+0F8h+var_6C], 0C7E46F79h
0x14000cb17  mov     [rsp+0F8h+var_B8], 0
0x14000cb20  lea     r8, [rsp+0F8h+var_B8]; struct Platform::Guid *
0x14000cb25  lea     rdx, [rsp+0F8h+var_78]; void *
0x14000cb2d  lea     rcx, aWindowsUiViewm_0; "Windows.UI.ViewManagement.ApplicationVi"...
0x14000cb34  call    ?__getActivationFactoryByPCWSTR@__winRT@@YAJPEAXAEAVGuid@Platform@@PEAPEAX@Z; __winRT::__getActivationFactoryByPCWSTR(void *,Platform::Guid &,void * *)
0x14000cb39  test    eax, eax
0x14000cb3b  js      loc_14000D03C
0x14000cb41  mov     rcx, [rsp+0F8h+var_B8]
0x14000cb46  mov     rax, [rcx]
0x14000cb49  mov     edx, 1
0x14000cb4e  mov     rax, [rax+38h]
0x14000cb52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cb57  test    eax, eax
0x14000cb59  js      loc_14000D044
0x14000cb5f  mov     rcx, [rsp+0F8h+var_B8]
0x14000cb64  test    rcx, rcx
0x14000cb67  jz      short loc_14000CB75
0x14000cb69  mov     rax, [rcx]
0x14000cb6c  mov     rax, [rax+10h]
0x14000cb70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cb75  mov     [rsp+0F8h+var_78], 0
0x14000cb81  xor     ecx, ecx
0x14000cb83  call    ??0Frame@Controls@Xaml@UI@Windows@@QE$AAA@XZ; Windows::UI::Xaml::Controls::Frame::Frame(void)
0x14000cb88  mov     rsi, rax
0x14000cb8b  mov     [rsp+0F8h+var_78], rax
0x14000cb93  test    rax, rax
0x14000cb96  jz      short loc_14000CBA7
0x14000cb98  mov     rcx, [rax]
0x14000cb9b  mov     rax, [rcx+8]
0x14000cb9f  mov     rcx, rsi
0x14000cba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cba7  mov     [rsp+0F8h+var_78], rsi
0x14000cbaf  test    rsi, rsi
0x14000cbb2  jz      short loc_14000CBC4
0x14000cbb4  mov     rax, [rsi]
0x14000cbb7  mov     rcx, rsi
0x14000cbba  mov     rax, [rax+10h]
0x14000cbbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cbc3  nop
0x14000cbc4  xor     r15d, r15d
0x14000cbc7  mov     [rsp+0F8h+var_B0], r15
0x14000cbcc  test    rsi, rsi
0x14000cbcf  jz      short loc_14000CBF8
0x14000cbd1  mov     rax, [rsi]
0x14000cbd4  lea     r8, [rsp+0F8h+var_B0]
0x14000cbd9  lea     rdx, __uuidof_?AUIFrameworkElement@Xaml@UI@Windows@@
0x14000cbe0  mov     rcx, rsi
0x14000cbe3  mov     rax, [rax]
0x14000cbe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cbeb  test    eax, eax
0x14000cbed  js      loc_14000D04C
0x14000cbf3  mov     r15, [rsp+0F8h+var_B0]
0x14000cbf8  mov     [rsp+0F8h+var_88], r15
0x14000cbfd  mov     dword ptr [rsp+0F8h+var_98], 75B40847h
0x14000cc05  mov     dword ptr [rsp+0F8h+var_98+4], 4A920A4Ch
0x14000cc0d  mov     dword ptr [rsp+0F8h+var_98+8], 63FD6595h
0x14000cc15  mov     dword ptr [rsp+0F8h+var_98+0Ch], 0ED7A5FC9h
0x14000cc1d  mov     [rsp+0F8h+var_B8], 0
0x14000cc26  lea     r8, [rsp+0F8h+var_B8]; struct Platform::Guid *
0x14000cc2b  lea     rdx, [rsp+0F8h+var_98]; void *
0x14000cc30  lea     rcx, aWindowsGlobali; "Windows.Globalization.ApplicationLangua"...
0x14000cc37  call    ?__getActivationFactoryByPCWSTR@__winRT@@YAJPEAXAEAVGuid@Platform@@PEAPEAX@Z; __winRT::__getActivationFactoryByPCWSTR(void *,Platform::Guid &,void * *)
0x14000cc3c  test    eax, eax
0x14000cc3e  js      loc_14000D054
0x14000cc44  mov     rcx, [rsp+0F8h+var_B8]
0x14000cc49  call    ?get@Content@IWindow@Xaml@UI@Windows@@UE$AAAPE$AAVUIElement@345@XZ; Windows::UI::Xaml::IWindow::Content::get(void)
0x14000cc4e  mov     r14, rax
0x14000cc51  mov     [rsp+0F8h+lpCriticalSection], rax
0x14000cc56  test    rax, rax
0x14000cc59  jz      short loc_14000CC6A
0x14000cc5b  mov     rcx, [rax]
0x14000cc5e  mov     rax, [rcx+8]
0x14000cc62  mov     rcx, r14
0x14000cc65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc6a  mov     [rsp+0F8h+lpCriticalSection], r14
0x14000cc6f  test    r14, r14
0x14000cc72  jz      short loc_14000CC84
0x14000cc74  mov     rax, [r14]
0x14000cc77  mov     rcx, r14
  ... truncated ...
```
