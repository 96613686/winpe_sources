# DisableAdminAccountTask::Execute(void)

- ea: `0x18002d550`
- end: `0x18002dbf9`
- name: `?Execute@DisableAdminAccountTask@@MEAAXXZ`
- size: `1705`
- prototype: `void __fastcall(DisableAdminAccountTask *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003390`
- `0x1800106c4`
- `0x18001094c`
- `0x180011a10`
- `0x180013988`
- `0x180014930`
- `0x180014d04`
- `0x18001e58c`
- `0x18001f8d4`
- `0x180022484`
- `0x180022aa8`
- `0x18002d518`
- `0x18002d550`
- `0x18002dc10`
- `0x18002dc5c`
- `0x18004729c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002d62c`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002d62c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d6e5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d871`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002da0b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d6e5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d871`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002da0b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002d7a3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002d7f0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002d90f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002d7a3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002d7f0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002d90f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002d72a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002d8b6`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002d72a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002d8b6`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18002da38`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18002da38`
- `netutils!NetApiBufferFree` at `0x18002dad1`
- `netutils!NetApiBufferFree` at `0x18002dad1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002d641`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18002d641`
- `samcli!NetUserGetInfo` at `0x18002da6e`
- `samcli!NetUserGetInfo` at `0x18002da6e`
- `samcli!NetUserSetInfo` at `0x18002d988`
- `samcli!NetUserSetInfo` at `0x18002dac2`
- `samcli!NetUserSetInfo` at `0x18002d988`
- `samcli!NetUserSetInfo` at `0x18002dac2`

## string_xrefs

- `0x18002d905`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\OobeWrite`
- `0x18002d7df`: `FirstRunCompletedTime`
- `0x18002d8a8`: `FirstRunCompletedTime`
- `0x18002d5ad`: `DelayDisableAdminAccess`
- `0x18002d5ed`: `DelayDisableAdminAccess`
- `0x18002d99e`: `DelayDisableAdminAccess`
- `0x18002d6db`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\ServiceReadWrite`
- `0x18002d799`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\ServiceReadWrite`
- `0x18002d7e6`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\ServiceReadWrite`
- `0x18002d867`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\ServiceReadWrite`
- `0x18002da01`: `Software\Microsoft\Windows\CurrentVersion\RetailDemo\ServiceReadWrite`
- `0x18002db34`: `shellcommon\internal\shell\inc\timehelpers.h`
- `0x18002d74b`: `delayDisableAdminAccess value missing from registry, assume default`
- `0x18002d5cb`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\disableadminaccount.cpp`
- `0x18002d800`: `firstRunCompleteTime missing from registry`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall DisableAdminAccountTask::Execute(DisableAdminAccountTask *this)
{
  unsigned int v1; // ebx
  HKEY v2; // rcx
  unsigned int v3; // eax
  const char *v4; // r9
  struct _FILETIME v5; // rbx
  unsigned int Key; // eax
  unsigned int v7; // eax
  unsigned int ValueW; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  LSTATUS v11; // eax
  unsigned __int64 v12; // r9
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  void *v16; // rcx
  int v17; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsd; // [rsp+20h] [rbp-E0h]
  int dwOptionse; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsf; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsg; // [rsp+20h] [rbp-E0h]
  int dwOptionsh; // [rsp+20h] [rbp-E0h]
  const char *samDesired; // [rsp+28h] [rbp-D8h]
  const char *samDesireda; // [rsp+28h] [rbp-D8h]
  struct _FILETIME FileTime; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v30; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v31; // [rsp+5Ch] [rbp-A4h] BYREF
  struct _FILETIME Data; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v34; // [rsp+6Ch] [rbp-94h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-90h] BYREF
  char v36; // [rsp+80h] [rbp-80h]
  _QWORD v37[42]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR pvData[264]; // [rsp+1E0h] [rbp+E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+438h] [rbp+338h]

  wil::ActivityBase<RetailDemoLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<RetailDemoLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v37);
  v37[0] = &RetailDemoTelemetry::DisableAdminAccount::`vftable';
  RetailDemoTelemetry::DisableAdminAccount::StartActivity((RetailDemoTelemetry::DisableAdminAccount *)v37);
  v1 = 48;
  v30 = 48;
  if ( (int)SHRegGetDWORD(
              v2,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\RetailInfo",
              L"DelayDisableAdminAccess",
              &v30) >= 0 )
  {
LABEL_4:
    v1 = v30;
    goto LABEL_5;
  }
  if ( (unsigned int)QueryRegValue() )
  {
    v30 = -1;
    v3 = SHRegSetDWORD(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\RetailInfo",
           L"DelayDisableAdminAccess",
           0xFFFFFFFF);
    if ( v3 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x2C,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\disableadminaccount.cpp",
        (const char *)v3,
        dwOptions);
    goto LABEL_4;
  }
  wil::details::in1diag3::Log_HrMsg(
    retaddr,
    (void *)0x31,
    (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\disableadminaccount.cpp",
    (const char *)0x8000FFFFLL,
    (int)"delayDisableAdminAccess value missing from registry, assume default",
    samDesired);
  v30 = 48;
LABEL_5:
  if ( v1 == -1 )
    goto LABEL_34;
  SystemTime = 0;
  GetLocalTime(&SystemTime);
  FileTime = 0;
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x24,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\timehelpers.h",
      v4);
  v5 = FileTime;
  Data = 0;
  pcbData = 8;
  v34 = 0;
  SHRegGetDWORD(
    (HKEY)retaddr,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\RetailInfo",
    L"RetailAdminAccountEnabled",
    &v34);
  if ( v34 )
  {
    Data = v5;
    FileTime = 0;
    *(_QWORD *)&SystemTime.wYear = &FileTime;
    *(_QWORD *)&SystemTime.wHour = 0;
    v36 = 1;
    Key = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\ServiceReadWrite",
            0,
            0,
            0,
            0x20006u,
            0,
            (PHKEY)&SystemTime.wHour,
            0);
    if ( Key )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x44,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\disableadminaccount.cpp",
        (const char *)Key,
        dwOptionsa);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&SystemTime);
    v7 = RegSetKeyValueW(*(HKEY *)&FileTime, 0, L"RetailAdminAccountEnabledTime", 0xBu, &Data, 8u);
    if ( v7 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x45,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\disableadminaccount.cpp",
        (const char *)v7,
        dwOptionsb);
  }
  else
  {
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\ServiceReadWrite",
            L"RetailAdminAccountEnabledTime",
            0x20010040u,
            0,
            &Data,
            &pcbData)
      && *(_QWORD *)&Data )
    {
      goto LABEL_18;
    }
    pcbData = 8;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\ServiceReadWrite",
               L"FirstRunCompletedTime",
               0x20010040u,
               0,
               &Data,
               &pcbData);
    wil::details::in1diag3::Log_IfWin32ErrorMsg(
      retaddr,
      (void *)0x50,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\disableadminaccount.cpp",
      (const char *)ValueW,
      (unsigned int)"firstRunCompleteTime missing from registry",
      samDesireda);
    if ( Data )
      goto LABEL_18;
    Data = v5;
    FileTime = 0;
    *(_QWORD *)&SystemTime.wYear = &FileTime;
    *(_QWORD *)&SystemTime.wHour = 0;
    v36 = 1;
    v9 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\ServiceReadWrite",
           0,
           0,
           0,
           0x20006u,
           0,
           (PHKEY)&SystemTime.wHour,
           0);
    if ( v9 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x56,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\disableadminaccount.cpp",
        (const char *)v9,
        dwOptionsc);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&SystemTime);
    v10 = RegSetKeyValueW(*(HKEY *)&FileTime, 0, L"FirstRunCompletedTime", 0xBu, &Data, 8u);
    if ( v10 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x57,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\disableadminaccount.cpp",
        (const char *)v10,
        dwOptionsd);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&FileTime);
LABEL_18:
  v31 = 514;
  v11 = RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\OobeWrite",
          L"AdminAccount",
          2u,
          0,
          pvData,
          &v31);
  v12 = (unsigned int)v11;
  if ( v11 )
  {
    pvData[0] = 0;
    if ( v11 > 0 )
      v12 = (unsigned __int16)v11 | 0x80070000;
  }
  if ( (v12 & 0x80000000) != 0LL )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\disableadminaccount.cpp",
      (const char *)v12,
      dwOptionse);
  if ( *(_QWORD *)&Data + 36000000000LL * (unsigned __int64)v30 > *(_QWORD *)&v5 )
  {
    FileTime = 0;
    if ( NetUserGetInfo(0, pvData, 0x14u, (LPBYTE *)&FileTime) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x76,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\disableadminaccount.cpp",
        (const char *)0x8000FFFFLL,
        dwOptionse);
    *(_QWORD *)&SystemTime.wYear = &FileTime;
    LOBYTE(SystemTime.wHour) = 1;
    v16 = (void *)FileTime;
    v17 = *(_DWORD *)(*(_QWORD *)&FileTime + 24LL);
    if ( (v17 & 2) != 0 )
    {
      v31 = v17 & 0xFFFEFFFD | 0x10000;
      if ( NetUserSetInfo(0, pvData, 0x3F0u, (LPBYTE)&v31, 0) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x80,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\disableadminaccount.cpp",
          (const char *)0x8000FFFFLL,
          dwOptionsh);
      v16 = (void *)FileTime;
    }
    NetApiBufferFree(v16);
  }
  else
  {
    v31 = 3;
    if ( NetUserSetInfo(0, pvData, 0x3F0u, (LPBYTE)&v31, 0) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x64,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\disableadminaccount.cpp",
        (const char *)0x8000FFFFLL,
        dwOptionsf);
    v30 = -1;
    v13 = SHRegSetDWORD(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\RetailInfo",
            L"DelayDisableAdminAccess",
            0xFFFFFFFF);
    if ( v13 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x68,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\disableadminaccount.cpp",
        (const char *)v13,
        dwOptionsf);
    FileTime = 0;
    *(_QWORD *)&SystemTime.wYear = &FileTime;
    *(_QWORD *)&SystemTime.wHour = 0;
    v36 = 1;
    v14 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\RetailDemo\\ServiceReadWrite",
            0,
            0,
            0,
            0x20006u,
            0,
            (PHKEY)&SystemTime.wHour,
            0);
    if ( v14 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x6B,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\disableadminaccount.cpp",
        (const char *)v14,
        dwOptionsg);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&SystemTime);
    v15 = RegDeleteKeyValueW(*(HKEY *)&FileTime, 0, L"RetailAdminAccountEnabledTime");
    if ( v15 != 2 && v15 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x6F,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\disableadminaccount.cpp",
        (const char *)v15,
        dwOptionsg);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&FileTime);
  }
LABEL_34:
  wil::ActivityBase<RetailDemoLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v37, 0);
  RetailDemoTelemetry::DisableAdminAccount::~DisableAdminAccount((RetailDemoTelemetry::DisableAdminAccount *)v37);
}

```

## disassembly

```asm
0x18002d550  push    rbp
0x18002d552  push    rbx
0x18002d553  push    rsi
0x18002d554  push    r13
0x18002d556  push    r14
0x18002d558  push    r15
0x18002d55a  lea     rbp, [rsp-308h]
0x18002d562  sub     rsp, 408h
0x18002d569  mov     rax, cs:__security_cookie
0x18002d570  xor     rax, rsp
0x18002d573  mov     [rbp+330h+var_40], rax
0x18002d57a  lea     rdx, aDisableadminac_0; "DisableAdminAccount"
0x18002d581  lea     rcx, [rbp+330h+var_3A0]; struct wil::details::IFailureCallback *
0x18002d585  call    ??0?$ActivityBase@VRetailDemoLogging@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<RetailDemoLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<RetailDemoLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002d58a  lea     rax, ??_7DisableAdminAccount@RetailDemoTelemetry@@6B@; const RetailDemoTelemetry::DisableAdminAccount::`vftable'
0x18002d591  mov     [rbp+330h+var_3A0], rax
0x18002d595  lea     rcx, [rbp+330h+var_3A0]; this
0x18002d599  call    ?StartActivity@DisableAdminAccount@RetailDemoTelemetry@@QEAAXXZ; RetailDemoTelemetry::DisableAdminAccount::StartActivity(void)
0x18002d59e  nop
0x18002d59f  mov     ebx, 30h ; '0'
0x18002d5a4  mov     [rsp+430h+var_3D8], ebx
0x18002d5a8  lea     r9, [rsp+430h+var_3D8]; unsigned int *
0x18002d5ad  lea     r8, ?c_retailDemoValueDelayDisableAdminAccess@@3QBGB; "DelayDisableAdminAccess"
0x18002d5b4  lea     rdx, ?c_retailDemoKeyRetailInfo@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002d5bb  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002d5c0  or      r13d, 0FFFFFFFFh
0x18002d5c4  mov     r15, 0FFFFFFFF80000002h
0x18002d5cb  lea     r14, aPcshellShellRe_13; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002d5d2  xor     esi, esi
0x18002d5d4  test    eax, eax
0x18002d5d6  jns     short loc_18002D612
0x18002d5d8  call    QueryRegValue
0x18002d5dd  test    eax, eax
0x18002d5df  jz      loc_18002D744
0x18002d5e5  mov     [rsp+430h+var_3D8], r13d
0x18002d5ea  mov     r9d, r13d; unsigned int
0x18002d5ed  lea     r8, ?c_retailDemoValueDelayDisableAdminAccess@@3QBGB; "DelayDisableAdminAccess"
0x18002d5f4  lea     rdx, ?c_retailDemoKeyRetailInfo@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002d5fb  mov     rcx, r15; HKEY
0x18002d5fe  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18002d603  mov     rcx, [rbp+338h]; this
0x18002d60a  test    eax, eax
0x18002d60c  jnz     loc_18002DB23
0x18002d612  mov     ebx, [rsp+430h+var_3D8]
0x18002d616  cmp     ebx, r13d
0x18002d619  jz      loc_18002DAD7
0x18002d61f  xorps   xmm0, xmm0
0x18002d622  movups  xmmword ptr [rsp+430h+SystemTime.wYear], xmm0
0x18002d627  lea     rcx, [rsp+430h+SystemTime]; lpSystemTime
0x18002d62c  call    cs:__imp_GetLocalTime
0x18002d632  mov     qword ptr [rsp+430h+FileTime.dwLowDateTime], rsi
0x18002d637  lea     rdx, [rsp+430h+FileTime]; lpFileTime
0x18002d63c  lea     rcx, [rsp+430h+SystemTime]; lpSystemTime
0x18002d641  call    cs:__imp_SystemTimeToFileTime
0x18002d647  mov     rcx, [rbp+338h]; this
0x18002d64e  test    eax, eax
0x18002d650  jz      loc_18002DB34
0x18002d656  mov     ebx, [rsp+430h+FileTime.dwHighDateTime]
0x18002d65a  shl     rbx, 20h
0x18002d65e  mov     eax, [rsp+430h+FileTime.dwLowDateTime]
0x18002d662  or      rbx, rax
0x18002d665  mov     [rsp+430h+Data], rsi
0x18002d66a  mov     [rsp+430h+pcbData], 8
0x18002d672  mov     [rsp+430h+var_3C4], esi
0x18002d676  lea     r9, [rsp+430h+var_3C4]; unsigned int *
0x18002d67b  lea     r8, ?c_retailDemoValueRetailAdminEnabled@@3QBGB; "RetailAdminAccountEnabled"
0x18002d682  lea     rdx, ?c_retailDemoKeyRetailInfo@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002d689  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18002d68e  cmp     [rsp+430h+var_3C4], esi
0x18002d692  jz      loc_18002D773
0x18002d698  mov     [rsp+430h+Data], rbx
0x18002d69d  mov     qword ptr [rsp+430h+FileTime.dwLowDateTime], rsi
0x18002d6a2  lea     rax, [rsp+430h+FileTime]
0x18002d6a7  mov     qword ptr [rsp+430h+SystemTime.wYear], rax
0x18002d6ac  mov     qword ptr [rsp+430h+SystemTime.wHour], rsi
0x18002d6b1  mov     [rbp+330h+var_3B0], 1
0x18002d6b5  mov     [rsp+430h+lpdwDisposition], rsi; lpdwDisposition
0x18002d6ba  lea     rax, [rsp+430h+SystemTime.wHour]
0x18002d6bf  mov     [rsp+430h+phkResult], rax; phkResult
0x18002d6c4  mov     [rsp+430h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18002d6c9  mov     [rsp+430h+samDesired], 20006h; samDesired
0x18002d6d1  mov     [rsp+430h+dwOptions], esi; unsigned int
0x18002d6d5  xor     r9d, r9d; lpClass
0x18002d6d8  xor     r8d, r8d; Reserved
0x18002d6db  lea     rdx, ?c_retailDemoKeyServiceReadWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002d6e2  mov     rcx, r15; hKey
0x18002d6e5  call    cs:__imp_RegCreateKeyExW
0x18002d6eb  mov     rcx, [rbp+338h]; this
0x18002d6f2  test    eax, eax
0x18002d6f4  jnz     loc_18002DB46
0x18002d6fa  lea     rcx, [rsp+430h+SystemTime]
0x18002d6ff  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18002d704  mov     [rsp+430h+samDesired], 8; cbData
0x18002d70c  lea     rax, [rsp+430h+Data]
0x18002d711  mov     qword ptr [rsp+430h+dwOptions], rax; unsigned int
0x18002d716  mov     r9d, 0Bh; dwType
0x18002d71c  lea     r8, ?c_retailDemoValueRetailAdminEnabledTime@@3QBGB; "RetailAdminAccountEnabledTime"
0x18002d723  xor     edx, edx; lpSubKey
0x18002d725  mov     rcx, qword ptr [rsp+430h+FileTime.dwLowDateTime]; hKey
0x18002d72a  call    cs:__imp_RegSetKeyValueW
0x18002d730  mov     rcx, [rbp+338h]; this
0x18002d737  test    eax, eax
0x18002d739  jnz     loc_18002DB57
0x18002d73f  jmp     loc_18002D8CB
0x18002d744  mov     rcx, [rbp+338h]; this
0x18002d74b  lea     rax, aDelaydisablead; "delayDisableAdminAccess value missing f"...
0x18002d752  mov     qword ptr [rsp+430h+dwOptions], rax; int
0x18002d757  mov     r9d, 8000FFFFh; char *
0x18002d75d  mov     r8, r14; unsigned int
0x18002d760  mov     edx, 31h ; '1'; void *
0x18002d765  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002d76a  mov     [rsp+430h+var_3D8], ebx
0x18002d76e  jmp     loc_18002D616
0x18002d773  lea     rax, [rsp+430h+pcbData]
0x18002d778  mov     [rsp+430h+lpSecurityAttributes], rax; pcbData
0x18002d77d  lea     rax, [rsp+430h+Data]
0x18002d782  mov     qword ptr [rsp+430h+samDesired], rax; pvData
0x18002d787  mov     qword ptr [rsp+430h+dwOptions], rsi; pdwType
0x18002d78c  mov     r9d, 20010040h; dwFlags
0x18002d792  lea     r8, ?c_retailDemoValueRetailAdminEnabledTime@@3QBGB; "RetailAdminAccountEnabledTime"
0x18002d799  lea     rdx, ?c_retailDemoKeyServiceReadWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002d7a0  mov     rcx, r15; hkey
0x18002d7a3  call    cs:__imp_RegGetValueW
0x18002d7a9  test    eax, eax
0x18002d7ab  jnz     short loc_18002D7B8
0x18002d7ad  cmp     [rsp+430h+Data], rsi
0x18002d7b2  jnz     loc_18002D8D5
0x18002d7b8  mov     [rsp+430h+pcbData], 8
0x18002d7c0  lea     rax, [rsp+430h+pcbData]
0x18002d7c5  mov     [rsp+430h+lpSecurityAttributes], rax; pcbData
0x18002d7ca  lea     rax, [rsp+430h+Data]
0x18002d7cf  mov     qword ptr [rsp+430h+samDesired], rax; char *
0x18002d7d4  mov     qword ptr [rsp+430h+dwOptions], rsi; pdwType
0x18002d7d9  mov     r9d, 20010040h; dwFlags
0x18002d7df  lea     r8, ?c_retailDemoValueFirstRunCompletedTime@@3QBGB; "FirstRunCompletedTime"
0x18002d7e6  lea     rdx, ?c_retailDemoKeyServiceReadWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002d7ed  mov     rcx, r15; hkey
0x18002d7f0  call    cs:__imp_RegGetValueW
0x18002d7f6  mov     r9d, eax; char *
0x18002d7f9  mov     rcx, [rbp+338h]; this
0x18002d800  lea     rax, aFirstruncomple; "firstRunCompleteTime missing from regis"...
0x18002d807  mov     qword ptr [rsp+430h+dwOptions], rax; unsigned int
0x18002d80c  mov     r8, r14; unsigned int
0x18002d80f  mov     edx, 50h ; 'P'; void *
0x18002d814  call    ?Log_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18002d819  cmp     [rsp+430h+Data], rsi
0x18002d81e  jnz     loc_18002D8D5
0x18002d824  mov     [rsp+430h+Data], rbx
0x18002d829  mov     qword ptr [rsp+430h+FileTime.dwLowDateTime], rsi
0x18002d82e  lea     rax, [rsp+430h+FileTime]
0x18002d833  mov     qword ptr [rsp+430h+SystemTime.wYear], rax
0x18002d838  mov     qword ptr [rsp+430h+SystemTime.wHour], rsi
0x18002d83d  mov     [rbp+330h+var_3B0], 1
0x18002d841  mov     [rsp+430h+lpdwDisposition], rsi; lpdwDisposition
0x18002d846  lea     rax, [rsp+430h+SystemTime.wHour]
0x18002d84b  mov     [rsp+430h+phkResult], rax; phkResult
0x18002d850  mov     [rsp+430h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18002d855  mov     [rsp+430h+samDesired], 20006h; samDesired
0x18002d85d  mov     [rsp+430h+dwOptions], esi; unsigned int
0x18002d861  xor     r9d, r9d; lpClass
0x18002d864  xor     r8d, r8d; Reserved
0x18002d867  lea     rdx, ?c_retailDemoKeyServiceReadWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002d86e  mov     rcx, r15; hKey
0x18002d871  call    cs:__imp_RegCreateKeyExW
0x18002d877  mov     rcx, [rbp+338h]; this
0x18002d87e  test    eax, eax
0x18002d880  jnz     loc_18002DB68
0x18002d886  lea     rcx, [rsp+430h+SystemTime]
0x18002d88b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18002d890  mov     [rsp+430h+samDesired], 8; cbData
0x18002d898  lea     rax, [rsp+430h+Data]
0x18002d89d  mov     qword ptr [rsp+430h+dwOptions], rax; unsigned int
0x18002d8a2  mov     r9d, 0Bh; dwType
0x18002d8a8  lea     r8, ?c_retailDemoValueFirstRunCompletedTime@@3QBGB; "FirstRunCompletedTime"
0x18002d8af  xor     edx, edx; lpSubKey
0x18002d8b1  mov     rcx, qword ptr [rsp+430h+FileTime.dwLowDateTime]; hKey
0x18002d8b6  call    cs:__imp_RegSetKeyValueW
0x18002d8bc  mov     rcx, [rbp+338h]; this
0x18002d8c3  test    eax, eax
0x18002d8c5  jnz     loc_18002DB79
0x18002d8cb  lea     rcx, [rsp+430h+FileTime]
0x18002d8d0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002d8d5  mov     [rsp+430h+var_3D4], 202h
0x18002d8dd  lea     rax, [rsp+430h+var_3D4]
0x18002d8e2  mov     [rsp+430h+lpSecurityAttributes], rax; pcbData
0x18002d8e7  lea     rax, [rbp+330h+pvData]
0x18002d8ee  mov     qword ptr [rsp+430h+samDesired], rax; pvData
0x18002d8f3  mov     qword ptr [rsp+430h+dwOptions], rsi; int
0x18002d8f8  mov     r9d, 2; dwFlags
0x18002d8fe  lea     r8, ?c_retailDemoValueAdminAccountName@@3QBGB; "AdminAccount"
0x18002d905  lea     rdx, ?c_retailDemoKeyOobeWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002d90c  mov     rcx, r15; hkey
0x18002d90f  call    cs:__imp_RegGetValueW
0x18002d915  mov     r9d, eax
0x18002d918  test    eax, eax
0x18002d91a  jz      short loc_18002D930
0x18002d91c  mov     [rbp+330h+pvData], si
0x18002d923  jle     short loc_18002D930
0x18002d925  movzx   r9d, ax
0x18002d929  or      r9d, 80070000h; char *
0x18002d930  mov     rcx, [rbp+338h]; this
0x18002d937  test    r9d, r9d
0x18002d93a  js      loc_18002DB8A
0x18002d940  mov     eax, [rsp+430h+var_3D8]
0x18002d944  mov     rcx, 861C46800h
0x18002d94e  imul    rax, rcx
0x18002d952  add     rax, [rsp+430h+Data]
0x18002d957  lea     rdx, [rbp+330h+pvData]; username
0x18002d95e  xor     ecx, ecx; servername
0x18002d960  cmp     rax, rbx
0x18002d963  mov     rbx, [rbp+338h]
0x18002d96a  ja      loc_18002DA5E
0x18002d970  mov     [rsp+430h+var_3D4], 3
0x18002d978  mov     qword ptr [rsp+430h+dwOptions], rsi; unsigned int
0x18002d97d  lea     r9, [rsp+430h+var_3D4]; buf
0x18002d982  mov     r8d, 3F0h; level
0x18002d988  call    cs:__imp_NetUserSetInfo
0x18002d98e  test    eax, eax
0x18002d990  jnz     loc_18002DB98
0x18002d996  mov     [rsp+430h+var_3D8], r13d
0x18002d99b  mov     r9d, r13d; unsigned int
0x18002d99e  lea     r8, ?c_retailDemoValueDelayDisableAdminAccess@@3QBGB; "DelayDisableAdminAccess"
0x18002d9a5  lea     rdx, ?c_retailDemoKeyRetailInfo@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002d9ac  mov     rcx, r15; HKEY
0x18002d9af  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18002d9b4  mov     rcx, [rbp+338h]; this
0x18002d9bb  test    eax, eax
0x18002d9bd  jnz     loc_18002DBAF
0x18002d9c3  mov     qword ptr [rsp+430h+FileTime.dwLowDateTime], rsi
0x18002d9c8  lea     rax, [rsp+430h+FileTime]
0x18002d9cd  mov     qword ptr [rsp+430h+SystemTime.wYear], rax
0x18002d9d2  mov     qword ptr [rsp+430h+SystemTime.wHour], rsi
0x18002d9d7  mov     [rbp+330h+var_3B0], 1
0x18002d9db  mov     [rsp+430h+lpdwDisposition], rsi; lpdwDisposition
0x18002d9e0  lea     rax, [rsp+430h+SystemTime.wHour]
0x18002d9e5  mov     [rsp+430h+phkResult], rax; phkResult
0x18002d9ea  mov     [rsp+430h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18002d9ef  mov     [rsp+430h+samDesired], 20006h; samDesired
0x18002d9f7  mov     [rsp+430h+dwOptions], esi; unsigned int
0x18002d9fb  xor     r9d, r9d; lpClass
0x18002d9fe  xor     r8d, r8d; Reserved
0x18002da01  lea     rdx, ?c_retailDemoKeyServiceReadWrite@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002da08  mov     rcx, r15; hKey
0x18002da0b  call    cs:__imp_RegCreateKeyExW
0x18002da11  mov     rcx, [rbp+338h]; this
0x18002da18  test    eax, eax
0x18002da1a  jnz     loc_18002DBC0
0x18002da20  lea     rcx, [rsp+430h+SystemTime]
0x18002da25  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18002da2a  lea     r8, ?c_retailDemoValueRetailAdminEnabledTime@@3QBGB; "RetailAdminAccountEnabledTime"
0x18002da31  xor     edx, edx; lpSubKey
0x18002da33  mov     rcx, qword ptr [rsp+430h+FileTime.dwLowDateTime]; hKey
0x18002da38  call    cs:__imp_RegDeleteKeyValueW
0x18002da3e  cmp     eax, 2
0x18002da41  jz      short loc_18002DA52
0x18002da43  mov     rcx, [rbp+338h]; this
0x18002da4a  test    eax, eax
0x18002da4c  jnz     loc_18002DBD1
0x18002da52  lea     rcx, [rsp+430h+FileTime]
0x18002da57  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002da5c  jmp     short loc_18002DAD7
0x18002da5e  mov     qword ptr [rsp+430h+FileTime.dwLowDateTime], rsi
0x18002da63  lea     r9, [rsp+430h+FileTime]; bufptr
0x18002da68  mov     r8d, 14h; level
0x18002da6e  call    cs:__imp_NetUserGetInfo
0x18002da74  test    eax, eax
0x18002da76  jnz     loc_18002DBE2
0x18002da7c  lea     rax, [rsp+430h+FileTime]
0x18002da81  mov     qword ptr [rsp+430h+SystemTime.wYear], rax
0x18002da86  mov     byte ptr [rsp+430h+SystemTime.wHour], 1
0x18002da8b  mov     rcx, qword ptr [rsp+430h+FileTime.dwLowDateTime]
0x18002da90  mov     eax, [rcx+18h]
0x18002da93  test    al, 2
0x18002da95  jz      short loc_18002DAD1
0x18002da97  and     eax, 0FFFFFFFDh
0x18002da9a  bts     eax, 10h
0x18002da9e  mov     [rsp+430h+var_3D4], eax
0x18002daa2  mov     rbx, [rbp+338h]
0x18002daa9  mov     qword ptr [rsp+430h+dwOptions], rsi; int
0x18002daae  lea     r9, [rsp+430h+var_3D4]; buf
0x18002dab3  mov     r8d, 3F0h; level
0x18002dab9  lea     rdx, [rbp+330h+pvData]; username
0x18002dac0  xor     ecx, ecx; servername
0x18002dac2  call    cs:__imp_NetUserSetInfo
0x18002dac8  test    eax, eax
0x18002daca  jnz     short loc_18002DB0C
0x18002dacc  mov     rcx, qword ptr [rsp+430h+FileTime.dwLowDateTime]; Buffer
0x18002dad1  call    cs:__imp_NetApiBufferFree
0x18002dad7  xor     edx, edx
0x18002dad9  lea     rcx, [rbp+330h+var_3A0]
0x18002dadd  call    ?Stop@?$ActivityBase@VRetailDemoLogging@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<RetailDemoLogging,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002dae2  nop
0x18002dae3  lea     rcx, [rbp+330h+var_3A0]; this
0x18002dae7  call    ??1DisableAdminAccount@RetailDemoTelemetry@@QEAA@XZ; RetailDemoTelemetry::DisableAdminAccount::~DisableAdminAccount(void)
0x18002daec  mov     rcx, [rbp+330h+var_40]
0x18002daf3  xor     rcx, rsp; StackCookie
0x18002daf6  call    __security_check_cookie
0x18002dafb  add     rsp, 408h
0x18002db02  pop     r15
0x18002db04  pop     r14
  ... truncated ...
```
