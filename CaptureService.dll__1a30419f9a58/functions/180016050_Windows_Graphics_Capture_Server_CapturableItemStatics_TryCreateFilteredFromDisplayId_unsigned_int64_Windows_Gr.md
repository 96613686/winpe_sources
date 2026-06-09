# Windows::Graphics::Capture::Server::CapturableItemStatics::TryCreateFilteredFromDisplayId(unsigned __int64,Windows::Graphics::Capture::Server::ICapturableItem * *)

- ea: `0x180016050`
- end: `0x18001623a`
- name: `?TryCreateFilteredFromDisplayId@CapturableItemStatics@Server@Capture@Graphics@Windows@@UEAAJ_KPEAPEAUICapturableItem@2345@@Z`
- size: `490`
- prototype: `__int64 __fastcall(Windows::Graphics::Capture::Server::CapturableItemStatics *__hidden this, unsigned __int64, struct Windows::Graphics::Capture::Server::ICapturableItem **)`
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
- `0x180016050`
- `0x18001e9d4`
- `0x180022010`

## string_xrefs

- `0x180016111`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x180016162`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x1800161b0`: `onecoreuap\windows\dwm\capture\svc\dll\capturableitem.cpp`
- `0x1800160a5`: `Windows.Internal.CaptureItemProvider`
- `0x1800160d8`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Graphics::Capture::Server::CapturableItemStatics::TryCreateFilteredFromDisplayId(
        Windows::Graphics::Capture::Server::CapturableItemStatics *this,
        __int64 a2,
        struct Windows::Graphics::Capture::Server::ICapturableItem **a3)
{
  int v6; // eax
  int v7; // ebx
  int v8; // eax
  int v9; // eax
  Windows::Graphics::Capture::Server::CapturableItem *v10; // rax
  int v11; // [rsp+20h] [rbp-50h] BYREF
  Windows::Graphics::Capture::Server::CapturableItem *v12; // [rsp+28h] [rbp-48h] BYREF
  struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *v13; // [rsp+30h] [rbp-40h] BYREF
  __int64 v14; // [rsp+38h] [rbp-38h] BYREF
  struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem *v15; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  __int64 v17; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  *a3 = 0;
  if ( !Windows::Graphics::Capture::Server::CheckCAMCapability(0) )
    return 2147942405LL;
  v14 = 0;
  v17 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.CaptureItemProvider",
    0x25u,
    0x24u);
  v6 = Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(
         v17,
         0,
         &GUID_ade12509_3bfc_420a_8bc0_136632a9adf5,
         &v14);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v7 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x299,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)v6,
      v11);
    if ( v7 == -2147467262 )
      goto LABEL_21;
  }
  if ( v14 )
  {
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37A,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
        (const char *)(unsigned int)v7,
        v11);
LABEL_18:
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v14);
      return (unsigned int)v7;
    }
    v13 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64, struct Windows::Internal::PlatformExtensions::Capture::ICapturableItem **))(*(_QWORD *)v14 + 48LL))(
           v14,
           a2,
           &v13);
    v7 = v8;
    if ( v8 == -2147024809 )
    {
      *a3 = 0;
LABEL_20:
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v13);
      goto LABEL_21;
    }
    if ( v8 >= 0 )
    {
      if ( !v13 )
        goto LABEL_20;
      LOBYTE(v11) = 1;
      v15 = v13;
      v12 = 0;
      v9 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CapturableItem,Windows::Graphics::Capture::Server::CapturableItem,Windows::Internal::PlatformExtensions::Capture::ICapturableItem *,bool>(
             &v12,
             &v15,
             (char *)&v11);
      v7 = v9;
      if ( v9 >= 0 )
      {
        v10 = v12;
        v12 = 0;
        *a3 = (struct Windows::Graphics::Capture::Server::ICapturableItem *)(((unsigned __int64)v10 + 48)
                                                                           & -(__int64)(v10 != 0));
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v12);
        goto LABEL_20;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x390,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
        (const char *)(unsigned int)v9,
        v11);
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v12);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x387,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturableitem.cpp",
        (const char *)(unsigned int)v8,
        v11);
    }
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v13);
    goto LABEL_18;
  }
LABEL_21:
  wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v14);
  return 0;
}

```

## disassembly

```asm
0x180016050  mov     [rsp-18h+arg_0], rbx
0x180016055  push    rbp
0x180016056  push    rsi
0x180016057  push    rdi
0x180016058  mov     rbp, rsp
0x18001605b  sub     rsp, 70h
0x18001605f  mov     rax, cs:__security_cookie
0x180016066  xor     rax, rsp
0x180016069  mov     [rbp+var_8], rax
0x18001606d  mov     rdi, r8
0x180016070  mov     rsi, rdx
0x180016073  mov     qword ptr [r8], 0
0x18001607a  xor     ecx, ecx
0x18001607c  call    ?CheckCAMCapability@Server@Capture@Graphics@Windows@@YA_NW4CaptureServerAccessRequestKind@1234@@Z; Windows::Graphics::Capture::Server::CheckCAMCapability(Windows::Graphics::Capture::Server::CaptureServerAccessRequestKind)
0x180016081  test    al, al
0x180016083  jnz     short loc_18001608F
0x180016085  mov     eax, 80070005h
0x18001608a  jmp     loc_18001621E
0x18001608f  mov     [rbp+var_38], 0
0x180016097  xor     ebx, ebx
0x180016099  mov     [rbp+var_10], rbx
0x18001609d  lea     r9d, [rbx+24h]; unsigned int
0x1800160a1  lea     r8d, [rbx+25h]; unsigned int
0x1800160a5  lea     rdx, aWindowsInterna_0; "Windows.Internal.CaptureItemProvider"
0x1800160ac  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800160b0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800160b5  lea     r9, [rbp+var_38]
0x1800160b9  lea     r8, _GUID_ade12509_3bfc_420a_8bc0_136632a9adf5
0x1800160c0  mov     edx, ebx
0x1800160c2  mov     rcx, [rbp+var_10]
0x1800160c6  call    ?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z; Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)
0x1800160cb  mov     ebx, eax
0x1800160cd  test    eax, eax
0x1800160cf  jns     short loc_1800160F7
0x1800160d1  mov     rcx, [rbp+18h]; this
0x1800160d5  mov     r9d, eax; char *
0x1800160d8  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x1800160df  mov     edx, 299h; void *
0x1800160e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800160e9  cmp     ebx, 80004002h
0x1800160ef  jz      loc_180016213
0x1800160f5  jmp     short loc_1800160F9
0x1800160f7  xor     ebx, ebx
0x1800160f9  mov     rcx, [rbp+var_38]
0x1800160fd  test    rcx, rcx
0x180016100  jz      loc_180016213
0x180016106  test    ebx, ebx
0x180016108  jns     short loc_180016127
0x18001610a  mov     rcx, [rbp+18h]; this
0x18001610e  mov     r9d, ebx; char *
0x180016111  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180016118  mov     edx, 37Ah; void *
0x18001611d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016122  jmp     loc_1800161D6
0x180016127  mov     [rbp+var_40], 0
0x18001612f  mov     rax, [rcx]
0x180016132  lea     r8, [rbp+var_40]
0x180016136  mov     rdx, rsi
0x180016139  mov     rax, [rax+30h]
0x18001613d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016142  mov     ebx, eax
0x180016144  cmp     eax, 80070057h
0x180016149  jnz     short loc_180016157
0x18001614b  mov     qword ptr [rdi], 0
0x180016152  jmp     loc_180016209
0x180016157  test    eax, eax
0x180016159  jns     short loc_180016175
0x18001615b  mov     rcx, [rbp+18h]; this
0x18001615f  mov     r9d, eax; char *
0x180016162  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x180016169  mov     edx, 387h; void *
0x18001616e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016173  jmp     short loc_1800161CC
0x180016175  mov     rax, [rbp+var_40]
0x180016179  test    rax, rax
0x18001617c  jz      loc_180016209
0x180016182  mov     byte ptr [rbp+var_50], 1
0x180016186  mov     [rbp+var_30], rax
0x18001618a  mov     [rbp+var_48], 0
0x180016192  lea     r8, [rbp+var_50]
0x180016196  lea     rdx, [rbp+var_30]
0x18001619a  lea     rcx, [rbp+var_48]
0x18001619e  call    ??$MakeAndInitialize@VCapturableItem@Server@Capture@Graphics@Windows@@V12345@PEAUICapturableItem@3PlatformExtensions@Internal@5@_N@Details@WRL@Microsoft@@YAJPEAPEAVCapturableItem@Server@Capture@Graphics@Windows@@$$QEAPEAUICapturableItem@5PlatformExtensions@Internal@7@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Graphics::Capture::Server::CapturableItem,Windows::Graphics::Capture::Server::CapturableItem,Windows::Internal::PlatformExtensions::Capture::ICapturableItem *,bool>(Windows::Graphics::Capture::Server::CapturableItem * *,Windows::Internal::PlatformExtensions::Capture::ICapturableItem * &&,bool &&)
0x1800161a3  mov     ebx, eax
0x1800161a5  test    eax, eax
0x1800161a7  jns     short loc_1800161E3
0x1800161a9  mov     rcx, [rbp+18h]; this
0x1800161ad  mov     r9d, eax; char *
0x1800161b0  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x1800161b7  mov     edx, 390h; void *
0x1800161bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800161c1  nop
0x1800161c2  lea     rcx, [rbp+var_48]
0x1800161c6  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x1800161cb  nop
0x1800161cc  lea     rcx, [rbp+var_40]
0x1800161d0  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x1800161d5  nop
0x1800161d6  lea     rcx, [rbp+var_38]
0x1800161da  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x1800161df  mov     eax, ebx
0x1800161e1  jmp     short loc_18001621E
0x1800161e3  mov     rax, [rbp+var_48]
0x1800161e7  mov     [rbp+var_48], 0
0x1800161ef  lea     rcx, [rax+30h]
0x1800161f3  neg     rax
0x1800161f6  sbb     rax, rax
0x1800161f9  and     rax, rcx
0x1800161fc  mov     [rdi], rax
0x1800161ff  lea     rcx, [rbp+var_48]
0x180016203  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016208  nop
0x180016209  lea     rcx, [rbp+var_40]
0x18001620d  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180016212  nop
0x180016213  lea     rcx, [rbp+var_38]
0x180016217  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001621c  xor     eax, eax
0x18001621e  mov     rcx, [rbp+var_8]
0x180016222  xor     rcx, rsp; StackCookie
0x180016225  call    __security_check_cookie
0x18001622a  mov     rbx, [rsp+70h+arg_0]
0x180016232  add     rsp, 70h
0x180016236  pop     rdi
0x180016237  pop     rsi
0x180016238  pop     rbp
0x180016239  retn
```
