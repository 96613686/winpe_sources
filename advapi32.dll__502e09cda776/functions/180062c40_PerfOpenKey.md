# PerfOpenKey

- ea: `0x180062c40`
- end: `0x180063421`
- name: `PerfOpenKey`
- size: `2017`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002b280`

## callees

- `0x180002e40`
- `0x18000ec08`
- `0x18000ecf0`
- `0x180022170`
- `0x1800253c0`
- `0x180029698`
- `0x18003fb18`
- `0x18003fd04`
- `0x180062c40`
- `0x180063b38`
- `0x180063b8c`
- `0x18007205a`
- `0x1800720b0`

## import_xrefs

- `msvcrt!_ultow_s` at `0x1800630d9`
- `msvcrt!_ultow_s` at `0x1800630d9`
- `ntdll!NtWaitForSingleObject` at `0x180062da4`
- `ntdll!NtWaitForSingleObject` at `0x180062da4`
- `ntdll!RtlGetVersion` at `0x180063376`
- `ntdll!RtlGetVersion` at `0x180063376`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800630bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800630bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180062dfc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180062dfc`
- `KERNEL32!CloseHandle` at `0x180062d47`
- `KERNEL32!CloseHandle` at `0x1800632a4`
- `KERNEL32!CloseHandle` at `0x1800632be`
- `KERNEL32!CloseHandle` at `0x180062d47`
- `KERNEL32!CloseHandle` at `0x1800632a4`
- `KERNEL32!CloseHandle` at `0x1800632be`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18006317d`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18006317d`
- `KERNEL32!CreateFileW` at `0x1800631b7`
- `KERNEL32!CreateFileW` at `0x1800631b7`
- `KERNEL32!CreateFileMappingW` at `0x1800631fa`
- `KERNEL32!CreateFileMappingW` at `0x1800631fa`
- `KERNEL32!MapViewOfFile` at `0x180063228`
- `KERNEL32!MapViewOfFile` at `0x180063228`
- `KERNEL32!ReleaseMutex` at `0x180062f25`
- `KERNEL32!ReleaseMutex` at `0x1800633bc`
- `KERNEL32!ReleaseMutex` at `0x180062f25`
- `KERNEL32!ReleaseMutex` at `0x1800633bc`
- `KERNEL32!GetComputerNameW` at `0x180062fbc`
- `KERNEL32!GetComputerNameW` at `0x18006300a`
- `KERNEL32!GetComputerNameW` at `0x180062fbc`
- `KERNEL32!GetComputerNameW` at `0x18006300a`
- `KERNEL32!CreateMutexW` at `0x180062cf3`
- `KERNEL32!CreateMutexW` at `0x180062cf3`

## string_xrefs

- `0x180063103`: `%TEMP%\Perflib_Perfdata_`
- `0x180063058`: `Configuration Flags`

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
    if ( bPerflibOpen && qword_1800B2208 + 18000000000LL > *(unsigned __int64 *)&SystemTimeAsFileTime )
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
    if ( !(unsigned int)PrivateRegQueryValueExT(
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
    if ( !(unsigned int)PrivateRegQueryValueExT(
                          KeyPerflib,
                          L"Disable Performance Counters",
                          v15,
                          (unsigned int *)&v29,
                          v31,
                          v30,
                          1)
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
        LODWORD(PerfpErrorLog.el_data) = 0;
        GetComputerNameW(0, (LPDWORD)&PerfpErrorLog.el_data);
        ++LODWORD(PerfpErrorLog.el_data);
        v16 = (void *)operator new(saturated_mul(LODWORD(PerfpErrorLog.el_data), 2u));
        pComputerName = v16;
        if ( v16 && GetComputerNameW((LPWSTR)v16, (LPDWORD)&PerfpErrorLog.el_data) )
        {
          *((_WORD *)pComputerName + LODWORD(PerfpErrorLog.el_data)) = 0;
          v18 = 2 * LODWORD(PerfpErrorLog.el_data) + 2;
        }
        else
        {
          v18 = 0;
        }
        LODWORD(PerfpErrorLog.el_data) = v18;
        LODWORD(v29) = 0;
        v30[0] = 4;
        if ( (unsigned int)PrivateRegQueryValueExT(
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
      qword_1800B2208 = (__int64)SystemTimeAsFileTime;
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
0x180062c40  push    rbp
0x180062c42  push    rbx
0x180062c43  push    rsi
0x180062c44  push    rdi
0x180062c45  push    r12
0x180062c47  push    r13
0x180062c49  push    r14
0x180062c4b  push    r15
0x180062c4d  lea     rbp, [rsp-0E8h]
0x180062c55  sub     rsp, 1E8h
0x180062c5c  mov     rax, cs:__security_cookie
0x180062c63  xor     rax, rsp
0x180062c66  mov     [rbp+120h+var_50], rax
0x180062c6d  xor     r15d, r15d
0x180062c70  mov     sil, dl
0x180062c73  mov     r14, rcx
0x180062c76  mov     [rsp+220h+var_1C0], r15
0x180062c7b  xor     edx, edx; Val
0x180062c7d  mov     dword ptr [rsp+220h+var_1D0], r15d
0x180062c82  lea     rcx, [rsp+220h+VersionInformation]; void *
0x180062c87  mov     r8d, 11Ch; Size
0x180062c8d  mov     ebx, r15d
0x180062c90  mov     edi, r15d
0x180062c93  call    memset_0
0x180062c98  mov     qword ptr [rsp+220h+SystemTimeAsFileTime.dwLowDateTime], r15
0x180062c9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180062ca4  lea     r12d, [r15+4]
0x180062ca8  test    [rcx+1Ch], r12b
0x180062cac  jz      short loc_180062CDC
0x180062cae  cmp     [rcx+19h], r12b
0x180062cb2  jb      short loc_180062CDC
0x180062cb4  mov     eax, cs:?NumberOfOpens@@3JA; long NumberOfOpens
0x180062cba  lea     edx, [r15+0Ah]
0x180062cbe  mov     rcx, [rcx+10h]
0x180062cc2  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180062cc9  mov     r9, r14
0x180062ccc  mov     [rsp+220h+dwCreationDisposition], eax
0x180062cd0  call    WPP_SF_qd
0x180062cd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180062cdc  mov     r9, cs:?hGlobalDataMutex@@3PEAXEA; void * hGlobalDataMutex
0x180062ce3  test    r9, r9
0x180062ce6  jnz     loc_180062D70
0x180062cec  xor     r8d, r8d; lpName
0x180062cef  xor     edx, edx; bInitialOwner
0x180062cf1  xor     ecx, ecx; lpMutexAttributes
0x180062cf3  call    cs:__imp_CreateMutexW
0x180062cfa  nop     dword ptr [rax+rax+00h]
0x180062cff  mov     rcx, rax; hObject
0x180062d02  test    rax, rax
0x180062d05  jnz     short loc_180062D3A
0x180062d07  mov     rcx, cs:WPP_GLOBAL_Control
0x180062d0e  test    [rcx+1Ch], r12b
0x180062d12  jz      loc_1800633FB
0x180062d18  cmp     byte ptr [rcx+19h], 2
0x180062d1c  jb      loc_1800633CF
0x180062d22  mov     rcx, [rcx+10h]
0x180062d26  lea     edx, [rax+0Bh]
0x180062d29  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180062d30  call    WPP_SF_
0x180062d35  jmp     loc_1800633C8
0x180062d3a  xor     eax, eax
0x180062d3c  lock cmpxchg cs:?hGlobalDataMutex@@3PEAXEA, rcx; void * hGlobalDataMutex
0x180062d45  jz      short loc_180062D53
0x180062d47  call    cs:__imp_CloseHandle
0x180062d4e  nop     dword ptr [rax+rax+00h]
0x180062d53  mov     r9, cs:?hGlobalDataMutex@@3PEAXEA; void * hGlobalDataMutex
0x180062d5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180062d61  test    r9, r9
0x180062d64  jnz     short loc_180062D70
0x180062d66  mov     edi, 54Fh
0x180062d6b  jmp     loc_1800633CF
0x180062d70  test    sil, sil
0x180062d73  jnz     loc_1800633CF
0x180062d79  mov     ecx, cs:?dwThreadAndLibraryTimeout@@3KA; ulong dwThreadAndLibraryTimeout
0x180062d7f  lea     eax, [rcx-1]
0x180062d82  cmp     eax, 0FFFFFFFDh
0x180062d85  ja      short loc_180062D9C
0x180062d87  imul    eax, ecx, 0FFFFD8F0h
0x180062d8d  lea     r8, [rsp+220h+var_1C0]
0x180062d92  movsxd  rcx, eax
0x180062d95  mov     [rsp+220h+var_1C0], rcx
0x180062d9a  jmp     short loc_180062D9F
0x180062d9c  mov     r8, r15; Timeout
0x180062d9f  xor     edx, edx; Alertable
0x180062da1  mov     rcx, r9; Handle
0x180062da4  call    cs:__imp_NtWaitForSingleObject
0x180062dab  nop     dword ptr [rax+rax+00h]
0x180062db0  mov     ebx, eax
0x180062db2  test    eax, eax
0x180062db4  jz      short loc_180062DF7
0x180062db6  mov     ecx, eax; int
0x180062db8  call    ?PerfpDosError@@YAKJ@Z; PerfpDosError(long)
0x180062dbd  mov     edi, eax
0x180062dbf  mov     rcx, cs:WPP_GLOBAL_Control
0x180062dc6  test    [rcx+1Ch], r12b
0x180062dca  jz      loc_1800633FB
0x180062dd0  cmp     byte ptr [rcx+19h], 2
0x180062dd4  jb      loc_1800633CF
0x180062dda  mov     rcx, [rcx+10h]
0x180062dde  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180062de5  mov     edx, 0Ch
0x180062dea  mov     r9d, ebx
0x180062ded  call    WPP_SF_d
0x180062df2  jmp     loc_1800633C8
0x180062df7  lea     rcx, [rsp+220h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180062dfc  call    cs:__imp_GetSystemTimeAsFileTime
0x180062e03  nop     dword ptr [rax+rax+00h]
0x180062e08  cmp     cs:?bPerflibOpen@@3EA, r15b; uchar bPerflibOpen
0x180062e0f  jz      short loc_180062E35
0x180062e11  mov     rcx, 430E23400h
0x180062e1b  add     rcx, cs:qword_1800B2208
0x180062e22  cmp     rcx, qword ptr [rsp+220h+SystemTimeAsFileTime.dwLowDateTime]
0x180062e27  jbe     short loc_180062E35
0x180062e29  mov     rcx, cs:?hGlobalDataMutex@@3PEAXEA; void * hGlobalDataMutex
0x180062e30  jmp     loc_1800633BC
0x180062e35  mov     r13d, 1
0x180062e3b  mov     eax, r13d
0x180062e3e  lock xadd cs:?NumberOfOpens@@3JA, eax; long NumberOfOpens
0x180062e46  add     eax, r13d
0x180062e49  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180062e4d  cmp     cs:?bPerflibOpen@@3EA, r15b; uchar bPerflibOpen
0x180062e54  jnz     short loc_180062E60
0x180062e56  cmp     eax, r13d
0x180062e59  jz      short loc_180062E69
0x180062e5b  jmp     loc_180063398
0x180062e60  cmp     eax, 2
0x180062e63  jnz     loc_180063398
0x180062e69  call    ?PerflibciGetKeyPerflib@@YAPEAUHKEY__@@XZ; PerflibciGetKeyPerflib(void)
0x180062e6e  mov     rsi, rax
0x180062e71  test    rax, rax
0x180062e74  jnz     short loc_180062EC6
0x180062e76  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180062e7a  lock add cs:?NumberOfOpens@@3JA, ecx; long NumberOfOpens
0x180062e81  mov     rcx, cs:WPP_GLOBAL_Control
0x180062e88  test    [rcx+1Ch], r12b
0x180062e8c  jz      short loc_180062EAE
0x180062e8e  cmp     byte ptr [rcx+19h], 2
0x180062e92  jb      short loc_180062EAE
0x180062e94  mov     rcx, [rcx+10h]
0x180062e98  lea     edx, [rax+0Dh]
0x180062e9b  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x180062ea2  call    WPP_SF_
0x180062ea7  mov     rcx, cs:WPP_GLOBAL_Control
0x180062eae  mov     rax, cs:?hGlobalDataMutex@@3PEAXEA; void * hGlobalDataMutex
0x180062eb5  test    rax, rax
0x180062eb8  jz      loc_1800633CF
0x180062ebe  mov     rcx, rax
0x180062ec1  jmp     loc_1800633BC
0x180062ec6  mov     r8d, 208h; Size
0x180062ecc  lea     rdi, ?PerfpErrorLog@@3UERROR_LOG@@A.el_data_size; ERROR_LOG PerfpErrorLog ...
0x180062ed3  mov     rcx, rdi; void *
0x180062ed6  mov     [rsp+220h+var_1D8], r8d
0x180062edb  xor     edx, edx; Val
0x180062edd  call    memset_0
0x180062ee2  lea     rax, [rsp+220h+var_1D8]
0x180062ee7  mov     dword ptr [rsp+220h+hTemplateFile], r13d; int
0x180062eec  mov     qword ptr [rsp+220h+dwFlagsAndAttributes], rax; unsigned int *
0x180062ef1  lea     r9, [rsp+220h+var_1E0]; unsigned int *
0x180062ef6  lea     rdx, aUpdating; "Updating"
0x180062efd  mov     qword ptr [rsp+220h+dwCreationDisposition], rdi; unsigned __int8 *
0x180062f02  mov     rcx, rsi; KeyHandle
0x180062f05  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x180062f0a  test    eax, eax
0x180062f0c  jnz     short loc_180062F39
0x180062f0e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180062f12  lock add cs:?NumberOfOpens@@3JA, ecx; long NumberOfOpens
0x180062f19  mov     rcx, cs:?hGlobalDataMutex@@3PEAXEA; hMutex
0x180062f20  test    rcx, rcx
0x180062f23  jz      short loc_180062F31
0x180062f25  call    cs:__imp_ReleaseMutex
0x180062f2c  nop     dword ptr [rax+rax+00h]
0x180062f31  mov     edi, r15d
0x180062f34  jmp     loc_1800633C8
0x180062f39  lea     rax, [rsp+220h+var_1D8]
0x180062f3e  mov     dword ptr [rsp+220h+hTemplateFile], r13d; int
0x180062f43  mov     qword ptr [rsp+220h+dwFlagsAndAttributes], rax; unsigned int *
0x180062f48  lea     r9, [rsp+220h+var_1E0]; unsigned int *
0x180062f4d  lea     rax, [rsp+220h+var_1D0]
0x180062f52  mov     [rsp+220h+var_1D8], r12d
0x180062f57  lea     rdx, ?DisablePerformanceCounters@@3QBGB; "Disable Performance Counters"
0x180062f5e  mov     qword ptr [rsp+220h+dwCreationDisposition], rax; unsigned __int8 *
0x180062f63  mov     rcx, rsi; KeyHandle
0x180062f66  mov     dword ptr [rsp+220h+var_1E0], r15d
0x180062f6b  mov     dword ptr [rsp+220h+var_1D0], r15d
0x180062f70  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x180062f75  test    eax, eax
0x180062f77  jnz     short loc_180062F9C
0x180062f79  cmp     dword ptr [rsp+220h+var_1E0], r12d
0x180062f7e  jnz     short loc_180062F9C
0x180062f80  cmp     dword ptr [rsp+220h+var_1D0], r13d
0x180062f85  jnz     short loc_180062F9C
0x180062f87  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180062f8b  lock add cs:?NumberOfOpens@@3JA, esi; long NumberOfOpens
0x180062f92  mov     edi, 422h
0x180062f97  jmp     loc_180063326
0x180062f9c  cmp     cs:?pComputerName@@3PEAGEA, r15; ushort * pComputerName
0x180062fa3  mov     edi, r15d
0x180062fa6  jnz     loc_180063322
0x180062fac  lea     rdx, ?PerfpErrorLog@@3UERROR_LOG@@A.el_data; nSize
0x180062fb3  mov     dword ptr cs:?PerfpErrorLog@@3UERROR_LOG@@A.el_data, r15d; ERROR_LOG PerfpErrorLog ...
0x180062fba  xor     ecx, ecx; lpBuffer
0x180062fbc  call    cs:__imp_GetComputerNameW
0x180062fc3  nop     dword ptr [rax+rax+00h]
0x180062fc8  mov     eax, dword ptr cs:?PerfpErrorLog@@3UERROR_LOG@@A.el_data; ERROR_LOG PerfpErrorLog ...
0x180062fce  add     eax, r13d
0x180062fd1  mov     ecx, eax
0x180062fd3  mov     dword ptr cs:?PerfpErrorLog@@3UERROR_LOG@@A.el_data, eax; ERROR_LOG PerfpErrorLog ...
0x180062fd9  mov     eax, 2
0x180062fde  mul     rcx
0x180062fe1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180062fe8  cmovb   rax, rcx
0x180062fec  mov     rcx, rax
0x180062fef  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180062ff4  mov     cs:?pComputerName@@3PEAGEA, rax; ushort * pComputerName
0x180062ffb  test    rax, rax
0x180062ffe  jz      short loc_18006301A
0x180063000  lea     rdx, ?PerfpErrorLog@@3UERROR_LOG@@A.el_data; nSize
0x180063007  mov     rcx, rax; lpBuffer
0x18006300a  call    cs:__imp_GetComputerNameW
0x180063011  nop     dword ptr [rax+rax+00h]
0x180063016  test    eax, eax
0x180063018  jnz     short loc_18006301F
0x18006301a  mov     eax, r15d
0x18006301d  jmp     short loc_18006303E
0x18006301f  mov     rax, cs:?pComputerName@@3PEAGEA; ushort * pComputerName
0x180063026  mov     edx, dword ptr cs:?PerfpErrorLog@@3UERROR_LOG@@A.el_data; ERROR_LOG PerfpErrorLog ...
0x18006302c  mov     [rax+rdx*2], r15w
0x180063031  mov     eax, dword ptr cs:?PerfpErrorLog@@3UERROR_LOG@@A.el_data; ERROR_LOG PerfpErrorLog ...
0x180063037  lea     eax, ds:2[rax*2]
0x18006303e  mov     dword ptr cs:?PerfpErrorLog@@3UERROR_LOG@@A.el_data, eax; ERROR_LOG PerfpErrorLog ...
0x180063044  lea     r9, [rsp+220h+var_1E0]; unsigned int *
0x180063049  lea     rax, [rsp+220h+var_1D8]
0x18006304e  mov     dword ptr [rsp+220h+hTemplateFile], r13d; int
0x180063053  mov     qword ptr [rsp+220h+dwFlagsAndAttributes], rax; unsigned int
0x180063058  lea     rdx, ?cszPerflibFlags@@3QBGB; "Configuration Flags"
0x18006305f  lea     rax, ?lPerflibConfigFlags@@3JA; long lPerflibConfigFlags
0x180063066  mov     dword ptr [rsp+220h+var_1E0], r15d
0x18006306b  mov     rcx, rsi; KeyHandle
0x18006306e  mov     qword ptr [rsp+220h+dwCreationDisposition], rax; unsigned __int8 *
0x180063073  mov     [rsp+220h+var_1D8], r12d
0x180063078  call    ?PrivateRegQueryValueExT@@YAJPEAUHKEY__@@PEBGPEAK2PEAE2H@Z; PrivateRegQueryValueExT(HKEY__ *,ushort const *,ulong *,ulong *,uchar *,ulong *,int)
0x18006307d  test    eax, eax
0x18006307f  jnz     short loc_180063090
0x180063081  cmp     dword ptr [rsp+220h+var_1E0], r12d
0x180063086  jnz     short loc_180063090
0x180063088  mov     eax, cs:?lPerflibConfigFlags@@3JA; long lPerflibConfigFlags
0x18006308e  jmp     short loc_180063099
0x180063090  mov     eax, r12d
0x180063093  mov     cs:?lPerflibConfigFlags@@3JA, eax; long lPerflibConfigFlags
0x180063099  cmp     cs:?hPerflibSectionFile@@3PEAXEA, r15; void * hPerflibSectionFile
0x1800630a0  jnz     loc_180063322
0x1800630a6  mov     ebx, 10h
0x1800630ab  test    bl, al
0x1800630ad  jz      loc_180063322
0x1800630b3  mov     qword ptr [rsp+220h+var_1D8], r15
0x1800630b8  mov     [rsp+220h+var_1E0], r15
0x1800630bd  call    cs:__imp_GetCurrentProcessId
0x1800630c4  nop     dword ptr [rax+rax+00h]
0x1800630c9  mov     r9d, ebx; Radix
0x1800630cc  lea     r8d, [rbx+10h]; BufferCount
0x1800630d0  mov     ecx, eax; Value
0x1800630d2  lea     rdx, [rbp+120h+Buffer]; Buffer
0x1800630d9  call    cs:__imp__ultow_s
0x1800630e0  nop     dword ptr [rax+rax+00h]
0x1800630e5  lea     rax, [rsp+220h+var_1D8]
0x1800630ea  mov     edx, 104h; unsigned __int64
0x1800630ef  lea     rsi, ?szPerflibSectionName@@3PAGA; ushort near * szPerflibSectionName
0x1800630f6  mov     qword ptr [rsp+220h+dwCreationDisposition], rax; unsigned __int64 *
0x1800630fb  mov     rcx, rsi; unsigned __int16 *
0x1800630fe  lea     r9, [rsp+220h+var_1E0]; unsigned __int16 **
0x180063103  lea     r8, aTempPerflibPer; "%TEMP%\\Perflib_Perfdata_"
0x18006310a  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18006310f  test    eax, eax
0x180063111  js      loc_1800631CF
0x180063117  mov     rdx, qword ptr [rsp+220h+var_1D8]; unsigned __int64
0x18006311c  lea     rax, [rsp+220h+var_1D8]
0x180063121  mov     rcx, [rsp+220h+var_1E0]; unsigned __int16 *
0x180063126  lea     r9, [rsp+220h+var_1E0]; unsigned __int16 **
0x18006312b  lea     r8, [rbp+120h+Buffer]; unsigned __int16 *
0x180063132  mov     qword ptr [rsp+220h+dwCreationDisposition], rax; unsigned __int64 *
0x180063137  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18006313c  test    eax, eax
0x18006313e  js      loc_1800631CF
0x180063144  mov     rdx, qword ptr [rsp+220h+var_1D8]; unsigned __int64
0x180063149  lea     rax, [rsp+220h+var_1D8]
0x18006314e  mov     rcx, [rsp+220h+var_1E0]; unsigned __int16 *
0x180063153  lea     r9, [rsp+220h+var_1E0]; unsigned __int16 **
0x180063158  lea     r8, aDat; ".dat"
0x18006315f  mov     qword ptr [rsp+220h+dwCreationDisposition], rax; unsigned __int64 *
0x180063164  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180063169  test    eax, eax
0x18006316b  js      short loc_1800631CF
0x18006316d  mov     r8d, 104h; nSize
0x180063173  lea     rdx, ?szPerflibSectionFile@@3PAGA; lpDst
0x18006317a  mov     rcx, rsi; lpSrc
0x18006317d  call    cs:__imp_ExpandEnvironmentStringsW
0x180063184  nop     dword ptr [rax+rax+00h]
0x180063189  dec     eax
0x18006318b  cmp     eax, 103h
0x180063190  ja      short loc_1800631CF
  ... truncated ...
```
