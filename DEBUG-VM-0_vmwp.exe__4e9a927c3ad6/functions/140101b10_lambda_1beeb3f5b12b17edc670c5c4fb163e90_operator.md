# _lambda_1beeb3f5b12b17edc670c5c4fb163e90_::operator()

- ea: `0x140101b10`
- end: `0x140101feb`
- name: `_lambda_1beeb3f5b12b17edc670c5c4fb163e90_::operator()`
- size: `1243`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14027e890`

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
- `0x140101a98`
- `0x140101b10`
- `0x140132940`
- `0x1401335fc`
- `0x140281188`
- `0x140282e3c`
- `0x140283890`
- `0x140284054`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140101c0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140101cd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140101c0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140101cd1`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140101c3e`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140101ef6`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140101f70`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140101c3e`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140101ef6`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140101f70`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x140101da6`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x140101da6`

## pseudocode

```c
__int64 __fastcall lambda_1beeb3f5b12b17edc670c5c4fb163e90_::operator()(__int64 a1, __int64 *a2)
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
    v18 = lambda_ae232efc167169ec614a6d5435ac4ed5_::operator()(v15 + 48, v32, v17, v16);
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
0x140101b10  push    rbx
0x140101b12  push    rsi
0x140101b13  push    rdi
0x140101b14  push    r13
0x140101b16  push    r14
0x140101b18  push    r15
0x140101b1a  sub     rsp, 398h
0x140101b21  mov     rax, cs:__security_cookie
0x140101b28  xor     rax, rsp
0x140101b2b  mov     [rsp+3C8h+var_48], rax
0x140101b33  mov     [rsp+3C8h+var_394], 0
0x140101b3b  mov     rax, [rdx]
0x140101b3e  mov     [rsp+3C8h+var_218], rax
0x140101b46  test    rax, rax
0x140101b49  jnz     short loc_140101B55
0x140101b4b  mov     eax, 8000FFFFh
0x140101b50  jmp     loc_140101FC9
0x140101b55  mov     [rsp+3C8h+var_398], 0
0x140101b5d  mov     r14, [rdx+8]
0x140101b61  mov     r13d, 1
0x140101b67  lock add [rax+28h], r13d
0x140101b6c  lea     rdi, [rsp+3C8h+var_218]
0x140101b74  mov     [rsp+3C8h+var_388], rdi
0x140101b79  mov     [rsp+3C8h+var_380], r13b
0x140101b7e  xor     edx, edx; Val
0x140101b80  mov     r8d, 150h; Size
0x140101b86  lea     rcx, [rsp+3C8h+var_198]; void *
0x140101b8e  call    memset_0
0x140101b93  mov     rdx, [rsp+3C8h+var_218]
0x140101b9b  lea     r8, [rdx+60h]
0x140101b9f  add     rdx, 50h ; 'P'
0x140101ba3  lea     rcx, [rsp+3C8h+var_198]; this
0x140101bab  call    VmPerf__StartRelatedActivity_VmWorkerTrace__VDevWorkerThread__GUID___
0x140101bb0  nop
0x140101bb1  mov     rdx, [rsp+3C8h+var_218]
0x140101bb9  lea     r9, [rdx+50h]; struct _GUID *
0x140101bbd  lea     r8, [rdx+60h]; struct _GUID *
0x140101bc1  mov     rdx, [rdx+10h]; struct Vml::VmPerfTraceComponent *
0x140101bc5  lea     rcx, [rsp+3C8h+var_208]; this
0x140101bcd  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEAVVmPerfTraceComponent@1@AEBU_GUID@@1@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceComponent &,_GUID const &,_GUID const &)
0x140101bd2  nop
0x140101bd3  xor     esi, esi
0x140101bd5  mov     byte ptr [rsp+3C8h+var_3A8+1], 0
0x140101bda  xor     r15b, r15b
0x140101bdd  mov     [rsp+3C8h+var_3A0], 0
0x140101be6  mov     rdx, [rsp+3C8h+var_218]
0x140101bee  add     rdx, 40h ; '@'
0x140101bf2  lea     rcx, [rsp+3C8h+var_3A0]
0x140101bf7  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x140101bfc  mov     rax, [rsp+3C8h+var_218]
0x140101c04  cmp     dword ptr [rax+20h], 0
0x140101c08  jnz     short loc_140101C2B
0x140101c0a  call    cs:__imp_GetCurrentThreadId
0x140101c11  nop     dword ptr [rax+rax+00h]
0x140101c16  mov     ecx, eax
0x140101c18  mov     rax, [rsp+3C8h+var_218]
0x140101c20  mov     [rax+20h], ecx
0x140101c23  mov     rax, [rsp+3C8h+var_218]
0x140101c2b  mov     al, [rax+8]
0x140101c2e  mov     rcx, [rsp+3C8h+var_218]
0x140101c36  test    al, al
0x140101c38  jz      short loc_140101C85
0x140101c3a  add     rcx, 48h ; 'H'; ConditionVariable
0x140101c3e  call    cs:__imp_WakeAllConditionVariable
0x140101c45  nop     dword ptr [rax+rax+00h]
0x140101c4a  lea     rcx, [rsp+3C8h+var_3A0]
0x140101c4f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140101c54  nop
0x140101c55  lea     rcx, [rsp+3C8h+var_1E0]
0x140101c5d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140101c62  nop
0x140101c63  lea     rcx, [rsp+3C8h+var_198]; this
0x140101c6b  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x140101c70  nop
0x140101c71  mov     [rsp+3C8h+var_380], 0
0x140101c76  mov     rax, [rdi]
0x140101c79  lock dec dword ptr [rax+28h]
0x140101c7d  or      eax, 0FFFFFFFFh
0x140101c80  jmp     loc_140101FC9
0x140101c85  mov     rax, [rcx+38h]
0x140101c89  mov     rbx, [rax]
0x140101c8c  xor     dl, dl
0x140101c8e  mov     byte ptr [rsp+3C8h+var_3A8], dl; int
0x140101c92  mov     rbx, [rbx]
0x140101c95  mov     rax, [rcx+38h]
0x140101c99  cmp     rbx, [rax]
0x140101c9c  jz      loc_140101D3B
0x140101ca2  cmp     dword ptr [rbx+34h], 0
0x140101ca6  jnz     short loc_140101CF3
0x140101ca8  cmp     byte ptr [rbx+3Fh], 0
0x140101cac  jnz     short loc_140101C92
0x140101cae  mov     r15b, r13b
0x140101cb1  mov     byte ptr [rsp+3C8h+var_3A8+2], r13b
0x140101cb6  cmp     dword ptr [rcx+70h], 0
0x140101cba  jz      short loc_140101D02
0x140101cbc  mov     eax, [rbx+38h]
0x140101cbf  and     eax, [rcx+70h]
0x140101cc2  cmp     eax, [rcx+70h]
0x140101cc5  jnz     short loc_140101D02
0x140101cc7  cmp     dword ptr [rcx+20h], 0
0x140101ccb  jz      short loc_140101CFD
0x140101ccd  mov     r15d, [rcx+20h]
0x140101cd1  call    cs:__imp_GetCurrentThreadId
0x140101cd8  nop     dword ptr [rax+rax+00h]
0x140101cdd  cmp     r15d, eax
0x140101ce0  jz      short loc_140101CF8
0x140101ce2  xor     r15b, r15b
0x140101ce5  mov     rcx, [rsp+3C8h+var_218]
0x140101ced  mov     dl, byte ptr [rsp+3C8h+var_3A8]
0x140101cf1  jmp     short loc_140101C92
0x140101cf3  mov     dl, r13b
0x140101cf6  jmp     short loc_140101C8E
0x140101cf8  mov     r15b, byte ptr [rsp+3C8h+var_3A8+2]
0x140101cfd  mov     byte ptr [rsp+3C8h+var_3A8+1], r13b
0x140101d02  mov     rax, [rbx+10h]
0x140101d06  add     rax, 40h ; '@'
0x140101d0a  cmp     qword ptr [rax+18h], 7
0x140101d0f  jbe     short loc_140101D14
0x140101d11  mov     rax, [rax]
0x140101d14  mov     [rsp+3C8h+var_390], rax
0x140101d19  lea     rdx, [rsp+3C8h+var_3A8+1]
0x140101d1e  lea     rcx, [rsp+3C8h+var_390]
0x140101d23  call    ??$FoundNodeToProcess@PEBGAEA_N@VmWorkerTrace@@SAX$$QEAPEBGAEA_N@Z; VmWorkerTrace::FoundNodeToProcess<ushort const *,bool &>(ushort const * &&,bool &)
0x140101d28  mov     rsi, rbx
0x140101d2b  mov     [rbx+3Fh], r13b
0x140101d2f  mov     rcx, [rsp+3C8h+var_218]
0x140101d37  mov     dl, byte ptr [rsp+3C8h+var_3A8]
0x140101d3b  test    dl, dl
0x140101d3d  jz      loc_140101DCE
0x140101d43  test    r15b, r15b
0x140101d46  jnz     loc_140101DCE
0x140101d4c  lock dec dword ptr [rcx+28h]
0x140101d50  mov     rax, [rsp+3C8h+var_218]
0x140101d58  mov     ecx, [rax+28h]
0x140101d5b  nop
0x140101d5c  test    ecx, ecx
0x140101d5e  mov     rcx, [rsp+3C8h+var_218]
0x140101d66  jnz     short loc_140101D97
0x140101d68  mov     eax, 8007046Bh
0x140101d6d  xchg    eax, [rcx+1Ch]
0x140101d70  mov     rcx, [rsp+3C8h+var_218]
0x140101d78  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____TraceDeviceGraph
0x140101d7d  mov     rcx, [rsp+3C8h]; this
0x140101d85  lea     r8, aOnecoreVmWorke_45; "onecore\\vm\\worker\\vmb\\ParallelVDevT"...
0x140101d8c  mov     edx, 100h; void *
0x140101d91  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140101d97  lea     rdx, [rcx+40h]; SRWLock
0x140101d9b  add     rcx, 48h ; 'H'; ConditionVariable
0x140101d9f  xor     r9d, r9d; Flags
0x140101da2  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x140101da6  call    cs:__imp_SleepConditionVariableSRW
0x140101dad  nop     dword ptr [rax+rax+00h]
0x140101db2  mov     rax, [rsp+3C8h+var_218]
0x140101dba  lock add [rax+28h], r13d
0x140101dbf  lea     rcx, [rsp+3C8h+var_3A0]
0x140101dc4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140101dc9  jmp     loc_140101BDD
0x140101dce  lea     rcx, [rsp+3C8h+var_3A0]
0x140101dd3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140101dd8  test    r15b, r15b
0x140101ddb  jnz     short loc_140101DE2
0x140101ddd  jmp     loc_140101F8B
0x140101de2  mov     rax, [rsi+10h]
0x140101de6  mov     [rsp+3C8h+var_390], rax
0x140101deb  lea     r8, [rsp+3C8h+var_208]
0x140101df3  lea     rdx, [rsp+3C8h+var_390]
0x140101df8  lea     rcx, [rsp+3C8h+var_288]
0x140101e00  call    ??$make_tuple@PEAUVirtualDeviceInformation@@AEAVVmPerfTraceOperation@Vml@@@std@@YA?AV?$tuple@PEAUVirtualDeviceInformation@@VVmPerfTraceOperation@Vml@@@0@$$QEAPEAUVirtualDeviceInformation@@AEAVVmPerfTraceOperation@Vml@@@Z; std::make_tuple<VirtualDeviceInformation *,Vml::VmPerfTraceOperation &>(VirtualDeviceInformation * &&,Vml::VmPerfTraceOperation &)
0x140101e05  mov     rbx, rax
0x140101e08  mov     [rsp+3C8h+var_378], r14
0x140101e0d  mov     rdx, rax; struct Vml::VmPerfTraceOperation *
0x140101e10  lea     rcx, [rsp+3C8h+var_370]; this
0x140101e15  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEBV01@@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceOperation const &)
0x140101e1a  mov     rax, [rbx+68h]
0x140101e1e  mov     [rsp+3C8h+var_308], rax
0x140101e26  mov     rbx, [rsp+3C8h+var_218]
0x140101e2e  mov     rax, [rsp+3C8h+var_378]
0x140101e33  mov     r15d, [rax]
0x140101e36  lea     rdx, [rsp+3C8h+var_370]; struct Vml::VmPerfTraceOperation *
0x140101e3b  lea     rcx, [rsp+3C8h+var_2F8]; this
0x140101e43  call    ??0VmPerfTraceOperation@Vml@@QEAA@AEBV01@@Z; Vml::VmPerfTraceOperation::VmPerfTraceOperation(Vml::VmPerfTraceOperation const &)
0x140101e48  mov     r9d, r15d
0x140101e4b  mov     r8, rax
0x140101e4e  mov     rdx, [rsp+3C8h+var_308]
0x140101e56  lea     rcx, [rbx+30h]
0x140101e5a  call    _lambda_ae232efc167169ec614a6d5435ac4ed5___operator__
0x140101e5f  mov     ebx, eax
0x140101e61  lea     rcx, [rsp+3C8h+var_348]
0x140101e69  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140101e6e  nop
0x140101e6f  lea     rcx, [rsp+3C8h+var_260]
0x140101e77  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140101e7c  mov     edx, ebx
0x140101e7e  mov     rcx, [rsp+3C8h+var_218]
0x140101e86  call    ParallelVDevTransitionOrchestrator__lambda_bfaf703db63e015698673ef70c5ed4c6_____SetResult
0x140101e8b  mov     rdx, [rsp+3C8h+var_218]
0x140101e93  test    ebx, ebx
0x140101e95  jns     short loc_140101EA2
0x140101e97  cmp     byte ptr [rdx+9], 0
0x140101e9b  jz      short loc_140101EA2
0x140101e9d  mov     al, r13b
0x140101ea0  jmp     short loc_140101EA4
0x140101ea2  xor     al, al
0x140101ea4  mov     rcx, [rsp+3C8h]; this
0x140101eac  test    al, al
0x140101eae  jz      short loc_140101EC4
0x140101eb0  mov     r9d, ebx; char *
0x140101eb3  lea     r8, aOnecoreVmWorke_45; "onecore\\vm\\worker\\vmb\\ParallelVDevT"...
0x140101eba  mov     edx, 11Eh; void *
0x140101ebf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140101ec4  mov     [rsp+3C8h+var_3A0], 0
0x140101ecd  add     rdx, 40h ; '@'
0x140101ed1  lea     rcx, [rsp+3C8h+var_3A0]
0x140101ed6  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x140101edb  mov     rax, [rsp+3C8h+var_218]
0x140101ee3  mov     cl, [rax+8]
0x140101ee6  test    cl, cl
0x140101ee8  jz      short loc_140101F3D
0x140101eea  mov     rcx, [rsp+3C8h+var_218]
0x140101ef2  add     rcx, 48h ; 'H'; ConditionVariable
0x140101ef6  call    cs:__imp_WakeAllConditionVariable
0x140101efd  nop     dword ptr [rax+rax+00h]
0x140101f02  lea     rcx, [rsp+3C8h+var_3A0]
0x140101f07  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140101f0c  nop
0x140101f0d  lea     rcx, [rsp+3C8h+var_1E0]
0x140101f15  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140101f1a  nop
0x140101f1b  lea     rcx, [rsp+3C8h+var_198]; this
0x140101f23  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x140101f28  nop
0x140101f29  mov     [rsp+3C8h+var_380], 0
0x140101f2e  mov     rax, [rdi]
0x140101f31  lock dec dword ptr [rax+28h]
0x140101f35  or      eax, 0FFFFFFFFh
0x140101f38  jmp     loc_140101FC9
0x140101f3d  or      [rsp+3C8h+var_394], 3
0x140101f42  mov     rcx, [rsi+20h]
0x140101f46  mov     rax, [rcx]
0x140101f49  cmp     rax, rcx
0x140101f4c  jz      short loc_140101F5A
0x140101f4e  mov     rdx, [rax+10h]
0x140101f52  dec     dword ptr [rdx+34h]
0x140101f55  mov     rax, [rax]
0x140101f58  jmp     short loc_140101F49
0x140101f5a  lea     rcx, [rsp+3C8h+var_3A0]
0x140101f5f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140101f64  mov     rcx, [rsp+3C8h+var_218]
0x140101f6c  add     rcx, 48h ; 'H'; ConditionVariable
0x140101f70  call    cs:__imp_WakeAllConditionVariable
0x140101f77  nop     dword ptr [rax+rax+00h]
0x140101f7c  jmp     loc_140101BD5
0x140101f81  mov     r13b, [rsp+3C8h+var_380]
0x140101f86  mov     rdi, [rsp+3C8h+var_388]
0x140101f8b  mov     ebx, [rsp+3C8h+var_398]
0x140101f8f  mov     edx, ebx
0x140101f91  lea     rcx, [rsp+3C8h+var_198]
0x140101f99  call    ?Stop@?$ActivityBase@VVmWorkerTrace@@$0A@$0CA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<VmWorkerTrace,0,32,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140101f9e  nop
0x140101f9f  lea     rcx, [rsp+3C8h+var_1E0]
0x140101fa7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140101fac  nop
0x140101fad  lea     rcx, [rsp+3C8h+var_198]; this
0x140101fb5  call    ??1VDevWorkerThread@VmWorkerTrace@@QEAA@XZ; VmWorkerTrace::VDevWorkerThread::~VDevWorkerThread(void)
0x140101fba  nop
0x140101fbb  test    r13b, r13b
0x140101fbe  jz      short loc_140101FC7
0x140101fc0  mov     rcx, [rdi]
0x140101fc3  lock dec dword ptr [rcx+28h]
0x140101fc7  mov     eax, ebx
0x140101fc9  mov     rcx, [rsp+3C8h+var_48]
0x140101fd1  xor     rcx, rsp; StackCookie
0x140101fd4  call    __security_check_cookie
0x140101fd9  add     rsp, 398h
0x140101fe0  pop     r15
0x140101fe2  pop     r14
0x140101fe4  pop     r13
0x140101fe6  pop     rdi
0x140101fe7  pop     rsi
0x140101fe8  pop     rbx
0x140101fe9  retn
```
