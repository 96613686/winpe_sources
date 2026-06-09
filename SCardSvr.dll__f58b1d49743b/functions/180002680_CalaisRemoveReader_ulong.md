# CalaisRemoveReader(ulong)

- ea: `0x180002680`
- end: `0x180002786`
- name: `?CalaisRemoveReader@@YAKK@Z`
- size: `262`
- prototype: `__int64 __fastcall(int)`
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002a5c0`
- `0x18002a67c`
- `0x18002a72c`
- `0x18002a7e4`

## callees

- `0x180002680`
- `0x1800037b8`
- `0x180012380`
- `0x1800123a0`
- `0x180017db0`
- `0x180019a40`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000275c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000275c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CalaisRemoveReader(int a1)
{
  __int64 v1; // rsi
  unsigned int v2; // edi
  struct CCriticalSectionObject *v3; // rbx
  __int64 v4; // rcx
  void *v5; // r14
  const unsigned __int8 *v6; // r8
  const unsigned __int8 *v7; // r9
  struct _TP_WORK *AsyncReaderHandlingWork; // rax
  ulong pExceptionObject; // [rsp+20h] [rbp-28h] BYREF
  ulong v11; // [rsp+24h] [rbp-24h] BYREF
  ulong v12; // [rsp+28h] [rbp-20h] BYREF
  char v13; // [rsp+58h] [rbp+10h] BYREF
  struct CCriticalSectionObject *v14; // [rsp+60h] [rbp+18h] BYREF

  try
  {
    v1 = a1;
    v2 = 0;
    v13 = 0;
    v3 = g_pcsControlLocks;
    v14 = g_pcsControlLocks;
    (**(void (__fastcall ***)(struct CCriticalSectionObject *, _QWORD, _QWORD))g_pcsControlLocks)(
      g_pcsControlLocks,
      0,
      0);
    if ( HIDWORD(qword_18004B0C8) <= (unsigned int)v1 )
    {
      pExceptionObject = -2146435063;
      throw &pExceptionObject;
    }
    v5 = (void *)*((_QWORD *)qword_18004B0D0 + v1);
    CDynamicArray<CReader>::Set(v4, (unsigned int)v1, 0);
    CMultiEvent::Signal(g_phReaderChangeEvent);
    (*(void (__fastcall **)(struct CCriticalSectionObject *))(*(_QWORD *)v3 + 8LL))(v3);
    if ( v5 )
    {
      COwnCriticalSection::COwnCriticalSection((COwnCriticalSection *)&v14, qword_18004BA68, v6, v7);
      ++l_dwReaderActionsInProgress;
      v13 = 1;
      AsyncReaderHandlingWork = CalaisCreateAsyncReaderHandlingWork(CalaisTerminateReader, v5);
      if ( !AsyncReaderHandlingWork )
      {
        v11 = -2146435066;
        throw &v11;
      }
      SubmitThreadpoolWork(AsyncReaderHandlingWork);
      COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&v14);
    }
  }
  catch ( ulong v12 )
  {
    LODWORD(v14) = v12;
    if ( v13 )
    {
      COwnCriticalSection::COwnCriticalSection((COwnCriticalSection *)&v13, qword_18004BA68, v6, v7);
      --l_dwReaderActionsInProgress;
      COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&v13);
      WakeAllConditionVariable(&l_cvReaderAsyncActionFinished);
    }
    return (unsigned int)v14;
  }
  catch ( ... )
  {
    LODWORD(v14) = -2146435068;
    if ( v13 )
    {
      COwnCriticalSection::COwnCriticalSection((COwnCriticalSection *)&v13, qword_18004BA68, v6, v7);
      --l_dwReaderActionsInProgress;
      COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&v13);
      WakeAllConditionVariable(&l_cvReaderAsyncActionFinished);
    }
    return (unsigned int)v14;
  }
  return v2;
}

```

## disassembly

```asm
0x180002680  mov     [rsp+arg_0], rbx
0x180002685  push    rsi
0x180002686  push    rdi
0x180002687  push    r14
0x180002689  sub     rsp, 30h
0x18000268d  movsxd  rsi, ecx
0x180002690  xor     edi, edi
0x180002692  mov     [rsp+48h+arg_8], dil
0x180002697  mov     rbx, cs:?g_pcsControlLocks@@3PAPEAVCCriticalSectionObject@@A; CCriticalSectionObject * near * g_pcsControlLocks
0x18000269e  mov     [rsp+48h+arg_10], rbx
0x1800026a3  mov     rax, [rbx]
0x1800026a6  xor     r8d, r8d
0x1800026a9  xor     edx, edx
0x1800026ab  mov     rcx, rbx
0x1800026ae  mov     rax, [rax]
0x1800026b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026b6  nop
0x1800026b7  cmp     dword ptr cs:qword_18004B0C8+4, esi
0x1800026bd  ja      short loc_1800026D8
0x1800026bf  mov     [rsp+48h+pExceptionObject], 80100009h
0x1800026c7  lea     rdx, _TI1K; pThrowInfo
0x1800026ce  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800026d3  call    _CxxThrowException_0
0x1800026d8  mov     rax, cs:qword_18004B0D0
0x1800026df  mov     r14, [rax+rsi*8]
0x1800026e3  xor     r8d, r8d
0x1800026e6  mov     edx, esi
0x1800026e8  call    ?Set@?$CDynamicArray@VCReader@@@@QEAAPEAVCReader@@HPEAV2@@Z; CDynamicArray<CReader>::Set(int,CReader *)
0x1800026ed  mov     rcx, cs:?g_phReaderChangeEvent@@3PEAVCMultiEvent@@EA; this
0x1800026f4  call    ?Signal@CMultiEvent@@QEAAXXZ; CMultiEvent::Signal(void)
0x1800026f9  nop
0x1800026fa  mov     rax, [rbx]
0x1800026fd  mov     rcx, rbx
0x180002700  mov     rax, [rax+8]
0x180002704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002709  nop
0x18000270a  test    r14, r14
0x18000270d  jz      short loc_18000276E
0x18000270f  mov     rdx, cs:qword_18004BA68; struct CCriticalSectionObject *
0x180002716  lea     rcx, [rsp+48h+arg_10]; this
0x18000271b  call    ??0COwnCriticalSection@@QEAA@PEAVCCriticalSectionObject@@PEBE1@Z; COwnCriticalSection::COwnCriticalSection(CCriticalSectionObject *,uchar const *,uchar const *)
0x180002720  nop
0x180002721  inc     cs:?l_dwReaderActionsInProgress@@3KA; ulong l_dwReaderActionsInProgress
0x180002727  mov     [rsp+48h+arg_8], 1
0x18000272c  mov     rdx, r14; pv
0x18000272f  lea     rcx, ?CalaisTerminateReader@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180002736  call    ?CalaisCreateAsyncReaderHandlingWork@@YAPEAU_TP_WORK@@P6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU1@@Z1@Z; CalaisCreateAsyncReaderHandlingWork(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),void *)
0x18000273b  test    rax, rax
0x18000273e  jnz     short loc_180002759
0x180002740  mov     [rsp+48h+var_24], 80100006h
0x180002748  lea     rdx, _TI1K; pThrowInfo
0x18000274f  lea     rcx, [rsp+48h+var_24]; pExceptionObject
0x180002754  call    _CxxThrowException_0
0x180002759  mov     rcx, rax; pwk
0x18000275c  call    cs:__imp_SubmitThreadpoolWork
0x180002762  nop
0x180002763  lea     rcx, [rsp+48h+arg_10]; this
0x180002768  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x18000276d  nop
0x18000276e  jmp     short loc_180002776
0x180002770  jmp     short $+2
0x180002772  mov     edi, dword ptr [rsp+48h+arg_10]
0x180002776  mov     eax, edi
0x180002778  mov     rbx, [rsp+48h+arg_0]
0x18000277d  add     rsp, 30h
0x180002781  pop     r14
0x180002783  pop     rdi
0x180002784  pop     rsi
0x180002785  retn
```
