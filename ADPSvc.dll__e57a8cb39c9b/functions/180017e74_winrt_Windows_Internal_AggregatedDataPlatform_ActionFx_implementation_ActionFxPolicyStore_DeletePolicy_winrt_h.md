# winrt::Windows::Internal::AggregatedDataPlatform::ActionFx::implementation::ActionFxPolicyStore::DeletePolicy(winrt::hstring const &)

- ea: `0x180017e74`
- end: `0x180018073`
- name: `?DeletePolicy@ActionFxPolicyStore@implementation@ActionFx@AggregatedDataPlatform@Internal@Windows@winrt@@QEAAXAEBUhstring@7@@Z`
- size: `511`
- prototype: `void __fastcall(winrt::Windows::Internal::AggregatedDataPlatform::ActionFx::implementation::ActionFxPolicyStore *this, const struct winrt::hstring *, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180017e40`

## callees

- `0x180001008`
- `0x180002250`
- `0x180005290`
- `0x18000e1d0`
- `0x180013830`
- `0x180017960`
- `0x180017e74`
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

- `0x18001805e`: `onecoreuap\base\appmodel\aggregateddataplatform\service\datastores\actionspolicytable.cpp`
- `0x180017f82`: `DELETE FROM ActionsCurationPolicies WHERE UserInterfaceContext = ?;`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::AggregatedDataPlatform::ActionFx::implementation::ActionFxPolicyStore::DeletePolicy(
        winrt::Windows::Internal::AggregatedDataPlatform::ActionFx::implementation::ActionFxPolicyStore *this,
        const struct winrt::hstring *a2,
        unsigned int a3)
{
  struct sqlite3_stmt *v5; // rbx
  struct sqlite3_stmt *v6; // rsi
  _DWORD *v7; // rcx
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // rax
  __int64 v11; // rbx
  __int128 *v12; // r8
  struct sqlite3_stmt *v13; // rbx
  const char *v14; // r9
  volatile signed __int32 *v15; // rbx
  struct sqlite3_stmt *v16[2]; // [rsp+40h] [rbp-49h] BYREF
  __int64 v17; // [rsp+50h] [rbp-39h] BYREF
  volatile signed __int32 *v18; // [rsp+58h] [rbp-31h]
  _BYTE v19[56]; // [rsp+60h] [rbp-29h] BYREF
  __int128 v20; // [rsp+98h] [rbp+Fh] BYREF
  __m128i si128; // [rsp+A8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  AggregatorsCommon::Utilities::ValidateText(a2, (const struct winrt::hstring *)0x400, a3);
  v5 = (struct sqlite3_stmt *)&S2;
  if ( *(_QWORD *)a2 )
    v6 = *(struct sqlite3_stmt **)(*(_QWORD *)a2 + 16LL);
  else
    v6 = (struct sqlite3_stmt *)&S2;
  v7 = (_DWORD *)*((_QWORD *)ADPTraceLoggingProvider::Instance() + 1);
  if ( *v7 > 4u )
  {
    v16[0] = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (_DWORD)v7,
      (unsigned int)&byte_18010030F,
      v8,
      v9,
      (__int64)v16);
  }
  ActionsPolicyDatabase::GetActionsPolicyTable(*((_QWORD *)this + 3), &v17);
  v20 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v20) = 0;
  if ( *(_QWORD *)a2 )
    v5 = *(struct sqlite3_stmt **)(*(_QWORD *)a2 + 16LL);
  v10 = -1;
  do
    ++v10;
  while ( *((_WORD *)v5 + v10) );
  v16[0] = v5;
  v16[1] = (struct sqlite3_stmt *)v10;
  to_utf8(v16, &v20);
  v11 = v17;
  ADPDatabase::BeginTransaction(*(_QWORD *)(v17 + 8), v19, 0);
  v16[0] = 0;
  sqlite3LockAndPrepare(
    *(_QWORD *)(*(_QWORD *)(v11 + 8) + 32LL),
    (unsigned int)"DELETE FROM ActionsCurationPolicies WHERE UserInterfaceContext = ?;",
    -1,
    128,
    0,
    (__int64)v16,
    0);
  v12 = &v20;
  if ( si128.m128i_i64[1] > 0xFuLL )
    LODWORD(v12) = v20;
  v13 = v16[0];
  bindText(v16[0], 1, (_DWORD)v12, -1, 0, 1);
  if ( (unsigned int)sqlite3_step(v13) != 101 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecoreuap\\base\\appmodel\\aggregateddataplatform\\service\\datastores\\actionspolicytable.cpp",
      v14);
  Transaction::Commit((Transaction *)v19);
  if ( v13 )
    unique_sqlite3_stmt::release_or_terminate(v13);
  Transaction::~Transaction((Transaction *)v19);
  std::string::~string(&v20);
  v15 = v18;
  if ( v18 && !_InterlockedDecrement(v18 + 2) )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
    if ( !_InterlockedDecrement(v15 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
  }
}

```

## disassembly

```asm
0x180017e74  mov     [rsp-8+arg_10], rbx
0x180017e79  push    rbp
0x180017e7a  push    rsi
0x180017e7b  push    rdi
0x180017e7c  push    r14
0x180017e7e  push    r15
0x180017e80  lea     rbp, [rsp-37h]
0x180017e85  sub     rsp, 0C0h
0x180017e8c  mov     rax, cs:__security_cookie
0x180017e93  xor     rax, rsp
0x180017e96  mov     [rbp+57h+var_28], rax
0x180017e9a  mov     rdi, rdx
0x180017e9d  mov     r14, rcx
0x180017ea0  mov     edx, 400h; struct winrt::hstring *
0x180017ea5  mov     rcx, rdi; this
0x180017ea8  call    ?ValidateText@Utilities@AggregatorsCommon@@YAXAEBUhstring@winrt@@I@Z; AggregatorsCommon::Utilities::ValidateText(winrt::hstring const &,uint)
0x180017ead  mov     rsi, [rdi]
0x180017eb0  lea     rbx, S2
0x180017eb7  xor     r15d, r15d
0x180017eba  test    rsi, rsi
0x180017ebd  jz      short loc_180017EC5
0x180017ebf  mov     rsi, [rsi+10h]
0x180017ec3  jmp     short loc_180017EC8
0x180017ec5  mov     rsi, rbx
0x180017ec8  call    ?Instance@ADPTraceLoggingProvider@@KAPEAV1@XZ; ADPTraceLoggingProvider::Instance(void)
0x180017ecd  mov     rcx, [rax+8]
0x180017ed1  mov     eax, [rcx]
0x180017ed3  cmp     eax, 4
0x180017ed6  jbe     short loc_180017EF1
0x180017ed8  mov     [rbp+57h+var_A0], rsi
0x180017edc  lea     rax, [rbp+57h+var_A0]
0x180017ee0  mov     [rsp+0E0h+var_C0], rax
0x180017ee5  lea     rdx, byte_18010030F
0x180017eec  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180017ef1  lea     rdx, [rbp+57h+var_90]
0x180017ef5  mov     rcx, [r14+18h]
0x180017ef9  call    ?GetActionsPolicyTable@ActionsPolicyDatabase@@QEAA?AV?$shared_ptr@UActionsPolicyTable@@@std@@XZ; ActionsPolicyDatabase::GetActionsPolicyTable(void)
0x180017efe  nop
0x180017eff  xorps   xmm0, xmm0
0x180017f02  movups  [rbp+57h+var_48], xmm0
0x180017f06  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180017f0e  movdqu  [rbp+57h+var_38], xmm1
0x180017f13  mov     byte ptr [rbp+57h+var_48], r15b
0x180017f17  mov     rax, [rdi]
0x180017f1a  test    rax, rax
0x180017f1d  jz      short loc_180017F23
0x180017f1f  mov     rbx, [rax+10h]
0x180017f23  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180017f27  mov     rax, rsi
0x180017f2a  inc     rax
0x180017f2d  cmp     [rbx+rax*2], r15w
0x180017f32  jnz     short loc_180017F2A
0x180017f34  mov     [rbp+57h+var_A0], rbx
0x180017f38  mov     [rbp+57h+var_98], rax
0x180017f3c  lea     rdx, [rbp+57h+var_48]
0x180017f40  lea     rcx, [rbp+57h+var_A0]
0x180017f44  call    ?to_utf8@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; to_utf8(std::wstring_view,std::string &)
0x180017f49  mov     rbx, [rbp+57h+var_90]
0x180017f4d  xor     r8d, r8d
0x180017f50  lea     rdx, [rbp+57h+var_80]
0x180017f54  mov     rcx, [rbx+8]
0x180017f58  call    ?BeginTransaction@ADPDatabase@@QEAA?AVTransaction@@W4TransactionLockType@@@Z; ADPDatabase::BeginTransaction(TransactionLockType)
0x180017f5d  nop
0x180017f5e  mov     [rbp+57h+var_A0], r15
0x180017f62  mov     rcx, [rbx+8]
0x180017f66  mov     [rsp+0E0h+var_B0], r15
0x180017f6b  lea     rax, [rbp+57h+var_A0]
0x180017f6f  mov     [rsp+0E0h+var_B8], rax
0x180017f74  mov     [rsp+0E0h+var_C0], r15
0x180017f79  mov     r9d, 80h
0x180017f7f  mov     r8d, esi
0x180017f82  lea     rdx, aDeleteFromActi; "DELETE FROM ActionsCurationPolicies WHE"...
0x180017f89  mov     rcx, [rcx+20h]
0x180017f8d  call    sqlite3LockAndPrepare
0x180017f92  lea     r8, [rbp+57h+var_48]
0x180017f96  cmp     qword ptr [rbp+57h+var_38+8], 0Fh
0x180017f9b  cmova   r8, qword ptr [rbp+57h+var_48]
0x180017fa0  mov     byte ptr [rsp+0E0h+var_B8], 1
0x180017fa5  mov     [rsp+0E0h+var_C0], r15
0x180017faa  mov     r9, rsi
0x180017fad  mov     edx, 1
0x180017fb2  mov     rbx, [rbp+57h+var_A0]
0x180017fb6  mov     rcx, rbx
0x180017fb9  call    bindText
0x180017fbe  mov     rdi, [rbp+5Fh]
0x180017fc2  mov     rcx, rbx
0x180017fc5  call    sqlite3_step
0x180017fca  cmp     eax, 65h ; 'e'
0x180017fcd  jnz     loc_18001805E
0x180017fd3  lea     rcx, [rbp+57h+var_80]; this
0x180017fd7  call    ?Commit@Transaction@@QEAAXXZ; Transaction::Commit(void)
0x180017fdc  nop
0x180017fdd  test    rbx, rbx
0x180017fe0  jz      short loc_180017FEB
0x180017fe2  mov     rcx, rbx; struct sqlite3_stmt *
0x180017fe5  call    ?release_or_terminate@unique_sqlite3_stmt@@CAXPEAUsqlite3_stmt@@@Z; unique_sqlite3_stmt::release_or_terminate(sqlite3_stmt *)
0x180017fea  nop
0x180017feb  lea     rcx, [rbp+57h+var_80]; this
0x180017fef  call    ??1Transaction@@QEAA@XZ; Transaction::~Transaction(void)
0x180017ff4  nop
0x180017ff5  lea     rcx, [rbp+57h+var_48]
0x180017ff9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180017ffe  nop
0x180017fff  mov     rbx, [rbp+57h+var_88]
0x180018003  test    rbx, rbx
0x180018006  jz      short loc_18001803B
0x180018008  mov     eax, esi
0x18001800a  lock xadd [rbx+8], eax
0x18001800f  add     eax, esi
0x180018011  jnz     short loc_18001803B
0x180018013  mov     rax, [rbx]
0x180018016  mov     rcx, rbx
0x180018019  mov     rax, [rax]
0x18001801c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018021  mov     eax, esi
0x180018023  lock xadd [rbx+0Ch], eax
0x180018028  add     eax, esi
0x18001802a  jnz     short loc_18001803B
0x18001802c  mov     rax, [rbx]
0x18001802f  mov     rcx, rbx
0x180018032  mov     rax, [rax+8]
0x180018036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001803b  mov     rcx, [rbp+57h+var_28]
0x18001803f  xor     rcx, rsp; StackCookie
0x180018042  call    __security_check_cookie
0x180018047  mov     rbx, [rsp+0E0h+arg_10]
0x18001804f  add     rsp, 0C0h
0x180018056  pop     r15
0x180018058  pop     r14
0x18001805a  pop     rdi
0x18001805b  pop     rsi
0x18001805c  pop     rbp
0x18001805d  retn
0x18001805e  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\aggregatedd"...
0x180018065  mov     edx, 41h ; 'A'; void *
0x18001806a  mov     rcx, rdi; this
0x18001806d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
