# TPUtils::parallel_for__lambda_8cb70c2ce1141461991bfe18208f4cb1___

- ea: `0x18002d634`
- end: `0x18002d91a`
- name: `TPUtils::parallel_for__lambda_8cb70c2ce1141461991bfe18208f4cb1___`
- size: `742`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800c5c80`

## callees

- `0x18002cc2c`
- `0x18002d634`
- `0x18002dcc0`
- `0x18002dcdc`
- `0x180038f08`
- `0x180043ccc`
- `0x180044c48`
- `0x18010b970`
- `0x180147154`
- `0x180157c70`
- `0x180188d90`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002d835`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002d835`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002d811`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002d811`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002d870`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002d870`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002d85d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002d85d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002d6e4`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002d6e4`

## string_xrefs

- `0x18002d8e9`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`
- `0x18002d902`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall TPUtils::parallel_for__lambda_8cb70c2ce1141461991bfe18208f4cb1___(
        __int64 a1,
        unsigned __int64 a2,
        __int128 *a3)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 ProcessorCount; // r8
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rdi
  __int64 v9; // rcx
  unsigned __int64 v10; // rdi
  __int64 Catalog_0; // r13
  _QWORD *v12; // rsi
  __int64 v13; // r15
  __int64 (__fastcall ***v14)(); // rdx
  unsigned __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // rax
  struct _TP_WORK *ThreadpoolWork; // rsi
  __int64 v20; // r8
  const char *v21; // r9
  __int64 v22; // [rsp+30h] [rbp-D0h]
  __int64 v23; // [rsp+38h] [rbp-C8h]
  __int64 (__fastcall **v24)(); // [rsp+40h] [rbp-C0h] BYREF
  __int128 v25; // [rsp+48h] [rbp-B8h]
  __int128 v26; // [rsp+58h] [rbp-A8h]
  __int64 v27; // [rsp+68h] [rbp-98h]
  __int64 (__fastcall ***v28)(); // [rsp+78h] [rbp-88h]
  _BYTE pv[56]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v30; // [rsp+B8h] [rbp-48h]
  int v31; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v32; // [rsp+C8h] [rbp-38h]
  _QWORD v33[128]; // [rsp+D0h] [rbp-30h] BYREF
  int v34; // [rsp+4D0h] [rbp+3D0h]
  TPResultException *v35; // [rsp+4D8h] [rbp+3D8h]
  __int64 v36; // [rsp+4E0h] [rbp+3E0h]
  __int64 v37; // [rsp+4E8h] [rbp+3E8h]
  wil::details::in1diag3 *retaddr; // [rsp+538h] [rbp+438h]

  v5 = 0;
  ProcessorCount = TPUtils::GetProcessorCount();
  if ( ProcessorCount == 1 || a2 <= 1 )
  {
    if ( !a2 )
      return;
    goto LABEL_30;
  }
  if ( (unsigned int)TPUtils::s_runningThreadCount > 0x19 )
  {
    do
LABEL_30:
      lambda_8cb70c2ce1141461991bfe18208f4cb1_::operator()(a3, (unsigned int)v5++, ProcessorCount);
    while ( v5 < a2 );
    return;
  }
  v7 = a2 / ProcessorCount;
  v8 = a2 % ProcessorCount;
  v9 = a2 / ProcessorCount;
  if ( !(a2 / ProcessorCount) )
    v9 = 1;
  v22 = v9;
  v23 = v8 & -(__int64)(v7 != 0);
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
  v24 = off_1802C1318;
  v25 = *a3;
  v26 = a3[1];
  v27 = *((_QWORD *)a3 + 4);
  v28 = &v24;
  v30 = 0;
  v30 = std::_Func_impl_no_alloc__lambda_8cb70c2ce1141461991bfe18208f4cb1__void_unsigned___int64_::_Move(&v24, pv);
  v31 = 0;
  v32 = v10;
  v12 = v33;
  v13 = 64;
  do
  {
    std::pair<unsigned __int64,unsigned __int64>::pair<unsigned __int64,unsigned __int64>(v12);
    v12 += 2;
    --v13;
  }
  while ( v13 );
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = Catalog_0;
  if ( v28 )
  {
    v14 = &v24;
    LOBYTE(v14) = v28 != &v24;
    ((void (__fastcall *)(__int64 (__fastcall ***)(), __int64 (__fastcall ***)()))(*v28)[4])(v28, v14);
    v28 = 0;
  }
  if ( v10 )
  {
    v15 = 0;
    v16 = v23;
    do
    {
      v33[2 * v15] = v5;
      v17 = v22 + 1;
      if ( !v16 )
        v17 = v22;
      v5 += v17;
      v33[2 * v15++ + 1] = v5;
      v18 = v16 - 1;
      if ( !v16 )
        v18 = 0;
      v16 = v18;
    }
    while ( v15 < v10 );
  }
  ThreadpoolWork = CreateThreadpoolWork(TPUtils::_ParallelForCallback, pv, 0);
  if ( !ThreadpoolWork )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\TPUtils.h",
      v21);
  for ( ; v10; --v10 )
    SubmitThreadpoolWork(ThreadpoolWork);
  do
    lambda_8cb70c2ce1141461991bfe18208f4cb1_::operator()(a3, (unsigned int)v5++, v20);
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
  TPUtils::_SParallelForContext::~_SParallelForContext((TPUtils::_SParallelForContext *)pv);
}

```

## disassembly

```asm
0x18002d634  mov     [rsp-8+arg_0], rbx
0x18002d639  push    rbp
0x18002d63a  push    rsi
0x18002d63b  push    rdi
0x18002d63c  push    r12
0x18002d63e  push    r13
0x18002d640  push    r14
0x18002d642  push    r15
0x18002d644  lea     rbp, [rsp-400h]
0x18002d64c  sub     rsp, 500h
0x18002d653  mov     rax, cs:__security_cookie
0x18002d65a  xor     rax, rsp
0x18002d65d  mov     [rbp+430h+var_40], rax
0x18002d664  mov     r12, r8
0x18002d667  mov     r14, rdx
0x18002d66a  xor     esi, esi
0x18002d66c  mov     ebx, esi
0x18002d66e  call    ?GetProcessorCount@TPUtils@@SA_KXZ; TPUtils::GetProcessorCount(void)
0x18002d673  mov     r8, rax
0x18002d676  lea     r15d, [rsi+1]
0x18002d67a  cmp     rax, r15
0x18002d67d  jz      loc_18002D8B7
0x18002d683  cmp     r14, r15
0x18002d686  jbe     loc_18002D8B7
0x18002d68c  mov     eax, cs:?s_runningThreadCount@TPUtils@@0JC; long volatile TPUtils::s_runningThreadCount
0x18002d692  cmp     eax, 19h
0x18002d695  ja      loc_18002D8BC
0x18002d69b  xor     edx, edx
0x18002d69d  mov     rax, r14
0x18002d6a0  div     r8
0x18002d6a3  mov     rdi, rdx
0x18002d6a6  mov     rcx, rax
0x18002d6a9  test    rax, rax
0x18002d6ac  cmovz   rcx, r15
0x18002d6b0  mov     [rsp+530h+var_500], rcx
0x18002d6b5  mov     rcx, rax
0x18002d6b8  neg     rcx
0x18002d6bb  sbb     rdx, rdx
0x18002d6be  and     rdx, rdi
0x18002d6c1  mov     [rsp+530h+var_4F8], rdx
0x18002d6c6  test    rax, rax
0x18002d6c9  cmovnz  rdi, r8
0x18002d6cd  sub     rdi, r15
0x18002d6d0  xor     r9d, r9d; Context
0x18002d6d3  xor     r8d, r8d; Parameter
0x18002d6d6  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18002d6dd  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18002d6e4  call    cs:__imp_InitOnceExecuteOnce
0x18002d6ea  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, sil; bool g_isPerUserCatalogEnabled
0x18002d6f1  jnz     loc_18002D8AA
0x18002d6f7  mov     r13d, esi
0x18002d6fa  lea     rax, off_1802C1318
0x18002d701  mov     [rsp+530h+var_4F0], rax
0x18002d706  movups  xmm0, xmmword ptr [r12]
0x18002d70b  movups  [rsp+530h+var_4E8], xmm0
0x18002d710  movups  xmm1, xmmword ptr [r12+10h]
0x18002d716  movups  [rsp+530h+var_4D8], xmm1
0x18002d71b  movsd   xmm0, qword ptr [r12+20h]
0x18002d722  movsd   [rsp+530h+var_4C8], xmm0
0x18002d728  lea     rax, [rsp+530h+var_4F0]
0x18002d72d  mov     [rsp+530h+var_4B8], rax
0x18002d732  lea     rax, [rbp+430h+pv]
0x18002d736  mov     qword ptr [rsp+530h+var_510], rax
0x18002d73b  mov     [rbp+430h+var_478], rsi
0x18002d73f  lea     rdx, [rbp+430h+pv]
0x18002d743  lea     rcx, [rsp+530h+var_4F0]
0x18002d748  call    std___Func_impl_no_alloc__lambda_8cb70c2ce1141461991bfe18208f4cb1__void_unsigned___int64____Move
0x18002d74d  mov     [rbp+430h+var_478], rax
0x18002d751  mov     [rbp+430h+var_470], esi
0x18002d754  mov     [rbp+430h+var_468], rdi
0x18002d758  lea     rsi, [rbp+430h+var_460]
0x18002d75c  mov     r15d, 40h ; '@'
0x18002d762  mov     rcx, rsi; void *
0x18002d765  call    ??$?0_K_K$0A@@?$pair@_K_K@std@@QEAA@XZ; std::pair<unsigned __int64,unsigned __int64>::pair<unsigned __int64,unsigned __int64>(void)
0x18002d76a  add     rsi, 10h
0x18002d76e  sub     r15, 1
0x18002d772  jnz     short loc_18002D762
0x18002d774  mov     [rbp+430h+var_60], r15d
0x18002d77b  mov     [rbp+430h+var_58], r15
0x18002d782  mov     [rbp+430h+var_50], r15
0x18002d789  mov     [rbp+430h+var_48], r13
0x18002d790  mov     rcx, [rsp+530h+var_4B8]
0x18002d795  test    rcx, rcx
0x18002d798  jz      short loc_18002D7B6
0x18002d79a  mov     rax, [rcx]
0x18002d79d  lea     rdx, [rsp+530h+var_4F0]
0x18002d7a2  cmp     rcx, rdx
0x18002d7a5  setnz   dl
0x18002d7a8  mov     rax, [rax+20h]
0x18002d7ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7b1  mov     [rsp+530h+var_4B8], r15
0x18002d7b6  test    rdi, rdi
0x18002d7b9  jz      short loc_18002D7FC
0x18002d7bb  mov     rdx, r15
0x18002d7be  mov     r10, [rsp+530h+var_500]
0x18002d7c3  mov     r8, [rsp+530h+var_4F8]
0x18002d7c8  mov     rcx, rdx
0x18002d7cb  add     rcx, rcx
0x18002d7ce  mov     [rbp+rcx*8+430h+var_460], rbx
0x18002d7d3  lea     rax, [r10+1]
0x18002d7d7  test    r8, r8
0x18002d7da  cmovz   rax, r10
0x18002d7de  add     rbx, rax
0x18002d7e1  mov     [rbp+rcx*8+430h+var_458], rbx
0x18002d7e6  inc     rdx
0x18002d7e9  lea     rax, [r8-1]
0x18002d7ed  test    r8, r8
0x18002d7f0  cmovz   rax, r8
0x18002d7f4  mov     r8, rax
0x18002d7f7  cmp     rdx, rdi
0x18002d7fa  jb      short loc_18002D7C8
0x18002d7fc  mov     [rsp+530h+var_508], 1
0x18002d803  xor     r8d, r8d; pcbe
0x18002d806  lea     rdx, [rbp+430h+pv]; pv
0x18002d80a  lea     rcx, ?_ParallelForCallback@TPUtils@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18002d811  call    cs:__imp_CreateThreadpoolWork
0x18002d817  mov     rsi, rax
0x18002d81a  mov     qword ptr [rsp+530h+var_510], rax; int
0x18002d81f  test    rax, rax
0x18002d822  jz      loc_18002D8FB
0x18002d828  mov     byte ptr [rsp+530h+var_508+1], 1
0x18002d82d  test    rdi, rdi
0x18002d830  jz      short loc_18002D841
0x18002d832  mov     rcx, rsi; pwk
0x18002d835  call    cs:__imp_SubmitThreadpoolWork
0x18002d83b  sub     rdi, 1
0x18002d83f  jnz     short loc_18002D832
0x18002d841  mov     edx, ebx
0x18002d843  mov     rcx, r12
0x18002d846  call    _lambda_8cb70c2ce1141461991bfe18208f4cb1___operator__
0x18002d84b  inc     rbx
0x18002d84e  cmp     rbx, r14
0x18002d851  jb      short loc_18002D841
0x18002d853  mov     byte ptr [rsp+530h+var_508+1], r15b
0x18002d858  xor     edx, edx; fCancelPendingCallbacks
0x18002d85a  mov     rcx, rsi; pwk
0x18002d85d  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18002d863  mov     eax, [rbp+430h+var_60]
0x18002d869  test    eax, eax
0x18002d86b  jg      short loc_18002D8D0
0x18002d86d  mov     rcx, rsi; pwk
0x18002d870  call    cs:__imp_CloseThreadpoolWork
0x18002d876  nop
0x18002d877  lea     rcx, [rbp+430h+pv]; this
0x18002d87b  call    ??1_SParallelForContext@TPUtils@@QEAA@XZ; TPUtils::_SParallelForContext::~_SParallelForContext(void)
0x18002d880  mov     rcx, [rbp+430h+var_40]
0x18002d887  xor     rcx, rsp; StackCookie
0x18002d88a  call    __security_check_cookie
0x18002d88f  mov     rbx, [rsp+530h+arg_0]
0x18002d897  add     rsp, 500h
0x18002d89e  pop     r15
0x18002d8a0  pop     r14
0x18002d8a2  pop     r13
0x18002d8a4  pop     r12
0x18002d8a6  pop     rdi
0x18002d8a7  pop     rsi
0x18002d8a8  pop     rbp
0x18002d8a9  retn
0x18002d8aa  call    PerUserCatalogNameForCorruption__GetCatalog_0
0x18002d8af  mov     r13, rax
0x18002d8b2  jmp     loc_18002D6FA
0x18002d8b7  test    r14, r14
0x18002d8ba  jz      short loc_18002D880
0x18002d8bc  mov     edx, ebx
0x18002d8be  mov     rcx, r12
0x18002d8c1  call    _lambda_8cb70c2ce1141461991bfe18208f4cb1___operator__
0x18002d8c6  add     rbx, r15
0x18002d8c9  cmp     rbx, r14
0x18002d8cc  jb      short loc_18002D8BC
0x18002d8ce  jmp     short loc_18002D880
0x18002d8d0  mov     rcx, [rbp+430h+var_58]; this
0x18002d8d7  test    rcx, rcx
0x18002d8da  jnz     short loc_18002D914
0x18002d8dc  mov     rcx, [rbp+438h]; this
0x18002d8e3  mov     r9d, 8000FFFFh; char *
0x18002d8e9  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18002d8f0  mov     edx, 194h; void *
0x18002d8f5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d8fb  mov     rcx, [rbp+438h]; this
0x18002d902  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18002d909  mov     edx, 7Eh ; '~'; void *
0x18002d90e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002d914  call    ?raise@TPResultException@@UEAAXXZ; TPResultException::raise(void)
```
