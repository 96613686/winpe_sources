# RdpTaskScheduler::CleanUp(int)

- ea: `0x1800db8a0`
- end: `0x1800dbbf0`
- name: `?CleanUp@RdpTaskScheduler@@UEAAJH@Z`
- size: `848`
- prototype: `__int64 __fastcall(RdpTaskScheduler *__hidden this, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x1800db634`

## callees

- `0x180001aa0`
- `0x180002550`
- `0x1800787d4`
- `0x180078820`
- `0x1800db8a0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800dbbd9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800dbbd9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800db991`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800db991`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800dbb0a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800dbb0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db99f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dbb19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800db99f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dbb19`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800db8ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800db8ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800db914`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800db914`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dbbbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dbbbe`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800db97b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800db97b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800db968`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800db968`

## string_xrefs

- `0x1800db9ea`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1800dba90`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1800dbb60`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1800db92e`: `Task scheduler cleanup`
- `0x1800dbb39`: `Creation of the cleanup threadpool group thread failed.`
- `0x1800dba65`: `CLEANUP_THREADPOOL_GROUP_INFO allocation failed`

## pseudocode

```c
__int64 __fastcall RdpTaskScheduler::CleanUp(RTL_SRWLOCK *this, int a2)
{
  RTL_SRWLOCK *v2; // rbx
  HMODULE Ptr; // r15
  struct _TP_TIMER *v6; // r14
  struct _TP_WAIT *v7; // rsi
  int v8; // r9d
  signed int LastError; // eax
  int v10; // r8d
  int v11; // r9d
  unsigned int v12; // ecx
  HMODULE *v13; // rax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  HMODULE *v17; // rbx
  HANDLE Thread; // rax
  signed int v19; // eax
  int v20; // r8d
  int v21; // r9d
  unsigned int v22; // ecx
  const char *v24; // [rsp+50h] [rbp-20h] BYREF
  const char *v25; // [rsp+58h] [rbp-18h] BYREF
  const char *v26; // [rsp+60h] [rbp-10h] BYREF
  const char *v27; // [rsp+68h] [rbp-8h] BYREF
  const char *v28; // [rsp+B0h] [rbp+40h] BYREF
  int v29; // [rsp+C0h] [rbp+50h] BYREF
  HMODULE phModule; // [rsp+C8h] [rbp+58h] BYREF

  v2 = this + 29;
  phModule = 0;
  AcquireSRWLockExclusive(this + 29);
  Ptr = (HMODULE)this[17].Ptr;
  v6 = (struct _TP_TIMER *)this[19].Ptr;
  v7 = (struct _TP_WAIT *)this[20].Ptr;
  this[17].Ptr = 0;
  this[18].Ptr = 0;
  this[19].Ptr = 0;
  this[20].Ptr = 0;
  ReleaseSRWLockExclusive(v2);
  if ( !Ptr )
    goto LABEL_24;
  if ( (unsigned int)CallbackContext > 4 )
  {
    v28 = "Task scheduler cleanup";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&CallbackContext,
      (unsigned int)qword_1801BC338,
      0,
      v8,
      (__int64)&v28);
  }
  if ( v6 )
    SetThreadpoolTimer(v6, 0, 0, 0);
  if ( v7 )
    SetThreadpoolWait(v7, 0, 0);
  if ( !GetModuleHandleExW(4u, (LPCWSTR)RdpTaskScheduler::STATIC_CleanupThreadpoolGroup, &phModule) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v28) = 267;
      v24 = "Failed to get module handle to itself.";
      v29 = v12;
      v25 = "CleanUp";
      v26 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
      v27 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v12,
        (unsigned int)&byte_1801BC297,
        v10,
        v11,
        (__int64)&v27,
        (__int64)&v29,
        (__int64)&v26,
        (__int64)&v28,
        (__int64)&v25,
        (__int64)&v24);
    }
    goto LABEL_25;
  }
  v13 = (HMODULE *)operator new(0x18u);
  v17 = v13;
  if ( !v13 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v28) = 270;
      v27 = "CLEANUP_THREADPOOL_GROUP_INFO allocation failed";
      v29 = -2147024882;
      v26 = "CleanUp";
      v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
      v24 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v14,
        (unsigned int)qword_1801BC2E8,
        v15,
        v16,
        (__int64)&v24,
        (__int64)&v29,
        (__int64)&v25,
        (__int64)&v28,
        (__int64)&v26,
        (__int64)&v27);
    }
    goto LABEL_25;
  }
  v13[1] = Ptr;
  *((_DWORD *)v13 + 4) = a2;
  *v13 = phModule;
  Thread = CreateThread(0, 0, RdpTaskScheduler::STATIC_CleanupThreadpoolGroup, v13, 0, 0);
  if ( Thread )
  {
    CloseHandle(Thread);
    phModule = 0;
LABEL_24:
    HIDWORD(this[5].Ptr) |= 4u;
    goto LABEL_25;
  }
  v19 = GetLastError();
  v22 = v19;
  if ( v19 > 0 )
    v22 = (unsigned __int16)v19 | 0x80070000;
  if ( (unsigned int)CallbackContext > 2 )
  {
    LODWORD(v28) = 284;
    v27 = "Creation of the cleanup threadpool group thread failed.";
    v29 = v22;
    v26 = "CleanUp";
    v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
    v24 = "Error condition failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v22,
      (unsigned int)&byte_1801BC1FF,
      v20,
      v21,
      (__int64)&v24,
      (__int64)&v29,
      (__int64)&v25,
      (__int64)&v28,
      (__int64)&v26,
      (__int64)&v27);
  }
  operator delete(v17);
LABEL_25:
  if ( phModule )
    FreeLibrary(phModule);
  return 0;
}

```

## disassembly

```asm
0x1800db8a0  push    rbp
0x1800db8a2  push    rbx
0x1800db8a3  push    rsi
0x1800db8a4  push    rdi
0x1800db8a5  push    r12
0x1800db8a7  push    r14
0x1800db8a9  push    r15
0x1800db8ab  mov     rbp, rsp
0x1800db8ae  sub     rsp, 70h
0x1800db8b2  lea     rbx, [rcx+0E8h]
0x1800db8b9  mov     [rbp+phModule], 0
0x1800db8c1  mov     rdi, rcx
0x1800db8c4  mov     r12d, edx
0x1800db8c7  mov     rcx, rbx; SRWLock
0x1800db8ca  call    cs:__imp_AcquireSRWLockExclusive
0x1800db8d0  mov     r15, [rdi+88h]
0x1800db8d7  mov     rcx, rbx; SRWLock
0x1800db8da  mov     r14, [rdi+98h]
0x1800db8e1  mov     rsi, [rdi+0A0h]
0x1800db8e8  mov     qword ptr [rdi+88h], 0
0x1800db8f3  mov     qword ptr [rdi+90h], 0
0x1800db8fe  mov     qword ptr [rdi+98h], 0
0x1800db909  mov     qword ptr [rdi+0A0h], 0
0x1800db914  call    cs:__imp_ReleaseSRWLockExclusive
0x1800db91a  test    r15, r15
0x1800db91d  jz      loc_1800DBBCC
0x1800db923  mov     eax, cs:CallbackContext
0x1800db929  cmp     eax, 4
0x1800db92c  jbe     short loc_1800DB958
0x1800db92e  lea     rax, aTaskSchedulerC; "Task scheduler cleanup"
0x1800db935  xor     r8d, r8d
0x1800db938  mov     [rbp+arg_0], rax
0x1800db93c  lea     rdx, qword_1801BC338
0x1800db943  lea     rax, [rbp+arg_0]
0x1800db947  lea     rcx, CallbackContext
0x1800db94e  mov     qword ptr [rsp+70h+dwCreationFlags], rax
0x1800db953  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800db958  test    r14, r14
0x1800db95b  jz      short loc_1800DB96E
0x1800db95d  xor     r9d, r9d; msWindowLength
0x1800db960  xor     r8d, r8d; msPeriod
0x1800db963  xor     edx, edx; pftDueTime
0x1800db965  mov     rcx, r14; pti
0x1800db968  call    cs:__imp_SetThreadpoolTimer
0x1800db96e  test    rsi, rsi
0x1800db971  jz      short loc_1800DB981
0x1800db973  xor     r8d, r8d; pftTimeout
0x1800db976  xor     edx, edx; h
0x1800db978  mov     rcx, rsi; pwa
0x1800db97b  call    cs:__imp_SetThreadpoolWait
0x1800db981  lea     r8, [rbp+phModule]; phModule
0x1800db985  mov     ecx, 4; dwFlags
0x1800db98a  lea     rdx, ?STATIC_CleanupThreadpoolGroup@RdpTaskScheduler@@KAKPEAX@Z; lpModuleName
0x1800db991  call    cs:__imp_GetModuleHandleExW
0x1800db997  test    eax, eax
0x1800db999  jnz     loc_1800DBA40
0x1800db99f  call    cs:__imp_GetLastError
0x1800db9a5  mov     ecx, eax
0x1800db9a7  test    eax, eax
0x1800db9a9  jle     short loc_1800DB9B4
0x1800db9ab  movzx   ecx, ax
0x1800db9ae  or      ecx, 80070000h
0x1800db9b4  mov     eax, cs:CallbackContext
0x1800db9ba  cmp     eax, 2
0x1800db9bd  jbe     loc_1800DBBD0
0x1800db9c3  lea     rax, aFailedToGetMod_0; "Failed to get module handle to itself."
0x1800db9ca  mov     dword ptr [rbp+arg_0], 10Bh
0x1800db9d1  mov     [rbp+var_20], rax
0x1800db9d5  lea     rdx, byte_1801BC297
0x1800db9dc  lea     rax, aCleanup; "CleanUp"
0x1800db9e3  mov     [rbp+arg_10], ecx
0x1800db9e6  mov     [rbp+var_18], rax
0x1800db9ea  lea     rax, aOnecoreTermsrv_52; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800db9f1  mov     [rbp+var_10], rax
0x1800db9f5  lea     rax, aErrorCondition; "Error condition failed"
0x1800db9fc  mov     [rbp+var_8], rax
0x1800dba00  lea     rax, [rbp+var_20]
0x1800dba04  mov     [rsp+70h+var_28], rax
0x1800dba09  lea     rax, [rbp+var_18]
0x1800dba0d  mov     [rsp+70h+var_30], rax
0x1800dba12  lea     rax, [rbp+arg_0]
0x1800dba16  mov     [rsp+70h+var_38], rax
0x1800dba1b  lea     rax, [rbp+var_10]
0x1800dba1f  mov     [rsp+70h+var_40], rax
0x1800dba24  lea     rax, [rbp+arg_10]
0x1800dba28  mov     [rsp+70h+lpThreadId], rax
0x1800dba2d  lea     rax, [rbp+var_8]
0x1800dba31  mov     qword ptr [rsp+70h+dwCreationFlags], rax
0x1800dba36  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800dba3b  jmp     loc_1800DBBD0
0x1800dba40  mov     ecx, 18h; Size
0x1800dba45  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800dba4a  mov     rbx, rax
0x1800dba4d  test    rax, rax
0x1800dba50  jnz     loc_1800DBADC
0x1800dba56  mov     eax, cs:CallbackContext
0x1800dba5c  cmp     eax, 2
0x1800dba5f  jbe     loc_1800DBBD0
0x1800dba65  lea     rax, aCleanupThreadp; "CLEANUP_THREADPOOL_GROUP_INFO allocatio"...
0x1800dba6c  mov     dword ptr [rbp+arg_0], 10Eh
0x1800dba73  mov     [rbp+var_8], rax
0x1800dba77  lea     rdx, qword_1801BC2E8
0x1800dba7e  lea     rax, aCleanup; "CleanUp"
0x1800dba85  mov     [rbp+arg_10], 8007000Eh
0x1800dba8c  mov     [rbp+var_10], rax
0x1800dba90  lea     rax, aOnecoreTermsrv_52; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800dba97  mov     [rbp+var_18], rax
0x1800dba9b  lea     rax, aErrorCondition; "Error condition failed"
0x1800dbaa2  mov     [rbp+var_20], rax
0x1800dbaa6  lea     rax, [rbp+var_8]
0x1800dbaaa  mov     [rsp+70h+var_28], rax
0x1800dbaaf  lea     rax, [rbp+var_10]
0x1800dbab3  mov     [rsp+70h+var_30], rax
0x1800dbab8  lea     rax, [rbp+arg_0]
0x1800dbabc  mov     [rsp+70h+var_38], rax
0x1800dbac1  lea     rax, [rbp+var_18]
0x1800dbac5  mov     [rsp+70h+var_40], rax
0x1800dbaca  lea     rax, [rbp+arg_10]
0x1800dbace  mov     [rsp+70h+lpThreadId], rax
0x1800dbad3  lea     rax, [rbp+var_20]
0x1800dbad7  jmp     loc_1800DBA31
0x1800dbadc  mov     [rax+8], r15
0x1800dbae0  lea     r8, ?STATIC_CleanupThreadpoolGroup@RdpTaskScheduler@@KAKPEAX@Z; lpStartAddress
0x1800dbae7  mov     [rax+10h], r12d
0x1800dbaeb  mov     r9, rbx; lpParameter
0x1800dbaee  mov     rax, [rbp+phModule]
0x1800dbaf2  xor     edx, edx; dwStackSize
0x1800dbaf4  mov     [rsp+70h+lpThreadId], 0; lpThreadId
0x1800dbafd  xor     ecx, ecx; lpThreadAttributes
0x1800dbaff  mov     [rbx], rax
0x1800dbb02  mov     [rsp+70h+dwCreationFlags], 0; dwCreationFlags
0x1800dbb0a  call    cs:__imp_CreateThread
0x1800dbb10  test    rax, rax
0x1800dbb13  jnz     loc_1800DBBBB
0x1800dbb19  call    cs:__imp_GetLastError
0x1800dbb1f  mov     ecx, eax
0x1800dbb21  test    eax, eax
0x1800dbb23  jle     short loc_1800DBB2E
0x1800dbb25  movzx   ecx, ax
0x1800dbb28  or      ecx, 80070000h
0x1800dbb2e  mov     eax, cs:CallbackContext
0x1800dbb34  cmp     eax, 2
0x1800dbb37  jbe     short loc_1800DBBB1
0x1800dbb39  lea     rax, aCreationOfTheC; "Creation of the cleanup threadpool grou"...
0x1800dbb40  mov     dword ptr [rbp+arg_0], 11Ch
0x1800dbb47  mov     [rbp+var_8], rax
0x1800dbb4b  lea     rdx, byte_1801BC1FF
0x1800dbb52  lea     rax, aCleanup; "CleanUp"
0x1800dbb59  mov     [rbp+arg_10], ecx
0x1800dbb5c  mov     [rbp+var_10], rax
0x1800dbb60  lea     rax, aOnecoreTermsrv_52; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800dbb67  mov     [rbp+var_18], rax
0x1800dbb6b  lea     rax, aErrorCondition; "Error condition failed"
0x1800dbb72  mov     [rbp+var_20], rax
0x1800dbb76  lea     rax, [rbp+var_8]
0x1800dbb7a  mov     [rsp+70h+var_28], rax
0x1800dbb7f  lea     rax, [rbp+var_10]
0x1800dbb83  mov     [rsp+70h+var_30], rax
0x1800dbb88  lea     rax, [rbp+arg_0]
0x1800dbb8c  mov     [rsp+70h+var_38], rax
0x1800dbb91  lea     rax, [rbp+var_18]
0x1800dbb95  mov     [rsp+70h+var_40], rax
0x1800dbb9a  lea     rax, [rbp+arg_10]
0x1800dbb9e  mov     [rsp+70h+lpThreadId], rax
0x1800dbba3  lea     rax, [rbp+var_20]
0x1800dbba7  mov     qword ptr [rsp+70h+dwCreationFlags], rax
0x1800dbbac  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800dbbb1  mov     rcx, rbx; Block
0x1800dbbb4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800dbbb9  jmp     short loc_1800DBBD0
0x1800dbbbb  mov     rcx, rax; hObject
0x1800dbbbe  call    cs:__imp_CloseHandle
0x1800dbbc4  mov     [rbp+phModule], 0
0x1800dbbcc  or      dword ptr [rdi+2Ch], 4
0x1800dbbd0  mov     rcx, [rbp+phModule]; hLibModule
0x1800dbbd4  test    rcx, rcx
0x1800dbbd7  jz      short loc_1800DBBDF
0x1800dbbd9  call    cs:__imp_FreeLibrary
0x1800dbbdf  xor     eax, eax
0x1800dbbe1  add     rsp, 70h
0x1800dbbe5  pop     r15
0x1800dbbe7  pop     r14
0x1800dbbe9  pop     r12
0x1800dbbeb  pop     rdi
0x1800dbbec  pop     rsi
0x1800dbbed  pop     rbx
0x1800dbbee  pop     rbp
0x1800dbbef  retn
```
