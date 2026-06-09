# UnionFs::UfsPersistenceManager::PersistPayloadsWorker(void *)

- ea: `0x1400526b0`
- end: `0x1400528fe`
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
- `0x140052188`
- `0x1400526b0`
- `0x14007b2b0`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!PsTerminateSystemThread` at `0x1400528bb`
- `ntoskrnl!PsTerminateSystemThread` at `0x1400528bb`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400527c4`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400527c4`
- `ntoskrnl!KeWaitForSingleObject` at `0x140052826`
- `ntoskrnl!KeWaitForSingleObject` at `0x140052826`
- `ntoskrnl!KeSetEvent` at `0x140052777`
- `ntoskrnl!KeSetEvent` at `0x140052777`

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
      (unsigned int)&dword_140098134,
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
0x1400526b0  push    rbp
0x1400526b2  push    rbx
0x1400526b3  push    rsi
0x1400526b4  push    rdi
0x1400526b5  push    r14
0x1400526b7  push    r15
0x1400526b9  lea     rbp, [rsp-278h]
0x1400526c1  sub     rsp, 378h
0x1400526c8  mov     rax, cs:__security_cookie
0x1400526cf  xor     rax, rsp
0x1400526d2  mov     [rbp+2A0h+var_40], rax
0x1400526d9  mov     eax, cs:dword_14009E178
0x1400526df  mov     rbx, rcx
0x1400526e2  cmp     eax, 5
0x1400526e5  jbe     loc_14005276E
0x1400526eb  mov     rcx, cs:qword_14009E190
0x1400526f2  mov     edx, 8000h
0x1400526f7  mov     rax, cs:qword_14009E188
0x1400526fe  test    rdx, rax
0x140052701  jz      short loc_14005276E
0x140052703  mov     rax, rcx
0x140052706  and     rax, rdx
0x140052709  cmp     rax, rcx
0x14005270c  jnz     short loc_14005276E
0x14005270e  lea     rax, aOnecoreBaseFsU_1; "onecore\\base\\fs\\unionfs\\sys\\persis"...
0x140052715  mov     [rsp+3A0h+var_35C], 206h
0x14005271d  mov     [rsp+3A0h+var_350], rax
0x140052722  lea     rdx, dword_140098134
0x140052729  lea     rax, aUnionfsUfspers_6; "UnionFs::UfsPersistenceManager::Persist"...
0x140052730  mov     [rsp+3A0h+var_348], rax
0x140052735  lea     rax, aEnter; "ENTER"
0x14005273c  mov     qword ptr [rsp+3A0h+var_358], rax
0x140052741  lea     rax, [rsp+3A0h+var_35C]
0x140052746  mov     [rsp+3A0h+WaitBlockArray], rax
0x14005274b  lea     rax, [rsp+3A0h+var_350]
0x140052750  mov     [rsp+3A0h+Timeout], rax
0x140052755  lea     rax, [rsp+3A0h+var_348]
0x14005275a  mov     qword ptr [rsp+3A0h+Alertable], rax
0x14005275f  lea     rax, [rsp+3A0h+var_358]
0x140052764  mov     qword ptr [rsp+3A0h+WaitMode], rax
0x140052769  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14005276e  lea     rcx, [rbx+40h]; Event
0x140052772  xor     r8d, r8d; Wait
0x140052775  xor     edx, edx; Increment
0x140052777  call    cs:__imp_KeSetEvent
0x14005277e  nop     dword ptr [rax+rax+00h]
0x140052783  lea     rax, [rbx+10h]
0x140052787  xor     dil, dil
0x14005278a  lea     r15, [rbx+28h]
0x14005278e  mov     [rsp+3A0h+Object], rax
0x140052793  mov     [rsp+3A0h+var_338], r15
0x140052798  xor     r9d, r9d; WaitReason
0x14005279b  mov     [rsp+3A0h+WaitBlockArray], 0; WaitBlockArray
0x1400527a4  mov     [rsp+3A0h+Timeout], 0; Timeout
0x1400527ad  lea     rdx, [rsp+3A0h+Object]; Object
0x1400527b2  mov     [rsp+3A0h+Alertable], 0; Alertable
0x1400527b7  mov     [rsp+3A0h+WaitMode], 0; WaitMode
0x1400527bc  lea     r8d, [r9+1]; WaitType
0x1400527c0  lea     ecx, [r9+2]; Count
0x1400527c4  call    cs:__imp_KeWaitForMultipleObjects
0x1400527cb  nop     dword ptr [rax+rax+00h]
0x1400527d0  cmp     eax, 1
0x1400527d3  jnz     short loc_1400527DA
0x1400527d5  mov     dil, al
0x1400527d8  jmp     short loc_140052800
0x1400527da  test    eax, eax
0x1400527dc  jz      short loc_1400527EA
0x1400527de  lea     rcx, aStatusStatusWa; "status == STATUS_WAIT_0"
0x1400527e5  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400527ea  cmp     cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA, 0; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400527f2  jnz     short loc_140052800
0x1400527f4  lea     rcx, aGFilterstate; "g_FilterState"
0x1400527fb  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140052800  mov     r14b, 1
0x140052803  test    dil, dil
0x140052806  jnz     short loc_140052859
0x140052808  lea     rax, [rsp+3A0h+var_358]
0x14005280d  mov     qword ptr [rsp+3A0h+var_358], 0FFFFFFFFFECED300h
0x140052816  xor     r9d, r9d; Alertable
0x140052819  mov     qword ptr [rsp+3A0h+WaitMode], rax; Timeout
0x14005281e  xor     r8d, r8d; WaitMode
0x140052821  xor     edx, edx; WaitReason
0x140052823  mov     rcx, r15; Object
0x140052826  call    cs:__imp_KeWaitForSingleObject
0x14005282d  nop     dword ptr [rax+rax+00h]
0x140052832  test    eax, eax
0x140052834  jnz     short loc_14005283B
0x140052836  mov     dil, 1
0x140052839  jmp     short loc_140052859
0x14005283b  cmp     eax, 102h
0x140052840  jz      short loc_14005284E
0x140052842  lea     rcx, aStatusStatusTi; "status == STATUS_TIMEOUT"
0x140052849  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14005284e  nop
0x14005284f  mov     dword ptr [rbx+8], 1
0x140052856  mfence
0x140052859  mov     rdx, 2D30017025Ah; unsigned __int64
0x140052863  lea     rcx, [rsp+3A0h+var_330]; this
0x140052868  call    ??0StackEventTracer@UnionFs@@QEAA@_K@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64)
0x14005286d  xor     sil, sil
0x140052870  mov     [rsp+3A0h+var_35F], 0
0x140052875  cmp     cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA, 0; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14005287d  mov     [rsp+3A0h+var_360], sil
0x140052882  jz      short loc_1400528B4
0x140052884  mov     rax, [rbx]
0x140052887  lea     r8, [rsp+3A0h+var_330]
0x14005288c  lea     rdx, [rsp+3A0h+var_35F]
0x140052891  mov     rcx, rbx
0x140052894  mov     rax, [rax+40h]
0x140052898  call    _guard_dispatch_icall
0x14005289d  lea     r8, [rsp+3A0h+var_330]; struct UnionFs::StackEventTracer *
0x1400528a2  mov     rcx, rbx; this
0x1400528a5  lea     rdx, [rsp+3A0h+var_360]; bool *
0x1400528aa  call    ?PersistPayloads@UfsPersistenceManager@UnionFs@@QEBAJPEA_NAEAVStackEventTracer@2@@Z; UnionFs::UfsPersistenceManager::PersistPayloads(bool *,UnionFs::StackEventTracer &)
0x1400528af  mov     sil, [rsp+3A0h+var_360]
0x1400528b4  test    dil, dil
0x1400528b7  jz      short loc_1400528C7
0x1400528b9  xor     ecx, ecx; ExitStatus
0x1400528bb  call    cs:__imp_PsTerminateSystemThread
0x1400528c2  nop     dword ptr [rax+rax+00h]
0x1400528c7  cmp     [rsp+3A0h+var_35F], 0
0x1400528cc  jnz     short loc_1400528E6
0x1400528ce  test    sil, sil
0x1400528d1  jnz     short loc_1400528E6
0x1400528d3  nop
0x1400528d4  or      eax, 0FFFFFFFFh
0x1400528d7  lock xadd [rbx+8], eax
0x1400528dc  dec     eax
0x1400528de  nop
0x1400528df  neg     eax
0x1400528e1  sbb     cl, cl
0x1400528e3  and     r14b, cl
0x1400528e6  lea     rcx, [rsp+3A0h+var_330]; this
0x1400528eb  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x1400528f0  test    r14b, r14b
0x1400528f3  jnz     loc_140052803
0x1400528f9  jmp     loc_140052798
```
