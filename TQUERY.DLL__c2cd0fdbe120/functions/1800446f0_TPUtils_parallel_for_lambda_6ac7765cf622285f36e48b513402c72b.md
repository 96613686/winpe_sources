# TPUtils::parallel_for__lambda_6ac7765cf622285f36e48b513402c72b___

- ea: `0x1800446f0`
- end: `0x180044956`
- name: `TPUtils::parallel_for__lambda_6ac7765cf622285f36e48b513402c72b___`
- size: `614`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180042e8c`

## callees

- `0x18002cc2c`
- `0x18002dc24`
- `0x180038f08`
- `0x180043ccc`
- `0x1800446f0`
- `0x18004495c`
- `0x180044c48`
- `0x180147154`
- `0x180157c70`
- `0x180188d90`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180044850`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180044850`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18004482c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18004482c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004489a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004489a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180044887`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180044887`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180044796`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180044796`

## string_xrefs

- `0x18004491e`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`
- `0x18004493e`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall TPUtils::parallel_for__lambda_6ac7765cf622285f36e48b513402c72b___(
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
  struct _TP_WORK *ThreadpoolWork; // rsi
  __int64 v15; // r8
  const char *v16; // r9
  unsigned __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rax
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
    goto LABEL_22;
  }
  if ( (unsigned int)TPUtils::s_runningThreadCount > 0x19 )
  {
    do
LABEL_22:
      lambda_83b45034d5a21304844f56d2dcb3cda9_::operator()(
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
  v20 = off_1802C1428;
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
    lambda_83b45034d5a21304844f56d2dcb3cda9_::operator()(
      *(_QWORD *)a3,
      **((_QWORD **)a3 + 1) + 24LL * (unsigned int)v5++,
      v15);
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
0x1800446f0  mov     [rsp-8+arg_0], rbx
0x1800446f5  mov     [rsp-8+arg_18], rsi
0x1800446fa  push    rbp
0x1800446fb  push    rdi
0x1800446fc  push    r13
0x1800446fe  push    r14
0x180044700  push    r15
0x180044702  lea     rbp, [rsp-3F0h]
0x18004470a  sub     rsp, 4F0h
0x180044711  mov     rax, cs:__security_cookie
0x180044718  xor     rax, rsp
0x18004471b  mov     [rbp+410h+var_30], rax
0x180044722  mov     r15, r8
0x180044725  mov     r14, rdx
0x180044728  xor     ebx, ebx
0x18004472a  call    ?GetProcessorCount@TPUtils@@SA_KXZ; TPUtils::GetProcessorCount(void)
0x18004472f  mov     r8, rax
0x180044732  lea     r9d, [rbx+1]
0x180044736  cmp     rax, r9
0x180044739  jz      loc_1800448DD
0x18004473f  cmp     r14, r9
0x180044742  jbe     loc_1800448DD
0x180044748  mov     eax, cs:?s_runningThreadCount@TPUtils@@0JC; long volatile TPUtils::s_runningThreadCount
0x18004474e  cmp     eax, 19h
0x180044751  ja      loc_1800448E2
0x180044757  xor     edx, edx
0x180044759  mov     rax, r14
0x18004475c  div     r8
0x18004475f  mov     rdi, rdx
0x180044762  mov     r13, rax
0x180044765  test    rax, rax
0x180044768  cmovz   r13, r9
0x18004476c  mov     rcx, rax
0x18004476f  neg     rcx
0x180044772  sbb     rsi, rsi
0x180044775  and     rsi, rdx
0x180044778  test    rax, rax
0x18004477b  cmovnz  rdi, r8
0x18004477f  sub     rdi, r9
0x180044782  xor     r9d, r9d; Context
0x180044785  xor     r8d, r8d; Parameter
0x180044788  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18004478f  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180044796  call    cs:__imp_InitOnceExecuteOnce
0x18004479c  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, bl; bool g_isPerUserCatalogEnabled
0x1800447a2  jz      loc_1800448D6
0x1800447a8  call    PerUserCatalogNameForCorruption__GetCatalog_0
0x1800447ad  lea     rcx, off_1802C1428
0x1800447b4  mov     [rsp+510h+var_4E0], rcx
0x1800447b9  movups  xmm0, xmmword ptr [r15]
0x1800447bd  movdqu  [rsp+510h+var_4D8], xmm0
0x1800447c3  lea     rcx, [rsp+510h+var_4E0]
0x1800447c8  mov     [rsp+510h+var_4A8], rcx
0x1800447cd  mov     r9, rax
0x1800447d0  mov     r8, rdi
0x1800447d3  lea     rdx, [rsp+510h+var_4E0]
0x1800447d8  lea     rcx, [rsp+510h+pv]
0x1800447dd  call    ??0_SParallelForContext@TPUtils@@QEAA@AEBV?$function@$$A6AX_K@Z@std@@_KPEB_W@Z; TPUtils::_SParallelForContext::_SParallelForContext(std::function<void (unsigned __int64)> const &,unsigned __int64,wchar_t const *)
0x1800447e2  nop
0x1800447e3  mov     rcx, [rsp+510h+var_4A8]
0x1800447e8  test    rcx, rcx
0x1800447eb  jz      short loc_18004480D
0x1800447ed  mov     rax, [rcx]
0x1800447f0  lea     rdx, [rsp+510h+var_4E0]
0x1800447f5  cmp     rcx, rdx
0x1800447f8  setnz   dl
0x1800447fb  mov     rax, [rax+20h]
0x1800447ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044804  mov     [rsp+510h+var_4A8], 0
0x18004480d  test    rdi, rdi
0x180044810  jnz     loc_180044930
0x180044816  mov     [rsp+510h+var_4E8], 1
0x18004481d  xor     r8d, r8d; pcbe
0x180044820  lea     rdx, [rsp+510h+pv]; pv
0x180044825  lea     rcx, ?_ParallelForCallback@TPUtils@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18004482c  call    cs:__imp_CreateThreadpoolWork
0x180044832  mov     rsi, rax
0x180044835  mov     qword ptr [rsp+510h+var_4F0], rax; int
0x18004483a  test    rax, rax
0x18004483d  jz      loc_180044937
0x180044843  mov     byte ptr [rsp+510h+var_4E8+1], 1
0x180044848  test    rdi, rdi
0x18004484b  jz      short loc_18004485C
0x18004484d  mov     rcx, rsi; pwk
0x180044850  call    cs:__imp_SubmitThreadpoolWork
0x180044856  sub     rdi, 1
0x18004485a  jnz     short loc_18004484D
0x18004485c  mov     eax, ebx
0x18004485e  lea     rdx, [rax+rax*2]
0x180044862  mov     rax, [r15+8]
0x180044866  mov     rcx, [rax]
0x180044869  lea     rdx, [rcx+rdx*8]
0x18004486d  mov     rcx, [r15]
0x180044870  call    _lambda_83b45034d5a21304844f56d2dcb3cda9___operator__
0x180044875  inc     rbx
0x180044878  cmp     rbx, r14
0x18004487b  jb      short loc_18004485C
0x18004487d  mov     byte ptr [rsp+510h+var_4E8+1], 0
0x180044882  xor     edx, edx; fCancelPendingCallbacks
0x180044884  mov     rcx, rsi; pwk
0x180044887  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18004488d  mov     eax, [rbp+410h+var_50]
0x180044893  test    eax, eax
0x180044895  jg      short loc_180044905
0x180044897  mov     rcx, rsi; pwk
0x18004489a  call    cs:__imp_CloseThreadpoolWork
0x1800448a0  nop
0x1800448a1  lea     rcx, [rsp+510h+pv]; this
0x1800448a6  call    ??1_SParallelForContext@TPUtils@@QEAA@XZ; TPUtils::_SParallelForContext::~_SParallelForContext(void)
0x1800448ab  mov     rcx, [rbp+410h+var_30]
0x1800448b2  xor     rcx, rsp; StackCookie
0x1800448b5  call    __security_check_cookie
0x1800448ba  lea     r11, [rsp+510h+var_20]
0x1800448c2  mov     rbx, [r11+30h]
0x1800448c6  mov     rsi, [r11+48h]
0x1800448ca  mov     rsp, r11
0x1800448cd  pop     r15
0x1800448cf  pop     r14
0x1800448d1  pop     r13
0x1800448d3  pop     rdi
0x1800448d4  pop     rbp
0x1800448d5  retn
0x1800448d6  xor     eax, eax
0x1800448d8  jmp     loc_1800447AD
0x1800448dd  test    r14, r14
0x1800448e0  jz      short loc_1800448AB
0x1800448e2  mov     eax, ebx
0x1800448e4  lea     rdx, [rax+rax*2]
0x1800448e8  mov     rax, [r15+8]
0x1800448ec  mov     rcx, [rax]
0x1800448ef  lea     rdx, [rcx+rdx*8]
0x1800448f3  mov     rcx, [r15]
0x1800448f6  call    _lambda_83b45034d5a21304844f56d2dcb3cda9___operator__
0x1800448fb  inc     rbx
0x1800448fe  cmp     rbx, r14
0x180044901  jb      short loc_1800448E2
0x180044903  jmp     short loc_1800448AB
0x180044905  mov     rcx, [rbp+410h+var_48]; this
0x18004490c  test    rcx, rcx
0x18004490f  jnz     short loc_180044950
0x180044911  mov     rcx, [rbp+418h]; this
0x180044918  mov     r9d, 8000FFFFh; char *
0x18004491e  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180044925  mov     edx, 194h; void *
0x18004492a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180044930  xor     edx, edx
0x180044932  jmp     loc_1802B79B4
0x180044937  mov     rcx, [rbp+418h]; this
0x18004493e  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180044945  mov     edx, 7Eh ; '~'; void *
0x18004494a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180044950  call    ?raise@TPResultException@@UEAAXXZ; TPResultException::raise(void)
0x1802b79b4  mov     rcx, rdx
0x1802b79b7  add     rcx, rcx
0x1802b79ba  mov     [rbp+rcx*8+410h+var_450], rbx
0x1802b79bf  lea     rax, [r13+1]
0x1802b79c3  test    rsi, rsi
0x1802b79c6  cmovz   rax, r13
0x1802b79ca  add     rbx, rax
0x1802b79cd  mov     [rbp+rcx*8+410h+var_448], rbx
0x1802b79d2  inc     rdx
0x1802b79d5  lea     rax, [rsi-1]
0x1802b79d9  test    rsi, rsi
0x1802b79dc  cmovz   rax, rsi
0x1802b79e0  mov     rsi, rax
0x1802b79e3  cmp     rdx, rdi
0x1802b79e6  jb      short loc_1802B79B4
0x1802b79e8  jmp     loc_180044816
```
