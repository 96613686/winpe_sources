# TPUtils::parallel_for__lambda_22db74719aa2a92dd9334db7ccfed19e___

- ea: `0x18002d920`
- end: `0x18002dc1e`
- name: `TPUtils::parallel_for__lambda_22db74719aa2a92dd9334db7ccfed19e___`
- size: `766`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800329b4`

## callees

- `0x18002cbb4`
- `0x18002cc2c`
- `0x18002d920`
- `0x18002dcc0`
- `0x18002e05c`
- `0x180036d60`
- `0x180038f08`
- `0x180044c48`
- `0x180147154`
- `0x180157c70`
- `0x180188d90`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002db09`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002db09`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002dae5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002dae5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002db4d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002db4d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002db36`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002db36`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002d9d7`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002d9d7`

## string_xrefs

- `0x18002dbed`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`
- `0x18002dc06`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall TPUtils::parallel_for__lambda_22db74719aa2a92dd9334db7ccfed19e___(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 ProcessorCount; // r8
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rdi
  __int64 v9; // rcx
  unsigned __int64 v10; // rdi
  __int64 Catalog_0; // r13
  char *v12; // rsi
  _QWORD *v13; // r15
  __int64 v14; // r12
  __int64 v15; // rdx
  unsigned __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 v19; // rax
  struct _TP_WORK *ThreadpoolWork; // rsi
  __int64 v21; // r8
  const char *v22; // r9
  _BYTE *v23; // rdx
  __int64 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  char v27; // [rsp+50h] [rbp-B0h] BYREF
  char *v28; // [rsp+88h] [rbp-78h]
  _BYTE pv[56]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE *v30; // [rsp+C8h] [rbp-38h]
  int v31; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v32; // [rsp+D8h] [rbp-28h]
  _QWORD v33[128]; // [rsp+E0h] [rbp-20h] BYREF
  int v34; // [rsp+4E0h] [rbp+3E0h]
  TPResultException *v35; // [rsp+4E8h] [rbp+3E8h]
  std::_Ref_count_base *v36; // [rsp+4F0h] [rbp+3F0h]
  __int64 v37; // [rsp+4F8h] [rbp+3F8h]
  wil::details::in1diag3 *retaddr; // [rsp+548h] [rbp+448h]

  v5 = 0;
  ProcessorCount = TPUtils::GetProcessorCount();
  if ( ProcessorCount == 1 || a2 <= 1 )
  {
    if ( !a2 )
      return;
    goto LABEL_35;
  }
  if ( (unsigned int)TPUtils::s_runningThreadCount > 0x19 )
  {
    do
LABEL_35:
      lambda_22db74719aa2a92dd9334db7ccfed19e_::operator()(a3, (unsigned int)v5++, ProcessorCount);
    while ( v5 < a2 );
    return;
  }
  v7 = a2 / ProcessorCount;
  v8 = a2 % ProcessorCount;
  v9 = a2 / ProcessorCount;
  if ( !(a2 / ProcessorCount) )
    v9 = 1;
  v24 = v9;
  v25 = v8 & -(__int64)(v7 != 0);
  if ( v7 )
    v8 = ProcessorCount;
  v10 = v8 - 1;
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( g_isPerUserCatalogEnabled )
    Catalog_0 = PerUserCatalogNameForCorruption::GetCatalog_0();
  else
    Catalog_0 = 0;
  v12 = (char *)std::_Global_new_std::_Func_impl_no_alloc__lambda_22db74719aa2a92dd9334db7ccfed19e__void_unsigned___int64___lambda_22db74719aa2a92dd9334db7ccfed19e__const___(a3);
  v28 = v12;
  v30 = 0;
  if ( v12 )
    v30 = (_BYTE *)(**(__int64 (__fastcall ***)(char *, _BYTE *))v12)(v12, pv);
  v31 = 0;
  v32 = v10;
  v13 = v33;
  v14 = 64;
  do
  {
    std::pair<unsigned __int64,unsigned __int64>::pair<unsigned __int64,unsigned __int64>(v13);
    v13 += 2;
    --v14;
  }
  while ( v14 );
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = Catalog_0;
  if ( v12 )
  {
    LOBYTE(v15) = v12 != &v27;
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v12 + 32LL))(v12, v15);
  }
  if ( v10 )
  {
    v16 = 0;
    v17 = v25;
    do
    {
      v33[2 * v16] = v5;
      v18 = v24 + 1;
      if ( !v17 )
        v18 = v24;
      v5 += v18;
      v33[2 * v16++ + 1] = v5;
      v19 = v17 - 1;
      if ( !v17 )
        v19 = 0;
      v17 = v19;
    }
    while ( v16 < v10 );
  }
  ThreadpoolWork = CreateThreadpoolWork(TPUtils::_ParallelForCallback, pv, 0);
  if ( !ThreadpoolWork )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\TPUtils.h",
      v22);
  for ( ; v10; --v10 )
    SubmitThreadpoolWork(ThreadpoolWork);
  do
    lambda_22db74719aa2a92dd9334db7ccfed19e_::operator()(a3, (unsigned int)v5++, v21);
  while ( v5 < a2 );
  WaitForThreadpoolWorkCallbacks(ThreadpoolWork, 0);
  if ( v34 > 0 )
  {
    if ( !v35 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x194,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\TPUtils.h",
        (const char *)0x8000FFFFLL,
        (int)ThreadpoolWork);
    TPResultException::raise(v35);
  }
  CloseThreadpoolWork(ThreadpoolWork);
  if ( v36 )
    std::_Ref_count_base::_Decref(v36);
  if ( v30 )
  {
    v23 = pv;
    LOBYTE(v23) = v30 != pv;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v30 + 32LL))(v30, v23);
  }
}

```

## disassembly

```asm
0x18002d920  mov     [rsp-8+arg_0], rbx
0x18002d925  push    rbp
0x18002d926  push    rsi
0x18002d927  push    rdi
0x18002d928  push    r12
0x18002d92a  push    r13
0x18002d92c  push    r14
0x18002d92e  push    r15
0x18002d930  lea     rbp, [rsp-410h]
0x18002d938  sub     rsp, 510h
0x18002d93f  mov     rax, cs:__security_cookie
0x18002d946  xor     rax, rsp
0x18002d949  mov     [rbp+440h+var_40], rax
0x18002d950  mov     rsi, r8
0x18002d953  mov     [rsp+540h+var_500], r8
0x18002d958  mov     r14, rdx
0x18002d95b  xor     r15d, r15d
0x18002d95e  mov     ebx, r15d
0x18002d961  call    ?GetProcessorCount@TPUtils@@SA_KXZ; TPUtils::GetProcessorCount(void)
0x18002d966  mov     r8, rax
0x18002d969  lea     r12d, [r15+1]
0x18002d96d  cmp     rax, r12
0x18002d970  jz      loc_18002DBBB
0x18002d976  cmp     r14, r12
0x18002d979  jbe     loc_18002DBBB
0x18002d97f  mov     eax, cs:?s_runningThreadCount@TPUtils@@0JC; long volatile TPUtils::s_runningThreadCount
0x18002d985  cmp     eax, 19h
0x18002d988  ja      loc_18002DBC0
0x18002d98e  xor     edx, edx
0x18002d990  mov     rax, r14
0x18002d993  div     r8
0x18002d996  mov     rdi, rdx
0x18002d999  mov     rcx, rax
0x18002d99c  test    rax, rax
0x18002d99f  cmovz   rcx, r12
0x18002d9a3  mov     [rsp+540h+var_510], rcx
0x18002d9a8  mov     rcx, rax
0x18002d9ab  neg     rcx
0x18002d9ae  sbb     rdx, rdx
0x18002d9b1  and     rdx, rdi
0x18002d9b4  mov     [rsp+540h+var_508], rdx
0x18002d9b9  test    rax, rax
0x18002d9bc  cmovnz  rdi, r8
0x18002d9c0  sub     rdi, r12
0x18002d9c3  xor     r9d, r9d; Context
0x18002d9c6  xor     r8d, r8d; Parameter
0x18002d9c9  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18002d9d0  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18002d9d7  call    cs:__imp_InitOnceExecuteOnce
0x18002d9dd  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, r15b; bool g_isPerUserCatalogEnabled
0x18002d9e4  jnz     loc_18002DBAE
0x18002d9ea  mov     r13d, r15d
0x18002d9ed  mov     [rbp+440h+var_4B8], r15
0x18002d9f1  mov     rcx, rsi
0x18002d9f4  call    std___Global_new_std___Func_impl_no_alloc__lambda_22db74719aa2a92dd9334db7ccfed19e__void_unsigned___int64___lambda_22db74719aa2a92dd9334db7ccfed19e__const___
0x18002d9f9  mov     rsi, rax
0x18002d9fc  mov     [rbp+440h+var_4B8], rax
0x18002da00  lea     rax, [rbp+440h+pv]
0x18002da04  mov     qword ptr [rsp+540h+var_520], rax
0x18002da09  mov     [rbp+440h+var_478], r15
0x18002da0d  test    rsi, rsi
0x18002da10  jz      short loc_18002DA28
0x18002da12  mov     rcx, [rsi]
0x18002da15  mov     rax, [rcx]
0x18002da18  lea     rdx, [rbp+440h+pv]
0x18002da1c  mov     rcx, rsi
0x18002da1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da24  mov     [rbp+440h+var_478], rax
0x18002da28  mov     [rbp+440h+var_470], r15d
0x18002da2c  mov     [rbp+440h+var_468], rdi
0x18002da30  lea     r15, [rbp+440h+var_460]
0x18002da34  mov     r12d, 40h ; '@'
0x18002da3a  mov     rcx, r15; void *
0x18002da3d  call    ??$?0_K_K$0A@@?$pair@_K_K@std@@QEAA@XZ; std::pair<unsigned __int64,unsigned __int64>::pair<unsigned __int64,unsigned __int64>(void)
0x18002da42  add     r15, 10h
0x18002da46  sub     r12, 1
0x18002da4a  jnz     short loc_18002DA3A
0x18002da4c  xor     r15d, r15d
0x18002da4f  mov     [rbp+440h+var_60], r15d
0x18002da56  mov     [rbp+440h+var_58], r15
0x18002da5d  mov     [rbp+440h+var_50], r15
0x18002da64  mov     [rbp+440h+var_48], r13
0x18002da6b  test    rsi, rsi
0x18002da6e  jz      short loc_18002DA8A
0x18002da70  mov     rax, [rsi]
0x18002da73  lea     rcx, [rsp+540h+var_4F0]
0x18002da78  cmp     rsi, rcx
0x18002da7b  setnz   dl
0x18002da7e  mov     rcx, rsi
0x18002da81  mov     rax, [rax+20h]
0x18002da85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da8a  test    rdi, rdi
0x18002da8d  jz      short loc_18002DAD0
0x18002da8f  mov     rdx, r15
0x18002da92  mov     r10, [rsp+540h+var_510]
0x18002da97  mov     r8, [rsp+540h+var_508]
0x18002da9c  mov     rcx, rdx
0x18002da9f  add     rcx, rcx
0x18002daa2  mov     [rbp+rcx*8+440h+var_460], rbx
0x18002daa7  lea     rax, [r10+1]
0x18002daab  test    r8, r8
0x18002daae  cmovz   rax, r10
0x18002dab2  add     rbx, rax
0x18002dab5  mov     [rbp+rcx*8+440h+var_458], rbx
0x18002daba  inc     rdx
0x18002dabd  lea     rax, [r8-1]
0x18002dac1  test    r8, r8
0x18002dac4  cmovz   rax, r8
0x18002dac8  mov     r8, rax
0x18002dacb  cmp     rdx, rdi
0x18002dace  jb      short loc_18002DA9C
0x18002dad0  mov     [rsp+540h+var_518], 1
0x18002dad7  xor     r8d, r8d; pcbe
0x18002dada  lea     rdx, [rbp+440h+pv]; pv
0x18002dade  lea     rcx, ?_ParallelForCallback@TPUtils@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18002dae5  call    cs:__imp_CreateThreadpoolWork
0x18002daeb  mov     rsi, rax
0x18002daee  mov     qword ptr [rsp+540h+var_520], rax; int
0x18002daf3  test    rax, rax
0x18002daf6  jz      loc_18002DBFF
0x18002dafc  mov     byte ptr [rsp+540h+var_518+1], 1
0x18002db01  test    rdi, rdi
0x18002db04  jz      short loc_18002DB15
0x18002db06  mov     rcx, rsi; pwk
0x18002db09  call    cs:__imp_SubmitThreadpoolWork
0x18002db0f  sub     rdi, 1
0x18002db13  jnz     short loc_18002DB06
0x18002db15  mov     rdi, [rsp+540h+var_500]
0x18002db1a  mov     edx, ebx
0x18002db1c  mov     rcx, rdi
0x18002db1f  call    _lambda_22db74719aa2a92dd9334db7ccfed19e___operator__
0x18002db24  inc     rbx
0x18002db27  cmp     rbx, r14
0x18002db2a  jb      short loc_18002DB1A
0x18002db2c  mov     byte ptr [rsp+540h+var_518+1], r15b
0x18002db31  xor     edx, edx; fCancelPendingCallbacks
0x18002db33  mov     rcx, rsi; pwk
0x18002db36  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18002db3c  mov     eax, [rbp+440h+var_60]
0x18002db42  test    eax, eax
0x18002db44  jg      loc_18002DBD4
0x18002db4a  mov     rcx, rsi; pwk
0x18002db4d  call    cs:__imp_CloseThreadpoolWork
0x18002db53  nop
0x18002db54  mov     rcx, [rbp+440h+var_50]; this
0x18002db5b  test    rcx, rcx
0x18002db5e  jz      short loc_18002DB65
0x18002db60  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002db65  mov     rcx, [rbp+440h+var_478]
0x18002db69  test    rcx, rcx
0x18002db6c  jz      short loc_18002DB84
0x18002db6e  mov     rax, [rcx]
0x18002db71  lea     rdx, [rbp+440h+pv]
0x18002db75  cmp     rcx, rdx
0x18002db78  setnz   dl
0x18002db7b  mov     rax, [rax+20h]
0x18002db7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db84  mov     rcx, [rbp+440h+var_40]
0x18002db8b  xor     rcx, rsp; StackCookie
0x18002db8e  call    __security_check_cookie
0x18002db93  mov     rbx, [rsp+540h+arg_0]
0x18002db9b  add     rsp, 510h
0x18002dba2  pop     r15
0x18002dba4  pop     r14
0x18002dba6  pop     r13
0x18002dba8  pop     r12
0x18002dbaa  pop     rdi
0x18002dbab  pop     rsi
0x18002dbac  pop     rbp
0x18002dbad  retn
0x18002dbae  call    PerUserCatalogNameForCorruption__GetCatalog_0
0x18002dbb3  mov     r13, rax
0x18002dbb6  jmp     loc_18002D9ED
0x18002dbbb  test    r14, r14
0x18002dbbe  jz      short loc_18002DB84
0x18002dbc0  mov     edx, ebx
0x18002dbc2  mov     rcx, rsi
0x18002dbc5  call    _lambda_22db74719aa2a92dd9334db7ccfed19e___operator__
0x18002dbca  add     rbx, r12
0x18002dbcd  cmp     rbx, r14
0x18002dbd0  jb      short loc_18002DBC0
0x18002dbd2  jmp     short loc_18002DB84
0x18002dbd4  mov     rcx, [rbp+440h+var_58]; this
0x18002dbdb  test    rcx, rcx
0x18002dbde  jnz     short loc_18002DC18
0x18002dbe0  mov     rcx, [rbp+448h]; this
0x18002dbe7  mov     r9d, 8000FFFFh; char *
0x18002dbed  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18002dbf4  mov     edx, 194h; void *
0x18002dbf9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002dbff  mov     rcx, [rbp+448h]; this
0x18002dc06  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18002dc0d  mov     edx, 7Eh ; '~'; void *
0x18002dc12  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002dc18  call    ?raise@TPResultException@@UEAAXXZ; TPResultException::raise(void)
```
