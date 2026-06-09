# Old_GatherRandomKey

- ea: `0x18004a97c`
- end: `0x18004b487`
- name: `Old_GatherRandomKey`
- size: `2827`
- prototype: `__int64 __fastcall(void *Src, size_t Size, LPVOID lpOutBuffer, LPDWORD lpBytesReturned)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18004b638`
- `0x18004b73c`

## callees

- `0x1800017b0`
- `0x1800021a8`
- `0x18004a97c`
- `0x18004b584`
- `0x18004b8f8`
- `0x18004bbf0`
- `0x180052520`
- `0x180053780`
- `0x1800537b0`
- `0x180054e10`
- `0x180054f60`
- `0x180054fe4`
- `0x1800569e0`
- `0x1800886fc`
- `0x180088750`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18004ace4`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18004ace4`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x18004acfd`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x18004acfd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004b455`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004b455`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004aaf9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b441`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004aaf9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b441`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004ab13`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004ab13`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004b3b2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004b3b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b3c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004b3c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004ab61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004ab61`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ab79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ab79`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x18004ac54`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x18004ac54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004aaa3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004aaa3`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18004ac14`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x18004ac14`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18004abbb`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18004abbb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004ab92`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004ab92`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004abe4`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004abe4`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsA` at `0x18004ad4b`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsA` at `0x18004ad4b`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x18004ac77`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x18004ac8b`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x18004ac77`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x18004ac8b`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x18004ad3d`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x18004ad3d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004aadf`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004aadf`

## pseudocode

```c
__int64 __fastcall Old_GatherRandomKey(void *Src, size_t Size, HKEY lpOutBuffer, LPDWORD lpBytesReturned)
{
  HKEY v5; // r15
  size_t v6; // rdi
  HANDLE v8; // rbx
  __int64 result; // rax
  HANDLE ProcessHeap; // rax
  __int64 v11; // r14
  _BYTE *v12; // r12
  unsigned int v13; // ebx
  __int64 v14; // r13
  unsigned int v15; // eax
  __int64 v16; // rdi
  unsigned int v17; // ebx
  unsigned int v18; // ebx
  unsigned int v19; // ebx
  char *v20; // r15
  int v21; // r13d
  CHAR *EnvironmentStringsW; // rsi
  const char *v23; // r14
  unsigned int v24; // edi
  const char *v25; // r14
  unsigned int v26; // eax
  __int64 v27; // rdi
  unsigned int v28; // ecx
  __int64 v29; // rax
  unsigned int v30; // ecx
  __int64 v31; // rax
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  __int64 v34; // rdi
  __int64 v35; // rdx
  unsigned int v36; // ebx
  __int64 v37; // rcx
  BYTE *v38; // rax
  __int128 *v39; // rax
  _BYTE *v40; // rax
  _BYTE *v41; // rax
  HANDLE v42; // rax
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  LPDWORD v45; // [rsp+50h] [rbp-B0h]
  __int128 v46; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v47; // [rsp+68h] [rbp-98h] BYREF
  __int128 v48; // [rsp+80h] [rbp-80h] BYREF
  __m256i v49; // [rsp+90h] [rbp-70h] BYREF
  __int128 v50; // [rsp+B0h] [rbp-50h]
  __int128 v51; // [rsp+C0h] [rbp-40h]
  BYTE Data[16]; // [rsp+100h] [rbp+0h] BYREF
  __m256i v53; // [rsp+110h] [rbp+10h]
  __int128 v54; // [rsp+130h] [rbp+30h]
  __int128 v55; // [rsp+140h] [rbp+40h]
  __int128 v56; // [rsp+160h] [rbp+60h]
  _BYTE v57[4]; // [rsp+180h] [rbp+80h] BYREF
  int v58; // [rsp+184h] [rbp+84h]
  _BYTE v59[4]; // [rsp+200h] [rbp+100h] BYREF
  int v60; // [rsp+204h] [rbp+104h]
  _BYTE v61[4]; // [rsp+280h] [rbp+180h] BYREF
  int v62; // [rsp+284h] [rbp+184h]
  _BYTE v63[4]; // [rsp+300h] [rbp+200h] BYREF
  int v64; // [rsp+304h] [rbp+204h]
  _BYTE v65[272]; // [rsp+380h] [rbp+280h] BYREF

  v45 = lpBytesReturned;
  hObject = 0;
  v5 = lpOutBuffer;
  hKey = lpOutBuffer;
  v6 = (unsigned int)Size;
  if ( (unsigned int)Old_IsRNGWinNT() )
  {
    v8 = g_hKsecDD;
    hObject = g_hKsecDD;
    if ( !g_hKsecDD )
    {
      memset(&v49, 0, 28);
      v46 = 0;
      v48 = 0;
      v47 = 0;
      if ( !__NtOpenFileRNG )
        goto LABEL_11;
      if ( !__RtlInitUnicodeStringRNG )
        goto LABEL_11;
      __RtlInitUnicodeStringRNG(&v46, L"\\Device\\KsecDD");
      v49.m256i_i64[0] = (__int64)&v46;
      LODWORD(v48) = 48;
      *((_QWORD *)&v48 + 1) = 0;
      v49.m256i_i32[2] = 64;
      *(_OWORD *)&v49.m256i_u64[2] = 0;
      if ( (int)((__int64 (__fastcall *)(HANDLE *, __int64, __int128 *, __int128 *, int, int))__NtOpenFileRNG)(
                  &hObject,
                  1048577,
                  &v48,
                  &v47,
                  7,
                  32) < 0 )
        goto LABEL_11;
      v8 = (HANDLE)_InterlockedCompareExchange64((volatile signed __int64 *)&g_hKsecDD, (signed __int64)hObject, 0);
      if ( v8 )
      {
        CloseHandle(hObject);
        hObject = v8;
      }
      else
      {
        v8 = hObject;
      }
    }
    if ( DeviceIoControl(v8, 0x390008u, Src, v6, v5, *lpBytesReturned, lpBytesReturned, 0) )
      return 1;
  }
LABEL_11:
  ProcessHeap = GetProcessHeap();
  v11 = 3584;
  result = (__int64)HeapAlloc(ProcessHeap, 0, 0xE00u);
  v12 = (_BYTE *)result;
  if ( !result )
    return result;
  v13 = 3584;
  v14 = 80;
  if ( (unsigned int)v6 <= 0xE00 )
  {
    memcpy_0((void *)result, Src, v6);
    v15 = (v6 + 8) & 0xFFFFFFF8;
    if ( v15 > 0xE00 )
      goto LABEL_14;
    v16 = v15;
    v17 = 3584 - v15;
    *(_DWORD *)&v12[v15] = GetCurrentProcessId();
    if ( v17 < 8 )
      goto LABEL_14;
    v18 = v17 - 8;
    *(_DWORD *)&v12[v16 + 8] = GetCurrentThreadId();
    if ( v18 < 8 )
      goto LABEL_14;
    v19 = v18 - 8;
    *(_DWORD *)&v12[v16 + 16] = GetTickCount();
    if ( v19 < 8 )
      goto LABEL_14;
    v13 = v19 - 8;
    if ( v13 < 0x10 )
      goto LABEL_95;
    GetLocalTime((LPSYSTEMTIME)&v12[v16 + 24]);
    if ( v13 < 0x18 )
    {
LABEL_14:
      v13 = 0;
    }
    else
    {
      v13 -= 24;
      if ( v13 >= 8 )
      {
        v20 = &v12[v16];
        QueryPerformanceCounter((LARGE_INTEGER *)&v12[v16 + 48]);
        if ( v13 >= 0x10 )
        {
          v13 -= 16;
          if ( v13 < 0x40 )
            goto LABEL_94;
          *((_DWORD *)v20 + 16) = 64;
          GlobalMemoryStatusEx((LPMEMORYSTATUSEX)v20 + 1);
          if ( v13 >= 0x48 )
          {
            v13 -= 72;
            if ( v13 < 0x10 )
              goto LABEL_94;
            GetDiskFreeSpaceW(0, (LPDWORD)v20 + 34, (LPDWORD)v20 + 35, (LPDWORD)v20 + 36, (LPDWORD)v20 + 37);
            if ( v13 >= 0x18 )
            {
              v13 -= 24;
              if ( !dword_1800AD8E8 )
              {
                v21 = 0;
                EnvironmentStringsW = (CHAR *)GetEnvironmentStringsW();
                if ( EnvironmentStringsW
                  || (EnvironmentStringsW = (CHAR *)GetEnvironmentStringsW(), v21 = 1, EnvironmentStringsW) )
                {
                  *(_DWORD *)&Data[4] = 0;
                  memset_0(Data, 0, 0x6Cu);
                  v23 = EnvironmentStringsW;
                  v24 = 0;
                  v56 = xmmword_180098DD8;
                  do
                  {
                    v25 = &v23[v24];
                    if ( v21 )
                    {
                      v23 = v25 + 1;
                      v24 = strnlen(v23, 0x7FFFu);
                    }
                    else
                    {
                      v23 = v25 + 2;
                      v24 = 2 * wcsnlen((const wchar_t *)v23, 0x7FFFu);
                    }
                    SymCryptHashAppendInternal(SymCryptMd4Algorithm_default, Data, v23, v24);
                  }
                  while ( v24 );
                  SymCryptMd4Result(Data, &xmmword_1800ADA60);
                  if ( v21 )
                    FreeEnvironmentStringsA(EnvironmentStringsW);
                  else
                    FreeEnvironmentStringsW((LPWCH)EnvironmentStringsW);
                  v11 = 3584;
                }
                dword_1800AD8E8 = 1;
                v14 = 80;
              }
              if ( v13 < 0x10 )
                goto LABEL_94;
              *((_OWORD *)v20 + 10) = xmmword_1800ADA60;
              if ( v13 >= 0x18 )
              {
                v13 -= 24;
                if ( !(unsigned int)Old_IsRNGWinNT() )
                  goto LABEL_94;
                if ( v13 < 0x40 )
                  goto LABEL_94;
                if ( !__NtQuerySystemInformationRNG )
                  goto LABEL_94;
                LODWORD(hObject) = v13;
                __NtQuerySystemInformationRNG(5, v20 + 184, v13);
                *(_DWORD *)&Data[4] = 0;
                memset_0(Data, 0, 0x7Cu);
                SymCryptSha1Init(Data);
                SymCryptSha1Append(Data, v20 + 184, (unsigned int)hObject);
                SymCryptSha1Result(Data, v20 + 184);
                v13 -= 24;
                if ( v13 < 0x30 )
                  goto LABEL_94;
                if ( (int)((__int64 (__fastcall *)(__int64, char *, __int64, HANDLE *))__NtQuerySystemInformationRNG)(
                            3,
                            v20 + 208,
                            48,
                            &hObject) < 0 )
                {
                  v27 = (__int64)(v20 + 208);
                }
                else
                {
                  v26 = ((_DWORD)hObject + 8) & 0xFFFFFFF8;
                  if ( v26 > v13 )
                    goto LABEL_22;
                  v13 -= v26;
                  v27 = (__int64)&v20[v26 + 208];
                  if ( v13 < 0x18 )
                    goto LABEL_94;
                }
                if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, HANDLE *))__NtQuerySystemInformationRNG)(
                            7,
                            v27,
                            24,
                            &hObject) >= 0 )
                {
                  v28 = ((_DWORD)hObject + 8) & 0xFFFFFFF8;
                  if ( v28 > v13 )
                    goto LABEL_22;
                  v27 += v28;
                  v13 -= v28;
                }
                if ( v13 < 0xB0 )
                  goto LABEL_94;
                if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, HANDLE *))__NtQuerySystemInformationRNG)(
                            80,
                            v27,
                            176,
                            &hObject) >= 0 )
                {
                  v29 = ((_DWORD)hObject + 8) & 0xFFFFFFF8;
                  if ( (unsigned int)v29 > v13 )
                    goto LABEL_22;
                  v13 -= v29;
                  if ( v13 < 0x40 )
                    goto LABEL_94;
                  v27 += v29;
                }
                if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, HANDLE *))__NtQuerySystemInformationRNG)(
                            21,
                            v27,
                            64,
                            &hObject) >= 0 )
                {
                  v30 = ((_DWORD)hObject + 8) & 0xFFFFFFF8;
                  if ( v30 > v13 )
                    goto LABEL_22;
                  v27 += v30;
                  v13 -= v30;
                }
                if ( v13 < 0x178 )
                  goto LABEL_94;
                if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, HANDLE *))__NtQuerySystemInformationRNG)(
                            2,
                            v27,
                            376,
                            &hObject) >= 0 )
                {
                  v31 = ((_DWORD)hObject + 8) & 0xFFFFFFF8;
                  if ( (unsigned int)v31 > v13 )
                    goto LABEL_22;
                  v13 -= v31;
                  if ( v13 < 0x10 )
                    goto LABEL_94;
                  v27 += v31;
                }
                if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, HANDLE *))__NtQuerySystemInformationRNG)(
                            33,
                            v27,
                            16,
                            &hObject) >= 0 )
                {
                  v32 = ((_DWORD)hObject + 8) & 0xFFFFFFF8;
                  if ( v32 > v13 )
                    goto LABEL_22;
                  v27 += v32;
                  v13 -= v32;
                }
                if ( v13 < 0x20 )
                  goto LABEL_94;
                if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, HANDLE *))__NtQuerySystemInformationRNG)(
                            45,
                            v27,
                            32,
                            &hObject) >= 0 )
                {
                  v33 = ((_DWORD)hObject + 8) & 0xFFFFFFF8;
                  if ( v33 > v13 )
                    goto LABEL_22;
                  v27 += v33;
                  v13 -= v33;
                }
                LODWORD(hObject) = v13;
                if ( (int)((__int64 (__fastcall *)(__int64, __int64, _QWORD, HANDLE *))__NtQuerySystemInformationRNG)(
                            8,
                            v27,
                            v13,
                            &hObject) >= 0 )
                {
                  DWORD1(v48) = 0;
                  memset_0(&v48, 0, 0x7Cu);
                  if ( v13 < 0x14 )
                    goto LABEL_94;
                  SymCryptSha1Init(&v48);
                  SymCryptSha1Append(&v48, v27, (unsigned int)hObject);
                  SymCryptSha1Result(&v48, v27);
                  if ( v13 < 0x18 )
                    goto LABEL_22;
                  v27 += 24;
                  v13 -= 24;
                }
                LODWORD(hObject) = v13;
                if ( (int)((__int64 (__fastcall *)(__int64, __int64, _QWORD, HANDLE *))__NtQuerySystemInformationRNG)(
                            61,
                            v27,
                            v13,
                            &hObject) >= 0 )
                {
                  v58 = 0;
                  memset_0(v57, 0, 0x7Cu);
                  if ( v13 < 0x14 )
                    goto LABEL_94;
                  SymCryptSha1Init(v57);
                  SymCryptSha1Append(v57, v27, (unsigned int)hObject);
                  SymCryptSha1Result(v57, v27);
                  if ( v13 < 0x18 )
                    goto LABEL_22;
                  v27 += 24;
                  v13 -= 24;
                }
                LODWORD(hObject) = v13;
                if ( (int)((__int64 (__fastcall *)(__int64, __int64, _QWORD, HANDLE *))__NtQuerySystemInformationRNG)(
                            18,
                            v27,
                            v13,
                            &hObject) >= 0 )
                {
                  v60 = 0;
                  memset_0(v59, 0, 0x7Cu);
                  if ( v13 < 0x14 )
                    goto LABEL_94;
                  SymCryptSha1Init(v59);
                  SymCryptSha1Append(v59, v27, (unsigned int)hObject);
                  SymCryptSha1Result(v59, v27);
                  if ( v13 < 0x18 )
                    goto LABEL_22;
                  v27 += 24;
                  v13 -= 24;
                }
                LODWORD(hObject) = v13;
                if ( (int)((__int64 (__fastcall *)(__int64, __int64, _QWORD, HANDLE *))__NtQuerySystemInformationRNG)(
                            23,
                            v27,
                            v13,
                            &hObject) >= 0 )
                {
                  v62 = 0;
                  memset_0(v61, 0, 0x7Cu);
                  if ( v13 < 0x14 )
                    goto LABEL_94;
                  SymCryptSha1Init(v61);
                  SymCryptSha1Append(v61, v27, (unsigned int)hObject);
                  SymCryptSha1Result(v61, v27);
                  if ( v13 < 0x18 )
                    goto LABEL_22;
                  v27 += 24;
                  v13 -= 24;
                }
                LODWORD(hObject) = v13;
                if ( (int)((__int64 (__fastcall *)(__int64, __int64, _QWORD, HANDLE *))__NtQuerySystemInformationRNG)(
                            42,
                            v27,
                            v13,
                            &hObject) < 0 )
                  goto LABEL_94;
                v64 = 0;
                memset_0(v63, 0, 0x7Cu);
                if ( v13 < 0x14 )
                  goto LABEL_94;
                SymCryptSha1Init(v63);
                SymCryptSha1Append(v63, v27, (unsigned int)hObject);
                SymCryptSha1Result(v63, v27);
                if ( v13 >= 0x18 )
                {
                  v13 -= 24;
                  goto LABEL_94;
                }
              }
            }
          }
        }
LABEL_22:
        v13 = 0;
LABEL_94:
        v5 = hKey;
      }
    }
  }
LABEL_95:
  v34 = 272;
  memset_0(v65, 0, sizeof(v65));
  v48 = *(_OWORD *)&::Data;
  v49 = (__m256i)ymmword_1800AD900;
  v51 = xmmword_1800AD930;
  v50 = xmmword_1800AD920;
  SymCryptRc4Init(v65, &v48, 80);
  v35 = 3584;
  if ( 3584 - v13 <= 0xE00 )
    v35 = 3584 - v13;
  v36 = VeryLargeHashUpdate(v12, v35, &v48);
  *(_OWORD *)Data = v48;
  v53 = v49;
  v54 = v50;
  v55 = v51;
  *(_OWORD *)&::Data = v48;
  ymmword_1800AD900 = (__m256)v49;
  xmmword_1800AD920 = v50;
  xmmword_1800AD930 = v51;
  SymCryptRc4Crypt(v65, Data, Data, 80);
  hKey = 0;
  if ( (unsigned int)AccessSeed(2u, &hKey) )
  {
    RegSetValueExW(hKey, L"Seed", 0, 3u, Data, 0x50u);
    RegCloseKey(hKey);
  }
  v37 = 80;
  v38 = Data;
  do
  {
    *v38++ = 0;
    --v37;
  }
  while ( v37 );
  SymCryptRc4Init(v65, &v48, 80);
  v39 = &v48;
  do
  {
    *(_BYTE *)v39 = 0;
    v39 = (__int128 *)((char *)v39 + 1);
    --v14;
  }
  while ( v14 );
  SymCryptRc4Crypt(v65, v5, v5, *v45);
  v40 = v65;
  do
  {
    *v40++ = 0;
    --v34;
  }
  while ( v34 );
  v41 = v12;
  do
  {
    *v41++ = 0;
    --v11;
  }
  while ( v11 );
  v42 = GetProcessHeap();
  HeapFree(v42, 0, v12);
  return v36;
}

```

## disassembly

```asm
0x18004a97c  push    rbp
0x18004a97e  push    rbx
0x18004a97f  push    rsi
0x18004a980  push    rdi
0x18004a981  push    r12
0x18004a983  push    r13
0x18004a985  push    r14
0x18004a987  push    r15
0x18004a989  lea     rbp, [rsp-3A8h]
0x18004a991  sub     rsp, 4A8h
0x18004a998  mov     rax, cs:__security_cookie
0x18004a99f  xor     rax, rsp
0x18004a9a2  mov     [rbp+3E0h+var_50], rax
0x18004a9a9  xor     r13d, r13d
0x18004a9ac  mov     [rsp+4E0h+var_490], r9
0x18004a9b1  mov     [rsp+4E0h+hObject], r13
0x18004a9b6  mov     r14, r9
0x18004a9b9  mov     r15, r8
0x18004a9bc  mov     [rsp+4E0h+hKey], r8
0x18004a9c1  mov     edi, edx
0x18004a9c3  mov     rsi, rcx
0x18004a9c6  call    Old_IsRNGWinNT
0x18004a9cb  test    eax, eax
0x18004a9cd  jz      loc_18004AAF9
0x18004a9d3  mov     rbx, cs:g_hKsecDD
0x18004a9da  mov     [rsp+4E0h+hObject], rbx
0x18004a9df  test    rbx, rbx
0x18004a9e2  jnz     loc_18004AABB
0x18004a9e8  xorps   xmm0, xmm0
0x18004a9eb  xor     eax, eax
0x18004a9ed  cmp     cs:___NtOpenFileRNG, r13
0x18004a9f4  movups  [rbp+3E0h+var_450], xmm0
0x18004a9f8  movups  [rbp+3E0h+var_450+0Ch], xmm0
0x18004a9fc  movups  [rsp+4E0h+var_488], xmm0
0x18004aa01  movups  [rbp+3E0h+var_460], xmm0
0x18004aa05  movups  [rsp+4E0h+var_478], xmm0
0x18004aa0a  jz      loc_18004AAF9
0x18004aa10  mov     rax, cs:___RtlInitUnicodeStringRNG
0x18004aa17  test    rax, rax
0x18004aa1a  jz      loc_18004AAF9
0x18004aa20  lea     rdx, aDeviceKsecdd; "\\Device\\KsecDD"
0x18004aa27  lea     rcx, [rsp+4E0h+var_488]
0x18004aa2c  call    cs:__guard_dispatch_icall_fptr
0x18004aa32  lea     rax, [rsp+4E0h+var_488]
0x18004aa37  mov     [rsp+4E0h+nOutBufferSize], 20h ; ' '
0x18004aa3f  mov     qword ptr [rbp+3E0h+var_450], rax
0x18004aa43  lea     r9, [rsp+4E0h+var_478]
0x18004aa48  mov     rax, cs:___NtOpenFileRNG
0x18004aa4f  lea     r8, [rbp+3E0h+var_460]
0x18004aa53  xorps   xmm0, xmm0
0x18004aa56  mov     dword ptr [rbp+3E0h+var_460], 30h ; '0'
0x18004aa5d  mov     edx, 100001h
0x18004aa62  mov     qword ptr [rbp+3E0h+var_460+8], r13
0x18004aa66  lea     rcx, [rsp+4E0h+hObject]
0x18004aa6b  mov     dword ptr [rbp+3E0h+var_450+8], 40h ; '@'
0x18004aa72  movdqu  [rbp+3E0h+var_440], xmm0
0x18004aa77  mov     dword ptr [rsp+4E0h+lpOutBuffer], 7
0x18004aa7f  call    cs:__guard_dispatch_icall_fptr
0x18004aa85  test    eax, eax
0x18004aa87  js      short loc_18004AAF9
0x18004aa89  mov     rcx, [rsp+4E0h+hObject]
0x18004aa8e  xor     eax, eax
0x18004aa90  lock cmpxchg cs:g_hKsecDD, rcx
0x18004aa99  mov     rbx, rax
0x18004aa9c  jz      short loc_18004AAB6
0x18004aa9e  mov     rcx, [rsp+4E0h+hObject]; hObject
0x18004aaa3  call    cs:__imp_CloseHandle
0x18004aaaa  nop     dword ptr [rax+rax+00h]
0x18004aaaf  mov     [rsp+4E0h+hObject], rbx
0x18004aab4  jmp     short loc_18004AABB
0x18004aab6  mov     rbx, [rsp+4E0h+hObject]
0x18004aabb  mov     eax, [r14]
0x18004aabe  mov     r9d, edi; nInBufferSize
0x18004aac1  mov     [rsp+4E0h+lpOverlapped], r13; lpOverlapped
0x18004aac6  mov     r8, rsi; lpInBuffer
0x18004aac9  mov     [rsp+4E0h+lpBytesReturned], r14; lpBytesReturned
0x18004aace  mov     edx, 390008h; dwIoControlCode
0x18004aad3  mov     [rsp+4E0h+nOutBufferSize], eax; nOutBufferSize
0x18004aad7  mov     rcx, rbx; hDevice
0x18004aada  mov     [rsp+4E0h+lpOutBuffer], r15; lpOutBuffer
0x18004aadf  call    cs:__imp_DeviceIoControl
0x18004aae6  nop     dword ptr [rax+rax+00h]
0x18004aaeb  test    eax, eax
0x18004aaed  jz      short loc_18004AAF9
0x18004aaef  mov     eax, 1
0x18004aaf4  jmp     loc_18004B463
0x18004aaf9  call    cs:__imp_GetProcessHeap
0x18004ab00  nop     dword ptr [rax+rax+00h]
0x18004ab05  mov     r14d, 0E00h
0x18004ab0b  xor     edx, edx; dwFlags
0x18004ab0d  mov     rcx, rax; hHeap
0x18004ab10  mov     r8d, r14d; dwBytes
0x18004ab13  call    cs:__imp_HeapAlloc
0x18004ab1a  nop     dword ptr [rax+rax+00h]
0x18004ab1f  mov     r12, rax
0x18004ab22  test    rax, rax
0x18004ab25  jz      loc_18004B463
0x18004ab2b  mov     ebx, r14d
0x18004ab2e  mov     r13d, 50h ; 'P'
0x18004ab34  cmp     edi, r14d
0x18004ab37  ja      loc_18004B295
0x18004ab3d  mov     r8, rdi; Size
0x18004ab40  mov     rdx, rsi; Src
0x18004ab43  mov     rcx, r12; void *
0x18004ab46  call    memcpy_0
0x18004ab4b  lea     eax, [rdi+8]
0x18004ab4e  and     eax, 0FFFFFFF8h
0x18004ab51  cmp     eax, r14d
0x18004ab54  jbe     short loc_18004AB5D
0x18004ab56  xor     ebx, ebx
0x18004ab58  jmp     loc_18004B295
0x18004ab5d  mov     edi, eax
0x18004ab5f  sub     ebx, eax
0x18004ab61  call    cs:__imp_GetCurrentProcessId
0x18004ab68  nop     dword ptr [rax+rax+00h]
0x18004ab6d  mov     [rdi+r12], eax
0x18004ab71  cmp     ebx, 8
0x18004ab74  jb      short loc_18004AB56
0x18004ab76  add     ebx, 0FFFFFFF8h
0x18004ab79  call    cs:__imp_GetCurrentThreadId
0x18004ab80  nop     dword ptr [rax+rax+00h]
0x18004ab85  mov     [rdi+r12+8], eax
0x18004ab8a  cmp     ebx, 8
0x18004ab8d  jb      short loc_18004AB56
0x18004ab8f  add     ebx, 0FFFFFFF8h
0x18004ab92  call    cs:__imp_GetTickCount
0x18004ab99  nop     dword ptr [rax+rax+00h]
0x18004ab9e  mov     [rdi+r12+10h], eax
0x18004aba3  cmp     ebx, 8
0x18004aba6  jb      short loc_18004AB56
0x18004aba8  add     ebx, 0FFFFFFF8h
0x18004abab  cmp     ebx, 10h
0x18004abae  jb      loc_18004B295
0x18004abb4  lea     rcx, [rdi+18h]
0x18004abb8  add     rcx, r12; lpSystemTime
0x18004abbb  call    cs:__imp_GetLocalTime
0x18004abc2  nop     dword ptr [rax+rax+00h]
0x18004abc7  cmp     ebx, 18h
0x18004abca  jb      short loc_18004AB56
0x18004abcc  mov     esi, 0FFFFFFE8h
0x18004abd1  add     ebx, esi
0x18004abd3  cmp     ebx, 8
0x18004abd6  jb      loc_18004B295
0x18004abdc  lea     r15, [rdi+r12]
0x18004abe0  lea     rcx, [r15+30h]; lpPerformanceCount
0x18004abe4  call    cs:__imp_QueryPerformanceCounter
0x18004abeb  nop     dword ptr [rax+rax+00h]
0x18004abf0  cmp     ebx, 10h
0x18004abf3  jnb     short loc_18004ABFC
0x18004abf5  xor     ebx, ebx
0x18004abf7  jmp     loc_18004B290
0x18004abfc  add     ebx, 0FFFFFFF0h
0x18004abff  cmp     ebx, 40h ; '@'
0x18004ac02  jb      loc_18004B290
0x18004ac08  lea     rcx, [r15+40h]; lpBuffer
0x18004ac0c  mov     dword ptr [r15+40h], 40h ; '@'
0x18004ac14  call    cs:__imp_GlobalMemoryStatusEx
0x18004ac1b  nop     dword ptr [rax+rax+00h]
0x18004ac20  cmp     ebx, 48h ; 'H'
0x18004ac23  jb      short loc_18004ABF5
0x18004ac25  add     ebx, 0FFFFFFB8h
0x18004ac28  cmp     ebx, 10h
0x18004ac2b  jb      loc_18004B290
0x18004ac31  lea     rax, [r15+94h]
0x18004ac38  xor     ecx, ecx; lpRootPathName
0x18004ac3a  lea     r9, [r15+90h]; lpNumberOfFreeClusters
0x18004ac41  mov     [rsp+4E0h+lpOutBuffer], rax; lpTotalNumberOfClusters
0x18004ac46  lea     r8, [r15+8Ch]; lpBytesPerSector
0x18004ac4d  lea     rdx, [r15+88h]; lpSectorsPerCluster
0x18004ac54  call    cs:__imp_GetDiskFreeSpaceW
0x18004ac5b  nop     dword ptr [rax+rax+00h]
0x18004ac60  cmp     ebx, 18h
0x18004ac63  jb      short loc_18004ABF5
0x18004ac65  add     ebx, esi
0x18004ac67  cmp     cs:dword_1800AD8E8, 0
0x18004ac6e  jnz     loc_18004AD72
0x18004ac74  xor     r13d, r13d
0x18004ac77  call    cs:__imp_GetEnvironmentStringsW
0x18004ac7e  nop     dword ptr [rax+rax+00h]
0x18004ac83  mov     rsi, rax
0x18004ac86  test    rax, rax
0x18004ac89  jnz     short loc_18004ACA9
0x18004ac8b  call    cs:__imp_GetEnvironmentStringsW
0x18004ac92  nop     dword ptr [rax+rax+00h]
0x18004ac97  mov     rsi, rax
0x18004ac9a  mov     r13d, 1
0x18004aca0  test    rax, rax
0x18004aca3  jz      loc_18004AD5D
0x18004aca9  xor     eax, eax
0x18004acab  lea     rcx, [rbp+3E0h+Data]; void *
0x18004acaf  xor     edx, edx; Val
0x18004acb1  mov     dword ptr [rbp+3E0h+Data+4], eax
0x18004acb4  lea     r8d, [rax+6Ch]; Size
0x18004acb8  call    memset_0
0x18004acbd  movups  xmm0, cs:xmmword_180098DD8
0x18004acc4  mov     r14, rsi
0x18004acc7  xor     edi, edi
0x18004acc9  movdqu  [rbp+3E0h+var_380], xmm0
0x18004acce  mov     eax, edi
0x18004acd0  mov     edx, 7FFFh; MaxCount
0x18004acd5  add     r14, rax
0x18004acd8  test    r13d, r13d
0x18004acdb  jnz     short loc_18004ACF7
0x18004acdd  add     r14, 2
0x18004ace1  mov     rcx, r14; Source
0x18004ace4  call    cs:__imp_wcsnlen
0x18004aceb  nop     dword ptr [rax+rax+00h]
0x18004acf0  mov     rdi, rax
0x18004acf3  add     edi, edi
0x18004acf5  jmp     short loc_18004AD0B
0x18004acf7  inc     r14
0x18004acfa  mov     rcx, r14; String
0x18004acfd  call    cs:__imp_strnlen
0x18004ad04  nop     dword ptr [rax+rax+00h]
0x18004ad09  mov     edi, eax
0x18004ad0b  mov     r9d, edi
0x18004ad0e  lea     rdx, [rbp+3E0h+Data]
0x18004ad12  mov     r8, r14
0x18004ad15  lea     rcx, SymCryptMd4Algorithm_default
0x18004ad1c  call    SymCryptHashAppendInternal
0x18004ad21  test    edi, edi
0x18004ad23  jnz     short loc_18004ACCE
0x18004ad25  lea     rdx, xmmword_1800ADA60
0x18004ad2c  lea     rcx, [rbp+3E0h+Data]
0x18004ad30  call    SymCryptMd4Result
0x18004ad35  mov     rcx, rsi; penv
0x18004ad38  test    r13d, r13d
0x18004ad3b  jnz     short loc_18004AD4B
0x18004ad3d  call    cs:__imp_FreeEnvironmentStringsW
0x18004ad44  nop     dword ptr [rax+rax+00h]
0x18004ad49  jmp     short loc_18004AD57
0x18004ad4b  call    cs:__imp_FreeEnvironmentStringsA
0x18004ad52  nop     dword ptr [rax+rax+00h]
0x18004ad57  mov     r14d, 0E00h
0x18004ad5d  mov     cs:dword_1800AD8E8, 1
0x18004ad67  mov     esi, 0FFFFFFE8h
0x18004ad6c  mov     r13d, 50h ; 'P'
0x18004ad72  cmp     ebx, 10h
0x18004ad75  jb      loc_18004B290
0x18004ad7b  movups  xmm0, cs:xmmword_1800ADA60
0x18004ad82  movdqu  xmmword ptr [r15+0A0h], xmm0
0x18004ad8b  cmp     ebx, 18h
0x18004ad8e  jb      loc_18004ABF5
0x18004ad94  add     ebx, esi
0x18004ad96  call    Old_IsRNGWinNT
0x18004ad9b  test    eax, eax
0x18004ad9d  jz      loc_18004B290
0x18004ada3  cmp     ebx, 40h ; '@'
0x18004ada6  jb      loc_18004B290
0x18004adac  mov     rax, cs:___NtQuerySystemInformationRNG
0x18004adb3  test    rax, rax
0x18004adb6  jz      loc_18004B290
0x18004adbc  xor     r9d, r9d
0x18004adbf  mov     dword ptr [rsp+4E0h+hObject], ebx
0x18004adc3  lea     rsi, [r15+0B8h]
0x18004adca  mov     r8d, ebx
0x18004adcd  mov     rdx, rsi
0x18004add0  lea     ecx, [r9+5]
0x18004add4  call    cs:__guard_dispatch_icall_fptr
0x18004adda  xor     eax, eax
0x18004addc  lea     rcx, [rbp+3E0h+Data]; void *
0x18004ade0  xor     edx, edx; Val
0x18004ade2  mov     dword ptr [rbp+3E0h+Data+4], eax
0x18004ade5  lea     r8d, [rax+7Ch]; Size
0x18004ade9  call    memset_0
0x18004adee  lea     rcx, [rbp+3E0h+Data]
0x18004adf2  call    SymCryptSha1Init
0x18004adf7  mov     r8d, dword ptr [rsp+4E0h+hObject]
0x18004adfc  lea     rcx, [rbp+3E0h+Data]
0x18004ae00  mov     rdx, rsi
0x18004ae03  call    SymCryptSha1Append
0x18004ae08  mov     rdx, rsi
0x18004ae0b  lea     rcx, [rbp+3E0h+Data]
0x18004ae0f  call    SymCryptSha1Result
0x18004ae14  mov     r15d, 0FFFFFFE8h
0x18004ae1a  add     ebx, r15d
0x18004ae1d  cmp     ebx, 30h ; '0'
0x18004ae20  jb      loc_18004B290
0x18004ae26  mov     rax, cs:___NtQuerySystemInformationRNG
0x18004ae2d  lea     r9, [rsp+4E0h+hObject]
0x18004ae32  mov     r8d, 30h ; '0'
0x18004ae38  add     rsi, 18h
0x18004ae3c  mov     rdx, rsi
0x18004ae3f  lea     ecx, [r8-2Dh]
0x18004ae43  call    cs:__guard_dispatch_icall_fptr
0x18004ae49  test    eax, eax
0x18004ae4b  js      short loc_18004AE71
0x18004ae4d  mov     eax, dword ptr [rsp+4E0h+hObject]
0x18004ae51  add     eax, 8
0x18004ae54  and     eax, 0FFFFFFF8h
0x18004ae57  cmp     eax, ebx
0x18004ae59  ja      loc_18004ABF5
0x18004ae5f  mov     edi, eax
0x18004ae61  sub     ebx, eax
0x18004ae63  add     rdi, rsi
0x18004ae66  cmp     ebx, 18h
0x18004ae69  jb      loc_18004B290
0x18004ae6f  jmp     short loc_18004AE74
0x18004ae71  mov     rdi, rsi
0x18004ae74  mov     rax, cs:___NtQuerySystemInformationRNG
  ... truncated ...
```
