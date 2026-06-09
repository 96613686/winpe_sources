# _lambda_1e8ca78bb1a037ad4a3196a6ee977c51_::operator()

- ea: `0x1401006e0`
- end: `0x140100c02`
- name: `_lambda_1e8ca78bb1a037ad4a3196a6ee977c51_::operator()`
- size: `1314`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14027e8a0`

## callees

- `0x1400315a8`
- `0x140031c88`
- `0x140031ccc`
- `0x140043c78`
- `0x14006af38`
- `0x1400764a4`
- `0x14007a72c`
- `0x14009f9ec`
- `0x1400ca820`
- `0x1400e1944`
- `0x1401006e0`
- `0x140101a98`
- `0x140132940`
- `0x1401335fc`
- `0x140281188`
- `0x140282e3c`
- `0x140283890`
- `0x140283ddc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401007f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401008ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401007f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401008ba`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14010082a`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140100b0d`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140100b87`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14010082a`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140100b0d`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140100b87`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x140100995`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x140100995`

## pseudocode

```c
__int64 __fastcall lambda_1e8ca78bb1a037ad4a3196a6ee977c51_::operator()(__int64 a1, __int64 *a2)
{
  __int64 v2; // rax
  __int64 *v4; // rsi
  _QWORD *v5; // r14
  int *v6; // r15
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 *v9; // rbx
  char v10; // dl
  int v11; // r12d
  _QWORD *v12; // rax
  const char *v13; // r9
  unsigned int v14; // ebx
  const struct Vml::VmPerfTraceOperation *v15; // rbx
  __int64 v16; // rbx
  __int64 v17; // rax
  int v18; // ebx
  _QWORD *v20; // rcx
  _QWORD *i; // rax
  int v22; // [rsp+20h] [rbp-3D8h]
  char v23; // [rsp+30h] [rbp-3C8h]
  char v24; // [rsp+31h] [rbp-3C7h]
  char v25[6]; // [rsp+32h] [rbp-3C6h] BYREF
  int v26[2]; // [rsp+38h] [rbp-3C0h] BYREF
  int v27; // [rsp+40h] [rbp-3B8h]
  _QWORD *v28; // [rsp+48h] [rbp-3B0h] BYREF
  unsigned int v29; // [rsp+50h] [rbp-3A8h]
  __int64 *v30; // [rsp+58h] [rbp-3A0h]
  char v31; // [rsp+60h] [rbp-398h]
  int *v32; // [rsp+70h] [rbp-388h]
  _QWORD *v33; // [rsp+78h] [rbp-380h]
  _BYTE v34[40]; // [rsp+80h] [rbp-378h] BYREF
  _BYTE v35[64]; // [rsp+A8h] [rbp-350h] BYREF
  __int64 v36; // [rsp+E8h] [rbp-310h]
  _BYTE v37[112]; // [rsp+F0h] [rbp-308h] BYREF
  _BYTE v38[40]; // [rsp+160h] [rbp-298h] BYREF
  _BYTE v39[72]; // [rsp+188h] [rbp-270h] BYREF
  __int64 v40; // [rsp+1D0h] [rbp-228h] BYREF
  __int128 v41; // [rsp+1D8h] [rbp-220h]
  _BYTE v42[40]; // [rsp+1F0h] [rbp-208h] BYREF
  _BYTE v43[72]; // [rsp+218h] [rbp-1E0h] BYREF
  _BYTE v44[336]; // [rsp+260h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+0h]

  v27 = 0;
  v41 = *(_OWORD *)(a2 + 1);
  v2 = *a2;
  v40 = v2;
  if ( !v2 )
    return 2147549183LL;
  v29 = 0;
  _InterlockedAdd((volatile signed __int32 *)(v2 + 40), 1u);
  v30 = &v40;
  v31 = 1;
  memset_0(v44, 0, sizeof(v44));
  VmPerf::StartRelatedActivity_VmWorkerTrace::VDevWorkerThread__GUID___((VmWorkerTrace::VDevWorkerThread *)v44);
  Vml::VmPerfTraceOperation::VmPerfTraceOperation(
    (Vml::VmPerfTraceOperation *)v42,
    *(struct Vml::VmPerfTraceComponent **)(v40 + 16),
    (const struct _GUID *)(v40 + 96),
    (const struct _GUID *)(v40 + 80));
  v4 = 0;
  v5 = (_QWORD *)*((_QWORD *)&v41 + 1);
  v6 = (int *)v41;
  while ( 1 )
  {
    v25[0] = 0;
    v23 = 0;
    while ( 1 )
    {
      *(_QWORD *)v26 = 0;
      wil::AcquireSRWLockExclusive(v26, v40 + 64);
      v7 = v40;
      if ( !*(_DWORD *)(v40 + 32) )
      {
        *(_DWORD *)(v40 + 32) = GetCurrentThreadId();
        v7 = v40;
      }
      v8 = v40;
      if ( *(_BYTE *)(v7 + 8) )
        goto LABEL_8;
      v9 = **(__int64 ***)(v40 + 56);
      v10 = 0;
LABEL_10:
      v24 = v10;
      while ( 1 )
      {
        v9 = (__int64 *)*v9;
        if ( v9 == **(__int64 ***)(v8 + 56) )
          break;
        if ( *((_DWORD *)v9 + 13) )
        {
          v10 = 1;
          goto LABEL_10;
        }
        if ( !*((_BYTE *)v9 + 63) )
        {
          v23 = 1;
          if ( !*(_DWORD *)(v8 + 112) || (*(_DWORD *)(v8 + 112) & (_DWORD)v9[7]) != *(_DWORD *)(v8 + 112) )
            goto LABEL_21;
          if ( !*(_DWORD *)(v8 + 32) || (v11 = *(_DWORD *)(v8 + 32), v11 == GetCurrentThreadId()) )
          {
            v25[0] = 1;
LABEL_21:
            v12 = (_QWORD *)(v9[2] + 64);
            if ( *(_QWORD *)(v9[2] + 88) > 7u )
              v12 = (_QWORD *)*v12;
            v28 = v12;
            VmWorkerTrace::FoundNodeToProcess<unsigned short const *,bool &>(&v28, v25);
            v4 = v9;
            *((_BYTE *)v9 + 63) = 1;
            v8 = v40;
            v10 = v24;
            break;
          }
          v23 = 0;
          v8 = v40;
          v10 = v24;
        }
      }
      if ( !v10 || v23 )
        break;
      _InterlockedDecrement((volatile signed __int32 *)(v8 + 40));
      if ( !*(_DWORD *)(v40 + 40) )
      {
        _InterlockedExchange((volatile __int32 *)(v40 + 28), -2147023765);
        ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::TraceDeviceGraph(v40);
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x100,
          (unsigned int)"onecore\\vm\\worker\\vmb\\ParallelVDevTransitionOrchestrator.h",
          v13);
      }
      SleepConditionVariableSRW((PCONDITION_VARIABLE)(v40 + 72), (PSRWLOCK)(v40 + 64), 0xFFFFFFFF, 0);
      _InterlockedAdd((volatile signed __int32 *)(v40 + 40), 1u);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v26);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v26);
    if ( !v23 )
      break;
    v28 = (_QWORD *)v4[2];
    v15 = (const struct Vml::VmPerfTraceOperation *)std::make_tuple<VirtualDeviceInformation *,Vml::VmPerfTraceOperation &>(
                                                      v38,
                                                      &v28,
                                                      v42);
    v32 = v6;
    v33 = v5;
    Vml::VmPerfTraceOperation::VmPerfTraceOperation((Vml::VmPerfTraceOperation *)v34, v15);
    v36 = *((_QWORD *)v15 + 13);
    v16 = v40;
    v26[0] = *v32;
    v28 = (_QWORD *)*v33;
    v17 = Vml::VmPerfTraceOperation::VmPerfTraceOperation(
            (Vml::VmPerfTraceOperation *)v37,
            (const struct Vml::VmPerfTraceOperation *)v34);
    v22 = v26[0];
    v18 = lambda_471742be78fc95ffa3bd838ab9f364e1_::operator()(v16 + 48, v36, v17, v28);
    std::wstring::_Tidy_deallocate(v35);
    std::wstring::_Tidy_deallocate(v39);
    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::SetResult(v40, (unsigned int)v18);
    if ( v18 < 0 && *(_BYTE *)(v40 + 9) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11E,
        (unsigned int)"onecore\\vm\\worker\\vmb\\ParallelVDevTransitionOrchestrator.h",
        (const char *)(unsigned int)v18,
        v22);
    *(_QWORD *)v26 = 0;
    wil::AcquireSRWLockExclusive(v26, v40 + 64);
    if ( *(_BYTE *)(v40 + 8) )
    {
LABEL_8:
      WakeAllConditionVariable((PCONDITION_VARIABLE)(v40 + 72));
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v26);
      std::wstring::_Tidy_deallocate(v43);
      VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread((VmWorkerTrace::VDevWorkerThread *)v44);
      v31 = 0;
      _InterlockedDecrement((volatile signed __int32 *)(v40 + 40));
      return 0xFFFFFFFFLL;
    }
    v27 |= 3u;
    v20 = (_QWORD *)v4[4];
    for ( i = (_QWORD *)*v20; i != v20; i = (_QWORD *)*i )
      --*(_DWORD *)(i[2] + 52LL);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v26);
    WakeAllConditionVariable((PCONDITION_VARIABLE)(v40 + 72));
  }
  v14 = v29;
  wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v44, v29);
  std::wstring::_Tidy_deallocate(v43);
  VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread((VmWorkerTrace::VDevWorkerThread *)v44);
  _InterlockedDecrement((volatile signed __int32 *)(v40 + 40));
  return v14;
}

```

## disassembly

```asm
0x1401006e0  push    rbx
0x1401006e2  push    rsi
0x1401006e3  push    rdi
0x1401006e4  push    r12
0x1401006e6  push    r14
0x1401006e8  push    r15
0x1401006ea  sub     rsp, 3C8h
0x1401006f1  mov     rax, cs:__security_cookie
0x1401006f8  xor     rax, rsp
0x1401006fb  mov     [rsp+3F8h+var_48], rax
0x140100703  mov     [rsp+3F8h+var_3B8], 0
0x14010070b  movups  xmm0, xmmword ptr [rdx+8]
0x14010070f  movdqu  [rsp+3F8h+var_220], xmm0
0x140100718  mov     rax, [rdx]
0x14010071b  mov     [rsp+3F8h+var_228], rax
0x140100723  test    rax, rax
0x140100726  jnz     short loc_140100732
0x140100728  mov     eax, 8000FFFFh
0x14010072d  jmp     loc_140100BE0
0x140100732  mov     [rsp+3F8h+var_3A8], 0
0x14010073a  mov     r12d, 1
0x140100740  lock add [rax+28h], r12d
0x140100745  lea     rdi, [rsp+3F8h+var_228]
0x14010074d  mov     [rsp+3F8h+var_3A0], rdi
0x140100752  mov     [rsp+3F8h+var_398], r12b
0x140100757  xor     edx, edx; Val
0x140100759  mov     r8d, 150h; Size
0x14010075f  lea     rcx, [rsp+3F8h+var_198]; void *
0x140100767  call    memset_0
0x14010076c  mov     rdx, [rsp+3F8h+var_228]
0x140100774  lea     r8, [rdx+60h]
0x140100778  add     rdx, 50h ; 'P'
0x14010077c  lea     rcx, [rsp+3F8h+var_198]; this
0x140100784  call    VmPerf__StartRelatedActivity_VmWorkerTrace__VDevWorkerThread__GUID___
0x140100789  nop
0x14010078a  mov     rdx, [rsp+3F8h+var_228]
0x140100792  lea     r9, [rdx+50h]; struct _GUID *
0x140100796  lea     r8, [rdx+60h]; struct _GUID *
0x14010079a  mov     rdx, [rdx+10h]; struct Vml::VmPerfTraceComponent *
0x14010079e  lea     rcx, [rsp+3F8h+var_208]; this
0x1401007a6  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x1401007ab  nop
0x1401007ac  xor     esi, esi
0x1401007ae  mov     r14, qword ptr [rsp+3F8h+var_220+8]
0x1401007b6  mov     r15, qword ptr [rsp+3F8h+var_220]
0x1401007be  mov     [rsp+3F8h+var_3C6], 0
0x1401007c3  xor     bl, bl
0x1401007c5  mov     [rsp+3F8h+var_3C8], bl
0x1401007c9  mov     qword ptr [rsp+3F8h+var_3C0], 0
0x1401007d2  mov     rdx, [rsp+3F8h+var_228]
0x1401007da  add     rdx, 40h ; '@'
0x1401007de  lea     rcx, [rsp+3F8h+var_3C0]
0x1401007e3  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1401007e8  mov     rax, [rsp+3F8h+var_228]
0x1401007f0  cmp     dword ptr [rax+20h], 0
0x1401007f4  jnz     short loc_140100817
0x1401007f6  call    cs:__imp_GetCurrentThreadId
0x1401007fd  nop     dword ptr [rax+rax+00h]
0x140100802  mov     ecx, eax
0x140100804  mov     rax, [rsp+3F8h+var_228]
0x14010080c  mov     [rax+20h], ecx
0x14010080f  mov     rax, [rsp+3F8h+var_228]
0x140100817  mov     al, [rax+8]
0x14010081a  mov     rcx, [rsp+3F8h+var_228]
0x140100822  test    al, al
0x140100824  jz      short loc_140100871
0x140100826  add     rcx, 48h ; 'H'; ConditionVariable
0x14010082a  call    cs:__imp_WakeAllConditionVariable
0x140100831  nop     dword ptr [rax+rax+00h]
0x140100836  lea     rcx, [rsp+3F8h+var_3C0]
0x14010083b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140100840  nop
0x140100841  lea     rcx, [rsp+3F8h+var_1E0]
0x140100849  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14010084e  nop
0x14010084f  lea     rcx, [rsp+3F8h+var_198]; this
0x140100857  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x14010085c  nop
0x14010085d  mov     [rsp+3F8h+var_398], 0
0x140100862  mov     rax, [rdi]
0x140100865  lock dec dword ptr [rax+28h]
0x140100869  or      eax, 0FFFFFFFFh
0x14010086c  jmp     loc_140100BE0
0x140100871  mov     rax, [rcx+38h]
0x140100875  mov     rbx, [rax]
0x140100878  xor     dl, dl
0x14010087a  mov     [rsp+3F8h+var_3C7], dl
0x14010087e  mov     rbx, [rbx]
0x140100881  mov     rax, [rcx+38h]
0x140100885  cmp     rbx, [rax]
0x140100888  jz      loc_140100927
0x14010088e  cmp     dword ptr [rbx+34h], 0
0x140100892  jnz     short loc_1401008E4
0x140100894  cmp     byte ptr [rbx+3Fh], 0
0x140100898  jnz     short loc_14010087E
0x14010089a  mov     [rsp+3F8h+var_3C8], r12b
0x14010089f  cmp     dword ptr [rcx+70h], 0
0x1401008a3  jz      short loc_1401008EE
0x1401008a5  mov     eax, [rbx+38h]
0x1401008a8  and     eax, [rcx+70h]
0x1401008ab  cmp     eax, [rcx+70h]
0x1401008ae  jnz     short loc_1401008EE
0x1401008b0  cmp     dword ptr [rcx+20h], 0
0x1401008b4  jz      short loc_1401008E9
0x1401008b6  mov     r12d, [rcx+20h]
0x1401008ba  call    cs:__imp_GetCurrentThreadId
0x1401008c1  nop     dword ptr [rax+rax+00h]
0x1401008c6  cmp     r12d, eax
0x1401008c9  mov     r12d, 1
0x1401008cf  jz      short loc_1401008E9
0x1401008d1  mov     [rsp+3F8h+var_3C8], 0
0x1401008d6  mov     rcx, [rsp+3F8h+var_228]
0x1401008de  mov     dl, [rsp+3F8h+var_3C7]
0x1401008e2  jmp     short loc_14010087E
0x1401008e4  mov     dl, r12b
0x1401008e7  jmp     short loc_14010087A
0x1401008e9  mov     [rsp+3F8h+var_3C6], r12b
0x1401008ee  mov     rax, [rbx+10h]
0x1401008f2  add     rax, 40h ; '@'
0x1401008f6  cmp     qword ptr [rax+18h], 7
0x1401008fb  jbe     short loc_140100900
0x1401008fd  mov     rax, [rax]
0x140100900  mov     [rsp+3F8h+var_3B0], rax
0x140100905  lea     rdx, [rsp+3F8h+var_3C6]
0x14010090a  lea     rcx, [rsp+3F8h+var_3B0]
0x14010090f  call    ??$FoundNodeToProcess@PEBGAEA_N@VmWorkerTrace@@SAX$$QEAPEBGAEA_N@Z; VmWorkerTrace::FoundNodeToProcess<ushort const *,bool &>(ushort const * &&,bool &)
0x140100914  mov     rsi, rbx
0x140100917  mov     [rbx+3Fh], r12b
0x14010091b  mov     rcx, [rsp+3F8h+var_228]
0x140100923  mov     dl, [rsp+3F8h+var_3C7]
0x140100927  mov     bl, [rsp+3F8h+var_3C8]
0x14010092b  test    dl, dl
0x14010092d  jz      loc_1401009BD
0x140100933  test    bl, bl
0x140100935  jnz     loc_1401009BD
0x14010093b  lock dec dword ptr [rcx+28h]
0x14010093f  mov     rax, [rsp+3F8h+var_228]
0x140100947  mov     ecx, [rax+28h]
0x14010094a  nop
0x14010094b  test    ecx, ecx
0x14010094d  mov     rcx, [rsp+3F8h+var_228]
0x140100955  jnz     short loc_140100986
0x140100957  mov     eax, 8007046Bh
0x14010095c  xchg    eax, [rcx+1Ch]
0x14010095f  mov     rcx, [rsp+3F8h+var_228]
0x140100967  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____TraceDeviceGraph
0x14010096c  mov     rcx, [rsp+3F8h]; this
0x140100974  lea     r8, aOnecoreVmWorke_45; "onecore\\vm\\worker\\vmb\\ParallelVDevT"...
0x14010097b  mov     edx, 100h; void *
0x140100980  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140100986  lea     rdx, [rcx+40h]; SRWLock
0x14010098a  add     rcx, 48h ; 'H'; ConditionVariable
0x14010098e  xor     r9d, r9d; Flags
0x140100991  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x140100995  call    cs:__imp_SleepConditionVariableSRW
0x14010099c  nop     dword ptr [rax+rax+00h]
0x1401009a1  mov     rax, [rsp+3F8h+var_228]
0x1401009a9  lock add [rax+28h], r12d
0x1401009ae  lea     rcx, [rsp+3F8h+var_3C0]
0x1401009b3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1401009b8  jmp     loc_1401007C9
0x1401009bd  lea     rcx, [rsp+3F8h+var_3C0]
0x1401009c2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1401009c7  test    bl, bl
0x1401009c9  jnz     short loc_1401009D4
0x1401009cb  mov     ebx, [rsp+3F8h+var_3A8]
0x1401009cf  jmp     loc_140100BA6
0x1401009d4  mov     rax, [rsi+10h]
0x1401009d8  mov     [rsp+3F8h+var_3B0], rax
0x1401009dd  lea     r8, [rsp+3F8h+var_208]
0x1401009e5  lea     rdx, [rsp+3F8h+var_3B0]
0x1401009ea  lea     rcx, [rsp+3F8h+var_298]
0x1401009f2  call    ??$make_tuple@PEAUVirtualDeviceInformation@@AEAVVmPerfTraceOperation@Vml@@@std@@YA?AV?$tuple@PEAUVirtualDeviceInformation@@VVmPerfTraceOperation@Vml@@@0@$$QEAPEAUVirtualDeviceInformation@@AEAVVmPerfTraceOperation@Vml@@@Z; std::make_tuple<VirtualDeviceInformation *,Vml::VmPerfTraceOperation &>(VirtualDeviceInformation * &&,Vml::VmPerfTraceOperation &)
0x1401009f7  mov     rbx, rax
0x1401009fa  mov     [rsp+3F8h+var_388], r15
0x1401009ff  mov     [rsp+3F8h+var_380], r14
0x140100a04  mov     rdx, rax; struct Vml::VmPerfTraceOperation *
0x140100a07  lea     rcx, [rsp+3F8h+var_378]; this
0x140100a0f  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEBV01@@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceOperation const &)
0x140100a14  mov     rax, [rbx+68h]
0x140100a18  mov     [rsp+3F8h+var_310], rax
0x140100a20  mov     rbx, [rsp+3F8h+var_228]
0x140100a28  mov     rax, [rsp+3F8h+var_388]
0x140100a2d  mov     eax, [rax]
0x140100a2f  mov     [rsp+3F8h+var_3C0], eax
0x140100a33  mov     rax, [rsp+3F8h+var_380]
0x140100a38  mov     rax, [rax]
0x140100a3b  mov     [rsp+3F8h+var_3B0], rax
0x140100a40  lea     rdx, [rsp+3F8h+var_378]; struct Vml::VmPerfTraceOperation *
0x140100a48  lea     rcx, [rsp+3F8h+var_308]; this
0x140100a50  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEBV01@@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceOperation const &)
0x140100a55  mov     r8, rax
0x140100a58  mov     eax, [rsp+3F8h+var_3C0]
0x140100a5c  mov     [rsp+3F8h+var_3D8], eax; int
0x140100a60  mov     r9, [rsp+3F8h+var_3B0]
0x140100a65  mov     rdx, [rsp+3F8h+var_310]
0x140100a6d  lea     rcx, [rbx+30h]
0x140100a71  call    _lambda_471742be78fc95ffa3bd838ab9f364e1___operator__
0x140100a76  mov     ebx, eax
0x140100a78  lea     rcx, [rsp+3F8h+var_350]
0x140100a80  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140100a85  nop
0x140100a86  lea     rcx, [rsp+3F8h+var_270]
0x140100a8e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140100a93  mov     edx, ebx
0x140100a95  mov     rcx, [rsp+3F8h+var_228]
0x140100a9d  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x140100aa2  mov     rdx, [rsp+3F8h+var_228]
0x140100aaa  test    ebx, ebx
0x140100aac  jns     short loc_140100AB9
0x140100aae  cmp     byte ptr [rdx+9], 0
0x140100ab2  jz      short loc_140100AB9
0x140100ab4  mov     al, r12b
0x140100ab7  jmp     short loc_140100ABB
0x140100ab9  xor     al, al
0x140100abb  mov     rcx, [rsp+3F8h]; this
0x140100ac3  test    al, al
0x140100ac5  jz      short loc_140100ADB
0x140100ac7  mov     r9d, ebx; char *
0x140100aca  lea     r8, aOnecoreVmWorke_45; "onecore\\vm\\worker\\vmb\\ParallelVDevT"...
0x140100ad1  mov     edx, 11Eh; void *
0x140100ad6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140100adb  mov     qword ptr [rsp+3F8h+var_3C0], 0
0x140100ae4  add     rdx, 40h ; '@'
0x140100ae8  lea     rcx, [rsp+3F8h+var_3C0]
0x140100aed  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x140100af2  mov     rax, [rsp+3F8h+var_228]
0x140100afa  mov     cl, [rax+8]
0x140100afd  test    cl, cl
0x140100aff  jz      short loc_140100B54
0x140100b01  mov     rcx, [rsp+3F8h+var_228]
0x140100b09  add     rcx, 48h ; 'H'; ConditionVariable
0x140100b0d  call    cs:__imp_WakeAllConditionVariable
0x140100b14  nop     dword ptr [rax+rax+00h]
0x140100b19  lea     rcx, [rsp+3F8h+var_3C0]
0x140100b1e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140100b23  nop
0x140100b24  lea     rcx, [rsp+3F8h+var_1E0]
0x140100b2c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140100b31  nop
0x140100b32  lea     rcx, [rsp+3F8h+var_198]; this
0x140100b3a  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x140100b3f  nop
0x140100b40  mov     [rsp+3F8h+var_398], 0
0x140100b45  mov     rax, [rdi]
0x140100b48  lock dec dword ptr [rax+28h]
0x140100b4c  or      eax, 0FFFFFFFFh
0x140100b4f  jmp     loc_140100BE0
0x140100b54  or      [rsp+3F8h+var_3B8], 3
0x140100b59  mov     rcx, [rsi+20h]
0x140100b5d  mov     rax, [rcx]
0x140100b60  cmp     rax, rcx
0x140100b63  jz      short loc_140100B71
0x140100b65  mov     rdx, [rax+10h]
0x140100b69  dec     dword ptr [rdx+34h]
0x140100b6c  mov     rax, [rax]
0x140100b6f  jmp     short loc_140100B60
0x140100b71  lea     rcx, [rsp+3F8h+var_3C0]
0x140100b76  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140100b7b  mov     rcx, [rsp+3F8h+var_228]
0x140100b83  add     rcx, 48h ; 'H'; ConditionVariable
0x140100b87  call    cs:__imp_WakeAllConditionVariable
0x140100b8e  nop     dword ptr [rax+rax+00h]
0x140100b93  jmp     loc_1401007BE
0x140100b98  mov     ebx, [rsp+3F8h+var_3C0]
0x140100b9c  mov     r12b, [rsp+3F8h+var_398]
0x140100ba1  mov     rdi, [rsp+3F8h+var_3A0]
0x140100ba6  mov     edx, ebx
0x140100ba8  lea     rcx, [rsp+3F8h+var_198]
0x140100bb0  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140100bb5  nop
0x140100bb6  lea     rcx, [rsp+3F8h+var_1E0]
0x140100bbe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140100bc3  nop
0x140100bc4  lea     rcx, [rsp+3F8h+var_198]; this
0x140100bcc  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x140100bd1  nop
0x140100bd2  test    r12b, r12b
0x140100bd5  jz      short loc_140100BDE
0x140100bd7  mov     rcx, [rdi]
0x140100bda  lock dec dword ptr [rcx+28h]
0x140100bde  mov     eax, ebx
0x140100be0  mov     rcx, [rsp+3F8h+var_48]
0x140100be8  xor     rcx, rsp; StackCookie
0x140100beb  call    __security_check_cookie
0x140100bf0  add     rsp, 3C8h
0x140100bf7  pop     r15
0x140100bf9  pop     r14
0x140100bfb  pop     r12
0x140100bfd  pop     rdi
0x140100bfe  pop     rsi
0x140100bff  pop     rbx
0x140100c00  retn
```
