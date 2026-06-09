# TPUtils::parallel_for<_lambda_6f2490d32fd63bf7c72dff986c6a958f_>(unsigned __int64,unsigned __int64,_lambda_6f2490d32fd63bf7c72dff986c6a958f_ const &)

- ea: `0x18007d878`
- end: `0x18007dae7`
- name: `??$parallel_for@V_lambda_6f2490d32fd63bf7c72dff986c6a958f_@@@TPUtils@@SAX_K0AEBV_lambda_6f2490d32fd63bf7c72dff986c6a958f_@@@Z`
- size: `623`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18007d5f0`

## callees

- `0x18002cc2c`
- `0x18002dc24`
- `0x180038f08`
- `0x180043ccc`
- `0x180043d18`
- `0x18007cf04`
- `0x18007d878`
- `0x180147154`
- `0x180157c70`
- `0x180188d90`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007da26`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18007da26`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18007d9ef`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18007d9ef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18007da92`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18007da92`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18007da4e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18007da4e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18007d91e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18007d91e`

## string_xrefs

- `0x18007da09`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`
- `0x18007da7d`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall TPUtils::parallel_for<_lambda_6f2490d32fd63bf7c72dff986c6a958f_>(
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
  void ***v13; // rdx
  unsigned __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rax
  struct _TP_WORK *ThreadpoolWork; // rsi
  __int64 v18; // r8
  const char *v19; // r9
  void **v20; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v21; // [rsp+38h] [rbp-C8h]
  __int128 v22; // [rsp+48h] [rbp-B8h]
  void ***v23; // [rsp+68h] [rbp-98h]
  _BYTE pv[1104]; // [rsp+70h] [rbp-90h] BYREF
  int v25; // [rsp+4C0h] [rbp+3C0h]
  TPResultException *v26; // [rsp+4C8h] [rbp+3C8h]
  wil::details::in1diag3 *retaddr; // [rsp+518h] [rbp+418h]

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
      _lambda_3530836d53173db97dafa8696e97945a_::operator()(a3, (unsigned int)v5++, ProcessorCount);
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
  v20 = &std::_Func_impl_no_alloc<_lambda_6f2490d32fd63bf7c72dff986c6a958f_,void,unsigned __int64>::`vftable';
  v21 = *a3;
  v22 = a3[1];
  v23 = &v20;
  TPUtils::_SParallelForContext::_SParallelForContext(pv, &v20, v11, Catalog);
  if ( v23 )
  {
    v13 = &v20;
    LOBYTE(v13) = v23 != &v20;
    ((void (__fastcall *)(void ***, void ***))(*v23)[4])(v23, v13);
    v23 = 0;
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
    _lambda_3530836d53173db97dafa8696e97945a_::operator()(a3, (unsigned int)v5++, v18);
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
0x18007d878  mov     [rsp-8+arg_0], rbx
0x18007d87d  mov     [rsp-8+arg_18], rsi
0x18007d882  push    rbp
0x18007d883  push    rdi
0x18007d884  push    r13
0x18007d886  push    r14
0x18007d888  push    r15
0x18007d88a  lea     rbp, [rsp-3F0h]
0x18007d892  sub     rsp, 4F0h
0x18007d899  mov     rax, cs:__security_cookie
0x18007d8a0  xor     rax, rsp
0x18007d8a3  mov     [rbp+410h+var_30], rax
0x18007d8aa  mov     r15, r8
0x18007d8ad  mov     r14, rdx
0x18007d8b0  xor     ebx, ebx
0x18007d8b2  call    ?GetProcessorCount@TPUtils@@SA_KXZ; TPUtils::GetProcessorCount(void)
0x18007d8b7  mov     r8, rax
0x18007d8ba  lea     r9d, [rbx+1]
0x18007d8be  cmp     rax, r9
0x18007d8c1  jz      loc_18007DAA5
0x18007d8c7  cmp     r14, r9
0x18007d8ca  jbe     loc_18007DAA5
0x18007d8d0  mov     eax, cs:?s_runningThreadCount@TPUtils@@0JC; long volatile TPUtils::s_runningThreadCount
0x18007d8d6  cmp     eax, 19h
0x18007d8d9  ja      loc_18007DAAA
0x18007d8df  xor     edx, edx
0x18007d8e1  mov     rax, r14
0x18007d8e4  div     r8
0x18007d8e7  mov     rdi, rdx
0x18007d8ea  mov     r13, rax
0x18007d8ed  test    rax, rax
0x18007d8f0  cmovz   r13, r9
0x18007d8f4  mov     rcx, rax
0x18007d8f7  neg     rcx
0x18007d8fa  sbb     rsi, rsi
0x18007d8fd  and     rsi, rdx
0x18007d900  test    rax, rax
0x18007d903  cmovnz  rdi, r8
0x18007d907  sub     rdi, r9
0x18007d90a  xor     r9d, r9d; Context
0x18007d90d  xor     r8d, r8d; Parameter
0x18007d910  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18007d917  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18007d91e  call    cs:__imp_InitOnceExecuteOnce
0x18007d924  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, bl; bool g_isPerUserCatalogEnabled
0x18007d92a  jz      short loc_18007D933
0x18007d92c  call    PerUserCatalogNameForCorruption__GetCatalog
0x18007d931  jmp     short loc_18007D935
0x18007d933  xor     eax, eax
0x18007d935  lea     rcx, ??_7?$_Func_impl_no_alloc@V_lambda_6f2490d32fd63bf7c72dff986c6a958f_@@X_K@std@@6B@; const std::_Func_impl_no_alloc<_lambda_6f2490d32fd63bf7c72dff986c6a958f_,void,unsigned __int64>::`vftable'
0x18007d93c  mov     [rsp+510h+var_4E0], rcx
0x18007d941  movups  xmm0, xmmword ptr [r15]
0x18007d945  movups  [rsp+510h+var_4D8], xmm0
0x18007d94a  movups  xmm1, xmmword ptr [r15+10h]
0x18007d94f  movups  [rsp+510h+var_4C8], xmm1
0x18007d954  lea     rcx, [rsp+510h+var_4E0]
0x18007d959  mov     [rsp+510h+var_4A8], rcx
0x18007d95e  mov     r9, rax
0x18007d961  mov     r8, rdi
0x18007d964  lea     rdx, [rsp+510h+var_4E0]
0x18007d969  lea     rcx, [rsp+510h+pv]
0x18007d96e  call    ??0_SParallelForContext@TPUtils@@QEAA@AEBV?$function@$$A6AX_K@Z@std@@_KPEB_W@Z; TPUtils::_SParallelForContext::_SParallelForContext(std::function<void (unsigned __int64)> const &,unsigned __int64,wchar_t const *)
0x18007d973  nop
0x18007d974  mov     rcx, [rsp+510h+var_4A8]
0x18007d979  test    rcx, rcx
0x18007d97c  jz      short loc_18007D99E
0x18007d97e  mov     rax, [rcx]
0x18007d981  lea     rdx, [rsp+510h+var_4E0]
0x18007d986  cmp     rcx, rdx
0x18007d989  setnz   dl
0x18007d98c  mov     rax, [rax+20h]
0x18007d990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d995  mov     [rsp+510h+var_4A8], 0
0x18007d99e  test    rdi, rdi
0x18007d9a1  jz      short loc_18007D9D9
0x18007d9a3  xor     edx, edx
0x18007d9a5  mov     rcx, rdx
0x18007d9a8  add     rcx, rcx
0x18007d9ab  mov     [rbp+rcx*8+410h+var_450], rbx
0x18007d9b0  lea     rax, [r13+1]
0x18007d9b4  test    rsi, rsi
0x18007d9b7  cmovz   rax, r13
0x18007d9bb  add     rbx, rax
0x18007d9be  mov     [rbp+rcx*8+410h+var_448], rbx
0x18007d9c3  inc     rdx
0x18007d9c6  lea     rax, [rsi-1]
0x18007d9ca  test    rsi, rsi
0x18007d9cd  cmovz   rax, rsi
0x18007d9d1  mov     rsi, rax
0x18007d9d4  cmp     rdx, rdi
0x18007d9d7  jb      short loc_18007D9A5
0x18007d9d9  mov     [rsp+510h+var_4E8], 1
0x18007d9e0  xor     r8d, r8d; pcbe
0x18007d9e3  lea     rdx, [rsp+510h+pv]; pv
0x18007d9e8  lea     rcx, ?_ParallelForCallback@TPUtils@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18007d9ef  call    cs:__imp_CreateThreadpoolWork
0x18007d9f5  mov     rsi, rax
0x18007d9f8  mov     qword ptr [rsp+510h+var_4F0], rax; int
0x18007d9fd  test    rax, rax
0x18007da00  jnz     short loc_18007DA19
0x18007da02  mov     rcx, [rbp+418h]; this
0x18007da09  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18007da10  lea     edx, [rax+7Eh]; void *
0x18007da13  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18007da19  mov     byte ptr [rsp+510h+var_4E8+1], 1
0x18007da1e  test    rdi, rdi
0x18007da21  jz      short loc_18007DA32
0x18007da23  mov     rcx, rsi; pwk
0x18007da26  call    cs:__imp_SubmitThreadpoolWork
0x18007da2c  sub     rdi, 1
0x18007da30  jnz     short loc_18007DA23
0x18007da32  mov     edx, ebx
0x18007da34  mov     rcx, r15
0x18007da37  call    ??R_lambda_3530836d53173db97dafa8696e97945a_@@QEBA@_K@Z; _lambda_3530836d53173db97dafa8696e97945a_::operator()(unsigned __int64)
0x18007da3c  inc     rbx
0x18007da3f  cmp     rbx, r14
0x18007da42  jb      short loc_18007DA32
0x18007da44  mov     byte ptr [rsp+510h+var_4E8+1], 0
0x18007da49  xor     edx, edx; fCancelPendingCallbacks
0x18007da4b  mov     rcx, rsi; pwk
0x18007da4e  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18007da54  mov     eax, [rbp+410h+var_50]
0x18007da5a  test    eax, eax
0x18007da5c  jle     short loc_18007DA8F
0x18007da5e  mov     rcx, [rbp+410h+var_48]; this
0x18007da65  test    rcx, rcx
0x18007da68  jz      short loc_18007DA70
0x18007da6a  call    ?raise@TPResultException@@UEAAXXZ; TPResultException::raise(void)
0x18007da70  mov     rcx, [rbp+418h]; this
0x18007da77  mov     r9d, 8000FFFFh; char *
0x18007da7d  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18007da84  mov     edx, 194h; void *
0x18007da89  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007da8f  mov     rcx, rsi; pwk
0x18007da92  call    cs:__imp_CloseThreadpoolWork
0x18007da98  nop
0x18007da99  lea     rcx, [rsp+510h+pv]; this
0x18007da9e  call    ??1_SParallelForContext@TPUtils@@QEAA@XZ; TPUtils::_SParallelForContext::~_SParallelForContext(void)
0x18007daa3  jmp     short loc_18007DABC
0x18007daa5  test    r14, r14
0x18007daa8  jz      short loc_18007DABC
0x18007daaa  mov     edx, ebx
0x18007daac  mov     rcx, r15
0x18007daaf  call    ??R_lambda_3530836d53173db97dafa8696e97945a_@@QEBA@_K@Z; _lambda_3530836d53173db97dafa8696e97945a_::operator()(unsigned __int64)
0x18007dab4  inc     rbx
0x18007dab7  cmp     rbx, r14
0x18007daba  jb      short loc_18007DAAA
0x18007dabc  mov     rcx, [rbp+410h+var_30]
0x18007dac3  xor     rcx, rsp; StackCookie
0x18007dac6  call    __security_check_cookie
0x18007dacb  lea     r11, [rsp+510h+var_20]
0x18007dad3  mov     rbx, [r11+30h]
0x18007dad7  mov     rsi, [r11+48h]
0x18007dadb  mov     rsp, r11
0x18007dade  pop     r15
0x18007dae0  pop     r14
0x18007dae2  pop     r13
0x18007dae4  pop     rdi
0x18007dae5  pop     rbp
0x18007dae6  retn
```
