# CalaisTerminateReader(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18002a970`
- end: `0x18002aa7d`
- name: `?CalaisTerminateReader@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `269`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, char *, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001900`
- `0x18000366c`
- `0x1800044e0`
- `0x18000d7a0`
- `0x180012380`
- `0x1800123a0`
- `0x18001cb74`
- `0x1800249e0`
- `0x180028b28`
- `0x180029e44`
- `0x18002a970`
- `0x18002e770`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002aa76`

## pseudocode

```c
void __fastcall CalaisTerminateReader(struct _TP_CALLBACK_INSTANCE *a1, char *a2, struct _TP_WORK *a3)
{
  unsigned int v4; // eax
  const unsigned __int8 *v5; // r8
  const unsigned __int8 *v6; // r9
  __int64 v7; // rdx
  __int64 v8; // rcx
  const unsigned __int8 *v9; // r8
  const unsigned __int8 *v10; // r9
  ulong pExceptionObject; // [rsp+20h] [rbp-18h] BYREF
  ulong v12; // [rsp+24h] [rbp-14h] BYREF
  char v13; // [rsp+48h] [rbp+10h] BYREF
  PTP_WORK v14; // [rsp+50h] [rbp+18h]
  CReader *v15; // [rsp+58h] [rbp+20h] BYREF

  v14 = a3;
  set_terminate(CalaisTerminate);
  v4 = CalRpcSetCallerId((void *)_InterlockedIncrement(&dword_18004BF90));
  try
  {
    if ( v4 )
    {
      pExceptionObject = v4;
      throw &pExceptionObject;
    }
    v15 = (CReader *)a2;
    CReader::TakeoverReader((CReader *)a2);
    CLockWrite::CLockWrite((CLockWrite *)&v13, (struct CAccessLock *)(a2 + 56));
    ++*((_DWORD *)a2 + 50);
    CReader::SetAvailabilityStatus(a2, 11);
    CLockWrite::~CLockWrite((CLockWrite *)&v13);
    CTakeReader::~CTakeReader(&v15);
    if ( (Microsoft_Windows_Smartcard_TriggerEnableBits & 1) != 0 )
      McTemplateU0j_EventWriteTransfer();
    CLockWrite::CLockWrite((CLockWrite *)&v13, (struct CAccessLock *)(a2 + 512));
    CLockWrite::~CLockWrite((CLockWrite *)&v13);
    if ( a2 )
      (**(void (__fastcall ***)(char *, __int64))a2)(a2, 1);
  }
  catch ( ulong v12 )
  {
  }
  catch ( ... )
  {
  }
  COwnCriticalSection::COwnCriticalSection((COwnCriticalSection *)&v13, qword_18004BA68, v5, v6);
  --l_dwReaderActionsInProgress;
  COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&v13);
  CalaisStopServiceIfNoReaders(v8, v7, v9, v10);
  CloseThreadpoolWork(v14);
}

```

## disassembly

```asm
0x18002a970  mov     [rsp+arg_10], r8
0x18002a975  push    rbx
0x18002a976  sub     rsp, 30h
0x18002a97a  mov     rbx, rdx
0x18002a97d  lea     rcx, ?CalaisTerminate@@YAXXZ; void (*)(void)
0x18002a984  call    ?set_terminate@@YAP6AXXZP6AXXZ@Z_0; set_terminate(void (*)(void))
0x18002a989  nop
0x18002a98a  mov     eax, 1
0x18002a98f  lock xadd cs:dword_18004BF90, eax
0x18002a997  inc     eax
0x18002a999  movsxd  rcx, eax; lpTlsValue
0x18002a99c  call    ?CalRpcSetCallerId@@YAKPEAX@Z; CalRpcSetCallerId(void *)
0x18002a9a1  test    eax, eax
0x18002a9a3  jz      short loc_18002A9BA
0x18002a9a5  mov     [rsp+38h+pExceptionObject], eax
0x18002a9a9  lea     rdx, _TI1K; pThrowInfo
0x18002a9b0  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18002a9b5  call    _CxxThrowException_0
0x18002a9ba  mov     [rsp+38h+arg_18], rbx
0x18002a9bf  mov     rcx, rbx; this
0x18002a9c2  call    ?TakeoverReader@CReader@@IEAAXXZ; CReader::TakeoverReader(void)
0x18002a9c7  nop
0x18002a9c8  lea     rdx, [rbx+38h]; struct CAccessLock *
0x18002a9cc  lea     rcx, [rsp+38h+arg_8]; this
0x18002a9d1  call    ??0CLockWrite@@QEAA@PEAVCAccessLock@@@Z; CLockWrite::CLockWrite(CAccessLock *)
0x18002a9d6  nop
0x18002a9d7  inc     dword ptr [rbx+0C8h]
0x18002a9dd  mov     edx, 0Bh
0x18002a9e2  mov     rcx, rbx
0x18002a9e5  call    ?SetAvailabilityStatus@CReader@@IEAAXW4AvailableState@1@@Z; CReader::SetAvailabilityStatus(CReader::AvailableState)
0x18002a9ea  nop
0x18002a9eb  lea     rcx, [rsp+38h+arg_8]; this
0x18002a9f0  call    ??1CLockWrite@@QEAA@XZ; CLockWrite::~CLockWrite(void)
0x18002a9f5  nop
0x18002a9f6  lea     rcx, [rsp+38h+arg_18]; this
0x18002a9fb  call    ??1CTakeReader@@QEAA@XZ; CTakeReader::~CTakeReader(void)
0x18002aa00  test    cs:Microsoft_Windows_Smartcard_TriggerEnableBits, 1
0x18002aa07  jz      short loc_18002AA0E
0x18002aa09  call    McTemplateU0j_EventWriteTransfer
0x18002aa0e  lea     rdx, [rbx+200h]; struct CAccessLock *
0x18002aa15  lea     rcx, [rsp+38h+arg_8]; this
0x18002aa1a  call    ??0CLockWrite@@QEAA@PEAVCAccessLock@@@Z; CLockWrite::CLockWrite(CAccessLock *)
0x18002aa1f  lea     rcx, [rsp+38h+arg_8]; this
0x18002aa24  call    ??1CLockWrite@@QEAA@XZ; CLockWrite::~CLockWrite(void)
0x18002aa29  test    rbx, rbx
0x18002aa2c  jz      short loc_18002AA42
0x18002aa2e  mov     rax, [rbx]
0x18002aa31  mov     edx, 1
0x18002aa36  mov     rcx, rbx
0x18002aa39  mov     rax, [rax]
0x18002aa3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa41  nop
0x18002aa42  jmp     short loc_18002AA46
0x18002aa44  jmp     short $+2
0x18002aa46  mov     rdx, cs:qword_18004BA68; struct CCriticalSectionObject *
0x18002aa4d  lea     rcx, [rsp+38h+arg_8]; this
0x18002aa52  call    ??0COwnCriticalSection@@QEAA@PEAVCCriticalSectionObject@@PEBE1@Z; COwnCriticalSection::COwnCriticalSection(CCriticalSectionObject *,uchar const *,uchar const *)
0x18002aa57  dec     cs:?l_dwReaderActionsInProgress@@3KA; ulong l_dwReaderActionsInProgress
0x18002aa5d  lea     rcx, [rsp+38h+arg_8]; this
0x18002aa62  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x18002aa67  call    ?CalaisStopServiceIfNoReaders@@YAXXZ; CalaisStopServiceIfNoReaders(void)
0x18002aa6c  mov     rcx, [rsp+38h+arg_10]
0x18002aa71  add     rsp, 30h
0x18002aa75  pop     rbx
0x18002aa76  jmp     cs:__imp_CloseThreadpoolWork
```
