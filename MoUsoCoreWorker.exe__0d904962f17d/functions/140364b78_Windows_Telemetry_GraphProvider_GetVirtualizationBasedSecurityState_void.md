# Windows::Telemetry::GraphProvider::GetVirtualizationBasedSecurityState(void)

- ea: `0x140364b78`
- end: `0x140364f99`
- name: `?GetVirtualizationBasedSecurityState@GraphProvider@Telemetry@Windows@@CAIXZ`
- size: `1057`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140364988`

## callees

- `0x14003c578`
- `0x140040184`
- `0x140057a20`
- `0x140075bdc`
- `0x140076f3c`
- `0x14012d7d8`
- `0x140364b78`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140364bb9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140364bb9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140364d15`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140364d15`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140364bec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140364bec`

## string_xrefs

- `0x140364bb2`: `ntdll.dll`
- `0x140364f38`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140364f52`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140364f6c`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140364f86`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140364d3d`: `EnableVirtualizationBasedSecurity`
- `0x140364f0c`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\graphprovider\GraphProviderTelemetry.hpp`
- `0x140364f1e`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\graphprovider\GraphProviderTelemetry.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 Windows::Telemetry::GraphProvider::GetVirtualizationBasedSecurityState(void)
{
  HMODULE Library; // rax
  const char *v1; // r9
  HMODULE v2; // rbx
  bool v3; // r15
  FARPROC ProcAddress; // rax
  int v5; // eax
  __int64 System; // rax
  __int64 v7; // rcx
  const char *v8; // r9
  volatile signed __int32 *v9; // rsi
  unsigned int v10; // r14d
  volatile signed __int32 *v11; // rsi
  __int64 result; // rax
  _BYTE *traits_2_unsigned_short; // rax
  __int64 v14; // r8
  const char *v15; // r9
  __int64 v16; // rax
  _BYTE *v17; // rax
  const char *v18; // r9
  int v19; // r11d
  __int64 v20; // rax
  __int64 v21; // rdx
  _BYTE *v22; // rax
  __int64 v23; // r8
  const char *v24; // r9
  __int64 v25; // rax
  _BYTE *v26; // rax
  const char *v27; // r9
  int v28; // r11d
  __int64 v29; // rax
  __int64 v30; // rdx
  int v31; // [rsp+20h] [rbp-B8h]
  _DWORD v32[4]; // [rsp+30h] [rbp-A8h] BYREF
  __int128 v33; // [rsp+40h] [rbp-98h] BYREF
  __int128 v34; // [rsp+50h] [rbp-88h] BYREF
  __int128 v35; // [rsp+60h] [rbp-78h] BYREF
  HMODULE v36; // [rsp+70h] [rbp-68h]
  _BYTE v37[8]; // [rsp+78h] [rbp-60h] BYREF
  volatile signed __int32 *v38; // [rsp+80h] [rbp-58h]
  int v39; // [rsp+88h] [rbp-50h] BYREF
  __int128 v40; // [rsp+90h] [rbp-48h] BYREF
  __int128 v41; // [rsp+A0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
  try
  {
    v2 = Library;
    v36 = Library;
    v3 = Library != 0;
    if ( !Library )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x61,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\graphprovider\\GraphProviderTelemetry.hpp",
        v1);
    ProcAddress = GetProcAddress(Library, "NtQuerySystemInformation");
    v41 = 0;
    v39 = 0;
    v5 = ((__int64 (__fastcall *)(__int64, __int128 *, __int64, int *))ProcAddress)(165, &v41, 16, &v39);
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x67,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\graphprovider\\GraphProviderTelemetry.hpp",
        (const char *)(unsigned int)v5,
        v31);
    v40 = 0;
    System = SystemInterface::Providers::GetSystem(v37);
    v7 = *(_QWORD *)System + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)System + 8LL) + 4LL);
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v7 + 32LL))(v7, &v40);
    v9 = v38;
    if ( v38 )
    {
      if ( _InterlockedExchangeAdd(v38 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
      }
    }
    v10 = 1;
    if ( (v41 & 1) != 0 )
    {
      v10 = 2;
    }
    else
    {
      v32[0] = 0;
      traits_2_unsigned_short = (_BYTE *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                           L"EnableVirtualizationBasedSecurity",
                                           &unk_1404860F4,
                                           0);
      if ( traits_2_unsigned_short == (_BYTE *)&unk_1404860F4
        || (v16 = (traits_2_unsigned_short - (_BYTE *)L"EnableVirtualizationBasedSecurity") >> 1, v16 == -1) )
      {
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v15);
      }
      *(_QWORD *)&v33 = L"EnableVirtualizationBasedSecurity";
      *((_QWORD *)&v33 + 1) = v16;
      v17 = (_BYTE *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                       L"\\DeviceGuard",
                       &unk_1404861CA,
                       v14);
      if ( v17 == (_BYTE *)&unk_1404861CA || (v20 = (v17 - (_BYTE *)L"\\DeviceGuard") >> 1, v20 == -1) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v18);
      v21 = -1;
      do
        ++v21;
      while ( SystemInterface::Registry::CURRENTCONTROLSETCONTROL_REDIRECTION_ID[v21] );
      v35 = v33;
      *(_QWORD *)&v33 = L"\\DeviceGuard";
      *((_QWORD *)&v33 + 1) = v20;
      *(_QWORD *)&v34 = SystemInterface::Registry::CURRENTCONTROLSETCONTROL_REDIRECTION_ID;
      *((_QWORD *)&v34 + 1) = v21;
      if ( (unsigned int)SystemInterface::Registry::GetSystemValueOrDefault(
                           v19,
                           (unsigned int)&v34,
                           (unsigned int)&v33,
                           (unsigned int)&v35,
                           (__int64)v32) != 1 )
      {
        v32[0] = 0;
        v22 = (_BYTE *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                         L"EnableVirtualizationBasedSecurity",
                         &unk_1404860F4,
                         0);
        if ( v22 == (_BYTE *)&unk_1404860F4
          || (v25 = (v22 - (_BYTE *)L"EnableVirtualizationBasedSecurity") >> 1, v25 == -1) )
        {
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v24);
        }
        *(_QWORD *)&v34 = L"EnableVirtualizationBasedSecurity";
        *((_QWORD *)&v34 + 1) = v25;
        v26 = (_BYTE *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                         L"\\DeviceGuard",
                         &unk_1404861CA,
                         v23);
        if ( v26 == (_BYTE *)&unk_1404861CA || (v29 = (v26 - (_BYTE *)L"\\DeviceGuard") >> 1, v29 == -1) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v27);
        v30 = -1;
        do
          ++v30;
        while ( SystemInterface::Registry::POLICIES_MICROSOFT_WINDOWS_REDIRECTION_ID[v30] );
        v35 = v34;
        *(_QWORD *)&v34 = L"\\DeviceGuard";
        *((_QWORD *)&v34 + 1) = v29;
        *(_QWORD *)&v33 = SystemInterface::Registry::POLICIES_MICROSOFT_WINDOWS_REDIRECTION_ID;
        *((_QWORD *)&v33 + 1) = v30;
        if ( (unsigned int)SystemInterface::Registry::GetSystemValueOrDefault(
                             v28,
                             (unsigned int)&v33,
                             (unsigned int)&v34,
                             (unsigned int)&v35,
                             (__int64)v32) != 1 )
          v10 = 0;
      }
    }
    v11 = (volatile signed __int32 *)*((_QWORD *)&v40 + 1);
    if ( *((_QWORD *)&v40 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v40 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
        if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
    if ( v3 )
      FreeLibrary(v2);
    result = v10;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x74,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\graphprovider\\GraphProviderTelemetry.hpp",
      v8);
    return 0xFFFFFFFFLL;
  }
  return result;
}

```

## disassembly

```asm
0x140364b78  mov     rax, rsp
0x140364b7b  mov     [rax+8], rbx
0x140364b7f  mov     [rax+10h], rsi
0x140364b83  mov     [rax+18h], rdi
0x140364b87  mov     [rax+20h], r12
0x140364b8b  push    r13
0x140364b8d  push    r14
0x140364b8f  push    r15
0x140364b91  sub     rsp, 0C0h
0x140364b98  mov     rax, cs:__security_cookie
0x140364b9f  xor     rax, rsp
0x140364ba2  mov     [rsp+0D8h+var_28], rax
0x140364baa  xor     edx, edx; hFile
0x140364bac  mov     r8d, 800h; dwFlags
0x140364bb2  lea     rcx, ModuleName; "ntdll.dll"
0x140364bb9  call    cs:__imp_LoadLibraryExW
0x140364bbf  mov     rbx, rax
0x140364bc2  mov     [rsp+0D8h+var_68], rax
0x140364bc7  mov     rcx, [rsp+0D8h]; this
0x140364bcf  xor     r12d, r12d
0x140364bd2  test    rax, rax
0x140364bd5  setnz   r15b
0x140364bd9  test    rax, rax
0x140364bdc  jz      loc_140364F0C
0x140364be2  lea     rdx, aNtquerysystemi; "NtQuerySystemInformation"
0x140364be9  mov     rcx, rbx; hModule
0x140364bec  call    cs:__imp_GetProcAddress
0x140364bf2  xorps   xmm0, xmm0
0x140364bf5  movups  [rsp+0D8h+var_38], xmm0
0x140364bfd  mov     [rsp+0D8h+var_50], r12d
0x140364c05  lea     r9, [rsp+0D8h+var_50]
0x140364c0d  mov     r8d, 10h
0x140364c13  lea     rdx, [rsp+0D8h+var_38]
0x140364c1b  mov     ecx, 0A5h
0x140364c20  call    _guard_dispatch_icall
0x140364c25  mov     rcx, [rsp+0D8h]; this
0x140364c2d  test    eax, eax
0x140364c2f  js      loc_140364F1B
0x140364c35  xorps   xmm0, xmm0
0x140364c38  movups  [rsp+0D8h+var_48], xmm0
0x140364c40  lea     rcx, [rsp+0D8h+var_60]
0x140364c45  call    ?GetSystem@Providers@SystemInterface@@YA?AV?$shared_ptr@VSystem@Providers@SystemInterface@@@std@@XZ; SystemInterface::Providers::GetSystem(void)
0x140364c4a  nop
0x140364c4b  mov     rdx, [rax]
0x140364c4e  mov     rax, [rdx+8]
0x140364c52  movsxd  rcx, dword ptr [rax+4]
0x140364c56  add     rdx, 8
0x140364c5a  add     rcx, rdx
0x140364c5d  mov     rax, [rcx]
0x140364c60  lea     rdx, [rsp+0D8h+var_48]
0x140364c68  mov     rax, [rax+20h]
0x140364c6c  call    _guard_dispatch_icall
0x140364c71  nop
0x140364c72  mov     rsi, [rsp+0D8h+var_58]
0x140364c7a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140364c7e  test    rsi, rsi
0x140364c81  jz      short loc_140364CB6
0x140364c83  mov     eax, edi
0x140364c85  lock xadd [rsi+8], eax
0x140364c8a  add     eax, edi
0x140364c8c  jnz     short loc_140364CB6
0x140364c8e  mov     rax, [rsi]
0x140364c91  mov     rcx, rsi
0x140364c94  mov     rax, [rax]
0x140364c97  call    _guard_dispatch_icall
0x140364c9c  mov     eax, edi
0x140364c9e  lock xadd [rsi+0Ch], eax
0x140364ca3  add     eax, edi
0x140364ca5  jnz     short loc_140364CB6
0x140364ca7  mov     rax, [rsi]
0x140364caa  mov     rcx, rsi
0x140364cad  mov     rax, [rax+8]
0x140364cb1  call    _guard_dispatch_icall
0x140364cb6  mov     r14d, 1
0x140364cbc  test    byte ptr [rsp+0D8h+var_38], r14b
0x140364cc4  jz      short loc_140364D23
0x140364cc6  mov     r14d, 2
0x140364ccc  mov     rsi, qword ptr [rsp+0D8h+var_48+8]
0x140364cd4  test    rsi, rsi
0x140364cd7  jz      short loc_140364D0D
0x140364cd9  mov     eax, edi
0x140364cdb  lock xadd [rsi+8], eax
0x140364ce0  add     eax, edi
0x140364ce2  jnz     short loc_140364D0D
0x140364ce4  mov     rax, [rsi]
0x140364ce7  mov     rcx, rsi
0x140364cea  mov     rax, [rax]
0x140364ced  call    _guard_dispatch_icall
0x140364cf2  mov     eax, edi
0x140364cf4  lock xadd [rsi+0Ch], eax
0x140364cf9  add     eax, edi
0x140364cfb  jnz     short loc_140364D0D
0x140364cfd  mov     rax, [rsi]
0x140364d00  mov     rcx, rsi
0x140364d03  mov     rax, [rax+8]
0x140364d07  call    _guard_dispatch_icall
0x140364d0c  nop
0x140364d0d  test    r15b, r15b
0x140364d10  jz      short loc_140364D1B
0x140364d12  mov     rcx, rbx; hLibModule
0x140364d15  call    cs:__imp_FreeLibrary
0x140364d1b  mov     eax, r14d
0x140364d1e  jmp     loc_140364EDA
0x140364d23  mov     r11, qword ptr [rsp+0D8h+var_48]
0x140364d2b  mov     [rsp+0D8h+var_A8], r12d
0x140364d30  xor     r8d, r8d
0x140364d33  lea     r13, unk_1404860F4
0x140364d3a  mov     rdx, r13
0x140364d3d  lea     rsi, aEnablevirtuali; "EnableVirtualizationBasedSecurity"
0x140364d44  mov     rcx, rsi
0x140364d47  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x140364d4c  cmp     rax, r13
0x140364d4f  jz      loc_140364F7E
0x140364d55  sub     rax, rsi
0x140364d58  sar     rax, 1
0x140364d5b  cmp     rax, rdi
0x140364d5e  jz      loc_140364F7E
0x140364d64  mov     qword ptr [rsp+0D8h+var_98], rsi
0x140364d69  mov     qword ptr [rsp+0D8h+var_98+8], rax
0x140364d6e  lea     rdx, unk_1404861CA
0x140364d75  lea     r13, aDeviceguard; "\\DeviceGuard"
0x140364d7c  mov     rcx, r13
0x140364d7f  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x140364d84  lea     rcx, unk_1404861CA
0x140364d8b  cmp     rax, rcx
0x140364d8e  jz      loc_140364F30
0x140364d94  sub     rax, r13
0x140364d97  sar     rax, 1
0x140364d9a  cmp     rax, rdi
0x140364d9d  jz      loc_140364F30
0x140364da3  mov     r8, cs:?CURRENTCONTROLSETCONTROL_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::CURRENTCONTROLSETCONTROL_REDIRECTION_ID
0x140364daa  mov     rdx, rdi
0x140364dad  inc     rdx
0x140364db0  cmp     [r8+rdx*2], r12w
0x140364db5  jnz     short loc_140364DAD
0x140364db7  movups  xmm0, [rsp+0D8h+var_98]
0x140364dbc  movdqu  [rsp+0D8h+var_78], xmm0
0x140364dc2  mov     qword ptr [rsp+0D8h+var_98], r13
0x140364dc7  mov     qword ptr [rsp+0D8h+var_98+8], rax
0x140364dcc  mov     qword ptr [rsp+0D8h+var_88], r8
0x140364dd1  mov     qword ptr [rsp+0D8h+var_88+8], rdx
0x140364dd6  lea     rax, [rsp+0D8h+var_A8]
0x140364ddb  mov     qword ptr [rsp+0D8h+var_B8], rax
0x140364de0  lea     r9, [rsp+0D8h+var_78]
0x140364de5  lea     r8, [rsp+0D8h+var_98]
0x140364dea  lea     rdx, [rsp+0D8h+var_88]
0x140364def  mov     rcx, r11
0x140364df2  call    ?GetSystemValueOrDefault@Registry@SystemInterface@@QEAAIV?$basic_zstring_view@_W@wil@@00AEBI@Z; SystemInterface::Registry::GetSystemValueOrDefault(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,uint const &)
0x140364df7  cmp     eax, r14d
0x140364dfa  jz      loc_140364CCC
0x140364e00  mov     r11, qword ptr [rsp+0D8h+var_48]
0x140364e08  mov     [rsp+0D8h+var_A8], r12d
0x140364e0d  xor     r8d, r8d
0x140364e10  lea     rdx, unk_1404860F4
0x140364e17  mov     rcx, rsi
0x140364e1a  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x140364e1f  lea     rcx, unk_1404860F4
0x140364e26  cmp     rax, rcx
0x140364e29  jz      loc_140364F64
0x140364e2f  sub     rax, rsi
0x140364e32  sar     rax, 1
0x140364e35  cmp     rax, rdi
0x140364e38  jz      loc_140364F64
0x140364e3e  mov     qword ptr [rsp+0D8h+var_88], rsi
0x140364e43  mov     qword ptr [rsp+0D8h+var_88+8], rax
0x140364e48  lea     rsi, unk_1404861CA
0x140364e4f  mov     rdx, rsi
0x140364e52  mov     rcx, r13
0x140364e55  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x140364e5a  cmp     rax, rsi
0x140364e5d  jz      loc_140364F4A
0x140364e63  sub     rax, r13
0x140364e66  sar     rax, 1
0x140364e69  cmp     rax, rdi
0x140364e6c  jz      loc_140364F4A
0x140364e72  mov     r8, cs:?POLICIES_MICROSOFT_WINDOWS_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::POLICIES_MICROSOFT_WINDOWS_REDIRECTION_ID
0x140364e79  mov     rdx, rdi
0x140364e7c  inc     rdx
0x140364e7f  cmp     [r8+rdx*2], r12w
0x140364e84  jnz     short loc_140364E7C
0x140364e86  movups  xmm0, [rsp+0D8h+var_88]
0x140364e8b  movdqu  [rsp+0D8h+var_78], xmm0
0x140364e91  mov     qword ptr [rsp+0D8h+var_88], r13
0x140364e96  mov     qword ptr [rsp+0D8h+var_88+8], rax
0x140364e9b  mov     qword ptr [rsp+0D8h+var_98], r8
0x140364ea0  mov     qword ptr [rsp+0D8h+var_98+8], rdx
0x140364ea5  lea     rax, [rsp+0D8h+var_A8]
0x140364eaa  mov     qword ptr [rsp+0D8h+var_B8], rax
0x140364eaf  lea     r9, [rsp+0D8h+var_78]
0x140364eb4  lea     r8, [rsp+0D8h+var_88]
0x140364eb9  lea     rdx, [rsp+0D8h+var_98]
0x140364ebe  mov     rcx, r11
0x140364ec1  call    ?GetSystemValueOrDefault@Registry@SystemInterface@@QEAAIV?$basic_zstring_view@_W@wil@@00AEBI@Z; SystemInterface::Registry::GetSystemValueOrDefault(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,uint const &)
0x140364ec6  cmp     eax, r14d
0x140364ec9  jz      loc_140364CCC
0x140364ecf  mov     r14d, r12d
0x140364ed2  jmp     loc_140364CCC
0x140364ed7  or      eax, 0FFFFFFFFh
0x140364eda  mov     rcx, [rsp+0D8h+var_28]
0x140364ee2  xor     rcx, rsp; StackCookie
0x140364ee5  call    __security_check_cookie
0x140364eea  lea     r11, [rsp+0D8h+var_18]
0x140364ef2  mov     rbx, [r11+20h]
0x140364ef6  mov     rsi, [r11+28h]
0x140364efa  mov     rdi, [r11+30h]
0x140364efe  mov     r12, [r11+38h]
0x140364f02  mov     rsp, r11
0x140364f05  pop     r15
0x140364f07  pop     r14
0x140364f09  pop     r13
0x140364f0b  retn
0x140364f0c  lea     r8, aCW1SSrcOrchest_13; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140364f13  lea     edx, [rax+61h]; void *
0x140364f16  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140364f1b  mov     r9d, eax; char *
0x140364f1e  lea     r8, aCW1SSrcOrchest_13; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140364f25  mov     edx, 67h ; 'g'; void *
0x140364f2a  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x140364f30  mov     rcx, [rsp+0D8h]; this
0x140364f38  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140364f3f  mov     edx, 0C9h; void *
0x140364f44  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140364f4a  mov     rcx, [rsp+0D8h]; this
0x140364f52  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140364f59  mov     edx, 0C9h; void *
0x140364f5e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140364f64  mov     rcx, [rsp+0D8h]; this
0x140364f6c  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140364f73  mov     edx, 0C9h; void *
0x140364f78  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140364f7e  mov     rcx, [rsp+0D8h]; this
0x140364f86  lea     r8, aCW1SPackagesMi_1; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140364f8d  mov     edx, 0C9h; void *
0x140364f92  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
