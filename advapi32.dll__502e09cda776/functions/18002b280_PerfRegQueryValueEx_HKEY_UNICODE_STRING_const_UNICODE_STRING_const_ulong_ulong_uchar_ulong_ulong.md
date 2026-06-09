# PerfRegQueryValueEx(HKEY__ *,_UNICODE_STRING const *,_UNICODE_STRING const *,ulong *,ulong *,uchar *,ulong *,ulong *)

- ea: `0x18002b280`
- end: `0x18002c10b`
- name: `?PerfRegQueryValueEx@@YAJPEAUHKEY__@@PEBU_UNICODE_STRING@@1PEAK2PEAE22@Z`
- size: `3723`
- prototype: `__int64 __fastcall(HKEY, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, unsigned int *, unsigned int *, unsigned __int8 *, unsigned int *, unsigned int *)`
- caller_count: `4`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002ad50`
- `0x18002ae50`
- `0x18002b230`
- `0x180063490`

## callees

- `0x180001978`
- `0x180002e40`
- `0x18000d240`
- `0x180027f50`
- `0x180029698`
- `0x18002a6a8`
- `0x18002b280`
- `0x18002f850`
- `0x18003c6c8`
- `0x18003e250`
- `0x18003fb18`
- `0x18003fd04`
- `0x180062c40`
- `0x18007204e`
- `0x1800720b0`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18002b49f`
- `ntdll!NtSetInformationThread` at `0x18002c0a6`
- `ntdll!NtSetInformationThread` at `0x18002b49f`
- `ntdll!NtSetInformationThread` at `0x18002c0a6`
- `ntdll!NtWaitForSingleObject` at `0x18002b54d`
- `ntdll!NtWaitForSingleObject` at `0x18002bca2`
- `ntdll!NtWaitForSingleObject` at `0x18002b54d`
- `ntdll!NtWaitForSingleObject` at `0x18002bca2`
- `ntdll!NtQueryInformationThread` at `0x18002b45e`
- `ntdll!NtQueryInformationThread` at `0x18002b45e`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18002b31d`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18002b31d`
- `ntdll!NtQueryPerformanceCounter` at `0x18002bddf`
- `ntdll!NtQueryPerformanceCounter` at `0x18002bddf`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18002b62b`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18002b681`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18002b62b`
- `ntdll!RtlGetThreadPreferredUILanguages` at `0x18002b681`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b414`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b414`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b42d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b42d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002bdef`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002bdef`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002bdcb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18002bdcb`
- `KERNEL32!LocalFree` at `0x18002b699`
- `KERNEL32!LocalFree` at `0x18002bbe3`
- `KERNEL32!LocalFree` at `0x18002b699`
- `KERNEL32!LocalFree` at `0x18002bbe3`
- `KERNEL32!ReleaseMutex` at `0x18002bc3e`
- `KERNEL32!ReleaseMutex` at `0x18002be9e`
- `KERNEL32!ReleaseMutex` at `0x18002bc3e`
- `KERNEL32!ReleaseMutex` at `0x18002be9e`
- `KERNEL32!GetModuleFileNameW` at `0x18002bf92`
- `KERNEL32!GetModuleFileNameW` at `0x18002bf92`
- `SspiCli!GetUserNameExW` at `0x18002bf6e`
- `SspiCli!GetUserNameExW` at `0x18002bf6e`

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
  RtlRunOnceExecuteOnce(qword_1800B21D0, PerfpInitializeCallback, 0, 0);
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
        Names = PerfGetNames(v78, &stru_1800755F0, &v85, a6, a7, a8, 0);
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
        Names = PerfGetNames(v78, &stru_1800755F0, &v85, a6, a7, a8, L"009");
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
        Names = PerfGetNames(v78, &stru_1800755F0, &v85, a6, a7, a8, &NativeLangId);
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
            v60 = PerfGetNames(v78, &stru_1800755F0, &v85, a6, v59, a8, &NativeLangId);
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
            v67 = PerfGetNames(v78, &stru_1800755F0, &v85, a6, v8, a8, &NativeLangId);
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
      Names = PerfGetNames(v78, &stru_1800755F0, &v85, a6, v8, a8, v45);
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
            if ( LODWORD(PerfpErrorLog.el_data) )
            {
              v72 = pComputerName;
              *((_DWORD *)a6 + 20) = PerfpErrorLog.el_data;
              *((_DWORD *)a6 + 21) = 88;
              memmove_0(a6 + 88, v72, LODWORD(PerfpErrorLog.el_data));
              v83 = &a6[((LODWORD(PerfpErrorLog.el_data) + 7) & 0xFFFFFFF8) + 88];
              *((_DWORD *)a6 + 6) = ((LODWORD(PerfpErrorLog.el_data) + 7) & 0xFFFFFFF8) + 88;
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
0x18002b280  mov     [rsp-8+arg_8], rbx
0x18002b285  push    rbp
0x18002b286  push    rsi
0x18002b287  push    rdi
0x18002b288  push    r12
0x18002b28a  push    r13
0x18002b28c  push    r14
0x18002b28e  push    r15
0x18002b290  lea     rbp, [rsp-320h]
0x18002b298  sub     rsp, 420h
0x18002b29f  mov     rax, cs:__security_cookie
0x18002b2a6  xor     rax, rsp
0x18002b2a9  mov     [rbp+350h+var_40], rax
0x18002b2b0  mov     rax, [rbp+350h+arg_20]
0x18002b2b7  lea     rdx, PerfpInitializeCallback
0x18002b2be  mov     rbx, [rbp+350h+arg_30]
0x18002b2c5  xor     r15d, r15d
0x18002b2c8  mov     r14, [rbp+350h+arg_28]
0x18002b2cf  xorps   xmm0, xmm0
0x18002b2d2  mov     r12, [rbp+350h+arg_38]
0x18002b2d9  mov     rdi, r8
0x18002b2dc  mov     rsi, rcx
0x18002b2df  mov     [rbp+350h+var_3C0], rax
0x18002b2e3  xor     r8d, r8d
0x18002b2e6  mov     [rbp+350h+var_3D0], rbx
0x18002b2ea  lea     rcx, qword_1800B21D0
0x18002b2f1  mov     [rsp+450h+var_3F0], r15
0x18002b2f6  xor     r9d, r9d
0x18002b2f9  mov     qword ptr [rsp+450h+var_3E0.Length], r15
0x18002b2fe  mov     [rsp+450h+var_3E0.Buffer], r15
0x18002b303  mov     qword ptr [rbp+350h+Timeout], r15
0x18002b307  movups  [rbp+350h+ThreadInformation], xmm0
0x18002b30b  mov     [rsp+450h+var_3FC], r15d
0x18002b310  movups  [rbp+350h+var_3A8], xmm0
0x18002b314  mov     [rsp+450h+var_400], r15d
0x18002b319  movups  [rbp+350h+var_398], xmm0
0x18002b31d  call    cs:__imp_RtlRunOnceExecuteOnce
0x18002b324  nop     dword ptr [rax+rax+00h]
0x18002b329  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b330  test    byte ptr [rcx+1Ch], 1
0x18002b334  jz      short loc_18002B35B
0x18002b336  cmp     byte ptr [rcx+19h], 4
0x18002b33a  jb      short loc_18002B35B
0x18002b33c  mov     rcx, [rcx+10h]
0x18002b340  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x18002b347  mov     edx, 12h
0x18002b34c  mov     r9, rdi
0x18002b34f  call    WPP_SF_Z
0x18002b354  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b35b  mov     [rsp+450h+var_3F0], r15
0x18002b360  mov     r13, 0FFFFFFFFFFFFFFFFh
0x18002b367  mov     [rsp+450h+var_400], r13d
0x18002b36c  mov     [rsp+450h+var_3FC], r13d
0x18002b371  test    rdi, rdi
0x18002b374  jz      loc_18002C072
0x18002b37a  cmp     [rdi+8], r15
0x18002b37e  jz      loc_18002C072
0x18002b384  movups  xmm0, xmmword ptr [rdi]
0x18002b387  mov     rcx, [rdi+8]; String1
0x18002b38b  movups  xmmword ptr [rsp+450h+var_3E0.Length], xmm0
0x18002b390  call    ?GetQueryType@@YAKPEAG@Z; GetQueryType(ushort *)
0x18002b395  mov     [rsp+450h+var_40C], eax
0x18002b399  movzx   edi, ax
0x18002b39c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b3a3  test    byte ptr [rcx+1Ch], 2
0x18002b3a7  jz      short loc_18002B3C7
0x18002b3a9  cmp     byte ptr [rcx+19h], 4
0x18002b3ad  jb      short loc_18002B3C7
0x18002b3af  mov     rcx, [rcx+10h]
0x18002b3b3  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x18002b3ba  mov     edx, 13h
0x18002b3bf  mov     r9d, edi
0x18002b3c2  call    WPP_SF_d
0x18002b3c7  lea     eax, [rdi-5]
0x18002b3ca  mov     rcx, rsi
0x18002b3cd  cmp     ax, 3
0x18002b3d1  setbe   al
0x18002b3d4  movzx   edx, al
0x18002b3d7  mov     [rsp+450h+var_408], al
0x18002b3db  call    PerfOpenKey
0x18002b3e0  mov     r15d, eax
0x18002b3e3  test    eax, eax
0x18002b3e5  jnz     loc_18002BF31
0x18002b3eb  lea     rax, [rsp+450h+hKey]
0x18002b3f0  xor     r15d, r15d
0x18002b3f3  mov     r9d, 20019h; samDesired
0x18002b3f9  mov     [rsp+450h+hKey], r15
0x18002b3fe  xor     r8d, r8d; ulOptions
0x18002b401  mov     [rsp+450h+phkResult], rax; phkResult
0x18002b406  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002b40d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b414  call    cs:__imp_RegOpenKeyExW
0x18002b41b  nop     dword ptr [rax+rax+00h]
0x18002b420  test    eax, eax
0x18002b422  jnz     loc_18002BF3D
0x18002b428  mov     rcx, [rsp+450h+hKey]; hKey
0x18002b42d  call    cs:__imp_RegCloseKey
0x18002b434  nop     dword ptr [rax+rax+00h]
0x18002b439  cmp     cs:?dwBoostPriority@@3KA, r15d; ulong dwBoostPriority
0x18002b440  jz      loc_18002B514
0x18002b446  mov     r9d, 30h ; '0'; ThreadInformationLength
0x18002b44c  mov     [rsp+450h+phkResult], r15; ReturnLength
0x18002b451  lea     r8, [rbp+350h+ThreadInformation]; ThreadInformation
0x18002b455  xor     edx, edx; ThreadInformationClass
0x18002b457  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18002b45e  call    cs:__imp_NtQueryInformationThread
0x18002b465  nop     dword ptr [rax+rax+00h]
0x18002b46a  test    eax, eax
0x18002b46c  js      short loc_18002B4DC
0x18002b46e  mov     eax, dword ptr [rbp+350h+var_398+8]
0x18002b471  mov     [rsp+450h+var_3FC], eax
0x18002b475  dec     eax
0x18002b477  mov     [rsp+450h+var_400], 0Fh
0x18002b47f  cmp     eax, 0Dh
0x18002b482  ja      loc_18002B50F
0x18002b488  mov     r9d, 4; ThreadInformationLength
0x18002b48e  lea     r8, [rsp+450h+var_400]; ThreadInformation
0x18002b493  mov     edx, 2; ThreadInformationClass
0x18002b498  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18002b49f  call    cs:__imp_NtSetInformationThread
0x18002b4a6  nop     dword ptr [rax+rax+00h]
0x18002b4ab  test    eax, eax
0x18002b4ad  jns     short loc_18002B514
0x18002b4af  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b4b6  test    byte ptr [rcx+1Ch], 2
0x18002b4ba  jz      short loc_18002B50F
0x18002b4bc  cmp     byte ptr [rcx+19h], 2
0x18002b4c0  jb      short loc_18002B50F
0x18002b4c2  mov     rcx, [rcx+10h]
0x18002b4c6  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x18002b4cd  mov     edx, 16h
0x18002b4d2  mov     r9d, eax
0x18002b4d5  call    WPP_SF_d
0x18002b4da  jmp     short loc_18002B50F
0x18002b4dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b4e3  test    byte ptr [rcx+1Ch], 2
0x18002b4e7  jz      short loc_18002B507
0x18002b4e9  cmp     byte ptr [rcx+19h], 2
0x18002b4ed  jb      short loc_18002B507
0x18002b4ef  mov     rcx, [rcx+10h]
0x18002b4f3  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x18002b4fa  mov     edx, 15h
0x18002b4ff  mov     r9d, eax
0x18002b502  call    WPP_SF_d
0x18002b507  mov     [rsp+450h+var_400], 0Fh
0x18002b50f  mov     [rsp+450h+var_3FC], r13d
0x18002b514  mov     [rsp+450h+var_410], r15d
0x18002b519  test    r12, r12
0x18002b51c  jz      short loc_18002B522
0x18002b51e  mov     [r12], r15d
0x18002b522  test    rbx, rbx
0x18002b525  jz      short loc_18002B52D
0x18002b527  mov     eax, [rbx]
0x18002b529  mov     [rsp+450h+var_410], eax
0x18002b52d  mov     rcx, cs:?hGlobalDataMutex@@3PEAXEA; Handle
0x18002b534  lea     r8, [rbp+350h+Timeout]; Timeout
0x18002b538  xor     edx, edx; Alertable
0x18002b53a  mov     qword ptr [rbp+350h+Timeout], 0FFFFFFFFFECED300h
0x18002b542  cmp     [rsp+450h+var_408], r15b
0x18002b547  jz      loc_18002BC86
0x18002b54d  call    cs:__imp_NtWaitForSingleObject
0x18002b554  nop     dword ptr [rax+rax+00h]
0x18002b559  test    eax, eax
0x18002b55b  jz      short loc_18002B58B
0x18002b55d  mov     r15d, 0AAh
0x18002b563  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b56a  test    byte ptr [rcx+1Ch], 2
0x18002b56e  jz      loc_18002C078
0x18002b574  cmp     byte ptr [rcx+19h], 2
0x18002b578  jb      loc_18002C078
0x18002b57e  mov     edx, 17h
0x18002b583  mov     r9d, eax
0x18002b586  jmp     loc_18002C059
0x18002b58b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b592  test    byte ptr [rcx+1Ch], 2
0x18002b596  jz      short loc_18002B5BA
0x18002b598  cmp     byte ptr [rcx+19h], 4
0x18002b59c  jb      short loc_18002B5BA
0x18002b59e  mov     rcx, [rcx+10h]
0x18002b5a2  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x18002b5a9  mov     edx, 18h
0x18002b5ae  call    WPP_SF_
0x18002b5b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b5ba  cmp     rsi, 0FFFFFFFF80000004h
0x18002b5c1  jnz     short loc_18002B5F1
0x18002b5c3  mov     ecx, [rsp+450h+var_40C]; unsigned int
0x18002b5c7  lea     r8, [rsp+450h+var_3E0]; struct _UNICODE_STRING *
0x18002b5cc  mov     [rsp+450h+var_420], r15; unsigned __int16 *
0x18002b5d1  lea     rdx, stru_1800755F0; struct _UNICODE_STRING *
0x18002b5d8  mov     [rsp+450h+var_428], r12; unsigned int *
0x18002b5dd  mov     r9, r14; unsigned __int8 *
0x18002b5e0  mov     [rsp+450h+phkResult], rbx; unsigned int *
0x18002b5e5  call    ?PerfGetNames@@YAJKPEBU_UNICODE_STRING@@0PEAEPEAK2PEBG@Z; PerfGetNames(ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar *,ulong *,ulong *,ushort const *)
0x18002b5ea  mov     edi, eax
0x18002b5ec  jmp     loc_18002BBEF
0x18002b5f1  lea     rax, [rsi+7FFFFFB0h]
0x18002b5f8  test    rax, 0FFFFFFFFFFFFFFEFh
0x18002b5fe  jz      short loc_18002B60A
0x18002b600  mov     edi, 0C000000Dh
0x18002b605  jmp     loc_18002BBFA
0x18002b60a  lea     r9, [rsp+450h+nSize]
0x18002b60f  mov     [rsp+450h+hKey], r15
0x18002b614  xor     r8d, r8d
0x18002b617  mov     [rsp+450h+nSize], r15d
0x18002b61c  lea     rdx, [rsp+450h+var_404]
0x18002b621  mov     [rsp+450h+var_404], r15d
0x18002b626  mov     ecx, 24h ; '$'
0x18002b62b  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x18002b632  nop     dword ptr [rax+rax+00h]
0x18002b637  mov     edi, eax
0x18002b639  test    eax, eax
0x18002b63b  jz      short loc_18002B644
0x18002b63d  cmp     eax, 0C0000023h
0x18002b642  jnz     short loc_18002B6BC
0x18002b644  mov     eax, [rsp+450h+nSize]
0x18002b648  test    eax, eax
0x18002b64a  jz      short loc_18002B6BC
0x18002b64c  mov     edx, eax
0x18002b64e  mov     eax, 2
0x18002b653  mul     rdx
0x18002b656  cmovb   rax, r13
0x18002b65a  mov     rcx, rax
0x18002b65d  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x18002b662  mov     [rsp+450h+hKey], rax
0x18002b667  mov     r15, rax
0x18002b66a  test    rax, rax
0x18002b66d  jz      short loc_18002B6AF
0x18002b66f  lea     r9, [rsp+450h+nSize]
0x18002b674  mov     r8, rax
0x18002b677  lea     rdx, [rsp+450h+var_404]
0x18002b67c  mov     ecx, 24h ; '$'
0x18002b681  call    cs:__imp_RtlGetThreadPreferredUILanguages
0x18002b688  nop     dword ptr [rax+rax+00h]
0x18002b68d  cmp     [rsp+450h+var_404], 0
0x18002b692  mov     edi, eax
0x18002b694  jnz     short loc_18002B6BC
0x18002b696  mov     rcx, r15; hMem
0x18002b699  call    cs:__imp_LocalFree
0x18002b6a0  nop     dword ptr [rax+rax+00h]
0x18002b6a5  xor     r15d, r15d
0x18002b6a8  mov     [rsp+450h+hKey], r15
0x18002b6ad  jmp     short loc_18002B6BC
0x18002b6af  mov     [rsp+450h+var_404], 0
0x18002b6b7  mov     edi, 0C0000017h
0x18002b6bc  cmp     rsi, 0FFFFFFFF80000050h
0x18002b6c3  jnz     loc_18002B911
0x18002b6c9  mov     ecx, [rsp+450h+var_40C]; unsigned int
0x18002b6cd  lea     rax, ?DefaultLangId@@3QBGB; "009"
0x18002b6d4  mov     [rsp+450h+var_420], rax; unsigned __int16 *
0x18002b6d9  lea     r8, [rsp+450h+var_3E0]; struct _UNICODE_STRING *
0x18002b6de  mov     [rsp+450h+var_428], r12; unsigned int *
0x18002b6e3  lea     rdx, stru_1800755F0; struct _UNICODE_STRING *
0x18002b6ea  mov     r9, r14; unsigned __int8 *
0x18002b6ed  mov     [rsp+450h+phkResult], rbx; unsigned int *
0x18002b6f2  call    ?PerfGetNames@@YAJKPEBU_UNICODE_STRING@@0PEAEPEAK2PEBG@Z; PerfGetNames(ulong,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar *,ulong *,ulong *,ushort const *)
0x18002b6f7  mov     ecx, 80000000h
0x18002b6fc  mov     edi, eax
0x18002b6fe  add     eax, ecx
0x18002b700  test    ecx, eax
0x18002b702  jnz     loc_18002BBD7
0x18002b708  cmp     edi, 80000005h
0x18002b70e  jz      loc_18002BBD7
0x18002b714  test    r15, r15
0x18002b717  jz      loc_18002BBD7
0x18002b71d  cmp     word ptr [r15], 0
0x18002b722  jz      loc_18002BBD7
0x18002b728  mov     rax, r13
0x18002b72b  nop     dword ptr [rax+rax+00h]
0x18002b730  cmp     word ptr [r15+rax*2+2], 0
0x18002b737  lea     rax, [rax+1]
0x18002b73b  jnz     short loc_18002B730
0x18002b73d  lea     rcx, [rax+1]
0x18002b741  cmp     word ptr [r15+rcx*2], 0
0x18002b747  lea     rcx, [r15+rcx*2]
0x18002b74b  jz      short loc_18002B77C
0x18002b74d  nop     dword ptr [rax]
0x18002b750  mov     rdx, rcx
0x18002b753  mov     rax, r13
0x18002b756  nop     word ptr [rax+rax+00000000h]
0x18002b760  cmp     word ptr [rcx+rax*2+2], 0
0x18002b766  lea     rax, [rax+1]
0x18002b76a  jnz     short loc_18002B760
0x18002b76c  lea     rcx, [rcx+rax*2]
0x18002b770  add     rcx, 2
0x18002b774  cmp     word ptr [rcx], 0
0x18002b778  jnz     short loc_18002B750
0x18002b77a  jmp     short loc_18002B77F
0x18002b77c  mov     rdx, r15
0x18002b77f  mov     rcx, rdx; unsigned __int16 *
0x18002b782  call    ?GetLangIdFromSzLang@@YAKPEBG@Z; GetLangIdFromSzLang(ushort const *)
0x18002b787  mov     r13d, [rsp+450h+var_410]
0x18002b78c  mov     esi, eax
0x18002b78e  movzx   edx, ax
0x18002b791  mov     r8d, 30h ; '0'
0x18002b797  shr     dx, 0Ch
0x18002b79b  mov     r15d, 57h ; 'W'
0x18002b7a1  cmp     dx, 0Ah
0x18002b7a5  mov     ecx, r8d
0x18002b7a8  xorps   xmm0, xmm0
0x18002b7ab  cmovnb  ecx, r15d
  ... truncated ...
```
