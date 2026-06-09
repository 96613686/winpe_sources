# StorageReserveHelper::Internal::RecursiveScanDirectory(ushort const *,_STORAGE_RESERVE_ID,StorageReserveHelper::Internal::_STORAGE_RESERVE_HARDLINK_STATS *)

- ea: `0x18002d6a0`
- end: `0x18002ddfc`
- name: `?RecursiveScanDirectory@Internal@StorageReserveHelper@@YAJPEBGW4_STORAGE_RESERVE_ID@@PEAU_STORAGE_RESERVE_HARDLINK_STATS@12@@Z`
- size: `1884`
- prototype: `__int64 __fastcall(StorageReserveHelper::Internal *this, const unsigned __int16 *, _DWORD *, struct StorageReserveHelper::Internal::_STORAGE_RESERVE_HARDLINK_STATS *)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18002a1fc`
- `0x18002d6a0`

## callees

- `0x180003870`
- `0x180003894`
- `0x180003c84`
- `0x180004164`
- `0x1800042f4`
- `0x1800044e0`
- `0x18000a0cc`
- `0x18000a0f4`
- `0x18002ce34`
- `0x18002d068`
- `0x18002d33c`
- `0x18002d5a4`
- `0x18002d6a0`
- `0x18002df1c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d76d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d76d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dbed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd1d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002db42`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002db42`
- `api-ms-win-core-file-l1-1-0!FindFirstFileNameW` at `0x18002dc8d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileNameW` at `0x18002dc8d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002d93f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002d93f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002d75f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002d75f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002dbd8`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18002dbd8`
- `api-ms-win-core-file-l1-1-0!FindNextFileNameW` at `0x18002dcee`
- `api-ms-win-core-file-l1-1-0!FindNextFileNameW` at `0x18002dcee`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002dc6e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002dd31`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002ddcd`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002dc6e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002dd31`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18002ddcd`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002d722`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002d73d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002d7d0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002d836`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002d851`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002d8b9`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002d98a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002d9e4`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002dc35`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002dc50`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002dd98`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002ddb3`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002d722`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002d73d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002d7d0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002d836`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002d851`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002d8b9`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002d98a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002d9e4`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002dc35`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002dc50`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002dd98`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18002ddb3`

## pseudocode

```c
__int64 __fastcall StorageReserveHelper::Internal::RecursiveScanDirectory(
        StorageReserveHelper::Internal *this,
        const unsigned __int16 *a2,
        _DWORD *a3,
        struct StorageReserveHelper::Internal::_STORAGE_RESERVE_HARDLINK_STATS *a4)
{
  unsigned int Dependencies; // ebx
  __int64 v7; // rdx
  DWORD FileAttributesW; // eax
  char v10; // r13
  signed int LastError; // eax
  struct _WIN32_FIND_DATAW *v12; // r14
  void *v13; // rbx
  int v14; // eax
  void **v15; // r8
  unsigned int v16; // edi
  int v17; // r13d
  int v18; // eax
  int (*v19)(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 **); // rdi
  const wchar_t *v20; // rdx
  int v21; // eax
  __int64 v22; // rdx
  HLOCAL v23; // r8
  char *v24; // r9
  HANDLE FirstFileW; // r12
  WCHAR *cFileName; // rsi
  int (*v27)(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int16 **); // rdi
  StorageReserveHelper::Internal *v28; // r10
  __int64 v29; // rcx
  int v30; // r9d
  char IsEnabled; // al
  unsigned int *v32; // r8
  StorageReserveHelper::Internal *v33; // rcx
  char FileLinkCnt; // al
  __int64 v35; // rdx
  const char *v36; // r9
  HANDLE FirstFileNameW; // rsi
  void **v38; // r8
  unsigned int v39; // edi
  signed int i; // ecx
  void **v41; // r8
  BOOL bIgnoreCase; // [rsp+20h] [rbp-60h]
  unsigned __int16 v43[2]; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int16 v44[2]; // [rsp+34h] [rbp-4Ch] BYREF
  __int64 v45; // [rsp+38h] [rbp-48h]
  HLOCAL hMem; // [rsp+40h] [rbp-40h] BYREF
  int cchCount2[2]; // [rsp+48h] [rbp-38h]
  __int64 v48; // [rsp+50h] [rbp-30h]
  HLOCAL v49; // [rsp+58h] [rbp-28h] BYREF
  __int64 v50; // [rsp+60h] [rbp-20h]
  __int64 v51; // [rsp+68h] [rbp-18h]
  DWORD StringLength; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v45 = -2;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  hMem = 0;
  *(_QWORD *)cchCount2 = 0;
  v48 = 0;
  *(_DWORD *)v43 = 0;
  if ( !this )
  {
    Dependencies = -2147024809;
    v7 = 299;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
      (const char *)Dependencies,
      bIgnoreCase);
LABEL_4:
    *(_QWORD *)cchCount2 = 0;
    v48 = 0;
    return Dependencies;
  }
  Dependencies = StorageReserveHelper::Internal::LoadDependencies(this);
  if ( (Dependencies & 0x80000000) != 0 )
  {
    v7 = 301;
    goto LABEL_3;
  }
  FileAttributesW = GetFileAttributesW((LPCWSTR)this);
  v10 = FileAttributesW;
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    Dependencies = LastError;
    if ( LastError > 0 )
      Dependencies = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_4;
  }
  v12 = (struct _WIN32_FIND_DATAW *)operator new[](0x250u);
  memset_0(v12, 0, sizeof(struct _WIN32_FIND_DATAW));
  v13 = 0;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::GetImpl'::`2'::impl) )
    v13 = operator new(0x208u);
  *(_QWORD *)cchCount2 = -1;
  v48 = -1;
  v14 = ((__int64 (__fastcall *)(StorageReserveHelper::Internal *, __int64, HLOCAL *))StorageReserveHelper::Internal::pfnPathAllocCanonicalize)(
          this,
          1,
          &hMem);
  v16 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
      (const char *)(unsigned int)v14,
      bIgnoreCase);
    if ( v13 )
      operator delete(v13);
LABEL_15:
    operator delete(v12);
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    *(_QWORD *)cchCount2 = 0;
    v48 = 0;
LABEL_18:
    if ( v49 )
      LocalFree(v49);
    return v16;
  }
  v17 = v10 & 0x10;
  if ( v17 )
  {
    v18 = StorageReserveHelper::Internal::SetAreaID(
            (StorageReserveHelper::Internal *)hMem,
            (const unsigned __int16 *)2,
            v15);
    v16 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x151,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
        (const char *)(unsigned int)v18,
        bIgnoreCase);
      if ( v13 )
        operator delete(v13);
      goto LABEL_15;
    }
  }
  v19 = StorageReserveHelper::Internal::pfnPathAllocCombine;
  if ( v49 )
  {
    LocalFree(v49);
    v49 = 0;
  }
  v50 = -1;
  v51 = -1;
  v20 = L"*";
  if ( !v17 )
    v20 = &qword_18003A1F8;
  v21 = ((__int64 (__fastcall *)(HLOCAL, const wchar_t *, __int64, HLOCAL *))v19)(hMem, v20, 1, &v49);
  v16 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x154,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
      (const char *)(unsigned int)v21,
      bIgnoreCase);
    if ( v13 )
      operator delete(v13);
    goto LABEL_15;
  }
  FirstFileW = FindFirstFileW((LPCWSTR)v49, v12);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    v16 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x157,
            (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
            v24);
    if ( v13 )
      operator delete(v13);
    operator delete(v12);
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    *(_QWORD *)cchCount2 = 0;
    v48 = 0;
    goto LABEL_18;
  }
  cFileName = v12->cFileName;
  do
  {
    if ( *cFileName == 46 && (!v12->cFileName[1] || v12->cFileName[1] == 46 && !v12->cFileName[2]) )
      continue;
    if ( !v17 )
      goto LABEL_100;
    v27 = StorageReserveHelper::Internal::pfnPathAllocCombine;
    if ( v49 )
    {
      LocalFree(v49);
      v49 = 0;
    }
    v50 = -1;
    v51 = -1;
    if ( ((int (__fastcall *)(HLOCAL, WCHAR *, __int64, HLOCAL *))v27)(hMem, cFileName, 1, &v49) < 0 )
      continue;
    v28 = (StorageReserveHelper::Internal *)v49;
    v29 = v50;
    if ( v50 == -1 )
    {
      if ( v49 )
      {
        v29 = -1;
        do
          ++v29;
        while ( *((_WORD *)v49 + v29) );
      }
      else
      {
        v29 = 0;
      }
      v50 = v29;
    }
    v23 = hMem;
    v22 = *(_QWORD *)cchCount2;
    if ( *(_QWORD *)cchCount2 == -1 )
    {
      if ( hMem )
      {
        v22 = -1;
        do
          ++v22;
        while ( *((_WORD *)hMem + v22) );
      }
      else
      {
        v22 = 0;
      }
      *(_QWORD *)cchCount2 = v22;
    }
    if ( v29 == v22 )
      goto LABEL_85;
    if ( v29 == -1 )
    {
      if ( v49 )
      {
        v29 = -1;
        do
          ++v29;
        while ( *((_WORD *)v49 + v29) );
        v50 = v29;
      }
      else
      {
        v50 = 0;
        v29 = 0;
      }
    }
    if ( v22 == -1 )
    {
      if ( hMem )
      {
        v22 = -1;
        do
          ++v22;
        while ( *((_WORD *)hMem + v22) );
      }
      else
      {
        v22 = 0;
      }
      *(_QWORD *)cchCount2 = v22;
    }
    if ( v29 == v22 + 1 )
    {
      if ( v29 == -1 )
      {
        if ( v49 )
        {
          v29 = -1;
          do
            ++v29;
          while ( *((_WORD *)v49 + v29) );
          v50 = v29;
        }
        else
        {
          v50 = 0;
          v29 = 0;
        }
      }
      if ( *((_WORD *)v49 + v29 - 1) == 92 )
      {
LABEL_85:
        if ( v22 == -1 )
        {
          if ( hMem )
          {
            v22 = -1;
            do
              ++v22;
            while ( *((_WORD *)hMem + v22) );
          }
          else
          {
            v22 = 0;
          }
          *(_QWORD *)cchCount2 = v22;
        }
        v30 = v22;
        if ( v22 == -1 )
        {
          if ( hMem )
          {
            v22 = -1;
            do
              ++v22;
            while ( *((_WORD *)hMem + v22) );
          }
          else
          {
            v22 = 0;
          }
          *(_QWORD *)cchCount2 = v22;
        }
        if ( CompareStringOrdinal((LPCWCH)v49, v22, (LPCWCH)hMem, v30, 0) == 2 )
          continue;
LABEL_100:
        v28 = (StorageReserveHelper::Internal *)v49;
      }
    }
    if ( (v12->dwFileAttributes & 0x10) != 0 )
    {
      if ( (v12->dwFileAttributes & 0x400) != 0 )
      {
        if ( !(unsigned __int8)((__int64 (__fastcall *)(_QWORD, __int64, HLOCAL))StorageReserveHelper::Internal::pfnRtlIsNonEmptyDirectoryReparsePointAllowed)(
                                 v12->dwReserved0,
                                 v22,
                                 v23) )
          continue;
        v28 = (StorageReserveHelper::Internal *)v49;
      }
      StorageReserveHelper::Internal::RecursiveScanDirectory(
        v28,
        (const unsigned __int16 *)2,
        (enum _STORAGE_RESERVE_ID)a3,
        (struct StorageReserveHelper::Internal::_STORAGE_RESERVE_HARDLINK_STATS *)v24);
    }
    else
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::GetImpl'::`2'::impl);
      v33 = (StorageReserveHelper::Internal *)v49;
      if ( !IsEnabled )
        goto LABEL_110;
      StringLength = 0;
      FileLinkCnt = StorageReserveHelper::Internal::GetFileLinkCnt((const WCHAR *)v49, v43, v32);
      v33 = (StorageReserveHelper::Internal *)v49;
      if ( !FileLinkCnt )
      {
        ++a3[2];
        v35 = 0;
        goto LABEL_111;
      }
      if ( *(_DWORD *)v43 == 1 )
      {
        ++a3[1];
LABEL_110:
        v35 = 2;
LABEL_111:
        StorageReserveHelper::Internal::SetAreaID(v33, (const unsigned __int16 *)v35, (void **)v32);
        continue;
      }
      ++a3[3];
      StringLength = 260;
      FirstFileNameW = FindFirstFileNameW((LPCWSTR)v33, 0, &StringLength, (PWSTR)v13);
      if ( FirstFileNameW == (HANDLE)-1LL )
      {
        ++a3[4];
        StorageReserveHelper::Internal::SetAreaID((StorageReserveHelper::Internal *)v49, 0, v38);
        cFileName = v12->cFileName;
      }
      else
      {
        *(_DWORD *)v44 = 0;
        v39 = 2;
        while ( 1 )
        {
          for ( i = StringLength; i > 0 && *((_WORD *)v13 + (unsigned int)i - 1) != 92; --i )
            ;
          *((_WORD *)v13 + i) = 0;
          if ( (int)StorageReserveHelper::Internal::QueryAreaID(
                      (StorageReserveHelper::Internal *)v13,
                      v44,
                      (enum _STORAGE_RESERVE_ID *)v38) < 0 )
            break;
          if ( *(_DWORD *)v44 != 2 )
          {
            ++a3[5];
            goto LABEL_134;
          }
          StringLength = 260;
          if ( !FindNextFileNameW(FirstFileNameW, &StringLength, (PWSTR)v13) )
            goto LABEL_135;
        }
        ++a3[4];
LABEL_134:
        v39 = 0;
LABEL_135:
        if ( GetLastError() != 38 && GetLastError() && GetLastError() != 18 )
        {
          ++a3[4];
          v39 = 0;
        }
        FindClose(FirstFileNameW);
        if ( v39 )
          ++a3[6];
        StorageReserveHelper::Internal::SetAreaID(
          (StorageReserveHelper::Internal *)v49,
          (const unsigned __int16 *)v39,
          v41);
        cFileName = v12->cFileName;
      }
    }
  }
  while ( FindNextFileW(FirstFileW, v12) );
  if ( GetLastError() == 18 )
  {
    if ( v13 )
      operator delete(v13);
    operator delete(v12);
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    *(_QWORD *)cchCount2 = 0;
    v48 = 0;
    if ( v49 )
    {
      LocalFree(v49);
      v49 = 0;
    }
    v50 = 0;
    v51 = 0;
    if ( FirstFileW )
      FindClose(FirstFileW);
    return 0;
  }
  else
  {
    v16 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x216,
            (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.cpp",
            v36);
    if ( v13 )
      operator delete(v13);
    operator delete(v12);
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    *(_QWORD *)cchCount2 = 0;
    v48 = 0;
    if ( v49 )
    {
      LocalFree(v49);
      v49 = 0;
    }
    v50 = 0;
    v51 = 0;
    if ( FirstFileW )
      FindClose(FirstFileW);
    return v16;
  }
}

```

## disassembly

```asm
0x18002d6a0  mov     rax, rsp
0x18002d6a3  push    rbp
0x18002d6a4  push    rsi
0x18002d6a5  push    rdi
0x18002d6a6  push    r12
0x18002d6a8  push    r13
0x18002d6aa  push    r14
0x18002d6ac  push    r15
0x18002d6ae  mov     rbp, rsp
0x18002d6b1  sub     rsp, 80h
0x18002d6b8  mov     [rbp+var_48], 0FFFFFFFFFFFFFFFEh
0x18002d6c0  mov     [rax+10h], rbx
0x18002d6c4  mov     rax, cs:__security_cookie
0x18002d6cb  xor     rax, rsp
0x18002d6ce  mov     [rbp+var_8], rax
0x18002d6d2  mov     r15, r8
0x18002d6d5  mov     rdi, rcx
0x18002d6d8  xor     r12d, r12d
0x18002d6db  mov     [rbp+var_28], r12
0x18002d6df  mov     [rbp+var_20], r12
0x18002d6e3  mov     [rbp+var_18], r12
0x18002d6e7  mov     [rbp+hMem], r12
0x18002d6eb  mov     qword ptr [rbp+cchCount2], r12
0x18002d6ef  mov     [rbp+var_30], r12
0x18002d6f3  mov     dword ptr [rbp+var_50], r12d
0x18002d6f7  test    rcx, rcx
0x18002d6fa  jnz     short loc_18002D74A
0x18002d6fc  mov     ebx, 80070057h
0x18002d701  mov     edx, 12Bh; void *
0x18002d706  mov     r9d, ebx; char *
0x18002d709  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002d710  mov     rcx, [rbp+38h]; this
0x18002d714  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d719  mov     rcx, [rbp+hMem]; hMem
0x18002d71d  test    rcx, rcx
0x18002d720  jz      short loc_18002D72C
0x18002d722  call    cs:__imp_LocalFree
0x18002d728  mov     [rbp+hMem], r12
0x18002d72c  mov     qword ptr [rbp+cchCount2], r12
0x18002d730  mov     [rbp+var_30], r12
0x18002d734  mov     rcx, [rbp+var_28]; hMem
0x18002d738  test    rcx, rcx
0x18002d73b  jz      short loc_18002D743
0x18002d73d  call    cs:__imp_LocalFree
0x18002d743  mov     eax, ebx
0x18002d745  jmp     loc_18002DDD5
0x18002d74a  call    ?LoadDependencies@Internal@StorageReserveHelper@@YAJXZ; StorageReserveHelper::Internal::LoadDependencies(void)
0x18002d74f  mov     ebx, eax
0x18002d751  test    eax, eax
0x18002d753  jns     short loc_18002D75C
0x18002d755  mov     edx, 12Dh
0x18002d75a  jmp     short loc_18002D706
0x18002d75c  mov     rcx, rdi; lpFileName
0x18002d75f  call    cs:__imp_GetFileAttributesW
0x18002d765  mov     r13d, eax
0x18002d768  cmp     eax, 0FFFFFFFFh
0x18002d76b  jnz     short loc_18002D784
0x18002d76d  call    cs:__imp_GetLastError
0x18002d773  mov     ebx, eax
0x18002d775  test    eax, eax
0x18002d777  jle     short loc_18002D719
0x18002d779  movzx   ebx, ax
0x18002d77c  or      ebx, 80070000h
0x18002d782  jmp     short loc_18002D719
0x18002d784  mov     ebx, 250h
0x18002d789  mov     ecx, ebx; unsigned __int64
0x18002d78b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002d790  mov     r14, rax
0x18002d793  mov     r8d, ebx; Size
0x18002d796  xor     edx, edx; Val
0x18002d798  mov     rcx, rax; void *
0x18002d79b  call    memset_0
0x18002d7a0  mov     rbx, r12
0x18002d7a3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix> `wil::Feature<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::GetImpl(void)'::`2'::impl
0x18002d7aa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::__private_IsEnabled(void)
0x18002d7af  test    al, al
0x18002d7b1  jz      short loc_18002D7C0
0x18002d7b3  mov     ecx, 208h; Size
0x18002d7b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d7bd  mov     rbx, rax
0x18002d7c0  mov     rsi, cs:?pfnPathAllocCanonicalize@Internal@StorageReserveHelper@@3P6AJPEBGKPEAPEAG@ZEA; long (*StorageReserveHelper::Internal::pfnPathAllocCanonicalize)(ushort const *,ulong,ushort * *)
0x18002d7c7  mov     rcx, [rbp+hMem]; hMem
0x18002d7cb  test    rcx, rcx
0x18002d7ce  jz      short loc_18002D7DA
0x18002d7d0  call    cs:__imp_LocalFree
0x18002d7d6  mov     [rbp+hMem], r12
0x18002d7da  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d7de  mov     qword ptr [rbp+cchCount2], rax
0x18002d7e2  mov     [rbp+var_30], rax
0x18002d7e6  lea     r8, [rbp+hMem]
0x18002d7ea  lea     edx, [rax+2]
0x18002d7ed  mov     rcx, rdi
0x18002d7f0  mov     rax, rsi
0x18002d7f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7f8  mov     edi, eax
0x18002d7fa  test    eax, eax
0x18002d7fc  jns     short loc_18002D85E
0x18002d7fe  mov     rcx, [rbp+38h]; this
0x18002d802  mov     r9d, eax; char *
0x18002d805  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002d80c  mov     edx, 147h; void *
0x18002d811  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d816  test    rbx, rbx
0x18002d819  jz      short loc_18002D824
0x18002d81b  mov     rcx, rbx; Block
0x18002d81e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d823  nop
0x18002d824  mov     rcx, r14; void *
0x18002d827  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d82c  nop
0x18002d82d  mov     rcx, [rbp+hMem]; hMem
0x18002d831  test    rcx, rcx
0x18002d834  jz      short loc_18002D840
0x18002d836  call    cs:__imp_LocalFree
0x18002d83c  mov     [rbp+hMem], r12
0x18002d840  mov     qword ptr [rbp+cchCount2], r12
0x18002d844  mov     [rbp+var_30], r12
0x18002d848  mov     rcx, [rbp+var_28]; hMem
0x18002d84c  test    rcx, rcx
0x18002d84f  jz      short loc_18002D857
0x18002d851  call    cs:__imp_LocalFree
0x18002d857  mov     eax, edi
0x18002d859  jmp     loc_18002DDD5
0x18002d85e  and     r13d, 10h
0x18002d862  jz      short loc_18002D8A9
0x18002d864  mov     edx, 2; unsigned __int16 *
0x18002d869  mov     rcx, [rbp+hMem]; this
0x18002d86d  call    ?SetAreaID@Internal@StorageReserveHelper@@YAJPEBGW4_STORAGE_RESERVE_ID@@K@Z; StorageReserveHelper::Internal::SetAreaID(ushort const *,_STORAGE_RESERVE_ID,ulong)
0x18002d872  mov     edi, eax
0x18002d874  test    eax, eax
0x18002d876  jns     short loc_18002D8A9
0x18002d878  mov     rcx, [rbp+38h]; this
0x18002d87c  mov     r9d, eax; char *
0x18002d87f  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002d886  mov     edx, 151h; void *
0x18002d88b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d890  test    rbx, rbx
0x18002d893  jz      short loc_18002D89E
0x18002d895  mov     rcx, rbx; Block
0x18002d898  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d89d  nop
0x18002d89e  mov     rcx, r14; void *
0x18002d8a1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d8a6  nop
0x18002d8a7  jmp     short loc_18002D82D
0x18002d8a9  mov     rdi, cs:?pfnPathAllocCombine@Internal@StorageReserveHelper@@3P6AJPEBG0KPEAPEAG@ZEA; long (*StorageReserveHelper::Internal::pfnPathAllocCombine)(ushort const *,ushort const *,ulong,ushort * *)
0x18002d8b0  mov     rcx, [rbp+var_28]; hMem
0x18002d8b4  test    rcx, rcx
0x18002d8b7  jz      short loc_18002D8C3
0x18002d8b9  call    cs:__imp_LocalFree
0x18002d8bf  mov     [rbp+var_28], r12
0x18002d8c3  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFFh
0x18002d8cb  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFFh
0x18002d8d3  lea     rax, qword_18003A1F8
0x18002d8da  lea     rdx, asc_18003EC68; "*"
0x18002d8e1  test    r13d, r13d
0x18002d8e4  cmovz   rdx, rax
0x18002d8e8  lea     r9, [rbp+var_28]
0x18002d8ec  mov     r8d, 1
0x18002d8f2  mov     rcx, [rbp+hMem]
0x18002d8f6  mov     rax, rdi
0x18002d8f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d8fe  mov     edi, eax
0x18002d900  test    eax, eax
0x18002d902  jns     short loc_18002D938
0x18002d904  mov     rcx, [rbp+38h]; this
0x18002d908  mov     r9d, eax; char *
0x18002d90b  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002d912  mov     edx, 154h; void *
0x18002d917  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d91c  test    rbx, rbx
0x18002d91f  jz      short loc_18002D92A
0x18002d921  mov     rcx, rbx; Block
0x18002d924  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d929  nop
0x18002d92a  mov     rcx, r14; void *
0x18002d92d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d932  nop
0x18002d933  jmp     loc_18002D82D
0x18002d938  mov     rdx, r14; lpFindFileData
0x18002d93b  mov     rcx, [rbp+var_28]; lpFileName
0x18002d93f  call    cs:__imp_FindFirstFileW
0x18002d945  mov     r12, rax
0x18002d948  or      r11, 0FFFFFFFFFFFFFFFFh
0x18002d94c  cmp     rax, r11
0x18002d94f  jnz     short loc_18002D9A1
0x18002d951  mov     rcx, [rbp+38h]; this
0x18002d955  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002d95c  mov     edx, 157h; void *
0x18002d961  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d966  mov     edi, eax
0x18002d968  xor     esi, esi
0x18002d96a  test    rbx, rbx
0x18002d96d  jz      short loc_18002D978
0x18002d96f  mov     rcx, rbx; Block
0x18002d972  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d977  nop
0x18002d978  mov     rcx, r14; void *
0x18002d97b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002d980  nop
0x18002d981  mov     rcx, [rbp+hMem]; hMem
0x18002d985  test    rcx, rcx
0x18002d988  jz      short loc_18002D994
0x18002d98a  call    cs:__imp_LocalFree
0x18002d990  mov     [rbp+hMem], rsi
0x18002d994  mov     qword ptr [rbp+cchCount2], rsi
0x18002d998  mov     [rbp+var_30], rsi
0x18002d99c  jmp     loc_18002D848
0x18002d9a1  lea     rsi, [r14+2Ch]
0x18002d9a5  xor     edi, edi
0x18002d9a7  cmp     word ptr [rsi], 2Eh ; '.'
0x18002d9ab  jnz     short loc_18002D9CB
0x18002d9ad  cmp     [r14+2Eh], di
0x18002d9b2  jz      loc_18002DBD2
0x18002d9b8  cmp     word ptr [r14+2Eh], 2Eh ; '.'
0x18002d9be  jnz     short loc_18002D9CB
0x18002d9c0  cmp     [r14+30h], di
0x18002d9c5  jz      loc_18002DBD2
0x18002d9cb  test    r13d, r13d
0x18002d9ce  jz      loc_18002DB51
0x18002d9d4  mov     rdi, cs:?pfnPathAllocCombine@Internal@StorageReserveHelper@@3P6AJPEBG0KPEAPEAG@ZEA; long (*StorageReserveHelper::Internal::pfnPathAllocCombine)(ushort const *,ushort const *,ulong,ushort * *)
0x18002d9db  mov     rcx, [rbp+var_28]; hMem
0x18002d9df  test    rcx, rcx
0x18002d9e2  jz      short loc_18002D9F6
0x18002d9e4  call    cs:__imp_LocalFree
0x18002d9ea  mov     [rbp+var_28], 0
0x18002d9f2  or      r11, 0FFFFFFFFFFFFFFFFh
0x18002d9f6  mov     [rbp+var_20], r11
0x18002d9fa  mov     [rbp+var_18], r11
0x18002d9fe  lea     r9, [rbp+var_28]
0x18002da02  mov     r8d, 1
0x18002da08  mov     rdx, rsi
0x18002da0b  mov     rcx, [rbp+hMem]
0x18002da0f  mov     rax, rdi
0x18002da12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da17  xor     edi, edi
0x18002da19  test    eax, eax
0x18002da1b  js      loc_18002DBD2
0x18002da21  mov     r10, [rbp+var_28]
0x18002da25  mov     rcx, [rbp+var_20]
0x18002da29  or      r11, 0FFFFFFFFFFFFFFFFh
0x18002da2d  cmp     rcx, r11
0x18002da30  jnz     short loc_18002DA4D
0x18002da32  test    r10, r10
0x18002da35  jz      short loc_18002DA46
0x18002da37  mov     rcx, r11
0x18002da3a  inc     rcx
0x18002da3d  cmp     [r10+rcx*2], di
0x18002da42  jnz     short loc_18002DA3A
0x18002da44  jmp     short loc_18002DA49
0x18002da46  mov     rcx, rdi
0x18002da49  mov     [rbp+var_20], rcx
0x18002da4d  mov     r8, [rbp+hMem]; lpString2
0x18002da51  mov     rdx, qword ptr [rbp+cchCount2]
0x18002da55  cmp     rdx, r11
0x18002da58  jnz     short loc_18002DA75
0x18002da5a  test    r8, r8
0x18002da5d  jz      short loc_18002DA6E
0x18002da5f  mov     rdx, r11
0x18002da62  inc     rdx
0x18002da65  cmp     [r8+rdx*2], di
0x18002da6a  jnz     short loc_18002DA62
0x18002da6c  jmp     short loc_18002DA71
0x18002da6e  mov     rdx, rdi
0x18002da71  mov     qword ptr [rbp+cchCount2], rdx
0x18002da75  cmp     rcx, rdx
0x18002da78  jz      short loc_18002DAF8
0x18002da7a  cmp     rcx, r11
0x18002da7d  jnz     short loc_18002DA9E
0x18002da7f  test    r10, r10
0x18002da82  jz      short loc_18002DA97
0x18002da84  mov     rcx, r11
0x18002da87  inc     rcx
0x18002da8a  cmp     [r10+rcx*2], di
0x18002da8f  jnz     short loc_18002DA87
0x18002da91  mov     [rbp+var_20], rcx
0x18002da95  jmp     short loc_18002DA9E
0x18002da97  mov     [rbp+var_20], rdi
0x18002da9b  mov     rcx, rdi
0x18002da9e  cmp     rdx, r11
0x18002daa1  jnz     short loc_18002DABE
0x18002daa3  test    r8, r8
0x18002daa6  jz      short loc_18002DAB7
0x18002daa8  mov     rdx, r11
0x18002daab  inc     rdx
0x18002daae  cmp     [r8+rdx*2], di
0x18002dab3  jnz     short loc_18002DAAB
0x18002dab5  jmp     short loc_18002DABA
0x18002dab7  mov     rdx, rdi
0x18002daba  mov     qword ptr [rbp+cchCount2], rdx
0x18002dabe  lea     rax, [rdx+1]
0x18002dac2  cmp     rcx, rax
0x18002dac5  jnz     loc_18002DB55
0x18002dacb  cmp     rcx, r11
0x18002dace  jnz     short loc_18002DAEF
0x18002dad0  test    r10, r10
0x18002dad3  jz      short loc_18002DAE8
0x18002dad5  mov     rcx, r11
0x18002dad8  inc     rcx
0x18002dadb  cmp     [r10+rcx*2], di
  ... truncated ...
```
