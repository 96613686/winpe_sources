# CSoftwareUpdates::SetSettings(__MIDL___MIDL_itf_wmssvc_0000_0000_0022,ulong,ushort const *,ulong,__MIDL___MIDL_itf_wmssvc_0000_0000_0023)

- ea: `0x140030d94`
- end: `0x14003141b`
- name: `?SetSettings@CSoftwareUpdates@@QEAAJW4__MIDL___MIDL_itf_wmssvc_0000_0000_0022@@KPEBGKW4__MIDL___MIDL_itf_wmssvc_0000_0000_0023@@@Z`
- size: `1671`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, ScriptUtils *, int, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14000bfb0`
- `0x140030474`

## callees

- `0x14002c8e8`
- `0x14002c950`
- `0x140030d94`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14006296c`
- `0x14006ea54`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400313fb`
- `ADVAPI32!RegCloseKey` at `0x1400313fb`
- `ADVAPI32!RegDeleteValueW` at `0x14003129b`
- `ADVAPI32!RegDeleteValueW` at `0x14003129b`
- `ADVAPI32!RegCreateKeyExW` at `0x1400310a0`
- `ADVAPI32!RegCreateKeyExW` at `0x1400310a0`
- `ADVAPI32!RegSetValueExW` at `0x140031158`
- `ADVAPI32!RegSetValueExW` at `0x1400311ee`
- `ADVAPI32!RegSetValueExW` at `0x1400312c1`
- `ADVAPI32!RegSetValueExW` at `0x140031359`
- `ADVAPI32!RegSetValueExW` at `0x140031158`
- `ADVAPI32!RegSetValueExW` at `0x1400311ee`
- `ADVAPI32!RegSetValueExW` at `0x1400312c1`
- `ADVAPI32!RegSetValueExW` at `0x140031359`
- `KERNEL32!GetFileAttributesW` at `0x140031046`
- `KERNEL32!GetFileAttributesW` at `0x140031046`
- `KERNEL32!IsDebuggerPresent` at `0x140030e11`
- `KERNEL32!IsDebuggerPresent` at `0x140030eaf`
- `KERNEL32!IsDebuggerPresent` at `0x140030f2f`
- `KERNEL32!IsDebuggerPresent` at `0x140030faa`
- `KERNEL32!IsDebuggerPresent` at `0x1400310f3`
- `KERNEL32!IsDebuggerPresent` at `0x1400311a7`
- `KERNEL32!IsDebuggerPresent` at `0x14003123d`
- `KERNEL32!IsDebuggerPresent` at `0x140031312`
- `KERNEL32!IsDebuggerPresent` at `0x1400313ae`
- `KERNEL32!IsDebuggerPresent` at `0x140030e11`
- `KERNEL32!IsDebuggerPresent` at `0x140030eaf`
- `KERNEL32!IsDebuggerPresent` at `0x140030f2f`
- `KERNEL32!IsDebuggerPresent` at `0x140030faa`
- `KERNEL32!IsDebuggerPresent` at `0x1400310f3`
- `KERNEL32!IsDebuggerPresent` at `0x1400311a7`
- `KERNEL32!IsDebuggerPresent` at `0x14003123d`
- `KERNEL32!IsDebuggerPresent` at `0x140031312`
- `KERNEL32!IsDebuggerPresent` at `0x1400313ae`

## string_xrefs

- `0x140030df2`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x140030e92`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x140030f12`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x140030f8d`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x1400310d0`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x140031184`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x14003121a`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x1400312ef`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x14003138b`: `termsrv\wms\src\devices\wmssvc\softwareupdates.cpp`
- `0x140030de1`: `CSoftwareUpdates::SetSettings`
- `0x140030e86`: `CSoftwareUpdates::SetSettings`
- `0x140030f06`: `CSoftwareUpdates::SetSettings`
- `0x140030f81`: `CSoftwareUpdates::SetSettings`
- `0x1400310c6`: `CSoftwareUpdates::SetSettings`
- `0x14003117a`: `CSoftwareUpdates::SetSettings`
- `0x140031210`: `CSoftwareUpdates::SetSettings`
- `0x1400312e5`: `CSoftwareUpdates::SetSettings`
- `0x140031381`: `CSoftwareUpdates::SetSettings`
- `0x140030e73`: `iScheduledUpdateStartHour <= ( 23 )`
- `0x140030eb7`: `iScheduledUpdateStartHour <= ( 23 )`
- `0x14003101a`: `CSoftwareUpdates::SetSettings - eUpdateMode = %s, start time = %i, script = %s, time limit = %i, return state = %s\n`
- `0x140031142`: `DpSoftwareUpdateMode`
- `0x1400311dc`: `DpSoftwareUpdateStartTime`
- `0x140031275`: `DpSoftwareUpdateScript`
- `0x140031294`: `DpSoftwareUpdateScript`
- `0x1400312af`: `DpSoftwareUpdateScriptMaxRuntimeMinutes`
- `0x140031347`: `DpSoftwareUpdateReturnState`
- `0x14003107d`: `System\CurrentControlSet\Services\WMS\Parameters\`

## pseudocode

```c
__int64 __fastcall CSoftwareUpdates::SetSettings(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        ScriptUtils *a4,
        int a5,
        unsigned int a6)
{
  int v7; // ebx
  bool v8; // zf
  const unsigned __int16 *v9; // rax
  __int64 v10; // r9
  const unsigned __int16 *v11; // rax
  int v12; // edi
  unsigned int v13; // esi
  const unsigned __int16 *v14; // rbx
  unsigned __int64 v15; // r9
  const unsigned __int16 *v16; // rax
  const unsigned __int16 *v17; // rdx
  DWORD FileAttributesW; // eax
  const unsigned __int16 *v19; // rdx
  LSTATUS v20; // eax
  __int64 v21; // r8
  LSTATUS v22; // eax
  LSTATUS v23; // eax
  const unsigned __int16 *v24; // r9
  LSTATUS v25; // eax
  LSTATUS v26; // eax
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-20h]
  PHKEY phkResult; // [rsp+38h] [rbp-18h]
  HKEY hKey; // [rsp+90h] [rbp+40h] BYREF
  unsigned int Data; // [rsp+98h] [rbp+48h] BYREF
  unsigned int v32; // [rsp+A0h] [rbp+50h] BYREF

  v32 = a3;
  Data = a2;
  hKey = 0;
  if ( a2 > 2 )
  {
    v7 = -2147024809;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
      0x5Du,
      L"CSoftwareUpdates::SetSettings",
      L"CBRAEx",
      L"(eMode >= __SUM_First) && (eMode <= __SUM_Last)",
      -2147024809);
    v8 = !IsDebuggerPresent();
    v9 = L"(eMode >= __SUM_First) && (eMode <= __SUM_Last)";
    if ( v8 )
    {
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
        93,
        L"CSoftwareUpdates::SetSettings",
        L"CBRAEx",
        L"(eMode >= __SUM_First) && (eMode <= __SUM_Last)",
        -2147024809);
      goto LABEL_64;
    }
    v10 = 93;
LABEL_4:
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
      v10,
      L"CSoftwareUpdates::SetSettings",
      L"CBRAEx",
      v9,
      -2147024809);
    goto LABEL_64;
  }
  if ( a3 > 0x17 )
  {
    v7 = -2147024809;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
      0x5Eu,
      L"CSoftwareUpdates::SetSettings",
      L"CBRAEx",
      L"iScheduledUpdateStartHour <= ( 23 )",
      -2147024809);
    v8 = !IsDebuggerPresent();
    v9 = L"iScheduledUpdateStartHour <= ( 23 )";
    if ( v8 )
    {
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
        94,
        L"CSoftwareUpdates::SetSettings",
        L"CBRAEx",
        L"iScheduledUpdateStartHour <= ( 23 )",
        -2147024809);
      goto LABEL_64;
    }
    v10 = 94;
    goto LABEL_4;
  }
  if ( (unsigned int)(a5 - 15) > 0xA5 )
  {
    v7 = -2147024809;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
      0x5Fu,
      L"CSoftwareUpdates::SetSettings",
      L"CBRAEx",
      L"(cMaxMinutesAllowedForCustomScript >= ( 15 )) && (cMaxMinutesAllowedForCustomScript <= ( 180 ))",
      -2147024809);
    v8 = !IsDebuggerPresent();
    v9 = L"(cMaxMinutesAllowedForCustomScript >= ( 15 )) && (cMaxMinutesAllowedForCustomScript <= ( 180 ))";
    if ( v8 )
    {
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
        95,
        L"CSoftwareUpdates::SetSettings",
        L"CBRAEx",
        L"(cMaxMinutesAllowedForCustomScript >= ( 15 )) && (cMaxMinutesAllowedForCustomScript <= ( 180 ))",
        -2147024809);
      goto LABEL_64;
    }
    v10 = 95;
    goto LABEL_4;
  }
  if ( a6 > 1 )
  {
    v7 = -2147024809;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
      0x60u,
      L"CSoftwareUpdates::SetSettings",
      L"CBRAEx",
      L"(eReturnState >= __SUR_First) && (eReturnState <= __SUR_Last)",
      -2147024809);
    v8 = !IsDebuggerPresent();
    v9 = L"(eReturnState >= __SUR_First) && (eReturnState <= __SUR_Last)";
    if ( v8 )
    {
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
        96,
        L"CSoftwareUpdates::SetSettings",
        L"CBRAEx",
        L"(eReturnState >= __SUR_First) && (eReturnState <= __SUR_Last)",
        -2147024809);
      goto LABEL_64;
    }
    v10 = 96;
    goto LABEL_4;
  }
  v11 = Utils::StringTableHelper(
          (Utils *)a6,
          (unsigned int)&qword_14009C260,
          (const struct Utils::SStringMap *)2,
          (unsigned __int64)a4);
  v12 = a5;
  v13 = v32;
  v14 = v11;
  v16 = Utils::StringTableHelper(
          (Utils *)Data,
          (unsigned int)&qword_14009C280,
          (const struct Utils::SStringMap *)3,
          v15);
  DEBUGMSG(
    L"CSoftwareUpdates::SetSettings - eUpdateMode = %s, start time = %i, script = %s, time limit = %i, return state = %s\n",
    v16,
    v13,
    a4,
    v12,
    v14);
  if ( a4 && *(_WORD *)a4 )
  {
    v7 = ScriptUtils::CheckExtension(a4, v17);
    if ( v7 < 0 )
      goto LABEL_64;
    FileAttributesW = GetFileAttributesW((LPCWSTR)a4);
    if ( FileAttributesW == -1 || (FileAttributesW & 0x10) != 0 )
    {
      DEBUGMSG(L"ScriptUtils::CheckExistence - File \"%s\" does not exist!", a4);
      v7 = -2147024894;
      goto LABEL_64;
    }
    v7 = ScriptUtils::CheckUsersGrpReadOnly((LPCWSTR)a4, v19);
    if ( v7 < 0 )
      goto LABEL_64;
  }
  v20 = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\WMS\\Parameters\\",
          0,
          0,
          0,
          2u,
          0,
          &hKey,
          0);
  v7 = v20;
  if ( v20 )
  {
    if ( v20 > 0 )
      v7 = (unsigned __int16)v20 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
      0x79u,
      L"CSoftwareUpdates::SetSettings",
      L"CBRAEx",
      L"err == 0L",
      v7);
    if ( IsDebuggerPresent() )
    {
      LODWORD(phkResult) = v7;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
        121,
        L"CSoftwareUpdates::SetSettings",
        L"CBRAEx",
        L"err == 0L",
        phkResult);
      goto LABEL_64;
    }
    v21 = 121;
  }
  else
  {
    v22 = RegSetValueExW(hKey, L"DpSoftwareUpdateMode", 0, 4u, (const BYTE *)&Data, 4u);
    v7 = v22;
    if ( v22 )
    {
      if ( v22 > 0 )
        v7 = (unsigned __int16)v22 | 0x80070000;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
        0x7Cu,
        L"CSoftwareUpdates::SetSettings",
        L"CBRAEx",
        L"err == 0L",
        v7);
      if ( IsDebuggerPresent() )
      {
        LODWORD(phkResult) = v7;
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
          124,
          L"CSoftwareUpdates::SetSettings",
          L"CBRAEx",
          L"err == 0L",
          phkResult);
        goto LABEL_64;
      }
      v21 = 124;
    }
    else
    {
      v23 = RegSetValueExW(hKey, L"DpSoftwareUpdateStartTime", 0, 4u, (const BYTE *)&v32, 4u);
      v7 = v23;
      if ( v23 )
      {
        if ( v23 > 0 )
          v7 = (unsigned __int16)v23 | 0x80070000;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
          0x7Fu,
          L"CSoftwareUpdates::SetSettings",
          L"CBRAEx",
          L"err == 0L",
          v7);
        if ( IsDebuggerPresent() )
        {
          LODWORD(phkResult) = v7;
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
            L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
            127,
            L"CSoftwareUpdates::SetSettings",
            L"CBRAEx",
            L"err == 0L",
            phkResult);
          goto LABEL_64;
        }
        v21 = 127;
      }
      else
      {
        if ( a4 && *(_WORD *)a4 )
        {
          v7 = RegUtil::SetStringValue(
                 (RegUtil *)hKey,
                 (HKEY)L"DpSoftwareUpdateScript",
                 (const unsigned __int16 *)a4,
                 v24);
          if ( v7 < 0 )
            goto LABEL_64;
        }
        else
        {
          v7 = RegDeleteValueW(hKey, L"DpSoftwareUpdateScript");
        }
        v25 = RegSetValueExW(hKey, L"DpSoftwareUpdateScriptMaxRuntimeMinutes", 0, 4u, (const BYTE *)&a5, 4u);
        if ( v25 )
        {
          if ( v25 > 0 )
            v7 = (unsigned __int16)v25 | 0x80070000;
          else
            v7 = v25;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
            0x8Du,
            L"CSoftwareUpdates::SetSettings",
            L"CBRAEx",
            L"err == 0L",
            v7);
          if ( IsDebuggerPresent() )
          {
            LODWORD(phkResult) = v7;
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
              141,
              L"CSoftwareUpdates::SetSettings",
              L"CBRAEx",
              L"err == 0L",
              phkResult);
            goto LABEL_64;
          }
          v21 = 141;
        }
        else
        {
          v26 = RegSetValueExW(hKey, L"DpSoftwareUpdateReturnState", 0, 4u, (const BYTE *)&a6, 4u);
          if ( !v26 )
            goto LABEL_64;
          if ( v26 > 0 )
            v7 = (unsigned __int16)v26 | 0x80070000;
          else
            v7 = v26;
          LOGASSERTHR(
            L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
            0x90u,
            L"CSoftwareUpdates::SetSettings",
            L"CBRAEx",
            L"err == 0L",
            v7);
          if ( IsDebuggerPresent() )
          {
            LODWORD(phkResult) = v7;
            DEBUGMSGLEVEL(
              2u,
              L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
              L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
              144,
              L"CSoftwareUpdates::SetSettings",
              L"CBRAEx",
              L"err == 0L",
              phkResult);
            goto LABEL_64;
          }
          v21 = 144;
        }
      }
    }
  }
  LODWORD(lpSecurityAttributes) = v7;
  DEBUGMSGBOX(
    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
    L"termsrv\\wms\\src\\devices\\wmssvc\\softwareupdates.cpp",
    v21,
    L"CSoftwareUpdates::SetSettings",
    L"CBRAEx",
    L"err == 0L",
    lpSecurityAttributes);
LABEL_64:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140030d94  mov     rax, rsp
0x140030d97  mov     [rax+20h], rbx
0x140030d9b  mov     [rax+18h], r8d
0x140030d9f  mov     [rax+10h], edx
0x140030da2  mov     [rax+8], rcx
0x140030da6  push    rbp
0x140030da7  push    rsi
0x140030da8  push    rdi
0x140030da9  push    r12
0x140030dab  push    r13
0x140030dad  push    r14
0x140030daf  push    r15
0x140030db1  mov     rbp, rsp
0x140030db4  sub     rsp, 50h
0x140030db8  xor     r12d, r12d
0x140030dbb  mov     r14, r9
0x140030dbe  mov     [rbp+hKey], r12
0x140030dc2  lea     r13d, [r12+2]
0x140030dc7  cmp     edx, r13d
0x140030dca  jbe     loc_140030E67
0x140030dd0  mov     r15d, 80070057h
0x140030dd6  lea     r14, aCbraex; "CBRAEx"
0x140030ddd  mov     [rax-60h], r15d
0x140030de1  lea     rsi, aCsoftwareupdat_5; "CSoftwareUpdates::SetSettings"
0x140030de8  lea     rax, aEmodeSumFirstE; "(eMode >= __SUM_First) && (eMode <= __S"...
0x140030def  mov     r9, r14; unsigned __int16 *
0x140030df2  lea     rdi, aTermsrvWmsSrcD_18; "termsrv\\wms\\src\\devices\\wmssvc\\sof"...
0x140030df9  mov     qword ptr [rsp+50h+dwOptions], rax; unsigned __int16 *
0x140030dfe  mov     r8, rsi; unsigned __int16 *
0x140030e01  lea     edx, [r12+5Dh]; unsigned int
0x140030e06  mov     rcx, rdi; unsigned __int16 *
0x140030e09  mov     ebx, r15d
0x140030e0c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140030e11  call    cs:__imp_IsDebuggerPresent
0x140030e17  test    eax, eax
0x140030e19  lea     rax, aEmodeSumFirstE; "(eMode >= __SUM_First) && (eMode <= __S"...
0x140030e20  jz      short loc_140030E52
0x140030e22  lea     r9d, [r12+5Dh]
0x140030e27  mov     dword ptr [rsp+50h+phkResult], r15d
0x140030e2c  mov     [rsp+50h+lpSecurityAttributes], rax
0x140030e31  mov     qword ptr [rsp+50h+samDesired], r14
0x140030e36  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140030e3d  mov     r8, rdi
0x140030e40  mov     qword ptr [rsp+50h+dwOptions], rsi
0x140030e45  mov     ecx, r13d; unsigned __int8
0x140030e48  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140030e4d  jmp     loc_1400313F2
0x140030e52  mov     dword ptr [rsp+50h+lpSecurityAttributes], r15d
0x140030e57  mov     r8d, 5Dh ; ']'
0x140030e5d  mov     qword ptr [rsp+50h+samDesired], rax
0x140030e62  jmp     loc_1400313DB
0x140030e67  cmp     r8d, 17h
0x140030e6b  jbe     short loc_140030EE0
0x140030e6d  mov     r15d, 80070057h
0x140030e73  lea     rax, aIscheduledupda; "iScheduledUpdateStartHour <= ( 23 )"
0x140030e7a  lea     r14, aCbraex; "CBRAEx"
0x140030e81  mov     [rsp+50h+samDesired], r15d; int
0x140030e86  lea     rsi, aCsoftwareupdat_5; "CSoftwareUpdates::SetSettings"
0x140030e8d  mov     qword ptr [rsp+50h+dwOptions], rax; unsigned __int16 *
0x140030e92  lea     rdi, aTermsrvWmsSrcD_18; "termsrv\\wms\\src\\devices\\wmssvc\\sof"...
0x140030e99  mov     r9, r14; unsigned __int16 *
0x140030e9c  mov     r8, rsi; unsigned __int16 *
0x140030e9f  mov     rcx, rdi; unsigned __int16 *
0x140030ea2  mov     edx, 5Eh ; '^'; unsigned int
0x140030ea7  mov     ebx, r15d
0x140030eaa  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140030eaf  call    cs:__imp_IsDebuggerPresent
0x140030eb5  test    eax, eax
0x140030eb7  lea     rax, aIscheduledupda; "iScheduledUpdateStartHour <= ( 23 )"
0x140030ebe  jz      short loc_140030ECB
0x140030ec0  mov     r9d, 5Eh ; '^'
0x140030ec6  jmp     loc_140030E27
0x140030ecb  mov     dword ptr [rsp+50h+lpSecurityAttributes], r15d
0x140030ed0  mov     r8d, 5Eh ; '^'
0x140030ed6  mov     qword ptr [rsp+50h+samDesired], rax
0x140030edb  jmp     loc_1400313DB
0x140030ee0  mov     eax, [rbp+arg_20]
0x140030ee3  add     eax, 0FFFFFFF1h
0x140030ee6  cmp     eax, 0A5h
0x140030eeb  jbe     short loc_140030F60
0x140030eed  mov     r15d, 80070057h
0x140030ef3  lea     rax, aCmaxminutesall_0; "(cMaxMinutesAllowedForCustomScript >= ("...
0x140030efa  lea     r14, aCbraex; "CBRAEx"
0x140030f01  mov     [rsp+50h+samDesired], r15d; int
0x140030f06  lea     rsi, aCsoftwareupdat_5; "CSoftwareUpdates::SetSettings"
0x140030f0d  mov     qword ptr [rsp+50h+dwOptions], rax; unsigned __int16 *
0x140030f12  lea     rdi, aTermsrvWmsSrcD_18; "termsrv\\wms\\src\\devices\\wmssvc\\sof"...
0x140030f19  mov     r9, r14; unsigned __int16 *
0x140030f1c  mov     r8, rsi; unsigned __int16 *
0x140030f1f  mov     rcx, rdi; unsigned __int16 *
0x140030f22  mov     edx, 5Fh ; '_'; unsigned int
0x140030f27  mov     ebx, r15d
0x140030f2a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140030f2f  call    cs:__imp_IsDebuggerPresent
0x140030f35  test    eax, eax
0x140030f37  lea     rax, aCmaxminutesall_0; "(cMaxMinutesAllowedForCustomScript >= ("...
0x140030f3e  jz      short loc_140030F4B
0x140030f40  mov     r9d, 5Fh ; '_'
0x140030f46  jmp     loc_140030E27
0x140030f4b  mov     dword ptr [rsp+50h+lpSecurityAttributes], r15d
0x140030f50  mov     r8d, 5Fh ; '_'
0x140030f56  mov     qword ptr [rsp+50h+samDesired], rax
0x140030f5b  jmp     loc_1400313DB
0x140030f60  mov     ecx, [rbp+arg_28]; this
0x140030f63  cmp     ecx, 1
0x140030f66  jbe     short loc_140030FDB
0x140030f68  mov     r15d, 80070057h
0x140030f6e  lea     rax, aEreturnstateSu; "(eReturnState >= __SUR_First) && (eRetu"...
0x140030f75  lea     r14, aCbraex; "CBRAEx"
0x140030f7c  mov     [rsp+50h+samDesired], r15d; int
0x140030f81  lea     rsi, aCsoftwareupdat_5; "CSoftwareUpdates::SetSettings"
0x140030f88  mov     qword ptr [rsp+50h+dwOptions], rax; unsigned __int16 *
0x140030f8d  lea     rdi, aTermsrvWmsSrcD_18; "termsrv\\wms\\src\\devices\\wmssvc\\sof"...
0x140030f94  mov     r9, r14; unsigned __int16 *
0x140030f97  mov     r8, rsi; unsigned __int16 *
0x140030f9a  mov     rcx, rdi; unsigned __int16 *
0x140030f9d  mov     edx, 60h ; '`'; unsigned int
0x140030fa2  mov     ebx, r15d
0x140030fa5  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140030faa  call    cs:__imp_IsDebuggerPresent
0x140030fb0  test    eax, eax
0x140030fb2  lea     rax, aEreturnstateSu; "(eReturnState >= __SUR_First) && (eRetu"...
0x140030fb9  jz      short loc_140030FC6
0x140030fbb  mov     r9d, 60h ; '`'; unsigned __int64
0x140030fc1  jmp     loc_140030E27
0x140030fc6  mov     dword ptr [rsp+50h+lpSecurityAttributes], r15d
0x140030fcb  mov     r8d, 60h ; '`'
0x140030fd1  mov     qword ptr [rsp+50h+samDesired], rax
0x140030fd6  jmp     loc_1400313DB
0x140030fdb  mov     r8, r13; struct Utils::SStringMap *
0x140030fde  lea     rdx, qword_14009C260; unsigned int
0x140030fe5  call    ?StringTableHelper@Utils@@YAPEBGKPEBUSStringMap@1@_K@Z; Utils::StringTableHelper(ulong,Utils::SStringMap const *,unsigned __int64)
0x140030fea  mov     ecx, [rbp+Data]; this
0x140030fed  lea     rdx, qword_14009C280; unsigned int
0x140030ff4  mov     edi, [rbp+arg_20]
0x140030ff7  mov     r8d, 3; struct Utils::SStringMap *
0x140030ffd  mov     esi, [rbp+arg_10]
0x140031000  mov     rbx, rax
0x140031003  call    ?StringTableHelper@Utils@@YAPEBGKPEBUSStringMap@1@_K@Z; Utils::StringTableHelper(ulong,Utils::SStringMap const *,unsigned __int64)
0x140031008  mov     r9, r14
0x14003100b  mov     qword ptr [rsp+50h+samDesired], rbx
0x140031010  mov     r8d, esi
0x140031013  mov     [rsp+50h+dwOptions], edi
0x140031017  mov     rdx, rax
0x14003101a  lea     rcx, aCsoftwareupdat_3; "CSoftwareUpdates::SetSettings - eUpdate"...
0x140031021  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140031026  test    r14, r14
0x140031029  jz      short loc_14003106F
0x14003102b  cmp     [r14], r12w
0x14003102f  jz      short loc_14003106F
0x140031031  mov     rcx, r14; this
0x140031034  call    ?CheckExtension@ScriptUtils@@YAJPEBG@Z; ScriptUtils::CheckExtension(ushort const *)
0x140031039  mov     ebx, eax
0x14003103b  test    eax, eax
0x14003103d  js      loc_1400313F2
0x140031043  mov     rcx, r14; lpFileName
0x140031046  call    cs:__imp_GetFileAttributesW
0x14003104c  cmp     eax, 0FFFFFFFFh
0x14003104f  jz      loc_140031111
0x140031055  test    al, 10h
0x140031057  jnz     loc_140031111
0x14003105d  mov     rcx, r14; pObjectName
0x140031060  call    ?CheckUsersGrpReadOnly@ScriptUtils@@YAJPEBG@Z; ScriptUtils::CheckUsersGrpReadOnly(ushort const *)
0x140031065  mov     ebx, eax
0x140031067  test    eax, eax
0x140031069  js      loc_1400313F2
0x14003106f  mov     [rsp+50h+lpdwDisposition], r12; lpdwDisposition
0x140031074  lea     rax, [rbp+hKey]
0x140031078  mov     [rsp+50h+phkResult], rax; phkResult
0x14003107d  lea     rdx, ?s_szRegKey@CSoftwareUpdates@@0QBGB; "System\\CurrentControlSet\\Services\\WM"...
0x140031084  mov     [rsp+50h+lpSecurityAttributes], r12; lpSecurityAttributes
0x140031089  xor     r9d, r9d; lpClass
0x14003108c  mov     [rsp+50h+samDesired], r13d; samDesired
0x140031091  xor     r8d, r8d; Reserved
0x140031094  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14003109b  mov     [rsp+50h+dwOptions], r12d; dwOptions
0x1400310a0  call    cs:__imp_RegCreateKeyExW
0x1400310a6  mov     ebx, eax
0x1400310a8  test    eax, eax
0x1400310aa  jz      loc_140031135
0x1400310b0  jle     short loc_1400310BB
0x1400310b2  movzx   ebx, ax
0x1400310b5  or      ebx, 80070000h
0x1400310bb  lea     r14, aCbraex; "CBRAEx"
0x1400310c2  mov     [rsp+50h+samDesired], ebx; int
0x1400310c6  lea     rsi, aCsoftwareupdat_5; "CSoftwareUpdates::SetSettings"
0x1400310cd  mov     r9, r14; unsigned __int16 *
0x1400310d0  lea     rdi, aTermsrvWmsSrcD_18; "termsrv\\wms\\src\\devices\\wmssvc\\sof"...
0x1400310d7  mov     r8, rsi; unsigned __int16 *
0x1400310da  lea     r15, aErr0l; "err == 0L"
0x1400310e1  mov     rcx, rdi; unsigned __int16 *
0x1400310e4  mov     edx, 79h ; 'y'; unsigned int
0x1400310e9  mov     qword ptr [rsp+50h+dwOptions], r15; unsigned __int16 *
0x1400310ee  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400310f3  call    cs:__imp_IsDebuggerPresent
0x1400310f9  test    eax, eax
0x1400310fb  jz      short loc_14003112A
0x1400310fd  mov     dword ptr [rsp+50h+phkResult], ebx
0x140031101  mov     r9d, 79h ; 'y'
0x140031107  mov     [rsp+50h+lpSecurityAttributes], r15
0x14003110c  jmp     loc_140030E31
0x140031111  mov     rdx, r14
0x140031114  lea     rcx, aScriptutilsChe; "ScriptUtils::CheckExistence - File \"%s"...
0x14003111b  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140031120  mov     ebx, 80070002h
0x140031125  jmp     loc_1400313F2
0x14003112a  mov     r8d, 79h ; 'y'
0x140031130  jmp     loc_1400313D2
0x140031135  mov     rcx, [rbp+hKey]; hKey
0x140031139  lea     rax, [rbp+Data]
0x14003113d  mov     edi, 4
0x140031142  lea     rdx, aDpsoftwareupda_5; "DpSoftwareUpdateMode"
0x140031149  mov     [rsp+50h+samDesired], edi; cbData
0x14003114d  mov     r9d, edi; dwType
0x140031150  xor     r8d, r8d; Reserved
0x140031153  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x140031158  call    cs:__imp_RegSetValueExW
0x14003115e  mov     ebx, eax
0x140031160  test    eax, eax
0x140031162  jz      short loc_1400311D0
0x140031164  jle     short loc_14003116F
0x140031166  movzx   ebx, ax
0x140031169  or      ebx, 80070000h
0x14003116f  lea     r14, aCbraex; "CBRAEx"
0x140031176  mov     [rsp+50h+samDesired], ebx; int
0x14003117a  lea     rsi, aCsoftwareupdat_5; "CSoftwareUpdates::SetSettings"
0x140031181  mov     r9, r14; unsigned __int16 *
0x140031184  lea     rdi, aTermsrvWmsSrcD_18; "termsrv\\wms\\src\\devices\\wmssvc\\sof"...
0x14003118b  mov     r8, rsi; unsigned __int16 *
0x14003118e  lea     r15, aErr0l; "err == 0L"
0x140031195  mov     rcx, rdi; unsigned __int16 *
0x140031198  mov     edx, 7Ch ; '|'; unsigned int
0x14003119d  mov     qword ptr [rsp+50h+dwOptions], r15; unsigned __int16 *
0x1400311a2  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400311a7  call    cs:__imp_IsDebuggerPresent
0x1400311ad  test    eax, eax
0x1400311af  jz      short loc_1400311C5
0x1400311b1  mov     dword ptr [rsp+50h+phkResult], ebx
0x1400311b5  mov     r9d, 7Ch ; '|'
0x1400311bb  mov     [rsp+50h+lpSecurityAttributes], r15
0x1400311c0  jmp     loc_140030E31
0x1400311c5  mov     r8d, 7Ch ; '|'
0x1400311cb  jmp     loc_1400313D2
0x1400311d0  mov     rcx, [rbp+hKey]; hKey
0x1400311d4  lea     rax, [rbp+arg_10]
0x1400311d8  mov     [rsp+50h+samDesired], edi; cbData
0x1400311dc  lea     rdx, aDpsoftwareupda_4; "DpSoftwareUpdateStartTime"
0x1400311e3  mov     r9d, edi; dwType
0x1400311e6  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1400311eb  xor     r8d, r8d; Reserved
0x1400311ee  call    cs:__imp_RegSetValueExW
0x1400311f4  mov     ebx, eax
0x1400311f6  test    eax, eax
0x1400311f8  jz      short loc_140031266
0x1400311fa  jle     short loc_140031205
0x1400311fc  movzx   ebx, ax
0x1400311ff  or      ebx, 80070000h
0x140031205  lea     r14, aCbraex; "CBRAEx"
0x14003120c  mov     [rsp+50h+samDesired], ebx; int
0x140031210  lea     rsi, aCsoftwareupdat_5; "CSoftwareUpdates::SetSettings"
0x140031217  mov     r9, r14; unsigned __int16 *
0x14003121a  lea     rdi, aTermsrvWmsSrcD_18; "termsrv\\wms\\src\\devices\\wmssvc\\sof"...
0x140031221  mov     r8, rsi; unsigned __int16 *
0x140031224  lea     r15, aErr0l; "err == 0L"
0x14003122b  mov     rcx, rdi; unsigned __int16 *
0x14003122e  mov     edx, 7Fh; unsigned int
0x140031233  mov     qword ptr [rsp+50h+dwOptions], r15; unsigned __int16 *
0x140031238  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14003123d  call    cs:__imp_IsDebuggerPresent
0x140031243  test    eax, eax
0x140031245  jz      short loc_14003125B
0x140031247  mov     dword ptr [rsp+50h+phkResult], ebx
0x14003124b  mov     r9d, 7Fh
0x140031251  mov     [rsp+50h+lpSecurityAttributes], r15
0x140031256  jmp     loc_140030E31
0x14003125b  mov     r8d, 7Fh
0x140031261  jmp     loc_1400313D2
0x140031266  test    r14, r14
0x140031269  jz      short loc_140031290
0x14003126b  cmp     [r14], r12w
0x14003126f  jz      short loc_140031290
0x140031271  mov     rcx, [rbp+hKey]; this
0x140031275  lea     rdx, aDpsoftwareupda; "DpSoftwareUpdateScript"
0x14003127c  mov     r8, r14; unsigned __int16 *
0x14003127f  call    ?SetStringValue@RegUtil@@YAJPEAUHKEY__@@PEBG1@Z; RegUtil::SetStringValue(HKEY__ *,ushort const *,ushort const *)
0x140031284  mov     ebx, eax
0x140031286  test    eax, eax
0x140031288  js      loc_1400313F2
0x14003128e  jmp     short loc_1400312A3
0x140031290  mov     rcx, [rbp+hKey]; hKey
0x140031294  lea     rdx, aDpsoftwareupda; "DpSoftwareUpdateScript"
0x14003129b  call    cs:__imp_RegDeleteValueW
0x1400312a1  mov     ebx, eax
0x1400312a3  mov     rcx, [rbp+hKey]; hKey
0x1400312a7  lea     rax, [rbp+arg_20]
0x1400312ab  mov     [rsp+50h+samDesired], edi; cbData
0x1400312af  lea     rdx, aDpsoftwareupda_6; "DpSoftwareUpdateScriptMaxRuntimeMinutes"
0x1400312b6  mov     r9d, edi; dwType
0x1400312b9  mov     qword ptr [rsp+50h+dwOptions], rax; lpData
0x1400312be  xor     r8d, r8d; Reserved
  ... truncated ...
```
