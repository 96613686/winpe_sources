# UsageAndQualityInsights::Database::FactStoreDatabase::RunDeleteFactsByEventsAndExpiration(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::vector<UsageAndQualityInsights::Database::EventNameAndExpiration,std::allocator<UsageAndQualityInsights::Database::EventNameAndExpiration>> const &)

- ea: `0x18004ab0c`
- end: `0x18004aebd`
- name: `?RunDeleteFactsByEventsAndExpiration@FactStoreDatabase@Database@UsageAndQualityInsights@@AEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$vector@UEventNameAndExpiration@Database@UsageAndQualityInsights@@V?$allocator@UEventNameAndExpiration@Database@UsageAndQualityInsights@@@std@@@5@@Z`
- size: `945`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18004a66c`

## callees

- `0x1800033d0`
- `0x1800033f4`
- `0x1800038b8`
- `0x180003fdc`
- `0x180020650`
- `0x18002adf0`
- `0x18002b258`
- `0x18002b2b0`
- `0x18002b470`
- `0x18002be8c`
- `0x180034b88`
- `0x180041358`
- `0x180048b20`
- `0x18004ab0c`
- `0x18004c634`
- `0x18004d080`
- `0x18004de34`
- `0x18004dff0`
- `0x18004ec60`
- `0x18004fe0c`
- `0x18004fee0`
- `0x1800c0e30`
- `0x1800c3160`
- `0x1800c6d20`

## string_xrefs

- `0x18004ac9b`: `DELETE FROM {} WHERE {};`
- `0x18004adf1`: `onecore\base\usageandqualityinsights\service\lib\database\factstoredatabase.cpp`
- `0x18004ab3b`: `RunDeleteStatement`
- `0x18004addb`: `Failed to execute delete statement for table %hs`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall UsageAndQualityInsights::Database::FactStoreDatabase::RunDeleteFactsByEventsAndExpiration(
        __int64 a1,
        const char *a2,
        int **a3)
{
  char *v6; // rbx
  __int64 *v7; // rdi
  unsigned int v8; // ebx
  const char *v9; // rcx
  int *v10; // rdi
  int *v11; // r15
  struct sqlite3_stmt *v12; // r14
  unsigned int v13; // ebx
  _QWORD *v14; // rax
  __int64 v15; // rcx
  struct sqlite3_stmt *v16; // r14
  int v17; // ebx
  struct sqlite3 *v18; // rax
  struct sqlite3 *v19; // rax
  int v20; // [rsp+20h] [rbp-E0h]
  struct sqlite3_stmt *v21; // [rsp+40h] [rbp-C0h] BYREF
  const char *p_pExceptionObject; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v23; // [rsp+58h] [rbp-A8h]
  char *pExceptionObject; // [rsp+60h] [rbp-A0h] BYREF
  char *pExceptionObject_8; // [rsp+68h] [rbp-98h]
  char *v26; // [rsp+70h] [rbp-90h]
  char *v27; // [rsp+80h] [rbp-80h] BYREF
  char *v28; // [rsp+88h] [rbp-78h]
  char **v29; // [rsp+90h] [rbp-70h]
  _BYTE v30[48]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD Src[4]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v32[16]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v33; // [rsp+100h] [rbp+0h]
  __int128 v34; // [rsp+110h] [rbp+10h] BYREF
  __int64 v35; // [rsp+120h] [rbp+20h]
  __int64 v36; // [rsp+128h] [rbp+28h]
  __int128 v37; // [rsp+130h] [rbp+30h] BYREF
  __int64 v38; // [rsp+140h] [rbp+40h]
  __int64 v39; // [rsp+148h] [rbp+48h]
  __int128 v40; // [rsp+150h] [rbp+50h] BYREF
  __int64 v41; // [rsp+160h] [rbp+60h]
  __int64 v42; // [rsp+168h] [rbp+68h]
  __int64 v43; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  UsageAndQualityInsightsCoreLogging::TraceLoggingInfo("RunDeleteStatement");
  v34 = 0;
  v35 = 0;
  v36 = 0;
  std::string::_Construct<1,char const *>(&v34, "fact_source =", 13);
  v37 = 0;
  v38 = 0;
  v39 = 0;
  std::string::_Construct<1,char const *>(&v37, "fact_name =", 11);
  v40 = 0;
  v41 = 0;
  v42 = 0;
  std::string::_Construct<1,char const *>(&v40, "fact_time <", 11);
  v6 = (char *)operator new(0x60u);
  pExceptionObject = v6;
  pExceptionObject_8 = v6;
  v26 = v6 + 96;
  p_pExceptionObject = (const char *)&pExceptionObject;
  v7 = (__int64 *)&v34;
  v27 = v6;
  v28 = v6;
  v29 = &pExceptionObject;
  do
  {
    std::string::string(v6, v7);
    v6 += 32;
    v28 = v6;
    v7 += 4;
  }
  while ( v7 != &v43 );
  pExceptionObject_8 = v6;
  UsageAndQualityInsights::Database::GetDeleteWhereClauses(v32);
  std::vector<std::string>::_Tidy(&pExceptionObject);
  `eh vector destructor iterator'(&v34, 0x20u, 3u, std::string::~string);
  if ( v33 )
  {
    p_pExceptionObject = "DELETE FROM {} WHERE {};";
    v23 = 24;
    std::format<std::string const &,std::string &>(Src);
    v8 = 1;
    UsageAndQualityInsights::Database::UQIDatabase::BeginTransaction(a1, v30);
    v9 = (const char *)Src;
    if ( Src[3] > 0xFu )
      v9 = (const char *)Src[0];
    p_pExceptionObject = v9;
    v23 = Src[2];
    sqlite3_prepare_v2_entire_cpp(&v21, *(_QWORD *)(a1 + 32), &p_pExceptionObject);
    v10 = *a3;
    v11 = a3[1];
    while ( v10 != v11 )
    {
      v12 = v21;
      if ( (unsigned int)sqlite3_bind_int64(v21, v8, *v10) )
      {
        v19 = (struct sqlite3 *)sqlite3_db_handle(v12);
        sqlite3_error::sqlite3_error((sqlite3_error *)&v27, v19);
        sqlite3_error::sqlite3_error(&pExceptionObject, &v27);
        throw (sqlite3_error *)&pExceptionObject;
      }
      v13 = v8 + 1;
      v14 = v10 + 2;
      if ( *((_QWORD *)v10 + 4) > 0xFu )
        v14 = (_QWORD *)*v14;
      v15 = -1;
      do
        ++v15;
      while ( *((_BYTE *)v14 + v15) );
      p_pExceptionObject = (const char *)v14;
      v23 = v15;
      sqlite3_bind_text_cpp(v21, v13, &p_pExceptionObject);
      v16 = v21;
      if ( (unsigned int)sqlite3_bind_int64(v21, v13 + 1, *((_QWORD *)v10 + 5) / 10000LL) )
      {
        v18 = (struct sqlite3 *)sqlite3_db_handle(v16);
        sqlite3_error::sqlite3_error((sqlite3_error *)&v27, v18);
        sqlite3_error::sqlite3_error(&pExceptionObject, &v27);
        throw (sqlite3_error *)&pExceptionObject;
      }
      v8 = v13 + 2;
      v10 += 12;
    }
    v17 = sqlite3_step(v21);
    Transaction::Commit((Transaction *)v30);
    if ( *((_QWORD *)a2 + 3) > 0xFu )
      a2 = *(const char **)a2;
    LOBYTE(v20) = v17 != 101;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x328,
      (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\database\\factstoredatabase.cpp",
      (const char *)0x80004005LL,
      v20,
      (bool)"Failed to execute delete statement for table %hs",
      a2);
    if ( v21 )
      unique_sqlite3_stmt::release_or_terminate(v21);
    Transaction::~Transaction((Transaction *)v30);
    std::string::~string(Src);
  }
  std::string::~string(v32);
}

```

## disassembly

```asm
0x18004ab0c  mov     [rsp-8+arg_10], rbx
0x18004ab11  push    rbp
0x18004ab12  push    rsi
0x18004ab13  push    rdi
0x18004ab14  push    r14
0x18004ab16  push    r15
0x18004ab18  lea     rbp, [rsp-80h]
0x18004ab1d  sub     rsp, 180h
0x18004ab24  mov     rax, cs:__security_cookie
0x18004ab2b  xor     rax, rsp
0x18004ab2e  mov     [rbp+0A0h+var_30], rax
0x18004ab32  mov     r14, r8
0x18004ab35  mov     rsi, rdx
0x18004ab38  mov     r15, rcx
0x18004ab3b  lea     rcx, aRundeletestate; "RunDeleteStatement"
0x18004ab42  call    ?TraceLoggingInfo@UsageAndQualityInsightsCoreLogging@@SAXPEBDZZ; UsageAndQualityInsightsCoreLogging::TraceLoggingInfo(char const *,...)
0x18004ab47  xorps   xmm0, xmm0
0x18004ab4a  movups  [rbp+0A0h+var_90], xmm0
0x18004ab4e  mov     [rbp+0A0h+var_80], 0
0x18004ab56  mov     [rbp+0A0h+var_78], 0
0x18004ab5e  mov     r8d, 0Dh
0x18004ab64  lea     rdx, aFactSource; "fact_source ="
0x18004ab6b  lea     rcx, [rbp+0A0h+var_90]
0x18004ab6f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18004ab74  nop
0x18004ab75  xorps   xmm0, xmm0
0x18004ab78  movups  [rbp+0A0h+var_70], xmm0
0x18004ab7c  mov     [rbp+0A0h+var_60], 0
0x18004ab84  mov     [rbp+0A0h+var_58], 0
0x18004ab8c  mov     ebx, 0Bh
0x18004ab91  mov     r8d, ebx
0x18004ab94  lea     rdx, aFactName; "fact_name ="
0x18004ab9b  lea     rcx, [rbp+0A0h+var_70]
0x18004ab9f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18004aba4  nop
0x18004aba5  xorps   xmm0, xmm0
0x18004aba8  movups  [rbp+0A0h+var_50], xmm0
0x18004abac  mov     [rbp+0A0h+var_40], 0
0x18004abb4  mov     [rbp+0A0h+var_38], 0
0x18004abbc  mov     r8d, ebx
0x18004abbf  lea     rdx, aFactTime; "fact_time <"
0x18004abc6  lea     rcx, [rbp+0A0h+var_50]
0x18004abca  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18004abcf  nop
0x18004abd0  xorps   xmm0, xmm0
0x18004abd3  movdqu  [rsp+1A0h+pExceptionObject], xmm0
0x18004abd9  mov     [rsp+1A0h+var_130], 0
0x18004abe2  lea     ecx, [rbx+55h]; Size
0x18004abe5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004abea  mov     rbx, rax
0x18004abed  mov     qword ptr [rsp+1A0h+pExceptionObject], rax
0x18004abf2  mov     qword ptr [rsp+1A0h+pExceptionObject+8], rax
0x18004abf7  lea     rcx, [rax+60h]
0x18004abfb  mov     [rsp+1A0h+var_130], rcx
0x18004ac00  lea     rax, [rsp+1A0h+pExceptionObject]
0x18004ac05  mov     [rsp+1A0h+var_150], rax
0x18004ac0a  lea     rdi, [rbp+0A0h+var_90]
0x18004ac0e  mov     [rbp+0A0h+var_120], rbx
0x18004ac12  mov     [rbp+0A0h+var_118], rbx
0x18004ac16  lea     rax, [rsp+1A0h+pExceptionObject]
0x18004ac1b  mov     [rbp+0A0h+var_110], rax
0x18004ac1f  mov     rdx, rdi
0x18004ac22  mov     rcx, rbx
0x18004ac25  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x18004ac2a  add     rbx, 20h ; ' '
0x18004ac2e  mov     [rbp+0A0h+var_118], rbx
0x18004ac32  add     rdi, 20h ; ' '
0x18004ac36  lea     rax, [rbp+0A0h+var_30]
0x18004ac3a  cmp     rdi, rax
0x18004ac3d  jnz     short loc_18004AC1F
0x18004ac3f  mov     qword ptr [rsp+1A0h+pExceptionObject+8], rbx
0x18004ac44  mov     rdx, [r14+8]
0x18004ac48  sub     rdx, [r14]
0x18004ac4b  sar     rdx, 4
0x18004ac4f  mov     rax, 0AAAAAAAAAAAAAAABh
0x18004ac59  imul    rdx, rax
0x18004ac5d  lea     r8, [rsp+1A0h+pExceptionObject]
0x18004ac62  lea     rcx, [rbp+0A0h+var_B0]; void *
0x18004ac66  call    ?GetDeleteWhereClauses@Database@UsageAndQualityInsights@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_KAEBV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@4@@Z; UsageAndQualityInsights::Database::GetDeleteWhereClauses(unsigned __int64,std::vector<std::string> const &)
0x18004ac6b  nop
0x18004ac6c  lea     rcx, [rsp+1A0h+pExceptionObject]
0x18004ac71  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x18004ac76  nop
0x18004ac77  lea     r9, ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; void (*)(void *)
0x18004ac7e  mov     edx, 20h ; ' '; unsigned __int64
0x18004ac83  lea     r8d, [rdx-1Dh]; unsigned __int64
0x18004ac87  lea     rcx, [rbp+0A0h+var_90]; void *
0x18004ac8b  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18004ac90  cmp     [rbp+0A0h+var_A0], 0
0x18004ac95  jz      loc_18004AE27
0x18004ac9b  lea     rax, aDeleteFromWher; "DELETE FROM {} WHERE {};"
0x18004aca2  mov     [rsp+1A0h+var_150], rax
0x18004aca7  mov     [rsp+1A0h+var_148], 18h
0x18004acb0  lea     r9, [rbp+0A0h+var_B0]
0x18004acb4  mov     r8, rsi
0x18004acb7  lea     rdx, [rsp+1A0h+var_150]
0x18004acbc  lea     rcx, [rbp+0A0h+Src]; Src
0x18004acc0  call    ??$format@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV12@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@U?$basic_format_string@DAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV12@@0@AEBV10@AEAV10@@Z; std::format<std::string const &,std::string &>(std::basic_format_string<char,std::string const &,std::string &>,std::string const &,std::string &)
0x18004acc5  nop
0x18004acc6  mov     ebx, 1
0x18004accb  lea     rdx, [rbp+0A0h+var_100]
0x18004accf  mov     rcx, r15
0x18004acd2  call    ?BeginTransaction@UQIDatabase@Database@UsageAndQualityInsights@@QEAA?AVTransaction@@W4TransactionLockType@@@Z; UsageAndQualityInsights::Database::UQIDatabase::BeginTransaction(TransactionLockType)
0x18004acd7  nop
0x18004acd8  lea     rcx, [rbp+0A0h+Src]
0x18004acdc  cmp     [rbp+0A0h+var_B8], 0Fh
0x18004ace1  cmova   rcx, [rbp+0A0h+Src]
0x18004ace6  mov     rax, [rbp+0A0h+var_C0]
0x18004acea  mov     [rsp+1A0h+var_150], rcx
0x18004acef  mov     [rsp+1A0h+var_148], rax
0x18004acf4  lea     r8, [rsp+1A0h+var_150]
0x18004acf9  mov     rdx, [r15+20h]
0x18004acfd  lea     rcx, [rsp+1A0h+var_160]
0x18004ad02  call    ?sqlite3_prepare_v2_entire_cpp@@YA?AUunique_sqlite3_stmt@@PEAUsqlite3@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; sqlite3_prepare_v2_entire_cpp(sqlite3 *,std::string_view)
0x18004ad07  nop
0x18004ad08  mov     rdi, [r14]
0x18004ad0b  mov     r15, [r14+8]
0x18004ad0f  jmp     loc_18004ADA1
0x18004ad14  mov     r14, [rsp+1A0h+var_160]
0x18004ad19  movsxd  r8, dword ptr [rdi]
0x18004ad1c  mov     edx, ebx
0x18004ad1e  mov     rcx, r14
0x18004ad21  call    sqlite3_bind_int64
0x18004ad26  test    eax, eax
0x18004ad28  jnz     loc_18004AE88
0x18004ad2e  inc     ebx
0x18004ad30  lea     rax, [rdi+8]
0x18004ad34  cmp     qword ptr [rax+18h], 0Fh
0x18004ad39  jbe     short loc_18004AD3E
0x18004ad3b  mov     rax, [rax]
0x18004ad3e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004ad42  inc     rcx
0x18004ad45  cmp     byte ptr [rax+rcx], 0
0x18004ad49  jnz     short loc_18004AD42
0x18004ad4b  mov     edx, ebx
0x18004ad4d  mov     [rsp+1A0h+var_150], rax
0x18004ad52  mov     [rsp+1A0h+var_148], rcx
0x18004ad57  lea     r8, [rsp+1A0h+var_150]
0x18004ad5c  mov     rcx, [rsp+1A0h+var_160]
0x18004ad61  call    ?sqlite3_bind_text_cpp@@YAXPEAUsqlite3_stmt@@HV?$basic_string_view@DU?$char_traits@D@std@@@std@@Q6AXPEAX@_E@Z; sqlite3_bind_text_cpp(sqlite3_stmt *,int,std::string_view,void (*const)(void *),...)
0x18004ad66  mov     rax, 346DC5D63886594Bh
0x18004ad70  imul    qword ptr [rdi+28h]
0x18004ad74  sar     rdx, 0Bh
0x18004ad78  mov     r8, rdx
0x18004ad7b  shr     r8, 3Fh
0x18004ad7f  add     r8, rdx
0x18004ad82  mov     r14, [rsp+1A0h+var_160]
0x18004ad87  lea     edx, [rbx+1]
0x18004ad8a  mov     rcx, r14
0x18004ad8d  call    sqlite3_bind_int64
0x18004ad92  test    eax, eax
0x18004ad94  jnz     loc_18004AE53
0x18004ad9a  add     ebx, 2
0x18004ad9d  add     rdi, 30h ; '0'
0x18004ada1  cmp     rdi, r15
0x18004ada4  jnz     loc_18004AD14
0x18004adaa  mov     rcx, [rsp+1A0h+var_160]
0x18004adaf  call    sqlite3_step
0x18004adb4  mov     ebx, eax
0x18004adb6  lea     rcx, [rbp+0A0h+var_100]; this
0x18004adba  call    ?Commit@Transaction@@QEAAXXZ; Transaction::Commit(void)
0x18004adbf  cmp     qword ptr [rsi+18h], 0Fh
0x18004adc4  jbe     short loc_18004ADC9
0x18004adc6  mov     rsi, [rsi]
0x18004adc9  cmp     ebx, 65h ; 'e'
0x18004adcc  setnz   al
0x18004adcf  mov     rcx, [rbp+0A8h]; this
0x18004add6  mov     [rsp+1A0h+var_170], rsi; char *
0x18004addb  lea     rdx, aFailedToExecut; "Failed to execute delete statement for "...
0x18004ade2  mov     qword ptr [rsp+1A0h+var_178], rdx; bool
0x18004ade7  mov     byte ptr [rsp+1A0h+var_180], al; int
0x18004adeb  mov     r9d, 80004005h; char *
0x18004adf1  lea     r8, aOnecoreBaseUsa_3; "onecore\\base\\usageandqualityinsights"...
0x18004adf8  mov     edx, 328h; void *
0x18004adfd  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18004ae02  nop
0x18004ae03  mov     rcx, [rsp+1A0h+var_160]; struct sqlite3_stmt *
0x18004ae08  test    rcx, rcx
0x18004ae0b  jz      short loc_18004AE13
0x18004ae0d  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x18004ae12  nop
0x18004ae13  lea     rcx, [rbp+0A0h+var_100]; this
0x18004ae17  call    ??1Transaction@@QEAA@XZ; Transaction::~Transaction(void)
0x18004ae1c  nop
0x18004ae1d  lea     rcx, [rbp+0A0h+Src]; void *
0x18004ae21  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004ae26  nop
0x18004ae27  lea     rcx, [rbp+0A0h+var_B0]; void *
0x18004ae2b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18004ae30  mov     rcx, [rbp+0A0h+var_30]
0x18004ae34  xor     rcx, rsp; StackCookie
0x18004ae37  call    __security_check_cookie
0x18004ae3c  mov     rbx, [rsp+1A0h+arg_10]
0x18004ae44  add     rsp, 180h
0x18004ae4b  pop     r15
0x18004ae4d  pop     r14
0x18004ae4f  pop     rdi
0x18004ae50  pop     rsi
0x18004ae51  pop     rbp
0x18004ae52  retn
0x18004ae53  mov     rcx, r14
0x18004ae56  call    sqlite3_db_handle
0x18004ae5b  mov     rdx, rax; struct sqlite3 *
0x18004ae5e  lea     rcx, [rbp+0A0h+var_120]; this
0x18004ae62  call    ??0sqlite3_error@@QEAA@PEAUsqlite3@@@Z; sqlite3_error::sqlite3_error(sqlite3 *)
0x18004ae67  nop
0x18004ae68  lea     rdx, [rbp+0A0h+var_120]
0x18004ae6c  lea     rcx, [rsp+1A0h+pExceptionObject]
0x18004ae71  call    ??0sqlite3_error@@QEAA@$$QEAU0@@Z; sqlite3_error::sqlite3_error(sqlite3_error &&)
0x18004ae76  lea     rdx, _TI2?AUsqlite3_error@@; pThrowInfo
0x18004ae7d  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x18004ae82  call    _CxxThrowException_0
0x18004ae88  mov     rcx, r14
0x18004ae8b  call    sqlite3_db_handle
0x18004ae90  mov     rdx, rax; struct sqlite3 *
0x18004ae93  lea     rcx, [rbp+0A0h+var_120]; this
0x18004ae97  call    ??0sqlite3_error@@QEAA@PEAUsqlite3@@@Z; sqlite3_error::sqlite3_error(sqlite3 *)
0x18004ae9c  nop
0x18004ae9d  lea     rdx, [rbp+0A0h+var_120]
0x18004aea1  lea     rcx, [rsp+1A0h+pExceptionObject]
0x18004aea6  call    ??0sqlite3_error@@QEAA@$$QEAU0@@Z; sqlite3_error::sqlite3_error(sqlite3_error &&)
0x18004aeab  lea     rdx, _TI2?AUsqlite3_error@@; pThrowInfo
0x18004aeb2  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x18004aeb7  call    _CxxThrowException_0
```
