# CTSThread::StartThread(long (*)(void *))

- ea: `0x180016300`
- end: `0x1800166c4`
- name: `?StartThread@CTSThread@@UEAAJP6AJPEAX@Z@Z`
- size: `964`
- prototype: `__int64 __fastcall(CTSThread *__hidden this, int (*)(void *))`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180001180`
- `0x180001364`
- `0x1800013f4`
- `0x180001518`
- `0x1800018dc`
- `0x180010900`
- `0x18001092c`
- `0x180016300`
- `0x180017f14`
- `0x18001a008`
- `0x18001bd9c`
- `0x18001c6c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800163e9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800163e9`

## string_xrefs

- `0x180016391`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x18001647e`: `onecore\termsrv\rdpplatform\common\devplatform\platform\thread.cpp`
- `0x18001637d`: `StartThread`
- `0x180016471`: `StartThread`
- `0x18001636b`: `Entry function does not exist can't start thread`
- `0x180016406`: `start sync event %p created - now create thread`
- `0x1800164a7`: `Thread exited with error code: 0x%x`
- `0x180016511`: `Thread exited with success error code`
- `0x18001653e`: `thread %d created successfully`

## pseudocode

```c
__int64 __fastcall CTSThread::StartThread(CTSThread *this, int (*a2)(void *))
{
  CTSReaderWriterLock *v4; // r13
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  int v8; // ebx
  unsigned int (*v9)(void *); // rcx
  char *EventW; // rdi
  int v11; // r8d
  int v12; // r9d
  PVOID *v13; // rcx
  int v14; // r8d
  int v15; // r9d
  int v16; // esi
  void *v17; // r12
  unsigned int ActivityIdPrefix; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  int v21; // r8d
  int v22; // r9d
  const char *v24; // [rsp+50h] [rbp-29h] BYREF
  const char *v25; // [rsp+58h] [rbp-21h] BYREF
  const char *v26; // [rsp+60h] [rbp-19h] BYREF
  __int128 v27; // [rsp+68h] [rbp-11h] BYREF
  __int128 v28; // [rsp+78h] [rbp-1h]
  __int128 v29; // [rsp+88h] [rbp+Fh]
  const char *v30; // [rsp+E0h] [rbp+67h] BYREF
  void *v31; // [rsp+F0h] [rbp+77h] BYREF
  const char *v32; // [rsp+F8h] [rbp+7Fh] BYREF

  LODWORD(v30) = 0;
  v27 = 0;
  v28 = 0;
  v31 = 0;
  v29 = 0;
  v4 = (CTSThread *)((char *)this + 148);
  CTSReaderWriterLock::WriteLock((CTSThread *)((char *)this + 148));
  if ( *((_DWORD *)this + 20) != 1 )
    goto LABEL_28;
  if ( !*((_QWORD *)this + 11) )
  {
    if ( (unsigned int)dword_1800EB958 > 2 )
    {
      LODWORD(v30) = 703;
      v25 = "Entry function does not exist can't start thread";
      v32 = "StartThread";
      v24 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
      LODWORD(v31) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v5,
        (unsigned int)qword_1800CCA40,
        v6,
        v7,
        (__int64)&v25,
        (__int64)&v31,
        (__int64)&v24,
        (__int64)&v30,
        (__int64)&v32);
    }
    v8 = -2147024809;
    goto LABEL_29;
  }
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  if ( !EventW )
  {
LABEL_28:
    v8 = -2147467259;
    goto LABEL_29;
  }
  if ( (unsigned int)dword_1800EB958 > 4 )
  {
    v32 = EventW;
    v25 = "start sync event %p created - now create thread";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (_DWORD)v9,
      (unsigned int)qword_1800CCA08,
      v11,
      v12,
      (__int64)&v25,
      (__int64)&v32);
  }
  *((_QWORD *)&v28 + 1) = *((_QWORD *)this + 12);
  *(_QWORD *)&v27 = *((_QWORD *)this + 11);
  *(_QWORD *)&v28 = EventW;
  *(_QWORD *)&v29 = this;
  *((_QWORD *)&v27 + 1) = a2;
  DWORD2(v29) = 0;
  if ( PAL_System_ThreadAllocInit(v9, &v27, EventW, (unsigned int *)&v30, &v31) >= 0 )
  {
    v16 = (int)v30;
    if ( (unsigned int)dword_1800EB958 > 4 )
    {
      v32 = "thread %d created successfully";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)v13,
        (unsigned int)byte_1800CC963,
        v14,
        v15,
        (__int64)&v32,
        (__int64)&v30);
    }
    if ( (unsigned int)dword_1800EB958 > 4 )
    {
      v30 = "event signalled";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v13,
        (unsigned int)word_1800CC942,
        v14,
        v15,
        (__int64)&v30);
    }
    v17 = v31;
    *((_DWORD *)this + 20) = 2;
    *((_QWORD *)this + 8) = v17;
    *((_DWORD *)this + 14) = v16;
    *((_DWORD *)this + 18) = 1;
    v13 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix();
      WPP_SF_DDi(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, v20, ActivityIdPrefix, v16, v17);
    }
  }
  else if ( (SDWORD2(v29) & 0x80000000) == 0 )
  {
    if ( (unsigned int)dword_1800EB958 > 4 )
    {
      v30 = "Thread exited with success error code";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v13,
        (unsigned int)&word_1800CC98E,
        v14,
        v15,
        (__int64)&v30);
    }
  }
  else if ( (unsigned int)dword_1800EB958 > 2 )
  {
    LODWORD(v30) = DWORD2(v29);
    v26 = "Thread exited with error code: 0x%x";
    v25 = "StartThread";
    LODWORD(v31) = 746;
    v24 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
    LODWORD(v32) = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)v13,
      (unsigned int)&byte_1800CC9AF,
      v14,
      v15,
      (__int64)&v26,
      (__int64)&v32,
      (__int64)&v24,
      (__int64)&v31,
      (__int64)&v25,
      (__int64)&v30);
  }
  if ( (unsigned int)dword_1800EB958 > 4 )
  {
    v30 = "Destroy event object";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (_DWORD)v13,
      (unsigned int)byte_1800CC921,
      v14,
      v15,
      (__int64)&v30);
  }
  v8 = PAL_System_HandleFree(EventW);
  if ( v8 < 0 && (unsigned int)dword_1800EB958 > 2 )
  {
    v32 = "StartThread";
    v25 = "Failed to close condition handle";
    LODWORD(v30) = 778;
    v26 = "onecore\\termsrv\\rdpplatform\\common\\devplatform\\platform\\thread.cpp";
    LODWORD(v31) = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      dword_1800EB958,
      (unsigned int)&dword_1800CC8DC,
      v21,
      v22,
      (__int64)&v25,
      (__int64)&v31,
      (__int64)&v26,
      (__int64)&v30,
      (__int64)&v32);
  }
LABEL_29:
  CTSReaderWriterLock::WriteUnlock(v4);
  if ( v8 >= 0 && SDWORD2(v29) < 0 )
    return (unsigned int)DWORD2(v29);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180016300  mov     [rsp-8+arg_8], rbx
0x180016305  push    rbp
0x180016306  push    rsi
0x180016307  push    rdi
0x180016308  push    r12
0x18001630a  push    r13
0x18001630c  push    r14
0x18001630e  push    r15
0x180016310  lea     rbp, [rsp-27h]
0x180016315  sub     rsp, 0A0h
0x18001631c  xorps   xmm0, xmm0
0x18001631f  mov     dword ptr [rbp+57h+arg_0], 0
0x180016326  movups  [rbp+57h+var_68], xmm0
0x18001632a  mov     rsi, rdx
0x18001632d  mov     rbx, rcx
0x180016330  movups  [rbp+57h+var_58], xmm0
0x180016334  mov     [rbp+57h+arg_10], 0
0x18001633c  movups  [rbp+57h+var_48], xmm0
0x180016340  lea     r13, [rcx+94h]
0x180016347  mov     rcx, r13; this
0x18001634a  call    ?WriteLock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteLock(void)
0x18001634f  cmp     dword ptr [rbx+50h], 1
0x180016353  jnz     loc_18001668E
0x180016359  cmp     qword ptr [rbx+58h], 0
0x18001635e  jnz     short loc_1800163DD
0x180016360  mov     eax, cs:dword_1800EB958
0x180016366  cmp     eax, 2
0x180016369  jbe     short loc_1800163D3
0x18001636b  lea     rax, aEntryFunctionD; "Entry function does not exist can't sta"...
0x180016372  mov     dword ptr [rbp+57h+arg_0], 2BFh
0x180016379  mov     [rbp+57h+var_78], rax
0x18001637d  lea     r14, aStartthread; "StartThread"
0x180016384  lea     rax, [rbp+57h+arg_18]
0x180016388  mov     [rbp+57h+arg_18], r14
0x18001638c  mov     [rsp+0D0h+var_90], rax
0x180016391  lea     r15, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180016398  lea     rax, [rbp+57h+arg_0]
0x18001639c  mov     [rbp+57h+var_80], r15
0x1800163a0  mov     [rsp+0D0h+var_98], rax
0x1800163a5  lea     rdx, qword_1800CCA40
0x1800163ac  lea     rax, [rbp+57h+var_80]
0x1800163b0  mov     dword ptr [rbp+57h+arg_10], 80004005h
0x1800163b7  mov     [rsp+0D0h+var_A0], rax
0x1800163bc  lea     rax, [rbp+57h+arg_10]
0x1800163c0  mov     [rsp+0D0h+var_A8], rax
0x1800163c5  lea     rax, [rbp+57h+var_78]
0x1800163c9  mov     [rsp+0D0h+var_B0], rax
0x1800163ce  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800163d3  mov     ebx, 80070057h
0x1800163d8  jmp     loc_180016693
0x1800163dd  xor     r9d, r9d; lpName
0x1800163e0  xor     r8d, r8d; bInitialState
0x1800163e3  xor     ecx, ecx; lpEventAttributes
0x1800163e5  lea     edx, [r9+1]; bManualReset
0x1800163e9  call    cs:__imp_CreateEventW
0x1800163ef  mov     rdi, rax
0x1800163f2  test    rax, rax
0x1800163f5  jz      loc_18001668E
0x1800163fb  mov     eax, cs:dword_1800EB958
0x180016401  cmp     eax, 4
0x180016404  jbe     short loc_180016433
0x180016406  lea     rax, aStartSyncEvent; "start sync event %p created - now creat"...
0x18001640d  mov     [rbp+57h+arg_18], rdi
0x180016411  mov     [rbp+57h+var_78], rax
0x180016415  lea     rdx, qword_1800CCA08
0x18001641c  lea     rax, [rbp+57h+arg_18]
0x180016420  mov     [rsp+0D0h+var_A8], rax
0x180016425  lea     rax, [rbp+57h+var_78]
0x180016429  mov     [rsp+0D0h+var_B0], rax
0x18001642e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180016433  mov     rax, [rbx+60h]
0x180016437  lea     r9, [rbp+57h+arg_0]; unsigned int *
0x18001643b  mov     qword ptr [rbp+57h+var_58+8], rax
0x18001643f  lea     rdx, [rbp+57h+var_68]; void *
0x180016443  mov     rax, [rbx+58h]
0x180016447  mov     r8, rdi; void *
0x18001644a  mov     qword ptr [rbp+57h+var_68], rax
0x18001644e  lea     rax, [rbp+57h+arg_10]
0x180016452  mov     [rsp+0D0h+var_B0], rax; void **
0x180016457  mov     qword ptr [rbp+57h+var_58], rdi
0x18001645b  mov     qword ptr [rbp+57h+var_48], rbx
0x18001645f  mov     qword ptr [rbp+57h+var_68+8], rsi
0x180016463  mov     dword ptr [rbp+57h+var_48+8], 0
0x18001646a  call    ?PAL_System_ThreadAllocInit@@YAJP6AIPEAX@Z00PEAKPEAPEAX@Z; PAL_System_ThreadAllocInit(uint (*)(void *),void *,void *,ulong *,void * *)
0x18001646f  test    eax, eax
0x180016471  lea     r14, aStartthread; "StartThread"
0x180016478  mov     eax, cs:dword_1800EB958
0x18001647e  lea     r15, aOnecoreTermsrv_3; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180016485  jns     loc_180016536
0x18001648b  cmp     dword ptr [rbp+57h+var_48+8], 0
0x18001648f  jge     short loc_180016508
0x180016491  cmp     eax, 2
0x180016494  jbe     loc_1800165EE
0x18001649a  mov     eax, dword ptr [rbp+57h+var_48+8]
0x18001649d  lea     rdx, byte_1800CC9AF
0x1800164a4  mov     dword ptr [rbp+57h+arg_0], eax
0x1800164a7  lea     rax, aThreadExitedWi; "Thread exited with error code: 0x%x"
0x1800164ae  mov     [rbp+57h+var_70], rax
0x1800164b2  lea     rax, [rbp+57h+arg_0]
0x1800164b6  mov     [rsp+0D0h+var_88], rax
0x1800164bb  lea     rax, [rbp+57h+var_78]
0x1800164bf  mov     [rsp+0D0h+var_90], rax
0x1800164c4  lea     rax, [rbp+57h+arg_10]
0x1800164c8  mov     [rsp+0D0h+var_98], rax
0x1800164cd  lea     rax, [rbp+57h+var_80]
0x1800164d1  mov     [rsp+0D0h+var_A0], rax
0x1800164d6  lea     rax, [rbp+57h+arg_18]
0x1800164da  mov     [rsp+0D0h+var_A8], rax
0x1800164df  lea     rax, [rbp+57h+var_70]
0x1800164e3  mov     [rsp+0D0h+var_B0], rax
0x1800164e8  mov     [rbp+57h+var_78], r14
0x1800164ec  mov     dword ptr [rbp+57h+arg_10], 2EAh
0x1800164f3  mov     [rbp+57h+var_80], r15
0x1800164f7  mov     dword ptr [rbp+57h+arg_18], 80004005h
0x1800164fe  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180016503  jmp     loc_1800165EE
0x180016508  cmp     eax, 4
0x18001650b  jbe     loc_1800165EE
0x180016511  lea     rax, aThreadExitedWi_0; "Thread exited with success error code"
0x180016518  mov     [rbp+57h+arg_0], rax
0x18001651c  lea     rdx, word_1800CC98E
0x180016523  lea     rax, [rbp+57h+arg_0]
0x180016527  mov     [rsp+0D0h+var_B0], rax
0x18001652c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180016531  jmp     loc_1800165EE
0x180016536  mov     esi, dword ptr [rbp+57h+arg_0]
0x180016539  cmp     eax, 4
0x18001653c  jbe     short loc_18001656A
0x18001653e  lea     rax, aThreadDCreated; "thread %d created successfully"
0x180016545  mov     dword ptr [rbp+57h+arg_0], esi
0x180016548  mov     [rbp+57h+arg_18], rax
0x18001654c  lea     rdx, byte_1800CC963
0x180016553  lea     rax, [rbp+57h+arg_0]
0x180016557  mov     [rsp+0D0h+var_A8], rax
0x18001655c  lea     rax, [rbp+57h+arg_18]
0x180016560  mov     [rsp+0D0h+var_B0], rax
0x180016565  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001656a  mov     eax, cs:dword_1800EB958
0x180016570  cmp     eax, 4
0x180016573  jbe     short loc_180016595
0x180016575  lea     rax, aEventSignalled; "event signalled"
0x18001657c  mov     [rbp+57h+arg_0], rax
0x180016580  lea     rdx, word_1800CC942
0x180016587  lea     rax, [rbp+57h+arg_0]
0x18001658b  mov     [rsp+0D0h+var_B0], rax
0x180016590  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180016595  mov     r12, [rbp+57h+arg_10]
0x180016599  mov     dword ptr [rbx+50h], 2
0x1800165a0  mov     [rbx+40h], r12
0x1800165a4  mov     [rbx+38h], esi
0x1800165a7  mov     dword ptr [rbx+48h], 1
0x1800165ae  mov     rax, cs:WPP_GLOBAL_Control
0x1800165b5  lea     rcx, WPP_GLOBAL_Control
0x1800165bc  cmp     rax, rcx
0x1800165bf  jz      short loc_1800165EE
0x1800165c1  test    byte ptr [rax+1Ch], 1
0x1800165c5  jz      short loc_1800165EE
0x1800165c7  cmp     byte ptr [rax+19h], 3
0x1800165cb  jb      short loc_1800165EE
0x1800165cd  call    RdpX_GetActivityIdPrefix
0x1800165d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800165d9  mov     r9d, eax
0x1800165dc  mov     [rsp+0D0h+var_A8], r12
0x1800165e1  mov     dword ptr [rsp+0D0h+var_B0], esi
0x1800165e5  mov     rcx, [rcx+10h]
0x1800165e9  call    WPP_SF_DDi
0x1800165ee  mov     eax, cs:dword_1800EB958
0x1800165f4  cmp     eax, 4
0x1800165f7  jbe     short loc_180016619
0x1800165f9  lea     rax, aDestroyEventOb; "Destroy event object"
0x180016600  mov     [rbp+57h+arg_0], rax
0x180016604  lea     rdx, byte_1800CC921
0x18001660b  lea     rax, [rbp+57h+arg_0]
0x18001660f  mov     [rsp+0D0h+var_B0], rax
0x180016614  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180016619  mov     rcx, rdi
0x18001661c  call    PAL_System_HandleFree
0x180016621  mov     ebx, eax
0x180016623  test    eax, eax
0x180016625  jns     short loc_180016693
0x180016627  mov     ecx, cs:dword_1800EB958
0x18001662d  cmp     ecx, 2
0x180016630  jbe     short loc_180016693
0x180016632  lea     rax, aFailedToCloseC; "Failed to close condition handle"
0x180016639  mov     [rbp+57h+arg_18], r14
0x18001663d  mov     [rbp+57h+var_78], rax
0x180016641  lea     rdx, dword_1800CC8DC
0x180016648  lea     rax, [rbp+57h+arg_18]
0x18001664c  mov     dword ptr [rbp+57h+arg_0], 30Ah
0x180016653  mov     [rsp+0D0h+var_90], rax
0x180016658  lea     rax, [rbp+57h+arg_0]
0x18001665c  mov     [rsp+0D0h+var_98], rax
0x180016661  lea     rax, [rbp+57h+var_70]
0x180016665  mov     [rsp+0D0h+var_A0], rax
0x18001666a  lea     rax, [rbp+57h+arg_10]
0x18001666e  mov     [rsp+0D0h+var_A8], rax
0x180016673  lea     rax, [rbp+57h+var_78]
0x180016677  mov     [rsp+0D0h+var_B0], rax
0x18001667c  mov     [rbp+57h+var_70], r15
0x180016680  mov     dword ptr [rbp+57h+arg_10], 80004005h
0x180016687  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001668c  jmp     short loc_180016693
0x18001668e  mov     ebx, 80004005h
0x180016693  mov     rcx, r13; this
0x180016696  call    ?WriteUnlock@CTSReaderWriterLock@@QEAAXXZ; CTSReaderWriterLock::WriteUnlock(void)
0x18001669b  test    ebx, ebx
0x18001669d  js      short loc_1800166A7
0x18001669f  mov     eax, dword ptr [rbp+57h+var_48+8]
0x1800166a2  test    eax, eax
0x1800166a4  cmovs   ebx, eax
0x1800166a7  mov     eax, ebx
0x1800166a9  mov     rbx, [rsp+0D0h+arg_8]
0x1800166b1  add     rsp, 0A0h
0x1800166b8  pop     r15
0x1800166ba  pop     r14
0x1800166bc  pop     r13
0x1800166be  pop     r12
0x1800166c0  pop     rdi
0x1800166c1  pop     rsi
0x1800166c2  pop     rbp
0x1800166c3  retn
```
