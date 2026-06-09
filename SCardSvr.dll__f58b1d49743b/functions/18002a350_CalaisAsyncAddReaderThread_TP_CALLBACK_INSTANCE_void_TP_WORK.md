# CalaisAsyncAddReaderThread(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18002a350`
- end: `0x18002a40d`
- name: `?CalaisAsyncAddReaderThread@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `189`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, char *, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180001900`
- `0x180012380`
- `0x1800123a0`
- `0x18001b3fc`
- `0x18001cb74`
- `0x180029e74`
- `0x180029ea0`
- `0x18002a350`
- `0x18003261b`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18002a3e9`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18002a3e9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002a3f4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18002a3f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CalaisAsyncAddReaderThread(struct _TP_CALLBACK_INSTANCE *a1, char *a2, struct _TP_WORK *a3)
{
  char *v3; // rbx
  unsigned int v4; // eax
  const unsigned __int16 *v5; // rax
  const unsigned __int8 *v6; // r8
  const unsigned __int8 *v7; // r9
  unsigned int v8; // edx
  ulong pExceptionObject; // [rsp+20h] [rbp-18h] BYREF
  ulong v10; // [rsp+24h] [rbp-14h] BYREF
  char *v11; // [rsp+48h] [rbp+10h] BYREF
  PTP_WORK pwk; // [rsp+50h] [rbp+18h]

  pwk = a3;
  v11 = a2;
  v3 = a2;
  set_terminate(CalaisTerminate);
  v4 = CalRpcSetCallerId((void *)_InterlockedIncrement(&dword_18004BF90));
  try
  {
    if ( v4 )
    {
      pExceptionObject = v4;
      throw &pExceptionObject;
    }
    v5 = CTextString::Unicode((CTextString *)(v3 + 8));
    CalaisAddReader(*(unsigned int (**)(const unsigned __int16 *, unsigned int))v3, v5, *((_DWORD *)v3 + 18));
  }
  catch ( ulong v10 )
  {
    v3 = v11;
  }
  catch ( ... )
  {
    v3 = v11;
  }
  COwnCriticalSection::COwnCriticalSection((COwnCriticalSection *)&v11, qword_18004BA68, v6, v7);
  --l_dwReaderActionsInProgress;
  COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&v11);
  WakeAllConditionVariable(&l_cvReaderAsyncActionFinished);
  CloseThreadpoolWork(pwk);
  if ( v3 )
    CAsyncAddReaderContext::`scalar deleting destructor'((CAsyncAddReaderContext *)v3, v8);
}

```

## disassembly

```asm
0x18002a350  mov     [rsp+pwk], r8
0x18002a355  mov     [rsp+arg_8], rdx
0x18002a35a  push    rbx
0x18002a35b  sub     rsp, 30h
0x18002a35f  mov     rbx, rdx
0x18002a362  lea     rcx, ?CalaisTerminate@@YAXXZ; void (*)(void)
0x18002a369  call    ?set_terminate@@YAP6AXXZP6AXXZ@Z_0; set_terminate(void (*)(void))
0x18002a36e  nop
0x18002a36f  mov     eax, 1
0x18002a374  lock xadd cs:dword_18004BF90, eax
0x18002a37c  inc     eax
0x18002a37e  movsxd  rcx, eax; lpTlsValue
0x18002a381  call    ?CalRpcSetCallerId@@YAKPEAX@Z; CalRpcSetCallerId(void *)
0x18002a386  test    eax, eax
0x18002a388  jz      short loc_18002A39F
0x18002a38a  mov     [rsp+38h+pExceptionObject], eax
0x18002a38e  lea     rdx, _TI1K; pThrowInfo
0x18002a395  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18002a39a  call    _CxxThrowException_0
0x18002a39f  lea     rcx, [rbx+8]; this
0x18002a3a3  call    ?Unicode@CTextString@@IEAAPEBGXZ; CTextString::Unicode(void)
0x18002a3a8  mov     r8d, [rbx+48h]; unsigned int
0x18002a3ac  mov     rdx, rax; unsigned __int16 *
0x18002a3af  mov     rcx, [rbx]; unsigned int (*)(const unsigned __int16 *, unsigned int)
0x18002a3b2  call    ?CalaisAddReader@@YAKP6AKPEBGK@Z0K@Z; CalaisAddReader(ulong (*)(ushort const *,ulong),ushort const *,ulong)
0x18002a3b7  nop
0x18002a3b8  jmp     short loc_18002A3C1
0x18002a3ba  jmp     short $+2
0x18002a3bc  mov     rbx, [rsp+38h+arg_8]
0x18002a3c1  mov     rdx, cs:qword_18004BA68; struct CCriticalSectionObject *
0x18002a3c8  lea     rcx, [rsp+38h+arg_8]; this
0x18002a3cd  call    ??0COwnCriticalSection@@QEAA@PEAVCCriticalSectionObject@@PEBE1@Z; COwnCriticalSection::COwnCriticalSection(CCriticalSectionObject *,uchar const *,uchar const *)
0x18002a3d2  dec     cs:?l_dwReaderActionsInProgress@@3KA; ulong l_dwReaderActionsInProgress
0x18002a3d8  lea     rcx, [rsp+38h+arg_8]; this
0x18002a3dd  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x18002a3e2  lea     rcx, ?l_cvReaderAsyncActionFinished@@3U_RTL_CONDITION_VARIABLE@@A; ConditionVariable
0x18002a3e9  call    cs:__imp_WakeAllConditionVariable
0x18002a3ef  mov     rcx, [rsp+38h+pwk]; pwk
0x18002a3f4  call    cs:__imp_CloseThreadpoolWork
0x18002a3fa  test    rbx, rbx
0x18002a3fd  jz      short loc_18002A407
0x18002a3ff  mov     rcx, rbx; this
0x18002a402  call    ??_GCAsyncAddReaderContext@@QEAAPEAXI@Z; CAsyncAddReaderContext::`scalar deleting destructor'(uint)
0x18002a407  add     rsp, 30h
0x18002a40b  pop     rbx
0x18002a40c  retn
```
