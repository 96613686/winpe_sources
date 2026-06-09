# CoreUiSession::CreateCoreUiSession(void)

- ea: `0x18003ca00`
- end: `0x18003cb04`
- name: `?CreateCoreUiSession@CoreUiSession@@SA?AV?$tuple@V?$com_ptr_t@UIMessageSession@@Uerr_exception_policy@wil@@@wil@@V?$com_ptr_t@UIAppViewStatics@WindowManagement@ApplicationModel@Internal@Windows@@Uerr_exception_policy@wil@@@2@V?$com_ptr_t@UIWindowStatics@WindowManagement@ApplicationModel@Internal@Windows@@Uerr_exception_policy@wil@@@2@V?$com_ptr_t@UIWindowWatcher@WindowManagement@ApplicationModel@Internal@Windows@@Uerr_exception_policy@wil@@@2@@std@@XZ`
- size: `260`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800067f8`
- `0x180020804`
- `0x180031540`
- `0x18003ca00`
- `0x18003cb0c`
- `0x18003cbac`
- `0x18003ccd0`
- `0x18003d294`

## import_xrefs

- `CoreMessaging!CoreUICreate` at `0x18003ca1c`
- `CoreMessaging!CoreUICreate` at `0x18003ca1c`

## string_xrefs

- `0x18003ca2d`: `onecore\windows\accessibletech\uiamanager\dll\coreuisession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct IUnknownVtbl **__fastcall CoreUiSession::CreateCoreUiSession(struct IUnknownVtbl **a1)
{
  int v2; // eax
  struct IUnknownVtbl **v3; // rax
  struct IUnknownVtbl *v4; // rdi
  struct IUnknownVtbl **v5; // rax
  struct IUnknownVtbl *v6; // rbx
  void **v7; // r8
  struct IUnknownVtbl *lpVtbl; // rax
  struct IUnknownVtbl *v9; // rax
  int v11; // [rsp+20h] [rbp-20h]
  struct IUnknownVtbl *v12; // [rsp+28h] [rbp-18h] BYREF
  char v13[8]; // [rsp+30h] [rbp-10h] BYREF
  char v14[8]; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  struct IUnknown v16; // [rsp+78h] [rbp+38h] BYREF
  struct IUnknownVtbl *v17; // [rsp+80h] [rbp+40h] BYREF
  struct IUnknownVtbl *v18; // [rsp+88h] [rbp+48h] BYREF

  v17 = 0;
  v2 = CoreUICreate(&v17);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x317,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\coreuisession.cpp",
      (const char *)(unsigned int)v2,
      v11);
  v12 = 0;
  v18 = 0;
  v16.lpVtbl = 0;
  v3 = (struct IUnknownVtbl **)wil::GetActivationFactory<Windows::Internal::ApplicationModel::WindowManagement::IAppViewStatics>(v14);
  v4 = *v3;
  *v3 = 0;
  v12 = v4;
  wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(v14);
  v5 = (struct IUnknownVtbl **)wil::GetActivationFactory<Windows::Internal::ApplicationModel::WindowManagement::IWindowStatics>(v14);
  v6 = *v5;
  *v5 = 0;
  v18 = v6;
  wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(v14);
  winrt::Windows::Internal::ApplicationModel::WindowManagement::WindowInProc::CreateWatcher();
  v16.lpVtbl = 0;
  winrt::copy_to_abi((winrt *)v13, &v16, v7);
  lpVtbl = v16.lpVtbl;
  v16.lpVtbl = 0;
  *a1 = lpVtbl;
  v18 = 0;
  a1[1] = v6;
  v12 = 0;
  a1[2] = v4;
  v9 = v17;
  v17 = 0;
  a1[3] = v9;
  winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow((winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow *)v13);
  wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v16);
  wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v18);
  wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v12);
  wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v17);
  return a1;
}

```

## disassembly

```asm
0x18003ca00  push    rbp
0x18003ca02  push    rbx
0x18003ca03  push    rsi
0x18003ca04  push    rdi
0x18003ca05  push    r14
0x18003ca07  mov     rbp, rsp
0x18003ca0a  sub     rsp, 40h
0x18003ca0e  mov     rsi, rcx
0x18003ca11  xor     r14d, r14d
0x18003ca14  mov     [rbp+arg_10], r14
0x18003ca18  lea     rcx, [rbp+arg_10]
0x18003ca1c  call    cs:__imp_CoreUICreate
0x18003ca22  mov     rcx, [rbp+28h]; this
0x18003ca26  test    eax, eax
0x18003ca28  jns     short loc_18003CA3F
0x18003ca2a  mov     r9d, eax; char *
0x18003ca2d  lea     r8, aOnecoreWindows_7; "onecore\\windows\\accessibletech\\uiama"...
0x18003ca34  mov     edx, 317h; void *
0x18003ca39  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003ca3f  mov     [rbp+var_18], r14
0x18003ca43  mov     [rbp+arg_18], r14
0x18003ca47  mov     [rbp+arg_8.lpVtbl], r14
0x18003ca4b  lea     rcx, [rbp+var_8]
0x18003ca4f  call    ??$GetActivationFactory@UIAppViewStatics@WindowManagement@ApplicationModel@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIAppViewStatics@WindowManagement@ApplicationModel@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::ApplicationModel::WindowManagement::IAppViewStatics>(ushort const *)
0x18003ca54  mov     rdi, [rax]
0x18003ca57  mov     [rax], r14
0x18003ca5a  mov     [rbp+var_18], rdi
0x18003ca5e  lea     rcx, [rbp+var_8]
0x18003ca62  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x18003ca67  lea     rcx, [rbp+var_8]
0x18003ca6b  call    ??$GetActivationFactory@UIWindowStatics@WindowManagement@ApplicationModel@Internal@Windows@@@wil@@YA?AV?$com_ptr_t@UIWindowStatics@WindowManagement@ApplicationModel@Internal@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Internal::ApplicationModel::WindowManagement::IWindowStatics>(ushort const *)
0x18003ca70  mov     rbx, [rax]
0x18003ca73  mov     [rax], r14
0x18003ca76  mov     [rbp+arg_18], rbx
0x18003ca7a  lea     rcx, [rbp+var_8]
0x18003ca7e  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x18003ca83  lea     rcx, [rbp+var_10]
0x18003ca87  call    ?CreateWatcher@WindowInProc@WindowManagement@ApplicationModel@Internal@Windows@winrt@@SA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::WindowInProc::CreateWatcher(void)
0x18003ca8c  nop
0x18003ca8d  mov     [rbp+arg_8.lpVtbl], r14
0x18003ca91  lea     rdx, [rbp+arg_8]; struct IUnknown *
0x18003ca95  lea     rcx, [rbp+var_10]; this
0x18003ca99  call    ?copy_to_abi@winrt@@YAXAEBUIUnknown@Foundation@Windows@1@AEAPEAX@Z; winrt::copy_to_abi(winrt::Windows::Foundation::IUnknown const &,void * &)
0x18003ca9e  mov     rax, [rbp+arg_8.lpVtbl]
0x18003caa2  mov     [rbp+arg_8.lpVtbl], r14
0x18003caa6  mov     [rsi], rax
0x18003caa9  mov     [rbp+arg_18], r14
0x18003caad  mov     [rsi+8], rbx
0x18003cab1  mov     [rbp+var_18], r14
0x18003cab5  mov     [rsi+10h], rdi
0x18003cab9  mov     rax, [rbp+arg_10]
0x18003cabd  mov     [rbp+arg_10], r14
0x18003cac1  mov     [rsi+18h], rax
0x18003cac5  lea     rcx, [rbp+var_10]; this
0x18003cac9  call    ??1IWindow@WindowManagement@ApplicationModel@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::ApplicationModel::WindowManagement::IWindow::~IWindow(void)
0x18003cace  nop
0x18003cacf  lea     rcx, [rbp+arg_8]
0x18003cad3  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x18003cad8  nop
0x18003cad9  lea     rcx, [rbp+arg_18]
0x18003cadd  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x18003cae2  nop
0x18003cae3  lea     rcx, [rbp+var_18]
0x18003cae7  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x18003caec  nop
0x18003caed  lea     rcx, [rbp+arg_10]
0x18003caf1  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x18003caf6  mov     rax, rsi
0x18003caf9  add     rsp, 40h
0x18003cafd  pop     r14
0x18003caff  pop     rdi
0x18003cb00  pop     rsi
0x18003cb01  pop     rbx
0x18003cb02  pop     rbp
0x18003cb03  retn
```
