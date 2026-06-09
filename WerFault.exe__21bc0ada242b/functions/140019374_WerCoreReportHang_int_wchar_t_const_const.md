# WerCoreReportHang(int,wchar_t const * * const)

- ea: `0x140019374`
- end: `0x140019f11`
- name: `?WerCoreReportHang@@YAHHQEAPEB_W@Z`
- size: `2973`
- prototype: `__int64 __fastcall(int, const wchar_t **const)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000d9f0`

## callees

- `0x140002470`
- `0x140002494`
- `0x1400030a8`
- `0x140003b14`
- `0x140003ce4`
- `0x140003e30`
- `0x14000bcf8`
- `0x14001444c`
- `0x140014474`
- `0x140014564`
- `0x140018ab4`
- `0x140018cd4`
- `0x140018dbc`
- `0x140018f64`
- `0x140019048`
- `0x140019374`
- `0x140019f18`
- `0x14001a0fc`
- `0x14001bdbc`
- `0x14001d1f8`
- `0x14001dd84`
- `0x14001f298`
- `0x14001fb18`
- `0x1400223c8`
- `0x140030450`
- `0x14005b770`
- `0x14005b7e8`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400198ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400198ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x140019594`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x140019594`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019641`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400197d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400198d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019b59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019e1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019e53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019641`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400197d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400198d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019b59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019e1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019e53`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x1400197c6`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x140019819`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x140019828`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x140019837`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x140019846`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x140019855`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x140019864`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x140019873`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x1400197c6`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x140019819`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x140019828`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x140019837`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x140019846`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x140019855`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x140019864`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x140019873`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x140019e14`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x140019e14`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x140019dbf`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x140019dbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140019db6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140019e06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140019db6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140019e06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019714`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140019714`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140019633`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x140019633`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001956f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001956f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14001974f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140019a50`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14001974f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140019a50`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140019b42`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140019b42`
- `ext-ms-win-ntuser-window-l1-1-0!GetShellWindow` at `0x140019d39`
- `ext-ms-win-ntuser-window-l1-1-0!GetShellWindow` at `0x140019d39`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x140019d47`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x140019d47`
- `ext-ms-win-wer-xbox-l1-1-1!XerDumpNotifyComplete` at `0x1400196a6`
- `ext-ms-win-wer-xbox-l1-1-1!XerDumpNotifyComplete` at `0x1400196a6`
- `ext-ms-win-wer-xbox-l1-1-1!XerDumpNotifyStart` at `0x140019b95`
- `ext-ms-win-wer-xbox-l1-1-1!XerDumpNotifyStart` at `0x140019b95`
- `ext-ms-win-wer-ui-l1-1-1!WerUIpCheckWindow` at `0x140019a9b`
- `ext-ms-win-wer-ui-l1-1-1!WerUIpCheckWindow` at `0x140019a9b`
- `ext-ms-win-imm-l1-1-0!ImmDisableIME` at `0x1400195a6`
- `ext-ms-win-imm-l1-1-0!ImmDisableIME` at `0x1400195a6`

## string_xrefs

- `0x140019812`: `_NT_SYMBOL_PATH`
- `0x140019821`: `_NT_ALT_SYMBOL_PATH`
- `0x140019830`: `_NT_EXECUTABLE_IMAGE_PATH`
- `0x14001983f`: `_NT_DEBUGGER_EXTENSION_PATH`
- `0x14001984e`: `_NT_SOURCE_PATH`
- `0x14001985d`: `_NT_DEBUG_LOG_FILE_OPEN`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WerCoreReportHang(int a1, const wchar_t **const a2)
{
  CUserModeHangReport *v4; // rdi
  char *v5; // rcx
  WCHAR *v6; // rax
  __int64 v7; // rdx
  char *v8; // r13
  CUserModeHangReport *v9; // rcx
  int i; // ebx
  UINT SystemDirectoryW; // eax
  signed int LastError; // eax
  unsigned int v13; // ebx
  CUserModeHangReport *v14; // rcx
  __int64 v15; // rdx
  CUserModeHangReport *v17; // rcx
  __int64 v18; // rdx
  signed int v19; // eax
  CConfig *v20; // rcx
  __int64 v21; // rcx
  signed int v22; // eax
  CUserModeHangReport *v23; // r10
  int v24; // r9d
  wchar_t *v25; // rbx
  __int64 v26; // rax
  __int64 v27; // r11
  int v28; // r8d
  int v29; // ecx
  int v30; // edx
  int v31; // ecx
  __int64 v32; // rdx
  const WCHAR *v33; // r15
  int v34; // eax
  CUserModeHangReport *v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // r9
  LPCVOID v38; // rbx
  HWND v39; // r9
  signed int v40; // eax
  int v41; // r14d
  CHangReport *v42; // rax
  CUserModeHangReport *v43; // rcx
  __int64 v44; // rdx
  CUserModeHangReport *v45; // rax
  int v46; // ebx
  unsigned int v47; // ebx
  HWND ShellWindow; // rax
  HANDLE CurrentProcess; // rax
  DWORD PriorityClass; // eax
  HANDLE v51; // rax
  signed int v52; // eax
  signed int v53; // eax
  DWORD v54; // [rsp+30h] [rbp-D0h] BYREF
  int v55; // [rsp+34h] [rbp-CCh]
  DWORD TickCount; // [rsp+38h] [rbp-C8h]
  LPCVOID lpBaseAddress; // [rsp+40h] [rbp-C0h] BYREF
  CUserModeHangReport *v58; // [rsp+48h] [rbp-B8h]
  char *v59; // [rsp+50h] [rbp-B0h]
  CHangReport *v60; // [rsp+58h] [rbp-A8h]
  _OWORD v61[3]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v62[1152]; // [rsp+90h] [rbp-70h] BYREF
  int v63; // [rsp+510h] [rbp+410h]
  DWORD dwProcessId; // [rsp+514h] [rbp+414h]
  unsigned int v65; // [rsp+518h] [rbp+418h]
  HWND v66; // [rsp+628h] [rbp+528h]
  int v67; // [rsp+630h] [rbp+530h]
  __int64 v68; // [rsp+810h] [rbp+710h] BYREF
  __int16 v69; // [rsp+818h] [rbp+718h]
  __int16 v70; // [rsp+A20h] [rbp+920h]
  __int16 v71; // [rsp+C28h] [rbp+B28h]
  __int16 v72; // [rsp+D28h] [rbp+C28h]
  __int16 v73; // [rsp+DACh] [rbp+CACh]
  _WORD *v74; // [rsp+EB8h] [rbp+DB8h]
  _WORD *v75; // [rsp+EC0h] [rbp+DC0h]
  _WORD v76[8]; // [rsp+EC8h] [rbp+DC8h] BYREF
  _WORD *v77; // [rsp+ED8h] [rbp+DD8h]
  _WORD *v78; // [rsp+EE0h] [rbp+DE0h]
  _WORD v79[8]; // [rsp+EE8h] [rbp+DE8h] BYREF
  _WORD *v80; // [rsp+EF8h] [rbp+DF8h]
  _WORD *v81; // [rsp+F00h] [rbp+E00h]
  _WORD v82[8]; // [rsp+F08h] [rbp+E08h] BYREF
  __int64 v83; // [rsp+F18h] [rbp+E18h]
  __int64 v84; // [rsp+F20h] [rbp+E20h]
  int v85; // [rsp+F28h] [rbp+E28h]
  _WORD *v86; // [rsp+F30h] [rbp+E30h]
  _WORD *v87; // [rsp+F38h] [rbp+E38h]
  _WORD v88[8]; // [rsp+F40h] [rbp+E40h] BYREF
  __int64 v89; // [rsp+F50h] [rbp+E50h]
  __int64 v90; // [rsp+F58h] [rbp+E58h]
  int v91; // [rsp+F60h] [rbp+E60h]
  __int128 v92; // [rsp+F64h] [rbp+E64h]
  _BYTE v93[28]; // [rsp+F74h] [rbp+E74h]
  char v94; // [rsp+F90h] [rbp+E90h] BYREF
  WCHAR Buffer[264]; // [rsp+10A0h] [rbp+FA0h] BYREF

  v55 = 0;
  lpBaseAddress = 0;
  v4 = 0;
  v58 = 0;
  v74 = v76;
  v75 = v76;
  v76[0] = 0;
  v77 = v79;
  v78 = v79;
  v79[0] = 0;
  v80 = v82;
  v81 = v82;
  v82[0] = 0;
  v86 = v88;
  v87 = v88;
  v88[0] = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v83 = 0;
  v84 = 0;
  v85 = 3;
  v89 = 0;
  v90 = 0;
  memset_0(Buffer, 0, 0x108u);
  v5 = &v94;
  v6 = Buffer;
  v7 = 2;
  do
  {
    *(_OWORD *)v5 = *(_OWORD *)v6;
    *((_OWORD *)v5 + 1) = *((_OWORD *)v6 + 1);
    *((_OWORD *)v5 + 2) = *((_OWORD *)v6 + 2);
    *((_OWORD *)v5 + 3) = *((_OWORD *)v6 + 3);
    *((_OWORD *)v5 + 4) = *((_OWORD *)v6 + 4);
    *((_OWORD *)v5 + 5) = *((_OWORD *)v6 + 5);
    *((_OWORD *)v5 + 6) = *((_OWORD *)v6 + 6);
    *((_OWORD *)v5 + 7) = *((_OWORD *)v6 + 7);
    v5 += 128;
    v6 += 64;
    --v7;
  }
  while ( v7 );
  *(_QWORD *)v5 = *(_QWORD *)v6;
  memset(v61, 0, sizeof(v61));
  v92 = *(_OWORD *)((char *)v61 + 4);
  *(_OWORD *)v93 = *(_OWORD *)((char *)&v61[1] + 4);
  *(_OWORD *)&v93[12] = 0;
  v91 = 48;
  memset_0(v62, 0, 0x778u);
  v54 = 0;
  TickCount = GetTickCount();
  v8 = 0;
  v59 = 0;
  CheckAttachDebugger();
  UtilCheckDebugWait(L"WaitOnCoreHang");
  SetErrorMode(0);
  if ( (unsigned __int8)IsImmDisableIMEPresent() )
    ImmDisableIME(0xFFFFFFFF);
  v9 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
    for ( i = 0; i < a1; ++i )
    {
      if ( v9 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 4) != 0 )
      {
        WPP_SF_dS(
          *((_QWORD *)v9 + 2),
          33,
          (unsigned int)WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids,
          i,
          (__int64)a2[i]);
        v9 = WPP_GLOBAL_Control;
      }
    }
  }
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( !SystemDirectoryW )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_20;
    }
    v15 = 34;
    goto LABEL_19;
  }
  if ( SystemDirectoryW > 0x104 )
  {
    v13 = -2147024774;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_20;
    }
    v18 = 35;
    goto LABEL_45;
  }
  if ( !SetEnvironmentVariableW(L"PATH", Buffer) )
  {
    v19 = GetLastError();
    v13 = v19;
    if ( v19 > 0 )
      v13 = (unsigned __int16)v19 | 0x80070000;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_20;
    }
    v15 = 36;
LABEL_19:
    WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids, v13);
    goto LABEL_20;
  }
  SetEnvironmentVariableW(L"_NT_SYMBOL_PATH", 0);
  SetEnvironmentVariableW(L"_NT_ALT_SYMBOL_PATH", 0);
  SetEnvironmentVariableW(L"_NT_EXECUTABLE_IMAGE_PATH", 0);
  SetEnvironmentVariableW(L"_NT_DEBUGGER_EXTENSION_PATH", 0);
  SetEnvironmentVariableW(L"_NT_SOURCE_PATH", 0);
  SetEnvironmentVariableW(L"_NT_DEBUG_LOG_FILE_OPEN", 0);
  SetEnvironmentVariableW(L"_NT_DEBUG_LOG_FILE_APPEND", 0);
  if ( (unsigned int)CConfig::IsHangReportingDisabled(v20) )
  {
    v13 = 1;
    UtilFireWerVerticalDisabledEvent(v21, L"Hangs", 1);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
      goto LABEL_20;
    }
    v18 = 37;
LABEL_45:
    WPP_SF_(*((_QWORD *)v17 + 2), v18, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids);
    goto LABEL_20;
  }
  g_instance = GetModuleHandleW(0);
  if ( !g_instance )
  {
    v22 = GetLastError();
    if ( v22 > 0 )
      v22 = (unsigned __int16)v22 | 0x80070000;
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
      goto LABEL_63;
    }
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids,
      (unsigned int)v22);
  }
  v23 = WPP_GLOBAL_Control;
LABEL_63:
  v24 = 0;
  if ( a1 <= 0 )
    goto LABEL_77;
  while ( 1 )
  {
    v25 = (wchar_t *)a2[v24];
    v26 = -1;
    do
      ++v26;
    while ( v25[v26] );
    if ( v26 == 7 )
      break;
LABEL_76:
    if ( ++v24 >= a1 )
      goto LABEL_77;
  }
  if ( v25 != L"/SHARED" )
  {
    v27 = 0;
    do
    {
      v28 = v25[v27];
      v29 = aShared[v27];
      v30 = v29 - 32;
      if ( (unsigned int)(v29 - 97) >= 0x1A )
        v30 = aShared[v27];
      v31 = v28 - 32;
      if ( (unsigned int)(v28 - 97) >= 0x1A )
        v31 = v25[v27];
      if ( v31 != v30 )
        goto LABEL_76;
    }
    while ( ++v27 != 7 );
  }
  if ( v24 >= a1 - 1 )
  {
    v13 = -2147024809;
    if ( v23 == (CUserModeHangReport *)&WPP_GLOBAL_Control || (*((_BYTE *)v23 + 28) & 1) == 0 )
      goto LABEL_20;
    v32 = 39;
LABEL_171:
    WPP_SF_(*((_QWORD *)v23 + 2), v32, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids);
    goto LABEL_20;
  }
  v33 = a2[v24 + 1];
  if ( !v33 )
  {
LABEL_77:
    v13 = -2147024809;
    if ( v23 == (CUserModeHangReport *)&WPP_GLOBAL_Control || (*((_BYTE *)v23 + 28) & 1) == 0 )
      goto LABEL_20;
    v32 = 40;
    goto LABEL_171;
  }
  v34 = OpenSharedMemory(v33, &lpBaseAddress);
  v13 = v34;
  if ( v34 < 0 )
  {
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v36 = 41;
      goto LABEL_86;
    }
    goto LABEL_20;
  }
  v38 = lpBaseAddress;
  memcpy_0(v62, lpBaseAddress, 0x778u);
  lpBaseAddress = 0;
  if ( v38 )
    UnmapViewOfFile(v38);
  v34 = ValidateSharedMemory((struct SharedHangRepData *)v62);
  v13 = v34;
  if ( v34 < 0 )
  {
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_20;
    }
    v36 = 42;
    goto LABEL_86;
  }
  if ( (unsigned __int8)IsWerUIpSetWindowSubclassPresent() )
  {
    v34 = WerUIpCheckWindow(v62);
    v13 = v34;
    if ( v34 )
    {
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_20;
      }
      v36 = 43;
      goto LABEL_86;
    }
    v39 = v66;
  }
  else
  {
    v39 = 0;
  }
  v13 = CProcessInformation::Init((CProcessInformation *)&v68, dwProcessId, v65, v39);
  if ( (v13 & 0x80000000) != 0 )
  {
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_20;
    }
    v36 = 44;
    goto LABEL_105;
  }
  if ( (unsigned __int8)IsXerDumpNotifyStartPresent() )
  {
    v8 = (char *)OpenProcess(0x1FFFFFu, 0, dwProcessId);
    v59 = v8;
    if ( v8 == (char *)-1LL || v8 + 1 == (char *)1 )
    {
      v40 = GetLastError();
      v13 = v40;
      if ( v40 > 0 )
        v13 = (unsigned __int16)v40 | 0x80070000;
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_20;
      }
      v36 = 45;
      goto LABEL_105;
    }
    XerDumpNotifyStart(v8);
  }
  v41 = 0;
  if ( v63 )
  {
    if ( v63 == 1 )
    {
      v41 = 4;
      v42 = (CHangReport *)operator new(0x6180u, (const struct std::nothrow_t *)&std::nothrow);
      v4 = v42;
      v60 = v42;
      if ( v42 )
      {
        CHangReport::CHangReport(v42);
        *(_QWORD *)v4 = &CKernelHangReport::`vftable';
        *((_DWORD *)v4 + 6228) = 0;
        *(_OWORD *)((char *)v4 + 24920) = 0;
        *(_OWORD *)((char *)v4 + 24936) = 0;
        *((_BYTE *)v4 + 24952) = 0;
      }
      else
      {
        v4 = 0;
      }
      v58 = v4;
      if ( !v4 )
      {
        v43 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v44 = 48;
          goto LABEL_134;
        }
        goto LABEL_135;
      }
    }
  }
  else
  {
    if ( (unsigned int)IsBeingDebugged(dwProcessId) )
    {
      v13 = 1;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids, dwProcessId);
      }
      goto LABEL_20;
    }
    v45 = (CUserModeHangReport *)operator new(0xA4E0u, (const struct std::nothrow_t *)&std::nothrow);
    v60 = v45;
    if ( v45 )
      v4 = CUserModeHangReport::CUserModeHangReport(v45);
    else
      v4 = 0;
    v58 = v4;
    if ( !v4 )
    {
      v43 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v44 = 47;
LABEL_134:
        WPP_SF_(*((_QWORD *)v43 + 2), v44, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids);
      }
LABEL_135:
      v13 = -2147024882;
      goto LABEL_20;
    }
    v55 = 1;
  }
  v46 = 4;
  if ( (v67 & 0x10004) != 4 )
    v46 = 0;
  v47 = v41 | ((v67 & 0xFFFF8000) << 16) | v46;
  if ( (v67 & 0x400) != 0
    || (ShellWindow = GetShellWindow(), GetWindowThreadProcessId(ShellWindow, &v54)) && dwProcessId == v54 )
  {
    v47 |= 0x80004u;
  }
  *((_DWORD *)v4 + 22) = TickCount;
  v34 = CHangReport::Create(v4, (struct CProcessInformation *)&v68, v47, (struct SharedHangRepData *)v62, v33);
  v13 = v34;
  if ( v34 < 0 )
  {
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_20;
    }
    v36 = 49;
LABEL_86:
    v37 = (unsigned int)v34;
    goto LABEL_87;
  }
  CurrentProcess = GetCurrentProcess();
  PriorityClass = GetPriorityClass(CurrentProcess);
  if ( PriorityClass )
  {
    if ( PriorityClass == 0x8000 )
    {
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids);
      }
      v51 = GetCurrentProcess();
      if ( !SetPriorityClass(v51, 0x20u) )
      {
        v52 = GetLastError();
        v13 = v52;
        if ( v52 > 0 )
          v13 = (unsigned __int16)v52 | 0x80070000;
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_20;
        }
        v36 = 51;
LABEL_105:
        v37 = v13;
LABEL_87:
        WPP_SF_d(*((_QWORD *)v35 + 2), v36, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids, v37);
        goto LABEL_20;
      }
    }
  }
  else
  {
    v53 = GetLastError();
    if ( v53 > 0 )
      v53 = (unsigned __int16)v53 | 0x80070000;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids,
        (unsigned int)v53);
    }
  }
  v34 = CHangReport::Submit(v4);
  v13 = v34;
  if ( v34 >= 0 )
  {
    v13 = 0;
    goto LABEL_20;
  }
  v35 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v36 = 53;
    goto LABEL_86;
  }
LABEL_20:
  if ( (unsigned __int8)IsXerDumpNotifyStartPresent() && (unsigned __int64)(v8 + 1) > 1 )
    XerDumpNotifyComplete(v8);
  if ( (v13 & 0x80000000) != 0 )
  {
    if ( v4 )
      CHangReport::LogReportError(v4, v13);
    RecordCatastrophicFailure(v13);
  }
  if ( v55 && v4 && g_hrCatastrophicFailure < 0 )
    v13 = g_hrCatastrophicFailure;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids, v13);
  }
  if ( (unsigned __int64)(v8 + 1) > 1 )
    CloseHandle(v8);
  CProcessInformation::~CProcessInformation((CProcessInformation *)&v68);
  if ( v4 )
    (*(void (__fastcall **)(CUserModeHangReport *, __int64))(*(_QWORD *)v4 + 192LL))(v4, 1);
  if ( lpBaseAddress )
    UnmapViewOfFile(lpBaseAddress);
  return v13;
}

```

## disassembly

```asm
0x140019374  push    rbp
0x140019376  push    rbx
0x140019377  push    rsi
0x140019378  push    rdi
0x140019379  push    r12
0x14001937b  push    r13
0x14001937d  push    r14
0x14001937f  push    r15
0x140019381  lea     rbp, [rsp-11C8h]
0x140019389  mov     eax, 12C8h
0x14001938e  call    _alloca_probe
0x140019393  sub     rsp, rax
0x140019396  mov     rax, cs:__security_cookie
0x14001939d  xor     rax, rsp
0x1400193a0  mov     [rbp+1200h+var_50], rax
0x1400193a7  mov     r12, rdx
0x1400193aa  mov     r14d, ecx
0x1400193ad  xor     r15d, r15d
0x1400193b0  mov     [rsp+1300h+var_12CC], r15d
0x1400193b5  mov     [rsp+1300h+lpBaseAddress], r15
0x1400193ba  mov     edi, r15d
0x1400193bd  mov     [rsp+1300h+var_12B8], r15
0x1400193c2  lea     rax, [rbp+1200h+var_438]
0x1400193c9  mov     [rbp+1200h+var_448], rax
0x1400193d0  lea     rax, [rbp+1200h+var_438]
0x1400193d7  mov     [rbp+1200h+var_440], rax
0x1400193de  mov     [rbp+1200h+var_438], r15w
0x1400193e6  lea     rax, [rbp+1200h+var_418]
0x1400193ed  mov     [rbp+1200h+var_428], rax
0x1400193f4  lea     rax, [rbp+1200h+var_418]
0x1400193fb  mov     [rbp+1200h+var_420], rax
0x140019402  mov     [rbp+1200h+var_418], r15w
0x14001940a  lea     rax, [rbp+1200h+var_3F8]
0x140019411  mov     [rbp+1200h+var_408], rax
0x140019418  lea     rax, [rbp+1200h+var_3F8]
0x14001941f  mov     [rbp+1200h+var_400], rax
0x140019426  mov     [rbp+1200h+var_3F8], r15w
0x14001942e  lea     rax, [rbp+1200h+var_3C0]
0x140019435  mov     [rbp+1200h+var_3D0], rax
0x14001943c  lea     rax, [rbp+1200h+var_3C0]
0x140019443  mov     [rbp+1200h+var_3C8], rax
0x14001944a  mov     [rbp+1200h+var_3C0], r15w
0x140019452  mov     [rbp+1200h+var_AF0], r15
0x140019459  mov     [rbp+1200h+var_AE8], r15w
0x140019461  mov     [rbp+1200h+var_8E0], r15w
0x140019469  mov     [rbp+1200h+var_6D8], r15w
0x140019471  mov     [rbp+1200h+var_5D8], r15w
0x140019479  mov     [rbp+1200h+var_554], r15w
0x140019481  mov     [rbp+1200h+var_3E8], r15
0x140019488  mov     [rbp+1200h+var_3E0], r15
0x14001948f  mov     [rbp+1200h+var_3D8], 3
0x140019499  mov     [rbp+1200h+var_3B0], r15
0x1400194a0  mov     [rbp+1200h+var_3A8], r15
0x1400194a7  xor     edx, edx; Val
0x1400194a9  mov     r8d, 108h; Size
0x1400194af  lea     rcx, [rbp+1200h+Buffer]; void *
0x1400194b6  call    memset_0
0x1400194bb  lea     rcx, [rbp+1200h+var_370]
0x1400194c2  lea     rax, [rbp+1200h+Buffer]
0x1400194c9  lea     edx, [r15+2]
0x1400194cd  lea     r8d, [rdx+7Eh]
0x1400194d1  movups  xmm0, xmmword ptr [rax]
0x1400194d4  movups  xmmword ptr [rcx], xmm0
0x1400194d7  movups  xmm1, xmmword ptr [rax+10h]
0x1400194db  movups  xmmword ptr [rcx+10h], xmm1
0x1400194df  movups  xmm0, xmmword ptr [rax+20h]
0x1400194e3  movups  xmmword ptr [rcx+20h], xmm0
0x1400194e7  movups  xmm1, xmmword ptr [rax+30h]
0x1400194eb  movups  xmmword ptr [rcx+30h], xmm1
0x1400194ef  movups  xmm0, xmmword ptr [rax+40h]
0x1400194f3  movups  xmmword ptr [rcx+40h], xmm0
0x1400194f7  movups  xmm1, xmmword ptr [rax+50h]
0x1400194fb  movups  xmmword ptr [rcx+50h], xmm1
0x1400194ff  movups  xmm0, xmmword ptr [rax+60h]
0x140019503  movups  xmmword ptr [rcx+60h], xmm0
0x140019507  movups  xmm1, xmmword ptr [rax+70h]
0x14001950b  movups  xmmword ptr [rcx+70h], xmm1
0x14001950f  add     rcx, r8
0x140019512  add     rax, r8
0x140019515  sub     rdx, 1; Val
0x140019519  jnz     short loc_1400194D1
0x14001951b  mov     rax, [rax]
0x14001951e  mov     [rcx], rax
0x140019521  xorps   xmm2, xmm2
0x140019524  movups  [rsp+1300h+var_12A0], xmm2
0x140019529  movups  [rsp+1300h+var_1290], xmm2
0x14001952e  movups  [rbp+1200h+var_1280], xmm2
0x140019532  movups  xmm0, [rsp+1300h+var_12A0+4]
0x140019537  movups  [rbp+1200h+var_39C], xmm0
0x14001953e  movups  xmm1, [rsp+1300h+var_1290+4]
0x140019543  movups  xmmword ptr [rbp+1200h+var_38C], xmm1
0x14001954a  movups  xmmword ptr [rbp+1200h+var_38C+0Ch], xmm2
0x140019551  mov     [rbp+1200h+var_3A0], 30h ; '0'
0x14001955b  mov     r8d, 778h; Size
0x140019561  lea     rcx, [rbp+1200h+var_1270]; void *
0x140019565  call    memset_0
0x14001956a  mov     [rsp+1300h+var_12D0], r15d
0x14001956f  call    cs:__imp_GetTickCount
0x140019575  mov     [rsp+1300h+var_12C8], eax
0x140019579  mov     r13, r15
0x14001957c  mov     [rsp+1300h+var_12B0], r15
0x140019581  call    ?CheckAttachDebugger@@YAXXZ; CheckAttachDebugger(void)
0x140019586  lea     rcx, aWaitoncorehang; "WaitOnCoreHang"
0x14001958d  call    ?UtilCheckDebugWait@@YAXPEB_W@Z; UtilCheckDebugWait(wchar_t const *)
0x140019592  xor     ecx, ecx; uMode
0x140019594  call    cs:__imp_SetErrorMode
0x14001959a  call    IsImmDisableIMEPresent
0x14001959f  test    al, al
0x1400195a1  jz      short loc_1400195AC
0x1400195a3  or      ecx, 0FFFFFFFFh; DWORD
0x1400195a6  call    cs:__imp_ImmDisableIME
0x1400195ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400195b3  lea     rsi, WPP_GLOBAL_Control
0x1400195ba  test    byte ptr [rcx+1Ch], 4
0x1400195be  jz      short loc_140019625
0x1400195c0  cmp     rcx, rsi
0x1400195c3  jz      short loc_1400195E1
0x1400195c5  mov     edx, 20h ; ' '
0x1400195ca  lea     r8, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids
0x1400195d1  mov     rcx, [rcx+10h]
0x1400195d5  call    WPP_SF_
0x1400195da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400195e1  mov     ebx, r15d
0x1400195e4  test    r14d, r14d
0x1400195e7  jle     short loc_140019625
0x1400195e9  cmp     rcx, rsi
0x1400195ec  jz      short loc_14001961E
0x1400195ee  test    byte ptr [rcx+1Ch], 4
0x1400195f2  jz      short loc_14001961E
0x1400195f4  mov     eax, ebx
0x1400195f6  mov     edx, 21h ; '!'
0x1400195fb  mov     rax, [r12+rax*8]
0x1400195ff  mov     [rsp+1300h+var_12E0], rax
0x140019604  mov     r9d, ebx
0x140019607  lea     r8, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids
0x14001960e  mov     rcx, [rcx+10h]
0x140019612  call    WPP_SF_dS
0x140019617  mov     rcx, cs:WPP_GLOBAL_Control
0x14001961e  inc     ebx
0x140019620  cmp     ebx, r14d
0x140019623  jl      short loc_1400195E9
0x140019625  mov     ebx, 104h
0x14001962a  mov     edx, ebx; uSize
0x14001962c  lea     rcx, [rbp+1200h+Buffer]; lpBuffer
0x140019633  call    cs:__imp_GetSystemDirectoryW
0x140019639  test    eax, eax
0x14001963b  jnz     loc_14001977B
0x140019641  call    cs:__imp_GetLastError
0x140019647  mov     ebx, eax
0x140019649  test    eax, eax
0x14001964b  jle     short loc_14001965D
0x14001964d  movzx   ebx, ax
0x140019650  or      ebx, 80070000h
0x140019656  lea     rsi, WPP_GLOBAL_Control
0x14001965d  mov     rcx, cs:WPP_GLOBAL_Control
0x140019664  cmp     rcx, rsi
0x140019667  jz      short loc_140019687
0x140019669  test    byte ptr [rcx+1Ch], 1
0x14001966d  jz      short loc_140019687
0x14001966f  mov     edx, 22h ; '"'
0x140019674  mov     r9d, ebx
0x140019677  lea     r8, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids
0x14001967e  mov     rcx, [rcx+10h]
0x140019682  call    WPP_SF_d
0x140019687  lea     r14, WPP_GLOBAL_Control
0x14001968e  call    IsXerDumpNotifyStartPresent
0x140019693  xor     esi, esi
0x140019695  test    al, al
0x140019697  jz      short loc_1400196AC
0x140019699  lea     rax, [r13+1]
0x14001969d  cmp     rax, 1
0x1400196a1  jbe     short loc_1400196AC
0x1400196a3  mov     rcx, r13
0x1400196a6  call    cs:__imp_XerDumpNotifyComplete
0x1400196ac  test    ebx, ebx
0x1400196ae  jns     short loc_1400196C6
0x1400196b0  test    rdi, rdi
0x1400196b3  jz      short loc_1400196BF
0x1400196b5  mov     edx, ebx; int
0x1400196b7  mov     rcx, rdi; this
0x1400196ba  call    ?LogReportError@CHangReport@@QEAAXJ@Z; CHangReport::LogReportError(long)
0x1400196bf  mov     ecx, ebx; int
0x1400196c1  call    ?RecordCatastrophicFailure@@YAXJ@Z; RecordCatastrophicFailure(long)
0x1400196c6  cmp     [rsp+1300h+var_12CC], esi
0x1400196ca  jz      short loc_1400196DC
0x1400196cc  test    rdi, rdi
0x1400196cf  jz      short loc_1400196DC
0x1400196d1  mov     eax, cs:?g_hrCatastrophicFailure@@3JA; long g_hrCatastrophicFailure
0x1400196d7  test    eax, eax
0x1400196d9  cmovs   ebx, eax
0x1400196dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400196e3  cmp     rcx, r14
0x1400196e6  jz      short loc_140019707
0x1400196e8  test    byte ptr [rcx+1Ch], 4
0x1400196ec  jz      short loc_140019707
0x1400196ee  mov     edx, 36h ; '6'
0x1400196f3  mov     r9d, ebx
0x1400196f6  lea     r8, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids
0x1400196fd  mov     rcx, [rcx+10h]
0x140019701  call    WPP_SF_d
0x140019706  nop
0x140019707  lea     rax, [r13+1]
0x14001970b  cmp     rax, 1
0x14001970f  jbe     short loc_14001971B
0x140019711  mov     rcx, r13; hObject
0x140019714  call    cs:__imp_CloseHandle
0x14001971a  nop
0x14001971b  lea     rcx, [rbp+1200h+var_AF0]; this
0x140019722  call    ??1CProcessInformation@@QEAA@XZ; CProcessInformation::~CProcessInformation(void)
0x140019727  nop
0x140019728  test    rdi, rdi
0x14001972b  jz      short loc_140019745
0x14001972d  mov     rax, [rdi]
0x140019730  mov     edx, 1
0x140019735  mov     rcx, rdi
0x140019738  mov     rax, [rax+0C0h]
0x14001973f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019744  nop
0x140019745  mov     rcx, [rsp+1300h+lpBaseAddress]; lpBaseAddress
0x14001974a  test    rcx, rcx
0x14001974d  jz      short loc_140019756
0x14001974f  call    cs:__imp_UnmapViewOfFile
0x140019755  nop
0x140019756  mov     eax, ebx
0x140019758  mov     rcx, [rbp+1200h+var_50]
0x14001975f  xor     rcx, rsp; StackCookie
0x140019762  call    __security_check_cookie
0x140019767  add     rsp, 12C8h
0x14001976e  pop     r15
0x140019770  pop     r14
0x140019772  pop     r13
0x140019774  pop     r12
0x140019776  pop     rdi
0x140019777  pop     rsi
0x140019778  pop     rbx
0x140019779  pop     rbp
0x14001977a  retn
0x14001977b  cmp     eax, ebx
0x14001977d  jbe     short loc_1400197B8
0x14001977f  mov     ebx, 8007007Ah
0x140019784  mov     rcx, cs:WPP_GLOBAL_Control
0x14001978b  cmp     rcx, rsi
0x14001978e  jz      loc_140019687
0x140019794  test    byte ptr [rcx+1Ch], 1
0x140019798  jz      loc_140019687
0x14001979e  mov     edx, 23h ; '#'
0x1400197a3  lea     r8, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids
0x1400197aa  mov     rcx, [rcx+10h]
0x1400197ae  call    WPP_SF_
0x1400197b3  jmp     loc_140019687
0x1400197b8  lea     rdx, [rbp+1200h+Buffer]; lpValue
0x1400197bf  lea     rcx, Name; "PATH"
0x1400197c6  call    cs:__imp_SetEnvironmentVariableW
0x1400197cc  test    eax, eax
0x1400197ce  jnz     short loc_140019810
0x1400197d0  call    cs:__imp_GetLastError
0x1400197d6  mov     ebx, eax
0x1400197d8  test    eax, eax
0x1400197da  jle     short loc_1400197EC
0x1400197dc  movzx   ebx, ax
0x1400197df  or      ebx, 80070000h
0x1400197e5  lea     rsi, WPP_GLOBAL_Control
0x1400197ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400197f3  cmp     rcx, rsi
0x1400197f6  jz      loc_140019687
0x1400197fc  test    byte ptr [rcx+1Ch], 1
0x140019800  jz      loc_140019687
0x140019806  mov     edx, 24h ; '$'
0x14001980b  jmp     loc_140019674
0x140019810  xor     edx, edx; lpValue
0x140019812  lea     rcx, aNtSymbolPath; "_NT_SYMBOL_PATH"
0x140019819  call    cs:__imp_SetEnvironmentVariableW
0x14001981f  xor     edx, edx; lpValue
0x140019821  lea     rcx, aNtAltSymbolPat; "_NT_ALT_SYMBOL_PATH"
0x140019828  call    cs:__imp_SetEnvironmentVariableW
0x14001982e  xor     edx, edx; lpValue
0x140019830  lea     rcx, aNtExecutableIm; "_NT_EXECUTABLE_IMAGE_PATH"
0x140019837  call    cs:__imp_SetEnvironmentVariableW
0x14001983d  xor     edx, edx; lpValue
0x14001983f  lea     rcx, aNtDebuggerExte; "_NT_DEBUGGER_EXTENSION_PATH"
0x140019846  call    cs:__imp_SetEnvironmentVariableW
0x14001984c  xor     edx, edx; lpValue
0x14001984e  lea     rcx, aNtSourcePath; "_NT_SOURCE_PATH"
0x140019855  call    cs:__imp_SetEnvironmentVariableW
0x14001985b  xor     edx, edx; lpValue
0x14001985d  lea     rcx, aNtDebugLogFile; "_NT_DEBUG_LOG_FILE_OPEN"
0x140019864  call    cs:__imp_SetEnvironmentVariableW
0x14001986a  xor     edx, edx; lpValue
0x14001986c  lea     rcx, aNtDebugLogFile_0; "_NT_DEBUG_LOG_FILE_APPEND"
0x140019873  call    cs:__imp_SetEnvironmentVariableW
0x140019879  call    ?IsHangReportingDisabled@CConfig@@QEAAHXZ; CConfig::IsHangReportingDisabled(void)
0x14001987e  test    eax, eax
0x140019880  jz      short loc_1400198B8
0x140019882  mov     ebx, 1
0x140019887  mov     r8d, ebx
0x14001988a  lea     rdx, aHangs; "Hangs"
0x140019891  call    ?UtilFireWerVerticalDisabledEvent@@YAXQEBU_tlgProvider_t@@PEB_WW4_VERTICAL_DISABLED_REASON@@@Z; UtilFireWerVerticalDisabledEvent(_tlgProvider_t const * const,wchar_t const *,_VERTICAL_DISABLED_REASON)
0x140019896  mov     rcx, cs:WPP_GLOBAL_Control
0x14001989d  cmp     rcx, rsi
0x1400198a0  jz      loc_140019687
  ... truncated ...
```
