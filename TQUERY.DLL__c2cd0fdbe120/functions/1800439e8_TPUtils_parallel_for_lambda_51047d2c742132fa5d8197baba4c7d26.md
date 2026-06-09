# TPUtils::parallel_for__lambda_51047d2c742132fa5d8197baba4c7d26___

- ea: `0x1800439e8`
- end: `0x180043c43`
- name: `TPUtils::parallel_for__lambda_51047d2c742132fa5d8197baba4c7d26___`
- size: `603`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180043770`

## callees

- `0x18002cc2c`
- `0x18002dc24`
- `0x180038f08`
- `0x1800439e8`
- `0x180043c64`
- `0x180043ccc`
- `0x180043d18`
- `0x180147154`
- `0x180157c70`
- `0x180188d90`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180043b5b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180043b5b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180043b37`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180043b37`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180043b96`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180043b96`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180043b83`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180043b83`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180043a8e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180043a8e`

## string_xrefs

- `0x180043c0b`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`
- `0x180043c2b`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall TPUtils::parallel_for__lambda_51047d2c742132fa5d8197baba4c7d26___(
        __int64 a1,
        unsigned __int64 a2,
        __int128 *a3)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 ProcessorCount; // r8
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rdi
  __int64 v9; // r13
  __int64 v10; // rsi
  unsigned __int64 v11; // rdi
  __int64 Catalog; // rax
  __int64 (__fastcall ***v13)(); // rdx
  struct _TP_WORK *ThreadpoolWork; // rsi
  __int64 v15; // r8
  const char *v16; // r9
  unsigned __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 (__fastcall **v20)(); // [rsp+30h] [rbp-D0h] BYREF
  __int128 v21; // [rsp+38h] [rbp-C8h]
  __int128 v22; // [rsp+48h] [rbp-B8h]
  __int128 v23; // [rsp+58h] [rbp-A8h]
  __int64 (__fastcall ***v24)(); // [rsp+68h] [rbp-98h]
  _BYTE pv[1104]; // [rsp+70h] [rbp-90h] BYREF
  int v26; // [rsp+4C0h] [rbp+3C0h]
  TPResultException *v27; // [rsp+4C8h] [rbp+3C8h]
  wil::details::in1diag3 *retaddr; // [rsp+518h] [rbp+418h]

  v5 = 0;
  ProcessorCount = TPUtils::GetProcessorCount();
  if ( ProcessorCount == 1 || a2 <= 1 )
  {
    if ( !a2 )
      return;
    goto LABEL_22;
  }
  if ( (unsigned int)TPUtils::s_runningThreadCount > 0x19 )
  {
    do
LABEL_22:
      lambda_51047d2c742132fa5d8197baba4c7d26_::operator()(a3, (unsigned int)v5++, ProcessorCount);
    while ( v5 < a2 );
    return;
  }
  v7 = a2 / ProcessorCount;
  v8 = a2 % ProcessorCount;
  v9 = a2 / ProcessorCount;
  if ( !(a2 / ProcessorCount) )
    v9 = 1;
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
  v20 = off_1802C1398;
  v21 = *a3;
  v22 = a3[1];
  v23 = a3[2];
  v24 = &v20;
  TPUtils::_SParallelForContext::_SParallelForContext(pv, &v20, v11, Catalog);
  if ( v24 )
  {
    v13 = &v20;
    LOBYTE(v13) = v24 != &v20;
    ((void (__fastcall *)(__int64 (__fastcall ***)(), __int64 (__fastcall ***)()))(*v24)[4])(v24, v13);
    v24 = 0;
  }
  if ( v11 )
  {
    v17 = 0;
    do
    {
      *(_QWORD *)&pv[16 * v17 + 80] = v5;
      v18 = v9 + 1;
      if ( !v10 )
        v18 = v9;
      v5 += v18;
      *(_QWORD *)&pv[16 * v17++ + 88] = v5;
      v19 = v10 - 1;
      if ( !v10 )
        v19 = 0;
      v10 = v19;
    }
    while ( v17 < v11 );
  }
  ThreadpoolWork = CreateThreadpoolWork(TPUtils::_ParallelForCallback, pv, 0);
  if ( !ThreadpoolWork )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\TPUtils.h",
      v16);
  for ( ; v11; --v11 )
    SubmitThreadpoolWork(ThreadpoolWork);
  do
    lambda_51047d2c742132fa5d8197baba4c7d26_::operator()(a3, (unsigned int)v5++, v15);
  while ( v5 < a2 );
  WaitForThreadpoolWorkCallbacks(ThreadpoolWork, 0);
  if ( v26 > 0 )
  {
    if ( !v27 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x194,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\TPUtils.h",
        (const char *)0x8000FFFFLL,
        (int)ThreadpoolWork);
    TPResultException::raise(v27);
  }
  CloseThreadpoolWork(ThreadpoolWork);
  TPUtils::_SParallelForContext::~_SParallelForContext((TPUtils::_SParallelForContext *)pv);
}

```

## disassembly

```asm
0x1800439e8  mov     [rsp-8+arg_0], rbx
0x1800439ed  mov     [rsp-8+arg_18], rsi
0x1800439f2  push    rbp
0x1800439f3  push    rdi
0x1800439f4  push    r13
0x1800439f6  push    r14
0x1800439f8  push    r15
0x1800439fa  lea     rbp, [rsp-3F0h]
0x180043a02  sub     rsp, 4F0h
0x180043a09  mov     rax, cs:__security_cookie
0x180043a10  xor     rax, rsp
0x180043a13  mov     [rbp+410h+var_30], rax
0x180043a1a  mov     r15, r8
0x180043a1d  mov     r14, rdx
0x180043a20  xor     ebx, ebx
0x180043a22  call    ?GetProcessorCount@TPUtils@@SA_KXZ; TPUtils::GetProcessorCount(void)
0x180043a27  mov     r8, rax
0x180043a2a  lea     r9d, [rbx+1]
0x180043a2e  cmp     rax, r9
0x180043a31  jz      loc_180043BD9
0x180043a37  cmp     r14, r9
0x180043a3a  jbe     loc_180043BD9
0x180043a40  mov     eax, cs:?s_runningThreadCount@TPUtils@@0JC; long volatile TPUtils::s_runningThreadCount
0x180043a46  cmp     eax, 19h
0x180043a49  ja      loc_180043BDE
0x180043a4f  xor     edx, edx
0x180043a51  mov     rax, r14
0x180043a54  div     r8
0x180043a57  mov     rdi, rdx
0x180043a5a  mov     r13, rax
0x180043a5d  test    rax, rax
0x180043a60  cmovz   r13, r9
0x180043a64  mov     rcx, rax
0x180043a67  neg     rcx
0x180043a6a  sbb     rsi, rsi
0x180043a6d  and     rsi, rdx
0x180043a70  test    rax, rax
0x180043a73  cmovnz  rdi, r8
0x180043a77  sub     rdi, r9
0x180043a7a  xor     r9d, r9d; Context
0x180043a7d  xor     r8d, r8d; Parameter
0x180043a80  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180043a87  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180043a8e  call    cs:__imp_InitOnceExecuteOnce
0x180043a94  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, bl; bool g_isPerUserCatalogEnabled
0x180043a9a  jz      loc_180043BD2
0x180043aa0  call    PerUserCatalogNameForCorruption__GetCatalog
0x180043aa5  lea     rcx, off_1802C1398
0x180043aac  mov     [rsp+510h+var_4E0], rcx
0x180043ab1  movups  xmm0, xmmword ptr [r15]
0x180043ab5  movups  [rsp+510h+var_4D8], xmm0
0x180043aba  movups  xmm1, xmmword ptr [r15+10h]
0x180043abf  movups  [rsp+510h+var_4C8], xmm1
0x180043ac4  movups  xmm0, xmmword ptr [r15+20h]
0x180043ac9  movups  [rsp+510h+var_4B8], xmm0
0x180043ace  lea     rcx, [rsp+510h+var_4E0]
0x180043ad3  mov     [rsp+510h+var_4A8], rcx
0x180043ad8  mov     r9, rax
0x180043adb  mov     r8, rdi
0x180043ade  lea     rdx, [rsp+510h+var_4E0]
0x180043ae3  lea     rcx, [rsp+510h+pv]
0x180043ae8  call    ??0_SParallelForContext@TPUtils@@QEAA@AEBV?$function@$$A6AX_K@Z@std@@_KPEB_W@Z; TPUtils::_SParallelForContext::_SParallelForContext(std::function<void (unsigned __int64)> const &,unsigned __int64,wchar_t const *)
0x180043aed  nop
0x180043aee  mov     rcx, [rsp+510h+var_4A8]
0x180043af3  test    rcx, rcx
0x180043af6  jz      short loc_180043B18
0x180043af8  mov     rax, [rcx]
0x180043afb  lea     rdx, [rsp+510h+var_4E0]
0x180043b00  cmp     rcx, rdx
0x180043b03  setnz   dl
0x180043b06  mov     rax, [rax+20h]
0x180043b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b0f  mov     [rsp+510h+var_4A8], 0
0x180043b18  test    rdi, rdi
0x180043b1b  jnz     loc_180043C1D
0x180043b21  mov     [rsp+510h+var_4E8], 1
0x180043b28  xor     r8d, r8d; pcbe
0x180043b2b  lea     rdx, [rsp+510h+pv]; pv
0x180043b30  lea     rcx, ?_ParallelForCallback@TPUtils@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180043b37  call    cs:__imp_CreateThreadpoolWork
0x180043b3d  mov     rsi, rax
0x180043b40  mov     qword ptr [rsp+510h+var_4F0], rax; int
0x180043b45  test    rax, rax
0x180043b48  jz      loc_180043C24
0x180043b4e  mov     byte ptr [rsp+510h+var_4E8+1], 1
0x180043b53  test    rdi, rdi
0x180043b56  jz      short loc_180043B67
0x180043b58  mov     rcx, rsi; pwk
0x180043b5b  call    cs:__imp_SubmitThreadpoolWork
0x180043b61  sub     rdi, 1
0x180043b65  jnz     short loc_180043B58
0x180043b67  mov     edx, ebx
0x180043b69  mov     rcx, r15
0x180043b6c  call    _lambda_51047d2c742132fa5d8197baba4c7d26___operator__
0x180043b71  inc     rbx
0x180043b74  cmp     rbx, r14
0x180043b77  jb      short loc_180043B67
0x180043b79  mov     byte ptr [rsp+510h+var_4E8+1], 0
0x180043b7e  xor     edx, edx; fCancelPendingCallbacks
0x180043b80  mov     rcx, rsi; pwk
0x180043b83  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180043b89  mov     eax, [rbp+410h+var_50]
0x180043b8f  test    eax, eax
0x180043b91  jg      short loc_180043BF2
0x180043b93  mov     rcx, rsi; pwk
0x180043b96  call    cs:__imp_CloseThreadpoolWork
0x180043b9c  nop
0x180043b9d  lea     rcx, [rsp+510h+pv]; this
0x180043ba2  call    ??1_SParallelForContext@TPUtils@@QEAA@XZ; TPUtils::_SParallelForContext::~_SParallelForContext(void)
0x180043ba7  mov     rcx, [rbp+410h+var_30]
0x180043bae  xor     rcx, rsp; StackCookie
0x180043bb1  call    __security_check_cookie
0x180043bb6  lea     r11, [rsp+510h+var_20]
0x180043bbe  mov     rbx, [r11+30h]
0x180043bc2  mov     rsi, [r11+48h]
0x180043bc6  mov     rsp, r11
0x180043bc9  pop     r15
0x180043bcb  pop     r14
0x180043bcd  pop     r13
0x180043bcf  pop     rdi
0x180043bd0  pop     rbp
0x180043bd1  retn
0x180043bd2  xor     eax, eax
0x180043bd4  jmp     loc_180043AA5
0x180043bd9  test    r14, r14
0x180043bdc  jz      short loc_180043BA7
0x180043bde  mov     edx, ebx
0x180043be0  mov     rcx, r15
0x180043be3  call    _lambda_51047d2c742132fa5d8197baba4c7d26___operator__
0x180043be8  inc     rbx
0x180043beb  cmp     rbx, r14
0x180043bee  jnb     short loc_180043BA7
0x180043bf0  jmp     short loc_180043BDE
0x180043bf2  mov     rcx, [rbp+410h+var_48]; this
0x180043bf9  test    rcx, rcx
0x180043bfc  jnz     short loc_180043C3D
0x180043bfe  mov     rcx, [rbp+418h]; this
0x180043c05  mov     r9d, 8000FFFFh; char *
0x180043c0b  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180043c12  mov     edx, 194h; void *
0x180043c17  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180043c1d  xor     edx, edx
0x180043c1f  jmp     loc_1802B797A
0x180043c24  mov     rcx, [rbp+418h]; this
0x180043c2b  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180043c32  mov     edx, 7Eh ; '~'; void *
0x180043c37  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180043c3d  call    ?raise@TPResultException@@UEAAXXZ; TPResultException::raise(void)
0x1802b797a  mov     rcx, rdx
0x1802b797d  add     rcx, rcx
0x1802b7980  mov     [rbp+rcx*8+410h+var_450], rbx
0x1802b7985  lea     rax, [r13+1]
0x1802b7989  test    rsi, rsi
0x1802b798c  cmovz   rax, r13
0x1802b7990  add     rbx, rax
0x1802b7993  mov     [rbp+rcx*8+410h+var_448], rbx
0x1802b7998  inc     rdx
0x1802b799b  lea     rax, [rsi-1]
0x1802b799f  test    rsi, rsi
0x1802b79a2  cmovz   rax, rsi
0x1802b79a6  mov     rsi, rax
0x1802b79a9  cmp     rdx, rdi
0x1802b79ac  jb      short loc_1802B797A
0x1802b79ae  jmp     loc_180043B21
```
