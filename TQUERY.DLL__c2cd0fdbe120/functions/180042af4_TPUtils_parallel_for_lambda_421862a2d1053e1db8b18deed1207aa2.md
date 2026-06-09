# TPUtils::parallel_for__lambda_421862a2d1053e1db8b18deed1207aa2___

- ea: `0x180042af4`
- end: `0x180042d84`
- name: `TPUtils::parallel_for__lambda_421862a2d1053e1db8b18deed1207aa2___`
- size: `656`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800429b4`

## callees

- `0x18002cc2c`
- `0x18002dc24`
- `0x180038f08`
- `0x180041b28`
- `0x180042af4`
- `0x180043ccc`
- `0x180043d18`
- `0x180147154`
- `0x180157c70`
- `0x180188d90`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180042c98`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180042c98`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180042c74`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180042c74`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180042ce1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180042ce1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180042cce`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180042cce`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180042bde`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180042bde`

## string_xrefs

- `0x180042d53`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`
- `0x180042d6c`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall TPUtils::parallel_for__lambda_421862a2d1053e1db8b18deed1207aa2___(
        __int64 a1,
        unsigned __int64 a2,
        _QWORD *a3)
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
  const char *v15; // r9
  unsigned __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 (__fastcall **v19)(); // [rsp+30h] [rbp-D0h] BYREF
  __int128 v20; // [rsp+38h] [rbp-C8h]
  __int64 (__fastcall ***v21)(); // [rsp+68h] [rbp-98h]
  _BYTE pv[1104]; // [rsp+70h] [rbp-90h] BYREF
  int v23; // [rsp+4C0h] [rbp+3C0h]
  TPResultException *v24; // [rsp+4C8h] [rbp+3C8h]
  wil::details::in1diag3 *retaddr; // [rsp+518h] [rbp+418h]

  v5 = 0;
  ProcessorCount = TPUtils::GetProcessorCount();
  if ( ProcessorCount == 1 || a2 <= 1 )
  {
    if ( !a2 )
      return;
    goto LABEL_3;
  }
  if ( (unsigned int)TPUtils::s_runningThreadCount > 0x19 )
  {
    do
LABEL_3:
      lambda_7866b6982f53eae8a3662833f5d24512_::operator()(*a3, *(_QWORD *)a3[1] + 3348LL * (unsigned int)v5++);
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
  v19 = off_1802C13F8;
  v20 = *(_OWORD *)a3;
  v21 = &v19;
  TPUtils::_SParallelForContext::_SParallelForContext(pv, &v19, v11, Catalog);
  if ( v21 )
  {
    v13 = &v19;
    LOBYTE(v13) = v21 != &v19;
    ((void (__fastcall *)(__int64 (__fastcall ***)(), __int64 (__fastcall ***)()))(*v21)[4])(v21, v13);
    v21 = 0;
  }
  if ( v11 )
  {
    v16 = 0;
    do
    {
      *(_QWORD *)&pv[16 * v16 + 80] = v5;
      v17 = v9 + 1;
      if ( !v10 )
        v17 = v9;
      v5 += v17;
      *(_QWORD *)&pv[16 * v16++ + 88] = v5;
      v18 = v10 - 1;
      if ( !v10 )
        v18 = 0;
      v10 = v18;
    }
    while ( v16 < v11 );
  }
  ThreadpoolWork = CreateThreadpoolWork(TPUtils::_ParallelForCallback, pv, 0);
  if ( !ThreadpoolWork )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\TPUtils.h",
      v15);
  for ( ; v11; --v11 )
    SubmitThreadpoolWork(ThreadpoolWork);
  do
    lambda_7866b6982f53eae8a3662833f5d24512_::operator()(*a3, *(_QWORD *)a3[1] + 3348LL * (unsigned int)v5++);
  while ( v5 < a2 );
  WaitForThreadpoolWorkCallbacks(ThreadpoolWork, 0);
  if ( v23 > 0 )
  {
    if ( !v24 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x194,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\TPUtils.h",
        (const char *)0x8000FFFFLL,
        (int)ThreadpoolWork);
    TPResultException::raise(v24);
  }
  CloseThreadpoolWork(ThreadpoolWork);
  TPUtils::_SParallelForContext::~_SParallelForContext((TPUtils::_SParallelForContext *)pv);
}

```

## disassembly

```asm
0x180042af4  mov     [rsp-8+arg_0], rbx
0x180042af9  mov     [rsp-8+arg_18], rsi
0x180042afe  push    rbp
0x180042aff  push    rdi
0x180042b00  push    r13
0x180042b02  push    r14
0x180042b04  push    r15
0x180042b06  lea     rbp, [rsp-3F0h]
0x180042b0e  sub     rsp, 4F0h
0x180042b15  mov     rax, cs:__security_cookie
0x180042b1c  xor     rax, rsp
0x180042b1f  mov     [rbp+410h+var_30], rax
0x180042b26  mov     r15, r8
0x180042b29  mov     r14, rdx
0x180042b2c  xor     ebx, ebx
0x180042b2e  call    ?GetProcessorCount@TPUtils@@SA_KXZ; TPUtils::GetProcessorCount(void)
0x180042b33  mov     r8, rax
0x180042b36  lea     r9d, [rbx+1]
0x180042b3a  cmp     rax, r9
0x180042b3d  jnz     short loc_180042B8F
0x180042b3f  test    r14, r14
0x180042b42  jz      short loc_180042B64
0x180042b44  mov     eax, ebx
0x180042b46  imul    rdx, rax, 0D14h
0x180042b4d  mov     rax, [r15+8]
0x180042b51  add     rdx, [rax]
0x180042b54  mov     rcx, [r15]
0x180042b57  call    _lambda_7866b6982f53eae8a3662833f5d24512___operator__
0x180042b5c  inc     rbx
0x180042b5f  cmp     rbx, r14
0x180042b62  jb      short loc_180042B44
0x180042b64  mov     rcx, [rbp+410h+var_30]
0x180042b6b  xor     rcx, rsp; StackCookie
0x180042b6e  call    __security_check_cookie
0x180042b73  lea     r11, [rsp+510h+var_20]
0x180042b7b  mov     rbx, [r11+30h]
0x180042b7f  mov     rsi, [r11+48h]
0x180042b83  mov     rsp, r11
0x180042b86  pop     r15
0x180042b88  pop     r14
0x180042b8a  pop     r13
0x180042b8c  pop     rdi
0x180042b8d  pop     rbp
0x180042b8e  retn
0x180042b8f  cmp     r14, r9
0x180042b92  jbe     short loc_180042B3F
0x180042b94  mov     eax, cs:?s_runningThreadCount@TPUtils@@0JC; long volatile TPUtils::s_runningThreadCount
0x180042b9a  cmp     eax, 19h
0x180042b9d  ja      short loc_180042B44
0x180042b9f  xor     edx, edx
0x180042ba1  mov     rax, r14
0x180042ba4  div     r8
0x180042ba7  mov     rdi, rdx
0x180042baa  mov     r13, rax
0x180042bad  test    rax, rax
0x180042bb0  cmovz   r13, r9
0x180042bb4  mov     rcx, rax
0x180042bb7  neg     rcx
0x180042bba  sbb     rsi, rsi
0x180042bbd  and     rsi, rdx
0x180042bc0  test    rax, rax
0x180042bc3  cmovnz  rdi, r8
0x180042bc7  sub     rdi, r9
0x180042bca  xor     r9d, r9d; Context
0x180042bcd  xor     r8d, r8d; Parameter
0x180042bd0  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180042bd7  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180042bde  call    cs:__imp_InitOnceExecuteOnce
0x180042be4  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, bl; bool g_isPerUserCatalogEnabled
0x180042bea  jz      loc_180042CF7
0x180042bf0  call    PerUserCatalogNameForCorruption__GetCatalog
0x180042bf5  lea     rcx, off_1802C13F8
0x180042bfc  mov     [rsp+510h+var_4E0], rcx
0x180042c01  movups  xmm0, xmmword ptr [r15]
0x180042c05  movdqu  [rsp+510h+var_4D8], xmm0
0x180042c0b  lea     rcx, [rsp+510h+var_4E0]
0x180042c10  mov     [rsp+510h+var_4A8], rcx
0x180042c15  mov     r9, rax
0x180042c18  mov     r8, rdi
0x180042c1b  lea     rdx, [rsp+510h+var_4E0]
0x180042c20  lea     rcx, [rsp+510h+pv]
0x180042c25  call    ??0_SParallelForContext@TPUtils@@QEAA@AEBV?$function@$$A6AX_K@Z@std@@_KPEB_W@Z; TPUtils::_SParallelForContext::_SParallelForContext(std::function<void (unsigned __int64)> const &,unsigned __int64,wchar_t const *)
0x180042c2a  nop
0x180042c2b  mov     rcx, [rsp+510h+var_4A8]
0x180042c30  test    rcx, rcx
0x180042c33  jz      short loc_180042C55
0x180042c35  mov     rax, [rcx]
0x180042c38  lea     rdx, [rsp+510h+var_4E0]
0x180042c3d  cmp     rcx, rdx
0x180042c40  setnz   dl
0x180042c43  mov     rax, [rax+20h]
0x180042c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c4c  mov     [rsp+510h+var_4A8], 0
0x180042c55  test    rdi, rdi
0x180042c58  jnz     loc_180042CFE
0x180042c5e  mov     [rsp+510h+var_4E8], 1
0x180042c65  xor     r8d, r8d; pcbe
0x180042c68  lea     rdx, [rsp+510h+pv]; pv
0x180042c6d  lea     rcx, ?_ParallelForCallback@TPUtils@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180042c74  call    cs:__imp_CreateThreadpoolWork
0x180042c7a  mov     rsi, rax
0x180042c7d  mov     qword ptr [rsp+510h+var_4F0], rax; int
0x180042c82  test    rax, rax
0x180042c85  jz      loc_180042D65
0x180042c8b  mov     byte ptr [rsp+510h+var_4E8+1], 1
0x180042c90  test    rdi, rdi
0x180042c93  jz      short loc_180042CA4
0x180042c95  mov     rcx, rsi; pwk
0x180042c98  call    cs:__imp_SubmitThreadpoolWork
0x180042c9e  sub     rdi, 1
0x180042ca2  jnz     short loc_180042C95
0x180042ca4  mov     eax, ebx
0x180042ca6  imul    rdx, rax, 0D14h
0x180042cad  mov     rax, [r15+8]
0x180042cb1  add     rdx, [rax]
0x180042cb4  mov     rcx, [r15]
0x180042cb7  call    _lambda_7866b6982f53eae8a3662833f5d24512___operator__
0x180042cbc  inc     rbx
0x180042cbf  cmp     rbx, r14
0x180042cc2  jb      short loc_180042CA4
0x180042cc4  mov     byte ptr [rsp+510h+var_4E8+1], 0
0x180042cc9  xor     edx, edx; fCancelPendingCallbacks
0x180042ccb  mov     rcx, rsi; pwk
0x180042cce  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180042cd4  mov     eax, [rbp+410h+var_50]
0x180042cda  test    eax, eax
0x180042cdc  jg      short loc_180042D3A
0x180042cde  mov     rcx, rsi; pwk
0x180042ce1  call    cs:__imp_CloseThreadpoolWork
0x180042ce7  nop
0x180042ce8  lea     rcx, [rsp+510h+pv]; this
0x180042ced  call    ??1_SParallelForContext@TPUtils@@QEAA@XZ; TPUtils::_SParallelForContext::~_SParallelForContext(void)
0x180042cf2  jmp     loc_180042B64
0x180042cf7  xor     eax, eax
0x180042cf9  jmp     loc_180042BF5
0x180042cfe  xor     edx, edx
0x180042d00  mov     rcx, rdx
0x180042d03  add     rcx, rcx
0x180042d06  mov     [rbp+rcx*8+410h+var_450], rbx
0x180042d0b  lea     rax, [r13+1]
0x180042d0f  test    rsi, rsi
0x180042d12  cmovz   rax, r13
0x180042d16  add     rbx, rax
0x180042d19  mov     [rbp+rcx*8+410h+var_448], rbx
0x180042d1e  inc     rdx
0x180042d21  lea     rax, [rsi-1]
0x180042d25  test    rsi, rsi
0x180042d28  cmovz   rax, rsi
0x180042d2c  mov     rsi, rax
0x180042d2f  cmp     rdx, rdi
0x180042d32  jnb     loc_180042C5E
0x180042d38  jmp     short loc_180042D00
0x180042d3a  mov     rcx, [rbp+410h+var_48]; this
0x180042d41  test    rcx, rcx
0x180042d44  jnz     short loc_180042D7E
0x180042d46  mov     rcx, [rbp+418h]; this
0x180042d4d  mov     r9d, 8000FFFFh; char *
0x180042d53  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180042d5a  mov     edx, 194h; void *
0x180042d5f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180042d65  mov     rcx, [rbp+418h]; this
0x180042d6c  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180042d73  mov     edx, 7Eh ; '~'; void *
0x180042d78  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180042d7e  call    ?raise@TPResultException@@UEAAXXZ; TPResultException::raise(void)
```
