# _lambda_664edb7134184b7e2576fb6f05eaacc8_::operator()

- ea: `0x1401015b4`
- end: `0x140101a8f`
- name: `_lambda_664edb7134184b7e2576fb6f05eaacc8_::operator()`
- size: `1243`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14027e8c0`

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
- `0x1401015b4`
- `0x140101a98`
- `0x140132940`
- `0x1401335fc`
- `0x140281188`
- `0x140282e3c`
- `0x140283890`
- `0x140283f34`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401016ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140101775`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1401016ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140101775`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1401016e2`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14010199a`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140101a14`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1401016e2`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14010199a`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140101a14`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x14010184a`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x14010184a`

## pseudocode

```c
__int64 __fastcall lambda_664edb7134184b7e2576fb6f05eaacc8_::operator()(__int64 a1, __int64 *a2)
{
  __int64 v2; // rax
  unsigned int *v4; // r14
  __int64 *v5; // rsi
  char v6; // r15
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 *v9; // rbx
  char v10; // dl
  int v11; // r15d
  _QWORD *v12; // rax
  const char *v13; // r9
  const struct Vml::VmPerfTraceOperation *v14; // rbx
  __int64 v15; // rbx
  unsigned int v16; // r15d
  __int64 v17; // rax
  int v18; // ebx
  _QWORD *v20; // rcx
  _QWORD *i; // rax
  unsigned int v22; // ebx
  int v23; // [rsp+20h] [rbp-3A8h] BYREF
  __int64 v24; // [rsp+28h] [rbp-3A0h] BYREF
  unsigned int v25; // [rsp+30h] [rbp-398h]
  int v26; // [rsp+34h] [rbp-394h]
  _QWORD v27[2]; // [rsp+38h] [rbp-390h] BYREF
  char v28; // [rsp+48h] [rbp-380h]
  unsigned int *v29; // [rsp+50h] [rbp-378h]
  _BYTE v30[40]; // [rsp+58h] [rbp-370h] BYREF
  _BYTE v31[64]; // [rsp+80h] [rbp-348h] BYREF
  __int64 v32; // [rsp+C0h] [rbp-308h]
  _BYTE v33[112]; // [rsp+D0h] [rbp-2F8h] BYREF
  _BYTE v34[40]; // [rsp+140h] [rbp-288h] BYREF
  _BYTE v35[72]; // [rsp+168h] [rbp-260h] BYREF
  __int64 v36; // [rsp+1B0h] [rbp-218h] BYREF
  _BYTE v37[40]; // [rsp+1C0h] [rbp-208h] BYREF
  _BYTE v38[72]; // [rsp+1E8h] [rbp-1E0h] BYREF
  _BYTE v39[336]; // [rsp+230h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+0h]

  v26 = 0;
  v2 = *a2;
  v36 = v2;
  if ( !v2 )
    return 2147549183LL;
  v25 = 0;
  v4 = (unsigned int *)a2[1];
  _InterlockedAdd((volatile signed __int32 *)(v2 + 40), 1u);
  v27[1] = &v36;
  v28 = 1;
  memset_0(v39, 0, sizeof(v39));
  VmPerf::StartRelatedActivity_VmWorkerTrace::VDevWorkerThread__GUID___((VmWorkerTrace::VDevWorkerThread *)v39);
  Vml::VmPerfTraceOperation::VmPerfTraceOperation(
    (Vml::VmPerfTraceOperation *)v37,
    *(struct Vml::VmPerfTraceComponent **)(v36 + 16),
    (const struct _GUID *)(v36 + 96),
    (const struct _GUID *)(v36 + 80));
  v5 = 0;
  while ( 1 )
  {
    BYTE1(v23) = 0;
    v6 = 0;
    while ( 1 )
    {
      v24 = 0;
      wil::AcquireSRWLockExclusive(&v24, v36 + 64);
      v7 = v36;
      if ( !*(_DWORD *)(v36 + 32) )
      {
        *(_DWORD *)(v36 + 32) = GetCurrentThreadId();
        v7 = v36;
      }
      v8 = v36;
      if ( *(_BYTE *)(v7 + 8) )
        goto LABEL_8;
      v9 = **(__int64 ***)(v36 + 56);
      v10 = 0;
LABEL_10:
      LOBYTE(v23) = v10;
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
          v6 = 1;
          BYTE2(v23) = 1;
          if ( !*(_DWORD *)(v8 + 112) || (*(_DWORD *)(v8 + 112) & (_DWORD)v9[7]) != *(_DWORD *)(v8 + 112) )
            goto LABEL_22;
          if ( !*(_DWORD *)(v8 + 32) )
            goto LABEL_21;
          v11 = *(_DWORD *)(v8 + 32);
          if ( v11 == GetCurrentThreadId() )
          {
            v6 = BYTE2(v23);
LABEL_21:
            BYTE1(v23) = 1;
LABEL_22:
            v12 = (_QWORD *)(v9[2] + 64);
            if ( *(_QWORD *)(v9[2] + 88) > 7u )
              v12 = (_QWORD *)*v12;
            v27[0] = v12;
            VmWorkerTrace::FoundNodeToProcess<unsigned short const *,bool &>(v27, (char *)&v23 + 1);
            v5 = v9;
            *((_BYTE *)v9 + 63) = 1;
            v8 = v36;
            v10 = v23;
            break;
          }
          v6 = 0;
          v8 = v36;
          v10 = v23;
        }
      }
      if ( !v10 || v6 )
        break;
      _InterlockedDecrement((volatile signed __int32 *)(v8 + 40));
      if ( !*(_DWORD *)(v36 + 40) )
      {
        _InterlockedExchange((volatile __int32 *)(v36 + 28), -2147023765);
        ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::TraceDeviceGraph(v36);
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x100,
          (unsigned int)"onecore\\vm\\worker\\vmb\\ParallelVDevTransitionOrchestrator.h",
          v13);
      }
      SleepConditionVariableSRW((PCONDITION_VARIABLE)(v36 + 72), (PSRWLOCK)(v36 + 64), 0xFFFFFFFF, 0);
      _InterlockedAdd((volatile signed __int32 *)(v36 + 40), 1u);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v24);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v24);
    if ( !v6 )
      break;
    v27[0] = v5[2];
    v14 = (const struct Vml::VmPerfTraceOperation *)std::make_tuple<VirtualDeviceInformation *,Vml::VmPerfTraceOperation &>(
                                                      v34,
                                                      v27,
                                                      v37);
    v29 = v4;
    Vml::VmPerfTraceOperation::VmPerfTraceOperation((Vml::VmPerfTraceOperation *)v30, v14);
    v32 = *((_QWORD *)v14 + 13);
    v15 = v36;
    v16 = *v29;
    v17 = Vml::VmPerfTraceOperation::VmPerfTraceOperation(
            (Vml::VmPerfTraceOperation *)v33,
            (const struct Vml::VmPerfTraceOperation *)v30);
    v18 = lambda_85c9e02f24e13dfa4db09b9da0195f41_::operator()(v15 + 48, v32, v17, v16);
    std::wstring::_Tidy_deallocate(v31);
    std::wstring::_Tidy_deallocate(v35);
    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6___::SetResult(v36, (unsigned int)v18);
    if ( v18 < 0 && *(_BYTE *)(v36 + 9) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11E,
        (unsigned int)"onecore\\vm\\worker\\vmb\\ParallelVDevTransitionOrchestrator.h",
        (const char *)(unsigned int)v18,
        v23);
    v24 = 0;
    wil::AcquireSRWLockExclusive(&v24, v36 + 64);
    if ( *(_BYTE *)(v36 + 8) )
    {
LABEL_8:
      WakeAllConditionVariable((PCONDITION_VARIABLE)(v36 + 72));
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v24);
      std::wstring::_Tidy_deallocate(v38);
      VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread((VmWorkerTrace::VDevWorkerThread *)v39);
      v28 = 0;
      _InterlockedDecrement((volatile signed __int32 *)(v36 + 40));
      return 0xFFFFFFFFLL;
    }
    v26 |= 3u;
    v20 = (_QWORD *)v5[4];
    for ( i = (_QWORD *)*v20; i != v20; i = (_QWORD *)*i )
      --*(_DWORD *)(i[2] + 52LL);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v24);
    WakeAllConditionVariable((PCONDITION_VARIABLE)(v36 + 72));
  }
  v22 = v25;
  wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v39, v25);
  std::wstring::_Tidy_deallocate(v38);
  VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread((VmWorkerTrace::VDevWorkerThread *)v39);
  _InterlockedDecrement((volatile signed __int32 *)(v36 + 40));
  return v22;
}

```

## disassembly

```asm
0x1401015b4  push    rbx
0x1401015b6  push    rsi
0x1401015b7  push    rdi
0x1401015b8  push    r13
0x1401015ba  push    r14
0x1401015bc  push    r15
0x1401015be  sub     rsp, 398h
0x1401015c5  mov     rax, cs:__security_cookie
0x1401015cc  xor     rax, rsp
0x1401015cf  mov     [rsp+3C8h+var_48], rax
0x1401015d7  mov     [rsp+3C8h+var_394], 0
0x1401015df  mov     rax, [rdx]
0x1401015e2  mov     [rsp+3C8h+var_218], rax
0x1401015ea  test    rax, rax
0x1401015ed  jnz     short loc_1401015F9
0x1401015ef  mov     eax, 8000FFFFh
0x1401015f4  jmp     loc_140101A6D
0x1401015f9  mov     [rsp+3C8h+var_398], 0
0x140101601  mov     r14, [rdx+8]
0x140101605  mov     r13d, 1
0x14010160b  lock add [rax+28h], r13d
0x140101610  lea     rdi, [rsp+3C8h+var_218]
0x140101618  mov     [rsp+3C8h+var_388], rdi
0x14010161d  mov     [rsp+3C8h+var_380], r13b
0x140101622  xor     edx, edx; Val
0x140101624  mov     r8d, 150h; Size
0x14010162a  lea     rcx, [rsp+3C8h+var_198]; void *
0x140101632  call    memset_0
0x140101637  mov     rdx, [rsp+3C8h+var_218]
0x14010163f  lea     r8, [rdx+60h]
0x140101643  add     rdx, 50h ; 'P'
0x140101647  lea     rcx, [rsp+3C8h+var_198]; this
0x14010164f  call    VmPerf__StartRelatedActivity_VmWorkerTrace__VDevWorkerThread__GUID___
0x140101654  nop
0x140101655  mov     rdx, [rsp+3C8h+var_218]
0x14010165d  lea     r9, [rdx+50h]; struct _GUID *
0x140101661  lea     r8, [rdx+60h]; struct _GUID *
0x140101665  mov     rdx, [rdx+10h]; struct Vml::VmPerfTraceComponent *
0x140101669  lea     rcx, [rsp+3C8h+var_208]; this
0x140101671  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x140101676  nop
0x140101677  xor     esi, esi
0x140101679  mov     byte ptr [rsp+3C8h+var_3A8+1], 0
0x14010167e  xor     r15b, r15b
0x140101681  mov     [rsp+3C8h+var_3A0], 0
0x14010168a  mov     rdx, [rsp+3C8h+var_218]
0x140101692  add     rdx, 40h ; '@'
0x140101696  lea     rcx, [rsp+3C8h+var_3A0]
0x14010169b  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1401016a0  mov     rax, [rsp+3C8h+var_218]
0x1401016a8  cmp     dword ptr [rax+20h], 0
0x1401016ac  jnz     short loc_1401016CF
0x1401016ae  call    cs:__imp_GetCurrentThreadId
0x1401016b5  nop     dword ptr [rax+rax+00h]
0x1401016ba  mov     ecx, eax
0x1401016bc  mov     rax, [rsp+3C8h+var_218]
0x1401016c4  mov     [rax+20h], ecx
0x1401016c7  mov     rax, [rsp+3C8h+var_218]
0x1401016cf  mov     al, [rax+8]
0x1401016d2  mov     rcx, [rsp+3C8h+var_218]
0x1401016da  test    al, al
0x1401016dc  jz      short loc_140101729
0x1401016de  add     rcx, 48h ; 'H'; ConditionVariable
0x1401016e2  call    cs:__imp_WakeAllConditionVariable
0x1401016e9  nop     dword ptr [rax+rax+00h]
0x1401016ee  lea     rcx, [rsp+3C8h+var_3A0]
0x1401016f3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1401016f8  nop
0x1401016f9  lea     rcx, [rsp+3C8h+var_1E0]
0x140101701  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140101706  nop
0x140101707  lea     rcx, [rsp+3C8h+var_198]; this
0x14010170f  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x140101714  nop
0x140101715  mov     [rsp+3C8h+var_380], 0
0x14010171a  mov     rax, [rdi]
0x14010171d  lock dec dword ptr [rax+28h]
0x140101721  or      eax, 0FFFFFFFFh
0x140101724  jmp     loc_140101A6D
0x140101729  mov     rax, [rcx+38h]
0x14010172d  mov     rbx, [rax]
0x140101730  xor     dl, dl
0x140101732  mov     byte ptr [rsp+3C8h+var_3A8], dl; int
0x140101736  mov     rbx, [rbx]
0x140101739  mov     rax, [rcx+38h]
0x14010173d  cmp     rbx, [rax]
0x140101740  jz      loc_1401017DF
0x140101746  cmp     dword ptr [rbx+34h], 0
0x14010174a  jnz     short loc_140101797
0x14010174c  cmp     byte ptr [rbx+3Fh], 0
0x140101750  jnz     short loc_140101736
0x140101752  mov     r15b, r13b
0x140101755  mov     byte ptr [rsp+3C8h+var_3A8+2], r13b
0x14010175a  cmp     dword ptr [rcx+70h], 0
0x14010175e  jz      short loc_1401017A6
0x140101760  mov     eax, [rbx+38h]
0x140101763  and     eax, [rcx+70h]
0x140101766  cmp     eax, [rcx+70h]
0x140101769  jnz     short loc_1401017A6
0x14010176b  cmp     dword ptr [rcx+20h], 0
0x14010176f  jz      short loc_1401017A1
0x140101771  mov     r15d, [rcx+20h]
0x140101775  call    cs:__imp_GetCurrentThreadId
0x14010177c  nop     dword ptr [rax+rax+00h]
0x140101781  cmp     r15d, eax
0x140101784  jz      short loc_14010179C
0x140101786  xor     r15b, r15b
0x140101789  mov     rcx, [rsp+3C8h+var_218]
0x140101791  mov     dl, byte ptr [rsp+3C8h+var_3A8]
0x140101795  jmp     short loc_140101736
0x140101797  mov     dl, r13b
0x14010179a  jmp     short loc_140101732
0x14010179c  mov     r15b, byte ptr [rsp+3C8h+var_3A8+2]
0x1401017a1  mov     byte ptr [rsp+3C8h+var_3A8+1], r13b
0x1401017a6  mov     rax, [rbx+10h]
0x1401017aa  add     rax, 40h ; '@'
0x1401017ae  cmp     qword ptr [rax+18h], 7
0x1401017b3  jbe     short loc_1401017B8
0x1401017b5  mov     rax, [rax]
0x1401017b8  mov     [rsp+3C8h+var_390], rax
0x1401017bd  lea     rdx, [rsp+3C8h+var_3A8+1]
0x1401017c2  lea     rcx, [rsp+3C8h+var_390]
0x1401017c7  call    ??$FoundNodeToProcess@PEBGAEA_N@VmWorkerTrace@@SAX$$QEAPEBGAEA_N@Z; VmWorkerTrace::FoundNodeToProcess<ushort const *,bool &>(ushort const * &&,bool &)
0x1401017cc  mov     rsi, rbx
0x1401017cf  mov     [rbx+3Fh], r13b
0x1401017d3  mov     rcx, [rsp+3C8h+var_218]
0x1401017db  mov     dl, byte ptr [rsp+3C8h+var_3A8]
0x1401017df  test    dl, dl
0x1401017e1  jz      loc_140101872
0x1401017e7  test    r15b, r15b
0x1401017ea  jnz     loc_140101872
0x1401017f0  lock dec dword ptr [rcx+28h]
0x1401017f4  mov     rax, [rsp+3C8h+var_218]
0x1401017fc  mov     ecx, [rax+28h]
0x1401017ff  nop
0x140101800  test    ecx, ecx
0x140101802  mov     rcx, [rsp+3C8h+var_218]
0x14010180a  jnz     short loc_14010183B
0x14010180c  mov     eax, 8007046Bh
0x140101811  xchg    eax, [rcx+1Ch]
0x140101814  mov     rcx, [rsp+3C8h+var_218]
0x14010181c  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____TraceDeviceGraph
0x140101821  mov     rcx, [rsp+3C8h]; this
0x140101829  lea     r8, aOnecoreVmWorke_45; "onecore\\vm\\worker\\vmb\\ParallelVDevT"...
0x140101830  mov     edx, 100h; void *
0x140101835  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x14010183b  lea     rdx, [rcx+40h]; SRWLock
0x14010183f  add     rcx, 48h ; 'H'; ConditionVariable
0x140101843  xor     r9d, r9d; Flags
0x140101846  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x14010184a  call    cs:__imp_SleepConditionVariableSRW
0x140101851  nop     dword ptr [rax+rax+00h]
0x140101856  mov     rax, [rsp+3C8h+var_218]
0x14010185e  lock add [rax+28h], r13d
0x140101863  lea     rcx, [rsp+3C8h+var_3A0]
0x140101868  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14010186d  jmp     loc_140101681
0x140101872  lea     rcx, [rsp+3C8h+var_3A0]
0x140101877  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x14010187c  test    r15b, r15b
0x14010187f  jnz     short loc_140101886
0x140101881  jmp     loc_140101A2F
0x140101886  mov     rax, [rsi+10h]
0x14010188a  mov     [rsp+3C8h+var_390], rax
0x14010188f  lea     r8, [rsp+3C8h+var_208]
0x140101897  lea     rdx, [rsp+3C8h+var_390]
0x14010189c  lea     rcx, [rsp+3C8h+var_288]
0x1401018a4  call    ??$make_tuple@PEAUVirtualDeviceInformation@@AEAVVmPerfTraceOperation@Vml@@@std@@YA?AV?$tuple@PEAUVirtualDeviceInformation@@VVmPerfTraceOperation@Vml@@@0@$$QEAPEAUVirtualDeviceInformation@@AEAVVmPerfTraceOperation@Vml@@@Z; std::make_tuple<VirtualDeviceInformation *,Vml::VmPerfTraceOperation &>(VirtualDeviceInformation * &&,Vml::VmPerfTraceOperation &)
0x1401018a9  mov     rbx, rax
0x1401018ac  mov     [rsp+3C8h+var_378], r14
0x1401018b1  mov     rdx, rax; struct Vml::VmPerfTraceOperation *
0x1401018b4  lea     rcx, [rsp+3C8h+var_370]; this
0x1401018b9  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEBV01@@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceOperation const &)
0x1401018be  mov     rax, [rbx+68h]
0x1401018c2  mov     [rsp+3C8h+var_308], rax
0x1401018ca  mov     rbx, [rsp+3C8h+var_218]
0x1401018d2  mov     rax, [rsp+3C8h+var_378]
0x1401018d7  mov     r15d, [rax]
0x1401018da  lea     rdx, [rsp+3C8h+var_370]; struct Vml::VmPerfTraceOperation *
0x1401018df  lea     rcx, [rsp+3C8h+var_2F8]; this
0x1401018e7  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEBV01@@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceOperation const &)
0x1401018ec  mov     r9d, r15d
0x1401018ef  mov     r8, rax
0x1401018f2  mov     rdx, [rsp+3C8h+var_308]
0x1401018fa  lea     rcx, [rbx+30h]
0x1401018fe  call    _lambda_85c9e02f24e13dfa4db09b9da0195f41___operator__
0x140101903  mov     ebx, eax
0x140101905  lea     rcx, [rsp+3C8h+var_348]
0x14010190d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140101912  nop
0x140101913  lea     rcx, [rsp+3C8h+var_260]
0x14010191b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140101920  mov     edx, ebx
0x140101922  mov     rcx, [rsp+3C8h+var_218]
0x14010192a  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x14010192f  mov     rdx, [rsp+3C8h+var_218]
0x140101937  test    ebx, ebx
0x140101939  jns     short loc_140101946
0x14010193b  cmp     byte ptr [rdx+9], 0
0x14010193f  jz      short loc_140101946
0x140101941  mov     al, r13b
0x140101944  jmp     short loc_140101948
0x140101946  xor     al, al
0x140101948  mov     rcx, [rsp+3C8h]; this
0x140101950  test    al, al
0x140101952  jz      short loc_140101968
0x140101954  mov     r9d, ebx; char *
0x140101957  lea     r8, aOnecoreVmWorke_45; "onecore\\vm\\worker\\vmb\\ParallelVDevT"...
0x14010195e  mov     edx, 11Eh; void *
0x140101963  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140101968  mov     [rsp+3C8h+var_3A0], 0
0x140101971  add     rdx, 40h ; '@'
0x140101975  lea     rcx, [rsp+3C8h+var_3A0]
0x14010197a  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x14010197f  mov     rax, [rsp+3C8h+var_218]
0x140101987  mov     cl, [rax+8]
0x14010198a  test    cl, cl
0x14010198c  jz      short loc_1401019E1
0x14010198e  mov     rcx, [rsp+3C8h+var_218]
0x140101996  add     rcx, 48h ; 'H'; ConditionVariable
0x14010199a  call    cs:__imp_WakeAllConditionVariable
0x1401019a1  nop     dword ptr [rax+rax+00h]
0x1401019a6  lea     rcx, [rsp+3C8h+var_3A0]
0x1401019ab  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1401019b0  nop
0x1401019b1  lea     rcx, [rsp+3C8h+var_1E0]
0x1401019b9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1401019be  nop
0x1401019bf  lea     rcx, [rsp+3C8h+var_198]; this
0x1401019c7  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x1401019cc  nop
0x1401019cd  mov     [rsp+3C8h+var_380], 0
0x1401019d2  mov     rax, [rdi]
0x1401019d5  lock dec dword ptr [rax+28h]
0x1401019d9  or      eax, 0FFFFFFFFh
0x1401019dc  jmp     loc_140101A6D
0x1401019e1  or      [rsp+3C8h+var_394], 3
0x1401019e6  mov     rcx, [rsi+20h]
0x1401019ea  mov     rax, [rcx]
0x1401019ed  cmp     rax, rcx
0x1401019f0  jz      short loc_1401019FE
0x1401019f2  mov     rdx, [rax+10h]
0x1401019f6  dec     dword ptr [rdx+34h]
0x1401019f9  mov     rax, [rax]
0x1401019fc  jmp     short loc_1401019ED
0x1401019fe  lea     rcx, [rsp+3C8h+var_3A0]
0x140101a03  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140101a08  mov     rcx, [rsp+3C8h+var_218]
0x140101a10  add     rcx, 48h ; 'H'; ConditionVariable
0x140101a14  call    cs:__imp_WakeAllConditionVariable
0x140101a1b  nop     dword ptr [rax+rax+00h]
0x140101a20  jmp     loc_140101679
0x140101a25  mov     r13b, [rsp+3C8h+var_380]
0x140101a2a  mov     rdi, [rsp+3C8h+var_388]
0x140101a2f  mov     ebx, [rsp+3C8h+var_398]
0x140101a33  mov     edx, ebx
0x140101a35  lea     rcx, [rsp+3C8h+var_198]
0x140101a3d  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140101a42  nop
0x140101a43  lea     rcx, [rsp+3C8h+var_1E0]
0x140101a4b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140101a50  nop
0x140101a51  lea     rcx, [rsp+3C8h+var_198]; this
0x140101a59  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x140101a5e  nop
0x140101a5f  test    r13b, r13b
0x140101a62  jz      short loc_140101A6B
0x140101a64  mov     rcx, [rdi]
0x140101a67  lock dec dword ptr [rcx+28h]
0x140101a6b  mov     eax, ebx
0x140101a6d  mov     rcx, [rsp+3C8h+var_48]
0x140101a75  xor     rcx, rsp; StackCookie
0x140101a78  call    __security_check_cookie
0x140101a7d  add     rsp, 398h
0x140101a84  pop     r15
0x140101a86  pop     r14
0x140101a88  pop     r13
0x140101a8a  pop     rdi
0x140101a8b  pop     rsi
0x140101a8c  pop     rbx
0x140101a8d  retn
```
