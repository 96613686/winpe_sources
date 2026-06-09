# Container::Manager::Core::Details::ContainerObject::PerformLogicalStateTransition(void)

- ea: `0x1800aa3dc`
- end: `0x1800aa63f`
- name: `?PerformLogicalStateTransition@ContainerObject@Details@Core@Manager@Container@@AEAAXXZ`
- size: `611`
- prototype: `void __fastcall(Container::Manager::Core::Details::ContainerObject *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800a3460`

## callees

- `0x18000a10c`
- `0x180016718`
- `0x18002d030`
- `0x1800a88f8`
- `0x1800a9bb4`
- `0x1800aa2c8`
- `0x1800aa3dc`
- `0x1800aa648`
- `0x1800aa830`
- `0x180187398`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800aa4b1`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800aa4b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800aa400`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800aa57f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800aa400`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800aa57f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800aa544`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800aa5aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800aa603`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800aa544`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800aa5aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800aa603`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aa40c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aa4bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aa58b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aa40c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aa4bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aa58b`

## pseudocode

```c
void __fastcall Container::Manager::Core::Details::ContainerObject::PerformLogicalStateTransition(
        Container::Manager::Core::Details::ContainerObject *this)
{
  PSRWLOCK v2; // rdi
  const char *v3; // r9
  int v4; // eax
  int v5; // r14d
  Csl *v6; // rcx
  DWORD v7; // r15d
  int UnbiasedInterruptTimeMs64; // r13d
  BOOL v9; // ebx
  DWORD CurrentThreadId; // eax
  Csl *v11; // rcx
  DWORD v12; // eax
  RTL_SRWLOCK *v13; // rcx
  int v14; // eax
  RTL_SRWLOCK *v15; // rcx
  int v16; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  int v18; // [rsp+80h] [rbp+40h] BYREF
  char v19; // [rsp+84h] [rbp+44h]
  PSRWLOCK SRWLock; // [rsp+88h] [rbp+48h] BYREF

  v2 = (PSRWLOCK)((char *)this + 456);
  AcquireSRWLockExclusive((PSRWLOCK)this + 57);
  LODWORD(v2[1].Ptr) = GetCurrentThreadId();
  SRWLock = v2;
  if ( *((_DWORD *)this + 217) == 3 )
  {
    LOBYTE(v18) = 0;
    v5 = Container::Manager::Core::Details::ContainerObject::PerformCreateLogicalStateTransition(
           this,
           (char *)&SRWLock,
           &v18);
    if ( v5 < 0 && (_BYTE)v18 )
    {
      v7 = 30000;
      while ( *((_DWORD *)this + 217) != 8 )
      {
        UnbiasedInterruptTimeMs64 = Csl::QueryUnbiasedInterruptTimeMs64(v6);
        LODWORD(SRWLock[1].Ptr) = 0;
        v9 = SleepConditionVariableSRW((PCONDITION_VARIABLE)this + 124, SRWLock, v7, 0);
        CurrentThreadId = GetCurrentThreadId();
        v11 = (Csl *)SRWLock;
        LODWORD(SRWLock[1].Ptr) = CurrentThreadId;
        if ( !v9 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
          break;
        }
        v12 = Csl::QueryUnbiasedInterruptTimeMs64(v11) - UnbiasedInterruptTimeMs64;
        if ( v12 >= v7 )
          v12 = v7;
        v7 -= v12;
      }
    }
  }
  else
  {
    switch ( *((_DWORD *)this + 217) )
    {
      case 5:
        v4 = Container::Manager::Core::Details::ContainerObject::PerformPauseLogicalStateTransition((struct _GUID *)this);
        break;
      case 7:
        v4 = Container::Manager::Core::Details::ContainerObject::PerformResumeLogicalStateTransition(this);
        break;
      case 8:
        goto LABEL_31;
      default:
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x2565,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
          v3);
    }
    v5 = v4;
  }
  *((_DWORD *)this + 225) = *((_DWORD *)this + 218);
  *((_QWORD *)this + 115) = *(_QWORD *)((char *)this + 892);
  if ( v5 < 0 )
  {
    v18 = *((_DWORD *)this + 217);
    v19 = 1;
    Container::Manager::Core::Details::ContainerObject::OnContainerStateTransitionFailed(this);
LABEL_30:
    v2 = SRWLock;
    goto LABEL_31;
  }
  if ( *((_DWORD *)this + 217) != 4 || (*((_BYTE *)this + 92) & 2) == 0 )
    goto LABEL_30;
  v13 = SRWLock;
  if ( SRWLock )
  {
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v13);
    SRWLock = 0;
  }
  v14 = Container::Manager::Core::Details::ContainerObject::PerformLargification(this);
  if ( v14 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2584,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)(unsigned int)v14,
      v16);
  AcquireSRWLockExclusive(v2);
  LODWORD(v2[1].Ptr) = GetCurrentThreadId();
  v15 = SRWLock;
  if ( SRWLock )
  {
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v15);
  }
  SRWLock = v2;
LABEL_31:
  if ( v2 )
  {
    LODWORD(v2[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v2);
  }
}

```

## disassembly

```asm
0x1800aa3dc  mov     [rsp-38h+arg_10], rbx
0x1800aa3e1  push    rbp
0x1800aa3e2  push    rsi
0x1800aa3e3  push    rdi
0x1800aa3e4  push    r12
0x1800aa3e6  push    r13
0x1800aa3e8  push    r14
0x1800aa3ea  push    r15
0x1800aa3ec  mov     rbp, rsp
0x1800aa3ef  sub     rsp, 40h
0x1800aa3f3  mov     rsi, rcx
0x1800aa3f6  lea     rdi, [rcx+1C8h]
0x1800aa3fd  mov     rcx, rdi; SRWLock
0x1800aa400  call    cs:__imp_AcquireSRWLockExclusive
0x1800aa407  nop     dword ptr [rax+rax+00h]
0x1800aa40c  call    cs:__imp_GetCurrentThreadId
0x1800aa413  nop     dword ptr [rax+rax+00h]
0x1800aa418  mov     [rdi+8], eax
0x1800aa41b  mov     [rbp+SRWLock], rdi
0x1800aa41f  mov     ecx, [rsi+364h]
0x1800aa425  sub     ecx, 3
0x1800aa428  jz      short loc_1800AA464
0x1800aa42a  sub     ecx, 2
0x1800aa42d  jz      short loc_1800AA450
0x1800aa42f  sub     ecx, 2
0x1800aa432  jz      short loc_1800AA442
0x1800aa434  cmp     ecx, 1
0x1800aa437  jnz     loc_1800AA629
0x1800aa43d  jmp     loc_1800AA5F4
0x1800aa442  lea     rdx, [rbp+SRWLock]
0x1800aa446  mov     rcx, rsi; this
0x1800aa449  call    ?PerformResumeLogicalStateTransition@ContainerObject@Details@Core@Manager@Container@@AEAAJAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::PerformResumeLogicalStateTransition(Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800aa44e  jmp     short loc_1800AA45C
0x1800aa450  lea     rdx, [rbp+SRWLock]
0x1800aa454  mov     rcx, rsi; struct _GUID *
0x1800aa457  call    ?PerformPauseLogicalStateTransition@ContainerObject@Details@Core@Manager@Container@@AEAAJAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::PerformPauseLogicalStateTransition(Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800aa45c  mov     r14d, eax
0x1800aa45f  jmp     loc_1800AA4F8
0x1800aa464  mov     byte ptr [rbp+arg_0], 0
0x1800aa468  lea     r8, [rbp+arg_0]
0x1800aa46c  lea     rdx, [rbp+SRWLock]
0x1800aa470  mov     rcx, rsi; this
0x1800aa473  call    ?PerformCreateLogicalStateTransition@ContainerObject@Details@Core@Manager@Container@@AEAAJAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@AEA_N@Z; Container::Manager::Core::Details::ContainerObject::PerformCreateLogicalStateTransition(Csl::SrwLock::ReleaseOnScopeExit<0> &,bool &)
0x1800aa478  mov     r14d, eax
0x1800aa47b  test    eax, eax
0x1800aa47d  jns     short loc_1800AA4F8
0x1800aa47f  cmp     byte ptr [rbp+arg_0], 0
0x1800aa483  jz      short loc_1800AA4F8
0x1800aa485  mov     r15d, 7530h
0x1800aa48b  jmp     short loc_1800AA4E8
0x1800aa48d  call    ?QueryUnbiasedInterruptTimeMs64@Csl@@YA_KXZ; Csl::QueryUnbiasedInterruptTimeMs64(void)
0x1800aa492  mov     r13, rax
0x1800aa495  mov     rcx, [rbp+SRWLock]
0x1800aa499  mov     dword ptr [rcx+8], 0
0x1800aa4a0  xor     r9d, r9d; Flags
0x1800aa4a3  mov     r8d, r15d; dwMilliseconds
0x1800aa4a6  mov     rdx, [rbp+SRWLock]; SRWLock
0x1800aa4aa  lea     rcx, [rsi+3E0h]; ConditionVariable
0x1800aa4b1  call    cs:__imp_SleepConditionVariableSRW
0x1800aa4b8  nop     dword ptr [rax+rax+00h]
0x1800aa4bd  mov     ebx, eax
0x1800aa4bf  call    cs:__imp_GetCurrentThreadId
0x1800aa4c6  nop     dword ptr [rax+rax+00h]
0x1800aa4cb  mov     rcx, [rbp+SRWLock]; this
0x1800aa4cf  mov     [rcx+8], eax
0x1800aa4d2  test    ebx, ebx
0x1800aa4d4  jz      short loc_1800AA4F3
0x1800aa4d6  call    ?QueryUnbiasedInterruptTimeMs64@Csl@@YA_KXZ; Csl::QueryUnbiasedInterruptTimeMs64(void)
0x1800aa4db  sub     eax, r13d
0x1800aa4de  cmp     eax, r15d
0x1800aa4e1  cmovnb  eax, r15d
0x1800aa4e5  sub     r15d, eax
0x1800aa4e8  cmp     dword ptr [rsi+364h], 8
0x1800aa4ef  jnz     short loc_1800AA48D
0x1800aa4f1  jmp     short loc_1800AA4F8
0x1800aa4f3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800aa4f8  mov     eax, [rsi+368h]
0x1800aa4fe  mov     [rsi+384h], eax
0x1800aa504  mov     rax, [rsi+37Ch]
0x1800aa50b  mov     [rsi+398h], rax
0x1800aa512  mov     eax, [rsi+364h]
0x1800aa518  test    r14d, r14d
0x1800aa51b  js      loc_1800AA5BC
0x1800aa521  cmp     eax, 4
0x1800aa524  jnz     loc_1800AA5F0
0x1800aa52a  test    byte ptr [rsi+5Ch], 2
0x1800aa52e  jz      loc_1800AA5F0
0x1800aa534  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800aa538  test    rcx, rcx
0x1800aa53b  jz      short loc_1800AA558
0x1800aa53d  mov     dword ptr [rcx+8], 0
0x1800aa544  call    cs:__imp_ReleaseSRWLockExclusive
0x1800aa54b  nop     dword ptr [rax+rax+00h]
0x1800aa550  mov     [rbp+SRWLock], 0
0x1800aa558  mov     rcx, rsi; this
0x1800aa55b  call    ?PerformLargification@ContainerObject@Details@Core@Manager@Container@@QEAAJXZ; Container::Manager::Core::Details::ContainerObject::PerformLargification(void)
0x1800aa560  test    eax, eax
0x1800aa562  jns     short loc_1800AA57C
0x1800aa564  mov     rcx, [rbp+38h]; this
0x1800aa568  mov     r9d, eax; char *
0x1800aa56b  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800aa572  mov     edx, 2584h; void *
0x1800aa577  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800aa57c  mov     rcx, rdi; SRWLock
0x1800aa57f  call    cs:__imp_AcquireSRWLockExclusive
0x1800aa586  nop     dword ptr [rax+rax+00h]
0x1800aa58b  call    cs:__imp_GetCurrentThreadId
0x1800aa592  nop     dword ptr [rax+rax+00h]
0x1800aa597  mov     [rdi+8], eax
0x1800aa59a  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800aa59e  test    rcx, rcx
0x1800aa5a1  jz      short loc_1800AA5B6
0x1800aa5a3  mov     dword ptr [rcx+8], 0
0x1800aa5aa  call    cs:__imp_ReleaseSRWLockExclusive
0x1800aa5b1  nop     dword ptr [rax+rax+00h]
0x1800aa5b6  mov     [rbp+SRWLock], rdi
0x1800aa5ba  jmp     short loc_1800AA5F4
0x1800aa5bc  xorps   xmm0, xmm0
0x1800aa5bf  xor     ecx, ecx
0x1800aa5c1  mov     dword ptr [rbp+arg_0], eax
0x1800aa5c4  mov     byte ptr [rbp+arg_0+4], 1
0x1800aa5c8  movzx   eax, word ptr [rbp+arg_0+5]
0x1800aa5cc  mov     word ptr [rbp+arg_0+5], ax
0x1800aa5d0  mov     al, byte ptr [rbp+arg_0+7]
0x1800aa5d3  mov     byte ptr [rbp+arg_0+7], al
0x1800aa5d6  movaps  [rbp+var_20], xmm0
0x1800aa5da  mov     [rbp+var_10], ecx
0x1800aa5dd  lea     r9, [rbp+var_20]
0x1800aa5e1  mov     r8, [rbp+arg_0]
0x1800aa5e5  mov     edx, r14d
0x1800aa5e8  mov     rcx, rsi
0x1800aa5eb  call    ?OnContainerStateTransitionFailed@ContainerObject@Details@Core@Manager@Container@@AEAAXJV?$optional@W4ContainerLogicalState@Details@Core@Manager@Container@@@utl@@V?$optional@VComputeSystemQosState@Details@Core@Manager@Container@@@7@@Z; Container::Manager::Core::Details::ContainerObject::OnContainerStateTransitionFailed(long,utl::optional<Container::Manager::Core::Details::ContainerLogicalState>,utl::optional<Container::Manager::Core::Details::ComputeSystemQosState>)
0x1800aa5f0  mov     rdi, [rbp+SRWLock]
0x1800aa5f4  test    rdi, rdi
0x1800aa5f7  jz      short loc_1800AA610
0x1800aa5f9  mov     dword ptr [rdi+8], 0
0x1800aa600  mov     rcx, rdi; SRWLock
0x1800aa603  call    cs:__imp_ReleaseSRWLockExclusive
0x1800aa60a  nop     dword ptr [rax+rax+00h]
0x1800aa60f  nop
0x1800aa610  mov     rbx, [rsp+40h+arg_10]
0x1800aa618  add     rsp, 40h
0x1800aa61c  pop     r15
0x1800aa61e  pop     r14
0x1800aa620  pop     r13
0x1800aa622  pop     r12
0x1800aa624  pop     rdi
0x1800aa625  pop     rsi
0x1800aa626  pop     rbp
0x1800aa627  retn
0x1800aa629  mov     rcx, [rbp+38h]; this
0x1800aa62d  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800aa634  mov     edx, 2565h; void *
0x1800aa639  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
