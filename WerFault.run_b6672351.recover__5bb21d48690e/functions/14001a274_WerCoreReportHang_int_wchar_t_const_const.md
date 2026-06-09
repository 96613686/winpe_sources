# WerCoreReportHang(int,wchar_t const * * const)

- ea: `0x14001a274`
- end: `0x14001aed9`
- name: `?WerCoreReportHang@@YAHHQEAPEB_W@Z`
- size: `3173`
- prototype: `__int64 __fastcall(int, const wchar_t **const)`
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000ddb8`

## callees

- `0x140002490`
- `0x1400024b4`
- `0x1400030f8`
- `0x140003b64`
- `0x140003d34`
- `0x140003e80`
- `0x14000bee0`
- `0x140014ee4`
- `0x140014f14`
- `0x140015014`
- `0x14001991c`
- `0x140019b6c`
- `0x140019c70`
- `0x140019e58`
- `0x140019f3c`
- `0x14001a274`
- `0x14001aee0`
- `0x14001b0d0`
- `0x14001cf1c`
- `0x14001e4a0`
- `0x14001f2dc`
- `0x140020870`
- `0x1400210a8`
- `0x140023a64`
- `0x140032600`
- `0x14005f510`
- `0x14005f588`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001a821`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001a821`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x14001a49a`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x14001a49a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a83e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001aae1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001adda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ae15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a83e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001aae1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001adda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001ae15`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14001a6f7`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14001a756`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14001a76b`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14001a780`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14001a795`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14001a7aa`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14001a7bf`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14001a7d4`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14001a6f7`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14001a756`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14001a76b`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14001a780`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14001a795`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14001a7aa`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14001a7bf`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14001a7d4`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x14001adc6`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x14001adc6`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x14001ad65`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x14001ad65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001ad56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001adb2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001ad56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14001adb2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a638`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a638`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14001a545`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14001a545`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001a46f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14001a46f`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14001a679`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14001a9c3`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14001a679`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x14001a9c3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001aac4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14001aac4`
- `ext-ms-win-ntuser-window-l1-1-0!GetShellWindow` at `0x14001accd`
- `ext-ms-win-ntuser-window-l1-1-0!GetShellWindow` at `0x14001accd`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x14001ace1`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x14001ace1`
- `ext-ms-win-wer-xbox-l1-1-1!XerDumpNotifyComplete` at `0x14001a5c4`
- `ext-ms-win-wer-xbox-l1-1-1!XerDumpNotifyComplete` at `0x14001a5c4`
- `ext-ms-win-wer-xbox-l1-1-1!XerDumpNotifyStart` at `0x14001ab23`
- `ext-ms-win-wer-xbox-l1-1-1!XerDumpNotifyStart` at `0x14001ab23`
- `ext-ms-win-wer-ui-l1-1-1!WerUIpCheckWindow` at `0x14001aa17`
- `ext-ms-win-wer-ui-l1-1-1!WerUIpCheckWindow` at `0x14001aa17`
- `ext-ms-win-imm-l1-1-0!ImmDisableIME` at `0x14001a4b2`
- `ext-ms-win-imm-l1-1-0!ImmDisableIME` at `0x14001a4b2`

## string_xrefs

- `0x14001a74f`: `_NT_SYMBOL_PATH`
- `0x14001a764`: `_NT_ALT_SYMBOL_PATH`
- `0x14001a779`: `_NT_EXECUTABLE_IMAGE_PATH`
- `0x14001a78e`: `_NT_DEBUGGER_EXTENSION_PATH`
- `0x14001a7a3`: `_NT_SOURCE_PATH`
- `0x14001a7b8`: `_NT_DEBUG_LOG_FILE_OPEN`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
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
  int v13; // ebx
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
  LPCVOID lpBaseAddress; // [rsp+40h] [rbp-C0h]
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
    WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids, (unsigned int)v13);
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
  v34 = OpenSharedMemory(v33);
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
  if ( v13 < 0 )
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
        v37 = (unsigned int)v13;
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
  if ( v13 < 0 )
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
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      54,
      WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids,
      (unsigned int)v13);
  }
  if ( (unsigned __int64)(v8 + 1) > 1 )
    CloseHandle(v8);
  CProcessInformation::~CProcessInformation((CProcessInformation *)&v68);
  if ( v4 )
    (*(void (__fastcall **)(CUserModeHangReport *, __int64))(*(_QWORD *)v4 + 192LL))(v4, 1);
  if ( lpBaseAddress )
    UnmapViewOfFile(lpBaseAddress);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14001a274  push    rbp
0x14001a276  push    rbx
0x14001a277  push    rsi
0x14001a278  push    rdi
0x14001a279  push    r12
0x14001a27b  push    r13
0x14001a27d  push    r14
0x14001a27f  push    r15
0x14001a281  lea     rbp, [rsp-11C8h]
0x14001a289  mov     eax, 12C8h
0x14001a28e  call    _alloca_probe
0x14001a293  sub     rsp, rax
0x14001a296  mov     rax, cs:__security_cookie
0x14001a29d  xor     rax, rsp
0x14001a2a0  mov     [rbp+1200h+var_50], rax
0x14001a2a7  mov     r12, rdx
0x14001a2aa  mov     r14d, ecx
0x14001a2ad  xor     r15d, r15d
0x14001a2b0  mov     [rsp+1300h+var_12CC], r15d
0x14001a2b5  mov     [rsp+1300h+lpBaseAddress], r15
0x14001a2ba  mov     edi, r15d
0x14001a2bd  mov     [rsp+1300h+var_12B8], r15
0x14001a2c2  lea     rax, [rbp+1200h+var_438]
0x14001a2c9  mov     [rbp+1200h+var_448], rax
0x14001a2d0  lea     rax, [rbp+1200h+var_438]
0x14001a2d7  mov     [rbp+1200h+var_440], rax
0x14001a2de  mov     [rbp+1200h+var_438], r15w
0x14001a2e6  lea     rax, [rbp+1200h+var_418]
0x14001a2ed  mov     [rbp+1200h+var_428], rax
0x14001a2f4  lea     rax, [rbp+1200h+var_418]
0x14001a2fb  mov     [rbp+1200h+var_420], rax
0x14001a302  mov     [rbp+1200h+var_418], r15w
0x14001a30a  lea     rax, [rbp+1200h+var_3F8]
0x14001a311  mov     [rbp+1200h+var_408], rax
0x14001a318  lea     rax, [rbp+1200h+var_3F8]
0x14001a31f  mov     [rbp+1200h+var_400], rax
0x14001a326  mov     [rbp+1200h+var_3F8], r15w
0x14001a32e  lea     rax, [rbp+1200h+var_3C0]
0x14001a335  mov     [rbp+1200h+var_3D0], rax
0x14001a33c  lea     rax, [rbp+1200h+var_3C0]
0x14001a343  mov     [rbp+1200h+var_3C8], rax
0x14001a34a  mov     [rbp+1200h+var_3C0], r15w
0x14001a352  mov     [rbp+1200h+var_AF0], r15
0x14001a359  mov     [rbp+1200h+var_AE8], r15w
0x14001a361  mov     [rbp+1200h+var_8E0], r15w
0x14001a369  mov     [rbp+1200h+var_6D8], r15w
0x14001a371  mov     [rbp+1200h+var_5D8], r15w
0x14001a379  mov     [rbp+1200h+var_554], r15w
0x14001a381  mov     [rbp+1200h+var_3E8], r15
0x14001a388  mov     [rbp+1200h+var_3E0], r15
0x14001a38f  mov     [rbp+1200h+var_3D8], 3
0x14001a399  mov     [rbp+1200h+var_3B0], r15
0x14001a3a0  mov     [rbp+1200h+var_3A8], r15
0x14001a3a7  xor     edx, edx; Val
0x14001a3a9  mov     r8d, 108h; Size
0x14001a3af  lea     rcx, [rbp+1200h+Buffer]; void *
0x14001a3b6  call    memset_0
0x14001a3bb  lea     rcx, [rbp+1200h+var_370]
0x14001a3c2  lea     rax, [rbp+1200h+Buffer]
0x14001a3c9  lea     edx, [r15+2]
0x14001a3cd  lea     r8d, [rdx+7Eh]
0x14001a3d1  movups  xmm0, xmmword ptr [rax]
0x14001a3d4  movups  xmmword ptr [rcx], xmm0
0x14001a3d7  movups  xmm1, xmmword ptr [rax+10h]
0x14001a3db  movups  xmmword ptr [rcx+10h], xmm1
0x14001a3df  movups  xmm0, xmmword ptr [rax+20h]
0x14001a3e3  movups  xmmword ptr [rcx+20h], xmm0
0x14001a3e7  movups  xmm1, xmmword ptr [rax+30h]
0x14001a3eb  movups  xmmword ptr [rcx+30h], xmm1
0x14001a3ef  movups  xmm0, xmmword ptr [rax+40h]
0x14001a3f3  movups  xmmword ptr [rcx+40h], xmm0
0x14001a3f7  movups  xmm1, xmmword ptr [rax+50h]
0x14001a3fb  movups  xmmword ptr [rcx+50h], xmm1
0x14001a3ff  movups  xmm0, xmmword ptr [rax+60h]
0x14001a403  movups  xmmword ptr [rcx+60h], xmm0
0x14001a407  movups  xmm1, xmmword ptr [rax+70h]
0x14001a40b  movups  xmmword ptr [rcx+70h], xmm1
0x14001a40f  add     rcx, r8
0x14001a412  add     rax, r8
0x14001a415  sub     rdx, 1; Val
0x14001a419  jnz     short loc_14001A3D1
0x14001a41b  mov     rax, [rax]
0x14001a41e  mov     [rcx], rax
0x14001a421  xorps   xmm2, xmm2
0x14001a424  movups  [rsp+1300h+var_12A0], xmm2
0x14001a429  movups  [rsp+1300h+var_1290], xmm2
0x14001a42e  movups  [rbp+1200h+var_1280], xmm2
0x14001a432  movups  xmm0, [rsp+1300h+var_12A0+4]
0x14001a437  movups  [rbp+1200h+var_39C], xmm0
0x14001a43e  movups  xmm1, [rsp+1300h+var_1290+4]
0x14001a443  movups  xmmword ptr [rbp+1200h+var_38C], xmm1
0x14001a44a  movups  xmmword ptr [rbp+1200h+var_38C+0Ch], xmm2
0x14001a451  mov     [rbp+1200h+var_3A0], 30h ; '0'
0x14001a45b  mov     r8d, 778h; Size
0x14001a461  lea     rcx, [rbp+1200h+var_1270]; void *
0x14001a465  call    memset_0
0x14001a46a  mov     [rsp+1300h+var_12D0], r15d
0x14001a46f  call    cs:__imp_GetTickCount
0x14001a476  nop     dword ptr [rax+rax+00h]
0x14001a47b  mov     [rsp+1300h+var_12C8], eax
0x14001a47f  mov     r13, r15
0x14001a482  mov     [rsp+1300h+var_12B0], r15
0x14001a487  call    ?CheckAttachDebugger@@YAXXZ; CheckAttachDebugger(void)
0x14001a48c  lea     rcx, aWaitoncorehang; "WaitOnCoreHang"
0x14001a493  call    ?UtilCheckDebugWait@@YAXPEB_W@Z; UtilCheckDebugWait(wchar_t const *)
0x14001a498  xor     ecx, ecx; uMode
0x14001a49a  call    cs:__imp_SetErrorMode
0x14001a4a1  nop     dword ptr [rax+rax+00h]
0x14001a4a6  call    IsImmDisableIMEPresent
0x14001a4ab  test    al, al
0x14001a4ad  jz      short loc_14001A4BE
0x14001a4af  or      ecx, 0FFFFFFFFh; DWORD
0x14001a4b2  call    cs:__imp_ImmDisableIME
0x14001a4b9  nop     dword ptr [rax+rax+00h]
0x14001a4be  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a4c5  lea     rsi, WPP_GLOBAL_Control
0x14001a4cc  test    byte ptr [rcx+1Ch], 4
0x14001a4d0  jz      short loc_14001A537
0x14001a4d2  cmp     rcx, rsi
0x14001a4d5  jz      short loc_14001A4F3
0x14001a4d7  mov     edx, 20h ; ' '
0x14001a4dc  lea     r8, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids
0x14001a4e3  mov     rcx, [rcx+10h]
0x14001a4e7  call    WPP_SF_
0x14001a4ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a4f3  mov     ebx, r15d
0x14001a4f6  test    r14d, r14d
0x14001a4f9  jle     short loc_14001A537
0x14001a4fb  cmp     rcx, rsi
0x14001a4fe  jz      short loc_14001A530
0x14001a500  test    byte ptr [rcx+1Ch], 4
0x14001a504  jz      short loc_14001A530
0x14001a506  mov     eax, ebx
0x14001a508  mov     edx, 21h ; '!'
0x14001a50d  mov     rax, [r12+rax*8]
0x14001a511  mov     [rsp+1300h+var_12E0], rax
0x14001a516  mov     r9d, ebx
0x14001a519  lea     r8, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids
0x14001a520  mov     rcx, [rcx+10h]
0x14001a524  call    WPP_SF_dS
0x14001a529  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a530  inc     ebx
0x14001a532  cmp     ebx, r14d
0x14001a535  jl      short loc_14001A4FB
0x14001a537  mov     ebx, 104h
0x14001a53c  mov     edx, ebx; uSize
0x14001a53e  lea     rcx, [rbp+1200h+Buffer]; lpBuffer
0x14001a545  call    cs:__imp_GetSystemDirectoryW
0x14001a54c  nop     dword ptr [rax+rax+00h]
0x14001a551  test    eax, eax
0x14001a553  jnz     loc_14001A6AC
0x14001a559  call    cs:__imp_GetLastError
0x14001a560  nop     dword ptr [rax+rax+00h]
0x14001a565  mov     ebx, eax
0x14001a567  test    eax, eax
0x14001a569  jle     short loc_14001A57B
0x14001a56b  movzx   ebx, ax
0x14001a56e  or      ebx, 80070000h
0x14001a574  lea     rsi, WPP_GLOBAL_Control
0x14001a57b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a582  cmp     rcx, rsi
0x14001a585  jz      short loc_14001A5A5
0x14001a587  test    byte ptr [rcx+1Ch], 1
0x14001a58b  jz      short loc_14001A5A5
0x14001a58d  mov     edx, 22h ; '"'
0x14001a592  mov     r9d, ebx
0x14001a595  lea     r8, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids
0x14001a59c  mov     rcx, [rcx+10h]
0x14001a5a0  call    WPP_SF_d
0x14001a5a5  lea     r14, WPP_GLOBAL_Control
0x14001a5ac  call    IsXerDumpNotifyStartPresent
0x14001a5b1  xor     esi, esi
0x14001a5b3  test    al, al
0x14001a5b5  jz      short loc_14001A5D0
0x14001a5b7  lea     rax, [r13+1]
0x14001a5bb  cmp     rax, 1
0x14001a5bf  jbe     short loc_14001A5D0
0x14001a5c1  mov     rcx, r13
0x14001a5c4  call    cs:__imp_XerDumpNotifyComplete
0x14001a5cb  nop     dword ptr [rax+rax+00h]
0x14001a5d0  test    ebx, ebx
0x14001a5d2  jns     short loc_14001A5EA
0x14001a5d4  test    rdi, rdi
0x14001a5d7  jz      short loc_14001A5E3
0x14001a5d9  mov     edx, ebx; int
0x14001a5db  mov     rcx, rdi; this
0x14001a5de  call    ?LogReportError@CHangReport@@QEAAXJ@Z; CHangReport::LogReportError(long)
0x14001a5e3  mov     ecx, ebx; int
0x14001a5e5  call    ?RecordCatastrophicFailure@@YAXJ@Z; RecordCatastrophicFailure(long)
0x14001a5ea  cmp     [rsp+1300h+var_12CC], esi
0x14001a5ee  jz      short loc_14001A600
0x14001a5f0  test    rdi, rdi
0x14001a5f3  jz      short loc_14001A600
0x14001a5f5  mov     eax, cs:?g_hrCatastrophicFailure@@3JA; long g_hrCatastrophicFailure
0x14001a5fb  test    eax, eax
0x14001a5fd  cmovs   ebx, eax
0x14001a600  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a607  cmp     rcx, r14
0x14001a60a  jz      short loc_14001A62B
0x14001a60c  test    byte ptr [rcx+1Ch], 4
0x14001a610  jz      short loc_14001A62B
0x14001a612  mov     edx, 36h ; '6'
0x14001a617  mov     r9d, ebx
0x14001a61a  lea     r8, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids
0x14001a621  mov     rcx, [rcx+10h]
0x14001a625  call    WPP_SF_d
0x14001a62a  nop
0x14001a62b  lea     rax, [r13+1]
0x14001a62f  cmp     rax, 1
0x14001a633  jbe     short loc_14001A645
0x14001a635  mov     rcx, r13; hObject
0x14001a638  call    cs:__imp_CloseHandle
0x14001a63f  nop     dword ptr [rax+rax+00h]
0x14001a644  nop
0x14001a645  lea     rcx, [rbp+1200h+var_AF0]; this
0x14001a64c  call    ??1CProcessInformation@@QEAA@XZ; CProcessInformation::~CProcessInformation(void)
0x14001a651  nop
0x14001a652  test    rdi, rdi
0x14001a655  jz      short loc_14001A66F
0x14001a657  mov     rax, [rdi]
0x14001a65a  mov     edx, 1
0x14001a65f  mov     rcx, rdi
0x14001a662  mov     rax, [rax+0C0h]
0x14001a669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a66e  nop
0x14001a66f  mov     rcx, [rsp+1300h+lpBaseAddress]; lpBaseAddress
0x14001a674  test    rcx, rcx
0x14001a677  jz      short loc_14001A686
0x14001a679  call    cs:__imp_UnmapViewOfFile
0x14001a680  nop     dword ptr [rax+rax+00h]
0x14001a685  nop
0x14001a686  mov     eax, ebx
0x14001a688  mov     rcx, [rbp+1200h+var_50]
0x14001a68f  xor     rcx, rsp; StackCookie
0x14001a692  call    __security_check_cookie
0x14001a697  add     rsp, 12C8h
0x14001a69e  pop     r15
0x14001a6a0  pop     r14
0x14001a6a2  pop     r13
0x14001a6a4  pop     r12
0x14001a6a6  pop     rdi
0x14001a6a7  pop     rsi
0x14001a6a8  pop     rbx
0x14001a6a9  pop     rbp
0x14001a6aa  retn
0x14001a6ac  cmp     eax, ebx
0x14001a6ae  jbe     short loc_14001A6E9
0x14001a6b0  mov     ebx, 8007007Ah
0x14001a6b5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a6bc  cmp     rcx, rsi
0x14001a6bf  jz      loc_14001A5A5
0x14001a6c5  test    byte ptr [rcx+1Ch], 1
0x14001a6c9  jz      loc_14001A5A5
0x14001a6cf  mov     edx, 23h ; '#'
0x14001a6d4  lea     r8, WPP_35a6bf14758d33cd61dd1b0f627037ef_Traceguids
0x14001a6db  mov     rcx, [rcx+10h]
0x14001a6df  call    WPP_SF_
0x14001a6e4  jmp     loc_14001A5A5
0x14001a6e9  lea     rdx, [rbp+1200h+Buffer]; lpValue
0x14001a6f0  lea     rcx, Name; "PATH"
0x14001a6f7  call    cs:__imp_SetEnvironmentVariableW
0x14001a6fe  nop     dword ptr [rax+rax+00h]
0x14001a703  test    eax, eax
0x14001a705  jnz     short loc_14001A74D
0x14001a707  call    cs:__imp_GetLastError
0x14001a70e  nop     dword ptr [rax+rax+00h]
0x14001a713  mov     ebx, eax
0x14001a715  test    eax, eax
0x14001a717  jle     short loc_14001A729
0x14001a719  movzx   ebx, ax
0x14001a71c  or      ebx, 80070000h
0x14001a722  lea     rsi, WPP_GLOBAL_Control
0x14001a729  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a730  cmp     rcx, rsi
0x14001a733  jz      loc_14001A5A5
0x14001a739  test    byte ptr [rcx+1Ch], 1
0x14001a73d  jz      loc_14001A5A5
0x14001a743  mov     edx, 24h ; '$'
0x14001a748  jmp     loc_14001A592
0x14001a74d  xor     edx, edx; lpValue
0x14001a74f  lea     rcx, aNtSymbolPath; "_NT_SYMBOL_PATH"
0x14001a756  call    cs:__imp_SetEnvironmentVariableW
0x14001a75d  nop     dword ptr [rax+rax+00h]
0x14001a762  xor     edx, edx; lpValue
0x14001a764  lea     rcx, aNtAltSymbolPat; "_NT_ALT_SYMBOL_PATH"
0x14001a76b  call    cs:__imp_SetEnvironmentVariableW
0x14001a772  nop     dword ptr [rax+rax+00h]
0x14001a777  xor     edx, edx; lpValue
0x14001a779  lea     rcx, aNtExecutableIm; "_NT_EXECUTABLE_IMAGE_PATH"
0x14001a780  call    cs:__imp_SetEnvironmentVariableW
0x14001a787  nop     dword ptr [rax+rax+00h]
0x14001a78c  xor     edx, edx; lpValue
0x14001a78e  lea     rcx, aNtDebuggerExte; "_NT_DEBUGGER_EXTENSION_PATH"
0x14001a795  call    cs:__imp_SetEnvironmentVariableW
0x14001a79c  nop     dword ptr [rax+rax+00h]
0x14001a7a1  xor     edx, edx; lpValue
0x14001a7a3  lea     rcx, aNtSourcePath; "_NT_SOURCE_PATH"
0x14001a7aa  call    cs:__imp_SetEnvironmentVariableW
0x14001a7b1  nop     dword ptr [rax+rax+00h]
0x14001a7b6  xor     edx, edx; lpValue
  ... truncated ...
```
