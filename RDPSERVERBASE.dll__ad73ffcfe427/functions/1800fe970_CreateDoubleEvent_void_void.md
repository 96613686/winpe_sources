# CreateDoubleEvent(void * *,void * *)

- ea: `0x1800fe970`
- end: `0x1800feb40`
- name: `?CreateDoubleEvent@@YAJPEAPEAX0@Z`
- size: `464`
- prototype: `int(void **, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800ff520`
- `0x1800ff900`

## callees

- `0x180002170`
- `0x1800fe970`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800fea44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800fea4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800fea44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800fea4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fe9a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fea85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fe9a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fea85`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800fea77`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800fea77`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800feb1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800feb1c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800fe995`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800fe995`

## string_xrefs

- `0x1800fe9cf`: `onecore\termsrv\rdpplatform\rdpenc\enccore\umtscommandplugin.cpp`
- `0x1800feaad`: `onecore\termsrv\rdpplatform\rdpenc\enccore\umtscommandplugin.cpp`
- `0x1800fe9e1`: `Failed to create event.  GetLastError[0x%x]`
- `0x1800feabf`: `Failed to create event.  GetLastError[0x%x]`
- `0x1800fe9ba`: `CreateDoubleEvent`
- `0x1800fea98`: `CreateDoubleEvent`

## pseudocode

```c
__int64 __fastcall CreateDoubleEvent(void **a1, void **a2)
{
  HANDLE EventW; // rdi
  int v5; // ecx
  signed int LastError; // ebx
  int v7; // r8d
  int v8; // r9d
  HANDLE CurrentProcess; // rbx
  HANDLE v10; // rax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v15; // [rsp+50h] [rbp-20h] BYREF
  const char *v16; // [rsp+58h] [rbp-18h] BYREF
  const char *v17; // [rsp+60h] [rbp-10h] BYREF
  const char *v18; // [rsp+68h] [rbp-8h] BYREF
  signed int v19; // [rsp+A0h] [rbp+30h] BYREF
  int v20; // [rsp+A8h] [rbp+38h] BYREF

  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    CurrentProcess = GetCurrentProcess();
    v10 = GetCurrentProcess();
    if ( DuplicateHandle(v10, EventW, CurrentProcess, a2, 0, 0, 2u) )
    {
      *a1 = EventW;
      return 0;
    }
    else
    {
      LastError = GetLastError();
      if ( (unsigned int)CallbackContext > 2 )
      {
        v19 = LastError;
        v18 = "CreateDoubleEvent";
        v20 = 566;
        v17 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\umtscommandplugin.cpp";
        v16 = "Failed to create event.  GetLastError[0x%x]";
        v15 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v11,
          (unsigned int)word_18028631A,
          v12,
          v13,
          (__int64)&v16,
          (__int64)&v15,
          (__int64)&v17,
          (__int64)&v20,
          (__int64)&v18,
          (__int64)&v19);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      CloseHandle(EventW);
    }
  }
  else
  {
    LastError = GetLastError();
    if ( (unsigned int)CallbackContext > 2 )
    {
      v19 = LastError;
      v16 = "CreateDoubleEvent";
      v20 = 552;
      v17 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\umtscommandplugin.cpp";
      v18 = "Failed to create event.  GetLastError[0x%x]";
      v15 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v5,
        (unsigned int)qword_1802862C8,
        v7,
        v8,
        (__int64)&v18,
        (__int64)&v15,
        (__int64)&v17,
        (__int64)&v20,
        (__int64)&v16,
        (__int64)&v19);
    }
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800fe970  mov     [rsp-18h+arg_0], rbx
0x1800fe975  mov     [rsp-18h+arg_8], rsi
0x1800fe97a  push    rbp
0x1800fe97b  push    rdi
0x1800fe97c  push    r14
0x1800fe97e  mov     rbp, rsp
0x1800fe981  sub     rsp, 70h
0x1800fe985  mov     r14, rdx
0x1800fe988  mov     rsi, rcx
0x1800fe98b  xor     edx, edx; bManualReset
0x1800fe98d  xor     ecx, ecx; lpEventAttributes
0x1800fe98f  xor     r9d, r9d; lpName
0x1800fe992  xor     r8d, r8d; bInitialState
0x1800fe995  call    cs:__imp_CreateEventW
0x1800fe99b  mov     rdi, rax
0x1800fe99e  test    rax, rax
0x1800fe9a1  jnz     loc_1800FEA44
0x1800fe9a7  call    cs:__imp_GetLastError
0x1800fe9ad  mov     ebx, eax
0x1800fe9af  mov     eax, cs:CallbackContext
0x1800fe9b5  cmp     eax, 2
0x1800fe9b8  jbe     short loc_1800FEA2E
0x1800fe9ba  lea     rax, aCreatedoubleev; "CreateDoubleEvent"
0x1800fe9c1  mov     [rbp+arg_10], ebx
0x1800fe9c4  mov     [rbp+var_18], rax
0x1800fe9c8  lea     rdx, qword_1802862C8
0x1800fe9cf  lea     rax, aOnecoreTermsrv_70; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800fe9d6  mov     [rbp+arg_18], 228h
0x1800fe9dd  mov     [rbp+var_10], rax
0x1800fe9e1  lea     rax, aFailedToCreate_64; "Failed to create event.  GetLastError[0"...
0x1800fe9e8  mov     [rbp+var_8], rax
0x1800fe9ec  lea     rax, [rbp+arg_10]
0x1800fe9f0  mov     [rsp+70h+var_28], rax
0x1800fe9f5  lea     rax, [rbp+var_18]
0x1800fe9f9  mov     [rsp+70h+var_30], rax
0x1800fe9fe  lea     rax, [rbp+arg_18]
0x1800fea02  mov     [rsp+70h+var_38], rax
0x1800fea07  lea     rax, [rbp+var_10]
0x1800fea0b  mov     qword ptr [rsp+70h+dwOptions], rax
0x1800fea10  lea     rax, [rbp+var_20]
0x1800fea14  mov     qword ptr [rsp+70h+bInheritHandle], rax
0x1800fea19  lea     rax, [rbp+var_8]
0x1800fea1d  mov     qword ptr [rsp+70h+dwDesiredAccess], rax
0x1800fea22  mov     [rbp+var_20], 80004005h
0x1800fea29  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800fea2e  test    ebx, ebx
0x1800fea30  jle     loc_1800FEB29
0x1800fea36  movzx   ebx, bx
0x1800fea39  or      ebx, 80070000h
0x1800fea3f  jmp     loc_1800FEB29
0x1800fea44  call    cs:__imp_GetCurrentProcess
0x1800fea4a  mov     rbx, rax
0x1800fea4d  call    cs:__imp_GetCurrentProcess
0x1800fea53  mov     [rsp+70h+dwOptions], 2; dwOptions
0x1800fea5b  mov     r9, r14; lpTargetHandle
0x1800fea5e  mov     rcx, rax; hSourceProcessHandle
0x1800fea61  mov     [rsp+70h+bInheritHandle], 0; bInheritHandle
0x1800fea69  mov     r8, rbx; hTargetProcessHandle
0x1800fea6c  mov     [rsp+70h+dwDesiredAccess], 0; dwDesiredAccess
0x1800fea74  mov     rdx, rdi; hSourceHandle
0x1800fea77  call    cs:__imp_DuplicateHandle
0x1800fea7d  test    eax, eax
0x1800fea7f  jnz     loc_1800FEB24
0x1800fea85  call    cs:__imp_GetLastError
0x1800fea8b  mov     ebx, eax
0x1800fea8d  mov     eax, cs:CallbackContext
0x1800fea93  cmp     eax, 2
0x1800fea96  jbe     short loc_1800FEB0C
0x1800fea98  lea     rax, aCreatedoubleev; "CreateDoubleEvent"
0x1800fea9f  mov     [rbp+arg_10], ebx
0x1800feaa2  mov     [rbp+var_8], rax
0x1800feaa6  lea     rdx, word_18028631A
0x1800feaad  lea     rax, aOnecoreTermsrv_70; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800feab4  mov     [rbp+arg_18], 236h
0x1800feabb  mov     [rbp+var_10], rax
0x1800feabf  lea     rax, aFailedToCreate_64; "Failed to create event.  GetLastError[0"...
0x1800feac6  mov     [rbp+var_18], rax
0x1800feaca  lea     rax, [rbp+arg_10]
0x1800feace  mov     [rsp+70h+var_28], rax
0x1800fead3  lea     rax, [rbp+var_8]
0x1800fead7  mov     [rsp+70h+var_30], rax
0x1800feadc  lea     rax, [rbp+arg_18]
0x1800feae0  mov     [rsp+70h+var_38], rax
0x1800feae5  lea     rax, [rbp+var_10]
0x1800feae9  mov     qword ptr [rsp+70h+dwOptions], rax
0x1800feaee  lea     rax, [rbp+var_20]
0x1800feaf2  mov     qword ptr [rsp+70h+bInheritHandle], rax
0x1800feaf7  lea     rax, [rbp+var_18]
0x1800feafb  mov     qword ptr [rsp+70h+dwDesiredAccess], rax
0x1800feb00  mov     [rbp+var_20], 80004005h
0x1800feb07  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800feb0c  test    ebx, ebx
0x1800feb0e  jle     short loc_1800FEB19
0x1800feb10  movzx   ebx, bx
0x1800feb13  or      ebx, 80070000h
0x1800feb19  mov     rcx, rdi; hObject
0x1800feb1c  call    cs:__imp_CloseHandle
0x1800feb22  jmp     short loc_1800FEB29
0x1800feb24  mov     [rsi], rdi
0x1800feb27  xor     ebx, ebx
0x1800feb29  lea     r11, [rsp+70h+var_s0]
0x1800feb2e  mov     eax, ebx
0x1800feb30  mov     rbx, [r11+20h]
0x1800feb34  mov     rsi, [r11+28h]
0x1800feb38  mov     rsp, r11
0x1800feb3b  pop     r14
0x1800feb3d  pop     rdi
0x1800feb3e  pop     rbp
0x1800feb3f  retn
```
