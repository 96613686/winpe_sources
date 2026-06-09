# UsageAndQualityInsights::Database::FactStoreDatabase::DeleteFactsBeforeFileTime(std::optional<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>)

- ea: `0x180047178`
- end: `0x1800473ef`
- name: `?DeleteFactsBeforeFileTime@FactStoreDatabase@Database@UsageAndQualityInsights@@QEAAXV?$optional@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@std@@@Z`
- size: `631`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001573c`

## callees

- `0x1800033d0`
- `0x180003fdc`
- `0x180020650`
- `0x18002adf0`
- `0x18002b258`
- `0x18002b2b0`
- `0x18002b470`
- `0x18002be8c`
- `0x180041358`
- `0x180043310`
- `0x18004394c`
- `0x180047178`
- `0x1800473f8`
- `0x180048234`
- `0x180048d8c`
- `0x18004c634`
- `0x18004dff0`
- `0x18004ec60`
- `0x18004fe0c`
- `0x18004fee0`
- `0x1800c0e30`
- `0x1800c3160`
- `0x1800c6d20`

## string_xrefs

- `0x180047236`: `DELETE FROM {} WHERE {};`
- `0x1800472e8`: `onecore\base\usageandqualityinsights\service\lib\database\factstoredatabase.cpp`
- `0x1800471a1`: `DeleteFactsBeforeFileTime`
- `0x1800472d2`: `Failed while trying to delete facts from table %hs`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall UsageAndQualityInsights::Database::FactStoreDatabase::DeleteFactsBeforeFileTime(__int64 a1, __int64 a2)
{
  __int64 v4; // r15
  __int64 *v5; // rbx
  const char *v6; // rdi
  char **v7; // rax
  struct sqlite3_stmt *v8; // r14
  int v9; // eax
  __int64 **v10; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  struct sqlite3 *v13; // rax
  int v14; // [rsp+20h] [rbp-E0h]
  struct sqlite3_stmt *v15; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v16[3]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD pExceptionObject[4]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v18[4]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v19[24]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v20[48]; // [rsp+B8h] [rbp-48h] BYREF
  char *Src[4]; // [rsp+E8h] [rbp-18h] BYREF
  _OWORD v22[2]; // [rsp+108h] [rbp+8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  UsageAndQualityInsightsCoreLogging::TraceLoggingInfo("DeleteFactsBeforeFileTime");
  if ( *(_BYTE *)(a2 + 8) )
  {
    UsageAndQualityInsights::Database::FactStoreDatabase::GenerateDateRange(v19);
    UsageAndQualityInsights::Database::FactStoreDatabase::GetExistingTablesFromDates(a1, v16, v19);
    memset(v22, 0, sizeof(v22));
    std::string::_Construct<1,char const *>(v22, "fact_time <= ?", 14);
    v4 = *(_QWORD *)a2 / 10000LL;
    v5 = *(__int64 **)v16[0];
    while ( !*((_BYTE *)v5 + 25) )
    {
      UsageAndQualityInsights::Database::UQIDatabase::BeginTransaction(a1, v20);
      pExceptionObject[0] = "DELETE FROM {} WHERE {};";
      pExceptionObject[1] = 24;
      v6 = (const char *)(v5 + 4);
      std::format<std::string const &,std::string &>(Src);
      v7 = Src;
      if ( Src[3] > (char *)0xF )
        v7 = (char **)Src[0];
      v18[0] = v7;
      v18[1] = Src[2];
      sqlite3_prepare_v2_entire_cpp(&v15, *(_QWORD *)(a1 + 32), v18);
      v8 = v15;
      if ( (unsigned int)sqlite3_bind_int64(v15, 1, v4) )
      {
        v13 = (struct sqlite3 *)sqlite3_db_handle(v8);
        sqlite3_error::sqlite3_error((sqlite3_error *)v18, v13);
        sqlite3_error::sqlite3_error(pExceptionObject, v18);
        throw (sqlite3_error *)pExceptionObject;
      }
      v9 = sqlite3_step(v15);
      if ( (unsigned __int64)v5[7] > 0xF )
        v6 = *(const char **)v6;
      LOBYTE(v14) = v9 != 101;
      wil::details::in1diag3::Throw_HrIfMsg(
        retaddr,
        (void *)0x381,
        (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\database\\factstoredatabase.cpp",
        (const char *)0x80004005LL,
        v14,
        (bool)"Failed while trying to delete facts from table %hs",
        v6);
      Transaction::Commit((Transaction *)v20);
      if ( v15 )
        unique_sqlite3_stmt::release_or_terminate(v15);
      std::string::~string(Src);
      Transaction::~Transaction((Transaction *)v20);
      v10 = (__int64 **)v5[2];
      if ( *((_BYTE *)v10 + 25) )
      {
        for ( i = (__int64 *)v5[1]; !*((_BYTE *)i + 25) && v5 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v5 = i;
        v5 = i;
      }
      else
      {
        v5 = (__int64 *)v5[2];
        for ( j = *v10; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v5 = j;
      }
    }
    UsageAndQualityInsights::Database::FactStoreDatabase::DropEmptyTables(a1, v16);
    std::string::~string((char **)v22);
    std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::~_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>(v16);
    std::vector<std::chrono::year_month_day>::~vector<std::chrono::year_month_day>(v19);
  }
}

```

## disassembly

```asm
0x180047178  push    rbp
0x18004717a  push    rbx
0x18004717b  push    rsi
0x18004717c  push    rdi
0x18004717d  push    r14
0x18004717f  push    r15
0x180047181  lea     rbp, [rsp-38h]
0x180047186  sub     rsp, 138h
0x18004718d  mov     rax, cs:__security_cookie
0x180047194  xor     rax, rsp
0x180047197  mov     [rbp+60h+var_38], rax
0x18004719b  mov     rbx, rdx
0x18004719e  mov     rsi, rcx
0x1800471a1  lea     rcx, aDeletefactsbef; "DeleteFactsBeforeFileTime"
0x1800471a8  call    ?TraceLoggingInfo@UsageAndQualityInsightsCoreLogging@@SAXPEBDZZ; UsageAndQualityInsightsCoreLogging::TraceLoggingInfo(char const *,...)
0x1800471ad  cmp     byte ptr [rbx+8], 0
0x1800471b1  jz      loc_18004739E
0x1800471b7  lea     rcx, [rbp+60h+var_C0]
0x1800471bb  call    ?GenerateDateRange@FactStoreDatabase@Database@UsageAndQualityInsights@@CA?AV?$vector@Vyear_month_day@chrono@std@@V?$allocator@Vyear_month_day@chrono@std@@@3@@std@@H@Z; UsageAndQualityInsights::Database::FactStoreDatabase::GenerateDateRange(int)
0x1800471c0  nop
0x1800471c1  lea     r8, [rbp+60h+var_C0]
0x1800471c5  lea     rdx, [rsp+160h+var_118]
0x1800471ca  mov     rcx, rsi
0x1800471cd  call    ?GetExistingTablesFromDates@FactStoreDatabase@Database@UsageAndQualityInsights@@AEAA?AV?$set@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEBV?$vector@Vyear_month_day@chrono@std@@V?$allocator@Vyear_month_day@chrono@std@@@3@@5@@Z; UsageAndQualityInsights::Database::FactStoreDatabase::GetExistingTablesFromDates(std::vector<std::chrono::year_month_day> const &)
0x1800471d2  nop
0x1800471d3  xorps   xmm0, xmm0
0x1800471d6  movups  [rbp+60h+var_58], xmm0
0x1800471da  xorps   xmm1, xmm1
0x1800471dd  movdqu  [rbp+60h+var_48], xmm1
0x1800471e2  mov     r8d, 0Eh
0x1800471e8  lea     rdx, aFactTime_0; "fact_time <= ?"
0x1800471ef  lea     rcx, [rbp+60h+var_58]
0x1800471f3  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800471f8  nop
0x1800471f9  mov     rax, 346DC5D63886594Bh
0x180047203  imul    qword ptr [rbx]
0x180047206  mov     r15, rdx
0x180047209  sar     r15, 0Bh
0x18004720d  mov     rax, r15
0x180047210  shr     rax, 3Fh
0x180047214  add     r15, rax
0x180047217  mov     rbx, [rsp+160h+var_118]
0x18004721c  mov     rbx, [rbx]
0x18004721f  mov     rcx, rsi
0x180047222  cmp     byte ptr [rbx+19h], 0
0x180047226  jnz     loc_180047375
0x18004722c  lea     rdx, [rbp+60h+var_A8]
0x180047230  call    ?BeginTransaction@UQIDatabase@Database@UsageAndQualityInsights@@QEAA?AVTransaction@@W4TransactionLockType@@@Z; UsageAndQualityInsights::Database::UQIDatabase::BeginTransaction(TransactionLockType)
0x180047235  nop
0x180047236  lea     rax, aDeleteFromWher; "DELETE FROM {} WHERE {};"
0x18004723d  mov     [rsp+160h+pExceptionObject], rax
0x180047242  mov     [rsp+160h+var_F8], 18h
0x18004724b  lea     rdi, [rbx+20h]
0x18004724f  lea     r9, [rbp+60h+var_58]
0x180047253  mov     r8, rdi
0x180047256  lea     rdx, [rsp+160h+pExceptionObject]
0x18004725b  lea     rcx, [rbp+60h+Src]; Src
0x18004725f  call    ??$format@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV12@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@U?$basic_format_string@DAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV12@@0@AEBV10@AEAV10@@Z; std::format<std::string const &,std::string &>(std::basic_format_string<char,std::string const &,std::string &>,std::string const &,std::string &)
0x180047264  nop
0x180047265  lea     rax, [rbp+60h+Src]
0x180047269  cmp     [rbp+60h+var_60], 0Fh
0x18004726e  cmova   rax, [rbp+60h+Src]
0x180047273  mov     [rbp+60h+var_E0], rax
0x180047277  mov     rax, [rbp+60h+var_68]
0x18004727b  mov     [rbp+60h+var_D8], rax
0x18004727f  lea     r8, [rbp+60h+var_E0]
0x180047283  mov     rdx, [rsi+20h]
0x180047287  lea     rcx, [rsp+160h+var_120]
0x18004728c  call    ?sqlite3_prepare_v2_entire_cpp@@YA?AUunique_sqlite3_stmt@@PEAUsqlite3@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; sqlite3_prepare_v2_entire_cpp(sqlite3 *,std::string_view)
0x180047291  nop
0x180047292  mov     r14, [rsp+160h+var_120]
0x180047297  mov     r8, r15
0x18004729a  mov     edx, 1
0x18004729f  mov     rcx, r14
0x1800472a2  call    sqlite3_bind_int64
0x1800472a7  test    eax, eax
0x1800472a9  jnz     loc_1800473BA
0x1800472af  mov     rcx, [rsp+160h+var_120]
0x1800472b4  call    sqlite3_step
0x1800472b9  cmp     qword ptr [rdi+18h], 0Fh
0x1800472be  jbe     short loc_1800472C3
0x1800472c0  mov     rdi, [rdi]
0x1800472c3  cmp     eax, 65h ; 'e'
0x1800472c6  setnz   al
0x1800472c9  mov     rcx, [rbp+68h]; this
0x1800472cd  mov     [rsp+160h+var_130], rdi; char *
0x1800472d2  lea     rdx, aFailedWhileTry; "Failed while trying to delete facts fro"...
0x1800472d9  mov     qword ptr [rsp+160h+var_138], rdx; bool
0x1800472de  mov     byte ptr [rsp+160h+var_140], al; int
0x1800472e2  mov     r9d, 80004005h; char *
0x1800472e8  lea     r8, aOnecoreBaseUsa_3; "onecore\\base\\usageandqualityinsights"...
0x1800472ef  mov     edx, 381h; void *
0x1800472f4  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800472f9  lea     rcx, [rbp+60h+var_A8]; this
0x1800472fd  call    ?Commit@Transaction@@QEAAXXZ; Transaction::Commit(void)
0x180047302  nop
0x180047303  mov     rcx, [rsp+160h+var_120]; struct sqlite3_stmt *
0x180047308  test    rcx, rcx
0x18004730b  jz      short loc_180047313
0x18004730d  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x180047312  nop
0x180047313  lea     rcx, [rbp+60h+Src]; void *
0x180047317  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004731c  nop
0x18004731d  lea     rcx, [rbp+60h+var_A8]; this
0x180047321  call    ??1Transaction@@QEAA@XZ; Transaction::~Transaction(void)
0x180047326  mov     rcx, [rbx+10h]
0x18004732a  cmp     byte ptr [rcx+19h], 0
0x18004732e  jz      short loc_180047351
0x180047330  mov     rax, [rbx+8]
0x180047334  jmp     short loc_180047343
0x180047336  cmp     rbx, [rax+10h]
0x18004733a  jnz     short loc_180047349
0x18004733c  mov     rbx, rax
0x18004733f  mov     rax, [rax+8]
0x180047343  cmp     byte ptr [rax+19h], 0
0x180047347  jz      short loc_180047336
0x180047349  mov     rbx, rax
0x18004734c  jmp     loc_18004721F
0x180047351  mov     rbx, rcx
0x180047354  mov     rcx, [rcx]
0x180047357  cmp     byte ptr [rcx+19h], 0
0x18004735b  jnz     loc_18004721F
0x180047361  mov     rbx, rcx
0x180047364  mov     rax, [rcx]
0x180047367  mov     rcx, rax
0x18004736a  cmp     byte ptr [rax+19h], 0
0x18004736e  jz      short loc_180047361
0x180047370  jmp     loc_18004721F
0x180047375  lea     rdx, [rsp+160h+var_118]
0x18004737a  call    ?DropEmptyTables@FactStoreDatabase@Database@UsageAndQualityInsights@@AEAAXAEBV?$set@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@@Z; UsageAndQualityInsights::Database::FactStoreDatabase::DropEmptyTables(std::set<std::string> const &)
0x18004737f  nop
0x180047380  lea     rcx, [rbp+60h+var_58]; void *
0x180047384  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180047389  nop
0x18004738a  lea     rcx, [rsp+160h+var_118]
0x18004738f  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::~_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>(void)
0x180047394  nop
0x180047395  lea     rcx, [rbp+60h+var_C0]
0x180047399  call    ??1?$vector@Vyear_month_day@chrono@std@@V?$allocator@Vyear_month_day@chrono@std@@@3@@std@@QEAA@XZ; std::vector<std::chrono::year_month_day>::~vector<std::chrono::year_month_day>(void)
0x18004739e  mov     rcx, [rbp+60h+var_38]
0x1800473a2  xor     rcx, rsp; StackCookie
0x1800473a5  call    __security_check_cookie
0x1800473aa  add     rsp, 138h
0x1800473b1  pop     r15
0x1800473b3  pop     r14
0x1800473b5  pop     rdi
0x1800473b6  pop     rsi
0x1800473b7  pop     rbx
0x1800473b8  pop     rbp
0x1800473b9  retn
0x1800473ba  mov     rcx, r14
0x1800473bd  call    sqlite3_db_handle
0x1800473c2  mov     rdx, rax; struct sqlite3 *
0x1800473c5  lea     rcx, [rbp+60h+var_E0]; this
0x1800473c9  call    ??0sqlite3_error@@QEAA@PEAUsqlite3@@@Z; sqlite3_error::sqlite3_error(sqlite3 *)
0x1800473ce  nop
0x1800473cf  lea     rdx, [rbp+60h+var_E0]
0x1800473d3  lea     rcx, [rsp+160h+pExceptionObject]
0x1800473d8  call    ??0sqlite3_error@@QEAA@$$QEAU0@@Z; sqlite3_error::sqlite3_error(sqlite3_error &&)
0x1800473dd  lea     rdx, _TI2?AUsqlite3_error@@; pThrowInfo
0x1800473e4  lea     rcx, [rsp+160h+pExceptionObject]; pExceptionObject
0x1800473e9  call    _CxxThrowException_0
```
