# InitLog(ITmInstance *,ushort *,ulong,ulong,ulong,ulong,int,int)

- ea: `0x180011634`
- end: `0x180011ab8`
- name: `?InitLog@@YAJPEAUITmInstance@@PEAGKKKKHH@Z`
- size: `1156`
- prototype: `int(struct ITmInstance *, unsigned __int16 *, unsigned int, unsigned int, unsigned int, unsigned int, int, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180049480`
- `0x18004a774`
- `0x18007544c`

## callees

- `0x180011634`
- `0x180011ac0`
- `0x18004b6fc`
- `0x18007168c`
- `0x1800737d8`
- `0x18007556c`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800116b3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800116b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800116f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800116f6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180011a4d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180011a4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800116c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800116c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011701`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180011980`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180011980`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011948`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180011948`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800119db`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800119db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011a1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011a1a`

## string_xrefs

- `0x1800116cd`: `com\complus\dtc\shared\util\initlog.cpp`
- `0x18001170d`: `com\complus\dtc\shared\util\initlog.cpp`
- `0x1800117ef`: `com\complus\dtc\shared\util\initlog.cpp`
- `0x180011a02`: `com\complus\dtc\shared\util\initlog.cpp`
- `0x180011a3e`: `com\complus\dtc\shared\util\initlog.cpp`
- `0x180011a85`: `com\complus\dtc\shared\util\initlog.cpp`
- `0x1800119fb`: `::InitLog - Failed: RegSetValueEx(...)`
- `0x180011968`: `::InitLog - Failed: RegOpenKey(...) on FileNotToBackup`
- `0x1800116d6`: `Failed to load msdtclog.dll`
- `0x1800116aa`: `msdtclog.dll`
- `0x180011716`: `Failed to find address of DllGetDtcLog2 function in msdtclog.dll`
- `0x1800116ec`: `DllGetDTCLOG2`
- `0x18001174e`: `::InitLog - Failed: DllGetDTCLOG(...)`
- `0x18001184f`: `::InitLog - Failed: piLogCreateStorage->CreateStream(...)`
- `0x1800117f6`: `::InitLog - Failed: piLogCreateStorage->CreateStorage(...)`

## pseudocode

```c
__int64 __fastcall InitLog(
        struct ITmInstance *a1,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        int a7)
{
  HMODULE Library; // rax
  HMODULE v12; // rsi
  DWORD v13; // eax
  unsigned int v14; // ebx
  FARPROC ProcAddress; // rax
  DWORD LastError; // eax
  unsigned int v17; // r9d
  char *v18; // rdx
  unsigned __int16 *BSW; // rax
  int v20; // eax
  unsigned __int16 *v21; // rax
  int v22; // eax
  int v23; // ecx
  unsigned __int16 *DefaultLogPath; // rax
  LSTATUS v25; // eax
  unsigned int v26; // r9d
  char *v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rcx
  LSTATUS v30; // eax
  LSTATUS v31; // eax
  unsigned int v32; // r9d
  char *v33; // rdx
  __int64 v35; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v38[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v39[264]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 Data[528]; // [rsp+490h] [rbp+390h] BYREF

  v35 = 0;
  dwDisposition[0] = 0;
  hKey = 0;
  if ( a3 < 5 )
  {
    v32 = 147;
    v33 = "::InitLog - Condition failed: dwTimer < MIN_LOG_TIMER_INTERVAL || dwTimer > MAX_LOG_TIMER_INTERVAL";
    goto LABEL_45;
  }
  if ( a4 < 0x64 )
  {
    v32 = 154;
    v33 = "::InitLog - Condition failed: dwCheckpoint < MIN_LOG_CHKPT_INTERVAL || dwCheckpoint > MAX_LOG_CHKPT_INTERVAL";
    goto LABEL_45;
  }
  if ( a5 - 5 > 0x3E3 )
  {
    v32 = 161;
    v33 = "::InitLog - Condition failed: dwFlush < MIN_LOG_FLUSH_INTERVAL || dwFlush > MAX_LOG_FLUSH_INTERVAL";
LABEL_45:
    v14 = -1073737688;
    TraceFile(-1073737688, v33, "com\\complus\\dtc\\shared\\util\\initlog.cpp", v32);
    return v14;
  }
  Library = LoadLibraryExA("msdtclog.dll", 0, 0);
  v12 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "DllGetDTCLOG2");
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      TraceFile(
        LastError,
        "Failed to find address of DllGetDtcLog2 function in msdtclog.dll",
        "com\\complus\\dtc\\shared\\util\\initlog.cpp",
        0xB3u);
      v14 = -1073737703;
LABEL_41:
      FreeLibrary(v12);
      return v14;
    }
    if ( ((unsigned int (__fastcall *)(GUID *, GUID *, __int64 *))ProcAddress)(
           &CLSID_CLogMgr,
           &IID_ILogCreateStorage2W,
           &v35) )
    {
      v17 = 186;
      v18 = "::InitLog - Failed: DllGetDTCLOG(...)";
      v14 = -1073737703;
LABEL_39:
      v23 = v14;
      goto LABEL_40;
    }
    BSW = SZStripLastBSW(a2);
    TracedStringCchPrintfW(v38, 0x105u, L"%s\\%s", BSW, L"MSDTC.LOG");
    v20 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, _QWORD, _QWORD, bool, unsigned int, unsigned int, unsigned int))(*(_QWORD *)v35 + 24LL))(
            v35,
            v38,
            a6,
            0,
            a7 == 0,
            a3,
            a5,
            a4);
    v14 = v20;
    if ( v20 == -2147024816 || v20 == -2147024713 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      v14 = 0;
    }
    else
    {
      if ( v20 )
      {
        TraceFile(
          v20,
          "::InitLog - Failed: piLogCreateStorage->CreateStorage(...)",
          "com\\complus\\dtc\\shared\\util\\initlog.cpp",
          0xE9u);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        goto LABEL_41;
      }
      v14 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v35 + 32LL))(v35, L"Streamname");
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      if ( v14 )
      {
        v17 = 212;
        v18 = "::InitLog - Failed: piLogCreateStorage->CreateStream(...)";
        goto LABEL_39;
      }
      v21 = SZStripLastBSW(a2);
      v22 = SetSddlOnLogFile(a1, v21, 0);
      v14 = v22;
      if ( v22 < 0 )
      {
        v17 = 220;
        v18 = "ResetLog: SetSddlOnLogFile FAILED";
        v23 = v22;
LABEL_40:
        TraceFile(v23, v18, "com\\complus\\dtc\\shared\\util\\initlog.cpp", v17);
        goto LABEL_41;
      }
    }
    DefaultLogPath = GetDefaultLogPath();
    TracedStringCchPrintfW(v39, 0x105u, L"%s\\%s\\%s", DefaultLogPath, L"trace", L"dtctrace.log");
    TracedStringCchPrintfW(Data, 0x20Bu, L"%s%c%s%c", v38, 0, v39, 0);
    v25 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SYSTEM\\CurrentControlSet\\Control\\BackupRestore\\FilesNotToBackup",
            0,
            (LPWSTR)&cchOriginalDestLength,
            0,
            0x2001Bu,
            0,
            &hKey,
            dwDisposition);
    if ( v25 )
    {
      if ( v25 > 0 )
        v14 = (unsigned __int16)v25 | 0x80070000;
      else
        v14 = v25;
      v26 = 272;
      v27 = "::InitLog - Failed: RegOpenKey(...) on FileNotToBackup";
    }
    else
    {
      RegDeleteValueW(hKey, L"MS Distributed Transaction Coordinatior");
      v28 = -1;
      v29 = -1;
      do
        ++v29;
      while ( v38[v29] );
      do
        ++v28;
      while ( v39[v28] );
      v30 = RegSetValueExW(
              hKey,
              L"MS Distributed Transaction Coordinator",
              0,
              7u,
              (const BYTE *)Data,
              2 * (v29 + v28) + 6);
      if ( !v30 )
        goto LABEL_33;
      if ( v30 > 0 )
        v14 = (unsigned __int16)v30 | 0x80070000;
      else
        v14 = v30;
      v26 = 293;
      v27 = "::InitLog - Failed: RegSetValueEx(...)";
    }
    TraceFile(v14, v27, "com\\complus\\dtc\\shared\\util\\initlog.cpp", v26);
LABEL_33:
    if ( !hKey )
      goto LABEL_41;
    v31 = RegCloseKey(hKey);
    if ( !v31 )
      goto LABEL_41;
    if ( v31 > 0 )
      v14 = (unsigned __int16)v31 | 0x80070000;
    else
      v14 = v31;
    v17 = 306;
    v18 = "::InitLog - Failed: RegCloseKey(...)";
    goto LABEL_39;
  }
  v13 = GetLastError();
  TraceFile(v13, "Failed to load msdtclog.dll", "com\\complus\\dtc\\shared\\util\\initlog.cpp", 0xAAu);
  return (unsigned int)-1073737703;
}

```

## disassembly

```asm
0x180011634  push    rbp
0x180011636  push    rbx
0x180011637  push    rsi
0x180011638  push    rdi
0x180011639  push    r12
0x18001163b  push    r13
0x18001163d  push    r14
0x18001163f  push    r15
0x180011641  lea     rbp, [rsp-7C8h]
0x180011649  sub     rsp, 8C8h
0x180011650  mov     rax, cs:__security_cookie
0x180011657  xor     rax, rsp
0x18001165a  mov     [rbp+800h+var_50], rax
0x180011661  xor     r13d, r13d
0x180011664  mov     edi, r9d
0x180011667  mov     [rsp+900h+var_8B0], r13
0x18001166c  mov     r14d, r8d
0x18001166f  mov     [rsp+900h+dwDisposition], r13d
0x180011674  mov     r15, rdx
0x180011677  mov     [rsp+900h+hKey], r13
0x18001167c  mov     r12, rcx
0x18001167f  cmp     r8d, 5
0x180011683  jb      loc_180011A73
0x180011689  cmp     r9d, 64h ; 'd'
0x18001168d  jb      loc_180011A64
0x180011693  mov     ebx, [rbp+800h+arg_20]
0x180011699  lea     eax, [rbx-5]
0x18001169c  cmp     eax, 3E3h
0x1800116a1  ja      loc_180011A55
0x1800116a7  xor     r8d, r8d; dwFlags
0x1800116aa  lea     rcx, aMsdtclogDll; "msdtclog.dll"
0x1800116b1  xor     edx, edx; hFile
0x1800116b3  call    cs:__imp_LoadLibraryExA
0x1800116b9  mov     rsi, rax
0x1800116bc  test    rax, rax
0x1800116bf  jnz     short loc_1800116EC
0x1800116c1  call    cs:__imp_GetLastError
0x1800116c7  mov     r9d, 0AAh; unsigned int
0x1800116cd  lea     r8, aComComplusDtcS_16; "com\\complus\\dtc\\shared\\util\\initlo"...
0x1800116d4  mov     ecx, eax; int
0x1800116d6  lea     rdx, aFailedToLoadMs; "Failed to load msdtclog.dll"
0x1800116dd  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x1800116e2  mov     ebx, 0C0001019h
0x1800116e7  jmp     loc_180011A93
0x1800116ec  lea     rdx, aDllgetdtclog2; "DllGetDTCLOG2"
0x1800116f3  mov     rcx, rsi; hModule
0x1800116f6  call    cs:__imp_GetProcAddress
0x1800116fc  test    rax, rax
0x1800116ff  jnz     short loc_18001172C
0x180011701  call    cs:__imp_GetLastError
0x180011707  mov     r9d, 0B3h; unsigned int
0x18001170d  lea     r8, aComComplusDtcS_16; "com\\complus\\dtc\\shared\\util\\initlo"...
0x180011714  mov     ecx, eax; int
0x180011716  lea     rdx, aFailedToFindAd; "Failed to find address of DllGetDtcLog2"...
0x18001171d  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180011722  mov     ebx, 0C0001019h
0x180011727  jmp     loc_180011A4A
0x18001172c  lea     r8, [rsp+900h+var_8B0]
0x180011731  lea     rdx, IID_ILogCreateStorage2W
0x180011738  lea     rcx, CLSID_CLogMgr
0x18001173f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011744  test    eax, eax
0x180011746  jz      short loc_18001175F
0x180011748  mov     r9d, 0BAh
0x18001174e  lea     rdx, aInitlogFailedD; "::InitLog - Failed: DllGetDTCLOG(...)"
0x180011755  mov     ebx, 0C0001019h
0x18001175a  jmp     loc_180011A3C
0x18001175f  mov     rcx, r15; unsigned __int16 *
0x180011762  call    ?SZStripLastBSW@@YAPEAGPEAG@Z; SZStripLastBSW(ushort *)
0x180011767  mov     r9, rax
0x18001176a  lea     r8, aSS_1; "%s\\%s"
0x180011771  lea     rax, aMsdtcLog; "MSDTC.LOG"
0x180011778  mov     edx, 105h; unsigned __int64
0x18001177d  lea     rcx, [rsp+900h+var_890]; unsigned __int16 *
0x180011782  mov     qword ptr [rsp+900h+dwOptions], rax
0x180011787  call    ?TracedStringCchPrintfW@@YAXPEAG_KPEBGZZ; TracedStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001178c  mov     r10, [rsp+900h+var_8B0]
0x180011791  lea     rdx, [rsp+900h+var_890]
0x180011796  cmp     [rbp+800h+arg_30], r13d
0x18001179d  mov     ecx, r13d
0x1800117a0  mov     r8d, [rbp+800h+arg_28]
0x1800117a7  setz    cl
0x1800117aa  mov     dword ptr [rsp+900h+phkResult], edi
0x1800117ae  mov     rax, [r10]
0x1800117b1  xor     r9d, r9d
0x1800117b4  mov     dword ptr [rsp+900h+lpSecurityAttributes], ebx
0x1800117b8  mov     [rsp+900h+samDesired], r14d
0x1800117bd  mov     [rsp+900h+dwOptions], ecx
0x1800117c1  mov     rcx, r10
0x1800117c4  mov     rax, [rax+18h]
0x1800117c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117cd  mov     ebx, eax
0x1800117cf  cmp     eax, 80070050h
0x1800117d4  jz      loc_18001188B
0x1800117da  cmp     eax, 800700B7h
0x1800117df  jz      loc_18001188B
0x1800117e5  test    eax, eax
0x1800117e7  jz      short loc_18001181A
0x1800117e9  mov     r9d, 0E9h; unsigned int
0x1800117ef  lea     r8, aComComplusDtcS_16; "com\\complus\\dtc\\shared\\util\\initlo"...
0x1800117f6  lea     rdx, aInitlogFailedP_0; "::InitLog - Failed: piLogCreateStorage-"...
0x1800117fd  mov     ecx, eax; int
0x1800117ff  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180011804  mov     rcx, [rsp+900h+var_8B0]
0x180011809  mov     rax, [rcx]
0x18001180c  mov     rax, [rax+10h]
0x180011810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011815  jmp     loc_180011A4A
0x18001181a  mov     rcx, [rsp+900h+var_8B0]
0x18001181f  lea     rdx, aStreamname; "Streamname"
0x180011826  mov     rax, [rcx]
0x180011829  mov     rax, [rax+20h]
0x18001182d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011832  mov     rcx, [rsp+900h+var_8B0]
0x180011837  mov     ebx, eax
0x180011839  mov     rax, [rcx]
0x18001183c  mov     rax, [rax+10h]
0x180011840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011845  test    ebx, ebx
0x180011847  jz      short loc_18001185B
0x180011849  mov     r9d, 0D4h
0x18001184f  lea     rdx, aInitlogFailedP; "::InitLog - Failed: piLogCreateStorage-"...
0x180011856  jmp     loc_180011A3C
0x18001185b  mov     rcx, r15; unsigned __int16 *
0x18001185e  call    ?SZStripLastBSW@@YAPEAGPEAG@Z; SZStripLastBSW(ushort *)
0x180011863  mov     rdx, rax; unsigned __int16 *
0x180011866  xor     r8d, r8d; int
0x180011869  mov     rcx, r12; struct ITmInstance *
0x18001186c  call    ?SetSddlOnLogFile@@YAJPEAUITmInstance@@PEAGH@Z; SetSddlOnLogFile(ITmInstance *,ushort *,int)
0x180011871  mov     ebx, eax
0x180011873  test    eax, eax
0x180011875  jns     short loc_18001189F
0x180011877  mov     r9d, 0DCh
0x18001187d  lea     rdx, aResetlogSetsdd_0; "ResetLog: SetSddlOnLogFile FAILED"
0x180011884  mov     ecx, eax
0x180011886  jmp     loc_180011A3E
0x18001188b  mov     rcx, [rsp+900h+var_8B0]
0x180011890  mov     rax, [rcx]
0x180011893  mov     rax, [rax+10h]
0x180011897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001189c  mov     ebx, r13d
0x18001189f  call    ?GetDefaultLogPath@@YAPEAGXZ; GetDefaultLogPath(void)
0x1800118a4  lea     rcx, aDtctraceLog; "dtctrace.log"
0x1800118ab  mov     r9, rax
0x1800118ae  mov     qword ptr [rsp+900h+samDesired], rcx
0x1800118b3  lea     r8, aSSS; "%s\\%s\\%s"
0x1800118ba  lea     rcx, aTrace; "trace"
0x1800118c1  mov     edx, 105h; unsigned __int64
0x1800118c6  mov     qword ptr [rsp+900h+dwOptions], rcx
0x1800118cb  lea     rcx, [rbp+800h+var_680]; unsigned __int16 *
0x1800118d2  call    ?TracedStringCchPrintfW@@YAXPEAG_KPEBGZZ; TracedStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800118d7  lea     rax, [rbp+800h+var_680]
0x1800118de  mov     [rsp+900h+lpSecurityAttributes], r13
0x1800118e3  mov     qword ptr [rsp+900h+samDesired], rax
0x1800118e8  lea     r9, [rsp+900h+var_890]
0x1800118ed  lea     r8, aSCSC; "%s%c%s%c"
0x1800118f4  mov     qword ptr [rsp+900h+dwOptions], r13
0x1800118f9  mov     edx, 20Bh; unsigned __int64
0x1800118fe  lea     rcx, [rbp+800h+Data]; unsigned __int16 *
0x180011905  call    ?TracedStringCchPrintfW@@YAXPEAG_KPEBGZZ; TracedStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001190a  lea     rax, [rsp+900h+dwDisposition]
0x18001190f  xor     r8d, r8d; Reserved
0x180011912  mov     [rsp+900h+lpdwDisposition], rax; lpdwDisposition
0x180011917  lea     r9, cchOriginalDestLength; lpClass
0x18001191e  lea     rax, [rsp+900h+hKey]
0x180011923  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001192a  mov     [rsp+900h+phkResult], rax; phkResult
0x18001192f  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Bac"...
0x180011936  mov     [rsp+900h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18001193b  mov     [rsp+900h+samDesired], 2001Bh; samDesired
0x180011943  mov     [rsp+900h+dwOptions], r13d; dwOptions
0x180011948  call    cs:__imp_RegCreateKeyExW
0x18001194e  test    eax, eax
0x180011950  jz      short loc_180011974
0x180011952  mov     edi, 80070000h
0x180011957  jg      short loc_18001195D
0x180011959  mov     ebx, eax
0x18001195b  jmp     short loc_180011962
0x18001195d  movzx   ebx, ax
0x180011960  or      ebx, edi
0x180011962  mov     r9d, 110h
0x180011968  lea     rdx, aInitlogFailedR; "::InitLog - Failed: RegOpenKey(...) on "...
0x18001196f  jmp     loc_180011A02
0x180011974  mov     rcx, [rsp+900h+hKey]; hKey
0x180011979  lea     rdx, aMsDistributedT; "MS Distributed Transaction Coordinatior"
0x180011980  call    cs:__imp_RegDeleteValueW
0x180011986  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001198a  lea     rdx, [rsp+900h+var_890]
0x18001198f  mov     rcx, rax
0x180011992  inc     rcx
0x180011995  cmp     [rdx+rcx*2], r13w
0x18001199a  jnz     short loc_180011992
0x18001199c  lea     rdx, [rbp+800h+var_680]
0x1800119a3  inc     rax
0x1800119a6  cmp     [rdx+rax*2], r13w
0x1800119ab  jnz     short loc_1800119A3
0x1800119ad  add     eax, ecx
0x1800119af  lea     rdx, aMsDistributedT_0; "MS Distributed Transaction Coordinator"
0x1800119b6  mov     rcx, [rsp+900h+hKey]; hKey
0x1800119bb  mov     r9d, 7; dwType
0x1800119c1  xor     r8d, r8d; Reserved
0x1800119c4  lea     eax, ds:6[rax*2]
0x1800119cb  mov     [rsp+900h+samDesired], eax; cbData
0x1800119cf  lea     rax, [rbp+800h+Data]
0x1800119d6  mov     qword ptr [rsp+900h+dwOptions], rax; lpData
0x1800119db  call    cs:__imp_RegSetValueExW
0x1800119e1  mov     edi, 80070000h
0x1800119e6  test    eax, eax
0x1800119e8  jz      short loc_180011A10
0x1800119ea  jg      short loc_1800119F0
0x1800119ec  mov     ebx, eax
0x1800119ee  jmp     short loc_1800119F5
0x1800119f0  movzx   ebx, ax
0x1800119f3  or      ebx, edi
0x1800119f5  mov     r9d, 125h; unsigned int
0x1800119fb  lea     rdx, aInitlogFailedR_0; "::InitLog - Failed: RegSetValueEx(...)"
0x180011a02  lea     r8, aComComplusDtcS_16; "com\\complus\\dtc\\shared\\util\\initlo"...
0x180011a09  mov     ecx, ebx; int
0x180011a0b  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180011a10  mov     rcx, [rsp+900h+hKey]; hKey
0x180011a15  test    rcx, rcx
0x180011a18  jz      short loc_180011A4A
0x180011a1a  call    cs:__imp_RegCloseKey
0x180011a20  test    eax, eax
0x180011a22  jz      short loc_180011A4A
0x180011a24  jg      short loc_180011A2A
0x180011a26  mov     ebx, eax
0x180011a28  jmp     short loc_180011A2F
0x180011a2a  movzx   ebx, ax
0x180011a2d  or      ebx, edi
0x180011a2f  mov     r9d, 132h; unsigned int
0x180011a35  lea     rdx, aInitlogFailedR_1; "::InitLog - Failed: RegCloseKey(...)"
0x180011a3c  mov     ecx, ebx; int
0x180011a3e  lea     r8, aComComplusDtcS_16; "com\\complus\\dtc\\shared\\util\\initlo"...
0x180011a45  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180011a4a  mov     rcx, rsi; hLibModule
0x180011a4d  call    cs:__imp_FreeLibrary
0x180011a53  jmp     short loc_180011A93
0x180011a55  mov     r9d, 0A1h
0x180011a5b  lea     rdx, aInitlogConditi; "::InitLog - Condition failed: dwFlush <"...
0x180011a62  jmp     short loc_180011A80
0x180011a64  mov     r9d, 9Ah
0x180011a6a  lea     rdx, aInitlogConditi_0; "::InitLog - Condition failed: dwCheckpo"...
0x180011a71  jmp     short loc_180011A80
0x180011a73  mov     r9d, 93h; unsigned int
0x180011a79  lea     rdx, aInitlogConditi_1; "::InitLog - Condition failed: dwTimer <"...
0x180011a80  mov     ebx, 0C0001028h
0x180011a85  lea     r8, aComComplusDtcS_16; "com\\complus\\dtc\\shared\\util\\initlo"...
0x180011a8c  mov     ecx, ebx; int
0x180011a8e  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x180011a93  mov     eax, ebx
0x180011a95  mov     rcx, [rbp+800h+var_50]
0x180011a9c  xor     rcx, rsp; StackCookie
0x180011a9f  call    __security_check_cookie
0x180011aa4  add     rsp, 8C8h
0x180011aab  pop     r15
0x180011aad  pop     r14
0x180011aaf  pop     r13
0x180011ab1  pop     r12
0x180011ab3  pop     rdi
0x180011ab4  pop     rsi
0x180011ab5  pop     rbx
0x180011ab6  pop     rbp
0x180011ab7  retn
```
