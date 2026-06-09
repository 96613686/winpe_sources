# Windows::Graphics::Capture::Server::CreateCAMCapabilityUsageSession(Windows::Graphics::Capture::Server::CaptureServerAccessRequestKind,Windows::Internal::CapabilityAccess::Management::ICapabilityUsageSession * *)

- ea: `0x18001ea40`
- end: `0x18001ebf2`
- name: `?CreateCAMCapabilityUsageSession@Server@Capture@Graphics@Windows@@YAJW4CaptureServerAccessRequestKind@1234@PEAPEAUICapabilityUsageSession@Management@CapabilityAccess@Internal@4@@Z`
- size: `434`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ccd0`
- `0x18001d350`

## callees

- `0x180002e60`
- `0x18000907c`
- `0x18000ddc4`
- `0x18000f7b4`
- `0x18001ea40`
- `0x18001f208`
- `0x18001f484`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001ead0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001ead0`

## string_xrefs

- `0x18001eab1`: `Windows.Internal.CapabilityAccess.Management.CapabilityUsage`
- `0x18001ea81`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`
- `0x18001eae3`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`
- `0x18001eb32`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`
- `0x18001eb86`: `onecoreuap\windows\dwm\capture\svc\dll\clientprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Graphics::Capture::Server::CreateCAMCapabilityUsageSession(
        unsigned int a1,
        unsigned int *a2)
{
  int ClientProcessId; // eax
  unsigned int v5; // ebx
  int ActivationFactory; // eax
  int v7; // eax
  int v8; // eax
  __int64 v9; // rax
  int v11; // [rsp+20h] [rbp-49h]
  unsigned int v12; // [rsp+30h] [rbp-39h] BYREF
  __int64 v13; // [rsp+38h] [rbp-31h] BYREF
  __int64 v14; // [rsp+40h] [rbp-29h] BYREF
  __int64 v15; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v16[24]; // [rsp+50h] [rbp-19h] BYREF
  __int64 v17; // [rsp+68h] [rbp-1h]
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+7h] BYREF
  __int64 v19; // [rsp+88h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v12 = 0;
  ClientProcessId = Windows::Graphics::Capture::Server::GetClientProcessId(
                      (Windows::Graphics::Capture::Server *)&v12,
                      a2);
  v5 = ClientProcessId;
  if ( ClientProcessId >= 0 )
  {
    v15 = 0;
    v19 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.CapabilityAccess.Management.CapabilityUsage",
      0x3Du,
      0x3Cu);
    ActivationFactory = RoGetActivationFactory(v19, &GUID_42947746_4ea0_48c2_9274_062ed61f8daa, &v15);
    v5 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v14 = 0;
      Windows::Graphics::Capture::Server::GetStringReferenceFromCapability(v16, a1);
      v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v15 + 48LL))(v15, v17, &v14);
      v5 = v7;
      if ( v7 >= 0 )
      {
        v13 = 0;
        v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v14 + 48LL))(v14, v12, 0, &v13);
        v5 = v8;
        if ( v8 >= 0 )
        {
          v9 = v13;
          v13 = 0;
          *(_QWORD *)a2 = v9;
          wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v13);
          v17 = 0;
          wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v14);
          v5 = 0;
          goto LABEL_11;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F8,
          (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\clientprocess.cpp",
          (const char *)(unsigned int)v8,
          v11);
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v13);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1F2,
          (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\clientprocess.cpp",
          (const char *)(unsigned int)v7,
          v11);
      }
      v17 = 0;
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v14);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1EC,
        (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\clientprocess.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v11);
    }
LABEL_11:
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v15);
    return v5;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E6,
    (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\clientprocess.cpp",
    (const char *)(unsigned int)ClientProcessId,
    v11);
  return v5;
}

```

## disassembly

```asm
0x18001ea40  push    rbp
0x18001ea42  push    rbx
0x18001ea43  push    rsi
0x18001ea44  push    rdi
0x18001ea45  lea     rbp, [rsp-3Fh]
0x18001ea4a  sub     rsp, 0A8h
0x18001ea51  mov     rax, cs:__security_cookie
0x18001ea58  xor     rax, rsp
0x18001ea5b  mov     [rbp+57h+var_30], rax
0x18001ea5f  mov     rdi, rdx
0x18001ea62  mov     esi, ecx
0x18001ea64  mov     [rbp+57h+var_90], 0
0x18001ea6b  lea     rcx, [rbp+57h+var_90]; this
0x18001ea6f  call    ?GetClientProcessId@Server@Capture@Graphics@Windows@@YAJPEAK@Z; Windows::Graphics::Capture::Server::GetClientProcessId(ulong *)
0x18001ea74  mov     ebx, eax
0x18001ea76  test    eax, eax
0x18001ea78  jns     short loc_18001EA97
0x18001ea7a  mov     rcx, [rbp+5Fh]; this
0x18001ea7e  mov     r9d, eax; char *
0x18001ea81  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001ea88  mov     edx, 1E6h; void *
0x18001ea8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ea92  jmp     loc_18001EBD8
0x18001ea97  mov     [rbp+57h+var_78], 0
0x18001ea9f  mov     [rbp+57h+var_38], 0
0x18001eaa7  mov     r9d, 3Ch ; '<'; unsigned int
0x18001eaad  lea     r8d, [r9+1]; unsigned int
0x18001eab1  lea     rdx, ?RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityUsage@@3QBGB; "Windows.Internal.CapabilityAccess.Manag"...
0x18001eab8  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001eabc  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001eac1  lea     r8, [rbp+57h+var_78]
0x18001eac5  lea     rdx, _GUID_42947746_4ea0_48c2_9274_062ed61f8daa
0x18001eacc  mov     rcx, [rbp+57h+var_38]
0x18001ead0  call    cs:__imp_RoGetActivationFactory
0x18001ead6  mov     ebx, eax
0x18001ead8  test    eax, eax
0x18001eada  jns     short loc_18001EAF9
0x18001eadc  mov     rcx, [rbp+5Fh]; this
0x18001eae0  mov     r9d, eax; char *
0x18001eae3  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001eaea  mov     edx, 1ECh; void *
0x18001eaef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eaf4  jmp     loc_18001EBCF
0x18001eaf9  mov     [rbp+57h+var_80], 0
0x18001eb01  mov     edx, esi
0x18001eb03  lea     rcx, [rbp+57h+var_70]
0x18001eb07  call    ?GetStringReferenceFromCapability@Server@Capture@Graphics@Windows@@YA?AVHStringReference@Wrappers@WRL@Microsoft@@W4CaptureServerAccessRequestKind@1234@@Z; Windows::Graphics::Capture::Server::GetStringReferenceFromCapability(Windows::Graphics::Capture::Server::CaptureServerAccessRequestKind)
0x18001eb0c  nop
0x18001eb0d  mov     rcx, [rbp+57h+var_78]
0x18001eb11  mov     rax, [rcx]
0x18001eb14  lea     r8, [rbp+57h+var_80]
0x18001eb18  mov     rdx, [rbp+57h+var_58]
0x18001eb1c  mov     rax, [rax+30h]
0x18001eb20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb25  mov     ebx, eax
0x18001eb27  test    eax, eax
0x18001eb29  jns     short loc_18001EB57
0x18001eb2b  mov     rcx, [rbp+5Fh]; this
0x18001eb2f  mov     r9d, eax; char *
0x18001eb32  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001eb39  mov     edx, 1F2h; void *
0x18001eb3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eb43  nop
0x18001eb44  mov     [rbp+57h+var_58], 0
0x18001eb4c  lea     rcx, [rbp+57h+var_80]
0x18001eb50  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001eb55  jmp     short loc_18001EBCF
0x18001eb57  mov     [rbp+57h+var_88], 0
0x18001eb5f  mov     rcx, [rbp+57h+var_80]
0x18001eb63  mov     rax, [rcx]
0x18001eb66  lea     r9, [rbp+57h+var_88]
0x18001eb6a  xor     r8d, r8d
0x18001eb6d  mov     edx, [rbp+57h+var_90]
0x18001eb70  mov     rax, [rax+30h]
0x18001eb74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb79  mov     ebx, eax
0x18001eb7b  test    eax, eax
0x18001eb7d  jns     short loc_18001EBA3
0x18001eb7f  mov     rcx, [rbp+5Fh]; this
0x18001eb83  mov     r9d, eax; char *
0x18001eb86  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001eb8d  mov     edx, 1F8h; void *
0x18001eb92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eb97  nop
0x18001eb98  lea     rcx, [rbp+57h+var_88]
0x18001eb9c  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001eba1  jmp     short loc_18001EB44
0x18001eba3  mov     rax, [rbp+57h+var_88]
0x18001eba7  mov     [rbp+57h+var_88], 0
0x18001ebaf  mov     [rdi], rax
0x18001ebb2  lea     rcx, [rbp+57h+var_88]
0x18001ebb6  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001ebbb  nop
0x18001ebbc  mov     [rbp+57h+var_58], 0
0x18001ebc4  lea     rcx, [rbp+57h+var_80]
0x18001ebc8  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001ebcd  xor     ebx, ebx
0x18001ebcf  lea     rcx, [rbp+57h+var_78]
0x18001ebd3  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001ebd8  mov     eax, ebx
0x18001ebda  mov     rcx, [rbp+57h+var_30]
0x18001ebde  xor     rcx, rsp; StackCookie
0x18001ebe1  call    __security_check_cookie
0x18001ebe6  add     rsp, 0A8h
0x18001ebed  pop     rdi
0x18001ebee  pop     rsi
0x18001ebef  pop     rbx
0x18001ebf0  pop     rbp
0x18001ebf1  retn
```
