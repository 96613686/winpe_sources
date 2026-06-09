# pEnumeratePartitions(_GUID *,_LIST_ENTRY *)

- ea: `0x18000d67c`
- end: `0x18000dd28`
- name: `?pEnumeratePartitions@@YAKPEAU_GUID@@PEAU_LIST_ENTRY@@@Z`
- size: `1708`
- prototype: `unsigned int __fastcall(struct _GUID *, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task`

## callers

- `0x18000ee80`

## callees

- `0x180002ba8`
- `0x1800059fc`
- `0x180006ed8`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x18000d67c`
- `0x18000eb1c`
- `0x180010e78`
- `0x180011134`
- `0x180050500`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000db23`
- `msvcrt!_wcsicmp` at `0x18000db23`
- `KERNEL32!GetLastError` at `0x18000d743`
- `KERNEL32!GetLastError` at `0x18000d8a0`
- `KERNEL32!GetLastError` at `0x18000d93e`
- `KERNEL32!GetLastError` at `0x18000d743`
- `KERNEL32!GetLastError` at `0x18000d8a0`
- `KERNEL32!GetLastError` at `0x18000d93e`
- `KERNEL32!HeapFree` at `0x18000d787`
- `KERNEL32!HeapFree` at `0x18000d7a2`
- `KERNEL32!HeapFree` at `0x18000d8c5`
- `KERNEL32!HeapFree` at `0x18000dcc5`
- `KERNEL32!HeapFree` at `0x18000dcde`
- `KERNEL32!HeapFree` at `0x18000d787`
- `KERNEL32!HeapFree` at `0x18000d7a2`
- `KERNEL32!HeapFree` at `0x18000d8c5`
- `KERNEL32!HeapFree` at `0x18000dcc5`
- `KERNEL32!HeapFree` at `0x18000dcde`
- `KERNEL32!HeapAlloc` at `0x18000d856`
- `KERNEL32!HeapAlloc` at `0x18000d8ea`
- `KERNEL32!HeapAlloc` at `0x18000d95d`
- `KERNEL32!HeapAlloc` at `0x18000d856`
- `KERNEL32!HeapAlloc` at `0x18000d8ea`
- `KERNEL32!HeapAlloc` at `0x18000d95d`
- `KERNEL32!GetProcessHeap` at `0x18000d779`
- `KERNEL32!GetProcessHeap` at `0x18000d794`
- `KERNEL32!GetProcessHeap` at `0x18000d844`
- `KERNEL32!GetProcessHeap` at `0x18000d8b7`
- `KERNEL32!GetProcessHeap` at `0x18000d8db`
- `KERNEL32!GetProcessHeap` at `0x18000d94b`
- `KERNEL32!GetProcessHeap` at `0x18000dcb7`
- `KERNEL32!GetProcessHeap` at `0x18000dcd0`
- `KERNEL32!GetProcessHeap` at `0x18000d779`
- `KERNEL32!GetProcessHeap` at `0x18000d794`
- `KERNEL32!GetProcessHeap` at `0x18000d844`
- `KERNEL32!GetProcessHeap` at `0x18000d8b7`
- `KERNEL32!GetProcessHeap` at `0x18000d8db`
- `KERNEL32!GetProcessHeap` at `0x18000d94b`
- `KERNEL32!GetProcessHeap` at `0x18000dcb7`
- `KERNEL32!GetProcessHeap` at `0x18000dcd0`
- `KERNEL32!CreateFileW` at `0x18000d829`
- `KERNEL32!CreateFileW` at `0x18000d829`
- `KERNEL32!CloseHandle` at `0x18000d76b`
- `KERNEL32!CloseHandle` at `0x18000dcac`
- `KERNEL32!CloseHandle` at `0x18000d76b`
- `KERNEL32!CloseHandle` at `0x18000dcac`
- `KERNEL32!DeviceIoControl` at `0x18000d892`
- `KERNEL32!DeviceIoControl` at `0x18000d934`
- `KERNEL32!DeviceIoControl` at `0x18000d9da`
- `KERNEL32!DeviceIoControl` at `0x18000db04`
- `KERNEL32!DeviceIoControl` at `0x18000d892`
- `KERNEL32!DeviceIoControl` at `0x18000d934`
- `KERNEL32!DeviceIoControl` at `0x18000d9da`
- `KERNEL32!DeviceIoControl` at `0x18000db04`
- `KERNEL32!GetDriveTypeW` at `0x18000d7ae`
- `KERNEL32!GetDriveTypeW` at `0x18000d7ae`
- `KERNEL32!FindFirstVolumeW` at `0x18000d732`
- `KERNEL32!FindFirstVolumeW` at `0x18000d732`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x18000da9e`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x18000da9e`
- `KERNEL32!FindNextVolumeW` at `0x18000db94`
- `KERNEL32!FindNextVolumeW` at `0x18000db94`
- `KERNEL32!FindVolumeClose` at `0x18000dc99`
- `KERNEL32!FindVolumeClose` at `0x18000dc99`

## string_xrefs

- `0x18000dbf0`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x18000dc34`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x18000dc59`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x18000dbe9`: `failed to copy volume name`
- `0x18000dbd1`: `failed to create partition name`

## pseudocode

```c
__int64 __fastcall pEnumeratePartitions(struct _GUID *a1, struct _LIST_ENTRY *a2)
{
  DWORD LastError; // ebx
  __int64 v4; // r14
  _DWORD *v5; // rsi
  struct _LIST_ENTRY **v6; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v8; // rax
  int v9; // r15d
  unsigned __int64 v10; // r15
  unsigned __int64 v11; // rcx
  HANDLE FileW; // rax
  HANDLE v13; // rax
  HANDLE v14; // rax
  SIZE_T v15; // rbx
  HANDLE v16; // rax
  HANDLE v17; // rax
  LPVOID v18; // rax
  __int64 v19; // r9
  struct _LIST_ENTRY *v20; // r15
  struct _LIST_ENTRY *Flink; // rax
  const wchar_t *v22; // r8
  __int64 v23; // r9
  const wchar_t *v24; // r8
  HANDLE v25; // rax
  HANDLE v26; // rax
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hFindVolume; // [rsp+50h] [rbp-B0h]
  struct _LIST_ENTRY *v32; // [rsp+58h] [rbp-A8h]
  DWORD BytesReturned; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v34; // [rsp+64h] [rbp-9Ch] BYREF
  _ULARGE_INTEGER FreeBytesAvailableToCaller; // [rsp+68h] [rbp-98h] BYREF
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+70h] [rbp-90h] BYREF
  int OutBuffer; // [rsp+80h] [rbp-80h] BYREF
  __int64 v38; // [rsp+88h] [rbp-78h]
  DWORD v39; // [rsp+98h] [rbp-68h]
  char v40; // [rsp+A0h] [rbp-60h]
  unsigned __int8 v41; // [rsp+A1h] [rbp-5Fh]
  struct _LIST_ENTRY *v42; // [rsp+A2h] [rbp-5Eh]
  int v43; // [rsp+AAh] [rbp-56h]
  __int16 v44; // [rsp+AEh] [rbp-52h]
  int v45; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v46[92]; // [rsp+114h] [rbp+14h] BYREF
  WCHAR szVolumeName[304]; // [rsp+170h] [rbp+70h] BYREF
  wchar_t String1[304]; // [rsp+3D0h] [rbp+2D0h] BYREF

  v32 = a2;
  memset_0(String1, 0, 0x25Cu);
  v45 = 0;
  memset_0(v46, 0, sizeof(v46));
  memset_0(&OutBuffer, 0, 0x90u);
  v30 = 0;
  v34 = 0;
  BytesReturned = 0;
  TotalNumberOfBytes.QuadPart = 0;
  FreeBytesAvailableToCaller.QuadPart = 0;
  winreGetWindowsVolume(a1, String1);
  hFindVolume = FindFirstVolumeW(szVolumeName, 0x12Eu);
  if ( hFindVolume == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    goto LABEL_62;
  }
  v4 = -1;
  v5 = 0;
  v6 = 0;
  while ( 1 )
  {
    LastError = 0;
    if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle((HANDLE)v4);
      v4 = 0;
    }
    if ( v6 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v6);
      v6 = 0;
    }
    if ( v5 )
    {
      v8 = GetProcessHeap();
      HeapFree(v8, 0, v5);
      v5 = 0;
    }
    if ( GetDriveTypeW(szVolumeName) != 3 )
      goto LABEL_39;
    v9 = StringCchLengthW(szVolumeName, 0x12Eu, &v30);
    if ( v9 < 0 )
    {
      LODWORD(dwFlagsAndAttributes) = 1951;
      UnattendLogW(
        2,
        L"pEnumeratePartitions %s (0x%x) in file %S line %d",
        L"failed to get volume name length",
        (unsigned int)v9,
        "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
        dwFlagsAndAttributes);
      LastError = (unsigned __int16)v9;
      goto LABEL_54;
    }
    v10 = v30;
    if ( !v30 )
      goto LABEL_39;
    v11 = 2 * v30 - 2;
    if ( v11 >= 0x25C )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)szVolumeName + v11) = 0;
    FileW = CreateFileW(szVolumeName, 1u, 7u, 0, 3u, 0x2000000u, 0);
    v4 = (__int64)FileW;
    if ( FileW == (HANDLE)-1LL )
      goto LABEL_39;
    winreIsRemovableDisk(FileW);
    v13 = GetProcessHeap();
    v5 = HeapAlloc(v13, 8u, 0x20u);
    if ( !v5 )
      break;
    if ( !DeviceIoControl((HANDLE)v4, 0x560000u, 0, 0, v5, 0x20u, &BytesReturned, 0) )
    {
      if ( GetLastError() != 234 )
        goto LABEL_39;
      BytesReturned = *v5;
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v5);
      v15 = 24LL * BytesReturned + 32;
      v16 = GetProcessHeap();
      v5 = HeapAlloc(v16, 8u, v15);
      if ( !v5 )
      {
        LODWORD(dwFlagsAndAttributes) = 2015;
        goto LABEL_50;
      }
      if ( !DeviceIoControl((HANDLE)v4, 0x560000u, 0, 0, v5, 24 * BytesReturned + 32, &v34, 0) )
      {
        LastError = GetLastError();
        goto LABEL_39;
      }
    }
    v17 = GetProcessHeap();
    v18 = HeapAlloc(v17, 8u, 0x530u);
    v6 = (struct _LIST_ENTRY **)v18;
    if ( !v18 )
    {
      LODWORD(dwFlagsAndAttributes) = 2038;
      goto LABEL_50;
    }
    LastError = StringCchCopyW((unsigned __int16 *)v18 + 26, 0x12Eu, szVolumeName);
    if ( (LastError & 0x80000000) != 0 )
    {
      LODWORD(dwFlagsAndAttributes) = 2042;
      v24 = L"failed to copy volume name";
      goto LABEL_47;
    }
    LastError = 0;
    v6[158] = (struct _LIST_ENTRY *)*((_QWORD *)v5 + 2);
    v6[159] = (struct _LIST_ENTRY *)*((_QWORD *)v5 + 3);
    *((_DWORD *)v6 + 324) = v5[2];
    if ( !DeviceIoControl((HANDLE)v4, 0x70048u, 0, 0, &OutBuffer, 0x90u, &v34, 0) )
      goto LABEL_37;
    if ( *((_QWORD *)v5 + 2) == v38 )
    {
      v19 = *((unsigned int *)v6 + 324);
      *((_DWORD *)v6 + 325) = v39;
      dwCreationDisposition[0] = v39;
      LastError = StringCchPrintfW(
                    (unsigned __int16 *)v6 + 328,
                    0x12Eu,
                    L"\\\\?\\GLOBALROOT\\device\\harddisk%u\\partition%u",
                    v19,
                    *(_QWORD *)dwCreationDisposition);
      if ( (LastError & 0x80000000) != 0 )
      {
        LODWORD(dwFlagsAndAttributes) = 2081;
        v24 = L"failed to create partition name";
LABEL_47:
        UnattendLogW(
          2,
          L"pEnumeratePartitions %s (0x%x) in file %S line %d",
          v24,
          LastError,
          "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
          dwFlagsAndAttributes);
        LastError = (unsigned __int16)LastError;
        goto LABEL_54;
      }
      if ( !OutBuffer )
      {
        *((_DWORD *)v6 + 327) = 1;
        *((_DWORD *)v6 + 328) = v41;
        *((_BYTE *)v6 + 16) = v40;
LABEL_30:
        *(_WORD *)&v46[2 * v10 + 90] = 92;
        if ( GetDiskFreeSpaceExW(szVolumeName, &FreeBytesAvailableToCaller, &TotalNumberOfBytes, 0) )
        {
          v6[160] = (struct _LIST_ENTRY *)FreeBytesAvailableToCaller.QuadPart;
          v6[161] = (struct _LIST_ENTRY *)TotalNumberOfBytes.QuadPart;
        }
        LastError = winreGetDiskSignature((struct PartitionNode *)v6);
        if ( LastError )
        {
          LODWORD(dwFlagsAndAttributes) = 2118;
          v22 = L"failed to get disk signature";
          v23 = LastError;
          goto LABEL_51;
        }
        if ( DeviceIoControl((HANDLE)v4, 0x90064u, 0, 0, &v45, 0x60u, &v34, 0) )
        {
          *((_DWORD *)v6 + 326) = 1;
          if ( !_wcsicmp(String1, (const wchar_t *)v6 + 26) )
            *((_DWORD *)v6 + 329) = 1;
          FveDetectVolumeEx((STRSAFE_PCNZWCH)v6 + 328);
        }
LABEL_37:
        v20 = v32;
        Flink = v32->Flink;
        if ( v32->Flink->Blink != v32 )
          __fastfail(3u);
        *v6 = Flink;
        v6[1] = v20;
        Flink->Blink = (struct _LIST_ENTRY *)v6;
        v20->Flink = (struct _LIST_ENTRY *)v6;
        v6 = 0;
        goto LABEL_39;
      }
      if ( OutBuffer == 1 )
      {
        *((_BYTE *)v6 + 16) = v40;
        *((_BYTE *)v6 + 17) = v41;
        *(struct _LIST_ENTRY **)((char *)v6 + 18) = v42;
        *(_DWORD *)((char *)v6 + 26) = v43;
        *((_WORD *)v6 + 15) = v44;
        goto LABEL_30;
      }
      LastError = 0;
    }
LABEL_39:
    if ( !FindNextVolumeW(hFindVolume, szVolumeName, 0x12Eu) )
      goto LABEL_54;
  }
  LODWORD(dwFlagsAndAttributes) = 1984;
LABEL_50:
  LastError = 8;
  v22 = L"failed to allocate memory";
  v23 = 8;
LABEL_51:
  UnattendLogW(
    2,
    L"pEnumeratePartitions %s (0x%x) in file %S line %d",
    v22,
    v23,
    "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
    dwFlagsAndAttributes);
LABEL_54:
  if ( hFindVolume )
    FindVolumeClose(hFindVolume);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v4);
  if ( v6 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v6);
  }
  if ( v5 )
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v5);
  }
LABEL_62:
  if ( LastError )
    UnattendLogW(1, L"pEnumeratePartitions failed: 0x%x", LastError);
  return LastError;
}

```

## disassembly

```asm
0x18000d67c  mov     [rsp-8+arg_10], rbx
0x18000d681  push    rbp
0x18000d682  push    rsi
0x18000d683  push    rdi
0x18000d684  push    r12
0x18000d686  push    r13
0x18000d688  push    r14
0x18000d68a  push    r15
0x18000d68c  lea     rbp, [rsp-540h]
0x18000d694  sub     rsp, 640h
0x18000d69b  mov     rax, cs:__security_cookie
0x18000d6a2  xor     rax, rsp
0x18000d6a5  mov     [rbp+570h+var_40], rax
0x18000d6ac  mov     [rsp+670h+var_618], rdx
0x18000d6b1  mov     rbx, rcx
0x18000d6b4  xor     edx, edx; Val
0x18000d6b6  lea     rcx, [rbp+570h+String1]; void *
0x18000d6bd  mov     r8d, 25Ch; Size
0x18000d6c3  call    memset_0
0x18000d6c8  xor     edx, edx; Val
0x18000d6ca  mov     [rbp+570h+var_560], 0
0x18000d6d1  lea     rcx, [rbp+570h+var_55C]; void *
0x18000d6d5  lea     r8d, [rdx+5Ch]; Size
0x18000d6d9  call    memset_0
0x18000d6de  xor     edx, edx; Val
0x18000d6e0  lea     rcx, [rbp+570h+OutBuffer]; void *
0x18000d6e4  mov     r8d, 90h; Size
0x18000d6ea  call    memset_0
0x18000d6ef  lea     rdx, [rbp+570h+String1]
0x18000d6f6  mov     [rsp+670h+var_628], 0
0x18000d6ff  mov     rcx, rbx
0x18000d702  mov     [rsp+670h+var_60C], 0
0x18000d70a  mov     [rsp+670h+BytesReturned], 0
0x18000d712  mov     qword ptr [rsp+670h+TotalNumberOfBytes], 0
0x18000d71b  mov     qword ptr [rsp+670h+FreeBytesAvailableToCaller], 0
0x18000d724  call    winreGetWindowsVolume
0x18000d729  mov     edx, 12Eh; cchBufferLength
0x18000d72e  lea     rcx, [rbp+570h+szVolumeName]; lpszVolumeName
0x18000d732  call    cs:__imp_FindFirstVolumeW
0x18000d738  mov     [rsp+670h+hFindVolume], rax
0x18000d73d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d741  jnz     short loc_18000D750
0x18000d743  call    cs:__imp_GetLastError
0x18000d749  mov     ebx, eax
0x18000d74b  jmp     loc_18000DCE4
0x18000d750  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000d754  xor     esi, esi
0x18000d756  xor     edi, edi
0x18000d758  lea     r12d, [r14+9]
0x18000d75c  xor     ebx, ebx
0x18000d75e  lea     rax, [r14-1]
0x18000d762  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d766  ja      short loc_18000D774
0x18000d768  mov     rcx, r14; hObject
0x18000d76b  call    cs:__imp_CloseHandle
0x18000d771  xor     r14d, r14d
0x18000d774  test    rdi, rdi
0x18000d777  jz      short loc_18000D78F
0x18000d779  call    cs:__imp_GetProcessHeap
0x18000d77f  mov     r8, rdi; lpMem
0x18000d782  xor     edx, edx; dwFlags
0x18000d784  mov     rcx, rax; hHeap
0x18000d787  call    cs:__imp_HeapFree
0x18000d78d  xor     edi, edi
0x18000d78f  test    rsi, rsi
0x18000d792  jz      short loc_18000D7AA
0x18000d794  call    cs:__imp_GetProcessHeap
0x18000d79a  mov     r8, rsi; lpMem
0x18000d79d  xor     edx, edx; dwFlags
0x18000d79f  mov     rcx, rax; hHeap
0x18000d7a2  call    cs:__imp_HeapFree
0x18000d7a8  xor     esi, esi
0x18000d7aa  lea     rcx, [rbp+570h+szVolumeName]; lpRootPathName
0x18000d7ae  call    cs:__imp_GetDriveTypeW
0x18000d7b4  cmp     eax, 3
0x18000d7b7  jnz     loc_18000DB85
0x18000d7bd  lea     r8, [rsp+670h+var_628]; unsigned __int64 *
0x18000d7c2  mov     edx, 12Eh; unsigned __int64
0x18000d7c7  lea     rcx, [rbp+570h+szVolumeName]; unsigned __int16 *
0x18000d7cb  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000d7d0  mov     r15d, eax
0x18000d7d3  test    eax, eax
0x18000d7d5  js      loc_18000DC59
0x18000d7db  mov     r15, [rsp+670h+var_628]
0x18000d7e0  cmp     r15, 1
0x18000d7e4  jb      loc_18000DB85
0x18000d7ea  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[r15*2]
0x18000d7f2  cmp     rcx, 25Ch
0x18000d7f9  jnb     loc_18000DC53
0x18000d7ff  xor     eax, eax
0x18000d801  xor     r9d, r9d; lpSecurityAttributes
0x18000d804  mov     [rsp+670h+hTemplateFile], rax; hTemplateFile
0x18000d809  mov     [rbp+rcx+570h+szVolumeName], ax
0x18000d80e  lea     rcx, [rbp+570h+szVolumeName]; lpFileName
0x18000d812  mov     dword ptr [rsp+670h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18000d81a  lea     edx, [rax+1]; dwDesiredAccess
0x18000d81d  mov     [rsp+670h+dwCreationDisposition], 3; dwCreationDisposition
0x18000d825  lea     r8d, [rax+7]; dwShareMode
0x18000d829  call    cs:__imp_CreateFileW
0x18000d82f  mov     r14, rax
0x18000d832  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d836  jz      loc_18000DB85
0x18000d83c  mov     rcx, rax
0x18000d83f  call    winreIsRemovableDisk
0x18000d844  call    cs:__imp_GetProcessHeap
0x18000d84a  mov     r8d, 20h ; ' '; dwBytes
0x18000d850  mov     edx, r12d; dwFlags
0x18000d853  mov     rcx, rax; hHeap
0x18000d856  call    cs:__imp_HeapAlloc
0x18000d85c  mov     rsi, rax
0x18000d85f  test    rax, rax
0x18000d862  jz      loc_18000DC1F
0x18000d868  mov     [rsp+670h+lpOverlapped], rbx; lpOverlapped
0x18000d86d  lea     rax, [rsp+670h+BytesReturned]
0x18000d872  mov     [rsp+670h+hTemplateFile], rax; lpBytesReturned
0x18000d877  xor     r9d, r9d; nInBufferSize
0x18000d87a  mov     dword ptr [rsp+670h+dwFlagsAndAttributes], 20h ; ' '; nOutBufferSize
0x18000d882  xor     r8d, r8d; lpInBuffer
0x18000d885  mov     edx, 560000h; dwIoControlCode
0x18000d88a  mov     qword ptr [rsp+670h+dwCreationDisposition], rsi; lpOutBuffer
0x18000d88f  mov     rcx, r14; hDevice
0x18000d892  call    cs:__imp_DeviceIoControl
0x18000d898  test    eax, eax
0x18000d89a  jnz     loc_18000D94B
0x18000d8a0  call    cs:__imp_GetLastError
0x18000d8a6  cmp     eax, 0EAh
0x18000d8ab  jnz     loc_18000DB85
0x18000d8b1  mov     eax, [rsi]
0x18000d8b3  mov     [rsp+670h+BytesReturned], eax
0x18000d8b7  call    cs:__imp_GetProcessHeap
0x18000d8bd  mov     r8, rsi; lpMem
0x18000d8c0  xor     edx, edx; dwFlags
0x18000d8c2  mov     rcx, rax; hHeap
0x18000d8c5  call    cs:__imp_HeapFree
0x18000d8cb  mov     eax, [rsp+670h+BytesReturned]
0x18000d8cf  lea     rcx, [rax+rax*2]
0x18000d8d3  lea     rbx, ds:20h[rcx*8]
0x18000d8db  call    cs:__imp_GetProcessHeap
0x18000d8e1  mov     r8, rbx; dwBytes
0x18000d8e4  mov     edx, r12d; dwFlags
0x18000d8e7  mov     rcx, rax; hHeap
0x18000d8ea  call    cs:__imp_HeapAlloc
0x18000d8f0  mov     rsi, rax
0x18000d8f3  test    rax, rax
0x18000d8f6  jz      loc_18000DBAB
0x18000d8fc  mov     eax, [rsp+670h+BytesReturned]
0x18000d900  xor     r9d, r9d; nInBufferSize
0x18000d903  mov     [rsp+670h+lpOverlapped], 0; lpOverlapped
0x18000d90c  xor     r8d, r8d; lpInBuffer
0x18000d90f  mov     edx, 560000h; dwIoControlCode
0x18000d914  lea     ecx, [rax+rax*2]
0x18000d917  lea     ecx, ds:20h[rcx*8]
0x18000d91e  lea     rax, [rsp+670h+var_60C]
0x18000d923  mov     [rsp+670h+hTemplateFile], rax; lpBytesReturned
0x18000d928  mov     dword ptr [rsp+670h+dwFlagsAndAttributes], ecx; nOutBufferSize
0x18000d92c  mov     rcx, r14; hDevice
0x18000d92f  mov     qword ptr [rsp+670h+dwCreationDisposition], rsi; lpOutBuffer
0x18000d934  call    cs:__imp_DeviceIoControl
0x18000d93a  test    eax, eax
0x18000d93c  jnz     short loc_18000D94B
0x18000d93e  call    cs:__imp_GetLastError
0x18000d944  mov     ebx, eax
0x18000d946  jmp     loc_18000DB85
0x18000d94b  call    cs:__imp_GetProcessHeap
0x18000d951  mov     r8d, 530h; dwBytes
0x18000d957  mov     edx, r12d; dwFlags
0x18000d95a  mov     rcx, rax; hHeap
0x18000d95d  call    cs:__imp_HeapAlloc
0x18000d963  mov     rdi, rax
0x18000d966  test    rax, rax
0x18000d969  jz      loc_18000DC15
0x18000d96f  lea     r8, [rbp+570h+szVolumeName]; unsigned __int16 *
0x18000d973  mov     edx, 12Eh; unsigned __int64
0x18000d978  lea     rcx, [rax+34h]; unsigned __int16 *
0x18000d97c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000d981  mov     ebx, eax
0x18000d983  test    eax, eax
0x18000d985  js      loc_18000DBE1
0x18000d98b  mov     rax, [rsi+10h]
0x18000d98f  xor     ebx, ebx
0x18000d991  mov     [rdi+4F0h], rax
0x18000d998  xor     r9d, r9d; nInBufferSize
0x18000d99b  mov     rax, [rsi+18h]
0x18000d99f  xor     r8d, r8d; lpInBuffer
0x18000d9a2  mov     [rdi+4F8h], rax
0x18000d9a9  mov     edx, 70048h; dwIoControlCode
0x18000d9ae  mov     eax, [rsi+8]
0x18000d9b1  mov     rcx, r14; hDevice
0x18000d9b4  mov     [rdi+510h], eax
0x18000d9ba  lea     rax, [rsp+670h+var_60C]
0x18000d9bf  mov     [rsp+670h+lpOverlapped], rbx; lpOverlapped
0x18000d9c4  mov     [rsp+670h+hTemplateFile], rax; lpBytesReturned
0x18000d9c9  lea     rax, [rbp+570h+OutBuffer]
0x18000d9cd  mov     dword ptr [rsp+670h+dwFlagsAndAttributes], 90h; nOutBufferSize
0x18000d9d5  mov     qword ptr [rsp+670h+dwCreationDisposition], rax; lpOutBuffer
0x18000d9da  call    cs:__imp_DeviceIoControl
0x18000d9e0  test    eax, eax
0x18000d9e2  jz      loc_18000DB61
0x18000d9e8  mov     rax, [rbp+570h+var_5E8]
0x18000d9ec  cmp     [rsi+10h], rax
0x18000d9f0  jnz     loc_18000DB7F
0x18000d9f6  mov     eax, [rbp+570h+var_5D8]
0x18000d9f9  lea     r13, [rdi+290h]
0x18000da00  mov     r9d, [rdi+510h]
0x18000da07  lea     r8, aGlobalrootDevi; "\\\\?\\GLOBALROOT\\device\\harddisk%u\\"...
0x18000da0e  mov     [rdi+514h], eax
0x18000da14  mov     rcx, r13; unsigned __int16 *
0x18000da17  mov     eax, [rbp+570h+var_5D8]
0x18000da1a  mov     edx, 12Eh; unsigned __int64
0x18000da1f  mov     [rsp+670h+dwCreationDisposition], eax
0x18000da23  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000da28  mov     ebx, eax
0x18000da2a  test    eax, eax
0x18000da2c  js      loc_18000DBC9
0x18000da32  mov     eax, [rbp+570h+OutBuffer]
0x18000da35  test    eax, eax
0x18000da37  jnz     short loc_18000DA55
0x18000da39  mov     dword ptr [rdi+51Ch], 1
0x18000da43  movzx   eax, [rbp+570h+var_5CF]
0x18000da47  mov     [rdi+520h], eax
0x18000da4d  mov     al, [rbp+570h+var_5D0]
0x18000da50  mov     [rdi+10h], al
0x18000da53  jmp     short loc_18000DA82
0x18000da55  cmp     eax, 1
0x18000da58  jnz     loc_18000DBA7
0x18000da5e  mov     al, [rbp+570h+var_5D0]
0x18000da61  mov     [rdi+10h], al
0x18000da64  mov     al, [rbp+570h+var_5CF]
0x18000da67  mov     [rdi+11h], al
0x18000da6a  movsd   xmm0, [rbp+570h+var_5CE]
0x18000da6f  movsd   qword ptr [rdi+12h], xmm0
0x18000da74  mov     eax, [rbp+570h+var_5C6]
0x18000da77  mov     [rdi+1Ah], eax
0x18000da7a  movzx   eax, [rbp+570h+var_5C2]
0x18000da7e  mov     [rdi+1Eh], ax
0x18000da82  mov     eax, 5Ch ; '\'
0x18000da87  lea     r8, [rsp+670h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x18000da8c  xor     r9d, r9d; lpTotalNumberOfFreeBytes
0x18000da8f  mov     [rbp+r15*2+570h+var_502], ax
0x18000da95  lea     rdx, [rsp+670h+FreeBytesAvailableToCaller]; lpFreeBytesAvailableToCaller
0x18000da9a  lea     rcx, [rbp+570h+szVolumeName]; lpDirectoryName
0x18000da9e  call    cs:__imp_GetDiskFreeSpaceExW
0x18000daa4  test    eax, eax
0x18000daa6  jz      short loc_18000DAC0
0x18000daa8  mov     rax, qword ptr [rsp+670h+FreeBytesAvailableToCaller]
0x18000daad  mov     [rdi+500h], rax
0x18000dab4  mov     rax, qword ptr [rsp+670h+TotalNumberOfBytes]
0x18000dab9  mov     [rdi+508h], rax
0x18000dac0  mov     rcx, rdi; struct PartitionNode *
0x18000dac3  call    ?winreGetDiskSignature@@YAKPEAUPartitionNode@@@Z; winreGetDiskSignature(PartitionNode *)
0x18000dac8  mov     ebx, eax
0x18000daca  test    eax, eax
0x18000dacc  jnz     loc_18000DBB5
0x18000dad2  mov     [rsp+670h+lpOverlapped], 0; lpOverlapped
0x18000dadb  lea     rax, [rsp+670h+var_60C]
0x18000dae0  mov     [rsp+670h+hTemplateFile], rax; lpBytesReturned
0x18000dae5  xor     r9d, r9d; nInBufferSize
0x18000dae8  lea     rax, [rbp+570h+var_560]
0x18000daec  mov     dword ptr [rsp+670h+dwFlagsAndAttributes], 60h ; '`'; nOutBufferSize
0x18000daf4  xor     r8d, r8d; lpInBuffer
0x18000daf7  mov     qword ptr [rsp+670h+dwCreationDisposition], rax; lpOutBuffer
0x18000dafc  mov     edx, 90064h; dwIoControlCode
0x18000db01  mov     rcx, r14; hDevice
0x18000db04  call    cs:__imp_DeviceIoControl
0x18000db0a  test    eax, eax
0x18000db0c  jz      short loc_18000DB61
0x18000db0e  lea     rdx, [rdi+34h]; String2
0x18000db12  mov     dword ptr [rdi+518h], 1
0x18000db1c  lea     rcx, [rbp+570h+String1]; String1
0x18000db23  call    cs:__imp__wcsicmp
0x18000db29  test    eax, eax
0x18000db2b  jnz     short loc_18000DB37
0x18000db2d  mov     dword ptr [rdi+524h], 1
0x18000db37  lea     rdx, [rsp+670h+var_630]
0x18000db3c  mov     [rsp+670h+var_630], 0
0x18000db44  mov     rcx, r13; psz
0x18000db47  call    FveDetectVolumeEx
0x18000db4c  test    eax, eax
0x18000db4e  js      short loc_18000DB61
0x18000db50  test    byte ptr [rsp+670h+var_630], 1
0x18000db55  jz      short loc_18000DB61
0x18000db57  mov     dword ptr [rdi+528h], 1
0x18000db61  mov     r15, [rsp+670h+var_618]
0x18000db66  mov     rax, [r15]
0x18000db69  cmp     [rax+8], r15
0x18000db6d  jnz     short loc_18000DBDA
0x18000db6f  mov     [rdi], rax
0x18000db72  mov     [rdi+8], r15
0x18000db76  mov     [rax+8], rdi
0x18000db7a  mov     [r15], rdi
0x18000db7d  xor     edi, edi
0x18000db7f  mov     r12d, 8
0x18000db85  mov     rcx, [rsp+670h+hFindVolume]; hFindVolume
0x18000db8a  lea     rdx, [rbp+570h+szVolumeName]; lpszVolumeName
0x18000db8e  mov     r8d, 12Eh; cchBufferLength
0x18000db94  call    cs:__imp_FindNextVolumeW
0x18000db9a  test    eax, eax
0x18000db9c  jnz     loc_18000D75C
0x18000dba2  jmp     loc_18000DC8C
0x18000dba7  xor     ebx, ebx
  ... truncated ...
```
