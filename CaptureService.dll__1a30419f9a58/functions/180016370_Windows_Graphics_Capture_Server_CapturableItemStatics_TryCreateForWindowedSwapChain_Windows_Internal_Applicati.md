# Windows::Graphics::Capture::Server::CapturableItemStatics::TryCreateForWindowedSwapChain(Windows::Internal::ApplicationModel::WindowManagement::WindowId,Windows::Graphics::Capture::Server::ICapturableItem * *)

- ea: `0x180016370`
- end: `0x18001653a`
- name: `?TryCreateForWindowedSwapChain@CapturableItemStatics@Server@Capture@Graphics@Windows@@UEAAJUWindowId@WindowManagement@ApplicationModel@Internal@5@PEAPEAUICapturableItem@2345@@Z`
- size: `458`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002e60`
- `0x18000907c`
- `0x18000c3e4`
- `0x18000ddc4`
- `0x18000f7b4`
- `0x180015d0c`
- `0x180016370`
- `0x18001e5e4`
- `0x180022010`

## string_xrefs

- `0x1800163b3`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x18001642a`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x18001647a`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x1800164c5`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x1800163df`: `Windows.Internal.CaptureItemProvider`
- `0x180016412`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Graphics::Capture::Server::CapturableItemStatics::TryCreateForWindowedSwapChain(
        __int64 a1,
        bool *a2,
        unsigned __int64 *a3)
{
  unsigned int v4; // edi
  int v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  Windows::Graphics::Capture::Server::CapturableItem *v10; // rax
  int v12; // [rsp+20h] [rbp-50h] BYREF
  Windows::Graphics::Capture::Server::CapturableItem *v13; // [rsp+28h] [rbp-48h] BYREF
  struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *v14; // [rsp+30h] [rbp-40h] BYREF
  __int64 v15; // [rsp+38h] [rbp-38h] BYREF
  struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *v16; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  __int64 v18; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v4 = (unsigned int)a2;
  *a3 = 0;
  LOBYTE(v12) = 0;
  v5 = Windows::Graphics::Capture::Server::AllowAppSiloAndFailUapAndInsufficientIL(
         (Windows::Graphics::Capture::Server *)&v12,
         a2);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v15 = 0;
    v18 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.CaptureItemProvider",
      0x25u,
      0x24u);
    v7 = Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(
           v18,
           0,
           &GUID_81731d62_a2b4_4600_bfdd_fb536bb2382c,
           &v15);
    v6 = v7;
    if ( v7 >= 0 )
    {
      if ( v15 )
      {
        v14 = 0;
        v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem **))(*(_QWORD *)v15 + 48LL))(
               v15,
               v4,
               &v14);
        v6 = v8;
        if ( v8 >= 0 )
        {
          v16 = v14;
          v13 = 0;
          v9 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CapturableItem,Windows::Graphics::Capture::Server::CapturableItem,Windows::Internal::PlatformExtensions::Capture::ICapturableItem *,bool>(
                 &v13,
                 &v16,
                 (char *)&v12);
          v6 = v9;
          if ( v9 >= 0 )
          {
            v10 = v13;
            v13 = 0;
            *a3 = ((unsigned __int64)v10 + 48) & -(__int64)(v10 != 0);
            wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v13);
            wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v14);
            v6 = 0;
            goto LABEL_13;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3B6,
            (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
            (const char *)(unsigned int)v9,
            v12);
          wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v13);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3B0,
            (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
            (const char *)(unsigned int)v8,
            v12);
        }
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v14);
      }
      else
      {
        v6 = -2147024891;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x299,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
        (const char *)(unsigned int)v7,
        v12);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A9,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
        (const char *)v6,
        v12);
    }
LABEL_13:
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v15);
    return v6;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3A2,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
    (const char *)(unsigned int)v5,
    v12);
  return v6;
}

```

## disassembly

```asm
0x180016370  mov     [rsp-18h+arg_0], rbx
0x180016375  push    rbp
0x180016376  push    rsi
0x180016377  push    rdi
0x180016378  mov     rbp, rsp
0x18001637b  sub     rsp, 70h
0x18001637f  mov     rax, cs:__security_cookie
0x180016386  xor     rax, rsp
0x180016389  mov     [rbp+var_8], rax
0x18001638d  mov     rsi, r8
0x180016390  mov     edi, edx
0x180016392  mov     qword ptr [r8], 0
0x180016399  mov     byte ptr [rbp+var_50], 0
0x18001639d  lea     rcx, [rbp+var_50]; this
0x1800163a1  call    ?AllowAppSiloAndFailUapAndInsufficientIL@Server@Capture@Graphics@Windows@@YAJPEA_N@Z; Windows::Graphics::Capture::Server::AllowAppSiloAndFailUapAndInsufficientIL(bool *)
0x1800163a6  mov     ebx, eax
0x1800163a8  test    eax, eax
0x1800163aa  jns     short loc_1800163C9
0x1800163ac  mov     rcx, [rbp+18h]; this
0x1800163b0  mov     r9d, eax; char *
0x1800163b3  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x1800163ba  mov     edx, 3A2h; void *
0x1800163bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800163c4  jmp     loc_18001651C
0x1800163c9  mov     [rbp+var_38], 0
0x1800163d1  xor     ebx, ebx
0x1800163d3  mov     [rbp+var_10], rbx
0x1800163d7  lea     r9d, [rbx+24h]; unsigned int
0x1800163db  lea     r8d, [rbx+25h]; unsigned int
0x1800163df  lea     rdx, aWindowsInterna_0; "Windows.Internal.CaptureItemProvider"
0x1800163e6  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800163ea  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800163ef  lea     r9, [rbp+var_38]
0x1800163f3  lea     r8, _GUID_81731d62_a2b4_4600_bfdd_fb536bb2382c
0x1800163fa  mov     edx, ebx
0x1800163fc  mov     rcx, [rbp+var_10]
0x180016400  call    ?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z; Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)
0x180016405  mov     ebx, eax
0x180016407  test    eax, eax
0x180016409  jns     short loc_180016440
0x18001640b  mov     rcx, [rbp+18h]; this
0x18001640f  mov     r9d, eax; char *
0x180016412  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180016419  mov     edx, 299h; void *
0x18001641e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016423  mov     rcx, [rbp+18h]; this
0x180016427  mov     r9d, ebx; char *
0x18001642a  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180016431  mov     edx, 3A9h; void *
0x180016436  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001643b  jmp     loc_180016513
0x180016440  mov     rcx, [rbp+var_38]
0x180016444  test    rcx, rcx
0x180016447  jnz     short loc_180016453
0x180016449  mov     ebx, 80070005h
0x18001644e  jmp     loc_180016513
0x180016453  mov     [rbp+var_40], 0
0x18001645b  mov     rax, [rcx]
0x18001645e  lea     r8, [rbp+var_40]
0x180016462  mov     edx, edi
0x180016464  mov     rax, [rax+30h]
0x180016468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001646d  mov     ebx, eax
0x18001646f  test    eax, eax
0x180016471  jns     short loc_180016497
0x180016473  mov     rcx, [rbp+18h]; this
0x180016477  mov     r9d, eax; char *
0x18001647a  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180016481  mov     edx, 3B0h; void *
0x180016486  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001648b  nop
0x18001648c  lea     rcx, [rbp+var_40]
0x180016490  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016495  jmp     short loc_180016513
0x180016497  mov     rax, [rbp+var_40]
0x18001649b  mov     [rbp+var_30], rax
0x18001649f  mov     [rbp+var_48], 0
0x1800164a7  lea     r8, [rbp+var_50]
0x1800164ab  lea     rdx, [rbp+var_30]
0x1800164af  lea     rcx, [rbp+var_48]
0x1800164b3  call    ??$MakeAndInitialize@VCapturableItem@Server@Capture@Graphics@Windows@@V12345@PEAUICapturableItem@3PlatformExtensions@Internal@5@_N@Details@WRL@Microsoft@@YAJPEAPEAVCapturableItem@Server@Capture@Graphics@Windows@@$$QEAPEAUICapturableItem@5PlatformExtensions@Internal@7@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CapturableItem,Windows::Graphics::Capture::Server::CapturableItem,Windows::Internal::PlatformExtensions::Capture::ICapturableItem *,bool>(Windows::Graphics::Capture::Server::CapturableItem * *,Windows::Internal::PlatformExtensions::Capture::ICapturableItem * &&,bool &&)
0x1800164b8  mov     ebx, eax
0x1800164ba  test    eax, eax
0x1800164bc  jns     short loc_1800164E2
0x1800164be  mov     rcx, [rbp+18h]; this
0x1800164c2  mov     r9d, eax; char *
0x1800164c5  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x1800164cc  mov     edx, 3B6h; void *
0x1800164d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800164d6  nop
0x1800164d7  lea     rcx, [rbp+var_48]
0x1800164db  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x1800164e0  jmp     short loc_18001648C
0x1800164e2  mov     rax, [rbp+var_48]
0x1800164e6  mov     [rbp+var_48], 0
0x1800164ee  lea     rcx, [rax+30h]
0x1800164f2  neg     rax
0x1800164f5  sbb     rax, rax
0x1800164f8  and     rax, rcx
0x1800164fb  mov     [rsi], rax
0x1800164fe  lea     rcx, [rbp+var_48]
0x180016502  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016507  nop
0x180016508  lea     rcx, [rbp+var_40]
0x18001650c  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016511  xor     ebx, ebx
0x180016513  lea     rcx, [rbp+var_38]
0x180016517  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001651c  mov     eax, ebx
0x18001651e  mov     rcx, [rbp+var_8]
0x180016522  xor     rcx, rsp; StackCookie
0x180016525  call    __security_check_cookie
0x18001652a  mov     rbx, [rsp+70h+arg_0]
0x180016532  add     rsp, 70h
0x180016536  pop     rdi
0x180016537  pop     rsi
0x180016538  pop     rbp
0x180016539  retn
```
