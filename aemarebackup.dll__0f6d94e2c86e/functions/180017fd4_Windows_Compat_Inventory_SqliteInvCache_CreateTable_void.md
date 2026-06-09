# Windows::Compat::Inventory::SqliteInvCache::CreateTable(void)

- ea: `0x180017fd4`
- end: `0x180018a2b`
- name: `?CreateTable@SqliteInvCache@Inventory@Compat@Windows@@AEAAJXZ`
- size: `2647`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this)`
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1800171f0`
- `0x18001ec10`

## callees

- `0x180004ea0`
- `0x180006c40`
- `0x18000fb60`
- `0x18001209c`
- `0x1800134b8`
- `0x180017fd4`
- `0x180018a34`
- `0x1800276cc`
- `0x180027d3c`
- `0x18004c020`
- `0x180059d64`
- `0x1800a494c`
- `0x1800c2b60`
- `0x1800c4b00`
- `0x1800c5440`
- `0x1800c7810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018259`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001867b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018882`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018259`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001867b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018882`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018247`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018870`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018247`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018870`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800181f0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800183c5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001874c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180018950`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800181f0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800183c5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001874c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180018950`

## string_xrefs

- `0x180018036`: `CreateTableString failed [%#x]`
- `0x180018605`: `CREATE TABLE `
- `0x180018813`: `CREATE TABLE IF NOT EXISTS `
- `0x180018043`: `Windows::Compat::Inventory::SqliteInvCache::CreateTable`
- `0x1800180e6`: `Windows::Compat::Inventory::SqliteInvCache::CreateTable`
- `0x18001818f`: `Windows::Compat::Inventory::SqliteInvCache::CreateTable`
- `0x1800181fd`: `Windows::Compat::Inventory::SqliteInvCache::CreateTable`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::CreateTable(
        Windows::Compat::Inventory::SqliteInvCache *this)
{
  int v2; // eax
  signed int v3; // ebx
  __int128 *v5; // rdx
  const char *v6; // rax
  __int64 v7; // rcx
  const wchar_t *v8; // rsi
  const wchar_t *v9; // r8
  __int64 v10; // r12
  const char *v11; // rax
  int i; // ebx
  int v13; // r13d
  DWORD LastError; // ebx
  __int128 *v15; // rdx
  const char *v16; // rax
  int v17; // r8d
  __int64 v18; // rsi
  const char *v19; // rax
  int j; // r12d
  const char *v21; // rax
  _WORD *v22; // rax
  unsigned __int64 v23; // r8
  __int128 *v24; // r8
  __int128 *v25; // r12
  char *v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int128 *v30; // rax
  __int64 v31; // rax
  DWORD v32; // ebx
  __int128 *v33; // rdx
  const char *v34; // rax
  int k; // r12d
  const char *v36; // rax
  __int64 v37; // r8
  _QWORD *v38; // rax
  unsigned __int64 v39; // rdx
  __int64 v40; // rax
  DWORD v41; // ebx
  __int128 *v42; // rdx
  const char *v43; // rax
  int m; // r12d
  const char *v45; // rax
  __int64 v46; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v47; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v48; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v49; // [rsp+60h] [rbp-A0h]
  __int128 v50; // [rsp+68h] [rbp-98h] BYREF
  __int128 v51; // [rsp+78h] [rbp-88h]
  __int128 v52; // [rsp+88h] [rbp-78h] BYREF
  __int128 v53; // [rsp+98h] [rbp-68h]
  __int128 v54; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v55; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v56; // [rsp+C0h] [rbp-40h]
  __int128 v57; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v58; // [rsp+D8h] [rbp-28h]
  char *Src[4]; // [rsp+E8h] [rbp-18h] BYREF

  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 7;
  LOWORD(v47) = 0;
  v2 = Windows::Compat::Inventory::SqliteInvCache::CreateTableString(this, &v47);
  v3 = v2;
  if ( v2 < 0 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
      1438,
      "CreateTableString failed [%#x]",
      v2);
    std::wstring::~wstring((char **)&v47);
    return (unsigned int)v3;
  }
  v52 = 0;
  v53 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    (char **)&v52,
    L"SELECT 1 FROM sqlite_master WHERE type='table' AND name=?;",
    0x3Au);
  v46 = 0;
  v5 = &v52;
  if ( *((_QWORD *)&v53 + 1) > 7u )
    LODWORD(v5) = v52;
  v3 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v5, -1, 128, (__int64)&v46, 0);
  if ( v3 )
  {
    v6 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
      1446,
      "sqlite3_prepare16_v2 failed: [%d] %hs",
      v3,
      v6);
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    std::wstring::~wstring((char **)&v52);
    std::wstring::~wstring((char **)&v47);
    v7 = v46;
    if ( !v46 )
      return (unsigned int)v3;
    goto LABEL_97;
  }
  v8 = (const wchar_t *)((char *)this + 72);
  if ( *((_QWORD *)this + 12) <= 7u )
    LODWORD(v9) = (_DWORD)this + 72;
  else
    v9 = *(const wchar_t **)v8;
  v10 = v46;
  v3 = bindText(v46, 1, (_DWORD)v9, -2, 0, 2);
  if ( v3 )
  {
    v11 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
      1452,
      "sqlite3_bind_text16 failed: [%d] %hs",
      v3,
      v11);
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    std::wstring::~wstring((char **)&v52);
    std::wstring::~wstring((char **)&v47);
    if ( v10 )
      sqlite3_finalize(v10);
    return (unsigned int)v3;
  }
  for ( i = 0; i < 100; ++i )
  {
    v13 = sqlite3_step(v10);
    if ( (unsigned int)(v13 - 5) > 1 )
      break;
    Sleep(5u);
  }
  if ( v13 == 100 )
  {
    v50 = 0;
    v51 = 0;
    std::wstring::_Construct<1,unsigned short const *>(
      (char **)&v50,
      L"SELECT sql FROM sqlite_master WHERE type='table' AND name=?;",
      0x3Cu);
    if ( v10 )
    {
      LastError = GetLastError();
      sqlite3_finalize(v10);
      SetLastError(LastError);
    }
    v46 = 0;
    v15 = &v50;
    if ( *((_QWORD *)&v51 + 1) > 7u )
      LODWORD(v15) = v50;
    v3 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v15, -1, 128, (__int64)&v46, 0);
    if ( v3 )
    {
      v16 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
        1463,
        "sqlite3_prepare16_v2 failed: [%d] %hs",
        v3,
        v16);
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      std::wstring::~wstring((char **)&v50);
      std::wstring::~wstring((char **)&v52);
      std::wstring::~wstring((char **)&v47);
      v7 = v46;
      if ( !v46 )
        return (unsigned int)v3;
      goto LABEL_97;
    }
    if ( *((_QWORD *)this + 12) > 7u )
      v8 = *(const wchar_t **)v8;
    v17 = (int)v8;
    v18 = v46;
    v3 = bindText(v46, 1, v17, -2, 0, 2);
    if ( v3 )
    {
      v19 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
        1469,
        "sqlite3_bind_text16 failed: [%d] %hs",
        v3,
        v19);
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      std::wstring::~wstring((char **)&v50);
      std::wstring::~wstring((char **)&v52);
      std::wstring::~wstring((char **)&v47);
      if ( !v18 )
        return (unsigned int)v3;
      goto LABEL_105;
    }
    for ( j = 0; j < 100; ++j )
    {
      v3 = sqlite3_step(v18);
      if ( (unsigned int)(v3 - 5) > 1 )
        break;
      Sleep(5u);
    }
    if ( v3 != 100 )
    {
      v21 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
        1475,
        "sqlite3_step failed: [%d] %hs",
        v3,
        v21);
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      std::wstring::~wstring((char **)&v50);
      std::wstring::~wstring((char **)&v52);
      std::wstring::~wstring((char **)&v47);
      if ( !v18 )
        return (unsigned int)v3;
      goto LABEL_105;
    }
    v22 = (_WORD *)sqlite3_column_text16(v18, 0);
    v54 = 0;
    v55 = 0;
    v56 = 0;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v54, v22, v23);
    if ( !v55 )
    {
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
        1482,
        "sqlite3_column_text16 returned a null schema [%#x]",
        -2147467259);
      std::wstring::~wstring((char **)&v54);
      std::wstring::~wstring((char **)&v50);
      std::wstring::~wstring((char **)&v52);
      std::wstring::~wstring((char **)&v47);
      if ( v18 )
        goto LABEL_62;
      return 2147500037LL;
    }
    v24 = &v47;
    if ( v49 > 7 )
      v24 = (__int128 *)v47;
    v25 = &v54;
    if ( v56 > 7 )
      v25 = (__int128 *)v54;
    if ( v48 > v55
      || v48
      && ((v26 = (char *)v25 + 2 * v55, v27 = _std_search_2(v25, v26, v24, v48), (char *)v27 == v26)
       || (v27 - (__int64)v25) >> 1 == -1) )
    {
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
        1488,
        "Schema mismatch [%#x]",
        -2147467259);
      std::wstring::~wstring((char **)&v54);
      std::wstring::~wstring((char **)&v50);
      std::wstring::~wstring((char **)&v52);
      std::wstring::~wstring((char **)&v47);
      if ( v18 )
LABEL_62:
        sqlite3_finalize(v18);
      return 2147500037LL;
    }
    std::wstring::~wstring((char **)&v54);
  }
  else
  {
    if ( *((_QWORD *)this + 12) > 7u )
      v8 = *(const wchar_t **)v8;
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
      1494,
      "Table %ls doesn't exist. Creating new table.",
      v8);
    if ( 0x7FFFFFFFFFFFFFFELL - v48 < 0xD )
      std::_Xlen_string();
    v30 = &v47;
    if ( v49 > 7 )
      v30 = (__int128 *)v47;
    std::wstring::wstring(Src, v28, v29, L"CREATE TABLE ", 13, v30, v48);
    v31 = std::wstring::append(Src, L";");
    v50 = 0;
    v51 = 0;
    v50 = *(_OWORD *)v31;
    v51 = *(_OWORD *)(v31 + 16);
    *(_QWORD *)(v31 + 16) = 0;
    *(_QWORD *)(v31 + 24) = 7;
    *(_WORD *)v31 = 0;
    std::wstring::~wstring(Src);
    if ( v10 )
    {
      v32 = GetLastError();
      sqlite3_finalize(v10);
      SetLastError(v32);
    }
    v46 = 0;
    v33 = &v50;
    if ( *((_QWORD *)&v51 + 1) > 7u )
      LODWORD(v33) = v50;
    v3 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v33, -1, 128, (__int64)&v46, 0);
    if ( v3 )
    {
      v34 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
        1501,
        "sqlite3_prepare16_v2 failed: [%d] %hs",
        v3,
        v34);
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      std::wstring::~wstring((char **)&v50);
      std::wstring::~wstring((char **)&v52);
      std::wstring::~wstring((char **)&v47);
      v7 = v46;
      if ( !v46 )
        return (unsigned int)v3;
LABEL_97:
      sqlite3_finalize(v7);
      return (unsigned int)v3;
    }
    v18 = v46;
    for ( k = 0; k < 100; ++k )
    {
      v3 = sqlite3_step(v18);
      if ( (unsigned int)(v3 - 5) > 1 )
        break;
      Sleep(5u);
    }
    if ( v3 != 101 )
    {
      v36 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
        1507,
        "sqlite3_step failed: [%d] %hs",
        v3,
        v36);
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      std::wstring::~wstring((char **)&v50);
      std::wstring::~wstring((char **)&v52);
      std::wstring::~wstring((char **)&v47);
      if ( !v18 )
        return (unsigned int)v3;
LABEL_105:
      sqlite3_finalize(v18);
      return (unsigned int)v3;
    }
  }
  std::wstring::~wstring((char **)&v50);
  v38 = (_QWORD *)((char *)this + 104);
  v39 = 0x7FFFFFFFFFFFFFFELL - *((_QWORD *)this + 15);
  if ( v39 < 0x1B )
    std::_Xlen_string();
  if ( *((_QWORD *)this + 16) > 7u )
    v38 = (_QWORD *)*v38;
  std::wstring::wstring(Src, v39, v37, L"CREATE TABLE IF NOT EXISTS ", 27, v38, *((_QWORD *)this + 15));
  v40 = std::wstring::append(Src, L" (Name TEXT PRIMARY KEY, Value TEXT);");
  v57 = 0;
  v58 = 0;
  v57 = *(_OWORD *)v40;
  v58 = *(_OWORD *)(v40 + 16);
  *(_QWORD *)(v40 + 16) = 0;
  *(_QWORD *)(v40 + 24) = 7;
  *(_WORD *)v40 = 0;
  std::wstring::~wstring(Src);
  if ( v18 )
  {
    v41 = GetLastError();
    sqlite3_finalize(v18);
    SetLastError(v41);
  }
  v46 = 0;
  v42 = &v57;
  if ( *((_QWORD *)&v58 + 1) > 7u )
    LODWORD(v42) = v57;
  v3 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v42, -1, 128, (__int64)&v46, 0);
  if ( v3 )
  {
    v43 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
      1517,
      "sqlite3_prepare16_v2 failed: [%d] %hs",
      v3,
      v43);
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    std::wstring::~wstring((char **)&v57);
    std::wstring::~wstring((char **)&v52);
    std::wstring::~wstring((char **)&v47);
    v7 = v46;
    if ( !v46 )
      return (unsigned int)v3;
    goto LABEL_97;
  }
  v18 = v46;
  for ( m = 0; m < 100; ++m )
  {
    v3 = sqlite3_step(v18);
    if ( (unsigned int)(v3 - 5) > 1 )
      break;
    Sleep(5u);
  }
  if ( v3 != 101 )
  {
    v45 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
      1523,
      "sqlite3_step failed: [%d] %hs",
      v3,
      v45);
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    std::wstring::~wstring((char **)&v57);
    std::wstring::~wstring((char **)&v52);
    std::wstring::~wstring((char **)&v47);
    if ( !v18 )
      return (unsigned int)v3;
    goto LABEL_105;
  }
  std::wstring::~wstring((char **)&v57);
  std::wstring::~wstring((char **)&v52);
  std::wstring::~wstring((char **)&v47);
  if ( v18 )
    sqlite3_finalize(v18);
  return 0;
}

```

## disassembly

```asm
0x180017fd4  push    rbp
0x180017fd6  push    rbx
0x180017fd7  push    rsi
0x180017fd8  push    rdi
0x180017fd9  push    r12
0x180017fdb  push    r13
0x180017fdd  push    r14
0x180017fdf  push    r15
0x180017fe1  lea     rbp, [rsp-18h]
0x180017fe6  sub     rsp, 118h
0x180017fed  mov     rax, cs:__security_cookie
0x180017ff4  xor     rax, rsp
0x180017ff7  mov     [rbp+50h+var_48], rax
0x180017ffb  mov     r15, rcx
0x180017ffe  xor     r13d, r13d
0x180018001  mov     [rsp+150h+var_110], r13
0x180018006  xorps   xmm0, xmm0
0x180018009  movups  [rsp+150h+var_108], xmm0
0x18001800e  mov     [rsp+150h+var_F8], r13
0x180018013  mov     [rsp+150h+var_F0], 7
0x18001801c  mov     word ptr [rsp+150h+var_108], r13w
0x180018022  lea     rdx, [rsp+150h+var_108]
0x180018027  call    ?CreateTableString@SqliteInvCache@Inventory@Compat@Windows@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Compat::Inventory::SqliteInvCache::CreateTableString(std::wstring &)
0x18001802c  mov     ebx, eax
0x18001802e  test    eax, eax
0x180018030  jns     short loc_180018066
0x180018032  mov     dword ptr [rsp+150h+var_130], eax
0x180018036  lea     r9, aCreatetablestr; "CreateTableString failed [%#x]"
0x18001803d  mov     r8d, 59Eh
0x180018043  lea     rdx, aWindowsCompatI_19; "Windows::Compat::Inventory::SqliteInvCa"...
0x18001804a  lea     ecx, [r13+1]
0x18001804e  call    AslLogCallPrintf
0x180018053  nop
0x180018054  lea     rcx, [rsp+150h+var_108]
0x180018059  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001805e  nop
0x18001805f  mov     eax, ebx
0x180018061  jmp     loc_1800189FF
0x180018066  xorps   xmm0, xmm0
0x180018069  movups  [rbp+50h+var_C8], xmm0
0x18001806d  xorps   xmm1, xmm1
0x180018070  movdqu  [rbp+50h+var_B8], xmm1
0x180018075  mov     r8d, 3Ah ; ':'
0x18001807b  lea     rdx, aSelect1FromSql; "SELECT 1 FROM sqlite_master WHERE type="...
0x180018082  lea     rcx, [rbp+50h+var_C8]
0x180018086  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001808b  nop
0x18001808c  mov     [rsp+150h+var_110], r13
0x180018091  lea     rdx, [rbp+50h+var_C8]
0x180018095  cmp     qword ptr [rbp+50h+var_B8+8], 7
0x18001809a  cmova   rdx, qword ptr [rbp+50h+var_C8]
0x18001809f  mov     [rsp+150h+var_128], r13
0x1800180a4  lea     rax, [rsp+150h+var_110]
0x1800180a9  mov     [rsp+150h+var_130], rax
0x1800180ae  mov     r9d, 80h
0x1800180b4  or      r8d, 0FFFFFFFFh
0x1800180b8  mov     rcx, [r15+8]
0x1800180bc  call    sqlite3Prepare16
0x1800180c1  mov     ebx, eax
0x1800180c3  test    eax, eax
0x1800180c5  jz      short loc_180018132
0x1800180c7  mov     rcx, [r15+8]
0x1800180cb  call    sqlite3_errmsg
0x1800180d0  mov     [rsp+150h+var_128], rax
0x1800180d5  mov     dword ptr [rsp+150h+var_130], ebx
0x1800180d9  lea     r9, aSqlite3Prepare_1; "sqlite3_prepare16_v2 failed: [%d] %hs"
0x1800180e0  mov     r8d, 5A6h
0x1800180e6  lea     rdx, aWindowsCompatI_19; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800180ed  mov     ecx, 1
0x1800180f2  call    AslLogCallPrintf
0x1800180f7  test    ebx, ebx
0x1800180f9  jle     short loc_180018104
0x1800180fb  movzx   ebx, bx
0x1800180fe  or      ebx, 80070000h
0x180018104  lea     rcx, [rbp+50h+var_C8]
0x180018108  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001810d  nop
0x18001810e  lea     rcx, [rsp+150h+var_108]
0x180018113  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018118  nop
0x180018119  mov     rcx, [rsp+150h+var_110]
0x18001811e  test    rcx, rcx
0x180018121  jz      loc_18001805F
0x180018127  call    sqlite3_finalize
0x18001812c  nop
0x18001812d  jmp     loc_18001805F
0x180018132  lea     rsi, [r15+48h]
0x180018136  cmp     qword ptr [rsi+18h], 7
0x18001813b  jbe     short loc_180018142
0x18001813d  mov     r8, [rsi]
0x180018140  jmp     short loc_180018145
0x180018142  mov     r8, rsi
0x180018145  mov     byte ptr [rsp+150h+var_128], 2
0x18001814a  mov     [rsp+150h+var_130], r13
0x18001814f  mov     edi, 1
0x180018154  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18001815b  mov     edx, edi
0x18001815d  mov     r12, [rsp+150h+var_110]
0x180018162  mov     rcx, r12
0x180018165  call    bindText
0x18001816a  mov     ebx, eax
0x18001816c  test    eax, eax
0x18001816e  jz      short loc_1800181D6
0x180018170  mov     rcx, [r15+8]
0x180018174  call    sqlite3_errmsg
0x180018179  mov     [rsp+150h+var_128], rax
0x18001817e  mov     dword ptr [rsp+150h+var_130], ebx
0x180018182  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x180018189  mov     r8d, 5ACh
0x18001818f  lea     rdx, aWindowsCompatI_19; "Windows::Compat::Inventory::SqliteInvCa"...
0x180018196  mov     ecx, edi
0x180018198  call    AslLogCallPrintf
0x18001819d  test    ebx, ebx
0x18001819f  jle     short loc_1800181AA
0x1800181a1  movzx   ebx, bx
0x1800181a4  or      ebx, 80070000h
0x1800181aa  lea     rcx, [rbp+50h+var_C8]
0x1800181ae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800181b3  nop
0x1800181b4  lea     rcx, [rsp+150h+var_108]
0x1800181b9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800181be  nop
0x1800181bf  test    r12, r12
0x1800181c2  jz      loc_18001805F
0x1800181c8  mov     rcx, r12
0x1800181cb  call    sqlite3_finalize
0x1800181d0  nop
0x1800181d1  jmp     loc_18001805F
0x1800181d6  mov     ebx, r13d
0x1800181d9  mov     rcx, r12
0x1800181dc  call    sqlite3_step
0x1800181e1  mov     r13d, eax
0x1800181e4  lea     ecx, [rax-5]
0x1800181e7  cmp     ecx, edi
0x1800181e9  ja      short loc_1800181FD
0x1800181eb  mov     ecx, 5; dwMilliseconds
0x1800181f0  call    cs:__imp_Sleep
0x1800181f6  add     ebx, edi
0x1800181f8  cmp     ebx, 64h ; 'd'
0x1800181fb  jl      short loc_1800181D9
0x1800181fd  lea     r14, aWindowsCompatI_19; "Windows::Compat::Inventory::SqliteInvCa"...
0x180018204  mov     rbx, 7FFFFFFFFFFFFFFEh
0x18001820e  cmp     r13d, 64h ; 'd'
0x180018212  jnz     loc_1800185A3
0x180018218  xorps   xmm0, xmm0
0x18001821b  movups  [rsp+150h+var_E8], xmm0
0x180018220  xorps   xmm1, xmm1
0x180018223  movdqu  [rsp+150h+var_D8], xmm1
0x180018229  lea     r8d, [r13-28h]
0x18001822d  lea     rdx, aSelectSqlFromS; "SELECT sql FROM sqlite_master WHERE typ"...
0x180018234  lea     rcx, [rsp+150h+var_E8]
0x180018239  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001823e  nop
0x18001823f  xor     r13d, r13d
0x180018242  test    r12, r12
0x180018245  jz      short loc_180018260
0x180018247  call    cs:__imp_GetLastError
0x18001824d  mov     ebx, eax
0x18001824f  mov     rcx, r12
0x180018252  call    sqlite3_finalize
0x180018257  mov     ecx, ebx; dwErrCode
0x180018259  call    cs:__imp_SetLastError
0x18001825f  nop
0x180018260  mov     [rsp+150h+var_110], r13
0x180018265  lea     rdx, [rsp+150h+var_E8]
0x18001826a  cmp     qword ptr [rbp+50h+var_D8+8], 7
0x18001826f  cmova   rdx, qword ptr [rsp+150h+var_E8]
0x180018275  mov     [rsp+150h+var_128], r13
0x18001827a  lea     rax, [rsp+150h+var_110]
0x18001827f  mov     [rsp+150h+var_130], rax
0x180018284  mov     r9d, 80h
0x18001828a  or      r8d, 0FFFFFFFFh
0x18001828e  mov     rcx, [r15+8]
0x180018292  call    sqlite3Prepare16
0x180018297  mov     ebx, eax
0x180018299  test    eax, eax
0x18001829b  jz      short loc_18001830C
0x18001829d  mov     rcx, [r15+8]
0x1800182a1  call    sqlite3_errmsg
0x1800182a6  mov     [rsp+150h+var_128], rax
0x1800182ab  mov     dword ptr [rsp+150h+var_130], ebx
0x1800182af  lea     r9, aSqlite3Prepare_1; "sqlite3_prepare16_v2 failed: [%d] %hs"
0x1800182b6  mov     r8d, 5B7h
0x1800182bc  mov     rdx, r14
0x1800182bf  mov     ecx, edi
0x1800182c1  call    AslLogCallPrintf
0x1800182c6  test    ebx, ebx
0x1800182c8  jle     short loc_1800182D3
0x1800182ca  movzx   ebx, bx
0x1800182cd  or      ebx, 80070000h
0x1800182d3  lea     rcx, [rsp+150h+var_E8]
0x1800182d8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800182dd  nop
0x1800182de  lea     rcx, [rbp+50h+var_C8]
0x1800182e2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800182e7  nop
0x1800182e8  lea     rcx, [rsp+150h+var_108]
0x1800182ed  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800182f2  nop
0x1800182f3  mov     rcx, [rsp+150h+var_110]
0x1800182f8  test    rcx, rcx
0x1800182fb  jz      loc_18001805F
0x180018301  call    sqlite3_finalize
0x180018306  nop
0x180018307  jmp     loc_18001805F
0x18001830c  cmp     qword ptr [rsi+18h], 7
0x180018311  jbe     short loc_180018316
0x180018313  mov     rsi, [rsi]
0x180018316  mov     byte ptr [rsp+150h+var_128], 2
0x18001831b  mov     [rsp+150h+var_130], r13
0x180018320  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180018327  mov     r8, rsi
0x18001832a  mov     edx, edi
0x18001832c  mov     rsi, [rsp+150h+var_110]
0x180018331  mov     rcx, rsi
0x180018334  call    bindText
0x180018339  mov     ebx, eax
0x18001833b  test    eax, eax
0x18001833d  jz      short loc_1800183AC
0x18001833f  mov     rcx, [r15+8]
0x180018343  call    sqlite3_errmsg
0x180018348  mov     [rsp+150h+var_128], rax
0x18001834d  mov     dword ptr [rsp+150h+var_130], ebx
0x180018351  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x180018358  mov     r8d, 5BDh
0x18001835e  mov     rdx, r14
0x180018361  mov     ecx, edi
0x180018363  call    AslLogCallPrintf
0x180018368  test    ebx, ebx
0x18001836a  jle     short loc_180018375
0x18001836c  movzx   ebx, bx
0x18001836f  or      ebx, 80070000h
0x180018375  lea     rcx, [rsp+150h+var_E8]
0x18001837a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001837f  nop
0x180018380  lea     rcx, [rbp+50h+var_C8]
0x180018384  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018389  nop
0x18001838a  lea     rcx, [rsp+150h+var_108]
0x18001838f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018394  nop
0x180018395  test    rsi, rsi
0x180018398  jz      loc_18001805F
0x18001839e  mov     rcx, rsi
0x1800183a1  call    sqlite3_finalize
0x1800183a6  nop
0x1800183a7  jmp     loc_18001805F
0x1800183ac  mov     r12d, r13d
0x1800183af  mov     rcx, rsi
0x1800183b2  call    sqlite3_step
0x1800183b7  mov     ebx, eax
0x1800183b9  add     eax, 0FFFFFFFBh
0x1800183bc  cmp     eax, edi
0x1800183be  ja      short loc_1800183D4
0x1800183c0  mov     ecx, 5; dwMilliseconds
0x1800183c5  call    cs:__imp_Sleep
0x1800183cb  add     r12d, edi
0x1800183ce  cmp     r12d, 64h ; 'd'
0x1800183d2  jl      short loc_1800183AF
0x1800183d4  cmp     ebx, 64h ; 'd'
0x1800183d7  jz      short loc_180018446
0x1800183d9  mov     rcx, [r15+8]
0x1800183dd  call    sqlite3_errmsg
0x1800183e2  mov     [rsp+150h+var_128], rax
0x1800183e7  mov     dword ptr [rsp+150h+var_130], ebx
0x1800183eb  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x1800183f2  mov     r8d, 5C3h
0x1800183f8  mov     rdx, r14
0x1800183fb  mov     ecx, edi
0x1800183fd  call    AslLogCallPrintf
0x180018402  test    ebx, ebx
0x180018404  jle     short loc_18001840F
0x180018406  movzx   ebx, bx
0x180018409  or      ebx, 80070000h
0x18001840f  lea     rcx, [rsp+150h+var_E8]
0x180018414  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018419  nop
0x18001841a  lea     rcx, [rbp+50h+var_C8]
0x18001841e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180018423  nop
0x180018424  lea     rcx, [rsp+150h+var_108]
0x180018429  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001842e  nop
0x18001842f  test    rsi, rsi
0x180018432  jz      loc_18001805F
0x180018438  mov     rcx, rsi
0x18001843b  call    sqlite3_finalize
0x180018440  nop
0x180018441  jmp     loc_18001805F
0x180018446  xor     edx, edx
0x180018448  mov     rcx, rsi
0x18001844b  call    sqlite3_column_text16
0x180018450  xorps   xmm0, xmm0
0x180018453  movups  [rbp+50h+var_A8], xmm0
0x180018457  mov     [rbp+50h+var_98], r13
0x18001845b  mov     [rbp+50h+var_90], r13
0x18001845f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180018463  inc     r8
0x180018466  cmp     [rax+r8*2], r13w
0x18001846b  jnz     short loc_180018463
  ... truncated ...
```
