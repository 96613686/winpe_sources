# Windows::Graphics::Capture::Server::_anonymous_namespace_::TryCreateItemFromInternalWindowId

- ea: `0x180016dc4`
- end: `0x180017312`
- name: `Windows::Graphics::Capture::Server::_anonymous_namespace_::TryCreateItemFromInternalWindowId`
- size: `1358`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800162d0`
- `0x1800167e0`

## callees

- `0x180002e60`
- `0x180007630`
- `0x18000907c`
- `0x18000a92c`
- `0x18000c3e4`
- `0x18000cd44`
- `0x18000cf50`
- `0x18000cf88`
- `0x18000ddc4`
- `0x18000e214`
- `0x18000e2ac`
- `0x18000f7b4`
- `0x180016dc4`
- `0x180017ecc`
- `0x180017f44`
- `0x18001881c`
- `0x180022010`

## string_xrefs

- `0x180016e35`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180016ea8`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180016f29`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180016f6e`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x1800170b0`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180017128`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180017223`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180017300`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180016e08`: `Windows.Internal.CaptureItemProvider`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall Windows::Graphics::Capture::Server::_anonymous_namespace_::TryCreateItemFromInternalWindowId(
        unsigned int a1,
        char a2,
        unsigned __int64 *a3)
{
  __int64 v4; // rdi
  int v5; // eax
  const char *v6; // r9
  unsigned int v7; // ebx
  int v8; // eax
  int v9; // eax
  struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *v10; // rcx
  int v11; // eax
  int i; // eax
  __int64 *v13; // rsi
  int (__fastcall ***v14)(_QWORD, GUID *, Windows::Graphics::Capture::Server::CapturableItem **); // rbx
  int v15; // eax
  Windows::Graphics::Capture::Server::CapturableItem *v16; // rax
  int v17; // eax
  int j; // eax
  __int64 *v19; // rsi
  int (__fastcall ***v20)(_QWORD, GUID *, Windows::Graphics::Capture::Server::CapturableItem **); // rbx
  int v21; // eax
  Windows::Graphics::Capture::Server::CapturableItem *v23; // rax
  int v24; // [rsp+20h] [rbp-59h] BYREF
  Windows::Graphics::Capture::Server::CapturableItem *v25; // [rsp+28h] [rbp-51h] BYREF
  struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *v26; // [rsp+30h] [rbp-49h] BYREF
  int v27; // [rsp+38h] [rbp-41h] BYREF
  Windows::Graphics::Capture::Server::CapturableItem *v28; // [rsp+40h] [rbp-39h] BYREF
  struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *v29; // [rsp+48h] [rbp-31h] BYREF
  void (__fastcall ***v30)(_QWORD, GUID *, _QWORD *); // [rsp+50h] [rbp-29h] BYREF
  struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *v31; // [rsp+58h] [rbp-21h] BYREF
  struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *v32; // [rsp+60h] [rbp-19h] BYREF
  int v33; // [rsp+68h] [rbp-11h]
  __int64 v34; // [rsp+70h] [rbp-9h] BYREF
  struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *v35; // [rsp+78h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp+7h] BYREF
  __int64 v37; // [rsp+98h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v4 = a1;
  LOBYTE(v24) = a2;
  *a3 = 0;
  v30 = 0;
  v37 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.CaptureItemProvider",
    0x25u,
    0x24u);
  v5 = Windows::Internal::PlatformExtensions::TryActivateContractExtension<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider>(
         v37,
         (__int64)&v30,
         0);
  v7 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
      (const char *)(unsigned int)v5,
      v24);
LABEL_48:
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v30);
    return v7;
  }
  if ( !v30 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
      v6);
  v26 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::GetImpl'::`2'::impl) )
  {
    wil::com_ptr_t<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider,wil::err_returncode_policy>::try_query<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider4>(
      &v30,
      &v28);
    if ( v28 )
    {
      v8 = (*(__int64 (__fastcall **)(Windows::Graphics::Capture::Server::CapturableItem *, __int64, struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem **))(*(_QWORD *)v28 + 48LL))(
             v28,
             v4,
             &v26);
      v7 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8F,
          (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
          (const char *)(unsigned int)v8,
          v24);
LABEL_8:
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v28);
LABEL_47:
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v26);
        goto LABEL_48;
      }
LABEL_30:
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v28);
      if ( v26 )
      {
        v29 = v26;
        v25 = 0;
        v15 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CapturableItem,Windows::Graphics::Capture::Server::CapturableItem,Windows::Internal::PlatformExtensions::Capture::ICapturableItem *,bool>(
                &v25,
                &v29,
                (char *)&v24);
        v7 = v15;
        if ( v15 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBF,
            (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
            (const char *)(unsigned int)v15,
            v24);
          wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v25);
          goto LABEL_47;
        }
        v16 = v25;
        v25 = 0;
        *a3 = ((unsigned __int64)v16 + 48) & -(__int64)(v16 != 0);
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v25);
      }
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v26);
      v7 = 0;
      goto LABEL_48;
    }
    wil::com_ptr_t<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider,wil::err_returncode_policy>::try_query<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider2>(
      &v30,
      &v31);
    if ( v31 )
    {
      v9 = (*(__int64 (__fastcall **)(struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *, __int64, struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem **))(*(_QWORD *)v31 + 48LL))(
             v31,
             v4,
             &v26);
      v7 = v9;
      if ( v9 == -2147024809 )
      {
        v10 = v26;
        v26 = 0;
        if ( v10 )
          (*(void (__fastcall **)(struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *))(*(_QWORD *)v10 + 16LL))(v10);
        goto LABEL_29;
      }
      if ( v9 >= 0 )
      {
LABEL_29:
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v31);
        goto LABEL_30;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9B,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
        (const char *)(unsigned int)v9,
        v24);
    }
    else
    {
      v35 = 0;
      v11 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *), struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem **))(*v30)[6])(
              v30,
              &v35);
      v7 = v11;
      if ( v11 >= 0 )
      {
        if ( v35 )
        {
          v29 = v35;
          v32 = v35;
          v33 = 0;
          v34 = 0;
          wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_exception_policy>::end(
            &v29,
            &hstringHeader);
          for ( i = v33; i != *(_DWORD *)&hstringHeader.Reserved.Reserved2[8]; i = ++v33 )
          {
            v13 = (__int64 *)wil::vector_range<Windows::Foundation::Collections::IVector<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,wil::err_exception_policy>::vector_iterator::operator*((unsigned int *)&v32);
            v27 = 0;
            v25 = 0;
            v14 = (int (__fastcall ***)(_QWORD, GUID *, Windows::Graphics::Capture::Server::CapturableItem **))*v13;
            wil::com_ptr_t<IDCompositionCaptureRenderTargetInternal,wil::err_returncode_policy>::reset(&v25);
            if ( (**v14)(v14, &GUID_5ed78b65_017c_4cb7_a935_7521855ecc71, &v25) >= 0
              && (*(int (__fastcall **)(Windows::Graphics::Capture::Server::CapturableItem *, int *))(*(_QWORD *)v25 + 48LL))(
                   v25,
                   &v27) >= 0
              && v27 == (_DWORD)v4 )
            {
              wil::com_ptr_t<Windows::Internal::PlatformExtensions::Capture::ICapturableItem,wil::err_returncode_policy>::operator=(
                (__int64 *)&v26,
                *v13);
              wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v25);
              break;
            }
            wil::com_ptr_t<IDCompositionCaptureRenderTargetInternal,wil::err_returncode_policy>::reset(&v25);
            wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v25);
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&hstringHeader.Reserved.Reserved2[16]);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
        }
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v35);
        goto LABEL_29;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA1,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
        (const char *)(unsigned int)v11,
        v24);
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v35);
    }
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v31);
    goto LABEL_8;
  }
  v29 = 0;
  v17 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, _QWORD *), struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem **))(*v30)[6])(
          v30,
          &v29);
  v7 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCD,
      (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
      (const char *)(unsigned int)v17,
      v24);
LABEL_46:
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v29);
    goto LABEL_47;
  }
  if ( v29 )
  {
    v31 = v29;
    v32 = v29;
    v33 = 0;
    v34 = 0;
    wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_exception_policy>::end(
      &v31,
      &hstringHeader);
    for ( j = v33; j != *(_DWORD *)&hstringHeader.Reserved.Reserved2[8]; j = ++v33 )
    {
      v19 = (__int64 *)wil::vector_range<Windows::Foundation::Collections::IVector<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,wil::err_exception_policy>::vector_iterator::operator*((unsigned int *)&v32);
      v27 = 0;
      v25 = 0;
      v20 = (int (__fastcall ***)(_QWORD, GUID *, Windows::Graphics::Capture::Server::CapturableItem **))*v19;
      wil::com_ptr_t<IDCompositionCaptureRenderTargetInternal,wil::err_returncode_policy>::reset(&v25);
      if ( (**v20)(v20, &GUID_5ed78b65_017c_4cb7_a935_7521855ecc71, &v25) >= 0
        && (*(int (__fastcall **)(Windows::Graphics::Capture::Server::CapturableItem *, int *))(*(_QWORD *)v25 + 48LL))(
             v25,
             &v27) >= 0
        && v27 == (_DWORD)v4 )
      {
        wil::com_ptr_t<Windows::Internal::PlatformExtensions::Capture::ICapturableItem,wil::err_returncode_policy>::operator=(
          (__int64 *)&v26,
          *v19);
        v31 = v26;
        v28 = 0;
        v21 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CapturableItem,Windows::Graphics::Capture::Server::CapturableItem,Windows::Internal::PlatformExtensions::Capture::ICapturableItem *,bool>(
                &v28,
                &v31,
                (char *)&v24);
        v7 = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xE0,
            (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
            (const char *)(unsigned int)v21,
            v24);
          wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v28);
          wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v25);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&hstringHeader.Reserved.Reserved2[16]);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
          goto LABEL_46;
        }
        v23 = v28;
        v28 = 0;
        *a3 = ((unsigned __int64)v23 + 48) & -(__int64)(v23 != 0);
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v28);
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v25);
        break;
      }
      wil::com_ptr_t<IDCompositionCaptureRenderTargetInternal,wil::err_returncode_policy>::reset(&v25);
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v25);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&hstringHeader.Reserved.Reserved2[16]);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  }
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v29);
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v26);
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v30);
  return 0;
}

```

## disassembly

```asm
0x180016dc4  mov     [rsp-8+arg_18], rbx
0x180016dc9  push    rbp
0x180016dca  push    rsi
0x180016dcb  push    rdi
0x180016dcc  push    r14
0x180016dce  push    r15
0x180016dd0  lea     rbp, [rsp-37h]
0x180016dd5  sub     rsp, 0B0h
0x180016ddc  mov     rax, cs:__security_cookie
0x180016de3  xor     rax, rsp
0x180016de6  mov     [rbp+57h+var_30], rax
0x180016dea  mov     r14, r8
0x180016ded  mov     edi, ecx
0x180016def  mov     byte ptr [rbp+57h+var_B0], dl
0x180016df2  xor     r15d, r15d
0x180016df5  mov     [r8], r15
0x180016df8  mov     [rbp+57h+var_80], r15
0x180016dfc  mov     [rbp+57h+var_38], r15
0x180016e00  lea     r9d, [r15+24h]; unsigned int
0x180016e04  lea     r8d, [r15+25h]; unsigned int
0x180016e08  lea     rdx, aWindowsInterna_0; "Windows.Internal.CaptureItemProvider"
0x180016e0f  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180016e13  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180016e18  mov     r8d, r15d
0x180016e1b  lea     rdx, [rbp+57h+var_80]
0x180016e1f  mov     rcx, [rbp+57h+var_38]
0x180016e23  call    ??$TryActivateContractExtension@UICaptureItemProvider@Capture@PlatformExtensions@Internal@Windows@@@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAPEAUICaptureItemProvider@Capture@012@UWindowId@WindowManagement@ApplicationModel@12@@Z; Windows::Internal::PlatformExtensions::TryActivateContractExtension<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider>(HSTRING__ *,Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider * *,Windows::Internal::ApplicationModel::WindowManagement::WindowId)
0x180016e28  mov     ebx, eax
0x180016e2a  mov     rcx, [rbp+5Fh]; this
0x180016e2e  test    eax, eax
0x180016e30  jns     short loc_180016E4B
0x180016e32  mov     r9d, eax; char *
0x180016e35  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180016e3c  mov     edx, 84h; void *
0x180016e41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016e46  jmp     loc_180017271
0x180016e4b  cmp     [rbp+57h+var_80], r15
0x180016e4f  jz      loc_180017300
0x180016e55  mov     [rbp+57h+var_A0], r15
0x180016e59  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows> `wil::Feature<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::GetImpl(void)'::`2'::impl
0x180016e60  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Capture_ExpandCapturableWindows>::__private_IsEnabled(void)
0x180016e65  test    al, al
0x180016e67  jz      loc_180017103
0x180016e6d  lea     rdx, [rbp+57h+var_90]
0x180016e71  lea     rcx, [rbp+57h+var_80]
0x180016e75  call    ??$try_query@UICaptureItemProvider4@Capture@PlatformExtensions@Internal@Windows@@@?$com_ptr_t@UICaptureItemProvider@Capture@PlatformExtensions@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UICaptureItemProvider4@Capture@PlatformExtensions@Internal@Windows@@Uerr_returncode_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider,wil::err_returncode_policy>::try_query<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider4>(void)
0x180016e7a  nop
0x180016e7b  mov     rcx, [rbp+57h+var_90]
0x180016e7f  test    rcx, rcx
0x180016e82  jz      short loc_180016EC8
0x180016e84  mov     rdx, rdi
0x180016e87  mov     rax, [rcx]
0x180016e8a  lea     r8, [rbp+57h+var_A0]
0x180016e8e  mov     rax, [rax+30h]
0x180016e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e97  mov     ebx, eax
0x180016e99  test    eax, eax
0x180016e9b  jns     loc_180017078
0x180016ea1  mov     rcx, [rbp+5Fh]; this
0x180016ea5  mov     r9d, eax; char *
0x180016ea8  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180016eaf  mov     edx, 8Fh; void *
0x180016eb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016eb9  nop
0x180016eba  lea     rcx, [rbp+57h+var_90]
0x180016ebe  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016ec3  jmp     loc_180017267
0x180016ec8  lea     rdx, [rbp+57h+var_78]
0x180016ecc  lea     rcx, [rbp+57h+var_80]
0x180016ed0  call    ??$try_query@UICaptureItemProvider2@Capture@PlatformExtensions@Internal@Windows@@@?$com_ptr_t@UICaptureItemProvider@Capture@PlatformExtensions@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UICaptureItemProvider2@Capture@PlatformExtensions@Internal@Windows@@Uerr_returncode_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider,wil::err_returncode_policy>::try_query<Windows::Internal::PlatformExtensions::Capture::ICaptureItemProvider2>(void)
0x180016ed5  nop
0x180016ed6  mov     rcx, [rbp+57h+var_78]
0x180016eda  test    rcx, rcx
0x180016edd  jz      short loc_180016F49
0x180016edf  mov     rax, [rcx]
0x180016ee2  mov     rdx, rdi
0x180016ee5  lea     r8, [rbp+57h+var_A0]
0x180016ee9  mov     rax, [rax+30h]
0x180016eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ef2  mov     ebx, eax
0x180016ef4  cmp     eax, 80070057h
0x180016ef9  jnz     short loc_180016F1A
0x180016efb  mov     rcx, [rbp+57h+var_A0]
0x180016eff  mov     [rbp+57h+var_A0], r15
0x180016f03  test    rcx, rcx
0x180016f06  jz      short loc_180016F15
0x180016f08  mov     rax, [rcx]
0x180016f0b  mov     rax, [rax+10h]
0x180016f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f14  nop
0x180016f15  jmp     loc_18001706E
0x180016f1a  test    eax, eax
0x180016f1c  jns     loc_18001706E
0x180016f22  mov     rcx, [rbp+5Fh]; this
0x180016f26  mov     r9d, eax; char *
0x180016f29  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180016f30  mov     edx, 9Bh; void *
0x180016f35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016f3a  nop
0x180016f3b  lea     rcx, [rbp+57h+var_78]
0x180016f3f  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016f44  jmp     loc_180016EBA
0x180016f49  mov     [rbp+57h+var_58], r15
0x180016f4d  mov     rcx, [rbp+57h+var_80]
0x180016f51  mov     rax, [rcx]
0x180016f54  lea     rdx, [rbp+57h+var_58]
0x180016f58  mov     rax, [rax+30h]
0x180016f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f61  mov     ebx, eax
0x180016f63  test    eax, eax
0x180016f65  jns     short loc_180016F8B
0x180016f67  mov     rcx, [rbp+5Fh]; this
0x180016f6b  mov     r9d, eax; char *
0x180016f6e  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180016f75  mov     edx, 0A1h; void *
0x180016f7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016f7f  nop
0x180016f80  lea     rcx, [rbp+57h+var_58]
0x180016f84  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016f89  jmp     short loc_180016F3B
0x180016f8b  mov     rax, [rbp+57h+var_58]
0x180016f8f  test    rax, rax
0x180016f92  jz      loc_180017064
0x180016f98  mov     [rbp+57h+var_88], rax
0x180016f9c  mov     [rbp+57h+var_70], rax
0x180016fa0  mov     [rbp+57h+var_68], r15d
0x180016fa4  mov     [rbp+57h+var_60], r15
0x180016fa8  lea     rdx, [rbp+57h+hstringHeader]
0x180016fac  lea     rcx, [rbp+57h+var_88]
0x180016fb0  call    ?end@?$vector_range@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_exception_policy>::end(void)
0x180016fb5  nop
0x180016fb6  mov     eax, [rbp+57h+var_68]
0x180016fb9  cmp     eax, dword ptr [rbp+57h+hstringHeader.Reserved+8]
0x180016fbc  jz      loc_180017050
0x180016fc2  lea     rcx, [rbp+57h+var_70]
0x180016fc6  call    ??Dvector_iterator@?$vector_range@U?$IVector@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@UICapturableItem@Capture@PlatformExtensions@Internal@Windows@@@WRL@Microsoft@@XZ; wil::vector_range<Windows::Foundation::Collections::IVector<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,wil::err_exception_policy>::vector_iterator::operator*(void)
0x180016fcb  mov     rsi, rax
0x180016fce  mov     [rbp+57h+var_98], r15d
0x180016fd2  mov     [rbp+57h+var_A8], r15
0x180016fd6  mov     rbx, [rax]
0x180016fd9  lea     rcx, [rbp+57h+var_A8]
0x180016fdd  call    ?reset@?$com_ptr_t@UIDCompositionCaptureRenderTargetInternal@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IDCompositionCaptureRenderTargetInternal,wil::err_returncode_policy>::reset(void)
0x180016fe2  mov     rdx, [rbx]
0x180016fe5  mov     rax, [rdx]
0x180016fe8  lea     r8, [rbp+57h+var_A8]
0x180016fec  lea     rdx, _GUID_5ed78b65_017c_4cb7_a935_7521855ecc71
0x180016ff3  mov     rcx, rbx
0x180016ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ffb  test    eax, eax
0x180016ffd  js      short loc_18001701C
0x180016fff  mov     rcx, [rbp+57h+var_A8]
0x180017003  mov     rax, [rcx]
0x180017006  lea     rdx, [rbp+57h+var_98]
0x18001700a  mov     rax, [rax+30h]
0x18001700e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017013  test    eax, eax
0x180017015  js      short loc_18001701C
0x180017017  cmp     [rbp+57h+var_98], edi
0x18001701a  jz      short loc_180017039
0x18001701c  lea     rcx, [rbp+57h+var_A8]
0x180017020  call    ?reset@?$com_ptr_t@UIDCompositionCaptureRenderTargetInternal@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IDCompositionCaptureRenderTargetInternal,wil::err_returncode_policy>::reset(void)
0x180017025  nop
0x180017026  lea     rcx, [rbp+57h+var_A8]
0x18001702a  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001702f  mov     eax, [rbp+57h+var_68]
0x180017032  inc     eax
0x180017034  mov     [rbp+57h+var_68], eax
0x180017037  jmp     short loc_180016FB9
0x180017039  mov     rdx, [rsi]
0x18001703c  lea     rcx, [rbp+57h+var_A0]
0x180017040  call    ??4?$com_ptr_t@UICapturableItem@Capture@PlatformExtensions@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUICapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::PlatformExtensions::Capture::ICapturableItem,wil::err_returncode_policy>::operator=(Windows::Internal::PlatformExtensions::Capture::ICapturableItem *)
0x180017045  nop
0x180017046  lea     rcx, [rbp+57h+var_A8]
0x18001704a  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001704f  nop
0x180017050  lea     rcx, [rbp+57h+hstringHeader.Reserved+10h]
0x180017054  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017059  nop
0x18001705a  lea     rcx, [rbp+57h+var_60]
0x18001705e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017063  nop
0x180017064  lea     rcx, [rbp+57h+var_58]
0x180017068  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001706d  nop
0x18001706e  lea     rcx, [rbp+57h+var_78]
0x180017072  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180017077  nop
0x180017078  lea     rcx, [rbp+57h+var_90]
0x18001707c  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180017081  mov     rax, [rbp+57h+var_A0]
0x180017085  test    rax, rax
0x180017088  jz      short loc_1800170F2
0x18001708a  mov     [rbp+57h+var_88], rax
0x18001708e  mov     [rbp+57h+var_A8], r15
0x180017092  lea     r8, [rbp+57h+var_B0]
0x180017096  lea     rdx, [rbp+57h+var_88]
0x18001709a  lea     rcx, [rbp+57h+var_A8]
0x18001709e  call    ??$MakeAndInitialize@VCapturableItem@Server@Capture@Graphics@Windows@@V12345@PEAUICapturableItem@3PlatformExtensions@Internal@5@_N@Details@WRL@Microsoft@@YAJPEAPEAVCapturableItem@Server@Capture@Graphics@Windows@@$$QEAPEAUICapturableItem@5PlatformExtensions@Internal@7@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CapturableItem,Windows::Graphics::Capture::Server::CapturableItem,Windows::Internal::PlatformExtensions::Capture::ICapturableItem *,bool>(Windows::Graphics::Capture::Server::CapturableItem * *,Windows::Internal::PlatformExtensions::Capture::ICapturableItem * &&,bool &&)
0x1800170a3  mov     ebx, eax
0x1800170a5  test    eax, eax
0x1800170a7  jns     short loc_1800170D0
0x1800170a9  mov     rcx, [rbp+5Fh]; this
0x1800170ad  mov     r9d, eax; char *
0x1800170b0  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x1800170b7  mov     edx, 0BFh; void *
0x1800170bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800170c1  nop
0x1800170c2  lea     rcx, [rbp+57h+var_A8]
0x1800170c6  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x1800170cb  jmp     loc_180017267
0x1800170d0  mov     rax, [rbp+57h+var_A8]
0x1800170d4  mov     [rbp+57h+var_A8], r15
0x1800170d8  lea     rcx, [rax+30h]
0x1800170dc  neg     rax
0x1800170df  sbb     rax, rax
0x1800170e2  and     rax, rcx
0x1800170e5  mov     [r14], rax
0x1800170e8  lea     rcx, [rbp+57h+var_A8]
0x1800170ec  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x1800170f1  nop
0x1800170f2  lea     rcx, [rbp+57h+var_A0]
0x1800170f6  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x1800170fb  mov     ebx, r15d
0x1800170fe  jmp     loc_180017271
0x180017103  mov     [rbp+57h+var_88], r15
0x180017107  mov     rcx, [rbp+57h+var_80]
0x18001710b  mov     rax, [rcx]
0x18001710e  lea     rdx, [rbp+57h+var_88]
0x180017112  mov     rax, [rax+30h]
0x180017116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001711b  mov     ebx, eax
0x18001711d  test    eax, eax
0x18001711f  jns     short loc_18001713E
0x180017121  mov     rcx, [rbp+5Fh]; this
0x180017125  mov     r9d, eax; char *
0x180017128  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001712f  mov     edx, 0CDh; void *
0x180017134  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017139  jmp     loc_18001725D
0x18001713e  mov     rax, [rbp+57h+var_88]
0x180017142  test    rax, rax
0x180017145  jz      loc_1800172BE
0x18001714b  mov     [rbp+57h+var_78], rax
0x18001714f  mov     [rbp+57h+var_70], rax
0x180017153  mov     [rbp+57h+var_68], r15d
0x180017157  mov     [rbp+57h+var_60], r15
0x18001715b  lea     rdx, [rbp+57h+hstringHeader]
0x18001715f  lea     rcx, [rbp+57h+var_78]
0x180017163  call    ?end@?$vector_range@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_exception_policy>::end(void)
0x180017168  nop
0x180017169  mov     eax, [rbp+57h+var_68]
0x18001716c  cmp     eax, dword ptr [rbp+57h+hstringHeader.Reserved+8]
0x18001716f  jz      loc_1800172AA
0x180017175  lea     rcx, [rbp+57h+var_70]
0x180017179  call    ??Dvector_iterator@?$vector_range@U?$IVector@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@UICapturableItem@Capture@PlatformExtensions@Internal@Windows@@@WRL@Microsoft@@XZ; wil::vector_range<Windows::Foundation::Collections::IVector<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,wil::err_exception_policy>::vector_iterator::operator*(void)
0x18001717e  mov     rsi, rax
0x180017181  mov     [rbp+57h+var_98], r15d
0x180017185  mov     [rbp+57h+var_A8], r15
0x180017189  mov     rbx, [rax]
0x18001718c  lea     rcx, [rbp+57h+var_A8]
0x180017190  call    ?reset@?$com_ptr_t@UIDCompositionCaptureRenderTargetInternal@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IDCompositionCaptureRenderTargetInternal,wil::err_returncode_policy>::reset(void)
0x180017195  mov     rdx, [rbx]
0x180017198  mov     rax, [rdx]
0x18001719b  lea     r8, [rbp+57h+var_A8]
0x18001719f  lea     rdx, _GUID_5ed78b65_017c_4cb7_a935_7521855ecc71
0x1800171a6  mov     rcx, rbx
0x1800171a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171ae  test    eax, eax
0x1800171b0  js      short loc_1800171CF
0x1800171b2  mov     rcx, [rbp+57h+var_A8]
0x1800171b6  mov     rax, [rcx]
0x1800171b9  lea     rdx, [rbp+57h+var_98]
0x1800171bd  mov     rax, [rax+30h]
0x1800171c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171c6  test    eax, eax
0x1800171c8  js      short loc_1800171CF
0x1800171ca  cmp     [rbp+57h+var_98], edi
0x1800171cd  jz      short loc_1800171EC
0x1800171cf  lea     rcx, [rbp+57h+var_A8]
0x1800171d3  call    ?reset@?$com_ptr_t@UIDCompositionCaptureRenderTargetInternal@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IDCompositionCaptureRenderTargetInternal,wil::err_returncode_policy>::reset(void)
0x1800171d8  nop
0x1800171d9  lea     rcx, [rbp+57h+var_A8]
0x1800171dd  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x1800171e2  mov     eax, [rbp+57h+var_68]
0x1800171e5  inc     eax
0x1800171e7  mov     [rbp+57h+var_68], eax
0x1800171ea  jmp     short loc_18001716C
0x1800171ec  mov     rdx, [rsi]
0x1800171ef  lea     rcx, [rbp+57h+var_A0]
0x1800171f3  call    ??4?$com_ptr_t@UICapturableItem@Capture@PlatformExtensions@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUICapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Z; wil::com_ptr_t<Windows::Internal::PlatformExtensions::Capture::ICapturableItem,wil::err_returncode_policy>::operator=(Windows::Internal::PlatformExtensions::Capture::ICapturableItem *)
0x1800171f8  nop
0x1800171f9  mov     rax, [rbp+57h+var_A0]
0x1800171fd  mov     [rbp+57h+var_78], rax
0x180017201  mov     [rbp+57h+var_90], r15
0x180017205  lea     r8, [rbp+57h+var_B0]
0x180017209  lea     rdx, [rbp+57h+var_78]
0x18001720d  lea     rcx, [rbp+57h+var_90]
0x180017211  call    ??$MakeAndInitialize@VCapturableItem@Server@Capture@Graphics@Windows@@V12345@PEAUICapturableItem@3PlatformExtensions@Internal@5@_N@Details@WRL@Microsoft@@YAJPEAPEAVCapturableItem@Server@Capture@Graphics@Windows@@$$QEAPEAUICapturableItem@5PlatformExtensions@Internal@7@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CapturableItem,Windows::Graphics::Capture::Server::CapturableItem,Windows::Internal::PlatformExtensions::Capture::ICapturableItem *,bool>(Windows::Graphics::Capture::Server::CapturableItem * *,Windows::Internal::PlatformExtensions::Capture::ICapturableItem * &&,bool &&)
0x180017216  mov     ebx, eax
0x180017218  test    eax, eax
  ... truncated ...
```
