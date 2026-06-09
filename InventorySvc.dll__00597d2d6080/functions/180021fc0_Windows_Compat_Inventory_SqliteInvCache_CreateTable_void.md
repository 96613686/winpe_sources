# Windows::Compat::Inventory::SqliteInvCache::CreateTable(void)

- ea: `0x180021fc0`
- end: `0x1800229c2`
- name: `?CreateTable@SqliteInvCache@Inventory@Compat@Windows@@AEAAJXZ`
- size: `2562`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this)`
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180021940`
- `0x180026f28`

## callees

- `0x180002bf0`
- `0x180005140`
- `0x180006a04`
- `0x1800074f0`
- `0x1800109dc`
- `0x1800152d0`
- `0x18001f4a4`
- `0x18001fd88`
- `0x180021fc0`
- `0x1800229c8`
- `0x180036be4`
- `0x1800817cc`
- `0x18009f9e0`
- `0x1800a1980`
- `0x1800a22c0`
- `0x1800a4690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022245`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002263b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022819`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022245`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002263b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180022819`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022629`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022807`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022629`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022807`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800221dc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800223b1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002270c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800228e7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800221dc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800223b1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002270c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800228e7`

## string_xrefs

- `0x180022022`: `CreateTableString failed [%#x]`
- `0x1800225f1`: `CREATE TABLE `
- `0x1800227d3`: `CREATE TABLE IF NOT EXISTS `
- `0x18002202f`: `Windows::Compat::Inventory::SqliteInvCache::CreateTable`
- `0x1800220d2`: `Windows::Compat::Inventory::SqliteInvCache::CreateTable`
- `0x18002217b`: `Windows::Compat::Inventory::SqliteInvCache::CreateTable`
- `0x1800221e9`: `Windows::Compat::Inventory::SqliteInvCache::CreateTable`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
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
  __int64 v22; // rax
  __int64 v23; // r8
  __int128 *v24; // r8
  __int128 *v25; // r12
  char *v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int128 *v30; // rax
  DWORD v31; // ebx
  __int128 *v32; // rdx
  const char *v33; // rax
  int k; // r12d
  const char *v35; // rax
  __int64 v36; // r8
  _QWORD *v37; // rax
  unsigned __int64 v38; // rdx
  DWORD v39; // ebx
  _QWORD *v40; // rdx
  const char *v41; // rax
  int m; // r12d
  const char *v43; // rax
  __int64 v44; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v45; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v46; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v47; // [rsp+60h] [rbp-A0h]
  __int128 v48; // [rsp+68h] [rbp-98h] BYREF
  __int128 v49; // [rsp+78h] [rbp-88h]
  __int128 v50; // [rsp+88h] [rbp-78h] BYREF
  __int128 v51; // [rsp+98h] [rbp-68h]
  __int128 v52; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v53; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v54; // [rsp+C0h] [rbp-40h]
  _QWORD v55[4]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v56[32]; // [rsp+E8h] [rbp-18h] BYREF

  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 7;
  LOWORD(v45) = 0;
  v2 = Windows::Compat::Inventory::SqliteInvCache::CreateTableString(this, &v45);
  v3 = v2;
  if ( v2 < 0 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
      1438,
      "CreateTableString failed [%#x]",
      v2);
    std::wstring::~wstring(&v45);
    return (unsigned int)v3;
  }
  v50 = 0;
  v51 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v50);
  v44 = 0;
  v5 = &v50;
  if ( *((_QWORD *)&v51 + 1) > 7u )
    LODWORD(v5) = v50;
  v3 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v5, -1, 128, (__int64)&v44, 0);
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
    std::wstring::~wstring(&v50);
    std::wstring::~wstring(&v45);
    v7 = v44;
    if ( !v44 )
      return (unsigned int)v3;
    goto LABEL_97;
  }
  v8 = (const wchar_t *)((char *)this + 72);
  if ( *((_QWORD *)this + 12) <= 7u )
    LODWORD(v9) = (_DWORD)this + 72;
  else
    v9 = *(const wchar_t **)v8;
  v10 = v44;
  v3 = bindText(v44, 1, (_DWORD)v9, -2, 0, 2);
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
    std::wstring::~wstring(&v50);
    std::wstring::~wstring(&v45);
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
    v48 = 0;
    v49 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v48);
    if ( v10 )
    {
      LastError = GetLastError();
      sqlite3_finalize(v10);
      SetLastError(LastError);
    }
    v44 = 0;
    v15 = &v48;
    if ( *((_QWORD *)&v49 + 1) > 7u )
      LODWORD(v15) = v48;
    v3 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v15, -1, 128, (__int64)&v44, 0);
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
      std::wstring::~wstring(&v48);
      std::wstring::~wstring(&v50);
      std::wstring::~wstring(&v45);
      v7 = v44;
      if ( !v44 )
        return (unsigned int)v3;
      goto LABEL_97;
    }
    if ( *((_QWORD *)this + 12) > 7u )
      v8 = *(const wchar_t **)v8;
    v17 = (int)v8;
    v18 = v44;
    v3 = bindText(v44, 1, v17, -2, 0, 2);
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
      std::wstring::~wstring(&v48);
      std::wstring::~wstring(&v50);
      std::wstring::~wstring(&v45);
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
      std::wstring::~wstring(&v48);
      std::wstring::~wstring(&v50);
      std::wstring::~wstring(&v45);
      if ( !v18 )
        return (unsigned int)v3;
      goto LABEL_105;
    }
    v22 = sqlite3_column_text16(v18, 0);
    v52 = 0;
    v53 = 0;
    v54 = 0;
    v23 = -1;
    do
      ++v23;
    while ( *(_WORD *)(v22 + 2 * v23) );
    std::wstring::_Construct<1,unsigned short const *>(&v52);
    if ( !v53 )
    {
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
        1482,
        "sqlite3_column_text16 returned a null schema [%#x]",
        -2147467259);
      std::wstring::~wstring(&v52);
      std::wstring::~wstring(&v48);
      std::wstring::~wstring(&v50);
      std::wstring::~wstring(&v45);
      if ( v18 )
        goto LABEL_62;
      return 2147500037LL;
    }
    v24 = &v45;
    if ( v47 > 7 )
      v24 = (__int128 *)v45;
    v25 = &v52;
    if ( v54 > 7 )
      v25 = (__int128 *)v52;
    if ( v46 > v53
      || v46
      && ((v26 = (char *)v25 + 2 * v53, v27 = _std_search_2(v25, v26, v24), (char *)v27 == v26)
       || (v27 - (__int64)v25) >> 1 == -1) )
    {
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
        1488,
        "Schema mismatch [%#x]",
        -2147467259);
      std::wstring::~wstring(&v52);
      std::wstring::~wstring(&v48);
      std::wstring::~wstring(&v50);
      std::wstring::~wstring(&v45);
      if ( v18 )
LABEL_62:
        sqlite3_finalize(v18);
      return 2147500037LL;
    }
    std::wstring::~wstring(&v52);
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
    if ( 0x7FFFFFFFFFFFFFFELL - v46 < 0xD )
      std::_Xlen_string();
    v30 = &v45;
    if ( v47 > 7 )
      v30 = (__int128 *)v45;
    std::wstring::wstring(v56, v28, v29, L"CREATE TABLE ", 13, v30, v46);
    std::operator+<unsigned short>(&v48, v56, L";");
    std::wstring::~wstring(v56);
    if ( v10 )
    {
      v31 = GetLastError();
      sqlite3_finalize(v10);
      SetLastError(v31);
    }
    v44 = 0;
    v32 = &v48;
    if ( *((_QWORD *)&v49 + 1) > 7u )
      LODWORD(v32) = v48;
    v3 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v32, -1, 128, (__int64)&v44, 0);
    if ( v3 )
    {
      v33 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
        1501,
        "sqlite3_prepare16_v2 failed: [%d] %hs",
        v3,
        v33);
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      std::wstring::~wstring(&v48);
      std::wstring::~wstring(&v50);
      std::wstring::~wstring(&v45);
      v7 = v44;
      if ( !v44 )
        return (unsigned int)v3;
LABEL_97:
      sqlite3_finalize(v7);
      return (unsigned int)v3;
    }
    v18 = v44;
    for ( k = 0; k < 100; ++k )
    {
      v3 = sqlite3_step(v18);
      if ( (unsigned int)(v3 - 5) > 1 )
        break;
      Sleep(5u);
    }
    if ( v3 != 101 )
    {
      v35 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
        1507,
        "sqlite3_step failed: [%d] %hs",
        v3,
        v35);
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      std::wstring::~wstring(&v48);
      std::wstring::~wstring(&v50);
      std::wstring::~wstring(&v45);
      if ( !v18 )
        return (unsigned int)v3;
LABEL_105:
      sqlite3_finalize(v18);
      return (unsigned int)v3;
    }
  }
  std::wstring::~wstring(&v48);
  v37 = (_QWORD *)((char *)this + 104);
  v38 = 0x7FFFFFFFFFFFFFFELL - *((_QWORD *)this + 15);
  if ( v38 < 0x1B )
    std::_Xlen_string();
  if ( *((_QWORD *)this + 16) > 7u )
    v37 = (_QWORD *)*v37;
  std::wstring::wstring(v56, v38, v36, L"CREATE TABLE IF NOT EXISTS ", 27, v37, *((_QWORD *)this + 15));
  std::operator+<unsigned short>(v55, v56, L" (Name TEXT PRIMARY KEY, Value TEXT);");
  std::wstring::~wstring(v56);
  if ( v18 )
  {
    v39 = GetLastError();
    sqlite3_finalize(v18);
    SetLastError(v39);
  }
  v44 = 0;
  v40 = v55;
  if ( v55[3] > 7u )
    LODWORD(v40) = v55[0];
  v3 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v40, -1, 128, (__int64)&v44, 0);
  if ( v3 )
  {
    v41 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
      1517,
      "sqlite3_prepare16_v2 failed: [%d] %hs",
      v3,
      v41);
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    std::wstring::~wstring(v55);
    std::wstring::~wstring(&v50);
    std::wstring::~wstring(&v45);
    v7 = v44;
    if ( !v44 )
      return (unsigned int)v3;
    goto LABEL_97;
  }
  v18 = v44;
  for ( m = 0; m < 100; ++m )
  {
    v3 = sqlite3_step(v18);
    if ( (unsigned int)(v3 - 5) > 1 )
      break;
    Sleep(5u);
  }
  if ( v3 != 101 )
  {
    v43 = (const char *)sqlite3_errmsg(*((_QWORD *)this + 1));
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
      1523,
      "sqlite3_step failed: [%d] %hs",
      v3,
      v43);
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    std::wstring::~wstring(v55);
    std::wstring::~wstring(&v50);
    std::wstring::~wstring(&v45);
    if ( !v18 )
      return (unsigned int)v3;
    goto LABEL_105;
  }
  std::wstring::~wstring(v55);
  std::wstring::~wstring(&v50);
  std::wstring::~wstring(&v45);
  if ( v18 )
    sqlite3_finalize(v18);
  return 0;
}

```

## disassembly

```asm
0x180021fc0  push    rbp
0x180021fc2  push    rbx
0x180021fc3  push    rsi
0x180021fc4  push    rdi
0x180021fc5  push    r12
0x180021fc7  push    r13
0x180021fc9  push    r14
0x180021fcb  push    r15
0x180021fcd  lea     rbp, [rsp-18h]
0x180021fd2  sub     rsp, 118h
0x180021fd9  mov     rax, cs:__security_cookie
0x180021fe0  xor     rax, rsp
0x180021fe3  mov     [rbp+50h+var_48], rax
0x180021fe7  mov     r15, rcx
0x180021fea  xor     r13d, r13d
0x180021fed  mov     [rsp+150h+var_110], r13
0x180021ff2  xorps   xmm0, xmm0
0x180021ff5  movups  [rsp+150h+var_108], xmm0
0x180021ffa  mov     [rsp+150h+var_F8], r13
0x180021fff  mov     [rsp+150h+var_F0], 7
0x180022008  mov     word ptr [rsp+150h+var_108], r13w
0x18002200e  lea     rdx, [rsp+150h+var_108]
0x180022013  call    ?CreateTableString@SqliteInvCache@Inventory@Compat@Windows@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Compat::Inventory::SqliteInvCache::CreateTableString(std::wstring &)
0x180022018  mov     ebx, eax
0x18002201a  test    eax, eax
0x18002201c  jns     short loc_180022052
0x18002201e  mov     dword ptr [rsp+150h+var_130], eax
0x180022022  lea     r9, aCreatetablestr; "CreateTableString failed [%#x]"
0x180022029  mov     r8d, 59Eh
0x18002202f  lea     rdx, aWindowsCompatI_40; "Windows::Compat::Inventory::SqliteInvCa"...
0x180022036  lea     ecx, [r13+1]
0x18002203a  call    AslLogCallPrintf
0x18002203f  nop
0x180022040  lea     rcx, [rsp+150h+var_108]; void *
0x180022045  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002204a  nop
0x18002204b  mov     eax, ebx
0x18002204d  jmp     loc_180022996
0x180022052  xorps   xmm0, xmm0
0x180022055  movups  [rbp+50h+var_C8], xmm0
0x180022059  xorps   xmm1, xmm1
0x18002205c  movdqu  [rbp+50h+var_B8], xmm1
0x180022061  mov     r8d, 3Ah ; ':'
0x180022067  lea     rdx, aSelect1FromSql; "SELECT 1 FROM sqlite_master WHERE type="...
0x18002206e  lea     rcx, [rbp+50h+var_C8]
0x180022072  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180022077  nop
0x180022078  mov     [rsp+150h+var_110], r13
0x18002207d  lea     rdx, [rbp+50h+var_C8]
0x180022081  cmp     qword ptr [rbp+50h+var_B8+8], 7
0x180022086  cmova   rdx, qword ptr [rbp+50h+var_C8]
0x18002208b  mov     [rsp+150h+var_128], r13
0x180022090  lea     rax, [rsp+150h+var_110]
0x180022095  mov     [rsp+150h+var_130], rax
0x18002209a  mov     r9d, 80h
0x1800220a0  or      r8d, 0FFFFFFFFh
0x1800220a4  mov     rcx, [r15+8]
0x1800220a8  call    sqlite3Prepare16
0x1800220ad  mov     ebx, eax
0x1800220af  test    eax, eax
0x1800220b1  jz      short loc_18002211E
0x1800220b3  mov     rcx, [r15+8]
0x1800220b7  call    sqlite3_errmsg
0x1800220bc  mov     [rsp+150h+var_128], rax
0x1800220c1  mov     dword ptr [rsp+150h+var_130], ebx
0x1800220c5  lea     r9, aSqlite3Prepare_1; "sqlite3_prepare16_v2 failed: [%d] %hs"
0x1800220cc  mov     r8d, 5A6h
0x1800220d2  lea     rdx, aWindowsCompatI_40; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800220d9  mov     ecx, 1
0x1800220de  call    AslLogCallPrintf
0x1800220e3  test    ebx, ebx
0x1800220e5  jle     short loc_1800220F0
0x1800220e7  movzx   ebx, bx
0x1800220ea  or      ebx, 80070000h
0x1800220f0  lea     rcx, [rbp+50h+var_C8]; void *
0x1800220f4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800220f9  nop
0x1800220fa  lea     rcx, [rsp+150h+var_108]; void *
0x1800220ff  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022104  nop
0x180022105  mov     rcx, [rsp+150h+var_110]
0x18002210a  test    rcx, rcx
0x18002210d  jz      loc_18002204B
0x180022113  call    sqlite3_finalize
0x180022118  nop
0x180022119  jmp     loc_18002204B
0x18002211e  lea     rsi, [r15+48h]
0x180022122  cmp     qword ptr [rsi+18h], 7
0x180022127  jbe     short loc_18002212E
0x180022129  mov     r8, [rsi]
0x18002212c  jmp     short loc_180022131
0x18002212e  mov     r8, rsi
0x180022131  mov     byte ptr [rsp+150h+var_128], 2
0x180022136  mov     [rsp+150h+var_130], r13
0x18002213b  mov     edi, 1
0x180022140  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180022147  mov     edx, edi
0x180022149  mov     r12, [rsp+150h+var_110]
0x18002214e  mov     rcx, r12
0x180022151  call    bindText
0x180022156  mov     ebx, eax
0x180022158  test    eax, eax
0x18002215a  jz      short loc_1800221C2
0x18002215c  mov     rcx, [r15+8]
0x180022160  call    sqlite3_errmsg
0x180022165  mov     [rsp+150h+var_128], rax
0x18002216a  mov     dword ptr [rsp+150h+var_130], ebx
0x18002216e  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x180022175  mov     r8d, 5ACh
0x18002217b  lea     rdx, aWindowsCompatI_40; "Windows::Compat::Inventory::SqliteInvCa"...
0x180022182  mov     ecx, edi
0x180022184  call    AslLogCallPrintf
0x180022189  test    ebx, ebx
0x18002218b  jle     short loc_180022196
0x18002218d  movzx   ebx, bx
0x180022190  or      ebx, 80070000h
0x180022196  lea     rcx, [rbp+50h+var_C8]; void *
0x18002219a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002219f  nop
0x1800221a0  lea     rcx, [rsp+150h+var_108]; void *
0x1800221a5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800221aa  nop
0x1800221ab  test    r12, r12
0x1800221ae  jz      loc_18002204B
0x1800221b4  mov     rcx, r12
0x1800221b7  call    sqlite3_finalize
0x1800221bc  nop
0x1800221bd  jmp     loc_18002204B
0x1800221c2  mov     ebx, r13d
0x1800221c5  mov     rcx, r12
0x1800221c8  call    sqlite3_step
0x1800221cd  mov     r13d, eax
0x1800221d0  lea     ecx, [rax-5]
0x1800221d3  cmp     ecx, edi
0x1800221d5  ja      short loc_1800221E9
0x1800221d7  mov     ecx, 5; dwMilliseconds
0x1800221dc  call    cs:__imp_Sleep
0x1800221e2  add     ebx, edi
0x1800221e4  cmp     ebx, 64h ; 'd'
0x1800221e7  jl      short loc_1800221C5
0x1800221e9  lea     r14, aWindowsCompatI_40; "Windows::Compat::Inventory::SqliteInvCa"...
0x1800221f0  mov     rbx, 7FFFFFFFFFFFFFFEh
0x1800221fa  cmp     r13d, 64h ; 'd'
0x1800221fe  jnz     loc_18002258F
0x180022204  xorps   xmm0, xmm0
0x180022207  movups  [rsp+150h+var_E8], xmm0
0x18002220c  xorps   xmm1, xmm1
0x18002220f  movdqu  [rsp+150h+var_D8], xmm1
0x180022215  lea     r8d, [r13-28h]
0x180022219  lea     rdx, aSelectSqlFromS; "SELECT sql FROM sqlite_master WHERE typ"...
0x180022220  lea     rcx, [rsp+150h+var_E8]
0x180022225  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002222a  nop
0x18002222b  xor     r13d, r13d
0x18002222e  test    r12, r12
0x180022231  jz      short loc_18002224C
0x180022233  call    cs:__imp_GetLastError
0x180022239  mov     ebx, eax
0x18002223b  mov     rcx, r12
0x18002223e  call    sqlite3_finalize
0x180022243  mov     ecx, ebx; dwErrCode
0x180022245  call    cs:__imp_SetLastError
0x18002224b  nop
0x18002224c  mov     [rsp+150h+var_110], r13
0x180022251  lea     rdx, [rsp+150h+var_E8]
0x180022256  cmp     qword ptr [rbp+50h+var_D8+8], 7
0x18002225b  cmova   rdx, qword ptr [rsp+150h+var_E8]
0x180022261  mov     [rsp+150h+var_128], r13
0x180022266  lea     rax, [rsp+150h+var_110]
0x18002226b  mov     [rsp+150h+var_130], rax
0x180022270  mov     r9d, 80h
0x180022276  or      r8d, 0FFFFFFFFh
0x18002227a  mov     rcx, [r15+8]
0x18002227e  call    sqlite3Prepare16
0x180022283  mov     ebx, eax
0x180022285  test    eax, eax
0x180022287  jz      short loc_1800222F8
0x180022289  mov     rcx, [r15+8]
0x18002228d  call    sqlite3_errmsg
0x180022292  mov     [rsp+150h+var_128], rax
0x180022297  mov     dword ptr [rsp+150h+var_130], ebx
0x18002229b  lea     r9, aSqlite3Prepare_1; "sqlite3_prepare16_v2 failed: [%d] %hs"
0x1800222a2  mov     r8d, 5B7h
0x1800222a8  mov     rdx, r14
0x1800222ab  mov     ecx, edi
0x1800222ad  call    AslLogCallPrintf
0x1800222b2  test    ebx, ebx
0x1800222b4  jle     short loc_1800222BF
0x1800222b6  movzx   ebx, bx
0x1800222b9  or      ebx, 80070000h
0x1800222bf  lea     rcx, [rsp+150h+var_E8]; void *
0x1800222c4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800222c9  nop
0x1800222ca  lea     rcx, [rbp+50h+var_C8]; void *
0x1800222ce  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800222d3  nop
0x1800222d4  lea     rcx, [rsp+150h+var_108]; void *
0x1800222d9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800222de  nop
0x1800222df  mov     rcx, [rsp+150h+var_110]
0x1800222e4  test    rcx, rcx
0x1800222e7  jz      loc_18002204B
0x1800222ed  call    sqlite3_finalize
0x1800222f2  nop
0x1800222f3  jmp     loc_18002204B
0x1800222f8  cmp     qword ptr [rsi+18h], 7
0x1800222fd  jbe     short loc_180022302
0x1800222ff  mov     rsi, [rsi]
0x180022302  mov     byte ptr [rsp+150h+var_128], 2
0x180022307  mov     [rsp+150h+var_130], r13
0x18002230c  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180022313  mov     r8, rsi
0x180022316  mov     edx, edi
0x180022318  mov     rsi, [rsp+150h+var_110]
0x18002231d  mov     rcx, rsi
0x180022320  call    bindText
0x180022325  mov     ebx, eax
0x180022327  test    eax, eax
0x180022329  jz      short loc_180022398
0x18002232b  mov     rcx, [r15+8]
0x18002232f  call    sqlite3_errmsg
0x180022334  mov     [rsp+150h+var_128], rax
0x180022339  mov     dword ptr [rsp+150h+var_130], ebx
0x18002233d  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x180022344  mov     r8d, 5BDh
0x18002234a  mov     rdx, r14
0x18002234d  mov     ecx, edi
0x18002234f  call    AslLogCallPrintf
0x180022354  test    ebx, ebx
0x180022356  jle     short loc_180022361
0x180022358  movzx   ebx, bx
0x18002235b  or      ebx, 80070000h
0x180022361  lea     rcx, [rsp+150h+var_E8]; void *
0x180022366  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002236b  nop
0x18002236c  lea     rcx, [rbp+50h+var_C8]; void *
0x180022370  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022375  nop
0x180022376  lea     rcx, [rsp+150h+var_108]; void *
0x18002237b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022380  nop
0x180022381  test    rsi, rsi
0x180022384  jz      loc_18002204B
0x18002238a  mov     rcx, rsi
0x18002238d  call    sqlite3_finalize
0x180022392  nop
0x180022393  jmp     loc_18002204B
0x180022398  mov     r12d, r13d
0x18002239b  mov     rcx, rsi
0x18002239e  call    sqlite3_step
0x1800223a3  mov     ebx, eax
0x1800223a5  add     eax, 0FFFFFFFBh
0x1800223a8  cmp     eax, edi
0x1800223aa  ja      short loc_1800223C0
0x1800223ac  mov     ecx, 5; dwMilliseconds
0x1800223b1  call    cs:__imp_Sleep
0x1800223b7  add     r12d, edi
0x1800223ba  cmp     r12d, 64h ; 'd'
0x1800223be  jl      short loc_18002239B
0x1800223c0  cmp     ebx, 64h ; 'd'
0x1800223c3  jz      short loc_180022432
0x1800223c5  mov     rcx, [r15+8]
0x1800223c9  call    sqlite3_errmsg
0x1800223ce  mov     [rsp+150h+var_128], rax
0x1800223d3  mov     dword ptr [rsp+150h+var_130], ebx
0x1800223d7  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x1800223de  mov     r8d, 5C3h
0x1800223e4  mov     rdx, r14
0x1800223e7  mov     ecx, edi
0x1800223e9  call    AslLogCallPrintf
0x1800223ee  test    ebx, ebx
0x1800223f0  jle     short loc_1800223FB
0x1800223f2  movzx   ebx, bx
0x1800223f5  or      ebx, 80070000h
0x1800223fb  lea     rcx, [rsp+150h+var_E8]; void *
0x180022400  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022405  nop
0x180022406  lea     rcx, [rbp+50h+var_C8]; void *
0x18002240a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002240f  nop
0x180022410  lea     rcx, [rsp+150h+var_108]; void *
0x180022415  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002241a  nop
0x18002241b  test    rsi, rsi
0x18002241e  jz      loc_18002204B
0x180022424  mov     rcx, rsi
0x180022427  call    sqlite3_finalize
0x18002242c  nop
0x18002242d  jmp     loc_18002204B
0x180022432  xor     edx, edx
0x180022434  mov     rcx, rsi
0x180022437  call    sqlite3_column_text16
0x18002243c  xorps   xmm0, xmm0
0x18002243f  movups  [rbp+50h+var_A8], xmm0
0x180022443  mov     [rbp+50h+var_98], r13
0x180022447  mov     [rbp+50h+var_90], r13
0x18002244b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002244f  inc     r8
0x180022452  cmp     [rax+r8*2], r13w
0x180022457  jnz     short loc_18002244F
  ... truncated ...
```
