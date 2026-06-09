# SideTransportStream::WriteSideBandData(ushort,void *,uint)

- ea: `0x1801563c0`
- end: `0x180156729`
- name: `?WriteSideBandData@SideTransportStream@@UEAAJGPEAXI@Z`
- size: `873`
- prototype: `int(SideTransportStream *__hidden this, unsigned __int16, void *, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800012dc`
- `0x18000202c`
- `0x180002d3c`
- `0x18007f42c`
- `0x18007f6f0`
- `0x18007f6fc`
- `0x1800a3474`
- `0x1800d4788`
- `0x180150ef0`
- `0x1801563c0`
- `0x1801572c4`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180156408`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180156408`

## string_xrefs

- `0x180156469`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x1801565cc`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x18015661a`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x1801566a6`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x180156445`: `Nano side transport pointer is null`
- `0x18015645e`: `WriteSideBandData`
- `0x1801565c1`: `WriteSideBandData`
- `0x18015660c`: `WriteSideBandData`
- `0x18015669b`: `WriteSideBandData`

## pseudocode

```c
__int64 __fastcall SideTransportStream::WriteSideBandData(RTL_SRWLOCK *this, unsigned __int16 a2, void *a3, __int64 a4)
{
  void *v4; // rdi
  rsize_t v5; // r14
  RTL_SRWLOCK *v8; // rsi
  RTL_SRWLOCK *v9; // rbx
  __int64 v10; // rbx
  int v11; // ebx
  char *v12; // rdx
  const char **v13; // rax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  void *v17; // rax
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  const char *v21; // rax
  const char **v23; // [rsp+30h] [rbp-50h]
  const char **v24; // [rsp+40h] [rbp-40h]
  const char **v25; // [rsp+48h] [rbp-38h]
  int v26; // [rsp+50h] [rbp-30h] BYREF
  __int64 v27; // [rsp+58h] [rbp-28h] BYREF
  const char *v28; // [rsp+60h] [rbp-20h] BYREF
  const char *v29; // [rsp+68h] [rbp-18h] BYREF
  const char *v30; // [rsp+70h] [rbp-10h] BYREF
  const char *v31; // [rsp+78h] [rbp-8h] BYREF
  RTL_SRWLOCK *v32; // [rsp+C0h] [rbp+40h] BYREF

  v4 = 0;
  v5 = (unsigned int)a4;
  v27 = 0;
  v8 = this;
  if ( !a3 || !(_DWORD)a4 )
  {
    v11 = -2147024809;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_20;
    LODWORD(v32) = 645;
    v31 = "Invalid peer ICE candidates string size";
    v12 = byte_18029BB6D;
    v30 = "WriteSideBandData";
    v29 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
    v21 = "Error condition failed";
    goto LABEL_18;
  }
  v9 = this + 13;
  AcquireSRWLockExclusive(this + 13);
  v32 = v9;
  wil::com_ptr_t<IRdpNanoServerTransport,wil::err_returncode_policy>::operator=(&v27, &v8[11]);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v32);
  v10 = v27;
  if ( v27 )
  {
    if ( (unsigned int)CallbackContext > 4 && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL, a3, a4) )
    {
      v29 = (const char *)0x1000000;
      v32 = v8 + 15;
      v31 = "Udp";
      v30 = "Stack";
      v28 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
        v14,
        (unsigned int)&byte_18029CC97,
        v15,
        v16,
        (__int64)&v28,
        (__int64)&v29,
        (__int64)&v30,
        (__int64)&v31,
        (__int64)&v32);
    }
    v17 = operator new[]((unsigned int)(v5 + 1));
    v4 = v17;
    if ( !v17 )
    {
      v11 = -2147024882;
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v32) = 659;
        v31 = "String allocation failed";
        v26 = -2147024882;
        v30 = "WriteSideBandData";
        v29 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
        v28 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v18,
          (unsigned int)word_18029C14A,
          v19,
          v20,
          (__int64)&v28,
          (__int64)&v26,
          (__int64)&v29,
          (__int64)&v32,
          (__int64)&v30,
          (__int64)&v31);
      }
      v4 = 0;
      goto LABEL_20;
    }
    memset_0(v17, 0, (unsigned int)(v5 + 1));
    memcpy_s_0(v4, v5, a3, v5);
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, void *))(*(_QWORD *)v10 + 88LL))(v10, a2, v4);
    if ( v11 >= 0 )
      goto LABEL_20;
    LODWORD(this) = (_DWORD)CallbackContext;
    if ( (unsigned int)CallbackContext <= 2 )
      goto LABEL_20;
    LODWORD(v32) = 664;
    v31 = "OnSignalingChannelDataReceived failed";
    v12 = byte_18029CDF5;
    v30 = "WriteSideBandData";
    v29 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
    v21 = "Error HResult failed";
LABEL_18:
    v28 = v21;
    v25 = &v31;
    v24 = &v30;
    v23 = &v29;
    v13 = &v28;
    goto LABEL_19;
  }
  v11 = -2147467261;
  if ( (unsigned int)CallbackContext > 2 )
  {
    LODWORD(v32) = 652;
    v28 = "Nano side transport pointer is null";
    v12 = (char *)&word_18029B8DE;
    v29 = "WriteSideBandData";
    v30 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
    v31 = "Error condition failed";
    v25 = &v28;
    v24 = &v29;
    v23 = &v30;
    v13 = &v31;
LABEL_19:
    v26 = v11;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (_DWORD)this,
      (_DWORD)v12,
      (_DWORD)a3,
      a4,
      (__int64)v13,
      (__int64)&v26,
      (__int64)v23,
      (__int64)&v32,
      (__int64)v24,
      (__int64)v25);
  }
LABEL_20:
  operator delete(v4);
  wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(&v27);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1801563c0  mov     [rsp-28h+arg_0], rbx
0x1801563c5  mov     [rsp-28h+arg_8], rsi
0x1801563ca  push    rbp
0x1801563cb  push    rdi
0x1801563cc  push    r12
0x1801563ce  push    r14
0x1801563d0  push    r15
0x1801563d2  mov     rbp, rsp
0x1801563d5  sub     rsp, 80h
0x1801563dc  xor     edi, edi
0x1801563de  mov     r14d, r9d
0x1801563e1  mov     [rbp+var_28], rdi
0x1801563e5  mov     r15, r8
0x1801563e8  movzx   r12d, dx
0x1801563ec  mov     rsi, rcx
0x1801563ef  test    r8, r8
0x1801563f2  jz      loc_180156672
0x1801563f8  test    r9d, r9d
0x1801563fb  jz      loc_180156672
0x180156401  lea     rbx, [rcx+68h]
0x180156405  mov     rcx, rbx; SRWLock
0x180156408  call    cs:__imp_AcquireSRWLockExclusive
0x18015640e  lea     rdx, [rsi+58h]
0x180156412  mov     [rbp+arg_10], rbx
0x180156416  lea     rcx, [rbp+var_28]
0x18015641a  call    ??4?$com_ptr_t@UIRdpNanoServerTransport@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IRdpNanoServerTransport,wil::err_returncode_policy>::operator=(wil::com_ptr_t<IRdpNanoServerTransport,wil::err_returncode_policy> const &)
0x18015641f  lea     rcx, [rbp+arg_10]
0x180156423  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180156428  mov     rbx, [rbp+var_28]
0x18015642c  mov     eax, cs:CallbackContext
0x180156432  test    rbx, rbx
0x180156435  jnz     short loc_1801564B5
0x180156437  mov     ebx, 80004003h
0x18015643c  cmp     eax, 2
0x18015643f  jbe     loc_1801566FA
0x180156445  lea     rax, aNanoSideTransp; "Nano side transport pointer is null"
0x18015644c  mov     dword ptr [rbp+arg_10], 28Ch
0x180156453  mov     [rbp+var_20], rax
0x180156457  lea     rdx, word_18029B8DE
0x18015645e  lea     rax, aWritesidebandd; "WriteSideBandData"
0x180156465  mov     [rbp+var_18], rax
0x180156469  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180156470  mov     [rbp+var_10], rax
0x180156474  lea     rax, aErrorCondition; "Error condition failed"
0x18015647b  mov     [rbp+var_8], rax
0x18015647f  lea     rax, [rbp+var_20]
0x180156483  mov     [rsp+80h+var_38], rax
0x180156488  lea     rax, [rbp+var_18]
0x18015648c  mov     [rsp+80h+var_40], rax
0x180156491  lea     rax, [rbp+arg_10]
0x180156495  mov     [rsp+80h+var_48], rax
0x18015649a  lea     rax, [rbp+var_10]
0x18015649e  mov     [rsp+80h+var_50], rax
0x1801564a3  lea     rax, [rbp+var_30]
0x1801564a7  mov     [rsp+80h+var_58], rax
0x1801564ac  lea     rax, [rbp+var_8]
0x1801564b0  jmp     loc_1801566ED
0x1801564b5  cmp     eax, 4
0x1801564b8  jbe     loc_180156542
0x1801564be  mov     rdx, 470000000000h
0x1801564c8  lea     rcx, CallbackContext
0x1801564cf  call    _tlgKeywordOn
0x1801564d4  test    al, al
0x1801564d6  jz      short loc_180156542
0x1801564d8  lea     rax, [rsi+78h]
0x1801564dc  mov     [rbp+var_18], 1000000h
0x1801564e4  mov     [rbp+arg_10], rax
0x1801564e8  lea     rdx, byte_18029CC97
0x1801564ef  lea     rax, aUdp; "Udp"
0x1801564f6  mov     [rbp+var_8], rax
0x1801564fa  lea     rax, aStack; "Stack"
0x180156501  mov     [rbp+var_10], rax
0x180156505  lea     rax, aCheckpoint; "Checkpoint"
0x18015650c  mov     [rbp+var_20], rax
0x180156510  lea     rax, [rbp+arg_10]
0x180156514  mov     [rsp+80h+var_40], rax
0x180156519  lea     rax, [rbp+var_8]
0x18015651d  mov     [rsp+80h+var_48], rax
0x180156522  lea     rax, [rbp+var_10]
0x180156526  mov     [rsp+80h+var_50], rax
0x18015652b  lea     rax, [rbp+var_18]
0x18015652f  mov     [rsp+80h+var_58], rax
0x180156534  lea     rax, [rbp+var_20]
0x180156538  mov     [rsp+80h+var_60], rax
0x18015653d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &)
0x180156542  lea     eax, [r14+1]
0x180156546  mov     ecx, eax; unsigned __int64
0x180156548  mov     esi, eax
0x18015654a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18015654f  mov     rdi, rax
0x180156552  test    rax, rax
0x180156555  jz      loc_1801565E3
0x18015655b  mov     r8d, esi; Size
0x18015655e  xor     edx, edx; Val
0x180156560  mov     rcx, rax; void *
0x180156563  call    memset_0
0x180156568  mov     rdx, r14; DestinationSize
0x18015656b  mov     r9, r14; SourceSize
0x18015656e  mov     r8, r15; Source
0x180156571  mov     rcx, rdi; Destination
0x180156574  call    memcpy_s_0
0x180156579  mov     rax, [rbx]
0x18015657c  mov     r8, rdi
0x18015657f  movzx   edx, r12w
0x180156583  mov     rcx, rbx
0x180156586  mov     rax, [rax+58h]
0x18015658a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015658f  mov     ebx, eax
0x180156591  test    eax, eax
0x180156593  jns     loc_1801566FA
0x180156599  mov     ecx, cs:CallbackContext
0x18015659f  cmp     ecx, 2
0x1801565a2  jbe     loc_1801566FA
0x1801565a8  lea     rax, aOnsignalingcha; "OnSignalingChannelDataReceived failed"
0x1801565af  mov     dword ptr [rbp+arg_10], 298h
0x1801565b6  mov     [rbp+var_8], rax
0x1801565ba  lea     rdx, byte_18029CDF5
0x1801565c1  lea     rax, aWritesidebandd; "WriteSideBandData"
0x1801565c8  mov     [rbp+var_10], rax
0x1801565cc  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801565d3  mov     [rbp+var_18], rax
0x1801565d7  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1801565de  jmp     loc_1801566B8
0x1801565e3  mov     eax, cs:CallbackContext
0x1801565e9  mov     ebx, 8007000Eh
0x1801565ee  cmp     eax, 2
0x1801565f1  jbe     short loc_18015666B
0x1801565f3  lea     rax, aStringAllocati; "String allocation failed"
0x1801565fa  mov     dword ptr [rbp+arg_10], 293h
0x180156601  mov     [rbp+var_8], rax
0x180156605  lea     rdx, word_18029C14A
0x18015660c  lea     rax, aWritesidebandd; "WriteSideBandData"
0x180156613  mov     [rbp+var_30], ebx
0x180156616  mov     [rbp+var_10], rax
0x18015661a  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180156621  mov     [rbp+var_18], rax
0x180156625  lea     rax, aErrorCondition; "Error condition failed"
0x18015662c  mov     [rbp+var_20], rax
0x180156630  lea     rax, [rbp+var_8]
0x180156634  mov     [rsp+80h+var_38], rax
0x180156639  lea     rax, [rbp+var_10]
0x18015663d  mov     [rsp+80h+var_40], rax
0x180156642  lea     rax, [rbp+arg_10]
0x180156646  mov     [rsp+80h+var_48], rax
0x18015664b  lea     rax, [rbp+var_18]
0x18015664f  mov     [rsp+80h+var_50], rax
0x180156654  lea     rax, [rbp+var_30]
0x180156658  mov     [rsp+80h+var_58], rax
0x18015665d  lea     rax, [rbp+var_20]
0x180156661  mov     [rsp+80h+var_60], rax
0x180156666  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18015666b  xor     edi, edi
0x18015666d  jmp     loc_1801566FA
0x180156672  mov     eax, cs:CallbackContext
0x180156678  mov     ebx, 80070057h
0x18015667d  cmp     eax, 2
0x180156680  jbe     short loc_1801566FA
0x180156682  lea     rax, aInvalidPeerIce; "Invalid peer ICE candidates string size"
0x180156689  mov     dword ptr [rbp+arg_10], 285h
0x180156690  mov     [rbp+var_8], rax
0x180156694  lea     rdx, byte_18029BB6D
0x18015669b  lea     rax, aWritesidebandd; "WriteSideBandData"
0x1801566a2  mov     [rbp+var_10], rax
0x1801566a6  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1801566ad  mov     [rbp+var_18], rax
0x1801566b1  lea     rax, aErrorCondition; "Error condition failed"
0x1801566b8  mov     [rbp+var_20], rax
0x1801566bc  lea     rax, [rbp+var_8]
0x1801566c0  mov     [rsp+80h+var_38], rax
0x1801566c5  lea     rax, [rbp+var_10]
0x1801566c9  mov     [rsp+80h+var_40], rax
0x1801566ce  lea     rax, [rbp+arg_10]
0x1801566d2  mov     [rsp+80h+var_48], rax
0x1801566d7  lea     rax, [rbp+var_18]
0x1801566db  mov     [rsp+80h+var_50], rax
0x1801566e0  lea     rax, [rbp+var_30]
0x1801566e4  mov     [rsp+80h+var_58], rax
0x1801566e9  lea     rax, [rbp+var_20]
0x1801566ed  mov     [rsp+80h+var_60], rax
0x1801566f2  mov     [rbp+var_30], ebx
0x1801566f5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1801566fa  mov     rcx, rdi; Block
0x1801566fd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180156702  lea     rcx, [rbp+var_28]
0x180156706  call    ??1?$com_ptr_t@UIRDPCollection@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(void)
0x18015670b  lea     r11, [rsp+80h+var_s0]
0x180156713  mov     eax, ebx
0x180156715  mov     rbx, [r11+30h]
0x180156719  mov     rsi, [r11+38h]
0x18015671d  mov     rsp, r11
0x180156720  pop     r15
0x180156722  pop     r14
0x180156724  pop     r12
0x180156726  pop     rdi
0x180156727  pop     rbp
0x180156728  retn
```
