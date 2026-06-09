# Windows::Compat::Inventory::SqliteInvCache::CreateTable(void)

- ea: `0x180011d38`
- end: `0x1800122e5`
- name: `?CreateTable@SqliteInvCache@Inventory@Compat@Windows@@AEAAJXZ`
- size: `1453`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::SqliteInvCache *__hidden this)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011620`
- `0x1800159ec`

## callees

- `0x180005890`
- `0x1800081e8`
- `0x1800088e0`
- `0x18000eb38`
- `0x18000ec14`
- `0x18000faf0`
- `0x1800103b0`
- `0x180011d38`
- `0x1800122ec`
- `0x18001c5f0`
- `0x18001c6d8`
- `0x18001c73c`
- `0x1800295dc`
- `0x18003fd34`
- `0x1800870b4`
- `0x1800a40a0`
- `0x1800a5e60`
- `0x1800a6630`

## string_xrefs

- `0x180011d96`: `CreateTableString failed [%#x]`
- `0x1800120a2`: `CREATE TABLE `
- `0x1800121a5`: `CREATE TABLE IF NOT EXISTS `
- `0x180011da3`: `Windows::Compat::Inventory::SqliteInvCache::CreateTable`
- `0x180011e2c`: `Windows::Compat::Inventory::SqliteInvCache::CreateTable`
- `0x180011eb7`: `Windows::Compat::Inventory::SqliteInvCache::CreateTable`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall Windows::Compat::Inventory::SqliteInvCache::CreateTable(
        Windows::Compat::Inventory::SqliteInvCache *this)
{
  int TableString; // eax
  signed int v3; // ebx
  _QWORD *v4; // rdx
  __int64 v5; // rax
  const char *v6; // r9
  __int64 v7; // r8
  const wchar_t *v8; // r15
  const wchar_t *v9; // r8
  Windows::Compat::Inventory *v10; // r12
  struct sqlite3_stmt *v11; // rdx
  int v12; // r8d
  _QWORD *v13; // rdx
  __int64 v14; // rax
  const char *v15; // r9
  __int64 v16; // r8
  _QWORD *v17; // rcx
  int v18; // r8d
  Windows::Compat::Inventory *v19; // r15
  struct sqlite3_stmt *v20; // rdx
  int v21; // r8d
  __int64 v22; // rax
  const char *v23; // r9
  __int64 v24; // r8
  _QWORD *v25; // rcx
  __int64 v26; // rax
  _QWORD *v27; // rdx
  struct sqlite3_stmt *v28; // rdx
  int v29; // r8d
  __int64 v30; // rax
  const char *v31; // r9
  __int64 v32; // r8
  __int64 v33; // rax
  _QWORD *v34; // rdx
  struct sqlite3_stmt *v35; // rdx
  int v36; // r8d
  __int64 v37; // rax
  const char *v38; // r9
  __int64 v39; // r8
  __int64 v41; // [rsp+20h] [rbp-E0h]
  __int64 v42; // [rsp+20h] [rbp-E0h]
  __int64 v43; // [rsp+20h] [rbp-E0h]
  __int64 v44; // [rsp+20h] [rbp-E0h]
  Windows::Compat::Inventory *v45; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v46[8]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v47[4]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v48[4]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v49[16]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v50; // [rsp+90h] [rbp-70h]
  _QWORD v51[4]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v52[4]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v53[2]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v54[32]; // [rsp+100h] [rbp+0h] BYREF

  v45 = 0;
  v53[0] = 0;
  v53[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v53[0]) = 0;
  TableString = Windows::Compat::Inventory::SqliteInvCache::CreateTableString(this, v53);
  v3 = TableString;
  if ( TableString >= 0 )
  {
    std::wstring::wstring(v47, L"SELECT 1 FROM sqlite_master WHERE type='table' AND name=?;");
    v45 = 0;
    v4 = v47;
    if ( v47[3] > 7u )
      LODWORD(v4) = v47[0];
    v3 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v4, -1, 128, (__int64)&v45, 0);
    if ( v3 )
    {
      v5 = sqlite3_errmsg(*((_QWORD *)this + 1));
      v6 = "sqlite3_prepare16_v2 failed: [%d] %hs";
      v7 = 1446;
      goto LABEL_7;
    }
    v8 = (const wchar_t *)((char *)this + 72);
    if ( *((_QWORD *)this + 12) <= 7u )
      LODWORD(v9) = (_DWORD)this + 72;
    else
      v9 = *(const wchar_t **)v8;
    v10 = v45;
    v3 = bindText((_DWORD)v45, 1, (_DWORD)v9, -2, 0, 2);
    if ( v3 )
    {
      v5 = sqlite3_errmsg(*((_QWORD *)this + 1));
      v6 = "sqlite3_bind_text16 failed: [%d] %hs";
      v7 = 1452;
LABEL_7:
      LODWORD(v41) = v3;
      AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::CreateTable", v7, v6, v41, v5);
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      goto LABEL_9;
    }
    if ( (unsigned int)Windows::Compat::Inventory::sqlite3_step_with_retry(v10, v11, v12) == 100 )
    {
      std::wstring::wstring(v48, L"SELECT sql FROM sqlite_master WHERE type='table' AND name=?;");
      if ( v10 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v46);
        sqlite3_finalize(v10);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v46);
      }
      v45 = 0;
      v13 = v48;
      if ( v48[3] > 7u )
        LODWORD(v13) = v48[0];
      v3 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v13, -1, 128, (__int64)&v45, 0);
      if ( v3 )
      {
        v14 = sqlite3_errmsg(*((_QWORD *)this + 1));
        v15 = "sqlite3_prepare16_v2 failed: [%d] %hs";
        v16 = 1463;
        goto LABEL_22;
      }
      if ( *((_QWORD *)this + 12) > 7u )
        v8 = *(const wchar_t **)v8;
      v18 = (int)v8;
      v19 = v45;
      v3 = bindText((_DWORD)v45, 1, v18, -2, 0, 2);
      if ( v3 )
      {
        v14 = sqlite3_errmsg(*((_QWORD *)this + 1));
        v15 = "sqlite3_bind_text16 failed: [%d] %hs";
        v16 = 1469;
        goto LABEL_22;
      }
      v3 = Windows::Compat::Inventory::sqlite3_step_with_retry(v19, v20, v21);
      if ( v3 != 100 )
      {
        v14 = sqlite3_errmsg(*((_QWORD *)this + 1));
        v15 = "sqlite3_step failed: [%d] %hs";
        v16 = 1475;
LABEL_22:
        LODWORD(v42) = v3;
        AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::CreateTable", v16, v15, v42, v14);
        if ( v3 > 0 )
          v3 = (unsigned __int16)v3 | 0x80070000;
        goto LABEL_24;
      }
      v22 = sqlite3_column_text16(v19, 0);
      std::wstring::wstring(v49, v22);
      if ( !v50 )
      {
        v23 = "sqlite3_column_text16 returned a null schema [%#x]";
        v24 = 1482;
LABEL_34:
        v3 = -2147467259;
        LODWORD(v42) = -2147467259;
        AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::CreateTable", v24, v23, v42);
        std::wstring::_Tidy_deallocate(v49);
LABEL_24:
        v17 = v48;
LABEL_25:
        std::wstring::_Tidy_deallocate(v17);
LABEL_9:
        std::wstring::_Tidy_deallocate(v47);
        goto LABEL_64;
      }
      if ( std::wstring::find(v49, v53) == -1 )
      {
        v23 = "Schema mismatch [%#x]";
        v24 = 1488;
        goto LABEL_34;
      }
      std::wstring::_Tidy_deallocate(v49);
      v25 = v48;
LABEL_52:
      std::wstring::_Tidy_deallocate(v25);
      v33 = std::operator+<unsigned short>(v54, L"CREATE TABLE IF NOT EXISTS ", (char *)this + 104);
      std::operator+<unsigned short>(v52, v33, L" (Name TEXT PRIMARY KEY, Value TEXT);");
      std::wstring::_Tidy_deallocate(v54);
      if ( v19 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v46);
        sqlite3_finalize(v19);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v46);
      }
      v45 = 0;
      v34 = v52;
      if ( v52[3] > 7u )
        LODWORD(v34) = v52[0];
      v3 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v34, -1, 128, (__int64)&v45, 0);
      if ( v3 )
      {
        v37 = sqlite3_errmsg(*((_QWORD *)this + 1));
        v38 = "sqlite3_prepare16_v2 failed: [%d] %hs";
        v39 = 1517;
      }
      else
      {
        v3 = Windows::Compat::Inventory::sqlite3_step_with_retry(v45, v35, v36);
        if ( v3 == 101 )
        {
          std::wstring::_Tidy_deallocate(v52);
          std::wstring::_Tidy_deallocate(v47);
          v3 = 0;
          goto LABEL_64;
        }
        v37 = sqlite3_errmsg(*((_QWORD *)this + 1));
        v38 = "sqlite3_step failed: [%d] %hs";
        v39 = 1523;
      }
      LODWORD(v44) = v3;
      AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::CreateTable", v39, v38, v44, v37);
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
      v17 = v52;
      goto LABEL_25;
    }
    if ( *((_QWORD *)this + 12) > 7u )
      v8 = *(const wchar_t **)v8;
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
      1494,
      "Table %ls doesn't exist. Creating new table.",
      v8);
    v26 = std::operator+<unsigned short>(v49, L"CREATE TABLE ", v53);
    std::operator+<unsigned short>(v51, v26, L";");
    std::wstring::_Tidy_deallocate(v49);
    if ( v10 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v46);
      sqlite3_finalize(v10);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v46);
    }
    v45 = 0;
    v27 = v51;
    if ( v51[3] > 7u )
      LODWORD(v27) = v51[0];
    v3 = sqlite3Prepare16(*((_QWORD *)this + 1), (_DWORD)v27, -1, 128, (__int64)&v45, 0);
    if ( v3 )
    {
      v30 = sqlite3_errmsg(*((_QWORD *)this + 1));
      v31 = "sqlite3_prepare16_v2 failed: [%d] %hs";
      v32 = 1501;
    }
    else
    {
      v19 = v45;
      v3 = Windows::Compat::Inventory::sqlite3_step_with_retry(v45, v28, v29);
      if ( v3 == 101 )
      {
        v25 = v51;
        goto LABEL_52;
      }
      v30 = sqlite3_errmsg(*((_QWORD *)this + 1));
      v31 = "sqlite3_step failed: [%d] %hs";
      v32 = 1507;
    }
    LODWORD(v43) = v3;
    AslLogCallPrintf(1, "Windows::Compat::Inventory::SqliteInvCache::CreateTable", v32, v31, v43, v30);
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    v17 = v51;
    goto LABEL_25;
  }
  AslLogCallPrintf(
    1,
    "Windows::Compat::Inventory::SqliteInvCache::CreateTable",
    1438,
    "CreateTableString failed [%#x]",
    TableString);
LABEL_64:
  std::wstring::_Tidy_deallocate(v53);
  wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (*)(sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<sqlite3_stmt *,int (*)(sqlite3_stmt *),&int sqlite3_finalize(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>(&v45);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180011d38  push    rbp
0x180011d3a  push    rbx
0x180011d3b  push    rsi
0x180011d3c  push    rdi
0x180011d3d  push    r12
0x180011d3f  push    r13
0x180011d41  push    r14
0x180011d43  push    r15
0x180011d45  lea     rbp, [rsp-38h]
0x180011d4a  sub     rsp, 138h
0x180011d51  mov     rax, cs:__security_cookie
0x180011d58  xor     rax, rsp
0x180011d5b  mov     [rbp+70h+var_50], rax
0x180011d5f  mov     r14, rcx
0x180011d62  xor     r13d, r13d
0x180011d65  mov     [rsp+170h+var_140], r13
0x180011d6a  xorps   xmm0, xmm0
0x180011d6d  movups  [rbp+70h+var_90], xmm0
0x180011d71  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180011d79  movdqu  [rbp+70h+var_80], xmm1
0x180011d7e  mov     word ptr [rbp+70h+var_90], r13w
0x180011d83  lea     rdx, [rbp+70h+var_90]
0x180011d87  call    ?CreateTableString@SqliteInvCache@Inventory@Compat@Windows@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Compat::Inventory::SqliteInvCache::CreateTableString(std::wstring &)
0x180011d8c  mov     ebx, eax
0x180011d8e  test    eax, eax
0x180011d90  jns     short loc_180011DB8
0x180011d92  mov     dword ptr [rsp+170h+var_150], eax
0x180011d96  lea     r9, aCreatetablestr; "CreateTableString failed [%#x]"
0x180011d9d  mov     r8d, 59Eh
0x180011da3  lea     rdx, aWindowsCompatI_11; "Windows::Compat::Inventory::SqliteInvCa"...
0x180011daa  lea     ecx, [r13+1]
0x180011dae  call    AslLogCallPrintf
0x180011db3  jmp     loc_1800122AF
0x180011db8  lea     rdx, aSelect1FromSql; "SELECT 1 FROM sqlite_master WHERE type="...
0x180011dbf  lea     rcx, [rsp+170h+var_130]
0x180011dc4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011dc9  nop
0x180011dca  mov     [rsp+170h+var_140], r13
0x180011dcf  lea     rdx, [rsp+170h+var_130]
0x180011dd4  cmp     [rsp+170h+var_118], 7
0x180011dda  cmova   rdx, [rsp+170h+var_130]
0x180011de0  mov     [rsp+170h+var_148], r13
0x180011de5  lea     rax, [rsp+170h+var_140]
0x180011dea  mov     [rsp+170h+var_150], rax
0x180011def  mov     r9d, 80h
0x180011df5  or      r8d, 0FFFFFFFFh
0x180011df9  mov     rcx, [r14+8]
0x180011dfd  call    sqlite3Prepare16
0x180011e02  mov     ebx, eax
0x180011e04  test    eax, eax
0x180011e06  jz      short loc_180011E54
0x180011e08  mov     rcx, [r14+8]
0x180011e0c  call    sqlite3_errmsg
0x180011e11  lea     r9, aSqlite3Prepare_1; "sqlite3_prepare16_v2 failed: [%d] %hs"
0x180011e18  mov     r8d, 5A6h
0x180011e1e  mov     ecx, 1
0x180011e23  mov     [rsp+170h+var_148], rax
0x180011e28  mov     dword ptr [rsp+170h+var_150], ebx
0x180011e2c  lea     rdx, aWindowsCompatI_11; "Windows::Compat::Inventory::SqliteInvCa"...
0x180011e33  call    AslLogCallPrintf
0x180011e38  test    ebx, ebx
0x180011e3a  jle     short loc_180011E45
0x180011e3c  movzx   ebx, bx
0x180011e3f  or      ebx, 80070000h
0x180011e45  lea     rcx, [rsp+170h+var_130]
0x180011e4a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180011e4f  jmp     loc_1800122AF
0x180011e54  lea     r15, [r14+48h]
0x180011e58  cmp     qword ptr [r15+18h], 7
0x180011e5d  jbe     short loc_180011E64
0x180011e5f  mov     r8, [r15]
0x180011e62  jmp     short loc_180011E67
0x180011e64  mov     r8, r15
0x180011e67  mov     byte ptr [rsp+170h+var_148], 2
0x180011e6c  mov     [rsp+170h+var_150], r13
0x180011e71  mov     esi, 1
0x180011e76  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180011e7d  mov     edx, esi
0x180011e7f  mov     r12, [rsp+170h+var_140]
0x180011e84  mov     rcx, r12
0x180011e87  call    bindText
0x180011e8c  mov     ebx, eax
0x180011e8e  test    eax, eax
0x180011e90  jz      short loc_180011EAF
0x180011e92  mov     rcx, [r14+8]
0x180011e96  call    sqlite3_errmsg
0x180011e9b  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x180011ea2  mov     r8d, 5ACh
0x180011ea8  mov     ecx, esi
0x180011eaa  jmp     loc_180011E23
0x180011eaf  mov     rcx, r12; this
0x180011eb2  call    ?sqlite3_step_with_retry@Inventory@Compat@Windows@@YAHPEAUsqlite3_stmt@@H@Z; Windows::Compat::Inventory::sqlite3_step_with_retry(sqlite3_stmt *,int)
0x180011eb7  lea     rdi, aWindowsCompatI_11; "Windows::Compat::Inventory::SqliteInvCa"...
0x180011ebe  cmp     eax, 64h ; 'd'
0x180011ec1  jnz     loc_180012075
0x180011ec7  lea     rdx, aSelectSqlFromS; "SELECT sql FROM sqlite_master WHERE typ"...
0x180011ece  lea     rcx, [rsp+170h+var_110]
0x180011ed3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011ed8  nop
0x180011ed9  test    r12, r12
0x180011edc  jz      short loc_180011EFB
0x180011ede  lea     rcx, [rsp+170h+var_138]; this
0x180011ee3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180011ee8  mov     rcx, r12
0x180011eeb  call    sqlite3_finalize
0x180011ef0  lea     rcx, [rsp+170h+var_138]; this
0x180011ef5  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180011efa  nop
0x180011efb  mov     [rsp+170h+var_140], r13
0x180011f00  lea     rdx, [rsp+170h+var_110]
0x180011f05  cmp     [rsp+170h+var_F8], 7
0x180011f0b  cmova   rdx, [rsp+170h+var_110]
0x180011f11  mov     [rsp+170h+var_148], r13
0x180011f16  lea     rax, [rsp+170h+var_140]
0x180011f1b  mov     [rsp+170h+var_150], rax
0x180011f20  mov     r9d, 80h
0x180011f26  or      r8d, 0FFFFFFFFh
0x180011f2a  mov     rcx, [r14+8]
0x180011f2e  call    sqlite3Prepare16
0x180011f33  mov     ebx, eax
0x180011f35  test    eax, eax
0x180011f37  jz      short loc_180011F7E
0x180011f39  mov     rcx, [r14+8]
0x180011f3d  call    sqlite3_errmsg
0x180011f42  lea     r9, aSqlite3Prepare_1; "sqlite3_prepare16_v2 failed: [%d] %hs"
0x180011f49  mov     r8d, 5B7h
0x180011f4f  mov     [rsp+170h+var_148], rax
0x180011f54  mov     dword ptr [rsp+170h+var_150], ebx
0x180011f58  mov     rdx, rdi
0x180011f5b  mov     ecx, esi
0x180011f5d  call    AslLogCallPrintf
0x180011f62  test    ebx, ebx
0x180011f64  jle     short loc_180011F6F
0x180011f66  movzx   ebx, bx
0x180011f69  or      ebx, 80070000h
0x180011f6f  lea     rcx, [rsp+170h+var_110]
0x180011f74  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180011f79  jmp     loc_180011E45
0x180011f7e  cmp     qword ptr [r15+18h], 7
0x180011f83  jbe     short loc_180011F88
0x180011f85  mov     r15, [r15]
0x180011f88  mov     byte ptr [rsp+170h+var_148], 2
0x180011f8d  mov     [rsp+170h+var_150], r13
0x180011f92  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180011f99  mov     r8, r15
0x180011f9c  mov     edx, esi
0x180011f9e  mov     r15, [rsp+170h+var_140]
0x180011fa3  mov     rcx, r15
0x180011fa6  call    bindText
0x180011fab  mov     ebx, eax
0x180011fad  test    eax, eax
0x180011faf  jz      short loc_180011FC9
0x180011fb1  mov     rcx, [r14+8]
0x180011fb5  call    sqlite3_errmsg
0x180011fba  lea     r9, aSqlite3BindTex; "sqlite3_bind_text16 failed: [%d] %hs"
0x180011fc1  mov     r8d, 5BDh
0x180011fc7  jmp     short loc_180011F4F
0x180011fc9  mov     rcx, r15; this
0x180011fcc  call    ?sqlite3_step_with_retry@Inventory@Compat@Windows@@YAHPEAUsqlite3_stmt@@H@Z; Windows::Compat::Inventory::sqlite3_step_with_retry(sqlite3_stmt *,int)
0x180011fd1  mov     ebx, eax
0x180011fd3  cmp     eax, 64h ; 'd'
0x180011fd6  jz      short loc_180011FF3
0x180011fd8  mov     rcx, [r14+8]
0x180011fdc  call    sqlite3_errmsg
0x180011fe1  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x180011fe8  mov     r8d, 5C3h
0x180011fee  jmp     loc_180011F4F
0x180011ff3  xor     edx, edx
0x180011ff5  mov     rcx, r15
0x180011ff8  call    sqlite3_column_text16
0x180011ffd  mov     rdx, rax
0x180012000  lea     rcx, [rbp+70h+var_F0]
0x180012004  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180012009  nop
0x18001200a  cmp     [rbp+70h+var_E0], r13
0x18001200e  jnz     short loc_18001203F
0x180012010  lea     r9, aSqlite3ColumnT; "sqlite3_column_text16 returned a null s"...
0x180012017  mov     r8d, 5CAh
0x18001201d  mov     ebx, 80004005h
0x180012022  mov     dword ptr [rsp+170h+var_150], ebx
0x180012026  mov     rdx, rdi
0x180012029  mov     ecx, esi
0x18001202b  call    AslLogCallPrintf
0x180012030  nop
0x180012031  lea     rcx, [rbp+70h+var_F0]
0x180012035  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001203a  jmp     loc_180011F6F
0x18001203f  lea     rdx, [rbp+70h+var_90]
0x180012043  lea     rcx, [rbp+70h+var_F0]
0x180012047  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x18001204c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012050  jnz     short loc_180012061
0x180012052  lea     r9, aSchemaMismatch; "Schema mismatch [%#x]"
0x180012059  mov     r8d, 5D0h
0x18001205f  jmp     short loc_18001201D
0x180012061  lea     rcx, [rbp+70h+var_F0]
0x180012065  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001206a  nop
0x18001206b  lea     rcx, [rsp+170h+var_110]
0x180012070  jmp     loc_18001219C
0x180012075  cmp     qword ptr [r15+18h], 7
0x18001207a  jbe     short loc_18001207F
0x18001207c  mov     r15, [r15]
0x18001207f  mov     [rsp+170h+var_150], r15
0x180012084  lea     r9, aTableLsDoesnTE; "Table %ls doesn't exist. Creating new t"...
0x18001208b  mov     r8d, 5D6h
0x180012091  mov     rdx, rdi
0x180012094  mov     ecx, 3
0x180012099  call    AslLogCallPrintf
0x18001209e  lea     r8, [rbp+70h+var_90]
0x1800120a2  lea     rdx, aCreateTable; "CREATE TABLE "
0x1800120a9  lea     rcx, [rbp+70h+var_F0]
0x1800120ad  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x1800120b2  nop
0x1800120b3  lea     r8, asc_1800F5830; ";"
0x1800120ba  mov     rdx, rax
0x1800120bd  lea     rcx, [rbp+70h+var_D0]
0x1800120c1  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800120c6  nop
0x1800120c7  lea     rcx, [rbp+70h+var_F0]
0x1800120cb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800120d0  test    r12, r12
0x1800120d3  jz      short loc_1800120F2
0x1800120d5  lea     rcx, [rsp+170h+var_138]; this
0x1800120da  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800120df  mov     rcx, r12
0x1800120e2  call    sqlite3_finalize
0x1800120e7  lea     rcx, [rsp+170h+var_138]; this
0x1800120ec  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800120f1  nop
0x1800120f2  mov     [rsp+170h+var_140], r13
0x1800120f7  lea     rdx, [rbp+70h+var_D0]
0x1800120fb  cmp     [rbp+70h+var_B8], 7
0x180012100  cmova   rdx, [rbp+70h+var_D0]
0x180012105  mov     [rsp+170h+var_148], r13
0x18001210a  lea     rax, [rsp+170h+var_140]
0x18001210f  mov     [rsp+170h+var_150], rax
0x180012114  mov     r9d, 80h
0x18001211a  or      r8d, 0FFFFFFFFh
0x18001211e  mov     rcx, [r14+8]
0x180012122  call    sqlite3Prepare16
0x180012127  mov     ebx, eax
0x180012129  test    eax, eax
0x18001212b  jz      short loc_18001216C
0x18001212d  mov     rcx, [r14+8]
0x180012131  call    sqlite3_errmsg
0x180012136  lea     r9, aSqlite3Prepare_1; "sqlite3_prepare16_v2 failed: [%d] %hs"
0x18001213d  mov     r8d, 5DDh
0x180012143  mov     [rsp+170h+var_148], rax
0x180012148  mov     dword ptr [rsp+170h+var_150], ebx
0x18001214c  mov     rdx, rdi
0x18001214f  mov     ecx, esi
0x180012151  call    AslLogCallPrintf
0x180012156  test    ebx, ebx
0x180012158  jle     short loc_180012163
0x18001215a  movzx   ebx, bx
0x18001215d  or      ebx, 80070000h
0x180012163  lea     rcx, [rbp+70h+var_D0]
0x180012167  jmp     loc_180011F74
0x18001216c  mov     r15, [rsp+170h+var_140]
0x180012171  mov     rcx, r15; this
0x180012174  call    ?sqlite3_step_with_retry@Inventory@Compat@Windows@@YAHPEAUsqlite3_stmt@@H@Z; Windows::Compat::Inventory::sqlite3_step_with_retry(sqlite3_stmt *,int)
0x180012179  mov     ebx, eax
0x18001217b  cmp     eax, 65h ; 'e'
0x18001217e  jz      short loc_180012198
0x180012180  mov     rcx, [r14+8]
0x180012184  call    sqlite3_errmsg
0x180012189  lea     r9, aSqlite3StepFai; "sqlite3_step failed: [%d] %hs"
0x180012190  mov     r8d, 5E3h
0x180012196  jmp     short loc_180012143
0x180012198  lea     rcx, [rbp+70h+var_D0]
0x18001219c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800121a1  lea     r8, [r14+68h]
0x1800121a5  lea     rdx, aCreateTableIfN; "CREATE TABLE IF NOT EXISTS "
0x1800121ac  lea     rcx, [rbp+70h+var_70]
0x1800121b0  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x1800121b5  nop
0x1800121b6  lea     r8, aNameTextPrimar; " (Name TEXT PRIMARY KEY, Value TEXT);"
0x1800121bd  mov     rdx, rax
0x1800121c0  lea     rcx, [rbp+70h+var_B0]
0x1800121c4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800121c9  nop
0x1800121ca  lea     rcx, [rbp+70h+var_70]
0x1800121ce  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800121d3  test    r15, r15
0x1800121d6  jz      short loc_1800121F5
0x1800121d8  lea     rcx, [rsp+170h+var_138]; this
0x1800121dd  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800121e2  mov     rcx, r15
0x1800121e5  call    sqlite3_finalize
0x1800121ea  lea     rcx, [rsp+170h+var_138]; this
0x1800121ef  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800121f4  nop
0x1800121f5  mov     [rsp+170h+var_140], r13
0x1800121fa  lea     rdx, [rbp+70h+var_B0]
0x1800121fe  cmp     [rbp+70h+var_98], 7
0x180012203  cmova   rdx, [rbp+70h+var_B0]
0x180012208  mov     [rsp+170h+var_148], r13
0x18001220d  lea     rax, [rsp+170h+var_140]
0x180012212  mov     [rsp+170h+var_150], rax
  ... truncated ...
```
