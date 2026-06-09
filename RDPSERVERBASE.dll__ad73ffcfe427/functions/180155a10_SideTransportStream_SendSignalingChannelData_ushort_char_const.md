# SideTransportStream::SendSignalingChannelData(ushort,char const *)

- ea: `0x180155a10`
- end: `0x180155e95`
- name: `?SendSignalingChannelData@SideTransportStream@@UEAAXGPEBD@Z`
- size: `1157`
- prototype: `void __fastcall(SideTransportStream *__hidden this, unsigned __int16, const char *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000116c`
- `0x1800012dc`
- `0x180001308`
- `0x18000146c`
- `0x18000202c`
- `0x180002d3c`
- `0x18004d52c`
- `0x18007e9e0`
- `0x1800a3474`
- `0x1800d4788`
- `0x180150b60`
- `0x180155a10`
- `0x180156860`
- `0x18019c010`

## import_xrefs

- `RDPBASE!RDPServerStackDiagnostics_LogShortpathPublicCheckpoint` at `0x180155c3c`
- `RDPBASE!RDPServerStackDiagnostics_LogShortpathPublicCheckpoint` at `0x180155c3c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180155a63`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180155a63`

## string_xrefs

- `0x180155afb`: `StartDirectlyWithSideTransport`
- `0x180155b79`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x180155daa`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x180155d35`: `Failed spRdpIceToStackCallback->OnICESidebandDataAvailable`

## pseudocode

```c
void __fastcall SideTransportStream::SendSignalingChannelData(RTL_SRWLOCK *this, unsigned __int16 a2, const char *a3)
{
  int (__fastcall ***Ptr)(_QWORD, GUID *, __int64 *); // rbx
  int (__fastcall **v7)(_QWORD, GUID *, __int64 *); // rax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  int v11; // r8d
  int v12; // r9d
  int v13; // ecx
  __int64 v14; // rbx
  __int64 v15; // r8
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  const char *v19; // rax
  __int64 v20; // rdx
  unsigned int v21; // ecx
  __int64 v22; // r14
  __int64 v23; // r8
  __int64 v24; // r9
  __int128 v25; // xmm0
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  int v29; // edx
  int v30; // r8d
  int v31; // r9d
  __int64 v32; // [rsp+50h] [rbp-39h] BYREF
  const char *v33; // [rsp+58h] [rbp-31h] BYREF
  const char *v34; // [rsp+60h] [rbp-29h] BYREF
  const char *v35; // [rsp+68h] [rbp-21h] BYREF
  const char *v36; // [rsp+70h] [rbp-19h] BYREF
  int v37; // [rsp+78h] [rbp-11h] BYREF
  __int64 v38; // [rsp+80h] [rbp-9h] BYREF
  __int64 v39; // [rsp+88h] [rbp-1h] BYREF
  GUID ActivityId; // [rsp+90h] [rbp+7h] BYREF
  __int128 v41; // [rsp+A0h] [rbp+17h] BYREF

  CacNx::TCntPtr<ID3D11PixelShader>::TCntPtr<ID3D11PixelShader>(&v39, &this[4]);
  v38 = 0;
  v37 = 0;
  AcquireSRWLockExclusive(this + 11);
  v35 = (const char *)&this[11];
  Ptr = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))this[6].Ptr;
  if ( Ptr )
  {
    v7 = *Ptr;
    v38 = 0;
    if ( (*v7)(Ptr, &IID_IRDPENCPlatformContext, &v38) < 0 && (unsigned int)CallbackContext > 3 )
    {
      v32 = (__int64)"pPlatformContext->QueryInterface(IID_IRDPENCPlatformContext) failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v8,
        (unsigned int)byte_18029C515,
        v9,
        v10,
        (__int64)&v32);
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v35);
  v13 = v38;
  if ( v38
    && (*(int (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v38 + 32LL))(
         v38,
         L"StartDirectlyWithSideTransport",
         &v37) >= 0
    && v37 )
  {
    v14 = v39;
    if ( !v39 )
    {
      if ( a3 )
      {
        v15 = -1;
        do
          ++v15;
        while ( a3[v15] );
      }
      else
      {
        v15 = 0;
      }
      if ( !(unsigned __int8)utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::assign(
                               &this[16],
                               a3,
                               v15)
        && (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v35) = 721;
        v36 = "SendSignalingChannelData";
        LODWORD(v32) = -2147024882;
        v33 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
        v34 = "m_initialIceCandidates allocation failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v16,
          (unsigned int)byte_18029BE55,
          v17,
          v18,
          (__int64)&v34,
          (__int64)&v32,
          (__int64)&v33,
          (__int64)&v35,
          (__int64)&v36);
      }
      LOWORD(this[20].Ptr) = a2;
      goto LABEL_35;
    }
  }
  else
  {
    v14 = v39;
    if ( !v39 )
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        LODWORD(v32) = -2147467262;
        *(_QWORD *)&v41 = "SendSignalingChannelData";
        v34 = "Failed to get IRdpIceToStackCallback interface";
        v33 = "Error condition failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v13,
          (unsigned int)byte_18029B33D,
          v11,
          v12,
          (__int64)&v33,
          (__int64)&v34,
          (__int64)&v32,
          (__int64)&v41);
      }
      goto LABEL_35;
    }
  }
  if ( a3 )
  {
    v19 = a3;
    v20 = 0x7FFFFFFF;
    do
    {
      if ( !*v19 )
        break;
      ++v19;
      --v20;
    }
    while ( v20 );
    v11 = 0x7FFFFFFF - v20;
    v21 = v20 == 0 ? 0x80070057 : 0;
    v22 = (0x7FFFFFFF - v20) & -(__int64)(v20 != 0);
    if ( v20 )
    {
      RDPServerStackDiagnostics_LogShortpathPublicCheckpoint(&this[13], 715, a3, (unsigned int)v22);
      if ( (unsigned int)CallbackContext > 4
        && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL, v23, v24) )
      {
        v25 = (__int128)*RdpActivityId::GetCurrentActivityId(&ActivityId);
        v32 = 0x1000000;
        v34 = (const char *)&v41;
        v33 = "Udp";
        v36 = "Stack";
        v35 = "Checkpoint";
        v41 = v25;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
          v26,
          (unsigned int)&dword_18029BF4C,
          v27,
          v28,
          (__int64)&v35,
          (__int64)&v32,
          (__int64)&v36,
          (__int64)&v33,
          (__int64)&v34);
      }
      v29 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, const char *, _DWORD))(*(_QWORD *)v14 + 24LL))(
              v14,
              SideTransportStream::m_requestId,
              a2,
              a3,
              v22);
      if ( v29 < 0 && (unsigned int)CallbackContext > 3 )
      {
        LODWORD(v32) = v29;
        v34 = "SendSignalingChannelData";
        v33 = "Failed spRdpIceToStackCallback->OnICESidebandDataAvailable";
        v36 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)byte_18029CB35,
          v30,
          v31,
          (__int64)&v36,
          (__int64)&v33,
          (__int64)&v32,
          (__int64)&v34);
      }
      goto LABEL_35;
    }
  }
  else
  {
    v21 = -2147024809;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    LODWORD(v32) = 736;
    v34 = "StringCbLengthA failed.";
    LODWORD(v35) = v21;
    v33 = "SendSignalingChannelData";
    v36 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
    *(_QWORD *)&v41 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v21,
      (unsigned int)&byte_18029BAD7,
      v11,
      v12,
      (__int64)&v41,
      (__int64)&v35,
      (__int64)&v36,
      (__int64)&v32,
      (__int64)&v33,
      (__int64)&v34);
  }
LABEL_35:
  wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(&v38);
  wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(&v39);
}

```

## disassembly

```asm
0x180155a10  mov     [rsp-8+arg_18], rbx
0x180155a15  push    rbp
0x180155a16  push    rsi
0x180155a17  push    rdi
0x180155a18  push    r14
0x180155a1a  push    r15
0x180155a1c  lea     rbp, [rsp-37h]
0x180155a21  sub     rsp, 0C0h
0x180155a28  mov     rax, cs:__security_cookie
0x180155a2f  xor     rax, rsp
0x180155a32  mov     [rbp+57h+var_30], rax
0x180155a36  movzx   r15d, dx
0x180155a3a  mov     rsi, rcx
0x180155a3d  lea     rdx, [rcx+20h]
0x180155a41  mov     rdi, r8
0x180155a44  lea     rcx, [rbp+57h+var_58]
0x180155a48  call    ??0?$TCntPtr@UID3D11PixelShader@@@CacNx@@QEAA@AEBV01@@Z; CacNx::TCntPtr<ID3D11PixelShader>::TCntPtr<ID3D11PixelShader>(CacNx::TCntPtr<ID3D11PixelShader> const &)
0x180155a4d  lea     rbx, [rsi+58h]
0x180155a51  mov     [rbp+57h+var_60], 0
0x180155a59  mov     rcx, rbx; SRWLock
0x180155a5c  mov     [rbp+57h+var_68], 0
0x180155a63  call    cs:__imp_AcquireSRWLockExclusive
0x180155a69  mov     [rbp+57h+var_78], rbx
0x180155a6d  mov     rbx, [rsi+30h]
0x180155a71  test    rbx, rbx
0x180155a74  jz      short loc_180155ADE
0x180155a76  mov     rax, [rbx]
0x180155a79  mov     rcx, [rbp+57h+var_60]
0x180155a7d  mov     [rbp+57h+var_60], 0
0x180155a85  mov     r14, [rax]
0x180155a88  test    rcx, rcx
0x180155a8b  jz      short loc_180155A99
0x180155a8d  mov     rax, [rcx]
0x180155a90  mov     rax, [rax+10h]
0x180155a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155a99  lea     r8, [rbp+57h+var_60]
0x180155a9d  mov     rcx, rbx
0x180155aa0  lea     rdx, IID_IRDPENCPlatformContext
0x180155aa7  mov     rax, r14
0x180155aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155aaf  test    eax, eax
0x180155ab1  jns     short loc_180155ADE
0x180155ab3  mov     eax, cs:CallbackContext
0x180155ab9  cmp     eax, 3
0x180155abc  jbe     short loc_180155ADE
0x180155abe  lea     rax, aPplatformconte_1; "pPlatformContext->QueryInterface(IID_IR"...
0x180155ac5  mov     [rbp+57h+var_90], rax
0x180155ac9  lea     rdx, byte_18029C515
0x180155ad0  lea     rax, [rbp+57h+var_90]
0x180155ad4  mov     [rsp+0E0h+var_C0], rax
0x180155ad9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180155ade  lea     rcx, [rbp+57h+var_78]
0x180155ae2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180155ae7  mov     rcx, [rbp+57h+var_60]
0x180155aeb  test    rcx, rcx
0x180155aee  jz      loc_180155BD5
0x180155af4  mov     rax, [rcx]
0x180155af7  lea     r8, [rbp+57h+var_68]
0x180155afb  lea     rdx, aStartdirectlyw; "StartDirectlyWithSideTransport"
0x180155b02  mov     rax, [rax+20h]
0x180155b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155b0b  test    eax, eax
0x180155b0d  js      loc_180155BD5
0x180155b13  cmp     [rbp+57h+var_68], 0
0x180155b17  jz      loc_180155BD5
0x180155b1d  mov     rbx, [rbp+57h+var_58]
0x180155b21  test    rbx, rbx
0x180155b24  jnz     loc_180155BE2
0x180155b2a  lea     rcx, [rsi+80h]
0x180155b31  test    rdi, rdi
0x180155b34  jz      short loc_180155B46
0x180155b36  or      r8, 0FFFFFFFFFFFFFFFFh
0x180155b3a  inc     r8
0x180155b3d  cmp     byte ptr [rdi+r8], 0
0x180155b42  jnz     short loc_180155B3A
0x180155b44  jmp     short loc_180155B49
0x180155b46  xor     r8d, r8d
0x180155b49  mov     rdx, rdi
0x180155b4c  call    ?assign@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@QEAA_NPEBD_K@Z; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::assign(char const *,unsigned __int64)
0x180155b51  test    al, al
0x180155b53  jnz     short loc_180155BC8
0x180155b55  mov     eax, cs:CallbackContext
0x180155b5b  cmp     eax, 2
0x180155b5e  jbe     short loc_180155BC8
0x180155b60  lea     rax, aSendsignalingc; "SendSignalingChannelData"
0x180155b67  mov     dword ptr [rbp+57h+var_78], 2D1h
0x180155b6e  mov     [rbp+57h+var_70], rax
0x180155b72  lea     rdx, byte_18029BE55
0x180155b79  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180155b80  mov     dword ptr [rbp+57h+var_90], 8007000Eh
0x180155b87  mov     [rbp+57h+var_88], rax
0x180155b8b  lea     rax, aMInitialicecan; "m_initialIceCandidates allocation faile"...
0x180155b92  mov     [rbp+57h+var_80], rax
0x180155b96  lea     rax, [rbp+57h+var_70]
0x180155b9a  mov     [rsp+0E0h+var_A0], rax
0x180155b9f  lea     rax, [rbp+57h+var_78]
0x180155ba3  mov     [rsp+0E0h+var_A8], rax
0x180155ba8  lea     rax, [rbp+57h+var_88]
0x180155bac  mov     [rsp+0E0h+var_B0], rax
0x180155bb1  lea     rax, [rbp+57h+var_90]
0x180155bb5  mov     [rsp+0E0h+var_B8], rax
0x180155bba  lea     rax, [rbp+57h+var_80]
0x180155bbe  mov     [rsp+0E0h+var_C0], rax
0x180155bc3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180155bc8  mov     [rsi+0A0h], r15w
0x180155bd0  jmp     loc_180155E60
0x180155bd5  mov     rbx, [rbp+57h+var_58]
0x180155bd9  test    rbx, rbx
0x180155bdc  jz      loc_180155DFD
0x180155be2  test    rdi, rdi
0x180155be5  jz      loc_180155D6F
0x180155beb  mov     r8d, 7FFFFFFFh
0x180155bf1  mov     rax, rdi
0x180155bf4  mov     edx, r8d
0x180155bf7  cmp     byte ptr [rax], 0
0x180155bfa  jz      short loc_180155C05
0x180155bfc  inc     rax
0x180155bff  sub     rdx, 1
0x180155c03  jnz     short loc_180155BF7
0x180155c05  mov     rax, rdx
0x180155c08  neg     rax
0x180155c0b  mov     rax, rdx
0x180155c0e  sbb     ecx, ecx
0x180155c10  sub     r8, rdx
0x180155c13  not     ecx
0x180155c15  and     ecx, 80070057h
0x180155c1b  neg     rax
0x180155c1e  sbb     r14, r14
0x180155c21  and     r14, r8
0x180155c24  test    rdx, rdx
0x180155c27  jz      loc_180155D74
0x180155c2d  lea     rcx, [rsi+68h]
0x180155c31  mov     r9d, r14d
0x180155c34  mov     r8, rdi
0x180155c37  mov     edx, 2CBh
0x180155c3c  call    cs:__imp_RDPServerStackDiagnostics_LogShortpathPublicCheckpoint
0x180155c42  mov     eax, cs:CallbackContext
0x180155c48  cmp     eax, 4
0x180155c4b  jbe     loc_180155CE6
0x180155c51  mov     rdx, 470000000000h
0x180155c5b  lea     rcx, CallbackContext
0x180155c62  call    _tlgKeywordOn
0x180155c67  test    al, al
0x180155c69  jz      short loc_180155CE6
0x180155c6b  lea     rcx, [rbp+57h+ActivityId]; ActivityId
0x180155c6f  call    ?GetCurrentActivityId@RdpActivityId@@SA?AU_GUID@@XZ; RdpActivityId::GetCurrentActivityId(void)
0x180155c74  lea     rdx, dword_18029BF4C
0x180155c7b  movups  xmm0, xmmword ptr [rax]
0x180155c7e  lea     rax, [rbp+57h+var_40]
0x180155c82  mov     [rbp+57h+var_90], 1000000h
0x180155c8a  mov     [rbp+57h+var_80], rax
0x180155c8e  lea     rax, aUdp; "Udp"
0x180155c95  mov     [rbp+57h+var_88], rax
0x180155c99  lea     rax, aStack; "Stack"
0x180155ca0  mov     [rbp+57h+var_70], rax
0x180155ca4  lea     rax, aCheckpoint; "Checkpoint"
0x180155cab  mov     [rbp+57h+var_78], rax
0x180155caf  lea     rax, [rbp+57h+var_80]
0x180155cb3  mov     [rsp+0E0h+var_A0], rax
0x180155cb8  lea     rax, [rbp+57h+var_88]
0x180155cbc  mov     [rsp+0E0h+var_A8], rax
0x180155cc1  lea     rax, [rbp+57h+var_70]
0x180155cc5  mov     [rsp+0E0h+var_B0], rax
0x180155cca  lea     rax, [rbp+57h+var_90]
0x180155cce  mov     [rsp+0E0h+var_B8], rax
0x180155cd3  lea     rax, [rbp+57h+var_78]
0x180155cd7  mov     [rsp+0E0h+var_C0], rax
0x180155cdc  movdqu  [rbp+57h+var_40], xmm0
0x180155ce1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &)
0x180155ce6  mov     rax, [rbx]
0x180155ce9  mov     r9, rdi
0x180155cec  mov     edx, cs:?m_requestId@SideTransportStream@@0IA; uint SideTransportStream::m_requestId
0x180155cf2  movzx   r8d, r15w
0x180155cf6  mov     rcx, rbx
0x180155cf9  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x180155cfe  mov     rax, [rax+18h]
0x180155d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155d07  mov     edx, eax
0x180155d09  test    eax, eax
0x180155d0b  jns     loc_180155E60
0x180155d11  mov     ecx, cs:CallbackContext
0x180155d17  cmp     ecx, 3
0x180155d1a  jbe     loc_180155E60
0x180155d20  lea     rax, aSendsignalingc; "SendSignalingChannelData"
0x180155d27  mov     dword ptr [rbp+57h+var_90], edx
0x180155d2a  mov     [rbp+57h+var_80], rax
0x180155d2e  lea     rdx, byte_18029CB35
0x180155d35  lea     rax, aFailedSprdpice_0; "Failed spRdpIceToStackCallback->OnICESi"...
0x180155d3c  mov     [rbp+57h+var_88], rax
0x180155d40  lea     rax, aWarningHresult; "Warning HResult failed"
0x180155d47  mov     [rbp+57h+var_70], rax
0x180155d4b  lea     rax, [rbp+57h+var_80]
0x180155d4f  mov     [rsp+0E0h+var_A8], rax
0x180155d54  lea     rax, [rbp+57h+var_90]
0x180155d58  mov     [rsp+0E0h+var_B0], rax
0x180155d5d  lea     rax, [rbp+57h+var_88]
0x180155d61  mov     [rsp+0E0h+var_B8], rax
0x180155d66  lea     rax, [rbp+57h+var_70]
0x180155d6a  jmp     loc_180155E56
0x180155d6f  mov     ecx, 80070057h
0x180155d74  mov     eax, cs:CallbackContext
0x180155d7a  cmp     eax, 2
0x180155d7d  jbe     loc_180155E60
0x180155d83  lea     rax, aStringcblength; "StringCbLengthA failed."
0x180155d8a  mov     dword ptr [rbp+57h+var_90], 2E0h
0x180155d91  mov     [rbp+57h+var_80], rax
0x180155d95  lea     rdx, byte_18029BAD7
0x180155d9c  lea     rax, aSendsignalingc; "SendSignalingChannelData"
0x180155da3  mov     dword ptr [rbp+57h+var_78], ecx
0x180155da6  mov     [rbp+57h+var_88], rax
0x180155daa  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180155db1  mov     [rbp+57h+var_70], rax
0x180155db5  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180155dbc  mov     qword ptr [rbp+57h+var_40], rax
0x180155dc0  lea     rax, [rbp+57h+var_80]
0x180155dc4  mov     [rsp+0E0h+var_98], rax
0x180155dc9  lea     rax, [rbp+57h+var_88]
0x180155dcd  mov     [rsp+0E0h+var_A0], rax
0x180155dd2  lea     rax, [rbp+57h+var_90]
0x180155dd6  mov     [rsp+0E0h+var_A8], rax
0x180155ddb  lea     rax, [rbp+57h+var_70]
0x180155ddf  mov     [rsp+0E0h+var_B0], rax
0x180155de4  lea     rax, [rbp+57h+var_78]
0x180155de8  mov     [rsp+0E0h+var_B8], rax
0x180155ded  lea     rax, [rbp+57h+var_40]
0x180155df1  mov     [rsp+0E0h+var_C0], rax
0x180155df6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180155dfb  jmp     short loc_180155E60
0x180155dfd  mov     eax, cs:CallbackContext
0x180155e03  cmp     eax, 3
0x180155e06  jbe     short loc_180155E60
0x180155e08  lea     rax, aSendsignalingc; "SendSignalingChannelData"
0x180155e0f  mov     dword ptr [rbp+57h+var_90], 80004002h
0x180155e16  mov     qword ptr [rbp+57h+var_40], rax
0x180155e1a  lea     rdx, byte_18029B33D
0x180155e21  lea     rax, aFailedToGetIrd_1; "Failed to get IRdpIceToStackCallback in"...
0x180155e28  mov     [rbp+57h+var_80], rax
0x180155e2c  lea     rax, aErrorCondition; "Error condition failed"
0x180155e33  mov     [rbp+57h+var_88], rax
0x180155e37  lea     rax, [rbp+57h+var_40]
0x180155e3b  mov     [rsp+0E0h+var_A8], rax
0x180155e40  lea     rax, [rbp+57h+var_90]
0x180155e44  mov     [rsp+0E0h+var_B0], rax
0x180155e49  lea     rax, [rbp+57h+var_80]
0x180155e4d  mov     [rsp+0E0h+var_B8], rax
0x180155e52  lea     rax, [rbp+57h+var_88]
0x180155e56  mov     [rsp+0E0h+var_C0], rax
0x180155e5b  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180155e60  lea     rcx, [rbp+57h+var_60]
0x180155e64  call    ??1?$com_ptr_t@UIRDPCollection@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(void)
0x180155e69  lea     rcx, [rbp+57h+var_58]
0x180155e6d  call    ??1?$com_ptr_t@UIRDPCollection@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(void)
0x180155e72  mov     rcx, [rbp+57h+var_30]
0x180155e76  xor     rcx, rsp; StackCookie
0x180155e79  call    __security_check_cookie
0x180155e7e  mov     rbx, [rsp+0E0h+arg_18]
0x180155e86  add     rsp, 0C0h
0x180155e8d  pop     r15
0x180155e8f  pop     r14
0x180155e91  pop     rdi
0x180155e92  pop     rsi
0x180155e93  pop     rbp
0x180155e94  retn
```
