# winrt::Windows::Internal::AggregatedDataPlatform::ActionFx::implementation::ActionFxCustomEntityStore::DeleteData(winrt::hstring const &,winrt::hstring const &)

- ea: `0x180014780`
- end: `0x180014a36`
- name: `?DeleteData@ActionFxCustomEntityStore@implementation@ActionFx@AggregatedDataPlatform@Internal@Windows@winrt@@QEAAXAEBUhstring@7@0@Z`
- size: `694`
- prototype: `void __fastcall(winrt::Windows::Internal::AggregatedDataPlatform::ActionFx::implementation::ActionFxCustomEntityStore *this, const struct winrt::hstring *, const struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180014740`

## callees

- `0x18000176c`
- `0x180002250`
- `0x180005290`
- `0x18000e1d0`
- `0x180013830`
- `0x180014780`
- `0x180017960`
- `0x180021aa8`
- `0x1800261b8`
- `0x18002888c`
- `0x180031978`
- `0x180034f40`
- `0x180035024`
- `0x180039be4`
- `0x1800807c0`
- `0x1800abe70`
- `0x1800ca010`

## string_xrefs

- `0x180014a21`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\customentitytable.cpp`
- `0x18001490e`: `DELETE FROM CustomEntities WHERE EntityKind = ? AND AppId = ?;`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::AggregatedDataPlatform::ActionFx::implementation::ActionFxCustomEntityStore::DeleteData(
        winrt::Windows::Internal::AggregatedDataPlatform::ActionFx::implementation::ActionFxCustomEntityStore *this,
        const struct winrt::hstring *a2,
        const struct winrt::hstring *a3)
{
  unsigned int v6; // r8d
  const wchar_t *v7; // rbx
  struct sqlite3_stmt *v8; // r14
  const wchar_t *v9; // rsi
  _DWORD *v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  const wchar_t *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rbx
  const char *v17; // r9
  __int128 *v18; // r8
  struct sqlite3_stmt *v19; // rbx
  __int128 *v20; // r8
  const char *v21; // r9
  volatile signed __int32 *v22; // rbx
  struct sqlite3_stmt *v23[2]; // [rsp+40h] [rbp-89h] BYREF
  const wchar_t *v24; // [rsp+50h] [rbp-79h] BYREF
  __int64 v25; // [rsp+58h] [rbp-71h]
  __int64 v26; // [rsp+60h] [rbp-69h] BYREF
  volatile signed __int32 *v27; // [rsp+68h] [rbp-61h]
  RTL_SRWLOCK v28[7]; // [rsp+70h] [rbp-59h] BYREF
  __int128 v29; // [rsp+A8h] [rbp-21h] BYREF
  __m128i v30; // [rsp+B8h] [rbp-11h]
  __int128 v31; // [rsp+C8h] [rbp-1h] BYREF
  __m128i si128; // [rsp+D8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  AggregatorsCommon::Utilities::ValidateText(a2, (const struct winrt::hstring *)0x100, (unsigned int)a3);
  AggregatorsCommon::Utilities::ValidateText(a3, (const struct winrt::hstring *)0x100, v6);
  v7 = &S2;
  if ( *(_QWORD *)a3 )
    v8 = *(struct sqlite3_stmt **)(*(_QWORD *)a3 + 16LL);
  else
    v8 = (struct sqlite3_stmt *)&S2;
  if ( *(_QWORD *)a2 )
    v9 = *(const wchar_t **)(*(_QWORD *)a2 + 16LL);
  else
    v9 = &S2;
  v10 = (_DWORD *)*((_QWORD *)ADPTraceLoggingProvider::Instance() + 1);
  if ( *v10 > 4u )
  {
    v23[0] = v8;
    v24 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
      (__int64)v10,
      (__int64)&byte_1801001BF,
      v11,
      v12,
      &v24,
      (const wchar_t **)v23);
  }
  CustomEntityDatabase::GetCustomEntitiesTable(*((_QWORD *)this + 3), &v26);
  v31 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v31) = 0;
  if ( *(_QWORD *)a2 )
    v13 = *(const wchar_t **)(*(_QWORD *)a2 + 16LL);
  else
    v13 = &S2;
  v14 = -1;
  do
    ++v14;
  while ( v13[v14] );
  v24 = v13;
  v25 = v14;
  to_utf8(&v24, &v31);
  v29 = 0;
  v30 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v29) = 0;
  if ( *(_QWORD *)a3 )
    v7 = *(const wchar_t **)(*(_QWORD *)a3 + 16LL);
  v15 = -1;
  do
    ++v15;
  while ( v7[v15] );
  v24 = v7;
  v25 = v15;
  to_utf8(&v24, &v29);
  v16 = v26;
  ADPDatabase::BeginTransaction(*(_QWORD *)(v26 + 8), (__int64)v28, 0, v17);
  v23[0] = 0;
  sqlite3LockAndPrepare(
    *(_QWORD *)(*(_QWORD *)(v16 + 8) + 32LL),
    (unsigned int)"DELETE FROM CustomEntities WHERE EntityKind = ? AND AppId = ?;",
    -1,
    128,
    0,
    (__int64)v23,
    0);
  v18 = &v31;
  if ( si128.m128i_i64[1] > 0xFuLL )
    LODWORD(v18) = v31;
  v19 = v23[0];
  bindText(v23[0], 1, (_DWORD)v18, -1, 0, 1);
  v20 = &v29;
  if ( v30.m128i_i64[1] > 0xFuLL )
    LODWORD(v20) = v29;
  bindText((_DWORD)v19, 2, (_DWORD)v20, -1, 0, 1);
  if ( (unsigned int)sqlite3_step(v19) != 101 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\customentitytable.cpp",
      v21);
  Transaction::Commit(v28);
  if ( v19 )
    unique_sqlite3_stmt::release_or_terminate(v19);
  Transaction::~Transaction((Transaction *)v28);
  std::string::~string((char **)&v29);
  std::string::~string((char **)&v31);
  v22 = v27;
  if ( v27 && !_InterlockedDecrement(v27 + 2) )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
    if ( !_InterlockedDecrement(v22 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
  }
}

```

## disassembly

```asm
0x180014780  mov     [rsp-8+arg_18], rbx
0x180014785  push    rbp
0x180014786  push    rsi
0x180014787  push    rdi
0x180014788  push    r12
0x18001478a  push    r13
0x18001478c  push    r14
0x18001478e  push    r15
0x180014790  lea     rbp, [rsp-27h]
0x180014795  sub     rsp, 0F0h
0x18001479c  mov     rax, cs:__security_cookie
0x1800147a3  xor     rax, rsp
0x1800147a6  mov     [rbp+57h+var_38], rax
0x1800147aa  mov     r15, r8
0x1800147ad  mov     rdi, rdx
0x1800147b0  mov     r13, rcx
0x1800147b3  mov     ebx, 100h
0x1800147b8  mov     edx, ebx; struct winrt::hstring *
0x1800147ba  mov     rcx, rdi; this
0x1800147bd  call    ?ValidateText@Utilities@AggregatorsCommon@@YAXAEBUhstring@winrt@@I@Z; AggregatorsCommon::Utilities::ValidateText(winrt::hstring const &,uint)
0x1800147c2  mov     edx, ebx; struct winrt::hstring *
0x1800147c4  mov     rcx, r15; this
0x1800147c7  call    ?ValidateText@Utilities@AggregatorsCommon@@YAXAEBUhstring@winrt@@I@Z; AggregatorsCommon::Utilities::ValidateText(winrt::hstring const &,uint)
0x1800147cc  mov     r14, [r15]
0x1800147cf  lea     rbx, S2
0x1800147d6  xor     r12d, r12d
0x1800147d9  test    r14, r14
0x1800147dc  jz      short loc_1800147E4
0x1800147de  mov     r14, [r14+10h]
0x1800147e2  jmp     short loc_1800147E7
0x1800147e4  mov     r14, rbx
0x1800147e7  mov     rax, [rdi]
0x1800147ea  test    rax, rax
0x1800147ed  jz      short loc_1800147F5
0x1800147ef  mov     rsi, [rax+10h]
0x1800147f3  jmp     short loc_1800147F8
0x1800147f5  mov     rsi, rbx
0x1800147f8  call    ?Instance@ADPTraceLoggingProvider@@KAPEAV1@XZ; ADPTraceLoggingProvider::Instance(void)
0x1800147fd  mov     rcx, [rax+8]
0x180014801  mov     eax, [rcx]
0x180014803  cmp     eax, 4
0x180014806  jbe     short loc_180014830
0x180014808  mov     [rsp+120h+var_E0], r14
0x18001480d  mov     [rbp+57h+var_D0], rsi
0x180014811  lea     rax, [rsp+120h+var_E0]
0x180014816  mov     [rsp+120h+var_F8], rax
0x18001481b  lea     rax, [rbp+57h+var_D0]
0x18001481f  mov     [rsp+120h+var_100], rax
0x180014824  lea     rdx, byte_1801001BF
0x18001482b  call    ??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x180014830  lea     rdx, [rbp+57h+var_C0]
0x180014834  mov     rcx, [r13+18h]
0x180014838  call    ?GetCustomEntitiesTable@CustomEntityDatabase@@QEAA?AV?$shared_ptr@UCustomEntityTable@@@std@@XZ; CustomEntityDatabase::GetCustomEntitiesTable(void)
0x18001483d  nop
0x18001483e  xorps   xmm0, xmm0
0x180014841  movups  [rbp+57h+var_58], xmm0
0x180014845  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18001484d  movdqu  [rbp+57h+var_48], xmm1
0x180014852  mov     byte ptr [rbp+57h+var_58], r12b
0x180014856  mov     rcx, [rdi]
0x180014859  test    rcx, rcx
0x18001485c  jz      short loc_180014864
0x18001485e  mov     rcx, [rcx+10h]
0x180014862  jmp     short loc_180014867
0x180014864  mov     rcx, rbx
0x180014867  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001486b  mov     rax, rsi
0x18001486e  inc     rax
0x180014871  cmp     [rcx+rax*2], r12w
0x180014876  jnz     short loc_18001486E
0x180014878  mov     [rbp+57h+var_D0], rcx
0x18001487c  mov     [rbp+57h+var_C8], rax
0x180014880  lea     rdx, [rbp+57h+var_58]
0x180014884  lea     rcx, [rbp+57h+var_D0]
0x180014888  call    ?to_utf8@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; to_utf8(std::wstring_view,std::string &)
0x18001488d  xorps   xmm0, xmm0
0x180014890  movups  [rbp+57h+var_78], xmm0
0x180014894  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18001489c  movdqu  [rbp+57h+var_68], xmm1
0x1800148a1  mov     byte ptr [rbp+57h+var_78], r12b
0x1800148a5  mov     rax, [r15]
0x1800148a8  test    rax, rax
0x1800148ab  jz      short loc_1800148B1
0x1800148ad  mov     rbx, [rax+10h]
0x1800148b1  mov     rax, rsi
0x1800148b4  inc     rax
0x1800148b7  cmp     [rbx+rax*2], r12w
0x1800148bc  jnz     short loc_1800148B4
0x1800148be  mov     [rbp+57h+var_D0], rbx
0x1800148c2  mov     [rbp+57h+var_C8], rax
0x1800148c6  lea     rdx, [rbp+57h+var_78]
0x1800148ca  lea     rcx, [rbp+57h+var_D0]
0x1800148ce  call    ?to_utf8@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; to_utf8(std::wstring_view,std::string &)
0x1800148d3  mov     rbx, [rbp+57h+var_C0]
0x1800148d7  xor     r8d, r8d
0x1800148da  lea     rdx, [rbp+57h+var_B0]
0x1800148de  mov     rcx, [rbx+8]
0x1800148e2  call    ?BeginTransaction@ADPDatabase@@QEAA?AVTransaction@@W4TransactionLockType@@@Z; ADPDatabase::BeginTransaction(TransactionLockType)
0x1800148e7  nop
0x1800148e8  mov     [rsp+120h+var_E0], r12
0x1800148ed  mov     rcx, [rbx+8]
0x1800148f1  mov     [rsp+120h+var_F0], r12
0x1800148f6  lea     rax, [rsp+120h+var_E0]
0x1800148fb  mov     [rsp+120h+var_F8], rax
0x180014900  mov     [rsp+120h+var_100], r12
0x180014905  mov     r9d, 80h
0x18001490b  mov     r8d, esi
0x18001490e  lea     rdx, aDeleteFromCust; "DELETE FROM CustomEntities WHERE Entity"...
0x180014915  mov     rcx, [rcx+20h]
0x180014919  call    sqlite3LockAndPrepare
0x18001491e  lea     r8, [rbp+57h+var_58]
0x180014922  cmp     qword ptr [rbp+57h+var_48+8], 0Fh
0x180014927  cmova   r8, qword ptr [rbp+57h+var_58]
0x18001492c  mov     byte ptr [rsp+120h+var_F8], 1
0x180014931  mov     [rsp+120h+var_100], r12
0x180014936  mov     r9, rsi
0x180014939  mov     edx, 1
0x18001493e  mov     rbx, [rsp+120h+var_E0]
0x180014943  mov     rcx, rbx
0x180014946  call    bindText
0x18001494b  lea     r8, [rbp+57h+var_78]
0x18001494f  cmp     qword ptr [rbp+57h+var_68+8], 0Fh
0x180014954  cmova   r8, qword ptr [rbp+57h+var_78]
0x180014959  mov     byte ptr [rsp+120h+var_F8], 1
0x18001495e  mov     [rsp+120h+var_100], r12
0x180014963  mov     r9, rsi
0x180014966  mov     edx, 2
0x18001496b  mov     rcx, rbx
0x18001496e  call    bindText
0x180014973  mov     rdi, [rbp+5Fh]
0x180014977  mov     rcx, rbx
0x18001497a  call    sqlite3_step
0x18001497f  cmp     eax, 65h ; 'e'
0x180014982  jnz     loc_180014A21
0x180014988  lea     rcx, [rbp+57h+var_B0]; this
0x18001498c  call    ?Commit@Transaction@@QEAAXXZ; Transaction::Commit(void)
0x180014991  nop
0x180014992  test    rbx, rbx
0x180014995  jz      short loc_1800149A0
0x180014997  mov     rcx, rbx; struct sqlite3_stmt *
0x18001499a  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x18001499f  nop
0x1800149a0  lea     rcx, [rbp+57h+var_B0]; this
0x1800149a4  call    ??1Transaction@@QEAA@XZ; Transaction::~Transaction(void)
0x1800149a9  nop
0x1800149aa  lea     rcx, [rbp+57h+var_78]
0x1800149ae  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800149b3  nop
0x1800149b4  lea     rcx, [rbp+57h+var_58]
0x1800149b8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800149bd  nop
0x1800149be  mov     rbx, [rbp+57h+var_B8]
0x1800149c2  test    rbx, rbx
0x1800149c5  jz      short loc_1800149FA
0x1800149c7  mov     eax, esi
0x1800149c9  lock xadd [rbx+8], eax
0x1800149ce  add     eax, esi
0x1800149d0  jnz     short loc_1800149FA
0x1800149d2  mov     rax, [rbx]
0x1800149d5  mov     rcx, rbx
0x1800149d8  mov     rax, [rax]
0x1800149db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149e0  mov     eax, esi
0x1800149e2  lock xadd [rbx+0Ch], eax
0x1800149e7  add     eax, esi
0x1800149e9  jnz     short loc_1800149FA
0x1800149eb  mov     rax, [rbx]
0x1800149ee  mov     rcx, rbx
0x1800149f1  mov     rax, [rax+8]
0x1800149f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149fa  mov     rcx, [rbp+57h+var_38]
0x1800149fe  xor     rcx, rsp; StackCookie
0x180014a01  call    __security_check_cookie
0x180014a06  mov     rbx, [rsp+120h+arg_18]
0x180014a0e  add     rsp, 0F0h
0x180014a15  pop     r15
0x180014a17  pop     r14
0x180014a19  pop     r13
0x180014a1b  pop     r12
0x180014a1d  pop     rdi
0x180014a1e  pop     rsi
0x180014a1f  pop     rbp
0x180014a20  retn
0x180014a21  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180014a28  mov     edx, 6Eh ; 'n'; void *
0x180014a2d  mov     rcx, rdi; this
0x180014a30  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
