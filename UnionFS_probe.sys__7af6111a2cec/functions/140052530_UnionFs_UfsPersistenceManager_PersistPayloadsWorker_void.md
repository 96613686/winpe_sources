# UnionFs::UfsPersistenceManager::PersistPayloadsWorker(void *)

- ea: `0x140052530`
- end: `0x14005277e`
- name: `?PersistPayloadsWorker@UfsPersistenceManager@UnionFs@@KAXPEAX@Z`
- size: `590`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140001008`
- `0x1400055d0`
- `0x140006168`
- `0x140052008`
- `0x140052530`
- `0x14007af90`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!PsTerminateSystemThread` at `0x14005273b`
- `ntoskrnl!PsTerminateSystemThread` at `0x14005273b`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140052644`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140052644`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400526a6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400526a6`
- `ntoskrnl!KeSetEvent` at `0x1400525f7`
- `ntoskrnl!KeSetEvent` at `0x1400525f7`

## pseudocode

```c
void __fastcall __noreturn UnionFs::UfsPersistenceManager::PersistPayloadsWorker(
        char *StartContext,
        __int64 a2,
        int a3,
        int a4)
{
  char v5; // di
  NTSTATUS v6; // eax
  char v7; // r14
  NTSTATUS v8; // eax
  bool v9; // si
  bool v10; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v11[3]; // [rsp+41h] [rbp-BFh] BYREF
  int v12; // [rsp+44h] [rbp-BCh] BYREF
  union _LARGE_INTEGER v13; // [rsp+48h] [rbp-B8h] BYREF
  const char *v14; // [rsp+50h] [rbp-B0h] BYREF
  const char *v15; // [rsp+58h] [rbp-A8h] BYREF
  PVOID Object[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v17[752]; // [rsp+70h] [rbp-90h] BYREF

  if ( (unsigned int)dword_14009E178 > 5
    && (qword_14009E188 & 0x8000) != 0
    && (qword_14009E190 & 0x8000) == qword_14009E190 )
  {
    v12 = 518;
    v14 = "onecore\\base\\fs\\unionfs\\sys\\persistencemanager.cpp";
    v15 = "UnionFs::UfsPersistenceManager::PersistPayloadsWorker";
    v13.QuadPart = (LONGLONG)"ENTER";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      qword_14009E190,
      (unsigned int)&dword_1400980B4,
      a3,
      a4,
      (__int64)&v13,
      (__int64)&v15,
      (__int64)&v14,
      (__int64)&v12);
  }
  KeSetEvent((PRKEVENT)(StartContext + 64), 0, 0);
  v5 = 0;
  Object[0] = StartContext + 16;
  Object[1] = StartContext + 40;
  while ( 1 )
  {
    v6 = KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 0, 0, 0);
    if ( v6 == 1 )
    {
      v5 = 1;
    }
    else
    {
      if ( v6 )
        MicrosoftTelemetryAssertTriggeredMsgKM("status == STATUS_WAIT_0");
      if ( !UnionFs::g_FilterState )
        MicrosoftTelemetryAssertTriggeredMsgKM("g_FilterState");
    }
    v7 = 1;
    do
    {
      if ( !v5 )
      {
        v13.QuadPart = -20000000;
        v8 = KeWaitForSingleObject(StartContext + 40, Executive, 0, 0, &v13);
        if ( v8 )
        {
          if ( v8 != 258 )
            MicrosoftTelemetryAssertTriggeredMsgKM("status == STATUS_TIMEOUT");
          *((_DWORD *)StartContext + 2) = 1;
          _mm_mfence();
        }
        else
        {
          v5 = 1;
        }
      }
      UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v17, 0x2D30017025AuLL);
      v9 = 0;
      v11[0] = 0;
      v10 = 0;
      if ( UnionFs::g_FilterState )
      {
        (*(void (__fastcall **)(char *, _BYTE *, _BYTE *))(*(_QWORD *)StartContext + 64LL))(StartContext, v11, v17);
        UnionFs::UfsPersistenceManager::PersistPayloads(
          (UnionFs::UfsPersistenceManager *)StartContext,
          &v10,
          (struct UnionFs::StackEventTracer *)v17);
        v9 = v10;
      }
      if ( v5 )
        PsTerminateSystemThread(0);
      if ( !v11[0] && !v9 )
        v7 = _InterlockedExchangeAdd((volatile signed __int32 *)StartContext + 2, 0xFFFFFFFF) != 1 ? v7 : 0;
      UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v17);
    }
    while ( v7 );
  }
}

```

## disassembly

```asm
0x140052530  push    rbp
0x140052532  push    rbx
0x140052533  push    rsi
0x140052534  push    rdi
0x140052535  push    r14
0x140052537  push    r15
0x140052539  lea     rbp, [rsp-278h]
0x140052541  sub     rsp, 378h
0x140052548  mov     rax, cs:__security_cookie
0x14005254f  xor     rax, rsp
0x140052552  mov     [rbp+2A0h+var_40], rax
0x140052559  mov     eax, cs:dword_14009E178
0x14005255f  mov     rbx, rcx
0x140052562  cmp     eax, 5
0x140052565  jbe     loc_1400525EE
0x14005256b  mov     rcx, cs:qword_14009E190
0x140052572  mov     edx, 8000h
0x140052577  mov     rax, cs:qword_14009E188
0x14005257e  test    rdx, rax
0x140052581  jz      short loc_1400525EE
0x140052583  mov     rax, rcx
0x140052586  and     rax, rdx
0x140052589  cmp     rax, rcx
0x14005258c  jnz     short loc_1400525EE
0x14005258e  lea     rax, aOnecoreBaseFsU_1; "onecore\\base\\fs\\unionfs\\sys\\persis"...
0x140052595  mov     [rsp+3A0h+var_35C], 206h
0x14005259d  mov     [rsp+3A0h+var_350], rax
0x1400525a2  lea     rdx, dword_1400980B4
0x1400525a9  lea     rax, aUnionfsUfspers_6; "UnionFs::UfsPersistenceManager::Persist"...
0x1400525b0  mov     [rsp+3A0h+var_348], rax
0x1400525b5  lea     rax, aEnter; "ENTER"
0x1400525bc  mov     qword ptr [rsp+3A0h+var_358], rax
0x1400525c1  lea     rax, [rsp+3A0h+var_35C]
0x1400525c6  mov     [rsp+3A0h+WaitBlockArray], rax
0x1400525cb  lea     rax, [rsp+3A0h+var_350]
0x1400525d0  mov     [rsp+3A0h+Timeout], rax
0x1400525d5  lea     rax, [rsp+3A0h+var_348]
0x1400525da  mov     qword ptr [rsp+3A0h+Alertable], rax
0x1400525df  lea     rax, [rsp+3A0h+var_358]
0x1400525e4  mov     qword ptr [rsp+3A0h+WaitMode], rax
0x1400525e9  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400525ee  lea     rcx, [rbx+40h]; Event
0x1400525f2  xor     r8d, r8d; Wait
0x1400525f5  xor     edx, edx; Increment
0x1400525f7  call    cs:__imp_KeSetEvent
0x1400525fe  nop     dword ptr [rax+rax+00h]
0x140052603  lea     rax, [rbx+10h]
0x140052607  xor     dil, dil
0x14005260a  lea     r15, [rbx+28h]
0x14005260e  mov     [rsp+3A0h+Object], rax
0x140052613  mov     [rsp+3A0h+var_338], r15
0x140052618  xor     r9d, r9d; WaitReason
0x14005261b  mov     [rsp+3A0h+WaitBlockArray], 0; WaitBlockArray
0x140052624  mov     [rsp+3A0h+Timeout], 0; Timeout
0x14005262d  lea     rdx, [rsp+3A0h+Object]; Object
0x140052632  mov     [rsp+3A0h+Alertable], 0; Alertable
0x140052637  mov     [rsp+3A0h+WaitMode], 0; WaitMode
0x14005263c  lea     r8d, [r9+1]; WaitType
0x140052640  lea     ecx, [r9+2]; Count
0x140052644  call    cs:__imp_KeWaitForMultipleObjects
0x14005264b  nop     dword ptr [rax+rax+00h]
0x140052650  cmp     eax, 1
0x140052653  jnz     short loc_14005265A
0x140052655  mov     dil, al
0x140052658  jmp     short loc_140052680
0x14005265a  test    eax, eax
0x14005265c  jz      short loc_14005266A
0x14005265e  lea     rcx, aStatusStatusWa; "status == STATUS_WAIT_0"
0x140052665  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14005266a  cmp     cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA, 0; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140052672  jnz     short loc_140052680
0x140052674  lea     rcx, aGFilterstate; "g_FilterState"
0x14005267b  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140052680  mov     r14b, 1
0x140052683  test    dil, dil
0x140052686  jnz     short loc_1400526D9
0x140052688  lea     rax, [rsp+3A0h+var_358]
0x14005268d  mov     qword ptr [rsp+3A0h+var_358], 0FFFFFFFFFECED300h
0x140052696  xor     r9d, r9d; Alertable
0x140052699  mov     qword ptr [rsp+3A0h+WaitMode], rax; Timeout
0x14005269e  xor     r8d, r8d; WaitMode
0x1400526a1  xor     edx, edx; WaitReason
0x1400526a3  mov     rcx, r15; Object
0x1400526a6  call    cs:__imp_KeWaitForSingleObject
0x1400526ad  nop     dword ptr [rax+rax+00h]
0x1400526b2  test    eax, eax
0x1400526b4  jnz     short loc_1400526BB
0x1400526b6  mov     dil, 1
0x1400526b9  jmp     short loc_1400526D9
0x1400526bb  cmp     eax, 102h
0x1400526c0  jz      short loc_1400526CE
0x1400526c2  lea     rcx, aStatusStatusTi; "status == STATUS_TIMEOUT"
0x1400526c9  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400526ce  nop
0x1400526cf  mov     dword ptr [rbx+8], 1
0x1400526d6  mfence
0x1400526d9  mov     rdx, 2D30017025Ah; unsigned __int64
0x1400526e3  lea     rcx, [rsp+3A0h+var_330]; this
0x1400526e8  call    ??0StackEventTracer@UnionFs@@QEAA@_K@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64)
0x1400526ed  xor     sil, sil
0x1400526f0  mov     [rsp+3A0h+var_35F], 0
0x1400526f5  cmp     cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA, 0; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400526fd  mov     [rsp+3A0h+var_360], sil
0x140052702  jz      short loc_140052734
0x140052704  mov     rax, [rbx]
0x140052707  lea     r8, [rsp+3A0h+var_330]
0x14005270c  lea     rdx, [rsp+3A0h+var_35F]
0x140052711  mov     rcx, rbx
0x140052714  mov     rax, [rax+40h]
0x140052718  call    _guard_dispatch_icall
0x14005271d  lea     r8, [rsp+3A0h+var_330]; struct UnionFs::StackEventTracer *
0x140052722  mov     rcx, rbx; this
0x140052725  lea     rdx, [rsp+3A0h+var_360]; bool *
0x14005272a  call    ?PersistPayloads@UfsPersistenceManager@UnionFs@@QEBAJPEA_NAEAVStackEventTracer@2@@Z; UnionFs::UfsPersistenceManager::PersistPayloads(bool *,UnionFs::StackEventTracer &)
0x14005272f  mov     sil, [rsp+3A0h+var_360]
0x140052734  test    dil, dil
0x140052737  jz      short loc_140052747
0x140052739  xor     ecx, ecx; ExitStatus
0x14005273b  call    cs:__imp_PsTerminateSystemThread
0x140052742  nop     dword ptr [rax+rax+00h]
0x140052747  cmp     [rsp+3A0h+var_35F], 0
0x14005274c  jnz     short loc_140052766
0x14005274e  test    sil, sil
0x140052751  jnz     short loc_140052766
0x140052753  nop
0x140052754  or      eax, 0FFFFFFFFh
0x140052757  lock xadd [rbx+8], eax
0x14005275c  dec     eax
0x14005275e  nop
0x14005275f  neg     eax
0x140052761  sbb     cl, cl
0x140052763  and     r14b, cl
0x140052766  lea     rcx, [rsp+3A0h+var_330]; this
0x14005276b  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x140052770  test    r14b, r14b
0x140052773  jnz     loc_140052683
0x140052779  jmp     loc_140052618
```
