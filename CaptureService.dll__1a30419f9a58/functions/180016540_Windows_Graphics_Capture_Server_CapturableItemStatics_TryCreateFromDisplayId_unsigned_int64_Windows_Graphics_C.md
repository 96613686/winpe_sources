# Windows::Graphics::Capture::Server::CapturableItemStatics::TryCreateFromDisplayId(unsigned __int64,Windows::Graphics::Capture::Server::ICapturableItem * *)

- ea: `0x180016540`
- end: `0x1800167cf`
- name: `?TryCreateFromDisplayId@CapturableItemStatics@Server@Capture@Graphics@Windows@@UEAAJ_KPEAPEAUICapturableItem@2345@@Z`
- size: `655`
- prototype: `__int64 __fastcall(Windows::Graphics::Capture::Server::CapturableItemStatics *__hidden this, unsigned __int64, struct Windows::Graphics::Capture::Server::ICapturableItem **)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002e60`
- `0x18000907c`
- `0x18000c3e4`
- `0x18000ccf8`
- `0x18000ddc4`
- `0x18000df0c`
- `0x18000f7b4`
- `0x180010f5c`
- `0x180016540`
- `0x1800169d8`
- `0x180017ecc`
- `0x1800186b0`
- `0x18001e9d4`
- `0x180022010`

## string_xrefs

- `0x1800165b4`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x18001663b`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x18001667a`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x1800166d0`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x18001671e`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x1800165f8`: `Windows.Internal.CaptureItemProvider`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Graphics::Capture::Server::CapturableItemStatics::TryCreateFromDisplayId(
        Windows::Graphics::Capture::Server::CapturableItemStatics *this,
        __int64 a2,
        struct Windows::Graphics::Capture::Server::ICapturableItem **a3)
{
  int v6; // eax
  unsigned int ItemFromHmonitor; // ebx
  int v8; // eax
  __int64 v9; // rax
  int DeviceIdFromDisplayId; // eax
  int v11; // eax
  int v12; // eax
  Windows::Graphics::Capture::Server::CapturableItem *v13; // rax
  int v14; // [rsp+20h] [rbp-60h] BYREF
  struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *v15; // [rsp+28h] [rbp-58h] BYREF
  HSTRING v16; // [rsp+30h] [rbp-50h] BYREF
  __int64 v17; // [rsp+38h] [rbp-48h] BYREF
  Windows::Graphics::Capture::Server::CapturableItem *v18; // [rsp+40h] [rbp-40h] BYREF
  struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *v19; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  __int64 v21; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  *a3 = 0;
  if ( !Windows::Graphics::Capture::Server::CheckCAMCapability(0) )
    return 2147942405LL;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::GetImpl'::`2'::impl) )
  {
    v17 = 0;
    v21 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.CaptureItemProvider",
      0x25u,
      0x24u);
    v8 = Windows::Internal::PlatformExtensions::TryActivateContractExtension<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider2>(
           v21,
           (__int64)&v17,
           0);
    ItemFromHmonitor = v8;
    if ( v8 == -2147467262 || !v17 )
    {
      ItemFromHmonitor = Windows::Graphics::Capture::Server::_anonymous_namespace_::TryCreateItemFromHmonitor(
                           a2,
                           1,
                           (unsigned __int64 *)a3);
      goto LABEL_26;
    }
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x33E,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
        (const char *)(unsigned int)v8,
        v14);
LABEL_26:
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v17);
      return ItemFromHmonitor;
    }
    v16 = 0;
    v9 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::put(&v16);
    DeviceIdFromDisplayId = Windows::Graphics::Capture::Server::_anonymous_namespace_::GetDeviceIdFromDisplayId(a2, v9);
    ItemFromHmonitor = DeviceIdFromDisplayId;
    if ( DeviceIdFromDisplayId < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x341,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
        (const char *)(unsigned int)DeviceIdFromDisplayId,
        v14);
LABEL_21:
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v16);
      goto LABEL_26;
    }
    v15 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, HSTRING, struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem **))(*(_QWORD *)v17 + 56LL))(
            v17,
            v16,
            &v15);
    ItemFromHmonitor = v11;
    if ( v11 == -2147024809 )
    {
      *a3 = 0;
LABEL_23:
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v15);
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v16);
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v17);
      return 0;
    }
    if ( v11 >= 0 )
    {
      if ( !v15 )
        goto LABEL_23;
      LOBYTE(v14) = 1;
      v19 = v15;
      v18 = 0;
      v12 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CapturableItem,Windows::Graphics::Capture::Server::CapturableItem,Windows::Internal::PlatformExtensions::Capture::ICapturableItem *,bool>(
              &v18,
              &v19,
              (char *)&v14);
      ItemFromHmonitor = v12;
      if ( v12 >= 0 )
      {
        v13 = v18;
        v18 = 0;
        *a3 = (struct Windows::Graphics::Capture::Server::ICapturableItem *)(((unsigned __int64)v13 + 48)
                                                                           & -(__int64)(v13 != 0));
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v18);
        goto LABEL_23;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x358,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
        (const char *)(unsigned int)v12,
        v14);
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v18);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x34F,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
        (const char *)(unsigned int)v11,
        v14);
    }
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v15);
    goto LABEL_21;
  }
  v15 = 0;
  v6 = Windows::Graphics::Capture::Server::_anonymous_namespace_::TryCreateItemFromHmonitor(
         a2,
         1,
         (unsigned __int64 *)a3);
  ItemFromHmonitor = v6;
  if ( v6 >= 0 )
  {
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v15);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x32E,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
    (const char *)(unsigned int)v6,
    v14);
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v15);
  return ItemFromHmonitor;
}

```

## disassembly

```asm
0x180016540  mov     [rsp-18h+arg_0], rbx
0x180016545  push    rbp
0x180016546  push    rsi
0x180016547  push    rdi
0x180016548  mov     rbp, rsp
0x18001654b  sub     rsp, 80h
0x180016552  mov     rax, cs:__security_cookie
0x180016559  xor     rax, rsp
0x18001655c  mov     [rbp+var_10], rax
0x180016560  mov     rdi, r8
0x180016563  mov     rsi, rdx
0x180016566  mov     qword ptr [r8], 0
0x18001656d  xor     ecx, ecx
0x18001656f  call    ?CheckCAMCapability@Server@Capture@Graphics@Windows@@YA_NW4CaptureServerAccessRequestKind@1234@@Z; Windows::Graphics::Capture::Server::CheckCAMCapability(Windows::Graphics::Capture::Server::CaptureServerAccessRequestKind)
0x180016574  test    al, al
0x180016576  jnz     short loc_180016582
0x180016578  mov     eax, 80070005h
0x18001657d  jmp     loc_1800167B0
0x180016582  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows> `wil::Feature<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::GetImpl(void)'::`2'::impl
0x180016589  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::__private_IsEnabled(void)
0x18001658e  test    al, al
0x180016590  jz      short loc_1800165E2
0x180016592  mov     [rbp+var_58], 0
0x18001659a  mov     r8, rdi
0x18001659d  mov     dl, 1
0x18001659f  mov     rcx, rsi
0x1800165a2  call    Windows__Graphics__Capture__Server___anonymous_namespace___TryCreateItemFromHmonitor
0x1800165a7  mov     ebx, eax
0x1800165a9  test    eax, eax
0x1800165ab  jns     short loc_1800165D4
0x1800165ad  mov     rcx, [rbp+18h]; this
0x1800165b1  mov     r9d, eax; char *
0x1800165b4  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x1800165bb  mov     edx, 32Eh; void *
0x1800165c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800165c5  nop
0x1800165c6  lea     rcx, [rbp+var_58]
0x1800165ca  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x1800165cf  jmp     loc_1800167AE
0x1800165d4  lea     rcx, [rbp+var_58]
0x1800165d8  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x1800165dd  jmp     loc_180016792
0x1800165e2  mov     [rbp+var_48], 0
0x1800165ea  xor     ebx, ebx
0x1800165ec  mov     [rbp+var_18], rbx
0x1800165f0  lea     r9d, [rbx+24h]; unsigned int
0x1800165f4  lea     r8d, [rbx+25h]; unsigned int
0x1800165f8  lea     rdx, aWindowsInterna_0; "Windows.Internal.CaptureItemProvider"
0x1800165ff  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180016603  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180016608  mov     r8d, ebx
0x18001660b  lea     rdx, [rbp+var_48]
0x18001660f  mov     rcx, [rbp+var_18]
0x180016613  call    ??$TryActivateContractExtension@UICaptureItemProvider2@Capture@PlatformExtensions@Internal@Windows@@@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAPEAUICaptureItemProvider2@Capture@012@UWindowId@WindowManagement@ApplicationModel@12@@Z; Windows::Internal::PlatformExtensions::TryActivateContractExtension<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider2>(HSTRING__ *,Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider2 * *,Windows::Internal::ApplicationModel::WindowManagement::WindowId)
0x180016618  mov     ebx, eax
0x18001661a  cmp     eax, 80004002h
0x18001661f  jz      loc_180016796
0x180016625  cmp     [rbp+var_48], 0
0x18001662a  jz      loc_180016796
0x180016630  test    eax, eax
0x180016632  jns     short loc_180016651
0x180016634  mov     rcx, [rbp+18h]; this
0x180016638  mov     r9d, eax; char *
0x18001663b  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180016642  mov     edx, 33Eh; void *
0x180016647  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001664c  jmp     loc_1800167A5
0x180016651  mov     [rbp+var_50], 0
0x180016659  lea     rcx, [rbp+var_50]
0x18001665d  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHSTRING__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::put(void)
0x180016662  mov     rdx, rax
0x180016665  mov     rcx, rsi
0x180016668  call    Windows__Graphics__Capture__Server___anonymous_namespace___GetDeviceIdFromDisplayId
0x18001666d  mov     ebx, eax
0x18001666f  test    eax, eax
0x180016671  jns     short loc_180016690
0x180016673  mov     rcx, [rbp+18h]; this
0x180016677  mov     r9d, eax; char *
0x18001667a  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180016681  mov     edx, 341h; void *
0x180016686  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001668b  jmp     loc_180016744
0x180016690  mov     [rbp+var_58], 0
0x180016698  mov     rcx, [rbp+var_48]
0x18001669c  mov     rax, [rcx]
0x18001669f  lea     r8, [rbp+var_58]
0x1800166a3  mov     rdx, [rbp+var_50]
0x1800166a7  mov     rax, [rax+38h]
0x1800166ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166b0  mov     ebx, eax
0x1800166b2  cmp     eax, 80070057h
0x1800166b7  jnz     short loc_1800166C5
0x1800166b9  mov     qword ptr [rdi], 0
0x1800166c0  jmp     loc_180016775
0x1800166c5  test    eax, eax
0x1800166c7  jns     short loc_1800166E3
0x1800166c9  mov     rcx, [rbp+18h]; this
0x1800166cd  mov     r9d, eax; char *
0x1800166d0  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x1800166d7  mov     edx, 34Fh; void *
0x1800166dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800166e1  jmp     short loc_18001673A
0x1800166e3  mov     rax, [rbp+var_58]
0x1800166e7  test    rax, rax
0x1800166ea  jz      loc_180016775
0x1800166f0  mov     byte ptr [rbp+var_60], 1
0x1800166f4  mov     [rbp+var_38], rax
0x1800166f8  mov     [rbp+var_40], 0
0x180016700  lea     r8, [rbp+var_60]
0x180016704  lea     rdx, [rbp+var_38]
0x180016708  lea     rcx, [rbp+var_40]
0x18001670c  call    ??$MakeAndInitialize@VCapturableItem@Server@Capture@Graphics@Windows@@V12345@PEAUICapturableItem@3PlatformExtensions@Internal@5@_N@Details@WRL@Microsoft@@YAJPEAPEAVCapturableItem@Server@Capture@Graphics@Windows@@$$QEAPEAUICapturableItem@5PlatformExtensions@Internal@7@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CapturableItem,Windows::Graphics::Capture::Server::CapturableItem,Windows::Internal::PlatformExtensions::Capture::ICapturableItem *,bool>(Windows::Graphics::Capture::Server::CapturableItem * *,Windows::Internal::PlatformExtensions::Capture::ICapturableItem * &&,bool &&)
0x180016711  mov     ebx, eax
0x180016713  test    eax, eax
0x180016715  jns     short loc_18001674F
0x180016717  mov     rcx, [rbp+18h]; this
0x18001671b  mov     r9d, eax; char *
0x18001671e  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180016725  mov     edx, 358h; void *
0x18001672a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001672f  nop
0x180016730  lea     rcx, [rbp+var_40]
0x180016734  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016739  nop
0x18001673a  lea     rcx, [rbp+var_58]
0x18001673e  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016743  nop
0x180016744  lea     rcx, [rbp+var_50]
0x180016748  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18001674d  jmp     short loc_1800167A5
0x18001674f  mov     rax, [rbp+var_40]
0x180016753  mov     [rbp+var_40], 0
0x18001675b  lea     rcx, [rax+30h]
0x18001675f  neg     rax
0x180016762  sbb     rax, rax
0x180016765  and     rax, rcx
0x180016768  mov     [rdi], rax
0x18001676b  lea     rcx, [rbp+var_40]
0x18001676f  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016774  nop
0x180016775  lea     rcx, [rbp+var_58]
0x180016779  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001677e  nop
0x18001677f  lea     rcx, [rbp+var_50]
0x180016783  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180016788  nop
0x180016789  lea     rcx, [rbp+var_48]
0x18001678d  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016792  xor     eax, eax
0x180016794  jmp     short loc_1800167B0
0x180016796  mov     r8, rdi
0x180016799  mov     dl, 1
0x18001679b  mov     rcx, rsi
0x18001679e  call    Windows__Graphics__Capture__Server___anonymous_namespace___TryCreateItemFromHmonitor
0x1800167a3  mov     ebx, eax
0x1800167a5  lea     rcx, [rbp+var_48]
0x1800167a9  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x1800167ae  mov     eax, ebx
0x1800167b0  mov     rcx, [rbp+var_10]
0x1800167b4  xor     rcx, rsp; StackCookie
0x1800167b7  call    __security_check_cookie
0x1800167bc  mov     rbx, [rsp+80h+arg_0]
0x1800167c4  add     rsp, 80h
0x1800167cb  pop     rdi
0x1800167cc  pop     rsi
0x1800167cd  pop     rbp
0x1800167ce  retn
```
