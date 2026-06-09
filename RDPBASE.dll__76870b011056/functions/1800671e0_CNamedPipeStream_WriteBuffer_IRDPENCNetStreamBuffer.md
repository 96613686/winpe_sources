# CNamedPipeStream::WriteBuffer(IRDPENCNetStreamBuffer *)

- ea: `0x1800671e0`
- end: `0x1800675df`
- name: `?WriteBuffer@CNamedPipeStream@@UEAAJPEAUIRDPENCNetStreamBuffer@@@Z`
- size: `1023`
- prototype: `__int64 __fastcall(PVOID pv, struct IRDPENCNetStreamBuffer *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x1801040c0`

## callees

- `0x1800018a4`
- `0x180001aa0`
- `0x180016ad0`
- `0x180016b00`
- `0x180019a80`
- `0x180019ab0`
- `0x18001cc0c`
- `0x18003bcac`
- `0x18003bcfc`
- `0x180067034`
- `0x1800671e0`
- `0x18007261c`
- `0x1800787d4`
- `0x180103ca8`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006721a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18006721a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006749f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006749f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180067495`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180067495`

## string_xrefs

- `0x1800672ae`: `WriteBuffer`
- `0x180067331`: `WriteBuffer`
- `0x1800673c8`: `WriteBuffer`
- `0x1800674e6`: `WriteBuffer`
- `0x180067546`: `WriteBuffer`
- `0x1800673ec`: `Too many pending writes to a named pipe. Aborting the write.`

## pseudocode

```c
__int64 __fastcall CNamedPipeStream::WriteBuffer(char *pv, struct IRDPENCNetStreamBuffer *a2)
{
  struct _OVERLAPPED *lpOverlapped; // rdi
  ULONGLONG TickCount64; // rbx
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  int v9; // ebx
  DWORD v10; // ecx
  char *v11; // rdx
  const char *v12; // rax
  struct _OVERLAPPED *v13; // rax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  _QWORD *p_InternalHigh; // r14
  signed int LastError; // r14d
  unsigned int v19; // edx
  int v21; // [rsp+50h] [rbp-30h] BYREF
  __int64 v22; // [rsp+58h] [rbp-28h] BYREF
  const char *v23; // [rsp+60h] [rbp-20h] BYREF
  const char *v24; // [rsp+68h] [rbp-18h] BYREF
  const char *v25; // [rsp+70h] [rbp-10h] BYREF
  const char *v26; // [rsp+78h] [rbp-8h] BYREF
  int v27; // [rsp+C0h] [rbp+40h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+C8h] [rbp+48h] BYREF
  signed int v29; // [rsp+D0h] [rbp+50h] BYREF
  int v30; // [rsp+D8h] [rbp+58h] BYREF

  v22 = 0;
  nNumberOfBytesToWrite = 0;
  v27 = 0;
  lpOverlapped = 0;
  v29 = 0;
  TickCount64 = GetTickCount64();
  (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *, int *))(*(_QWORD *)a2 + 56LL))(a2, &v27);
  (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *, DWORD *))(*(_QWORD *)a2 + 40LL))(a2, &nNumberOfBytesToWrite);
  (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *, __int64 *))(*(_QWORD *)a2 + 24LL))(a2, &v22);
  (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *, signed int *))(*(_QWORD *)a2 + 32LL))(a2, &v29);
  CTSCriticalSection::Lock((CTSCriticalSection *)(pv + 80));
  if ( !*((_DWORD *)pv + 24) )
  {
    v9 = -2147467259;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v30 = 474;
      v23 = "SendBuffer: Stream closed";
      v21 = -2147467259;
      v24 = "WriteBuffer";
      v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
      v26 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v6,
        (unsigned int)byte_1801C6F9B,
        v7,
        v8,
        (__int64)&v26,
        (__int64)&v21,
        (__int64)&v25,
        (__int64)&v30,
        (__int64)&v24,
        (__int64)&v23);
    }
    goto LABEL_28;
  }
  v10 = nNumberOfBytesToWrite + v27;
  if ( (int)(nNumberOfBytesToWrite + v27) > v29 )
  {
    v9 = -2147024809;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_28;
    v30 = 478;
    v26 = "WriteBuffer";
    v11 = byte_1801C6FE9;
    v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
    v12 = "Buffer overflow detected";
LABEL_7:
    v24 = v12;
    v21 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v10,
      (_DWORD)v11,
      v7,
      v8,
      (__int64)&v24,
      (__int64)&v21,
      (__int64)&v25,
      (__int64)&v30,
      (__int64)&v26);
    goto LABEL_28;
  }
  if ( *((_DWORD *)pv + 26) > 0x3E8u && TickCount64 - *((_QWORD *)pv + 14) > 0xEA60 )
  {
    v9 = -2147014836;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_28;
    v30 = 495;
    v26 = "WriteBuffer";
    v11 = &byte_1801C6F07;
    v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
    v12 = "Too many pending writes to a named pipe. Aborting the write.";
    goto LABEL_7;
  }
  v9 = 1;
  ++*((_DWORD *)pv + 26);
  v13 = (struct _OVERLAPPED *)operator new(0x38u);
  lpOverlapped = v13;
  if ( v13 )
  {
    v13[1].InternalHigh = 0;
    p_InternalHigh = &v13[1].InternalHigh;
    v13[1].Pointer = 0;
    *(_OWORD *)&v13->Internal = 0;
    *(_OWORD *)&v13->Offset = 0;
    *(_OWORD *)&v13[1].Internal = 0;
    v13[1].Pointer = 0;
    if ( pv != (char *)v13[1].InternalHigh )
    {
      TCntPtr<CTSCoreEventSource>::SafeRelease(&v13[1].InternalHigh);
      *p_InternalHigh = pv;
      TCntPtr<CNamedPipeStream>::SafeAddRef(&lpOverlapped[1].InternalHigh);
    }
    if ( a2 != lpOverlapped[1].Pointer )
    {
      TCntPtr<IXMLDOMNodeList>::SafeRelease(&lpOverlapped[1].16);
      lpOverlapped[1].Pointer = a2;
      TCntPtr<ITSAsyncCallback>::SafeAddRef(&lpOverlapped[1].Offset);
    }
    CNamedPipeStream::StartThreadpoolIo((CNamedPipeStream *)pv);
    if ( WriteFile(*((HANDLE *)pv + 7), (LPCVOID)(v22 + v27), nNumberOfBytesToWrite, 0, lpOverlapped) )
    {
      v9 = 0;
      goto LABEL_28;
    }
    LastError = GetLastError();
    if ( LastError == 997 )
      goto LABEL_28;
    --*((_DWORD *)pv + 26);
    CNamedPipeStream::CancelThreadpoolIo((CNamedPipeStream *)pv);
    v9 = LastError > 0 ? (unsigned __int16)LastError | 0x80070000 : LastError;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_28;
    v30 = 541;
    v26 = "WriteBuffer";
    v11 = byte_1801C6E85;
    v25 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
    v12 = "Failed to post a send. Disconnecting stream.";
    goto LABEL_7;
  }
  v9 = -2147024882;
  if ( (unsigned int)CallbackContext > 2 )
  {
    v30 = 509;
    v26 = "NP_OVERLAPPED_CONTEXT allocation failed";
    v21 = -2147024882;
    v25 = "WriteBuffer";
    v24 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\namedpipestream.cpp";
    v23 = "Error condition failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v14,
      (unsigned int)byte_1801C6F4D,
      v15,
      v16,
      (__int64)&v23,
      (__int64)&v21,
      (__int64)&v24,
      (__int64)&v30,
      (__int64)&v25,
      (__int64)&v26);
  }
  lpOverlapped = 0;
LABEL_28:
  CTSCriticalSection::UnLock((CTSCriticalSection *)(pv + 80));
  if ( v9 < 0 )
  {
    CNamedPipeStream::CloseStream(pv, v9);
    if ( lpOverlapped )
      CNamedPipeStream::NP_OVERLAPPED_CONTEXT::`scalar deleting destructor'(
        (CNamedPipeStream::NP_OVERLAPPED_CONTEXT *)lpOverlapped,
        v19);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800671e0  push    rbp
0x1800671e2  push    rbx
0x1800671e3  push    rsi
0x1800671e4  push    rdi
0x1800671e5  push    r12
0x1800671e7  push    r14
0x1800671e9  push    r15
0x1800671eb  mov     rbp, rsp
0x1800671ee  sub     rsp, 80h
0x1800671f5  mov     r15, rdx
0x1800671f8  mov     [rbp+var_28], 0
0x180067200  mov     rsi, rcx
0x180067203  mov     [rbp+nNumberOfBytesToWrite], 0
0x18006720a  mov     [rbp+arg_0], 0
0x180067211  xor     edi, edi
0x180067213  mov     [rbp+arg_10], 0
0x18006721a  call    cs:__imp_GetTickCount64
0x180067220  lea     rdx, [rbp+arg_0]
0x180067224  mov     rcx, r15
0x180067227  mov     rbx, rax
0x18006722a  mov     rax, [r15]
0x18006722d  mov     rax, [rax+38h]
0x180067231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067236  mov     rax, [r15]
0x180067239  lea     rdx, [rbp+nNumberOfBytesToWrite]
0x18006723d  mov     rcx, r15
0x180067240  mov     rax, [rax+28h]
0x180067244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067249  mov     rax, [r15]
0x18006724c  lea     rdx, [rbp+var_28]
0x180067250  mov     rcx, r15
0x180067253  mov     rax, [rax+18h]
0x180067257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006725c  mov     rax, [r15]
0x18006725f  lea     rdx, [rbp+arg_10]
0x180067263  mov     rcx, r15
0x180067266  mov     rax, [rax+20h]
0x18006726a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006726f  lea     rcx, [rsi+50h]; this
0x180067273  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180067278  cmp     [rsi+60h], edi
0x18006727b  jnz     loc_180067312
0x180067281  mov     eax, cs:CallbackContext
0x180067287  mov     ebx, 80004005h
0x18006728c  cmp     eax, 2
0x18006728f  jbe     loc_1800675A7
0x180067295  lea     rax, aSendbufferStre; "SendBuffer: Stream closed"
0x18006729c  mov     [rbp+arg_18], 1DAh
0x1800672a3  mov     [rbp+var_20], rax
0x1800672a7  lea     rdx, byte_1801C6F9B
0x1800672ae  lea     rax, aWritebuffer; "WriteBuffer"
0x1800672b5  mov     [rbp+var_30], ebx
0x1800672b8  mov     [rbp+var_18], rax
0x1800672bc  lea     rax, aOnecoreTermsrv_74; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800672c3  mov     [rbp+var_10], rax
0x1800672c7  lea     rax, aErrorCondition; "Error condition failed"
0x1800672ce  mov     [rbp+var_8], rax
0x1800672d2  lea     rax, [rbp+var_20]
0x1800672d6  mov     [rsp+80h+var_38], rax
0x1800672db  lea     rax, [rbp+var_18]
0x1800672df  mov     [rsp+80h+var_40], rax
0x1800672e4  lea     rax, [rbp+arg_18]
0x1800672e8  mov     [rsp+80h+var_48], rax
0x1800672ed  lea     rax, [rbp+var_10]
0x1800672f1  mov     [rsp+80h+var_50], rax
0x1800672f6  lea     rax, [rbp+var_30]
0x1800672fa  mov     [rsp+80h+var_58], rax
0x1800672ff  lea     rax, [rbp+var_8]
0x180067303  mov     [rsp+80h+lpOverlapped], rax
0x180067308  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18006730d  jmp     loc_1800675A7
0x180067312  mov     ecx, [rbp+arg_0]
0x180067315  add     ecx, [rbp+nNumberOfBytesToWrite]
0x180067318  cmp     ecx, [rbp+arg_10]
0x18006731b  jle     short loc_18006739A
0x18006731d  mov     eax, cs:CallbackContext
0x180067323  mov     ebx, 80070057h
0x180067328  cmp     eax, 2
0x18006732b  jbe     loc_1800675A7
0x180067331  lea     rax, aWritebuffer; "WriteBuffer"
0x180067338  mov     [rbp+arg_18], 1DEh
0x18006733f  mov     [rbp+var_8], rax
0x180067343  lea     rdx, byte_1801C6FE9
0x18006734a  lea     rax, aOnecoreTermsrv_74; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180067351  mov     [rbp+var_10], rax
0x180067355  lea     rax, aBufferOverflow; "Buffer overflow detected"
0x18006735c  mov     [rbp+var_18], rax
0x180067360  lea     rax, [rbp+var_8]
0x180067364  mov     [rsp+80h+var_40], rax
0x180067369  lea     rax, [rbp+arg_18]
0x18006736d  mov     [rsp+80h+var_48], rax
0x180067372  lea     rax, [rbp+var_10]
0x180067376  mov     [rsp+80h+var_50], rax
0x18006737b  lea     rax, [rbp+var_30]
0x18006737f  mov     [rsp+80h+var_58], rax
0x180067384  lea     rax, [rbp+var_18]
0x180067388  mov     [rsp+80h+lpOverlapped], rax
0x18006738d  mov     [rbp+var_30], ebx
0x180067390  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180067395  jmp     loc_1800675A7
0x18006739a  mov     eax, [rsi+68h]
0x18006739d  cmp     eax, 3E8h
0x1800673a2  jbe     short loc_1800673F8
0x1800673a4  mov     rax, [rsi+70h]
0x1800673a8  sub     rbx, rax
0x1800673ab  cmp     rbx, 0EA60h
0x1800673b2  jbe     short loc_1800673F8
0x1800673b4  mov     eax, cs:CallbackContext
0x1800673ba  mov     ebx, 8007274Ch
0x1800673bf  cmp     eax, 2
0x1800673c2  jbe     loc_1800675A7
0x1800673c8  lea     rax, aWritebuffer; "WriteBuffer"
0x1800673cf  mov     [rbp+arg_18], 1EFh
0x1800673d6  mov     [rbp+var_8], rax
0x1800673da  lea     rdx, byte_1801C6F07
0x1800673e1  lea     rax, aOnecoreTermsrv_74; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800673e8  mov     [rbp+var_10], rax
0x1800673ec  lea     rax, aTooManyPending; "Too many pending writes to a named pipe"...
0x1800673f3  jmp     loc_18006735C
0x1800673f8  mov     eax, [rsi+68h]
0x1800673fb  mov     ebx, 1
0x180067400  add     eax, ebx
0x180067402  mov     [rsi+68h], eax
0x180067405  lea     ecx, [rbx+37h]; Size
0x180067408  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006740d  mov     rdi, rax
0x180067410  test    rax, rax
0x180067413  jz      loc_18006751D
0x180067419  mov     qword ptr [rax+28h], 0
0x180067421  lea     r14, [rdi+28h]
0x180067425  mov     qword ptr [rax+30h], 0
0x18006742d  xorps   xmm0, xmm0
0x180067430  movups  xmmword ptr [rdi], xmm0
0x180067433  xor     eax, eax
0x180067435  movups  xmmword ptr [rdi+10h], xmm0
0x180067439  movups  xmmword ptr [rdi+20h], xmm0
0x18006743d  mov     [rdi+30h], rax
0x180067441  cmp     rsi, [r14]
0x180067444  jz      short loc_180067459
0x180067446  mov     rcx, r14
0x180067449  call    ?SafeRelease@?$TCntPtr@VCTSCoreEventSource@@@@AEAAXXZ; TCntPtr<CTSCoreEventSource>::SafeRelease(void)
0x18006744e  mov     rcx, r14
0x180067451  mov     [r14], rsi
0x180067454  call    ?SafeAddRef@?$TCntPtr@VCNamedPipeStream@@@@AEAAXXZ; TCntPtr<CNamedPipeStream>::SafeAddRef(void)
0x180067459  lea     r14, [rdi+30h]
0x18006745d  cmp     r15, [r14]
0x180067460  jz      short loc_180067475
0x180067462  mov     rcx, r14; void *
0x180067465  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18006746a  mov     rcx, r14
0x18006746d  mov     [r14], r15
0x180067470  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x180067475  mov     rcx, rsi; this
0x180067478  call    ?StartThreadpoolIo@CNamedPipeStream@@AEAAXXZ; CNamedPipeStream::StartThreadpoolIo(void)
0x18006747d  movsxd  rdx, [rbp+arg_0]
0x180067481  xor     r9d, r9d; lpNumberOfBytesWritten
0x180067484  add     rdx, [rbp+var_28]; lpBuffer
0x180067488  mov     r8d, [rbp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18006748c  mov     rcx, [rsi+38h]; hFile
0x180067490  mov     [rsp+80h+lpOverlapped], rdi; lpOverlapped
0x180067495  call    cs:__imp_WriteFile
0x18006749b  test    eax, eax
0x18006749d  jnz     short loc_180067516
0x18006749f  call    cs:__imp_GetLastError
0x1800674a5  mov     r14d, eax
0x1800674a8  cmp     eax, 3E5h
0x1800674ad  jz      loc_1800675A7
0x1800674b3  mov     eax, [rsi+68h]
0x1800674b6  mov     rcx, rsi; this
0x1800674b9  sub     eax, ebx
0x1800674bb  mov     [rsi+68h], eax
0x1800674be  call    ?CancelThreadpoolIo@CNamedPipeStream@@AEAAXXZ; CNamedPipeStream::CancelThreadpoolIo(void)
0x1800674c3  test    r14d, r14d
0x1800674c6  jg      short loc_1800674CD
0x1800674c8  mov     ebx, r14d
0x1800674cb  jmp     short loc_1800674D7
0x1800674cd  movzx   ebx, r14w
0x1800674d1  or      ebx, 80070000h
0x1800674d7  mov     eax, cs:CallbackContext
0x1800674dd  cmp     eax, 2
0x1800674e0  jbe     loc_1800675A7
0x1800674e6  lea     rax, aWritebuffer; "WriteBuffer"
0x1800674ed  mov     [rbp+arg_18], 21Dh
0x1800674f4  mov     [rbp+var_8], rax
0x1800674f8  lea     rdx, byte_1801C6E85
0x1800674ff  lea     rax, aOnecoreTermsrv_74; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180067506  mov     [rbp+var_10], rax
0x18006750a  lea     rax, aFailedToPostAS; "Failed to post a send. Disconnecting st"...
0x180067511  jmp     loc_18006735C
0x180067516  xor     ebx, ebx
0x180067518  jmp     loc_1800675A7
0x18006751d  mov     eax, cs:CallbackContext
0x180067523  mov     ebx, 8007000Eh
0x180067528  cmp     eax, 2
0x18006752b  jbe     short loc_1800675A5
0x18006752d  lea     rax, aNpOverlappedCo; "NP_OVERLAPPED_CONTEXT allocation failed"
0x180067534  mov     [rbp+arg_18], 1FDh
0x18006753b  mov     [rbp+var_8], rax
0x18006753f  lea     rdx, byte_1801C6F4D
0x180067546  lea     rax, aWritebuffer; "WriteBuffer"
0x18006754d  mov     [rbp+var_30], ebx
0x180067550  mov     [rbp+var_10], rax
0x180067554  lea     rax, aOnecoreTermsrv_74; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18006755b  mov     [rbp+var_18], rax
0x18006755f  lea     rax, aErrorCondition; "Error condition failed"
0x180067566  mov     [rbp+var_20], rax
0x18006756a  lea     rax, [rbp+var_8]
0x18006756e  mov     [rsp+80h+var_38], rax
0x180067573  lea     rax, [rbp+var_10]
0x180067577  mov     [rsp+80h+var_40], rax
0x18006757c  lea     rax, [rbp+arg_18]
0x180067580  mov     [rsp+80h+var_48], rax
0x180067585  lea     rax, [rbp+var_18]
0x180067589  mov     [rsp+80h+var_50], rax
0x18006758e  lea     rax, [rbp+var_30]
0x180067592  mov     [rsp+80h+var_58], rax
0x180067597  lea     rax, [rbp+var_20]
0x18006759b  mov     [rsp+80h+lpOverlapped], rax
0x1800675a0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800675a5  xor     edi, edi
0x1800675a7  lea     rcx, [rsi+50h]; this
0x1800675ab  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x1800675b0  test    ebx, ebx
0x1800675b2  jns     short loc_1800675CB
0x1800675b4  mov     edx, ebx; int
0x1800675b6  mov     rcx, rsi; pv
0x1800675b9  call    ?CloseStream@CNamedPipeStream@@AEAAJJ@Z; CNamedPipeStream::CloseStream(long)
0x1800675be  test    rdi, rdi
0x1800675c1  jz      short loc_1800675CB
0x1800675c3  mov     rcx, rdi; this
0x1800675c6  call    ??_GNP_OVERLAPPED_CONTEXT@CNamedPipeStream@@QEAAPEAXI@Z; CNamedPipeStream::NP_OVERLAPPED_CONTEXT::`scalar deleting destructor'(uint)
0x1800675cb  mov     eax, ebx
0x1800675cd  add     rsp, 80h
0x1800675d4  pop     r15
0x1800675d6  pop     r14
0x1800675d8  pop     r12
0x1800675da  pop     rdi
0x1800675db  pop     rsi
0x1800675dc  pop     rbx
0x1800675dd  pop     rbp
0x1800675de  retn
```
