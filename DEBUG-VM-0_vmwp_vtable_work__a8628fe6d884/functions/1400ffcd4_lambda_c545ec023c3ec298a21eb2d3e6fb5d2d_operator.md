# _lambda_c545ec023c3ec298a21eb2d3e6fb5d2d_::operator()

- ea: `0x1400ffcd4`
- end: `0x1401001f6`
- name: `_lambda_c545ec023c3ec298a21eb2d3e6fb5d2d_::operator()`
- size: `1314`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14027e8e0`

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
- `0x1400ffcd4`
- `0x140101a98`
- `0x140132940`
- `0x1401335fc`
- `0x140281188`
- `0x140282e3c`
- `0x140283890`
- `0x140284160`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400ffdea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400ffeae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400ffdea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400ffeae`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1400ffe1e`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140100101`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14010017b`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1400ffe1e`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140100101`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14010017b`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1400fff89`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1400fff89`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall lambda_c545ec023c3ec298a21eb2d3e6fb5d2d_::operator()(__int64 a1, __int64 *a2)
{
  __int64 v2; // rax
  char v4; // r12
  __int64 *v5; // rdi
  __int64 *v6; // rsi
  _QWORD *v7; // r14
  int *v8; // r15
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 *v11; // rbx
  char v12; // dl
  int v13; // r12d
  bool v14; // zf
  _QWORD *v15; // rax
  const char *v16; // r9
  unsigned int v17; // ebx
  const struct Vml::VmPerfTraceOperation *v18; // rbx
  __int64 v19; // rbx
  __int64 v20; // rax
  int v21; // ebx
  wil *v23; // rcx
  _QWORD *v24; // rcx
  _QWORD *i; // rax
  unsigned int v26; // eax
  int v27; // edx
  int v28; // [rsp+20h] [rbp-3D8h]
  char v29; // [rsp+30h] [rbp-3C8h]
  char v30; // [rsp+31h] [rbp-3C7h]
  char v31[6]; // [rsp+32h] [rbp-3C6h] BYREF
  int v32[2]; // [rsp+38h] [rbp-3C0h] BYREF
  int v33; // [rsp+40h] [rbp-3B8h]
  _QWORD *v34; // [rsp+48h] [rbp-3B0h] BYREF
  unsigned int v35; // [rsp+50h] [rbp-3A8h]
  __int64 *v36; // [rsp+58h] [rbp-3A0h]
  char v37; // [rsp+60h] [rbp-398h]
  int *v38; // [rsp+70h] [rbp-388h]
  _QWORD *v39; // [rsp+78h] [rbp-380h]
  _BYTE v40[40]; // [rsp+80h] [rbp-378h] BYREF
  _BYTE v41[64]; // [rsp+A8h] [rbp-350h] BYREF
  __int64 v42; // [rsp+E8h] [rbp-310h]
  _BYTE v43[112]; // [rsp+F0h] [rbp-308h] BYREF
  _BYTE v44[40]; // [rsp+160h] [rbp-298h] BYREF
  _BYTE v45[72]; // [rsp+188h] [rbp-270h] BYREF
  __int64 v46; // [rsp+1D0h] [rbp-228h] BYREF
  __int128 v47; // [rsp+1D8h] [rbp-220h]
  _BYTE v48[40]; // [rsp+1F0h] [rbp-208h] BYREF
  _BYTE v49[72]; // [rsp+218h] [rbp-1E0h] BYREF
  _BYTE v50[336]; // [rsp+260h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+0h]

  v33 = 0;
  v47 = *(_OWORD *)(a2 + 1);
  v2 = *a2;
  v46 = v2;
  if ( !v2 )
    return 2147549183LL;
  v35 = 0;
  v4 = 1;
  _InterlockedAdd((volatile signed __int32 *)(v2 + 40), 1u);
  v5 = &v46;
  v36 = &v46;
  v37 = 1;
  memset_0(v50, 0, sizeof(v50));
  VmPerf::StartRelatedActivity_VmWorkerTrace::VDevWorkerThread__GUID___(
    (VmWorkerTrace::VDevWorkerThread *)v50,
    v46 + 80,
    (const struct _GUID *)(v46 + 96));
  Vml::VmPerfTraceOperation::VmPerfTraceOperation(
    (Vml::VmPerfTraceOperation *)v48,
    *(struct Vml::VmPerfTraceComponent **)(v46 + 16),
    (const struct _GUID *)(v46 + 96),
    (const struct _GUID *)(v46 + 80));
  v6 = 0;
  v7 = (_QWORD *)*((_QWORD *)&v47 + 1);
  v8 = (int *)v47;
  while ( 1 )
  {
    v31[0] = 0;
    v29 = 0;
    while ( 1 )
    {
      *(_QWORD *)v32 = 0;
      wil::AcquireSRWLockExclusive(v32, v46 + 64);
      v9 = v46;
      if ( !*(_DWORD *)(v46 + 32) )
      {
        *(_DWORD *)(v46 + 32) = GetCurrentThreadId();
        v9 = v46;
      }
      v10 = v46;
      if ( *(_BYTE *)(v9 + 8) )
        goto LABEL_8;
      v11 = **(__int64 ***)(v46 + 56);
      v12 = 0;
LABEL_10:
      v30 = v12;
      while ( 1 )
      {
        v11 = (__int64 *)*v11;
        if ( v11 == **(__int64 ***)(v10 + 56) )
          break;
        if ( *((_DWORD *)v11 + 13) )
        {
          v12 = 1;
          goto LABEL_10;
        }
        if ( !*((_BYTE *)v11 + 63) )
        {
          v29 = 1;
          if ( !*(_DWORD *)(v10 + 112) || (*(_DWORD *)(v10 + 112) & (_DWORD)v11[7]) != *(_DWORD *)(v10 + 112) )
            goto LABEL_21;
          if ( !*(_DWORD *)(v10 + 32) || (v13 = *(_DWORD *)(v10 + 32), v14 = v13 == GetCurrentThreadId(), v4 = 1, v14) )
          {
            v31[0] = 1;
LABEL_21:
            v15 = (_QWORD *)(v11[2] + 64);
            if ( *(_QWORD *)(v11[2] + 88) > 7u )
              v15 = (_QWORD *)*v15;
            v34 = v15;
            VmWorkerTrace::FoundNodeToProcess<unsigned short const *,bool &>(&v34, v31);
            v6 = v11;
            *((_BYTE *)v11 + 63) = 1;
            v10 = v46;
            v12 = v30;
            break;
          }
          v29 = 0;
          v10 = v46;
          v12 = v30;
        }
      }
      if ( !v12 || v29 )
        break;
      _InterlockedDecrement((volatile signed __int32 *)(v10 + 40));
      if ( !*(_DWORD *)(v46 + 40) )
      {
        _InterlockedExchange((volatile __int32 *)(v46 + 28), -2147023765);
        ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::TraceDeviceGraph(v46);
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x100,
          (unsigned int)"onecore\\vm\\worker\\vmb\\ParallelVDevTransitionOrchestrator.h",
          v16);
      }
      SleepConditionVariableSRW((PCONDITION_VARIABLE)(v46 + 72), (PSRWLOCK)(v46 + 64), 0xFFFFFFFF, 0);
      _InterlockedAdd((volatile signed __int32 *)(v46 + 40), 1u);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v32);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v32);
    if ( !v29 )
      break;
    try
    {
      v34 = (_QWORD *)v6[2];
      v18 = (const struct Vml::VmPerfTraceOperation *)std::make_tuple<VirtualDeviceInformation *,Vml::VmPerfTraceOperation &>(
                                                        v44,
                                                        &v34,
                                                        v48);
      v38 = v8;
      v39 = v7;
      Vml::VmPerfTraceOperation::VmPerfTraceOperation((Vml::VmPerfTraceOperation *)v40, v18);
      v42 = *((_QWORD *)v18 + 13);
      v19 = v46;
      v32[0] = *v38;
      v34 = (_QWORD *)*v39;
      v20 = Vml::VmPerfTraceOperation::VmPerfTraceOperation(
              (Vml::VmPerfTraceOperation *)v43,
              (const struct Vml::VmPerfTraceOperation *)v40);
      v28 = v32[0];
      v21 = lambda_bfaf703db63e015698673ef70c5ed4c6_::operator()(v19 + 48, v42, v20, v34);
      std::wstring::_Tidy_deallocate(v41);
      std::wstring::_Tidy_deallocate(v45);
      ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::SetResult(v46, (unsigned int)v21);
      if ( v21 < 0 && *(_BYTE *)(v46 + 9) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x11E,
          (unsigned int)"onecore\\vm\\worker\\vmb\\ParallelVDevTransitionOrchestrator.h",
          (const char *)(unsigned int)v21,
          v28);
      *(_QWORD *)v32 = 0;
      wil::AcquireSRWLockExclusive(v32, v46 + 64);
    }
    catch ( ... )
    {
      v26 = wil::ResultFromCaughtException(v23);
      ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::SetResult(v46, v26);
      v32[0] = v27;
      *(_BYTE *)(v46 + 8) = 1;
      WakeAllConditionVariable((PCONDITION_VARIABLE)(v46 + 72));
      v17 = v32[0];
      v4 = v37;
      v5 = v36;
      goto LABEL_43;
    }
    if ( *(_BYTE *)(v46 + 8) )
    {
LABEL_8:
      WakeAllConditionVariable((PCONDITION_VARIABLE)(v46 + 72));
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v32);
      std::wstring::_Tidy_deallocate(v49);
      VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread((VmWorkerTrace::VDevWorkerThread *)v50);
      v37 = 0;
      _InterlockedDecrement((volatile signed __int32 *)(v46 + 40));
      return 0xFFFFFFFFLL;
    }
    v33 |= 3u;
    v24 = (_QWORD *)v6[4];
    for ( i = (_QWORD *)*v24; i != v24; i = (_QWORD *)*i )
      --*(_DWORD *)(i[2] + 52LL);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v32);
    WakeAllConditionVariable((PCONDITION_VARIABLE)(v46 + 72));
  }
  v17 = v35;
LABEL_43:
  wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v50, v17);
  std::wstring::_Tidy_deallocate(v49);
  VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread((VmWorkerTrace::VDevWorkerThread *)v50);
  if ( v4 )
    _InterlockedDecrement((volatile signed __int32 *)(*v5 + 40));
  return v17;
}

```

## disassembly

```asm
0x1400ffcd4  push    rbx
0x1400ffcd6  push    rsi
0x1400ffcd7  push    rdi
0x1400ffcd8  push    r12
0x1400ffcda  push    r14
0x1400ffcdc  push    r15
0x1400ffcde  sub     rsp, 3C8h
0x1400ffce5  mov     rax, cs:__security_cookie
0x1400ffcec  xor     rax, rsp
0x1400ffcef  mov     [rsp+3F8h+var_48], rax
0x1400ffcf7  mov     [rsp+3F8h+var_3B8], 0
0x1400ffcff  movups  xmm0, xmmword ptr [rdx+8]
0x1400ffd03  movdqu  [rsp+3F8h+var_220], xmm0
0x1400ffd0c  mov     rax, [rdx]
0x1400ffd0f  mov     [rsp+3F8h+var_228], rax
0x1400ffd17  test    rax, rax
0x1400ffd1a  jnz     short loc_1400FFD26
0x1400ffd1c  mov     eax, 8000FFFFh
0x1400ffd21  jmp     loc_1401001D4
0x1400ffd26  mov     [rsp+3F8h+var_3A8], 0
0x1400ffd2e  mov     r12d, 1
0x1400ffd34  lock add [rax+28h], r12d
0x1400ffd39  lea     rdi, [rsp+3F8h+var_228]
0x1400ffd41  mov     [rsp+3F8h+var_3A0], rdi
0x1400ffd46  mov     [rsp+3F8h+var_398], r12b
0x1400ffd4b  xor     edx, edx; Val
0x1400ffd4d  mov     r8d, 150h; Size
0x1400ffd53  lea     rcx, [rsp+3F8h+var_198]; void *
0x1400ffd5b  call    memset_0
0x1400ffd60  mov     rdx, [rsp+3F8h+var_228]
0x1400ffd68  lea     r8, [rdx+60h]
0x1400ffd6c  add     rdx, 50h ; 'P'
0x1400ffd70  lea     rcx, [rsp+3F8h+var_198]; this
0x1400ffd78  call    VmPerf__StartRelatedActivity_VmWorkerTrace__VDevWorkerThread__GUID___
0x1400ffd7d  nop
0x1400ffd7e  mov     rdx, [rsp+3F8h+var_228]
0x1400ffd86  lea     r9, [rdx+50h]; struct _GUID *
0x1400ffd8a  lea     r8, [rdx+60h]; struct _GUID *
0x1400ffd8e  mov     rdx, [rdx+10h]; struct Vml::VmPerfTraceComponent *
0x1400ffd92  lea     rcx, [rsp+3F8h+var_208]; this
0x1400ffd9a  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x1400ffd9f  nop
0x1400ffda0  xor     esi, esi
0x1400ffda2  mov     r14, qword ptr [rsp+3F8h+var_220+8]
0x1400ffdaa  mov     r15, qword ptr [rsp+3F8h+var_220]
0x1400ffdb2  mov     [rsp+3F8h+var_3C6], 0
0x1400ffdb7  xor     bl, bl
0x1400ffdb9  mov     [rsp+3F8h+var_3C8], bl
0x1400ffdbd  mov     qword ptr [rsp+3F8h+var_3C0], 0
0x1400ffdc6  mov     rdx, [rsp+3F8h+var_228]
0x1400ffdce  add     rdx, 40h ; '@'
0x1400ffdd2  lea     rcx, [rsp+3F8h+var_3C0]
0x1400ffdd7  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1400ffddc  mov     rax, [rsp+3F8h+var_228]
0x1400ffde4  cmp     dword ptr [rax+20h], 0
0x1400ffde8  jnz     short loc_1400FFE0B
0x1400ffdea  call    cs:__imp_GetCurrentThreadId
0x1400ffdf1  nop     dword ptr [rax+rax+00h]
0x1400ffdf6  mov     ecx, eax
0x1400ffdf8  mov     rax, [rsp+3F8h+var_228]
0x1400ffe00  mov     [rax+20h], ecx
0x1400ffe03  mov     rax, [rsp+3F8h+var_228]
0x1400ffe0b  mov     al, [rax+8]
0x1400ffe0e  mov     rcx, [rsp+3F8h+var_228]
0x1400ffe16  test    al, al
0x1400ffe18  jz      short loc_1400FFE65
0x1400ffe1a  add     rcx, 48h ; 'H'; ConditionVariable
0x1400ffe1e  call    cs:__imp_WakeAllConditionVariable
0x1400ffe25  nop     dword ptr [rax+rax+00h]
0x1400ffe2a  lea     rcx, [rsp+3F8h+var_3C0]
0x1400ffe2f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1400ffe34  nop
0x1400ffe35  lea     rcx, [rsp+3F8h+var_1E0]
0x1400ffe3d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400ffe42  nop
0x1400ffe43  lea     rcx, [rsp+3F8h+var_198]; this
0x1400ffe4b  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x1400ffe50  nop
0x1400ffe51  mov     [rsp+3F8h+var_398], 0
0x1400ffe56  mov     rax, [rdi]
0x1400ffe59  lock dec dword ptr [rax+28h]
0x1400ffe5d  or      eax, 0FFFFFFFFh
0x1400ffe60  jmp     loc_1401001D4
0x1400ffe65  mov     rax, [rcx+38h]
0x1400ffe69  mov     rbx, [rax]
0x1400ffe6c  xor     dl, dl
0x1400ffe6e  mov     [rsp+3F8h+var_3C7], dl
0x1400ffe72  mov     rbx, [rbx]
0x1400ffe75  mov     rax, [rcx+38h]
0x1400ffe79  cmp     rbx, [rax]
0x1400ffe7c  jz      loc_1400FFF1B
0x1400ffe82  cmp     dword ptr [rbx+34h], 0
0x1400ffe86  jnz     short loc_1400FFED8
0x1400ffe88  cmp     byte ptr [rbx+3Fh], 0
0x1400ffe8c  jnz     short loc_1400FFE72
0x1400ffe8e  mov     [rsp+3F8h+var_3C8], r12b
0x1400ffe93  cmp     dword ptr [rcx+70h], 0
0x1400ffe97  jz      short loc_1400FFEE2
0x1400ffe99  mov     eax, [rbx+38h]
0x1400ffe9c  and     eax, [rcx+70h]
0x1400ffe9f  cmp     eax, [rcx+70h]
0x1400ffea2  jnz     short loc_1400FFEE2
0x1400ffea4  cmp     dword ptr [rcx+20h], 0
0x1400ffea8  jz      short loc_1400FFEDD
0x1400ffeaa  mov     r12d, [rcx+20h]
0x1400ffeae  call    cs:__imp_GetCurrentThreadId
0x1400ffeb5  nop     dword ptr [rax+rax+00h]
0x1400ffeba  cmp     r12d, eax
0x1400ffebd  mov     r12d, 1
0x1400ffec3  jz      short loc_1400FFEDD
0x1400ffec5  mov     [rsp+3F8h+var_3C8], 0
0x1400ffeca  mov     rcx, [rsp+3F8h+var_228]
0x1400ffed2  mov     dl, [rsp+3F8h+var_3C7]
0x1400ffed6  jmp     short loc_1400FFE72
0x1400ffed8  mov     dl, r12b
0x1400ffedb  jmp     short loc_1400FFE6E
0x1400ffedd  mov     [rsp+3F8h+var_3C6], r12b
0x1400ffee2  mov     rax, [rbx+10h]
0x1400ffee6  add     rax, 40h ; '@'
0x1400ffeea  cmp     qword ptr [rax+18h], 7
0x1400ffeef  jbe     short loc_1400FFEF4
0x1400ffef1  mov     rax, [rax]
0x1400ffef4  mov     [rsp+3F8h+var_3B0], rax
0x1400ffef9  lea     rdx, [rsp+3F8h+var_3C6]
0x1400ffefe  lea     rcx, [rsp+3F8h+var_3B0]
0x1400fff03  call    ??$FoundNodeToProcess@PEBGAEA_N@VmWorkerTrace@@SAX$$QEAPEBGAEA_N@Z; VmWorkerTrace::FoundNodeToProcess<ushort const *,bool &>(ushort const * &&,bool &)
0x1400fff08  mov     rsi, rbx
0x1400fff0b  mov     [rbx+3Fh], r12b
0x1400fff0f  mov     rcx, [rsp+3F8h+var_228]
0x1400fff17  mov     dl, [rsp+3F8h+var_3C7]
0x1400fff1b  mov     bl, [rsp+3F8h+var_3C8]
0x1400fff1f  test    dl, dl
0x1400fff21  jz      loc_1400FFFB1
0x1400fff27  test    bl, bl
0x1400fff29  jnz     loc_1400FFFB1
0x1400fff2f  lock dec dword ptr [rcx+28h]
0x1400fff33  mov     rax, [rsp+3F8h+var_228]
0x1400fff3b  mov     ecx, [rax+28h]
0x1400fff3e  nop
0x1400fff3f  test    ecx, ecx
0x1400fff41  mov     rcx, [rsp+3F8h+var_228]
0x1400fff49  jnz     short loc_1400FFF7A
0x1400fff4b  mov     eax, 8007046Bh
0x1400fff50  xchg    eax, [rcx+1Ch]
0x1400fff53  mov     rcx, [rsp+3F8h+var_228]
0x1400fff5b  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____TraceDeviceGraph
0x1400fff60  mov     rcx, [rsp+3F8h]; this
0x1400fff68  lea     r8, aOnecoreVmWorke_45; "onecore\\vm\\worker\\vmb\\ParallelVDevT"...
0x1400fff6f  mov     edx, 100h; void *
0x1400fff74  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400fff7a  lea     rdx, [rcx+40h]; SRWLock
0x1400fff7e  add     rcx, 48h ; 'H'; ConditionVariable
0x1400fff82  xor     r9d, r9d; Flags
0x1400fff85  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x1400fff89  call    cs:__imp_SleepConditionVariableSRW
0x1400fff90  nop     dword ptr [rax+rax+00h]
0x1400fff95  mov     rax, [rsp+3F8h+var_228]
0x1400fff9d  lock add [rax+28h], r12d
0x1400fffa2  lea     rcx, [rsp+3F8h+var_3C0]
0x1400fffa7  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1400fffac  jmp     loc_1400FFDBD
0x1400fffb1  lea     rcx, [rsp+3F8h+var_3C0]
0x1400fffb6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1400fffbb  test    bl, bl
0x1400fffbd  jnz     short loc_1400FFFC8
0x1400fffbf  mov     ebx, [rsp+3F8h+var_3A8]
0x1400fffc3  jmp     loc_14010019A
0x1400fffc8  mov     rax, [rsi+10h]
0x1400fffcc  mov     [rsp+3F8h+var_3B0], rax
0x1400fffd1  lea     r8, [rsp+3F8h+var_208]
0x1400fffd9  lea     rdx, [rsp+3F8h+var_3B0]
0x1400fffde  lea     rcx, [rsp+3F8h+var_298]
0x1400fffe6  call    ??$make_tuple@PEAUVirtualDeviceInformation@@AEAVVmPerfTraceOperation@Vml@@@std@@YA?AV?$tuple@PEAUVirtualDeviceInformation@@VVmPerfTraceOperation@Vml@@@0@$$QEAPEAUVirtualDeviceInformation@@AEAVVmPerfTraceOperation@Vml@@@Z; std::make_tuple<VirtualDeviceInformation *,Vml::VmPerfTraceOperation &>(VirtualDeviceInformation * &&,Vml::VmPerfTraceOperation &)
0x1400fffeb  mov     rbx, rax
0x1400fffee  mov     [rsp+3F8h+var_388], r15
0x1400ffff3  mov     [rsp+3F8h+var_380], r14
0x1400ffff8  mov     rdx, rax; struct Vml::VmPerfTraceOperation *
0x1400ffffb  lea     rcx, [rsp+3F8h+var_378]; this
0x140100003  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEBV01@@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceOperation const &)
0x140100008  mov     rax, [rbx+68h]
0x14010000c  mov     [rsp+3F8h+var_310], rax
0x140100014  mov     rbx, [rsp+3F8h+var_228]
0x14010001c  mov     rax, [rsp+3F8h+var_388]
0x140100021  mov     eax, [rax]
0x140100023  mov     [rsp+3F8h+var_3C0], eax
0x140100027  mov     rax, [rsp+3F8h+var_380]
0x14010002c  mov     rax, [rax]
0x14010002f  mov     [rsp+3F8h+var_3B0], rax
0x140100034  lea     rdx, [rsp+3F8h+var_378]; struct Vml::VmPerfTraceOperation *
0x14010003c  lea     rcx, [rsp+3F8h+var_308]; this
0x140100044  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEBV01@@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceOperation const &)
0x140100049  mov     r8, rax
0x14010004c  mov     eax, [rsp+3F8h+var_3C0]
0x140100050  mov     [rsp+3F8h+var_3D8], eax; int
0x140100054  mov     r9, [rsp+3F8h+var_3B0]
0x140100059  mov     rdx, [rsp+3F8h+var_310]
0x140100061  lea     rcx, [rbx+30h]
0x140100065  call    _lambda_bfaf703db63e015698673ef70c5ed4c6___operator__
0x14010006a  mov     ebx, eax
0x14010006c  lea     rcx, [rsp+3F8h+var_350]
0x140100074  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140100079  nop
0x14010007a  lea     rcx, [rsp+3F8h+var_270]
0x140100082  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140100087  mov     edx, ebx
0x140100089  mov     rcx, [rsp+3F8h+var_228]
0x140100091  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x140100096  mov     rdx, [rsp+3F8h+var_228]
0x14010009e  test    ebx, ebx
0x1401000a0  jns     short loc_1401000AD
0x1401000a2  cmp     byte ptr [rdx+9], 0
0x1401000a6  jz      short loc_1401000AD
0x1401000a8  mov     al, r12b
0x1401000ab  jmp     short loc_1401000AF
0x1401000ad  xor     al, al
0x1401000af  mov     rcx, [rsp+3F8h]; this
0x1401000b7  test    al, al
0x1401000b9  jz      short loc_1401000CF
0x1401000bb  mov     r9d, ebx; char *
0x1401000be  lea     r8, aOnecoreVmWorke_45; "onecore\\vm\\worker\\vmb\\ParallelVDevT"...
0x1401000c5  mov     edx, 11Eh; void *
0x1401000ca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1401000cf  mov     qword ptr [rsp+3F8h+var_3C0], 0
0x1401000d8  add     rdx, 40h ; '@'
0x1401000dc  lea     rcx, [rsp+3F8h+var_3C0]
0x1401000e1  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1401000e6  mov     rax, [rsp+3F8h+var_228]
0x1401000ee  mov     cl, [rax+8]
0x1401000f1  test    cl, cl
0x1401000f3  jz      short loc_140100148
0x1401000f5  mov     rcx, [rsp+3F8h+var_228]
0x1401000fd  add     rcx, 48h ; 'H'; ConditionVariable
0x140100101  call    cs:__imp_WakeAllConditionVariable
0x140100108  nop     dword ptr [rax+rax+00h]
0x14010010d  lea     rcx, [rsp+3F8h+var_3C0]
0x140100112  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140100117  nop
0x140100118  lea     rcx, [rsp+3F8h+var_1E0]
0x140100120  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140100125  nop
0x140100126  lea     rcx, [rsp+3F8h+var_198]; this
0x14010012e  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x140100133  nop
0x140100134  mov     [rsp+3F8h+var_398], 0
0x140100139  mov     rax, [rdi]
0x14010013c  lock dec dword ptr [rax+28h]
0x140100140  or      eax, 0FFFFFFFFh
0x140100143  jmp     loc_1401001D4
0x140100148  or      [rsp+3F8h+var_3B8], 3
0x14010014d  mov     rcx, [rsi+20h]
0x140100151  mov     rax, [rcx]
0x140100154  cmp     rax, rcx
0x140100157  jz      short loc_140100165
0x140100159  mov     rdx, [rax+10h]
0x14010015d  dec     dword ptr [rdx+34h]
0x140100160  mov     rax, [rax]
0x140100163  jmp     short loc_140100154
0x140100165  lea     rcx, [rsp+3F8h+var_3C0]
0x14010016a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14010016f  mov     rcx, [rsp+3F8h+var_228]
0x140100177  add     rcx, 48h ; 'H'; ConditionVariable
0x14010017b  call    cs:__imp_WakeAllConditionVariable
0x140100182  nop     dword ptr [rax+rax+00h]
0x140100187  jmp     loc_1400FFDB2
0x14010018c  mov     ebx, [rsp+3F8h+var_3C0]
0x140100190  mov     r12b, [rsp+3F8h+var_398]
0x140100195  mov     rdi, [rsp+3F8h+var_3A0]
0x14010019a  mov     edx, ebx
0x14010019c  lea     rcx, [rsp+3F8h+var_198]
0x1401001a4  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1401001a9  nop
0x1401001aa  lea     rcx, [rsp+3F8h+var_1E0]
0x1401001b2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1401001b7  nop
0x1401001b8  lea     rcx, [rsp+3F8h+var_198]; this
0x1401001c0  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x1401001c5  nop
0x1401001c6  test    r12b, r12b
0x1401001c9  jz      short loc_1401001D2
0x1401001cb  mov     rcx, [rdi]
0x1401001ce  lock dec dword ptr [rcx+28h]
0x1401001d2  mov     eax, ebx
0x1401001d4  mov     rcx, [rsp+3F8h+var_48]
0x1401001dc  xor     rcx, rsp; StackCookie
0x1401001df  call    __security_check_cookie
0x1401001e4  add     rsp, 3C8h
0x1401001eb  pop     r15
0x1401001ed  pop     r14
0x1401001ef  pop     r12
0x1401001f1  pop     rdi
0x1401001f2  pop     rsi
0x1401001f3  pop     rbx
0x1401001f4  retn
```
