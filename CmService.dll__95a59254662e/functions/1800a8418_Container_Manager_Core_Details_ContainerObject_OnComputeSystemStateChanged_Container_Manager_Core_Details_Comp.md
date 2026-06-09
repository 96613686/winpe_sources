# Container::Manager::Core::Details::ContainerObject::OnComputeSystemStateChanged(Container::Manager::Core::Details::ComputeSystemState const &,long)

- ea: `0x1800a8418`
- end: `0x1800a87ce`
- name: `?OnComputeSystemStateChanged@ContainerObject@Details@Core@Manager@Container@@AEAAXAEBUComputeSystemState@2345@J@Z`
- size: `950`
- prototype: `void __fastcall(Container::Manager::Core::Details::ContainerObject *__hidden this, const struct Container::Manager::Core::Details::ComputeSystemState *, int)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800a87e0`

## callees

- `0x180004fc4`
- `0x180016718`
- `0x18004feb4`
- `0x180060ea0`
- `0x180079a28`
- `0x18009e4e4`
- `0x18009fae8`
- `0x1800a6478`
- `0x1800a8418`
- `0x1800ae4ec`
- `0x1800b7aac`
- `0x1800b9400`
- `0x1800bc0c0`
- `0x180125a08`
- `0x1801959f8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800a8657`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800a8657`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800a8714`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800a8714`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a8447`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a869c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a8447`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a869c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a853b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a86e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a87a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a853b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a86e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a87a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a8453`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a86a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a8453`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a86a8`

## pseudocode

```c
void __fastcall Container::Manager::Core::Details::ContainerObject::OnComputeSystemStateChanged(
        Container::Manager::Core::Details::ContainerObject *this,
        const struct Container::Manager::Core::Details::ComputeSystemState *a2,
        int a3)
{
  char *v3; // r13
  int v7; // r15d
  char v8; // r10
  char v9; // r9
  int v10; // r8d
  char v11; // dl
  char v12; // cl
  __int16 v13; // ax
  __int16 v14; // bx
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  bool v17; // zf
  unsigned int v18; // ebx
  int v19; // eax
  Container::Manager::Core::ResourceHandle *v20; // rbx
  Csl::VirtualDisk *v21; // rbx
  char v22; // r14
  struct _TP_TIMER *v23; // rcx
  BOOL v24; // r12d
  __int64 v25; // r15
  __int64 v26; // r14
  unsigned int v27; // eax
  __int128 v28; // xmm0
  __int64 v29; // rdx
  int v30; // [rsp+20h] [rbp-49h]
  char v31; // [rsp+30h] [rbp-39h]
  int v32; // [rsp+40h] [rbp-29h] BYREF
  char v33; // [rsp+44h] [rbp-25h]
  char v34; // [rsp+45h] [rbp-24h]
  __int16 v35; // [rsp+46h] [rbp-23h]
  int v36; // [rsp+48h] [rbp-21h]
  char v37; // [rsp+4Ch] [rbp-1Dh]
  char v38; // [rsp+4Dh] [rbp-1Ch]
  __int16 v39; // [rsp+4Eh] [rbp-1Bh]
  int v40; // [rsp+50h] [rbp-19h]
  int v41; // [rsp+54h] [rbp-15h]
  int v42; // [rsp+58h] [rbp-11h]
  __int128 v43; // [rsp+60h] [rbp-9h]
  __int128 v44; // [rsp+70h] [rbp+7h] BYREF
  __int64 v45; // [rsp+82h] [rbp+19h]
  __int16 v46; // [rsp+8Ah] [rbp+21h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  char v48; // [rsp+D0h] [rbp+67h]
  char v49; // [rsp+D8h] [rbp+6Fh]
  char v50; // [rsp+E8h] [rbp+7Fh]

  v3 = (char *)this + 456;
  AcquireSRWLockExclusive((PSRWLOCK)this + 57);
  *((_DWORD *)v3 + 2) = GetCurrentThreadId();
  v7 = *((_DWORD *)this + 219);
  v8 = *((_BYTE *)this + 880);
  v9 = *((_BYTE *)this + 881);
  v10 = *((_DWORD *)this + 221);
  v11 = *((_BYTE *)this + 888);
  v12 = *((_BYTE *)this + 889);
  v13 = *((_WORD *)this + 449);
  v14 = *((_WORD *)this + 441);
  v45 = *(_QWORD *)((char *)this + 890);
  v15 = *(_OWORD *)a2;
  v41 = v7;
  v48 = v8;
  *(_OWORD *)((char *)this + 872) = v15;
  v49 = v9;
  v16 = *(_OWORD *)((char *)a2 + 12);
  v42 = v10;
  v50 = v11;
  *(_OWORD *)((char *)this + 884) = v16;
  v17 = *((_DWORD *)this + 218) == 5;
  v31 = v12;
  v46 = v13;
  if ( v17 )
  {
    v18 = Container::Manager::Core::Details::ConvertExitInformationToExitReason(**((_QWORD **)this + 157) + 72LL);
    if ( Container::Manager::Hcs::ComputeSystem::WasGracefullyShutdown(*((Container::Manager::Hcs::ComputeSystem **)this
                                                                       + 157))
      && a3 >= 0 )
    {
      a3 = -2147023781;
    }
    else if ( v18 == 7 && a3 >= 0 )
    {
      a3 = -2143878905;
    }
    Container::Manager::Core::Details::ContainerObject::TransitionToExitedState(this, v18, (unsigned int)a3);
    *((_DWORD *)v3 + 2) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v3);
    if ( a3 < 0 )
    {
      v19 = Container::Manager::Core::Details::ContainerOrchestrator::OnComputeSystemExitFailure(
              *((Container::Manager::Core::Details::ContainerOrchestrator **)this + 195),
              a3,
              *((struct Container::Manager::Core::ResourceHandle **)this + 187));
      if ( v19 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2AAA,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
          (const char *)(unsigned int)v19,
          v30);
    }
    v20 = (Container::Manager::Core::ResourceHandle *)*((_QWORD *)this + 187);
    *((_QWORD *)this + 187) = 0;
    if ( v20 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v20);
      operator delete(v20, (const struct std::nothrow_t *)0x58);
    }
    if ( *((_BYTE *)this + 1592) )
    {
      Container::Manager::Core::Details::DebugConfigurationHandle::~DebugConfigurationHandle((Container::Manager::Core::Details::ContainerObject *)((char *)this + 1568));
      *((_BYTE *)this + 1592) = 0;
    }
    if ( *((_DWORD *)this + 22) == 2 )
    {
      v21 = (Csl::VirtualDisk *)*((_QWORD *)this + 184);
      *((_QWORD *)this + 184) = 0;
      if ( v21 )
      {
        Csl::VirtualDisk::~VirtualDisk(v21);
        operator delete(v21, (const struct std::nothrow_t *)0x30);
      }
    }
    Container::Manager::Core::ResourceHandle::ReleaseExclusiveAccess(*((Container::Manager::Core::ResourceHandle **)this
                                                                     + 160));
  }
  else
  {
    if ( *((_DWORD *)this + 219) != v7
      || *((_BYTE *)this + 880) != v8
      || *((_BYTE *)this + 881) != v9
      || *((_DWORD *)this + 221) != v10
      || *((_BYTE *)this + 888) != v11
      || (v22 = 1, *((_BYTE *)this + 889) != v12) )
    {
      v22 = 0;
    }
    if ( *((_DWORD *)this + 296) )
    {
      v23 = (struct _TP_TIMER *)*((_QWORD *)this + 147);
      *((_DWORD *)this + 296) = 0;
      SetThreadpoolTimer(v23, 0, 0, 0);
    }
    if ( v22 )
    {
      Container::Manager::Core::Details::ContainerObject::SignalPhysicalStateTransitionWaiter(
        this,
        *((unsigned int *)this + 218),
        0);
    }
    else
    {
      v17 = *((_DWORD *)this + 219) == 0;
      v40 = *((_DWORD *)this + 219);
      v24 = !v17;
      if ( v24 != (v7 != 0) )
      {
        v25 = *((_QWORD *)this + 169);
        v26 = *((_QWORD *)this + 69);
        AcquireSRWLockExclusive((PSRWLOCK)v25);
        *(_DWORD *)(v25 + 8) = GetCurrentThreadId();
        *(_DWORD *)(v26 + 56) &= ~1u;
        *(_DWORD *)(v26 + 56) |= v24;
        if ( !v40 )
        {
          v27 = *(_DWORD *)(v26 + 60);
          if ( v27 >= *(_DWORD *)(v25 + 24) >> 1 )
            v27 = *(_DWORD *)(v25 + 24) >> 1;
          *(_DWORD *)(v26 + 60) = v27;
        }
        *(_DWORD *)(v25 + 8) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)v25);
        v7 = v41;
      }
      if ( (v7 & 1) != 0 && (*((_BYTE *)this + 876) & 1) == 0 && *((_DWORD *)this + 215) )
      {
        *((_DWORD *)this + 216) = 1;
        WakeByAddressAll((char *)this + 864);
      }
      v28 = *(_OWORD *)((char *)this + 876);
      v29 = *((unsigned int *)this + 217);
      v33 = v48;
      v34 = v49;
      v36 = v42;
      v37 = v50;
      v38 = v31;
      v39 = v45;
      v43 = v28;
      v32 = v7;
      v35 = v14;
      Container::Manager::Core::Details::ContainerObject::EmitContainerStateChangedTelemetry(this, v29, &v32);
    }
    Container::Manager::Core::Details::ContainerObject::NotifyActivitiesOfContainerState(this);
    Container::Manager::Core::Details::ContainerObject::UpdateDesiredStateAndQueueStateTransitions(this, &v44);
    *((_DWORD *)v3 + 2) = 0;
    ReleaseSRWLockExclusive((PSRWLOCK)v3);
  }
}

```

## disassembly

```asm
0x1800a8418  mov     [rsp-8+arg_10], rbx
0x1800a841d  push    rbp
0x1800a841e  push    rsi
0x1800a841f  push    rdi
0x1800a8420  push    r12
0x1800a8422  push    r13
0x1800a8424  push    r14
0x1800a8426  push    r15
0x1800a8428  lea     rbp, [rsp-27h]
0x1800a842d  sub     rsp, 90h
0x1800a8434  lea     r13, [rcx+1C8h]
0x1800a843b  mov     rsi, rcx
0x1800a843e  mov     rcx, r13; SRWLock
0x1800a8441  mov     r14d, r8d
0x1800a8444  mov     rdi, rdx
0x1800a8447  call    cs:__imp_AcquireSRWLockExclusive
0x1800a844e  nop     dword ptr [rax+rax+00h]
0x1800a8453  call    cs:__imp_GetCurrentThreadId
0x1800a845a  nop     dword ptr [rax+rax+00h]
0x1800a845f  mov     [r13+8], eax
0x1800a8463  movsd   xmm0, qword ptr [rsi+37Ah]
0x1800a846b  mov     r15d, [rsi+36Ch]
0x1800a8472  mov     r10b, [rsi+370h]
0x1800a8479  mov     r9b, [rsi+371h]
0x1800a8480  mov     r8d, [rsi+374h]
0x1800a8487  mov     dl, [rsi+378h]
0x1800a848d  mov     cl, [rsi+379h]
0x1800a8493  movzx   eax, word ptr [rsi+382h]
0x1800a849a  movzx   ebx, word ptr [rsi+372h]
0x1800a84a1  movsd   [rbp+57h+var_3E], xmm0
0x1800a84a6  movups  xmm0, xmmword ptr [rdi]
0x1800a84a9  mov     [rbp+57h+var_6C], r15d
0x1800a84ad  mov     [rbp+57h+arg_0], r10b
0x1800a84b1  movups  xmmword ptr [rsi+368h], xmm0
0x1800a84b8  mov     [rbp+57h+arg_8], r9b
0x1800a84bc  movups  xmm1, xmmword ptr [rdi+0Ch]
0x1800a84c0  mov     [rbp+57h+var_68], r8d
0x1800a84c4  mov     [rbp+57h+arg_18], dl
0x1800a84c7  movups  xmmword ptr [rsi+374h], xmm1
0x1800a84ce  cmp     dword ptr [rsi+368h], 5
0x1800a84d5  mov     [rbp+57h+var_90], cl
0x1800a84d8  mov     [rbp+57h+var_36], ax
0x1800a84dc  jnz     loc_1800A85FE
0x1800a84e2  mov     rax, [rsi+4E8h]
0x1800a84e9  mov     rcx, [rax]
0x1800a84ec  add     rcx, 48h ; 'H'
0x1800a84f0  call    ?ConvertExitInformationToExitReason@Details@Core@Manager@Container@@YA?AW4_CMS_EXIT_REASON@@AEBVComputeSystemExitInformation@Hcs@34@@Z; Container::Manager::Core::Details::ConvertExitInformationToExitReason(Container::Manager::Hcs::ComputeSystemExitInformation const &)
0x1800a84f5  mov     rcx, [rsi+4E8h]; this
0x1800a84fc  mov     ebx, eax
0x1800a84fe  call    ?WasGracefullyShutdown@ComputeSystem@Hcs@Manager@Container@@QEBA_NXZ; Container::Manager::Hcs::ComputeSystem::WasGracefullyShutdown(void)
0x1800a8503  xor     edi, edi
0x1800a8505  test    al, al
0x1800a8507  jz      short loc_1800A8516
0x1800a8509  test    r14d, r14d
0x1800a850c  js      short loc_1800A8516
0x1800a850e  mov     r14d, 8007045Bh
0x1800a8514  jmp     short loc_1800A8527
0x1800a8516  cmp     ebx, 7
0x1800a8519  jnz     short loc_1800A8527
0x1800a851b  test    r14d, r14d
0x1800a851e  mov     eax, 80370107h
0x1800a8523  cmovns  r14d, eax
0x1800a8527  mov     r8d, r14d
0x1800a852a  mov     edx, ebx
0x1800a852c  mov     rcx, rsi
0x1800a852f  call    ?TransitionToExitedState@ContainerObject@Details@Core@Manager@Container@@AEAAXW4_CMS_EXIT_REASON@@J@Z; Container::Manager::Core::Details::ContainerObject::TransitionToExitedState(_CMS_EXIT_REASON,long)
0x1800a8534  mov     rcx, r13; SRWLock
0x1800a8537  mov     [r13+8], edi
0x1800a853b  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a8542  nop     dword ptr [rax+rax+00h]
0x1800a8547  test    r14d, r14d
0x1800a854a  jns     short loc_1800A857E
0x1800a854c  mov     r8, [rsi+5D8h]; struct Container::Manager::Core::ResourceHandle *
0x1800a8553  mov     edx, r14d; int
0x1800a8556  mov     rcx, [rsi+618h]; this
0x1800a855d  call    ?OnComputeSystemExitFailure@ContainerOrchestrator@Details@Core@Manager@Container@@QEAAJJAEAVResourceHandle@345@@Z; Container::Manager::Core::Details::ContainerOrchestrator::OnComputeSystemExitFailure(long,Container::Manager::Core::ResourceHandle &)
0x1800a8562  test    eax, eax
0x1800a8564  jns     short loc_1800A857E
0x1800a8566  mov     rcx, [rbp+5Fh]; this
0x1800a856a  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a8571  mov     r9d, eax; char *
0x1800a8574  mov     edx, 2AAAh; void *
0x1800a8579  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a857e  mov     rbx, [rsi+5D8h]
0x1800a8585  mov     [rsi+5D8h], rdi
0x1800a858c  test    rbx, rbx
0x1800a858f  jz      short loc_1800A85A6
0x1800a8591  mov     rcx, rbx; this
0x1800a8594  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x1800a8599  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x1800a859e  mov     rcx, rbx; void *
0x1800a85a1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a85a6  lea     rbx, [rsi+620h]
0x1800a85ad  cmp     [rbx+18h], dil
0x1800a85b1  jz      short loc_1800A85BF
0x1800a85b3  mov     rcx, rbx; this
0x1800a85b6  call    ??1DebugConfigurationHandle@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::DebugConfigurationHandle::~DebugConfigurationHandle(void)
0x1800a85bb  mov     [rbx+18h], dil
0x1800a85bf  cmp     dword ptr [rsi+58h], 2
0x1800a85c3  jnz     short loc_1800A85ED
0x1800a85c5  mov     rbx, [rsi+5C0h]
0x1800a85cc  mov     [rsi+5C0h], rdi
0x1800a85d3  test    rbx, rbx
0x1800a85d6  jz      short loc_1800A85ED
0x1800a85d8  mov     rcx, rbx; this
0x1800a85db  call    ??1VirtualDisk@Csl@@QEAA@XZ; Csl::VirtualDisk::~VirtualDisk(void)
0x1800a85e0  mov     edx, 30h ; '0'; struct std::nothrow_t *
0x1800a85e5  mov     rcx, rbx; void *
0x1800a85e8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a85ed  mov     rcx, [rsi+500h]; this
0x1800a85f4  call    ?ReleaseExclusiveAccess@ResourceHandle@Core@Manager@Container@@QEAAXXZ; Container::Manager::Core::ResourceHandle::ReleaseExclusiveAccess(void)
0x1800a85f9  jmp     loc_1800A87B2
0x1800a85fe  xor     edi, edi
0x1800a8600  cmp     [rsi+36Ch], r15d
0x1800a8607  jnz     short loc_1800A8637
0x1800a8609  cmp     [rsi+370h], r10b
0x1800a8610  jnz     short loc_1800A8637
0x1800a8612  cmp     [rsi+371h], r9b
0x1800a8619  jnz     short loc_1800A8637
0x1800a861b  cmp     [rsi+374h], r8d
0x1800a8622  jnz     short loc_1800A8637
0x1800a8624  cmp     [rsi+378h], dl
0x1800a862a  jnz     short loc_1800A8637
0x1800a862c  mov     r14b, 1
0x1800a862f  cmp     [rsi+379h], cl
0x1800a8635  jz      short loc_1800A863A
0x1800a8637  mov     r14b, dil
0x1800a863a  cmp     [rsi+4A0h], edi
0x1800a8640  jz      short loc_1800A8663
0x1800a8642  mov     rcx, [rsi+498h]; pti
0x1800a8649  xor     r9d, r9d; msWindowLength
0x1800a864c  xor     r8d, r8d; msPeriod
0x1800a864f  mov     [rsi+4A0h], edi
0x1800a8655  xor     edx, edx; pftDueTime
0x1800a8657  call    cs:__imp_SetThreadpoolTimer
0x1800a865e  nop     dword ptr [rax+rax+00h]
0x1800a8663  test    r14b, r14b
0x1800a8666  jnz     loc_1800A877A
0x1800a866c  mov     eax, [rsi+36Ch]
0x1800a8672  mov     r12d, edi
0x1800a8675  test    eax, eax
0x1800a8677  mov     [rbp+57h+var_70], eax
0x1800a867a  mov     eax, edi
0x1800a867c  setnz   r12b
0x1800a8680  test    r15d, r15d
0x1800a8683  setnz   al
0x1800a8686  cmp     r12d, eax
0x1800a8689  jz      short loc_1800A86F0
0x1800a868b  mov     r15, [rsi+548h]
0x1800a8692  mov     r14, [rsi+228h]
0x1800a8699  mov     rcx, r15; SRWLock
0x1800a869c  call    cs:__imp_AcquireSRWLockExclusive
0x1800a86a3  nop     dword ptr [rax+rax+00h]
0x1800a86a8  call    cs:__imp_GetCurrentThreadId
0x1800a86af  nop     dword ptr [rax+rax+00h]
0x1800a86b4  mov     [r15+8], eax
0x1800a86b8  and     dword ptr [r14+38h], 0FFFFFFFEh
0x1800a86bd  or      [r14+38h], r12d
0x1800a86c1  cmp     [rbp+57h+var_70], edi
0x1800a86c4  jnz     short loc_1800A86D9
0x1800a86c6  mov     eax, [r14+3Ch]
0x1800a86ca  mov     edx, [r15+18h]
0x1800a86ce  shr     edx, 1
0x1800a86d0  cmp     eax, edx
0x1800a86d2  cmovnb  eax, edx
0x1800a86d5  mov     [r14+3Ch], eax
0x1800a86d9  mov     rcx, r15; SRWLock
0x1800a86dc  mov     [r15+8], edi
0x1800a86e0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a86e7  nop     dword ptr [rax+rax+00h]
0x1800a86ec  mov     r15d, [rbp+57h+var_6C]
0x1800a86f0  test    r15b, 1
0x1800a86f4  jz      short loc_1800A8720
0x1800a86f6  test    byte ptr [rsi+36Ch], 1
0x1800a86fd  jnz     short loc_1800A8720
0x1800a86ff  cmp     [rsi+35Ch], edi
0x1800a8705  jbe     short loc_1800A8720
0x1800a8707  lea     rcx, [rsi+360h]; Address
0x1800a870e  mov     dword ptr [rcx], 1
0x1800a8714  call    cs:__imp_WakeByAddressAll
0x1800a871b  nop     dword ptr [rax+rax+00h]
0x1800a8720  mov     al, [rbp+57h+arg_0]
0x1800a8723  lea     r8, [rbp+57h+var_80]
0x1800a8727  movups  xmm0, xmmword ptr [rsi+36Ch]
0x1800a872e  mov     edx, [rsi+364h]
0x1800a8734  mov     rcx, rsi
0x1800a8737  mov     [rbp+57h+var_7C], al
0x1800a873a  mov     r9d, edx
0x1800a873d  mov     al, [rbp+57h+arg_8]
0x1800a8740  mov     [rbp+57h+var_7B], al
0x1800a8743  mov     eax, [rbp+57h+var_68]
0x1800a8746  mov     [rbp+57h+var_78], eax
0x1800a8749  mov     al, [rbp+57h+arg_18]
0x1800a874c  mov     [rbp+57h+var_74], al
0x1800a874f  mov     al, [rbp+57h+var_90]
0x1800a8752  mov     [rbp+57h+var_73], al
0x1800a8755  movzx   eax, word ptr [rbp+57h+var_3E]
0x1800a8759  mov     [rbp+57h+var_72], ax
0x1800a875d  lea     rax, [rbp+57h+var_60]
0x1800a8761  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1800a8766  movdqu  [rbp+57h+var_60], xmm0
0x1800a876b  mov     [rbp+57h+var_80], r15d
0x1800a876f  mov     [rbp+57h+var_7A], bx
0x1800a8773  call    ?EmitContainerStateChangedTelemetry@ContainerObject@Details@Core@Manager@Container@@AEAAXW4ContainerLogicalState@2345@VComputeSystemQosState@2345@01@Z; Container::Manager::Core::Details::ContainerObject::EmitContainerStateChangedTelemetry(Container::Manager::Core::Details::ContainerLogicalState,Container::Manager::Core::Details::ComputeSystemQosState,Container::Manager::Core::Details::ContainerLogicalState,Container::Manager::Core::Details::ComputeSystemQosState)
0x1800a8778  jmp     short loc_1800A878B
0x1800a877a  mov     edx, [rsi+368h]
0x1800a8780  xor     r8d, r8d
0x1800a8783  mov     rcx, rsi
0x1800a8786  call    ?SignalPhysicalStateTransitionWaiter@ContainerObject@Details@Core@Manager@Container@@AEAAXW4ComputeSystemPhysicalState@2345@J@Z; Container::Manager::Core::Details::ContainerObject::SignalPhysicalStateTransitionWaiter(Container::Manager::Core::Details::ComputeSystemPhysicalState,long)
0x1800a878b  mov     rcx, rsi; this
0x1800a878e  call    ?NotifyActivitiesOfContainerState@ContainerObject@Details@Core@Manager@Container@@AEAAXXZ; Container::Manager::Core::Details::ContainerObject::NotifyActivitiesOfContainerState(void)
0x1800a8793  lea     rdx, [rbp+57h+var_50]
0x1800a8797  mov     rcx, rsi; this
0x1800a879a  call    ?UpdateDesiredStateAndQueueStateTransitions@ContainerObject@Details@Core@Manager@Container@@AEAA?AV?$optional@UComputeSystemState@Details@Core@Manager@Container@@@utl@@XZ; Container::Manager::Core::Details::ContainerObject::UpdateDesiredStateAndQueueStateTransitions(void)
0x1800a879f  mov     rcx, r13; SRWLock
0x1800a87a2  mov     [r13+8], edi
0x1800a87a6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a87ad  nop     dword ptr [rax+rax+00h]
0x1800a87b2  mov     rbx, [rsp+0C0h+arg_10]
0x1800a87ba  add     rsp, 90h
0x1800a87c1  pop     r15
0x1800a87c3  pop     r14
0x1800a87c5  pop     r13
0x1800a87c7  pop     r12
0x1800a87c9  pop     rdi
0x1800a87ca  pop     rsi
0x1800a87cb  pop     rbp
0x1800a87cc  retn
```
