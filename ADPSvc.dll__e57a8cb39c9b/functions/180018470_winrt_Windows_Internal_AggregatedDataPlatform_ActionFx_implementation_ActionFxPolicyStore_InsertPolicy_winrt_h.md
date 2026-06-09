# winrt::Windows::Internal::AggregatedDataPlatform::ActionFx::implementation::ActionFxPolicyStore::InsertPolicy(winrt::hstring const &,winrt::hstring const &)

- ea: `0x180018470`
- end: `0x1800186f6`
- name: `?InsertPolicy@ActionFxPolicyStore@implementation@ActionFx@AggregatedDataPlatform@Internal@Windows@winrt@@QEAAXAEBUhstring@7@0@Z`
- size: `646`
- prototype: `void __fastcall(winrt::Windows::Internal::AggregatedDataPlatform::ActionFx::implementation::ActionFxPolicyStore *this, const struct winrt::hstring *, const struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180018430`

## callees

- `0x180001008`
- `0x180002250`
- `0x180005290`
- `0x18000e1d0`
- `0x180013830`
- `0x180017960`
- `0x180018470`
- `0x180021aa8`
- `0x18002888c`
- `0x18002a010`
- `0x180031978`
- `0x180034f40`
- `0x180035024`
- `0x180039be4`
- `0x1800807c0`
- `0x1800abe70`
- `0x1800ca010`

## string_xrefs

- `0x1800186e1`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\actionspolicytable.cpp`
- `0x1800185d8`: `REPLACE INTO ActionsCurationPolicies(UserInterfaceContext, CurationPolicyData, LastUpdatedTimestamp) VALUES (?, ?, datetime('now'));`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::AggregatedDataPlatform::ActionFx::implementation::ActionFxPolicyStore::InsertPolicy(
        winrt::Windows::Internal::AggregatedDataPlatform::ActionFx::implementation::ActionFxPolicyStore *this,
        const struct winrt::hstring *a2,
        const struct winrt::hstring *a3)
{
  unsigned int v6; // r8d
  struct sqlite3_stmt *v7; // rbx
  struct sqlite3_stmt *v8; // rdi
  _DWORD *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  struct sqlite3_stmt *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rbx
  const char *v16; // r9
  __int128 *v17; // r8
  struct sqlite3_stmt *v18; // rbx
  __int128 *v19; // r8
  const char *v20; // r9
  volatile signed __int32 *v21; // rbx
  struct sqlite3_stmt *v22; // [rsp+40h] [rbp-79h] BYREF
  __int64 v23; // [rsp+48h] [rbp-71h]
  __int64 v24; // [rsp+50h] [rbp-69h] BYREF
  volatile signed __int32 *v25; // [rsp+58h] [rbp-61h]
  RTL_SRWLOCK v26[7]; // [rsp+60h] [rbp-59h] BYREF
  __int128 v27; // [rsp+98h] [rbp-21h] BYREF
  __m128i v28; // [rsp+A8h] [rbp-11h]
  __int128 v29; // [rsp+B8h] [rbp-1h] BYREF
  __m128i si128; // [rsp+C8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  AggregatorsCommon::Utilities::ValidateText(a2, (const struct winrt::hstring *)0x400, (unsigned int)a3);
  AggregatorsCommon::Utilities::ValidateText(a3, (const struct winrt::hstring *)0x8000, v6);
  v7 = (struct sqlite3_stmt *)&S2;
  if ( *(_QWORD *)a2 )
    v8 = *(struct sqlite3_stmt **)(*(_QWORD *)a2 + 16LL);
  else
    v8 = (struct sqlite3_stmt *)&S2;
  v9 = (_DWORD *)*((_QWORD *)ADPTraceLoggingProvider::Instance() + 1);
  if ( *v9 > 4u )
  {
    v22 = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (__int64)v9,
      (__int64)byte_1801003E5,
      v10,
      v11,
      (const wchar_t **)&v22);
  }
  ActionsPolicyDatabase::GetActionsPolicyTable(*((_QWORD *)this + 3), &v24);
  v29 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v29) = 0;
  if ( *(_QWORD *)a2 )
    v12 = *(struct sqlite3_stmt **)(*(_QWORD *)a2 + 16LL);
  else
    v12 = (struct sqlite3_stmt *)&S2;
  v13 = -1;
  do
    ++v13;
  while ( *((_WORD *)v12 + v13) );
  v22 = v12;
  v23 = v13;
  to_utf8(&v22, &v29);
  v27 = 0;
  v28 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v27) = 0;
  if ( *(_QWORD *)a3 )
    v7 = *(struct sqlite3_stmt **)(*(_QWORD *)a3 + 16LL);
  v14 = -1;
  do
    ++v14;
  while ( *((_WORD *)v7 + v14) );
  v22 = v7;
  v23 = v14;
  to_utf8(&v22, &v27);
  v15 = v24;
  ADPDatabase::BeginTransaction(*(_QWORD *)(v24 + 8), (__int64)v26, 0, v16);
  v22 = 0;
  sqlite3LockAndPrepare(
    *(_QWORD *)(*(_QWORD *)(v15 + 8) + 32LL),
    (unsigned int)"REPLACE INTO ActionsCurationPolicies(UserInterfaceContext, CurationPolicyData, LastUpdatedTimestamp) V"
                  "ALUES (?, ?, datetime('now'));",
    -1,
    128,
    0,
    (__int64)&v22,
    0);
  v17 = &v29;
  if ( si128.m128i_i64[1] > 0xFuLL )
    LODWORD(v17) = v29;
  v18 = v22;
  bindText((_DWORD)v22, 1, (_DWORD)v17, -1, 0, 1);
  v19 = &v27;
  if ( v28.m128i_i64[1] > 0xFuLL )
    LODWORD(v19) = v27;
  bindText((_DWORD)v18, 2, (_DWORD)v19, -1, 0, 1);
  if ( (unsigned int)sqlite3_step(v18) != 101 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\actionspolicytable.cpp",
      v20);
  Transaction::Commit(v26);
  if ( v18 )
    unique_sqlite3_stmt::release_or_terminate(v18);
  Transaction::~Transaction((Transaction *)v26);
  std::string::~string((char **)&v27);
  std::string::~string((char **)&v29);
  v21 = v25;
  if ( v25 && !_InterlockedDecrement(v25 + 2) )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
    if ( !_InterlockedDecrement(v21 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
  }
}

```

## disassembly

```asm
0x180018470  push    rbp
0x180018472  push    rbx
0x180018473  push    rsi
0x180018474  push    rdi
0x180018475  push    r12
0x180018477  push    r14
0x180018479  push    r15
0x18001847b  lea     rbp, [rsp-27h]
0x180018480  sub     rsp, 0E0h
0x180018487  mov     rax, cs:__security_cookie
0x18001848e  xor     rax, rsp
0x180018491  mov     [rbp+57h+var_38], rax
0x180018495  mov     r14, r8
0x180018498  mov     rsi, rdx
0x18001849b  mov     r15, rcx
0x18001849e  mov     edx, 400h; struct winrt::hstring *
0x1800184a3  mov     rcx, rsi; this
0x1800184a6  call    ?ValidateText@Utilities@AggregatorsCommon@@YAXAEBUhstring@winrt@@I@Z; AggregatorsCommon::Utilities::ValidateText(winrt::hstring const &,uint)
0x1800184ab  mov     edx, 8000h; struct winrt::hstring *
0x1800184b0  mov     rcx, r14; this
0x1800184b3  call    ?ValidateText@Utilities@AggregatorsCommon@@YAXAEBUhstring@winrt@@I@Z; AggregatorsCommon::Utilities::ValidateText(winrt::hstring const &,uint)
0x1800184b8  mov     rdi, [rsi]
0x1800184bb  lea     rbx, S2
0x1800184c2  xor     r12d, r12d
0x1800184c5  test    rdi, rdi
0x1800184c8  jz      short loc_1800184D0
0x1800184ca  mov     rdi, [rdi+10h]
0x1800184ce  jmp     short loc_1800184D3
0x1800184d0  mov     rdi, rbx
0x1800184d3  call    ?Instance@ADPTraceLoggingProvider@@KAPEAV1@XZ; ADPTraceLoggingProvider::Instance(void)
0x1800184d8  mov     rcx, [rax+8]
0x1800184dc  mov     eax, [rcx]
0x1800184de  cmp     eax, 4
0x1800184e1  jbe     short loc_1800184FC
0x1800184e3  mov     [rbp+57h+var_D0], rdi
0x1800184e7  lea     rax, [rbp+57h+var_D0]
0x1800184eb  mov     [rsp+110h+var_F0], rax
0x1800184f0  lea     rdx, byte_1801003E5
0x1800184f7  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1800184fc  lea     rdx, [rbp+57h+var_C0]
0x180018500  mov     rcx, [r15+18h]
0x180018504  call    ?GetActionsPolicyTable@ActionsPolicyDatabase@@QEAA?AV?$shared_ptr@UActionsPolicyTable@@@std@@XZ; ActionsPolicyDatabase::GetActionsPolicyTable(void)
0x180018509  nop
0x18001850a  xorps   xmm0, xmm0
0x18001850d  movups  [rbp+57h+var_58], xmm0
0x180018511  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180018519  movdqu  [rbp+57h+var_48], xmm1
0x18001851e  mov     byte ptr [rbp+57h+var_58], r12b
0x180018522  mov     rcx, [rsi]
0x180018525  test    rcx, rcx
0x180018528  jz      short loc_180018530
0x18001852a  mov     rcx, [rcx+10h]
0x18001852e  jmp     short loc_180018533
0x180018530  mov     rcx, rbx
0x180018533  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180018537  mov     rax, rsi
0x18001853a  inc     rax
0x18001853d  cmp     [rcx+rax*2], r12w
0x180018542  jnz     short loc_18001853A
0x180018544  mov     [rbp+57h+var_D0], rcx
0x180018548  mov     [rbp+57h+var_C8], rax
0x18001854c  lea     rdx, [rbp+57h+var_58]
0x180018550  lea     rcx, [rbp+57h+var_D0]
0x180018554  call    ?to_utf8@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; to_utf8(std::wstring_view,std::string &)
0x180018559  xorps   xmm0, xmm0
0x18001855c  movups  [rbp+57h+var_78], xmm0
0x180018560  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180018568  movdqu  [rbp+57h+var_68], xmm1
0x18001856d  mov     byte ptr [rbp+57h+var_78], r12b
0x180018571  mov     rax, [r14]
0x180018574  test    rax, rax
0x180018577  jz      short loc_18001857D
0x180018579  mov     rbx, [rax+10h]
0x18001857d  mov     rax, rsi
0x180018580  inc     rax
0x180018583  cmp     [rbx+rax*2], r12w
0x180018588  jnz     short loc_180018580
0x18001858a  mov     [rbp+57h+var_D0], rbx
0x18001858e  mov     [rbp+57h+var_C8], rax
0x180018592  lea     rdx, [rbp+57h+var_78]
0x180018596  lea     rcx, [rbp+57h+var_D0]
0x18001859a  call    ?to_utf8@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; to_utf8(std::wstring_view,std::string &)
0x18001859f  mov     rbx, [rbp+57h+var_C0]
0x1800185a3  xor     r8d, r8d
0x1800185a6  lea     rdx, [rbp+57h+var_B0]
0x1800185aa  mov     rcx, [rbx+8]
0x1800185ae  call    ?BeginTransaction@ADPDatabase@@QEAA?AVTransaction@@W4TransactionLockType@@@Z; ADPDatabase::BeginTransaction(TransactionLockType)
0x1800185b3  nop
0x1800185b4  mov     [rbp+57h+var_D0], r12
0x1800185b8  mov     rcx, [rbx+8]
0x1800185bc  mov     [rsp+110h+var_E0], r12
0x1800185c1  lea     rax, [rbp+57h+var_D0]
0x1800185c5  mov     [rsp+110h+var_E8], rax
0x1800185ca  mov     [rsp+110h+var_F0], r12
0x1800185cf  mov     r9d, 80h
0x1800185d5  mov     r8d, esi
0x1800185d8  lea     rdx, aReplaceIntoAct; "REPLACE INTO ActionsCurationPolicies(Us"...
0x1800185df  mov     rcx, [rcx+20h]
0x1800185e3  call    sqlite3LockAndPrepare
0x1800185e8  lea     r8, [rbp+57h+var_58]
0x1800185ec  cmp     qword ptr [rbp+57h+var_48+8], 0Fh
0x1800185f1  cmova   r8, qword ptr [rbp+57h+var_58]
0x1800185f6  mov     byte ptr [rsp+110h+var_E8], 1
0x1800185fb  mov     [rsp+110h+var_F0], r12
0x180018600  mov     r9, rsi
0x180018603  mov     edx, 1
0x180018608  mov     rbx, [rbp+57h+var_D0]
0x18001860c  mov     rcx, rbx
0x18001860f  call    bindText
0x180018614  lea     r8, [rbp+57h+var_78]
0x180018618  cmp     qword ptr [rbp+57h+var_68+8], 0Fh
0x18001861d  cmova   r8, qword ptr [rbp+57h+var_78]
0x180018622  mov     byte ptr [rsp+110h+var_E8], 1
0x180018627  mov     [rsp+110h+var_F0], r12
0x18001862c  mov     r9, rsi
0x18001862f  mov     edx, 2
0x180018634  mov     rcx, rbx
0x180018637  call    bindText
0x18001863c  mov     rdi, [rbp+5Fh]
0x180018640  mov     rcx, rbx
0x180018643  call    sqlite3_step
0x180018648  cmp     eax, 65h ; 'e'
0x18001864b  jnz     loc_1800186E1
0x180018651  lea     rcx, [rbp+57h+var_B0]; this
0x180018655  call    ?Commit@Transaction@@QEAAXXZ; Transaction::Commit(void)
0x18001865a  nop
0x18001865b  test    rbx, rbx
0x18001865e  jz      short loc_180018669
0x180018660  mov     rcx, rbx; struct sqlite3_stmt *
0x180018663  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x180018668  nop
0x180018669  lea     rcx, [rbp+57h+var_B0]; this
0x18001866d  call    ??1Transaction@@QEAA@XZ; Transaction::~Transaction(void)
0x180018672  nop
0x180018673  lea     rcx, [rbp+57h+var_78]
0x180018677  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001867c  nop
0x18001867d  lea     rcx, [rbp+57h+var_58]
0x180018681  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180018686  nop
0x180018687  mov     rbx, [rbp+57h+var_B8]
0x18001868b  test    rbx, rbx
0x18001868e  jz      short loc_1800186C3
0x180018690  mov     eax, esi
0x180018692  lock xadd [rbx+8], eax
0x180018697  add     eax, esi
0x180018699  jnz     short loc_1800186C3
0x18001869b  mov     rax, [rbx]
0x18001869e  mov     rcx, rbx
0x1800186a1  mov     rax, [rax]
0x1800186a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186a9  mov     eax, esi
0x1800186ab  lock xadd [rbx+0Ch], eax
0x1800186b0  add     eax, esi
0x1800186b2  jnz     short loc_1800186C3
0x1800186b4  mov     rax, [rbx]
0x1800186b7  mov     rcx, rbx
0x1800186ba  mov     rax, [rax+8]
0x1800186be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186c3  mov     rcx, [rbp+57h+var_38]
0x1800186c7  xor     rcx, rsp; StackCookie
0x1800186ca  call    __security_check_cookie
0x1800186cf  add     rsp, 0E0h
0x1800186d6  pop     r15
0x1800186d8  pop     r14
0x1800186da  pop     r12
0x1800186dc  pop     rdi
0x1800186dd  pop     rsi
0x1800186de  pop     rbx
0x1800186df  pop     rbp
0x1800186e0  retn
0x1800186e1  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x1800186e8  mov     edx, 1Ch; void *
0x1800186ed  mov     rcx, rdi; this
0x1800186f0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
