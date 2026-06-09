# TPUtils::parallel_for__lambda_1386101e5f266f35d8b0f707b5d5cdef___

- ea: `0x1800432c4`
- end: `0x180043555`
- name: `TPUtils::parallel_for__lambda_1386101e5f266f35d8b0f707b5d5cdef___`
- size: `657`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180043108`

## callees

- `0x18002cc2c`
- `0x18002dc24`
- `0x180038f08`
- `0x1800432c4`
- `0x18004355c`
- `0x180043ccc`
- `0x180044c48`
- `0x180147154`
- `0x180157c70`
- `0x180188d90`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180043453`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180043453`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18004342f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18004342f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004349d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004349d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18004348a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18004348a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18004336a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18004336a`

## string_xrefs

- `0x180043524`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`
- `0x18004353d`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall TPUtils::parallel_for__lambda_1386101e5f266f35d8b0f707b5d5cdef___(
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
  __int64 Catalog_0; // rax
  __int64 (__fastcall ***v13)(); // rdx
  unsigned __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rax
  struct _TP_WORK *ThreadpoolWork; // rsi
  __int64 v18; // r8
  const char *v19; // r9
  __int64 (__fastcall **v20)(); // [rsp+30h] [rbp-D0h] BYREF
  __int128 v21; // [rsp+38h] [rbp-C8h]
  __int64 (__fastcall ***v22)(); // [rsp+68h] [rbp-98h]
  _BYTE pv[1104]; // [rsp+70h] [rbp-90h] BYREF
  int v24; // [rsp+4C0h] [rbp+3C0h]
  TPResultException *v25; // [rsp+4C8h] [rbp+3C8h]
  wil::details::in1diag3 *retaddr; // [rsp+518h] [rbp+418h]

  v5 = 0;
  ProcessorCount = TPUtils::GetProcessorCount();
  if ( ProcessorCount == 1 || a2 <= 1 )
  {
    if ( !a2 )
      return;
    goto LABEL_28;
  }
  if ( (unsigned int)TPUtils::s_runningThreadCount > 0x19 )
  {
    do
LABEL_28:
      lambda_bca537cbfea3210b06304040d74e5d5f_::operator()(
        *(_QWORD *)a3,
        **((_QWORD **)a3 + 1) + 24LL * (unsigned int)v5++,
        ProcessorCount);
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
    Catalog_0 = PerUserCatalogNameForCorruption::GetCatalog_0();
  else
    Catalog_0 = 0;
  v20 = off_1802C13C8;
  v21 = *a3;
  v22 = &v20;
  TPUtils::_SParallelForContext::_SParallelForContext(pv, &v20, v11, Catalog_0);
  if ( v22 )
  {
    v13 = &v20;
    LOBYTE(v13) = v22 != &v20;
    ((void (__fastcall *)(__int64 (__fastcall ***)(), __int64 (__fastcall ***)()))(*v22)[4])(v22, v13);
    v22 = 0;
  }
  if ( v11 )
  {
    v14 = 0;
    do
    {
      *(_QWORD *)&pv[16 * v14 + 80] = v5;
      v15 = v9 + 1;
      if ( !v10 )
        v15 = v9;
      v5 += v15;
      *(_QWORD *)&pv[16 * v14++ + 88] = v5;
      v16 = v10 - 1;
      if ( !v10 )
        v16 = 0;
      v10 = v16;
    }
    while ( v14 < v11 );
  }
  ThreadpoolWork = CreateThreadpoolWork(TPUtils::_ParallelForCallback, pv, 0);
  if ( !ThreadpoolWork )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\TPUtils.h",
      v19);
  for ( ; v11; --v11 )
    SubmitThreadpoolWork(ThreadpoolWork);
  do
    lambda_bca537cbfea3210b06304040d74e5d5f_::operator()(
      *(_QWORD *)a3,
      **((_QWORD **)a3 + 1) + 24LL * (unsigned int)v5++,
      v18);
  while ( v5 < a2 );
  WaitForThreadpoolWorkCallbacks(ThreadpoolWork, 0);
  if ( v24 > 0 )
  {
    if ( !v25 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x194,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\TPUtils.h",
        (const char *)0x8000FFFFLL,
        (int)ThreadpoolWork);
    TPResultException::raise(v25);
  }
  CloseThreadpoolWork(ThreadpoolWork);
  TPUtils::_SParallelForContext::~_SParallelForContext((TPUtils::_SParallelForContext *)pv);
}

```

## disassembly

```asm
0x1800432c4  mov     [rsp-8+arg_0], rbx
0x1800432c9  mov     [rsp-8+arg_18], rsi
0x1800432ce  push    rbp
0x1800432cf  push    rdi
0x1800432d0  push    r13
0x1800432d2  push    r14
0x1800432d4  push    r15
0x1800432d6  lea     rbp, [rsp-3F0h]
0x1800432de  sub     rsp, 4F0h
0x1800432e5  mov     rax, cs:__security_cookie
0x1800432ec  xor     rax, rsp
0x1800432ef  mov     [rbp+410h+var_30], rax
0x1800432f6  mov     r15, r8
0x1800432f9  mov     r14, rdx
0x1800432fc  xor     ebx, ebx
0x1800432fe  call    ?GetProcessorCount@TPUtils@@SA_KXZ; TPUtils::GetProcessorCount(void)
0x180043303  mov     r8, rax
0x180043306  lea     r9d, [rbx+1]
0x18004330a  cmp     rax, r9
0x18004330d  jz      loc_1800434E3
0x180043313  cmp     r14, r9
0x180043316  jbe     loc_1800434E3
0x18004331c  mov     eax, cs:?s_runningThreadCount@TPUtils@@0JC; long volatile TPUtils::s_runningThreadCount
0x180043322  cmp     eax, 19h
0x180043325  ja      loc_1800434E8
0x18004332b  xor     edx, edx
0x18004332d  mov     rax, r14
0x180043330  div     r8
0x180043333  mov     rdi, rdx
0x180043336  mov     r13, rax
0x180043339  test    rax, rax
0x18004333c  cmovz   r13, r9
0x180043340  mov     rcx, rax
0x180043343  neg     rcx
0x180043346  sbb     rsi, rsi
0x180043349  and     rsi, rdx
0x18004334c  test    rax, rax
0x18004334f  cmovnz  rdi, r8
0x180043353  sub     rdi, r9
0x180043356  xor     r9d, r9d; Context
0x180043359  xor     r8d, r8d; Parameter
0x18004335c  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180043363  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18004336a  call    cs:__imp_InitOnceExecuteOnce
0x180043370  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, bl; bool g_isPerUserCatalogEnabled
0x180043376  jnz     loc_1800434D9
0x18004337c  xor     eax, eax
0x18004337e  lea     rcx, off_1802C13C8
0x180043385  mov     [rsp+510h+var_4E0], rcx
0x18004338a  movups  xmm0, xmmword ptr [r15]
0x18004338e  movdqu  [rsp+510h+var_4D8], xmm0
0x180043394  lea     rcx, [rsp+510h+var_4E0]
0x180043399  mov     [rsp+510h+var_4A8], rcx
0x18004339e  mov     r9, rax
0x1800433a1  mov     r8, rdi
0x1800433a4  lea     rdx, [rsp+510h+var_4E0]
0x1800433a9  lea     rcx, [rsp+510h+pv]
0x1800433ae  call    ??0_SParallelForContext@TPUtils@@QEAA@AEBV?$function@$$A6AX_K@Z@std@@_KPEB_W@Z; TPUtils::_SParallelForContext::_SParallelForContext(std::function<void (unsigned __int64)> const &,unsigned __int64,wchar_t const *)
0x1800433b3  nop
0x1800433b4  mov     rcx, [rsp+510h+var_4A8]
0x1800433b9  test    rcx, rcx
0x1800433bc  jz      short loc_1800433DE
0x1800433be  mov     rax, [rcx]
0x1800433c1  lea     rdx, [rsp+510h+var_4E0]
0x1800433c6  cmp     rcx, rdx
0x1800433c9  setnz   dl
0x1800433cc  mov     rax, [rax+20h]
0x1800433d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800433d5  mov     [rsp+510h+var_4A8], 0
0x1800433de  test    rdi, rdi
0x1800433e1  jz      short loc_180043419
0x1800433e3  xor     edx, edx
0x1800433e5  mov     rcx, rdx
0x1800433e8  add     rcx, rcx
0x1800433eb  mov     [rbp+rcx*8+410h+var_450], rbx
0x1800433f0  lea     rax, [r13+1]
0x1800433f4  test    rsi, rsi
0x1800433f7  cmovz   rax, r13
0x1800433fb  add     rbx, rax
0x1800433fe  mov     [rbp+rcx*8+410h+var_448], rbx
0x180043403  inc     rdx
0x180043406  lea     rax, [rsi-1]
0x18004340a  test    rsi, rsi
0x18004340d  cmovz   rax, rsi
0x180043411  mov     rsi, rax
0x180043414  cmp     rdx, rdi
0x180043417  jb      short loc_1800433E5
0x180043419  mov     [rsp+510h+var_4E8], 1
0x180043420  xor     r8d, r8d; pcbe
0x180043423  lea     rdx, [rsp+510h+pv]; pv
0x180043428  lea     rcx, ?_ParallelForCallback@TPUtils@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18004342f  call    cs:__imp_CreateThreadpoolWork
0x180043435  mov     rsi, rax
0x180043438  mov     qword ptr [rsp+510h+var_4F0], rax; int
0x18004343d  test    rax, rax
0x180043440  jz      loc_180043536
0x180043446  mov     byte ptr [rsp+510h+var_4E8+1], 1
0x18004344b  test    rdi, rdi
0x18004344e  jz      short loc_18004345F
0x180043450  mov     rcx, rsi; pwk
0x180043453  call    cs:__imp_SubmitThreadpoolWork
0x180043459  sub     rdi, 1
0x18004345d  jnz     short loc_180043450
0x18004345f  mov     eax, ebx
0x180043461  lea     rdx, [rax+rax*2]
0x180043465  mov     rax, [r15+8]
0x180043469  mov     rcx, [rax]
0x18004346c  lea     rdx, [rcx+rdx*8]
0x180043470  mov     rcx, [r15]
0x180043473  call    _lambda_bca537cbfea3210b06304040d74e5d5f___operator__
0x180043478  inc     rbx
0x18004347b  cmp     rbx, r14
0x18004347e  jb      short loc_18004345F
0x180043480  mov     byte ptr [rsp+510h+var_4E8+1], 0
0x180043485  xor     edx, edx; fCancelPendingCallbacks
0x180043487  mov     rcx, rsi; pwk
0x18004348a  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180043490  mov     eax, [rbp+410h+var_50]
0x180043496  test    eax, eax
0x180043498  jg      short loc_18004350B
0x18004349a  mov     rcx, rsi; pwk
0x18004349d  call    cs:__imp_CloseThreadpoolWork
0x1800434a3  nop
0x1800434a4  lea     rcx, [rsp+510h+pv]; this
0x1800434a9  call    ??1_SParallelForContext@TPUtils@@QEAA@XZ; TPUtils::_SParallelForContext::~_SParallelForContext(void)
0x1800434ae  mov     rcx, [rbp+410h+var_30]
0x1800434b5  xor     rcx, rsp; StackCookie
0x1800434b8  call    __security_check_cookie
0x1800434bd  lea     r11, [rsp+510h+var_20]
0x1800434c5  mov     rbx, [r11+30h]
0x1800434c9  mov     rsi, [r11+48h]
0x1800434cd  mov     rsp, r11
0x1800434d0  pop     r15
0x1800434d2  pop     r14
0x1800434d4  pop     r13
0x1800434d6  pop     rdi
0x1800434d7  pop     rbp
0x1800434d8  retn
0x1800434d9  call    PerUserCatalogNameForCorruption__GetCatalog_0
0x1800434de  jmp     loc_18004337E
0x1800434e3  test    r14, r14
0x1800434e6  jz      short loc_1800434AE
0x1800434e8  mov     eax, ebx
0x1800434ea  lea     rdx, [rax+rax*2]
0x1800434ee  mov     rax, [r15+8]
0x1800434f2  mov     rcx, [rax]
0x1800434f5  lea     rdx, [rcx+rdx*8]
0x1800434f9  mov     rcx, [r15]
0x1800434fc  call    _lambda_bca537cbfea3210b06304040d74e5d5f___operator__
0x180043501  inc     rbx
0x180043504  cmp     rbx, r14
0x180043507  jb      short loc_1800434E8
0x180043509  jmp     short loc_1800434AE
0x18004350b  mov     rcx, [rbp+410h+var_48]; this
0x180043512  test    rcx, rcx
0x180043515  jnz     short loc_18004354F
0x180043517  mov     rcx, [rbp+418h]; this
0x18004351e  mov     r9d, 8000FFFFh; char *
0x180043524  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18004352b  mov     edx, 194h; void *
0x180043530  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180043536  mov     rcx, [rbp+418h]; this
0x18004353d  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180043544  mov     edx, 7Eh ; '~'; void *
0x180043549  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18004354f  call    ?raise@TPResultException@@UEAAXXZ; TPResultException::raise(void)
```
