# CPipeManager::StartUpdateEncodingSequence(void)

- ea: `0x18009eb90`
- end: `0x18009effc`
- name: `?StartUpdateEncodingSequence@CPipeManager@@IEAAJXZ`
- size: `1132`
- prototype: `__int64 __fastcall(CPipeManager *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update`

## callers

- `0x18005a85c`

## callees

- `0x180001308`
- `0x180001f84`
- `0x18000202c`
- `0x18000ce04`
- `0x18000ce34`
- `0x180028a30`
- `0x18002aafc`
- `0x18004af40`
- `0x18004f5bc`
- `0x18004fc5c`
- `0x18005c334`
- `0x18009eb90`
- `0x180158180`
- `0x18019c010`

## import_xrefs

- `RDPBASE!?GetInstance@PipelineClock@@SAAEAV1@XZ` at `0x18009ee89`
- `RDPBASE!?GetInstance@PipelineClock@@SAAEAV1@XZ` at `0x18009ef88`
- `RDPBASE!?GetInstance@PipelineClock@@SAAEAV1@XZ` at `0x18009efab`
- `RDPBASE!?GetInstance@PipelineClock@@SAAEAV1@XZ` at `0x18009efc2`
- `RDPBASE!?GetInstance@PipelineClock@@SAAEAV1@XZ` at `0x18009ee89`
- `RDPBASE!?GetInstance@PipelineClock@@SAAEAV1@XZ` at `0x18009ef88`
- `RDPBASE!?GetInstance@PipelineClock@@SAAEAV1@XZ` at `0x18009efab`
- `RDPBASE!?GetInstance@PipelineClock@@SAAEAV1@XZ` at `0x18009efc2`
- `RDPBASE!?GetMillisecondCount@PipelineClock@@QEAAIXZ` at `0x18009ee92`
- `RDPBASE!?GetMillisecondCount@PipelineClock@@QEAAIXZ` at `0x18009ef91`
- `RDPBASE!?GetMillisecondCount@PipelineClock@@QEAAIXZ` at `0x18009efb4`
- `RDPBASE!?GetMillisecondCount@PipelineClock@@QEAAIXZ` at `0x18009efcb`
- `RDPBASE!?GetMillisecondCount@PipelineClock@@QEAAIXZ` at `0x18009ee92`
- `RDPBASE!?GetMillisecondCount@PipelineClock@@QEAAIXZ` at `0x18009ef91`
- `RDPBASE!?GetMillisecondCount@PipelineClock@@QEAAIXZ` at `0x18009efb4`
- `RDPBASE!?GetMillisecondCount@PipelineClock@@QEAAIXZ` at `0x18009efcb`

## string_xrefs

- `0x18009ec2a`: `UpdateFbrProfileState failed`
- `0x18009ecf6`: `PipeManagerError_StartUpdateEncSeqLockCtxDataAndProcessUpdatesFail`
- `0x18009eda5`: `PipeManagerError_StartUpdateEncSeqLockCtxDataAndProcessUpdatesFail`
- `0x18009ec43`: `StartUpdateEncodingSequence`
- `0x18009ed37`: `StartUpdateEncodingSequence`
- `0x18009ede6`: `StartUpdateEncodingSequence`
- `0x18009ed1e`: `LockContextDataAndProcessUpdates failed!`
- `0x18009edcd`: `ProcessStoredUpdates failed!`
- `0x18009eeaf`: `Frame: no graphics update. Elapsed time since last loop run`
- `0x18009ef03`: `Frame: too soon since last graphics update; skip this no graphics update loop`
- `0x18009ef62`: `Frame: Starting pipeline loop with no graphics update`

## pseudocode

```c
__int64 __fastcall CPipeManager::StartUpdateEncodingSequence(CPipeManager *this)
{
  __int64 *v2; // rbx
  int v3; // r12d
  __int64 *v4; // rdi
  int v5; // r8d
  int v6; // r9d
  int updated; // r14d
  int v8; // ecx
  char *v9; // rdx
  const char **v10; // rax
  char *v11; // rdx
  __int64 v12; // rax
  signed int v13; // eax
  signed int v14; // eax
  __int64 TimeHNS; // rax
  unsigned int v16; // edx
  struct IRDPPerfCounterGeneric *v17; // rcx
  bool v18; // zf
  int v19; // edi
  PipelineClock *v20; // rax
  unsigned int v21; // eax
  int v22; // r8d
  int v23; // r9d
  int v24; // ecx
  int v25; // r15d
  unsigned int v26; // edi
  int v27; // r8d
  int v28; // ebx
  PipelineClock *v29; // rax
  unsigned int v30; // ecx
  unsigned int MillisecondCount; // ecx
  PipelineClock *Instance; // rax
  PipelineClock *v33; // rax
  int v35; // [rsp+20h] [rbp-50h]
  const char **v36; // [rsp+30h] [rbp-40h]
  const char **v37; // [rsp+40h] [rbp-30h]
  const char **v38; // [rsp+48h] [rbp-28h]
  const char *v39; // [rsp+50h] [rbp-20h] BYREF
  const char *v40; // [rsp+58h] [rbp-18h] BYREF
  const char *v41; // [rsp+60h] [rbp-10h] BYREF
  const char *v42; // [rsp+68h] [rbp-8h] BYREF
  int v43; // [rsp+B0h] [rbp+40h] BYREF
  const char *v44; // [rsp+B8h] [rbp+48h] BYREF
  const char *v45; // [rsp+C0h] [rbp+50h] BYREF
  __int64 *v46; // [rsp+C8h] [rbp+58h] BYREF

  v43 = 0;
  v2 = 0;
  v44 = (char *)this + 48896;
  v46 = 0;
  CTSCriticalSection::Lock((CPipeManager *)((char *)this + 48896));
  v3 = *((_DWORD *)this + 13260);
  v43 = *((_DWORD *)this + 13265);
  if ( *((_QWORD *)this + 1625) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease(&v46);
    v46 = (__int64 *)*((_QWORD *)this + 1625);
    v2 = v46;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v46);
    v4 = v2;
  }
  else
  {
    v4 = 0;
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v44);
  updated = CPipeManager::UpdateFbrProfileState(this);
  if ( updated >= 0 )
  {
    *((_QWORD *)this + 6649) = CPipeManager::GetTimeHNS((CPipeManager *)((char *)this + 8));
    if ( v4 )
    {
      v11 = (char *)this + 53096;
      v12 = *v4;
      if ( *((_DWORD *)this + 13436) )
      {
        v14 = (*(__int64 (__fastcall **)(__int64 *, char *, int *))(v12 + 40))(v4, v11, &v43);
        updated = v14;
        if ( v14 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
            "PipeManagerError_StartUpdateEncSeqLockCtxDataAndProcessUpdatesFail",
            (char *)0x1BF7,
            v14,
            v35);
          if ( (unsigned int)CallbackContext <= 2 )
            goto LABEL_31;
          LODWORD(v44) = 7160;
          v42 = "ProcessStoredUpdates failed!";
          v9 = &byte_180277317;
          v41 = "StartUpdateEncodingSequence";
          v40 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
          v39 = "Error HResult failed";
          v38 = &v42;
          v37 = &v41;
          v36 = &v40;
          v10 = &v39;
          goto LABEL_7;
        }
      }
      else
      {
        v13 = (*(__int64 (__fastcall **)(__int64 *, char *, int *))(v12 + 24))(v4, v11, &v43);
        updated = v13;
        if ( v13 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
            "PipeManagerError_StartUpdateEncSeqLockCtxDataAndProcessUpdatesFail",
            (char *)0x1BF1,
            v13,
            v35);
          if ( (unsigned int)CallbackContext <= 2 )
            goto LABEL_31;
          LODWORD(v44) = 7154;
          v42 = "LockContextDataAndProcessUpdates failed!";
          v9 = byte_180277365;
          v41 = "StartUpdateEncodingSequence";
          v40 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
          v39 = "Error HResult failed";
          v38 = &v42;
          v37 = &v41;
          v36 = &v40;
          v10 = &v39;
          goto LABEL_7;
        }
      }
    }
    TimeHNS = CPipeManager::GetTimeHNS((CPipeManager *)((char *)this + 8));
    v16 = *((_DWORD *)this + 13250);
    v17 = (struct IRDPPerfCounterGeneric *)*((_QWORD *)this + 6602);
    *((_QWORD *)this + 6650) = TimeHNS;
    PerfCounterSetRdpIntervalMarker(v17, v16, 0);
    v18 = v43 == 0;
    *((_QWORD *)this + 6653) = *((_QWORD *)this + 6650);
    if ( !v18 || v3 )
    {
      Instance = (PipelineClock *)PipelineClock::GetInstance();
      MillisecondCount = PipelineClock::GetMillisecondCount(Instance);
    }
    else
    {
      v19 = *((_DWORD *)this + 13253);
      v20 = (PipelineClock *)PipelineClock::GetInstance();
      v21 = PipelineClock::GetMillisecondCount(v20);
      v24 = (int)CallbackContext;
      v25 = v21 - v19;
      v26 = *((_DWORD *)this + 13254);
      if ( (unsigned int)CallbackContext > 5 )
      {
        LODWORD(v44) = v25;
        v45 = "Frame: no graphics update. Elapsed time since last loop run";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)CallbackContext,
          (unsigned int)qword_1802772E8,
          v22,
          v23,
          (__int64)&v45,
          (__int64)&v44);
      }
      if ( v25 + 5 < v26 )
      {
        if ( v2 )
          (*(void (__fastcall **)(__int64 *))(*v2 + 48))(v2);
        if ( (unsigned int)CallbackContext > 5 )
        {
          v44 = "Frame: too soon since last graphics update; skip this no graphics update loop";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v24,
            (unsigned int)&word_1802772C6,
            v22,
            v23,
            (__int64)&v44);
        }
        PerfCounterSetRdpIntervalMarker(
          *((struct IRDPPerfCounterGeneric **)this + 6612),
          *((_DWORD *)this + 13249),
          0x66u);
        *((_DWORD *)this + 13248) = 17;
        CPipeManager::ScheduleTask(this, v26 - v25, v27);
        goto LABEL_31;
      }
      if ( (unsigned int)CallbackContext > 5 )
      {
        v44 = "Frame: Starting pipeline loop with no graphics update";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v24,
          (unsigned int)&dword_1802772A4,
          v22,
          v23,
          (__int64)&v44);
      }
      v28 = *((_DWORD *)this + 13251);
      v29 = (PipelineClock *)PipelineClock::GetInstance();
      v30 = PipelineClock::GetMillisecondCount(v29) - v28;
      MillisecondCount = v28 + v30 - v30 % *((_DWORD *)this + 13254);
    }
    *((_DWORD *)this + 13251) = MillisecondCount;
    v33 = (PipelineClock *)PipelineClock::GetInstance();
    *((_DWORD *)this + 13252) = PipelineClock::GetMillisecondCount(v33);
    *((_DWORD *)this + 13248) = 7;
    goto LABEL_31;
  }
  v8 = (int)CallbackContext;
  if ( (unsigned int)CallbackContext > 2 )
  {
    LODWORD(v44) = 7144;
    v39 = "UpdateFbrProfileState failed";
    v9 = byte_1802773B3;
    v40 = "StartUpdateEncodingSequence";
    v41 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
    v42 = "Error HResult failed";
    v38 = &v39;
    v37 = &v40;
    v36 = &v41;
    v10 = &v42;
LABEL_7:
    LODWORD(v45) = updated;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v8,
      (_DWORD)v9,
      v5,
      v6,
      (__int64)v10,
      (__int64)&v45,
      (__int64)v36,
      (__int64)&v44,
      (__int64)v37,
      (__int64)v38);
  }
LABEL_31:
  TCntPtr<IRdpVCMgr>::SafeRelease(&v46);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18009eb90  push    rbp
0x18009eb92  push    rbx
0x18009eb93  push    rsi
0x18009eb94  push    rdi
0x18009eb95  push    r12
0x18009eb97  push    r14
0x18009eb99  push    r15
0x18009eb9b  mov     rbp, rsp
0x18009eb9e  sub     rsp, 70h
0x18009eba2  mov     rsi, rcx
0x18009eba5  mov     [rbp+arg_0], 0
0x18009ebac  add     rcx, 0BF00h; this
0x18009ebb3  xor     ebx, ebx
0x18009ebb5  mov     [rbp+arg_8], rcx
0x18009ebb9  mov     [rbp+arg_18], rbx
0x18009ebbd  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x18009ebc2  mov     eax, [rsi+0CF44h]
0x18009ebc8  mov     r12d, [rsi+0CF30h]
0x18009ebcf  mov     [rbp+arg_0], eax
0x18009ebd2  cmp     [rsi+32C8h], rbx
0x18009ebd9  jnz     short loc_18009EBDF
0x18009ebdb  xor     edi, edi
0x18009ebdd  jmp     short loc_18009EBFF
0x18009ebdf  lea     rcx, [rbp+arg_18]
0x18009ebe3  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18009ebe8  mov     rbx, [rsi+32C8h]
0x18009ebef  lea     rcx, [rbp+arg_18]
0x18009ebf3  mov     [rbp+arg_18], rbx
0x18009ebf7  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18009ebfc  mov     rdi, rbx
0x18009ebff  lea     rcx, [rbp+arg_8]; this
0x18009ec03  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18009ec08  mov     rcx, rsi; this
0x18009ec0b  call    ?UpdateFbrProfileState@CPipeManager@@IEAAJXZ; CPipeManager::UpdateFbrProfileState(void)
0x18009ec10  mov     r14d, eax
0x18009ec13  test    eax, eax
0x18009ec15  jns     loc_18009ECA8
0x18009ec1b  mov     ecx, cs:CallbackContext
0x18009ec21  cmp     ecx, 2
0x18009ec24  jbe     loc_18009EFE1
0x18009ec2a  lea     rax, aUpdatefbrprofi; "UpdateFbrProfileState failed"
0x18009ec31  mov     dword ptr [rbp+arg_8], 1BE8h
0x18009ec38  mov     [rbp+var_20], rax
0x18009ec3c  lea     rdx, byte_1802773B3
0x18009ec43  lea     rax, aStartupdateenc; "StartUpdateEncodingSequence"
0x18009ec4a  mov     [rbp+var_18], rax
0x18009ec4e  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18009ec55  mov     [rbp+var_10], rax
0x18009ec59  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18009ec60  mov     [rbp+var_8], rax
0x18009ec64  lea     rax, [rbp+var_20]
0x18009ec68  mov     [rsp+70h+var_28], rax
0x18009ec6d  lea     rax, [rbp+var_18]
0x18009ec71  mov     [rsp+70h+var_30], rax
0x18009ec76  lea     rax, [rbp+arg_8]
0x18009ec7a  mov     [rsp+70h+var_38], rax
0x18009ec7f  lea     rax, [rbp+var_10]
0x18009ec83  mov     [rsp+70h+var_40], rax
0x18009ec88  lea     rax, [rbp+arg_10]
0x18009ec8c  mov     [rsp+70h+var_48], rax
0x18009ec91  lea     rax, [rbp+var_8]
0x18009ec95  mov     dword ptr [rbp+arg_10], r14d
0x18009ec99  mov     [rsp+70h+var_50], rax
0x18009ec9e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18009eca3  jmp     loc_18009EFE1
0x18009eca8  lea     rcx, [rsi+8]; this
0x18009ecac  call    ?GetTimeHNS@CPipeManager@@UEAA_JXZ; CPipeManager::GetTimeHNS(void)
0x18009ecb1  mov     [rsi+0CFC8h], rax
0x18009ecb8  test    rdi, rdi
0x18009ecbb  jz      loc_18009EE3D
0x18009ecc1  cmp     dword ptr [rsi+0D1F0h], 0
0x18009ecc8  lea     rdx, [rsi+0CF68h]
0x18009eccf  mov     rax, [rdi]
0x18009ecd2  lea     r8, [rbp+arg_0]
0x18009ecd6  mov     rcx, rdi
0x18009ecd9  jnz     loc_18009ED8E
0x18009ecdf  mov     rax, [rax+18h]
0x18009ece3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ece8  mov     r14d, eax
0x18009eceb  test    eax, eax
0x18009eced  jns     loc_18009EE3D
0x18009ecf3  mov     r9d, eax; unsigned int
0x18009ecf6  lea     rdx, aPipemanagererr_21; "PipeManagerError_StartUpdateEncSeqLockC"...
0x18009ecfd  mov     r8d, 1BF1h; char *
0x18009ed03  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x18009ed0a  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18009ed0f  mov     eax, cs:CallbackContext
0x18009ed15  cmp     eax, 2
0x18009ed18  jbe     loc_18009EFE1
0x18009ed1e  lea     rax, aLockcontextdat_1; "LockContextDataAndProcessUpdates failed"...
0x18009ed25  mov     dword ptr [rbp+arg_8], 1BF2h
0x18009ed2c  mov     [rbp+var_8], rax
0x18009ed30  lea     rdx, byte_180277365
0x18009ed37  lea     rax, aStartupdateenc; "StartUpdateEncodingSequence"
0x18009ed3e  mov     [rbp+var_10], rax
0x18009ed42  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18009ed49  mov     [rbp+var_18], rax
0x18009ed4d  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18009ed54  mov     [rbp+var_20], rax
0x18009ed58  lea     rax, [rbp+var_8]
0x18009ed5c  mov     [rsp+70h+var_28], rax
0x18009ed61  lea     rax, [rbp+var_10]
0x18009ed65  mov     [rsp+70h+var_30], rax
0x18009ed6a  lea     rax, [rbp+arg_8]
0x18009ed6e  mov     [rsp+70h+var_38], rax
0x18009ed73  lea     rax, [rbp+var_18]
0x18009ed77  mov     [rsp+70h+var_40], rax
0x18009ed7c  lea     rax, [rbp+arg_10]
0x18009ed80  mov     [rsp+70h+var_48], rax
0x18009ed85  lea     rax, [rbp+var_20]
0x18009ed89  jmp     loc_18009EC95
0x18009ed8e  mov     rax, [rax+28h]
0x18009ed92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ed97  mov     r14d, eax
0x18009ed9a  test    eax, eax
0x18009ed9c  jns     loc_18009EE3D
0x18009eda2  mov     r9d, eax; unsigned int
0x18009eda5  lea     rdx, aPipemanagererr_21; "PipeManagerError_StartUpdateEncSeqLockC"...
0x18009edac  mov     r8d, 1BF7h; char *
0x18009edb2  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x18009edb9  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18009edbe  mov     eax, cs:CallbackContext
0x18009edc4  cmp     eax, 2
0x18009edc7  jbe     loc_18009EFE1
0x18009edcd  lea     rax, aProcessstoredu; "ProcessStoredUpdates failed!"
0x18009edd4  mov     dword ptr [rbp+arg_8], 1BF8h
0x18009eddb  mov     [rbp+var_8], rax
0x18009eddf  lea     rdx, byte_180277317
0x18009ede6  lea     rax, aStartupdateenc; "StartUpdateEncodingSequence"
0x18009eded  mov     [rbp+var_10], rax
0x18009edf1  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18009edf8  mov     [rbp+var_18], rax
0x18009edfc  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18009ee03  mov     [rbp+var_20], rax
0x18009ee07  lea     rax, [rbp+var_8]
0x18009ee0b  mov     [rsp+70h+var_28], rax
0x18009ee10  lea     rax, [rbp+var_10]
0x18009ee14  mov     [rsp+70h+var_30], rax
0x18009ee19  lea     rax, [rbp+arg_8]
0x18009ee1d  mov     [rsp+70h+var_38], rax
0x18009ee22  lea     rax, [rbp+var_18]
0x18009ee26  mov     [rsp+70h+var_40], rax
0x18009ee2b  lea     rax, [rbp+arg_10]
0x18009ee2f  mov     [rsp+70h+var_48], rax
0x18009ee34  lea     rax, [rbp+var_20]
0x18009ee38  jmp     loc_18009EC95
0x18009ee3d  lea     rcx, [rsi+8]; this
0x18009ee41  call    ?GetTimeHNS@CPipeManager@@UEAA_JXZ; CPipeManager::GetTimeHNS(void)
0x18009ee46  mov     edx, [rsi+0CF08h]; unsigned int
0x18009ee4c  xor     r8d, r8d; unsigned int
0x18009ee4f  mov     rcx, [rsi+0CE50h]; struct IRDPPerfCounterGeneric *
0x18009ee56  mov     [rsi+0CFD0h], rax
0x18009ee5d  call    ?PerfCounterSetRdpIntervalMarker@@YAJPEAUIRDPPerfCounterGeneric@@II@Z; PerfCounterSetRdpIntervalMarker(IRDPPerfCounterGeneric *,uint,uint)
0x18009ee62  cmp     [rbp+arg_0], 0
0x18009ee66  mov     rax, [rsi+0CFD0h]
0x18009ee6d  mov     [rsi+0CFE8h], rax
0x18009ee74  jnz     loc_18009EFAB
0x18009ee7a  test    r12d, r12d
0x18009ee7d  jnz     loc_18009EFAB
0x18009ee83  mov     edi, [rsi+0CF14h]
0x18009ee89  call    cs:__imp_?GetInstance@PipelineClock@@SAAEAV1@XZ; PipelineClock::GetInstance(void)
0x18009ee8f  mov     rcx, rax
0x18009ee92  call    cs:__imp_?GetMillisecondCount@PipelineClock@@QEAAIXZ; PipelineClock::GetMillisecondCount(void)
0x18009ee98  mov     ecx, cs:CallbackContext
0x18009ee9e  mov     r15d, eax
0x18009eea1  sub     r15d, edi
0x18009eea4  mov     edi, [rsi+0CF18h]
0x18009eeaa  cmp     ecx, 5
0x18009eead  jbe     short loc_18009EEDC
0x18009eeaf  lea     rax, aFrameNoGraphic; "Frame: no graphics update. Elapsed time"...
0x18009eeb6  mov     dword ptr [rbp+arg_8], r15d
0x18009eeba  mov     [rbp+arg_10], rax
0x18009eebe  lea     rdx, qword_1802772E8
0x18009eec5  lea     rax, [rbp+arg_8]
0x18009eec9  mov     [rsp+70h+var_48], rax
0x18009eece  lea     rax, [rbp+arg_10]
0x18009eed2  mov     [rsp+70h+var_50], rax
0x18009eed7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18009eedc  lea     eax, [r15+5]
0x18009eee0  cmp     eax, edi
0x18009eee2  jnb     short loc_18009EF57
0x18009eee4  test    rbx, rbx
0x18009eee7  jz      short loc_18009EEF8
0x18009eee9  mov     rax, [rbx]
0x18009eeec  mov     rcx, rbx
0x18009eeef  mov     rax, [rax+30h]
0x18009eef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009eef8  mov     eax, cs:CallbackContext
0x18009eefe  cmp     eax, 5
0x18009ef01  jbe     short loc_18009EF23
0x18009ef03  lea     rax, aFrameTooSoonSi; "Frame: too soon since last graphics upd"...
0x18009ef0a  mov     [rbp+arg_8], rax
0x18009ef0e  lea     rdx, word_1802772C6
0x18009ef15  lea     rax, [rbp+arg_8]
0x18009ef19  mov     [rsp+70h+var_50], rax
0x18009ef1e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009ef23  mov     edx, [rsi+0CF04h]; unsigned int
0x18009ef29  mov     r8d, 66h ; 'f'; unsigned int
0x18009ef2f  mov     rcx, [rsi+0CEA0h]; struct IRDPPerfCounterGeneric *
0x18009ef36  call    ?PerfCounterSetRdpIntervalMarker@@YAJPEAUIRDPPerfCounterGeneric@@II@Z; PerfCounterSetRdpIntervalMarker(IRDPPerfCounterGeneric *,uint,uint)
0x18009ef3b  sub     edi, r15d
0x18009ef3e  mov     dword ptr [rsi+0CF00h], 11h
0x18009ef48  mov     edx, edi; unsigned int
0x18009ef4a  mov     rcx, rsi; this
0x18009ef4d  call    ?ScheduleTask@CPipeManager@@IEAAXIH@Z; CPipeManager::ScheduleTask(uint,int)
0x18009ef52  jmp     loc_18009EFE1
0x18009ef57  mov     eax, cs:CallbackContext
0x18009ef5d  cmp     eax, 5
0x18009ef60  jbe     short loc_18009EF82
0x18009ef62  lea     rax, aFrameStartingP; "Frame: Starting pipeline loop with no g"...
0x18009ef69  mov     [rbp+arg_8], rax
0x18009ef6d  lea     rdx, dword_1802772A4
0x18009ef74  lea     rax, [rbp+arg_8]
0x18009ef78  mov     [rsp+70h+var_50], rax
0x18009ef7d  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009ef82  mov     ebx, [rsi+0CF0Ch]
0x18009ef88  call    cs:__imp_?GetInstance@PipelineClock@@SAAEAV1@XZ; PipelineClock::GetInstance(void)
0x18009ef8e  mov     rcx, rax
0x18009ef91  call    cs:__imp_?GetMillisecondCount@PipelineClock@@QEAAIXZ; PipelineClock::GetMillisecondCount(void)
0x18009ef97  mov     ecx, eax
0x18009ef99  xor     edx, edx
0x18009ef9b  sub     ecx, ebx
0x18009ef9d  mov     eax, ecx
0x18009ef9f  div     dword ptr [rsi+0CF18h]
0x18009efa5  sub     ecx, edx
0x18009efa7  add     ecx, ebx
0x18009efa9  jmp     short loc_18009EFBC
0x18009efab  call    cs:__imp_?GetInstance@PipelineClock@@SAAEAV1@XZ; PipelineClock::GetInstance(void)
0x18009efb1  mov     rcx, rax
0x18009efb4  call    cs:__imp_?GetMillisecondCount@PipelineClock@@QEAAIXZ; PipelineClock::GetMillisecondCount(void)
0x18009efba  mov     ecx, eax
0x18009efbc  mov     [rsi+0CF0Ch], ecx
0x18009efc2  call    cs:__imp_?GetInstance@PipelineClock@@SAAEAV1@XZ; PipelineClock::GetInstance(void)
0x18009efc8  mov     rcx, rax
0x18009efcb  call    cs:__imp_?GetMillisecondCount@PipelineClock@@QEAAIXZ; PipelineClock::GetMillisecondCount(void)
0x18009efd1  mov     [rsi+0CF10h], eax
0x18009efd7  mov     dword ptr [rsi+0CF00h], 7
0x18009efe1  lea     rcx, [rbp+arg_18]
0x18009efe5  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18009efea  mov     eax, r14d
0x18009efed  add     rsp, 70h
0x18009eff1  pop     r15
0x18009eff3  pop     r14
0x18009eff5  pop     r12
0x18009eff7  pop     rdi
0x18009eff8  pop     rsi
0x18009eff9  pop     rbx
0x18009effa  pop     rbp
0x18009effb  retn
```
