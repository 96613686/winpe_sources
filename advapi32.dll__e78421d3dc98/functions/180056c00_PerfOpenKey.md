# PerfOpenKey

- ea: `0x180056c00`
- end: `0x180057372`
- name: `PerfOpenKey`
- size: `1906`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800288a0`

## callees

- `0x180015d70`
- `0x180015e40`
- `0x180017100`
- `0x1800177c0`
- `0x180022c40`
- `0x180026a7c`
- `0x18003b57c`
- `0x18003b748`
- `0x180056c00`
- `0x180057a4c`
- `0x180057a98`
- `0x18006505a`
- `0x180065090`

## import_xrefs

- `msvcrt!_ultow_s` at `0x180057065`
- `msvcrt!_ultow_s` at `0x180057065`
- `ntdll!NtWaitForSingleObject` at `0x180056d54`
- `ntdll!NtWaitForSingleObject` at `0x180056d54`
- `ntdll!RtlGetVersion` at `0x1800572d4`
- `ntdll!RtlGetVersion` at `0x1800572d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005704f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005704f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180056da6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180056da6`
- `KERNEL32!CloseHandle` at `0x180056cfd`
- `KERNEL32!CloseHandle` at `0x18005720e`
- `KERNEL32!CloseHandle` at `0x180057222`
- `KERNEL32!CloseHandle` at `0x180056cfd`
- `KERNEL32!CloseHandle` at `0x18005720e`
- `KERNEL32!CloseHandle` at `0x180057222`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800570ff`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1800570ff`
- `KERNEL32!CreateFileW` at `0x180057133`
- `KERNEL32!CreateFileW` at `0x180057133`
- `KERNEL32!CreateFileMappingW` at `0x180057170`
- `KERNEL32!CreateFileMappingW` at `0x180057170`
- `KERNEL32!MapViewOfFile` at `0x180057198`
- `KERNEL32!MapViewOfFile` at `0x180057198`
- `KERNEL32!ReleaseMutex` at `0x180056ec9`
- `KERNEL32!ReleaseMutex` at `0x180057314`
- `KERNEL32!ReleaseMutex` at `0x180056ec9`
- `KERNEL32!ReleaseMutex` at `0x180057314`
- `KERNEL32!GetComputerNameW` at `0x180056f5a`
- `KERNEL32!GetComputerNameW` at `0x180056fa2`
- `KERNEL32!GetComputerNameW` at `0x180056f5a`
- `KERNEL32!GetComputerNameW` at `0x180056fa2`
- `KERNEL32!CreateMutexW` at `0x180056caf`
- `KERNEL32!CreateMutexW` at `0x180056caf`

## string_xrefs

- `0x180057089`: `%TEMP%\Perflib_Perfdata_`
- `0x180056fea`: `Configuration Flags`

## pseudocode

```c
__int64 __fastcall PerfOpenKey(__int64 a1, char a2)
{
  NTSTATUS Version; // ebx
  unsigned int v5; // edi
  _QWORD *v6; // rcx
  HANDLE v7; // r9
  HANDLE MutexW; // rax
  LARGE_INTEGER *v9; // r8
  NTSTATUS v10; // eax
  HANDLE v11; // rcx
  signed __int32 v12; // eax
  HKEY KeyPerflib; // rsi
  unsigned int *v14; // r8
  unsigned int *v15; // r8
  void *v16; // rax
  unsigned int *v17; // r8
  int v18; // eax
  unsigned __int8 v19; // al
  DWORD CurrentProcessId; // eax
  char *FileW; // rcx
  HANDLE FileMappingW; // rax
  _DWORD *v23; // rax
  _DWORD *v24; // rbx
  unsigned int dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  unsigned int dwFlagsAndAttributesa; // [rsp+28h] [rbp-D8h]
  unsigned int dwFlagsAndAttributesb; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v29; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v30[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int8 v31[8]; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+70h] [rbp-90h] BYREF
  char v35; // [rsp+18Ah] [rbp+8Ah]
  wchar_t Buffer[32]; // [rsp+190h] [rbp+90h] BYREF

  v33 = 0;
  *(_DWORD *)v31 = 0;
  Version = 0;
  v5 = 0;
  memset_0(&VersionInformation, 0, 0x11Cu);
  SystemTimeAsFileTime = 0;
  v6 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_qd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids,
      a1,
      NumberOfOpens);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = hGlobalDataMutex;
  if ( hGlobalDataMutex )
    goto LABEL_13;
  MutexW = CreateMutexW(0, 0, 0);
  if ( MutexW )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&hGlobalDataMutex, (signed __int64)MutexW, 0) )
      CloseHandle(MutexW);
    v7 = hGlobalDataMutex;
    v6 = WPP_GLOBAL_Control;
    if ( !hGlobalDataMutex )
    {
      v5 = 1359;
      goto LABEL_89;
    }
LABEL_13:
    if ( a2 )
      goto LABEL_89;
    if ( dwThreadAndLibraryTimeout - 1 > 0xFFFFFFFD )
    {
      v9 = 0;
    }
    else
    {
      v9 = (LARGE_INTEGER *)&v33;
      v33 = (int)(-10000 * dwThreadAndLibraryTimeout);
    }
    v10 = NtWaitForSingleObject(v7, 0, v9);
    Version = v10;
    if ( v10 )
    {
      v5 = PerfpDosError(v10);
      v6 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        return v5;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_89;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids,
        (unsigned int)Version);
      goto LABEL_88;
    }
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( bPerflibOpen && qword_1800A30C8 + 18000000000LL > *(unsigned __int64 *)&SystemTimeAsFileTime )
    {
      v11 = hGlobalDataMutex;
LABEL_87:
      ReleaseMutex(v11);
      goto LABEL_88;
    }
    v12 = _InterlockedIncrement(&NumberOfOpens);
    if ( bPerflibOpen )
    {
      if ( v12 != 2 )
        goto LABEL_83;
    }
    else if ( v12 != 1 )
    {
      goto LABEL_83;
    }
    KeyPerflib = PerflibciGetKeyPerflib();
    if ( !KeyPerflib )
    {
      _InterlockedAdd(&NumberOfOpens, 0xFFFFFFFF);
      v6 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids);
        v6 = WPP_GLOBAL_Control;
      }
      if ( !hGlobalDataMutex )
        goto LABEL_89;
      v11 = hGlobalDataMutex;
      goto LABEL_87;
    }
    v30[0] = 520;
    memset_0(&PerfpErrorLog.el_data_size, 0, 0x208u);
    if ( !PrivateRegQueryValueExT(
            KeyPerflib,
            L"Updating",
            v14,
            (unsigned int *)&v29,
            (unsigned __int8 *)&PerfpErrorLog.el_data_size,
            v30,
            1) )
    {
      _InterlockedAdd(&NumberOfOpens, 0xFFFFFFFF);
      if ( hGlobalDataMutex )
        ReleaseMutex(hGlobalDataMutex);
      v5 = 0;
      goto LABEL_88;
    }
    v30[0] = 4;
    LODWORD(v29) = 0;
    *(_DWORD *)v31 = 0;
    if ( !PrivateRegQueryValueExT(KeyPerflib, L"Disable Performance Counters", v15, (unsigned int *)&v29, v31, v30, 1)
      && (_DWORD)v29 == 4
      && *(_DWORD *)v31 == 1 )
    {
      _InterlockedAdd(&NumberOfOpens, 0xFFFFFFFF);
      v5 = 1058;
    }
    else
    {
      v5 = 0;
      if ( !pComputerName )
      {
        LODWORD(ComputerNameLength) = 0;
        GetComputerNameW(0, (LPDWORD)&ComputerNameLength);
        LODWORD(ComputerNameLength) = ComputerNameLength + 1;
        v16 = (void *)operator new(saturated_mul((unsigned int)ComputerNameLength, 2u));
        pComputerName = v16;
        if ( v16 && GetComputerNameW((LPWSTR)v16, (LPDWORD)&ComputerNameLength) )
        {
          *((_WORD *)pComputerName + (unsigned int)ComputerNameLength) = 0;
          v18 = 2 * ComputerNameLength + 2;
        }
        else
        {
          v18 = 0;
        }
        LODWORD(ComputerNameLength) = v18;
        LODWORD(v29) = 0;
        v30[0] = 4;
        if ( PrivateRegQueryValueExT(
               KeyPerflib,
               L"Configuration Flags",
               v17,
               (unsigned int *)&v29,
               &lPerflibConfigFlags,
               v30,
               1)
          || (_DWORD)v29 != 4 )
        {
          v19 = 4;
          *(_DWORD *)&lPerflibConfigFlags = 4;
        }
        else
        {
          v19 = lPerflibConfigFlags;
        }
        if ( !hPerflibSectionFile && (v19 & 0x10) != 0 )
        {
          *(_QWORD *)v30 = 0;
          v29 = 0;
          CurrentProcessId = GetCurrentProcessId();
          _ultow_s(CurrentProcessId, Buffer, 0x20u, 16);
          if ( (int)StringCchCopyExW(
                      &szPerflibSectionName,
                      0x104u,
                      L"%TEMP%\\Perflib_Perfdata_",
                      &v29,
                      (unsigned __int64 *)v30,
                      dwFlagsAndAttributes) < 0
            || (int)StringCchCopyExW(
                      v29,
                      *(unsigned __int64 *)v30,
                      Buffer,
                      &v29,
                      (unsigned __int64 *)v30,
                      dwFlagsAndAttributesa) < 0
            || (int)StringCchCopyExW(
                      v29,
                      *(unsigned __int64 *)v30,
                      L".dat",
                      &v29,
                      (unsigned __int64 *)v30,
                      dwFlagsAndAttributesb) < 0
            || ExpandEnvironmentStringsW(&szPerflibSectionName, &szPerflibSectionFile, 0x104u) - 1 > 0x103 )
          {
            FileW = (char *)hPerflibSectionFile;
          }
          else
          {
            FileW = (char *)CreateFileW(&szPerflibSectionFile, 0xC0000000, 3u, 0, 4u, 0x14000100u, 0);
            hPerflibSectionFile = FileW;
          }
          if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids);
          }
          else
          {
            FileMappingW = CreateFileMappingW(FileW, 0, 4u, 0, 0x4000u, &szPerflibSectionName);
            hPerflibSectionMap = FileMappingW;
            if ( FileMappingW )
            {
              v23 = MapViewOfFile(FileMappingW, 2u, 0, 0, 0x4000u);
              lpPerflibSectionAddr = v23;
              v24 = v23;
              if ( v23 )
              {
                if ( v23[3] != 19088743 )
                {
                  memset_0(v23 + 4, 0, 0x3FF0u);
                  *v24 = 0;
                  *(_QWORD *)(v24 + 1) = 127;
                  v24[3] = 19088743;
                }
                goto LABEL_76;
              }
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids);
              CloseHandle(hPerflibSectionMap);
              hPerflibSectionMap = 0;
            }
            else if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids);
            }
            CloseHandle(hPerflibSectionFile);
          }
          hPerflibSectionFile = 0;
        }
      }
    }
LABEL_76:
    OpenExtensibleObjects();
    if ( bPerflibOpen )
      _InterlockedAdd(&NumberOfOpens, 0xFFFFFFFF);
    bPerflibOpen = 1;
    if ( a1 == -2147483644 )
      qword_1800A30C8 = (__int64)SystemTimeAsFileTime;
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
    VersionInformation.dwOSVersionInfoSize = 284;
    Version = RtlGetVersion(&VersionInformation);
    if ( Version >= 0 && v35 == 1 )
      dwBoostPriority = 0;
LABEL_83:
    if ( a1 != -2147483644 && v5 != 1058 )
      _InterlockedAdd(&NumberOfOpens, 0xFFFFFFFF);
    v11 = hGlobalDataMutex;
    if ( !hGlobalDataMutex )
      goto LABEL_88;
    goto LABEL_87;
  }
  v6 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    return v5;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids);
LABEL_88:
    v6 = WPP_GLOBAL_Control;
  }
LABEL_89:
  if ( (*((_BYTE *)v6 + 28) & 4) != 0 && *((_BYTE *)v6 + 25) >= 4u )
    WPP_SF_dD(v6[2], 17, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids, (unsigned int)NumberOfOpens, Version);
  return v5;
}

```

## disassembly

```asm
0x180056c00  push    rbp
0x180056c02  push    rbx
0x180056c03  push    rsi
0x180056c04  push    rdi
0x180056c05  push    r12
0x180056c07  push    r13
0x180056c09  push    r14
0x180056c0b  push    r15
0x180056c0d  lea     rbp, [rsp-0E8h]
0x180056c15  sub     rsp, 1E8h
0x180056c1c  mov     rax, cs:__security_cookie
0x180056c23  xor     rax, rsp
0x180056c26  mov     [rbp+120h+var_50], rax
0x180056c2d  xor     r15d, r15d
0x180056c30  mov     sil, dl
0x180056c33  mov     r14, rcx
0x180056c36  mov     [rsp+220h+var_1C0], r15
0x180056c3b  xor     edx, edx; Val
0x180056c3d  mov     dword ptr [rsp+220h+var_1D0], r15d
0x180056c42  lea     rcx, [rsp+220h+VersionInformation]; void *
0x180056c47  mov     r8d, 11Ch; Size
0x180056c4d  mov     ebx, r15d
0x180056c50  mov     edi, r15d
0x180056c53  call    memset_0
0x180056c58  mov     qword ptr [rsp+220h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180056c5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180056c64  lea     r12d, [r15+4]
0x180056c68  test    [rcx+1Ch], r12b
0x180056c6c  jz      short loc_180056C9C
0x180056c6e  cmp     [rcx+19h], r12b
0x180056c72  jb      short loc_180056C9C
0x180056c74  mov     eax, cs:?NumberOfOpens@@3JA; long NumberOfOpens
0x180056c7a  lea     edx, [r15+0Ah]
0x180056c7e  mov     rcx, [rcx+10h]
0x180056c82  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180056c89  mov     r9, r14
0x180056c8c  mov     [rsp+220h+dwCreationDisposition], eax
0x180056c90  call    WPP_SF_qd
0x180056c95  mov     rcx, cs:WPP_GLOBAL_Control
0x180056c9c  mov     r9, cs:?hGlobalDataMutex@@3PEAXEA; void * hGlobalDataMutex
0x180056ca3  test    r9, r9
0x180056ca6  jnz     short loc_180056D20
0x180056ca8  xor     r8d, r8d; lpName
0x180056cab  xor     edx, edx; bInitialOwner
0x180056cad  xor     ecx, ecx; lpMutexAttributes
0x180056caf  call    cs:__imp_CreateMutexW
0x180056cb5  mov     rcx, rax; hObject
0x180056cb8  test    rax, rax
0x180056cbb  jnz     short loc_180056CF0
0x180056cbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180056cc4  test    [rcx+1Ch], r12b
0x180056cc8  jz      loc_18005734D
0x180056cce  cmp     byte ptr [rcx+19h], 2
0x180056cd2  jb      loc_180057321
0x180056cd8  mov     rcx, [rcx+10h]
0x180056cdc  lea     edx, [rax+0Bh]
0x180056cdf  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180056ce6  call    WPP_SF_
0x180056ceb  jmp     loc_18005731A
0x180056cf0  xor     eax, eax
0x180056cf2  lock cmpxchg cs:?hGlobalDataMutex@@3PEAXEA, rcx; void * hGlobalDataMutex
0x180056cfb  jz      short loc_180056D03
0x180056cfd  call    cs:__imp_CloseHandle
0x180056d03  mov     r9, cs:?hGlobalDataMutex@@3PEAXEA; void * hGlobalDataMutex
0x180056d0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180056d11  test    r9, r9
0x180056d14  jnz     short loc_180056D20
0x180056d16  mov     edi, 54Fh
0x180056d1b  jmp     loc_180057321
0x180056d20  test    sil, sil
0x180056d23  jnz     loc_180057321
0x180056d29  mov     ecx, cs:?dwThreadAndLibraryTimeout@@3KA; ulong dwThreadAndLibraryTimeout
0x180056d2f  lea     eax, [rcx-1]
0x180056d32  cmp     eax, 0FFFFFFFDh
0x180056d35  ja      short loc_180056D4C
0x180056d37  imul    eax, ecx, 0FFFFD8F0h
0x180056d3d  lea     r8, [rsp+220h+var_1C0]
0x180056d42  movsxd  rcx, eax
0x180056d45  mov     [rsp+220h+var_1C0], rcx
0x180056d4a  jmp     short loc_180056D4F
0x180056d4c  mov     r8, r15; Timeout
0x180056d4f  xor     edx, edx; Alertable
0x180056d51  mov     rcx, r9; Handle
0x180056d54  call    cs:__imp_NtWaitForSingleObject
0x180056d5a  mov     ebx, eax
0x180056d5c  test    eax, eax
0x180056d5e  jz      short loc_180056DA1
0x180056d60  mov     ecx, eax; int
0x180056d62  call    ?PerfpDosError@@YAKJ@Z; PerfpDosError(long)
0x180056d67  mov     edi, eax
0x180056d69  mov     rcx, cs:WPP_GLOBAL_Control
0x180056d70  test    [rcx+1Ch], r12b
0x180056d74  jz      loc_18005734D
0x180056d7a  cmp     byte ptr [rcx+19h], 2
0x180056d7e  jb      loc_180057321
0x180056d84  mov     rcx, [rcx+10h]
0x180056d88  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180056d8f  mov     edx, 0Ch
0x180056d94  mov     r9d, ebx
0x180056d97  call    WPP_SF_d
0x180056d9c  jmp     loc_18005731A
0x180056da1  lea     rcx, [rsp+220h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180056da6  call    cs:__imp_GetSystemTimeAsFileTime
0x180056dac  cmp     cs:?bPerflibOpen@@3EA, r15b; uchar bPerflibOpen
0x180056db3  jz      short loc_180056DD9
0x180056db5  mov     rcx, 430E23400h
0x180056dbf  add     rcx, cs:qword_1800A30C8
0x180056dc6  cmp     rcx, qword ptr [rsp+220h+SystemTimeAsFileTime.dwLowDateTime]
0x180056dcb  jbe     short loc_180056DD9
0x180056dcd  mov     rcx, cs:?hGlobalDataMutex@@3PEAXEA; void * hGlobalDataMutex
0x180056dd4  jmp     loc_180057314
0x180056dd9  mov     r13d, 1
0x180056ddf  mov     eax, r13d
0x180056de2  lock xadd cs:?NumberOfOpens@@3JA, eax; long NumberOfOpens
0x180056dea  add     eax, r13d
0x180056ded  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180056df1  cmp     cs:?bPerflibOpen@@3EA, r15b; uchar bPerflibOpen
0x180056df8  jnz     short loc_180056E04
0x180056dfa  cmp     eax, r13d
0x180056dfd  jz      short loc_180056E0D
0x180056dff  jmp     loc_1800572F0
0x180056e04  cmp     eax, 2
0x180056e07  jnz     loc_1800572F0
0x180056e0d  call    ?PerflibciGetKeyPerflib@@YAPEAUHKEY__@@XZ; PerflibciGetKeyPerflib(void)
0x180056e12  mov     rsi, rax
0x180056e15  test    rax, rax
0x180056e18  jnz     short loc_180056E6A
0x180056e1a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180056e1e  lock add cs:?NumberOfOpens@@3JA, ecx; long NumberOfOpens
0x180056e25  mov     rcx, cs:WPP_GLOBAL_Control
0x180056e2c  test    [rcx+1Ch], r12b
0x180056e30  jz      short loc_180056E52
0x180056e32  cmp     byte ptr [rcx+19h], 2
0x180056e36  jb      short loc_180056E52
0x180056e38  mov     rcx, [rcx+10h]
0x180056e3c  lea     edx, [rax+0Dh]
0x180056e3f  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180056e46  call    WPP_SF_
0x180056e4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180056e52  mov     rax, cs:?hGlobalDataMutex@@3PEAXEA; void * hGlobalDataMutex
0x180056e59  test    rax, rax
0x180056e5c  jz      loc_180057321
0x180056e62  mov     rcx, rax
0x180056e65  jmp     loc_180057314
0x180056e6a  mov     r8d, 208h; Size
0x180056e70  lea     rdi, ?PerfpErrorLog@@3UERROR_LOG@@A.el_data_size; ERROR_LOG PerfpErrorLog ...
0x180056e77  mov     rcx, rdi; void *
0x180056e7a  mov     [rsp+220h+var_1D8], r8d
0x180056e7f  xor     edx, edx; Val
0x180056e81  call    memset_0
0x180056e86  lea     rax, [rsp+220h+var_1D8]
0x180056e8b  mov     dword ptr [rsp+220h+hTemplateFile], r13d; int
0x180056e90  mov     qword ptr [rsp+220h+dwFlagsAndAttributes], rax; unsigned int *
0x180056e95  lea     r9, [rsp+220h+var_1E0]; unsigned int *
0x180056e9a  lea     rdx, aUpdating; "Updating"
0x180056ea1  mov     qword ptr [rsp+220h+dwCreationDisposition], rdi; unsigned __int8 *
0x180056ea6  mov     rcx, rsi; KeyHandle
0x180056ea9  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x180056eae  test    eax, eax
0x180056eb0  jnz     short loc_180056ED7
0x180056eb2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180056eb6  lock add cs:?NumberOfOpens@@3JA, ecx; long NumberOfOpens
0x180056ebd  mov     rcx, cs:?hGlobalDataMutex@@3PEAXEA; hMutex
0x180056ec4  test    rcx, rcx
0x180056ec7  jz      short loc_180056ECF
0x180056ec9  call    cs:__imp_ReleaseMutex
0x180056ecf  mov     edi, r15d
0x180056ed2  jmp     loc_18005731A
0x180056ed7  lea     rax, [rsp+220h+var_1D8]
0x180056edc  mov     dword ptr [rsp+220h+hTemplateFile], r13d; int
0x180056ee1  mov     qword ptr [rsp+220h+dwFlagsAndAttributes], rax; unsigned int *
0x180056ee6  lea     r9, [rsp+220h+var_1E0]; unsigned int *
0x180056eeb  lea     rax, [rsp+220h+var_1D0]
0x180056ef0  mov     [rsp+220h+var_1D8], r12d
0x180056ef5  lea     rdx, ?DisablePerformanceCounters@@3QBGB; "Disable Performance Counters"
0x180056efc  mov     qword ptr [rsp+220h+dwCreationDisposition], rax; unsigned __int8 *
0x180056f01  mov     rcx, rsi; KeyHandle
0x180056f04  mov     dword ptr [rsp+220h+var_1E0], r15d
0x180056f09  mov     dword ptr [rsp+220h+var_1D0], r15d
0x180056f0e  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x180056f13  test    eax, eax
0x180056f15  jnz     short loc_180056F3A
0x180056f17  cmp     dword ptr [rsp+220h+var_1E0], r12d
0x180056f1c  jnz     short loc_180056F3A
0x180056f1e  cmp     dword ptr [rsp+220h+var_1D0], r13d
0x180056f23  jnz     short loc_180056F3A
0x180056f25  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180056f29  lock add cs:?NumberOfOpens@@3JA, esi; long NumberOfOpens
0x180056f30  mov     edi, 422h
0x180056f35  jmp     loc_180057284
0x180056f3a  cmp     cs:?pComputerName@@3PEAGEA, r15; ushort * pComputerName
0x180056f41  mov     edi, r15d
0x180056f44  jnz     loc_180057280
0x180056f4a  lea     rdx, ?ComputerNameLength@@3KA; nSize
0x180056f51  mov     cs:?ComputerNameLength@@3KA, r15d; ulong ComputerNameLength
0x180056f58  xor     ecx, ecx; lpBuffer
0x180056f5a  call    cs:__imp_GetComputerNameW
0x180056f60  mov     eax, cs:?ComputerNameLength@@3KA; ulong ComputerNameLength
0x180056f66  add     eax, r13d
0x180056f69  mov     ecx, eax
0x180056f6b  mov     cs:?ComputerNameLength@@3KA, eax; ulong ComputerNameLength
0x180056f71  mov     eax, 2
0x180056f76  mul     rcx
0x180056f79  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180056f80  cmovb   rax, rcx
0x180056f84  mov     rcx, rax
0x180056f87  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180056f8c  mov     cs:?pComputerName@@3PEAGEA, rax; ushort * pComputerName
0x180056f93  test    rax, rax
0x180056f96  jz      short loc_180056FAC
0x180056f98  lea     rdx, ?ComputerNameLength@@3KA; nSize
0x180056f9f  mov     rcx, rax; lpBuffer
0x180056fa2  call    cs:__imp_GetComputerNameW
0x180056fa8  test    eax, eax
0x180056faa  jnz     short loc_180056FB1
0x180056fac  mov     eax, r15d
0x180056faf  jmp     short loc_180056FD0
0x180056fb1  mov     rax, cs:?pComputerName@@3PEAGEA; ushort * pComputerName
0x180056fb8  mov     edx, cs:?ComputerNameLength@@3KA; ulong ComputerNameLength
0x180056fbe  mov     [rax+rdx*2], r15w
0x180056fc3  mov     eax, cs:?ComputerNameLength@@3KA; ulong ComputerNameLength
0x180056fc9  lea     eax, ds:2[rax*2]
0x180056fd0  mov     cs:?ComputerNameLength@@3KA, eax; ulong ComputerNameLength
0x180056fd6  lea     r9, [rsp+220h+var_1E0]; unsigned int *
0x180056fdb  lea     rax, [rsp+220h+var_1D8]
0x180056fe0  mov     dword ptr [rsp+220h+hTemplateFile], r13d; int
0x180056fe5  mov     qword ptr [rsp+220h+dwFlagsAndAttributes], rax; unsigned int
0x180056fea  lea     rdx, ?cszPerflibFlags@@3QBGB; "Configuration Flags"
0x180056ff1  lea     rax, ?lPerflibConfigFlags@@3JA; long lPerflibConfigFlags
0x180056ff8  mov     dword ptr [rsp+220h+var_1E0], r15d
0x180056ffd  mov     rcx, rsi; KeyHandle
0x180057000  mov     qword ptr [rsp+220h+dwCreationDisposition], rax; unsigned __int8 *
0x180057005  mov     [rsp+220h+var_1D8], r12d
0x18005700a  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x18005700f  test    eax, eax
0x180057011  jnz     short loc_180057022
0x180057013  cmp     dword ptr [rsp+220h+var_1E0], r12d
0x180057018  jnz     short loc_180057022
0x18005701a  mov     eax, cs:?lPerflibConfigFlags@@3JA; long lPerflibConfigFlags
0x180057020  jmp     short loc_18005702B
0x180057022  mov     eax, r12d
0x180057025  mov     cs:?lPerflibConfigFlags@@3JA, eax; long lPerflibConfigFlags
0x18005702b  cmp     cs:?hPerflibSectionFile@@3PEAXEA, r15; void * hPerflibSectionFile
0x180057032  jnz     loc_180057280
0x180057038  mov     ebx, 10h
0x18005703d  test    bl, al
0x18005703f  jz      loc_180057280
0x180057045  mov     qword ptr [rsp+220h+var_1D8], r15
0x18005704a  mov     [rsp+220h+var_1E0], r15
0x18005704f  call    cs:__imp_GetCurrentProcessId
0x180057055  mov     r9d, ebx; Radix
0x180057058  lea     r8d, [rbx+10h]; BufferCount
0x18005705c  mov     ecx, eax; Value
0x18005705e  lea     rdx, [rbp+120h+Buffer]; Buffer
0x180057065  call    cs:__imp__ultow_s
0x18005706b  lea     rax, [rsp+220h+var_1D8]
0x180057070  mov     edx, 104h; unsigned __int64
0x180057075  lea     rsi, ?szPerflibSectionName@@3PAGA; ushort near * szPerflibSectionName
0x18005707c  mov     qword ptr [rsp+220h+dwCreationDisposition], rax; unsigned __int64 *
0x180057081  mov     rcx, rsi; unsigned __int16 *
0x180057084  lea     r9, [rsp+220h+var_1E0]; unsigned __int16 **
0x180057089  lea     r8, aTempPerflibPer; "%TEMP%\\Perflib_Perfdata_"
0x180057090  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180057095  test    eax, eax
0x180057097  js      loc_180057145
0x18005709d  mov     rdx, qword ptr [rsp+220h+var_1D8]; unsigned __int64
0x1800570a2  lea     rax, [rsp+220h+var_1D8]
0x1800570a7  mov     rcx, [rsp+220h+var_1E0]; unsigned __int16 *
0x1800570ac  lea     r9, [rsp+220h+var_1E0]; unsigned __int16 **
0x1800570b1  lea     r8, [rbp+120h+Buffer]; unsigned __int16 *
0x1800570b8  mov     qword ptr [rsp+220h+dwCreationDisposition], rax; unsigned __int64 *
0x1800570bd  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800570c2  test    eax, eax
0x1800570c4  js      short loc_180057145
0x1800570c6  mov     rdx, qword ptr [rsp+220h+var_1D8]; unsigned __int64
0x1800570cb  lea     rax, [rsp+220h+var_1D8]
0x1800570d0  mov     rcx, [rsp+220h+var_1E0]; unsigned __int16 *
0x1800570d5  lea     r9, [rsp+220h+var_1E0]; unsigned __int16 **
0x1800570da  lea     r8, aDat; ".dat"
0x1800570e1  mov     qword ptr [rsp+220h+dwCreationDisposition], rax; unsigned __int64 *
0x1800570e6  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800570eb  test    eax, eax
0x1800570ed  js      short loc_180057145
0x1800570ef  mov     r8d, 104h; nSize
0x1800570f5  lea     rdx, ?szPerflibSectionFile@@3PAGA; lpDst
0x1800570fc  mov     rcx, rsi; lpSrc
0x1800570ff  call    cs:__imp_ExpandEnvironmentStringsW
0x180057105  dec     eax
0x180057107  cmp     eax, 103h
0x18005710c  ja      short loc_180057145
0x18005710e  mov     [rsp+220h+hTemplateFile], r15; hTemplateFile
0x180057113  lea     r8d, [rbx-0Dh]; dwShareMode
0x180057117  mov     [rsp+220h+dwFlagsAndAttributes], 14000100h; dwFlagsAndAttributes
0x18005711f  lea     rcx, ?szPerflibSectionFile@@3PAGA; lpFileName
0x180057126  xor     r9d, r9d; lpSecurityAttributes
0x180057129  mov     [rsp+220h+dwCreationDisposition], r12d; dwCreationDisposition
0x18005712e  mov     edx, 0C0000000h; dwDesiredAccess
0x180057133  call    cs:__imp_CreateFileW
0x180057139  mov     rcx, rax
0x18005713c  mov     cs:?hPerflibSectionFile@@3PEAXEA, rax; void * hPerflibSectionFile
  ... truncated ...
```
