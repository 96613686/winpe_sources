# CRDPENCNamedPipeListener::HandleSingleConnection(_SECURITY_ATTRIBUTES const &,ITSThread *,int *)

- ea: `0x1800652a0`
- end: `0x180065917`
- name: `?HandleSingleConnection@CRDPENCNamedPipeListener@@IEAAJAEBU_SECURITY_ATTRIBUTES@@PEAVITSThread@@PEAH@Z`
- size: `1655`
- prototype: `__int64 __fastcall(CRDPENCNamedPipeListener *__hidden this, LPSECURITY_ATTRIBUTES lpSecurityAttributes, struct ITSThread *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180065920`

## callees

- `0x1800018a4`
- `0x180001aa0`
- `0x180002550`
- `0x1800025dc`
- `0x180003c38`
- `0x180005090`
- `0x18000552c`
- `0x1800646f8`
- `0x180064e60`
- `0x1800652a0`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065421`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006551c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006568f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800657a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065421`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006551c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006568f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800657a8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800655e4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800655e4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180065746`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180065746`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006540f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006540f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065705`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065714`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065705`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065714`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x180065505`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x180065505`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180065685`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180065685`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18006579e`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18006579e`

## string_xrefs

- `0x180065445`: `CreateEvent failed`
- `0x1800652f7`: `pThread is NULL`
- `0x180065393`: `pfCreatePipeEventSignalled is NULL`
- `0x1800655b4`: `Created named pipe instance`
- `0x180065540`: `CreatePipe failed`

## pseudocode

```c
__int64 __fastcall CRDPENCNamedPipeListener::HandleSingleConnection(
        CRDPENCNamedPipeListener *this,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        struct ITSThread *a3,
        int *a4)
{
  unsigned int v7; // ebx
  char *v8; // rdx
  HANDLE *p_hFile; // rax
  HANDLE EventW; // r13
  signed int LastError; // eax
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  bool v15; // cf
  int v16; // eax
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  HANDLE v20; // rbx
  signed int v21; // eax
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  CRDPENCNamedPipeListener *v25; // rcx
  int v26; // eax
  int v27; // r8d
  int v28; // r9d
  HANDLE v29; // r12
  signed int v30; // eax
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  void *v35; // rcx
  int v36; // r9d
  signed int v37; // eax
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  int v41; // ecx
  int v42; // r8d
  int v43; // r9d
  const char **nDefaultTimeOut; // [rsp+30h] [rbp-59h]
  const char **v45; // [rsp+40h] [rbp-49h]
  HANDLE *v46; // [rsp+48h] [rbp-41h]
  const char *v47; // [rsp+50h] [rbp-39h] BYREF
  const char *v48; // [rsp+58h] [rbp-31h] BYREF
  HANDLE hFile; // [rsp+60h] [rbp-29h] BYREF
  const char *v50; // [rsp+68h] [rbp-21h] BYREF
  int v51[2]; // [rsp+70h] [rbp-19h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+78h] [rbp-11h] BYREF
  const char *NumberOfBytesTransferred; // [rsp+100h] [rbp+77h] BYREF

  NumberOfBytesTransferred = (const char *)a3;
  v51[0] = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( a3 )
  {
    if ( !a4 )
    {
      v7 = -2147024809;
      if ( (unsigned int)CallbackContext <= 2 )
        return v7;
      LODWORD(NumberOfBytesTransferred) = 553;
      v48 = "pfCreatePipeEventSignalled is NULL";
      v47 = "HandleSingleConnection";
      hFile = "Error condition failed";
      v50 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
      v46 = (HANDLE *)&v48;
      v8 = byte_1801C5DA9;
      v45 = &v47;
      nDefaultTimeOut = &v50;
      p_hFile = &hFile;
      goto LABEL_4;
    }
    EventW = CreateEventW(0, 1, 0, 0);
    if ( !EventW )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(NumberOfBytesTransferred) = 567;
        v50 = "CreateEvent failed";
        v48 = "HandleSingleConnection";
        v47 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
        v51[0] = v7;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v12,
          (unsigned int)byte_1801C5D0D,
          v13,
          v14,
          (__int64)&v50,
          (__int64)v51,
          (__int64)&v47,
          (__int64)&NumberOfBytesTransferred,
          (__int64)&v48);
      }
      return v7;
    }
    v15 = *((_DWORD *)this + 167) != 0;
    v16 = *((_DWORD *)this + 166);
    Overlapped.hEvent = EventW;
    hFile = CreateNamedPipeW(
              (LPCWSTR)this + 76,
              0x40000003u,
              v16 != 0 ? 8 : 0,
              v15 ? 1 : 255,
              0x8000u,
              0x8000u,
              0,
              lpSecurityAttributes);
    v20 = hFile;
    if ( hFile == (HANDLE)-1LL )
    {
      v21 = GetLastError();
      v7 = v21;
      if ( v21 > 0 )
        v7 = (unsigned __int16)v21 | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(NumberOfBytesTransferred) = 607;
        v50 = "CreatePipe failed";
        v48 = "HandleSingleConnection";
        v47 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
        v51[0] = v7;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v22,
          (unsigned int)byte_1801C5C93,
          v23,
          v24,
          (__int64)&v50,
          (__int64)v51,
          (__int64)&v47,
          (__int64)&NumberOfBytesTransferred,
          (__int64)&v48);
      }
LABEL_31:
      if ( EventW != (HANDLE)-1LL )
        CloseHandle(EventW);
      return v7;
    }
    if ( (unsigned int)CallbackContext > 5 )
    {
      v48 = (char *)this + 152;
      v47 = "Created named pipe instance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v17,
        (unsigned int)byte_1801C5CDD,
        v18,
        v19,
        (__int64)&v47,
        (__int64)&v48);
    }
    ResetEvent(EventW);
    v26 = CRDPENCNamedPipeListener::AcceptClient(v25, v20, &Overlapped, v51);
    v7 = v26;
    if ( v26 >= 0 )
    {
      if ( !*a4 )
      {
        v35 = (void *)*((_QWORD *)this + 15);
        *((_DWORD *)this + 32) = 0;
        SetEvent(v35);
        *a4 = 1;
      }
      v7 = (*(__int64 (__fastcall **)(const char *, HANDLE, __int64, __int64))(*(_QWORD *)NumberOfBytesTransferred + 72LL))(
             NumberOfBytesTransferred,
             EventW,
             3,
             0xFFFFFFFFLL);
      if ( (v7 & 0x80000000) == 0 )
      {
        v29 = hFile;
        if ( !v51[0]
          || (LODWORD(NumberOfBytesTransferred) = 0,
              GetOverlappedResult(hFile, &Overlapped, (LPDWORD)&NumberOfBytesTransferred, 0)) )
        {
          if ( (unsigned int)CallbackContext > 4 )
          {
            NumberOfBytesTransferred = "Named Pipe Client Connected successfully";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              (unsigned int)&CallbackContext,
              (unsigned int)byte_1801C5B7B,
              0,
              v36,
              (__int64)&NumberOfBytesTransferred);
          }
          if ( (unsigned int)CallbackContext > 4 && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL) )
          {
            hFile = (HANDLE)0x1000000;
            NumberOfBytesTransferred = (char *)this + 152;
            v48 = "wwwwwwwwwwwwwwwwFailed to Initialize";
            v47 = "NamedPipe";
            v50 = "Stack";
            *(_QWORD *)v51 = "Checkpoint";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>>(
              v41,
              (unsigned int)byte_1801C5BA1,
              v42,
              v43,
              (__int64)v51,
              (__int64)&hFile,
              (__int64)&v50,
              (__int64)&v47,
              (__int64)&v48,
              (__int64)&NumberOfBytesTransferred);
          }
          CRDPENCNamedPipeListener::Decouple_OnConnectionCompleted(this, v29);
          goto LABEL_31;
        }
        v37 = GetLastError();
        v7 = v37;
        if ( v37 > 0 )
          v7 = (unsigned __int16)v37 | 0x80070000;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v48 = "HandleSingleConnection";
          v50 = "GetOverlappedResult failed";
          v51[0] = 653;
          v47 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
          LODWORD(hFile) = v7;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v38,
            (unsigned int)byte_1801C5C09,
            v39,
            v40,
            (__int64)&v50,
            (__int64)&hFile,
            (__int64)&v47,
            (__int64)v51,
            (__int64)&v48);
        }
        goto LABEL_24;
      }
    }
    else if ( (unsigned int)CallbackContext > 3 )
    {
      LODWORD(NumberOfBytesTransferred) = v26;
      v48 = "HandleSingleConnection";
      v47 = "Error while accepting named pipe client";
      v50 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)byte_1801C5C53,
        v27,
        v28,
        (__int64)&v50,
        (__int64)&v47,
        (__int64)&NumberOfBytesTransferred,
        (__int64)&v48);
    }
    v29 = hFile;
LABEL_24:
    if ( v7 != -2147024787 && !CancelIoEx(v29, 0) )
    {
      v30 = GetLastError();
      v7 = v30;
      if ( v30 > 0 )
        v7 = (unsigned __int16)v30 | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v48 = "HandleSingleConnection";
        v50 = "CancelIo failed. Ignoring and closing handle";
        LODWORD(NumberOfBytesTransferred) = 685;
        v47 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
        LODWORD(hFile) = v7;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v31,
          (unsigned int)byte_1801C5B31,
          v32,
          v33,
          (__int64)&v50,
          (__int64)&hFile,
          (__int64)&v47,
          (__int64)&NumberOfBytesTransferred,
          (__int64)&v48);
      }
    }
    CloseHandle(v29);
    goto LABEL_31;
  }
  v7 = -2147024809;
  if ( (unsigned int)CallbackContext > 2 )
  {
    LODWORD(NumberOfBytesTransferred) = 552;
    hFile = "pThread is NULL";
    v50 = "HandleSingleConnection";
    v48 = "Error condition failed";
    v47 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
    v46 = &hFile;
    v8 = &byte_1801C5D57;
    v45 = &v50;
    nDefaultTimeOut = &v47;
    p_hFile = (HANDLE *)&v48;
LABEL_4:
    v51[0] = -2147024809;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      -2147024809,
      (_DWORD)v8,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)p_hFile,
      (__int64)v51,
      (__int64)nDefaultTimeOut,
      (__int64)&NumberOfBytesTransferred,
      (__int64)v45,
      (__int64)v46);
  }
  return v7;
}

```

## disassembly

```asm
0x1800652a0  mov     [rsp-8+NumberOfBytesTransferred], r8
0x1800652a5  push    rbp
0x1800652a6  push    rbx
0x1800652a7  push    rsi
0x1800652a8  push    rdi
0x1800652a9  push    r12
0x1800652ab  push    r13
0x1800652ad  push    r14
0x1800652af  push    r15
0x1800652b1  lea     rbp, [rsp-1Fh]
0x1800652b6  sub     rsp, 0A8h
0x1800652bd  mov     [rbp+57h+var_70], 0
0x1800652c4  xorps   xmm0, xmm0
0x1800652c7  mov     r12, r9
0x1800652ca  mov     rbx, rdx
0x1800652cd  mov     r15, rcx
0x1800652d0  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x1800652d4  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x1800652d8  test    r8, r8
0x1800652db  jnz     loc_180065374
0x1800652e1  mov     eax, cs:CallbackContext
0x1800652e7  mov     ecx, 80070057h
0x1800652ec  mov     ebx, ecx
0x1800652ee  cmp     eax, 2
0x1800652f1  jbe     loc_18006571A
0x1800652f7  lea     rax, aPthreadIsNull; "pThread is NULL"
0x1800652fe  mov     dword ptr [rbp+57h+NumberOfBytesTransferred], 228h
0x180065305  mov     [rbp+57h+hFile], rax
0x180065309  lea     rdi, aHandlesingleco; "HandleSingleConnection"
0x180065310  lea     rax, aErrorCondition; "Error condition failed"
0x180065317  mov     [rbp+57h+var_78], rdi
0x18006531b  mov     [rbp+57h+var_88], rax
0x18006531f  lea     rsi, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180065326  lea     rax, [rbp+57h+hFile]
0x18006532a  mov     [rbp+57h+var_90], rsi
0x18006532e  mov     [rsp+0E0h+var_98], rax
0x180065333  lea     rdx, byte_1801C5D57
0x18006533a  lea     rax, [rbp+57h+var_78]
0x18006533e  mov     [rsp+0E0h+var_A0], rax
0x180065343  lea     rax, [rbp+57h+NumberOfBytesTransferred]
0x180065347  mov     [rsp+0E0h+lpSecurityAttributes], rax
0x18006534c  lea     rax, [rbp+57h+var_90]
0x180065350  mov     qword ptr [rsp+0E0h+nDefaultTimeOut], rax
0x180065355  lea     rax, [rbp+57h+var_70]
0x180065359  mov     qword ptr [rsp+0E0h+nInBufferSize], rax
0x18006535e  lea     rax, [rbp+57h+var_88]
0x180065362  mov     qword ptr [rsp+0E0h+nOutBufferSize], rax
0x180065367  mov     [rbp+57h+var_70], ecx
0x18006536a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18006536f  jmp     loc_18006571A
0x180065374  test    r12, r12
0x180065377  jnz     loc_180065403
0x18006537d  mov     eax, cs:CallbackContext
0x180065383  mov     ecx, 80070057h
0x180065388  mov     ebx, ecx
0x18006538a  cmp     eax, 2
0x18006538d  jbe     loc_18006571A
0x180065393  lea     rax, aPfcreatepipeev; "pfCreatePipeEventSignalled is NULL"
0x18006539a  mov     dword ptr [rbp+57h+NumberOfBytesTransferred], 229h
0x1800653a1  mov     [rbp+57h+var_88], rax
0x1800653a5  lea     rdi, aHandlesingleco; "HandleSingleConnection"
0x1800653ac  lea     rax, aErrorCondition; "Error condition failed"
0x1800653b3  mov     [rbp+57h+var_90], rdi
0x1800653b7  mov     [rbp+57h+hFile], rax
0x1800653bb  lea     rsi, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800653c2  lea     rax, [rbp+57h+var_88]
0x1800653c6  mov     [rbp+57h+var_78], rsi
0x1800653ca  mov     [rsp+0E0h+var_98], rax
0x1800653cf  lea     rdx, byte_1801C5DA9
0x1800653d6  lea     rax, [rbp+57h+var_90]
0x1800653da  mov     [rsp+0E0h+var_A0], rax
0x1800653df  lea     rax, [rbp+57h+NumberOfBytesTransferred]
0x1800653e3  mov     [rsp+0E0h+lpSecurityAttributes], rax
0x1800653e8  lea     rax, [rbp+57h+var_78]
0x1800653ec  mov     qword ptr [rsp+0E0h+nDefaultTimeOut], rax
0x1800653f1  lea     rax, [rbp+57h+var_70]
0x1800653f5  mov     qword ptr [rsp+0E0h+nInBufferSize], rax
0x1800653fa  lea     rax, [rbp+57h+hFile]
0x1800653fe  jmp     loc_180065362
0x180065403  xor     r9d, r9d; lpName
0x180065406  xor     r8d, r8d; bInitialState
0x180065409  xor     ecx, ecx; lpEventAttributes
0x18006540b  lea     edx, [r9+1]; bManualReset
0x18006540f  call    cs:__imp_CreateEventW
0x180065415  mov     r13, rax
0x180065418  test    rax, rax
0x18006541b  jnz     loc_1800654AE
0x180065421  call    cs:__imp_GetLastError
0x180065427  mov     ebx, eax
0x180065429  test    eax, eax
0x18006542b  jle     short loc_180065436
0x18006542d  movzx   ebx, ax
0x180065430  or      ebx, 80070000h
0x180065436  mov     eax, cs:CallbackContext
0x18006543c  cmp     eax, 2
0x18006543f  jbe     loc_18006571A
0x180065445  lea     rax, aCreateeventFai; "CreateEvent failed"
0x18006544c  mov     dword ptr [rbp+57h+NumberOfBytesTransferred], 237h
0x180065453  mov     [rbp+57h+var_78], rax
0x180065457  lea     rdi, aHandlesingleco; "HandleSingleConnection"
0x18006545e  lea     rax, [rbp+57h+var_88]
0x180065462  mov     [rbp+57h+var_88], rdi
0x180065466  mov     [rsp+0E0h+var_A0], rax
0x18006546b  lea     rsi, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180065472  lea     rax, [rbp+57h+NumberOfBytesTransferred]
0x180065476  mov     [rbp+57h+var_90], rsi
0x18006547a  mov     [rsp+0E0h+lpSecurityAttributes], rax
0x18006547f  lea     rdx, byte_1801C5D0D
0x180065486  lea     rax, [rbp+57h+var_90]
0x18006548a  mov     [rbp+57h+var_70], ebx
0x18006548d  mov     qword ptr [rsp+0E0h+nDefaultTimeOut], rax
0x180065492  lea     rax, [rbp+57h+var_70]
0x180065496  mov     qword ptr [rsp+0E0h+nInBufferSize], rax
0x18006549b  lea     rax, [rbp+57h+var_78]
0x18006549f  mov     qword ptr [rsp+0E0h+nOutBufferSize], rax
0x1800654a4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800654a9  jmp     loc_18006571A
0x1800654ae  mov     eax, [r15+29Ch]
0x1800654b5  lea     rdi, [r15+98h]
0x1800654bc  neg     eax
0x1800654be  mov     [rsp+0E0h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800654c3  mov     eax, [r15+298h]
0x1800654ca  mov     edx, 40000003h; dwOpenMode
0x1800654cf  sbb     r9d, r9d
0x1800654d2  mov     [rsp+0E0h+nDefaultTimeOut], 0; nDefaultTimeOut
0x1800654da  and     r9d, 0FFFFFF02h
0x1800654e1  mov     [rbp+57h+Overlapped.hEvent], r13
0x1800654e5  add     r9d, 0FFh; nMaxInstances
0x1800654ec  mov     rcx, rdi; lpName
0x1800654ef  neg     eax
0x1800654f1  mov     eax, 8000h
0x1800654f6  sbb     r8d, r8d
0x1800654f9  mov     [rsp+0E0h+nInBufferSize], eax; nInBufferSize
0x1800654fd  and     r8d, 8; dwPipeMode
0x180065501  mov     [rsp+0E0h+nOutBufferSize], eax; nOutBufferSize
0x180065505  call    cs:__imp_CreateNamedPipeW
0x18006550b  mov     [rbp+57h+hFile], rax
0x18006550f  mov     rbx, rax
0x180065512  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180065516  jnz     loc_1800655A9
0x18006551c  call    cs:__imp_GetLastError
0x180065522  mov     ebx, eax
0x180065524  test    eax, eax
0x180065526  jle     short loc_180065531
0x180065528  movzx   ebx, ax
0x18006552b  or      ebx, 80070000h
0x180065531  mov     eax, cs:CallbackContext
0x180065537  cmp     eax, 2
0x18006553a  jbe     loc_18006570B
0x180065540  lea     rax, aCreatepipeFail; "CreatePipe failed"
0x180065547  mov     dword ptr [rbp+57h+NumberOfBytesTransferred], 25Fh
0x18006554e  mov     [rbp+57h+var_78], rax
0x180065552  lea     rdi, aHandlesingleco; "HandleSingleConnection"
0x180065559  lea     rax, [rbp+57h+var_88]
0x18006555d  mov     [rbp+57h+var_88], rdi
0x180065561  mov     [rsp+0E0h+var_A0], rax
0x180065566  lea     rsi, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18006556d  lea     rax, [rbp+57h+NumberOfBytesTransferred]
0x180065571  mov     [rbp+57h+var_90], rsi
0x180065575  mov     [rsp+0E0h+lpSecurityAttributes], rax
0x18006557a  lea     rdx, byte_1801C5C93
0x180065581  lea     rax, [rbp+57h+var_90]
0x180065585  mov     [rbp+57h+var_70], ebx
0x180065588  mov     qword ptr [rsp+0E0h+nDefaultTimeOut], rax
0x18006558d  lea     rax, [rbp+57h+var_70]
0x180065591  mov     qword ptr [rsp+0E0h+nInBufferSize], rax
0x180065596  lea     rax, [rbp+57h+var_78]
0x18006559a  mov     qword ptr [rsp+0E0h+nOutBufferSize], rax
0x18006559f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800655a4  jmp     loc_18006570B
0x1800655a9  mov     eax, cs:CallbackContext
0x1800655af  cmp     eax, 5
0x1800655b2  jbe     short loc_1800655E1
0x1800655b4  lea     rax, aCreatedNamedPi; "Created named pipe instance"
0x1800655bb  mov     [rbp+57h+var_88], rdi
0x1800655bf  mov     [rbp+57h+var_90], rax
0x1800655c3  lea     rdx, byte_1801C5CDD
0x1800655ca  lea     rax, [rbp+57h+var_88]
0x1800655ce  mov     qword ptr [rsp+0E0h+nInBufferSize], rax
0x1800655d3  lea     rax, [rbp+57h+var_90]
0x1800655d7  mov     qword ptr [rsp+0E0h+nOutBufferSize], rax
0x1800655dc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800655e1  mov     rcx, r13; hEvent
0x1800655e4  call    cs:__imp_ResetEvent
0x1800655ea  lea     r9, [rbp+57h+var_70]; int *
0x1800655ee  mov     rdx, rbx; void *
0x1800655f1  lea     r8, [rbp+57h+Overlapped]; struct _OVERLAPPED *
0x1800655f5  call    ?AcceptClient@CRDPENCNamedPipeListener@@IEAAJPEAXPEAU_OVERLAPPED@@PEAH@Z; CRDPENCNamedPipeListener::AcceptClient(void *,_OVERLAPPED *,int *)
0x1800655fa  lea     rsi, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180065601  mov     ebx, eax
0x180065603  lea     rdi, aHandlesingleco; "HandleSingleConnection"
0x18006560a  mov     r14d, 80070000h
0x180065610  test    eax, eax
0x180065612  jns     loc_180065730
0x180065618  mov     ecx, cs:CallbackContext
0x18006561e  cmp     ecx, 3
0x180065621  jbe     short loc_180065670
0x180065623  mov     dword ptr [rbp+57h+NumberOfBytesTransferred], eax
0x180065626  lea     rdx, byte_1801C5C53
0x18006562d  lea     rax, aErrorWhileAcce; "Error while accepting named pipe client"
0x180065634  mov     [rbp+57h+var_88], rdi
0x180065638  mov     [rbp+57h+var_90], rax
0x18006563c  lea     rax, aWarningHresult; "Warning HResult failed"
0x180065643  mov     [rbp+57h+var_78], rax
0x180065647  lea     rax, [rbp+57h+var_88]
0x18006564b  mov     [rsp+0E0h+lpSecurityAttributes], rax
0x180065650  lea     rax, [rbp+57h+NumberOfBytesTransferred]
0x180065654  mov     qword ptr [rsp+0E0h+nDefaultTimeOut], rax
0x180065659  lea     rax, [rbp+57h+var_90]
0x18006565d  mov     qword ptr [rsp+0E0h+nInBufferSize], rax
0x180065662  lea     rax, [rbp+57h+var_78]
0x180065666  mov     qword ptr [rsp+0E0h+nOutBufferSize], rax
0x18006566b  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180065670  mov     r12, [rbp+57h+hFile]
0x180065674  cmp     ebx, 8007006Dh
0x18006567a  jz      loc_180065702
0x180065680  xor     edx, edx; lpOverlapped
0x180065682  mov     rcx, r12; hFile
0x180065685  call    cs:__imp_CancelIoEx
0x18006568b  test    eax, eax
0x18006568d  jnz     short loc_180065702
0x18006568f  call    cs:__imp_GetLastError
0x180065695  mov     ebx, eax
0x180065697  test    eax, eax
0x180065699  jle     short loc_1800656A1
0x18006569b  movzx   ebx, ax
0x18006569e  or      ebx, r14d
0x1800656a1  mov     eax, cs:CallbackContext
0x1800656a7  cmp     eax, 2
0x1800656aa  jbe     short loc_180065702
0x1800656ac  lea     rax, aCancelioFailed; "CancelIo failed. Ignoring and closing h"...
0x1800656b3  mov     [rbp+57h+var_88], rdi
0x1800656b7  mov     [rbp+57h+var_78], rax
0x1800656bb  lea     rdx, byte_1801C5B31
0x1800656c2  lea     rax, [rbp+57h+var_88]
0x1800656c6  mov     dword ptr [rbp+57h+NumberOfBytesTransferred], 2ADh
0x1800656cd  mov     [rsp+0E0h+var_A0], rax
0x1800656d2  lea     rax, [rbp+57h+NumberOfBytesTransferred]
0x1800656d6  mov     [rsp+0E0h+lpSecurityAttributes], rax
0x1800656db  lea     rax, [rbp+57h+var_90]
0x1800656df  mov     qword ptr [rsp+0E0h+nDefaultTimeOut], rax
0x1800656e4  lea     rax, [rbp+57h+hFile]
0x1800656e8  mov     qword ptr [rsp+0E0h+nInBufferSize], rax
0x1800656ed  lea     rax, [rbp+57h+var_78]
0x1800656f1  mov     qword ptr [rsp+0E0h+nOutBufferSize], rax
0x1800656f6  mov     [rbp+57h+var_90], rsi
0x1800656fa  mov     dword ptr [rbp+57h+hFile], ebx
0x1800656fd  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180065702  mov     rcx, r12; hObject
0x180065705  call    cs:__imp_CloseHandle
0x18006570b  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x18006570f  jz      short loc_18006571A
0x180065711  mov     rcx, r13; hObject
0x180065714  call    cs:__imp_CloseHandle
0x18006571a  mov     eax, ebx
0x18006571c  add     rsp, 0A8h
0x180065723  pop     r15
0x180065725  pop     r14
0x180065727  pop     r13
0x180065729  pop     r12
0x18006572b  pop     rdi
0x18006572c  pop     rsi
0x18006572d  pop     rbx
0x18006572e  pop     rbp
0x18006572f  retn
0x180065730  cmp     dword ptr [r12], 0
0x180065735  jnz     short loc_180065754
0x180065737  mov     rcx, [r15+78h]; hEvent
0x18006573b  mov     dword ptr [r15+80h], 0
0x180065746  call    cs:__imp_SetEvent
0x18006574c  mov     dword ptr [r12], 1
0x180065754  mov     rcx, [rbp+57h+NumberOfBytesTransferred]
0x180065758  or      r9d, 0FFFFFFFFh
0x18006575c  mov     r8d, 3
0x180065762  mov     rdx, r13
0x180065765  mov     rax, [rcx]
0x180065768  mov     rax, [rax+48h]
0x18006576c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065771  mov     ebx, eax
0x180065773  test    eax, eax
0x180065775  js      loc_180065670
0x18006577b  cmp     [rbp+57h+var_70], 0
0x18006577f  mov     r12, [rbp+57h+hFile]
0x180065783  jz      loc_180065824
0x180065789  xor     r9d, r9d; bWait
0x18006578c  mov     dword ptr [rbp+57h+NumberOfBytesTransferred], 0
0x180065793  lea     r8, [rbp+57h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180065797  mov     rcx, r12; hFile
0x18006579a  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x18006579e  call    cs:__imp_GetOverlappedResult
0x1800657a4  test    eax, eax
0x1800657a6  jnz     short loc_180065824
0x1800657a8  call    cs:__imp_GetLastError
0x1800657ae  mov     ebx, eax
0x1800657b0  test    eax, eax
0x1800657b2  jle     short loc_1800657BA
0x1800657b4  movzx   ebx, ax
0x1800657b7  or      ebx, r14d
0x1800657ba  mov     eax, cs:CallbackContext
0x1800657c0  cmp     eax, 2
  ... truncated ...
```
