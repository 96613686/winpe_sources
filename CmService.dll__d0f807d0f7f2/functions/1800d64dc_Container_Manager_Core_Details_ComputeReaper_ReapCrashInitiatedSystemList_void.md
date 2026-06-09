# Container::Manager::Core::Details::ComputeReaper::ReapCrashInitiatedSystemList(void)

- ea: `0x1800d64dc`
- end: `0x1800d6821`
- name: `?ReapCrashInitiatedSystemList@ComputeReaper@Details@Core@Manager@Container@@AEAA_NXZ`
- size: `837`
- prototype: `bool __fastcall(PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800d5590`

## callees

- `0x180004bf4`
- `0x180066670`
- `0x1800d64dc`
- `0x180125bb0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d6776`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800d6776`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d65ff`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d65ff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d6737`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d6737`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800d66c2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800d67b1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800d66c2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800d67b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d6503`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d6670`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d6751`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d67c5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d6503`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d6670`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d6751`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d67c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d659f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d6702`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d678a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d67f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d659f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d6702`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d678a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d67f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d66b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d66b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d66d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d66d0`

## pseudocode

```c
char __fastcall Container::Manager::Core::Details::ComputeReaper::ReapCrashInitiatedSystemList(PSRWLOCK SRWLock)
{
  PSRWLOCK v2; // rsi
  RTL_SRWLOCK *Ptr; // rdx
  PSRWLOCK *v4; // rax
  PSRWLOCK v5; // rax
  PSRWLOCK **v6; // rcx
  char v7; // r15
  PSRWLOCK *v8; // rdi
  PSRWLOCK v9; // rax
  PSRWLOCK *v10; // r13
  struct _TP_TIMER *ThreadpoolTimer; // rbx
  _QWORD *v12; // rax
  _QWORD *v13; // r15
  PSRWLOCK *v14; // rcx
  struct _TP_TIMER **v15; // r12
  struct _TP_TIMER *v16; // r13
  DWORD LastError; // edi
  struct _TP_TIMER *v18; // rcx
  __int64 v19; // rax
  PVOID v20; // r15
  bool v21; // zf
  PSRWLOCK *v22; // rax
  char v24; // [rsp+20h] [rbp-28h] BYREF
  PSRWLOCK v25; // [rsp+28h] [rbp-20h] BYREF
  PSRWLOCK **v26; // [rsp+30h] [rbp-18h]
  char v27; // [rsp+90h] [rbp+48h]
  struct _FILETIME pftDueTime; // [rsp+98h] [rbp+50h] BYREF
  _QWORD *v29; // [rsp+A0h] [rbp+58h] BYREF
  PSRWLOCK *v30; // [rsp+A8h] [rbp+60h]

  v26 = (PSRWLOCK **)&v25;
  v25 = (PSRWLOCK)&v25;
  AcquireSRWLockExclusive(SRWLock);
  v2 = SRWLock + 2;
  Ptr = (RTL_SRWLOCK *)SRWLock[2].Ptr;
  if ( Ptr != &SRWLock[2] )
  {
    if ( Ptr[1].Ptr != v2
      || (v4 = (PSRWLOCK *)SRWLock[3].Ptr, *v4 != v2)
      || (*v4 = Ptr, Ptr[1].Ptr = v4, v5 = v25, SRWLock[3].Ptr = &SRWLock[2], v2->Ptr = v2, v5[1].Ptr != &v25)
      || (v6 = v26, *v26 != &v25)
      || *((RTL_SRWLOCK **)Ptr->Ptr + 1) != Ptr
      || *(RTL_SRWLOCK **)Ptr[1].Ptr != Ptr )
    {
LABEL_38:
      __fastfail(3u);
    }
    *v26 = (PSRWLOCK *)Ptr;
    v26 = (PSRWLOCK **)Ptr[1].Ptr;
    *(_QWORD *)Ptr[1].Ptr = &v25;
    Ptr[1].Ptr = v6;
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v7 = 0;
  v27 = 0;
  while ( 1 )
  {
    v8 = (PSRWLOCK *)v25;
    if ( v25 == (PSRWLOCK)&v25 )
      return v7;
    if ( v25[1].Ptr != &v25 )
      goto LABEL_38;
    v9 = (PSRWLOCK)v25->Ptr;
    if ( *((PSRWLOCK *)v25->Ptr + 1) != v25 )
      goto LABEL_38;
    v25 = (PSRWLOCK)v25->Ptr;
    v10 = v8 - 1;
    v9[1].Ptr = &v25;
    v30 = v8 - 1;
    ThreadpoolTimer = CreateThreadpoolTimer(
                        Container::Manager::Core::Details::ComputeReaper::OnCrashDumpCollectionTimeout,
                        v8 - 1,
                        0);
    v12 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v13 = v12;
    if ( v12 )
    {
      *v12 = 0;
      v12[1] = 0;
      v12[2] = 0;
    }
    else
    {
      v13 = 0;
    }
    v29 = v13;
    if ( ThreadpoolTimer
      && v13
      && (int)Container::Manager::Hcs::ComputeSystem::WatchForCrashDumpCollectionCompletion(v10[4], v13) >= 0 )
    {
      AcquireSRWLockExclusive(SRWLock);
      v14 = (PSRWLOCK *)SRWLock[5].Ptr;
      if ( *v14 != &SRWLock[4] )
        goto LABEL_38;
      *v8 = SRWLock + 4;
      v15 = (struct _TP_TIMER **)(v10 + 6);
      v8[1] = (PSRWLOCK)v14;
      *v14 = (PSRWLOCK)v8;
      SRWLock[5].Ptr = v8;
      if ( v10 + 6 != (PSRWLOCK *)&v24 )
      {
        v16 = *v15;
        if ( *v15 )
        {
          LastError = GetLastError();
          CloseThreadpoolTimer(v16);
          SetLastError(LastError);
        }
        v10 = v30;
        *v15 = ThreadpoolTimer;
        ThreadpoolTimer = 0;
      }
      v29 = 0;
      wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(v10 + 7, v13);
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      v18 = *v15;
      v19 = -10000LL * *((unsigned int *)v10 + 10);
      pftDueTime.dwLowDateTime = -10000 * *((_DWORD *)v10 + 10);
      pftDueTime.dwHighDateTime = HIDWORD(v19);
      SetThreadpoolTimer(v18, &pftDueTime, 0, 0x3E8u);
      v20 = v10[7]->Ptr;
      AcquireSRWLockExclusive((PSRWLOCK)v20 + 1);
      v21 = *(_DWORD *)v20 == 2;
      *((_QWORD *)v20 + 2) = Container::Manager::Core::Details::ComputeReaper::OnCrashDumpCollectionCompleted;
      *((_QWORD *)v20 + 3) = v10;
      if ( v21 )
        SubmitThreadpoolWork(*((PTP_WORK *)v20 + 4));
      if ( v20 != (PVOID)-8LL )
        ReleaseSRWLockExclusive((PSRWLOCK)v20 + 1);
      v7 = v27;
    }
    else
    {
      AcquireSRWLockExclusive(SRWLock);
      v22 = (PSRWLOCK *)SRWLock[3].Ptr;
      if ( *v22 != v2 )
        goto LABEL_38;
      *v8 = v2;
      v7 = 1;
      v8[1] = (PSRWLOCK)v22;
      *v22 = (PSRWLOCK)v8;
      v27 = 1;
      SRWLock[3].Ptr = v8;
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
    }
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&v29, 0);
    if ( ThreadpoolTimer )
      CloseThreadpoolTimer(ThreadpoolTimer);
  }
}

```

## disassembly

```asm
0x1800d64dc  push    rbp
0x1800d64de  push    rbx
0x1800d64df  push    rsi
0x1800d64e0  push    rdi
0x1800d64e1  push    r12
0x1800d64e3  push    r13
0x1800d64e5  push    r14
0x1800d64e7  push    r15
0x1800d64e9  mov     rbp, rsp
0x1800d64ec  sub     rsp, 48h
0x1800d64f0  lea     rax, [rbp+var_20]
0x1800d64f4  mov     r14, rcx
0x1800d64f7  mov     [rbp+var_18], rax
0x1800d64fb  lea     rax, [rbp+var_20]
0x1800d64ff  mov     [rbp+var_20], rax
0x1800d6503  call    cs:__imp_AcquireSRWLockExclusive
0x1800d650a  nop     dword ptr [rax+rax+00h]
0x1800d650f  lea     rsi, [r14+10h]
0x1800d6513  mov     rdx, [rsi]
0x1800d6516  cmp     rdx, rsi
0x1800d6519  jz      short loc_1800D6597
0x1800d651b  cmp     [rdx+8], rsi
0x1800d651f  jnz     loc_1800D6805
0x1800d6525  mov     rax, [rsi+8]
0x1800d6529  cmp     [rax], rsi
0x1800d652c  jnz     loc_1800D6805
0x1800d6532  mov     [rax], rdx
0x1800d6535  lea     rcx, [rbp+var_20]
0x1800d6539  mov     [rdx+8], rax
0x1800d653d  mov     rax, [rbp+var_20]
0x1800d6541  mov     [rsi+8], rsi
0x1800d6545  mov     [rsi], rsi
0x1800d6548  cmp     [rax+8], rcx
0x1800d654c  jnz     loc_1800D6805
0x1800d6552  mov     rcx, [rbp+var_18]
0x1800d6556  lea     rax, [rbp+var_20]
0x1800d655a  cmp     [rcx], rax
0x1800d655d  jnz     loc_1800D6805
0x1800d6563  mov     rax, [rdx]
0x1800d6566  cmp     [rax+8], rdx
0x1800d656a  jnz     loc_1800D6805
0x1800d6570  mov     rax, [rdx+8]
0x1800d6574  cmp     [rax], rdx
0x1800d6577  jnz     loc_1800D6805
0x1800d657d  mov     [rcx], rdx
0x1800d6580  lea     r8, [rbp+var_20]
0x1800d6584  mov     rax, [rdx+8]
0x1800d6588  mov     [rbp+var_18], rax
0x1800d658c  mov     rax, [rdx+8]
0x1800d6590  mov     [rax], r8
0x1800d6593  mov     [rdx+8], rcx
0x1800d6597  test    r14, r14
0x1800d659a  jz      short loc_1800D65AB
0x1800d659c  mov     rcx, r14; SRWLock
0x1800d659f  call    cs:__imp_ReleaseSRWLockExclusive
0x1800d65a6  nop     dword ptr [rax+rax+00h]
0x1800d65ab  xor     r15b, r15b
0x1800d65ae  mov     [rbp+arg_0], r15b
0x1800d65b2  mov     rdi, [rbp+var_20]
0x1800d65b6  lea     rax, [rbp+var_20]
0x1800d65ba  cmp     rdi, rax
0x1800d65bd  jz      loc_1800D680C
0x1800d65c3  lea     rax, [rbp+var_20]
0x1800d65c7  cmp     [rdi+8], rax
0x1800d65cb  jnz     loc_1800D6805
0x1800d65d1  mov     rax, [rdi]
0x1800d65d4  cmp     [rax+8], rdi
0x1800d65d8  jnz     loc_1800D6805
0x1800d65de  lea     rcx, [rbp+var_20]
0x1800d65e2  mov     [rbp+var_20], rax
0x1800d65e6  lea     r13, [rdi-8]
0x1800d65ea  mov     [rax+8], rcx
0x1800d65ee  lea     rcx, ?OnCrashDumpCollectionTimeout@ComputeReaper@Details@Core@Manager@Container@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800d65f5  mov     [rbp+arg_18], r13
0x1800d65f9  xor     r8d, r8d; pcbe
0x1800d65fc  mov     rdx, r13; pv
0x1800d65ff  call    cs:__imp_CreateThreadpoolTimer
0x1800d6606  nop     dword ptr [rax+rax+00h]
0x1800d660b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800d6612  mov     ecx, 18h; unsigned __int64
0x1800d6617  mov     rbx, rax
0x1800d661a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800d661f  mov     r15, rax
0x1800d6622  test    rax, rax
0x1800d6625  jz      short loc_1800D6640
0x1800d6627  mov     qword ptr [rax], 0
0x1800d662e  mov     qword ptr [rax+8], 0
0x1800d6636  mov     qword ptr [rax+10h], 0
0x1800d663e  jmp     short loc_1800D6643
0x1800d6640  xor     r15d, r15d
0x1800d6643  mov     [rbp+arg_10], r15
0x1800d6647  test    rbx, rbx
0x1800d664a  jz      loc_1800D67C2
0x1800d6650  test    r15, r15
0x1800d6653  jz      loc_1800D67C2
0x1800d6659  mov     rcx, [r13+20h]
0x1800d665d  mov     rdx, r15
0x1800d6660  call    ?WatchForCrashDumpCollectionCompletion@ComputeSystem@Hcs@Manager@Container@@QEAAJAEAV?$AsyncOperation@X@Csl@@@Z; Container::Manager::Hcs::ComputeSystem::WatchForCrashDumpCollectionCompletion(Csl::AsyncOperation<void> &)
0x1800d6665  test    eax, eax
0x1800d6667  js      loc_1800D67C2
0x1800d666d  mov     rcx, r14; SRWLock
0x1800d6670  call    cs:__imp_AcquireSRWLockExclusive
0x1800d6677  nop     dword ptr [rax+rax+00h]
0x1800d667c  lea     rax, [r14+20h]
0x1800d6680  mov     rcx, [rax+8]
0x1800d6684  cmp     [rcx], rax
0x1800d6687  jnz     loc_1800D6805
0x1800d668d  mov     [rdi], rax
0x1800d6690  lea     r12, [r13+30h]
0x1800d6694  mov     [rdi+8], rcx
0x1800d6698  mov     [rcx], rdi
0x1800d669b  mov     [rax+8], rdi
0x1800d669f  lea     rax, [rbp+var_28]
0x1800d66a3  cmp     r12, rax
0x1800d66a6  jz      short loc_1800D66E6
0x1800d66a8  mov     r13, [r12]
0x1800d66ac  test    r13, r13
0x1800d66af  jz      short loc_1800D66DC
0x1800d66b1  call    cs:__imp_GetLastError
0x1800d66b8  nop     dword ptr [rax+rax+00h]
0x1800d66bd  mov     rcx, r13; pti
0x1800d66c0  mov     edi, eax
0x1800d66c2  call    cs:__imp_CloseThreadpoolTimer
0x1800d66c9  nop     dword ptr [rax+rax+00h]
0x1800d66ce  mov     ecx, edi; dwErrCode
0x1800d66d0  call    cs:__imp_SetLastError
0x1800d66d7  nop     dword ptr [rax+rax+00h]
0x1800d66dc  mov     r13, [rbp+arg_18]
0x1800d66e0  mov     [r12], rbx
0x1800d66e4  xor     ebx, ebx
0x1800d66e6  mov     rdx, r15
0x1800d66e9  mov     [rbp+arg_10], 0
0x1800d66f1  lea     rcx, [r13+38h]
0x1800d66f5  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x1800d66fa  test    r14, r14
0x1800d66fd  jz      short loc_1800D670E
0x1800d66ff  mov     rcx, r14; SRWLock
0x1800d6702  call    cs:__imp_ReleaseSRWLockExclusive
0x1800d6709  nop     dword ptr [rax+rax+00h]
0x1800d670e  mov     eax, [r13+28h]
0x1800d6712  mov     r9d, 3E8h; msWindowLength
0x1800d6718  mov     rcx, [r12]; pti
0x1800d671c  xor     r8d, r8d; msPeriod
0x1800d671f  imul    rax, 0FFFFFFFFFFFFD8F0h
0x1800d6726  mov     rdx, rax
0x1800d6729  mov     [rbp+pftDueTime.dwLowDateTime], eax
0x1800d672c  shr     rdx, 20h
0x1800d6730  mov     [rbp+pftDueTime.dwHighDateTime], edx
0x1800d6733  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x1800d6737  call    cs:__imp_SetThreadpoolTimer
0x1800d673e  nop     dword ptr [rax+rax+00h]
0x1800d6743  mov     rax, [r13+38h]
0x1800d6747  mov     r15, [rax]
0x1800d674a  lea     rdi, [r15+8]
0x1800d674e  mov     rcx, rdi; SRWLock
0x1800d6751  call    cs:__imp_AcquireSRWLockExclusive
0x1800d6758  nop     dword ptr [rax+rax+00h]
0x1800d675d  cmp     dword ptr [r15], 2
0x1800d6761  lea     rax, ?OnCrashDumpCollectionCompleted@ComputeReaper@Details@Core@Manager@Container@@CAXJPEAX@Z; Container::Manager::Core::Details::ComputeReaper::OnCrashDumpCollectionCompleted(long,void *)
0x1800d6768  mov     [r15+10h], rax
0x1800d676c  mov     [r15+18h], r13
0x1800d6770  jnz     short loc_1800D6782
0x1800d6772  mov     rcx, [r15+20h]; pwk
0x1800d6776  call    cs:__imp_SubmitThreadpoolWork
0x1800d677d  nop     dword ptr [rax+rax+00h]
0x1800d6782  test    rdi, rdi
0x1800d6785  jz      short loc_1800D6796
0x1800d6787  mov     rcx, rdi; SRWLock
0x1800d678a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800d6791  nop     dword ptr [rax+rax+00h]
0x1800d6796  mov     r15b, [rbp+arg_0]
0x1800d679a  xor     edx, edx
0x1800d679c  lea     rcx, [rbp+arg_10]
0x1800d67a0  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x1800d67a5  test    rbx, rbx
0x1800d67a8  jz      loc_1800D65B2
0x1800d67ae  mov     rcx, rbx; pti
0x1800d67b1  call    cs:__imp_CloseThreadpoolTimer
0x1800d67b8  nop     dword ptr [rax+rax+00h]
0x1800d67bd  jmp     loc_1800D65B2
0x1800d67c2  mov     rcx, r14; SRWLock
0x1800d67c5  call    cs:__imp_AcquireSRWLockExclusive
0x1800d67cc  nop     dword ptr [rax+rax+00h]
0x1800d67d1  mov     rax, [rsi+8]
0x1800d67d5  cmp     [rax], rsi
0x1800d67d8  jnz     short loc_1800D6805
0x1800d67da  mov     [rdi], rsi
0x1800d67dd  mov     r15b, 1
0x1800d67e0  mov     [rdi+8], rax
0x1800d67e4  mov     [rax], rdi
0x1800d67e7  mov     [rbp+arg_0], r15b
0x1800d67eb  mov     [rsi+8], rdi
0x1800d67ef  test    r14, r14
0x1800d67f2  jz      short loc_1800D679A
0x1800d67f4  mov     rcx, r14; SRWLock
0x1800d67f7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800d67fe  nop     dword ptr [rax+rax+00h]
0x1800d6803  jmp     short loc_1800D679A
0x1800d6805  mov     ecx, 3
0x1800d680a  int     29h; Win8: RtlFailFast(ecx)
0x1800d680c  mov     al, r15b
0x1800d680f  add     rsp, 48h
0x1800d6813  pop     r15
0x1800d6815  pop     r14
0x1800d6817  pop     r13
0x1800d6819  pop     r12
0x1800d681b  pop     rdi
0x1800d681c  pop     rsi
0x1800d681d  pop     rbx
0x1800d681e  pop     rbp
0x1800d681f  retn
```
