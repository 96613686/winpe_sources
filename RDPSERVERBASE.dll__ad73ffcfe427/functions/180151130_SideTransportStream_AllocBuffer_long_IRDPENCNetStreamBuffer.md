# SideTransportStream::AllocBuffer(long,IRDPENCNetStreamBuffer * *)

- ea: `0x180151130`
- end: `0x18015147c`
- name: `?AllocBuffer@SideTransportStream@@UEAAJJPEAPEAUIRDPENCNetStreamBuffer@@@Z`
- size: `844`
- prototype: `int(SideTransportStream *__hidden this, int, struct IRDPENCNetStreamBuffer **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000202c`
- `0x18007e9e0`
- `0x1800a3474`
- `0x1800d4788`
- `0x180139344`
- `0x180150ef0`
- `0x180151130`
- `0x180152b54`
- `0x18019c010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015145a`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18015145a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180151184`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180151184`

## string_xrefs

- `0x1801511ee`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x18015128a`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x18015134c`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x1801513e4`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x1801511c7`: `Nano side transport pointer is null`
- `0x1801513bd`: `RDPENCNetStreamBufferAdapter::CreateInstance failed`
- `0x180151325`: `spNanoSideTransport->AllocBuffer failed`

## pseudocode

```c
__int64 __fastcall SideTransportStream::AllocBuffer(
        SideTransportStream *this,
        unsigned int a2,
        struct IRDPENCNetStreamBuffer **a3)
{
  int v6; // r8d
  int v7; // r9d
  _QWORD *v8; // rbx
  int Instance; // ebx
  __int64 v10; // rax
  struct IRdpNanoStreamBuffer *v11; // rcx
  __int64 (__fastcall *v12)(_QWORD *, _QWORD, struct IRdpNanoStreamBuffer **); // rdi
  int v13; // r8d
  int v14; // r9d
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  int v19; // [rsp+50h] [rbp-29h] BYREF
  char *v20; // [rsp+58h] [rbp-21h] BYREF
  const char *v21; // [rsp+60h] [rbp-19h] BYREF
  const char *v22; // [rsp+68h] [rbp-11h] BYREF
  const char *v23; // [rsp+70h] [rbp-9h] BYREF
  const char *v24; // [rsp+78h] [rbp-1h] BYREF
  struct IRdpNanoStreamBuffer *v25; // [rsp+80h] [rbp+7h] BYREF
  _QWORD *v26; // [rsp+88h] [rbp+Fh] BYREF
  GUID ActivityId; // [rsp+90h] [rbp+17h] BYREF

  CAutoSetThreadActivityId::CAutoSetThreadActivityId(&ActivityId, (const struct _GUID *)this + 9);
  v25 = 0;
  v26 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 16);
  v20 = (char *)this + 128;
  wil::com_ptr_t<IRdpNanoServerTransport,wil::err_returncode_policy>::operator=(&v26, (char *)this + 112);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v20);
  v8 = v26;
  if ( v26 )
  {
    if ( a3 )
    {
      v10 = *v26;
      v11 = v25;
      v25 = 0;
      v12 = *(__int64 (__fastcall **)(_QWORD *, _QWORD, struct IRdpNanoStreamBuffer **))(v10 + 56);
      if ( v11 )
        (*(void (__fastcall **)(struct IRdpNanoStreamBuffer *))(*(_QWORD *)v11 + 16LL))(v11);
      Instance = v12(v8, a2, &v25);
      if ( Instance >= 0 )
      {
        Instance = RDPENCNetStreamBufferAdapter::CreateInstance(v25, a3);
        if ( Instance >= 0 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
        }
        else if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v20) = 1187;
          v24 = "RDPENCNetStreamBufferAdapter::CreateInstance failed";
          v19 = Instance;
          v23 = "AllocBuffer";
          v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
          v21 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v15,
            (unsigned int)qword_18029B4D0,
            v16,
            v17,
            (__int64)&v21,
            (__int64)&v19,
            (__int64)&v22,
            (__int64)&v20,
            (__int64)&v23,
            (__int64)&v24);
        }
      }
      else if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v20) = 1184;
        v24 = "spNanoSideTransport->AllocBuffer failed";
        v19 = Instance;
        v23 = "AllocBuffer";
        v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
        v21 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)byte_18029C303,
          v13,
          v14,
          (__int64)&v21,
          (__int64)&v19,
          (__int64)&v22,
          (__int64)&v20,
          (__int64)&v23,
          (__int64)&v24);
      }
    }
    else
    {
      Instance = -2147467261;
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v20) = 1181;
        v24 = "ppBuffer is null";
        v19 = -2147467261;
        v23 = "AllocBuffer";
        v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
        v21 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          -2147467261,
          (unsigned int)word_18029C842,
          v6,
          v7,
          (__int64)&v21,
          (__int64)&v19,
          (__int64)&v22,
          (__int64)&v20,
          (__int64)&v23,
          (__int64)&v24);
      }
    }
  }
  else
  {
    Instance = -2147467261;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v19 = 1179;
      v21 = "Nano side transport pointer is null";
      LODWORD(v20) = -2147467261;
      v22 = "AllocBuffer";
      v23 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
      v24 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147467261,
        (unsigned int)&dword_18029C7AC,
        v6,
        v7,
        (__int64)&v24,
        (__int64)&v20,
        (__int64)&v23,
        (__int64)&v19,
        (__int64)&v22,
        (__int64)&v21);
    }
  }
  wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(&v26);
  wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(&v25);
  EventActivityIdControl(2u, &ActivityId);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180151130  push    rbp
0x180151132  push    rbx
0x180151133  push    rsi
0x180151134  push    rdi
0x180151135  push    r14
0x180151137  lea     rbp, [rsp-37h]
0x18015113c  sub     rsp, 0B0h
0x180151143  mov     rax, cs:__security_cookie
0x18015114a  xor     rax, rsp
0x18015114d  mov     [rbp+57h+var_30], rax
0x180151151  mov     r14d, edx
0x180151154  mov     rdi, rcx
0x180151157  lea     rdx, [rcx+90h]; struct _GUID *
0x18015115e  mov     rsi, r8
0x180151161  lea     rcx, [rbp+57h+ActivityId]; ActivityId
0x180151165  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x18015116a  lea     rbx, [rdi+80h]
0x180151171  mov     [rbp+57h+var_50], 0
0x180151179  mov     rcx, rbx; SRWLock
0x18015117c  mov     [rbp+57h+var_48], 0
0x180151184  call    cs:__imp_AcquireSRWLockExclusive
0x18015118a  lea     rdx, [rdi+70h]
0x18015118e  mov     [rbp+57h+var_78], rbx
0x180151192  lea     rcx, [rbp+57h+var_48]
0x180151196  call    ??4?$com_ptr_t@UIRdpNanoServerTransport@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IRdpNanoServerTransport,wil::err_returncode_policy>::operator=(wil::com_ptr_t<IRdpNanoServerTransport,wil::err_returncode_policy> const &)
0x18015119b  lea     rcx, [rbp+57h+var_78]
0x18015119f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1801511a4  mov     rbx, [rbp+57h+var_48]
0x1801511a8  test    rbx, rbx
0x1801511ab  jnz     loc_180151244
0x1801511b1  mov     eax, cs:CallbackContext
0x1801511b7  mov     ecx, 80004003h
0x1801511bc  mov     ebx, ecx
0x1801511be  cmp     eax, 2
0x1801511c1  jbe     loc_18015143F
0x1801511c7  lea     rax, aNanoSideTransp; "Nano side transport pointer is null"
0x1801511ce  mov     [rbp+57h+var_80], 49Bh
0x1801511d5  mov     [rbp+57h+var_70], rax
0x1801511d9  lea     rdx, dword_18029C7AC
0x1801511e0  lea     rax, aAllocbuffer; "AllocBuffer"
0x1801511e7  mov     dword ptr [rbp+57h+var_78], ecx
0x1801511ea  mov     [rbp+57h+var_68], rax
0x1801511ee  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801511f5  mov     [rbp+57h+var_60], rax
0x1801511f9  lea     rax, aErrorCondition; "Error condition failed"
0x180151200  mov     [rbp+57h+var_58], rax
0x180151204  lea     rax, [rbp+57h+var_70]
0x180151208  mov     [rsp+0D0h+var_88], rax
0x18015120d  lea     rax, [rbp+57h+var_68]
0x180151211  mov     [rsp+0D0h+var_90], rax
0x180151216  lea     rax, [rbp+57h+var_80]
0x18015121a  mov     [rsp+0D0h+var_98], rax
0x18015121f  lea     rax, [rbp+57h+var_60]
0x180151223  mov     [rsp+0D0h+var_A0], rax
0x180151228  lea     rax, [rbp+57h+var_78]
0x18015122c  mov     [rsp+0D0h+var_A8], rax
0x180151231  lea     rax, [rbp+57h+var_58]
0x180151235  mov     [rsp+0D0h+var_B0], rax
0x18015123a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18015123f  jmp     loc_18015143F
0x180151244  test    rsi, rsi
0x180151247  jnz     loc_1801512D6
0x18015124d  mov     eax, cs:CallbackContext
0x180151253  mov     ecx, 80004003h
0x180151258  mov     ebx, ecx
0x18015125a  cmp     eax, 2
0x18015125d  jbe     loc_18015143F
0x180151263  lea     rax, aPpbufferIsNull; "ppBuffer is null"
0x18015126a  mov     dword ptr [rbp+57h+var_78], 49Dh
0x180151271  mov     [rbp+57h+var_58], rax
0x180151275  lea     rdx, word_18029C842
0x18015127c  lea     rax, aAllocbuffer; "AllocBuffer"
0x180151283  mov     [rbp+57h+var_80], ecx
0x180151286  mov     [rbp+57h+var_60], rax
0x18015128a  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180151291  mov     [rbp+57h+var_68], rax
0x180151295  lea     rax, aErrorCondition; "Error condition failed"
0x18015129c  mov     [rbp+57h+var_70], rax
0x1801512a0  lea     rax, [rbp+57h+var_58]
0x1801512a4  mov     [rsp+0D0h+var_88], rax
0x1801512a9  lea     rax, [rbp+57h+var_60]
0x1801512ad  mov     [rsp+0D0h+var_90], rax
0x1801512b2  lea     rax, [rbp+57h+var_78]
0x1801512b6  mov     [rsp+0D0h+var_98], rax
0x1801512bb  lea     rax, [rbp+57h+var_68]
0x1801512bf  mov     [rsp+0D0h+var_A0], rax
0x1801512c4  lea     rax, [rbp+57h+var_80]
0x1801512c8  mov     [rsp+0D0h+var_A8], rax
0x1801512cd  lea     rax, [rbp+57h+var_70]
0x1801512d1  jmp     loc_180151235
0x1801512d6  mov     rax, [rbx]
0x1801512d9  mov     rcx, [rbp+57h+var_50]
0x1801512dd  mov     [rbp+57h+var_50], 0
0x1801512e5  mov     rdi, [rax+38h]
0x1801512e9  test    rcx, rcx
0x1801512ec  jz      short loc_1801512FA
0x1801512ee  mov     rax, [rcx]
0x1801512f1  mov     rax, [rax+10h]
0x1801512f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801512fa  lea     r8, [rbp+57h+var_50]
0x1801512fe  mov     edx, r14d
0x180151301  mov     rcx, rbx
0x180151304  mov     rax, rdi
0x180151307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015130c  mov     ebx, eax
0x18015130e  test    eax, eax
0x180151310  jns     loc_180151398
0x180151316  mov     ecx, cs:CallbackContext
0x18015131c  cmp     ecx, 2
0x18015131f  jbe     loc_18015143F
0x180151325  lea     rax, aSpnanosidetran; "spNanoSideTransport->AllocBuffer failed"
0x18015132c  mov     dword ptr [rbp+57h+var_78], 4A0h
0x180151333  mov     [rbp+57h+var_58], rax
0x180151337  lea     rdx, byte_18029C303
0x18015133e  lea     rax, aAllocbuffer; "AllocBuffer"
0x180151345  mov     [rbp+57h+var_80], ebx
0x180151348  mov     [rbp+57h+var_60], rax
0x18015134c  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180151353  mov     [rbp+57h+var_68], rax
0x180151357  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18015135e  mov     [rbp+57h+var_70], rax
0x180151362  lea     rax, [rbp+57h+var_58]
0x180151366  mov     [rsp+0D0h+var_88], rax
0x18015136b  lea     rax, [rbp+57h+var_60]
0x18015136f  mov     [rsp+0D0h+var_90], rax
0x180151374  lea     rax, [rbp+57h+var_78]
0x180151378  mov     [rsp+0D0h+var_98], rax
0x18015137d  lea     rax, [rbp+57h+var_68]
0x180151381  mov     [rsp+0D0h+var_A0], rax
0x180151386  lea     rax, [rbp+57h+var_80]
0x18015138a  mov     [rsp+0D0h+var_A8], rax
0x18015138f  lea     rax, [rbp+57h+var_70]
0x180151393  jmp     loc_180151235
0x180151398  mov     rcx, [rbp+57h+var_50]; struct IRdpNanoStreamBuffer *
0x18015139c  mov     rdx, rsi; struct IRDPENCNetStreamBuffer **
0x18015139f  call    ?CreateInstance@RDPENCNetStreamBufferAdapter@@SAJPEAUIRdpNanoStreamBuffer@@PEAPEAUIRDPENCNetStreamBuffer@@@Z; RDPENCNetStreamBufferAdapter::CreateInstance(IRdpNanoStreamBuffer *,IRDPENCNetStreamBuffer * *)
0x1801513a4  mov     ebx, eax
0x1801513a6  test    eax, eax
0x1801513a8  jns     loc_180151430
0x1801513ae  mov     eax, cs:CallbackContext
0x1801513b4  cmp     eax, 2
0x1801513b7  jbe     loc_18015143F
0x1801513bd  lea     rax, aRdpencnetstrea; "RDPENCNetStreamBufferAdapter::CreateIns"...
0x1801513c4  mov     dword ptr [rbp+57h+var_78], 4A3h
0x1801513cb  mov     [rbp+57h+var_58], rax
0x1801513cf  lea     rdx, qword_18029B4D0
0x1801513d6  lea     rax, aAllocbuffer; "AllocBuffer"
0x1801513dd  mov     [rbp+57h+var_80], ebx
0x1801513e0  mov     [rbp+57h+var_60], rax
0x1801513e4  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801513eb  mov     [rbp+57h+var_68], rax
0x1801513ef  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1801513f6  mov     [rbp+57h+var_70], rax
0x1801513fa  lea     rax, [rbp+57h+var_58]
0x1801513fe  mov     [rsp+0D0h+var_88], rax
0x180151403  lea     rax, [rbp+57h+var_60]
0x180151407  mov     [rsp+0D0h+var_90], rax
0x18015140c  lea     rax, [rbp+57h+var_78]
0x180151410  mov     [rsp+0D0h+var_98], rax
0x180151415  lea     rax, [rbp+57h+var_68]
0x180151419  mov     [rsp+0D0h+var_A0], rax
0x18015141e  lea     rax, [rbp+57h+var_80]
0x180151422  mov     [rsp+0D0h+var_A8], rax
0x180151427  lea     rax, [rbp+57h+var_70]
0x18015142b  jmp     loc_180151235
0x180151430  mov     rcx, [rsi]
0x180151433  mov     rax, [rcx]
0x180151436  mov     rax, [rax+8]
0x18015143a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015143f  lea     rcx, [rbp+57h+var_48]
0x180151443  call    ??1?$com_ptr_t@UIRDPCollection@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(void)
0x180151448  lea     rcx, [rbp+57h+var_50]
0x18015144c  call    ??1?$com_ptr_t@UIRDPCollection@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(void)
0x180151451  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x180151455  mov     ecx, 2; ControlCode
0x18015145a  call    cs:__imp_EventActivityIdControl
0x180151460  mov     eax, ebx
0x180151462  mov     rcx, [rbp+57h+var_30]
0x180151466  xor     rcx, rsp; StackCookie
0x180151469  call    __security_check_cookie
0x18015146e  add     rsp, 0B0h
0x180151475  pop     r14
0x180151477  pop     rdi
0x180151478  pop     rsi
0x180151479  pop     rbx
0x18015147a  pop     rbp
0x18015147b  retn
```
