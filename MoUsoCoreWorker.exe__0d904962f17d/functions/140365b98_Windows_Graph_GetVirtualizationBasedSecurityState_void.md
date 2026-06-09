# Windows::Graph::GetVirtualizationBasedSecurityState(void)

- ea: `0x140365b98`
- end: `0x14036602e`
- name: `?GetVirtualizationBasedSecurityState@Graph@Windows@@YAIXZ`
- size: `1174`
- prototype: `unsigned int __fastcall(Windows::Graph *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1403662f0`
- `0x14036bf50`

## callees

- `0x14003c578`
- `0x140040184`
- `0x140057a20`
- `0x140075bdc`
- `0x140076f3c`
- `0x14012d7d8`
- `0x140365b98`
- `0x14036e7c4`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140365c1b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140365c1b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140365d85`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140365d85`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140365c4b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140365c4b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140365bde`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140365bde`

## string_xrefs

- `0x140365c14`: `ntdll.dll`
- `0x140365fcd`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140365fe7`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140366001`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14036601b`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140365dad`: `EnableVirtualizationBasedSecurity`
- `0x140365f8e`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\graphprovider\GraphProvider.cpp`
- `0x140365f9f`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\graphprovider\GraphProvider.cpp`
- `0x140365fb3`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\graphprovider\GraphProvider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Graph::GetVirtualizationBasedSecurityState(Windows::Graph *this)
{
  const char *v1; // r9
  HMODULE Library; // rax
  const char *v3; // r9
  HMODULE v4; // rbx
  bool v5; // r15
  FARPROC ProcAddress; // rax
  const char *v7; // r9
  int v8; // eax
  __int64 System; // rax
  __int64 v10; // rcx
  const char *v11; // r9
  volatile signed __int32 *v12; // rsi
  unsigned int v13; // r14d
  volatile signed __int32 *v14; // rsi
  __int64 result; // rax
  _BYTE *traits_2_unsigned_short; // rax
  __int64 v17; // r8
  const char *v18; // r9
  __int64 v19; // rax
  _BYTE *v20; // rax
  const char *v21; // r9
  int v22; // r11d
  __int64 v23; // rax
  __int64 v24; // rdx
  _BYTE *v25; // rax
  __int64 v26; // r8
  const char *v27; // r9
  __int64 v28; // rax
  _BYTE *v29; // rax
  const char *v30; // r9
  int v31; // r11d
  __int64 v32; // rax
  __int64 v33; // rdx
  int v34; // [rsp+20h] [rbp-B8h]
  _DWORD v35[4]; // [rsp+30h] [rbp-A8h] BYREF
  __int128 v36; // [rsp+40h] [rbp-98h] BYREF
  __int128 v37; // [rsp+50h] [rbp-88h] BYREF
  __int128 v38; // [rsp+60h] [rbp-78h] BYREF
  HMODULE v39; // [rsp+70h] [rbp-68h]
  _BYTE v40[8]; // [rsp+78h] [rbp-60h] BYREF
  volatile signed __int32 *v41; // [rsp+80h] [rbp-58h]
  int v42; // [rsp+88h] [rbp-50h] BYREF
  __int128 v43; // [rsp+90h] [rbp-48h] BYREF
  __int128 v44; // [rsp+A0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  InitOnceExecuteOnce(
    &`wil::Wil_Staging_FailFastOnAssertEnabled'::`2'::s_initonce,
    `wil::Wil_Staging_FailFastOnAssertEnabled'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
    0,
    0);
  try
  {
    if ( `wil::Wil_Staging_FailFastOnAssertEnabled'::`2'::s_isFailFastOnAssertEnabled
      && !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_CHPE_AND_VBS_State>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Report_CHPE_AND_VBS_State>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1EFB,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\staging.h",
        v1);
    }
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    v4 = Library;
    v39 = Library;
    v5 = Library != 0;
    if ( !Library )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x93,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\graphprovider\\GraphProvider.cpp",
        v3);
    ProcAddress = GetProcAddress(Library, "NtQuerySystemInformation");
    if ( !ProcAddress )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x96,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\graphprovider\\GraphProvider.cpp",
        v7);
    v44 = 0;
    v42 = 0;
    v8 = ((__int64 (__fastcall *)(__int64, __int128 *, __int64, int *))ProcAddress)(165, &v44, 16, &v42);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x9A,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\graphprovider\\GraphProvider.cpp",
        (const char *)(unsigned int)v8,
        v34);
    v43 = 0;
    System = SystemInterface::Providers::GetSystem(v40);
    v10 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v10 + 32LL))(v10, &v43);
    v12 = v41;
    if ( v41 )
    {
      if ( _InterlockedExchangeAdd(v41 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    v13 = 1;
    if ( (v44 & 1) != 0 )
    {
      v13 = 2;
    }
    else
    {
      v35[0] = 0;
      traits_2_unsigned_short = (_BYTE *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                           L"EnableVirtualizationBasedSecurity",
                                           &unk_1404860F4,
                                           0);
      if ( traits_2_unsigned_short == (_BYTE *)&unk_1404860F4
        || (v19 = (traits_2_unsigned_short - (_BYTE *)L"EnableVirtualizationBasedSecurity") >> 1, v19 == -1) )
      {
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v18);
      }
      *(_QWORD *)&v36 = L"EnableVirtualizationBasedSecurity";
      *((_QWORD *)&v36 + 1) = v19;
      v20 = (_BYTE *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                       L"\\DeviceGuard",
                       &unk_1404861CA,
                       v17);
      if ( v20 == (_BYTE *)&unk_1404861CA || (v23 = (v20 - (_BYTE *)L"\\DeviceGuard") >> 1, v23 == -1) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v21);
      v24 = -1;
      do
        ++v24;
      while ( SystemInterface::Registry::CURRENTCONTROLSETCONTROL_REDIRECTION_ID[v24] );
      v38 = v36;
      *(_QWORD *)&v36 = L"\\DeviceGuard";
      *((_QWORD *)&v36 + 1) = v23;
      *(_QWORD *)&v37 = SystemInterface::Registry::CURRENTCONTROLSETCONTROL_REDIRECTION_ID;
      *((_QWORD *)&v37 + 1) = v24;
      if ( (unsigned int)SystemInterface::Registry::GetSystemValueOrDefault(
                           v22,
                           (unsigned int)&v37,
                           (unsigned int)&v36,
                           (unsigned int)&v38,
                           (__int64)v35) != 1 )
      {
        v35[0] = 0;
        v25 = (_BYTE *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                         L"EnableVirtualizationBasedSecurity",
                         &unk_1404860F4,
                         0);
        if ( v25 == (_BYTE *)&unk_1404860F4
          || (v28 = (v25 - (_BYTE *)L"EnableVirtualizationBasedSecurity") >> 1, v28 == -1) )
        {
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v27);
        }
        *(_QWORD *)&v37 = L"EnableVirtualizationBasedSecurity";
        *((_QWORD *)&v37 + 1) = v28;
        v29 = (_BYTE *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                         L"\\DeviceGuard",
                         &unk_1404861CA,
                         v26);
        if ( v29 == (_BYTE *)&unk_1404861CA || (v32 = (v29 - (_BYTE *)L"\\DeviceGuard") >> 1, v32 == -1) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v30);
        v33 = -1;
        do
          ++v33;
        while ( SystemInterface::Registry::POLICIES_MICROSOFT_WINDOWS_REDIRECTION_ID[v33] );
        v38 = v37;
        *(_QWORD *)&v37 = L"\\DeviceGuard";
        *((_QWORD *)&v37 + 1) = v32;
        *(_QWORD *)&v36 = SystemInterface::Registry::POLICIES_MICROSOFT_WINDOWS_REDIRECTION_ID;
        *((_QWORD *)&v36 + 1) = v33;
        if ( (unsigned int)SystemInterface::Registry::GetSystemValueOrDefault(
                             v31,
                             (unsigned int)&v36,
                             (unsigned int)&v37,
                             (unsigned int)&v38,
                             (__int64)v35) != 1 )
          v13 = 0;
      }
    }
    v14 = (volatile signed __int32 *)*((_QWORD *)&v43 + 1);
    if ( *((_QWORD *)&v43 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v43 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
    }
    if ( v5 )
      FreeLibrary(v4);
    result = v13;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xA7,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\graphprovider\\GraphProvider.cpp",
      v11);
    return 0xFFFFFFFFLL;
  }
  return result;
}

```

## disassembly

```asm
0x140365b98  mov     rax, rsp
0x140365b9b  mov     [rax+8], rbx
0x140365b9f  mov     [rax+10h], rsi
0x140365ba3  mov     [rax+18h], rdi
0x140365ba7  mov     [rax+20h], r12
0x140365bab  push    r13
0x140365bad  push    r14
0x140365baf  push    r15
0x140365bb1  sub     rsp, 0C0h
0x140365bb8  mov     rax, cs:__security_cookie
0x140365bbf  xor     rax, rsp
0x140365bc2  mov     [rsp+0D8h+var_28], rax
0x140365bca  xor     r9d, r9d; Context
0x140365bcd  xor     r8d, r8d; Parameter
0x140365bd0  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x140365bd7  lea     rcx, ?s_initonce@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@4T_RTL_RUN_ONCE@@A; InitOnce
0x140365bde  call    cs:__imp_InitOnceExecuteOnce
0x140365be4  xor     r12d, r12d
0x140365be7  cmp     cs:?s_isFailFastOnAssertEnabled@?1??Wil_Staging_FailFastOnAssertEnabled@wil@@YA_NXZ@4_NA, r12b; bool `wil::Wil_Staging_FailFastOnAssertEnabled(void)'::`2'::s_isFailFastOnAssertEnabled
0x140365bee  jz      short loc_140365C0C
0x140365bf0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_Report_CHPE_AND_VBS_State@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Report_CHPE_AND_VBS_State@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_CHPE_AND_VBS_State> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_Report_CHPE_AND_VBS_State>::GetImpl(void)'::`2'::impl
0x140365bf7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_Report_CHPE_AND_VBS_State@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_Report_CHPE_AND_VBS_State>::__private_IsEnabled(wil::ReportingKind)
0x140365bfc  mov     rcx, [rsp+0D8h]; this
0x140365c04  test    al, al
0x140365c06  jz      loc_140365F7C
0x140365c0c  xor     edx, edx; hFile
0x140365c0e  mov     r8d, 800h; dwFlags
0x140365c14  lea     rcx, ModuleName; "ntdll.dll"
0x140365c1b  call    cs:__imp_LoadLibraryExW
0x140365c21  mov     rbx, rax
0x140365c24  mov     [rsp+0D8h+var_68], rax
0x140365c29  mov     rcx, [rsp+0D8h]; this
0x140365c31  test    rax, rax
0x140365c34  setnz   r15b
0x140365c38  test    rax, rax
0x140365c3b  jz      loc_140365F8E
0x140365c41  lea     rdx, aNtquerysystemi; "NtQuerySystemInformation"
0x140365c48  mov     rcx, rbx; hModule
0x140365c4b  call    cs:__imp_GetProcAddress
0x140365c51  mov     rcx, [rsp+0D8h]; this
0x140365c59  test    rax, rax
0x140365c5c  jz      loc_140365F9F
0x140365c62  xorps   xmm0, xmm0
0x140365c65  movups  [rsp+0D8h+var_38], xmm0
0x140365c6d  mov     [rsp+0D8h+var_50], r12d
0x140365c75  lea     r9, [rsp+0D8h+var_50]
0x140365c7d  mov     r8d, 10h
0x140365c83  lea     rdx, [rsp+0D8h+var_38]
0x140365c8b  mov     ecx, 0A5h
0x140365c90  call    _guard_dispatch_icall
0x140365c95  mov     rcx, [rsp+0D8h]; this
0x140365c9d  test    eax, eax
0x140365c9f  js      loc_140365FB0
0x140365ca5  xorps   xmm0, xmm0
0x140365ca8  movups  [rsp+0D8h+var_48], xmm0
0x140365cb0  lea     rcx, [rsp+0D8h+var_60]
0x140365cb5  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x140365cba  nop
0x140365cbb  mov     rdx, [rax]
0x140365cbe  mov     rax, [rdx+8]
0x140365cc2  movsxd  rcx, dword ptr [rax+4]
0x140365cc6  add     rdx, 8
0x140365cca  add     rcx, rdx
0x140365ccd  mov     rax, [rcx]
0x140365cd0  lea     rdx, [rsp+0D8h+var_48]
0x140365cd8  mov     rax, [rax+20h]
0x140365cdc  call    _guard_dispatch_icall
0x140365ce1  nop
0x140365ce2  mov     rsi, [rsp+0D8h+var_58]
0x140365cea  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140365cee  test    rsi, rsi
0x140365cf1  jz      short loc_140365D26
0x140365cf3  mov     eax, edi
0x140365cf5  lock xadd [rsi+8], eax
0x140365cfa  add     eax, edi
0x140365cfc  jnz     short loc_140365D26
0x140365cfe  mov     rax, [rsi]
0x140365d01  mov     rcx, rsi
0x140365d04  mov     rax, [rax]
0x140365d07  call    _guard_dispatch_icall
0x140365d0c  mov     eax, edi
0x140365d0e  lock xadd [rsi+0Ch], eax
0x140365d13  add     eax, edi
0x140365d15  jnz     short loc_140365D26
0x140365d17  mov     rax, [rsi]
0x140365d1a  mov     rcx, rsi
0x140365d1d  mov     rax, [rax+8]
0x140365d21  call    _guard_dispatch_icall
0x140365d26  mov     r14d, 1
0x140365d2c  test    byte ptr [rsp+0D8h+var_38], r14b
0x140365d34  jz      short loc_140365D93
0x140365d36  mov     r14d, 2
0x140365d3c  mov     rsi, qword ptr [rsp+0D8h+var_48+8]
0x140365d44  test    rsi, rsi
0x140365d47  jz      short loc_140365D7D
0x140365d49  mov     eax, edi
0x140365d4b  lock xadd [rsi+8], eax
0x140365d50  add     eax, edi
0x140365d52  jnz     short loc_140365D7D
0x140365d54  mov     rax, [rsi]
0x140365d57  mov     rcx, rsi
0x140365d5a  mov     rax, [rax]
0x140365d5d  call    _guard_dispatch_icall
0x140365d62  mov     eax, edi
0x140365d64  lock xadd [rsi+0Ch], eax
0x140365d69  add     eax, edi
0x140365d6b  jnz     short loc_140365D7D
0x140365d6d  mov     rax, [rsi]
0x140365d70  mov     rcx, rsi
0x140365d73  mov     rax, [rax+8]
0x140365d77  call    _guard_dispatch_icall
0x140365d7c  nop
0x140365d7d  test    r15b, r15b
0x140365d80  jz      short loc_140365D8B
0x140365d82  mov     rcx, rbx; hLibModule
0x140365d85  call    cs:__imp_FreeLibrary
0x140365d8b  mov     eax, r14d
0x140365d8e  jmp     loc_140365F4A
0x140365d93  mov     r11, qword ptr [rsp+0D8h+var_48]
0x140365d9b  mov     [rsp+0D8h+var_A8], r12d
0x140365da0  xor     r8d, r8d
0x140365da3  lea     r13, unk_1404860F4
0x140365daa  mov     rdx, r13
0x140365dad  lea     rsi, aEnablevirtuali; "EnableVirtualizationBasedSecurity"
0x140365db4  mov     rcx, rsi
0x140365db7  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x140365dbc  cmp     rax, r13
0x140365dbf  jz      loc_140366013
0x140365dc5  sub     rax, rsi
0x140365dc8  sar     rax, 1
0x140365dcb  cmp     rax, rdi
0x140365dce  jz      loc_140366013
0x140365dd4  mov     qword ptr [rsp+0D8h+var_98], rsi
0x140365dd9  mov     qword ptr [rsp+0D8h+var_98+8], rax
0x140365dde  lea     rdx, unk_1404861CA
0x140365de5  lea     r13, aDeviceguard; "\\DeviceGuard"
0x140365dec  mov     rcx, r13
0x140365def  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x140365df4  lea     rcx, unk_1404861CA
0x140365dfb  cmp     rax, rcx
0x140365dfe  jz      loc_140365FC5
0x140365e04  sub     rax, r13
0x140365e07  sar     rax, 1
0x140365e0a  cmp     rax, rdi
0x140365e0d  jz      loc_140365FC5
0x140365e13  mov     r8, cs:?CURRENTCONTROLSETCONTROL_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::CURRENTCONTROLSETCONTROL_REDIRECTION_ID
0x140365e1a  mov     rdx, rdi
0x140365e1d  inc     rdx
0x140365e20  cmp     [r8+rdx*2], r12w
0x140365e25  jnz     short loc_140365E1D
0x140365e27  movups  xmm0, [rsp+0D8h+var_98]
0x140365e2c  movdqu  [rsp+0D8h+var_78], xmm0
0x140365e32  mov     qword ptr [rsp+0D8h+var_98], r13
0x140365e37  mov     qword ptr [rsp+0D8h+var_98+8], rax
0x140365e3c  mov     qword ptr [rsp+0D8h+var_88], r8
0x140365e41  mov     qword ptr [rsp+0D8h+var_88+8], rdx
0x140365e46  lea     rax, [rsp+0D8h+var_A8]
0x140365e4b  mov     qword ptr [rsp+0D8h+var_B8], rax
0x140365e50  lea     r9, [rsp+0D8h+var_78]
0x140365e55  lea     r8, [rsp+0D8h+var_98]
0x140365e5a  lea     rdx, [rsp+0D8h+var_88]
0x140365e5f  mov     rcx, r11
0x140365e62  call    ?GetSystemValueOrDefault@Registry@SystemInterface@@QEAAIV?$basic_zstring_view@_W@wil@@00AEBI@Z; SystemInterface::Registry::GetSystemValueOrDefault(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,uint const &)
0x140365e67  cmp     eax, r14d
0x140365e6a  jz      loc_140365D3C
0x140365e70  mov     r11, qword ptr [rsp+0D8h+var_48]
0x140365e78  mov     [rsp+0D8h+var_A8], r12d
0x140365e7d  xor     r8d, r8d
0x140365e80  lea     rdx, unk_1404860F4
0x140365e87  mov     rcx, rsi
0x140365e8a  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x140365e8f  lea     rcx, unk_1404860F4
0x140365e96  cmp     rax, rcx
0x140365e99  jz      loc_140365FF9
0x140365e9f  sub     rax, rsi
0x140365ea2  sar     rax, 1
0x140365ea5  cmp     rax, rdi
0x140365ea8  jz      loc_140365FF9
0x140365eae  mov     qword ptr [rsp+0D8h+var_88], rsi
0x140365eb3  mov     qword ptr [rsp+0D8h+var_88+8], rax
0x140365eb8  lea     rsi, unk_1404861CA
0x140365ebf  mov     rdx, rsi
0x140365ec2  mov     rcx, r13
0x140365ec5  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x140365eca  cmp     rax, rsi
0x140365ecd  jz      loc_140365FDF
0x140365ed3  sub     rax, r13
0x140365ed6  sar     rax, 1
0x140365ed9  cmp     rax, rdi
0x140365edc  jz      loc_140365FDF
0x140365ee2  mov     r8, cs:?POLICIES_MICROSOFT_WINDOWS_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::POLICIES_MICROSOFT_WINDOWS_REDIRECTION_ID
0x140365ee9  mov     rdx, rdi
0x140365eec  inc     rdx
0x140365eef  cmp     [r8+rdx*2], r12w
0x140365ef4  jnz     short loc_140365EEC
0x140365ef6  movups  xmm0, [rsp+0D8h+var_88]
0x140365efb  movdqu  [rsp+0D8h+var_78], xmm0
0x140365f01  mov     qword ptr [rsp+0D8h+var_88], r13
0x140365f06  mov     qword ptr [rsp+0D8h+var_88+8], rax
0x140365f0b  mov     qword ptr [rsp+0D8h+var_98], r8
0x140365f10  mov     qword ptr [rsp+0D8h+var_98+8], rdx
0x140365f15  lea     rax, [rsp+0D8h+var_A8]
0x140365f1a  mov     qword ptr [rsp+0D8h+var_B8], rax
0x140365f1f  lea     r9, [rsp+0D8h+var_78]
0x140365f24  lea     r8, [rsp+0D8h+var_88]
0x140365f29  lea     rdx, [rsp+0D8h+var_98]
0x140365f2e  mov     rcx, r11
0x140365f31  call    ?GetSystemValueOrDefault@Registry@SystemInterface@@QEAAIV?$basic_zstring_view@_W@wil@@00AEBI@Z; SystemInterface::Registry::GetSystemValueOrDefault(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,uint const &)
0x140365f36  cmp     eax, r14d
0x140365f39  jz      loc_140365D3C
0x140365f3f  mov     r14d, r12d
0x140365f42  jmp     loc_140365D3C
0x140365f47  or      eax, 0FFFFFFFFh
0x140365f4a  mov     rcx, [rsp+0D8h+var_28]
0x140365f52  xor     rcx, rsp; StackCookie
0x140365f55  call    __security_check_cookie
0x140365f5a  lea     r11, [rsp+0D8h+var_18]
0x140365f62  mov     rbx, [r11+20h]
0x140365f66  mov     rsi, [r11+28h]
0x140365f6a  mov     rdi, [r11+30h]
0x140365f6e  mov     r12, [r11+38h]
0x140365f72  mov     rsp, r11
0x140365f75  pop     r15
0x140365f77  pop     r14
0x140365f79  pop     r13
0x140365f7b  retn
0x140365f7c  lea     r8, aCW1SPackagesMi_6; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140365f83  mov     edx, 1EFBh; void *
0x140365f88  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140365f8e  lea     r8, aCW1SSrcOrchest_39; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140365f95  mov     edx, 93h; void *
0x140365f9a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140365f9f  lea     r8, aCW1SSrcOrchest_39; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140365fa6  mov     edx, 96h; void *
0x140365fab  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140365fb0  mov     r9d, eax; char *
0x140365fb3  lea     r8, aCW1SSrcOrchest_39; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140365fba  mov     edx, 9Ah; void *
0x140365fbf  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x140365fc5  mov     rcx, [rsp+0D8h]; this
0x140365fcd  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140365fd4  mov     edx, 0C9h; void *
0x140365fd9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140365fdf  mov     rcx, [rsp+0D8h]; this
0x140365fe7  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140365fee  mov     edx, 0C9h; void *
0x140365ff3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140365ff9  mov     rcx, [rsp+0D8h]; this
0x140366001  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140366008  mov     edx, 0C9h; void *
0x14036600d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140366013  mov     rcx, [rsp+0D8h]; this
0x14036601b  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140366022  mov     edx, 0C9h; void *
0x140366027  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
