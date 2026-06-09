# Windows::Graphics::Capture::Server::_anonymous_namespace_::TryCreateItemFromHmonitor

- ea: `0x1800169d8`
- end: `0x180016dbb`
- name: `Windows::Graphics::Capture::Server::_anonymous_namespace_::TryCreateItemFromHmonitor`
- size: `995`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016240`
- `0x180016540`

## callees

- `0x180002e60`
- `0x18000907c`
- `0x18000a92c`
- `0x18000c3e4`
- `0x18000cd44`
- `0x18000cf50`
- `0x18000cf88`
- `0x18000d4a4`
- `0x18000ddc4`
- `0x18000df0c`
- `0x18000f7b4`
- `0x180010f5c`
- `0x1800169d8`
- `0x180017318`
- `0x180017ecc`
- `0x1800186b0`
- `0x180022010`

## string_xrefs

- `0x180016a45`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180016ab8`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180016b1d`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180016ba8`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180016c4d`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180016cc5`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180016d25`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180016da9`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180016a18`: `Windows.Internal.CaptureItemProvider`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall Windows::Graphics::Capture::Server::_anonymous_namespace_::TryCreateItemFromHmonitor(
        __int64 a1,
        char a2,
        unsigned __int64 *a3)
{
  int v5; // eax
  const char *v6; // r9
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v9; // rax
  int DeviceIdFromDisplayId; // eax
  __int64 v11; // rdx
  int v12; // eax
  __int64 *v13; // rax
  int v14; // eax
  Windows::Graphics::Capture::Server::CapturableItem *v15; // rax
  int v16; // eax
  __int64 *v17; // rax
  int v18; // eax
  Windows::Graphics::Capture::Server::CapturableItem *v20; // rax
  int v21; // [rsp+20h] [rbp-39h] BYREF
  Windows::Graphics::Capture::Server::CapturableItem *v22; // [rsp+28h] [rbp-31h] BYREF
  struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *CaptureItemForMonitor; // [rsp+30h] [rbp-29h] BYREF
  Windows::Graphics::Capture::Server::CapturableItem *v24; // [rsp+38h] [rbp-21h] BYREF
  void (__fastcall ***v25)(_QWORD, GUID *, _QWORD *); // [rsp+40h] [rbp-19h] BYREF
  HSTRING v26; // [rsp+48h] [rbp-11h] BYREF
  struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *v27; // [rsp+50h] [rbp-9h] BYREF
  __int64 v28; // [rsp+58h] [rbp-1h] BYREF
  __int64 v29; // [rsp+60h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v31; // [rsp+80h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  LOBYTE(v21) = a2;
  *a3 = 0;
  v25 = 0;
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.CaptureItemProvider",
    0x25u,
    0x24u);
  v5 = Windows::Internal::PlatformExtensions::TryActivateContractExtension<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider>(
         v31,
         (__int64)&v25,
         0);
  v7 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFE,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
      (const char *)(unsigned int)v5,
      v21);
LABEL_38:
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v25);
    return v7;
  }
  if ( !v25 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
      v6);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::GetImpl'::`2'::impl) )
  {
    CaptureItemForMonitor = 0;
    wil::com_ptr_t<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider,wil::err_returncode_policy>::try_query<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider4>(
      &v25,
      &v29);
    if ( v29 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, __int64, struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem **))(*(_QWORD *)v29 + 56LL))(
             v29,
             a1,
             &CaptureItemForMonitor);
      v7 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x10A,
          (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
          (const char *)(unsigned int)v8,
          v21);
LABEL_8:
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v29);
LABEL_9:
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&CaptureItemForMonitor);
        goto LABEL_38;
      }
LABEL_26:
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v29);
      if ( CaptureItemForMonitor )
      {
        v27 = CaptureItemForMonitor;
        v22 = 0;
        v14 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CapturableItem,Windows::Graphics::Capture::Server::CapturableItem,Windows::Internal::PlatformExtensions::Capture::ICapturableItem *,bool>(
                &v22,
                &v27,
                (char *)&v21);
        v7 = v14;
        if ( v14 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x130,
            (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
            (const char *)(unsigned int)v14,
            v21);
          wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v22);
          goto LABEL_9;
        }
        v15 = v22;
        v22 = 0;
        *a3 = ((unsigned __int64)v15 + 48) & -(__int64)(v15 != 0);
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v22);
      }
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&CaptureItemForMonitor);
      v7 = 0;
      goto LABEL_38;
    }
    wil::com_ptr_t<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider,wil::err_returncode_policy>::try_query<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider2>(
      &v25,
      &v28);
    if ( v28 )
    {
      v26 = 0;
      v9 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::put(&v26);
      DeviceIdFromDisplayId = Windows::Graphics::Capture::Server::_anonymous_namespace_::GetDeviceIdFromDisplayId(
                                a1,
                                v9);
      v7 = DeviceIdFromDisplayId;
      if ( DeviceIdFromDisplayId < 0 )
      {
        v11 = 271;
LABEL_13:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v11,
          (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
          (const char *)(unsigned int)DeviceIdFromDisplayId,
          v21);
        wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v26);
LABEL_14:
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v28);
        goto LABEL_8;
      }
      DeviceIdFromDisplayId = (*(__int64 (__fastcall **)(__int64, HSTRING, struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem **))(*(_QWORD *)v28 + 56LL))(
                                v28,
                                v26,
                                &CaptureItemForMonitor);
      v7 = DeviceIdFromDisplayId;
      if ( DeviceIdFromDisplayId == -2147024809 )
      {
        *a3 = 0;
      }
      else if ( DeviceIdFromDisplayId < 0 )
      {
        v11 = 281;
        goto LABEL_13;
      }
      wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v26);
    }
    else
    {
      v24 = 0;
      v12 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *), Windows::Graphics::Capture::Server::CapturableItem **))(*v25)[6])(
              v25,
              &v24);
      v7 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x121,
          (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
          (const char *)(unsigned int)v12,
          v21);
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v24);
        goto LABEL_14;
      }
      if ( v24 )
      {
        v13 = wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,wil::err_returncode_policy>::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,wil::err_returncode_policy>(
                (__int64 *)&v26,
                (__int64 *)&v24);
        CaptureItemForMonitor = (struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *)Windows::Graphics::Capture::Server::_anonymous_namespace_::TryFindCaptureItemForMonitor(a1, v13);
      }
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v24);
    }
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v28);
    goto LABEL_26;
  }
  v22 = 0;
  v16 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *), Windows::Graphics::Capture::Server::CapturableItem **))(*v25)[6])(
          v25,
          &v22);
  v7 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13D,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
      (const char *)(unsigned int)v16,
      v21);
LABEL_37:
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v22);
    goto LABEL_38;
  }
  if ( v22 )
  {
    v17 = wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,wil::err_returncode_policy>::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,wil::err_returncode_policy>(
            (__int64 *)&v27,
            (__int64 *)&v22);
    v27 = (struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *)Windows::Graphics::Capture::Server::_anonymous_namespace_::TryFindCaptureItemForMonitor(
                                                                                      a1,
                                                                                      v17);
    if ( v27 )
    {
      v24 = 0;
      v18 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CapturableItem,Windows::Graphics::Capture::Server::CapturableItem,Windows::Internal::PlatformExtensions::Capture::ICapturableItem *,bool>(
              &v24,
              &v27,
              (char *)&v21);
      v7 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x149,
          (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
          (const char *)(unsigned int)v18,
          v21);
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v24);
        goto LABEL_37;
      }
      v20 = v24;
      v24 = 0;
      *a3 = ((unsigned __int64)v20 + 48) & -(__int64)(v20 != 0);
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v24);
    }
  }
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v22);
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v25);
  return 0;
}

```

## disassembly

```asm
0x1800169d8  push    rbp
0x1800169da  push    rbx
0x1800169db  push    rsi
0x1800169dc  push    rdi
0x1800169dd  push    r14
0x1800169df  lea     rbp, [rsp-37h]
0x1800169e4  sub     rsp, 90h
0x1800169eb  mov     rax, cs:__security_cookie
0x1800169f2  xor     rax, rsp
0x1800169f5  mov     [rbp+57h+var_28], rax
0x1800169f9  mov     rdi, r8
0x1800169fc  mov     rsi, rcx
0x1800169ff  mov     byte ptr [rbp+57h+var_90], dl
0x180016a02  xor     r14d, r14d
0x180016a05  mov     [r8], r14
0x180016a08  mov     [rbp+57h+var_70], r14
0x180016a0c  mov     [rbp+57h+var_30], r14
0x180016a10  lea     r9d, [r14+24h]; unsigned int
0x180016a14  lea     r8d, [r14+25h]; unsigned int
0x180016a18  lea     rdx, aWindowsInterna_0; "Windows.Internal.CaptureItemProvider"
0x180016a1f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180016a23  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180016a28  mov     r8d, r14d
0x180016a2b  lea     rdx, [rbp+57h+var_70]
0x180016a2f  mov     rcx, [rbp+57h+var_30]
0x180016a33  call    ??$TryActivateContractExtension@UICaptureItemProvider@Capture@PlatformExtensions@Internal@Windows@@@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAPEAUICaptureItemProvider@Capture@012@UWindowId@WindowManagement@ApplicationModel@12@@Z; Windows::Internal::PlatformExtensions::TryActivateContractExtension<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider>(HSTRING__ *,Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider * *,Windows::Internal::ApplicationModel::WindowManagement::WindowId)
0x180016a38  mov     ebx, eax
0x180016a3a  mov     rcx, [rbp+5Fh]; this
0x180016a3e  test    eax, eax
0x180016a40  jns     short loc_180016A5B
0x180016a42  mov     r9d, eax; char *
0x180016a45  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180016a4c  mov     edx, 0FEh; void *
0x180016a51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016a56  jmp     loc_180016D4B
0x180016a5b  cmp     [rbp+57h+var_70], r14
0x180016a5f  jz      loc_180016DA9
0x180016a65  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows> `wil::Feature<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::GetImpl(void)'::`2'::impl
0x180016a6c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::__private_IsEnabled(void)
0x180016a71  test    al, al
0x180016a73  jz      loc_180016CA0
0x180016a79  mov     [rbp+57h+var_80], r14
0x180016a7d  lea     rdx, [rbp+57h+var_50]
0x180016a81  lea     rcx, [rbp+57h+var_70]
0x180016a85  call    ??$try_query@UICaptureItemProvider4@Capture@PlatformExtensions@Internal@Windows@@@?$com_ptr_t@UICaptureItemProvider@Capture@PlatformExtensions@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UICaptureItemProvider4@Capture@PlatformExtensions@Internal@Windows@@Uerr_returncode_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider,wil::err_returncode_policy>::try_query<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider4>(void)
0x180016a8a  nop
0x180016a8b  mov     rcx, [rbp+57h+var_50]
0x180016a8f  test    rcx, rcx
0x180016a92  jz      short loc_180016AE2
0x180016a94  mov     rax, [rcx]
0x180016a97  lea     r8, [rbp+57h+var_80]
0x180016a9b  mov     rdx, rsi
0x180016a9e  mov     rax, [rax+38h]
0x180016aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016aa7  mov     ebx, eax
0x180016aa9  test    eax, eax
0x180016aab  jns     loc_180016C15
0x180016ab1  mov     rcx, [rbp+5Fh]; this
0x180016ab5  mov     r9d, eax; char *
0x180016ab8  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180016abf  mov     edx, 10Ah; void *
0x180016ac4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016ac9  nop
0x180016aca  lea     rcx, [rbp+57h+var_50]
0x180016ace  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016ad3  nop
0x180016ad4  lea     rcx, [rbp+57h+var_80]
0x180016ad8  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016add  jmp     loc_180016D4B
0x180016ae2  lea     rdx, [rbp+57h+var_58]
0x180016ae6  lea     rcx, [rbp+57h+var_70]
0x180016aea  call    ??$try_query@UICaptureItemProvider2@Capture@PlatformExtensions@Internal@Windows@@@?$com_ptr_t@UICaptureItemProvider@Capture@PlatformExtensions@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UICaptureItemProvider2@Capture@PlatformExtensions@Internal@Windows@@Uerr_returncode_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider,wil::err_returncode_policy>::try_query<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider2>(void)
0x180016aef  nop
0x180016af0  cmp     [rbp+57h+var_58], r14
0x180016af4  jz      loc_180016B83
0x180016afa  mov     [rbp+57h+var_68], r14
0x180016afe  lea     rcx, [rbp+57h+var_68]
0x180016b02  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHSTRING__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::put(void)
0x180016b07  mov     rdx, rax
0x180016b0a  mov     rcx, rsi
0x180016b0d  call    Windows__Graphics__Capture__Server___anonymous_namespace___GetDeviceIdFromDisplayId
0x180016b12  mov     ebx, eax
0x180016b14  test    eax, eax
0x180016b16  jns     short loc_180016B46
0x180016b18  mov     edx, 10Fh; void *
0x180016b1d  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180016b24  mov     r9d, eax; char *
0x180016b27  mov     rcx, [rbp+5Fh]; this
0x180016b2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016b30  nop
0x180016b31  lea     rcx, [rbp+57h+var_68]
0x180016b35  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180016b3a  nop
0x180016b3b  lea     rcx, [rbp+57h+var_58]
0x180016b3f  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016b44  jmp     short loc_180016ACA
0x180016b46  mov     rcx, [rbp+57h+var_58]
0x180016b4a  mov     rax, [rcx]
0x180016b4d  lea     r8, [rbp+57h+var_80]
0x180016b51  mov     rdx, [rbp+57h+var_68]
0x180016b55  mov     rax, [rax+38h]
0x180016b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b5e  mov     ebx, eax
0x180016b60  cmp     eax, 80070057h
0x180016b65  jnz     short loc_180016B78
0x180016b67  mov     [rdi], r14
0x180016b6a  lea     rcx, [rbp+57h+var_68]
0x180016b6e  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180016b73  jmp     loc_180016C0B
0x180016b78  test    eax, eax
0x180016b7a  jns     short loc_180016B6A
0x180016b7c  mov     edx, 119h
0x180016b81  jmp     short loc_180016B1D
0x180016b83  mov     [rbp+57h+var_78], r14
0x180016b87  mov     rcx, [rbp+57h+var_70]
0x180016b8b  mov     rax, [rcx]
0x180016b8e  lea     rdx, [rbp+57h+var_78]
0x180016b92  mov     rax, [rax+30h]
0x180016b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b9b  mov     ebx, eax
0x180016b9d  test    eax, eax
0x180016b9f  jns     short loc_180016BC8
0x180016ba1  mov     rcx, [rbp+5Fh]; this
0x180016ba5  mov     r9d, eax; char *
0x180016ba8  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180016baf  mov     edx, 121h; void *
0x180016bb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016bb9  nop
0x180016bba  lea     rcx, [rbp+57h+var_78]
0x180016bbe  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016bc3  jmp     loc_180016B3B
0x180016bc8  cmp     [rbp+57h+var_78], r14
0x180016bcc  jz      short loc_180016C01
0x180016bce  lea     rdx, [rbp+57h+var_78]
0x180016bd2  lea     rcx, [rbp+57h+var_68]
0x180016bd6  call    ??0?$com_ptr_t@U?$IVector@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,wil::err_returncode_policy>::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,wil::err_returncode_policy>(wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,wil::err_returncode_policy> const &)
0x180016bdb  mov     rdx, rax
0x180016bde  mov     rcx, rsi
0x180016be1  call    Windows__Graphics__Capture__Server___anonymous_namespace___TryFindCaptureItemForMonitor
0x180016be6  nop
0x180016be7  mov     rcx, [rbp+57h+var_80]
0x180016beb  mov     [rbp+57h+var_80], rax
0x180016bef  test    rcx, rcx
0x180016bf2  jz      short loc_180016C01
0x180016bf4  mov     rax, [rcx]
0x180016bf7  mov     rax, [rax+10h]
0x180016bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c00  nop
0x180016c01  lea     rcx, [rbp+57h+var_78]
0x180016c05  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016c0a  nop
0x180016c0b  lea     rcx, [rbp+57h+var_58]
0x180016c0f  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016c14  nop
0x180016c15  lea     rcx, [rbp+57h+var_50]
0x180016c19  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016c1e  mov     rax, [rbp+57h+var_80]
0x180016c22  test    rax, rax
0x180016c25  jz      short loc_180016C8F
0x180016c27  mov     [rbp+57h+var_60], rax
0x180016c2b  mov     [rbp+57h+var_88], r14
0x180016c2f  lea     r8, [rbp+57h+var_90]
0x180016c33  lea     rdx, [rbp+57h+var_60]
0x180016c37  lea     rcx, [rbp+57h+var_88]
0x180016c3b  call    ??$MakeAndInitialize@VCapturableItem@Server@Capture@Graphics@Windows@@V12345@PEAUICapturableItem@3PlatformExtensions@Internal@5@_N@Details@WRL@Microsoft@@YAJPEAPEAVCapturableItem@Server@Capture@Graphics@Windows@@$$QEAPEAUICapturableItem@5PlatformExtensions@Internal@7@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CapturableItem,Windows::Graphics::Capture::Server::CapturableItem,Windows::Internal::PlatformExtensions::Capture::ICapturableItem *,bool>(Windows::Graphics::Capture::Server::CapturableItem * *,Windows::Internal::PlatformExtensions::Capture::ICapturableItem * &&,bool &&)
0x180016c40  mov     ebx, eax
0x180016c42  test    eax, eax
0x180016c44  jns     short loc_180016C6D
0x180016c46  mov     rcx, [rbp+5Fh]; this
0x180016c4a  mov     r9d, eax; char *
0x180016c4d  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180016c54  mov     edx, 130h; void *
0x180016c59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016c5e  nop
0x180016c5f  lea     rcx, [rbp+57h+var_88]
0x180016c63  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016c68  jmp     loc_180016AD4
0x180016c6d  mov     rax, [rbp+57h+var_88]
0x180016c71  mov     [rbp+57h+var_88], r14
0x180016c75  lea     rcx, [rax+30h]
0x180016c79  neg     rax
0x180016c7c  sbb     rax, rax
0x180016c7f  and     rax, rcx
0x180016c82  mov     [rdi], rax
0x180016c85  lea     rcx, [rbp+57h+var_88]
0x180016c89  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016c8e  nop
0x180016c8f  lea     rcx, [rbp+57h+var_80]
0x180016c93  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016c98  mov     ebx, r14d
0x180016c9b  jmp     loc_180016D4B
0x180016ca0  mov     [rbp+57h+var_88], r14
0x180016ca4  mov     rcx, [rbp+57h+var_70]
0x180016ca8  mov     rax, [rcx]
0x180016cab  lea     rdx, [rbp+57h+var_88]
0x180016caf  mov     rax, [rax+30h]
0x180016cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cb8  mov     ebx, eax
0x180016cba  test    eax, eax
0x180016cbc  jns     short loc_180016CD8
0x180016cbe  mov     rcx, [rbp+5Fh]; this
0x180016cc2  mov     r9d, eax; char *
0x180016cc5  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180016ccc  mov     edx, 13Dh; void *
0x180016cd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016cd6  jmp     short loc_180016D41
0x180016cd8  cmp     [rbp+57h+var_88], r14
0x180016cdc  jz      loc_180016D7A
0x180016ce2  lea     rdx, [rbp+57h+var_88]
0x180016ce6  lea     rcx, [rbp+57h+var_60]
0x180016cea  call    ??0?$com_ptr_t@U?$IVector@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,wil::err_returncode_policy>::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,wil::err_returncode_policy>(wil::com_ptr_t<Windows::Foundation::Collections::IVector<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,wil::err_returncode_policy> const &)
0x180016cef  mov     rdx, rax
0x180016cf2  mov     rcx, rsi
0x180016cf5  call    Windows__Graphics__Capture__Server___anonymous_namespace___TryFindCaptureItemForMonitor
0x180016cfa  mov     [rbp+57h+var_60], rax
0x180016cfe  test    rax, rax
0x180016d01  jz      short loc_180016D7A
0x180016d03  mov     [rbp+57h+var_78], r14
0x180016d07  lea     r8, [rbp+57h+var_90]
0x180016d0b  lea     rdx, [rbp+57h+var_60]
0x180016d0f  lea     rcx, [rbp+57h+var_78]
0x180016d13  call    ??$MakeAndInitialize@VCapturableItem@Server@Capture@Graphics@Windows@@V12345@PEAUICapturableItem@3PlatformExtensions@Internal@5@_N@Details@WRL@Microsoft@@YAJPEAPEAVCapturableItem@Server@Capture@Graphics@Windows@@$$QEAPEAUICapturableItem@5PlatformExtensions@Internal@7@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CapturableItem,Windows::Graphics::Capture::Server::CapturableItem,Windows::Internal::PlatformExtensions::Capture::ICapturableItem *,bool>(Windows::Graphics::Capture::Server::CapturableItem * *,Windows::Internal::PlatformExtensions::Capture::ICapturableItem * &&,bool &&)
0x180016d18  mov     ebx, eax
0x180016d1a  test    eax, eax
0x180016d1c  jns     short loc_180016D58
0x180016d1e  mov     rcx, [rbp+5Fh]; this
0x180016d22  mov     r9d, eax; char *
0x180016d25  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180016d2c  mov     edx, 149h; void *
0x180016d31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016d36  nop
0x180016d37  lea     rcx, [rbp+57h+var_78]
0x180016d3b  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016d40  nop
0x180016d41  lea     rcx, [rbp+57h+var_88]
0x180016d45  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016d4a  nop
0x180016d4b  lea     rcx, [rbp+57h+var_70]
0x180016d4f  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016d54  mov     eax, ebx
0x180016d56  jmp     short loc_180016D8F
0x180016d58  mov     rax, [rbp+57h+var_78]
0x180016d5c  mov     [rbp+57h+var_78], r14
0x180016d60  lea     rcx, [rax+30h]
0x180016d64  neg     rax
0x180016d67  sbb     rax, rax
0x180016d6a  and     rax, rcx
0x180016d6d  mov     [rdi], rax
0x180016d70  lea     rcx, [rbp+57h+var_78]
0x180016d74  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016d79  nop
0x180016d7a  lea     rcx, [rbp+57h+var_88]
0x180016d7e  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016d83  nop
0x180016d84  lea     rcx, [rbp+57h+var_70]
0x180016d88  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016d8d  xor     eax, eax
0x180016d8f  mov     rcx, [rbp+57h+var_28]
0x180016d93  xor     rcx, rsp; StackCookie
0x180016d96  call    __security_check_cookie
0x180016d9b  add     rsp, 90h
0x180016da2  pop     r14
0x180016da4  pop     rdi
0x180016da5  pop     rsi
0x180016da6  pop     rbx
0x180016da7  pop     rbp
0x180016da8  retn
0x180016da9  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180016db0  mov     edx, 101h; void *
0x180016db5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
