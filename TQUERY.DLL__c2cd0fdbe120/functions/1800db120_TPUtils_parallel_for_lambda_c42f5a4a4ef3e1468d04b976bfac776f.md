# TPUtils::parallel_for__lambda_c42f5a4a4ef3e1468d04b976bfac776f___

- ea: `0x1800db120`
- end: `0x1800db37a`
- name: `TPUtils::parallel_for__lambda_c42f5a4a4ef3e1468d04b976bfac776f___`
- size: `602`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800da790`

## callees

- `0x18002cc2c`
- `0x18002dc24`
- `0x180038f08`
- `0x180043ccc`
- `0x180043d18`
- `0x1800db120`
- `0x180147154`
- `0x180157c70`
- `0x18015f050`
- `0x18016dcf4`
- `0x180188d90`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800db2ba`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800db2ba`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800db283`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800db283`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800db326`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800db326`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800db2e2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800db2e2`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800db1c8`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800db1c8`

## string_xrefs

- `0x1800db29d`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`
- `0x1800db311`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall TPUtils::parallel_for__lambda_c42f5a4a4ef3e1468d04b976bfac776f___(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 ProcessorCount; // r8
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // r13
  unsigned __int64 v11; // rdi
  __int64 Catalog; // r15
  _BYTE *v13; // rsi
  __int64 v14; // rdx
  unsigned __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rax
  struct _TP_WORK *ThreadpoolWork; // rsi
  __int64 v19; // r8
  const char *v20; // r9
  int v21[2]; // [rsp+20h] [rbp-E0h]
  _BYTE v22[56]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE *v23; // [rsp+68h] [rbp-98h]
  _BYTE pv[1104]; // [rsp+70h] [rbp-90h] BYREF
  int v25; // [rsp+4C0h] [rbp+3C0h]
  TPResultException *v26; // [rsp+4C8h] [rbp+3C8h]
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+428h]

  v5 = 0;
  ProcessorCount = TPUtils::GetProcessorCount();
  if ( ProcessorCount == 1 || a2 <= 1 )
  {
    if ( !a2 )
      return;
    goto LABEL_31;
  }
  if ( (unsigned int)TPUtils::s_runningThreadCount > 0x19 )
  {
    do
LABEL_31:
      lambda_c42f5a4a4ef3e1468d04b976bfac776f_::operator()(a3, (unsigned int)v5++, ProcessorCount);
    while ( v5 < a2 );
    return;
  }
  v7 = a2 / ProcessorCount;
  v8 = a2 % ProcessorCount;
  v9 = a2 / ProcessorCount;
  if ( !(a2 / ProcessorCount) )
    v9 = 1;
  *(_QWORD *)v21 = v9;
  v10 = (a2 % ProcessorCount) & -(__int64)(v7 != 0);
  if ( v7 )
    v8 = ProcessorCount;
  v11 = v8 - 1;
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( g_isPerUserCatalogEnabled )
    Catalog = PerUserCatalogNameForCorruption::GetCatalog();
  else
    Catalog = 0;
  v13 = (_BYTE *)std::_Global_new_std::_Func_impl_no_alloc__lambda_c42f5a4a4ef3e1468d04b976bfac776f__void_unsigned___int64___lambda_c42f5a4a4ef3e1468d04b976bfac776f__const___(a3);
  v23 = v13;
  TPUtils::_SParallelForContext::_SParallelForContext(pv, v22, v11, Catalog);
  if ( v13 )
  {
    LOBYTE(v14) = v13 != v22;
    (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v13 + 32LL))(v13, v14);
  }
  if ( v11 )
  {
    v15 = 0;
    do
    {
      *(_QWORD *)&pv[16 * v15 + 80] = v5;
      v16 = *(_QWORD *)v21 + 1LL;
      if ( !v10 )
        v16 = *(_QWORD *)v21;
      v5 += v16;
      *(_QWORD *)&pv[16 * v15++ + 88] = v5;
      v17 = v10 - 1;
      if ( !v10 )
        v17 = 0;
      v10 = v17;
    }
    while ( v15 < v11 );
  }
  ThreadpoolWork = CreateThreadpoolWork(TPUtils::_ParallelForCallback, pv, 0);
  if ( !ThreadpoolWork )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\TPUtils.h",
      v20);
  for ( ; v11; --v11 )
    SubmitThreadpoolWork(ThreadpoolWork);
  do
    lambda_c42f5a4a4ef3e1468d04b976bfac776f_::operator()(a3, (unsigned int)v5++, v19);
  while ( v5 < a2 );
  WaitForThreadpoolWorkCallbacks(ThreadpoolWork, 0);
  if ( v25 > 0 )
  {
    if ( v26 )
      TPResultException::raise(v26);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x194,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\TPUtils.h",
      (const char *)0x8000FFFFLL,
      (int)ThreadpoolWork);
  }
  CloseThreadpoolWork(ThreadpoolWork);
  TPUtils::_SParallelForContext::~_SParallelForContext((TPUtils::_SParallelForContext *)pv);
}

```

## disassembly

```asm
0x1800db120  mov     [rsp-8+arg_0], rbx
0x1800db125  push    rbp
0x1800db126  push    rsi
0x1800db127  push    rdi
0x1800db128  push    r12
0x1800db12a  push    r13
0x1800db12c  push    r14
0x1800db12e  push    r15
0x1800db130  lea     rbp, [rsp-3F0h]
0x1800db138  sub     rsp, 4F0h
0x1800db13f  mov     rax, cs:__security_cookie
0x1800db146  xor     rax, rsp
0x1800db149  mov     [rbp+420h+var_40], rax
0x1800db150  mov     r12, r8
0x1800db153  mov     r14, rdx
0x1800db156  xor     ebx, ebx
0x1800db158  call    ?GetProcessorCount@TPUtils@@SA_KXZ; TPUtils::GetProcessorCount(void)
0x1800db15d  mov     r8, rax
0x1800db160  lea     esi, [rbx+1]
0x1800db163  cmp     rax, rsi
0x1800db166  jz      loc_1800DB339
0x1800db16c  cmp     r14, rsi
0x1800db16f  jbe     loc_1800DB339
0x1800db175  mov     eax, cs:?s_runningThreadCount@TPUtils@@0JC; long volatile TPUtils::s_runningThreadCount
0x1800db17b  cmp     eax, 19h
0x1800db17e  ja      loc_1800DB33E
0x1800db184  xor     edx, edx
0x1800db186  mov     rax, r14
0x1800db189  div     r8
0x1800db18c  mov     rdi, rdx
0x1800db18f  mov     rcx, rax
0x1800db192  test    rax, rax
0x1800db195  cmovz   rcx, rsi
0x1800db199  mov     qword ptr [rsp+520h+var_500], rcx
0x1800db19e  mov     rcx, rax
0x1800db1a1  neg     rcx
0x1800db1a4  sbb     r13, r13
0x1800db1a7  and     r13, rdx
0x1800db1aa  test    rax, rax
0x1800db1ad  cmovnz  rdi, r8
0x1800db1b1  sub     rdi, rsi
0x1800db1b4  xor     r9d, r9d; Context
0x1800db1b7  xor     r8d, r8d; Parameter
0x1800db1ba  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800db1c1  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1800db1c8  call    cs:__imp_InitOnceExecuteOnce
0x1800db1ce  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, bl; bool g_isPerUserCatalogEnabled
0x1800db1d4  jz      short loc_1800DB1E0
0x1800db1d6  call    PerUserCatalogNameForCorruption__GetCatalog
0x1800db1db  mov     r15, rax
0x1800db1de  jmp     short loc_1800DB1E3
0x1800db1e0  xor     r15d, r15d
0x1800db1e3  mov     [rsp+520h+var_4B8], rbx
0x1800db1e8  mov     rcx, r12
0x1800db1eb  call    std___Global_new_std___Func_impl_no_alloc__lambda_c42f5a4a4ef3e1468d04b976bfac776f__void_unsigned___int64___lambda_c42f5a4a4ef3e1468d04b976bfac776f__const___
0x1800db1f0  mov     rsi, rax
0x1800db1f3  mov     [rsp+520h+var_4B8], rax
0x1800db1f8  mov     r9, r15
0x1800db1fb  mov     r8, rdi
0x1800db1fe  lea     rdx, [rsp+520h+var_4F0]
0x1800db203  lea     rcx, [rsp+520h+pv]
0x1800db208  call    ??0_SParallelForContext@TPUtils@@QEAA@AEBV?$function@$$A6AX_K@Z@std@@_KPEB_W@Z; TPUtils::_SParallelForContext::_SParallelForContext(std::function<void (unsigned __int64)> const &,unsigned __int64,wchar_t const *)
0x1800db20d  nop
0x1800db20e  test    rsi, rsi
0x1800db211  jz      short loc_1800DB22D
0x1800db213  mov     rax, [rsi]
0x1800db216  lea     rcx, [rsp+520h+var_4F0]
0x1800db21b  cmp     rsi, rcx
0x1800db21e  setnz   dl
0x1800db221  mov     rcx, rsi
0x1800db224  mov     rax, [rax+20h]
0x1800db228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800db22d  test    rdi, rdi
0x1800db230  jz      short loc_1800DB26D
0x1800db232  xor     edx, edx
0x1800db234  mov     r8, qword ptr [rsp+520h+var_500]
0x1800db239  mov     rcx, rdx
0x1800db23c  add     rcx, rcx
0x1800db23f  mov     [rbp+rcx*8+420h+var_460], rbx
0x1800db244  lea     rax, [r8+1]
0x1800db248  test    r13, r13
0x1800db24b  cmovz   rax, r8
0x1800db24f  add     rbx, rax
0x1800db252  mov     [rbp+rcx*8+420h+var_458], rbx
0x1800db257  inc     rdx
0x1800db25a  lea     rax, [r13-1]
0x1800db25e  test    r13, r13
0x1800db261  cmovz   rax, r13
0x1800db265  mov     r13, rax
0x1800db268  cmp     rdx, rdi
0x1800db26b  jb      short loc_1800DB239
0x1800db26d  mov     [rsp+520h+var_4F8], 1
0x1800db274  xor     r8d, r8d; pcbe
0x1800db277  lea     rdx, [rsp+520h+pv]; pv
0x1800db27c  lea     rcx, ?_ParallelForCallback@TPUtils@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800db283  call    cs:__imp_CreateThreadpoolWork
0x1800db289  mov     rsi, rax
0x1800db28c  mov     qword ptr [rsp+520h+var_500], rax; int
0x1800db291  test    rax, rax
0x1800db294  jnz     short loc_1800DB2AD
0x1800db296  mov     rcx, [rbp+428h]; this
0x1800db29d  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800db2a4  lea     edx, [rax+7Eh]; void *
0x1800db2a7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800db2ad  mov     byte ptr [rsp+520h+var_4F8+1], 1
0x1800db2b2  test    rdi, rdi
0x1800db2b5  jz      short loc_1800DB2C6
0x1800db2b7  mov     rcx, rsi; pwk
0x1800db2ba  call    cs:__imp_SubmitThreadpoolWork
0x1800db2c0  sub     rdi, 1
0x1800db2c4  jnz     short loc_1800DB2B7
0x1800db2c6  mov     edx, ebx
0x1800db2c8  mov     rcx, r12
0x1800db2cb  call    _lambda_c42f5a4a4ef3e1468d04b976bfac776f___operator__
0x1800db2d0  inc     rbx
0x1800db2d3  cmp     rbx, r14
0x1800db2d6  jb      short loc_1800DB2C6
0x1800db2d8  mov     byte ptr [rsp+520h+var_4F8+1], 0
0x1800db2dd  xor     edx, edx; fCancelPendingCallbacks
0x1800db2df  mov     rcx, rsi; pwk
0x1800db2e2  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800db2e8  mov     eax, [rbp+420h+var_60]
0x1800db2ee  test    eax, eax
0x1800db2f0  jle     short loc_1800DB323
0x1800db2f2  mov     rcx, [rbp+420h+var_58]; this
0x1800db2f9  test    rcx, rcx
0x1800db2fc  jz      short loc_1800DB304
0x1800db2fe  call    ?raise@TPResultException@@UEAAXXZ; TPResultException::raise(void)
0x1800db304  mov     rcx, [rbp+428h]; this
0x1800db30b  mov     r9d, 8000FFFFh; char *
0x1800db311  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1800db318  mov     edx, 194h; void *
0x1800db31d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800db323  mov     rcx, rsi; pwk
0x1800db326  call    cs:__imp_CloseThreadpoolWork
0x1800db32c  nop
0x1800db32d  lea     rcx, [rsp+520h+pv]; this
0x1800db332  call    ??1_SParallelForContext@TPUtils@@QEAA@XZ; TPUtils::_SParallelForContext::~_SParallelForContext(void)
0x1800db337  jmp     short loc_1800DB350
0x1800db339  test    r14, r14
0x1800db33c  jz      short loc_1800DB350
0x1800db33e  mov     edx, ebx
0x1800db340  mov     rcx, r12
0x1800db343  call    _lambda_c42f5a4a4ef3e1468d04b976bfac776f___operator__
0x1800db348  add     rbx, rsi
0x1800db34b  cmp     rbx, r14
0x1800db34e  jb      short loc_1800DB33E
0x1800db350  mov     rcx, [rbp+420h+var_40]
0x1800db357  xor     rcx, rsp; StackCookie
0x1800db35a  call    __security_check_cookie
0x1800db35f  mov     rbx, [rsp+520h+arg_0]
0x1800db367  add     rsp, 4F0h
0x1800db36e  pop     r15
0x1800db370  pop     r14
0x1800db372  pop     r13
0x1800db374  pop     r12
0x1800db376  pop     rdi
0x1800db377  pop     rsi
0x1800db378  pop     rbp
0x1800db379  retn
```
