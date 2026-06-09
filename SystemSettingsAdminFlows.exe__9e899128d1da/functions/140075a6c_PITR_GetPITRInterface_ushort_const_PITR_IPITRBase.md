# PITR::GetPITRInterface(ushort const *,PITR::IPITRBase * *)

- ea: `0x140075a6c`
- end: `0x140075eec`
- name: `?GetPITRInterface@PITR@@YAJPEBGPEAPEAUIPITRBase@1@@Z`
- size: `1152`
- prototype: `__int64 __fastcall(PITR *__hidden this, const unsigned __int16 *, struct PITR::IPITRBase **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400752bc`

## callees

- `0x140074d90`
- `0x14007528c`
- `0x140075a6c`
- `0x1400761e4`
- `0x140076218`
- `0x14007640c`
- `0x1400764b8`
- `0x14007d010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x140075a8f`
- `KERNEL32!GetTickCount` at `0x140075aa0`
- `KERNEL32!GetTickCount` at `0x140075e9d`
- `KERNEL32!GetTickCount` at `0x140075a8f`
- `KERNEL32!GetTickCount` at `0x140075aa0`
- `KERNEL32!GetTickCount` at `0x140075e9d`
- `KERNEL32!LeaveCriticalSection` at `0x140075eb2`
- `KERNEL32!LeaveCriticalSection` at `0x140075eb2`
- `KERNEL32!EnterCriticalSection` at `0x140075acc`
- `KERNEL32!EnterCriticalSection` at `0x140075acc`
- `KERNEL32!GetProcAddress` at `0x140075d82`
- `KERNEL32!GetProcAddress` at `0x140075d82`
- `KERNEL32!HeapFree` at `0x140075ecb`
- `KERNEL32!HeapFree` at `0x140075ecb`
- `KERNEL32!GetProcessHeap` at `0x140075ebd`
- `KERNEL32!GetProcessHeap` at `0x140075ebd`
- `KERNEL32!LoadLibraryExW` at `0x140075c8b`
- `KERNEL32!LoadLibraryExW` at `0x140075c8b`
- `KERNEL32!GetLastError` at `0x140075b35`
- `KERNEL32!GetLastError` at `0x140075bb3`
- `KERNEL32!GetLastError` at `0x140075c22`
- `KERNEL32!GetLastError` at `0x140075cd5`
- `KERNEL32!GetLastError` at `0x140075ced`
- `KERNEL32!GetLastError` at `0x140075d05`
- `KERNEL32!GetLastError` at `0x140075d91`
- `KERNEL32!GetLastError` at `0x140075da9`
- `KERNEL32!GetLastError` at `0x140075dc1`
- `KERNEL32!GetLastError` at `0x140075e30`
- `KERNEL32!GetLastError` at `0x140075b35`
- `KERNEL32!GetLastError` at `0x140075bb3`
- `KERNEL32!GetLastError` at `0x140075c22`
- `KERNEL32!GetLastError` at `0x140075cd5`
- `KERNEL32!GetLastError` at `0x140075ced`
- `KERNEL32!GetLastError` at `0x140075d05`
- `KERNEL32!GetLastError` at `0x140075d91`
- `KERNEL32!GetLastError` at `0x140075da9`
- `KERNEL32!GetLastError` at `0x140075dc1`
- `KERNEL32!GetLastError` at `0x140075e30`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140075b25`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140075b25`
- `WDSCORE!WdsSetupLogMessageW` at `0x140075e97`
- `WDSCORE!WdsSetupLogMessageW` at `0x140075e97`
- `WDSCORE!CurrentIP` at `0x140075b3d`
- `WDSCORE!CurrentIP` at `0x140075bbb`
- `WDSCORE!CurrentIP` at `0x140075c2a`
- `WDSCORE!CurrentIP` at `0x140075d0d`
- `WDSCORE!CurrentIP` at `0x140075dc9`
- `WDSCORE!CurrentIP` at `0x140075e38`
- `WDSCORE!CurrentIP` at `0x140075b3d`
- `WDSCORE!CurrentIP` at `0x140075bbb`
- `WDSCORE!CurrentIP` at `0x140075c2a`
- `WDSCORE!CurrentIP` at `0x140075d0d`
- `WDSCORE!CurrentIP` at `0x140075dc9`
- `WDSCORE!CurrentIP` at `0x140075e38`

## string_xrefs

- `0x140075b04`: `%windir%\System32\OOBE\PITR.dll`
- `0x140075d16`: `PITR::GetPITRInterface: LoadLibraryEx failed for %s. Error: 0x%08X`

## pseudocode

```c
__int64 __fastcall PITR::GetPITRInterface(PITR *this, const unsigned __int16 *a2, struct PITR::IPITRBase **a3)
{
  DWORD TickCount; // r14d
  DWORD v5; // eax
  char *v7; // rbp
  struct _RTL_CRITICAL_SECTION *GlobalLock; // r15
  const WCHAR *Expand; // rax
  int IsFileMicrosoftTrusted; // esi
  DWORD LastError; // edi
  __int64 v12; // rbx
  struct tagLOG_PARTIAL_MSG *v13; // rax
  DWORD v14; // edi
  __int64 v15; // rbx
  struct tagLOG_PARTIAL_MSG *v16; // rax
  DWORD v17; // edi
  __int64 v18; // rbx
  struct tagLOG_PARTIAL_MSG *v19; // rax
  HMODULE Library; // rax
  signed int v21; // eax
  bool v22; // sf
  signed int v23; // eax
  DWORD v24; // edi
  __int64 v25; // rbx
  struct tagLOG_PARTIAL_MSG *v26; // rax
  HMODULE v27; // rax
  FARPROC ProcAddress; // rax
  signed int v29; // eax
  bool v30; // sf
  signed int v31; // eax
  DWORD v32; // edi
  __int64 v33; // rbx
  struct tagLOG_PARTIAL_MSG *v34; // rax
  DWORD v35; // edi
  __int64 v36; // rbx
  struct tagLOG_PARTIAL_MSG *v37; // rax
  DWORD v38; // eax
  HANDLE ProcessHeap; // rax
  PITR *v40; // [rsp+90h] [rbp+8h] BYREF

  v40 = this;
  PITRTelemetryInitialize();
  TickCount = GetTickCount();
  if ( !a2 )
  {
    v5 = GetTickCount();
    PITRTelemetryLogInterfaceCreation(-2147024809, v5 - TickCount);
    return 2147942487LL;
  }
  v7 = 0;
  GlobalLock = pGetGlobalLock();
  EnterCriticalSection(GlobalLock);
  v40 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(void *, PITR **))(g_PitrDll + 56LL))(&g_PitrDll, &v40) )
  {
    Expand = (const WCHAR *)AllocateExpand(L"%windir%\\System32\\OOBE\\PITR.dll");
    v7 = (char *)Expand;
    if ( !Expand )
    {
      IsFileMicrosoftTrusted = -2147024888;
LABEL_30:
      v38 = GetTickCount();
      PITRTelemetryLogInterfaceCreation(IsFileMicrosoftTrusted, v38 - TickCount);
      goto LABEL_31;
    }
    if ( GetFileAttributesW(Expand) == -1 )
    {
      IsFileMicrosoftTrusted = -2147023728;
      LastError = GetLastError();
      v12 = CurrentIP();
      v13 = ConstructPartialMsgW(0x2000000u, "PITR::GetPITRInterface: %s not found. Error: 0x%08X", v7, -2147023728);
      WdsSetupLogMessageW(
        v13,
        0,
        L"D",
        0,
        448,
        L"base\\diagnosis\\srt\\pitr\\lib\\src\\pitr.cpp",
        L"PITR::GetPITRInterface",
        v12,
        LastError,
        0,
        0);
      goto LABEL_30;
    }
    LODWORD(v40) = 0;
    IsFileMicrosoftTrusted = pIsFileMicrosoftTrusted((const unsigned __int16 *)v7, (int *)&v40);
    if ( IsFileMicrosoftTrusted < 0 )
    {
      v14 = GetLastError();
      v15 = CurrentIP();
      v16 = ConstructPartialMsgW(
              0x2000000u,
              "PITR::GetPITRInterface: Failed to validate trust for %s. Error: 0x%08X",
              v7,
              IsFileMicrosoftTrusted);
      WdsSetupLogMessageW(
        v16,
        0,
        L"D",
        0,
        459,
        L"base\\diagnosis\\srt\\pitr\\lib\\src\\pitr.cpp",
        L"PITR::GetPITRInterface",
        v15,
        v14,
        0,
        0);
      goto LABEL_30;
    }
    if ( !(_DWORD)v40 )
    {
      IsFileMicrosoftTrusted = -2147023106;
      v17 = GetLastError();
      v18 = CurrentIP();
      v19 = ConstructPartialMsgW(
              0x2000000u,
              "PITR::GetPITRInterface: %s is not trusted. Error: 0x%08X",
              v7,
              -2147023106);
      WdsSetupLogMessageW(
        v19,
        0,
        L"D",
        0,
        466,
        L"base\\diagnosis\\srt\\pitr\\lib\\src\\pitr.cpp",
        L"PITR::GetPITRInterface",
        v18,
        v17,
        0,
        0);
      goto LABEL_30;
    }
    Library = LoadLibraryExW((LPCWSTR)v7, 0, 8u);
    (*(void (__fastcall **)(void *, HMODULE))(g_PitrDll + 48LL))(&g_PitrDll, Library);
    v40 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(void *, PITR **))(g_PitrDll + 56LL))(&g_PitrDll, &v40) )
    {
      v21 = GetLastError();
      v22 = v21 < 0;
      if ( v21 > 0 )
        v22 = 1;
      if ( v22 )
      {
        v23 = GetLastError();
        IsFileMicrosoftTrusted = v23;
        if ( v23 > 0 )
          IsFileMicrosoftTrusted = (unsigned __int16)v23 | 0x80070000;
      }
      else
      {
        IsFileMicrosoftTrusted = -2147467259;
      }
      v24 = GetLastError();
      v25 = CurrentIP();
      v26 = ConstructPartialMsgW(
              0x2000000u,
              "PITR::GetPITRInterface: LoadLibraryEx failed for %s. Error: 0x%08X",
              v7,
              IsFileMicrosoftTrusted);
      WdsSetupLogMessageW(
        v26,
        0,
        L"D",
        0,
        476,
        L"base\\diagnosis\\srt\\pitr\\lib\\src\\pitr.cpp",
        L"PITR::GetPITRInterface",
        v25,
        v24,
        0,
        0);
      goto LABEL_30;
    }
  }
  v27 = (HMODULE)(*(__int64 (__fastcall **)(void *))(g_PitrDll + 32LL))(&g_PitrDll);
  ProcAddress = GetProcAddress(v27, "GetPITRInterface_Internal");
  if ( !ProcAddress )
  {
    v29 = GetLastError();
    v30 = v29 < 0;
    if ( v29 > 0 )
      v30 = 1;
    if ( v30 )
    {
      v31 = GetLastError();
      IsFileMicrosoftTrusted = v31;
      if ( v31 > 0 )
        IsFileMicrosoftTrusted = (unsigned __int16)v31 | 0x80070000;
    }
    else
    {
      IsFileMicrosoftTrusted = -2147467259;
    }
    v32 = GetLastError();
    v33 = CurrentIP();
    v34 = ConstructPartialMsgW(
            0x2000000u,
            "PITR::GetPITRInterface: GetProcAddress failed for GetPITRInterface_Internal. Error: 0x%08X",
            IsFileMicrosoftTrusted);
    WdsSetupLogMessageW(
      v34,
      0,
      L"D",
      0,
      486,
      L"base\\diagnosis\\srt\\pitr\\lib\\src\\pitr.cpp",
      L"PITR::GetPITRInterface",
      v33,
      v32,
      0,
      0);
    goto LABEL_30;
  }
  IsFileMicrosoftTrusted = ((__int64 (__fastcall *)(_QWORD, __int64, const unsigned __int16 *))ProcAddress)(0, 1, a2);
  if ( IsFileMicrosoftTrusted < 0 )
  {
    v35 = GetLastError();
    v36 = CurrentIP();
    v37 = ConstructPartialMsgW(
            0x2000000u,
            "PITR::GetPITRInterface: GetPITRInterface_Internal failed. Error: 0x%08X",
            IsFileMicrosoftTrusted);
    WdsSetupLogMessageW(
      v37,
      0,
      L"D",
      0,
      494,
      L"base\\diagnosis\\srt\\pitr\\lib\\src\\pitr.cpp",
      L"PITR::GetPITRInterface",
      v36,
      v35,
      0,
      0);
    goto LABEL_30;
  }
LABEL_31:
  LeaveCriticalSection(GlobalLock);
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
0x140075a6c  mov     [rsp+arg_8], rbx
0x140075a71  mov     [rsp+arg_10], rbp
0x140075a76  mov     [rsp+arg_0], rcx
0x140075a7b  push    rsi
0x140075a7c  push    rdi
0x140075a7d  push    r12
0x140075a7f  push    r14
0x140075a81  push    r15
0x140075a83  sub     rsp, 60h
0x140075a87  mov     rbx, rdx
0x140075a8a  call    ?PITRTelemetryInitialize@@YAJXZ; PITRTelemetryInitialize(void)
0x140075a8f  call    cs:__imp_GetTickCount
0x140075a95  xor     r12d, r12d
0x140075a98  mov     r14d, eax
0x140075a9b  test    rbx, rbx
0x140075a9e  jnz     short loc_140075ABE
0x140075aa0  call    cs:__imp_GetTickCount
0x140075aa6  sub     eax, r14d
0x140075aa9  mov     ebx, 80070057h
0x140075aae  mov     edx, eax; unsigned int
0x140075ab0  mov     ecx, ebx; int
0x140075ab2  call    ?PITRTelemetryLogInterfaceCreation@@YAXJK@Z; PITRTelemetryLogInterfaceCreation(long,ulong)
0x140075ab7  mov     eax, ebx
0x140075ab9  jmp     loc_140075ED3
0x140075abe  mov     rbp, r12
0x140075ac1  call    ?pGetGlobalLock@@YAPEAU_RTL_CRITICAL_SECTION@@XZ; pGetGlobalLock(void)
0x140075ac6  mov     rcx, rax; lpCriticalSection
0x140075ac9  mov     r15, rax
0x140075acc  call    cs:__imp_EnterCriticalSection
0x140075ad2  mov     rcx, cs:?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x140075ad9  lea     rdi, ?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x140075ae0  lea     rdx, [rsp+88h+arg_0]
0x140075ae8  mov     [rsp+88h+arg_0], r12
0x140075af0  mov     rax, [rcx+38h]
0x140075af4  mov     rcx, rdi
0x140075af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140075afc  test    al, al
0x140075afe  jz      loc_140075D65
0x140075b04  lea     rcx, aWindirSystem32; "%windir%\\System32\\OOBE\\PITR.dll"
0x140075b0b  call    AllocateExpand
0x140075b10  mov     rbp, rax
0x140075b13  test    rax, rax
0x140075b16  jnz     short loc_140075B22
0x140075b18  mov     esi, 80070008h
0x140075b1d  jmp     loc_140075E9D
0x140075b22  mov     rcx, rbp; lpFileName
0x140075b25  call    cs:__imp_GetFileAttributesW
0x140075b2b  cmp     eax, 0FFFFFFFFh
0x140075b2e  jnz     short loc_140075B95
0x140075b30  mov     esi, 80070490h
0x140075b35  call    cs:__imp_GetLastError
0x140075b3b  mov     edi, eax
0x140075b3d  call    cs:__imp_CurrentIP
0x140075b43  mov     r9d, esi
0x140075b46  lea     rdx, aPitrGetpitrint_5; "PITR::GetPITRInterface: %s not found. E"...
0x140075b4d  mov     r8, rbp
0x140075b50  mov     ecx, 2000000h; unsigned int
0x140075b55  mov     rbx, rax
0x140075b58  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x140075b5d  mov     [rsp+88h+var_38], r12d
0x140075b62  lea     rcx, aPitrGetpitrint_0; "PITR::GetPITRInterface"
0x140075b69  mov     [rsp+88h+var_40], r12
0x140075b6e  mov     [rsp+88h+var_48], edi
0x140075b72  mov     [rsp+88h+var_50], rbx
0x140075b77  mov     [rsp+88h+var_58], rcx
0x140075b7c  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x140075b83  mov     [rsp+88h+var_60], rcx
0x140075b88  mov     [rsp+88h+var_68], 1C0h
0x140075b90  jmp     loc_140075E88
0x140075b95  lea     rdx, [rsp+88h+arg_0]; int *
0x140075b9d  mov     dword ptr [rsp+88h+arg_0], r12d
0x140075ba5  mov     rcx, rbp; unsigned __int16 *
0x140075ba8  call    ?pIsFileMicrosoftTrusted@@YAJPEBGPEAH@Z; pIsFileMicrosoftTrusted(ushort const *,int *)
0x140075bad  mov     esi, eax
0x140075baf  test    eax, eax
0x140075bb1  jns     short loc_140075C13
0x140075bb3  call    cs:__imp_GetLastError
0x140075bb9  mov     edi, eax
0x140075bbb  call    cs:__imp_CurrentIP
0x140075bc1  mov     r9d, esi
0x140075bc4  lea     rdx, aPitrGetpitrint; "PITR::GetPITRInterface: Failed to valid"...
0x140075bcb  mov     r8, rbp
0x140075bce  mov     ecx, 2000000h; unsigned int
0x140075bd3  mov     rbx, rax
0x140075bd6  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x140075bdb  mov     [rsp+88h+var_38], r12d
0x140075be0  lea     rcx, aPitrGetpitrint_0; "PITR::GetPITRInterface"
0x140075be7  mov     [rsp+88h+var_40], r12
0x140075bec  mov     [rsp+88h+var_48], edi
0x140075bf0  mov     [rsp+88h+var_50], rbx
0x140075bf5  mov     [rsp+88h+var_58], rcx
0x140075bfa  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x140075c01  mov     [rsp+88h+var_60], rcx
0x140075c06  mov     [rsp+88h+var_68], 1CBh
0x140075c0e  jmp     loc_140075E88
0x140075c13  cmp     dword ptr [rsp+88h+arg_0], r12d
0x140075c1b  jnz     short loc_140075C82
0x140075c1d  mov     esi, 800706FEh
0x140075c22  call    cs:__imp_GetLastError
0x140075c28  mov     edi, eax
0x140075c2a  call    cs:__imp_CurrentIP
0x140075c30  mov     r9d, esi
0x140075c33  lea     rdx, aPitrGetpitrint_1; "PITR::GetPITRInterface: %s is not trust"...
0x140075c3a  mov     r8, rbp
0x140075c3d  mov     ecx, 2000000h; unsigned int
0x140075c42  mov     rbx, rax
0x140075c45  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x140075c4a  mov     [rsp+88h+var_38], r12d
0x140075c4f  lea     rcx, aPitrGetpitrint_0; "PITR::GetPITRInterface"
0x140075c56  mov     [rsp+88h+var_40], r12
0x140075c5b  mov     [rsp+88h+var_48], edi
0x140075c5f  mov     [rsp+88h+var_50], rbx
0x140075c64  mov     [rsp+88h+var_58], rcx
0x140075c69  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x140075c70  mov     [rsp+88h+var_60], rcx
0x140075c75  mov     [rsp+88h+var_68], 1D2h
0x140075c7d  jmp     loc_140075E88
0x140075c82  xor     edx, edx; hFile
0x140075c84  mov     rcx, rbp; lpLibFileName
0x140075c87  lea     r8d, [rdx+8]; dwFlags
0x140075c8b  call    cs:__imp_LoadLibraryExW
0x140075c91  mov     rcx, cs:?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x140075c98  mov     rdx, rax
0x140075c9b  mov     r8, [rcx+30h]
0x140075c9f  mov     rcx, rdi
0x140075ca2  mov     rax, r8
0x140075ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140075caa  mov     rax, cs:?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x140075cb1  lea     rdx, [rsp+88h+arg_0]
0x140075cb9  mov     rcx, rdi
0x140075cbc  mov     [rsp+88h+arg_0], r12
0x140075cc4  mov     rax, [rax+38h]
0x140075cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140075ccd  test    al, al
0x140075ccf  jz      loc_140075D65
0x140075cd5  call    cs:__imp_GetLastError
0x140075cdb  mov     ebx, 80070000h
0x140075ce0  test    eax, eax
0x140075ce2  jle     short loc_140075CEB
0x140075ce4  movzx   eax, ax
0x140075ce7  or      eax, ebx
0x140075ce9  test    eax, eax
0x140075ceb  jns     short loc_140075D00
0x140075ced  call    cs:__imp_GetLastError
0x140075cf3  mov     esi, eax
0x140075cf5  test    eax, eax
0x140075cf7  jle     short loc_140075D05
0x140075cf9  movzx   esi, ax
0x140075cfc  or      esi, ebx
0x140075cfe  jmp     short loc_140075D05
0x140075d00  mov     esi, 80004005h
0x140075d05  call    cs:__imp_GetLastError
0x140075d0b  mov     edi, eax
0x140075d0d  call    cs:__imp_CurrentIP
0x140075d13  mov     r9d, esi
0x140075d16  lea     rdx, aPitrGetpitrint_3; "PITR::GetPITRInterface: LoadLibraryEx f"...
0x140075d1d  mov     r8, rbp
0x140075d20  mov     ecx, 2000000h; unsigned int
0x140075d25  mov     rbx, rax
0x140075d28  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x140075d2d  mov     [rsp+88h+var_38], r12d
0x140075d32  lea     rcx, aPitrGetpitrint_0; "PITR::GetPITRInterface"
0x140075d39  mov     [rsp+88h+var_40], r12
0x140075d3e  mov     [rsp+88h+var_48], edi
0x140075d42  mov     [rsp+88h+var_50], rbx
0x140075d47  mov     [rsp+88h+var_58], rcx
0x140075d4c  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x140075d53  mov     [rsp+88h+var_60], rcx
0x140075d58  mov     [rsp+88h+var_68], 1DCh
0x140075d60  jmp     loc_140075E88
0x140075d65  mov     rax, cs:?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x140075d6c  mov     rcx, rdi
0x140075d6f  mov     rax, [rax+20h]
0x140075d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140075d78  mov     rcx, rax; hModule
0x140075d7b  lea     rdx, aGetpitrinterfa; "GetPITRInterface_Internal"
0x140075d82  call    cs:__imp_GetProcAddress
0x140075d88  test    rax, rax
0x140075d8b  jnz     loc_140075E1B
0x140075d91  call    cs:__imp_GetLastError
0x140075d97  mov     ebx, 80070000h
0x140075d9c  test    eax, eax
0x140075d9e  jle     short loc_140075DA7
0x140075da0  movzx   eax, ax
0x140075da3  or      eax, ebx
0x140075da5  test    eax, eax
0x140075da7  jns     short loc_140075DBC
0x140075da9  call    cs:__imp_GetLastError
0x140075daf  mov     esi, eax
0x140075db1  test    eax, eax
0x140075db3  jle     short loc_140075DC1
0x140075db5  movzx   esi, ax
0x140075db8  or      esi, ebx
0x140075dba  jmp     short loc_140075DC1
0x140075dbc  mov     esi, 80004005h
0x140075dc1  call    cs:__imp_GetLastError
0x140075dc7  mov     edi, eax
0x140075dc9  call    cs:__imp_CurrentIP
0x140075dcf  mov     r8d, esi
0x140075dd2  lea     rdx, aPitrGetpitrint_4; "PITR::GetPITRInterface: GetProcAddress "...
0x140075dd9  mov     ecx, 2000000h; unsigned int
0x140075dde  mov     rbx, rax
0x140075de1  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x140075de6  mov     [rsp+88h+var_38], r12d
0x140075deb  lea     rcx, aPitrGetpitrint_0; "PITR::GetPITRInterface"
0x140075df2  mov     [rsp+88h+var_40], r12
0x140075df7  mov     [rsp+88h+var_48], edi
0x140075dfb  mov     [rsp+88h+var_50], rbx
0x140075e00  mov     [rsp+88h+var_58], rcx
0x140075e05  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x140075e0c  mov     [rsp+88h+var_60], rcx
0x140075e11  mov     [rsp+88h+var_68], 1E6h
0x140075e19  jmp     short loc_140075E88
0x140075e1b  mov     r8, rbx
0x140075e1e  mov     edx, 1
0x140075e23  xor     ecx, ecx
0x140075e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140075e2a  mov     esi, eax
0x140075e2c  test    eax, eax
0x140075e2e  jns     short loc_140075EAF
0x140075e30  call    cs:__imp_GetLastError
0x140075e36  mov     edi, eax
0x140075e38  call    cs:__imp_CurrentIP
0x140075e3e  mov     r8d, esi
0x140075e41  lea     rdx, aPitrGetpitrint_2; "PITR::GetPITRInterface: GetPITRInterfac"...
0x140075e48  mov     ecx, 2000000h; unsigned int
0x140075e4d  mov     rbx, rax
0x140075e50  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x140075e55  mov     [rsp+88h+var_38], r12d
0x140075e5a  lea     rcx, aPitrGetpitrint_0; "PITR::GetPITRInterface"
0x140075e61  mov     [rsp+88h+var_40], r12
0x140075e66  mov     [rsp+88h+var_48], edi
0x140075e6a  mov     [rsp+88h+var_50], rbx
0x140075e6f  mov     [rsp+88h+var_58], rcx
0x140075e74  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x140075e7b  mov     [rsp+88h+var_60], rcx
0x140075e80  mov     [rsp+88h+var_68], 1EEh
0x140075e88  xor     r9d, r9d
0x140075e8b  lea     r8, aD_1; "D"
0x140075e92  xor     edx, edx
0x140075e94  mov     rcx, rax
0x140075e97  call    cs:__imp_WdsSetupLogMessageW
0x140075e9d  call    cs:__imp_GetTickCount
0x140075ea3  sub     eax, r14d
0x140075ea6  mov     ecx, esi; int
0x140075ea8  mov     edx, eax; unsigned int
0x140075eaa  call    ?PITRTelemetryLogInterfaceCreation@@YAXJK@Z; PITRTelemetryLogInterfaceCreation(long,ulong)
0x140075eaf  mov     rcx, r15; lpCriticalSection
0x140075eb2  call    cs:__imp_LeaveCriticalSection
0x140075eb8  test    rbp, rbp
0x140075ebb  jz      short loc_140075ED1
0x140075ebd  call    cs:__imp_GetProcessHeap
0x140075ec3  mov     r8, rbp; lpMem
0x140075ec6  xor     edx, edx; dwFlags
0x140075ec8  mov     rcx, rax; hHeap
0x140075ecb  call    cs:__imp_HeapFree
0x140075ed1  mov     eax, esi
0x140075ed3  lea     r11, [rsp+88h+var_28]
0x140075ed8  mov     rbx, [r11+38h]
0x140075edc  mov     rbp, [r11+40h]
0x140075ee0  mov     rsp, r11
0x140075ee3  pop     r15
0x140075ee5  pop     r14
0x140075ee7  pop     r12
0x140075ee9  pop     rdi
0x140075eea  pop     rsi
0x140075eeb  retn
```
