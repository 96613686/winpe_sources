# CTmProxyCore::~CTmProxyCore(void)

- ea: `0x180023dec`
- end: `0x180024096`
- name: `??1CTmProxyCore@@QEAA@XZ`
- size: `682`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180024730`

## callees

- `0x18001e0e4`
- `0x18001e9ec`
- `0x180023dec`
- `0x18003831c`
- `0x180039c6c`
- `0x18003c590`
- `0x1800414bc`
- `0x18005593c`
- `0x18007c9e0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023f37`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023f37`
- `WS2_32!__imp_WSACleanup` at `0x180023ee8`
- `WS2_32!__imp_WSACleanup` at `0x180023ee8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180023f0e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180023f0e`

## pseudocode

```c
void __fastcall CTmProxyCore::~CTmProxyCore(struct _RTL_CRITICAL_SECTION *this)
{
  ULONG_PTR SpinCount; // rcx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  __int64 v4; // rcx
  HANDLE OwningThread; // rcx
  HANDLE LockSemaphore; // rcx
  ULONG_PTR v7; // rcx
  HANDLE v8; // rcx
  HANDLE v9; // rcx
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CTmProxyCore::`vftable';
  ThreadId = 0;
  SpinCount = this[86].SpinCount;
  if ( SpinCount )
    (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)SpinCount + 16LL))(SpinCount);
  DebugInfo = this[87].DebugInfo;
  if ( DebugInfo )
    (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)&DebugInfo->Type + 16LL))(DebugInfo);
  v4 = *(_QWORD *)&this[87].LockCount;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  OwningThread = this[87].OwningThread;
  if ( OwningThread )
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)OwningThread + 16LL))(OwningThread);
  LockSemaphore = this[87].LockSemaphore;
  if ( LockSemaphore )
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)LockSemaphore + 16LL))(LockSemaphore);
  v7 = this[87].SpinCount;
  if ( v7 )
    (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = this[88].LockSemaphore;
  if ( v8 )
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v8 + 16LL))(v8);
  v9 = this[88].OwningThread;
  if ( v9 )
  {
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v9 + 40LL))(v9);
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)this[88].OwningThread + 16LL))(this[88].OwningThread);
  }
  ShutDownCmEx();
  if ( HIDWORD(this[95].SpinCount) )
    WSACleanup();
  CreateThread(0, 0, FreeLibraryThreadMain, 0, 0, &ThreadId);
  this[84].LockSemaphore = &CITxSnapshot::`vftable';
  this[84].SpinCount = (ULONG_PTR)&CSemExclusive::`vftable';
  DeleteCriticalSection(this + 85);
  this[84].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CImpTmNodeName::`vftable';
  CIDtcNetworkAccessConfig::~CIDtcNetworkAccessConfig((CIDtcNetworkAccessConfig *)&this[83]);
  this[82].OwningThread = &CTipHelper::`vftable';
  CMarshal::~CMarshal((CMarshal *)&this[81].LockSemaphore);
  this[81].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CLuRecoveryFac::`vftable';
  this[80].OwningThread = &CLuSubordinateDtcFac::`vftable';
  this[79].SpinCount = (ULONG_PTR)&CLuRmEnlistFac::`vftable';
  *(_QWORD *)&this[79].LockCount = &CLuConfigure::`vftable';
  this[51].LockSemaphore = &CDtcToXaHelperSinglePipe::`vftable';
  CHashTable::~CHashTable((CHashTable *)&this[52].LockCount);
  this[51].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CDtcToXaHelperFactory::`vftable';
  CDtcToXaMapper::~CDtcToXaMapper((CDtcToXaMapper *)&this[21].LockCount);
  this[20].LockSemaphore = &CImpTransactionTransmitterFactory::`vftable';
  this[20].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CImpTransactionReceiverFactory::`vftable';
  this[19].OwningThread = &CImpTransactionVoterFactory::`vftable';
  CIXAConfig::~CIXAConfig((CIXAConfig *)&this[10].OwningThread);
  CImpIXaMapperFactory::~CImpIXaMapperFactory((CImpIXaMapperFactory *)&this[7].SpinCount);
  this[6].SpinCount = (ULONG_PTR)&CImpIXATransLookup::`vftable'{for `IXATransLookup'};
  this[7].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CImpIXATransLookup::`vftable'{for `IXATransLookup2'};
  *(_QWORD *)&this[7].LockCount = &CImpIXATransLookup::`vftable'{for `ISendReceiveSink'};
  CITransactionImportWhereabouts::~CITransactionImportWhereabouts((CITransactionImportWhereabouts *)&this[4].LockCount);
  this[3].LockSemaphore = &CITransactionDispenser::`vftable';
  this[3].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CIResourceManagerFactory::`vftable';
  this[2].OwningThread = &CITransactionImport::`vftable';
  this[1].SpinCount = (ULONG_PTR)&CITransactionExportFactory::`vftable';
  this[1].DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CITmProxyInit::`vftable';
}

```

## disassembly

```asm
0x180023dec  push    rbx
0x180023dee  sub     rsp, 30h
0x180023df2  mov     rbx, rcx
0x180023df5  lea     rax, ??_7CTmProxyCore@@6B@; const CTmProxyCore::`vftable'
0x180023dfc  mov     [rcx], rax
0x180023dff  mov     [rsp+38h+ThreadId], 0
0x180023e07  mov     rcx, [rcx+0D90h]
0x180023e0e  test    rcx, rcx
0x180023e11  jz      short loc_180023E1F
0x180023e13  mov     rax, [rcx]
0x180023e16  mov     rax, [rax+10h]
0x180023e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e1f  mov     rcx, [rbx+0D98h]
0x180023e26  test    rcx, rcx
0x180023e29  jz      short loc_180023E37
0x180023e2b  mov     rax, [rcx]
0x180023e2e  mov     rax, [rax+10h]
0x180023e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e37  mov     rcx, [rbx+0DA0h]
0x180023e3e  test    rcx, rcx
0x180023e41  jz      short loc_180023E4F
0x180023e43  mov     rax, [rcx]
0x180023e46  mov     rax, [rax+10h]
0x180023e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e4f  mov     rcx, [rbx+0DA8h]
0x180023e56  test    rcx, rcx
0x180023e59  jz      short loc_180023E67
0x180023e5b  mov     rax, [rcx]
0x180023e5e  mov     rax, [rax+10h]
0x180023e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e67  mov     rcx, [rbx+0DB0h]
0x180023e6e  test    rcx, rcx
0x180023e71  jz      short loc_180023E7F
0x180023e73  mov     rax, [rcx]
0x180023e76  mov     rax, [rax+10h]
0x180023e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e7f  mov     rcx, [rbx+0DB8h]
0x180023e86  test    rcx, rcx
0x180023e89  jz      short loc_180023E97
0x180023e8b  mov     rax, [rcx]
0x180023e8e  mov     rax, [rax+10h]
0x180023e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e97  mov     rcx, [rbx+0DD8h]
0x180023e9e  test    rcx, rcx
0x180023ea1  jz      short loc_180023EAF
0x180023ea3  mov     rax, [rcx]
0x180023ea6  mov     rax, [rax+10h]
0x180023eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023eaf  mov     rcx, [rbx+0DD0h]
0x180023eb6  test    rcx, rcx
0x180023eb9  jz      short loc_180023EDA
0x180023ebb  mov     rax, [rcx]
0x180023ebe  mov     rax, [rax+28h]
0x180023ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ec7  mov     rcx, [rbx+0DD0h]
0x180023ece  mov     rax, [rcx]
0x180023ed1  mov     rax, [rax+10h]
0x180023ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023eda  call    ShutDownCmEx
0x180023edf  cmp     dword ptr [rbx+0EFCh], 0
0x180023ee6  jz      short loc_180023EEE
0x180023ee8  call    cs:__imp_WSACleanup
0x180023eee  lea     rax, [rsp+38h+ThreadId]
0x180023ef3  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180023ef8  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180023f00  xor     r9d, r9d; lpParameter
0x180023f03  lea     r8, ?FreeLibraryThreadMain@@YAKPEAX@Z; lpStartAddress
0x180023f0a  xor     edx, edx; dwStackSize
0x180023f0c  xor     ecx, ecx; lpThreadAttributes
0x180023f0e  call    cs:__imp_CreateThread
0x180023f14  lea     rax, ??_7CITxSnapshot@@6B@; const CITxSnapshot::`vftable'
0x180023f1b  mov     [rbx+0D38h], rax
0x180023f22  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x180023f29  mov     [rbx+0D40h], rax
0x180023f30  lea     rcx, [rbx+0D48h]; lpCriticalSection
0x180023f37  call    cs:__imp_DeleteCriticalSection
0x180023f3d  nop
0x180023f3e  lea     rax, ??_7CImpTmNodeName@@6B@; const CImpTmNodeName::`vftable'
0x180023f45  mov     [rbx+0D20h], rax
0x180023f4c  lea     rcx, [rbx+0CF8h]; this
0x180023f53  call    ??1CIDtcNetworkAccessConfig@@QEAA@XZ; CIDtcNetworkAccessConfig::~CIDtcNetworkAccessConfig(void)
0x180023f58  lea     rax, ??_7CTipHelper@@6B@; const CTipHelper::`vftable'
0x180023f5f  mov     [rbx+0CE0h], rax
0x180023f66  lea     rcx, [rbx+0CC0h]; this
0x180023f6d  call    ??1CMarshal@@UEAA@XZ; CMarshal::~CMarshal(void)
0x180023f72  lea     rax, ??_7CLuRecoveryFac@@6B@; const CLuRecoveryFac::`vftable'
0x180023f79  mov     [rbx+0CA8h], rax
0x180023f80  lea     rax, ??_7CLuSubordinateDtcFac@@6B@; const CLuSubordinateDtcFac::`vftable'
0x180023f87  mov     [rbx+0C90h], rax
0x180023f8e  lea     rax, ??_7CLuRmEnlistFac@@6B@; const CLuRmEnlistFac::`vftable'
0x180023f95  mov     [rbx+0C78h], rax
0x180023f9c  lea     rax, ??_7CLuConfigure@@6B@; const CLuConfigure::`vftable'
0x180023fa3  mov     [rbx+0C60h], rax
0x180023faa  lea     rax, ??_7CDtcToXaHelperSinglePipe@@6B@; const CDtcToXaHelperSinglePipe::`vftable'
0x180023fb1  mov     [rbx+810h], rax
0x180023fb8  lea     rcx, [rbx+828h]; this
0x180023fbf  call    ??1CHashTable@@QEAA@XZ; CHashTable::~CHashTable(void)
0x180023fc4  lea     rax, ??_7CDtcToXaHelperFactory@@6B@; const CDtcToXaHelperFactory::`vftable'
0x180023fcb  mov     [rbx+7F8h], rax
0x180023fd2  lea     rcx, [rbx+350h]; this
0x180023fd9  call    ??1CDtcToXaMapper@@QEAA@XZ; CDtcToXaMapper::~CDtcToXaMapper(void)
0x180023fde  lea     rax, ??_7CImpTransactionTransmitterFactory@@6B@; const CImpTransactionTransmitterFactory::`vftable'
0x180023fe5  mov     [rbx+338h], rax
0x180023fec  lea     rax, ??_7CImpTransactionReceiverFactory@@6B@; const CImpTransactionReceiverFactory::`vftable'
0x180023ff3  mov     [rbx+320h], rax
0x180023ffa  lea     rax, ??_7CImpTransactionVoterFactory@@6B@; const CImpTransactionVoterFactory::`vftable'
0x180024001  mov     [rbx+308h], rax
0x180024008  lea     rcx, [rbx+1A0h]; this
0x18002400f  call    ??1CIXAConfig@@QEAA@XZ; CIXAConfig::~CIXAConfig(void)
0x180024014  lea     rcx, [rbx+138h]; this
0x18002401b  call    ??1CImpIXaMapperFactory@@QEAA@XZ; CImpIXaMapperFactory::~CImpIXaMapperFactory(void)
0x180024020  lea     rax, ??_7CImpIXATransLookup@@6BIXATransLookup@@@; const CImpIXATransLookup::`vftable'{for `IXATransLookup'}
0x180024027  mov     [rbx+110h], rax
0x18002402e  lea     rax, ??_7CImpIXATransLookup@@6BIXATransLookup2@@@; const CImpIXATransLookup::`vftable'{for `IXATransLookup2'}
0x180024035  mov     [rbx+118h], rax
0x18002403c  lea     rax, ??_7CImpIXATransLookup@@6BISendReceiveSink@@@; const CImpIXATransLookup::`vftable'{for `ISendReceiveSink'}
0x180024043  mov     [rbx+120h], rax
0x18002404a  lea     rcx, [rbx+0A8h]; this
0x180024051  call    ??1CITransactionImportWhereabouts@@QEAA@XZ; CITransactionImportWhereabouts::~CITransactionImportWhereabouts(void)
0x180024056  lea     rax, ??_7CITransactionDispenser@@6B@; const CITransactionDispenser::`vftable'
0x18002405d  mov     [rbx+90h], rax
0x180024064  lea     rax, ??_7CIResourceManagerFactory@@6B@; const CIResourceManagerFactory::`vftable'
0x18002406b  mov     [rbx+78h], rax
0x18002406f  lea     rax, ??_7CITransactionImport@@6B@; const CITransactionImport::`vftable'
0x180024076  mov     [rbx+60h], rax
0x18002407a  lea     rax, ??_7CITransactionExportFactory@@6B@; const CITransactionExportFactory::`vftable'
0x180024081  mov     [rbx+48h], rax
0x180024085  lea     rax, ??_7CITmProxyInit@@6B@; const CITmProxyInit::`vftable'
0x18002408c  mov     [rbx+28h], rax
0x180024090  add     rsp, 30h
0x180024094  pop     rbx
0x180024095  retn
```
