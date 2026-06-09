# CAppInfo::Initialize(tagPACKAGEDISPINFO *)

- ea: `0x1800061f8`
- end: `0x180006b89`
- name: `?Initialize@CAppInfo@@QEAAHPEAUtagPACKAGEDISPINFO@@@Z`
- size: `2449`
- prototype: `_BOOL8 __fastcall(CAppInfo *this, struct tagPACKAGEDISPINFO *)`
- caller_count: `3`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180004e30`
- `0x180004ef0`
- `0x18000ffdc`

## callees

- `0x1800016d0`
- `0x180002024`
- `0x180002aa0`
- `0x180002b14`
- `0x1800061f8`
- `0x180006b90`
- `0x180006e88`
- `0x180006f60`
- `0x18000a554`
- `0x18000f3fc`
- `0x180012fbc`
- `0x180013058`
- `0x180013108`
- `0x18001b1a0`
- `0x18001c204`
- `0x18002ada8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006843`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000685b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006843`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000685b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000680c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000680c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800068ad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800068dd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000690d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006945`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000697e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006a25`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800068ad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800068dd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000690d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006945`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000697e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006a25`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006875`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006b11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006875`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006b11`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006a8e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006a8e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180006adc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180006adc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800067e5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800067e5`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180006831`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180006831`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800063d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800063d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800063a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800065e6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800066e8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800063a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800065e6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800066e8`

## string_xrefs

- `0x180006961`: `Install UI`
- `0x180006a01`: `RemovedAppState`
- `0x180006ad5`: `RemovedAppState`

## pseudocode

```c
_BOOL8 __fastcall CAppInfo::Initialize(CAppInfo *this, struct tagPACKAGEDISPINFO *a2)
{
  BYTE *v4; // r12
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rsi
  SIZE_T v8; // rax
  unsigned __int16 *v9; // rax
  int v10; // eax
  unsigned __int16 *v11; // rcx
  struct _GUID *v13; // r14
  __int64 v14; // r9
  const wchar_t *v15; // r10
  __int64 v16; // rdx
  _WORD *v17; // r8
  _WORD *v18; // rcx
  CGPOInfoList *v19; // r15
  int v20; // esi
  const WCHAR *v21; // r13
  unsigned __int16 *v22; // rax
  struct CGPOInfo *v23; // r14
  const unsigned __int16 *v24; // rdx
  struct CGPOInfo *v25; // rax
  const unsigned __int16 *v26; // rcx
  unsigned __int16 **v27; // r15
  __int64 v28; // rax
  const unsigned __int16 *v29; // rcx
  unsigned int v30; // eax
  HLOCAL v31; // rax
  unsigned __int16 *v32; // rax
  unsigned int v33; // eax
  __int64 v34; // rcx
  unsigned int *v35; // rdx
  unsigned int i; // edx
  SIZE_T v37; // rax
  HLOCAL v38; // rax
  unsigned int v39; // r9d
  unsigned int j; // r10d
  __int64 v41; // r8
  __int64 v42; // rcx
  __int64 v43; // r8
  int v44; // ecx
  int v45; // ecx
  __int64 v46; // rax
  LSTATUS v47; // eax
  __int64 v48; // rcx
  LSTATUS v49; // esi
  DWORD LastError; // eax
  DWORD v51; // eax
  HKEY v52; // rcx
  const WCHAR **v53; // r14
  const unsigned __int16 **v54; // rsi
  HKEY v55; // rcx
  const WCHAR *v56; // r9
  CAppList *v57; // rcx
  struct CAppInfo *v58; // rax
  int v59; // ecx
  int v60; // ecx
  PHKEY phkResult; // [rsp+20h] [rbp-89h]
  DWORD cbData; // [rsp+30h] [rbp-79h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-71h] BYREF
  BYTE Data[16]; // [rsp+40h] [rbp-69h] BYREF
  struct _GUID v65; // [rsp+50h] [rbp-59h] BYREF
  WCHAR SubKey[48]; // [rsp+60h] [rbp-49h] BYREF

  *((_DWORD *)this + 42) = 5;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  v4 = (BYTE *)this + 224;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 26) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_DWORD *)this + 30) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *(_QWORD *)((char *)this + 172) = 0;
  *((_WORD *)this + 90) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_DWORD *)this + 48) = 0;
  *(_QWORD *)((char *)this + 196) = 0;
  v5 = *((_QWORD *)this + 2);
  *((_DWORD *)this + 51) = 0;
  *((_QWORD *)this + 26) = 1;
  hKey = 0;
  cbData = 0;
  *((_DWORD *)this + 54) = -1;
  *((_DWORD *)this + 56) = 0;
  *(_QWORD *)((char *)this + 228) = 0;
  *((_DWORD *)this + 59) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_DWORD *)this + 62) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_DWORD *)this + 78) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_DWORD *)this + 82) = 0;
  *((_DWORD *)this + 86) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_DWORD *)this + 90) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0xFFFF;
  *((_DWORD *)this + 96) = 1;
  *((_QWORD *)this + 54) = 0;
  *((_QWORD *)this + 55) = 0;
  *((_QWORD *)this + 56) = 0;
  if ( !v5 )
    return 0;
  v6 = *(_QWORD *)(v5 + 256);
  if ( v6 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(v6 + 2 * v7) );
  }
  else
  {
    LODWORD(v7) = 0;
  }
  v8 = 2LL * (unsigned int)(v7 + 44);
  if ( !is_mul_ok((unsigned int)(v7 + 44), 2u) )
    v8 = -1;
  v9 = (unsigned __int16 *)LocalAlloc(0, v8);
  *((_QWORD *)this + 11) = v9;
  if ( !v9 )
    return 0;
  v10 = StringCchCopyW(v9, (unsigned int)(v7 + 44), *(const unsigned __int16 **)(*((_QWORD *)this + 2) + 256LL));
  v11 = (unsigned __int16 *)*((_QWORD *)this + 11);
  if ( v10 < 0 )
    goto LABEL_10;
  v13 = (struct _GUID *)((char *)this + 24);
  GuidToString((struct _GUID *)((char *)this + 24), &v11[(unsigned int)v7]);
  v14 = 2147483646;
  v15 = L".aas";
  v16 = 6;
  v17 = (_WORD *)(*((_QWORD *)this + 11) + 2LL * (unsigned int)(v7 + 38));
  do
  {
    if ( !v14 )
      break;
    if ( !*v15 )
      break;
    *v17++ = *v15++;
    --v14;
    --v16;
  }
  while ( v16 );
  v18 = v17 - 1;
  if ( v16 )
    v18 = v17;
  *v18 = 0;
  if ( !v16 )
  {
    v11 = (unsigned __int16 *)*((_QWORD *)this + 11);
LABEL_10:
    LocalFree(v11);
    return 0;
  }
  v19 = (CGPOInfoList *)*((_QWORD *)this + 2);
  v20 = 0;
  if ( *((_DWORD *)v19 + 110) == 4 )
  {
    *((_DWORD *)this + 96) = 4;
  }
  else if ( *((_DWORD *)v19 + 116) )
  {
    *((_DWORD *)this + 96) = 5;
  }
  v21 = &word_18002F430;
  if ( !a2 )
  {
    v27 = (unsigned __int16 **)((char *)this + 72);
    goto LABEL_73;
  }
  *((_DWORD *)this + 40) = *((_DWORD *)a2 + 22);
  *((_DWORD *)this + 41) = *((_DWORD *)a2 + 23);
  *((_WORD *)this + 90) = *((_WORD *)a2 + 64);
  *((_DWORD *)this + 46) = GetLanguagePriority(*((_WORD *)a2 + 64), *((_DWORD *)a2 + 2));
  v22 = StringDuplicate(*((const unsigned __int16 **)a2 + 2));
  *((_QWORD *)this + 12) = v22;
  if ( !v22 && !*(_DWORD *)(*((_QWORD *)this + 2) + 308LL) )
    return 0;
  v23 = 0;
  *((_QWORD *)this + 5) = StringDuplicate(*(const unsigned __int16 **)a2);
  GuidToString((struct _GUID *)((char *)a2 + 44), (unsigned __int16 **)this + 10);
  GuidToString((struct _GUID *)((char *)a2 + 100), (unsigned __int16 **)this + 6);
  v24 = (const unsigned __int16 *)*((_QWORD *)this + 6);
  if ( v24 )
  {
    v25 = CGPOInfoList::Find(v19, v24);
    v23 = v25;
    if ( v25 )
      v26 = (const unsigned __int16 *)*((_QWORD *)v25 + 3);
    else
      v26 = &word_18002F430;
    v27 = (unsigned __int16 **)((char *)this + 72);
    *((_QWORD *)this + 9) = StringDuplicate(v26);
  }
  else
  {
    v27 = (unsigned __int16 **)((char *)this + 72);
  }
  *((_QWORD *)this + 18) = StringDuplicate(*((const unsigned __int16 **)a2 + 3));
  *((_QWORD *)this + 19) = StringDuplicate(*((const unsigned __int16 **)a2 + 4));
  v28 = *((_QWORD *)this + 2);
  if ( !*(_DWORD *)(v28 + 392) && !*(_DWORD *)(v28 + 308) || (v20 = CAppInfo::InitializeCategoriesList(this, a2)) == 0 )
  {
    if ( *(_DWORD *)(*((_QWORD *)this + 2) + 392LL) )
    {
      if ( v23 )
        v29 = (const unsigned __int16 *)*((_QWORD *)v23 + 5);
      else
        v29 = &word_18002F430;
      *((_QWORD *)this + 7) = StringDuplicate(v29);
      v30 = *((_DWORD *)a2 + 36);
      if ( v30 )
      {
        v31 = LocalAlloc(0, v30);
        *((_QWORD *)this + 30) = v31;
        if ( v31 )
        {
          if ( *((_QWORD *)a2 + 17) )
          {
            *((_DWORD *)this + 62) = *((_DWORD *)a2 + 36);
            memcpy_0(v31, *((const void **)a2 + 17), *((unsigned int *)a2 + 36));
          }
        }
      }
      v32 = StringDuplicate(*((const unsigned __int16 **)a2 + 19));
      *((_QWORD *)this + 8) = v32;
      if ( !*((_QWORD *)this + 7) || !v32 )
      {
        v20 = 14;
        goto LABEL_51;
      }
      v20 = CAppInfo::InitializeRSOPTransformsList(this, a2);
      if ( v20 || (v20 = CAppInfo::InitializeRSOPArchitectureInfo(this, a2)) != 0 )
      {
        if ( v20 <= 0 )
        {
          v33 = v20;
          goto LABEL_52;
        }
LABEL_51:
        v33 = (unsigned __int16)v20 | 0x80070000;
LABEL_52:
        v34 = *((_QWORD *)this + 2);
        if ( *(_DWORD *)(v34 + 392) )
        {
          v35 = *(unsigned int **)(v34 + 400);
          if ( v35 )
            *v35 = v33;
        }
        *(_DWORD *)(v34 + 392) = 0;
      }
    }
  }
  for ( i = 0; i < *((_DWORD *)a2 + 29); ++i )
  {
    if ( (*(_BYTE *)(*((_QWORD *)a2 + 15) + 48LL * i + 40) & 3) != 0 )
      ++*((_DWORD *)this + 26);
  }
  if ( *((_DWORD *)this + 26) )
  {
    v37 = 32LL * *((unsigned int *)this + 26);
    if ( !is_mul_ok(*((unsigned int *)this + 26), 0x20u) )
      v37 = -1;
    v38 = LocalAlloc(0, v37);
    *((_QWORD *)this + 14) = v38;
    if ( !v38 )
      return 0;
    memset_0(v38, 0, 32LL * *((unsigned int *)this + 26));
    v39 = 0;
    for ( j = 0; v39 < *((_DWORD *)a2 + 29); ++v39 )
    {
      v41 = *((_QWORD *)a2 + 15);
      if ( (*(_BYTE *)(v41 + 48LL * v39 + 40) & 3) != 0 )
      {
        v42 = 32LL * j;
        *(_OWORD *)(*((_QWORD *)this + 14) + v42) = *(_OWORD *)(v41 + 48LL * v39 + 8);
        *(_DWORD *)(*((_QWORD *)this + 14) + v42 + 16) = 4;
        v43 = v42 + *((_QWORD *)this + 14);
        v44 = *(_DWORD *)(v43 + 16);
        if ( (*(_BYTE *)(*((_QWORD *)a2 + 15) + 48LL * v39 + 40) & 1) != 0 )
          v45 = v44 | 1;
        else
          v45 = v44 | 2;
        *(_DWORD *)(v43 + 16) = v45;
        ++j;
      }
    }
  }
  v13 = (struct _GUID *)((char *)this + 24);
  *(_QWORD *)((char *)this + 172) = *((_QWORD *)a2 + 10);
  *((_DWORD *)this + 51) = *((_DWORD *)a2 + 24);
  *((_DWORD *)this + 52) = *((_DWORD *)a2 + 10);
  *((_DWORD *)this + 42) = *((_DWORD *)a2 + 3);
  *((_DWORD *)this + 53) = *((_DWORD *)a2 + 2);
LABEL_73:
  GuidToString(v13, SubKey);
  if ( !v20 )
  {
    v46 = *((_QWORD *)this + 2);
    if ( *(_DWORD *)(v46 + 396) != 1 )
    {
      if ( *(_DWORD *)(v46 + 296) )
        RevertToSelf();
      v47 = RegOpenKeyExW(*(HKEY *)(*((_QWORD *)this + 2) + 288LL), SubKey, 0, 0x2001Bu, &hKey);
      v48 = *((_QWORD *)this + 2);
      v49 = v47;
      if ( *(_DWORD *)(v48 + 396) == 1 || !*(_DWORD *)(v48 + 296) || ImpersonateLoggedOnUser(*(HANDLE *)(v48 + 264)) )
      {
        v51 = 0;
      }
      else
      {
        if ( *(_DWORD *)&gDebugLevel )
        {
          LastError = GetLastError();
          _DebugMsg(2u, 0xBC4u, LastError);
        }
        v51 = GetLastError();
      }
      if ( !v49 )
      {
        v52 = hKey;
        if ( v51 )
        {
          RegCloseKey(hKey);
          goto LABEL_108;
        }
        *(_DWORD *)v4 = 10;
        cbData = 4;
        RegQueryValueExW(v52, L"AppState", 0, 0, v4, &cbData);
        cbData = 4;
        RegQueryValueExW(hKey, L"AssignCount", 0, 0, (LPBYTE)this + 188, &cbData);
        cbData = 4;
        RegQueryValueExW(hKey, L"Revision", 0, 0, (LPBYTE)this + 192, &cbData);
        if ( *((_DWORD *)this + 48) )
        {
          cbData = 8;
          RegQueryValueExW(hKey, L"ScriptTime", 0, 0, (LPBYTE)this + 196, &cbData);
        }
        if ( a2 )
        {
          v54 = (const unsigned __int16 **)((char *)this + 48);
          v53 = (const WCHAR **)((char *)this + 40);
        }
        else
        {
          cbData = 4;
          RegQueryValueExW(hKey, L"Install UI", 0, 0, (LPBYTE)this + 208, &cbData);
          v53 = (const WCHAR **)((char *)this + 40);
          ReadStringValue(hKey, L"Deployment Name", (unsigned __int16 **)this + 5);
          ReadStringValue(hKey, L"GPO Name", v27);
          v54 = (const unsigned __int16 **)((char *)this + 48);
          ReadStringValue(hKey, L"GPO ID", (unsigned __int16 **)this + 6);
          ReadStringValue(hKey, L"Product ID", (unsigned __int16 **)this + 10);
        }
        if ( !*(_DWORD *)(*((_QWORD *)this + 2) + 332LL) )
          goto LABEL_105;
        *(_DWORD *)Data = 0;
        cbData = 4;
        if ( RegQueryValueExW(hKey, L"RemovedAppState", 0, 0, Data, &cbData) )
          goto LABEL_105;
        if ( (*v4 & 0x60) != 0 )
        {
          if ( !a2 && (!*v54 || !CGPOInfoList::Find(*((CGPOInfoList **)this + 2), *v54)) )
            goto LABEL_105;
          v55 = hKey;
          *(_DWORD *)v4 = *(_DWORD *)Data;
          cbData = 4;
          RegSetValueExW(v55, L"AppState", 0, 4u, Data, 4u);
          *((_DWORD *)this + 78) = 1;
          if ( *(_DWORD *)&gDebugLevel )
          {
            v56 = &word_18002F430;
            if ( *v27 )
              v56 = *v27;
            if ( *v53 )
              v21 = *v53;
            LODWORD(phkResult) = *(_DWORD *)v4;
            _DebugMsg(4u, 0xCA6u, v21, v56, phkResult);
          }
        }
        RegDeleteValueW(hKey, L"RemovedAppState");
LABEL_105:
        if ( (*(_DWORD *)v4 & 0x41) == 1 )
          *((_DWORD *)this + 95) = 1;
        ReadStringValue(hKey, L"SupercededIDs", (unsigned __int16 **)this + 17);
        RegCloseKey(hKey);
        v13 = (struct _GUID *)((char *)this + 24);
      }
    }
  }
LABEL_108:
  if ( (*(_DWORD *)v4 & 0x300) == 0 )
  {
    v57 = (CAppList *)(*((_QWORD *)this + 2) + 136LL);
    v65 = *v13;
    v58 = CAppList::Find(v57, &v65);
    v59 = *(_DWORD *)v4;
    if ( v58 )
      v60 = v59 | 0x500;
    else
      v60 = v59 | 0x200;
    *(_DWORD *)v4 = v60;
  }
  if ( !*((_QWORD *)this + 5) || !*((_QWORD *)this + 6) || !*v27 )
    return 0;
  return *((_QWORD *)this + 10) != 0;
}

```

## disassembly

```asm
0x1800061f8  mov     [rsp-8+arg_10], rbx
0x1800061fd  push    rbp
0x1800061fe  push    rsi
0x1800061ff  push    rdi
0x180006200  push    r12
0x180006202  push    r13
0x180006204  push    r14
0x180006206  push    r15
0x180006208  lea     rbp, [rsp-27h]
0x18000620d  sub     rsp, 0D0h
0x180006214  mov     rax, cs:__security_cookie
0x18000621b  xor     rax, rsp
0x18000621e  mov     [rbp+57h+var_40], rax
0x180006222  xor     r13d, r13d
0x180006225  mov     dword ptr [rcx+0A8h], 5
0x18000622f  mov     rbx, rcx
0x180006232  mov     [rcx+28h], r13
0x180006236  xor     eax, eax
0x180006238  mov     [rcx+30h], r13
0x18000623c  mov     [rcx+48h], r13
0x180006240  mov     rdi, rdx
0x180006243  mov     [rcx+38h], r13
0x180006247  mov     [rcx+40h], r13
0x18000624b  lea     r12, [rbx+0E0h]
0x180006252  mov     [rcx+50h], r13
0x180006256  mov     [rcx+58h], r13
0x18000625a  mov     [rcx+60h], r13
0x18000625e  mov     [rcx+68h], r13d
0x180006262  mov     [rcx+70h], r13
0x180006266  mov     [rcx+78h], r13d
0x18000626a  mov     [rcx+80h], r13
0x180006271  mov     [rcx+88h], r13
0x180006278  mov     [rcx+90h], r13
0x18000627f  mov     [rcx+98h], r13
0x180006286  mov     [rcx+0A0h], r13
0x18000628d  mov     [rcx+0ACh], rax
0x180006294  mov     [rcx+0B4h], r13w
0x18000629c  mov     [rcx+0B8h], r13
0x1800062a3  mov     [rcx+0C0h], r13d
0x1800062aa  mov     [rcx+0C4h], rax
0x1800062b1  mov     rax, [rbx+10h]
0x1800062b5  mov     [rcx+0CCh], r13d
0x1800062bc  mov     qword ptr [rcx+0D0h], 1
0x1800062c7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800062cb  mov     [rbp+57h+hKey], r13
0x1800062cf  mov     [rbp+57h+cbData], r13d
0x1800062d3  mov     [rbx+0D8h], ecx
0x1800062d9  mov     [r12], r13d
0x1800062dd  mov     [rbx+0E4h], r13
0x1800062e4  mov     [rbx+0ECh], r13d
0x1800062eb  mov     [rbx+0F0h], r13
0x1800062f2  mov     [rbx+0F8h], r13d
0x1800062f9  mov     [rbx+128h], r13
0x180006300  mov     [rbx+130h], r13
0x180006307  mov     [rbx+138h], r13d
0x18000630e  mov     [rbx+140h], r13
0x180006315  mov     [rbx+150h], r13
0x18000631c  mov     [rbx+148h], r13d
0x180006323  mov     [rbx+158h], r13d
0x18000632a  mov     [rbx+160h], r13
0x180006331  mov     [rbx+188h], r13
0x180006338  mov     [rbx+168h], r13d
0x18000633f  mov     [rbx+170h], r13
0x180006346  mov     qword ptr [rbx+178h], 0FFFFh
0x180006351  mov     dword ptr [rbx+180h], 1
0x18000635b  mov     [rbx+1B0h], r13
0x180006362  mov     [rbx+1B8h], r13
0x180006369  mov     [rbx+1C0h], r13
0x180006370  test    rax, rax
0x180006373  jz      short loc_1800063DB
0x180006375  mov     rax, [rax+100h]
0x18000637c  test    rax, rax
0x18000637f  jnz     short loc_180006386
0x180006381  mov     esi, r13d
0x180006384  jmp     short loc_180006393
0x180006386  mov     rsi, rcx
0x180006389  inc     rsi
0x18000638c  cmp     [rax+rsi*2], r13w
0x180006391  jnz     short loc_180006389
0x180006393  lea     r14d, [rsi+2Ch]
0x180006397  mov     eax, 2
0x18000639c  mul     r14
0x18000639f  cmovb   rax, rcx
0x1800063a3  xor     ecx, ecx; uFlags
0x1800063a5  mov     rdx, rax; uBytes
0x1800063a8  call    cs:__imp_LocalAlloc
0x1800063ae  mov     [rbx+58h], rax
0x1800063b2  test    rax, rax
0x1800063b5  jz      short loc_1800063DB
0x1800063b7  mov     r8, [rbx+10h]
0x1800063bb  mov     edx, r14d; unsigned __int64
0x1800063be  mov     rcx, rax; unsigned __int16 *
0x1800063c1  mov     r8, [r8+100h]; unsigned __int16 *
0x1800063c8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800063cd  mov     rcx, [rbx+58h]; hMem
0x1800063d1  test    eax, eax
0x1800063d3  jns     short loc_180006404
0x1800063d5  call    cs:__imp_LocalFree
0x1800063db  xor     eax, eax
0x1800063dd  mov     rcx, [rbp+57h+var_40]
0x1800063e1  xor     rcx, rsp; StackCookie
0x1800063e4  call    __security_check_cookie
0x1800063e9  mov     rbx, [rsp+100h+arg_10]
0x1800063f1  add     rsp, 0D0h
0x1800063f8  pop     r15
0x1800063fa  pop     r14
0x1800063fc  pop     r13
0x1800063fe  pop     r12
0x180006400  pop     rdi
0x180006401  pop     rsi
0x180006402  pop     rbp
0x180006403  retn
0x180006404  mov     eax, esi
0x180006406  lea     r14, [rbx+18h]
0x18000640a  lea     rdx, [rcx+rax*2]; unsigned __int16 *
0x18000640e  mov     rcx, r14; struct _GUID *
0x180006411  call    ?GuidToString@@YAXAEAU_GUID@@PEAG@Z; GuidToString(_GUID &,ushort *)
0x180006416  mov     rax, [rbx+58h]
0x18000641a  lea     ecx, [rsi+26h]
0x18000641d  mov     r9d, 7FFFFFFEh
0x180006423  lea     r10, aAas_0; ".aas"
0x18000642a  mov     edx, 6
0x18000642f  lea     r8, [rax+rcx*2]
0x180006433  test    r9, r9
0x180006436  jz      short loc_180006456
0x180006438  movzx   eax, word ptr [r10]
0x18000643c  test    ax, ax
0x18000643f  jz      short loc_180006456
0x180006441  mov     [r8], ax
0x180006445  add     r10, 2
0x180006449  add     r8, 2
0x18000644d  dec     r9
0x180006450  sub     rdx, 1
0x180006454  jnz     short loc_180006433
0x180006456  test    rdx, rdx
0x180006459  lea     rcx, [r8-2]
0x18000645d  cmovnz  rcx, r8
0x180006461  mov     [rcx], r13w
0x180006465  jnz     short loc_180006470
0x180006467  mov     rcx, [rbx+58h]
0x18000646b  jmp     loc_1800063D5
0x180006470  mov     r15, [rbx+10h]
0x180006474  mov     esi, r13d
0x180006477  cmp     dword ptr [r15+1B8h], 4
0x18000647f  jnz     short loc_18000648D
0x180006481  mov     dword ptr [rbx+180h], 4
0x18000648b  jmp     short loc_1800064A0
0x18000648d  cmp     [r15+1D0h], r13d
0x180006494  jz      short loc_1800064A0
0x180006496  mov     dword ptr [rbx+180h], 5
0x1800064a0  lea     r13, word_18002F430
0x1800064a7  test    rdi, rdi
0x1800064aa  jz      loc_1800067B4
0x1800064b0  mov     eax, [rdi+58h]
0x1800064b3  mov     [rbx+0A0h], eax
0x1800064b9  mov     eax, [rdi+5Ch]
0x1800064bc  mov     [rbx+0A4h], eax
0x1800064c2  movzx   eax, word ptr [rdi+80h]
0x1800064c9  mov     [rbx+0B4h], ax
0x1800064d0  mov     edx, [rdi+8]; unsigned int
0x1800064d3  movzx   ecx, word ptr [rdi+80h]; unsigned __int16
0x1800064da  call    ?GetLanguagePriority@@YAKGK@Z; GetLanguagePriority(ushort,ulong)
0x1800064df  mov     [rbx+0B8h], eax
0x1800064e5  mov     rcx, [rdi+10h]; unsigned __int16 *
0x1800064e9  call    ?StringDuplicate@@YAPEAGPEBG@Z; StringDuplicate(ushort const *)
0x1800064ee  mov     [rbx+60h], rax
0x1800064f2  test    rax, rax
0x1800064f5  jnz     short loc_180006507
0x1800064f7  mov     rax, [rbx+10h]
0x1800064fb  cmp     [rax+134h], esi
0x180006501  jz      loc_1800063DB
0x180006507  mov     rcx, [rdi]; unsigned __int16 *
0x18000650a  xor     r14d, r14d
0x18000650d  call    ?StringDuplicate@@YAPEAGPEBG@Z; StringDuplicate(ushort const *)
0x180006512  lea     rcx, [rdi+2Ch]; struct _GUID *
0x180006516  mov     [rbx+28h], rax
0x18000651a  lea     rdx, [rbx+50h]; unsigned __int16 **
0x18000651e  call    ?GuidToString@@YAXAEAU_GUID@@PEAPEAG@Z; GuidToString(_GUID &,ushort * *)
0x180006523  lea     rcx, [rdi+64h]; struct _GUID *
0x180006527  lea     rdx, [rbx+30h]; unsigned __int16 **
0x18000652b  call    ?GuidToString@@YAXAEAU_GUID@@PEAPEAG@Z; GuidToString(_GUID &,ushort * *)
0x180006530  mov     rdx, [rbx+30h]; unsigned __int16 *
0x180006534  test    rdx, rdx
0x180006537  jz      short loc_180006560
0x180006539  mov     rcx, r15; this
0x18000653c  call    ?Find@CGPOInfoList@@QEAAPEAVCGPOInfo@@PEBG@Z; CGPOInfoList::Find(ushort const *)
0x180006541  mov     r14, rax
0x180006544  test    rax, rax
0x180006547  jz      short loc_18000654F
0x180006549  mov     rcx, [rax+18h]
0x18000654d  jmp     short loc_180006552
0x18000654f  mov     rcx, r13; unsigned __int16 *
0x180006552  call    ?StringDuplicate@@YAPEAGPEBG@Z; StringDuplicate(ushort const *)
0x180006557  lea     r15, [rbx+48h]
0x18000655b  mov     [r15], rax
0x18000655e  jmp     short loc_180006564
0x180006560  lea     r15, [rbx+48h]
0x180006564  mov     rcx, [rdi+18h]; unsigned __int16 *
0x180006568  call    ?StringDuplicate@@YAPEAGPEBG@Z; StringDuplicate(ushort const *)
0x18000656d  mov     [rbx+90h], rax
0x180006574  mov     rcx, [rdi+20h]; unsigned __int16 *
0x180006578  call    ?StringDuplicate@@YAPEAGPEBG@Z; StringDuplicate(ushort const *)
0x18000657d  mov     [rbx+98h], rax
0x180006584  mov     rax, [rbx+10h]
0x180006588  cmp     [rax+188h], esi
0x18000658e  jnz     short loc_180006598
0x180006590  cmp     [rax+134h], esi
0x180006596  jz      short loc_1800065AD
0x180006598  mov     rdx, rdi; struct tagPACKAGEDISPINFO *
0x18000659b  mov     rcx, rbx; this
0x18000659e  call    ?InitializeCategoriesList@CAppInfo@@AEAAJPEAUtagPACKAGEDISPINFO@@@Z; CAppInfo::InitializeCategoriesList(tagPACKAGEDISPINFO *)
0x1800065a3  mov     esi, eax
0x1800065a5  test    eax, eax
0x1800065a7  jnz     loc_180006699
0x1800065ad  mov     rcx, [rbx+10h]
0x1800065b1  cmp     dword ptr [rcx+188h], 0
0x1800065b8  jz      loc_180006699
0x1800065be  test    r14, r14
0x1800065c1  jz      short loc_1800065C9
0x1800065c3  mov     rcx, [r14+28h]
0x1800065c7  jmp     short loc_1800065CC
0x1800065c9  mov     rcx, r13; unsigned __int16 *
0x1800065cc  call    ?StringDuplicate@@YAPEAGPEBG@Z; StringDuplicate(ushort const *)
0x1800065d1  mov     [rbx+38h], rax
0x1800065d5  xor     r14d, r14d
0x1800065d8  mov     eax, [rdi+90h]
0x1800065de  test    eax, eax
0x1800065e0  jz      short loc_180006623
0x1800065e2  mov     edx, eax; uBytes
0x1800065e4  xor     ecx, ecx; uFlags
0x1800065e6  call    cs:__imp_LocalAlloc
0x1800065ec  mov     [rbx+0F0h], rax
0x1800065f3  test    rax, rax
0x1800065f6  jz      short loc_180006623
0x1800065f8  cmp     [rdi+88h], r14
0x1800065ff  jz      short loc_180006623
0x180006601  mov     ecx, [rdi+90h]
0x180006607  mov     [rbx+0F8h], ecx
0x18000660d  mov     rcx, rax; void *
0x180006610  mov     r8d, [rdi+90h]; Size
0x180006617  mov     rdx, [rdi+88h]; Src
0x18000661e  call    memcpy_0
0x180006623  mov     rcx, [rdi+98h]; unsigned __int16 *
0x18000662a  call    ?StringDuplicate@@YAPEAGPEBG@Z; StringDuplicate(ushort const *)
0x18000662f  mov     [rbx+40h], rax
0x180006633  cmp     [rbx+38h], r14
0x180006637  jz      short loc_180006668
0x180006639  test    rax, rax
0x18000663c  jz      short loc_180006668
0x18000663e  mov     rdx, rdi; struct tagPACKAGEDISPINFO *
0x180006641  mov     rcx, rbx; this
0x180006644  call    ?InitializeRSOPTransformsList@CAppInfo@@AEAAJPEAUtagPACKAGEDISPINFO@@@Z; CAppInfo::InitializeRSOPTransformsList(tagPACKAGEDISPINFO *)
0x180006649  mov     esi, eax
0x18000664b  test    eax, eax
0x18000664d  jnz     short loc_180006660
0x18000664f  mov     rdx, rdi; struct tagPACKAGEDISPINFO *
0x180006652  mov     rcx, rbx; this
0x180006655  call    ?InitializeRSOPArchitectureInfo@CAppInfo@@AEAAJPEAUtagPACKAGEDISPINFO@@@Z; CAppInfo::InitializeRSOPArchitectureInfo(tagPACKAGEDISPINFO *)
0x18000665a  mov     esi, eax
0x18000665c  test    eax, eax
0x18000665e  jz      short loc_18000669C
0x180006660  test    esi, esi
0x180006662  jg      short loc_18000666D
0x180006664  mov     eax, esi
0x180006666  jmp     short loc_180006675
0x180006668  mov     esi, 0Eh
0x18000666d  movzx   eax, si
0x180006670  or      eax, 80070000h
0x180006675  mov     rcx, [rbx+10h]
0x180006679  cmp     [rcx+188h], r14d
0x180006680  jz      short loc_180006690
0x180006682  mov     rdx, [rcx+190h]
0x180006689  test    rdx, rdx
0x18000668c  jz      short loc_180006690
0x18000668e  mov     [rdx], eax
0x180006690  mov     [rcx+188h], r14d
0x180006697  jmp     short loc_18000669C
0x180006699  xor     r14d, r14d
0x18000669c  mov     edx, r14d
0x18000669f  cmp     [rdi+74h], r14d
0x1800066a3  jbe     short loc_1800066C3
0x1800066a5  mov     eax, edx
0x1800066a7  lea     rcx, [rax+rax*2]
0x1800066ab  mov     rax, [rdi+78h]
0x1800066af  add     rcx, rcx
0x1800066b2  test    byte ptr [rax+rcx*8+28h], 3
0x1800066b7  jz      short loc_1800066BC
0x1800066b9  inc     dword ptr [rbx+68h]
0x1800066bc  inc     edx
0x1800066be  cmp     edx, [rdi+74h]
0x1800066c1  jb      short loc_1800066A5
0x1800066c3  cmp     [rbx+68h], r14d
0x1800066c7  jbe     loc_18000677F
0x1800066cd  mov     ecx, [rbx+68h]
0x1800066d0  mov     eax, 20h ; ' '
0x1800066d5  mul     rcx
0x1800066d8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800066df  cmovb   rax, rcx
0x1800066e3  xor     ecx, ecx; uFlags
0x1800066e5  mov     rdx, rax; uBytes
  ... truncated ...
```
