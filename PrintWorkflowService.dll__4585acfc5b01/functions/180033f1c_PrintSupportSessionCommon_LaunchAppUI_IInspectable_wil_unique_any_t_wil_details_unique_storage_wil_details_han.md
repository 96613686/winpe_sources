# PrintSupportSessionCommon::LaunchAppUI(IInspectable *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x180033f1c`
- end: `0x1800341f9`
- name: `?LaunchAppUI@PrintSupportSessionCommon@@QEAAJPEAUIInspectable@@AEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `733`
- prototype: `__int64 __fastcall(PrintSupportSessionCommon *this, int, HANDLE *)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003d1f8`
- `0x1800444e4`

## callees

- `0x1800096d0`
- `0x180009718`
- `0x1800127a4`
- `0x1800128a4`
- `0x1800129dc`
- `0x180012b10`
- `0x1800147fc`
- `0x18001a7c0`
- `0x180023664`
- `0x18002ef08`
- `0x18002f308`
- `0x180031288`
- `0x180031a6c`
- `0x180033c50`
- `0x180033f1c`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003408f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003408f`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180034143`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180034143`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180033ff3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180033ff3`

## string_xrefs

- `0x180034197`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsessioncommon.cpp`
- `0x1800341ab`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsessioncommon.cpp`
- `0x1800341bc`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsessioncommon.cpp`
- `0x1800341d1`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsessioncommon.cpp`
- `0x1800341e6`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportsessioncommon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PrintSupportSessionCommon::LaunchAppUI(PrintSupportSessionCommon *this, int a2, HANDLE *a3)
{
  int v6; // eax
  int v7; // eax
  HANDLE v8; // rax
  const char *v9; // r9
  PrintSupportSessionCommon *v10; // rcx
  const char *v11; // r9
  HRESULT Instance; // eax
  _QWORD *v13; // rsi
  __int64 v14; // r14
  const unsigned __int16 *v15; // rax
  __int64 v16; // rdx
  int v17; // eax
  DWORD ProcessId; // eax
  PrintSupportSessionCommon *v19; // rcx
  __int64 result; // rax
  int ppv; // [rsp+20h] [rbp-58h]
  int ppva; // [rsp+20h] [rbp-58h]
  __int64 v23; // [rsp+50h] [rbp-28h] BYREF
  __int64 v24; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  _QWORD *dwProcessId; // [rsp+80h] [rbp+8h] BYREF
  __int64 v27; // [rsp+98h] [rbp+20h] BYREF

  try
  {
    if ( !*((_BYTE *)this + 121) )
      PrintSupportSessionCommon::InitializeCentennialAppData(this);
    if ( *((_BYTE *)this + 120) )
    {
      dwProcessId = 0;
      Instance = CoCreateInstance(
                   &GUID_168eb462_775f_42ae_9111_d714b2306c2e,
                   0,
                   1u,
                   &GUID_f158268a_d5a5_45ce_99cf_00d6c3f3fc0a,
                   (LPVOID *)&dwProcessId);
      if ( Instance < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B3,
          (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsessioncommon.cpp",
          (const char *)(unsigned int)Instance,
          ppva);
      v13 = dwProcessId;
      v14 = *dwProcessId;
      if ( !*((_BYTE *)this + 121) )
        PrintSupportSessionCommon::InitializeCentennialAppData(this);
      winrt::hstring::hstring((winrt::hstring *)&v27, (PrintSupportSessionCommon *)((char *)this + 112));
      winrt::hstring::c_str((PrintSupportSessionCommon *)((char *)this + 88));
      v15 = winrt::hstring::c_str((winrt::hstring *)&v27);
      v17 = (*(__int64 (__fastcall **)(_QWORD *, __int64, const unsigned __int16 *, const WCHAR *))(v14 + 40))(
              v13,
              v16,
              v15,
              &sourceString);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1B8,
          (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsessioncommon.cpp",
          (const char *)(unsigned int)v17,
          6176);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v27);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl'::`2'::impl) )
      {
        ProcessId = GetProcessId(*a3);
        PrintSupportSessionCommon::AddDebugSessionData(v19, *((_DWORD *)this + 68), ProcessId, 1);
      }
      if ( dwProcessId )
        winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&dwProcessId);
    }
    else
    {
      winrt::hstring::hstring((winrt::hstring *)&v24, L"Windows.PrintSupportJobUI");
      wil::CoCreateInstance<IApplicationActivationManagerPriv,wil::err_exception_policy>(&v23);
      v27 = 0;
      v6 = Microsoft::WRL::Details::MakeAndInitialize<CImmersiveWindowFactory,Windows::UI::Core::ICoreWindowFactory,>(&v27);
      if ( v6 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1A2,
          (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsessioncommon.cpp",
          (const char *)(unsigned int)v6,
          ppv);
      LODWORD(dwProcessId) = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v23 + 24LL))(
             v23,
             *((_QWORD *)this + 11),
             v27,
             v24);
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1A6,
          (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsessioncommon.cpp",
          (const char *)(unsigned int)v7,
          a2);
      v8 = OpenProcess(0x101000u, 0, (DWORD)dwProcessId);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        a3,
        v8);
      if ( !*a3 )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x1A9,
          (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsessioncommon.cpp",
          v9);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl'::`2'::impl) )
        PrintSupportSessionCommon::AddDebugSessionData(v10, *((_DWORD *)this + 68), (unsigned int)dwProcessId, 1);
      wil::com_ptr_t<IApplicationActivationManagerPriv,wil::err_exception_policy>::~com_ptr_t<IApplicationActivationManagerPriv,wil::err_exception_policy>(&v27);
      wil::com_ptr_t<IApplicationActivationManagerPriv,wil::err_exception_policy>::~com_ptr_t<IApplicationActivationManagerPriv,wil::err_exception_policy>(&v23);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v24);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1C2,
                           (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportsessioncommon.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x180033f1c  mov     [rsp+arg_8], rbx
0x180033f21  mov     [rsp+arg_10], rsi
0x180033f26  push    rdi
0x180033f27  push    r14
0x180033f29  push    r15
0x180033f2b  sub     rsp, 60h
0x180033f2f  mov     rdi, r8
0x180033f32  mov     r15, rdx
0x180033f35  mov     rbx, rcx
0x180033f38  cmp     byte ptr [rcx+79h], 0
0x180033f3c  jnz     short loc_180033F43
0x180033f3e  call    ?InitializeCentennialAppData@PrintSupportSessionCommon@@IEAAXXZ; PrintSupportSessionCommon::InitializeCentennialAppData(void)
0x180033f43  cmp     byte ptr [rbx+78h], 0
0x180033f47  jnz     loc_180034062
0x180033f4d  lea     rdx, aWindowsPrintsu_2; "Windows.PrintSupportJobUI"
0x180033f54  lea     rcx, [rsp+78h+var_20]; this
0x180033f59  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180033f5e  nop
0x180033f5f  lea     rcx, [rsp+78h+var_28]
0x180033f64  call    ??$CoCreateInstance@UIApplicationActivationManagerPriv@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIApplicationActivationManagerPriv@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<IApplicationActivationManagerPriv,wil::err_exception_policy>(_GUID const &,ulong)
0x180033f69  nop
0x180033f6a  mov     [rsp+78h+arg_18], 0
0x180033f76  lea     rcx, [rsp+78h+arg_18]
0x180033f7e  call    ??$MakeAndInitialize@VCImmersiveWindowFactory@@UICoreWindowFactory@Core@UI@Windows@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUICoreWindowFactory@Core@UI@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CImmersiveWindowFactory,Windows::UI::Core::ICoreWindowFactory,>(Windows::UI::Core::ICoreWindowFactory * *)
0x180033f83  mov     rcx, [rsp+78h]; this
0x180033f88  test    eax, eax
0x180033f8a  js      loc_180034194
0x180033f90  mov     dword ptr [rsp+78h+dwProcessId], 0
0x180033f9b  mov     rcx, [rsp+78h+var_28]
0x180033fa0  mov     rax, [rcx]
0x180033fa3  lea     rdx, [rsp+78h+dwProcessId]
0x180033fab  mov     [rsp+78h+var_48], rdx
0x180033fb0  mov     [rsp+78h+var_50], 0
0x180033fb8  mov     [rsp+78h+ppv], r15; int
0x180033fbd  mov     r9, [rsp+78h+var_20]
0x180033fc2  mov     r8, [rsp+78h+arg_18]
0x180033fca  mov     rdx, [rbx+58h]
0x180033fce  mov     rax, [rax+18h]
0x180033fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033fd7  mov     rcx, [rsp+78h]; this
0x180033fdc  test    eax, eax
0x180033fde  js      loc_1800341A8
0x180033fe4  mov     r8d, dword ptr [rsp+78h+dwProcessId]; dwProcessId
0x180033fec  xor     edx, edx; bInheritHandle
0x180033fee  mov     ecx, 101000h; dwDesiredAccess
0x180033ff3  call    cs:__imp_OpenProcess
0x180033ff9  mov     rdx, rax
0x180033ffc  mov     rcx, rdi
0x180033fff  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180034004  mov     rcx, [rsp+78h]; this
0x180034009  cmp     qword ptr [rdi], 0
0x18003400d  jz      loc_1800341BC
0x180034013  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x18003401a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x18003401f  test    al, al
0x180034021  jz      short loc_18003403A
0x180034023  mov     r9b, 1; bool
0x180034026  mov     r8d, dword ptr [rsp+78h+dwProcessId]; unsigned int
0x18003402e  mov     edx, [rbx+110h]; unsigned int
0x180034034  call    ?AddDebugSessionData@PrintSupportSessionCommon@@IEAAXII_N@Z; PrintSupportSessionCommon::AddDebugSessionData(uint,uint,bool)
0x180034039  nop
0x18003403a  lea     rcx, [rsp+78h+arg_18]
0x180034042  call    ??1?$com_ptr_t@UIApplicationActivationManagerPriv@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IApplicationActivationManagerPriv,wil::err_exception_policy>::~com_ptr_t<IApplicationActivationManagerPriv,wil::err_exception_policy>(void)
0x180034047  nop
0x180034048  lea     rcx, [rsp+78h+var_28]
0x18003404d  call    ??1?$com_ptr_t@UIApplicationActivationManagerPriv@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IApplicationActivationManagerPriv,wil::err_exception_policy>::~com_ptr_t<IApplicationActivationManagerPriv,wil::err_exception_policy>(void)
0x180034052  nop
0x180034053  lea     rcx, [rsp+78h+var_20]
0x180034058  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18003405d  jmp     loc_180034173
0x180034062  mov     [rsp+78h+dwProcessId], 0
0x18003406e  lea     rax, [rsp+78h+dwProcessId]
0x180034076  mov     [rsp+78h+ppv], rax; int
0x18003407b  lea     r9, _GUID_f158268a_d5a5_45ce_99cf_00d6c3f3fc0a; riid
0x180034082  xor     edx, edx; pUnkOuter
0x180034084  lea     r8d, [rdx+1]; dwClsContext
0x180034088  lea     rcx, _GUID_168eb462_775f_42ae_9111_d714b2306c2e; rclsid
0x18003408f  call    cs:__imp_CoCreateInstance
0x180034095  mov     rcx, [rsp+78h]; this
0x18003409a  test    eax, eax
0x18003409c  js      loc_1800341CE
0x1800340a2  mov     rsi, [rsp+78h+dwProcessId]
0x1800340aa  mov     r14, [rsi]
0x1800340ad  cmp     byte ptr [rbx+79h], 0
0x1800340b1  jnz     short loc_1800340BB
0x1800340b3  mov     rcx, rbx; this
0x1800340b6  call    ?InitializeCentennialAppData@PrintSupportSessionCommon@@IEAAXXZ; PrintSupportSessionCommon::InitializeCentennialAppData(void)
0x1800340bb  lea     rdx, [rbx+70h]; struct winrt::hstring *
0x1800340bf  lea     rcx, [rsp+78h+arg_18]; this
0x1800340c7  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x1800340cc  nop
0x1800340cd  lea     rcx, [rbx+58h]; this
0x1800340d1  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800340d6  mov     rdx, rax
0x1800340d9  lea     rcx, [rsp+78h+arg_18]; this
0x1800340e1  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1800340e6  mov     r8, rax
0x1800340e9  mov     [rsp+78h+var_40], rdi
0x1800340ee  mov     [rsp+78h+var_48], r15
0x1800340f3  mov     [rsp+78h+var_50], 0
0x1800340fb  mov     dword ptr [rsp+78h+ppv], 1820h; int
0x180034103  lea     r9, sourceString
0x18003410a  mov     rcx, rsi
0x18003410d  mov     rax, [r14+28h]
0x180034111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034116  mov     rcx, [rsp+78h]; this
0x18003411b  test    eax, eax
0x18003411d  js      loc_1800341E3
0x180034123  lea     rcx, [rsp+78h+arg_18]
0x18003412b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180034130  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1> `wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetImpl(void)'::`2'::impl
0x180034137  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)
0x18003413c  test    al, al
0x18003413e  jz      short loc_18003415B
0x180034140  mov     rcx, [rdi]; Process
0x180034143  call    cs:__imp_GetProcessId
0x180034149  mov     r9b, 1; bool
0x18003414c  mov     r8d, eax; unsigned int
0x18003414f  mov     edx, [rbx+110h]; unsigned int
0x180034155  call    ?AddDebugSessionData@PrintSupportSessionCommon@@IEAAXII_N@Z; PrintSupportSessionCommon::AddDebugSessionData(uint,uint,bool)
0x18003415a  nop
0x18003415b  cmp     [rsp+78h+dwProcessId], 0
0x180034164  jz      short loc_180034173
0x180034166  lea     rcx, [rsp+78h+dwProcessId]
0x18003416e  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x180034173  xor     eax, eax
0x180034175  jmp     short loc_18003417E
0x180034177  mov     eax, dword ptr [rsp+78h+dwProcessId]
0x18003417e  lea     r11, [rsp+78h+var_18]
0x180034183  mov     rbx, [r11+28h]
0x180034187  mov     rsi, [r11+30h]
0x18003418b  mov     rsp, r11
0x18003418e  pop     r15
0x180034190  pop     r14
0x180034192  pop     rdi
0x180034193  retn
0x180034194  mov     r9d, eax; char *
0x180034197  lea     r8, aOnecoreuapPrin_26; "onecoreuap\\printscan\\print\\workflow"...
0x18003419e  mov     edx, 1A2h; void *
0x1800341a3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800341a8  mov     r9d, eax; char *
0x1800341ab  lea     r8, aOnecoreuapPrin_26; "onecoreuap\\printscan\\print\\workflow"...
0x1800341b2  mov     edx, 1A6h; void *
0x1800341b7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800341bc  lea     r8, aOnecoreuapPrin_26; "onecoreuap\\printscan\\print\\workflow"...
0x1800341c3  mov     edx, 1A9h; void *
0x1800341c8  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800341ce  mov     r9d, eax; char *
0x1800341d1  lea     r8, aOnecoreuapPrin_26; "onecoreuap\\printscan\\print\\workflow"...
0x1800341d8  mov     edx, 1B3h; void *
0x1800341dd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800341e3  mov     r9d, eax; char *
0x1800341e6  lea     r8, aOnecoreuapPrin_26; "onecoreuap\\printscan\\print\\workflow"...
0x1800341ed  mov     edx, 1B8h; void *
0x1800341f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
