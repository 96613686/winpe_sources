# ActionsPolicyTable::GetLastModifiedTime(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x18002a30c`
- end: `0x18002a5c2`
- name: `?GetLastModifiedTime@ActionsPolicyTable@@QEAA?AV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z`
- size: `694`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD *, const char *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180018080`

## callees

- `0x180002250`
- `0x180005290`
- `0x1800120e4`
- `0x180013830`
- `0x180026948`
- `0x18002732c`
- `0x1800275e8`
- `0x180028608`
- `0x18002888c`
- `0x18002a30c`
- `0x180031978`
- `0x180034f40`
- `0x180035024`
- `0x180039be4`
- `0x1800807c0`
- `0x1800a70f0`
- `0x1800abe70`

## import_xrefs

- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18002a53e`
- `msvcp_win!??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18002a53e`
- `msvcp_win!??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18002a534`
- `msvcp_win!??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ` at `0x18002a534`
- `msvcp_win!?fail@ios_base@std@@QEBA_NXZ` at `0x18002a4a6`
- `msvcp_win!?fail@ios_base@std@@QEBA_NXZ` at `0x18002a4a6`
- `api-ms-win-crt-private-l1-1-0!_o__get_timezone` at `0x18002a4e9`
- `api-ms-win-crt-private-l1-1-0!_o__get_timezone` at `0x18002a4e9`
- `api-ms-win-crt-private-l1-1-0!_o__mktime64` at `0x18002a4c2`
- `api-ms-win-crt-private-l1-1-0!_o__mktime64` at `0x18002a4c2`

## string_xrefs

- `0x18002a58c`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\actionspolicytable.cpp`
- `0x18002a59e`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\actionspolicytable.cpp`
- `0x18002a5b0`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\actionspolicytable.cpp`
- `0x18002a38c`: `SELECT LastUpdatedTimestamp FROM ActionsCurationPolicies WHERE UserInterfaceContext = ?;`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall ActionsPolicyTable::GetLastModifiedTime(__int64 a1, _QWORD *a2, _QWORD *a3, const char *a4)
{
  struct sqlite3_stmt *v7; // rbx
  const char *v8; // rax
  const char *v9; // r9
  __int64 v10; // r8
  const char *v11; // rax
  const char *v12; // r9
  __int64 v13; // rdi
  const char *v14; // r9
  int v16; // [rsp+40h] [rbp-C0h] BYREF
  struct sqlite3_stmt *v17; // [rsp+48h] [rbp-B8h] BYREF
  RTL_SRWLOCK v18[8]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v19[2]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v20[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v21[120]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v22[96]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v23; // [rsp+180h] [rbp+80h] BYREF
  __int128 v24; // [rsp+190h] [rbp+90h]
  _OWORD v25[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v26; // [rsp+1C0h] [rbp+C0h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  ADPDatabase::BeginTransaction(*(_QWORD *)(a1 + 8), (__int64)v18, 1, a4);
  *a2 = 0;
  v17 = 0;
  sqlite3LockAndPrepare(
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 32LL),
    (unsigned int)"SELECT LastUpdatedTimestamp FROM ActionsCurationPolicies WHERE UserInterfaceContext = ?;",
    -1,
    128,
    0,
    (__int64)&v17,
    0);
  if ( a3[3] > 0xFu )
    a3 = (_QWORD *)*a3;
  v7 = v17;
  bindText((_DWORD)v17, 1, (_DWORD)a3, -1, 0, 1);
  if ( (unsigned int)sqlite3_step(v7) == 100 )
  {
    v8 = (const char *)sqlite3_column_text(v7, 0);
    if ( !v8 )
      wil::details::in1diag3::_FailFast_NullAlloc(
        retaddr,
        (void *)0x55,
        (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\actionspolicytable.cpp",
        v9);
    memset(v25, 0, sizeof(v25));
    v26 = 0;
    v23 = 0;
    v24 = 0;
    v10 = -1;
    do
      ++v10;
    while ( v8[v10] );
    std::string::_Construct<1,char const *>(&v23, v8);
    std::istringstream::istringstream(v19, &v23);
    std::string::~string((char **)&v23);
    *(_QWORD *)&v23 = v25;
    v11 = "%Y-%m-%d %H:%M:%S";
    *((_QWORD *)&v23 + 1) = "%Y-%m-%d %H:%M:%S";
    do
      ++v11;
    while ( *v11 );
    *(_QWORD *)&v24 = v11;
    std::operator>><char,std::char_traits<char>>(v19, &v23);
    if ( std::ios_base::fail((std::ios_base *)((char *)v19 + *(int *)(v19[0] + 4LL))) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x5B,
        (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\actionspolicytable.cpp",
        v12);
    v13 = _o__mktime64(v25);
    if ( v13 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x5E,
        (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\actionspolicytable.cpp",
        v14);
    v16 = 0;
    _o__get_timezone(&v16);
    *a2 = 10000000 * (v13 - v16);
    *(_QWORD *)((char *)v19 + *(int *)(v19[0] + 4LL)) = &std::istringstream::`vftable';
    *(_DWORD *)((char *)&v18[7].Ptr + *(int *)(v19[0] + 4LL) + 4) = *(_DWORD *)(v19[0] + 4LL) - 144;
    std::stringbuf::~stringbuf(v20);
    std::istream::~istream<char,std::char_traits<char>>(v21);
    std::ios::~ios<char,std::char_traits<char>>(v22);
  }
  Transaction::Commit(v18);
  if ( v7 )
    unique_sqlite3_stmt::release_or_terminate(v7);
  Transaction::~Transaction((Transaction *)v18);
  return a2;
}

```

## disassembly

```asm
0x18002a30c  mov     [rsp-8+arg_18], rbx
0x18002a311  push    rbp
0x18002a312  push    rsi
0x18002a313  push    rdi
0x18002a314  lea     rbp, [rsp-0D0h]
0x18002a31c  sub     rsp, 1D0h
0x18002a323  mov     rax, cs:__security_cookie
0x18002a32a  xor     rax, rsp
0x18002a32d  mov     [rbp+0E0h+var_18], rax
0x18002a334  mov     rdi, r8
0x18002a337  mov     rsi, rdx
0x18002a33a  mov     rbx, rcx
0x18002a33d  mov     r8d, 1
0x18002a343  lea     rdx, [rsp+1E0h+var_190]
0x18002a348  mov     rcx, [rcx+8]
0x18002a34c  call    ?BeginTransaction@ADPDatabase@@QEAA?AVTransaction@@W4TransactionLockType@@@Z; ADPDatabase::BeginTransaction(TransactionLockType)
0x18002a351  nop
0x18002a352  mov     qword ptr [rsi], 0
0x18002a359  mov     [rsp+1E0h+var_198], 0
0x18002a362  mov     rcx, [rbx+8]
0x18002a366  mov     [rsp+1E0h+var_1B0], 0
0x18002a36f  lea     rax, [rsp+1E0h+var_198]
0x18002a374  mov     [rsp+1E0h+var_1B8], rax
0x18002a379  mov     [rsp+1E0h+var_1C0], 0
0x18002a382  mov     r9d, 80h
0x18002a388  or      r8d, 0FFFFFFFFh
0x18002a38c  lea     rdx, aSelectLastupda; "SELECT LastUpdatedTimestamp FROM Action"...
0x18002a393  mov     rcx, [rcx+20h]
0x18002a397  call    sqlite3LockAndPrepare
0x18002a39c  cmp     qword ptr [rdi+18h], 0Fh
0x18002a3a1  jbe     short loc_18002A3A6
0x18002a3a3  mov     rdi, [rdi]
0x18002a3a6  mov     byte ptr [rsp+1E0h+var_1B8], 1
0x18002a3ab  mov     [rsp+1E0h+var_1C0], 0
0x18002a3b4  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002a3b8  mov     r8, rdi
0x18002a3bb  lea     edx, [r9+2]
0x18002a3bf  mov     rbx, [rsp+1E0h+var_198]
0x18002a3c4  mov     rcx, rbx
0x18002a3c7  call    bindText
0x18002a3cc  mov     rcx, rbx
0x18002a3cf  call    sqlite3_step
0x18002a3d4  cmp     eax, 64h ; 'd'
0x18002a3d7  jnz     loc_18002A544
0x18002a3dd  xor     edx, edx
0x18002a3df  mov     rcx, rbx
0x18002a3e2  call    sqlite3_column_text
0x18002a3e7  mov     rcx, [rbp+0E8h]; this
0x18002a3ee  test    rax, rax
0x18002a3f1  jz      loc_18002A59E
0x18002a3f7  xorps   xmm0, xmm0
0x18002a3fa  xor     ecx, ecx
0x18002a3fc  movups  [rbp+0E0h+var_40], xmm0
0x18002a403  movups  [rbp+0E0h+var_30], xmm0
0x18002a40a  mov     [rbp+0E0h+var_20], ecx
0x18002a410  movups  [rbp+0E0h+var_60], xmm0
0x18002a417  xorps   xmm1, xmm1
0x18002a41a  movdqu  [rbp+0E0h+var_50], xmm1
0x18002a422  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002a426  inc     r8
0x18002a429  cmp     [rax+r8], cl
0x18002a42d  jnz     short loc_18002A426
0x18002a42f  mov     rdx, rax
0x18002a432  lea     rcx, [rbp+0E0h+var_60]
0x18002a439  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18002a43e  nop
0x18002a43f  lea     rdx, [rbp+0E0h+var_60]
0x18002a446  lea     rcx, [rbp+0E0h+var_150]
0x18002a44a  call    ??0?$basic_istringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@H@Z; std::istringstream::istringstream(std::string &&,int)
0x18002a44f  nop
0x18002a450  lea     rcx, [rbp+0E0h+var_60]
0x18002a457  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002a45c  lea     rax, [rbp+0E0h+var_40]
0x18002a463  mov     qword ptr [rbp+0E0h+var_60], rax
0x18002a46a  lea     rax, aYMDHMS; "%Y-%m-%d %H:%M:%S"
0x18002a471  mov     qword ptr [rbp+0E0h+var_60+8], rax
0x18002a478  inc     rax
0x18002a47b  cmp     byte ptr [rax], 0
0x18002a47e  jnz     short loc_18002A478
0x18002a480  mov     qword ptr [rbp+0E0h+var_50], rax
0x18002a487  lea     rdx, [rbp+0E0h+var_60]
0x18002a48e  lea     rcx, [rbp+0E0h+var_150]
0x18002a492  call    ??$?5DU?$char_traits@D@std@@@std@@YAAEAV?$basic_istream@DU?$char_traits@D@std@@@0@AEAV10@AEBU?$_Timeobj@DPEAUtm@@@0@@Z; std::operator>><char,std::char_traits<char>>(std::istream &,std::_Timeobj<char,tm *> const &)
0x18002a497  mov     rax, [rbp+0E0h+var_150]
0x18002a49b  movsxd  rcx, dword ptr [rax+4]
0x18002a49f  lea     rax, [rbp+0E0h+var_150]
0x18002a4a3  add     rcx, rax
0x18002a4a6  call    cs:__imp_?fail@ios_base@std@@QEBA_NXZ; std::ios_base::fail(void)
0x18002a4ac  mov     rcx, [rbp+0E8h]; this
0x18002a4b3  test    al, al
0x18002a4b5  jnz     loc_18002A5B0
0x18002a4bb  lea     rcx, [rbp+0E0h+var_40]
0x18002a4c2  call    cs:__imp__o__mktime64
0x18002a4c8  mov     rdi, rax
0x18002a4cb  mov     rcx, [rbp+0E8h]; this
0x18002a4d2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002a4d6  jz      loc_18002A58C
0x18002a4dc  mov     [rsp+1E0h+var_1A0], 0
0x18002a4e4  lea     rcx, [rsp+1E0h+var_1A0]
0x18002a4e9  call    cs:__imp__o__get_timezone
0x18002a4ef  movsxd  rax, [rsp+1E0h+var_1A0]
0x18002a4f4  sub     rdi, rax
0x18002a4f7  imul    rax, rdi, 989680h
0x18002a4fe  mov     [rsi], rax
0x18002a501  mov     rax, [rbp+0E0h+var_150]
0x18002a505  movsxd  rcx, dword ptr [rax+4]
0x18002a509  lea     rax, ??_7?$basic_istringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@6B@; const std::istringstream::`vftable'
0x18002a510  mov     [rbp+rcx+0E0h+var_150], rax
0x18002a515  mov     rax, [rbp+0E0h+var_150]
0x18002a519  movsxd  rcx, dword ptr [rax+4]
0x18002a51d  lea     edx, [rcx-90h]
0x18002a523  mov     [rbp+rcx+0E0h+var_154], edx
0x18002a527  lea     rcx, [rbp+0E0h+var_140]
0x18002a52b  call    ??1?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UEAA@XZ; std::stringbuf::~stringbuf(void)
0x18002a530  lea     rcx, [rbp+0E0h+var_138]
0x18002a534  call    cs:__imp_??1?$basic_istream@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::istream::~istream<char,std::char_traits<char>>(void)
0x18002a53a  lea     rcx, [rbp+0E0h+var_C0]
0x18002a53e  call    cs:__imp_??1?$basic_ios@DU?$char_traits@D@std@@@std@@UEAA@XZ; std::ios::~ios<char,std::char_traits<char>>(void)
0x18002a544  lea     rcx, [rsp+1E0h+var_190]; this
0x18002a549  call    ?Commit@Transaction@@QEAAXXZ; Transaction::Commit(void)
0x18002a54e  nop
0x18002a54f  test    rbx, rbx
0x18002a552  jz      short loc_18002A55D
0x18002a554  mov     rcx, rbx; struct sqlite3_stmt *
0x18002a557  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x18002a55c  nop
0x18002a55d  lea     rcx, [rsp+1E0h+var_190]; this
0x18002a562  call    ??1Transaction@@QEAA@XZ; Transaction::~Transaction(void)
0x18002a567  mov     rax, rsi
0x18002a56a  mov     rcx, [rbp+0E0h+var_18]
0x18002a571  xor     rcx, rsp; StackCookie
0x18002a574  call    __security_check_cookie
0x18002a579  mov     rbx, [rsp+1E0h+arg_18]
0x18002a581  add     rsp, 1D0h
0x18002a588  pop     rdi
0x18002a589  pop     rsi
0x18002a58a  pop     rbp
0x18002a58b  retn
0x18002a58c  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x18002a593  mov     edx, 5Eh ; '^'; void *
0x18002a598  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002a59e  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x18002a5a5  mov     edx, 55h ; 'U'; void *
0x18002a5aa  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x18002a5b0  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x18002a5b7  mov     edx, 5Bh ; '['; void *
0x18002a5bc  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
