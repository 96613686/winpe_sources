# CustomEntityTable::GetLastModified(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180027eb8`
- end: `0x1800281ac`
- name: `?GetLastModified@CustomEntityTable@@QEAA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@0@Z`
- size: `756`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD *, const char *)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001554c`

## callees

- `0x180002250`
- `0x180005290`
- `0x1800120e4`
- `0x180013830`
- `0x180026948`
- `0x18002732c`
- `0x1800275e8`
- `0x180027eb8`
- `0x180028608`
- `0x18002888c`
- `0x180031978`
- `0x180034f40`
- `0x180035024`
- `0x180039be4`
- `0x1800807c0`
- `0x1800a5f80`
- `0x1800a70f0`
- `0x1800abe70`

## import_xrefs

- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18002812b`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18002812b`
- `msvcp_win!??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180028121`
- `msvcp_win!??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x180028121`
- `msvcp_win!?fail@ios_base@std@@QEBA_NXZ` at `0x180028094`
- `msvcp_win!?fail@ios_base@std@@QEBA_NXZ` at `0x180028094`
- `api-ms-win-crt-private-l1-1-0!_o__get_timezone` at `0x1800280d6`
- `api-ms-win-crt-private-l1-1-0!_o__get_timezone` at `0x1800280d6`
- `api-ms-win-crt-private-l1-1-0!_o__mktime64` at `0x1800280b0`
- `api-ms-win-crt-private-l1-1-0!_o__mktime64` at `0x1800280b0`

## string_xrefs

- `0x180027f3f`: `SELECT LastUpdatedTimestamp FROM CustomEntities WHERE EntityKind = ? AND AppId = ? ORDER BY LastUpdatedTimestamp DESC LIMIT ?;`
- `0x180028176`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\customentitytable.cpp`
- `0x180028188`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\customentitytable.cpp`
- `0x18002819a`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\customentitytable.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall CustomEntityTable::GetLastModified(__int64 a1, _QWORD *a2, _QWORD *a3, const char *a4)
{
  const char *v4; // rdi
  struct sqlite3_stmt *v8; // rbx
  const char *v9; // rax
  const char *v10; // r9
  __int64 v11; // r8
  const char *v12; // rax
  const char *v13; // r9
  __int64 v14; // rdi
  const char *v15; // r9
  int v17; // [rsp+40h] [rbp-C0h] BYREF
  struct sqlite3_stmt *v18; // [rsp+48h] [rbp-B8h] BYREF
  RTL_SRWLOCK v19[8]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v20[2]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v21[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v22[120]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v23[96]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v24; // [rsp+180h] [rbp+80h] BYREF
  __int128 v25; // [rsp+190h] [rbp+90h]
  _OWORD v26[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v27; // [rsp+1C0h] [rbp+C0h]
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v4 = a4;
  ADPDatabase::BeginTransaction(*(_QWORD *)(a1 + 8), (__int64)v19, 1, a4);
  *a2 = 0;
  v18 = 0;
  sqlite3LockAndPrepare(
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 32LL),
    (unsigned int)"SELECT LastUpdatedTimestamp FROM CustomEntities WHERE EntityKind = ? AND AppId = ? ORDER BY LastUpdate"
                  "dTimestamp DESC LIMIT ?;",
    -1,
    128,
    0,
    (__int64)&v18,
    0);
  if ( a3[3] > 0xFu )
    a3 = (_QWORD *)*a3;
  v8 = v18;
  bindText((_DWORD)v18, 1, (_DWORD)a3, -1, 0, 1);
  if ( *((_QWORD *)v4 + 3) > 0xFu )
    v4 = *(const char **)v4;
  bindText((_DWORD)v8, 2, (_DWORD)v4, -1, 0, 1);
  sqlite3_bind_int64(v8, 3, 1);
  if ( (unsigned int)sqlite3_step(v8) == 100 )
  {
    v9 = (const char *)sqlite3_column_text(v8, 0);
    if ( !v9 )
      wil::details::in1diag3::_FailFast_NullAlloc(
        retaddr,
        (void *)0x20,
        (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\customentitytable.cpp",
        v10);
    memset(v26, 0, sizeof(v26));
    v27 = 0;
    v24 = 0;
    v25 = 0;
    v11 = -1;
    do
      ++v11;
    while ( v9[v11] );
    std::string::_Construct<1,char const *>(&v24, v9);
    std::istringstream::istringstream(v20, &v24);
    std::string::~string((char **)&v24);
    *(_QWORD *)&v24 = v26;
    v12 = "%Y-%m-%d %H:%M:%S";
    *((_QWORD *)&v24 + 1) = "%Y-%m-%d %H:%M:%S";
    do
      ++v12;
    while ( *v12 );
    *(_QWORD *)&v25 = v12;
    std::operator>><char,std::char_traits<char>>(v20, &v24);
    if ( std::ios_base::fail((std::ios_base *)((char *)v20 + *(int *)(v20[0] + 4LL))) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\customentitytable.cpp",
        v13);
    v14 = _o__mktime64(v26);
    if ( v14 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x29,
        (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\customentitytable.cpp",
        v15);
    v17 = 0;
    _o__get_timezone(&v17);
    *a2 = 10000000 * (v14 - v17);
    *(_QWORD *)((char *)v20 + *(int *)(v20[0] + 4LL)) = &std::istringstream::`vftable';
    *(_DWORD *)((char *)&v19[7].Ptr + *(int *)(v20[0] + 4LL) + 4) = *(_DWORD *)(v20[0] + 4LL) - 144;
    std::stringbuf::~stringbuf(v21);
    std::istream::~istream<char,std::char_traits<char>>(v22);
    std::ios::~ios<char,std::char_traits<char>>(v23);
  }
  Transaction::Commit(v19);
  if ( v8 )
    unique_sqlite3_stmt::release_or_terminate(v8);
  Transaction::~Transaction((Transaction *)v19);
  return a2;
}

```

## disassembly

```asm
0x180027eb8  push    rbp
0x180027eba  push    rbx
0x180027ebb  push    rsi
0x180027ebc  push    rdi
0x180027ebd  push    r13
0x180027ebf  push    r14
0x180027ec1  lea     rbp, [rsp-0D8h]
0x180027ec9  sub     rsp, 1D8h
0x180027ed0  mov     rax, cs:__security_cookie
0x180027ed7  xor     rax, rsp
0x180027eda  mov     [rbp+100h+var_38], rax
0x180027ee1  mov     rdi, r9
0x180027ee4  mov     rsi, r8
0x180027ee7  mov     r14, rdx
0x180027eea  mov     rbx, rcx
0x180027eed  mov     r8d, 1
0x180027ef3  lea     rdx, [rsp+200h+var_1B0]
0x180027ef8  mov     rcx, [rcx+8]
0x180027efc  call    ?BeginTransaction@ADPDatabase@@QEAA?AVTransaction@@W4TransactionLockType@@@Z; ADPDatabase::BeginTransaction(TransactionLockType)
0x180027f01  nop
0x180027f02  mov     qword ptr [r14], 0
0x180027f09  mov     [rsp+200h+var_1B8], 0
0x180027f12  mov     rcx, [rbx+8]
0x180027f16  mov     [rsp+200h+var_1D0], 0
0x180027f1f  lea     rax, [rsp+200h+var_1B8]
0x180027f24  mov     [rsp+200h+var_1D8], rax
0x180027f29  mov     [rsp+200h+var_1E0], 0
0x180027f32  mov     r9d, 80h
0x180027f38  or      r13, 0FFFFFFFFFFFFFFFFh
0x180027f3c  mov     r8d, r13d
0x180027f3f  lea     rdx, aSelectLastupda_0; "SELECT LastUpdatedTimestamp FROM Custom"...
0x180027f46  mov     rcx, [rcx+20h]
0x180027f4a  call    sqlite3LockAndPrepare
0x180027f4f  cmp     qword ptr [rsi+18h], 0Fh
0x180027f54  jbe     short loc_180027F59
0x180027f56  mov     rsi, [rsi]
0x180027f59  mov     byte ptr [rsp+200h+var_1D8], 1
0x180027f5e  mov     [rsp+200h+var_1E0], 0
0x180027f67  mov     r9, r13
0x180027f6a  mov     r8, rsi
0x180027f6d  mov     edx, 1
0x180027f72  mov     rbx, [rsp+200h+var_1B8]
0x180027f77  mov     rcx, rbx
0x180027f7a  call    bindText
0x180027f7f  cmp     qword ptr [rdi+18h], 0Fh
0x180027f84  jbe     short loc_180027F89
0x180027f86  mov     rdi, [rdi]
0x180027f89  mov     byte ptr [rsp+200h+var_1D8], 1
0x180027f8e  mov     [rsp+200h+var_1E0], 0
0x180027f97  mov     r9, r13
0x180027f9a  mov     r8, rdi
0x180027f9d  mov     edx, 2
0x180027fa2  mov     rcx, rbx
0x180027fa5  call    bindText
0x180027faa  mov     edx, 3
0x180027faf  lea     r8d, [rdx-2]
0x180027fb3  mov     rcx, rbx
0x180027fb6  call    sqlite3_bind_int64
0x180027fbb  mov     rcx, rbx
0x180027fbe  call    sqlite3_step
0x180027fc3  cmp     eax, 64h ; 'd'
0x180027fc6  jnz     loc_180028131
0x180027fcc  xor     edx, edx
0x180027fce  mov     rcx, rbx
0x180027fd1  call    sqlite3_column_text
0x180027fd6  mov     rcx, [rbp+108h]; this
0x180027fdd  test    rax, rax
0x180027fe0  jz      loc_180028188
0x180027fe6  xorps   xmm0, xmm0
0x180027fe9  xor     ecx, ecx
0x180027feb  movups  [rbp+100h+var_60], xmm0
0x180027ff2  movups  [rbp+100h+var_50], xmm0
0x180027ff9  mov     [rbp+100h+var_40], ecx
0x180027fff  movups  [rbp+100h+var_80], xmm0
0x180028006  xorps   xmm1, xmm1
0x180028009  movdqu  [rbp+100h+var_70], xmm1
0x180028011  mov     r8, r13
0x180028014  inc     r8
0x180028017  cmp     [rax+r8], cl
0x18002801b  jnz     short loc_180028014
0x18002801d  mov     rdx, rax
0x180028020  lea     rcx, [rbp+100h+var_80]
0x180028027  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18002802c  nop
0x18002802d  lea     rdx, [rbp+100h+var_80]
0x180028034  lea     rcx, [rbp+100h+var_170]
0x180028038  call    ??0?$basic_istringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@H@Z; std::istringstream::istringstream(std::string &&,int)
0x18002803d  nop
0x18002803e  lea     rcx, [rbp+100h+var_80]
0x180028045  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002804a  lea     rax, [rbp+100h+var_60]
0x180028051  mov     qword ptr [rbp+100h+var_80], rax
0x180028058  lea     rax, aYMDHMS; "%Y-%m-%d %H:%M:%S"
0x18002805f  mov     qword ptr [rbp+100h+var_80+8], rax
0x180028066  inc     rax
0x180028069  cmp     byte ptr [rax], 0
0x18002806c  jnz     short loc_180028066
0x18002806e  mov     qword ptr [rbp+100h+var_70], rax
0x180028075  lea     rdx, [rbp+100h+var_80]
0x18002807c  lea     rcx, [rbp+100h+var_170]
0x180028080  call    ??$?5DU?$char_traits@D@std@@@std@@YAAEAV?$basic_istream@DU?$char_traits@D@std@@@0@AEAV10@AEBU?$_Timeobj@DPEAUtm@@@0@@Z; std::operator>><char,std::char_traits<char>>(std::istream &,std::_Timeobj<char,tm *> const &)
0x180028085  mov     rax, [rbp+100h+var_170]
0x180028089  movsxd  rcx, dword ptr [rax+4]
0x18002808d  lea     rax, [rbp+100h+var_170]
0x180028091  add     rcx, rax
0x180028094  call    cs:__imp_?fail@ios_base@std@@QEBA_NXZ; std::ios_base::fail(void)
0x18002809a  mov     rcx, [rbp+108h]; this
0x1800280a1  test    al, al
0x1800280a3  jnz     loc_18002819A
0x1800280a9  lea     rcx, [rbp+100h+var_60]
0x1800280b0  call    cs:__imp__o__mktime64
0x1800280b6  mov     rdi, rax
0x1800280b9  mov     rcx, [rbp+108h]; this
0x1800280c0  cmp     rax, r13
0x1800280c3  jz      loc_180028176
0x1800280c9  mov     [rsp+200h+var_1C0], 0
0x1800280d1  lea     rcx, [rsp+200h+var_1C0]
0x1800280d6  call    cs:__imp__o__get_timezone
0x1800280dc  movsxd  rax, [rsp+200h+var_1C0]
0x1800280e1  sub     rdi, rax
0x1800280e4  imul    rax, rdi, 989680h
0x1800280eb  mov     [r14], rax
0x1800280ee  mov     rax, [rbp+100h+var_170]
0x1800280f2  movsxd  rcx, dword ptr [rax+4]
0x1800280f6  lea     rax, ??_7?$basic_istringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::istringstream::`vftable'
0x1800280fd  mov     [rbp+rcx+100h+var_170], rax
0x180028102  mov     rax, [rbp+100h+var_170]
0x180028106  movsxd  rcx, dword ptr [rax+4]
0x18002810a  lea     edx, [rcx-90h]
0x180028110  mov     [rbp+rcx+100h+var_174], edx
0x180028114  lea     rcx, [rbp+100h+var_160]
0x180028118  call    ??1?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UEAA@XZ; std::stringbuf::~stringbuf(void)
0x18002811d  lea     rcx, [rbp+100h+var_158]
0x180028121  call    cs:__imp_??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::istream::~istream<char,std::char_traits<char>>(void)
0x180028127  lea     rcx, [rbp+100h+var_E0]
0x18002812b  call    cs:__imp_??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ios::~ios<char,std::char_traits<char>>(void)
0x180028131  lea     rcx, [rsp+200h+var_1B0]; this
0x180028136  call    ?Commit@Transaction@@QEAAXXZ; Transaction::Commit(void)
0x18002813b  nop
0x18002813c  test    rbx, rbx
0x18002813f  jz      short loc_18002814A
0x180028141  mov     rcx, rbx; struct sqlite3_stmt *
0x180028144  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x180028149  nop
0x18002814a  lea     rcx, [rsp+200h+var_1B0]; this
0x18002814f  call    ??1Transaction@@QEAA@XZ; Transaction::~Transaction(void)
0x180028154  mov     rax, r14
0x180028157  mov     rcx, [rbp+100h+var_38]
0x18002815e  xor     rcx, rsp; StackCookie
0x180028161  call    __security_check_cookie
0x180028166  add     rsp, 1D8h
0x18002816d  pop     r14
0x18002816f  pop     r13
0x180028171  pop     rdi
0x180028172  pop     rsi
0x180028173  pop     rbx
0x180028174  pop     rbp
0x180028175  retn
0x180028176  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x18002817d  mov     edx, 29h ; ')'; void *
0x180028182  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180028188  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x18002818f  mov     edx, 20h ; ' '; void *
0x180028194  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x18002819a  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x1800281a1  mov     edx, 26h ; '&'; void *
0x1800281a6  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
