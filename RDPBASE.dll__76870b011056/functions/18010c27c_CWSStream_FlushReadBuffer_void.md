# CWSStream::FlushReadBuffer(void)

- ea: `0x18010c27c`
- end: `0x18010c616`
- name: `?FlushReadBuffer@CWSStream@@AEAAJXZ`
- size: `922`
- prototype: `__int64 __fastcall(CWSStream *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18010ddb0`
- `0x18010f5d0`

## callees

- `0x1800018a4`
- `0x180001aa0`
- `0x18001b3f8`
- `0x18002058c`
- `0x180040750`
- `0x180078c20`
- `0x180108d8c`
- `0x18010c27c`
- `0x18010fa20`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010c2cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18010c2cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010c313`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010c5e0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010c313`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18010c5e0`

## string_xrefs

- `0x18010c397`: `ReadBuffer: Stream closed`
- `0x18010c433`: `ReadBuffer: Stream closed`
- `0x18010c56a`: `pStream->IoReadDataAsync failed`
- `0x18010c3b0`: `FlushReadBuffer`
- `0x18010c44c`: `FlushReadBuffer`
- `0x18010c4cb`: `FlushReadBuffer`
- `0x18010c583`: `FlushReadBuffer`

## pseudocode

```c
__int64 __fastcall CWSStream::FlushReadBuffer(CWSStream *this)
{
  int v2; // ebx
  _QWORD *v3; // r14
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  int v7; // r8d
  int v8; // r9d
  int v10; // [rsp+50h] [rbp-49h] BYREF
  int v11; // [rsp+54h] [rbp-45h] BYREF
  const char *v12; // [rsp+58h] [rbp-41h] BYREF
  const char *v13; // [rsp+60h] [rbp-39h] BYREF
  const char *v14; // [rsp+68h] [rbp-31h] BYREF
  int v15; // [rsp+70h] [rbp-29h] BYREF
  int v16; // [rsp+74h] [rbp-25h] BYREF
  int v17; // [rsp+78h] [rbp-21h] BYREF
  const char *v18; // [rsp+80h] [rbp-19h] BYREF
  int v19; // [rsp+88h] [rbp-11h] BYREF
  __int64 v20; // [rsp+90h] [rbp-9h] BYREF
  __int64 v21; // [rsp+98h] [rbp-1h] BYREF
  GUID ActivityId; // [rsp+A0h] [rbp+7h] BYREF

  CAutoSetThreadActivityId::CAutoSetThreadActivityId(&ActivityId, (const struct _GUID *)((char *)this + 1148));
  v2 = 0;
  v21 = 0;
  v16 = 0;
  v15 = 0;
  v19 = 0;
  v17 = 0;
  v20 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 2);
  v3 = (_QWORD *)((char *)this + 1104);
  if ( *((_QWORD *)this + 138) || !*((_DWORD *)this + 274) )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 2);
  }
  else
  {
    RdpXSPtr<RdpXInterfaceHttpConnection>::operator=(&v20, (char *)this + 1288);
    CComPtrList<IRDPENCNetStreamBuffer,ComPlainSmartPtr<IRDPENCNetStreamBuffer>>::RemoveHead(
      (char *)this + 656,
      (char *)this + 1104);
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 2);
    (*(void (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v3 + 56LL))(*v3, &v15);
    (*(void (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v3 + 40LL))(*v3, &v16);
    (*(void (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v3 + 32LL))(*v3, &v17);
    (*(void (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v3 + 24LL))(*v3, &v21);
    (*(void (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v3 + 72LL))(*v3, &v19);
    if ( *((_DWORD *)this + 30) )
    {
      if ( *((_DWORD *)this + 31) )
      {
        if ( v15 + v16 <= v17 )
        {
          if ( !*((_QWORD *)this + 162) )
          {
            v2 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 40LL))(v20, v21 + v15);
            if ( v2 < 0 && (unsigned int)CallbackContext > 2 )
            {
              v11 = 1656;
              v14 = "pStream->IoReadDataAsync failed";
              v10 = v2;
              v13 = "FlushReadBuffer";
              v12 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
              v18 = "Error HResult failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                (_DWORD)CallbackContext,
                (unsigned int)byte_1801C8A25,
                v7,
                v8,
                (__int64)&v18,
                (__int64)&v10,
                (__int64)&v12,
                (__int64)&v11,
                (__int64)&v13,
                (__int64)&v14);
            }
          }
        }
        else
        {
          v2 = -2147024809;
          if ( (unsigned int)CallbackContext > 2 )
          {
            v11 = 1640;
            v14 = "FlushReadBuffer";
            v10 = -2147024809;
            v13 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
            v12 = "Buffer overflow detected";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v4,
              (unsigned int)&dword_1801C89DC,
              v16,
              v6,
              (__int64)&v12,
              (__int64)&v10,
              (__int64)&v13,
              (__int64)&v11,
              (__int64)&v14);
          }
        }
      }
      else
      {
        v2 = -2147467259;
        if ( (unsigned int)CallbackContext > 2 )
        {
          v11 = 1636;
          v14 = "ReadBuffer: Stream closed";
          v10 = -2147467259;
          v13 = "FlushReadBuffer";
          v12 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
          v18 = "Error condition failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            -2147467259,
            (unsigned int)&byte_1801C8AC7,
            v5,
            v6,
            (__int64)&v18,
            (__int64)&v10,
            (__int64)&v12,
            (__int64)&v11,
            (__int64)&v13,
            (__int64)&v14);
        }
      }
    }
    else
    {
      v2 = -2147467259;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v10 = 1635;
        v18 = "ReadBuffer: Stream closed";
        v11 = -2147467259;
        v12 = "FlushReadBuffer";
        v13 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\websocketstream\\websocketstream.cpp";
        v14 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          -2147467259,
          (unsigned int)&word_1801C8A76,
          v5,
          v6,
          (__int64)&v14,
          (__int64)&v11,
          (__int64)&v13,
          (__int64)&v10,
          (__int64)&v12,
          (__int64)&v18);
      }
    }
  }
  RdpXSPtr<RdpXInterfaceHttpRequest>::SafeRelease(&v20);
  CAutoSetThreadActivityId::~CAutoSetThreadActivityId(&ActivityId);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18010c27c  push    rbp
0x18010c27e  push    rbx
0x18010c27f  push    rsi
0x18010c280  push    rdi
0x18010c281  push    r14
0x18010c283  push    r15
0x18010c285  lea     rbp, [rsp-2Fh]
0x18010c28a  sub     rsp, 0C8h
0x18010c291  mov     rax, cs:__security_cookie
0x18010c298  xor     rax, rsp
0x18010c29b  mov     [rbp+57h+var_40], rax
0x18010c29f  mov     rdi, rcx
0x18010c2a2  lea     rdx, [rcx+47Ch]; struct _GUID *
0x18010c2a9  lea     rcx, [rbp+57h+ActivityId]; ActivityId
0x18010c2ad  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x18010c2b2  xor     ebx, ebx
0x18010c2b4  lea     rsi, [rdi+50h]
0x18010c2b8  mov     rcx, rsi; lpCriticalSection
0x18010c2bb  mov     [rbp+57h+var_58], rbx
0x18010c2bf  mov     [rbp+57h+var_7C], ebx
0x18010c2c2  mov     [rbp+57h+var_80], ebx
0x18010c2c5  mov     [rbp+57h+var_68], ebx
0x18010c2c8  mov     [rbp+57h+var_78], ebx
0x18010c2cb  mov     [rbp+57h+var_60], rbx
0x18010c2cf  call    cs:__imp_EnterCriticalSection
0x18010c2d5  lea     r14, [rdi+450h]
0x18010c2dc  cmp     [r14], rbx
0x18010c2df  jnz     loc_18010C5DD
0x18010c2e5  cmp     [rdi+448h], ebx
0x18010c2eb  jz      loc_18010C5DD
0x18010c2f1  lea     rdx, [rdi+508h]
0x18010c2f8  lea     rcx, [rbp+57h+var_60]
0x18010c2fc  call    ??4?$RdpXSPtr@URdpXInterfaceHttpConnection@@@@QEAAPEAURdpXInterfaceHttpConnection@@AEBV0@@Z; RdpXSPtr<RdpXInterfaceHttpConnection>::operator=(RdpXSPtr<RdpXInterfaceHttpConnection> const &)
0x18010c301  mov     rdx, r14
0x18010c304  lea     rcx, [rdi+290h]
0x18010c30b  call    ?RemoveHead@?$CComPtrList@UIRDPENCNetStreamBuffer@@V?$ComPlainSmartPtr@UIRDPENCNetStreamBuffer@@@@@@QEAAHAEAV?$ComPlainSmartPtr@UIRDPENCNetStreamBuffer@@@@@Z; CComPtrList<IRDPENCNetStreamBuffer,ComPlainSmartPtr<IRDPENCNetStreamBuffer>>::RemoveHead(ComPlainSmartPtr<IRDPENCNetStreamBuffer> &)
0x18010c310  mov     rcx, rsi; lpCriticalSection
0x18010c313  call    cs:__imp_LeaveCriticalSection
0x18010c319  mov     rcx, [r14]
0x18010c31c  lea     rdx, [rbp+57h+var_80]
0x18010c320  mov     rax, [rcx]
0x18010c323  mov     rax, [rax+38h]
0x18010c327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c32c  mov     rcx, [r14]
0x18010c32f  lea     rdx, [rbp+57h+var_7C]
0x18010c333  mov     rax, [rcx]
0x18010c336  mov     rax, [rax+28h]
0x18010c33a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c33f  mov     rcx, [r14]
0x18010c342  lea     rdx, [rbp+57h+var_78]
0x18010c346  mov     rax, [rcx]
0x18010c349  mov     rax, [rax+20h]
0x18010c34d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c352  mov     rcx, [r14]
0x18010c355  lea     rdx, [rbp+57h+var_58]
0x18010c359  mov     rax, [rcx]
0x18010c35c  mov     rax, [rax+18h]
0x18010c360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c365  mov     rcx, [r14]
0x18010c368  lea     rdx, [rbp+57h+var_68]
0x18010c36c  mov     rax, [rcx]
0x18010c36f  mov     rax, [rax+48h]
0x18010c373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c378  cmp     [rdi+78h], ebx
0x18010c37b  jnz     loc_18010C414
0x18010c381  mov     eax, cs:CallbackContext
0x18010c387  mov     ecx, 80004005h
0x18010c38c  mov     ebx, ecx
0x18010c38e  cmp     eax, 2
0x18010c391  jbe     loc_18010C5E6
0x18010c397  lea     rax, aReadbufferStre; "ReadBuffer: Stream closed"
0x18010c39e  mov     [rbp+57h+var_A0], 663h
0x18010c3a5  mov     [rbp+57h+var_70], rax
0x18010c3a9  lea     rdx, word_1801C8A76
0x18010c3b0  lea     rax, aFlushreadbuffe_0; "FlushReadBuffer"
0x18010c3b7  mov     [rbp+57h+var_9C], ecx
0x18010c3ba  mov     [rbp+57h+var_98], rax
0x18010c3be  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010c3c5  mov     [rbp+57h+var_90], rax
0x18010c3c9  lea     rax, aErrorCondition; "Error condition failed"
0x18010c3d0  mov     [rbp+57h+var_88], rax
0x18010c3d4  lea     rax, [rbp+57h+var_70]
0x18010c3d8  mov     [rsp+0F0h+var_A8], rax
0x18010c3dd  lea     rax, [rbp+57h+var_98]
0x18010c3e1  mov     [rsp+0F0h+var_B0], rax
0x18010c3e6  lea     rax, [rbp+57h+var_A0]
0x18010c3ea  mov     [rsp+0F0h+var_B8], rax
0x18010c3ef  lea     rax, [rbp+57h+var_90]
0x18010c3f3  mov     [rsp+0F0h+var_C0], rax
0x18010c3f8  lea     rax, [rbp+57h+var_9C]
0x18010c3fc  mov     [rsp+0F0h+var_C8], rax
0x18010c401  lea     rax, [rbp+57h+var_88]
0x18010c405  mov     [rsp+0F0h+var_D0], rax
0x18010c40a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18010c40f  jmp     loc_18010C5E6
0x18010c414  cmp     [rdi+7Ch], ebx
0x18010c417  jnz     loc_18010C4A6
0x18010c41d  mov     eax, cs:CallbackContext
0x18010c423  mov     ecx, 80004005h
0x18010c428  mov     ebx, ecx
0x18010c42a  cmp     eax, 2
0x18010c42d  jbe     loc_18010C5E6
0x18010c433  lea     rax, aReadbufferStre; "ReadBuffer: Stream closed"
0x18010c43a  mov     [rbp+57h+var_9C], 664h
0x18010c441  mov     [rbp+57h+var_88], rax
0x18010c445  lea     rdx, byte_1801C8AC7
0x18010c44c  lea     rax, aFlushreadbuffe_0; "FlushReadBuffer"
0x18010c453  mov     [rbp+57h+var_A0], ecx
0x18010c456  mov     [rbp+57h+var_90], rax
0x18010c45a  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010c461  mov     [rbp+57h+var_98], rax
0x18010c465  lea     rax, aErrorCondition; "Error condition failed"
0x18010c46c  mov     [rbp+57h+var_70], rax
0x18010c470  lea     rax, [rbp+57h+var_88]
0x18010c474  mov     [rsp+0F0h+var_A8], rax
0x18010c479  lea     rax, [rbp+57h+var_90]
0x18010c47d  mov     [rsp+0F0h+var_B0], rax
0x18010c482  lea     rax, [rbp+57h+var_9C]
0x18010c486  mov     [rsp+0F0h+var_B8], rax
0x18010c48b  lea     rax, [rbp+57h+var_98]
0x18010c48f  mov     [rsp+0F0h+var_C0], rax
0x18010c494  lea     rax, [rbp+57h+var_A0]
0x18010c498  mov     [rsp+0F0h+var_C8], rax
0x18010c49d  lea     rax, [rbp+57h+var_70]
0x18010c4a1  jmp     loc_18010C405
0x18010c4a6  movsxd  rdx, [rbp+57h+var_80]
0x18010c4aa  mov     r8d, [rbp+57h+var_7C]
0x18010c4ae  lea     eax, [rdx+r8]
0x18010c4b2  cmp     eax, [rbp+57h+var_78]
0x18010c4b5  jle     short loc_18010C534
0x18010c4b7  mov     eax, cs:CallbackContext
0x18010c4bd  mov     ebx, 80070057h
0x18010c4c2  cmp     eax, 2
0x18010c4c5  jbe     loc_18010C5E6
0x18010c4cb  lea     rax, aFlushreadbuffe_0; "FlushReadBuffer"
0x18010c4d2  mov     [rbp+57h+var_9C], 668h
0x18010c4d9  mov     [rbp+57h+var_88], rax
0x18010c4dd  lea     rdx, dword_1801C89DC
0x18010c4e4  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010c4eb  mov     [rbp+57h+var_A0], ebx
0x18010c4ee  mov     [rbp+57h+var_90], rax
0x18010c4f2  lea     rax, aBufferOverflow; "Buffer overflow detected"
0x18010c4f9  mov     [rbp+57h+var_98], rax
0x18010c4fd  lea     rax, [rbp+57h+var_88]
0x18010c501  mov     [rsp+0F0h+var_B0], rax
0x18010c506  lea     rax, [rbp+57h+var_9C]
0x18010c50a  mov     [rsp+0F0h+var_B8], rax
0x18010c50f  lea     rax, [rbp+57h+var_90]
0x18010c513  mov     [rsp+0F0h+var_C0], rax
0x18010c518  lea     rax, [rbp+57h+var_A0]
0x18010c51c  mov     [rsp+0F0h+var_C8], rax
0x18010c521  lea     rax, [rbp+57h+var_98]
0x18010c525  mov     [rsp+0F0h+var_D0], rax
0x18010c52a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18010c52f  jmp     loc_18010C5E6
0x18010c534  cmp     [rdi+510h], rbx
0x18010c53b  jnz     loc_18010C5E6
0x18010c541  mov     rcx, [rbp+57h+var_60]
0x18010c545  add     rdx, [rbp+57h+var_58]
0x18010c549  mov     rax, [rcx]
0x18010c54c  mov     rax, [rax+28h]
0x18010c550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010c555  mov     ebx, eax
0x18010c557  test    eax, eax
0x18010c559  jns     loc_18010C5E6
0x18010c55f  mov     ecx, cs:CallbackContext
0x18010c565  cmp     ecx, 2
0x18010c568  jbe     short loc_18010C5E6
0x18010c56a  lea     rax, aPstreamIoreadd; "pStream->IoReadDataAsync failed"
0x18010c571  mov     [rbp+57h+var_9C], 678h
0x18010c578  mov     [rbp+57h+var_88], rax
0x18010c57c  lea     rdx, byte_1801C8A25
0x18010c583  lea     rax, aFlushreadbuffe_0; "FlushReadBuffer"
0x18010c58a  mov     [rbp+57h+var_A0], ebx
0x18010c58d  mov     [rbp+57h+var_90], rax
0x18010c591  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18010c598  mov     [rbp+57h+var_98], rax
0x18010c59c  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18010c5a3  mov     [rbp+57h+var_70], rax
0x18010c5a7  lea     rax, [rbp+57h+var_88]
0x18010c5ab  mov     [rsp+0F0h+var_A8], rax
0x18010c5b0  lea     rax, [rbp+57h+var_90]
0x18010c5b4  mov     [rsp+0F0h+var_B0], rax
0x18010c5b9  lea     rax, [rbp+57h+var_9C]
0x18010c5bd  mov     [rsp+0F0h+var_B8], rax
0x18010c5c2  lea     rax, [rbp+57h+var_98]
0x18010c5c6  mov     [rsp+0F0h+var_C0], rax
0x18010c5cb  lea     rax, [rbp+57h+var_A0]
0x18010c5cf  mov     [rsp+0F0h+var_C8], rax
0x18010c5d4  lea     rax, [rbp+57h+var_70]
0x18010c5d8  jmp     loc_18010C405
0x18010c5dd  mov     rcx, rsi; lpCriticalSection
0x18010c5e0  call    cs:__imp_LeaveCriticalSection
0x18010c5e6  lea     rcx, [rbp+57h+var_60]
0x18010c5ea  call    ?SafeRelease@?$RdpXSPtr@URdpXInterfaceHttpRequest@@@@AEAAXXZ; RdpXSPtr<RdpXInterfaceHttpRequest>::SafeRelease(void)
0x18010c5ef  lea     rcx, [rbp+57h+ActivityId]; ActivityId
0x18010c5f3  call    ??1CAutoSetThreadActivityId@@QEAA@XZ; CAutoSetThreadActivityId::~CAutoSetThreadActivityId(void)
0x18010c5f8  mov     eax, ebx
0x18010c5fa  mov     rcx, [rbp+57h+var_40]
0x18010c5fe  xor     rcx, rsp; StackCookie
0x18010c601  call    __security_check_cookie
0x18010c606  add     rsp, 0C8h
0x18010c60d  pop     r15
0x18010c60f  pop     r14
0x18010c611  pop     rdi
0x18010c612  pop     rsi
0x18010c613  pop     rbx
0x18010c614  pop     rbp
0x18010c615  retn
```
