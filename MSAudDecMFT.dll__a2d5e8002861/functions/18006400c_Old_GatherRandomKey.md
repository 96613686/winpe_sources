# Old_GatherRandomKey

- ea: `0x18006400c`
- end: `0x1800649f8`
- name: `Old_GatherRandomKey`
- size: `2540`
- prototype: `__int64 __fastcall(void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x180044e8c`
- `0x180064c18`

## callees

- `0x180049260`
- `0x18004a5b0`
- `0x18004a6f8`
- `0x18004a7cc`
- `0x18004a8c0`
- `0x18004a8e8`
- `0x18004d320`
- `0x18004dd14`
- `0x18006400c`
- `0x180064a00`
- `0x180064b64`
- `0x180064d70`
- `0x1800650dc`
- `0x180067d80`
- `0x18009606c`
- `0x1800960c0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180064255`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180064255`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x18006426e`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x18006426e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800640de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800640de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800640c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800640c6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180064149`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180064149`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800640f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800640f7`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180064179`
- `api-ms-win-core-sysinfo-l1-1-0!GlobalMemoryStatusEx` at `0x180064179`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180064120`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180064120`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180064921`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180064921`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180064932`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180064932`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064078`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064078`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006405e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800649b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006405e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800649b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800649c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800649c6`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x1800641b9`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceW` at `0x1800641b9`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsA` at `0x1800642c2`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsA` at `0x1800642c2`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x1800641e1`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x1800641f5`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x1800641e1`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x1800641f5`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x1800642b4`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x1800642b4`

## pseudocode

```c
__int64 __fastcall Old_GatherRandomKey(void *Src, size_t Size, HKEY a3, DWORD *a4)
{
  HKEY v4; // r15
  size_t v6; // rdi
  __int64 result; // rax
  HANDLE ProcessHeap; // rax
  __int64 v9; // r13
  _BYTE *v10; // r12
  unsigned int v11; // ebx
  __int64 v12; // r14
  unsigned int v13; // eax
  __int64 v14; // rdi
  unsigned int v15; // ebx
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  char *v18; // r15
  CHAR *EnvironmentStringsW; // rsi
  const char *v20; // r14
  unsigned int v21; // edi
  const char *v22; // r14
  unsigned int v23; // eax
  __int64 v24; // rdi
  unsigned int v25; // ecx
  __int64 v26; // rax
  unsigned int v27; // ecx
  __int64 v28; // rax
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  __int64 v31; // rdi
  __int64 v32; // rdx
  unsigned int v33; // ebx
  __int64 v34; // rcx
  BYTE *v35; // rax
  __int128 *v36; // rax
  _BYTE *v37; // rax
  _BYTE *v38; // rax
  HANDLE v39; // rax
  unsigned int v40; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD *v42; // [rsp+40h] [rbp-C0h]
  __int128 v43; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v44; // [rsp+60h] [rbp-A0h]
  __int128 v45; // [rsp+70h] [rbp-90h]
  __int128 v46; // [rsp+80h] [rbp-80h]
  __int128 v47; // [rsp+90h] [rbp-70h]
  BYTE Data[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v49; // [rsp+E0h] [rbp-20h]
  __int128 v50; // [rsp+F0h] [rbp-10h]
  __int128 v51; // [rsp+100h] [rbp+0h]
  __int128 v52; // [rsp+110h] [rbp+10h]
  __int128 v53; // [rsp+130h] [rbp+30h]
  _BYTE v54[4]; // [rsp+150h] [rbp+50h] BYREF
  int v55; // [rsp+154h] [rbp+54h]
  _BYTE v56[4]; // [rsp+1D0h] [rbp+D0h] BYREF
  int v57; // [rsp+1D4h] [rbp+D4h]
  _BYTE v58[4]; // [rsp+250h] [rbp+150h] BYREF
  int v59; // [rsp+254h] [rbp+154h]
  _BYTE v60[4]; // [rsp+2D0h] [rbp+1D0h] BYREF
  int v61; // [rsp+2D4h] [rbp+1D4h]
  _BYTE v62[272]; // [rsp+350h] [rbp+250h] BYREF

  v42 = a4;
  v4 = a3;
  hKey = a3;
  v6 = (unsigned int)Size;
  if ( (unsigned int)Old_GatherRandomKeyFastUserMode(Src, Size, a3, a4) )
    return 1;
  ProcessHeap = GetProcessHeap();
  v9 = 3584;
  result = (__int64)HeapAlloc(ProcessHeap, 0, 0xE00u);
  v10 = (_BYTE *)result;
  if ( result )
  {
    v11 = 3584;
    v12 = 80;
    if ( (unsigned int)v6 <= 0xE00 )
    {
      memcpy_0((void *)result, Src, v6);
      v13 = (v6 + 8) & 0xFFFFFFF8;
      if ( v13 > 0xE00 )
        goto LABEL_6;
      v14 = v13;
      v15 = 3584 - v13;
      *(_DWORD *)&v10[v13] = GetCurrentProcessId();
      if ( v15 < 8 )
        goto LABEL_6;
      v16 = v15 - 8;
      *(_DWORD *)&v10[v14 + 8] = GetCurrentThreadId();
      if ( v16 < 8 )
        goto LABEL_6;
      v17 = v16 - 8;
      *(_DWORD *)&v10[v14 + 16] = GetTickCount();
      if ( v17 < 8 )
        goto LABEL_6;
      v11 = v17 - 8;
      if ( v11 < 0x10 )
        goto LABEL_87;
      GetLocalTime((LPSYSTEMTIME)&v10[v14 + 24]);
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
          v18 = &v10[v14];
          QueryPerformanceCounter((LARGE_INTEGER *)&v10[v14 + 48]);
          if ( v11 >= 0x10 )
          {
            v11 -= 16;
            if ( v11 < 0x40 )
              goto LABEL_86;
            *((_DWORD *)v18 + 16) = 64;
            GlobalMemoryStatusEx((LPMEMORYSTATUSEX)v18 + 1);
            if ( v11 >= 0x48 )
            {
              v11 -= 72;
              if ( v11 < 0x10 )
                goto LABEL_86;
              GetDiskFreeSpaceW(0, (LPDWORD)v18 + 34, (LPDWORD)v18 + 35, (LPDWORD)v18 + 36, (LPDWORD)v18 + 37);
              if ( v11 >= 0x18 )
              {
                v11 -= 24;
                if ( !dword_1800E5960 )
                {
                  v40 = 0;
                  EnvironmentStringsW = (CHAR *)GetEnvironmentStringsW();
                  if ( EnvironmentStringsW || (v40 = 1, (EnvironmentStringsW = (CHAR *)GetEnvironmentStringsW()) != 0) )
                  {
                    *(_DWORD *)&Data[4] = 0;
                    memset_0(Data, 0, 0x6Cu);
                    v20 = EnvironmentStringsW;
                    v21 = 0;
                    v53 = xmmword_1800B74F0;
                    do
                    {
                      v22 = &v20[v21];
                      if ( v40 )
                      {
                        v20 = v22 + 1;
                        v21 = strnlen(v20, 0x7FFFu);
                      }
                      else
                      {
                        v20 = v22 + 2;
                        v21 = 2 * wcsnlen((const wchar_t *)v20, 0x7FFFu);
                      }
                      SymCryptHashAppendInternal(SymCryptMd4Algorithm_default, Data, v20, v21);
                    }
                    while ( v21 );
                    SymCryptMd4Result(Data, &xmmword_1800E5AE0);
                    v9 = 3584;
                    if ( v40 )
                      FreeEnvironmentStringsA(EnvironmentStringsW);
                    else
                      FreeEnvironmentStringsW((LPWCH)EnvironmentStringsW);
                    v12 = 80;
                  }
                  dword_1800E5960 = 1;
                }
                if ( v11 < 0x10 )
                  goto LABEL_86;
                *((_OWORD *)v18 + 10) = xmmword_1800E5AE0;
                if ( v11 >= 0x18 )
                {
                  v11 -= 24;
                  if ( !(unsigned int)Old_IsRNGWinNT() )
                    goto LABEL_86;
                  if ( v11 < 0x40 )
                    goto LABEL_86;
                  if ( !__NtQuerySystemInformationRNG )
                    goto LABEL_86;
                  v40 = v11;
                  __NtQuerySystemInformationRNG(5, v18 + 184, v11);
                  *(_DWORD *)&Data[4] = 0;
                  memset_0(Data, 0, 0x7Cu);
                  SymCryptSha1Init(Data);
                  SymCryptSha1Append(Data, v18 + 184, v11);
                  SymCryptSha1Result(Data, v18 + 184);
                  v11 -= 24;
                  if ( v11 < 0x30 )
                    goto LABEL_86;
                  if ( (int)((__int64 (__fastcall *)(__int64, char *, __int64, unsigned int *))__NtQuerySystemInformationRNG)(
                              3,
                              v18 + 208,
                              48,
                              &v40) < 0 )
                  {
                    v24 = (__int64)(v18 + 208);
                  }
                  else
                  {
                    v23 = (v40 + 8) & 0xFFFFFFF8;
                    if ( v23 > v11 )
                      goto LABEL_14;
                    v11 -= v23;
                    v24 = (__int64)&v18[v23 + 208];
                    if ( v11 < 0x18 )
                      goto LABEL_86;
                  }
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, unsigned int *))__NtQuerySystemInformationRNG)(
                              7,
                              v24,
                              24,
                              &v40) >= 0 )
                  {
                    v25 = (v40 + 8) & 0xFFFFFFF8;
                    if ( v25 > v11 )
                      goto LABEL_14;
                    v24 += v25;
                    v11 -= v25;
                  }
                  if ( v11 < 0xB0 )
                    goto LABEL_86;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, unsigned int *))__NtQuerySystemInformationRNG)(
                              80,
                              v24,
                              176,
                              &v40) >= 0 )
                  {
                    v26 = (v40 + 8) & 0xFFFFFFF8;
                    if ( (unsigned int)v26 > v11 )
                      goto LABEL_14;
                    v11 -= v26;
                    if ( v11 < 0x40 )
                      goto LABEL_86;
                    v24 += v26;
                  }
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, unsigned int *))__NtQuerySystemInformationRNG)(
                              21,
                              v24,
                              64,
                              &v40) >= 0 )
                  {
                    v27 = (v40 + 8) & 0xFFFFFFF8;
                    if ( v27 > v11 )
                      goto LABEL_14;
                    v24 += v27;
                    v11 -= v27;
                  }
                  if ( v11 < 0x178 )
                    goto LABEL_86;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, unsigned int *))__NtQuerySystemInformationRNG)(
                              2,
                              v24,
                              376,
                              &v40) >= 0 )
                  {
                    v28 = (v40 + 8) & 0xFFFFFFF8;
                    if ( (unsigned int)v28 > v11 )
                      goto LABEL_14;
                    v11 -= v28;
                    if ( v11 < 0x10 )
                      goto LABEL_86;
                    v24 += v28;
                  }
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, unsigned int *))__NtQuerySystemInformationRNG)(
                              33,
                              v24,
                              16,
                              &v40) >= 0 )
                  {
                    v29 = (v40 + 8) & 0xFFFFFFF8;
                    if ( v29 > v11 )
                      goto LABEL_14;
                    v24 += v29;
                    v11 -= v29;
                  }
                  if ( v11 < 0x20 )
                    goto LABEL_86;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, __int64, unsigned int *))__NtQuerySystemInformationRNG)(
                              45,
                              v24,
                              32,
                              &v40) >= 0 )
                  {
                    v30 = (v40 + 8) & 0xFFFFFFF8;
                    if ( v30 > v11 )
                      goto LABEL_14;
                    v24 += v30;
                    v11 -= v30;
                  }
                  v40 = v11;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, _QWORD, unsigned int *))__NtQuerySystemInformationRNG)(
                              8,
                              v24,
                              v11,
                              &v40) >= 0 )
                  {
                    DWORD1(v43) = 0;
                    memset_0(&v43, 0, 0x7Cu);
                    if ( v11 < 0x14 )
                      goto LABEL_86;
                    SymCryptSha1Init(&v43);
                    SymCryptSha1Append(&v43, v24, v40);
                    SymCryptSha1Result(&v43, v24);
                    if ( v11 < 0x18 )
                      goto LABEL_14;
                    v24 += 24;
                    v11 -= 24;
                  }
                  v40 = v11;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, _QWORD, unsigned int *))__NtQuerySystemInformationRNG)(
                              61,
                              v24,
                              v11,
                              &v40) >= 0 )
                  {
                    v55 = 0;
                    memset_0(v54, 0, 0x7Cu);
                    if ( v11 < 0x14 )
                      goto LABEL_86;
                    SymCryptSha1Init(v54);
                    SymCryptSha1Append(v54, v24, v40);
                    SymCryptSha1Result(v54, v24);
                    if ( v11 < 0x18 )
                      goto LABEL_14;
                    v24 += 24;
                    v11 -= 24;
                  }
                  v40 = v11;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, _QWORD, unsigned int *))__NtQuerySystemInformationRNG)(
                              18,
                              v24,
                              v11,
                              &v40) >= 0 )
                  {
                    v57 = 0;
                    memset_0(v56, 0, 0x7Cu);
                    if ( v11 < 0x14 )
                      goto LABEL_86;
                    SymCryptSha1Init(v56);
                    SymCryptSha1Append(v56, v24, v40);
                    SymCryptSha1Result(v56, v24);
                    if ( v11 < 0x18 )
                      goto LABEL_14;
                    v24 += 24;
                    v11 -= 24;
                  }
                  v40 = v11;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, _QWORD, unsigned int *))__NtQuerySystemInformationRNG)(
                              23,
                              v24,
                              v11,
                              &v40) >= 0 )
                  {
                    v59 = 0;
                    memset_0(v58, 0, 0x7Cu);
                    if ( v11 < 0x14 )
                      goto LABEL_86;
                    SymCryptSha1Init(v58);
                    SymCryptSha1Append(v58, v24, v40);
                    SymCryptSha1Result(v58, v24);
                    if ( v11 < 0x18 )
                      goto LABEL_14;
                    v24 += 24;
                    v11 -= 24;
                  }
                  v40 = v11;
                  if ( (int)((__int64 (__fastcall *)(__int64, __int64, _QWORD, unsigned int *))__NtQuerySystemInformationRNG)(
                              42,
                              v24,
                              v11,
                              &v40) < 0 )
                    goto LABEL_86;
                  v61 = 0;
                  memset_0(v60, 0, 0x7Cu);
                  if ( v11 < 0x14 )
                    goto LABEL_86;
                  SymCryptSha1Init(v60);
                  SymCryptSha1Append(v60, v24, v40);
                  SymCryptSha1Result(v60, v24);
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
    v31 = 272;
    memset_0(v62, 0, sizeof(v62));
    v43 = *(_OWORD *)&::Data;
    v45 = xmmword_1800E5990;
    v44 = xmmword_1800E5980;
    v47 = xmmword_1800E59B0;
    v46 = xmmword_1800E59A0;
    SymCryptRc4Init(v62, &v43, 80);
    v32 = 3584;
    if ( 3584 - v11 <= 0xE00 )
      v32 = 3584 - v11;
    v33 = VeryLargeHashUpdate(v10, v32, &v43);
    *(_OWORD *)Data = v43;
    v49 = v44;
    v50 = v45;
    v51 = v46;
    v52 = v47;
    *(_OWORD *)&::Data = v43;
    xmmword_1800E5980 = v44;
    xmmword_1800E5990 = v45;
    xmmword_1800E59A0 = v46;
    xmmword_1800E59B0 = v47;
    SymCryptRc4Crypt(v62, Data, Data, 80);
    hKey = 0;
    if ( (unsigned int)AccessSeed(2u, &hKey) )
    {
      RegSetValueExW(hKey, L"Seed", 0, 3u, Data, 0x50u);
      RegCloseKey(hKey);
    }
    v34 = 80;
    v35 = Data;
    do
    {
      *v35++ = 0;
      --v34;
    }
    while ( v34 );
    SymCryptRc4Init(v62, &v43, 80);
    v36 = &v43;
    do
    {
      *(_BYTE *)v36 = 0;
      v36 = (__int128 *)((char *)v36 + 1);
      --v12;
    }
    while ( v12 );
    SymCryptRc4Crypt(v62, v4, v4, *v42);
    v37 = v62;
    do
    {
      *v37++ = 0;
      --v31;
    }
    while ( v31 );
    v38 = v10;
    do
    {
      *v38++ = 0;
      --v9;
    }
    while ( v9 );
    v39 = GetProcessHeap();
    HeapFree(v39, 0, v10);
    return v33;
  }
  return result;
}

```

## disassembly

```asm
0x18006400c  push    rbp
0x18006400e  push    rbx
0x18006400f  push    rsi
0x180064010  push    rdi
0x180064011  push    r12
0x180064013  push    r13
0x180064015  push    r14
0x180064017  push    r15
0x180064019  lea     rbp, [rsp-378h]
0x180064021  sub     rsp, 478h
0x180064028  mov     rax, cs:__security_cookie
0x18006402f  xor     rax, rsp
0x180064032  mov     [rbp+3B0h+var_50], rax
0x180064039  mov     [rsp+4B0h+var_470], r9
0x18006403e  mov     r15, r8
0x180064041  mov     [rsp+4B0h+hKey], r8
0x180064046  mov     rsi, rcx
0x180064049  mov     edi, edx
0x18006404b  call    Old_GatherRandomKeyFastUserMode
0x180064050  test    eax, eax
0x180064052  jz      short loc_18006405E
0x180064054  mov     eax, 1
0x180064059  jmp     loc_1800649D4
0x18006405e  call    cs:__imp_GetProcessHeap
0x180064065  nop     dword ptr [rax+rax+00h]
0x18006406a  mov     r13d, 0E00h
0x180064070  xor     edx, edx; dwFlags
0x180064072  mov     rcx, rax; hHeap
0x180064075  mov     r8d, r13d; dwBytes
0x180064078  call    cs:__imp_HeapAlloc
0x18006407f  nop     dword ptr [rax+rax+00h]
0x180064084  mov     r12, rax
0x180064087  test    rax, rax
0x18006408a  jz      loc_1800649D4
0x180064090  mov     ebx, r13d
0x180064093  mov     r14d, 50h ; 'P'
0x180064099  cmp     edi, r13d
0x18006409c  ja      loc_1800647FC
0x1800640a2  mov     r8, rdi; Size
0x1800640a5  mov     rdx, rsi; Src
0x1800640a8  mov     rcx, r12; void *
0x1800640ab  call    memcpy_0
0x1800640b0  lea     eax, [rdi+8]
0x1800640b3  and     eax, 0FFFFFFF8h
0x1800640b6  cmp     eax, r13d
0x1800640b9  jbe     short loc_1800640C2
0x1800640bb  xor     ebx, ebx
0x1800640bd  jmp     loc_1800647FC
0x1800640c2  mov     edi, eax
0x1800640c4  sub     ebx, eax
0x1800640c6  call    cs:__imp_GetCurrentProcessId
0x1800640cd  nop     dword ptr [rax+rax+00h]
0x1800640d2  mov     [rdi+r12], eax
0x1800640d6  cmp     ebx, 8
0x1800640d9  jb      short loc_1800640BB
0x1800640db  add     ebx, 0FFFFFFF8h
0x1800640de  call    cs:__imp_GetCurrentThreadId
0x1800640e5  nop     dword ptr [rax+rax+00h]
0x1800640ea  mov     [rdi+r12+8], eax
0x1800640ef  cmp     ebx, 8
0x1800640f2  jb      short loc_1800640BB
0x1800640f4  add     ebx, 0FFFFFFF8h
0x1800640f7  call    cs:__imp_GetTickCount
0x1800640fe  nop     dword ptr [rax+rax+00h]
0x180064103  mov     [rdi+r12+10h], eax
0x180064108  cmp     ebx, 8
0x18006410b  jb      short loc_1800640BB
0x18006410d  add     ebx, 0FFFFFFF8h
0x180064110  cmp     ebx, 10h
0x180064113  jb      loc_1800647FC
0x180064119  lea     rcx, [rdi+18h]
0x18006411d  add     rcx, r12; lpSystemTime
0x180064120  call    cs:__imp_GetLocalTime
0x180064127  nop     dword ptr [rax+rax+00h]
0x18006412c  cmp     ebx, 18h
0x18006412f  jb      short loc_1800640BB
0x180064131  mov     esi, 0FFFFFFE8h
0x180064136  add     ebx, esi
0x180064138  cmp     ebx, 8
0x18006413b  jb      loc_1800647FC
0x180064141  lea     r15, [rdi+r12]
0x180064145  lea     rcx, [r15+30h]; lpPerformanceCount
0x180064149  call    cs:__imp_QueryPerformanceCounter
0x180064150  nop     dword ptr [rax+rax+00h]
0x180064155  cmp     ebx, 10h
0x180064158  jnb     short loc_180064161
0x18006415a  xor     ebx, ebx
0x18006415c  jmp     loc_1800647F7
0x180064161  add     ebx, 0FFFFFFF0h
0x180064164  cmp     ebx, 40h ; '@'
0x180064167  jb      loc_1800647F7
0x18006416d  lea     rcx, [r15+40h]; lpBuffer
0x180064171  mov     dword ptr [r15+40h], 40h ; '@'
0x180064179  call    cs:__imp_GlobalMemoryStatusEx
0x180064180  nop     dword ptr [rax+rax+00h]
0x180064185  cmp     ebx, 48h ; 'H'
0x180064188  jb      short loc_18006415A
0x18006418a  add     ebx, 0FFFFFFB8h
0x18006418d  cmp     ebx, 10h
0x180064190  jb      loc_1800647F7
0x180064196  lea     rax, [r15+94h]
0x18006419d  xor     ecx, ecx; lpRootPathName
0x18006419f  lea     r9, [r15+90h]; lpNumberOfFreeClusters
0x1800641a6  mov     [rsp+4B0h+lpTotalNumberOfClusters], rax; lpTotalNumberOfClusters
0x1800641ab  lea     r8, [r15+8Ch]; lpBytesPerSector
0x1800641b2  lea     rdx, [r15+88h]; lpSectorsPerCluster
0x1800641b9  call    cs:__imp_GetDiskFreeSpaceW
0x1800641c0  nop     dword ptr [rax+rax+00h]
0x1800641c5  cmp     ebx, 18h
0x1800641c8  jb      short loc_18006415A
0x1800641ca  add     ebx, esi
0x1800641cc  cmp     cs:dword_1800E5960, 0
0x1800641d3  jnz     loc_1800642E3
0x1800641d9  mov     [rsp+4B0h+var_480], 0
0x1800641e1  call    cs:__imp_GetEnvironmentStringsW
0x1800641e8  nop     dword ptr [rax+rax+00h]
0x1800641ed  mov     rsi, rax
0x1800641f0  test    rax, rax
0x1800641f3  jnz     short loc_180064215
0x1800641f5  call    cs:__imp_GetEnvironmentStringsW
0x1800641fc  nop     dword ptr [rax+rax+00h]
0x180064201  mov     [rsp+4B0h+var_480], 1
0x180064209  mov     rsi, rax
0x18006420c  test    rax, rax
0x18006420f  jz      loc_1800642D4
0x180064215  xor     eax, eax
0x180064217  lea     rcx, [rbp+3B0h+Data]; void *
0x18006421b  xor     edx, edx; Val
0x18006421d  mov     dword ptr [rbp+3B0h+Data+4], eax
0x180064220  lea     r8d, [rax+6Ch]; Size
0x180064224  call    memset_0
0x180064229  movups  xmm0, cs:xmmword_1800B74F0
0x180064230  mov     r13d, [rsp+4B0h+var_480]
0x180064235  mov     r14, rsi
0x180064238  xor     edi, edi
0x18006423a  movdqu  [rbp+3B0h+var_380], xmm0
0x18006423f  mov     eax, edi
0x180064241  mov     edx, 7FFFh; MaxCount
0x180064246  add     r14, rax
0x180064249  test    r13d, r13d
0x18006424c  jnz     short loc_180064268
0x18006424e  add     r14, 2
0x180064252  mov     rcx, r14; Source
0x180064255  call    cs:__imp_wcsnlen
0x18006425c  nop     dword ptr [rax+rax+00h]
0x180064261  mov     rdi, rax
0x180064264  add     edi, edi
0x180064266  jmp     short loc_18006427C
0x180064268  inc     r14
0x18006426b  mov     rcx, r14; String
0x18006426e  call    cs:__imp_strnlen
0x180064275  nop     dword ptr [rax+rax+00h]
0x18006427a  mov     edi, eax
0x18006427c  mov     r9d, edi
0x18006427f  lea     rdx, [rbp+3B0h+Data]
0x180064283  mov     r8, r14
0x180064286  lea     rcx, SymCryptMd4Algorithm_default
0x18006428d  call    SymCryptHashAppendInternal
0x180064292  test    edi, edi
0x180064294  jnz     short loc_18006423F
0x180064296  lea     rdx, xmmword_1800E5AE0
0x18006429d  lea     rcx, [rbp+3B0h+Data]
0x1800642a1  call    SymCryptMd4Result
0x1800642a6  cmp     r13d, edi
0x1800642a9  mov     rcx, rsi; penv
0x1800642ac  mov     r13d, 0E00h
0x1800642b2  jnz     short loc_1800642C2
0x1800642b4  call    cs:__imp_FreeEnvironmentStringsW
0x1800642bb  nop     dword ptr [rax+rax+00h]
0x1800642c0  jmp     short loc_1800642CE
0x1800642c2  call    cs:__imp_FreeEnvironmentStringsA
0x1800642c9  nop     dword ptr [rax+rax+00h]
0x1800642ce  mov     r14d, 50h ; 'P'
0x1800642d4  mov     cs:dword_1800E5960, 1
0x1800642de  mov     esi, 0FFFFFFE8h
0x1800642e3  cmp     ebx, 10h
0x1800642e6  jb      loc_1800647F7
0x1800642ec  movups  xmm0, cs:xmmword_1800E5AE0
0x1800642f3  movdqu  xmmword ptr [r15+0A0h], xmm0
0x1800642fc  cmp     ebx, 18h
0x1800642ff  jb      loc_18006415A
0x180064305  add     ebx, esi
0x180064307  call    Old_IsRNGWinNT
0x18006430c  test    eax, eax
0x18006430e  jz      loc_1800647F7
0x180064314  cmp     ebx, 40h ; '@'
0x180064317  jb      loc_1800647F7
0x18006431d  mov     rax, cs:___NtQuerySystemInformationRNG
0x180064324  test    rax, rax
0x180064327  jz      loc_1800647F7
0x18006432d  xor     r9d, r9d
0x180064330  mov     [rsp+4B0h+var_480], ebx
0x180064334  lea     rsi, [r15+0B8h]
0x18006433b  mov     r8d, ebx
0x18006433e  mov     rdx, rsi
0x180064341  lea     ecx, [r9+5]
0x180064345  call    cs:__guard_dispatch_icall_fptr
0x18006434b  xor     eax, eax
0x18006434d  lea     rcx, [rbp+3B0h+Data]; void *
0x180064351  xor     edx, edx; Val
0x180064353  mov     dword ptr [rbp+3B0h+Data+4], eax
0x180064356  lea     r8d, [rax+7Ch]; Size
0x18006435a  call    memset_0
0x18006435f  lea     rcx, [rbp+3B0h+Data]
0x180064363  call    SymCryptSha1Init
0x180064368  mov     r8d, [rsp+4B0h+var_480]
0x18006436d  lea     rcx, [rbp+3B0h+Data]
0x180064371  mov     rdx, rsi
0x180064374  call    SymCryptSha1Append
0x180064379  mov     rdx, rsi
0x18006437c  lea     rcx, [rbp+3B0h+Data]
0x180064380  call    SymCryptSha1Result
0x180064385  mov     r15d, 0FFFFFFE8h
0x18006438b  mov     r8d, 30h ; '0'
0x180064391  add     ebx, r15d
0x180064394  cmp     ebx, r8d
0x180064397  jb      loc_1800647F7
0x18006439d  mov     rax, cs:___NtQuerySystemInformationRNG
0x1800643a4  lea     r9, [rsp+4B0h+var_480]
0x1800643a9  add     rsi, 18h
0x1800643ad  lea     ecx, [r8-2Dh]
0x1800643b1  mov     rdx, rsi
0x1800643b4  call    cs:__guard_dispatch_icall_fptr
0x1800643ba  test    eax, eax
0x1800643bc  js      short loc_1800643E2
0x1800643be  mov     eax, [rsp+4B0h+var_480]
0x1800643c2  add     eax, 8
0x1800643c5  and     eax, 0FFFFFFF8h
0x1800643c8  cmp     eax, ebx
0x1800643ca  ja      loc_18006415A
0x1800643d0  mov     edi, eax
0x1800643d2  sub     ebx, eax
0x1800643d4  add     rdi, rsi
0x1800643d7  cmp     ebx, 18h
0x1800643da  jb      loc_1800647F7
0x1800643e0  jmp     short loc_1800643E5
0x1800643e2  mov     rdi, rsi
0x1800643e5  mov     rax, cs:___NtQuerySystemInformationRNG
0x1800643ec  lea     r9, [rsp+4B0h+var_480]
0x1800643f1  mov     r8d, 18h
0x1800643f7  mov     rdx, rdi
0x1800643fa  lea     ecx, [r8-11h]
0x1800643fe  call    cs:__guard_dispatch_icall_fptr
0x180064404  mov     esi, 0FFFFFFF8h
0x180064409  test    eax, eax
0x18006440b  js      short loc_180064425
0x18006440d  mov     ecx, [rsp+4B0h+var_480]
0x180064411  add     ecx, 8
0x180064414  and     ecx, esi
0x180064416  cmp     ecx, ebx
0x180064418  ja      loc_18006415A
0x18006441e  mov     eax, ecx
0x180064420  add     rdi, rax
0x180064423  sub     ebx, ecx
0x180064425  mov     r8d, 0B0h
0x18006442b  cmp     ebx, r8d
0x18006442e  jb      loc_1800647F7
0x180064434  mov     rax, cs:___NtQuerySystemInformationRNG
0x18006443b  lea     r9, [rsp+4B0h+var_480]
0x180064440  mov     rdx, rdi
0x180064443  mov     ecx, r14d
0x180064446  call    cs:__guard_dispatch_icall_fptr
0x18006444c  test    eax, eax
0x18006444e  js      short loc_18006446F
0x180064450  mov     eax, [rsp+4B0h+var_480]
0x180064454  add     eax, 8
0x180064457  and     eax, esi
0x180064459  cmp     eax, ebx
0x18006445b  ja      loc_18006415A
0x180064461  sub     ebx, eax
0x180064463  cmp     ebx, 40h ; '@'
0x180064466  jb      loc_1800647F7
0x18006446c  add     rdi, rax
0x18006446f  mov     rax, cs:___NtQuerySystemInformationRNG
0x180064476  lea     r9, [rsp+4B0h+var_480]
0x18006447b  mov     r8d, 40h ; '@'
0x180064481  mov     rdx, rdi
0x180064484  lea     ecx, [r8-2Bh]
0x180064488  call    cs:__guard_dispatch_icall_fptr
0x18006448e  test    eax, eax
0x180064490  js      short loc_1800644AA
0x180064492  mov     ecx, [rsp+4B0h+var_480]
0x180064496  add     ecx, 8
0x180064499  and     ecx, esi
0x18006449b  cmp     ecx, ebx
0x18006449d  ja      loc_18006415A
0x1800644a3  mov     eax, ecx
0x1800644a5  add     rdi, rax
0x1800644a8  sub     ebx, ecx
0x1800644aa  mov     r8d, 178h
0x1800644b0  cmp     ebx, r8d
0x1800644b3  jb      loc_1800647F7
0x1800644b9  mov     rax, cs:___NtQuerySystemInformationRNG
0x1800644c0  lea     r9, [rsp+4B0h+var_480]
0x1800644c5  mov     rdx, rdi
0x1800644c8  mov     ecx, 2
0x1800644cd  call    cs:__guard_dispatch_icall_fptr
0x1800644d3  test    eax, eax
0x1800644d5  js      short loc_1800644F6
0x1800644d7  mov     eax, [rsp+4B0h+var_480]
  ... truncated ...
```
