# TPUtils::parallel_for__lambda_6bf67cf5ea3f53ea73cdaae9034577fe___

- ea: `0x18002bea4`
- end: `0x18002c12a`
- name: `TPUtils::parallel_for__lambda_6bf67cf5ea3f53ea73cdaae9034577fe___`
- size: `646`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180032558`

## callees

- `0x18002add8`
- `0x18002bea4`
- `0x18002cc2c`
- `0x18002dc24`
- `0x180038f08`
- `0x180043ccc`
- `0x180044c48`
- `0x180147154`
- `0x180157c70`
- `0x180188d90`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002c07a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18002c07a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002c056`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18002c056`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002c0c3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002c0c3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002c0b0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18002c0b0`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002bf8e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002bf8e`

## string_xrefs

- `0x18002c0f9`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`
- `0x18002c112`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall TPUtils::parallel_for__lambda_6bf67cf5ea3f53ea73cdaae9034577fe___(
        __int64 a1,
        unsigned __int64 a2,
        _QWORD *a3)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 ProcessorCount; // rax
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rdi
  __int64 v10; // r13
  __int64 v11; // rsi
  unsigned __int64 v12; // rdi
  __int64 Catalog_0; // rax
  __int64 (__fastcall ***v14)(); // rdx
  unsigned __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rax
  struct _TP_WORK *ThreadpoolWork; // rsi
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
  v7 = ProcessorCount;
  if ( a2 <= 1 || ProcessorCount == 1 )
  {
    if ( !a2 )
      return;
    goto LABEL_3;
  }
  if ( (unsigned int)TPUtils::s_runningThreadCount > 0x19 )
  {
    do
LABEL_3:
      lambda_5e3e7757fa92688a6d3e4e0847bf4b0e_::operator()(*a3, *(_QWORD *)a3[1] + 3348LL * (unsigned int)v5++);
    while ( v5 < a2 );
    return;
  }
  v8 = a2 / ProcessorCount;
  v9 = a2 % v7;
  v10 = a2 / v7;
  if ( !(a2 / v7) )
    v10 = 1;
  v11 = (a2 % v7) & -(__int64)(v8 != 0);
  if ( v8 )
    v9 = v7;
  v12 = v9 - 1;
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( g_isPerUserCatalogEnabled )
    Catalog_0 = PerUserCatalogNameForCorruption::GetCatalog_0();
  else
    Catalog_0 = 0;
  v20 = off_1802C1458;
  v21 = *(_OWORD *)a3;
  v22 = &v20;
  TPUtils::_SParallelForContext::_SParallelForContext(pv, &v20, v12, Catalog_0);
  if ( v22 )
  {
    v14 = &v20;
    LOBYTE(v14) = v22 != &v20;
    ((void (__fastcall *)(__int64 (__fastcall ***)(), __int64 (__fastcall ***)()))(*v22)[4])(v22, v14);
    v22 = 0;
  }
  if ( v12 )
  {
    v15 = 0;
    do
    {
      *(_QWORD *)&pv[16 * v15 + 80] = v5;
      v16 = v10 + 1;
      if ( !v11 )
        v16 = v10;
      v5 += v16;
      *(_QWORD *)&pv[16 * v15++ + 88] = v5;
      v17 = v11 - 1;
      if ( !v11 )
        v17 = 0;
      v11 = v17;
    }
    while ( v15 < v12 );
  }
  ThreadpoolWork = CreateThreadpoolWork(TPUtils::_ParallelForCallback, pv, 0);
  if ( !ThreadpoolWork )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\TPUtils.h",
      v19);
  for ( ; v12; --v12 )
    SubmitThreadpoolWork(ThreadpoolWork);
  do
    lambda_5e3e7757fa92688a6d3e4e0847bf4b0e_::operator()(*a3, *(_QWORD *)a3[1] + 3348LL * (unsigned int)v5++);
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
0x18002bea4  mov     [rsp-8+arg_0], rbx
0x18002bea9  mov     [rsp-8+arg_18], rsi
0x18002beae  push    rbp
0x18002beaf  push    rdi
0x18002beb0  push    r13
0x18002beb2  push    r14
0x18002beb4  push    r15
0x18002beb6  lea     rbp, [rsp-3F0h]
0x18002bebe  sub     rsp, 4F0h
0x18002bec5  mov     rax, cs:__security_cookie
0x18002becc  xor     rax, rsp
0x18002becf  mov     [rbp+410h+var_30], rax
0x18002bed6  mov     r15, r8
0x18002bed9  mov     r14, rdx
0x18002bedc  xor     ebx, ebx
0x18002bede  call    ?GetProcessorCount@TPUtils@@SA_KXZ; TPUtils::GetProcessorCount(void)
0x18002bee3  mov     r8, rax
0x18002bee6  lea     r9d, [rbx+1]
0x18002beea  cmp     r14, r9
0x18002beed  ja      short loc_18002BF3F
0x18002beef  test    r14, r14
0x18002bef2  jz      short loc_18002BF14
0x18002bef4  mov     eax, ebx
0x18002bef6  imul    rdx, rax, 0D14h
0x18002befd  mov     rax, [r15+8]
0x18002bf01  add     rdx, [rax]
0x18002bf04  mov     rcx, [r15]
0x18002bf07  call    _lambda_5e3e7757fa92688a6d3e4e0847bf4b0e___operator__
0x18002bf0c  inc     rbx
0x18002bf0f  cmp     rbx, r14
0x18002bf12  jb      short loc_18002BEF4
0x18002bf14  mov     rcx, [rbp+410h+var_30]
0x18002bf1b  xor     rcx, rsp; StackCookie
0x18002bf1e  call    __security_check_cookie
0x18002bf23  lea     r11, [rsp+510h+var_20]
0x18002bf2b  mov     rbx, [r11+30h]
0x18002bf2f  mov     rsi, [r11+48h]
0x18002bf33  mov     rsp, r11
0x18002bf36  pop     r15
0x18002bf38  pop     r14
0x18002bf3a  pop     r13
0x18002bf3c  pop     rdi
0x18002bf3d  pop     rbp
0x18002bf3e  retn
0x18002bf3f  cmp     rax, r9
0x18002bf42  jz      short loc_18002BEEF
0x18002bf44  mov     eax, cs:?s_runningThreadCount@TPUtils@@0JC; long volatile TPUtils::s_runningThreadCount
0x18002bf4a  cmp     eax, 19h
0x18002bf4d  ja      short loc_18002BEF4
0x18002bf4f  xor     edx, edx
0x18002bf51  mov     rax, r14
0x18002bf54  div     r8
0x18002bf57  mov     rdi, rdx
0x18002bf5a  mov     r13, rax
0x18002bf5d  test    rax, rax
0x18002bf60  cmovz   r13, r9
0x18002bf64  mov     rcx, rax
0x18002bf67  neg     rcx
0x18002bf6a  sbb     rsi, rsi
0x18002bf6d  and     rsi, rdx
0x18002bf70  test    rax, rax
0x18002bf73  cmovnz  rdi, r8
0x18002bf77  sub     rdi, r9
0x18002bf7a  xor     r9d, r9d; Context
0x18002bf7d  xor     r8d, r8d; Parameter
0x18002bf80  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18002bf87  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18002bf8e  call    cs:__imp_InitOnceExecuteOnce
0x18002bf94  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, bl; bool g_isPerUserCatalogEnabled
0x18002bf9a  jz      loc_18002C0D9
0x18002bfa0  call    PerUserCatalogNameForCorruption__GetCatalog_0
0x18002bfa5  lea     rcx, off_1802C1458
0x18002bfac  mov     [rsp+510h+var_4E0], rcx
0x18002bfb1  movups  xmm0, xmmword ptr [r15]
0x18002bfb5  movdqu  [rsp+510h+var_4D8], xmm0
0x18002bfbb  lea     rcx, [rsp+510h+var_4E0]
0x18002bfc0  mov     [rsp+510h+var_4A8], rcx
0x18002bfc5  mov     r9, rax
0x18002bfc8  mov     r8, rdi
0x18002bfcb  lea     rdx, [rsp+510h+var_4E0]
0x18002bfd0  lea     rcx, [rsp+510h+pv]
0x18002bfd5  call    ??0_SParallelForContext@TPUtils@@QEAA@AEBV?$function@$$A6AX_K@Z@std@@_KPEB_W@Z; TPUtils::_SParallelForContext::_SParallelForContext(std::function<void (unsigned __int64)> const &,unsigned __int64,wchar_t const *)
0x18002bfda  nop
0x18002bfdb  mov     rcx, [rsp+510h+var_4A8]
0x18002bfe0  test    rcx, rcx
0x18002bfe3  jz      short loc_18002C005
0x18002bfe5  mov     rax, [rcx]
0x18002bfe8  lea     rdx, [rsp+510h+var_4E0]
0x18002bfed  cmp     rcx, rdx
0x18002bff0  setnz   dl
0x18002bff3  mov     rax, [rax+20h]
0x18002bff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bffc  mov     [rsp+510h+var_4A8], 0
0x18002c005  test    rdi, rdi
0x18002c008  jz      short loc_18002C040
0x18002c00a  xor     edx, edx
0x18002c00c  mov     rcx, rdx
0x18002c00f  add     rcx, rcx
0x18002c012  mov     [rbp+rcx*8+410h+var_450], rbx
0x18002c017  lea     rax, [r13+1]
0x18002c01b  test    rsi, rsi
0x18002c01e  cmovz   rax, r13
0x18002c022  add     rbx, rax
0x18002c025  mov     [rbp+rcx*8+410h+var_448], rbx
0x18002c02a  inc     rdx
0x18002c02d  lea     rax, [rsi-1]
0x18002c031  test    rsi, rsi
0x18002c034  cmovz   rax, rsi
0x18002c038  mov     rsi, rax
0x18002c03b  cmp     rdx, rdi
0x18002c03e  jb      short loc_18002C00C
0x18002c040  mov     [rsp+510h+var_4E8], 1
0x18002c047  xor     r8d, r8d; pcbe
0x18002c04a  lea     rdx, [rsp+510h+pv]; pv
0x18002c04f  lea     rcx, ?_ParallelForCallback@TPUtils@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18002c056  call    cs:__imp_CreateThreadpoolWork
0x18002c05c  mov     rsi, rax
0x18002c05f  mov     qword ptr [rsp+510h+var_4F0], rax; int
0x18002c064  test    rax, rax
0x18002c067  jz      loc_18002C10B
0x18002c06d  mov     byte ptr [rsp+510h+var_4E8+1], 1
0x18002c072  test    rdi, rdi
0x18002c075  jz      short loc_18002C086
0x18002c077  mov     rcx, rsi; pwk
0x18002c07a  call    cs:__imp_SubmitThreadpoolWork
0x18002c080  sub     rdi, 1
0x18002c084  jnz     short loc_18002C077
0x18002c086  mov     eax, ebx
0x18002c088  imul    rdx, rax, 0D14h
0x18002c08f  mov     rax, [r15+8]
0x18002c093  add     rdx, [rax]
0x18002c096  mov     rcx, [r15]
0x18002c099  call    _lambda_5e3e7757fa92688a6d3e4e0847bf4b0e___operator__
0x18002c09e  inc     rbx
0x18002c0a1  cmp     rbx, r14
0x18002c0a4  jb      short loc_18002C086
0x18002c0a6  mov     byte ptr [rsp+510h+var_4E8+1], 0
0x18002c0ab  xor     edx, edx; fCancelPendingCallbacks
0x18002c0ad  mov     rcx, rsi; pwk
0x18002c0b0  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18002c0b6  mov     eax, [rbp+410h+var_50]
0x18002c0bc  test    eax, eax
0x18002c0be  jg      short loc_18002C0E0
0x18002c0c0  mov     rcx, rsi; pwk
0x18002c0c3  call    cs:__imp_CloseThreadpoolWork
0x18002c0c9  nop
0x18002c0ca  lea     rcx, [rsp+510h+pv]; this
0x18002c0cf  call    ??1_SParallelForContext@TPUtils@@QEAA@XZ; TPUtils::_SParallelForContext::~_SParallelForContext(void)
0x18002c0d4  jmp     loc_18002BF14
0x18002c0d9  xor     eax, eax
0x18002c0db  jmp     loc_18002BFA5
0x18002c0e0  mov     rcx, [rbp+410h+var_48]; this
0x18002c0e7  test    rcx, rcx
0x18002c0ea  jnz     short loc_18002C124
0x18002c0ec  mov     rcx, [rbp+418h]; this
0x18002c0f3  mov     r9d, 8000FFFFh; char *
0x18002c0f9  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18002c100  mov     edx, 194h; void *
0x18002c105  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002c10b  mov     rcx, [rbp+418h]; this
0x18002c112  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18002c119  mov     edx, 7Eh ; '~'; void *
0x18002c11e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002c124  call    ?raise@TPResultException@@UEAAXXZ; TPResultException::raise(void)
```
