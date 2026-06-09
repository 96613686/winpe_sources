# PerfRegQueryValueEx(HKEY__ *,_UNICODE_STRING const *,_UNICODE_STRING const *,ulong *,ulong *,uchar *,ulong *,ulong *)

- ea: `0x1800288a0`
- end: `0x1800296c4`
- name: `?PerfRegQueryValueEx@@YAJPEAUHKEY__@@PEBU_UNICODE_STRING@@1PEAK2PEAE22@Z`
- size: `3620`
- prototype: `__int64 __fastcall(HKEY, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, unsigned int *, unsigned int *, unsigned __int8 *, unsigned int *, unsigned int *)`
- caller_count: `4`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800283b4`
- `0x1800284b0`
- `0x180028850`
- `0x1800573e0`

## callees

- `0x180014430`
- `0x180017100`
- `0x1800257d0`
- `0x180026a7c`
- `0x180027230`
- `0x1800288a0`
- `0x18002bbd8`
- `0x18002cde0`
- `0x180038490`
- `0x180039e5c`
- `0x18003b57c`
- `0x18003b748`
- `0x180056c00`
- `0x18006504e`
- `0x180065090`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x180028aa7`
- `ntdll!NtSetInformationThread` at `0x180029666`
- `ntdll!NtSetInformationThread` at `0x180028aa7`
- `ntdll!NtSetInformationThread` at `0x180029666`
- `ntdll!NtWaitForSingleObject` at `0x180028b4f`
- `ntdll!NtWaitForSingleObject` at `0x180029286`
- `ntdll!NtWaitForSingleObject` at `0x180028b4f`
- `ntdll!NtWaitForSingleObject` at `0x180029286`
- `ntdll!NtQueryInformationThread` at `0x180028a6c`
- `ntdll!NtQueryInformationThread` at `0x180028a6c`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18002893d`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18002893d`
- `ntdll!NtQueryPerformanceCounter` at `0x1800293b7`
- `ntdll!NtQueryPerformanceCounter` at `0x1800293b7`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180028c27`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180028c77`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180028c27`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x180028c77`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028a2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028a2e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028a41`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028a41`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800293c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800293c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800293a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800293a9`
- `KERNEL32!LocalFree` at `0x180028c89`
- `KERNEL32!LocalFree` at `0x1800291d3`
- `KERNEL32!LocalFree` at `0x180028c89`
- `KERNEL32!LocalFree` at `0x1800291d3`
- `KERNEL32!ReleaseMutex` at `0x180029228`
- `KERNEL32!ReleaseMutex` at `0x18002946a`
- `KERNEL32!ReleaseMutex` at `0x180029228`
- `KERNEL32!ReleaseMutex` at `0x18002946a`
- `KERNEL32!GetModuleFileNameW` at `0x180029552`
- `KERNEL32!GetModuleFileNameW` at `0x180029552`
- `SspiCli!GetUserNameExW` at `0x180029534`
- `SspiCli!GetUserNameExW` at `0x180029534`

## pseudocode

```c
__int64 __fastcall PerfRegQueryValueEx(
        HKEY a1,
        const struct _UNICODE_STRING *a2,
        const struct _UNICODE_STRING *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned __int8 *a6,
        unsigned int *a7,
        unsigned int *a8)
{
  unsigned int *v8; // rbx
  _QWORD *v11; // rcx
  __int64 v12; // r13
  wchar_t *Buffer; // rcx
  unsigned int QueryType; // eax
  int v15; // edi
  unsigned int ExtensibleData; // r15d
  _WORD *v17; // r15
  NTSTATUS InformationThread; // eax
  NTSTATUS v19; // eax
  unsigned int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r9
  _QWORD *v23; // rcx
  int Names; // edi
  int ThreadPreferredUILanguages; // eax
  HKEY v26; // rax
  __int64 v27; // rax
  bool v28; // zf
  const unsigned __int16 *v29; // rcx
  const unsigned __int16 *v30; // rdx
  __int64 v31; // rax
  unsigned __int16 LangIdFromSzLang; // si
  char v33; // cl
  unsigned __int16 v34; // ax
  unsigned __int16 v35; // cx
  char v36; // al
  char v37; // al
  unsigned __int16 v38; // cx
  char v39; // al
  unsigned __int16 v40; // si
  unsigned __int16 v41; // cx
  char v42; // dl
  char v43; // al
  unsigned __int16 v44; // si
  const unsigned __int16 *v45; // rax
  _WORD *v46; // rsi
  int v47; // ebx
  __int64 v48; // rdx
  __int64 i; // r8
  int v50; // ecx
  int v51; // ebx
  int v52; // ebx
  char v53; // al
  char v54; // al
  unsigned __int16 v55; // cx
  char v56; // al
  unsigned __int16 v57; // cx
  char v58; // al
  unsigned int *v59; // rax
  int v60; // eax
  unsigned __int16 v61; // bx
  unsigned __int16 v62; // cx
  char v63; // al
  unsigned __int16 v64; // bx
  char v65; // al
  char v66; // al
  int v67; // eax
  __int64 v68; // rax
  unsigned int v69; // eax
  unsigned int v70; // esi
  _QWORD *v71; // rcx
  HLOCAL v72; // rdx
  int v73; // eax
  int v74; // r8d
  __int64 v75; // rax
  unsigned int v77; // [rsp+40h] [rbp-C0h]
  unsigned int v78; // [rsp+44h] [rbp-BCh]
  int v79; // [rsp+4Ch] [rbp-B4h] BYREF
  int v80; // [rsp+50h] [rbp-B0h] BYREF
  int v81; // [rsp+54h] [rbp-ACh] BYREF
  ULONG nSize; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int8 *v83; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING v85; // [rsp+70h] [rbp-90h] BYREF
  unsigned int *v86; // [rsp+80h] [rbp-80h]
  LARGE_INTEGER Timeout; // [rsp+88h] [rbp-78h] BYREF
  unsigned int *v88; // [rsp+90h] [rbp-70h]
  _OWORD ThreadInformation[2]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v90; // [rsp+B8h] [rbp-48h]
  __int64 v91; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v92; // [rsp+D0h] [rbp-30h]
  __int128 v93; // [rsp+E0h] [rbp-20h]
  __int64 v94; // [rsp+F0h] [rbp-10h]
  __int64 v95; // [rsp+F8h] [rbp-8h]
  WCHAR NameBuffer[128]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR Filename[264]; // [rsp+200h] [rbp+100h] BYREF

  v8 = a7;
  v88 = a5;
  v86 = a7;
  v83 = 0;
  *(_QWORD *)&v85.Length = 0;
  v85.Buffer = 0;
  Timeout.QuadPart = 0;
  memset(ThreadInformation, 0, sizeof(ThreadInformation));
  v81 = 0;
  v80 = 0;
  v90 = 0;
  RtlRunOnceExecuteOnce(qword_1800A3088, PerfpInitializeCallback, 0, 0);
  v11 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids, a3);
    v11 = WPP_GLOBAL_Control;
  }
  v83 = 0;
  v12 = -1;
  v80 = -1;
  v81 = -1;
  if ( !a3 || !a3->Buffer )
  {
    ExtensibleData = 87;
    goto LABEL_199;
  }
  Buffer = a3->Buffer;
  v85 = *a3;
  QueryType = GetQueryType(Buffer);
  v78 = QueryType;
  v15 = (unsigned __int16)QueryType;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids,
      (unsigned __int16)QueryType);
  ExtensibleData = PerfOpenKey((__int64)a1, (unsigned __int16)(v15 - 5) <= 3u);
  if ( ExtensibleData )
    goto LABEL_182;
  v17 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib",
          0,
          0x20019u,
          &hKey) )
  {
    RegCloseKey(hKey);
    if ( !dwBoostPriority )
      goto LABEL_23;
    InformationThread = NtQueryInformationThread(
                          (HANDLE)0xFFFFFFFFFFFFFFFELL,
                          ThreadBasicInformation,
                          ThreadInformation,
                          0x30u,
                          0);
    if ( InformationThread < 0 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids,
          (unsigned int)InformationThread);
      v80 = 15;
    }
    else
    {
      v81 = DWORD2(v90);
      v80 = 15;
      if ( (unsigned int)(DWORD2(v90) - 1) <= 0xD )
      {
        v19 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPriority, &v80, 4u);
        if ( v19 >= 0 )
          goto LABEL_23;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids,
            (unsigned int)v19);
      }
    }
    v81 = -1;
LABEL_23:
    v77 = 0;
    if ( a8 )
      *a8 = 0;
    if ( a7 )
      v77 = *a7;
    Timeout.QuadPart = -20000000;
    if ( (unsigned __int16)(v15 - 5) <= 3u )
    {
      v20 = NtWaitForSingleObject(hGlobalDataMutex, 0, &Timeout);
      if ( v20 )
      {
        ExtensibleData = 170;
        v11 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v21 = 23;
          v22 = v20;
LABEL_197:
          WPP_SF_d(v11[2], v21, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids, v22);
          v11 = WPP_GLOBAL_Control;
          goto LABEL_199;
        }
        goto LABEL_199;
      }
      v23 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids);
        v23 = WPP_GLOBAL_Control;
      }
      if ( a1 == HKEY_PERFORMANCE_DATA )
      {
        Names = PerfGetNames(v78, &stru_180067610, &v85, a6, a7, a8, 0);
LABEL_137:
        if ( Names >= 0 )
        {
LABEL_142:
          ExtensibleData = PerfpDosError(Names);
          if ( v88 )
            *v88 = 7;
          ReleaseMutex(hGlobalDataMutex);
          v11 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids);
            v11 = WPP_GLOBAL_Control;
          }
          goto LABEL_199;
        }
        v23 = WPP_GLOBAL_Control;
LABEL_139:
        if ( (*((_BYTE *)v23 + 28) & 2) != 0 && *((_BYTE *)v23 + 25) >= 2u )
          WPP_SF_d(v23[2], 25, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids, (unsigned int)Names);
        goto LABEL_142;
      }
      if ( ((unsigned __int64)(a1 + 536870892) & 0xFFFFFFFFFFFFFFEFuLL) != 0 )
      {
        Names = -1073741811;
        goto LABEL_139;
      }
      hKey = 0;
      nSize = 0;
      v79 = 0;
      ThreadPreferredUILanguages = RtlGetThreadPreferredUILanguages(36, &v79, 0, &nSize);
      Names = ThreadPreferredUILanguages;
      if ( (!ThreadPreferredUILanguages || ThreadPreferredUILanguages == -1073741789) && nSize )
      {
        v26 = (HKEY)operator new(saturated_mul(nSize, 2u));
        hKey = v26;
        v17 = v26;
        if ( v26 )
        {
          Names = RtlGetThreadPreferredUILanguages(36, &v79, v26, &nSize);
          if ( !v79 )
          {
            LocalFree(v17);
            v17 = 0;
            hKey = 0;
          }
        }
        else
        {
          v79 = 0;
          Names = -1073741801;
        }
      }
      if ( a1 == HKEY_PERFORMANCE_TEXT )
      {
        Names = PerfGetNames(v78, &stru_180067610, &v85, a6, a7, a8, L"009");
        if ( (int)(Names + 0x80000000) < 0 || Names == -2147483643 || !v17 || !*v17 )
          goto LABEL_135;
        v27 = -1;
        do
          v28 = v17[++v27] == 0;
        while ( !v28 );
        v29 = &v17[v27 + 1];
        if ( *v29 )
        {
          do
          {
            v30 = v29;
            v31 = -1;
            do
              v28 = v29[++v31] == 0;
            while ( !v28 );
            v29 += v31 + 1;
          }
          while ( *v29 );
        }
        else
        {
          v30 = v17;
        }
        LangIdFromSzLang = GetLangIdFromSzLang(v30);
        v33 = 48;
        if ( (unsigned __int16)(LangIdFromSzLang >> 12) >= 0xAu )
          v33 = 87;
        v34 = (char)((LangIdFromSzLang >> 12) + v33);
        v35 = HIBYTE(LangIdFromSzLang) & 0xF;
        *(_OWORD *)&NativeLangId = 0;
        NativeLangId = v34;
        v36 = 48;
        if ( v35 >= 0xAu )
          v36 = 87;
        *(&NativeLangId + 1) = (char)(v35 + v36);
        v37 = 48;
        v38 = (unsigned __int8)LangIdFromSzLang >> 4;
        if ( v38 >= 0xAu )
          v37 = 87;
        *(&NativeLangId + 2) = (char)(v38 + v37);
        v39 = 48;
        if ( (LangIdFromSzLang & 0xFu) >= 0xA )
          v39 = 87;
        *(&NativeLangId + 3) = (char)((LangIdFromSzLang & 0xF) + v39);
        *(_DWORD *)(&NativeLangId + 3) = *(&NativeLangId + 3);
        if ( a7 )
          *a7 = v77;
        if ( a8 )
          *a8 = 0;
        Names = PerfGetNames(v78, &stru_180067610, &v85, a6, a7, a8, &NativeLangId);
        if ( (int)(Names + 0x80000000) < 0 || Names == -2147483643 )
          goto LABEL_135;
        v40 = LangIdFromSzLang & 0x3FF;
        *((_QWORD *)&NativeLangId + 1) = 0;
        *(&NativeLangId + 3) = 0;
        NativeLangId = HIBYTE(v40) + 48;
        v41 = (unsigned __int8)v40 >> 4;
        v42 = 48;
        v43 = 48;
        if ( v41 >= 0xAu )
          v43 = 87;
        v44 = v40 & 0xF;
        *(&NativeLangId + 1) = (char)(v41 + v43);
        if ( v44 >= 0xAu )
          v42 = 87;
        *(&NativeLangId + 2) = (char)(v44 + v42);
        if ( a7 )
          *a7 = v77;
        if ( a8 )
          *a8 = 0;
        v45 = &NativeLangId;
      }
      else
      {
        if ( a1 != HKEY_PERFORMANCE_NLSTEXT )
          goto LABEL_135;
        if ( v17 && *v17 )
        {
          v46 = v17;
          while ( 1 )
          {
            v47 = 0;
            v48 = -1;
            do
              ++v48;
            while ( v46[v48] );
            for ( i = 0; (unsigned int)i < (unsigned int)v48; i = (unsigned int)(i + 1) )
            {
              v50 = (unsigned __int16)v46[i];
              v51 = 16 * v47;
              if ( (unsigned __int16)(v50 - 48) > 9u )
              {
                if ( (unsigned __int16)(v50 - 97) > 5u )
                {
                  if ( (unsigned __int16)(v50 - 65) > 5u )
                  {
                    LOWORD(v47) = 0;
                    break;
                  }
                  v52 = v51 - 55;
                }
                else
                {
                  v52 = v51 - 87;
                }
              }
              else
              {
                v52 = v51 - 48;
              }
              v47 = v50 + v52;
            }
            v53 = 48;
            *(_OWORD *)&NativeLangId = 0;
            if ( (unsigned __int16)((unsigned __int16)v47 >> 12) >= 0xAu )
              v53 = 87;
            NativeLangId = (char)(((unsigned __int16)v47 >> 12) + v53);
            v54 = 48;
            v55 = BYTE1(v47) & 0xF;
            if ( v55 >= 0xAu )
              v54 = 87;
            *(&NativeLangId + 1) = (char)(v55 + v54);
            v56 = 48;
            v57 = (unsigned __int8)v47 >> 4;
            if ( v57 >= 0xAu )
              v56 = 87;
            *(&NativeLangId + 2) = (char)(v57 + v56);
            v58 = 48;
            if ( (v47 & 0xFu) >= 0xA )
              v58 = 87;
            *(&NativeLangId + 3) = (char)((v47 & 0xF) + v58);
            *(_DWORD *)(&NativeLangId + 3) = *(&NativeLangId + 3);
            v59 = v86;
            if ( v86 )
              *v86 = v77;
            if ( a8 )
              *a8 = 0;
            v60 = PerfGetNames(v78, &stru_180067610, &v85, a6, v59, a8, &NativeLangId);
            Names = v60;
            if ( v60 >= 0 )
              break;
            if ( v60 == -2147483643 )
              goto LABEL_135;
            v61 = v47 & 0x3FF;
            *((_QWORD *)&NativeLangId + 1) = 0;
            *(&NativeLangId + 3) = 0;
            NativeLangId = HIBYTE(v61) + 48;
            v62 = (unsigned __int8)v61 >> 4;
            v63 = 48;
            if ( v62 >= 0xAu )
              v63 = 87;
            v64 = v61 & 0xF;
            *(&NativeLangId + 1) = (char)(v62 + v63);
            v65 = 48;
            if ( v64 >= 0xAu )
              v65 = 87;
            v66 = v64 + v65;
            v8 = v86;
            *(&NativeLangId + 2) = v66;
            if ( v86 )
              *v86 = v77;
            if ( a8 )
              *a8 = 0;
            v67 = PerfGetNames(v78, &stru_180067610, &v85, a6, v8, a8, &NativeLangId);
            Names = v67;
            if ( v67 < 0 )
            {
              if ( v67 == -2147483643 )
                goto LABEL_135;
              v68 = -1;
              do
                v28 = v46[++v68] == 0;
              while ( !v28 );
              v46 += v68 + 1;
              if ( *v46 )
                continue;
            }
            goto LABEL_127;
          }
          v8 = v86;
LABEL_127:
          if ( (int)(Names + 0x80000000) < 0 || Names == -2147483643 )
            goto LABEL_135;
        }
        if ( v8 )
          *v8 = v77;
        if ( a8 )
          *a8 = 0;
        v45 = L"009";
      }
      Names = PerfGetNames(v78, &stru_180067610, &v85, a6, v8, a8, v45);
LABEL_135:
      if ( v79 )
        LocalFree(hKey);
      goto LABEL_137;
    }
    v91 = 0;
    v94 = 0;
    v92 = 0;
    v95 = 0;
    v93 = 0;
    v69 = NtWaitForSingleObject(hGlobalDataMutex, 0, &Timeout);
    if ( v69 )
    {
      ExtensibleData = 170;
      v11 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        v70 = v77;
LABEL_178:
        if ( a8 )
        {
          *a8 = v70;
          v11 = WPP_GLOBAL_Control;
        }
        if ( !v88 )
          goto LABEL_199;
        *v88 = 3;
LABEL_182:
        v11 = WPP_GLOBAL_Control;
        goto LABEL_199;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids, v69);
      v70 = v77;
    }
    else
    {
      v71 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids);
        v71 = WPP_GLOBAL_Control;
      }
      if ( v77 >= 0x7A )
      {
        if ( a6 )
        {
          if ( v15 == 3 )
          {
            v83 = a6;
            *(_OWORD *)a6 = 0;
            *((_OWORD *)a6 + 1) = 0;
            *((_OWORD *)a6 + 2) = 0;
            *((_OWORD *)a6 + 3) = 0;
            *((_OWORD *)a6 + 4) = 0;
            *((_QWORD *)a6 + 10) = 0;
          }
          else
          {
            *(_DWORD *)a6 = 4522064;
            *((_DWORD *)a6 + 1) = 4587602;
            *((_DWORD *)a6 + 2) = 1;
            *((_DWORD *)a6 + 3) = 1;
            *((_QWORD *)a6 + 2) = 1;
            *((_DWORD *)a6 + 7) = 0;
            *((_DWORD *)a6 + 8) = 238;
            GetSystemTime((LPSYSTEMTIME)(a6 + 36));
            NtQueryPerformanceCounter((PLARGE_INTEGER)a6 + 7, (PLARGE_INTEGER)a6 + 8);
            GetSystemTimeAsFileTime((LPFILETIME)a6 + 9);
            if ( (_DWORD)ComputerNameLength )
            {
              v72 = pComputerName;
              *((_DWORD *)a6 + 20) = ComputerNameLength;
              *((_DWORD *)a6 + 21) = 88;
              memmove_0(a6 + 88, v72, (unsigned int)ComputerNameLength);
              v83 = &a6[(((_DWORD)ComputerNameLength + 7) & 0xFFFFFFF8) + 88];
              *((_DWORD *)a6 + 6) = ((ComputerNameLength + 7) & 0xFFFFFFF8) + 88;
            }
            else
            {
              *((_QWORD *)a6 + 10) = 0;
              v83 = a6 + 88;
              *((_DWORD *)a6 + 6) = 88;
            }
          }
        }
        LODWORD(v91) = v78;
        *(_QWORD *)&v92 = v85.Buffer;
        *((_QWORD *)&v93 + 1) = &v83;
        *((_QWORD *)&v92 + 1) = a6;
        *(_QWORD *)&v93 = a7;
        v94 = 0;
        v95 = 0;
        ExtensibleData = QueryExtensibleData((struct COLLECT_THREAD_DATA *)&v91);
      }
      else
      {
        if ( (*((_BYTE *)v71 + 28) & 2) != 0 && *((_BYTE *)v71 + 25) >= 2u )
          WPP_SF_d(v71[2], 29, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids, v77);
        ExtensibleData = 234;
      }
      ReleaseMutex(hGlobalDataMutex);
      v11 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids);
        v11 = WPP_GLOBAL_Control;
      }
      if ( ExtensibleData )
      {
        v73 = 122;
        if ( v77 < 0x7A )
          v73 = v77;
        v70 = v73;
        goto LABEL_178;
      }
      ExtensibleData = 0;
      v70 = (_DWORD)v83 - (_DWORD)a6;
      if ( a7 )
        *a7 = v70;
      *((_DWORD *)a6 + 5) = v70;
    }
    v11 = WPP_GLOBAL_Control;
    goto LABEL_178;
  }
  if ( PerfpThrottleError(0x3E8u, 0, &PerfpErrorLog) )
  {
    nSize = 128;
    if ( !GetUserNameExW((EXTENDED_NAME_FORMAT)65538, NameBuffer, &nSize) )
      NameBuffer[0] = 0;
    if ( !GetModuleFileNameW(0, Filename, 0x104u) )
      Filename[0] = 0;
    if ( (Microsoft_Windows_PerflibEnableBits & 2) != 0 )
    {
      v75 = -1;
      do
        v28 = NameBuffer[++v75] == 0;
      while ( !v28 );
      *(_QWORD *)&v93 = (unsigned int)(2 * v75 + 2);
      *((_QWORD *)&v92 + 1) = NameBuffer;
      do
        v28 = Filename[++v12] == 0;
      while ( !v28 );
      v94 = (unsigned int)(2 * v12 + 2);
      *((_QWORD *)&v93 + 1) = Filename;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)S_Perflib_Context,
        (unsigned int)PERFLIB_ACCESS_DENIED,
        v74,
        3,
        (__int64)&v91);
    }
  }
  ExtensibleData = 5;
  v11 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v21 = 20;
    v22 = 5;
    goto LABEL_197;
  }
LABEL_199:
  if ( dwBoostPriority && v81 > 0 && v81 != v80 )
  {
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPriority, &v81, 4u);
    v11 = WPP_GLOBAL_Control;
  }
  if ( (*((_BYTE *)v11 + 28) & 1) != 0 && *((_BYTE *)v11 + 25) >= 4u )
    WPP_SF_d(v11[2], 31, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids, ExtensibleData);
  return ExtensibleData;
}

```

## disassembly

```asm
0x1800288a0  mov     [rsp-8+arg_8], rbx
0x1800288a5  push    rbp
0x1800288a6  push    rsi
0x1800288a7  push    rdi
0x1800288a8  push    r12
0x1800288aa  push    r13
0x1800288ac  push    r14
0x1800288ae  push    r15
0x1800288b0  lea     rbp, [rsp-320h]
0x1800288b8  sub     rsp, 420h
0x1800288bf  mov     rax, cs:__security_cookie
0x1800288c6  xor     rax, rsp
0x1800288c9  mov     [rbp+350h+var_40], rax
0x1800288d0  mov     rax, [rbp+350h+arg_20]
0x1800288d7  lea     rdx, PerfpInitializeCallback
0x1800288de  mov     rbx, [rbp+350h+arg_30]
0x1800288e5  xor     r15d, r15d
0x1800288e8  mov     r14, [rbp+350h+arg_28]
0x1800288ef  xorps   xmm0, xmm0
0x1800288f2  mov     r12, [rbp+350h+arg_38]
0x1800288f9  mov     rdi, r8
0x1800288fc  mov     rsi, rcx
0x1800288ff  mov     [rbp+350h+var_3C0], rax
0x180028903  xor     r8d, r8d
0x180028906  mov     [rbp+350h+var_3D0], rbx
0x18002890a  lea     rcx, qword_1800A3088
0x180028911  mov     [rsp+450h+var_3F0], r15
0x180028916  xor     r9d, r9d
0x180028919  mov     qword ptr [rsp+450h+var_3E0.Length], r15
0x18002891e  mov     [rsp+450h+var_3E0.Buffer], r15
0x180028923  mov     qword ptr [rbp+350h+Timeout], r15
0x180028927  movups  [rbp+350h+ThreadInformation], xmm0
0x18002892b  mov     [rsp+450h+var_3FC], r15d
0x180028930  movups  [rbp+350h+var_3A8], xmm0
0x180028934  mov     [rsp+450h+var_400], r15d
0x180028939  movups  [rbp+350h+var_398], xmm0
0x18002893d  call    cs:__imp_RtlRunOnceExecuteOnce
0x180028943  mov     rcx, cs:WPP_GLOBAL_Control
0x18002894a  test    byte ptr [rcx+1Ch], 1
0x18002894e  jz      short loc_180028975
0x180028950  cmp     byte ptr [rcx+19h], 4
0x180028954  jb      short loc_180028975
0x180028956  mov     rcx, [rcx+10h]
0x18002895a  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180028961  mov     edx, 12h
0x180028966  mov     r9, rdi
0x180028969  call    WPP_SF_Z
0x18002896e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028975  mov     [rsp+450h+var_3F0], r15
0x18002897a  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180028981  mov     [rsp+450h+var_400], r13d
0x180028986  mov     [rsp+450h+var_3FC], r13d
0x18002898b  test    rdi, rdi
0x18002898e  jz      loc_180029632
0x180028994  cmp     [rdi+8], r15
0x180028998  jz      loc_180029632
0x18002899e  movups  xmm0, xmmword ptr [rdi]
0x1800289a1  mov     rcx, [rdi+8]; String1
0x1800289a5  movups  xmmword ptr [rsp+450h+var_3E0.Length], xmm0
0x1800289aa  call    ?GetQueryType@@YAKPEAG@Z; GetQueryType(ushort *)
0x1800289af  mov     [rsp+450h+var_40C], eax
0x1800289b3  movzx   edi, ax
0x1800289b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800289bd  test    byte ptr [rcx+1Ch], 2
0x1800289c1  jz      short loc_1800289E1
0x1800289c3  cmp     byte ptr [rcx+19h], 4
0x1800289c7  jb      short loc_1800289E1
0x1800289c9  mov     rcx, [rcx+10h]
0x1800289cd  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x1800289d4  mov     edx, 13h
0x1800289d9  mov     r9d, edi
0x1800289dc  call    WPP_SF_d
0x1800289e1  lea     eax, [rdi-5]
0x1800289e4  mov     rcx, rsi
0x1800289e7  cmp     ax, 3
0x1800289eb  setbe   al
0x1800289ee  movzx   edx, al
0x1800289f1  mov     [rsp+450h+var_408], al
0x1800289f5  call    PerfOpenKey
0x1800289fa  mov     r15d, eax
0x1800289fd  test    eax, eax
0x1800289ff  jnz     loc_1800294F7
0x180028a05  lea     rax, [rsp+450h+hKey]
0x180028a0a  xor     r15d, r15d
0x180028a0d  mov     r9d, 20019h; samDesired
0x180028a13  mov     [rsp+450h+hKey], r15
0x180028a18  xor     r8d, r8d; ulOptions
0x180028a1b  mov     [rsp+450h+phkResult], rax; phkResult
0x180028a20  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180028a27  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180028a2e  call    cs:__imp_RegOpenKeyExW
0x180028a34  test    eax, eax
0x180028a36  jnz     loc_180029503
0x180028a3c  mov     rcx, [rsp+450h+hKey]; hKey
0x180028a41  call    cs:__imp_RegCloseKey
0x180028a47  cmp     cs:?dwBoostPriority@@3KA, r15d; ulong dwBoostPriority
0x180028a4e  jz      loc_180028B16
0x180028a54  mov     r9d, 30h ; '0'; ThreadInformationLength
0x180028a5a  mov     [rsp+450h+phkResult], r15; ReturnLength
0x180028a5f  lea     r8, [rbp+350h+ThreadInformation]; ThreadInformation
0x180028a63  xor     edx, edx; ThreadInformationClass
0x180028a65  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180028a6c  call    cs:__imp_NtQueryInformationThread
0x180028a72  test    eax, eax
0x180028a74  js      short loc_180028ADE
0x180028a76  mov     eax, dword ptr [rbp+350h+var_398+8]
0x180028a79  mov     [rsp+450h+var_3FC], eax
0x180028a7d  dec     eax
0x180028a7f  mov     [rsp+450h+var_400], 0Fh
0x180028a87  cmp     eax, 0Dh
0x180028a8a  ja      loc_180028B11
0x180028a90  mov     r9d, 4; ThreadInformationLength
0x180028a96  lea     r8, [rsp+450h+var_400]; ThreadInformation
0x180028a9b  mov     edx, 2; ThreadInformationClass
0x180028aa0  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180028aa7  call    cs:__imp_NtSetInformationThread
0x180028aad  test    eax, eax
0x180028aaf  jns     short loc_180028B16
0x180028ab1  mov     rcx, cs:WPP_GLOBAL_Control
0x180028ab8  test    byte ptr [rcx+1Ch], 2
0x180028abc  jz      short loc_180028B11
0x180028abe  cmp     byte ptr [rcx+19h], 2
0x180028ac2  jb      short loc_180028B11
0x180028ac4  mov     rcx, [rcx+10h]
0x180028ac8  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180028acf  mov     edx, 16h
0x180028ad4  mov     r9d, eax
0x180028ad7  call    WPP_SF_d
0x180028adc  jmp     short loc_180028B11
0x180028ade  mov     rcx, cs:WPP_GLOBAL_Control
0x180028ae5  test    byte ptr [rcx+1Ch], 2
0x180028ae9  jz      short loc_180028B09
0x180028aeb  cmp     byte ptr [rcx+19h], 2
0x180028aef  jb      short loc_180028B09
0x180028af1  mov     rcx, [rcx+10h]
0x180028af5  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180028afc  mov     edx, 15h
0x180028b01  mov     r9d, eax
0x180028b04  call    WPP_SF_d
0x180028b09  mov     [rsp+450h+var_400], 0Fh
0x180028b11  mov     [rsp+450h+var_3FC], r13d
0x180028b16  mov     [rsp+450h+var_410], r15d
0x180028b1b  test    r12, r12
0x180028b1e  jz      short loc_180028B24
0x180028b20  mov     [r12], r15d
0x180028b24  test    rbx, rbx
0x180028b27  jz      short loc_180028B2F
0x180028b29  mov     eax, [rbx]
0x180028b2b  mov     [rsp+450h+var_410], eax
0x180028b2f  mov     rcx, cs:?hGlobalDataMutex@@3PEAXEA; Handle
0x180028b36  lea     r8, [rbp+350h+Timeout]; Timeout
0x180028b3a  xor     edx, edx; Alertable
0x180028b3c  mov     qword ptr [rbp+350h+Timeout], 0FFFFFFFFFECED300h
0x180028b44  cmp     [rsp+450h+var_408], r15b
0x180028b49  jz      loc_18002926A
0x180028b4f  call    cs:__imp_NtWaitForSingleObject
0x180028b55  test    eax, eax
0x180028b57  jz      short loc_180028B87
0x180028b59  mov     r15d, 0AAh
0x180028b5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b66  test    byte ptr [rcx+1Ch], 2
0x180028b6a  jz      loc_180029638
0x180028b70  cmp     byte ptr [rcx+19h], 2
0x180028b74  jb      loc_180029638
0x180028b7a  mov     edx, 17h
0x180028b7f  mov     r9d, eax
0x180028b82  jmp     loc_180029619
0x180028b87  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b8e  test    byte ptr [rcx+1Ch], 2
0x180028b92  jz      short loc_180028BB6
0x180028b94  cmp     byte ptr [rcx+19h], 4
0x180028b98  jb      short loc_180028BB6
0x180028b9a  mov     rcx, [rcx+10h]
0x180028b9e  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180028ba5  mov     edx, 18h
0x180028baa  call    WPP_SF_
0x180028baf  mov     rcx, cs:WPP_GLOBAL_Control
0x180028bb6  cmp     rsi, 0FFFFFFFF80000004h
0x180028bbd  jnz     short loc_180028BED
0x180028bbf  mov     ecx, [rsp+450h+var_40C]; unsigned int
0x180028bc3  lea     r8, [rsp+450h+var_3E0]; struct _UNICODE_STRING *
0x180028bc8  mov     [rsp+450h+var_420], r15; unsigned __int16 *
0x180028bcd  lea     rdx, stru_180067610; struct _UNICODE_STRING *
0x180028bd4  mov     [rsp+450h+var_428], r12; unsigned int *
0x180028bd9  mov     r9, r14; unsigned __int8 *
0x180028bdc  mov     [rsp+450h+phkResult], rbx; unsigned int *
0x180028be1  call    ?PerfGetNames@@YAJKPEBU_UNICODE_STRING@@0PEAEPEAK2PEBG@Z; PerfGetNames(ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar *,ulong *,ulong *,ushort const *)
0x180028be6  mov     edi, eax
0x180028be8  jmp     loc_1800291D9
0x180028bed  lea     rax, [rsi+7FFFFFB0h]
0x180028bf4  test    rax, 0FFFFFFFFFFFFFFEFh
0x180028bfa  jz      short loc_180028C06
0x180028bfc  mov     edi, 0C000000Dh
0x180028c01  jmp     loc_1800291E4
0x180028c06  lea     r9, [rsp+450h+nSize]
0x180028c0b  mov     [rsp+450h+hKey], r15
0x180028c10  xor     r8d, r8d
0x180028c13  mov     [rsp+450h+nSize], r15d
0x180028c18  lea     rdx, [rsp+450h+var_404]
0x180028c1d  mov     [rsp+450h+var_404], r15d
0x180028c22  mov     ecx, 24h ; '$'
0x180028c27  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x180028c2d  mov     edi, eax
0x180028c2f  test    eax, eax
0x180028c31  jz      short loc_180028C3A
0x180028c33  cmp     eax, 0C0000023h
0x180028c38  jnz     short loc_180028CA6
0x180028c3a  mov     eax, [rsp+450h+nSize]
0x180028c3e  test    eax, eax
0x180028c40  jz      short loc_180028CA6
0x180028c42  mov     edx, eax
0x180028c44  mov     eax, 2
0x180028c49  mul     rdx
0x180028c4c  cmovb   rax, r13
0x180028c50  mov     rcx, rax
0x180028c53  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180028c58  mov     [rsp+450h+hKey], rax
0x180028c5d  mov     r15, rax
0x180028c60  test    rax, rax
0x180028c63  jz      short loc_180028C99
0x180028c65  lea     r9, [rsp+450h+nSize]
0x180028c6a  mov     r8, rax
0x180028c6d  lea     rdx, [rsp+450h+var_404]
0x180028c72  mov     ecx, 24h ; '$'
0x180028c77  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x180028c7d  cmp     [rsp+450h+var_404], 0
0x180028c82  mov     edi, eax
0x180028c84  jnz     short loc_180028CA6
0x180028c86  mov     rcx, r15; hMem
0x180028c89  call    cs:__imp_LocalFree
0x180028c8f  xor     r15d, r15d
0x180028c92  mov     [rsp+450h+hKey], r15
0x180028c97  jmp     short loc_180028CA6
0x180028c99  mov     [rsp+450h+var_404], 0
0x180028ca1  mov     edi, 0C0000017h
0x180028ca6  cmp     rsi, 0FFFFFFFF80000050h
0x180028cad  jnz     loc_180028F01
0x180028cb3  mov     ecx, [rsp+450h+var_40C]; unsigned int
0x180028cb7  lea     rax, ?DefaultLangId@@3QBGB; "009"
0x180028cbe  mov     [rsp+450h+var_420], rax; unsigned __int16 *
0x180028cc3  lea     r8, [rsp+450h+var_3E0]; struct _UNICODE_STRING *
0x180028cc8  mov     [rsp+450h+var_428], r12; unsigned int *
0x180028ccd  lea     rdx, stru_180067610; struct _UNICODE_STRING *
0x180028cd4  mov     r9, r14; unsigned __int8 *
0x180028cd7  mov     [rsp+450h+phkResult], rbx; unsigned int *
0x180028cdc  call    ?PerfGetNames@@YAJKPEBU_UNICODE_STRING@@0PEAEPEAK2PEBG@Z; PerfGetNames(ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar *,ulong *,ulong *,ushort const *)
0x180028ce1  mov     ecx, 80000000h
0x180028ce6  mov     edi, eax
0x180028ce8  add     eax, ecx
0x180028cea  test    ecx, eax
0x180028cec  jnz     loc_1800291C7
0x180028cf2  cmp     edi, 80000005h
0x180028cf8  jz      loc_1800291C7
0x180028cfe  test    r15, r15
0x180028d01  jz      loc_1800291C7
0x180028d07  cmp     word ptr [r15], 0
0x180028d0c  jz      loc_1800291C7
0x180028d12  mov     rax, r13
0x180028d15  nop     word ptr [rax+rax+00000000h]
0x180028d20  cmp     word ptr [r15+rax*2+2], 0
0x180028d27  lea     rax, [rax+1]
0x180028d2b  jnz     short loc_180028D20
0x180028d2d  lea     rcx, [rax+1]
0x180028d31  cmp     word ptr [r15+rcx*2], 0
0x180028d37  lea     rcx, [r15+rcx*2]
0x180028d3b  jz      short loc_180028D6C
0x180028d3d  nop     dword ptr [rax]
0x180028d40  mov     rdx, rcx
0x180028d43  mov     rax, r13
0x180028d46  nop     word ptr [rax+rax+00000000h]
0x180028d50  cmp     word ptr [rcx+rax*2+2], 0
0x180028d56  lea     rax, [rax+1]
0x180028d5a  jnz     short loc_180028D50
0x180028d5c  lea     rcx, [rcx+rax*2]
0x180028d60  add     rcx, 2
0x180028d64  cmp     word ptr [rcx], 0
0x180028d68  jnz     short loc_180028D40
0x180028d6a  jmp     short loc_180028D6F
0x180028d6c  mov     rdx, r15
0x180028d6f  mov     rcx, rdx; unsigned __int16 *
0x180028d72  call    ?GetLangIdFromSzLang@@YAKPEBG@Z; GetLangIdFromSzLang(ushort const *)
0x180028d77  mov     r13d, [rsp+450h+var_410]
0x180028d7c  mov     esi, eax
0x180028d7e  movzx   edx, ax
0x180028d81  mov     r8d, 30h ; '0'
0x180028d87  shr     dx, 0Ch
0x180028d8b  mov     r15d, 57h ; 'W'
0x180028d91  cmp     dx, 0Ah
0x180028d95  mov     ecx, r8d
0x180028d98  xorps   xmm0, xmm0
0x180028d9b  cmovnb  ecx, r15d
0x180028d9f  add     cl, dl
0x180028da1  movsx   eax, cl
0x180028da4  movzx   ecx, si
0x180028da7  shr     cx, 8
0x180028dab  and     cx, 0Fh
0x180028daf  cmp     cx, 0Ah
0x180028db3  movups  cs:?NativeLangId@@3PAGA, xmm0; ushort near * NativeLangId
0x180028dba  mov     word ptr cs:?NativeLangId@@3PAGA, ax; ushort near * NativeLangId
0x180028dc1  mov     eax, r8d
  ... truncated ...
```
