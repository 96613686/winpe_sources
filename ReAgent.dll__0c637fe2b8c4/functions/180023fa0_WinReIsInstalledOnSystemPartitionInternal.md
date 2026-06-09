# WinReIsInstalledOnSystemPartitionInternal

- ea: `0x180023fa0`
- end: `0x1800243e1`
- name: `WinReIsInstalledOnSystemPartitionInternal`
- size: `1089`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001aa00`
- `0x180023f20`

## callees

- `0x1800059fc`
- `0x1800061c0`
- `0x18000c6f0`
- `0x18000ed74`
- `0x18000f044`
- `0x18001f75c`
- `0x180023fa0`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005cff0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800240f3`
- `KERNEL32!GetLastError` at `0x180024109`
- `KERNEL32!GetLastError` at `0x1800241ab`
- `KERNEL32!GetLastError` at `0x1800241cc`
- `KERNEL32!GetLastError` at `0x18002424e`
- `KERNEL32!GetLastError` at `0x180024295`
- `KERNEL32!GetLastError` at `0x180024361`
- `KERNEL32!GetLastError` at `0x1800240f3`
- `KERNEL32!GetLastError` at `0x180024109`
- `KERNEL32!GetLastError` at `0x1800241ab`
- `KERNEL32!GetLastError` at `0x1800241cc`
- `KERNEL32!GetLastError` at `0x18002424e`
- `KERNEL32!GetLastError` at `0x180024295`
- `KERNEL32!GetLastError` at `0x180024361`
- `KERNEL32!HeapFree` at `0x1800240e9`
- `KERNEL32!HeapFree` at `0x1800243ad`
- `KERNEL32!HeapFree` at `0x1800240e9`
- `KERNEL32!HeapFree` at `0x1800243ad`
- `KERNEL32!HeapAlloc` at `0x180024087`
- `KERNEL32!HeapAlloc` at `0x180024087`
- `KERNEL32!GetProcessHeap` at `0x180024078`
- `KERNEL32!GetProcessHeap` at `0x1800240db`
- `KERNEL32!GetProcessHeap` at `0x18002439f`
- `KERNEL32!GetProcessHeap` at `0x180024078`
- `KERNEL32!GetProcessHeap` at `0x1800240db`
- `KERNEL32!GetProcessHeap` at `0x18002439f`
- `KERNEL32!CompareStringW` at `0x1800242fd`
- `KERNEL32!CompareStringW` at `0x1800242fd`
- `KERNEL32!GetVolumePathNameW` at `0x180024244`
- `KERNEL32!GetVolumePathNameW` at `0x180024244`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18002428b`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1800242d0`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x18002428b`
- `KERNEL32!GetVolumeNameForVolumeMountPointW` at `0x1800242d0`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x180024357`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x180024357`
- `bcd!SyspartGetSystemPartition` at `0x180024051`
- `bcd!SyspartGetSystemPartition` at `0x1800240a1`
- `bcd!SyspartGetSystemPartition` at `0x180024051`
- `bcd!SyspartGetSystemPartition` at `0x1800240a1`

## string_xrefs

- `0x18002402e`: ` (WinRE)WinReIsInstalledOnSystemPartitionInternal() Invalid parameters`
- `0x18002412c`: ` (WinRE) WinReIsInstalledOnSystemPartitionInternal() GetSystemPartitionNTPath failed. Error: 0x%08x`
- `0x18002417e`: ` (WinRE) WinReIsInstalledOnSystemPartitionInternal() StringCchPrintf failed. Error: 0x%08x`
- `0x1800241b1`: ` (WinRE) WinReIsInstalledOnSystemPartitionInternal() winreGetConfigByGuid failed. Error: 0x%08x`
- `0x1800241d2`: `failed to get winre config. Error: 0x%08x`
- `0x180024254`: ` (WinRE) WinReIsInstalledOnSystemPartitionInternal() GetVolumePathName failed. Error: 0x%08x`
- `0x180024269`: ` (WinRE) WinReIsInstalledOnSystemPartitionInternal() WinRE volume path: %s`
- `0x18002429e`: ` (WinRE) WinReIsInstalledOnSystemPartitionInternal() GetVolumeNameForVolumeMountPoint failed. Error: 0x%08x`
- `0x1800242b3`: ` (WinRE) WinReIsInstalledOnSystemPartitionInternal() System volume path: %s`
- `0x180024303`: ` (WinRE) WinReIsInstalledOnSystemPartitionInternal() WinRE image is on the system partition`
- `0x18002430d`: ` (WinRE) WinReIsInstalledOnSystemPartitionInternal() WinRE is not located on the System partition`
- `0x180024329`: ` (WinRE) WinReIsInstalledOnSystemPartitionInternal() WinRE is not enabled`
- `0x180024367`: ` (WinRE) WinReIsInstalledOnSystemPartitionInternal() GetDiskFreeSpaceEx failed. Error: 0x%08x`
- `0x180024384`: ` (WinRE) WinReIsInstalledOnSystemPartitionInternal() Free space on %s: %I64u`
- `0x1800240b9`: `GetSystemPartitionNTPath: Found system partition at [%s].`
- `0x1800240cd`: `GetSystemPartitionNTPath: BCD APIs could not find system partition; status = 0x%x`
- `0x180024144`: `GetSystemPartitionNTPath: BCD APIs could not find system partition; status = 0x%x`

## pseudocode

```c
__int64 __fastcall WinReIsInstalledOnSystemPartitionInternal(const struct _GUID *a1, union _ULARGE_INTEGER *a2)
{
  unsigned int v4; // r12d
  unsigned int SystemPartition; // eax
  SIZE_T v6; // rbx
  HANDLE ProcessHeap; // rax
  LPVOID v8; // rax
  void *v9; // rsi
  int v10; // eax
  signed int v11; // ebx
  HANDLE v12; // rax
  signed int LastError; // eax
  bool v14; // sf
  signed int v15; // eax
  __int64 v16; // r8
  const wchar_t *v17; // rdx
  __int64 v18; // rcx
  signed int v19; // eax
  int v20; // eax
  const wchar_t *v21; // rdx
  int v22; // ebx
  DWORD v23; // eax
  HANDLE v24; // rax
  union _ULARGE_INTEGER FreeBytesAvailableToCaller; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+40h] [rbp-C0h] BYREF
  int v28; // [rsp+48h] [rbp-B8h]
  WCHAR szFileName[1556]; // [rsp+2B8h] [rbp+1B8h] BYREF
  WCHAR szVolumeName[64]; // [rsp+EE0h] [rbp+DE0h] BYREF
  WCHAR String1[64]; // [rsp+F60h] [rbp+E60h] BYREF
  WCHAR szVolumeMountPoint; // [rsp+FE0h] [rbp+EE0h] BYREF
  _BYTE v33[606]; // [rsp+FE2h] [rbp+EE2h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+1240h] [rbp+1140h] BYREF

  szVolumeMountPoint = 0;
  v4 = 0;
  memset_0(v33, 0, 0x25Au);
  memset_0(&v27, 0, 0xEA0u);
  if ( a2 )
  {
    FreeBytesAvailableToCaller.QuadPart = 0;
    a2->QuadPart = 0;
  }
  if ( (unsigned int)winreIsWinPE() && !a1 )
  {
    UnattendLogW(1, L" (WinRE)WinReIsInstalledOnSystemPartitionInternal() Invalid parameters");
    return v4;
  }
  FreeBytesAvailableToCaller.LowPart = 0;
  SystemPartition = SyspartGetSystemPartition(0, 0, &FreeBytesAvailableToCaller);
  if ( SystemPartition != -1073741789 || !FreeBytesAvailableToCaller.LowPart )
  {
    v9 = 0;
    LibLog(
      &g_WdsLibLog,
      0x4000000,
      L"GetSystemPartitionNTPath: BCD APIs could not find system partition; status = 0x%x",
      SystemPartition);
    goto LABEL_23;
  }
  v6 = 2LL * FreeBytesAvailableToCaller.LowPart;
  ProcessHeap = GetProcessHeap();
  v8 = HeapAlloc(ProcessHeap, 8u, v6);
  v9 = v8;
  if ( v8 )
  {
    v10 = SyspartGetSystemPartition(v8, FreeBytesAvailableToCaller.LowPart, &FreeBytesAvailableToCaller);
    if ( v10 < 0 )
    {
      LibLog(
        &g_WdsLibLog,
        0x4000000,
        L"GetSystemPartitionNTPath: BCD APIs could not find system partition; status = 0x%x",
        (unsigned int)v10);
      v11 = 1;
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v9);
      v9 = 0;
    }
    else
    {
      v11 = 0;
      LibLog(&g_WdsLibLog, 0x4000000, L"GetSystemPartitionNTPath: Found system partition at [%s].", v9);
    }
  }
  else
  {
    LastError = GetLastError();
    v14 = LastError < 0;
    if ( LastError > 0 )
      v14 = 1;
    if ( v14 )
    {
      v15 = GetLastError();
      v11 = v15;
      if ( v15 > 0 )
        v11 = (unsigned __int16)v15 | 0x80070000;
    }
    else
    {
      v11 = -2147467259;
    }
  }
  if ( v11 >= 0 )
  {
LABEL_23:
    v19 = StringCchPrintfW(&szVolumeMountPoint, 0x12Eu, L"\\\\?\\GLOBALROOT%s\\", v9);
    if ( v19 < 0 )
    {
      v17 = L" (WinRE) WinReIsInstalledOnSystemPartitionInternal() StringCchPrintf failed. Error: 0x%08x";
LABEL_25:
      v16 = (unsigned int)v19;
      v18 = 1;
      goto LABEL_21;
    }
    v27 = 3744;
    if ( a1 )
    {
      if ( !(unsigned int)winreGetConfigByGuid(a1, (struct _WINRE_CONFIG *)&v27) )
      {
        v19 = GetLastError();
        v17 = L" (WinRE) WinReIsInstalledOnSystemPartitionInternal() winreGetConfigByGuid failed. Error: 0x%08x";
        goto LABEL_25;
      }
    }
    else if ( !(unsigned int)WinReGetConfigInternal(0, 0, &v27) )
    {
      v19 = GetLastError();
      v17 = L"failed to get winre config. Error: 0x%08x";
      goto LABEL_25;
    }
    if ( v28 && szFileName[0] )
    {
      memset_0(szVolumePathName, 0, 0x208u);
      memset_0(szVolumeName, 0, sizeof(szVolumeName));
      memset_0(String1, 0, sizeof(String1));
      if ( !GetVolumePathNameW(szFileName, szVolumePathName, 0x104u) )
      {
        v19 = GetLastError();
        v17 = L" (WinRE) WinReIsInstalledOnSystemPartitionInternal() GetVolumePathName failed. Error: 0x%08x";
        goto LABEL_25;
      }
      UnattendLogW(0, L" (WinRE) WinReIsInstalledOnSystemPartitionInternal() WinRE volume path: %s", szVolumePathName);
      if ( !GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x40u)
        || (UnattendLogW(
              0,
              L" (WinRE) WinReIsInstalledOnSystemPartitionInternal() System volume path: %s",
              &szVolumeMountPoint),
            !GetVolumeNameForVolumeMountPointW(&szVolumeMountPoint, String1, 0x40u)) )
      {
        v16 = GetLastError();
        v17 = L" (WinRE) WinReIsInstalledOnSystemPartitionInternal() GetVolumeNameForVolumeMountPoint failed. Error: 0x%08x";
        goto LABEL_20;
      }
      v20 = CompareStringW(0x409u, 1u, String1, -1, szVolumeName, -1);
      v21 = L" (WinRE) WinReIsInstalledOnSystemPartitionInternal() WinRE image is on the system partition";
      v22 = v20 - 2;
      if ( v20 != 2 )
        v21 = L" (WinRE) WinReIsInstalledOnSystemPartitionInternal() WinRE is not located on the System partition";
      UnattendLogW(0, v21);
      LOBYTE(v4) = v22 == 0;
    }
    else
    {
      UnattendLogW(0, L" (WinRE) WinReIsInstalledOnSystemPartitionInternal() WinRE is not enabled");
    }
    if ( a2 )
    {
      FreeBytesAvailableToCaller.QuadPart = 0;
      if ( !GetDiskFreeSpaceExW(&szVolumeMountPoint, &FreeBytesAvailableToCaller, 0, 0) )
      {
        v23 = GetLastError();
        UnattendLogW(
          1,
          L" (WinRE) WinReIsInstalledOnSystemPartitionInternal() GetDiskFreeSpaceEx failed. Error: 0x%08x",
          v23);
      }
      UnattendLogW(
        0,
        L" (WinRE) WinReIsInstalledOnSystemPartitionInternal() Free space on %s: %I64u",
        &szVolumeMountPoint,
        FreeBytesAvailableToCaller.QuadPart);
      *a2 = FreeBytesAvailableToCaller;
    }
    goto LABEL_46;
  }
  v16 = (unsigned int)v11;
  v17 = L" (WinRE) WinReIsInstalledOnSystemPartitionInternal() GetSystemPartitionNTPath failed. Error: 0x%08x";
LABEL_20:
  v18 = 2;
LABEL_21:
  UnattendLogW(v18, v17, v16);
LABEL_46:
  if ( v9 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v9);
  }
  return v4;
}

```

## disassembly

```asm
0x180023fa0  mov     [rsp-8+arg_0], rbx
0x180023fa5  mov     [rsp-8+arg_10], rsi
0x180023faa  push    rbp
0x180023fab  push    rdi
0x180023fac  push    r12
0x180023fae  push    r14
0x180023fb0  push    r15
0x180023fb2  lea     rbp, [rsp-1360h]
0x180023fba  mov     eax, 1460h
0x180023fbf  call    _alloca_probe
0x180023fc4  sub     rsp, rax
0x180023fc7  mov     rax, cs:__security_cookie
0x180023fce  xor     rax, rsp
0x180023fd1  mov     [rbp+1380h+var_30], rax
0x180023fd8  mov     r15, rdx
0x180023fdb  mov     r14, rcx
0x180023fde  xor     eax, eax
0x180023fe0  lea     rcx, [rbp+1380h+var_49E]; void *
0x180023fe7  xor     edx, edx; Val
0x180023fe9  mov     [rbp+1380h+szVolumeMountPoint], ax
0x180023ff0  mov     r8d, 25Ah; Size
0x180023ff6  xor     r12d, r12d
0x180023ff9  call    memset_0
0x180023ffe  xor     edx, edx; Val
0x180024000  lea     rcx, [rsp+1480h+var_1440]; void *
0x180024005  mov     r8d, 0EA0h; Size
0x18002400b  call    memset_0
0x180024010  test    r15, r15
0x180024013  jz      short loc_180024020
0x180024015  mov     eax, r12d
0x180024018  mov     qword ptr [rsp+1480h+FreeBytesAvailableToCaller], r12
0x18002401d  mov     [r15], rax
0x180024020  call    ?winreIsWinPE@@YAHXZ; winreIsWinPE(void)
0x180024025  test    eax, eax
0x180024027  jz      short loc_180024043
0x180024029  test    r14, r14
0x18002402c  jnz     short loc_180024043
0x18002402e  lea     rdx, aWinreWinreisin_3; " (WinRE)WinReIsInstalledOnSystemPartiti"...
0x180024035  lea     ecx, [r14+1]
0x180024039  call    UnattendLogW
0x18002403e  jmp     loc_1800243B3
0x180024043  lea     r8, [rsp+1480h+FreeBytesAvailableToCaller]
0x180024048  mov     dword ptr [rsp+1480h+FreeBytesAvailableToCaller], r12d
0x18002404d  xor     edx, edx
0x18002404f  xor     ecx, ecx
0x180024051  call    cs:__imp_SyspartGetSystemPartition
0x180024057  mov     edi, 1
0x18002405c  cmp     eax, 0C0000023h
0x180024061  jnz     loc_180024142
0x180024067  mov     ecx, dword ptr [rsp+1480h+FreeBytesAvailableToCaller]
0x18002406b  test    ecx, ecx
0x18002406d  jz      loc_180024142
0x180024073  mov     ebx, ecx
0x180024075  add     rbx, rbx
0x180024078  call    cs:__imp_GetProcessHeap
0x18002407e  mov     r8, rbx; dwBytes
0x180024081  lea     edx, [rdi+7]; dwFlags
0x180024084  mov     rcx, rax; hHeap
0x180024087  call    cs:__imp_HeapAlloc
0x18002408d  mov     rsi, rax
0x180024090  test    rax, rax
0x180024093  jz      short loc_1800240F3
0x180024095  mov     edx, dword ptr [rsp+1480h+FreeBytesAvailableToCaller]
0x180024099  lea     r8, [rsp+1480h+FreeBytesAvailableToCaller]
0x18002409e  mov     rcx, rax
0x1800240a1  call    cs:__imp_SyspartGetSystemPartition
0x1800240a7  mov     edx, 4000000h
0x1800240ac  lea     rcx, g_WdsLibLog
0x1800240b3  test    eax, eax
0x1800240b5  js      short loc_1800240CA
0x1800240b7  xor     ebx, ebx
0x1800240b9  lea     r8, aGetsystemparti_0; "GetSystemPartitionNTPath: Found system "...
0x1800240c0  mov     r9, rsi
0x1800240c3  call    LibLog
0x1800240c8  jmp     short loc_180024125
0x1800240ca  mov     r9d, eax
0x1800240cd  lea     r8, aGetsystemparti; "GetSystemPartitionNTPath: BCD APIs coul"...
0x1800240d4  call    LibLog
0x1800240d9  mov     ebx, edi
0x1800240db  call    cs:__imp_GetProcessHeap
0x1800240e1  mov     r8, rsi; lpMem
0x1800240e4  xor     edx, edx; dwFlags
0x1800240e6  mov     rcx, rax; hHeap
0x1800240e9  call    cs:__imp_HeapFree
0x1800240ef  xor     esi, esi
0x1800240f1  jmp     short loc_180024125
0x1800240f3  call    cs:__imp_GetLastError
0x1800240f9  test    eax, eax
0x1800240fb  jle     short loc_180024107
0x1800240fd  movzx   eax, ax
0x180024100  or      eax, 80070000h
0x180024105  test    eax, eax
0x180024107  jns     short loc_180024120
0x180024109  call    cs:__imp_GetLastError
0x18002410f  mov     ebx, eax
0x180024111  test    eax, eax
0x180024113  jle     short loc_180024125
0x180024115  movzx   ebx, ax
0x180024118  or      ebx, 80070000h
0x18002411e  jmp     short loc_180024125
0x180024120  mov     ebx, 80004005h
0x180024125  test    ebx, ebx
0x180024127  jns     short loc_18002415F
0x180024129  mov     r8d, ebx
0x18002412c  lea     rdx, aWinreWinreisin_10; " (WinRE) WinReIsInstalledOnSystemPartit"...
0x180024133  mov     ecx, 2
0x180024138  call    UnattendLogW
0x18002413d  jmp     loc_18002439A
0x180024142  xor     esi, esi
0x180024144  lea     r8, aGetsystemparti; "GetSystemPartitionNTPath: BCD APIs coul"...
0x18002414b  mov     r9d, eax
0x18002414e  lea     rcx, g_WdsLibLog
0x180024155  mov     edx, 4000000h
0x18002415a  call    LibLog
0x18002415f  mov     r9, rsi
0x180024162  lea     r8, aGlobalrootS_0; "\\\\?\\GLOBALROOT%s\\"
0x180024169  mov     edx, 12Eh; unsigned __int64
0x18002416e  lea     rcx, [rbp+1380h+szVolumeMountPoint]; unsigned __int16 *
0x180024175  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002417a  test    eax, eax
0x18002417c  jns     short loc_18002418C
0x18002417e  lea     rdx, aWinreWinreisin_1; " (WinRE) WinReIsInstalledOnSystemPartit"...
0x180024185  mov     r8d, eax
0x180024188  mov     ecx, edi
0x18002418a  jmp     short loc_180024138
0x18002418c  mov     [rsp+1480h+var_1440], 0EA0h
0x180024195  test    r14, r14
0x180024198  jz      short loc_1800241BA
0x18002419a  lea     rdx, [rsp+1480h+var_1440]; struct _WINRE_CONFIG *
0x18002419f  mov     rcx, r14; struct _GUID *
0x1800241a2  call    ?winreGetConfigByGuid@@YAHPEBU_GUID@@PEAU_WINRE_CONFIG@@@Z; winreGetConfigByGuid(_GUID const *,_WINRE_CONFIG *)
0x1800241a7  test    eax, eax
0x1800241a9  jnz     short loc_1800241DB
0x1800241ab  call    cs:__imp_GetLastError
0x1800241b1  lea     rdx, aWinreWinreisin_9; " (WinRE) WinReIsInstalledOnSystemPartit"...
0x1800241b8  jmp     short loc_180024185
0x1800241ba  lea     r8, [rsp+1480h+var_1440]
0x1800241bf  xor     edx, edx
0x1800241c1  xor     ecx, ecx
0x1800241c3  call    WinReGetConfigInternal
0x1800241c8  test    eax, eax
0x1800241ca  jnz     short loc_1800241DB
0x1800241cc  call    cs:__imp_GetLastError
0x1800241d2  lea     rdx, aFailedToGetWin_5; "failed to get winre config. Error: 0x%0"...
0x1800241d9  jmp     short loc_180024185
0x1800241db  cmp     [rsp+1480h+var_1438], r12d
0x1800241e0  jz      loc_180024329
0x1800241e6  xor     eax, eax
0x1800241e8  cmp     ax, [rbp+1380h+szFileName]
0x1800241ef  jz      loc_180024329
0x1800241f5  xor     edx, edx; Val
0x1800241f7  lea     rcx, [rbp+1380h+szVolumePathName]; void *
0x1800241fe  mov     r8d, 208h; Size
0x180024204  call    memset_0
0x180024209  mov     ebx, 80h
0x18002420e  lea     rcx, [rbp+1380h+szVolumeName]; void *
0x180024215  mov     r8d, ebx; Size
0x180024218  xor     edx, edx; Val
0x18002421a  call    memset_0
0x18002421f  mov     r8d, ebx; Size
0x180024222  lea     rcx, [rbp+1380h+String1]; void *
0x180024229  xor     edx, edx; Val
0x18002422b  call    memset_0
0x180024230  mov     r8d, 104h; cchBufferLength
0x180024236  lea     rdx, [rbp+1380h+szVolumePathName]; lpszVolumePathName
0x18002423d  lea     rcx, [rbp+1380h+szFileName]; lpszFileName
0x180024244  call    cs:__imp_GetVolumePathNameW
0x18002424a  test    eax, eax
0x18002424c  jnz     short loc_180024260
0x18002424e  call    cs:__imp_GetLastError
0x180024254  lea     rdx, aWinreWinreisin_5; " (WinRE) WinReIsInstalledOnSystemPartit"...
0x18002425b  jmp     loc_180024185
0x180024260  lea     r8, [rbp+1380h+szVolumePathName]
0x180024267  xor     ecx, ecx
0x180024269  lea     rdx, aWinreWinreisin_7; " (WinRE) WinReIsInstalledOnSystemPartit"...
0x180024270  call    UnattendLogW
0x180024275  mov     ebx, 40h ; '@'
0x18002427a  lea     rdx, [rbp+1380h+szVolumeName]; lpszVolumeName
0x180024281  mov     r8d, ebx; cchBufferLength
0x180024284  lea     rcx, [rbp+1380h+szVolumePathName]; lpszVolumeMountPoint
0x18002428b  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180024291  test    eax, eax
0x180024293  jnz     short loc_1800242AA
0x180024295  call    cs:__imp_GetLastError
0x18002429b  mov     r8d, eax
0x18002429e  lea     rdx, aWinreWinreisin_11; " (WinRE) WinReIsInstalledOnSystemPartit"...
0x1800242a5  jmp     loc_180024133
0x1800242aa  lea     r8, [rbp+1380h+szVolumeMountPoint]
0x1800242b1  xor     ecx, ecx
0x1800242b3  lea     rdx, aWinreWinreisin; " (WinRE) WinReIsInstalledOnSystemPartit"...
0x1800242ba  call    UnattendLogW
0x1800242bf  mov     r8d, ebx; cchBufferLength
0x1800242c2  lea     rdx, [rbp+1380h+String1]; lpszVolumeName
0x1800242c9  lea     rcx, [rbp+1380h+szVolumeMountPoint]; lpszVolumeMountPoint
0x1800242d0  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800242d6  test    eax, eax
0x1800242d8  jz      short loc_180024295
0x1800242da  or      r9d, 0FFFFFFFFh; cchCount1
0x1800242de  lea     rax, [rbp+1380h+szVolumeName]
0x1800242e5  mov     [rsp+1480h+cchCount2], r9d; cchCount2
0x1800242ea  lea     r8, [rbp+1380h+String1]; lpString1
0x1800242f1  mov     edx, edi; dwCmpFlags
0x1800242f3  mov     [rsp+1480h+lpString2], rax; lpString2
0x1800242f8  mov     ecx, 409h; Locale
0x1800242fd  call    cs:__imp_CompareStringW
0x180024303  lea     rdx, aWinreWinreisin_2; " (WinRE) WinReIsInstalledOnSystemPartit"...
0x18002430a  lea     ebx, [rax-2]
0x18002430d  lea     rax, aWinreWinreisin_0; " (WinRE) WinReIsInstalledOnSystemPartit"...
0x180024314  test    ebx, ebx
0x180024316  cmovnz  rdx, rax
0x18002431a  xor     ecx, ecx
0x18002431c  call    UnattendLogW
0x180024321  test    ebx, ebx
0x180024323  setz    r12b
0x180024327  jmp     short loc_180024337
0x180024329  lea     rdx, aWinreWinreisin_4; " (WinRE) WinReIsInstalledOnSystemPartit"...
0x180024330  xor     ecx, ecx
0x180024332  call    UnattendLogW
0x180024337  test    r15, r15
0x18002433a  jz      short loc_18002439A
0x18002433c  xor     r9d, r9d; lpTotalNumberOfFreeBytes
0x18002433f  mov     qword ptr [rsp+1480h+FreeBytesAvailableToCaller], 0
0x180024348  xor     r8d, r8d; lpTotalNumberOfBytes
0x18002434b  lea     rdx, [rsp+1480h+FreeBytesAvailableToCaller]; lpFreeBytesAvailableToCaller
0x180024350  lea     rcx, [rbp+1380h+szVolumeMountPoint]; lpDirectoryName
0x180024357  call    cs:__imp_GetDiskFreeSpaceExW
0x18002435d  test    eax, eax
0x18002435f  jnz     short loc_180024378
0x180024361  call    cs:__imp_GetLastError
0x180024367  lea     rdx, aWinreWinreisin_8; " (WinRE) WinReIsInstalledOnSystemPartit"...
0x18002436e  mov     ecx, edi
0x180024370  mov     r8d, eax
0x180024373  call    UnattendLogW
0x180024378  mov     r9, qword ptr [rsp+1480h+FreeBytesAvailableToCaller]
0x18002437d  lea     r8, [rbp+1380h+szVolumeMountPoint]
0x180024384  lea     rdx, aWinreWinreisin_6; " (WinRE) WinReIsInstalledOnSystemPartit"...
0x18002438b  xor     ecx, ecx
0x18002438d  call    UnattendLogW
0x180024392  mov     rcx, qword ptr [rsp+1480h+FreeBytesAvailableToCaller]
0x180024397  mov     [r15], rcx
0x18002439a  test    rsi, rsi
0x18002439d  jz      short loc_1800243B3
0x18002439f  call    cs:__imp_GetProcessHeap
0x1800243a5  mov     r8, rsi; lpMem
0x1800243a8  xor     edx, edx; dwFlags
0x1800243aa  mov     rcx, rax; hHeap
0x1800243ad  call    cs:__imp_HeapFree
0x1800243b3  mov     eax, r12d
0x1800243b6  mov     rcx, [rbp+1380h+var_30]
0x1800243bd  xor     rcx, rsp; StackCookie
0x1800243c0  call    __security_check_cookie
0x1800243c5  lea     r11, [rsp+1480h+var_20]
0x1800243cd  mov     rbx, [r11+30h]
0x1800243d1  mov     rsi, [r11+40h]
0x1800243d5  mov     rsp, r11
0x1800243d8  pop     r15
0x1800243da  pop     r14
0x1800243dc  pop     r12
0x1800243de  pop     rdi
0x1800243df  pop     rbp
0x1800243e0  retn
```
