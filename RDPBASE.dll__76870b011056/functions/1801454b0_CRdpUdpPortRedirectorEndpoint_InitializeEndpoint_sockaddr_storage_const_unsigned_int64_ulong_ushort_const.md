# CRdpUdpPortRedirectorEndpoint::InitializeEndpoint(sockaddr_storage const &,unsigned __int64,ulong,ushort const *)

- ea: `0x1801454b0`
- end: `0x18014578b`
- name: `?InitializeEndpoint@CRdpUdpPortRedirectorEndpoint@@MEAAJAEBUsockaddr_storage@@_KKPEBG@Z`
- size: `731`
- prototype: `__int64 __fastcall(CRdpUdpPortRedirectorEndpoint *this, const struct sockaddr_storage *, __int64, unsigned int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001aa0`
- `0x180002550`
- `0x1801281e0`
- `0x1801454b0`
- `0x180145d84`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145556`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145556`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180145547`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180145547`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801454d3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1801454d3`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x1801454e0`
- `api-ms-win-core-synch-l1-2-0!InitializeConditionVariable` at `0x1801454e0`

## string_xrefs

- `0x18014557a`: `Failed to create socket event`
- `0x180145620`: `Failed to create shared handle in CRdpUdpPortRedirectorEndpoint::InitializeEndpoint`

## pseudocode

```c
__int64 __fastcall CRdpUdpPortRedirectorEndpoint::InitializeEndpoint(
        CRdpUdpPortRedirectorEndpoint *this,
        const struct sockaddr_storage *a2,
        __int64 a3,
        unsigned int a4,
        unsigned __int16 *a5)
{
  HANDLE EventW; // rax
  signed int LastError; // eax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  signed int v13; // ebx
  char *v14; // rdx
  const char **v15; // rax
  __int64 v16; // rcx
  const char **v18; // [rsp+30h] [rbp-40h]
  const char **v19; // [rsp+40h] [rbp-30h]
  const char **v20; // [rsp+48h] [rbp-28h]
  const char *v21; // [rsp+50h] [rbp-20h] BYREF
  const char *v22; // [rsp+58h] [rbp-18h] BYREF
  const char *v23; // [rsp+60h] [rbp-10h] BYREF
  const char *v24; // [rsp+68h] [rbp-8h] BYREF
  struct ISharedHandle *v25; // [rsp+A0h] [rbp+30h] BYREF
  signed int v26; // [rsp+A8h] [rbp+38h] BYREF

  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 696));
  InitializeConditionVariable((PCONDITION_VARIABLE)this + 96);
  *((_DWORD *)this + 195) = 1;
  *(struct sockaddr_storage *)((char *)this + 80) = *a2;
  EventW = CreateEventW(0, 1, 0, 0);
  if ( EventW )
  {
    v25 = 0;
    v13 = SharedHandle::CreateInstance(EventW, &v25);
    if ( v13 < 0 )
    {
      v10 = (int)CallbackContext;
      if ( (unsigned int)CallbackContext <= 2 )
        return (unsigned int)v13;
      LODWORD(v25) = 77;
      v24 = "Failed to create shared handle in CRdpUdpPortRedirectorEndpoint::InitializeEndpoint";
      v14 = &byte_1801D5D1F;
      v23 = "InitializeEndpoint";
      v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpportredirectorendpoint.cpp";
      v21 = "Error HResult failed";
      v20 = &v24;
      v19 = &v23;
      v18 = &v22;
      v15 = &v21;
      goto LABEL_6;
    }
    v16 = *((_QWORD *)this + 7);
    *((_QWORD *)this + 7) = v25;
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v13 = CRdpUdpPortRedirectorEndpoint::RegisterWithPortRedirector(
            (CRdpUdpPortRedirectorEndpoint *)((char *)this - 8),
            (struct sockaddr_storage *)((char *)this + 80),
            a4,
            a5);
    if ( v13 < 0 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        return (unsigned int)v13;
      LODWORD(v25) = 83;
      v24 = "RegisterWithPortRedirector failed";
      v14 = (char *)&dword_1801D5CD4;
      v23 = "InitializeEndpoint";
      v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpportredirectorendpoint.cpp";
      v21 = "Error HResult failed";
      v20 = &v24;
      v19 = &v23;
      v18 = &v22;
      v15 = &v21;
      goto LABEL_6;
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      v25 = (struct ISharedHandle *)"UDP port redirector endpoint initialized";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&CallbackContext,
        (unsigned int)byte_1801D5CB5,
        0,
        v12,
        (__int64)&v25);
    }
  }
  else
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v25) = 73;
      v21 = "Failed to create socket event";
      v14 = &byte_1801D5E07;
      v22 = "InitializeEndpoint";
      v23 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\udptransport\\rdpudpportredirectorendpoint.cpp";
      v24 = "Error condition failed";
      v20 = &v21;
      v19 = &v22;
      v18 = &v23;
      v15 = &v24;
LABEL_6:
      v26 = v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v10,
        (_DWORD)v14,
        v11,
        v12,
        (__int64)v15,
        (__int64)&v26,
        (__int64)v18,
        (__int64)&v25,
        (__int64)v19,
        (__int64)v20);
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1801454b0  mov     [rsp-28h+arg_10], rbx
0x1801454b5  push    rbp
0x1801454b6  push    rsi
0x1801454b7  push    rdi
0x1801454b8  push    r14
0x1801454ba  push    r15
0x1801454bc  mov     rbp, rsp
0x1801454bf  sub     rsp, 70h
0x1801454c3  mov     rdi, rcx
0x1801454c6  mov     r15d, r9d
0x1801454c9  add     rcx, 2B8h; lpCriticalSection
0x1801454d0  mov     rbx, rdx
0x1801454d3  call    cs:__imp_InitializeCriticalSection
0x1801454d9  lea     rcx, [rdi+300h]; ConditionVariable
0x1801454e0  call    cs:__imp_InitializeConditionVariable
0x1801454e6  mov     edx, 1; bManualReset
0x1801454eb  xor     r9d, r9d; lpName
0x1801454ee  mov     [rdi+30Ch], edx
0x1801454f4  xor     r8d, r8d; bInitialState
0x1801454f7  movups  xmm0, xmmword ptr [rbx]
0x1801454fa  xor     ecx, ecx; lpEventAttributes
0x1801454fc  movups  xmmword ptr [rdi+50h], xmm0
0x180145500  movups  xmm1, xmmword ptr [rbx+10h]
0x180145504  movups  xmmword ptr [rdi+60h], xmm1
0x180145508  movups  xmm0, xmmword ptr [rbx+20h]
0x18014550c  movups  xmmword ptr [rdi+70h], xmm0
0x180145510  movups  xmm1, xmmword ptr [rbx+30h]
0x180145514  movups  xmmword ptr [rdi+80h], xmm1
0x18014551b  movups  xmm0, xmmword ptr [rbx+40h]
0x18014551f  movups  xmmword ptr [rdi+90h], xmm0
0x180145526  movups  xmm1, xmmword ptr [rbx+50h]
0x18014552a  movups  xmmword ptr [rdi+0A0h], xmm1
0x180145531  movups  xmm0, xmmword ptr [rbx+60h]
0x180145535  movups  xmmword ptr [rdi+0B0h], xmm0
0x18014553c  movups  xmm1, xmmword ptr [rbx+70h]
0x180145540  movups  xmmword ptr [rdi+0C0h], xmm1
0x180145547  call    cs:__imp_CreateEventW
0x18014554d  test    rax, rax
0x180145550  jnz     loc_1801455F7
0x180145556  call    cs:__imp_GetLastError
0x18014555c  mov     ebx, eax
0x18014555e  test    eax, eax
0x180145560  jle     short loc_18014556B
0x180145562  movzx   ebx, ax
0x180145565  or      ebx, 80070000h
0x18014556b  mov     eax, cs:CallbackContext
0x180145571  cmp     eax, 2
0x180145574  jbe     loc_180145775
0x18014557a  lea     rax, aFailedToCreate_86; "Failed to create socket event"
0x180145581  mov     dword ptr [rbp+arg_0], 49h ; 'I'
0x180145588  mov     [rbp+var_20], rax
0x18014558c  lea     rdx, byte_1801D5E07
0x180145593  lea     rax, aInitializeendp_0; "InitializeEndpoint"
0x18014559a  mov     [rbp+var_18], rax
0x18014559e  lea     rax, aOnecoreTermsrv_69; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801455a5  mov     [rbp+var_10], rax
0x1801455a9  lea     rax, aErrorCondition; "Error condition failed"
0x1801455b0  mov     [rbp+var_8], rax
0x1801455b4  lea     rax, [rbp+var_20]
0x1801455b8  mov     [rsp+70h+var_28], rax
0x1801455bd  lea     rax, [rbp+var_18]
0x1801455c1  mov     [rsp+70h+var_30], rax
0x1801455c6  lea     rax, [rbp+arg_0]
0x1801455ca  mov     [rsp+70h+var_38], rax
0x1801455cf  lea     rax, [rbp+var_10]
0x1801455d3  mov     [rsp+70h+var_40], rax
0x1801455d8  lea     rax, [rbp+arg_8]
0x1801455dc  mov     [rsp+70h+var_48], rax
0x1801455e1  lea     rax, [rbp+var_8]
0x1801455e5  mov     [rbp+arg_8], ebx
0x1801455e8  mov     [rsp+70h+var_50], rax
0x1801455ed  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1801455f2  jmp     loc_180145775
0x1801455f7  lea     rdx, [rbp+arg_0]; struct ISharedHandle **
0x1801455fb  mov     [rbp+arg_0], 0
0x180145603  mov     rcx, rax; void *
0x180145606  call    ?CreateInstance@SharedHandle@@SAJPEAXPEAPEAUISharedHandle@@@Z; SharedHandle::CreateInstance(void *,ISharedHandle * *)
0x18014560b  mov     ebx, eax
0x18014560d  test    eax, eax
0x18014560f  jns     short loc_180145690
0x180145611  mov     ecx, cs:CallbackContext
0x180145617  cmp     ecx, 2
0x18014561a  jbe     loc_180145775
0x180145620  lea     rax, aFailedToCreate; "Failed to create shared handle in CRdpU"...
0x180145627  mov     dword ptr [rbp+arg_0], 4Dh ; 'M'
0x18014562e  mov     [rbp+var_8], rax
0x180145632  lea     rdx, byte_1801D5D1F
0x180145639  lea     rax, aInitializeendp_0; "InitializeEndpoint"
0x180145640  mov     [rbp+var_10], rax
0x180145644  lea     rax, aOnecoreTermsrv_69; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x18014564b  mov     [rbp+var_18], rax
0x18014564f  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180145656  mov     [rbp+var_20], rax
0x18014565a  lea     rax, [rbp+var_8]
0x18014565e  mov     [rsp+70h+var_28], rax
0x180145663  lea     rax, [rbp+var_10]
0x180145667  mov     [rsp+70h+var_30], rax
0x18014566c  lea     rax, [rbp+arg_0]
0x180145670  mov     [rsp+70h+var_38], rax
0x180145675  lea     rax, [rbp+var_18]
0x180145679  mov     [rsp+70h+var_40], rax
0x18014567e  lea     rax, [rbp+arg_8]
0x180145682  mov     [rsp+70h+var_48], rax
0x180145687  lea     rax, [rbp+var_20]
0x18014568b  jmp     loc_1801455E5
0x180145690  mov     rcx, [rdi+38h]
0x180145694  mov     rax, [rbp+arg_0]
0x180145698  mov     [rdi+38h], rax
0x18014569c  test    rcx, rcx
0x18014569f  jz      short loc_1801456AD
0x1801456a1  mov     rax, [rcx]
0x1801456a4  mov     rax, [rax+10h]
0x1801456a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801456ad  mov     r9, [rbp+arg_20]; unsigned __int16 *
0x1801456b1  lea     rdx, [rdi+50h]; struct sockaddr_storage *
0x1801456b5  mov     r8d, r15d; unsigned int
0x1801456b8  lea     rcx, [rdi-8]; this
0x1801456bc  call    ?RegisterWithPortRedirector@CRdpUdpPortRedirectorEndpoint@@IEAAJAEAUsockaddr_storage@@KPEBG@Z; CRdpUdpPortRedirectorEndpoint::RegisterWithPortRedirector(sockaddr_storage &,ulong,ushort const *)
0x1801456c1  mov     ebx, eax
0x1801456c3  test    eax, eax
0x1801456c5  mov     eax, cs:CallbackContext
0x1801456cb  jns     short loc_180145746
0x1801456cd  cmp     eax, 2
0x1801456d0  jbe     loc_180145775
0x1801456d6  lea     rax, aRegisterwithpo_0; "RegisterWithPortRedirector failed"
0x1801456dd  mov     dword ptr [rbp+arg_0], 53h ; 'S'
0x1801456e4  mov     [rbp+var_8], rax
0x1801456e8  lea     rdx, dword_1801D5CD4
0x1801456ef  lea     rax, aInitializeendp_0; "InitializeEndpoint"
0x1801456f6  mov     [rbp+var_10], rax
0x1801456fa  lea     rax, aOnecoreTermsrv_69; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180145701  mov     [rbp+var_18], rax
0x180145705  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18014570c  mov     [rbp+var_20], rax
0x180145710  lea     rax, [rbp+var_8]
0x180145714  mov     [rsp+70h+var_28], rax
0x180145719  lea     rax, [rbp+var_10]
0x18014571d  mov     [rsp+70h+var_30], rax
0x180145722  lea     rax, [rbp+arg_0]
0x180145726  mov     [rsp+70h+var_38], rax
0x18014572b  lea     rax, [rbp+var_18]
0x18014572f  mov     [rsp+70h+var_40], rax
0x180145734  lea     rax, [rbp+arg_8]
0x180145738  mov     [rsp+70h+var_48], rax
0x18014573d  lea     rax, [rbp+var_20]
0x180145741  jmp     loc_1801455E5
0x180145746  cmp     eax, 4
0x180145749  jbe     short loc_180145775
0x18014574b  lea     rax, aUdpPortRedirec_2; "UDP port redirector endpoint initialize"...
0x180145752  xor     r8d, r8d
0x180145755  mov     [rbp+arg_0], rax
0x180145759  lea     rdx, byte_1801D5CB5
0x180145760  lea     rax, [rbp+arg_0]
0x180145764  lea     rcx, CallbackContext
0x18014576b  mov     [rsp+70h+var_50], rax
0x180145770  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180145775  mov     eax, ebx
0x180145777  mov     rbx, [rsp+70h+arg_10]
0x18014577f  add     rsp, 70h
0x180145783  pop     r15
0x180145785  pop     r14
0x180145787  pop     rdi
0x180145788  pop     rsi
0x180145789  pop     rbp
0x18014578a  retn
```
