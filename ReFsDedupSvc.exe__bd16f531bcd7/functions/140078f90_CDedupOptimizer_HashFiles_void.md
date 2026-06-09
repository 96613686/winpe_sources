# CDedupOptimizer::HashFiles(void)

- ea: `0x140078f90`
- end: `0x1400792b9`
- name: `?HashFiles@CDedupOptimizer@@AEAAKXZ`
- size: `809`
- prototype: `unsigned int __fastcall(CDedupOptimizer *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x14007a6fc`

## callees

- `0x14000dea0`
- `0x140019600`
- `0x14001c194`
- `0x140029c1c`
- `0x140032398`
- `0x140062c28`
- `0x1400635dc`
- `0x140063a2c`
- `0x14006c56c`
- `0x14007356c`
- `0x140073644`
- `0x140073b70`
- `0x140074378`
- `0x140075e50`
- `0x140076078`
- `0x140076940`
- `0x140078c9c`
- `0x140078f90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140079220`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140079257`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140079220`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140079257`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140079185`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140079185`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007907d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400790e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007907d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400790e5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400790af`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400790af`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x140079043`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x140079043`

## string_xrefs

- `0x1400790f8`: `Couldn't create worker thread, error = 0x%x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDedupOptimizer::HashFiles(CDedupOptimizer *this)
{
  DWORD LastError; // ebx
  HANDLE v3; // r14
  __int64 v4; // r15
  unsigned int v5; // eax
  void *v6; // rdx
  unsigned int v7; // esi
  int v8; // eax
  __int64 v9; // rdx
  const wchar_t *v10; // rax
  CDedupOptimizer *v12; // [rsp+30h] [rbp-18h] BYREF
  char v13; // [rsp+38h] [rbp-10h]
  double v14; // [rsp+80h] [rbp+38h] BYREF
  HANDLE hHandle; // [rsp+88h] [rbp+40h] BYREF
  unsigned __int64 v16; // [rsp+90h] [rbp+48h] BYREF
  __int64 v17; // [rsp+98h] [rbp+50h] BYREF

  hHandle = 0;
  v17 = -1;
  v16 = 0;
  v14 = COERCE_DOUBLE(std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 128));
  if ( *((_BYTE *)this + 16) )
  {
    DedupUtil::Print<unsigned short const *>(0, L"Optimizing files on %s...\n", &v14);
    if ( !(unsigned __int8)CDedupOptimizer::UpdateState(this, 5) )
    {
      if ( *((_DWORD *)this + 102) == 3 )
        LastError = 1223;
      else
        LastError = 170;
      goto LABEL_26;
    }
  }
  else
  {
    DedupUtil::Print<unsigned short const *>(0, L"Estimating space savings on %s...\n", &v14);
  }
  if ( !*((_QWORD *)this + 117) )
  {
LABEL_8:
    LastError = 0;
    goto LABEL_26;
  }
  *((_BYTE *)this + 921) = 1;
  v14 = COERCE_DOUBLE(CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 1u));
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    (char *)this + 296,
    &v14);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v14);
  if ( ((*((_QWORD *)this + 37) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    goto LABEL_26;
  }
  v14 = COERCE_DOUBLE(CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CDedupOptimizer::ReadFileCompletionWorker, this, 0, 0));
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    &hHandle,
    &v14);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v14);
  v3 = hHandle;
  if ( (((unsigned __int64)hHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LODWORD(v14) = GetLastError();
    DedupUtil::Print<unsigned long &>(6, L"Couldn't create worker thread, error = 0x%x\n", &v14);
    LastError = LODWORD(v14);
    goto LABEL_26;
  }
  v12 = this;
  v13 = 1;
  v4 = *(_QWORD *)std::chrono::steady_clock::now(&v14);
  v14 = *(double *)&this;
  v5 = CHashIndex::ForEachProcessedCandidate__CDedupOptimizer::HashFiles_::_2_::_lambda_2___(
         *((_QWORD *)this + 29),
         &v14);
  v7 = v5;
  if ( v5 != 1223 )
  {
    if ( v5 > 0x15 || (v8 = 2629632, !_bittest(&v8, v7)) )
    {
      if ( v7 != 112 && v7 != 1462 )
      {
        *((_BYTE *)this + 921) = 0;
        CDedupOptimizer::CheckForScanComplete(this);
        WaitForSingleObject(v3, 0xFFFFFFFF);
        if ( !CDedupOptimizer::GetTotalSharedBytes(this, &v16) )
          _InterlockedExchange64((volatile __int64 *)this + 131, v16);
        v14 = (double)(int)(*(_QWORD *)std::chrono::steady_clock::now(&v14) - v4) / 6.0e10;
        v10 = L"Optimization";
        if ( !*((_BYTE *)this + 16) )
          v10 = L"Estimation";
        v16 = (unsigned __int64)v10;
        DedupUtil::Print<unsigned short const *,double>((__int64)L"Estimation", v9, &v16, &v14);
        v13 = 0;
        CDedupOptimizer::HashFiles_::_2_::_lambda_1_::operator()(&v12);
        goto LABEL_8;
      }
    }
  }
  wil::details::SetEvent(*((wil::details **)this + 54), v6);
  AcquireSRWLockExclusive((PSRWLOCK)this + 76);
  *(_QWORD *)&v14 = (char *)this + 608;
  if ( *((_QWORD *)this + 85) )
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
      &v14,
      0);
    _wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
      (char *)this + 728,
      0xFFFFFFFFLL);
    AcquireSRWLockExclusive((PSRWLOCK)this + 76);
    v16 = (unsigned __int64)this + 608;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(
      &v14,
      &v16);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
  v13 = 0;
  CDedupOptimizer::HashFiles_::_2_::_lambda_1_::operator()(&v12);
  LastError = v7;
LABEL_26:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hHandle);
  return LastError;
}

```

## disassembly

```asm
0x140078f90  push    rbp
0x140078f92  push    rbx
0x140078f93  push    rsi
0x140078f94  push    rdi
0x140078f95  push    r14
0x140078f97  push    r15
0x140078f99  mov     rbp, rsp
0x140078f9c  sub     rsp, 48h
0x140078fa0  mov     rdi, rcx
0x140078fa3  mov     [rbp+hHandle], 0
0x140078fab  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140078faf  mov     [rbp+arg_18], rbx
0x140078fb3  mov     [rbp+arg_10], 0
0x140078fbb  sub     rcx, 0FFFFFFFFFFFFFF80h
0x140078fbf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140078fc4  mov     [rbp+arg_0], rax
0x140078fc8  lea     r8, [rbp+arg_0]
0x140078fcc  xor     ecx, ecx
0x140078fce  cmp     [rdi+10h], cl
0x140078fd1  jz      short loc_14007900E
0x140078fd3  lea     rdx, aOptimizingFile; "Optimizing files on %s...\n"
0x140078fda  call    ??$Print@PEBG@DedupUtil@@YAXW4MessageType@0@PEBG$$QEAPEBG@Z; DedupUtil::Print<ushort const *>(DedupUtil::MessageType,ushort const *,ushort const * &&)
0x140078fdf  lea     edx, [rbx+6]
0x140078fe2  mov     rcx, rdi
0x140078fe5  call    ?UpdateState@CDedupOptimizer@@AEAA_NW4OptimizerState@RefsDedup@@@Z; CDedupOptimizer::UpdateState(RefsDedup::OptimizerState)
0x140078fea  test    al, al
0x140078fec  jnz     short loc_14007901A
0x140078fee  mov     eax, [rdi+198h]
0x140078ff4  nop
0x140078ff5  cmp     eax, 3
0x140078ff8  jnz     short loc_140079004
0x140078ffa  mov     ebx, 4C7h
0x140078fff  jmp     loc_140079296
0x140079004  mov     ebx, 0AAh
0x140079009  jmp     loc_140079296
0x14007900e  lea     rdx, aEstimatingSpac; "Estimating space savings on %s...\n"
0x140079015  call    ??$Print@PEBG@DedupUtil@@YAXW4MessageType@0@PEBG$$QEAPEBG@Z; DedupUtil::Print<ushort const *>(DedupUtil::MessageType,ushort const *,ushort const * &&)
0x14007901a  mov     rax, [rdi+3A8h]
0x140079021  nop
0x140079022  test    rax, rax
0x140079025  jnz     short loc_14007902E
0x140079027  xor     ebx, ebx
0x140079029  jmp     loc_140079296
0x14007902e  mov     byte ptr [rdi+399h], 1
0x140079035  mov     r9d, 1; NumberOfConcurrentThreads
0x14007903b  xor     r8d, r8d; CompletionKey
0x14007903e  xor     edx, edx; ExistingCompletionPort
0x140079040  mov     rcx, rbx; FileHandle
0x140079043  call    cs:__imp_CreateIoCompletionPort
0x14007904a  nop     dword ptr [rax+rax+00h]
0x14007904f  mov     [rbp+arg_0], rax
0x140079053  lea     rbx, [rdi+128h]
0x14007905a  lea     rdx, [rbp+arg_0]
0x14007905e  mov     rcx, rbx
0x140079061  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x140079066  lea     rcx, [rbp+arg_0]
0x14007906a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14007906f  mov     rax, [rbx]
0x140079072  inc     rax
0x140079075  test    rax, 0FFFFFFFFFFFFFFFEh
0x14007907b  jnz     short loc_140079090
0x14007907d  call    cs:__imp_GetLastError
0x140079084  nop     dword ptr [rax+rax+00h]
0x140079089  mov     ebx, eax
0x14007908b  jmp     loc_140079296
0x140079090  mov     [rsp+48h+lpThreadId], 0; lpThreadId
0x140079099  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x1400790a1  mov     r9, rdi; lpParameter
0x1400790a4  lea     r8, ?ReadFileCompletionWorker@CDedupOptimizer@@CAKPEAX@Z; lpStartAddress
0x1400790ab  xor     edx, edx; dwStackSize
0x1400790ad  xor     ecx, ecx; lpThreadAttributes
0x1400790af  call    cs:__imp_CreateThread
0x1400790b6  nop     dword ptr [rax+rax+00h]
0x1400790bb  mov     [rbp+arg_0], rax
0x1400790bf  lea     rdx, [rbp+arg_0]
0x1400790c3  lea     rcx, [rbp+hHandle]
0x1400790c7  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1400790cc  lea     rcx, [rbp+arg_0]
0x1400790d0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400790d5  mov     r14, [rbp+hHandle]
0x1400790d9  lea     rax, [r14+1]
0x1400790dd  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400790e3  jnz     short loc_140079111
0x1400790e5  call    cs:__imp_GetLastError
0x1400790ec  nop     dword ptr [rax+rax+00h]
0x1400790f1  mov     dword ptr [rbp+arg_0], eax
0x1400790f4  lea     r8, [rbp+arg_0]
0x1400790f8  lea     rdx, aCouldnTCreateW; "Couldn't create worker thread, error = "...
0x1400790ff  mov     ecx, 6
0x140079104  call    ??$Print@AEAK@DedupUtil@@YAXW4MessageType@0@PEBGAEAK@Z; DedupUtil::Print<ulong &>(DedupUtil::MessageType,ushort const *,ulong &)
0x140079109  mov     ebx, dword ptr [rbp+arg_0]
0x14007910c  jmp     loc_140079296
0x140079111  mov     [rbp+var_18], rdi
0x140079115  mov     [rbp+var_10], 1
0x140079119  lea     rcx, [rbp+arg_0]
0x14007911d  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x140079122  mov     r15, [rax]
0x140079125  mov     [rbp+arg_0], rdi
0x140079129  lea     rdx, [rbp+arg_0]
0x14007912d  mov     rcx, [rdi+0E8h]
0x140079134  call    CHashIndex__ForEachProcessedCandidate__CDedupOptimizer__HashFiles____2____lambda_2___
0x140079139  mov     esi, eax
0x14007913b  mov     ebx, 4C7h
0x140079140  cmp     eax, ebx
0x140079142  jz      loc_14007920A
0x140079148  cmp     eax, 15h
0x14007914b  ja      short loc_14007915B
0x14007914d  mov     eax, 282000h
0x140079152  bt      eax, esi
0x140079155  jb      loc_14007920A
0x14007915b  cmp     esi, 70h ; 'p'
0x14007915e  jz      loc_14007920A
0x140079164  cmp     esi, 5B6h
0x14007916a  jz      loc_14007920A
0x140079170  mov     byte ptr [rdi+399h], 0
0x140079177  mov     rcx, rdi; this
0x14007917a  call    ?CheckForScanComplete@CDedupOptimizer@@AEAAXXZ; CDedupOptimizer::CheckForScanComplete(void)
0x14007917f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140079182  mov     rcx, r14; hHandle
0x140079185  call    cs:__imp_WaitForSingleObject
0x14007918c  nop     dword ptr [rax+rax+00h]
0x140079191  lea     rdx, [rbp+arg_10]; unsigned __int64 *
0x140079195  mov     rcx, rdi; this
0x140079198  call    ?GetTotalSharedBytes@CDedupOptimizer@@AEAAKAEA_K@Z; CDedupOptimizer::GetTotalSharedBytes(unsigned __int64 &)
0x14007919d  test    eax, eax
0x14007919f  jnz     short loc_1400791AC
0x1400791a1  mov     rax, [rbp+arg_10]
0x1400791a5  xchg    rax, [rdi+418h]
0x1400791ac  lea     rcx, [rbp+arg_0]
0x1400791b0  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x1400791b5  mov     rcx, [rax]
0x1400791b8  sub     rcx, r15
0x1400791bb  xorps   xmm0, xmm0
0x1400791be  cvtsi2sd xmm0, rcx
0x1400791c3  divsd   xmm0, cs:__real@422bf08eb0000000
0x1400791cb  movsd   [rbp+arg_0], xmm0
0x1400791d0  lea     rcx, aEstimation; "Estimation"
0x1400791d7  lea     rax, aOptimization; "Optimization"
0x1400791de  cmp     byte ptr [rdi+10h], 0
0x1400791e2  cmovz   rax, rcx
0x1400791e6  mov     [rbp+arg_10], rax
0x1400791ea  lea     r9, [rbp+arg_0]
0x1400791ee  lea     r8, [rbp+arg_10]
0x1400791f2  call    ??$Print@PEBGN@DedupUtil@@YAXW4MessageType@0@PEBG$$QEAPEBG$$QEAN@Z; DedupUtil::Print<ushort const *,double>(DedupUtil::MessageType,ushort const *,ushort const * &&,double &&)
0x1400791f7  nop
0x1400791f8  mov     [rbp+var_10], 0
0x1400791fc  lea     rcx, [rbp+var_18]
0x140079200  call    _CDedupOptimizer__HashFiles____2____lambda_1___operator__
0x140079205  jmp     loc_140079027
0x14007920a  mov     rcx, [rdi+1B0h]; this
0x140079211  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x140079216  lea     rbx, [rdi+260h]
0x14007921d  mov     rcx, rbx; SRWLock
0x140079220  call    cs:__imp_AcquireSRWLockExclusive
0x140079227  nop     dword ptr [rax+rax+00h]
0x14007922c  mov     [rbp+arg_0], rbx
0x140079230  cmp     qword ptr [rdi+2A8h], 0
0x140079238  jz      short loc_14007927D
0x14007923a  xor     edx, edx
0x14007923c  lea     rcx, [rbp+arg_0]
0x140079240  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x140079245  lea     rcx, [rdi+2D8h]
0x14007924c  or      edx, 0FFFFFFFFh
0x14007924f  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NKH@Z
0x140079254  mov     rcx, rbx; SRWLock
0x140079257  call    cs:__imp_AcquireSRWLockExclusive
0x14007925e  nop     dword ptr [rax+rax+00h]
0x140079263  mov     [rbp+arg_10], rbx
0x140079267  lea     rdx, [rbp+arg_10]
0x14007926b  lea     rcx, [rbp+arg_0]
0x14007926f  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> &&)
0x140079274  lea     rcx, [rbp+arg_10]
0x140079278  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14007927d  lea     rcx, [rbp+arg_0]
0x140079281  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140079286  nop
0x140079287  mov     [rbp+var_10], 0
0x14007928b  lea     rcx, [rbp+var_18]
0x14007928f  call    _CDedupOptimizer__HashFiles____2____lambda_1___operator__
0x140079294  mov     ebx, esi
0x140079296  lea     rcx, [rbp+arg_18]
0x14007929a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14007929f  nop
0x1400792a0  lea     rcx, [rbp+hHandle]
0x1400792a4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400792a9  mov     eax, ebx
0x1400792ab  add     rsp, 48h
0x1400792af  pop     r15
0x1400792b1  pop     r14
0x1400792b3  pop     rdi
0x1400792b4  pop     rsi
0x1400792b5  pop     rbx
0x1400792b6  pop     rbp
0x1400792b7  retn
```
