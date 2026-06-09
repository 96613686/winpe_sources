# TPUtils::parallel_for__lambda_8fb44b1675b6f5f94f7a5f9c60fc5019___

- ea: `0x18017dcf0`
- end: `0x18017df8e`
- name: `TPUtils::parallel_for__lambda_8fb44b1675b6f5f94f7a5f9c60fc5019___`
- size: `670`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18017b5a0`

## callees

- `0x18002cc2c`
- `0x18002dc24`
- `0x180038f08`
- `0x180043ccc`
- `0x1800eaa2c`
- `0x1800ee964`
- `0x1800f2ee8`
- `0x180157c70`
- `0x18017dcf0`
- `0x180188d90`
- `0x18019c834`
- `0x180239048`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017ddbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017ddd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017ddbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017ddd1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18017def6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18017def6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18017ddb1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18017ddb1`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18017dd98`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18017dd98`

## string_xrefs

- `0x18017df25`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`
- `0x18017ddf2`: `onecoreuap\base\appmodel\Search\common\include\PerUserCatalogResetHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall TPUtils::parallel_for__lambda_8fb44b1675b6f5f94f7a5f9c60fc5019___(
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
  __int128 v26; // [rsp+58h] [rbp-A8h]
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
      lambda_8fb44b1675b6f5f94f7a5f9c60fc5019_::operator()(a3, (unsigned int)v5++, ProcessorCount);
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
  v24 = off_1802C8A90;
  v25 = *a3;
  v26 = a3[1];
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
    lambda_8fb44b1675b6f5f94f7a5f9c60fc5019_::operator()(a3, (unsigned int)v5++, v19);
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
0x18017dcf0  mov     [rsp-8+arg_0], rbx
0x18017dcf5  push    rbp
0x18017dcf6  push    rsi
0x18017dcf7  push    rdi
0x18017dcf8  push    r12
0x18017dcfa  push    r13
0x18017dcfc  push    r14
0x18017dcfe  push    r15
0x18017dd00  lea     rbp, [rsp-400h]
0x18017dd08  sub     rsp, 500h
0x18017dd0f  mov     rax, cs:__security_cookie
0x18017dd16  xor     rax, rsp
0x18017dd19  mov     [rbp+430h+var_40], rax
0x18017dd20  mov     r12, r8
0x18017dd23  mov     rdi, rdx
0x18017dd26  xor     ebx, ebx
0x18017dd28  call    ?GetProcessorCount@TPUtils@@SA_KXZ; TPUtils::GetProcessorCount(void)
0x18017dd2d  mov     r8, rax
0x18017dd30  lea     esi, [rbx+1]
0x18017dd33  cmp     rax, rsi
0x18017dd36  jz      loc_18017DF4D
0x18017dd3c  cmp     rdi, rsi
0x18017dd3f  jbe     loc_18017DF4D
0x18017dd45  mov     eax, cs:?s_runningThreadCount@TPUtils@@0JC; long volatile TPUtils::s_runningThreadCount
0x18017dd4b  cmp     eax, 19h
0x18017dd4e  ja      loc_18017DF52
0x18017dd54  xor     edx, edx
0x18017dd56  mov     rax, rdi
0x18017dd59  div     r8
0x18017dd5c  mov     r14, rdx
0x18017dd5f  mov     r15, rax
0x18017dd62  test    rax, rax
0x18017dd65  cmovz   r15, rsi
0x18017dd69  mov     [rsp+530h+pwk], r15
0x18017dd6e  mov     rcx, rax
0x18017dd71  neg     rcx
0x18017dd74  sbb     r13, r13
0x18017dd77  and     r13, rdx
0x18017dd7a  test    rax, rax
0x18017dd7d  cmovnz  r14, r8
0x18017dd81  sub     r14, rsi
0x18017dd84  xor     r9d, r9d; Context
0x18017dd87  xor     r8d, r8d; Parameter
0x18017dd8a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18017dd91  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18017dd98  call    cs:__imp_InitOnceExecuteOnce
0x18017dd9e  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, bl; bool g_isPerUserCatalogEnabled
0x18017dda4  jz      short loc_18017DE0A
0x18017dda6  mov     ecx, cs:?g_tlsIndex@PerUserCatalogNameForCorruption@@3KA; dwTlsIndex
0x18017ddac  cmp     ecx, 0FFFFFFFFh
0x18017ddaf  jz      short loc_18017DE0A
0x18017ddb1  call    cs:__imp_TlsGetValue
0x18017ddb7  mov     rsi, rax
0x18017ddba  test    rax, rax
0x18017ddbd  jnz     short loc_18017DDCE
0x18017ddbf  call    cs:__imp_GetLastError
0x18017ddc5  test    eax, eax
0x18017ddc7  jz      short loc_18017DDCE
0x18017ddc9  mov     r15b, 1
0x18017ddcc  jmp     short loc_18017DDD1
0x18017ddce  xor     r15b, r15b
0x18017ddd1  call    cs:__imp_GetLastError
0x18017ddd7  test    eax, eax
0x18017ddd9  jle     short loc_18017DDE3
0x18017dddb  movzx   eax, ax
0x18017ddde  or      eax, 80070000h
0x18017dde3  mov     rcx, [rbp+438h]; this
0x18017ddea  test    r15b, r15b
0x18017dded  jz      short loc_18017DE03
0x18017ddef  mov     r9d, eax; char *
0x18017ddf2  lea     r8, aOnecoreuapBase_288; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18017ddf9  mov     edx, 47h ; 'G'; void *
0x18017ddfe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18017de03  mov     r15, [rsp+530h+pwk]
0x18017de08  jmp     short loc_18017DE0C
0x18017de0a  xor     esi, esi
0x18017de0c  lea     rax, off_1802C8A90
0x18017de13  mov     [rsp+530h+var_4F0], rax
0x18017de18  movups  xmm0, xmmword ptr [r12]
0x18017de1d  movups  [rsp+530h+var_4E8], xmm0
0x18017de22  movups  xmm1, xmmword ptr [r12+10h]
0x18017de28  movups  [rsp+530h+var_4D8], xmm1
0x18017de2d  lea     rax, [rsp+530h+var_4F0]
0x18017de32  mov     [rsp+530h+var_4B8], rax
0x18017de37  mov     r9, rsi
0x18017de3a  mov     r8, r14
0x18017de3d  lea     rdx, [rsp+530h+var_4F0]
0x18017de42  lea     rcx, [rbp+430h+var_4B0]
0x18017de46  call    ??0_SParallelForContext@TPUtils@@QEAA@AEBV?$function@$$A6AX_K@Z@std@@_KPEB_W@Z; TPUtils::_SParallelForContext::_SParallelForContext(std::function<void (unsigned __int64)> const &,unsigned __int64,wchar_t const *)
0x18017de4b  nop
0x18017de4c  mov     rcx, [rsp+530h+var_4B8]
0x18017de51  xor     esi, esi
0x18017de53  test    rcx, rcx
0x18017de56  jz      short loc_18017DE74
0x18017de58  mov     rax, [rcx]
0x18017de5b  lea     rdx, [rsp+530h+var_4F0]
0x18017de60  cmp     rcx, rdx
0x18017de63  setnz   dl
0x18017de66  mov     rax, [rax+20h]
0x18017de6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017de6f  mov     [rsp+530h+var_4B8], rsi
0x18017de74  test    r14, r14
0x18017de77  jz      short loc_18017DEB0
0x18017de79  mov     rdx, rsi
0x18017de7c  mov     rcx, rdx
0x18017de7f  add     rcx, rcx
0x18017de82  mov     [rbp+rcx*8+430h+var_460], rbx
0x18017de87  lea     rax, [r15+1]
0x18017de8b  test    r13, r13
0x18017de8e  cmovz   rax, r15
0x18017de92  add     rbx, rax
0x18017de95  mov     [rbp+rcx*8+430h+var_458], rbx
0x18017de9a  inc     rdx; bool
0x18017de9d  lea     rax, [r13-1]
0x18017dea1  test    r13, r13
0x18017dea4  cmovz   rax, r13
0x18017dea8  mov     r13, rax
0x18017deab  cmp     rdx, r14
0x18017deae  jb      short loc_18017DE7C
0x18017deb0  mov     [rsp+530h+pwk], rsi
0x18017deb5  lea     r9, [rbp+430h+var_4B0]; void *
0x18017deb9  lea     r8, ?_ParallelForCallback@TPUtils@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)
0x18017dec0  lea     rcx, [rsp+530h+pwk]; this
0x18017dec5  call    ?Init@CThreadPoolWork@@QEAAX_NP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z2PEAU_TP_CALLBACK_ENVIRON_V3@@@Z; CThreadPoolWork::Init(bool,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *,_TP_CALLBACK_ENVIRON_V3 *)
0x18017deca  nop
0x18017decb  mov     rdx, r14; unsigned __int64
0x18017dece  lea     rcx, [rsp+530h+pwk]; this
0x18017ded3  call    ?SubmitThreadpoolWork@CThreadPoolWork@@QEAAX_K@Z; CThreadPoolWork::SubmitThreadpoolWork(unsigned __int64)
0x18017ded8  mov     edx, ebx
0x18017deda  mov     rcx, r12
0x18017dedd  call    _lambda_8fb44b1675b6f5f94f7a5f9c60fc5019___operator__
0x18017dee2  inc     rbx
0x18017dee5  cmp     rbx, rdi
0x18017dee8  jb      short loc_18017DED8
0x18017deea  mov     [rsp+530h+var_4F7], sil
0x18017deef  xor     edx, edx; fCancelPendingCallbacks
0x18017def1  mov     rcx, [rsp+530h+pwk]; pwk
0x18017def6  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18017defc  mov     eax, [rbp+430h+var_60]
0x18017df02  test    eax, eax
0x18017df04  jle     short loc_18017DF37
0x18017df06  mov     rcx, [rbp+430h+var_58]; this
0x18017df0d  test    rcx, rcx
0x18017df10  jz      short loc_18017DF18
0x18017df12  call    ?raise@TPResultException@@UEAAXXZ; TPResultException::raise(void)
0x18017df18  mov     rcx, [rbp+438h]; this
0x18017df1f  mov     r9d, 8000FFFFh; char *
0x18017df25  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18017df2c  mov     edx, 194h; void *
0x18017df31  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017df37  lea     rcx, [rsp+530h+pwk]; this
0x18017df3c  call    ??1CThreadPoolWork@@QEAA@XZ; CThreadPoolWork::~CThreadPoolWork(void)
0x18017df41  nop
0x18017df42  lea     rcx, [rbp+430h+var_4B0]; this
0x18017df46  call    ??1_SParallelForContext@TPUtils@@QEAA@XZ; TPUtils::_SParallelForContext::~_SParallelForContext(void)
0x18017df4b  jmp     short loc_18017DF64
0x18017df4d  test    rdi, rdi
0x18017df50  jz      short loc_18017DF64
0x18017df52  mov     edx, ebx
0x18017df54  mov     rcx, r12
0x18017df57  call    _lambda_8fb44b1675b6f5f94f7a5f9c60fc5019___operator__
0x18017df5c  add     rbx, rsi
0x18017df5f  cmp     rbx, rdi
0x18017df62  jb      short loc_18017DF52
0x18017df64  mov     rcx, [rbp+430h+var_40]
0x18017df6b  xor     rcx, rsp; StackCookie
0x18017df6e  call    __security_check_cookie
0x18017df73  mov     rbx, [rsp+530h+arg_0]
0x18017df7b  add     rsp, 500h
0x18017df82  pop     r15
0x18017df84  pop     r14
0x18017df86  pop     r13
0x18017df88  pop     r12
0x18017df8a  pop     rdi
0x18017df8b  pop     rsi
0x18017df8c  pop     rbp
0x18017df8d  retn
```
