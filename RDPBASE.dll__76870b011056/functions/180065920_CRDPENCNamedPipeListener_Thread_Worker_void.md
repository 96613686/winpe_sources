# CRDPENCNamedPipeListener::Thread_Worker(void)

- ea: `0x180065920`
- end: `0x180066103`
- name: `?Thread_Worker@CRDPENCNamedPipeListener@@IEAAXXZ`
- size: `2019`
- prototype: `void __fastcall(CRDPENCNamedPipeListener *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801019f0`

## callees

- `0x1800018a4`
- `0x180001aa0`
- `0x1800025dc`
- `0x180003c38`
- `0x180004a94`
- `0x180005090`
- `0x18000552c`
- `0x180019a80`
- `0x180019ab0`
- `0x18001b3f8`
- `0x1800648e4`
- `0x1800652a0`
- `0x180065920`
- `0x180078820`
- `0x180078c20`
- `0x180101334`
- `0x180162010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180065986`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180065986`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065a77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065b34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065a77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065b34`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800660bf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800660bf`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180065a69`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180065a69`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180065b26`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180065b26`

## string_xrefs

- `0x1800659f6`: `Thread_Worker`
- `0x180065aad`: `Thread_Worker`
- `0x180065b6a`: `Thread_Worker`
- `0x180065d1b`: `Thread_Worker`
- `0x180065ecd`: `Thread_Worker`
- `0x180065eea`: `Thread_Worker`
- `0x180065a10`: `Failed to build named pipe ACL`
- `0x180065b58`: `Failed to SetSecurityDescriptorDacl`
- `0x180065a9b`: `Failed to InitializeSecurityDescriptor`
- `0x180065dc0`: `Pipe got broken during establishing named pipe connection. Continuing with the pipe listening loop.`
- `0x180065f82`: `The Named Pipe Listener thread received E_TSC_QUIT`
- `0x180065f07`: `Abnormal wait termination for the Named Pipe Listener thread`
- `0x180065fb0`: `The Named Pipe Listener thread is exiting`

## pseudocode

```c
void __fastcall CRDPENCNamedPipeListener::Thread_Worker(CRDPENCNamedPipeListener *this)
{
  struct ITSThread *v1; // rbx
  int v3; // r14d
  __int64 v4; // rdi
  int v5; // r9d
  unsigned __int64 v6; // rdx
  void **v7; // rcx
  int v8; // edi
  int v9; // r8d
  int v10; // r9d
  const char *v11; // rcx
  signed int LastError; // eax
  int v13; // r8d
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  signed int v17; // eax
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v21; // eax
  int *v22; // rdx
  const char *v23; // rax
  char *v24; // rdx
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  void *v28; // rcx
  __int64 v29; // [rsp+50h] [rbp-79h] BYREF
  const char *v30; // [rsp+58h] [rbp-71h] BYREF
  const char *v31; // [rsp+60h] [rbp-69h] BYREF
  const char *v32; // [rsp+68h] [rbp-61h] BYREF
  int v33; // [rsp+70h] [rbp-59h] BYREF
  const char *v34; // [rsp+78h] [rbp-51h] BYREF
  const char *v35; // [rsp+80h] [rbp-49h] BYREF
  PACL pDacl; // [rsp+88h] [rbp-41h] BYREF
  __int64 v37; // [rsp+90h] [rbp-39h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+98h] [rbp-31h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v40; // [rsp+D0h] [rbp+7h]
  GUID ActivityId; // [rsp+D8h] [rbp+Fh] BYREF

  v40 = 0;
  v1 = 0;
  pDacl = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  v3 = 0;
  v37 = 0;
  v33 = 0;
  ActivityId = *(GUID *)"wwwwwwwwwwwwwwwwFailed to Initialize";
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  EventActivityIdControl(4u, &ActivityId);
  v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 12) + 64LL))(*((_QWORD *)this + 12));
  if ( v4 )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease(&v37);
    v1 = (struct ITSThread *)v4;
    v37 = v4;
    TCntPtr<ITSAsyncCallback>::SafeAddRef(&v37);
  }
  v6 = *((_QWORD *)this + 85);
  v7 = (void **)*((_QWORD *)this + 84);
  SecurityAttributes.lpSecurityDescriptor = pSecurityDescriptor;
  SecurityAttributes.bInheritHandle = 1;
  SecurityAttributes.nLength = 24;
  v8 = BuildNamedPipeAcl(v7, v6, &pDacl, v5);
  v11 = "Thread_Worker";
  if ( v8 >= 0 )
  {
    if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v33 = 448;
        v35 = "Failed to InitializeSecurityDescriptor";
        v29 = (__int64)"Thread_Worker";
        v32 = "Error condition failed";
        v31 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
        LODWORD(v30) = v8;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)v11,
          (unsigned int)&unk_1801C6138,
          v13,
          v10,
          (__int64)&v32,
          (__int64)&v30,
          (__int64)&v31,
          (__int64)&v33,
          (__int64)&v29,
          (__int64)&v35);
      }
      goto LABEL_43;
    }
    if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0) )
    {
      v17 = GetLastError();
      v8 = v17;
      if ( v17 > 0 )
        v8 = (unsigned __int16)v17 | 0x80070000;
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v30) = 451;
        v32 = "Failed to SetSecurityDescriptorDacl";
        v31 = "Thread_Worker";
        v29 = (__int64)"Error condition failed";
        v35 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
        v33 = v8;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)v11,
          (unsigned int)word_1801C618A,
          v13,
          v10,
          (__int64)&v29,
          (__int64)&v33,
          (__int64)&v35,
          (__int64)&v30,
          (__int64)&v31,
          (__int64)&v32);
      }
LABEL_43:
      if ( v8 >= 0 )
      {
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_55;
        v34 = "Thread_Worker";
        v23 = "The Named Pipe Listener thread is exiting";
        LODWORD(v29) = 516;
        v24 = byte_1801C5DFB;
        v32 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
        LODWORD(v30) = v8;
        goto LABEL_54;
      }
      goto LABEL_44;
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      v32 = (char *)this + 152;
      v31 = "Starting named pipe listen";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v14,
        (unsigned int)&unk_1801C6098,
        v15,
        v16,
        (__int64)&v31,
        (__int64)&v32);
    }
    if ( (unsigned int)CallbackContext > 4 && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL) )
    {
      v30 = (const char *)0x1000000;
      v32 = (char *)this + 152;
      v31 = "wwwwwwwwwwwwwwwwFailed to Initialize";
      v35 = "NamedPipe";
      v29 = (__int64)"Stack";
      v34 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>>(
        v18,
        (unsigned int)&unk_1801C60C8,
        v19,
        v20,
        (__int64)&v34,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v35,
        (__int64)&v31,
        (__int64)&v32);
    }
    while ( 1 )
    {
      v21 = CRDPENCNamedPipeListener::HandleSingleConnection(this, &SecurityAttributes, v1, &v33);
      LODWORD(v11) = 0x80000000;
      v8 = v21;
      if ( (int)(v21 + 0x80000000) >= 0 && v21 != -2092629996 )
      {
        if ( v21 == -2147024787 || v21 == -2147024890 || v21 == -2147024895 )
        {
          if ( (unsigned int)CallbackContext > 3 )
          {
            LODWORD(v29) = v21;
            v34 = "Pipe got broken during establishing named pipe connection. Continuing with the pipe listening loop.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              0x80000000,
              (unsigned int)byte_1801C5F45,
              v13,
              v10,
              (__int64)&v34,
              (__int64)&v29);
          }
          if ( (unsigned int)CallbackContext <= 4 || !(unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL) )
            goto LABEL_37;
          v22 = (int *)byte_1801C5F73;
        }
        else
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            LODWORD(v30) = 478;
            v34 = "Thread_Worker";
            LODWORD(v29) = v21;
            v32 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
            v31 = "Unexpected error while establishing named pipe connection. Aborting the named pipe listener.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              0x80000000,
              (unsigned int)word_1801C5FE2,
              v13,
              v10,
              (__int64)&v31,
              (__int64)&v29,
              (__int64)&v32,
              (__int64)&v30,
              (__int64)&v34);
          }
          if ( (unsigned int)CallbackContext <= 4 || !(unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL) )
            goto LABEL_37;
          v22 = &dword_1801C602C;
        }
        v29 = 0x1000000;
        v34 = (char *)this + 152;
        v32 = "wwwwwwwwwwwwwwwwFailed to Initialize";
        v31 = "NamedPipe";
        v35 = "Stack";
        v30 = "Checkpoint";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v11,
          (_DWORD)v22,
          v13,
          v10,
          (__int64)&v30,
          (__int64)&v29,
          (__int64)&v35,
          (__int64)&v31,
          (__int64)&v32,
          (__int64)&v34);
      }
LABEL_37:
      if ( *((_DWORD *)this + 167) || v8 < 0 && v8 != -2147024787 && v8 != -2147024890 && v8 != -2147024895 )
      {
        v3 = v33;
        goto LABEL_43;
      }
    }
  }
  if ( (unsigned int)CallbackContext <= 3 )
    goto LABEL_45;
  v29 = (__int64)"Thread_Worker";
  v30 = "Failed to build named pipe ACL";
  v33 = v8;
  v35 = "Warning HResult failed";
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
    (unsigned int)"Thread_Worker",
    (unsigned int)&dword_1801C61DC,
    v9,
    v10,
    (__int64)&v35,
    (__int64)&v30,
    (__int64)&v33,
    (__int64)&v29);
LABEL_44:
  v11 = "Thread_Worker";
LABEL_45:
  v13 = -2092629996;
  if ( v8 == -2092629996 )
  {
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_55;
    v32 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
    v23 = "The Named Pipe Listener thread received E_TSC_QUIT";
    v24 = byte_1801C5EFB;
    v34 = "Thread_Worker";
    LODWORD(v29) = 513;
    LODWORD(v30) = -2092629996;
LABEL_54:
    v31 = v23;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (_DWORD)v11,
      (_DWORD)v24,
      v13,
      v10,
      (__int64)&v31,
      (__int64)&v30,
      (__int64)&v32,
      (__int64)&v29,
      (__int64)&v34);
    goto LABEL_55;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    v32 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\rdpenccon\\rdpencnamedpipelistener.cpp";
    v31 = "Abnormal wait termination for the Named Pipe Listener thread";
    v34 = "Thread_Worker";
    LODWORD(v29) = 504;
    LODWORD(v30) = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (unsigned int)"Thread_Worker",
      (unsigned int)byte_1801C5EB1,
      -2092629996,
      v10,
      (__int64)&v31,
      (__int64)&v30,
      (__int64)&v32,
      (__int64)&v29,
      (__int64)&v34);
  }
  if ( v3 )
    CRDPENCNamedPipeListener::Decouple_OnConnectorError(this, v8);
LABEL_55:
  if ( (unsigned int)CallbackContext > 4 && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL) )
  {
    v29 = 0x1000000;
    v34 = (char *)this + 152;
    v32 = "wwwwwwwwwwwwwwwwFailed to Initialize";
    v31 = "NamedPipe";
    v35 = "Stack";
    v30 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>>(
      v25,
      (unsigned int)byte_1801C5E45,
      v26,
      v27,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&v35,
      (__int64)&v31,
      (__int64)&v32,
      (__int64)&v34);
  }
  if ( !v3 )
  {
    v28 = (void *)*((_QWORD *)this + 15);
    *((_DWORD *)this + 32) = v8;
    SetEvent(v28);
  }
  if ( pDacl )
    operator delete(pDacl);
  CAutoSetThreadActivityId::~CAutoSetThreadActivityId(&ActivityId);
  TCntPtr<IXMLDOMNodeList>::SafeRelease(&v37);
}

```

## disassembly

```asm
0x180065920  push    rbp
0x180065922  push    rbx
0x180065923  push    rsi
0x180065924  push    rdi
0x180065925  push    r12
0x180065927  push    r14
0x180065929  lea     rbp, [rsp-2Fh]
0x18006592e  sub     rsp, 0F8h
0x180065935  mov     rax, cs:__security_cookie
0x18006593c  xor     rax, rsp
0x18006593f  mov     [rbp+57h+var_38], rax
0x180065943  xor     eax, eax
0x180065945  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180065949  xorps   xmm0, xmm0
0x18006594c  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x180065950  xorps   xmm1, xmm1
0x180065953  mov     [rbp+57h+var_50], rax
0x180065957  xor     ebx, ebx
0x180065959  mov     [rbp+57h+pDacl], rax
0x18006595d  movups  xmmword ptr [rbp+57h+SecurityAttributes.nLength], xmm0
0x180065961  mov     rsi, rcx
0x180065964  xor     r14d, r14d
0x180065967  movups  xmm0, xmmword ptr cs:aWwwwwwwwwwwwww; "wwwwwwwwwwwwwwwwFailed to Initialize"
0x18006596e  lea     ecx, [rbx+4]; ControlCode
0x180065971  mov     [rbp+57h+var_90], rbx
0x180065975  mov     [rbp+57h+var_B0], r14d
0x180065979  movdqu  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x18006597e  movups  [rbp+57h+pSecurityDescriptor], xmm1
0x180065982  movups  [rbp+57h+var_60], xmm1
0x180065986  call    cs:__imp_EventActivityIdControl
0x18006598c  mov     rcx, [rsi+60h]
0x180065990  mov     rax, [rcx]
0x180065993  mov     rax, [rax+40h]
0x180065997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006599c  mov     rdi, rax
0x18006599f  test    rax, rax
0x1800659a2  jz      short loc_1800659BD
0x1800659a4  lea     rcx, [rbp+57h+var_90]; void *
0x1800659a8  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x1800659ad  mov     rbx, rdi
0x1800659b0  lea     rcx, [rbp+57h+var_90]
0x1800659b4  mov     [rbp+57h+var_90], rbx
0x1800659b8  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x1800659bd  mov     rdx, [rsi+2A8h]; unsigned __int64
0x1800659c4  lea     rax, [rbp+57h+pSecurityDescriptor]
0x1800659c8  mov     rcx, [rsi+2A0h]; void **
0x1800659cf  lea     r8, [rbp+57h+pDacl]; struct _ACL **
0x1800659d3  mov     r12d, 1
0x1800659d9  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800659dd  mov     [rbp+57h+SecurityAttributes.bInheritHandle], r12d
0x1800659e1  mov     [rbp+57h+SecurityAttributes.nLength], 18h
0x1800659e8  call    ?BuildNamedPipeAcl@@YAJPEAPEAX_KPEAPEAU_ACL@@@Z; BuildNamedPipeAcl(void * *,unsigned __int64,_ACL * *)
0x1800659ed  lea     rdx, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800659f4  mov     edi, eax
0x1800659f6  lea     rcx, aThreadWorker; "Thread_Worker"
0x1800659fd  test    eax, eax
0x1800659ff  jns     short loc_180065A62
0x180065a01  mov     eax, cs:CallbackContext
0x180065a07  cmp     eax, 3
0x180065a0a  jbe     loc_180065EF1
0x180065a10  lea     rax, aFailedToBuildN; "Failed to build named pipe ACL"
0x180065a17  mov     [rbp+57h+var_D0], rcx
0x180065a1b  mov     [rbp+57h+var_C8], rax
0x180065a1f  lea     rdx, dword_1801C61DC
0x180065a26  lea     rax, aWarningHresult; "Warning HResult failed"
0x180065a2d  mov     [rbp+57h+var_B0], edi
0x180065a30  mov     [rbp+57h+var_A0], rax
0x180065a34  lea     rax, [rbp+57h+var_D0]
0x180065a38  mov     [rsp+120h+var_E8], rax
0x180065a3d  lea     rax, [rbp+57h+var_B0]
0x180065a41  mov     [rsp+120h+var_F0], rax
0x180065a46  lea     rax, [rbp+57h+var_C8]
0x180065a4a  mov     [rsp+120h+var_F8], rax
0x180065a4f  lea     rax, [rbp+57h+var_A0]
0x180065a53  mov     [rsp+120h+var_100], rax
0x180065a58  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180065a5d  jmp     loc_180065EE3
0x180065a62  mov     edx, r12d; dwRevision
0x180065a65  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180065a69  call    cs:__imp_InitializeSecurityDescriptor
0x180065a6f  test    eax, eax
0x180065a71  jnz     loc_180065B18
0x180065a77  call    cs:__imp_GetLastError
0x180065a7d  mov     edi, eax
0x180065a7f  test    eax, eax
0x180065a81  jle     short loc_180065A8C
0x180065a83  movzx   edi, ax
0x180065a86  or      edi, 80070000h
0x180065a8c  mov     eax, cs:CallbackContext
0x180065a92  cmp     eax, 2
0x180065a95  jbe     loc_180065ECD
0x180065a9b  lea     rax, aFailedToInitia_54; "Failed to InitializeSecurityDescriptor"
0x180065aa2  mov     [rbp+57h+var_B0], 1C0h
0x180065aa9  mov     [rbp+57h+var_A0], rax
0x180065aad  lea     rbx, aThreadWorker; "Thread_Worker"
0x180065ab4  lea     rax, aErrorCondition; "Error condition failed"
0x180065abb  mov     [rbp+57h+var_D0], rbx
0x180065abf  mov     [rbp+57h+var_B8], rax
0x180065ac3  lea     r12, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180065aca  lea     rax, [rbp+57h+var_A0]
0x180065ace  mov     [rbp+57h+var_C0], r12
0x180065ad2  mov     [rsp+120h+var_D8], rax
0x180065ad7  lea     rdx, unk_1801C6138
0x180065ade  lea     rax, [rbp+57h+var_D0]
0x180065ae2  mov     dword ptr [rbp+57h+var_C8], edi
0x180065ae5  mov     [rsp+120h+var_E0], rax
0x180065aea  lea     rax, [rbp+57h+var_B0]
0x180065aee  mov     [rsp+120h+var_E8], rax
0x180065af3  lea     rax, [rbp+57h+var_C0]
0x180065af7  mov     [rsp+120h+var_F0], rax
0x180065afc  lea     rax, [rbp+57h+var_C8]
0x180065b00  mov     [rsp+120h+var_F8], rax
0x180065b05  lea     rax, [rbp+57h+var_B8]
0x180065b09  mov     [rsp+120h+var_100], rax
0x180065b0e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180065b13  jmp     loc_180065EDB
0x180065b18  mov     r8, [rbp+57h+pDacl]; pDacl
0x180065b1c  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180065b20  xor     r9d, r9d; bDaclDefaulted
0x180065b23  mov     edx, r12d; bDaclPresent
0x180065b26  call    cs:__imp_SetSecurityDescriptorDacl
0x180065b2c  test    eax, eax
0x180065b2e  jnz     loc_180065BCB
0x180065b34  call    cs:__imp_GetLastError
0x180065b3a  mov     edi, eax
0x180065b3c  test    eax, eax
0x180065b3e  jle     short loc_180065B49
0x180065b40  movzx   edi, ax
0x180065b43  or      edi, 80070000h
0x180065b49  mov     eax, cs:CallbackContext
0x180065b4f  cmp     eax, 2
0x180065b52  jbe     loc_180065ECD
0x180065b58  lea     rax, aFailedToSetsec; "Failed to SetSecurityDescriptorDacl"
0x180065b5f  mov     dword ptr [rbp+57h+var_C8], 1C3h
0x180065b66  mov     [rbp+57h+var_B8], rax
0x180065b6a  lea     rbx, aThreadWorker; "Thread_Worker"
0x180065b71  lea     rax, aErrorCondition; "Error condition failed"
0x180065b78  mov     [rbp+57h+var_C0], rbx
0x180065b7c  mov     [rbp+57h+var_D0], rax
0x180065b80  lea     r12, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180065b87  lea     rax, [rbp+57h+var_B8]
0x180065b8b  mov     [rbp+57h+var_A0], r12
0x180065b8f  mov     [rsp+120h+var_D8], rax
0x180065b94  lea     rdx, word_1801C618A
0x180065b9b  lea     rax, [rbp+57h+var_C0]
0x180065b9f  mov     [rbp+57h+var_B0], edi
0x180065ba2  mov     [rsp+120h+var_E0], rax
0x180065ba7  lea     rax, [rbp+57h+var_C8]
0x180065bab  mov     [rsp+120h+var_E8], rax
0x180065bb0  lea     rax, [rbp+57h+var_A0]
0x180065bb4  mov     [rsp+120h+var_F0], rax
0x180065bb9  lea     rax, [rbp+57h+var_B0]
0x180065bbd  mov     [rsp+120h+var_F8], rax
0x180065bc2  lea     rax, [rbp+57h+var_D0]
0x180065bc6  jmp     loc_180065B09
0x180065bcb  mov     eax, cs:CallbackContext
0x180065bd1  cmp     eax, 4
0x180065bd4  jbe     short loc_180065C0A
0x180065bd6  lea     rax, [rsi+98h]
0x180065bdd  mov     [rbp+57h+var_B8], rax
0x180065be1  lea     rdx, unk_1801C6098
0x180065be8  lea     rax, aStartingNamedP; "Starting named pipe listen"
0x180065bef  mov     [rbp+57h+var_C0], rax
0x180065bf3  lea     rax, [rbp+57h+var_B8]
0x180065bf7  mov     [rsp+120h+var_F8], rax
0x180065bfc  lea     rax, [rbp+57h+var_C0]
0x180065c00  mov     [rsp+120h+var_100], rax
0x180065c05  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180065c0a  mov     eax, cs:CallbackContext
0x180065c10  cmp     eax, 4
0x180065c13  jbe     loc_180065CB8
0x180065c19  mov     rdx, 470000000000h
0x180065c23  lea     rcx, CallbackContext
0x180065c2a  call    _tlgKeywordOn
0x180065c2f  test    al, al
0x180065c31  jz      loc_180065CB8
0x180065c37  lea     rax, [rsi+98h]
0x180065c3e  mov     [rbp+57h+var_C8], 1000000h
0x180065c46  mov     [rbp+57h+var_B8], rax
0x180065c4a  lea     rdx, unk_1801C60C8
0x180065c51  lea     rax, aWwwwwwwwwwwwww; "wwwwwwwwwwwwwwwwFailed to Initialize"
0x180065c58  mov     [rbp+57h+var_C0], rax
0x180065c5c  lea     rax, aNamedpipe; "NamedPipe"
0x180065c63  mov     [rbp+57h+var_A0], rax
0x180065c67  lea     rax, aStack; "Stack"
0x180065c6e  mov     [rbp+57h+var_D0], rax
0x180065c72  lea     rax, aCheckpoint; "Checkpoint"
0x180065c79  mov     [rbp+57h+var_A8], rax
0x180065c7d  lea     rax, [rbp+57h+var_B8]
0x180065c81  mov     [rsp+120h+var_D8], rax
0x180065c86  lea     rax, [rbp+57h+var_C0]
0x180065c8a  mov     [rsp+120h+var_E0], rax
0x180065c8f  lea     rax, [rbp+57h+var_A0]
0x180065c93  mov     [rsp+120h+var_E8], rax
0x180065c98  lea     rax, [rbp+57h+var_D0]
0x180065c9c  mov     [rsp+120h+var_F0], rax
0x180065ca1  lea     rax, [rbp+57h+var_C8]
0x180065ca5  mov     [rsp+120h+var_F8], rax
0x180065caa  lea     rax, [rbp+57h+var_A8]
0x180065cae  mov     [rsp+120h+var_100], rax
0x180065cb3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &)
0x180065cb8  mov     r14d, 8007006Dh
0x180065cbe  lea     r12d, [r14-67h]
0x180065cc2  lea     r9, [rbp+57h+var_B0]; int *
0x180065cc6  mov     r8, rbx; struct ITSThread *
0x180065cc9  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x180065ccd  mov     rcx, rsi; this
0x180065cd0  call    ?HandleSingleConnection@CRDPENCNamedPipeListener@@IEAAJAEBU_SECURITY_ATTRIBUTES@@PEAVITSThread@@PEAH@Z; CRDPENCNamedPipeListener::HandleSingleConnection(_SECURITY_ATTRIBUTES const &,ITSThread *,int *)
0x180065cd5  mov     ecx, 80000000h
0x180065cda  mov     edi, eax
0x180065cdc  add     eax, ecx
0x180065cde  test    ecx, eax
0x180065ce0  jnz     loc_180065E9A
0x180065ce6  cmp     edi, 83450014h
0x180065cec  jz      loc_180065E9A
0x180065cf2  cmp     edi, r14d
0x180065cf5  jz      loc_180065DB5
0x180065cfb  cmp     edi, r12d
0x180065cfe  jz      loc_180065DB5
0x180065d04  cmp     edi, 80070001h
0x180065d0a  jz      loc_180065DB5
0x180065d10  mov     eax, cs:CallbackContext
0x180065d16  cmp     eax, 2
0x180065d19  jbe     short loc_180065D7F
0x180065d1b  lea     rax, aThreadWorker; "Thread_Worker"
0x180065d22  mov     dword ptr [rbp+57h+var_C8], 1DEh
0x180065d29  mov     [rbp+57h+var_A8], rax
0x180065d2d  lea     rdx, word_1801C5FE2
0x180065d34  lea     rax, aOnecoreTermsrv_71; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180065d3b  mov     dword ptr [rbp+57h+var_D0], edi
0x180065d3e  mov     [rbp+57h+var_B8], rax
0x180065d42  lea     rax, aUnexpectedErro_1; "Unexpected error while establishing nam"...
0x180065d49  mov     [rbp+57h+var_C0], rax
0x180065d4d  lea     rax, [rbp+57h+var_A8]
0x180065d51  mov     [rsp+120h+var_E0], rax
0x180065d56  lea     rax, [rbp+57h+var_C8]
0x180065d5a  mov     [rsp+120h+var_E8], rax
0x180065d5f  lea     rax, [rbp+57h+var_B8]
0x180065d63  mov     [rsp+120h+var_F0], rax
0x180065d68  lea     rax, [rbp+57h+var_D0]
0x180065d6c  mov     [rsp+120h+var_F8], rax
0x180065d71  lea     rax, [rbp+57h+var_C0]
0x180065d75  mov     [rsp+120h+var_100], rax
0x180065d7a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180065d7f  mov     eax, cs:CallbackContext
0x180065d85  cmp     eax, 4
0x180065d88  jbe     loc_180065E9A
0x180065d8e  mov     rdx, 470000000000h
0x180065d98  lea     rcx, CallbackContext
0x180065d9f  call    _tlgKeywordOn
0x180065da4  test    al, al
0x180065da6  jz      loc_180065E9A
0x180065dac  lea     rdx, dword_1801C602C
0x180065db3  jmp     short loc_180065E20
0x180065db5  mov     eax, cs:CallbackContext
0x180065dbb  cmp     eax, 3
0x180065dbe  jbe     short loc_180065DEC
0x180065dc0  lea     rax, aPipeGotBrokenD; "Pipe got broken during establishing nam"...
0x180065dc7  mov     dword ptr [rbp+57h+var_D0], edi
0x180065dca  mov     [rbp+57h+var_A8], rax
0x180065dce  lea     rdx, byte_1801C5F45
0x180065dd5  lea     rax, [rbp+57h+var_D0]
0x180065dd9  mov     [rsp+120h+var_F8], rax
0x180065dde  lea     rax, [rbp+57h+var_A8]
0x180065de2  mov     [rsp+120h+var_100], rax
0x180065de7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180065dec  mov     eax, cs:CallbackContext
0x180065df2  cmp     eax, 4
0x180065df5  jbe     loc_180065E9A
0x180065dfb  mov     rdx, 470000000000h
0x180065e05  lea     rcx, CallbackContext
0x180065e0c  call    _tlgKeywordOn
0x180065e11  test    al, al
0x180065e13  jz      loc_180065E9A
0x180065e19  lea     rdx, byte_1801C5F73
0x180065e20  lea     rax, [rsi+98h]
0x180065e27  mov     [rbp+57h+var_D0], 1000000h
0x180065e2f  mov     [rbp+57h+var_A8], rax
0x180065e33  lea     rax, aWwwwwwwwwwwwww; "wwwwwwwwwwwwwwwwFailed to Initialize"
0x180065e3a  mov     [rbp+57h+var_B8], rax
0x180065e3e  lea     rax, aNamedpipe; "NamedPipe"
0x180065e45  mov     [rbp+57h+var_C0], rax
0x180065e49  lea     rax, aStack; "Stack"
0x180065e50  mov     [rbp+57h+var_A0], rax
0x180065e54  lea     rax, aCheckpoint; "Checkpoint"
0x180065e5b  mov     [rbp+57h+var_C8], rax
0x180065e5f  lea     rax, [rbp+57h+var_A8]
0x180065e63  mov     [rsp+120h+var_D8], rax
0x180065e68  lea     rax, [rbp+57h+var_B8]
0x180065e6c  mov     [rsp+120h+var_E0], rax
0x180065e71  lea     rax, [rbp+57h+var_C0]
0x180065e75  mov     [rsp+120h+var_E8], rax
0x180065e7a  lea     rax, [rbp+57h+var_A0]
0x180065e7e  mov     [rsp+120h+var_F0], rax
0x180065e83  lea     rax, [rbp+57h+var_D0]
0x180065e87  mov     [rsp+120h+var_F8], rax
0x180065e8c  lea     rax, [rbp+57h+var_C8]
0x180065e90  mov     [rsp+120h+var_100], rax
0x180065e95  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &)
0x180065e9a  cmp     dword ptr [rsi+29Ch], 0
  ... truncated ...
```
