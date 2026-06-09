# SideTransportStream::OnReadCompleted(IRdpNanoStreamBuffer *)

- ea: `0x180154bf0`
- end: `0x180154f47`
- name: `?OnReadCompleted@SideTransportStream@@UEAAXPEAUIRdpNanoStreamBuffer@@@Z`
- size: `855`
- prototype: `void(SideTransportStream *__hidden this, struct IRdpNanoStreamBuffer *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000116c`
- `0x1800a3474`
- `0x1800d4788`
- `0x180150ea0`
- `0x180150ef0`
- `0x180152b54`
- `0x180154bf0`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180154de1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180154e8b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180154de1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180154e8b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180154d74`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180154d74`

## string_xrefs

- `0x180154c36`: `OnReadCompleted`
- `0x180154ceb`: `OnReadCompleted`
- `0x180154eb1`: `OnReadCompleted`
- `0x180154c4f`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x180154d00`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x180154eca`: `onecore\termsrv\rdpplatform\rdpenc\transports\sidetransportstream\sidetransportstream.cpp`
- `0x180154d12`: `RDPENCNetStreamBufferAdapter::CreateInstance failed`
- `0x180154edc`: `SideTransportStream::OnReadCompleted error invalid parameter (contents)`
- `0x180154c61`: `SideTransportStream::OnReadCompleted error invalid parameter`

## pseudocode

```c
void __fastcall SideTransportStream::OnReadCompleted(
        RTL_SRWLOCK *this,
        struct IRdpNanoStreamBuffer *a2,
        int a3,
        int a4)
{
  int v6; // edi
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  int v10; // eax
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rbx
  __int64 v14; // rdi
  __int64 v15; // [rsp+50h] [rbp-30h] BYREF
  __int64 v16; // [rsp+58h] [rbp-28h] BYREF
  __int64 v17; // [rsp+60h] [rbp-20h] BYREF
  const char *v18; // [rsp+68h] [rbp-18h] BYREF
  const char *v19; // [rsp+70h] [rbp-10h] BYREF
  const char *v20; // [rsp+78h] [rbp-8h] BYREF
  RTL_SRWLOCK *v21; // [rsp+A8h] [rbp+28h] BYREF
  int v22; // [rsp+B0h] [rbp+30h] BYREF
  struct IRDPENCNetStreamBuffer *v23; // [rsp+B8h] [rbp+38h] BYREF

  v17 = 0;
  v16 = 0;
  v15 = 0;
  if ( a2 )
  {
    v6 = (*(__int64 (__fastcall **)(struct IRdpNanoStreamBuffer *))(*(_QWORD *)a2 + 40LL))(a2);
    if ( (*(__int64 (__fastcall **)(struct IRdpNanoStreamBuffer *))(*(_QWORD *)a2 + 24LL))(a2) && v6 )
    {
      v23 = 0;
      v10 = RDPENCNetStreamBufferAdapter::CreateInstance(a2, &v23);
      if ( v10 >= 0 )
      {
        (*(void (__fastcall **)(struct IRDPENCNetStreamBuffer *, _QWORD))(*(_QWORD *)v23 + 8LL))(v23, (unsigned int)v10);
        AcquireSRWLockExclusive(this + 11);
        v21 = this + 11;
        wil::com_ptr_t<IRdpNanoServerTransport,wil::err_returncode_policy>::operator=(&v16, &this[8]);
        wil::com_ptr_t<IRDPENCNetStreamEvents,wil::err_returncode_policy>::operator=(&v17, this[5].Ptr);
        wil::com_ptr_t<IRdpNanoServerTransport,wil::err_returncode_policy>::operator=(&v15, &this[9]);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v21);
        if ( v17 )
          (*(void (__fastcall **)(__int64, struct IRDPENCNetStreamBuffer *))(*(_QWORD *)v17 + 32LL))(v17, v23);
        v13 = v16;
        if ( v16 )
        {
          HIDWORD(this[22].Ptr) += 8 * v6;
          if ( GetTickCount() - HIDWORD(this[27].Ptr) > 0x64 )
          {
            (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v13 + 32LL))(v13, 106, HIDWORD(this[22].Ptr));
            (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v13 + 32LL))(v13, 104, HIDWORD(this[22].Ptr));
            (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v13 + 32LL))(
              v13,
              124,
              HIDWORD(this[22].Ptr) >> 3);
            if ( v15 )
            {
              v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 136LL))(v15);
              (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v13 + 32LL))(
                v13,
                107,
                (unsigned int)(v14 - LODWORD(this[26].Ptr)));
              this[26].Ptr = (PVOID)v14;
            }
            HIDWORD(this[27].Ptr) = GetTickCount();
            HIDWORD(this[22].Ptr) = 0;
          }
        }
      }
      else if ( (unsigned int)CallbackContext > 2 )
      {
        v22 = v10;
        v20 = "OnReadCompleted";
        LODWORD(v21) = 1331;
        v19 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
        v18 = "RDPENCNetStreamBufferAdapter::CreateInstance failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)CallbackContext,
          (unsigned int)&word_18029C966,
          v11,
          v12,
          (__int64)&v18,
          (__int64)&v22,
          (__int64)&v19,
          (__int64)&v21,
          (__int64)&v20);
      }
      wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(&v23);
    }
    else if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v21) = 1297;
      v20 = "OnReadCompleted";
      v22 = -2147467261;
      v19 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
      v18 = "SideTransportStream::OnReadCompleted error invalid parameter (contents)";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v7,
        (unsigned int)&dword_18029CD1C,
        v8,
        v9,
        (__int64)&v18,
        (__int64)&v22,
        (__int64)&v19,
        (__int64)&v21,
        (__int64)&v20);
    }
  }
  else if ( (unsigned int)CallbackContext > 2 )
  {
    LODWORD(v21) = 1287;
    v18 = "OnReadCompleted";
    v22 = -2147024809;
    v19 = "onecore\\termsrv\\rdpplatform\\rdpenc\\transports\\sidetransportstream\\sidetransportstream.cpp";
    v20 = "SideTransportStream::OnReadCompleted error invalid parameter";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (_DWORD)this,
      (unsigned int)&word_18029CA6E,
      a3,
      a4,
      (__int64)&v20,
      (__int64)&v22,
      (__int64)&v19,
      (__int64)&v21,
      (__int64)&v18);
  }
  wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(&v15);
  wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(&v16);
  wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(&v17);
}

```

## disassembly

```asm
0x180154bf0  mov     r11, rsp
0x180154bf3  mov     [r11+8], rbx
0x180154bf7  push    rbp
0x180154bf8  push    rsi
0x180154bf9  push    rdi
0x180154bfa  mov     rbp, rsp
0x180154bfd  sub     rsp, 80h
0x180154c04  mov     [rbp+var_20], 0
0x180154c0c  mov     rbx, rdx
0x180154c0f  mov     [rbp+var_28], 0
0x180154c17  mov     rsi, rcx
0x180154c1a  mov     [rbp+var_30], 0
0x180154c22  test    rdx, rdx
0x180154c25  jnz     short loc_180154C95
0x180154c27  mov     eax, cs:CallbackContext
0x180154c2d  cmp     eax, 2
0x180154c30  jbe     loc_180154F19
0x180154c36  lea     rax, aOnreadcomplete; "OnReadCompleted"
0x180154c3d  mov     dword ptr [rbp+arg_8], 507h
0x180154c44  mov     [rbp+var_18], rax
0x180154c48  lea     rdx, word_18029CA6E
0x180154c4f  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180154c56  mov     [rbp+arg_10], 80070057h
0x180154c5d  mov     [rbp+var_10], rax
0x180154c61  lea     rax, aSidetransports_6; "SideTransportStream::OnReadCompleted er"...
0x180154c68  mov     [rbp+var_8], rax
0x180154c6c  lea     rax, [rbp+var_18]
0x180154c70  mov     [r11-58h], rax
0x180154c74  lea     rax, [rbp+arg_8]
0x180154c78  mov     [r11-60h], rax
0x180154c7c  lea     rax, [rbp+var_10]
0x180154c80  mov     [r11-68h], rax
0x180154c84  lea     rax, [rbp+arg_10]
0x180154c88  mov     [r11-70h], rax
0x180154c8c  lea     rax, [rbp+var_8]
0x180154c90  jmp     loc_180154F0F
0x180154c95  mov     rax, [rdx]
0x180154c98  mov     rcx, rbx
0x180154c9b  mov     rax, [rax+28h]
0x180154c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154ca4  mov     rcx, [rbx]
0x180154ca7  mov     edi, eax
0x180154ca9  mov     rax, [rcx+18h]
0x180154cad  mov     rcx, rbx
0x180154cb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154cb5  test    rax, rax
0x180154cb8  jz      loc_180154EA6
0x180154cbe  test    edi, edi
0x180154cc0  jz      loc_180154EA6
0x180154cc6  lea     rdx, [rbp+arg_18]; struct IRDPENCNetStreamBuffer **
0x180154cca  mov     [rbp+arg_18], 0
0x180154cd2  mov     rcx, rbx; struct IRdpNanoStreamBuffer *
0x180154cd5  call    ?CreateInstance@RDPENCNetStreamBufferAdapter@@SAJPEAUIRdpNanoStreamBuffer@@PEAPEAUIRDPENCNetStreamBuffer@@@Z; RDPENCNetStreamBufferAdapter::CreateInstance(IRdpNanoStreamBuffer *,IRDPENCNetStreamBuffer * *)
0x180154cda  mov     edx, eax
0x180154cdc  test    eax, eax
0x180154cde  jns     short loc_180154D5D
0x180154ce0  mov     ecx, cs:CallbackContext
0x180154ce6  cmp     ecx, 2
0x180154ce9  jbe     short loc_180154D4F
0x180154ceb  lea     rax, aOnreadcomplete; "OnReadCompleted"
0x180154cf2  mov     [rbp+arg_10], edx
0x180154cf5  mov     [rbp+var_8], rax
0x180154cf9  lea     rdx, word_18029C966
0x180154d00  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180154d07  mov     dword ptr [rbp+arg_8], 533h
0x180154d0e  mov     [rbp+var_10], rax
0x180154d12  lea     rax, aRdpencnetstrea; "RDPENCNetStreamBufferAdapter::CreateIns"...
0x180154d19  mov     [rbp+var_18], rax
0x180154d1d  lea     rax, [rbp+var_8]
0x180154d21  mov     [rsp+80h+var_40], rax
0x180154d26  lea     rax, [rbp+arg_8]
0x180154d2a  mov     [rsp+80h+var_48], rax
0x180154d2f  lea     rax, [rbp+var_10]
0x180154d33  mov     [rsp+80h+var_50], rax
0x180154d38  lea     rax, [rbp+arg_10]
0x180154d3c  mov     [rsp+80h+var_58], rax
0x180154d41  lea     rax, [rbp+var_18]
0x180154d45  mov     [rsp+80h+var_60], rax
0x180154d4a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180154d4f  lea     rcx, [rbp+arg_18]
0x180154d53  call    ??1?$com_ptr_t@UIRDPCollection@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(void)
0x180154d58  jmp     loc_180154F19
0x180154d5d  mov     rcx, [rbp+arg_18]
0x180154d61  mov     rax, [rcx]
0x180154d64  mov     rax, [rax+8]
0x180154d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154d6d  lea     rbx, [rsi+58h]
0x180154d71  mov     rcx, rbx; SRWLock
0x180154d74  call    cs:__imp_AcquireSRWLockExclusive
0x180154d7a  lea     rdx, [rsi+40h]
0x180154d7e  mov     [rbp+arg_8], rbx
0x180154d82  lea     rcx, [rbp+var_28]
0x180154d86  call    ??4?$com_ptr_t@UIRdpNanoServerTransport@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IRdpNanoServerTransport,wil::err_returncode_policy>::operator=(wil::com_ptr_t<IRdpNanoServerTransport,wil::err_returncode_policy> const &)
0x180154d8b  mov     rdx, [rsi+28h]
0x180154d8f  lea     rcx, [rbp+var_20]
0x180154d93  call    ??4?$com_ptr_t@UIRDPENCNetStreamEvents@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIRDPENCNetStreamEvents@@@Z; wil::com_ptr_t<IRDPENCNetStreamEvents,wil::err_returncode_policy>::operator=(IRDPENCNetStreamEvents *)
0x180154d98  lea     rdx, [rsi+48h]
0x180154d9c  lea     rcx, [rbp+var_30]
0x180154da0  call    ??4?$com_ptr_t@UIRdpNanoServerTransport@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IRdpNanoServerTransport,wil::err_returncode_policy>::operator=(wil::com_ptr_t<IRdpNanoServerTransport,wil::err_returncode_policy> const &)
0x180154da5  lea     rcx, [rbp+arg_8]
0x180154da9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180154dae  mov     rcx, [rbp+var_20]
0x180154db2  test    rcx, rcx
0x180154db5  jz      short loc_180154DC7
0x180154db7  mov     rax, [rcx]
0x180154dba  mov     rdx, [rbp+arg_18]
0x180154dbe  mov     rax, [rax+20h]
0x180154dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154dc7  mov     rbx, [rbp+var_28]
0x180154dcb  test    rbx, rbx
0x180154dce  jz      loc_180154D4F
0x180154dd4  lea     eax, ds:0[rdi*8]
0x180154ddb  add     [rsi+0B4h], eax
0x180154de1  call    cs:__imp_GetTickCount
0x180154de7  sub     eax, [rsi+0DCh]
0x180154ded  cmp     eax, 64h ; 'd'
0x180154df0  jbe     loc_180154D4F
0x180154df6  mov     rax, [rbx]
0x180154df9  mov     edx, 6Ah ; 'j'
0x180154dfe  mov     r8d, [rsi+0B4h]
0x180154e05  mov     rcx, rbx
0x180154e08  mov     rax, [rax+20h]
0x180154e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154e11  mov     rax, [rbx]
0x180154e14  mov     edx, 68h ; 'h'
0x180154e19  mov     r8d, [rsi+0B4h]
0x180154e20  mov     rcx, rbx
0x180154e23  mov     rax, [rax+20h]
0x180154e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154e2c  mov     rax, [rbx]
0x180154e2f  mov     edx, 7Ch ; '|'
0x180154e34  mov     r8d, [rsi+0B4h]
0x180154e3b  mov     rcx, rbx
0x180154e3e  shr     r8d, 3
0x180154e42  mov     rax, [rax+20h]
0x180154e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154e4b  mov     rcx, [rbp+var_30]
0x180154e4f  test    rcx, rcx
0x180154e52  jz      short loc_180154E8B
0x180154e54  mov     rax, [rcx]
0x180154e57  mov     rax, [rax+88h]
0x180154e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154e63  mov     rcx, [rbx]
0x180154e66  mov     r8d, eax
0x180154e69  sub     r8d, [rsi+0D0h]
0x180154e70  mov     rdi, rax
0x180154e73  mov     edx, 6Bh ; 'k'
0x180154e78  mov     rax, [rcx+20h]
0x180154e7c  mov     rcx, rbx
0x180154e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154e84  mov     [rsi+0D0h], rdi
0x180154e8b  call    cs:__imp_GetTickCount
0x180154e91  mov     [rsi+0DCh], eax
0x180154e97  mov     dword ptr [rsi+0B4h], 0
0x180154ea1  jmp     loc_180154D4F
0x180154ea6  mov     eax, cs:CallbackContext
0x180154eac  cmp     eax, 2
0x180154eaf  jbe     short loc_180154F19
0x180154eb1  lea     rax, aOnreadcomplete; "OnReadCompleted"
0x180154eb8  mov     dword ptr [rbp+arg_8], 511h
0x180154ebf  mov     [rbp+var_8], rax
0x180154ec3  lea     rdx, dword_18029CD1C
0x180154eca  lea     rax, aOnecoreTermsrv_41; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180154ed1  mov     [rbp+arg_10], 80004003h
0x180154ed8  mov     [rbp+var_10], rax
0x180154edc  lea     rax, aSidetransports_8; "SideTransportStream::OnReadCompleted er"...
0x180154ee3  mov     [rbp+var_18], rax
0x180154ee7  lea     rax, [rbp+var_8]
0x180154eeb  mov     [rsp+80h+var_40], rax
0x180154ef0  lea     rax, [rbp+arg_8]
0x180154ef4  mov     [rsp+80h+var_48], rax
0x180154ef9  lea     rax, [rbp+var_10]
0x180154efd  mov     [rsp+80h+var_50], rax
0x180154f02  lea     rax, [rbp+arg_10]
0x180154f06  mov     [rsp+80h+var_58], rax
0x180154f0b  lea     rax, [rbp+var_18]
0x180154f0f  mov     [rsp+80h+var_60], rax
0x180154f14  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180154f19  lea     rcx, [rbp+var_30]
0x180154f1d  call    ??1?$com_ptr_t@UIRDPCollection@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(void)
0x180154f22  lea     rcx, [rbp+var_28]
0x180154f26  call    ??1?$com_ptr_t@UIRDPCollection@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(void)
0x180154f2b  lea     rcx, [rbp+var_20]
0x180154f2f  call    ??1?$com_ptr_t@UIRDPCollection@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IRDPCollection,wil::err_returncode_policy>::~com_ptr_t<IRDPCollection,wil::err_returncode_policy>(void)
0x180154f34  mov     rbx, [rsp+80h+arg_0]
0x180154f3c  add     rsp, 80h
0x180154f43  pop     rdi
0x180154f44  pop     rsi
0x180154f45  pop     rbp
0x180154f46  retn
```
