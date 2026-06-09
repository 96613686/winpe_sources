# DpspDeleteOldDirectories

- ea: `0x180015b84`
- end: `0x1800161f9`
- name: `DpspDeleteOldDirectories`
- size: `1653`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180016200`

## callees

- `0x1800069b0`
- `0x180007e90`
- `0x1800082a8`
- `0x180008328`
- `0x1800083a8`
- `0x180009044`
- `0x180009090`
- `0x180009fb0`
- `0x180009ff0`
- `0x18000a856`
- `0x18000c93c`
- `0x18000f3d0`
- `0x18001585c`
- `0x180015918`
- `0x180015b84`
- `0x180018b49`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180015fed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180015fed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180016010`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001606b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180016010`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001606b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800161b4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800161b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180015f0c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180015f0c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180015f1b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180015f1b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800160de`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180016109`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800160de`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180016109`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180015d36`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180015e87`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180015d36`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180015e87`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800160ca`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800160f3`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800160ca`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800160f3`

## string_xrefs

- `0x180015c1e`: `DpspDeleteOldDirectories`
- `0x180015d48`: `DpspDeleteOldDirectories`

## pseudocode

```c
__int64 DpspDeleteOldDirectories()
{
  int Args; // eax
  unsigned int v1; // ebx
  int inited; // eax
  __int64 v3; // r12
  __int64 v4; // rsi
  size_t v5; // r8
  __int64 v6; // r15
  __int64 v7; // r13
  HANDLE FirstFileW; // rax
  void *v9; // r12
  int v10; // edx
  int v11; // edx
  __int64 v12; // rax
  int v13; // r8d
  int v14; // eax
  char *v15; // rax
  void *v16; // r13
  int v17; // edx
  int v18; // edx
  __int64 dwHighDateTime; // r12
  __int64 dwLowDateTime; // r13
  int InstanceDirectorySize; // eax
  unsigned __int64 v22; // r12
  int v23; // eax
  int v24; // r8d
  int v25; // eax
  int v26; // eax
  HANDLE v28; // [rsp+30h] [rbp-D0h]
  int v29; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v30; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE v33; // [rsp+58h] [rbp-A8h]
  __int128 v34; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v35; // [rsp+70h] [rbp-90h] BYREF
  __int64 v36; // [rsp+80h] [rbp-80h]
  __int64 v37; // [rsp+88h] [rbp-78h]
  struct _GUID v38; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID v39; // [rsp+A0h] [rbp-60h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Destination[264]; // [rsp+300h] [rbp+200h] BYREF
  _WORD v42[264]; // [rsp+510h] [rbp+410h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v32 = 0;
  v30 = 0;
  v39 = 0;
  v29 = 0;
  v38 = 0;
  v34 = 0;
  v35 = 0;
  _InterlockedIncrement(&g_DataRetentionCount);
  Args = DpspInitDirectoryTable(&v34, 30, 0);
  v1 = Args;
  if ( Args < 0 )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
      (int)L"DpspDeleteOldDirectories",
      671,
      (int)L"Error = %d",
      Args);
    goto LABEL_71;
  }
  inited = DpspInitDirectoryTable(&v35, 31, 1);
  v1 = inited;
  if ( inited < 0 )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
      (int)L"DpspDeleteOldDirectories",
      674,
      (int)L"Error = %d",
      inited);
    goto LABEL_71;
  }
  v3 = -1;
  v4 = _InterlockedExchange64(&g_DirSizeLimit, g_DirSizeLimit);
  do
    ++v3;
  while ( *((_WORD *)g_WdiDir + v3) );
  if ( (unsigned __int64)(v3 + 4) >= 0x104 )
  {
    v1 = -2147024362;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
      (int)L"DpspDeleteOldDirectories",
      687,
      (int)L"Error = %d",
      22);
    goto LABEL_71;
  }
  if ( memcpy_s(Destination, 0x208u, g_WdiDir, 2 * v3) )
  {
    v1 = -2147024362;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
      (int)L"DpspDeleteOldDirectories",
      693,
      (int)L"Error = %d",
      22);
    goto LABEL_71;
  }
  v5 = 2 * v3 + 4;
  *(_DWORD *)&Destination[v3] = 2752604;
  if ( v5 >= 0x208 )
    _report_rangecheckfailure();
  *(WCHAR *)((char *)Destination + v5) = 0;
  v6 = 0;
  v7 = v4 / 2;
  v37 = v4 / 2;
  memcpy_0(v42, Destination, v5);
  FirstFileW = FindFirstFileW(Destination, &FindFileData);
  v33 = FirstFileW;
  if ( FirstFileW )
  {
    v36 = v3 + 1;
    if ( FirstFileW != (HANDLE)-1LL )
    {
      v9 = FirstFileW;
      while ( 1 )
      {
        v10 = FindFileData.cFileName[0] - 46;
        if ( FindFileData.cFileName[0] == 46 )
          v10 = FindFileData.cFileName[1];
        if ( v10 )
        {
          v11 = FindFileData.cFileName[0] - 46;
          if ( FindFileData.cFileName[0] == 46 )
          {
            v11 = FindFileData.cFileName[1] - 46;
            if ( FindFileData.cFileName[1] == 46 )
              v11 = FindFileData.cFileName[2];
          }
          if ( v11 )
            break;
        }
LABEL_60:
        if ( !FindNextFileW(v9, &FindFileData) )
        {
          FindClose(v9);
          v7 = v37;
          goto LABEL_62;
        }
      }
      if ( (int)WdipStringToGuid(FindFileData.cFileName, &v39) < 0 )
      {
LABEL_23:
        v1 = 0;
        goto LABEL_60;
      }
      v12 = -1;
      do
        ++v12;
      while ( FindFileData.cFileName[v12] );
      if ( (unsigned __int64)(v12 + 1 + v36) > 0x104 )
      {
        v13 = 733;
LABEL_28:
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
          (int)L"DpspDeleteOldDirectories",
          v13,
          (int)L"Error = %d",
          22);
        goto LABEL_23;
      }
      if ( memcpy_s(&v42[v36], 260 - v36, FindFileData.cFileName, v12 + 1) )
      {
        v13 = 739;
        goto LABEL_28;
      }
      v14 = StringCchPrintfW(Destination, 0x104u, L"%s\\*", v42);
      v1 = v14;
      if ( v14 < 0 )
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
          (int)L"DpspDeleteOldDirectories",
          747,
          (int)L"Error = %d",
          v14);
        goto LABEL_23;
      }
      v15 = (char *)FindFirstFileW(Destination, &FindFileData);
      v28 = v15;
      if ( (unsigned __int64)(v15 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        goto LABEL_60;
      v16 = v15;
      while ( 1 )
      {
        v17 = FindFileData.cFileName[0] - 46;
        if ( FindFileData.cFileName[0] == 46 )
          v17 = FindFileData.cFileName[1];
        if ( !v17 )
          goto LABEL_58;
        v18 = FindFileData.cFileName[0] - 46;
        if ( FindFileData.cFileName[0] == 46 )
        {
          v18 = FindFileData.cFileName[1] - 46;
          if ( FindFileData.cFileName[1] == 46 )
            v18 = FindFileData.cFileName[2];
        }
        if ( !v18 )
          goto LABEL_58;
        v1 = 0;
        if ( (int)WdipStringToGuid(FindFileData.cFileName, &v38) < 0 )
          goto LABEL_58;
        SystemTimeAsFileTime = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        if ( CompareFileTime(&FindFileData.ftLastWriteTime, &SystemTimeAsFileTime) <= 0 )
          break;
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
          (int)L"DpspGetFileAge",
          581,
          (int)L"Error = %d",
          5);
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
          (int)L"DpspDeleteOldDirectories",
          773,
          (int)L"Error = %d",
          5);
LABEL_58:
        if ( !FindNextFileW(v16, &FindFileData) )
        {
          FindClose(v16);
          v9 = v33;
          goto LABEL_60;
        }
      }
      dwHighDateTime = FindFileData.ftLastWriteTime.dwHighDateTime;
      dwLowDateTime = FindFileData.ftLastWriteTime.dwLowDateTime;
      InstanceDirectorySize = DpspGetInstanceDirectorySize(&v39, &v38, &v32);
      v1 = InstanceDirectorySize;
      if ( InstanceDirectorySize < 0 )
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
          (int)L"DpspDeleteOldDirectories",
          779,
          (int)L"Error = %d",
          InstanceDirectorySize);
        v1 = 0;
LABEL_57:
        v16 = v28;
        goto LABEL_58;
      }
      v22 = (SystemTimeAsFileTime.dwLowDateTime
           + ((unsigned __int64)SystemTimeAsFileTime.dwHighDateTime << 32)
           - (dwHighDateTime << 32)
           - dwLowDateTime)
          / 0x989680
          / 0x15180;
      AcquireSRWLockShared(&g_SRWInstanceList);
      if ( DpspGetInstanceFromId(&v38, &v29) )
      {
        ReleaseSRWLockShared(&g_SRWInstanceList);
        v6 += v32;
        if ( v29 != 2 )
          goto LABEL_57;
        v23 = DpspAddDirectoryToTable((unsigned int)&v35, (unsigned int)&v39, (unsigned int)&v38, v22, v32);
        v1 = v23;
        if ( v23 >= 0 )
          goto LABEL_57;
        v24 = 827;
      }
      else
      {
        ReleaseSRWLockShared(&g_SRWInstanceList);
        if ( (unsigned int)v22 < 0x1E )
        {
          v6 += v32;
          v23 = DpspAddDirectoryToTable((unsigned int)&v34, (unsigned int)&v39, (unsigned int)&v38, v22, v32);
          v1 = v23;
          if ( v23 >= 0 )
            goto LABEL_57;
          v24 = 875;
        }
        else
        {
          v23 = DpspDeleteInstanceDirectory(&v39, &v38);
          v1 = v23;
          if ( v23 >= 0 )
            goto LABEL_57;
          v24 = 858;
        }
      }
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
        (int)L"DpspDeleteOldDirectories",
        v24,
        (int)L"Error = %d",
        v23);
      v1 = 0;
      goto LABEL_57;
    }
  }
LABEL_62:
  if ( v6 > v7 )
  {
    v25 = DpspTrimDirectoriesBelowLimit((struct __DIRTABLE *)&v34, v6 - v7, &v30);
    v1 = v25;
    if ( v25 < 0 )
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
        (int)L"DpspDeleteOldDirectories",
        898,
        (int)L"Error = %d",
        v25);
      v1 = 0;
    }
    v6 -= v30;
  }
  v30 = 0;
  if ( v6 > v7 )
  {
    v26 = DpspTrimDirectoriesBelowLimit((struct __DIRTABLE *)&v35, v6 - v7, &v30);
    v1 = v26;
    if ( v26 < 0 )
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
        (int)L"DpspDeleteOldDirectories",
        917,
        (int)L"Error = %d",
        v26);
      v1 = 0;
    }
    v6 -= v30;
  }
  _InterlockedExchange64(&g_CurrentDirSize, v6);
LABEL_71:
  ResetEvent(g_hDataRetentionControl);
  DpspFreeDirectoryTable(&v34);
  DpspFreeDirectoryTable(&v35);
  return v1;
}

```

## disassembly

```asm
0x180015b84  push    rbp
0x180015b86  push    rbx
0x180015b87  push    rsi
0x180015b88  push    rdi
0x180015b89  push    r12
0x180015b8b  push    r13
0x180015b8d  push    r14
0x180015b8f  push    r15
0x180015b91  lea     rbp, [rsp-638h]
0x180015b99  sub     rsp, 738h
0x180015ba0  mov     rax, cs:__security_cookie
0x180015ba7  xor     rax, rsp
0x180015baa  mov     [rbp+670h+var_50], rax
0x180015bb1  xor     edx, edx; Val
0x180015bb3  lea     rcx, [rbp+670h+FindFileData]; void *
0x180015bb7  mov     r8d, 250h; Size
0x180015bbd  call    memset_0
0x180015bc2  xor     r14d, r14d
0x180015bc5  xorps   xmm0, xmm0
0x180015bc8  xorps   xmm1, xmm1
0x180015bcb  mov     [rsp+770h+var_720], r14
0x180015bd0  mov     [rsp+770h+var_730], r14
0x180015bd5  movups  xmmword ptr [rbp+670h+var_6D0.Data1], xmm0
0x180015bd9  mov     [rsp+770h+var_738], r14d
0x180015bde  movups  xmmword ptr [rbp+670h+var_6E0.Data1], xmm1
0x180015be2  movups  [rsp+770h+var_710], xmm0
0x180015be7  movups  [rsp+770h+var_700], xmm1
0x180015bec  lock inc cs:g_DataRetentionCount
0x180015bf3  xor     r8d, r8d
0x180015bf6  lea     edx, [r14+1Eh]
0x180015bfa  lea     rcx, [rsp+770h+var_710]
0x180015bff  call    DpspInitDirectoryTable
0x180015c04  mov     ebx, eax
0x180015c06  test    eax, eax
0x180015c08  jns     short loc_180015C36
0x180015c0a  movzx   ecx, ax
0x180015c0d  mov     r8d, 29Fh; int
0x180015c13  mov     dword ptr [rsp+770h+Args], ecx; Args
0x180015c17  lea     r9, aErrorD; "Error = %d"
0x180015c1e  lea     rdx, aDpspdeleteoldd; "DpspDeleteOldDirectories"
0x180015c25  lea     rcx, aClientcoreBase_1; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180015c2c  call    WdipTraceError
0x180015c31  jmp     loc_1800161AD
0x180015c36  mov     edx, 1Fh
0x180015c3b  lea     rcx, [rsp+770h+var_700]
0x180015c40  lea     r8d, [rdx-1Eh]
0x180015c44  call    DpspInitDirectoryTable
0x180015c49  mov     ebx, eax
0x180015c4b  test    eax, eax
0x180015c4d  jns     short loc_180015C5E
0x180015c4f  movzx   eax, ax
0x180015c52  mov     r8d, 2A2h
0x180015c58  mov     dword ptr [rsp+770h+Args], eax
0x180015c5c  jmp     short loc_180015C17
0x180015c5e  mov     rsi, cs:g_DirSizeLimit
0x180015c65  or      r12, 0FFFFFFFFFFFFFFFFh
0x180015c69  xchg    rsi, cs:g_DirSizeLimit
0x180015c70  mov     r8, cs:g_WdiDir; Source
0x180015c77  inc     r12
0x180015c7a  cmp     [r8+r12*2], r14w
0x180015c7f  jnz     short loc_180015C77
0x180015c81  lea     rax, [r12+4]
0x180015c86  cmp     rax, 104h
0x180015c8c  jb      short loc_180015CA6
0x180015c8e  mov     ebx, 80070216h
0x180015c93  mov     dword ptr [rsp+770h+Args], 216h
0x180015c9b  mov     r8d, 2AFh
0x180015ca1  jmp     loc_180015C17
0x180015ca6  lea     rdi, [r12+r12]
0x180015caa  mov     r15d, 208h
0x180015cb0  mov     r9, rdi; SourceSize
0x180015cb3  lea     rcx, [rbp+670h+Destination]; Destination
0x180015cba  mov     edx, r15d; DestinationSize
0x180015cbd  call    memcpy_s
0x180015cc2  test    eax, eax
0x180015cc4  jz      short loc_180015CDE
0x180015cc6  mov     ebx, 80070216h
0x180015ccb  mov     dword ptr [rsp+770h+Args], 216h
0x180015cd3  mov     r8d, 2B5h
0x180015cd9  jmp     loc_180015C17
0x180015cde  lea     r8, ds:4[r12*2]; Size
0x180015ce6  mov     dword ptr [rbp+rdi+670h+Destination], 2A005Ch
0x180015cf1  cmp     r8, r15
0x180015cf4  jnb     loc_1800161F3
0x180015cfa  mov     rax, rsi
0x180015cfd  mov     [rbp+r8+670h+Destination], r14w
0x180015d06  cqo
0x180015d08  lea     rcx, [rbp+670h+var_260]; void *
0x180015d0f  sub     rax, rdx
0x180015d12  mov     r15, r14
0x180015d15  sar     rax, 1
0x180015d18  lea     rdx, [rbp+670h+Destination]; Src
0x180015d1f  mov     r13, rax
0x180015d22  mov     [rbp+670h+var_6E8], rax
0x180015d26  call    memcpy_0
0x180015d2b  lea     rdx, [rbp+670h+FindFileData]; lpFindFileData
0x180015d2f  lea     rcx, [rbp+670h+Destination]; lpFileName
0x180015d36  call    cs:__imp_FindFirstFileW
0x180015d3c  mov     [rsp+770h+var_718], rax
0x180015d41  lea     rdi, aErrorD; "Error = %d"
0x180015d48  lea     r14, aDpspdeleteoldd; "DpspDeleteOldDirectories"
0x180015d4f  lea     rsi, aClientcoreBase_1; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180015d56  test    rax, rax
0x180015d59  jz      loc_180016113
0x180015d5f  inc     r12
0x180015d62  mov     [rbp+670h+var_6F0], r12
0x180015d66  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015d6a  jz      loc_180016113
0x180015d70  mov     ecx, 2Eh ; '.'
0x180015d75  mov     r12, rax
0x180015d78  xor     r13d, r13d
0x180015d7b  movzx   edx, [rbp+670h+FindFileData.cFileName]
0x180015d7f  movzx   eax, cx
0x180015d82  sub     edx, eax
0x180015d84  jnz     short loc_180015D95
0x180015d86  movzx   edx, [rbp+670h+FindFileData.cFileName+2]
0x180015d8a  movzx   ecx, r13w
0x180015d8e  sub     edx, ecx
0x180015d90  mov     ecx, 2Eh ; '.'
0x180015d95  test    edx, edx
0x180015d97  jz      loc_1800160EC
0x180015d9d  movzx   edx, [rbp+670h+FindFileData.cFileName]
0x180015da1  movzx   eax, cx
0x180015da4  sub     edx, eax
0x180015da6  jnz     short loc_180015DBD
0x180015da8  movzx   edx, [rbp+670h+FindFileData.cFileName+2]
0x180015dac  movzx   eax, cx
0x180015daf  sub     edx, eax
0x180015db1  jnz     short loc_180015DBD
0x180015db3  movzx   edx, [rbp+670h+FindFileData.cFileName+4]
0x180015db7  movzx   ecx, r13w
0x180015dbb  sub     edx, ecx
0x180015dbd  test    edx, edx
0x180015dbf  jz      loc_1800160EC
0x180015dc5  lea     rdx, [rbp+670h+var_6D0]
0x180015dc9  lea     rcx, [rbp+670h+FindFileData.cFileName]
0x180015dcd  call    WdipStringToGuid
0x180015dd2  test    eax, eax
0x180015dd4  jns     short loc_180015DDE
0x180015dd6  mov     ebx, r13d
0x180015dd9  jmp     loc_1800160EC
0x180015dde  lea     rcx, [rbp+670h+FindFileData.cFileName]
0x180015de2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015de6  inc     rax
0x180015de9  cmp     [rcx+rax*2], r13w
0x180015dee  jnz     short loc_180015DE6
0x180015df0  mov     rcx, [rbp+670h+var_6F0]
0x180015df4  lea     r9, [rax+1]; SourceSize
0x180015df8  mov     ebx, 104h
0x180015dfd  lea     rax, [r9+rcx]
0x180015e01  cmp     rax, rbx
0x180015e04  jbe     short loc_180015E24
0x180015e06  mov     r8d, 2DDh; int
0x180015e0c  mov     dword ptr [rsp+770h+Args], 216h; Args
0x180015e14  mov     r9, rdi; int
0x180015e17  mov     rdx, r14; int
0x180015e1a  mov     rcx, rsi; int
0x180015e1d  call    WdipTraceError
0x180015e22  jmp     short loc_180015DD6
0x180015e24  lea     rax, [rbp+670h+var_260]
0x180015e2b  mov     rdx, rbx
0x180015e2e  sub     rdx, rcx; DestinationSize
0x180015e31  lea     r8, [rbp+670h+FindFileData.cFileName]; Source
0x180015e35  lea     rcx, [rax+rcx*2]; Destination
0x180015e39  call    memcpy_s
0x180015e3e  test    eax, eax
0x180015e40  jz      short loc_180015E4A
0x180015e42  mov     r8d, 2E3h
0x180015e48  jmp     short loc_180015E0C
0x180015e4a  lea     r9, [rbp+670h+var_260]
0x180015e51  mov     rdx, rbx; unsigned __int64
0x180015e54  lea     r8, aS; "%s\\*"
0x180015e5b  lea     rcx, [rbp+670h+Destination]; unsigned __int16 *
0x180015e62  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015e67  mov     ebx, eax
0x180015e69  test    eax, eax
0x180015e6b  jns     short loc_180015E7C
0x180015e6d  movzx   eax, ax
0x180015e70  mov     r8d, 2EBh
0x180015e76  mov     dword ptr [rsp+770h+Args], eax
0x180015e7a  jmp     short loc_180015E14
0x180015e7c  lea     rdx, [rbp+670h+FindFileData]; lpFindFileData
0x180015e80  lea     rcx, [rbp+670h+Destination]; lpFileName
0x180015e87  call    cs:__imp_FindFirstFileW
0x180015e8d  mov     [rsp+770h+var_740], rax
0x180015e92  lea     rcx, [rax-1]
0x180015e96  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180015e9a  ja      loc_1800160EC
0x180015ea0  mov     r13, rax
0x180015ea3  xor     r8d, r8d
0x180015ea6  movzx   edx, [rbp+670h+FindFileData.cFileName]
0x180015eaa  mov     r9d, 2Eh ; '.'
0x180015eb0  sub     edx, r9d
0x180015eb3  jnz     short loc_180015EBF
0x180015eb5  movzx   edx, [rbp+670h+FindFileData.cFileName+2]
0x180015eb9  movzx   ecx, r8w
0x180015ebd  sub     edx, ecx
0x180015ebf  test    edx, edx
0x180015ec1  jz      loc_1800160C3
0x180015ec7  movzx   edx, [rbp+670h+FindFileData.cFileName]
0x180015ecb  sub     edx, r9d
0x180015ece  jnz     short loc_180015EE3
0x180015ed0  movzx   edx, [rbp+670h+FindFileData.cFileName+2]
0x180015ed4  sub     edx, r9d
0x180015ed7  jnz     short loc_180015EE3
0x180015ed9  movzx   edx, [rbp+670h+FindFileData.cFileName+4]
0x180015edd  movzx   ecx, r8w
0x180015ee1  sub     edx, ecx
0x180015ee3  test    edx, edx
0x180015ee5  jz      loc_1800160C3
0x180015eeb  lea     rdx, [rbp+670h+var_6E0]
0x180015eef  lea     rcx, [rbp+670h+FindFileData.cFileName]
0x180015ef3  call    WdipStringToGuid
0x180015ef8  xor     ebx, ebx
0x180015efa  test    eax, eax
0x180015efc  js      loc_1800160C3
0x180015f02  lea     rcx, [rsp+770h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180015f07  mov     qword ptr [rsp+770h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x180015f0c  call    cs:__imp_GetSystemTimeAsFileTime
0x180015f12  lea     rdx, [rsp+770h+SystemTimeAsFileTime]; lpFileTime2
0x180015f17  lea     rcx, [rbp+670h+FindFileData.ftLastWriteTime]; lpFileTime1
0x180015f1b  call    cs:__imp_CompareFileTime
0x180015f21  test    eax, eax
0x180015f23  jle     short loc_180015F66
0x180015f25  mov     r12d, 4005h
0x180015f2b  lea     rdx, aDpspgetfileage; "DpspGetFileAge"
0x180015f32  mov     r9, rdi; int
0x180015f35  mov     dword ptr [rsp+770h+Args], r12d; Args
0x180015f3a  mov     r8d, 245h; int
0x180015f40  mov     rcx, rsi; int
0x180015f43  call    WdipTraceError
0x180015f48  mov     r9, rdi; int
0x180015f4b  mov     dword ptr [rsp+770h+Args], r12d; Args
0x180015f50  mov     r8d, 305h; int
0x180015f56  mov     rdx, r14; int
0x180015f59  mov     rcx, rsi; int
0x180015f5c  call    WdipTraceError
0x180015f61  jmp     loc_1800160C3
0x180015f66  mov     r12d, [rbp+670h+FindFileData.ftLastWriteTime.dwHighDateTime]
0x180015f6a  mov     r13d, [rbp+670h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x180015f6e  lea     r8, [rsp+770h+var_720]; __int64 *
0x180015f73  lea     rdx, [rbp+670h+var_6E0]; struct _GUID *
0x180015f77  lea     rcx, [rbp+670h+var_6D0]; struct _GUID *
0x180015f7b  call    ?DpspGetInstanceDirectorySize@@YAJPEBU_GUID@@0PEA_J@Z; DpspGetInstanceDirectorySize(_GUID const *,_GUID const *,__int64 *)
0x180015f80  mov     ebx, eax
0x180015f82  test    eax, eax
0x180015f84  jns     short loc_180015FA8
0x180015f86  movzx   eax, ax
0x180015f89  mov     r9, rdi; int
0x180015f8c  mov     r8d, 30Bh; int
0x180015f92  mov     dword ptr [rsp+770h+Args], eax; Args
0x180015f96  mov     rdx, r14; int
0x180015f99  mov     rcx, rsi; int
0x180015f9c  call    WdipTraceError
0x180015fa1  xor     ebx, ebx
0x180015fa3  jmp     loc_1800160BE
0x180015fa8  mov     eax, [rsp+770h+SystemTimeAsFileTime.dwLowDateTime]
0x180015fac  mov     ecx, [rsp+770h+SystemTimeAsFileTime.dwHighDateTime]
0x180015fb0  shl     rcx, 20h
0x180015fb4  shl     r12, 20h
0x180015fb8  sub     rcx, r12
0x180015fbb  sub     rcx, r13
0x180015fbe  add     rcx, rax
0x180015fc1  mov     rax, 0D6BF94D5E57A42BDh
0x180015fcb  mul     rcx
0x180015fce  mov     rax, 0C22E450672894AB7h
0x180015fd8  lea     rcx, g_SRWInstanceList; SRWLock
0x180015fdf  shr     rdx, 17h
0x180015fe3  mul     rdx
0x180015fe6  mov     r12, rdx
0x180015fe9  shr     r12, 10h
0x180015fed  call    cs:__imp_AcquireSRWLockShared
0x180015ff3  lea     rdx, [rsp+770h+var_738]
0x180015ff8  lea     rcx, [rbp+670h+var_6E0]
0x180015ffc  call    DpspGetInstanceFromId
0x180016001  xor     r13d, r13d
0x180016004  lea     rcx, g_SRWInstanceList; SRWLock
0x18001600b  test    rax, rax
0x18001600e  jnz     short loc_18001606B
0x180016010  call    cs:__imp_ReleaseSRWLockShared
0x180016016  cmp     r12d, 1Eh
0x18001601a  jb      short loc_18001603B
0x18001601c  lea     rdx, [rbp+670h+var_6E0]
0x180016020  lea     rcx, [rbp+670h+var_6D0]
0x180016024  call    DpspDeleteInstanceDirectory
0x180016029  mov     ebx, eax
0x18001602b  test    eax, eax
0x18001602d  jns     loc_1800160BE
0x180016033  mov     r8d, 35Ah
0x180016039  jmp     short loc_1800160A6
0x18001603b  mov     rax, [rsp+770h+var_720]
0x180016040  lea     r8, [rbp+670h+var_6E0]
0x180016044  mov     r9d, r12d
0x180016047  mov     qword ptr [rsp+770h+Args], rax
0x18001604c  lea     rdx, [rbp+670h+var_6D0]
0x180016050  add     r15, rax
0x180016053  lea     rcx, [rsp+770h+var_710]
0x180016058  call    DpspAddDirectoryToTable
0x18001605d  mov     ebx, eax
0x18001605f  test    eax, eax
  ... truncated ...
```
