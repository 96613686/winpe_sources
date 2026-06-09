# TPUtils::parallel_for__lambda_400fe692df54aa0eaacf0f632abd034a___

- ea: `0x180178638`
- end: `0x1801788d8`
- name: `TPUtils::parallel_for__lambda_400fe692df54aa0eaacf0f632abd034a___`
- size: `672`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1801833a0`

## callees

- `0x18002cc2c`
- `0x18002dc24`
- `0x180038f08`
- `0x180043ccc`
- `0x1800eaa2c`
- `0x1800ee964`
- `0x1800f2ee8`
- `0x180157c70`
- `0x180178638`
- `0x180188d90`
- `0x18019c834`
- `0x180236fec`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180178707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180178719`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180178707`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180178719`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180178840`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180178840`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801786f9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1801786f9`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1801786e0`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1801786e0`

## string_xrefs

- `0x18017886f`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`
- `0x18017873a`: `onecoreuap\base\appmodel\Search\common\include\PerUserCatalogResetHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall TPUtils::parallel_for__lambda_400fe692df54aa0eaacf0f632abd034a___(
        __int64 a1,
        unsigned __int64 a2,
        __int128 *a3)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 ProcessorCount; // r8
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // r14
  __int64 v9; // r15
  __int64 v10; // r13
  unsigned __int64 v11; // r14
  LPVOID Value; // rsi
  bool v13; // r15
  signed int LastError; // eax
  unsigned __int64 v15; // rdx
  __int64 (__fastcall ***v16)(); // rdx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // r8
  struct _TP_CALLBACK_ENVIRON_V3 *v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  PTP_WORK pwk; // [rsp+30h] [rbp-D0h] BYREF
  char v23; // [rsp+39h] [rbp-C7h]
  __int64 (__fastcall **v24)(); // [rsp+40h] [rbp-C0h] BYREF
  __int128 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  __int64 (__fastcall ***v27)(); // [rsp+78h] [rbp-88h]
  _BYTE v28[1104]; // [rsp+80h] [rbp-80h] BYREF
  int v29; // [rsp+4D0h] [rbp+3D0h]
  TPResultException *v30; // [rsp+4D8h] [rbp+3D8h]
  wil::details::in1diag3 *retaddr; // [rsp+538h] [rbp+438h]

  v5 = 0;
  ProcessorCount = TPUtils::GetProcessorCount();
  if ( ProcessorCount == 1 || a2 <= 1 )
  {
    if ( !a2 )
      return;
    goto LABEL_37;
  }
  if ( (unsigned int)TPUtils::s_runningThreadCount > 0x19 )
  {
    do
LABEL_37:
      lambda_400fe692df54aa0eaacf0f632abd034a_::operator()(a3, (unsigned int)v5++, ProcessorCount);
    while ( v5 < a2 );
    return;
  }
  v7 = a2 / ProcessorCount;
  v8 = a2 % ProcessorCount;
  v9 = a2 / ProcessorCount;
  if ( !(a2 / ProcessorCount) )
    v9 = 1;
  pwk = (PTP_WORK)v9;
  v10 = (a2 % ProcessorCount) & -(__int64)(v7 != 0);
  if ( v7 )
    v8 = ProcessorCount;
  v11 = v8 - 1;
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( !g_isPerUserCatalogEnabled || PerUserCatalogNameForCorruption::g_tlsIndex == -1 )
  {
    Value = 0;
  }
  else
  {
    Value = TlsGetValue(PerUserCatalogNameForCorruption::g_tlsIndex);
    v13 = !Value && GetLastError();
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( v13 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\PerUserCatalogResetHelper.h",
        (const char *)(unsigned int)LastError,
        (int)v20);
    v9 = (__int64)pwk;
  }
  v24 = off_1802C87B8;
  v25 = *a3;
  v26 = *((_QWORD *)a3 + 2);
  v27 = &v24;
  TPUtils::_SParallelForContext::_SParallelForContext(v28, &v24, v11, Value);
  if ( v27 )
  {
    v16 = &v24;
    LOBYTE(v16) = v27 != &v24;
    ((void (__fastcall *)(__int64 (__fastcall ***)(), __int64 (__fastcall ***)()))(*v27)[4])(v27, v16);
    v27 = 0;
  }
  if ( v11 )
  {
    v15 = 0;
    do
    {
      *(_QWORD *)&v28[16 * v15 + 80] = v5;
      v17 = v9 + 1;
      if ( !v10 )
        v17 = v9;
      v5 += v17;
      *(_QWORD *)&v28[16 * v15++ + 88] = v5;
      v18 = v10 - 1;
      if ( !v10 )
        v18 = 0;
      v10 = v18;
    }
    while ( v15 < v11 );
  }
  pwk = 0;
  CThreadPoolWork::Init((CThreadPoolWork *)&pwk, v15, TPUtils::_ParallelForCallback, v28, v20);
  CThreadPoolWork::SubmitThreadpoolWork((CThreadPoolWork *)&pwk, v11);
  do
    lambda_400fe692df54aa0eaacf0f632abd034a_::operator()(a3, (unsigned int)v5++, v19);
  while ( v5 < a2 );
  v23 = 0;
  WaitForThreadpoolWorkCallbacks(pwk, 0);
  if ( v29 > 0 )
  {
    if ( v30 )
      TPResultException::raise(v30);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x194,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\TPUtils.h",
      (const char *)0x8000FFFFLL,
      v21);
  }
  CThreadPoolWork::~CThreadPoolWork(&pwk);
  TPUtils::_SParallelForContext::~_SParallelForContext((TPUtils::_SParallelForContext *)v28);
}

```

## disassembly

```asm
0x180178638  mov     [rsp-8+arg_0], rbx
0x18017863d  push    rbp
0x18017863e  push    rsi
0x18017863f  push    rdi
0x180178640  push    r12
0x180178642  push    r13
0x180178644  push    r14
0x180178646  push    r15
0x180178648  lea     rbp, [rsp-400h]
0x180178650  sub     rsp, 500h
0x180178657  mov     rax, cs:__security_cookie
0x18017865e  xor     rax, rsp
0x180178661  mov     [rbp+430h+var_40], rax
0x180178668  mov     r12, r8
0x18017866b  mov     rdi, rdx
0x18017866e  xor     ebx, ebx
0x180178670  call    ?GetProcessorCount@TPUtils@@SA_KXZ; TPUtils::GetProcessorCount(void)
0x180178675  mov     r8, rax
0x180178678  lea     esi, [rbx+1]
0x18017867b  cmp     rax, rsi
0x18017867e  jz      loc_180178897
0x180178684  cmp     rdi, rsi
0x180178687  jbe     loc_180178897
0x18017868d  mov     eax, cs:?s_runningThreadCount@TPUtils@@0JC; long volatile TPUtils::s_runningThreadCount
0x180178693  cmp     eax, 19h
0x180178696  ja      loc_18017889C
0x18017869c  xor     edx, edx
0x18017869e  mov     rax, rdi
0x1801786a1  div     r8
0x1801786a4  mov     r14, rdx
0x1801786a7  mov     r15, rax
0x1801786aa  test    rax, rax
0x1801786ad  cmovz   r15, rsi
0x1801786b1  mov     [rsp+530h+pwk], r15
0x1801786b6  mov     rcx, rax
0x1801786b9  neg     rcx
0x1801786bc  sbb     r13, r13
0x1801786bf  and     r13, rdx
0x1801786c2  test    rax, rax
0x1801786c5  cmovnz  r14, r8
0x1801786c9  sub     r14, rsi
0x1801786cc  xor     r9d, r9d; Context
0x1801786cf  xor     r8d, r8d; Parameter
0x1801786d2  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1801786d9  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1801786e0  call    cs:__imp_InitOnceExecuteOnce
0x1801786e6  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, bl; bool g_isPerUserCatalogEnabled
0x1801786ec  jz      short loc_180178752
0x1801786ee  mov     ecx, cs:?g_tlsIndex@PerUserCatalogNameForCorruption@@3KA; dwTlsIndex
0x1801786f4  cmp     ecx, 0FFFFFFFFh
0x1801786f7  jz      short loc_180178752
0x1801786f9  call    cs:__imp_TlsGetValue
0x1801786ff  mov     rsi, rax
0x180178702  test    rax, rax
0x180178705  jnz     short loc_180178716
0x180178707  call    cs:__imp_GetLastError
0x18017870d  test    eax, eax
0x18017870f  jz      short loc_180178716
0x180178711  mov     r15b, 1
0x180178714  jmp     short loc_180178719
0x180178716  xor     r15b, r15b
0x180178719  call    cs:__imp_GetLastError
0x18017871f  test    eax, eax
0x180178721  jle     short loc_18017872B
0x180178723  movzx   eax, ax
0x180178726  or      eax, 80070000h
0x18017872b  mov     rcx, [rbp+438h]; this
0x180178732  test    r15b, r15b
0x180178735  jz      short loc_18017874B
0x180178737  mov     r9d, eax; char *
0x18017873a  lea     r8, aOnecoreuapBase_288; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180178741  mov     edx, 47h ; 'G'; void *
0x180178746  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017874b  mov     r15, [rsp+530h+pwk]
0x180178750  jmp     short loc_180178754
0x180178752  xor     esi, esi
0x180178754  lea     rax, off_1802C87B8
0x18017875b  mov     [rsp+530h+var_4F0], rax
0x180178760  movups  xmm0, xmmword ptr [r12]
0x180178765  movups  [rsp+530h+var_4E8], xmm0
0x18017876a  movsd   xmm1, qword ptr [r12+10h]
0x180178771  movsd   [rsp+530h+var_4D8], xmm1
0x180178777  lea     rax, [rsp+530h+var_4F0]
0x18017877c  mov     [rsp+530h+var_4B8], rax
0x180178781  mov     r9, rsi
0x180178784  mov     r8, r14
0x180178787  lea     rdx, [rsp+530h+var_4F0]
0x18017878c  lea     rcx, [rbp+430h+var_4B0]
0x180178790  call    ??0_SParallelForContext@TPUtils@@QEAA@AEBV?$function@$$A6AX_K@Z@std@@_KPEB_W@Z; TPUtils::_SParallelForContext::_SParallelForContext(std::function<void (unsigned __int64)> const &,unsigned __int64,wchar_t const *)
0x180178795  nop
0x180178796  mov     rcx, [rsp+530h+var_4B8]
0x18017879b  xor     esi, esi
0x18017879d  test    rcx, rcx
0x1801787a0  jz      short loc_1801787BE
0x1801787a2  mov     rax, [rcx]
0x1801787a5  lea     rdx, [rsp+530h+var_4F0]
0x1801787aa  cmp     rcx, rdx
0x1801787ad  setnz   dl
0x1801787b0  mov     rax, [rax+20h]
0x1801787b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801787b9  mov     [rsp+530h+var_4B8], rsi
0x1801787be  test    r14, r14
0x1801787c1  jz      short loc_1801787FA
0x1801787c3  mov     rdx, rsi
0x1801787c6  mov     rcx, rdx
0x1801787c9  add     rcx, rcx
0x1801787cc  mov     [rbp+rcx*8+430h+var_460], rbx
0x1801787d1  lea     rax, [r15+1]
0x1801787d5  test    r13, r13
0x1801787d8  cmovz   rax, r15
0x1801787dc  add     rbx, rax
0x1801787df  mov     [rbp+rcx*8+430h+var_458], rbx
0x1801787e4  inc     rdx; bool
0x1801787e7  lea     rax, [r13-1]
0x1801787eb  test    r13, r13
0x1801787ee  cmovz   rax, r13
0x1801787f2  mov     r13, rax
0x1801787f5  cmp     rdx, r14
0x1801787f8  jb      short loc_1801787C6
0x1801787fa  mov     [rsp+530h+pwk], rsi
0x1801787ff  lea     r9, [rbp+430h+var_4B0]; void *
0x180178803  lea     r8, ?_ParallelForCallback@TPUtils@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)
0x18017880a  lea     rcx, [rsp+530h+pwk]; this
0x18017880f  call    ?Init@CThreadPoolWork@@QEAAX_NP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z2PEAU_TP_CALLBACK_ENVIRON_V3@@@Z; CThreadPoolWork::Init(bool,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *,_TP_CALLBACK_ENVIRON_V3 *)
0x180178814  nop
0x180178815  mov     rdx, r14; unsigned __int64
0x180178818  lea     rcx, [rsp+530h+pwk]; this
0x18017881d  call    ?SubmitThreadpoolWork@CThreadPoolWork@@QEAAX_K@Z; CThreadPoolWork::SubmitThreadpoolWork(unsigned __int64)
0x180178822  mov     edx, ebx
0x180178824  mov     rcx, r12
0x180178827  call    _lambda_400fe692df54aa0eaacf0f632abd034a___operator__
0x18017882c  inc     rbx
0x18017882f  cmp     rbx, rdi
0x180178832  jb      short loc_180178822
0x180178834  mov     [rsp+530h+var_4F7], sil
0x180178839  xor     edx, edx; fCancelPendingCallbacks
0x18017883b  mov     rcx, [rsp+530h+pwk]; pwk
0x180178840  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180178846  mov     eax, [rbp+430h+var_60]
0x18017884c  test    eax, eax
0x18017884e  jle     short loc_180178881
0x180178850  mov     rcx, [rbp+430h+var_58]; this
0x180178857  test    rcx, rcx
0x18017885a  jz      short loc_180178862
0x18017885c  call    ?raise@TPResultException@@UEAAXXZ; TPResultException::raise(void)
0x180178862  mov     rcx, [rbp+438h]; this
0x180178869  mov     r9d, 8000FFFFh; char *
0x18017886f  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180178876  mov     edx, 194h; void *
0x18017887b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180178881  lea     rcx, [rsp+530h+pwk]; this
0x180178886  call    ??1CThreadPoolWork@@QEAA@XZ; CThreadPoolWork::~CThreadPoolWork(void)
0x18017888b  nop
0x18017888c  lea     rcx, [rbp+430h+var_4B0]; this
0x180178890  call    ??1_SParallelForContext@TPUtils@@QEAA@XZ; TPUtils::_SParallelForContext::~_SParallelForContext(void)
0x180178895  jmp     short loc_1801788AE
0x180178897  test    rdi, rdi
0x18017889a  jz      short loc_1801788AE
0x18017889c  mov     edx, ebx
0x18017889e  mov     rcx, r12
0x1801788a1  call    _lambda_400fe692df54aa0eaacf0f632abd034a___operator__
0x1801788a6  add     rbx, rsi
0x1801788a9  cmp     rbx, rdi
0x1801788ac  jb      short loc_18017889C
0x1801788ae  mov     rcx, [rbp+430h+var_40]
0x1801788b5  xor     rcx, rsp; StackCookie
0x1801788b8  call    __security_check_cookie
0x1801788bd  mov     rbx, [rsp+530h+arg_0]
0x1801788c5  add     rsp, 500h
0x1801788cc  pop     r15
0x1801788ce  pop     r14
0x1801788d0  pop     r13
0x1801788d2  pop     r12
0x1801788d4  pop     rdi
0x1801788d5  pop     rsi
0x1801788d6  pop     rbp
0x1801788d7  retn
```
