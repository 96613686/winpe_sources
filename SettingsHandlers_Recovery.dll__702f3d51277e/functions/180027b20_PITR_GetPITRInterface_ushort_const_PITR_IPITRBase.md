# PITR::GetPITRInterface(ushort const *,PITR::IPITRBase * *)

- ea: `0x180027b20`
- end: `0x180027fbc`
- name: `?GetPITRInterface@PITR@@YAJPEBGPEAPEAUIPITRBase@1@@Z`
- size: `1180`
- prototype: `__int64 __fastcall(PITR *__hidden this, const unsigned __int16 *, struct PITR::IPITRBase **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000bf24`

## callees

- `0x18000bef4`
- `0x180027b20`
- `0x1800282d4`
- `0x1800284c8`
- `0x1800285a4`
- `0x180029014`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027e50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180027e50`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180027d59`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180027d59`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027f82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027f82`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027b9a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027b9a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180027b8d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180027b8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027f8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027f8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027f9b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027f9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027cf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027da3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027dbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027dd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027efc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027cf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027da3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027dbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027dd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027e8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027efc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180027bf3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180027bf3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180027b43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180027b54`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180027f69`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180027b43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180027b54`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180027f69`
- `WDSCORE!WdsSetupLogMessageW` at `0x180027f63`
- `WDSCORE!WdsSetupLogMessageW` at `0x180027f63`
- `WDSCORE!CurrentIP` at `0x180027c0b`
- `WDSCORE!CurrentIP` at `0x180027c89`
- `WDSCORE!CurrentIP` at `0x180027cf8`
- `WDSCORE!CurrentIP` at `0x180027ddb`
- `WDSCORE!CurrentIP` at `0x180027e97`
- `WDSCORE!CurrentIP` at `0x180027f04`
- `WDSCORE!CurrentIP` at `0x180027c0b`
- `WDSCORE!CurrentIP` at `0x180027c89`
- `WDSCORE!CurrentIP` at `0x180027cf8`
- `WDSCORE!CurrentIP` at `0x180027ddb`
- `WDSCORE!CurrentIP` at `0x180027e97`
- `WDSCORE!CurrentIP` at `0x180027f04`

## string_xrefs

- `0x180027bd2`: `%windir%\System32\OOBE\PITR.dll`
- `0x180027de4`: `PITR::GetPITRInterface: LoadLibraryEx failed for %s. Error: 0x%08X`

## pseudocode

```c
__int64 __fastcall PITR::GetPITRInterface(PITR *this, const unsigned __int16 *a2, struct PITR::IPITRBase **a3)
{
  DWORD TickCount; // r14d
  DWORD v5; // eax
  char *v7; // rbp
  const WCHAR *Expand; // rax
  signed int IsFileMicrosoftTrusted; // esi
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
  if ( !_InterlockedCompareExchange(&dword_180059FC0, 1, 0) )
    InitializeCriticalSection(&stru_18005A210);
  EnterCriticalSection(&stru_18005A210);
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
  LeaveCriticalSection(&stru_18005A210);
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
0x180027b20  mov     [rsp+arg_8], rbx
0x180027b25  mov     [rsp+arg_10], rbp
0x180027b2a  mov     [rsp+arg_0], rcx
0x180027b2f  push    rsi
0x180027b30  push    rdi
0x180027b31  push    r12
0x180027b33  push    r14
0x180027b35  push    r15
0x180027b37  sub     rsp, 60h
0x180027b3b  mov     rbx, rdx
0x180027b3e  call    ?PITRTelemetryInitialize@@YAJXZ; PITRTelemetryInitialize(void)
0x180027b43  call    cs:__imp_GetTickCount
0x180027b49  xor     r15d, r15d
0x180027b4c  mov     r14d, eax
0x180027b4f  test    rbx, rbx
0x180027b52  jnz     short loc_180027B72
0x180027b54  call    cs:__imp_GetTickCount
0x180027b5a  sub     eax, r14d
0x180027b5d  mov     ebx, 80070057h
0x180027b62  mov     edx, eax; unsigned int
0x180027b64  mov     ecx, ebx; int
0x180027b66  call    ?PITRTelemetryLogInterfaceCreation@@YAXJK@Z; PITRTelemetryLogInterfaceCreation(long,ulong)
0x180027b6b  mov     eax, ebx
0x180027b6d  jmp     loc_180027FA3
0x180027b72  xor     eax, eax
0x180027b74  mov     rbp, r15
0x180027b77  lea     r12d, [rax+1]
0x180027b7b  lock cmpxchg cs:dword_180059FC0, r12d
0x180027b84  jnz     short loc_180027B93
0x180027b86  lea     rcx, stru_18005A210; lpCriticalSection
0x180027b8d  call    cs:__imp_InitializeCriticalSection
0x180027b93  lea     rcx, stru_18005A210; lpCriticalSection
0x180027b9a  call    cs:__imp_EnterCriticalSection
0x180027ba0  mov     rax, cs:?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x180027ba7  lea     rdi, ?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x180027bae  lea     rdx, [rsp+88h+arg_0]
0x180027bb6  mov     [rsp+88h+arg_0], r15
0x180027bbe  mov     rcx, rdi
0x180027bc1  mov     rax, [rax+38h]
0x180027bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bca  test    al, al
0x180027bcc  jz      loc_180027E33
0x180027bd2  lea     rcx, aWindirSystem32; "%windir%\\System32\\OOBE\\PITR.dll"
0x180027bd9  call    AllocateExpand
0x180027bde  mov     rbp, rax
0x180027be1  test    rax, rax
0x180027be4  jnz     short loc_180027BF0
0x180027be6  mov     esi, 80070008h
0x180027beb  jmp     loc_180027F69
0x180027bf0  mov     rcx, rbp; lpFileName
0x180027bf3  call    cs:__imp_GetFileAttributesW
0x180027bf9  cmp     eax, 0FFFFFFFFh
0x180027bfc  jnz     short loc_180027C63
0x180027bfe  mov     esi, 80070490h
0x180027c03  call    cs:__imp_GetLastError
0x180027c09  mov     edi, eax
0x180027c0b  call    cs:__imp_CurrentIP
0x180027c11  mov     r9d, esi
0x180027c14  lea     rdx, aPitrGetpitrint_5; "PITR::GetPITRInterface: %s not found. E"...
0x180027c1b  mov     r8, rbp
0x180027c1e  mov     ecx, 2000000h; unsigned int
0x180027c23  mov     rbx, rax
0x180027c26  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180027c2b  mov     [rsp+88h+var_38], r15d
0x180027c30  lea     rcx, aPitrGetpitrint_0; "PITR::GetPITRInterface"
0x180027c37  mov     [rsp+88h+var_40], r15
0x180027c3c  mov     [rsp+88h+var_48], edi
0x180027c40  mov     [rsp+88h+var_50], rbx
0x180027c45  mov     [rsp+88h+var_58], rcx
0x180027c4a  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x180027c51  mov     [rsp+88h+var_60], rcx
0x180027c56  mov     [rsp+88h+var_68], 1C0h
0x180027c5e  jmp     loc_180027F54
0x180027c63  lea     rdx, [rsp+88h+arg_0]; int *
0x180027c6b  mov     dword ptr [rsp+88h+arg_0], r15d
0x180027c73  mov     rcx, rbp; unsigned __int16 *
0x180027c76  call    ?pIsFileMicrosoftTrusted@@YAJPEBGPEAH@Z; pIsFileMicrosoftTrusted(ushort const *,int *)
0x180027c7b  mov     esi, eax
0x180027c7d  test    eax, eax
0x180027c7f  jns     short loc_180027CE1
0x180027c81  call    cs:__imp_GetLastError
0x180027c87  mov     edi, eax
0x180027c89  call    cs:__imp_CurrentIP
0x180027c8f  mov     r9d, esi
0x180027c92  lea     rdx, aPitrGetpitrint; "PITR::GetPITRInterface: Failed to valid"...
0x180027c99  mov     r8, rbp
0x180027c9c  mov     ecx, 2000000h; unsigned int
0x180027ca1  mov     rbx, rax
0x180027ca4  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180027ca9  mov     [rsp+88h+var_38], r15d
0x180027cae  lea     rcx, aPitrGetpitrint_0; "PITR::GetPITRInterface"
0x180027cb5  mov     [rsp+88h+var_40], r15
0x180027cba  mov     [rsp+88h+var_48], edi
0x180027cbe  mov     [rsp+88h+var_50], rbx
0x180027cc3  mov     [rsp+88h+var_58], rcx
0x180027cc8  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x180027ccf  mov     [rsp+88h+var_60], rcx
0x180027cd4  mov     [rsp+88h+var_68], 1CBh
0x180027cdc  jmp     loc_180027F54
0x180027ce1  cmp     dword ptr [rsp+88h+arg_0], r15d
0x180027ce9  jnz     short loc_180027D50
0x180027ceb  mov     esi, 800706FEh
0x180027cf0  call    cs:__imp_GetLastError
0x180027cf6  mov     edi, eax
0x180027cf8  call    cs:__imp_CurrentIP
0x180027cfe  mov     r9d, esi
0x180027d01  lea     rdx, aPitrGetpitrint_1; "PITR::GetPITRInterface: %s is not trust"...
0x180027d08  mov     r8, rbp
0x180027d0b  mov     ecx, 2000000h; unsigned int
0x180027d10  mov     rbx, rax
0x180027d13  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180027d18  mov     [rsp+88h+var_38], r15d
0x180027d1d  lea     rcx, aPitrGetpitrint_0; "PITR::GetPITRInterface"
0x180027d24  mov     [rsp+88h+var_40], r15
0x180027d29  mov     [rsp+88h+var_48], edi
0x180027d2d  mov     [rsp+88h+var_50], rbx
0x180027d32  mov     [rsp+88h+var_58], rcx
0x180027d37  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x180027d3e  mov     [rsp+88h+var_60], rcx
0x180027d43  mov     [rsp+88h+var_68], 1D2h
0x180027d4b  jmp     loc_180027F54
0x180027d50  xor     edx, edx; hFile
0x180027d52  mov     rcx, rbp; lpLibFileName
0x180027d55  lea     r8d, [rdx+8]; dwFlags
0x180027d59  call    cs:__imp_LoadLibraryExW
0x180027d5f  mov     rcx, cs:?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x180027d66  mov     rdx, rax
0x180027d69  mov     r8, [rcx+30h]
0x180027d6d  mov     rcx, rdi
0x180027d70  mov     rax, r8
0x180027d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d78  mov     rax, cs:?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x180027d7f  lea     rdx, [rsp+88h+arg_0]
0x180027d87  mov     rcx, rdi
0x180027d8a  mov     [rsp+88h+arg_0], r15
0x180027d92  mov     rax, [rax+38h]
0x180027d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d9b  test    al, al
0x180027d9d  jz      loc_180027E33
0x180027da3  call    cs:__imp_GetLastError
0x180027da9  mov     ebx, 80070000h
0x180027dae  test    eax, eax
0x180027db0  jle     short loc_180027DB9
0x180027db2  movzx   eax, ax
0x180027db5  or      eax, ebx
0x180027db7  test    eax, eax
0x180027db9  jns     short loc_180027DCE
0x180027dbb  call    cs:__imp_GetLastError
0x180027dc1  mov     esi, eax
0x180027dc3  test    eax, eax
0x180027dc5  jle     short loc_180027DD3
0x180027dc7  movzx   esi, ax
0x180027dca  or      esi, ebx
0x180027dcc  jmp     short loc_180027DD3
0x180027dce  mov     esi, 80004005h
0x180027dd3  call    cs:__imp_GetLastError
0x180027dd9  mov     edi, eax
0x180027ddb  call    cs:__imp_CurrentIP
0x180027de1  mov     r9d, esi
0x180027de4  lea     rdx, aPitrGetpitrint_3; "PITR::GetPITRInterface: LoadLibraryEx f"...
0x180027deb  mov     r8, rbp
0x180027dee  mov     ecx, 2000000h; unsigned int
0x180027df3  mov     rbx, rax
0x180027df6  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180027dfb  mov     [rsp+88h+var_38], r15d
0x180027e00  lea     rcx, aPitrGetpitrint_0; "PITR::GetPITRInterface"
0x180027e07  mov     [rsp+88h+var_40], r15
0x180027e0c  mov     [rsp+88h+var_48], edi
0x180027e10  mov     [rsp+88h+var_50], rbx
0x180027e15  mov     [rsp+88h+var_58], rcx
0x180027e1a  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x180027e21  mov     [rsp+88h+var_60], rcx
0x180027e26  mov     [rsp+88h+var_68], 1DCh
0x180027e2e  jmp     loc_180027F54
0x180027e33  mov     rax, cs:?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x180027e3a  mov     rcx, rdi
0x180027e3d  mov     rax, [rax+20h]
0x180027e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e46  mov     rcx, rax; hModule
0x180027e49  lea     rdx, aGetpitrinterfa; "GetPITRInterface_Internal"
0x180027e50  call    cs:__imp_GetProcAddress
0x180027e56  test    rax, rax
0x180027e59  jnz     loc_180027EE9
0x180027e5f  call    cs:__imp_GetLastError
0x180027e65  mov     ebx, 80070000h
0x180027e6a  test    eax, eax
0x180027e6c  jle     short loc_180027E75
0x180027e6e  movzx   eax, ax
0x180027e71  or      eax, ebx
0x180027e73  test    eax, eax
0x180027e75  jns     short loc_180027E8A
0x180027e77  call    cs:__imp_GetLastError
0x180027e7d  mov     esi, eax
0x180027e7f  test    eax, eax
0x180027e81  jle     short loc_180027E8F
0x180027e83  movzx   esi, ax
0x180027e86  or      esi, ebx
0x180027e88  jmp     short loc_180027E8F
0x180027e8a  mov     esi, 80004005h
0x180027e8f  call    cs:__imp_GetLastError
0x180027e95  mov     edi, eax
0x180027e97  call    cs:__imp_CurrentIP
0x180027e9d  mov     r8d, esi
0x180027ea0  lea     rdx, aPitrGetpitrint_4; "PITR::GetPITRInterface: GetProcAddress "...
0x180027ea7  mov     ecx, 2000000h; unsigned int
0x180027eac  mov     rbx, rax
0x180027eaf  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180027eb4  mov     [rsp+88h+var_38], r15d
0x180027eb9  lea     rcx, aPitrGetpitrint_0; "PITR::GetPITRInterface"
0x180027ec0  mov     [rsp+88h+var_40], r15
0x180027ec5  mov     [rsp+88h+var_48], edi
0x180027ec9  mov     [rsp+88h+var_50], rbx
0x180027ece  mov     [rsp+88h+var_58], rcx
0x180027ed3  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x180027eda  mov     [rsp+88h+var_60], rcx
0x180027edf  mov     [rsp+88h+var_68], 1E6h
0x180027ee7  jmp     short loc_180027F54
0x180027ee9  mov     r8, rbx
0x180027eec  mov     edx, r12d
0x180027eef  xor     ecx, ecx
0x180027ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ef6  mov     esi, eax
0x180027ef8  test    eax, eax
0x180027efa  jns     short loc_180027F7B
0x180027efc  call    cs:__imp_GetLastError
0x180027f02  mov     edi, eax
0x180027f04  call    cs:__imp_CurrentIP
0x180027f0a  mov     r8d, esi
0x180027f0d  lea     rdx, aPitrGetpitrint_2; "PITR::GetPITRInterface: GetPITRInterfac"...
0x180027f14  mov     ecx, 2000000h; unsigned int
0x180027f19  mov     rbx, rax
0x180027f1c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180027f21  mov     [rsp+88h+var_38], r15d
0x180027f26  lea     rcx, aPitrGetpitrint_0; "PITR::GetPITRInterface"
0x180027f2d  mov     [rsp+88h+var_40], r15
0x180027f32  mov     [rsp+88h+var_48], edi
0x180027f36  mov     [rsp+88h+var_50], rbx
0x180027f3b  mov     [rsp+88h+var_58], rcx
0x180027f40  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x180027f47  mov     [rsp+88h+var_60], rcx
0x180027f4c  mov     [rsp+88h+var_68], 1EEh
0x180027f54  xor     r9d, r9d
0x180027f57  lea     r8, aD; "D"
0x180027f5e  xor     edx, edx
0x180027f60  mov     rcx, rax
0x180027f63  call    cs:__imp_WdsSetupLogMessageW
0x180027f69  call    cs:__imp_GetTickCount
0x180027f6f  sub     eax, r14d
0x180027f72  mov     ecx, esi; int
0x180027f74  mov     edx, eax; unsigned int
0x180027f76  call    ?PITRTelemetryLogInterfaceCreation@@YAXJK@Z; PITRTelemetryLogInterfaceCreation(long,ulong)
0x180027f7b  lea     rcx, stru_18005A210; lpCriticalSection
0x180027f82  call    cs:__imp_LeaveCriticalSection
0x180027f88  test    rbp, rbp
0x180027f8b  jz      short loc_180027FA1
0x180027f8d  call    cs:__imp_GetProcessHeap
0x180027f93  mov     r8, rbp; lpMem
0x180027f96  xor     edx, edx; dwFlags
0x180027f98  mov     rcx, rax; hHeap
0x180027f9b  call    cs:__imp_HeapFree
0x180027fa1  mov     eax, esi
0x180027fa3  lea     r11, [rsp+88h+var_28]
0x180027fa8  mov     rbx, [r11+38h]
0x180027fac  mov     rbp, [r11+40h]
0x180027fb0  mov     rsp, r11
0x180027fb3  pop     r15
0x180027fb5  pop     r14
0x180027fb7  pop     r12
0x180027fb9  pop     rdi
0x180027fba  pop     rsi
0x180027fbb  retn
```
