# CoreUiSession::CoreUiSession(std::weak_ptr<IViewManagerEventsHandler>,std::function<std::tuple<wil::com_ptr_t<IMessageSession,wil::err_exception_policy>,wil::com_ptr_t<Windows::Internal::ApplicationModel::WindowManagement::IAppViewStatics,wil::err_exception_policy>,wil::com_ptr_t<Windows::Internal::ApplicationModel::WindowManagement::IWindowStatics,wil::err_exception_policy>,wil::com_ptr_t<Windows::Internal::ApplicationModel::WindowManagement::IWindowWatcher,wil::err_exception_policy>> (void)>,bool)

- ea: `0x180015e54`
- end: `0x180016009`
- name: `??0CoreUiSession@@QEAA@V?$weak_ptr@UIViewManagerEventsHandler@@@std@@V?$function@$$A6A?AV?$tuple@V?$com_ptr_t@UIMessageSession@@Uerr_exception_policy@wil@@@wil@@V?$com_ptr_t@UIAppViewStatics@WindowManagement@ApplicationModel@Internal@Windows@@Uerr_exception_policy@wil@@@2@V?$com_ptr_t@UIWindowStatics@WindowManagement@ApplicationModel@Internal@Windows@@Uerr_exception_policy@wil@@@2@V?$com_ptr_t@UIWindowWatcher@WindowManagement@ApplicationModel@Internal@Windows@@Uerr_exception_policy@wil@@@2@@std@@XZ@2@_N@Z`
- size: `437`
- prototype: `__int64 __fastcall(std::thread *this)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002ac2c`

## callees

- `0x180004ecc`
- `0x180007344`
- `0x1800078c4`
- `0x1800125c0`
- `0x180015e54`
- `0x18001607c`
- `0x1800161b8`
- `0x1800161ec`
- `0x18001620c`
- `0x180016250`
- `0x18001626c`
- `0x180016304`
- `0x1800163c0`
- `0x18001d9c4`
- `0x180031540`
- `0x180037920`
- `0x180043680`
- `0x180079640`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015fda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015fda`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180015f4a`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180015f4a`

## string_xrefs

- `0x180015fba`: `onecore\windows\accessibletech\uiamanager\dll\coreuisession.cpp`
- `0x180015ff7`: `onecore\windows\accessibletech\uiamanager\dll\coreuisession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
CoreUiSession *__fastcall CoreUiSession::CoreUiSession(CoreUiSession *this, __int64 a2, __int64 a3)
{
  __int64 v6; // rax
  void *v7; // rax
  DWORD v8; // eax
  std::_Ref_count_base *v9; // rcx
  DWORD LastError; // ebx
  unsigned int v12; // [rsp+20h] [rbp-E0h]
  char v13[8]; // [rsp+30h] [rbp-D0h] BYREF
  int v14; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v15[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v16[16]; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE Handles[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v18[8]; // [rsp+70h] [rbp-90h] BYREF
  std::_Ref_count_base *v19; // [rsp+78h] [rbp-88h]
  CoreUiSession *v20; // [rsp+80h] [rbp-80h]
  __int64 v21; // [rsp+88h] [rbp-78h]
  __int64 v22; // [rsp+90h] [rbp-70h]
  _BYTE v23[128]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v20 = this;
  v21 = a2;
  v22 = a3;
  v13[0] = 1;
  *(_OWORD *)this = 0;
  *((_BYTE *)this + 16) = 0;
  std::make_shared<CoreUiSession::CoreUiThreadState,>((char *)this + 24);
  v14 = 1;
  ____0W4EventOptions_wil_____shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    v15,
    &v14);
  std::shared_ptr<CoreUiSession::HwndAndViewIdConversionData>::shared_ptr<CoreUiSession::HwndAndViewIdConversionData>(
    v18,
    (char *)this + 24);
  v6 = lambda_714b79bcc13b51cad6173b18f11543ae_::_lambda_714b79bcc13b51cad6173b18f11543ae_(
         (unsigned int)v23,
         (unsigned int)v18,
         (unsigned int)v15,
         a3,
         a2,
         (__int64)v13);
  std::thread::_Start__lambda_714b79bcc13b51cad6173b18f11543ae___((__int64)v16, v6);
  std::thread::operator=(this, v16);
  std::thread::~thread((std::thread *)v16);
  lambda_714b79bcc13b51cad6173b18f11543ae_::__lambda_714b79bcc13b51cad6173b18f11543ae_(v23);
  v7 = (void *)v15[0];
  if ( v15[0] )
    v7 = *(void **)v15[0];
  Handles[0] = v7;
  Handles[1] = *(HANDLE *)this;
  v8 = WaitForMultipleObjects(2u, Handles, 0, 0xBB8u);
  if ( v8 )
  {
    if ( v8 == 1 )
    {
      std::thread::join(this);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2E9,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\coreuisession.cpp",
        (const char *)0x80004005LL,
        v12);
    }
    if ( v8 == 258 )
      LastError = 1460;
    else
      LastError = GetLastError();
    if ( *((_DWORD *)this + 2) )
      std::thread::detach(this);
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x2F7,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\coreuisession.cpp",
      (const char *)LastError,
      v12);
  }
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
  std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(v15);
  v9 = *(std::_Ref_count_base **)(a2 + 8);
  if ( v9 )
    std::_Ref_count_base::_Decwref(v9);
  std::_Func_class<void,GetCompositionInputSinkViewInstanceIdFromPointRequestPayload,RequestCompleter<HrResponse<GetCompositionInputSinkViewInstanceIdFromPointService::ResponsePayload>>>::_Tidy(a3);
  return this;
}

```

## disassembly

```asm
0x180015e54  push    rbp
0x180015e56  push    rbx
0x180015e57  push    rsi
0x180015e58  push    rdi
0x180015e59  push    r14
0x180015e5b  lea     rbp, [rsp-30h]
0x180015e60  sub     rsp, 130h
0x180015e67  mov     rax, cs:__security_cookie
0x180015e6e  xor     rax, rsp
0x180015e71  mov     [rbp+50h+var_30], rax
0x180015e75  mov     rsi, r8
0x180015e78  mov     r14, rdx
0x180015e7b  mov     rdi, rcx
0x180015e7e  mov     [rbp+50h+var_D0], rcx
0x180015e82  mov     [rbp+50h+var_C8], rdx
0x180015e86  mov     [rbp+50h+var_C0], r8
0x180015e8a  mov     [rsp+150h+var_120], 1
0x180015e8f  xorps   xmm0, xmm0
0x180015e92  movups  xmmword ptr [rcx], xmm0
0x180015e95  mov     byte ptr [rcx+10h], 0
0x180015e99  add     rcx, 18h
0x180015e9d  call    ??$make_shared@VCoreUiThreadState@CoreUiSession@@$$V@std@@YA?AV?$shared_ptr@VCoreUiThreadState@CoreUiSession@@@0@XZ; std::make_shared<CoreUiSession::CoreUiThreadState,>(void)
0x180015ea2  nop
0x180015ea3  mov     [rsp+150h+var_118], 1
0x180015eab  lea     rdx, [rsp+150h+var_118]
0x180015eb0  lea     rcx, [rsp+150h+var_110]
0x180015eb5  call    ??$?0W4EventOptions@wil@@@?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x180015eba  nop
0x180015ebb  lea     rdx, [rdi+18h]
0x180015ebf  lea     rcx, [rsp+150h+var_E0]
0x180015ec4  call    ??0?$shared_ptr@UHwndAndViewIdConversionData@CoreUiSession@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<CoreUiSession::HwndAndViewIdConversionData>::shared_ptr<CoreUiSession::HwndAndViewIdConversionData>(std::shared_ptr<CoreUiSession::HwndAndViewIdConversionData> const &)
0x180015ec9  nop
0x180015eca  lea     rax, [rsp+150h+var_120]
0x180015ecf  mov     [rsp+150h+var_128], rax
0x180015ed4  mov     qword ptr [rsp+150h+var_130], r14; unsigned int
0x180015ed9  mov     r9, rsi
0x180015edc  lea     r8, [rsp+150h+var_110]
0x180015ee1  lea     rdx, [rsp+150h+var_E0]
0x180015ee6  lea     rcx, [rbp+50h+var_B0]
0x180015eea  call    _lambda_714b79bcc13b51cad6173b18f11543ae____lambda_714b79bcc13b51cad6173b18f11543ae_
0x180015eef  nop
0x180015ef0  mov     rdx, rax
0x180015ef3  lea     rcx, [rsp+150h+var_100]
0x180015ef8  call    std__thread___Start__lambda_714b79bcc13b51cad6173b18f11543ae___
0x180015efd  lea     rdx, [rsp+150h+var_100]
0x180015f02  mov     rcx, rdi
0x180015f05  call    ??4thread@std@@QEAAAEAV01@$$QEAV01@@Z; std::thread::operator=(std::thread &&)
0x180015f0a  lea     rcx, [rsp+150h+var_100]; this
0x180015f0f  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x180015f14  nop
0x180015f15  lea     rcx, [rbp+50h+var_B0]
0x180015f19  call    _lambda_714b79bcc13b51cad6173b18f11543ae_____lambda_714b79bcc13b51cad6173b18f11543ae_
0x180015f1e  mov     rax, [rsp+150h+var_110]
0x180015f23  test    rax, rax
0x180015f26  jz      short loc_180015F2B
0x180015f28  mov     rax, [rax]
0x180015f2b  mov     [rsp+150h+Handles], rax
0x180015f30  mov     rax, [rdi]
0x180015f33  mov     [rsp+150h+var_E8], rax
0x180015f38  mov     r9d, 0BB8h; dwMilliseconds
0x180015f3e  xor     r8d, r8d; bWaitAll
0x180015f41  lea     rdx, [rsp+150h+Handles]; lpHandles
0x180015f46  lea     ecx, [r8+2]; nCount
0x180015f4a  call    cs:__imp_WaitForMultipleObjects
0x180015f50  test    eax, eax
0x180015f52  jnz     short loc_180015FA3
0x180015f54  mov     rcx, [rsp+150h+var_D8]; this
0x180015f59  test    rcx, rcx
0x180015f5c  jz      short loc_180015F64
0x180015f5e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015f63  nop
0x180015f64  lea     rcx, [rsp+150h+var_110]
0x180015f69  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x180015f6e  nop
0x180015f6f  mov     rcx, [r14+8]; this
0x180015f73  test    rcx, rcx
0x180015f76  jz      short loc_180015F7E
0x180015f78  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180015f7d  nop
0x180015f7e  mov     rcx, rsi
0x180015f81  call    ?_Tidy@?$_Func_class@XUGetCompositionInputSinkViewInstanceIdFromPointRequestPayload@@V?$RequestCompleter@U?$HrResponse@UResponsePayload@GetCompositionInputSinkViewInstanceIdFromPointService@@@@@@@std@@IEAAXXZ; std::_Func_class<void,GetCompositionInputSinkViewInstanceIdFromPointRequestPayload,RequestCompleter<HrResponse<GetCompositionInputSinkViewInstanceIdFromPointService::ResponsePayload>>>::_Tidy(void)
0x180015f86  mov     rax, rdi
0x180015f89  mov     rcx, [rbp+50h+var_30]
0x180015f8d  xor     rcx, rsp; StackCookie
0x180015f90  call    __security_check_cookie
0x180015f95  add     rsp, 130h
0x180015f9c  pop     r14
0x180015f9e  pop     rdi
0x180015f9f  pop     rsi
0x180015fa0  pop     rbx
0x180015fa1  pop     rbp
0x180015fa2  retn
0x180015fa3  cmp     eax, 1
0x180015fa6  jnz     short loc_180015FCC
0x180015fa8  mov     rcx, rdi; this
0x180015fab  call    ?join@thread@std@@QEAAXXZ; std::thread::join(void)
0x180015fb0  mov     rcx, [rbp+58h]; this
0x180015fb4  mov     r9d, 80004005h; char *
0x180015fba  lea     r8, aOnecoreWindows_7; "onecore\\windows\\accessibletech\\uiama"...
0x180015fc1  mov     edx, 2E9h; void *
0x180015fc6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180015fcc  cmp     eax, 102h
0x180015fd1  jnz     short loc_180015FDA
0x180015fd3  mov     ebx, 5B4h
0x180015fd8  jmp     short loc_180015FE2
0x180015fda  call    cs:__imp_GetLastError
0x180015fe0  mov     ebx, eax
0x180015fe2  cmp     dword ptr [rdi+8], 0
0x180015fe6  jz      short loc_180015FF0
0x180015fe8  mov     rcx, rdi; this
0x180015feb  call    ?detach@thread@std@@QEAAXXZ; std::thread::detach(void)
0x180015ff0  mov     rcx, [rbp+58h]; this
0x180015ff4  mov     r9d, ebx; char *
0x180015ff7  lea     r8, aOnecoreWindows_7; "onecore\\windows\\accessibletech\\uiama"...
0x180015ffe  mov     edx, 2F7h; void *
0x180016003  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
