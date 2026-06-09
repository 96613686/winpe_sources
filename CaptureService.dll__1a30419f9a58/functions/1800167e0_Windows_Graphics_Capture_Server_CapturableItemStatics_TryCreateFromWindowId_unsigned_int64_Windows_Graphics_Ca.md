# Windows::Graphics::Capture::Server::CapturableItemStatics::TryCreateFromWindowId(unsigned __int64,Windows::Graphics::Capture::Server::ICapturableItem * *)

- ea: `0x1800167e0`
- end: `0x1800169cf`
- name: `?TryCreateFromWindowId@CapturableItemStatics@Server@Capture@Graphics@Windows@@UEAAJ_KPEAPEAUICapturableItem@2345@@Z`
- size: `495`
- prototype: `__int64 __fastcall(Windows::Graphics::Capture::Server::CapturableItemStatics *__hidden this, unsigned __int64, struct Windows::Graphics::Capture::Server::ICapturableItem **)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002e60`
- `0x18000907c`
- `0x18000c3e4`
- `0x18000ccf8`
- `0x18000ddc4`
- `0x18000f7b4`
- `0x1800167e0`
- `0x180016dc4`
- `0x180017ecc`
- `0x18001e9d4`
- `0x180022010`

## string_xrefs

- `0x18001689b`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x1800168ec`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180016936`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180016856`: `Windows.Internal.CaptureItemProvider`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Graphics::Capture::Server::CapturableItemStatics::TryCreateFromWindowId(
        Windows::Graphics::Capture::Server::CapturableItemStatics *this,
        __int64 a2,
        struct Windows::Graphics::Capture::Server::ICapturableItem **a3)
{
  int v6; // eax
  unsigned int ItemFromInternalWindowId; // ebx
  int v8; // eax
  int v9; // eax
  Windows::Graphics::Capture::Server::CapturableItem *v10; // rax
  int v11; // [rsp+20h] [rbp-50h] BYREF
  __int64 v12; // [rsp+28h] [rbp-48h] BYREF
  Windows::Graphics::Capture::Server::CapturableItem *v13; // [rsp+30h] [rbp-40h] BYREF
  struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *v14; // [rsp+38h] [rbp-38h] BYREF
  struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *v15; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  __int64 v17; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  *a3 = 0;
  if ( !Windows::Graphics::Capture::Server::CheckCAMCapability(0) )
    return 2147942405LL;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::GetImpl'::`2'::impl) )
    return Windows::Graphics::Capture::Server::_anonymous_namespace_::TryCreateItemFromInternalWindowId(
             a2,
             1,
             (unsigned __int64 *)a3);
  v12 = 0;
  v17 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.CaptureItemProvider",
    0x25u,
    0x24u);
  v6 = Windows::Internal::PlatformExtensions::TryActivateContractExtension<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider2>(
         v17,
         (__int64)&v12,
         0);
  ItemFromInternalWindowId = v6;
  if ( v6 == -2147467262 || !v12 )
  {
    ItemFromInternalWindowId = Windows::Graphics::Capture::Server::_anonymous_namespace_::TryCreateItemFromInternalWindowId(
                                 a2,
                                 1,
                                 (unsigned __int64 *)a3);
    goto LABEL_20;
  }
  if ( v6 >= 0 )
  {
    v14 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64, struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem **))(*(_QWORD *)v12 + 48LL))(
           v12,
           a2,
           &v14);
    ItemFromInternalWindowId = v8;
    if ( v8 == -2147024809 )
    {
      *a3 = 0;
LABEL_18:
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v14);
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v12);
      return 0;
    }
    if ( v8 >= 0 )
    {
      if ( !v14 )
        goto LABEL_18;
      LOBYTE(v11) = 1;
      v15 = v14;
      v13 = 0;
      v9 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CapturableItem,Windows::Graphics::Capture::Server::CapturableItem,Windows::Internal::PlatformExtensions::Capture::ICapturableItem *,bool>(
             &v13,
             &v15,
             (char *)&v11);
      ItemFromInternalWindowId = v9;
      if ( v9 >= 0 )
      {
        v10 = v13;
        v13 = 0;
        *a3 = (struct Windows::Graphics::Capture::Server::ICapturableItem *)(((unsigned __int64)v10 + 48)
                                                                           & -(__int64)(v10 != 0));
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v13);
        goto LABEL_18;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C0,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
        (const char *)(unsigned int)v9,
        v11);
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v13);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B7,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
        (const char *)(unsigned int)v8,
        v11);
    }
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v14);
    goto LABEL_20;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2A9,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
    (const char *)(unsigned int)v6,
    v11);
LABEL_20:
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v12);
  return ItemFromInternalWindowId;
}

```

## disassembly

```asm
0x1800167e0  mov     [rsp-18h+arg_0], rbx
0x1800167e5  push    rbp
0x1800167e6  push    rsi
0x1800167e7  push    rdi
0x1800167e8  mov     rbp, rsp
0x1800167eb  sub     rsp, 70h
0x1800167ef  mov     rax, cs:__security_cookie
0x1800167f6  xor     rax, rsp
0x1800167f9  mov     [rbp+var_8], rax
0x1800167fd  mov     rdi, r8
0x180016800  mov     rsi, rdx
0x180016803  mov     qword ptr [r8], 0
0x18001680a  xor     ecx, ecx
0x18001680c  call    ?CheckCAMCapability@Server@Capture@Graphics@Windows@@YA_NW4CaptureServerAccessRequestKind@1234@@Z; Windows::Graphics::Capture::Server::CheckCAMCapability(Windows::Graphics::Capture::Server::CaptureServerAccessRequestKind)
0x180016811  test    al, al
0x180016813  jnz     short loc_18001681F
0x180016815  mov     eax, 80070005h
0x18001681a  jmp     loc_1800169B3
0x18001681f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows> `wil::Feature<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::GetImpl(void)'::`2'::impl
0x180016826  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::__private_IsEnabled(void)
0x18001682b  test    al, al
0x18001682d  jz      short loc_180016840
0x18001682f  mov     r8, rdi
0x180016832  mov     dl, 1
0x180016834  mov     ecx, esi
0x180016836  call    Windows__Graphics__Capture__Server___anonymous_namespace___TryCreateItemFromInternalWindowId
0x18001683b  jmp     loc_1800169B3
0x180016840  mov     [rbp+var_48], 0
0x180016848  xor     ebx, ebx
0x18001684a  mov     [rbp+var_10], rbx
0x18001684e  lea     r9d, [rbx+24h]; unsigned int
0x180016852  lea     r8d, [rbx+25h]; unsigned int
0x180016856  lea     rdx, aWindowsInterna_0; "Windows.Internal.CaptureItemProvider"
0x18001685d  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180016861  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180016866  mov     r8d, ebx
0x180016869  lea     rdx, [rbp+var_48]
0x18001686d  mov     rcx, [rbp+var_10]
0x180016871  call    ??$TryActivateContractExtension@UICaptureItemProvider2@Capture@PlatformExtensions@Internal@Windows@@@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAPEAUICaptureItemProvider2@Capture@012@UWindowId@WindowManagement@ApplicationModel@12@@Z; Windows::Internal::PlatformExtensions::TryActivateContractExtension<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider2>(HSTRING__ *,Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider2 * *,Windows::Internal::ApplicationModel::WindowManagement::WindowId)
0x180016876  mov     ebx, eax
0x180016878  cmp     eax, 80004002h
0x18001687d  jz      loc_18001699A
0x180016883  mov     rcx, [rbp+var_48]
0x180016887  test    rcx, rcx
0x18001688a  jz      loc_18001699A
0x180016890  test    eax, eax
0x180016892  jns     short loc_1800168B1
0x180016894  mov     rcx, [rbp+18h]; this
0x180016898  mov     r9d, eax; char *
0x18001689b  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x1800168a2  mov     edx, 2A9h; void *
0x1800168a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800168ac  jmp     loc_1800169A8
0x1800168b1  mov     [rbp+var_38], 0
0x1800168b9  mov     rax, [rcx]
0x1800168bc  lea     r8, [rbp+var_38]
0x1800168c0  mov     rdx, rsi
0x1800168c3  mov     rax, [rax+30h]
0x1800168c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168cc  mov     ebx, eax
0x1800168ce  cmp     eax, 80070057h
0x1800168d3  jnz     short loc_1800168E1
0x1800168d5  mov     qword ptr [rdi], 0
0x1800168dc  jmp     loc_180016983
0x1800168e1  test    eax, eax
0x1800168e3  jns     short loc_1800168FF
0x1800168e5  mov     rcx, [rbp+18h]; this
0x1800168e9  mov     r9d, eax; char *
0x1800168ec  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x1800168f3  mov     edx, 2B7h; void *
0x1800168f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800168fd  jmp     short loc_180016952
0x1800168ff  mov     rax, [rbp+var_38]
0x180016903  test    rax, rax
0x180016906  jz      short loc_180016983
0x180016908  mov     byte ptr [rbp+var_50], 1
0x18001690c  mov     [rbp+var_30], rax
0x180016910  mov     [rbp+var_40], 0
0x180016918  lea     r8, [rbp+var_50]
0x18001691c  lea     rdx, [rbp+var_30]
0x180016920  lea     rcx, [rbp+var_40]
0x180016924  call    ??$MakeAndInitialize@VCapturableItem@Server@Capture@Graphics@Windows@@V12345@PEAUICapturableItem@3PlatformExtensions@Internal@5@_N@Details@WRL@Microsoft@@YAJPEAPEAVCapturableItem@Server@Capture@Graphics@Windows@@$$QEAPEAUICapturableItem@5PlatformExtensions@Internal@7@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CapturableItem,Windows::Graphics::Capture::Server::CapturableItem,Windows::Internal::PlatformExtensions::Capture::ICapturableItem *,bool>(Windows::Graphics::Capture::Server::CapturableItem * *,Windows::Internal::PlatformExtensions::Capture::ICapturableItem * &&,bool &&)
0x180016929  mov     ebx, eax
0x18001692b  test    eax, eax
0x18001692d  jns     short loc_18001695D
0x18001692f  mov     rcx, [rbp+18h]; this
0x180016933  mov     r9d, eax; char *
0x180016936  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001693d  mov     edx, 2C0h; void *
0x180016942  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016947  nop
0x180016948  lea     rcx, [rbp+var_40]
0x18001694c  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016951  nop
0x180016952  lea     rcx, [rbp+var_38]
0x180016956  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001695b  jmp     short loc_1800169A8
0x18001695d  mov     rax, [rbp+var_40]
0x180016961  mov     [rbp+var_40], 0
0x180016969  lea     rcx, [rax+30h]
0x18001696d  neg     rax
0x180016970  sbb     rax, rax
0x180016973  and     rax, rcx
0x180016976  mov     [rdi], rax
0x180016979  lea     rcx, [rbp+var_40]
0x18001697d  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016982  nop
0x180016983  lea     rcx, [rbp+var_38]
0x180016987  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001698c  nop
0x18001698d  lea     rcx, [rbp+var_48]
0x180016991  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016996  xor     eax, eax
0x180016998  jmp     short loc_1800169B3
0x18001699a  mov     r8, rdi
0x18001699d  mov     dl, 1
0x18001699f  mov     ecx, esi
0x1800169a1  call    Windows__Graphics__Capture__Server___anonymous_namespace___TryCreateItemFromInternalWindowId
0x1800169a6  mov     ebx, eax
0x1800169a8  lea     rcx, [rbp+var_48]
0x1800169ac  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x1800169b1  mov     eax, ebx
0x1800169b3  mov     rcx, [rbp+var_8]
0x1800169b7  xor     rcx, rsp; StackCookie
0x1800169ba  call    __security_check_cookie
0x1800169bf  mov     rbx, [rsp+70h+arg_0]
0x1800169c7  add     rsp, 70h
0x1800169cb  pop     rdi
0x1800169cc  pop     rsi
0x1800169cd  pop     rbp
0x1800169ce  retn
```
