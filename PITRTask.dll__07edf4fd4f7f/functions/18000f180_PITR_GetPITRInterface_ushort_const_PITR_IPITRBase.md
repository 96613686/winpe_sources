# PITR::GetPITRInterface(ushort const *,PITR::IPITRBase * *)

- ea: `0x18000f180`
- end: `0x18000f61c`
- name: `?GetPITRInterface@PITR@@YAJPEBGPEAPEAUIPITRBase@1@@Z`
- size: `1180`
- prototype: `__int64 __fastcall(PITR *__hidden this, const unsigned __int16 *, struct PITR::IPITRBase **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000a4f0`

## callees

- `0x180004664`
- `0x18000ece8`
- `0x18000ee38`
- `0x18000f180`
- `0x18000f934`
- `0x18000fb28`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f4b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f4b0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000f3b9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000f3b9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000f253`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000f253`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000f1ed`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000f1ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f5e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f5e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f1fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f1fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f5ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f5ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f5fb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f5fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f263`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f350`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f403`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f41b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f55c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f263`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f350`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f403`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f41b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f433`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f4ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f55c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f1a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f1b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f5c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f1a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f1b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f5c9`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000f5c3`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000f5c3`
- `WDSCORE!CurrentIP` at `0x18000f26b`
- `WDSCORE!CurrentIP` at `0x18000f2e9`
- `WDSCORE!CurrentIP` at `0x18000f358`
- `WDSCORE!CurrentIP` at `0x18000f43b`
- `WDSCORE!CurrentIP` at `0x18000f4f7`
- `WDSCORE!CurrentIP` at `0x18000f564`
- `WDSCORE!CurrentIP` at `0x18000f26b`
- `WDSCORE!CurrentIP` at `0x18000f2e9`
- `WDSCORE!CurrentIP` at `0x18000f358`
- `WDSCORE!CurrentIP` at `0x18000f43b`
- `WDSCORE!CurrentIP` at `0x18000f4f7`
- `WDSCORE!CurrentIP` at `0x18000f564`

## string_xrefs

- `0x18000f232`: `%windir%\System32\OOBE\PITR.dll`
- `0x18000f444`: `PITR::GetPITRInterface: LoadLibraryEx failed for %s. Error: 0x%08X`

## pseudocode

```c
__int64 __fastcall PITR::GetPITRInterface(PITR *this, const unsigned __int16 *a2, struct PITR::IPITRBase **a3)
{
  DWORD TickCount; // r14d
  DWORD v5; // eax
  char *v7; // rbp
  const WCHAR *Expand; // rax
  int IsFileMicrosoftTrusted; // esi
  DWORD LastError; // edi
  __int64 v11; // rbx
  struct tagLOG_PARTIAL_MSG *v12; // rax
  DWORD v13; // edi
  __int64 v14; // rbx
  struct tagLOG_PARTIAL_MSG *v15; // rax
  DWORD v16; // edi
  __int64 v17; // rbx
  struct tagLOG_PARTIAL_MSG *v18; // rax
  HMODULE Library; // rax
  signed int v20; // eax
  bool v21; // sf
  signed int v22; // eax
  DWORD v23; // edi
  __int64 v24; // rbx
  struct tagLOG_PARTIAL_MSG *v25; // rax
  HMODULE v26; // rax
  FARPROC ProcAddress; // rax
  signed int v28; // eax
  bool v29; // sf
  signed int v30; // eax
  DWORD v31; // edi
  __int64 v32; // rbx
  struct tagLOG_PARTIAL_MSG *v33; // rax
  DWORD v34; // edi
  __int64 v35; // rbx
  struct tagLOG_PARTIAL_MSG *v36; // rax
  DWORD v37; // eax
  HANDLE ProcessHeap; // rax
  PITR *v39; // [rsp+90h] [rbp+8h] BYREF

  v39 = this;
  PITRTelemetryInitialize();
  TickCount = GetTickCount();
  if ( !a2 )
  {
    v5 = GetTickCount();
    PITRTelemetryLogInterfaceCreation(-2147024809, v5 - TickCount);
    return 2147942487LL;
  }
  v7 = 0;
  if ( !_InterlockedCompareExchange(&dword_18001BFB4, 1, 0) )
    InitializeCriticalSection(&stru_18001BFF0);
  EnterCriticalSection(&stru_18001BFF0);
  v39 = 0;
  if ( ((unsigned __int8 (__fastcall *)(void ***, PITR **))g_PitrDll[7])(&g_PitrDll, &v39) )
  {
    Expand = (const WCHAR *)AllocateExpand(L"%windir%\\System32\\OOBE\\PITR.dll");
    v7 = (char *)Expand;
    if ( !Expand )
    {
      IsFileMicrosoftTrusted = -2147024888;
LABEL_32:
      v37 = GetTickCount();
      PITRTelemetryLogInterfaceCreation(IsFileMicrosoftTrusted, v37 - TickCount);
      goto LABEL_33;
    }
    if ( GetFileAttributesW(Expand) == -1 )
    {
      IsFileMicrosoftTrusted = -2147023728;
      LastError = GetLastError();
      v11 = CurrentIP();
      v12 = ConstructPartialMsgW(0x2000000u, "PITR::GetPITRInterface: %s not found. Error: 0x%08X", v7, -2147023728);
      WdsSetupLogMessageW(
        v12,
        0,
        L"D",
        0,
        448,
        L"base\\diagnosis\\srt\\pitr\\lib\\src\\pitr.cpp",
        L"PITR::GetPITRInterface",
        v11,
        LastError,
        0,
        0);
      goto LABEL_32;
    }
    LODWORD(v39) = 0;
    IsFileMicrosoftTrusted = pIsFileMicrosoftTrusted((const unsigned __int16 *)v7, (int *)&v39);
    if ( IsFileMicrosoftTrusted < 0 )
    {
      v13 = GetLastError();
      v14 = CurrentIP();
      v15 = ConstructPartialMsgW(
              0x2000000u,
              "PITR::GetPITRInterface: Failed to validate trust for %s. Error: 0x%08X",
              v7,
              IsFileMicrosoftTrusted);
      WdsSetupLogMessageW(
        v15,
        0,
        L"D",
        0,
        459,
        L"base\\diagnosis\\srt\\pitr\\lib\\src\\pitr.cpp",
        L"PITR::GetPITRInterface",
        v14,
        v13,
        0,
        0);
      goto LABEL_32;
    }
    if ( !(_DWORD)v39 )
    {
      IsFileMicrosoftTrusted = -2147023106;
      v16 = GetLastError();
      v17 = CurrentIP();
      v18 = ConstructPartialMsgW(
              0x2000000u,
              "PITR::GetPITRInterface: %s is not trusted. Error: 0x%08X",
              v7,
              -2147023106);
      WdsSetupLogMessageW(
        v18,
        0,
        L"D",
        0,
        466,
        L"base\\diagnosis\\srt\\pitr\\lib\\src\\pitr.cpp",
        L"PITR::GetPITRInterface",
        v17,
        v16,
        0,
        0);
      goto LABEL_32;
    }
    Library = LoadLibraryExW((LPCWSTR)v7, 0, 8u);
    ((void (__fastcall *)(void ***, HMODULE))g_PitrDll[6])(&g_PitrDll, Library);
    v39 = 0;
    if ( ((unsigned __int8 (__fastcall *)(void ***, PITR **))g_PitrDll[7])(&g_PitrDll, &v39) )
    {
      v20 = GetLastError();
      v21 = v20 < 0;
      if ( v20 > 0 )
        v21 = 1;
      if ( v21 )
      {
        v22 = GetLastError();
        IsFileMicrosoftTrusted = v22;
        if ( v22 > 0 )
          IsFileMicrosoftTrusted = (unsigned __int16)v22 | 0x80070000;
      }
      else
      {
        IsFileMicrosoftTrusted = -2147467259;
      }
      v23 = GetLastError();
      v24 = CurrentIP();
      v25 = ConstructPartialMsgW(
              0x2000000u,
              "PITR::GetPITRInterface: LoadLibraryEx failed for %s. Error: 0x%08X",
              v7,
              IsFileMicrosoftTrusted);
      WdsSetupLogMessageW(
        v25,
        0,
        L"D",
        0,
        476,
        L"base\\diagnosis\\srt\\pitr\\lib\\src\\pitr.cpp",
        L"PITR::GetPITRInterface",
        v24,
        v23,
        0,
        0);
      goto LABEL_32;
    }
  }
  v26 = (HMODULE)((__int64 (__fastcall *)(void ***))g_PitrDll[4])(&g_PitrDll);
  ProcAddress = GetProcAddress(v26, "GetPITRInterface_Internal");
  if ( !ProcAddress )
  {
    v28 = GetLastError();
    v29 = v28 < 0;
    if ( v28 > 0 )
      v29 = 1;
    if ( v29 )
    {
      v30 = GetLastError();
      IsFileMicrosoftTrusted = v30;
      if ( v30 > 0 )
        IsFileMicrosoftTrusted = (unsigned __int16)v30 | 0x80070000;
    }
    else
    {
      IsFileMicrosoftTrusted = -2147467259;
    }
    v31 = GetLastError();
    v32 = CurrentIP();
    v33 = ConstructPartialMsgW(
            0x2000000u,
            "PITR::GetPITRInterface: GetProcAddress failed for GetPITRInterface_Internal. Error: 0x%08X",
            IsFileMicrosoftTrusted);
    WdsSetupLogMessageW(
      v33,
      0,
      L"D",
      0,
      486,
      L"base\\diagnosis\\srt\\pitr\\lib\\src\\pitr.cpp",
      L"PITR::GetPITRInterface",
      v32,
      v31,
      0,
      0);
    goto LABEL_32;
  }
  IsFileMicrosoftTrusted = ((__int64 (__fastcall *)(_QWORD, __int64, const unsigned __int16 *))ProcAddress)(0, 1, a2);
  if ( IsFileMicrosoftTrusted < 0 )
  {
    v34 = GetLastError();
    v35 = CurrentIP();
    v36 = ConstructPartialMsgW(
            0x2000000u,
            "PITR::GetPITRInterface: GetPITRInterface_Internal failed. Error: 0x%08X",
            IsFileMicrosoftTrusted);
    WdsSetupLogMessageW(
      v36,
      0,
      L"D",
      0,
      494,
      L"base\\diagnosis\\srt\\pitr\\lib\\src\\pitr.cpp",
      L"PITR::GetPITRInterface",
      v35,
      v34,
      0,
      0);
    goto LABEL_32;
  }
LABEL_33:
  LeaveCriticalSection(&stru_18001BFF0);
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
  return (unsigned int)IsFileMicrosoftTrusted;
}

```

## disassembly

```asm
0x18000f180  mov     [rsp+arg_8], rbx
0x18000f185  mov     [rsp+arg_10], rbp
0x18000f18a  mov     [rsp+arg_0], rcx
0x18000f18f  push    rsi
0x18000f190  push    rdi
0x18000f191  push    r12
0x18000f193  push    r14
0x18000f195  push    r15
0x18000f197  sub     rsp, 60h
0x18000f19b  mov     rbx, rdx
0x18000f19e  call    ?PITRTelemetryInitialize@@YAJXZ; PITRTelemetryInitialize(void)
0x18000f1a3  call    cs:__imp_GetTickCount
0x18000f1a9  xor     r15d, r15d
0x18000f1ac  mov     r14d, eax
0x18000f1af  test    rbx, rbx
0x18000f1b2  jnz     short loc_18000F1D2
0x18000f1b4  call    cs:__imp_GetTickCount
0x18000f1ba  sub     eax, r14d
0x18000f1bd  mov     ebx, 80070057h
0x18000f1c2  mov     edx, eax; unsigned int
0x18000f1c4  mov     ecx, ebx; int
0x18000f1c6  call    ?PITRTelemetryLogInterfaceCreation@@YAXJK@Z; PITRTelemetryLogInterfaceCreation(long,ulong)
0x18000f1cb  mov     eax, ebx
0x18000f1cd  jmp     loc_18000F603
0x18000f1d2  xor     eax, eax
0x18000f1d4  mov     rbp, r15
0x18000f1d7  lea     r12d, [rax+1]
0x18000f1db  lock cmpxchg cs:dword_18001BFB4, r12d
0x18000f1e4  jnz     short loc_18000F1F3
0x18000f1e6  lea     rcx, stru_18001BFF0; lpCriticalSection
0x18000f1ed  call    cs:__imp_InitializeCriticalSection
0x18000f1f3  lea     rcx, stru_18001BFF0; lpCriticalSection
0x18000f1fa  call    cs:__imp_EnterCriticalSection
0x18000f200  mov     rax, cs:?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x18000f207  lea     rdi, ?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x18000f20e  lea     rdx, [rsp+88h+arg_0]
0x18000f216  mov     [rsp+88h+arg_0], r15
0x18000f21e  mov     rcx, rdi
0x18000f221  mov     rax, [rax+38h]
0x18000f225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f22a  test    al, al
0x18000f22c  jz      loc_18000F493
0x18000f232  lea     rcx, Src; "%windir%\\System32\\OOBE\\PITR.dll"
0x18000f239  call    AllocateExpand
0x18000f23e  mov     rbp, rax
0x18000f241  test    rax, rax
0x18000f244  jnz     short loc_18000F250
0x18000f246  mov     esi, 80070008h
0x18000f24b  jmp     loc_18000F5C9
0x18000f250  mov     rcx, rbp; lpFileName
0x18000f253  call    cs:__imp_GetFileAttributesW
0x18000f259  cmp     eax, 0FFFFFFFFh
0x18000f25c  jnz     short loc_18000F2C3
0x18000f25e  mov     esi, 80070490h
0x18000f263  call    cs:__imp_GetLastError
0x18000f269  mov     edi, eax
0x18000f26b  call    cs:__imp_CurrentIP
0x18000f271  mov     r9d, esi
0x18000f274  lea     rdx, aPitrGetpitrint_5; "PITR::GetPITRInterface: %s not found. E"...
0x18000f27b  mov     r8, rbp
0x18000f27e  mov     ecx, 2000000h; unsigned int
0x18000f283  mov     rbx, rax
0x18000f286  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000f28b  mov     [rsp+88h+var_38], r15d
0x18000f290  lea     rcx, aPitrGetpitrint_0; "PITR::GetPITRInterface"
0x18000f297  mov     [rsp+88h+var_40], r15
0x18000f29c  mov     [rsp+88h+var_48], edi
0x18000f2a0  mov     [rsp+88h+var_50], rbx
0x18000f2a5  mov     [rsp+88h+var_58], rcx
0x18000f2aa  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x18000f2b1  mov     [rsp+88h+var_60], rcx
0x18000f2b6  mov     [rsp+88h+var_68], 1C0h
0x18000f2be  jmp     loc_18000F5B4
0x18000f2c3  lea     rdx, [rsp+88h+arg_0]; int *
0x18000f2cb  mov     dword ptr [rsp+88h+arg_0], r15d
0x18000f2d3  mov     rcx, rbp; unsigned __int16 *
0x18000f2d6  call    ?pIsFileMicrosoftTrusted@@YAJPEBGPEAH@Z; pIsFileMicrosoftTrusted(ushort const *,int *)
0x18000f2db  mov     esi, eax
0x18000f2dd  test    eax, eax
0x18000f2df  jns     short loc_18000F341
0x18000f2e1  call    cs:__imp_GetLastError
0x18000f2e7  mov     edi, eax
0x18000f2e9  call    cs:__imp_CurrentIP
0x18000f2ef  mov     r9d, esi
0x18000f2f2  lea     rdx, aPitrGetpitrint; "PITR::GetPITRInterface: Failed to valid"...
0x18000f2f9  mov     r8, rbp
0x18000f2fc  mov     ecx, 2000000h; unsigned int
0x18000f301  mov     rbx, rax
0x18000f304  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000f309  mov     [rsp+88h+var_38], r15d
0x18000f30e  lea     rcx, aPitrGetpitrint_0; "PITR::GetPITRInterface"
0x18000f315  mov     [rsp+88h+var_40], r15
0x18000f31a  mov     [rsp+88h+var_48], edi
0x18000f31e  mov     [rsp+88h+var_50], rbx
0x18000f323  mov     [rsp+88h+var_58], rcx
0x18000f328  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x18000f32f  mov     [rsp+88h+var_60], rcx
0x18000f334  mov     [rsp+88h+var_68], 1CBh
0x18000f33c  jmp     loc_18000F5B4
0x18000f341  cmp     dword ptr [rsp+88h+arg_0], r15d
0x18000f349  jnz     short loc_18000F3B0
0x18000f34b  mov     esi, 800706FEh
0x18000f350  call    cs:__imp_GetLastError
0x18000f356  mov     edi, eax
0x18000f358  call    cs:__imp_CurrentIP
0x18000f35e  mov     r9d, esi
0x18000f361  lea     rdx, aPitrGetpitrint_1; "PITR::GetPITRInterface: %s is not trust"...
0x18000f368  mov     r8, rbp
0x18000f36b  mov     ecx, 2000000h; unsigned int
0x18000f370  mov     rbx, rax
0x18000f373  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000f378  mov     [rsp+88h+var_38], r15d
0x18000f37d  lea     rcx, aPitrGetpitrint_0; "PITR::GetPITRInterface"
0x18000f384  mov     [rsp+88h+var_40], r15
0x18000f389  mov     [rsp+88h+var_48], edi
0x18000f38d  mov     [rsp+88h+var_50], rbx
0x18000f392  mov     [rsp+88h+var_58], rcx
0x18000f397  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x18000f39e  mov     [rsp+88h+var_60], rcx
0x18000f3a3  mov     [rsp+88h+var_68], 1D2h
0x18000f3ab  jmp     loc_18000F5B4
0x18000f3b0  xor     edx, edx; hFile
0x18000f3b2  mov     rcx, rbp; lpLibFileName
0x18000f3b5  lea     r8d, [rdx+8]; dwFlags
0x18000f3b9  call    cs:__imp_LoadLibraryExW
0x18000f3bf  mov     rcx, cs:?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x18000f3c6  mov     rdx, rax
0x18000f3c9  mov     r8, [rcx+30h]
0x18000f3cd  mov     rcx, rdi
0x18000f3d0  mov     rax, r8
0x18000f3d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3d8  mov     rax, cs:?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x18000f3df  lea     rdx, [rsp+88h+arg_0]
0x18000f3e7  mov     rcx, rdi
0x18000f3ea  mov     [rsp+88h+arg_0], r15
0x18000f3f2  mov     rax, [rax+38h]
0x18000f3f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3fb  test    al, al
0x18000f3fd  jz      loc_18000F493
0x18000f403  call    cs:__imp_GetLastError
0x18000f409  mov     ebx, 80070000h
0x18000f40e  test    eax, eax
0x18000f410  jle     short loc_18000F419
0x18000f412  movzx   eax, ax
0x18000f415  or      eax, ebx
0x18000f417  test    eax, eax
0x18000f419  jns     short loc_18000F42E
0x18000f41b  call    cs:__imp_GetLastError
0x18000f421  mov     esi, eax
0x18000f423  test    eax, eax
0x18000f425  jle     short loc_18000F433
0x18000f427  movzx   esi, ax
0x18000f42a  or      esi, ebx
0x18000f42c  jmp     short loc_18000F433
0x18000f42e  mov     esi, 80004005h
0x18000f433  call    cs:__imp_GetLastError
0x18000f439  mov     edi, eax
0x18000f43b  call    cs:__imp_CurrentIP
0x18000f441  mov     r9d, esi
0x18000f444  lea     rdx, aPitrGetpitrint_3; "PITR::GetPITRInterface: LoadLibraryEx f"...
0x18000f44b  mov     r8, rbp
0x18000f44e  mov     ecx, 2000000h; unsigned int
0x18000f453  mov     rbx, rax
0x18000f456  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000f45b  mov     [rsp+88h+var_38], r15d
0x18000f460  lea     rcx, aPitrGetpitrint_0; "PITR::GetPITRInterface"
0x18000f467  mov     [rsp+88h+var_40], r15
0x18000f46c  mov     [rsp+88h+var_48], edi
0x18000f470  mov     [rsp+88h+var_50], rbx
0x18000f475  mov     [rsp+88h+var_58], rcx
0x18000f47a  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x18000f481  mov     [rsp+88h+var_60], rcx
0x18000f486  mov     [rsp+88h+var_68], 1DCh
0x18000f48e  jmp     loc_18000F5B4
0x18000f493  mov     rax, cs:?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x18000f49a  mov     rcx, rdi
0x18000f49d  mov     rax, [rax+20h]
0x18000f4a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4a6  mov     rcx, rax; hModule
0x18000f4a9  lea     rdx, aGetpitrinterfa; "GetPITRInterface_Internal"
0x18000f4b0  call    cs:__imp_GetProcAddress
0x18000f4b6  test    rax, rax
0x18000f4b9  jnz     loc_18000F549
0x18000f4bf  call    cs:__imp_GetLastError
0x18000f4c5  mov     ebx, 80070000h
0x18000f4ca  test    eax, eax
0x18000f4cc  jle     short loc_18000F4D5
0x18000f4ce  movzx   eax, ax
0x18000f4d1  or      eax, ebx
0x18000f4d3  test    eax, eax
0x18000f4d5  jns     short loc_18000F4EA
0x18000f4d7  call    cs:__imp_GetLastError
0x18000f4dd  mov     esi, eax
0x18000f4df  test    eax, eax
0x18000f4e1  jle     short loc_18000F4EF
0x18000f4e3  movzx   esi, ax
0x18000f4e6  or      esi, ebx
0x18000f4e8  jmp     short loc_18000F4EF
0x18000f4ea  mov     esi, 80004005h
0x18000f4ef  call    cs:__imp_GetLastError
0x18000f4f5  mov     edi, eax
0x18000f4f7  call    cs:__imp_CurrentIP
0x18000f4fd  mov     r8d, esi
0x18000f500  lea     rdx, aPitrGetpitrint_4; "PITR::GetPITRInterface: GetProcAddress "...
0x18000f507  mov     ecx, 2000000h; unsigned int
0x18000f50c  mov     rbx, rax
0x18000f50f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000f514  mov     [rsp+88h+var_38], r15d
0x18000f519  lea     rcx, aPitrGetpitrint_0; "PITR::GetPITRInterface"
0x18000f520  mov     [rsp+88h+var_40], r15
0x18000f525  mov     [rsp+88h+var_48], edi
0x18000f529  mov     [rsp+88h+var_50], rbx
0x18000f52e  mov     [rsp+88h+var_58], rcx
0x18000f533  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x18000f53a  mov     [rsp+88h+var_60], rcx
0x18000f53f  mov     [rsp+88h+var_68], 1E6h
0x18000f547  jmp     short loc_18000F5B4
0x18000f549  mov     r8, rbx
0x18000f54c  mov     edx, r12d
0x18000f54f  xor     ecx, ecx
0x18000f551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f556  mov     esi, eax
0x18000f558  test    eax, eax
0x18000f55a  jns     short loc_18000F5DB
0x18000f55c  call    cs:__imp_GetLastError
0x18000f562  mov     edi, eax
0x18000f564  call    cs:__imp_CurrentIP
0x18000f56a  mov     r8d, esi
0x18000f56d  lea     rdx, aPitrGetpitrint_2; "PITR::GetPITRInterface: GetPITRInterfac"...
0x18000f574  mov     ecx, 2000000h; unsigned int
0x18000f579  mov     rbx, rax
0x18000f57c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000f581  mov     [rsp+88h+var_38], r15d
0x18000f586  lea     rcx, aPitrGetpitrint_0; "PITR::GetPITRInterface"
0x18000f58d  mov     [rsp+88h+var_40], r15
0x18000f592  mov     [rsp+88h+var_48], edi
0x18000f596  mov     [rsp+88h+var_50], rbx
0x18000f59b  mov     [rsp+88h+var_58], rcx
0x18000f5a0  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x18000f5a7  mov     [rsp+88h+var_60], rcx
0x18000f5ac  mov     [rsp+88h+var_68], 1EEh
0x18000f5b4  xor     r9d, r9d
0x18000f5b7  lea     r8, aD; "D"
0x18000f5be  xor     edx, edx
0x18000f5c0  mov     rcx, rax
0x18000f5c3  call    cs:__imp_WdsSetupLogMessageW
0x18000f5c9  call    cs:__imp_GetTickCount
0x18000f5cf  sub     eax, r14d
0x18000f5d2  mov     ecx, esi; int
0x18000f5d4  mov     edx, eax; unsigned int
0x18000f5d6  call    ?PITRTelemetryLogInterfaceCreation@@YAXJK@Z; PITRTelemetryLogInterfaceCreation(long,ulong)
0x18000f5db  lea     rcx, stru_18001BFF0; lpCriticalSection
0x18000f5e2  call    cs:__imp_LeaveCriticalSection
0x18000f5e8  test    rbp, rbp
0x18000f5eb  jz      short loc_18000F601
0x18000f5ed  call    cs:__imp_GetProcessHeap
0x18000f5f3  mov     r8, rbp; lpMem
0x18000f5f6  xor     edx, edx; dwFlags
0x18000f5f8  mov     rcx, rax; hHeap
0x18000f5fb  call    cs:__imp_HeapFree
0x18000f601  mov     eax, esi
0x18000f603  lea     r11, [rsp+88h+var_28]
0x18000f608  mov     rbx, [r11+38h]
0x18000f60c  mov     rbp, [r11+40h]
0x18000f610  mov     rsp, r11
0x18000f613  pop     r15
0x18000f615  pop     r14
0x18000f617  pop     r12
0x18000f619  pop     rdi
0x18000f61a  pop     rsi
0x18000f61b  retn
```
