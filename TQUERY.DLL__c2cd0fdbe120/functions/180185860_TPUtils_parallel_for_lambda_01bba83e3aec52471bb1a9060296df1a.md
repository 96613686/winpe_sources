# TPUtils::parallel_for__lambda_01bba83e3aec52471bb1a9060296df1a___

- ea: `0x180185860`
- end: `0x180185ade`
- name: `TPUtils::parallel_for__lambda_01bba83e3aec52471bb1a9060296df1a___`
- size: `638`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18017d9a0`

## callees

- `0x18002cc2c`
- `0x18002dc24`
- `0x180038f08`
- `0x180043ccc`
- `0x1800eaa2c`
- `0x1800ee964`
- `0x1800f2ee8`
- `0x180157c70`
- `0x180185860`
- `0x180185ae4`
- `0x180188d90`
- `0x18019c834`
- `0x180240aa4`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018592f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018593c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018592f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018593c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180185a46`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180185a46`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180185921`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180185921`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180185908`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180185908`

## string_xrefs

- `0x180185a75`: `onecoreuap\base\appmodel\Search\common\include\TPUtils.h`
- `0x18018595d`: `onecoreuap\base\appmodel\Search\common\include\PerUserCatalogResetHelper.h`

## pseudocode

```c
void __fastcall TPUtils::parallel_for__lambda_01bba83e3aec52471bb1a9060296df1a___(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3)
{
  unsigned __int64 v5; // rbx
  __int64 v6; // r8
  unsigned __int64 ProcessorCount; // r9
  char v8; // di
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // r15
  __int64 v11; // rcx
  __int64 v12; // r13
  unsigned __int64 v13; // r15
  LPVOID Value; // r14
  signed int LastError; // eax
  _BYTE *v16; // rdi
  unsigned __int64 v17; // rdx
  PTP_WORK v18; // r9
  PTP_WORK v19; // rax
  __int64 v20; // rax
  __int64 v21; // r8
  __int64 v22; // r9
  struct _TP_CALLBACK_ENVIRON_V3 *v23; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+20h] [rbp-E0h]
  PTP_WORK pwk; // [rsp+30h] [rbp-D0h] BYREF
  char v26; // [rsp+39h] [rbp-C7h]
  _BYTE v27[56]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE *v28; // [rsp+78h] [rbp-88h]
  _BYTE v29[1104]; // [rsp+80h] [rbp-80h] BYREF
  int v30; // [rsp+4D0h] [rbp+3D0h]
  TPResultException *v31; // [rsp+4D8h] [rbp+3D8h]
  wil::details::in1diag3 *retaddr; // [rsp+538h] [rbp+438h]

  v5 = 0;
  ProcessorCount = TPUtils::GetProcessorCount();
  v8 = 1;
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
      lambda_01bba83e3aec52471bb1a9060296df1a_::operator()(a3, (unsigned int)v5++, v6, ProcessorCount);
    while ( v5 < a2 );
    return;
  }
  v9 = a2 / ProcessorCount;
  v10 = a2 % ProcessorCount;
  v11 = a2 / ProcessorCount;
  if ( !(a2 / ProcessorCount) )
    v11 = 1;
  pwk = (PTP_WORK)v11;
  v12 = (a2 % ProcessorCount) & -(__int64)(v9 != 0);
  if ( v9 )
    v10 = ProcessorCount;
  v13 = v10 - 1;
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
    if ( Value || !GetLastError() )
      v8 = 0;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( v8 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\PerUserCatalogResetHelper.h",
        (const char *)(unsigned int)LastError,
        (int)v23);
  }
  v16 = (_BYTE *)std::_Global_new_std::_Func_impl_no_alloc__lambda_01bba83e3aec52471bb1a9060296df1a__void_unsigned___int64___lambda_01bba83e3aec52471bb1a9060296df1a__const___(a3);
  v28 = v16;
  TPUtils::_SParallelForContext::_SParallelForContext(v29, v27, v13, Value);
  if ( v16 )
  {
    LOBYTE(v17) = v16 != v27;
    (*(void (__fastcall **)(_BYTE *, unsigned __int64))(*(_QWORD *)v16 + 32LL))(v16, v17);
  }
  if ( v13 )
  {
    v17 = 0;
    v18 = pwk;
    do
    {
      *(_QWORD *)&v29[16 * v17 + 80] = v5;
      v19 = (PTP_WORK)((char *)v18 + 1);
      if ( !v12 )
        v19 = v18;
      v5 += (unsigned __int64)v19;
      *(_QWORD *)&v29[16 * v17++ + 88] = v5;
      v20 = v12 - 1;
      if ( !v12 )
        v20 = 0;
      v12 = v20;
    }
    while ( v17 < v13 );
  }
  pwk = 0;
  CThreadPoolWork::Init((CThreadPoolWork *)&pwk, v17, TPUtils::_ParallelForCallback, v29, v23);
  CThreadPoolWork::SubmitThreadpoolWork((CThreadPoolWork *)&pwk, v13);
  do
    lambda_01bba83e3aec52471bb1a9060296df1a_::operator()(a3, (unsigned int)v5++, v21, v22);
  while ( v5 < a2 );
  v26 = 0;
  WaitForThreadpoolWorkCallbacks(pwk, 0);
  if ( v30 > 0 )
  {
    if ( v31 )
      TPResultException::raise(v31);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x194,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\TPUtils.h",
      (const char *)0x8000FFFFLL,
      v24);
  }
  CThreadPoolWork::~CThreadPoolWork(&pwk);
  TPUtils::_SParallelForContext::~_SParallelForContext((TPUtils::_SParallelForContext *)v29);
}

```

## disassembly

```asm
0x180185860  mov     [rsp-8+arg_0], rbx
0x180185865  push    rbp
0x180185866  push    rsi
0x180185867  push    rdi
0x180185868  push    r12
0x18018586a  push    r13
0x18018586c  push    r14
0x18018586e  push    r15
0x180185870  lea     rbp, [rsp-400h]
0x180185878  sub     rsp, 500h
0x18018587f  mov     rax, cs:__security_cookie
0x180185886  xor     rax, rsp
0x180185889  mov     [rbp+430h+var_40], rax
0x180185890  mov     r12, r8
0x180185893  mov     rsi, rdx
0x180185896  xor     ebx, ebx
0x180185898  call    ?GetProcessorCount@TPUtils@@SA_KXZ; TPUtils::GetProcessorCount(void)
0x18018589d  mov     r9, rax
0x1801858a0  lea     edi, [rbx+1]
0x1801858a3  cmp     rax, rdi
0x1801858a6  jz      loc_180185A9D
0x1801858ac  cmp     rsi, rdi
0x1801858af  jbe     loc_180185A9D
0x1801858b5  mov     eax, cs:?s_runningThreadCount@TPUtils@@0JC; long volatile TPUtils::s_runningThreadCount
0x1801858bb  cmp     eax, 19h
0x1801858be  ja      loc_180185AA2
0x1801858c4  xor     edx, edx
0x1801858c6  mov     rax, rsi
0x1801858c9  div     r9
0x1801858cc  mov     r15, rdx
0x1801858cf  mov     rcx, rax
0x1801858d2  test    rax, rax
0x1801858d5  cmovz   rcx, rdi
0x1801858d9  mov     [rsp+530h+pwk], rcx
0x1801858de  mov     rcx, rax
0x1801858e1  neg     rcx
0x1801858e4  sbb     r13, r13
0x1801858e7  and     r13, rdx
0x1801858ea  test    rax, rax
0x1801858ed  cmovnz  r15, r9
0x1801858f1  sub     r15, rdi
0x1801858f4  xor     r9d, r9d; Context
0x1801858f7  xor     r8d, r8d; Parameter
0x1801858fa  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180185901  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180185908  call    cs:__imp_InitOnceExecuteOnce
0x18018590e  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, bl; bool g_isPerUserCatalogEnabled
0x180185914  jz      short loc_180185970
0x180185916  mov     ecx, cs:?g_tlsIndex@PerUserCatalogNameForCorruption@@3KA; dwTlsIndex
0x18018591c  cmp     ecx, 0FFFFFFFFh
0x18018591f  jz      short loc_180185970
0x180185921  call    cs:__imp_TlsGetValue
0x180185927  mov     r14, rax
0x18018592a  test    rax, rax
0x18018592d  jnz     short loc_180185939
0x18018592f  call    cs:__imp_GetLastError
0x180185935  test    eax, eax
0x180185937  jnz     short loc_18018593C
0x180185939  xor     dil, dil
0x18018593c  call    cs:__imp_GetLastError
0x180185942  test    eax, eax
0x180185944  jle     short loc_18018594E
0x180185946  movzx   eax, ax
0x180185949  or      eax, 80070000h
0x18018594e  mov     rcx, [rbp+438h]; this
0x180185955  test    dil, dil
0x180185958  jz      short loc_180185973
0x18018595a  mov     r9d, eax; char *
0x18018595d  lea     r8, aOnecoreuapBase_288; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180185964  mov     edx, 47h ; 'G'; void *
0x180185969  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18018596e  jmp     short loc_180185973
0x180185970  xor     r14d, r14d
0x180185973  mov     [rsp+530h+var_4B8], rbx
0x180185978  mov     rcx, r12
0x18018597b  call    std___Global_new_std___Func_impl_no_alloc__lambda_01bba83e3aec52471bb1a9060296df1a__void_unsigned___int64___lambda_01bba83e3aec52471bb1a9060296df1a__const___
0x180185980  mov     rdi, rax
0x180185983  mov     [rsp+530h+var_4B8], rax
0x180185988  mov     r9, r14
0x18018598b  mov     r8, r15
0x18018598e  lea     rdx, [rsp+530h+var_4F0]
0x180185993  lea     rcx, [rbp+430h+var_4B0]
0x180185997  call    ??0_SParallelForContext@TPUtils@@QEAA@AEBV?$function@$$A6AX_K@Z@std@@_KPEB_W@Z; TPUtils::_SParallelForContext::_SParallelForContext(std::function<void (unsigned __int64)> const &,unsigned __int64,wchar_t const *)
0x18018599c  nop
0x18018599d  test    rdi, rdi
0x1801859a0  jz      short loc_1801859BC
0x1801859a2  mov     rax, [rdi]
0x1801859a5  lea     rcx, [rsp+530h+var_4F0]
0x1801859aa  cmp     rdi, rcx
0x1801859ad  setnz   dl
0x1801859b0  mov     rcx, rdi
0x1801859b3  mov     rax, [rax+20h]
0x1801859b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801859bc  test    r15, r15
0x1801859bf  jz      short loc_1801859FC
0x1801859c1  xor     edx, edx
0x1801859c3  mov     r9, [rsp+530h+pwk]
0x1801859c8  mov     rcx, rdx
0x1801859cb  add     rcx, rcx
0x1801859ce  mov     [rbp+rcx*8+430h+var_460], rbx
0x1801859d3  lea     rax, [r9+1]
0x1801859d7  test    r13, r13
0x1801859da  cmovz   rax, r9
0x1801859de  add     rbx, rax
0x1801859e1  mov     [rbp+rcx*8+430h+var_458], rbx
0x1801859e6  inc     rdx; bool
0x1801859e9  lea     rax, [r13-1]
0x1801859ed  test    r13, r13
0x1801859f0  cmovz   rax, r13
0x1801859f4  mov     r13, rax
0x1801859f7  cmp     rdx, r15
0x1801859fa  jb      short loc_1801859C8
0x1801859fc  mov     [rsp+530h+pwk], 0
0x180185a05  lea     r9, [rbp+430h+var_4B0]; void *
0x180185a09  lea     r8, ?_ParallelForCallback@TPUtils@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)
0x180185a10  lea     rcx, [rsp+530h+pwk]; this
0x180185a15  call    ?Init@CThreadPoolWork@@QEAAX_NP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z2PEAU_TP_CALLBACK_ENVIRON_V3@@@Z; CThreadPoolWork::Init(bool,void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *,_TP_CALLBACK_ENVIRON_V3 *)
0x180185a1a  nop
0x180185a1b  mov     rdx, r15; unsigned __int64
0x180185a1e  lea     rcx, [rsp+530h+pwk]; this
0x180185a23  call    ?SubmitThreadpoolWork@CThreadPoolWork@@QEAAX_K@Z; CThreadPoolWork::SubmitThreadpoolWork(unsigned __int64)
0x180185a28  mov     edx, ebx
0x180185a2a  mov     rcx, r12
0x180185a2d  call    _lambda_01bba83e3aec52471bb1a9060296df1a___operator__
0x180185a32  inc     rbx
0x180185a35  cmp     rbx, rsi
0x180185a38  jb      short loc_180185A28
0x180185a3a  mov     [rsp+530h+var_4F7], 0
0x180185a3f  xor     edx, edx; fCancelPendingCallbacks
0x180185a41  mov     rcx, [rsp+530h+pwk]; pwk
0x180185a46  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180185a4c  mov     eax, [rbp+430h+var_60]
0x180185a52  test    eax, eax
0x180185a54  jle     short loc_180185A87
0x180185a56  mov     rcx, [rbp+430h+var_58]; this
0x180185a5d  test    rcx, rcx
0x180185a60  jz      short loc_180185A68
0x180185a62  call    ?raise@TPResultException@@UEAAXXZ; TPResultException::raise(void)
0x180185a68  mov     rcx, [rbp+438h]; this
0x180185a6f  mov     r9d, 8000FFFFh; char *
0x180185a75  lea     r8, aOnecoreuapBase_163; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180185a7c  mov     edx, 194h; void *
0x180185a81  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180185a87  lea     rcx, [rsp+530h+pwk]; this
0x180185a8c  call    ??1CThreadPoolWork@@QEAA@XZ; CThreadPoolWork::~CThreadPoolWork(void)
0x180185a91  nop
0x180185a92  lea     rcx, [rbp+430h+var_4B0]; this
0x180185a96  call    ??1_SParallelForContext@TPUtils@@QEAA@XZ; TPUtils::_SParallelForContext::~_SParallelForContext(void)
0x180185a9b  jmp     short loc_180185AB4
0x180185a9d  test    rsi, rsi
0x180185aa0  jz      short loc_180185AB4
0x180185aa2  mov     edx, ebx
0x180185aa4  mov     rcx, r12
0x180185aa7  call    _lambda_01bba83e3aec52471bb1a9060296df1a___operator__
0x180185aac  add     rbx, rdi
0x180185aaf  cmp     rbx, rsi
0x180185ab2  jb      short loc_180185AA2
0x180185ab4  mov     rcx, [rbp+430h+var_40]
0x180185abb  xor     rcx, rsp; StackCookie
0x180185abe  call    __security_check_cookie
0x180185ac3  mov     rbx, [rsp+530h+arg_0]
0x180185acb  add     rsp, 500h
0x180185ad2  pop     r15
0x180185ad4  pop     r14
0x180185ad6  pop     r13
0x180185ad8  pop     r12
0x180185ada  pop     rdi
0x180185adb  pop     rsi
0x180185adc  pop     rbp
0x180185add  retn
```
