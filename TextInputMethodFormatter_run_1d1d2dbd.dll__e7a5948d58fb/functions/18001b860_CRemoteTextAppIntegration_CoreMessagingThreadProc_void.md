# CRemoteTextAppIntegration::CoreMessagingThreadProc(void *)

- ea: `0x18001b860`
- end: `0x18001bf5e`
- name: `?CoreMessagingThreadProc@CRemoteTextAppIntegration@@CAKPEAX@Z`
- size: `1790`
- prototype: `__int64 __fastcall(char *Parameter, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180002240`
- `0x180002270`
- `0x180006a14`
- `0x180012030`
- `0x180012050`
- `0x1800148f0`
- `0x1800191fc`
- `0x18001b860`
- `0x180028b14`
- `0x180028d64`
- `0x18002bd40`
- `0x18002e7a8`
- `0x18002fc94`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001bdfd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001bdfd`
- `CoreMessaging!CoreUICreate` at `0x18001b8cb`
- `CoreMessaging!CoreUICreate` at `0x18001b8cb`
- `CoreUIComponents!CoreUIFactoryCreate` at `0x18001b8fc`
- `CoreUIComponents!CoreUIFactoryCreate` at `0x18001b8fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRemoteTextAppIntegration::CoreMessagingThreadProc(
        char *Parameter,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  char *v5; // rdi
  __int64 v6; // rcx
  int v7; // eax
  struct IMessagePort **v8; // rbx
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  int v12; // eax
  char *v13; // r15
  int v14; // eax
  RemoteAppIntegrationServer *v15; // rbx
  RemoteAppIntegrationServer *v16; // rax
  int v17; // r12d
  int v18; // esi
  RemoteAppIntegrationServer *v19; // rdi
  __int64 v20; // rdi
  __int64 v21; // rcx
  __int64 v22; // rcx
  char *v23; // rsi
  char *v24; // rax
  char *v25; // rdi
  int v26; // r15d
  __int64 v27; // rax
  __int64 v28; // rcx
  GUID *v29; // rdi
  GUID *v30; // rax
  GUID *v31; // r15
  __int64 v32; // rax
  __int64 v33; // r15
  __int64 v34; // rcx
  int MessageObject; // eax
  int v36; // eax
  __int64 v37; // rcx
  __int64 v38; // rcx
  int v39; // eax
  int v41; // [rsp+20h] [rbp-A9h]
  struct _GUID v42; // [rsp+30h] [rbp-99h] BYREF
  struct IMessagePort *v43; // [rsp+40h] [rbp-89h] BYREF
  struct _GUID v44; // [rsp+50h] [rbp-79h] BYREF
  _OWORD v45[2]; // [rsp+80h] [rbp-49h] BYREF
  __int64 v46; // [rsp+A0h] [rbp-29h]
  __int128 v47; // [rsp+B0h] [rbp-19h] BYREF
  __int128 v48; // [rsp+C0h] [rbp-9h]
  __int64 v49; // [rsp+D0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  if ( Parameter )
    (*(void (__fastcall **)(char *, __int64, __int64, const char *))(*(_QWORD *)Parameter + 8LL))(Parameter, a2, a3, a4);
  if ( !Parameter )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x53,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remotetextappintegration.cpp",
      a4);
  v5 = Parameter + 40;
  v6 = *((_QWORD *)Parameter + 5);
  if ( v6 )
  {
    *(_QWORD *)v5 = 0;
    (*(void (__fastcall **)(__int64, __int64, __int64, const char *))(*(_QWORD *)v6 + 16LL))(v6, a2, a3, a4);
  }
  v7 = CoreUICreate(Parameter + 40);
  if ( v7 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remotetextappintegration.cpp",
      (const char *)(unsigned int)v7,
      v41);
  v8 = (struct IMessagePort **)(Parameter + 48);
  v9 = *((_QWORD *)Parameter + 6);
  if ( v9 )
  {
    *v8 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v10 = CoreUIFactoryCreate(Parameter + 48);
  if ( v10 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remotetextappintegration.cpp",
      (const char *)(unsigned int)v10,
      v41);
  v11 = (*(__int64 (__fastcall **)(_QWORD, void *, char *, char *))(**(_QWORD **)v5 + 112LL))(
          *(_QWORD *)v5,
          &IRemoteTextInputServer_ToPdu::OnHotKeyRegistrationChanged,
          Parameter,
          Parameter + 56);
  if ( v11 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remotetextappintegration.cpp",
      (const char *)(unsigned int)v11,
      v41);
  v12 = SharedMessagePortRefPtr::Initialize(Parameter + 64, 0);
  if ( v12 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remotetextappintegration.cpp",
      (const char *)(unsigned int)v12,
      v41);
  v13 = Parameter + 104;
  if ( !*((_QWORD *)Parameter + 13) )
  {
    *(_QWORD *)&v42.Data1 = *(_QWORD *)v5;
    v43 = *v8;
    *(_QWORD *)&v44.Data1 = *((_QWORD *)Parameter + 9);
    v14 = Microsoft::WRL::Details::MakeAndInitialize<RemoteAppIntegrationClientManager,RemoteAppIntegrationClientManager,_GUID &,IMessagePort *,IMessageFactory *,IMessageSession *>(
            (int)Parameter + 104,
            (int)Parameter + 896,
            (unsigned int)&v44,
            (unsigned int)&v43,
            (__int64)&v42);
    if ( v14 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remotetextappintegration.cpp",
        (const char *)(unsigned int)v14,
        v41);
  }
  v15 = 0;
  v16 = (RemoteAppIntegrationServer *)operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
  v17 = -2147024882;
  if ( v16 )
  {
    v19 = RemoteAppIntegrationServer::RemoteAppIntegrationServer(v16);
    v44 = (struct _GUID)*((_OWORD *)Parameter + 56);
    v18 = RemoteAppIntegrationServer::RuntimeClassInitialize(v19, &v44);
    if ( v18 >= 0 )
    {
      if ( v19 )
        (*(void (__fastcall **)(RemoteAppIntegrationServer *))(*(_QWORD *)v19 + 8LL))(v19);
      v15 = v19;
      if ( v19 )
        (*(void (__fastcall **)(RemoteAppIntegrationServer *))(*(_QWORD *)v19 + 16LL))(v19);
      v18 = 0;
    }
    else if ( v19 )
    {
      (*(void (__fastcall **)(RemoteAppIntegrationServer *))(*(_QWORD *)v19 + 16LL))(v19);
    }
  }
  else
  {
    v18 = -2147024882;
  }
  if ( v18 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remotetextappintegration.cpp",
      (const char *)(unsigned int)v18,
      v41);
  v20 = *(_QWORD *)v13;
  if ( *(RemoteAppIntegrationServer **)(*(_QWORD *)v13 + 16LL) != v15 )
  {
    if ( v15 )
      (*(void (__fastcall **)(RemoteAppIntegrationServer *))(*(_QWORD *)v15 + 8LL))(v15);
    v21 = *(_QWORD *)(v20 + 16);
    *(_QWORD *)(v20 + 16) = v15;
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  if ( *((RemoteAppIntegrationServer **)Parameter + 14) != v15 )
  {
    if ( v15 )
      (*(void (__fastcall **)(RemoteAppIntegrationServer *))(*(_QWORD *)v15 + 8LL))(v15);
    v22 = *((_QWORD *)Parameter + 14);
    *((_QWORD *)Parameter + 14) = v15;
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  }
  v23 = 0;
  v24 = (char *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  v25 = v24;
  if ( v24 )
  {
    *((_DWORD *)v24 + 5) = 1;
    *(_QWORD *)v24 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRemoteCoreInputViewManager,IMessageProxyReconnectAdapterOwner>::`vftable'{for `IRemoteCoreInputViewManager'};
    *((_QWORD *)v24 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRemoteCoreInputViewManager,IMessageProxyReconnectAdapterOwner>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMessageProxyReconnectAdapterOwner>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v25 = &RemoteAppIntegrationViewForwarder::`vftable'{for `IRemoteCoreInputViewManager'};
    *((_QWORD *)v25 + 1) = &RemoteAppIntegrationViewForwarder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMessageProxyReconnectAdapterOwner>'};
    *((_QWORD *)v25 + 3) = 0;
    *((_QWORD *)v25 + 4) = 0;
    *((_QWORD *)v25 + 5) = 0;
    *((_QWORD *)v25 + 6) = 0;
    *(GUID *)(v25 + 56) = GUID_NULL;
    v44 = (struct _GUID)*((_OWORD *)Parameter + 56);
    v26 = RemoteAppIntegrationViewForwarder::RuntimeClassInitialize((RemoteAppIntegrationViewForwarder *)v25, &v44);
    v27 = *(_QWORD *)v25;
    if ( v26 >= 0 )
    {
      (*(void (__fastcall **)(char *))(v27 + 8))(v25);
      v23 = v25;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v25 + 16LL))(v25);
      v26 = 0;
    }
    else
    {
      (*(void (__fastcall **)(char *))(v27 + 16))(v25);
    }
  }
  else
  {
    v26 = -2147024882;
  }
  if ( v26 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x6B,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remotetextappintegration.cpp",
      (const char *)(unsigned int)v26,
      v41);
  if ( *((char **)Parameter + 15) != v23 )
  {
    if ( v23 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v23 + 8LL))(v23);
    v28 = *((_QWORD *)Parameter + 15);
    *((_QWORD *)Parameter + 15) = v23;
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  *(_QWORD *)&v44.Data1 = *((_QWORD *)Parameter + 6);
  v43 = (struct IMessagePort *)*((_QWORD *)Parameter + 9);
  v29 = 0;
  v30 = (GUID *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v31 = v30;
  if ( v30 )
  {
    *(_DWORD *)&v30[1].Data2 = 1;
    *(_QWORD *)&v30->Data1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRemoteCoreInputView,IMessageObjectOwner>::`vftable'{for `IRemoteCoreInputView'};
    *(_QWORD *)v30->Data4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRemoteCoreInputView,IMessageObjectOwner>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMessageObjectOwner>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)&v31->Data1 = &RemoteAppIntegrationView::`vftable'{for `IRemoteCoreInputView'};
    *(_QWORD *)v31->Data4 = &RemoteAppIntegrationView::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMessageObjectOwner>'};
    *(_QWORD *)v31[1].Data4 = 0;
    v31[2] = GUID_NULL;
    *(_QWORD *)&v31[3].Data1 = 0;
    *(_QWORD *)v31[3].Data4 = 0;
    v42 = (struct _GUID)*((_OWORD *)Parameter + 56);
    v17 = RemoteAppIntegrationView::RuntimeClassInitialize(
            (RemoteAppIntegrationView *)v31,
            (struct IRemoteAppIntegrationOwner *)(Parameter + 16),
            &v42,
            v43,
            *(struct IMessageFactory **)&v44.Data1);
    v32 = *(_QWORD *)&v31->Data1;
    if ( v17 >= 0 )
    {
      (*(void (__fastcall **)(GUID *))(v32 + 8))(v31);
      v29 = v31;
      (*(void (__fastcall **)(GUID *))(*(_QWORD *)&v31->Data1 + 16LL))(v31);
      v17 = 0;
    }
    else
    {
      (*(void (__fastcall **)(GUID *))(v32 + 16))(v31);
    }
  }
  if ( v17 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x74,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remotetextappintegration.cpp",
      (const char *)(unsigned int)v17,
      v41);
  v33 = *((_QWORD *)Parameter + 15);
  if ( *(GUID **)(v33 + 48) != v29 )
  {
    if ( v29 )
      (*(void (__fastcall **)(GUID *))(*(_QWORD *)&v29->Data1 + 8LL))(v29);
    v34 = *(_QWORD *)(v33 + 48);
    *(_QWORD *)(v33 + 48) = v29;
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  if ( *(_QWORD *)(v33 + 32) )
  {
    v47 = 0;
    v48 = 0;
    v49 = 0;
    *(_QWORD *)&v42.Data1 = 0;
    MessageObject = RemoteAppIntegrationView::GetMessageObject(
                      *(RemoteAppIntegrationView **)(v33 + 48),
                      (struct IMessageObject **)&v42);
    if ( MessageObject >= 0 )
    {
      v36 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)&v42.Data1 + 64LL))(
              *(_QWORD *)&v42.Data1,
              &v47);
      if ( v36 >= 0 )
      {
        v37 = *(_QWORD *)(v33 + 32);
        v45[0] = v47;
        v45[1] = v48;
        v46 = v49;
        (*(void (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v37 + 24LL))(v37, v45);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x37,
          (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remoteappintegrationviewforwarder.cpp",
          (const char *)(unsigned int)v36,
          v41);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36,
        (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remoteappintegrationviewforwarder.cpp",
        (const char *)(unsigned int)MessageObject,
        v41);
    }
    v38 = *(_QWORD *)&v42.Data1;
    if ( *(_QWORD *)&v42.Data1 )
    {
      *(_QWORD *)&v42.Data1 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
  }
  SetEvent(*((HANDLE *)Parameter + 11));
  v39 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)Parameter + 5) + 232LL))(*((_QWORD *)Parameter + 5));
  if ( v39 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remotetextappintegration.cpp",
      (const char *)(unsigned int)v39,
      v41);
  if ( v29 )
    (*(void (__fastcall **)(GUID *))(*(_QWORD *)&v29->Data1 + 16LL))(v29);
  if ( v23 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)v23 + 16LL))(v23);
  if ( v15 )
    (*(void (__fastcall **)(RemoteAppIntegrationServer *))(*(_QWORD *)v15 + 16LL))(v15);
  (*(void (__fastcall **)(char *))(*(_QWORD *)Parameter + 16LL))(Parameter);
  return 0;
}

```

## disassembly

```asm
0x18001b860  push    rbp
0x18001b862  push    rbx
0x18001b863  push    rsi
0x18001b864  push    rdi
0x18001b865  push    r12
0x18001b867  push    r13
0x18001b869  push    r14
0x18001b86b  push    r15
0x18001b86d  lea     rbp, [rsp-1Fh]
0x18001b872  sub     rsp, 0E8h
0x18001b879  mov     rax, cs:__security_cookie
0x18001b880  xor     rax, rsp
0x18001b883  mov     [rbp+57h+var_48], rax
0x18001b887  mov     r14, rcx
0x18001b88a  xor     r12d, r12d
0x18001b88d  test    rcx, rcx
0x18001b890  jz      short loc_18001B89F
0x18001b892  mov     rax, [rcx]
0x18001b895  mov     rax, [rax+8]
0x18001b899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b89e  nop
0x18001b89f  mov     rcx, [rbp+5Fh]; this
0x18001b8a3  test    r14, r14
0x18001b8a6  jz      loc_18001BEA4
0x18001b8ac  lea     rdi, [r14+28h]
0x18001b8b0  mov     rcx, [rdi]
0x18001b8b3  test    rcx, rcx
0x18001b8b6  jz      short loc_18001B8C8
0x18001b8b8  mov     [rdi], r12
0x18001b8bb  mov     rax, [rcx]
0x18001b8be  mov     rax, [rax+10h]
0x18001b8c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8c7  nop
0x18001b8c8  mov     rcx, rdi
0x18001b8cb  call    cs:__imp_CoreUICreate
0x18001b8d1  mov     rcx, [rbp+5Fh]; this
0x18001b8d5  test    eax, eax
0x18001b8d7  js      loc_18001BEB6
0x18001b8dd  lea     rbx, [r14+30h]
0x18001b8e1  mov     rcx, [rbx]
0x18001b8e4  test    rcx, rcx
0x18001b8e7  jz      short loc_18001B8F9
0x18001b8e9  mov     [rbx], r12
0x18001b8ec  mov     rax, [rcx]
0x18001b8ef  mov     rax, [rax+10h]
0x18001b8f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8f8  nop
0x18001b8f9  mov     rcx, rbx
0x18001b8fc  call    cs:__imp_CoreUIFactoryCreate
0x18001b902  mov     rcx, [rbp+5Fh]; this
0x18001b906  test    eax, eax
0x18001b908  js      loc_18001BECB
0x18001b90e  mov     rcx, [rdi]
0x18001b911  mov     rax, [rcx]
0x18001b914  lea     r9, [r14+38h]
0x18001b918  mov     r8, r14
0x18001b91b  lea     rdx, ?OnHotKeyRegistrationChanged@IRemoteTextInputServer_ToPdu@@UEAAJUHotKeyRegistrationData@@_N@Z; IRemoteTextInputServer_ToPdu::OnHotKeyRegistrationChanged(HotKeyRegistrationData,bool)
0x18001b922  mov     rax, [rax+70h]
0x18001b926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b92b  mov     rcx, [rbp+5Fh]; this
0x18001b92f  test    eax, eax
0x18001b931  js      loc_18001BEE0
0x18001b937  lea     rcx, [r14+40h]
0x18001b93b  xor     edx, edx
0x18001b93d  call    ?Initialize@SharedMessagePortRefPtr@@QEAAJW4InputCapability@@@Z; SharedMessagePortRefPtr::Initialize(InputCapability)
0x18001b942  mov     rcx, [rbp+5Fh]; this
0x18001b946  test    eax, eax
0x18001b948  js      loc_18001BEF5
0x18001b94e  lea     r15, [r14+68h]
0x18001b952  cmp     [r15], r12
0x18001b955  jnz     short loc_18001B99D
0x18001b957  mov     rax, [rdi]
0x18001b95a  mov     qword ptr [rsp+120h+var_F0.Data1], rax
0x18001b95f  mov     rax, [rbx]
0x18001b962  mov     [rsp+120h+var_E0], rax
0x18001b967  mov     rax, [r14+48h]
0x18001b96b  mov     qword ptr [rbp+57h+var_D0.Data1], rax
0x18001b96f  lea     rdx, [r14+380h]
0x18001b976  lea     rax, [rsp+120h+var_F0]
0x18001b97b  mov     qword ptr [rsp+120h+var_100], rax; int
0x18001b980  lea     r9, [rsp+120h+var_E0]
0x18001b985  lea     r8, [rbp+57h+var_D0]
0x18001b989  mov     rcx, r15
0x18001b98c  call    ??$MakeAndInitialize@VRemoteAppIntegrationClientManager@@V1@AEAU_GUID@@PEAUIMessagePort@@PEAUIMessageFactory@@PEAUIMessageSession@@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VRemoteAppIntegrationClientManager@@@WRL@Microsoft@@@012@AEAU_GUID@@$$QEAPEAUIMessagePort@@$$QEAPEAUIMessageFactory@@$$QEAPEAUIMessageSession@@@Z; Microsoft::WRL::Details::MakeAndInitialize<RemoteAppIntegrationClientManager,RemoteAppIntegrationClientManager,_GUID &,IMessagePort *,IMessageFactory *,IMessageSession *>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<RemoteAppIntegrationClientManager>>,_GUID &,IMessagePort * &&,IMessageFactory * &&,IMessageSession * &&)
0x18001b991  mov     rcx, [rbp+5Fh]; this
0x18001b995  test    eax, eax
0x18001b997  js      loc_18001BF0A
0x18001b99d  mov     r13d, 380h
0x18001b9a3  mov     rsi, r14
0x18001b9a6  mov     rbx, r12
0x18001b9a9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b9b0  mov     ecx, 80h; unsigned __int64
0x18001b9b5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001b9ba  mov     r12d, 8007000Eh
0x18001b9c0  test    rax, rax
0x18001b9c3  jnz     short loc_18001B9CA
0x18001b9c5  mov     esi, r12d
0x18001b9c8  jmp     short loc_18001BA37
0x18001b9ca  mov     rcx, rax; this
0x18001b9cd  call    ??0RemoteAppIntegrationServer@@QEAA@XZ; RemoteAppIntegrationServer::RemoteAppIntegrationServer(void)
0x18001b9d2  mov     rdi, rax
0x18001b9d5  movups  xmm0, xmmword ptr [rsi+r13]
0x18001b9da  movdqu  xmmword ptr [rbp+57h+var_D0.Data1], xmm0
0x18001b9df  lea     rdx, [rbp+57h+var_D0]; struct _GUID
0x18001b9e3  mov     rcx, rax; this
0x18001b9e6  call    ?RuntimeClassInitialize@RemoteAppIntegrationServer@@QEAAJU_GUID@@@Z; RemoteAppIntegrationServer::RuntimeClassInitialize(_GUID)
0x18001b9eb  mov     esi, eax
0x18001b9ed  test    eax, eax
0x18001b9ef  jns     short loc_18001BA08
0x18001b9f1  test    rdi, rdi
0x18001b9f4  jz      short loc_18001BA06
0x18001b9f6  mov     rax, [rdi]
0x18001b9f9  mov     rcx, rdi
0x18001b9fc  mov     rax, [rax+10h]
0x18001ba00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba05  nop
0x18001ba06  jmp     short loc_18001BA37
0x18001ba08  test    rdi, rdi
0x18001ba0b  jz      short loc_18001BA1D
0x18001ba0d  mov     rax, [rdi]
0x18001ba10  mov     rcx, rdi
0x18001ba13  mov     rax, [rax+8]
0x18001ba17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba1c  nop
0x18001ba1d  mov     rbx, rdi
0x18001ba20  test    rdi, rdi
0x18001ba23  jz      short loc_18001BA35
0x18001ba25  mov     rax, [rdi]
0x18001ba28  mov     rcx, rdi
0x18001ba2b  mov     rax, [rax+10h]
0x18001ba2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba34  nop
0x18001ba35  xor     esi, esi
0x18001ba37  mov     rcx, [rbp+5Fh]; this
0x18001ba3b  test    esi, esi
0x18001ba3d  js      loc_18001BF1F
0x18001ba43  mov     rdi, [r15]
0x18001ba46  cmp     [rdi+10h], rbx
0x18001ba4a  jz      short loc_18001BA7B
0x18001ba4c  test    rbx, rbx
0x18001ba4f  jz      short loc_18001BA61
0x18001ba51  mov     rax, [rbx]
0x18001ba54  mov     rcx, rbx
0x18001ba57  mov     rax, [rax+8]
0x18001ba5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba60  nop
0x18001ba61  mov     rcx, [rdi+10h]
0x18001ba65  mov     [rdi+10h], rbx
0x18001ba69  test    rcx, rcx
0x18001ba6c  jz      short loc_18001BA7B
0x18001ba6e  mov     rax, [rcx]
0x18001ba71  mov     rax, [rax+10h]
0x18001ba75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba7a  nop
0x18001ba7b  cmp     [r14+70h], rbx
0x18001ba7f  jz      short loc_18001BAB0
0x18001ba81  test    rbx, rbx
0x18001ba84  jz      short loc_18001BA96
0x18001ba86  mov     rax, [rbx]
0x18001ba89  mov     rcx, rbx
0x18001ba8c  mov     rax, [rax+8]
0x18001ba90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba95  nop
0x18001ba96  mov     rcx, [r14+70h]
0x18001ba9a  mov     [r14+70h], rbx
0x18001ba9e  test    rcx, rcx
0x18001baa1  jz      short loc_18001BAB0
0x18001baa3  mov     rax, [rcx]
0x18001baa6  mov     rax, [rax+10h]
0x18001baaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001baaf  nop
0x18001bab0  xor     esi, esi
0x18001bab2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001bab9  lea     ecx, [rsi+48h]; unsigned __int64
0x18001babc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001bac1  mov     rdi, rax
0x18001bac4  test    rax, rax
0x18001bac7  jnz     short loc_18001BAD1
0x18001bac9  mov     r15d, r12d
0x18001bacc  jmp     loc_18001BB9A
0x18001bad1  mov     dword ptr [rax+14h], 1
0x18001bad8  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIRemoteCoreInputViewManager@@UIMessageProxyReconnectAdapterOwner@@@WRL@Microsoft@@6BIRemoteCoreInputViewManager@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRemoteCoreInputViewManager,IMessageProxyReconnectAdapterOwner>::`vftable'{for `IRemoteCoreInputViewManager'}
0x18001badf  mov     [rdi], rax
0x18001bae2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIRemoteCoreInputViewManager@@UIMessageProxyReconnectAdapterOwner@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMessageProxyReconnectAdapterOwner@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRemoteCoreInputViewManager,IMessageProxyReconnectAdapterOwner>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMessageProxyReconnectAdapterOwner>'}
0x18001bae9  mov     [rdi+8], rax
0x18001baed  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001baf4  test    rcx, rcx
0x18001baf7  jz      short loc_18001BB06
0x18001baf9  mov     rax, [rcx]
0x18001bafc  mov     rax, [rax+8]
0x18001bb00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb05  nop
0x18001bb06  lea     rax, ??_7RemoteAppIntegrationViewForwarder@@6BIRemoteCoreInputViewManager@@@; const RemoteAppIntegrationViewForwarder::`vftable'{for `IRemoteCoreInputViewManager'}
0x18001bb0d  mov     [rdi], rax
0x18001bb10  lea     rax, ??_7RemoteAppIntegrationViewForwarder@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMessageProxyReconnectAdapterOwner@@@Details@WRL@Microsoft@@@; const RemoteAppIntegrationViewForwarder::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMessageProxyReconnectAdapterOwner>'}
0x18001bb17  mov     [rdi+8], rax
0x18001bb1b  mov     qword ptr [rdi+18h], 0
0x18001bb23  mov     qword ptr [rdi+20h], 0
0x18001bb2b  mov     qword ptr [rdi+28h], 0
0x18001bb33  mov     qword ptr [rdi+30h], 0
0x18001bb3b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001bb42  movdqu  xmmword ptr [rdi+38h], xmm0
0x18001bb47  movups  xmm0, xmmword ptr [r14+r13]
0x18001bb4c  movdqu  xmmword ptr [rbp+57h+var_D0.Data1], xmm0
0x18001bb51  lea     rdx, [rbp+57h+var_D0]; struct _GUID
0x18001bb55  mov     rcx, rdi; this
0x18001bb58  call    ?RuntimeClassInitialize@RemoteAppIntegrationViewForwarder@@QEAAJU_GUID@@@Z; RemoteAppIntegrationViewForwarder::RuntimeClassInitialize(_GUID)
0x18001bb5d  mov     r15d, eax
0x18001bb60  mov     rax, [rdi]
0x18001bb63  test    r15d, r15d
0x18001bb66  jns     short loc_18001BB77
0x18001bb68  mov     rcx, rdi
0x18001bb6b  mov     rax, [rax+10h]
0x18001bb6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb74  nop
0x18001bb75  jmp     short loc_18001BB9A
0x18001bb77  mov     rcx, rdi
0x18001bb7a  mov     rax, [rax+8]
0x18001bb7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb83  nop
0x18001bb84  mov     rsi, rdi
0x18001bb87  mov     rax, [rdi]
0x18001bb8a  mov     rcx, rdi
0x18001bb8d  mov     rax, [rax+10h]
0x18001bb91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb96  nop
0x18001bb97  xor     r15d, r15d
0x18001bb9a  mov     rcx, [rbp+5Fh]; this
0x18001bb9e  test    r15d, r15d
0x18001bba1  js      loc_18001BF34
0x18001bba7  cmp     [r14+78h], rsi
0x18001bbab  jz      short loc_18001BBDC
0x18001bbad  test    rsi, rsi
0x18001bbb0  jz      short loc_18001BBC2
0x18001bbb2  mov     rax, [rsi]
0x18001bbb5  mov     rcx, rsi
0x18001bbb8  mov     rax, [rax+8]
0x18001bbbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbc1  nop
0x18001bbc2  mov     rcx, [r14+78h]
0x18001bbc6  mov     [r14+78h], rsi
0x18001bbca  test    rcx, rcx
0x18001bbcd  jz      short loc_18001BBDC
0x18001bbcf  mov     rax, [rcx]
0x18001bbd2  mov     rax, [rax+10h]
0x18001bbd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbdb  nop
0x18001bbdc  mov     rax, [r14+30h]
0x18001bbe0  mov     qword ptr [rbp+57h+var_D0.Data1], rax
0x18001bbe4  mov     rax, [r14+48h]
0x18001bbe8  mov     [rsp+120h+var_E0], rax
0x18001bbed  xor     edi, edi
0x18001bbef  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001bbf6  lea     ecx, [rdi+40h]; unsigned __int64
0x18001bbf9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001bbfe  mov     r15, rax
0x18001bc01  test    rax, rax
0x18001bc04  jnz     short loc_18001BC0E
0x18001bc06  xor     r13d, r13d
0x18001bc09  jmp     loc_18001BCE7
0x18001bc0e  mov     dword ptr [rax+14h], 1
0x18001bc15  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIRemoteCoreInputView@@UIMessageObjectOwner@@@WRL@Microsoft@@6BIRemoteCoreInputView@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRemoteCoreInputView,IMessageObjectOwner>::`vftable'{for `IRemoteCoreInputView'}
0x18001bc1c  mov     [r15], rax
0x18001bc1f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIRemoteCoreInputView@@UIMessageObjectOwner@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMessageObjectOwner@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRemoteCoreInputView,IMessageObjectOwner>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMessageObjectOwner>'}
0x18001bc26  mov     [r15+8], rax
0x18001bc2a  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001bc31  test    rcx, rcx
0x18001bc34  jz      short loc_18001BC43
0x18001bc36  mov     rax, [rcx]
0x18001bc39  mov     rax, [rax+8]
0x18001bc3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc42  nop
0x18001bc43  lea     rax, ??_7RemoteAppIntegrationView@@6BIRemoteCoreInputView@@@; const RemoteAppIntegrationView::`vftable'{for `IRemoteCoreInputView'}
0x18001bc4a  mov     [r15], rax
0x18001bc4d  lea     rax, ??_7RemoteAppIntegrationView@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMessageObjectOwner@@@Details@WRL@Microsoft@@@; const RemoteAppIntegrationView::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMessageObjectOwner>'}
0x18001bc54  mov     [r15+8], rax
0x18001bc58  mov     qword ptr [r15+18h], 0
0x18001bc60  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001bc67  movdqu  xmmword ptr [r15+20h], xmm0
0x18001bc6d  mov     qword ptr [r15+30h], 0
0x18001bc75  mov     qword ptr [r15+38h], 0
0x18001bc7d  movups  xmm0, xmmword ptr [r14+r13]
0x18001bc82  movdqu  xmmword ptr [rsp+120h+var_F0.Data1], xmm0
0x18001bc88  lea     rdx, [r14+10h]; struct IRemoteAppIntegrationOwner *
0x18001bc8c  mov     rax, qword ptr [rbp+57h+var_D0.Data1]
0x18001bc90  mov     qword ptr [rsp+120h+var_100], rax; int
0x18001bc95  mov     r9, [rsp+120h+var_E0]; struct IMessagePort *
0x18001bc9a  lea     r8, [rsp+120h+var_F0]; struct _GUID *
0x18001bc9f  mov     rcx, r15; this
0x18001bca2  call    ?RuntimeClassInitialize@RemoteAppIntegrationView@@QEAAJPEAUIRemoteAppIntegrationOwner@@U_GUID@@PEAUIMessagePort@@PEAUIMessageFactory@@@Z; RemoteAppIntegrationView::RuntimeClassInitialize(IRemoteAppIntegrationOwner *,_GUID,IMessagePort *,IMessageFactory *)
0x18001bca7  mov     r12d, eax
0x18001bcaa  mov     rax, [r15]
0x18001bcad  xor     r13d, r13d
0x18001bcb0  test    r12d, r12d
0x18001bcb3  jns     short loc_18001BCC4
0x18001bcb5  mov     rcx, r15
0x18001bcb8  mov     rax, [rax+10h]
0x18001bcbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcc1  nop
0x18001bcc2  jmp     short loc_18001BCE7
  ... truncated ...
```
