# sub_1800F5ACC

- ea: `0x1800f5acc`
- end: `0x1800f671f`
- name: `sub_1800F5ACC`
- size: `3155`
- prototype: `__int64 __fastcall(void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800f6940`
- `0x1800f6a98`

## callees

- `0x180057fe4`
- `0x180068c4c`
- `0x180068c64`
- `0x180069108`
- `0x1800695b4`
- `0x1800994a0`
- `0x180099ee0`
- `0x1800ad3e0`
- `0x1800cd0e8`
- `0x1800cd56c`
- `0x1800cd9c8`
- `0x1800cde64`
- `0x1800f5acc`
- `0x1800f6728`
- `0x1800f688c`
- `0x1800f6d18`
- `0x1800f72c0`
- `0x18020cab0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x1800f5d44`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x1800f5d44`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800f5d2a`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800f5d2a`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x1800f5c3d`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x1800f5c3d`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800f5be3`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800f5be3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800f5bb9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800f5bb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f6629`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f6629`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800f6618`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800f6618`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f5ba0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f5ba0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800f5b88`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800f5b88`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f5c0d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f5c0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f66ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800f66ed`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f5b38`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f5b38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f5b1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f66d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f5b1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f66d9`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x1800f5c79`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x1800f5c79`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsA` at `0x1800f5dc0`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsA` at `0x1800f5dc0`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x1800f5db2`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x1800f5db2`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x1800f5ca0`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x1800f5cb4`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x1800f5ca0`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x1800f5cb4`

## pseudocode

```c
__int64 __fastcall sub_1800F5ACC(void *Src, size_t Size, HKEY a3, DWORD *a4)
{
  HKEY v4; // r13
  size_t v6; // rbx
  __int64 result; // rax
  HANDLE ProcessHeap; // rax
  __int64 v9; // r12
  _BYTE *v10; // r15
  unsigned int v11; // esi
  unsigned int v12; // eax
  __int64 v13; // rdi
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  char *v16; // rbx
  char *v17; // r13
  CHAR *EnvironmentStringsW; // r15
  void (__fastcall *v19)(BYTE *); // rbx
  unsigned int v20; // r14d
  const char *v21; // r12
  const char *v22; // r12
  void (__fastcall *v23)(BYTE *, const char *, _QWORD); // rdi
  void (__fastcall *v24)(BYTE *, __int128 *); // rbx
  char *v25; // r13
  void (__fastcall *v26)(BYTE *); // rbx
  void (__fastcall *v27)(BYTE *, char *, _QWORD); // rdi
  void (__fastcall *v28)(BYTE *, char *); // rbx
  unsigned int v29; // eax
  __int64 v30; // r14
  unsigned int v31; // ecx
  __int64 v32; // rax
  unsigned int v33; // ecx
  __int64 v34; // rax
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  void (__fastcall *v37)(_OWORD *); // rbx
  void (__fastcall *v38)(_OWORD *, __int64, _QWORD); // rdi
  void (__fastcall *v39)(_OWORD *, __int64); // rbx
  void (__fastcall *v40)(_DWORD *); // rbx
  void (__fastcall *v41)(_DWORD *, __int64, _QWORD); // rdi
  void (__fastcall *v42)(_DWORD *, __int64); // rbx
  void (__fastcall *v43)(_DWORD *); // rbx
  void (__fastcall *v44)(_DWORD *, __int64, _QWORD); // rdi
  void (__fastcall *v45)(_DWORD *, __int64); // rbx
  void (__fastcall *v46)(_DWORD *); // rbx
  void (__fastcall *v47)(_DWORD *, __int64, _QWORD); // rdi
  void (__fastcall *v48)(_DWORD *, __int64); // rbx
  void (__fastcall *v49)(_DWORD *); // rbx
  void (__fastcall *v50)(_DWORD *, __int64, _QWORD); // rdi
  void (__fastcall *v51)(_DWORD *, __int64); // rbx
  __int64 v52; // r14
  __int64 v53; // rdi
  void (__fastcall *v54)(_BYTE *, _OWORD *, __int64); // rbx
  __int64 v55; // rdx
  unsigned int v56; // esi
  void (__fastcall *v57)(_BYTE *, BYTE *, BYTE *, __int64); // rbx
  __int64 v58; // rdx
  BYTE *v59; // rax
  void (__fastcall *v60)(_BYTE *, _OWORD *, __int64); // rbx
  _BYTE *v61; // rax
  DWORD v62; // ebx
  void (__fastcall *v63)(_BYTE *, HKEY, HKEY, _QWORD); // rdi
  _BYTE *v64; // rax
  _BYTE *v65; // rax
  HANDLE v66; // rax
  int v67; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  char *v69; // [rsp+40h] [rbp-C0h]
  __int64 v70; // [rsp+48h] [rbp-B8h]
  DWORD *v71; // [rsp+50h] [rbp-B0h]
  _OWORD v72[8]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[128]; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v74[32]; // [rsp+160h] [rbp+60h] BYREF
  _DWORD v75[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  _DWORD v76[32]; // [rsp+260h] [rbp+160h] BYREF
  _DWORD v77[32]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v78[272]; // [rsp+360h] [rbp+260h] BYREF

  v71 = a4;
  v4 = a3;
  hKey = a3;
  v6 = (unsigned int)Size;
  if ( (unsigned int)sub_1800F6728(Src, Size, a3, a4) )
    return 1;
  ProcessHeap = GetProcessHeap();
  v9 = 3584;
  result = (__int64)HeapAlloc(ProcessHeap, 0, 0xE00u);
  v70 = result;
  v10 = (_BYTE *)result;
  if ( result )
  {
    v11 = 3584;
    if ( (unsigned int)v6 <= 0xE00 )
    {
      memcpy((void *)result, Src, v6);
      v12 = (v6 + 8) & 0xFFFFFFF8;
      if ( v12 > 0xE00 )
        goto LABEL_6;
      v13 = v12;
      v14 = 3584 - v12;
      *(_DWORD *)&v10[v12] = GetCurrentProcessId();
      if ( v14 < 8 )
        goto LABEL_6;
      v15 = v14 - 8;
      *(_DWORD *)&v10[v13 + 8] = GetCurrentThreadId();
      if ( v15 < 8 )
        goto LABEL_6;
      *(_DWORD *)&v10[v13 + 16] = GetTickCount();
      if ( v15 - 8 < 8 )
        goto LABEL_6;
      v11 = v15 - 16;
      if ( v15 - 16 < 0x10 )
        goto LABEL_87;
      v16 = &v10[v13];
      GetLocalTime((LPSYSTEMTIME)&v10[v13 + 24]);
      if ( v11 < 0x18 )
      {
LABEL_6:
        v11 = 0;
      }
      else
      {
        v11 -= 24;
        if ( v11 >= 8 )
        {
          QueryPerformanceCounter((LARGE_INTEGER *)v16 + 6);
          if ( v11 >= 0x10 )
          {
            v11 -= 16;
            if ( v11 < 0x40 )
              goto LABEL_86;
            *((_DWORD *)v16 + 16) = 64;
            GlobalMemoryStatusEx((LPMEMORYSTATUSEX)v16 + 1);
            if ( v11 >= 0x48 )
            {
              v11 -= 72;
              if ( v11 < 0x10 )
                goto LABEL_86;
              v17 = v16 + 136;
              v69 = v16 + 136;
              GetDiskFreeSpaceW(0, (LPDWORD)v16 + 34, (LPDWORD)v16 + 35, (LPDWORD)v16 + 36, (LPDWORD)v16 + 37);
              if ( v11 >= 0x18 )
              {
                v11 -= 24;
                if ( !dword_18028D0E0 )
                {
                  v67 = 0;
                  EnvironmentStringsW = (CHAR *)GetEnvironmentStringsW();
                  if ( EnvironmentStringsW || (v67 = 1, (EnvironmentStringsW = (CHAR *)GetEnvironmentStringsW()) != 0) )
                  {
                    memset(Data, 0, 0x6Cu);
                    v19 = (void (__fastcall *)(BYTE *))sub_180069108(&word_180270E2A);
                    v19(Data);
                    sub_180068C4C(v19);
                    v20 = 0;
                    v21 = EnvironmentStringsW;
                    do
                    {
                      v22 = &v21[v20];
                      if ( v67 )
                      {
                        v21 = v22 + 1;
                        v20 = strnlen(v21, 0x7FFFu);
                      }
                      else
                      {
                        v21 = v22 + 2;
                        v20 = 2 * wcsnlen((const wchar_t *)v21, 0x7FFFu);
                      }
                      v23 = (void (__fastcall *)(BYTE *, const char *, _QWORD))sub_180068C64(byte_1802724D1);
                      v23(Data, v21, v20);
                      sub_180068C4C(v23);
                    }
                    while ( v20 );
                    v24 = (void (__fastcall *)(BYTE *, __int128 *))sub_180069108(&word_180272A02);
                    v24(Data, &xmmword_18028D260);
                    sub_180068C4C(v24);
                    v17 = v69;
                    if ( v67 )
                      FreeEnvironmentStringsA(EnvironmentStringsW);
                    else
                      FreeEnvironmentStringsW((LPWCH)EnvironmentStringsW);
                    v9 = 3584;
                  }
                  v10 = (_BYTE *)v70;
                  dword_18028D0E0 = 1;
                }
                if ( v11 < 0x10 )
                  goto LABEL_86;
                *(_OWORD *)(v17 + 24) = xmmword_18028D260;
                if ( v11 >= 0x18 )
                {
                  v11 -= 24;
                  if ( !(unsigned int)sub_1800F688C() )
                    goto LABEL_86;
                  if ( v11 < 0x40 )
                    goto LABEL_86;
                  if ( !qword_18028FD40 )
                    goto LABEL_86;
                  v67 = v11;
                  v25 = v17 + 48;
                  qword_18028FD40(5, v25, v11);
                  memset(Data, 0, 0x7Cu);
                  v26 = (void (__fastcall *)(BYTE *))sub_1800CD9C8(&word_18026FA66);
                  v26(Data);
                  sub_180057FE4(v26);
                  v27 = (void (__fastcall *)(BYTE *, char *, _QWORD))sub_1800CDE64(&byte_1802617F7);
                  v27(Data, v25, v11);
                  sub_180057FE4(v27);
                  v28 = (void (__fastcall *)(BYTE *, char *))sub_1800CD56C(byte_180261DAB);
                  v28(Data, v25);
                  sub_180057FE4(v28);
                  v11 -= 24;
                  if ( v11 < 0x30 )
                    goto LABEL_86;
                  if ( (int)((__int64 (__fastcall *)(__int64, char *, __int64, int *))qword_18028FD40)(
                              3,
                              v25 + 24,
                              48,
                              &v67) < 0 )
                  {
                    v30 = (__int64)(v25 + 24);
                  }
                  else
                  {
                    v29 = (v67 + 8) & 0xFFFFFFF8;
                    if ( v29 > v11 )
                      goto LABEL_14;
                    v11 -= v29;
                    v30 = (__int64)&v25[v29 + 24];
                    if ( v11 < 0x18 )
                      goto LABEL_86;
                  }
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, int *))qword_18028FD40)(
                              7,
                              v30,
                              24,
                              &v67) >= 0 )
                  {
                    v31 = (v67 + 8) & 0xFFFFFFF8;
                    if ( v31 > v11 )
                      goto LABEL_14;
                    v30 += v31;
                    v11 -= v31;
                  }
                  if ( v11 < 0xB0 )
                    goto LABEL_86;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, int *))qword_18028FD40)(
                              80,
                              v30,
                              176,
                              &v67) >= 0 )
                  {
                    v32 = (v67 + 8) & 0xFFFFFFF8;
                    if ( (unsigned int)v32 > v11 )
                      goto LABEL_14;
                    v11 -= v32;
                    if ( v11 < 0x40 )
                      goto LABEL_86;
                    v30 += v32;
                  }
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, int *))qword_18028FD40)(
                              21,
                              v30,
                              64,
                              &v67) >= 0 )
                  {
                    v33 = (v67 + 8) & 0xFFFFFFF8;
                    if ( v33 > v11 )
                      goto LABEL_14;
                    v30 += v33;
                    v11 -= v33;
                  }
                  if ( v11 < 0x178 )
                    goto LABEL_86;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, int *))qword_18028FD40)(
                              2,
                              v30,
                              376,
                              &v67) >= 0 )
                  {
                    v34 = (v67 + 8) & 0xFFFFFFF8;
                    if ( (unsigned int)v34 > v11 )
                      goto LABEL_14;
                    v11 -= v34;
                    if ( v11 < 0x10 )
                      goto LABEL_86;
                    v30 += v34;
                  }
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, int *))qword_18028FD40)(
                              33,
                              v30,
                              16,
                              &v67) >= 0 )
                  {
                    v35 = (v67 + 8) & 0xFFFFFFF8;
                    if ( v35 > v11 )
                      goto LABEL_14;
                    v30 += v35;
                    v11 -= v35;
                  }
                  if ( v11 < 0x20 )
                    goto LABEL_86;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, int *))qword_18028FD40)(
                              45,
                              v30,
                              32,
                              &v67) >= 0 )
                  {
                    v36 = (v67 + 8) & 0xFFFFFFF8;
                    if ( v36 > v11 )
                      goto LABEL_14;
                    v30 += v36;
                    v11 -= v36;
                  }
                  v67 = v11;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, _QWORD, int *))qword_18028FD40)(
                              8,
                              v30,
                              v11,
                              &v67) >= 0 )
                  {
                    memset(v72, 0, 0x7Cu);
                    if ( v11 < 0x14 )
                      goto LABEL_86;
                    v37 = (void (__fastcall *)(_OWORD *))sub_1800CD9C8(&word_18026FA66);
                    v37(v72);
                    sub_180057FE4(v37);
                    LODWORD(v37) = v67;
                    v38 = (void (__fastcall *)(_OWORD *, __int64, _QWORD))sub_1800CDE64(&byte_1802617F7);
                    v38(v72, v30, (unsigned int)v37);
                    sub_180057FE4(v38);
                    v39 = (void (__fastcall *)(_OWORD *, __int64))sub_1800CD56C(byte_180261DAB);
                    v39(v72, v30);
                    sub_180057FE4(v39);
                    if ( v11 < 0x18 )
                      goto LABEL_14;
                    v30 += 24;
                    v11 -= 24;
                  }
                  v67 = v11;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, _QWORD, int *))qword_18028FD40)(
                              61,
                              v30,
                              v11,
                              &v67) >= 0 )
                  {
                    memset(v74, 0, 0x7Cu);
                    if ( v11 < 0x14 )
                      goto LABEL_86;
                    v40 = (void (__fastcall *)(_DWORD *))sub_1800CD9C8(&word_18026FA66);
                    v40(v74);
                    sub_180057FE4(v40);
                    LODWORD(v40) = v67;
                    v41 = (void (__fastcall *)(_DWORD *, __int64, _QWORD))sub_1800CDE64(&byte_1802617F7);
                    v41(v74, v30, (unsigned int)v40);
                    sub_180057FE4(v41);
                    v42 = (void (__fastcall *)(_DWORD *, __int64))sub_1800CD56C(byte_180261DAB);
                    v42(v74, v30);
                    sub_180057FE4(v42);
                    if ( v11 < 0x18 )
                      goto LABEL_14;
                    v30 += 24;
                    v11 -= 24;
                  }
                  v67 = v11;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, _QWORD, int *))qword_18028FD40)(
                              18,
                              v30,
                              v11,
                              &v67) >= 0 )
                  {
                    memset(v75, 0, 0x7Cu);
                    if ( v11 < 0x14 )
                      goto LABEL_86;
                    v43 = (void (__fastcall *)(_DWORD *))sub_1800CD9C8(&word_18026FA66);
                    v43(v75);
                    sub_180057FE4(v43);
                    LODWORD(v43) = v67;
                    v44 = (void (__fastcall *)(_DWORD *, __int64, _QWORD))sub_1800CDE64(&byte_1802617F7);
                    v44(v75, v30, (unsigned int)v43);
                    sub_180057FE4(v44);
                    v45 = (void (__fastcall *)(_DWORD *, __int64))sub_1800CD56C(byte_180261DAB);
                    v45(v75, v30);
                    sub_180057FE4(v45);
                    if ( v11 < 0x18 )
                      goto LABEL_14;
                    v30 += 24;
                    v11 -= 24;
                  }
                  v67 = v11;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, _QWORD, int *))qword_18028FD40)(
                              23,
                              v30,
                              v11,
                              &v67) >= 0 )
                  {
                    memset(v76, 0, 0x7Cu);
                    if ( v11 < 0x14 )
                      goto LABEL_86;
                    v46 = (void (__fastcall *)(_DWORD *))sub_1800CD9C8(&word_18026FA66);
                    v46(v76);
                    sub_180057FE4(v46);
                    LODWORD(v46) = v67;
                    v47 = (void (__fastcall *)(_DWORD *, __int64, _QWORD))sub_1800CDE64(&byte_1802617F7);
                    v47(v76, v30, (unsigned int)v46);
                    sub_180057FE4(v47);
                    v48 = (void (__fastcall *)(_DWORD *, __int64))sub_1800CD56C(byte_180261DAB);
                    v48(v76, v30);
                    sub_180057FE4(v48);
                    if ( v11 < 0x18 )
                      goto LABEL_14;
                    v30 += 24;
                    v11 -= 24;
                  }
                  v67 = v11;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, _QWORD, int *))qword_18028FD40)(
                              42,
                              v30,
                              v11,
                              &v67) < 0 )
                    goto LABEL_86;
                  memset(v77, 0, 0x7Cu);
                  if ( v11 < 0x14 )
                    goto LABEL_86;
                  v49 = (void (__fastcall *)(_DWORD *))sub_1800CD9C8(&word_18026FA66);
                  v49(v77);
                  sub_180057FE4(v49);
                  LODWORD(v49) = v67;
                  v50 = (void (__fastcall *)(_DWORD *, __int64, _QWORD))sub_1800CDE64(&byte_1802617F7);
                  v50(v77, v30, (unsigned int)v49);
                  sub_180057FE4(v50);
                  v51 = (void (__fastcall *)(_DWORD *, __int64))sub_1800CD56C(byte_180261DAB);
                  v51(v77, v30);
                  sub_180057FE4(v51);
                  if ( v11 >= 0x18 )
                  {
                    v11 -= 24;
                    goto LABEL_86;
                  }
                }
              }
            }
          }
LABEL_14:
          v11 = 0;
LABEL_86:
          v4 = hKey;
        }
      }
    }
LABEL_87:
    v52 = 272;
    memset(v78, 0, sizeof(v78));
    v72[0] = *(_OWORD *)&xmmword_18028D0F0;
    v72[2] = xmmword_18028D110;
    v72[1] = xmmword_18028D100;
    v72[4] = xmmword_18028D130;
    v72[3] = xmmword_18028D120;
    v53 = 80;
    v54 = (void (__fastcall *)(_BYTE *, _OWORD *, __int64))sub_1800CD0E8(byte_180251695);
    v54(v78, v72, 80);
    sub_180057FE4(v54);
    v55 = 3584;
    if ( 3584 - v11 <= 0xE00 )
      v55 = 3584 - v11;
    v56 = sub_1800F72C0(v10, v55, v72);
    *(_OWORD *)Data = v72[0];
    *(_OWORD *)&Data[16] = v72[1];
    *(_OWORD *)&Data[32] = v72[2];
    *(_OWORD *)&Data[48] = v72[3];
    *(_OWORD *)&Data[64] = v72[4];
    *(_OWORD *)&xmmword_18028D0F0 = v72[0];
    xmmword_18028D100 = v72[1];
    xmmword_18028D110 = v72[2];
    xmmword_18028D120 = v72[3];
    xmmword_18028D130 = v72[4];
    v57 = (void (__fastcall *)(_BYTE *, BYTE *, BYTE *, __int64))sub_1800695B4(byte_18025196D);
    v57(v78, Data, Data, 80);
    sub_180057FE4(v57);
    hKey = 0;
    if ( (unsigned int)sub_1800F6D18(2u, &hKey) )
    {
      RegSetValueExW(hKey, L"Seed", 0, 3u, Data, 0x50u);
      RegCloseKey(hKey);
    }
    v58 = 80;
    v59 = Data;
    do
    {
      *v59++ = 0;
      --v58;
    }
    while ( v58 );
    v60 = (void (__fastcall *)(_BYTE *, _OWORD *, __int64))sub_1800CD0E8(byte_180251695);
    v60(v78, v72, 80);
    sub_180057FE4(v60);
    v61 = v72;
    do
    {
      *v61++ = 0;
      --v53;
    }
    while ( v53 );
    v62 = *v71;
    v63 = (void (__fastcall *)(_BYTE *, HKEY, HKEY, _QWORD))sub_1800695B4(byte_18025196D);
    v63(v78, v4, v4, v62);
    sub_180057FE4(v63);
    v64 = v78;
    do
    {
      *v64++ = 0;
      --v52;
    }
    while ( v52 );
    v65 = v10;
    do
    {
      *v65++ = 0;
      --v9;
    }
    while ( v9 );
    v66 = GetProcessHeap();
    HeapFree(v66, 0, v10);
    return v56;
  }
  return result;
}

```

## disassembly

```asm
0x1800f5acc  push    rbp
0x1800f5ace  push    rbx
0x1800f5acf  push    rsi
0x1800f5ad0  push    rdi
0x1800f5ad1  push    r12
0x1800f5ad3  push    r13
0x1800f5ad5  push    r14
0x1800f5ad7  push    r15
0x1800f5ad9  lea     rbp, [rsp-388h]
0x1800f5ae1  sub     rsp, 488h
0x1800f5ae8  mov     rax, cs:__security_cookie
0x1800f5aef  xor     rax, rsp
0x1800f5af2  mov     [rbp+3C0h+var_50], rax
0x1800f5af9  mov     [rsp+4C0h+var_470], r9
0x1800f5afe  mov     r13, r8
0x1800f5b01  mov     [rsp+4C0h+hKey], r8
0x1800f5b06  mov     rdi, rcx
0x1800f5b09  mov     ebx, edx
0x1800f5b0b  call    sub_1800F6728
0x1800f5b10  test    eax, eax
0x1800f5b12  jz      short loc_1800F5B1E
0x1800f5b14  mov     eax, 1
0x1800f5b19  jmp     loc_1800F66FB
0x1800f5b1e  call    cs:GetProcessHeap
0x1800f5b25  nop     dword ptr [rax+rax+00h]
0x1800f5b2a  mov     r12d, 0E00h
0x1800f5b30  xor     edx, edx; dwFlags
0x1800f5b32  mov     rcx, rax; hHeap
0x1800f5b35  mov     r8d, r12d; dwBytes
0x1800f5b38  call    cs:HeapAlloc
0x1800f5b3f  nop     dword ptr [rax+rax+00h]
0x1800f5b44  mov     [rsp+4C0h+var_478], rax
0x1800f5b49  mov     r15, rax
0x1800f5b4c  test    rax, rax
0x1800f5b4f  jz      loc_1800F66FB
0x1800f5b55  mov     esi, r12d
0x1800f5b58  cmp     ebx, r12d
0x1800f5b5b  ja      loc_1800F64C6
0x1800f5b61  mov     r8, rbx; Size
0x1800f5b64  mov     rdx, rdi; Src
0x1800f5b67  mov     rcx, r15; void *
0x1800f5b6a  call    memcpy
0x1800f5b6f  lea     eax, [rbx+8]
0x1800f5b72  and     eax, 0FFFFFFF8h
0x1800f5b75  cmp     eax, r12d
0x1800f5b78  jbe     short loc_1800F5B81
0x1800f5b7a  xor     esi, esi
0x1800f5b7c  jmp     loc_1800F64C6
0x1800f5b81  mov     ebx, r12d
0x1800f5b84  mov     edi, eax
0x1800f5b86  sub     ebx, eax
0x1800f5b88  call    cs:GetCurrentProcessId
0x1800f5b8f  nop     dword ptr [rax+rax+00h]
0x1800f5b94  mov     [rdi+r15], eax
0x1800f5b98  cmp     ebx, 8
0x1800f5b9b  jb      short loc_1800F5B7A
0x1800f5b9d  add     ebx, 0FFFFFFF8h
0x1800f5ba0  call    cs:GetCurrentThreadId
0x1800f5ba7  nop     dword ptr [rax+rax+00h]
0x1800f5bac  mov     [rdi+r15+8], eax
0x1800f5bb1  cmp     ebx, 8
0x1800f5bb4  jb      short loc_1800F5B7A
0x1800f5bb6  lea     esi, [rbx-8]
0x1800f5bb9  call    cs:GetTickCount
0x1800f5bc0  nop     dword ptr [rax+rax+00h]
0x1800f5bc5  mov     [rdi+r15+10h], eax
0x1800f5bca  cmp     esi, 8
0x1800f5bcd  jb      short loc_1800F5B7A
0x1800f5bcf  add     esi, 0FFFFFFF8h
0x1800f5bd2  cmp     esi, 10h
0x1800f5bd5  jb      loc_1800F64C6
0x1800f5bdb  lea     rbx, [rdi+r15]
0x1800f5bdf  lea     rcx, [rbx+18h]; lpSystemTime
0x1800f5be3  call    cs:GetLocalTime
0x1800f5bea  nop     dword ptr [rax+rax+00h]
0x1800f5bef  cmp     esi, 18h
0x1800f5bf2  jb      short loc_1800F5B7A
0x1800f5bf4  mov     r14d, 0FFFFFFE8h
0x1800f5bfa  add     esi, r14d
0x1800f5bfd  cmp     esi, 8
0x1800f5c00  jb      loc_1800F64C6
0x1800f5c06  lea     r13, [rbx+30h]
0x1800f5c0a  mov     rcx, r13; lpPerformanceCount
0x1800f5c0d  call    cs:QueryPerformanceCounter
0x1800f5c14  nop     dword ptr [rax+rax+00h]
0x1800f5c19  cmp     esi, 10h
0x1800f5c1c  jnb     short loc_1800F5C25
0x1800f5c1e  xor     esi, esi
0x1800f5c20  jmp     loc_1800F64C1
0x1800f5c25  add     esi, 0FFFFFFF0h
0x1800f5c28  cmp     esi, 40h ; '@'
0x1800f5c2b  jb      loc_1800F64C1
0x1800f5c31  lea     rcx, [r13+10h]; lpBuffer
0x1800f5c35  mov     dword ptr [r13+10h], 40h ; '@'
0x1800f5c3d  call    cs:GlobalMemoryStatusEx
0x1800f5c44  nop     dword ptr [rax+rax+00h]
0x1800f5c49  cmp     esi, 48h ; 'H'
0x1800f5c4c  jb      short loc_1800F5C1E
0x1800f5c4e  add     esi, 0FFFFFFB8h
0x1800f5c51  cmp     esi, 10h
0x1800f5c54  jb      loc_1800F64C1
0x1800f5c5a  add     r13, 58h ; 'X'
0x1800f5c5e  xor     ecx, ecx; lpRootPathName
0x1800f5c60  mov     rdx, r13; lpSectorsPerCluster
0x1800f5c63  mov     [rsp+4C0h+var_480], r13
0x1800f5c68  lea     rax, [r13+0Ch]
0x1800f5c6c  lea     r9, [r13+8]; lpNumberOfFreeClusters
0x1800f5c70  mov     [rsp+4C0h+lpTotalNumberOfClusters], rax; lpTotalNumberOfClusters
0x1800f5c75  lea     r8, [r13+4]; lpBytesPerSector
0x1800f5c79  call    cs:GetDiskFreeSpaceW
0x1800f5c80  nop     dword ptr [rax+rax+00h]
0x1800f5c85  cmp     esi, 18h
0x1800f5c88  jb      short loc_1800F5C1E
0x1800f5c8a  add     esi, r14d
0x1800f5c8d  cmp     cs:dword_18028D0E0, 0
0x1800f5c94  jnz     loc_1800F5DE7
0x1800f5c9a  xor     eax, eax
0x1800f5c9c  mov     [rsp+4C0h+var_490], eax
0x1800f5ca0  call    cs:GetEnvironmentStringsW
0x1800f5ca7  nop     dword ptr [rax+rax+00h]
0x1800f5cac  mov     r15, rax
0x1800f5caf  test    rax, rax
0x1800f5cb2  jnz     short loc_1800F5CD4
0x1800f5cb4  call    cs:GetEnvironmentStringsW
0x1800f5cbb  nop     dword ptr [rax+rax+00h]
0x1800f5cc0  mov     [rsp+4C0h+var_490], 1
0x1800f5cc8  mov     r15, rax
0x1800f5ccb  test    rax, rax
0x1800f5cce  jz      loc_1800F5DD8
0x1800f5cd4  xor     eax, eax
0x1800f5cd6  lea     rcx, [rbp+3C0h+Data]; void *
0x1800f5cda  xor     edx, edx; Val
0x1800f5cdc  mov     dword ptr [rbp+3C0h+Data+4], eax
0x1800f5cdf  lea     r8d, [rax+6Ch]; Size
0x1800f5ce3  call    memset
0x1800f5ce8  lea     rcx, word_180270E2A
0x1800f5cef  call    sub_180069108
0x1800f5cf4  lea     rcx, [rbp+3C0h+Data]
0x1800f5cf8  mov     rbx, rax
0x1800f5cfb  call    rax
0x1800f5cfd  nop     dword ptr [rax]
0x1800f5d00  mov     rcx, rbx
0x1800f5d03  call    sub_180068C4C
0x1800f5d08  mov     r13d, [rsp+4C0h+var_490]
0x1800f5d0d  xor     r14d, r14d
0x1800f5d10  mov     r12, r15
0x1800f5d13  mov     eax, r14d
0x1800f5d16  mov     edx, 7FFFh; MaxCount
0x1800f5d1b  add     r12, rax
0x1800f5d1e  test    r13d, r13d
0x1800f5d21  jnz     short loc_1800F5D3E
0x1800f5d23  add     r12, 2
0x1800f5d27  mov     rcx, r12; Source
0x1800f5d2a  call    cs:wcsnlen
0x1800f5d31  nop     dword ptr [rax+rax+00h]
0x1800f5d36  mov     r14, rax
0x1800f5d39  add     r14d, r14d
0x1800f5d3c  jmp     short loc_1800F5D53
0x1800f5d3e  inc     r12
0x1800f5d41  mov     rcx, r12; String
0x1800f5d44  call    cs:strnlen
0x1800f5d4b  nop     dword ptr [rax+rax+00h]
0x1800f5d50  mov     r14d, eax
0x1800f5d53  lea     rcx, byte_1802724D1
0x1800f5d5a  call    sub_180068C64
0x1800f5d5f  mov     r8d, r14d
0x1800f5d62  lea     rcx, [rbp+3C0h+Data]
0x1800f5d66  mov     rdx, r12
0x1800f5d69  mov     rdi, rax
0x1800f5d6c  call    rax
0x1800f5d6e  nop     dword ptr [rax]
0x1800f5d71  mov     rcx, rdi
0x1800f5d74  call    sub_180068C4C
0x1800f5d79  test    r14d, r14d
0x1800f5d7c  jnz     short loc_1800F5D13
0x1800f5d7e  lea     rcx, word_180272A02
0x1800f5d85  call    sub_180069108
0x1800f5d8a  lea     rdx, xmmword_18028D260
0x1800f5d91  mov     rbx, rax
0x1800f5d94  lea     rcx, [rbp+3C0h+Data]
0x1800f5d98  call    rax
0x1800f5d9a  nop     dword ptr [rax]
0x1800f5d9d  mov     rcx, rbx
0x1800f5da0  call    sub_180068C4C
0x1800f5da5  test    r13d, r13d
0x1800f5da8  mov     rcx, r15; penv
0x1800f5dab  mov     r13, [rsp+4C0h+var_480]
0x1800f5db0  jnz     short loc_1800F5DC0
0x1800f5db2  call    cs:FreeEnvironmentStringsW
0x1800f5db9  nop     dword ptr [rax+rax+00h]
0x1800f5dbe  jmp     short loc_1800F5DCC
0x1800f5dc0  call    cs:FreeEnvironmentStringsA
0x1800f5dc7  nop     dword ptr [rax+rax+00h]
0x1800f5dcc  mov     r14d, 0FFFFFFE8h
0x1800f5dd2  mov     r12d, 0E00h
0x1800f5dd8  mov     r15, [rsp+4C0h+var_478]
0x1800f5ddd  mov     cs:dword_18028D0E0, 1
0x1800f5de7  cmp     esi, 10h
0x1800f5dea  jb      loc_1800F64C1
0x1800f5df0  movups  xmm0, cs:xmmword_18028D260
0x1800f5df7  movdqu  xmmword ptr [r13+18h], xmm0
0x1800f5dfd  cmp     esi, 18h
0x1800f5e00  jb      loc_1800F5C1E
0x1800f5e06  add     esi, r14d
0x1800f5e09  call    sub_1800F688C
0x1800f5e0e  test    eax, eax
0x1800f5e10  jz      loc_1800F64C1
0x1800f5e16  cmp     esi, 40h ; '@'
0x1800f5e19  jb      loc_1800F64C1
0x1800f5e1f  mov     rax, cs:NtQuerySystemInformation
0x1800f5e26  test    rax, rax
0x1800f5e29  jz      loc_1800F64C1
0x1800f5e2f  xor     r9d, r9d
0x1800f5e32  mov     [rsp+4C0h+var_490], esi
0x1800f5e36  add     r13, 30h ; '0'
0x1800f5e3a  mov     r8d, esi
0x1800f5e3d  mov     rdx, r13
0x1800f5e40  lea     ecx, [r9+5]
0x1800f5e44  call    cs:__guard_dispatch_icall_fptr
0x1800f5e4a  xor     eax, eax
0x1800f5e4c  lea     rcx, [rbp+3C0h+Data]; void *
0x1800f5e50  xor     edx, edx; Val
0x1800f5e52  mov     dword ptr [rbp+3C0h+Data+4], eax
0x1800f5e55  lea     r8d, [rax+7Ch]; Size
0x1800f5e59  call    memset
0x1800f5e5e  lea     rcx, word_18026FA66
0x1800f5e65  call    sub_1800CD9C8
0x1800f5e6a  lea     rcx, [rbp+3C0h+Data]
0x1800f5e6e  mov     rbx, rax
0x1800f5e71  call    rax
0x1800f5e73  nop     dword ptr [rax]
0x1800f5e76  mov     rcx, rbx
0x1800f5e79  call    sub_180057FE4
0x1800f5e7e  mov     ebx, [rsp+4C0h+var_490]
0x1800f5e82  lea     rcx, byte_1802617F7
0x1800f5e89  call    sub_1800CDE64
0x1800f5e8e  mov     r8d, ebx
0x1800f5e91  lea     rcx, [rbp+3C0h+Data]
0x1800f5e95  mov     rdx, r13
0x1800f5e98  mov     rdi, rax
0x1800f5e9b  call    rax
0x1800f5e9d  nop     dword ptr [rax]
0x1800f5ea0  mov     rcx, rdi
0x1800f5ea3  call    sub_180057FE4
0x1800f5ea8  lea     rcx, byte_180261DAB
0x1800f5eaf  call    sub_1800CD56C
0x1800f5eb4  mov     rdx, r13
0x1800f5eb7  lea     rcx, [rbp+3C0h+Data]
0x1800f5ebb  mov     rbx, rax
0x1800f5ebe  call    rax
0x1800f5ec0  nop     dword ptr [rax]
0x1800f5ec3  mov     rcx, rbx
0x1800f5ec6  call    sub_180057FE4
0x1800f5ecb  mov     r8d, 30h ; '0'
0x1800f5ed1  add     esi, r14d
0x1800f5ed4  cmp     esi, r8d
0x1800f5ed7  jb      loc_1800F64C1
0x1800f5edd  mov     rax, cs:NtQuerySystemInformation
0x1800f5ee4  lea     rbx, [r13+18h]
0x1800f5ee8  mov     rdx, rbx
0x1800f5eeb  lea     r9, [rsp+4C0h+var_490]
0x1800f5ef0  lea     ecx, [r8-2Dh]
0x1800f5ef4  call    cs:__guard_dispatch_icall_fptr
0x1800f5efa  mov     edi, 0FFFFFFF8h
0x1800f5eff  test    eax, eax
0x1800f5f01  js      short loc_1800F5F27
0x1800f5f03  mov     eax, [rsp+4C0h+var_490]
0x1800f5f07  add     eax, 8
0x1800f5f0a  and     eax, edi
0x1800f5f0c  cmp     eax, esi
0x1800f5f0e  ja      loc_1800F5C1E
0x1800f5f14  mov     r14d, eax
0x1800f5f17  sub     esi, eax
0x1800f5f19  add     r14, rbx
0x1800f5f1c  cmp     esi, 18h
0x1800f5f1f  jb      loc_1800F64C1
0x1800f5f25  jmp     short loc_1800F5F2A
0x1800f5f27  mov     r14, rbx
0x1800f5f2a  mov     rax, cs:NtQuerySystemInformation
0x1800f5f31  lea     r9, [rsp+4C0h+var_490]
0x1800f5f36  mov     r8d, 18h
0x1800f5f3c  mov     rdx, r14
0x1800f5f3f  lea     ecx, [r8-11h]
0x1800f5f43  call    cs:__guard_dispatch_icall_fptr
0x1800f5f49  test    eax, eax
0x1800f5f4b  js      short loc_1800F5F65
0x1800f5f4d  mov     ecx, [rsp+4C0h+var_490]
0x1800f5f51  add     ecx, 8
0x1800f5f54  and     ecx, edi
0x1800f5f56  cmp     ecx, esi
0x1800f5f58  ja      loc_1800F5C1E
0x1800f5f5e  mov     eax, ecx
0x1800f5f60  add     r14, rax
0x1800f5f63  sub     esi, ecx
0x1800f5f65  mov     r8d, 0B0h
0x1800f5f6b  cmp     esi, r8d
0x1800f5f6e  jb      loc_1800F64C1
0x1800f5f74  mov     rax, cs:NtQuerySystemInformation
0x1800f5f7b  lea     r9, [rsp+4C0h+var_490]
0x1800f5f80  mov     rdx, r14
  ... truncated ...
```
