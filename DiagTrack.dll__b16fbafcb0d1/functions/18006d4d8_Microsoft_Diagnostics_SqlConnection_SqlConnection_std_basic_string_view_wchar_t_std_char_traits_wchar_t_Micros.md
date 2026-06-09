# Microsoft::Diagnostics::SqlConnection::SqlConnection(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,Microsoft::Diagnostics::SqlConnection::Options const &)

- ea: `0x18006d4d8`
- end: `0x18006d8a7`
- name: `??0SqlConnection@Diagnostics@Microsoft@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBUOptions@012@@Z`
- size: `975`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006d398`
- `0x1801ca5e0`

## callees

- `0x180027c28`
- `0x180027e50`
- `0x18002ac10`
- `0x18002b7c0`
- `0x18002df00`
- `0x18004f6d0`
- `0x18004fdb0`
- `0x180050d08`
- `0x1800520d8`
- `0x180061f68`
- `0x1800624ac`
- `0x1800626a8`
- `0x18006d2fc`
- `0x18006d4d8`
- `0x18006dd6c`
- `0x18009c8c0`
- `0x1800bfc24`
- `0x1801a9494`
- `0x18020aac0`
- `0x1802b3d2c`
- `0x1802b3fd4`

## import_xrefs

- `winsqlite3!sqlite3_column_count` at `0x18006d738`
- `winsqlite3!sqlite3_column_count` at `0x18006d738`
- `winsqlite3!sqlite3_prepare_v2` at `0x18006d6fb`
- `winsqlite3!sqlite3_prepare_v2` at `0x18006d6fb`
- `winsqlite3!sqlite3_open16` at `0x18006d5cf`
- `winsqlite3!sqlite3_open16` at `0x18006d5cf`
- `winsqlite3!sqlite3_open` at `0x18006d64a`
- `winsqlite3!sqlite3_open` at `0x18006d64a`
- `winsqlite3!sqlite3_open_v2` at `0x18006d663`
- `winsqlite3!sqlite3_open_v2` at `0x18006d663`
- `winsqlite3!sqlite3_extended_result_codes` at `0x18006d851`
- `winsqlite3!sqlite3_extended_result_codes` at `0x18006d851`

## string_xrefs

- `0x18006d595`: `onecore\base\telemetry\utc\service\include\Sqlite.h`
- `0x18006d722`: `onecore\base\telemetry\utc\service\include\Sqlite.h`
- `0x18006d7fd`: `onecore\base\telemetry\utc\service\include\Sqlite.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
Microsoft::Diagnostics::SqlConnection *__fastcall Microsoft::Diagnostics::SqlConnection::SqlConnection(
        Microsoft::Diagnostics::SqlConnection *this,
        __int64 a2,
        _BYTE *a3)
{
  _QWORD *v6; // rdi
  __int64 v7; // r8
  __int64 v8; // r12
  void *appended; // rax
  char *v10; // r15
  char **v11; // r13
  char *v12; // rbx
  _QWORD *v13; // rcx
  unsigned int v14; // eax
  int v15; // eax
  __int64 v16; // r8
  __int128 v17; // xmm6
  char **v18; // rcx
  unsigned int v19; // eax
  int v20; // eax
  char *v21; // rdi
  char *v22; // rbx
  unsigned int v23; // eax
  int v24; // eax
  __int64 v25; // rax
  _QWORD *v26; // rax
  char **v27; // rcx
  const char *v28; // rax
  __int64 *v29; // rdi
  __int64 v30; // rbx
  unsigned int v31; // eax
  int v33; // [rsp+28h] [rbp-E0h]
  char *v34[2]; // [rsp+38h] [rbp-D0h] BYREF
  char v35; // [rsp+50h] [rbp-B8h]
  _BYTE v36[16]; // [rsp+60h] [rbp-A8h] BYREF
  _BYTE v37[24]; // [rsp+70h] [rbp-98h] BYREF
  Microsoft::Diagnostics::SqlConnection *v38; // [rsp+88h] [rbp-80h]
  char *v39[2]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v40; // [rsp+A0h] [rbp-68h]
  unsigned __int64 v41; // [rsp+A8h] [rbp-60h]
  struct sqlite3_stmt *v42; // [rsp+B0h] [rbp-58h] BYREF
  _QWORD v43[4]; // [rsp+B8h] [rbp-50h] BYREF
  unsigned int v44; // [rsp+D8h] [rbp-30h]
  _QWORD Src[6]; // [rsp+E0h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]

  v38 = this;
  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_BYTE *)this + 32) = 0;
  v6 = (_QWORD *)((char *)this + 40);
  std::wstring::wstring((char *)this + 40, a2);
  Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)Src);
  v8 = *(_QWORD *)(a2 + 8);
  if ( v8 )
  {
    *(_OWORD *)v34 = *(_OWORD *)a2;
    appended = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(Src);
    Microsoft::Diagnostics::WideStringStream::operator<<(appended);
  }
  if ( a3[1] )
  {
    *(_OWORD *)v34 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v37, v7);
    Microsoft::Diagnostics::Utils::String::WideStringToMultiByteString((__int64)v39, (__int64)v34);
    v17 = *(_OWORD *)std::wstring::operator std::wstring_view(v6, v36, v16);
    v18 = v39;
    if ( a3[3] )
    {
      if ( v41 > 0xF )
        v18 = (char **)v39[0];
      v19 = sqlite3_open_v2(v18, this, 1);
    }
    else
    {
      if ( v41 > 0xF )
        v18 = (char **)v39[0];
      v19 = sqlite3_open(v18, this);
    }
    *(_OWORD *)v34 = v17;
    v20 = Microsoft::Diagnostics::VerifySqlCall(v19, v34);
    Microsoft::Diagnostics::SqlConnection::ValidateOpenSqlConnection(this, v20);
    std::string::_Tidy_deallocate(v39);
    v11 = (char **)(v6 + 2);
  }
  else
  {
    if ( a3[3] )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\Sqlite.h",
        (const char *)0x80004001LL,
        v33);
    if ( v6[3] <= 7u )
      v10 = (char *)v6;
    else
      v10 = (char *)*v6;
    v11 = (char **)(v6 + 2);
    v12 = (char *)v6[2];
    v13 = Src;
    if ( Src[3] > 7u )
      v13 = (_QWORD *)Src[0];
    v14 = sqlite3_open16(v13, this);
    v34[0] = v10;
    v34[1] = v12;
    v15 = Microsoft::Diagnostics::VerifySqlCall(v14, v34);
    Microsoft::Diagnostics::SqlConnection::ValidateOpenSqlConnection(this, v15);
  }
  if ( v8 && !*a3 )
  {
    if ( v6[3] > 7u )
      v6 = (_QWORD *)*v6;
    v34[0] = (char *)v6;
    v34[1] = *v11;
    v42 = 0;
    std::wstring::wstring(v43, v34);
    v21 = (char *)v43;
    if ( v43[3] > 7u )
      v21 = (char *)v43[0];
    v22 = (char *)v43[2];
    v23 = sqlite3_prepare_v2(*(_QWORD *)this, "PRAGMA quick_check;", 19, &v42);
    v34[0] = v21;
    v34[1] = v22;
    v24 = Microsoft::Diagnostics::VerifySqlCall(v23, v34);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x103,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\Sqlite.h",
        (const char *)(unsigned int)v24,
        0);
    v44 = sqlite3_column_count(v42);
    Microsoft::Diagnostics::SqliteBoundStatement::SqliteBoundStatement(
      (Microsoft::Diagnostics::SqliteBoundStatement *)v37,
      v42,
      v44);
    v25 = Microsoft::Diagnostics::SqliteBoundStatement::Step(v37, v34);
    v26 = (_QWORD *)Microsoft::Diagnostics::SqliteQueryResult::Next<std::string_view>(v25, v36);
    *(_OWORD *)v39 = 0;
    v40 = 0;
    v41 = 0;
    std::string::_Construct<1,char const *>(v39, *v26, v26[1]);
    if ( v35 )
      std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(v34);
    std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(v37);
    v27 = v39;
    if ( v41 > 0xF )
      v27 = (char **)v39[0];
    if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<char>>(v27, v40, "ok", 2) )
    {
      v28 = (const char *)v39;
      if ( v41 > 0xF )
        v28 = v39[0];
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x185,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\Sqlite.h",
        (const char *)0x87C52301LL,
        (int)"%hs",
        v28);
    }
    std::string::_Tidy_deallocate(v39);
    std::wstring::_Tidy_deallocate(v43);
    wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,void (sqlite3_stmt *),&void wilp::sqlite_finalize_wrapper(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<sqlite3_stmt *,void (sqlite3_stmt *),&void wilp::sqlite_finalize_wrapper(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>(&v42);
  }
  v29 = &qword_180462860;
  if ( (unsigned __int64)qword_180462878 > 7 )
    v29 = (__int64 *)qword_180462860;
  v30 = qword_180462870;
  v31 = sqlite3_extended_result_codes(*(_QWORD *)this, 1);
  v34[0] = (char *)v29;
  v34[1] = (char *)v30;
  Microsoft::Diagnostics::VerifySqlCall(v31, v34);
  std::wstring::_Tidy_deallocate(Src);
  return this;
}

```

## disassembly

```asm
0x18006d4d8  mov     rax, rsp
0x18006d4db  mov     [rax+18h], rbx
0x18006d4df  push    rbp
0x18006d4e0  push    rsi
0x18006d4e1  push    rdi
0x18006d4e2  push    r12
0x18006d4e4  push    r13
0x18006d4e6  push    r14
0x18006d4e8  push    r15
0x18006d4ea  lea     rbp, [rax-58h]
0x18006d4ee  sub     rsp, 120h
0x18006d4f5  movaps  xmmword ptr [rax-48h], xmm6
0x18006d4f9  mov     rax, cs:__security_cookie
0x18006d500  xor     rax, rsp
0x18006d503  mov     [rbp+50h+var_48], rax
0x18006d507  mov     r14, r8
0x18006d50a  mov     rbx, rdx
0x18006d50d  mov     rsi, rcx
0x18006d510  mov     [rbp+50h+var_D0], rcx
0x18006d514  xor     r15d, r15d
0x18006d517  mov     [rcx], r15
0x18006d51a  mov     [rcx+8], r15d
0x18006d51e  mov     [rcx+10h], r15
0x18006d522  mov     [rcx+18h], r15
0x18006d526  mov     [rcx+20h], r15b
0x18006d52a  lea     rdi, [rcx+28h]
0x18006d52e  mov     rcx, rdi
0x18006d531  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18006d536  nop
0x18006d537  lea     rcx, [rbp+50h+Src]; this
0x18006d53b  call    ??0WideStringStream@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::WideStringStream::WideStringStream(void)
0x18006d540  nop
0x18006d541  mov     r12, [rbx+8]
0x18006d545  test    r12, r12
0x18006d548  jz      short loc_18006D57F
0x18006d54a  movaps  xmm0, xmmword ptr [rbx]
0x18006d54d  movdqa  xmmword ptr [rsp+150h+var_128+8], xmm0
0x18006d553  lea     rdx, [rsp+150h+var_128+8]
0x18006d558  lea     rcx, [rbp+50h+Src]; Src
0x18006d55c  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x18006d561  lea     rcx, aEventstoreDb; "\\EventStore.db"
0x18006d568  lea     rdx, Src
0x18006d56f  cmp     [r14+2], r15b
0x18006d573  cmovz   rdx, rcx
0x18006d577  mov     rcx, rax; Src
0x18006d57a  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18006d57f  cmp     [r14+1], r15b
0x18006d583  jnz     short loc_18006D5FD
0x18006d585  mov     rcx, [rbp+58h]; this
0x18006d589  cmp     [r14+3], r15b
0x18006d58d  jz      short loc_18006D5A7
0x18006d58f  mov     r9d, 80004001h; char *
0x18006d595  lea     r8, aOnecoreBaseTel_130; "onecore\\base\\telemetry\\utc\\service"...
0x18006d59c  mov     edx, 16Eh; void *
0x18006d5a1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006d5a7  cmp     qword ptr [rdi+18h], 7
0x18006d5ac  jbe     short loc_18006D5B3
0x18006d5ae  mov     r15, [rdi]
0x18006d5b1  jmp     short loc_18006D5B6
0x18006d5b3  mov     r15, rdi
0x18006d5b6  lea     r13, [rdi+10h]
0x18006d5ba  mov     rbx, [r13+0]
0x18006d5be  lea     rcx, [rbp+50h+Src]
0x18006d5c2  cmp     [rbp+50h+var_60], 7
0x18006d5c7  cmova   rcx, [rbp+50h+Src]
0x18006d5cc  mov     rdx, rsi
0x18006d5cf  call    cs:__imp_sqlite3_open16
0x18006d5d5  mov     [rsp+150h+var_128+8], r15
0x18006d5da  mov     [rsp+150h+var_118], rbx
0x18006d5df  lea     rdx, [rsp+150h+var_128+8]
0x18006d5e4  mov     ecx, eax
0x18006d5e6  call    ?VerifySqlCall@Diagnostics@Microsoft@@YAJHV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::VerifySqlCall(int,std::wstring_view)
0x18006d5eb  mov     edx, eax; int
0x18006d5ed  mov     rcx, rsi; this
0x18006d5f0  call    ?ValidateOpenSqlConnection@SqlConnection@Diagnostics@Microsoft@@QEAAXJ@Z; Microsoft::Diagnostics::SqlConnection::ValidateOpenSqlConnection(long)
0x18006d5f5  xor     r15d, r15d
0x18006d5f8  jmp     loc_18006D693
0x18006d5fd  lea     rdx, [rsp+150h+var_E8]
0x18006d602  lea     rcx, [rbp+50h+Src]
0x18006d606  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18006d60b  movups  xmm0, xmmword ptr [rax]
0x18006d60e  movdqu  xmmword ptr [rsp+150h+var_128+8], xmm0
0x18006d614  lea     rdx, [rsp+150h+var_128+8]
0x18006d619  lea     rcx, [rbp+50h+var_C8]
0x18006d61d  call    ?WideStringToMultiByteString@String@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::WideStringToMultiByteString(std::wstring_view,ulong)
0x18006d622  nop
0x18006d623  lea     rdx, [rsp+150h+var_F8]
0x18006d628  mov     rcx, rdi
0x18006d62b  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18006d630  movups  xmm6, xmmword ptr [rax]
0x18006d633  lea     rcx, [rbp+50h+var_C8]
0x18006d637  mov     rdx, rsi
0x18006d63a  cmp     [r14+3], r15b
0x18006d63e  jnz     short loc_18006D652
0x18006d640  cmp     [rbp+50h+var_B0], 0Fh
0x18006d645  cmova   rcx, [rbp+50h+var_C8]
0x18006d64a  call    cs:__imp_sqlite3_open
0x18006d650  jmp     short loc_18006D669
0x18006d652  cmp     [rbp+50h+var_B0], 0Fh
0x18006d657  cmova   rcx, [rbp+50h+var_C8]
0x18006d65c  xor     r9d, r9d
0x18006d65f  lea     r8d, [r9+1]
0x18006d663  call    cs:__imp_sqlite3_open_v2
0x18006d669  movdqu  xmmword ptr [rsp+150h+var_128+8], xmm6
0x18006d66f  lea     rdx, [rsp+150h+var_128+8]
0x18006d674  mov     ecx, eax
0x18006d676  call    ?VerifySqlCall@Diagnostics@Microsoft@@YAJHV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::VerifySqlCall(int,std::wstring_view)
0x18006d67b  mov     edx, eax; int
0x18006d67d  mov     rcx, rsi; this
0x18006d680  call    ?ValidateOpenSqlConnection@SqlConnection@Diagnostics@Microsoft@@QEAAXJ@Z; Microsoft::Diagnostics::SqlConnection::ValidateOpenSqlConnection(long)
0x18006d685  nop
0x18006d686  lea     rcx, [rbp+50h+var_C8]
0x18006d68a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18006d68f  lea     r13, [rdi+10h]
0x18006d693  test    r12, r12
0x18006d696  jz      loc_18006D82B
0x18006d69c  cmp     [r14], r15b
0x18006d69f  jnz     loc_18006D82B
0x18006d6a5  cmp     qword ptr [rdi+18h], 7
0x18006d6aa  jbe     short loc_18006D6AF
0x18006d6ac  mov     rdi, [rdi]
0x18006d6af  mov     [rsp+150h+var_128+8], rdi
0x18006d6b4  mov     rax, [r13+0]
0x18006d6b8  mov     [rsp+150h+var_118], rax
0x18006d6bd  mov     [rbp+50h+var_A8], r15
0x18006d6c1  lea     rdx, [rsp+150h+var_128+8]
0x18006d6c6  lea     rcx, [rbp+50h+var_A0]
0x18006d6ca  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18006d6cf  nop
0x18006d6d0  lea     rdi, [rbp+50h+var_A0]
0x18006d6d4  cmp     [rbp+50h+var_88], 7
0x18006d6d9  cmova   rdi, [rbp+50h+var_A0]
0x18006d6de  mov     rbx, [rbp+50h+var_90]
0x18006d6e2  mov     qword ptr [rsp+150h+var_130], r15; int
0x18006d6e7  lea     r9, [rbp+50h+var_A8]
0x18006d6eb  mov     r8d, 13h
0x18006d6f1  lea     rdx, aPragmaQuickChe; "PRAGMA quick_check;"
0x18006d6f8  mov     rcx, [rsi]
0x18006d6fb  call    cs:__imp_sqlite3_prepare_v2
0x18006d701  mov     [rsp+150h+var_128+8], rdi
0x18006d706  mov     [rsp+150h+var_118], rbx
0x18006d70b  lea     rdx, [rsp+150h+var_128+8]
0x18006d710  mov     ecx, eax
0x18006d712  call    ?VerifySqlCall@Diagnostics@Microsoft@@YAJHV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::VerifySqlCall(int,std::wstring_view)
0x18006d717  mov     rcx, [rbp+58h]; this
0x18006d71b  test    eax, eax
0x18006d71d  jns     short loc_18006D734
0x18006d71f  mov     r9d, eax; char *
0x18006d722  lea     r8, aOnecoreBaseTel_130; "onecore\\base\\telemetry\\utc\\service"...
0x18006d729  mov     edx, 103h; void *
0x18006d72e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006d734  mov     rcx, [rbp+50h+var_A8]
0x18006d738  call    cs:__imp_sqlite3_column_count
0x18006d73e  mov     [rbp+50h+var_80], eax
0x18006d741  mov     r8d, eax; unsigned int
0x18006d744  mov     rdx, [rbp+50h+var_A8]; struct sqlite3_stmt *
0x18006d748  lea     rcx, [rsp+150h+var_E8]; this
0x18006d74d  call    ??0SqliteBoundStatement@Diagnostics@Microsoft@@QEAA@PEAUsqlite3_stmt@@K@Z; Microsoft::Diagnostics::SqliteBoundStatement::SqliteBoundStatement(sqlite3_stmt *,ulong)
0x18006d752  nop
0x18006d753  lea     rdx, [rsp+150h+var_128+8]
0x18006d758  lea     rcx, [rsp+150h+var_E8]
0x18006d75d  call    ?Step@SqliteBoundStatement@Diagnostics@Microsoft@@QEAA?AV?$optional@VSqliteQueryResult@Diagnostics@Microsoft@@@std@@XZ; Microsoft::Diagnostics::SqliteBoundStatement::Step(void)
0x18006d762  nop
0x18006d763  lea     rdx, [rsp+150h+var_F8]
0x18006d768  mov     rcx, rax
0x18006d76b  call    ??$Next@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@SqliteQueryResult@Diagnostics@Microsoft@@QEAA?AV?$basic_string_view@DU?$char_traits@D@std@@@std@@XZ; Microsoft::Diagnostics::SqliteQueryResult::Next<std::string_view>(void)
0x18006d770  xorps   xmm0, xmm0
0x18006d773  movups  xmmword ptr [rbp+50h+var_C8], xmm0
0x18006d777  mov     [rbp+50h+var_B8], r15
0x18006d77b  mov     [rbp+50h+var_B0], r15
0x18006d77f  mov     r8, [rax+8]
0x18006d783  mov     rdx, [rax]
0x18006d786  lea     rcx, [rbp+50h+var_C8]
0x18006d78a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18006d78f  nop
0x18006d790  cmp     [rsp+150h+var_108], r15b
0x18006d795  jz      short loc_18006D7A2
0x18006d797  lea     rcx, [rsp+150h+var_128+8]; void *
0x18006d79c  call    ??1?$shared_ptr@$$CBUProviderGroupInfo@Diagnostics@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(void)
0x18006d7a1  nop
0x18006d7a2  lea     rcx, [rsp+150h+var_E8]; void *
0x18006d7a7  call    ??1?$shared_ptr@$$CBUProviderGroupInfo@Diagnostics@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(void)
0x18006d7ac  lea     rcx, [rbp+50h+var_C8]
0x18006d7b0  cmp     [rbp+50h+var_B0], 0Fh
0x18006d7b5  cmova   rcx, [rbp+50h+var_C8]
0x18006d7ba  mov     r9d, 2
0x18006d7c0  lea     r8, aOk_0; "ok"
0x18006d7c7  mov     rdx, [rbp+50h+var_B8]
0x18006d7cb  call    ??$_Traits_equal@U?$char_traits@D@std@@@std@@YA_NQEBD_K01@Z; std::_Traits_equal<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x18006d7d0  test    al, al
0x18006d7d2  jnz     short loc_18006D80F
0x18006d7d4  lea     rax, [rbp+50h+var_C8]
0x18006d7d8  cmp     [rbp+50h+var_B0], 0Fh
0x18006d7dd  cmova   rax, [rbp+50h+var_C8]
0x18006d7e2  mov     rcx, [rbp+58h]; this
0x18006d7e6  mov     [rsp+150h+var_128], rax; char *
0x18006d7eb  lea     rax, aHs; "%hs"
0x18006d7f2  mov     qword ptr [rsp+150h+var_130], rax; int
0x18006d7f7  mov     r9d, 87C52301h; char *
0x18006d7fd  lea     r8, aOnecoreBaseTel_130; "onecore\\base\\telemetry\\utc\\service"...
0x18006d804  mov     edx, 185h; void *
0x18006d809  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006d80f  lea     rcx, [rbp+50h+var_C8]
0x18006d813  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18006d818  nop
0x18006d819  lea     rcx, [rbp+50h+var_A0]
0x18006d81d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d822  lea     rcx, [rbp+50h+var_A8]
0x18006d826  call    ??1?$unique_storage@U?$resource_policy@PEAUsqlite3_stmt@@$$A6AXPEAU1@@Z$1?sqlite_finalize_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<sqlite3_stmt *,void (sqlite3_stmt *),&wilp::sqlite_finalize_wrapper(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<sqlite3_stmt *,void (sqlite3_stmt *),&wilp::sqlite_finalize_wrapper(sqlite3_stmt *),wistd::integral_constant<unsigned __int64,0>,sqlite3_stmt *,sqlite3_stmt *,0,std::nullptr_t>>(void)
0x18006d82b  lea     rdi, qword_180462860
0x18006d832  cmp     cs:qword_180462878, 7
0x18006d83a  cmova   rdi, cs:qword_180462860
0x18006d842  mov     rbx, cs:qword_180462870
0x18006d849  mov     edx, 1
0x18006d84e  mov     rcx, [rsi]
0x18006d851  call    cs:__imp_sqlite3_extended_result_codes
0x18006d857  mov     [rsp+150h+var_128+8], rdi
0x18006d85c  mov     [rsp+150h+var_118], rbx
0x18006d861  lea     rdx, [rsp+150h+var_128+8]
0x18006d866  mov     ecx, eax
0x18006d868  call    ?VerifySqlCall@Diagnostics@Microsoft@@YAJHV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::VerifySqlCall(int,std::wstring_view)
0x18006d86d  nop
0x18006d86e  lea     rcx, [rbp+50h+Src]
0x18006d872  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d877  nop
0x18006d878  mov     rax, rsi
0x18006d87b  mov     rcx, [rbp+50h+var_48]
0x18006d87f  xor     rcx, rsp; StackCookie
0x18006d882  call    __security_check_cookie
0x18006d887  lea     r11, [rsp+150h+var_30]
0x18006d88f  mov     rbx, [r11+50h]
0x18006d893  movaps  xmm6, xmmword ptr [r11-10h]
0x18006d898  mov     rsp, r11
0x18006d89b  pop     r15
0x18006d89d  pop     r14
0x18006d89f  pop     r13
0x18006d8a1  pop     r12
0x18006d8a3  pop     rdi
0x18006d8a4  pop     rsi
0x18006d8a5  pop     rbp
0x18006d8a6  retn
```
