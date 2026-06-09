# _anonymous_namespace_::DispatchOntoThreadPool__lambda_c3b9f7a6bf3a675a648bda1db91c274b___

- ea: `0x18006df9c`
- end: `0x18006e361`
- name: `_anonymous_namespace_::DispatchOntoThreadPool__lambda_c3b9f7a6bf3a675a648bda1db91c274b___`
- size: `965`
- prototype: `__int64 __fastcall(DWORD dwMilliseconds, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800136f0`

## callees

- `0x1800054f8`
- `0x180006edc`
- `0x18001607c`
- `0x18001d9c4`
- `0x180043680`
- `0x18006d9b8`
- `0x18006db60`
- `0x18006df9c`
- `0x18006e368`
- `0x18006e988`
- `0x18006ebf8`
- `0x18006ec28`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18006e1e9`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18006e1e9`

## string_xrefs

- `0x18006e000`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x18006e0b7`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x18006e13a`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x18006e206`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x18006e27d`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::DispatchOntoThreadPool__lambda_c3b9f7a6bf3a675a648bda1db91c274b___(
        DWORD dwMilliseconds,
        const unsigned __int16 *a2)
{
  _QWORD *v4; // rax
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v8; // rax
  HANDLE v9; // rsi
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, HANDLE, __int64 *); // rbx
  int v12; // eax
  unsigned int v13; // ebx
  void *v14; // rcx
  void *v15; // rcx
  DWORD v16; // eax
  int v17[2]; // [rsp+20h] [rbp-B8h] BYREF
  __int64 v18; // [rsp+28h] [rbp-B0h] BYREF
  _QWORD v19[2]; // [rsp+30h] [rbp-A8h] BYREF
  _QWORD v20[3]; // [rsp+40h] [rbp-98h] BYREF
  _BYTE v21[56]; // [rsp+58h] [rbp-80h] BYREF
  HANDLE Handles[4]; // [rsp+90h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v20[2] = a2;
  *(_QWORD *)v17 = 0;
  v4 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                   (HSTRING *)Handles,
                   (const unsigned __int16 (*)[36])a2);
  v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Threading::IThreadPoolStatics>>(
         *v4,
         v17);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
      (const char *)(unsigned int)v5,
      v17[0]);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v17);
    lambda_c3b9f7a6bf3a675a648bda1db91c274b_::__lambda_c3b9f7a6bf3a675a648bda1db91c274b_(a2);
    return v6;
  }
  LODWORD(Handles[0]) = 1;
  ____0W4EventOptions_wil_____shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    v20,
    Handles);
  LODWORD(Handles[0]) = 1;
  ____0W4EventOptions_wil_____shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    v19,
    Handles);
  v8 = lambda_3d1a2ea0a4679e06f5ff1be96072533d_::_lambda_3d1a2ea0a4679e06f5ff1be96072533d_(v21, a2, v20, v19);
  Microsoft::WRL::Callback_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::System::Threading::IWorkItemHandler_Microsoft::WRL::FtmBase___lambda_3d1a2ea0a4679e06f5ff1be96072533d___(
    Handles,
    v8);
  lambda_3d1a2ea0a4679e06f5ff1be96072533d_::__lambda_3d1a2ea0a4679e06f5ff1be96072533d_(v21);
  v9 = Handles[0];
  if ( !Handles[0] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
      (const char *)0x8007000ELL,
      v17[0]);
    std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(v19);
    std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(v20);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v17);
    lambda_c3b9f7a6bf3a675a648bda1db91c274b_::__lambda_c3b9f7a6bf3a675a648bda1db91c274b_(a2);
    return 2147942414LL;
  }
  v18 = 0;
  v10 = *(_QWORD *)v17;
  v11 = *(__int64 (__fastcall **)(__int64, HANDLE, __int64 *))(**(_QWORD **)v17 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
  v12 = v11(v10, v9, &v18);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
      (const char *)(unsigned int)v12,
      v17[0]);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    if ( v9 )
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v9 + 16LL))(v9);
    std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(v19);
    std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(v20);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v17);
    lambda_c3b9f7a6bf3a675a648bda1db91c274b_::__lambda_c3b9f7a6bf3a675a648bda1db91c274b_(a2);
    return v13;
  }
  if ( !dwMilliseconds )
    goto LABEL_24;
  if ( v20[0] )
    v14 = *(void **)v20[0];
  else
    v14 = 0;
  Handles[0] = v14;
  if ( v19[0] )
    v15 = *(void **)v19[0];
  else
    v15 = 0;
  Handles[1] = v15;
  v16 = WaitForMultipleObjects(2u, Handles, 0, dwMilliseconds);
  if ( v16 == 258 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
      (const char *)0x800705B4LL,
      v17[0]);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    if ( v9 )
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v9 + 16LL))(v9);
    std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(v19);
    std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(v20);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v17);
    lambda_c3b9f7a6bf3a675a648bda1db91c274b_::__lambda_c3b9f7a6bf3a675a648bda1db91c274b_(a2);
    return 2147943860LL;
  }
  if ( v16 == 1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
      (const char *)0x80004005LL,
      v17[0]);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    if ( v9 )
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v9 + 16LL))(v9);
    std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(v19);
    std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(v20);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v17);
    lambda_c3b9f7a6bf3a675a648bda1db91c274b_::__lambda_c3b9f7a6bf3a675a648bda1db91c274b_(a2);
    return 2147500037LL;
  }
  else
  {
LABEL_24:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    if ( v9 )
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v9 + 16LL))(v9);
    std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(v19);
    std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(v20);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v17);
    lambda_c3b9f7a6bf3a675a648bda1db91c274b_::__lambda_c3b9f7a6bf3a675a648bda1db91c274b_(a2);
    return 0;
  }
}

```

## disassembly

```asm
0x18006df9c  mov     r11, rsp
0x18006df9f  mov     [r11+18h], rbx
0x18006dfa3  mov     [r11+20h], rsi
0x18006dfa7  push    rdi
0x18006dfa8  push    r14
0x18006dfaa  push    r15
0x18006dfac  sub     rsp, 0C0h
0x18006dfb3  mov     rax, cs:__security_cookie
0x18006dfba  xor     rax, rsp
0x18006dfbd  mov     [rsp+0D8h+var_28], rax
0x18006dfc5  mov     r14, rdx
0x18006dfc8  mov     r15d, ecx
0x18006dfcb  mov     [rsp+0D8h+var_88], rdx
0x18006dfd0  mov     qword ptr [rsp+0D8h+var_B8], 0; int
0x18006dfd9  lea     rcx, [r11-48h]; string
0x18006dfdd  call    ??$?0$0CE@@StringReference@Internal@Windows@@QEAA@AEAY0CE@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[36])
0x18006dfe2  lea     rdx, [rsp+0D8h+var_B8]
0x18006dfe7  mov     rcx, [rax]
0x18006dfea  call    ??$GetActivationFactory@V?$ComPtr@UIThreadPoolStatics@Threading@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIThreadPoolStatics@Threading@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Threading::IThreadPoolStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Threading::IThreadPoolStatics>>)
0x18006dfef  mov     ebx, eax
0x18006dff1  test    eax, eax
0x18006dff3  jns     short loc_18006E02C
0x18006dff5  mov     rcx, [rsp+0D8h]; this
0x18006dffd  mov     r9d, eax; char *
0x18006e000  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006e007  mov     edx, 21h ; '!'; void *
0x18006e00c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e011  nop
0x18006e012  lea     rcx, [rsp+0D8h+var_B8]
0x18006e017  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006e01c  nop
0x18006e01d  mov     rcx, r14
0x18006e020  call    _lambda_c3b9f7a6bf3a675a648bda1db91c274b_____lambda_c3b9f7a6bf3a675a648bda1db91c274b_
0x18006e025  mov     eax, ebx
0x18006e027  jmp     loc_18006E338
0x18006e02c  mov     dword ptr [rsp+0D8h+Handles], 1
0x18006e037  lea     rdx, [rsp+0D8h+Handles]
0x18006e03f  lea     rcx, [rsp+0D8h+var_98]
0x18006e044  call    ??$?0W4EventOptions@wil@@@?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x18006e049  nop
0x18006e04a  mov     dword ptr [rsp+0D8h+Handles], 1
0x18006e055  lea     rdx, [rsp+0D8h+Handles]
0x18006e05d  lea     rcx, [rsp+0D8h+var_A8]
0x18006e062  call    ??$?0W4EventOptions@wil@@@?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x18006e067  nop
0x18006e068  lea     r9, [rsp+0D8h+var_A8]
0x18006e06d  lea     r8, [rsp+0D8h+var_98]
0x18006e072  mov     rdx, r14
0x18006e075  lea     rcx, [rsp+0D8h+var_80]
0x18006e07a  call    _lambda_3d1a2ea0a4679e06f5ff1be96072533d____lambda_3d1a2ea0a4679e06f5ff1be96072533d_
0x18006e07f  mov     rdx, rax
0x18006e082  lea     rcx, [rsp+0D8h+Handles]
0x18006e08a  call    Microsoft__WRL__Callback_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__Windows__System__Threading__IWorkItemHandler_Microsoft__WRL__FtmBase___lambda_3d1a2ea0a4679e06f5ff1be96072533d___
0x18006e08f  nop
0x18006e090  lea     rcx, [rsp+0D8h+var_80]
0x18006e095  call    _lambda_3d1a2ea0a4679e06f5ff1be96072533d_____lambda_3d1a2ea0a4679e06f5ff1be96072533d_
0x18006e09a  mov     rsi, [rsp+0D8h+Handles]
0x18006e0a2  test    rsi, rsi
0x18006e0a5  jnz     short loc_18006E0F7
0x18006e0a7  mov     rcx, [rsp+0D8h]; this
0x18006e0af  mov     ebx, 8007000Eh
0x18006e0b4  mov     r9d, ebx; char *
0x18006e0b7  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006e0be  lea     edx, [rsi+37h]; void *
0x18006e0c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e0c6  nop
0x18006e0c7  lea     rcx, [rsp+0D8h+var_A8]
0x18006e0cc  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18006e0d1  nop
0x18006e0d2  lea     rcx, [rsp+0D8h+var_98]
0x18006e0d7  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18006e0dc  nop
0x18006e0dd  lea     rcx, [rsp+0D8h+var_B8]
0x18006e0e2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006e0e7  nop
0x18006e0e8  mov     rcx, r14
0x18006e0eb  call    _lambda_c3b9f7a6bf3a675a648bda1db91c274b_____lambda_c3b9f7a6bf3a675a648bda1db91c274b_
0x18006e0f0  mov     eax, ebx
0x18006e0f2  jmp     loc_18006E338
0x18006e0f7  mov     [rsp+0D8h+var_B0], 0
0x18006e100  mov     rdi, qword ptr [rsp+0D8h+var_B8]
0x18006e105  mov     rax, [rdi]
0x18006e108  mov     rbx, [rax+30h]
0x18006e10c  lea     rcx, [rsp+0D8h+var_B0]
0x18006e111  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006e116  lea     r8, [rsp+0D8h+var_B0]
0x18006e11b  mov     rdx, rsi
0x18006e11e  mov     rcx, rdi
0x18006e121  mov     rax, rbx
0x18006e124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e129  mov     ebx, eax
0x18006e12b  test    eax, eax
0x18006e12d  jns     short loc_18006E19C
0x18006e12f  mov     rcx, [rsp+0D8h]; this
0x18006e137  mov     r9d, eax; char *
0x18006e13a  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006e141  mov     edx, 3Ah ; ':'; void *
0x18006e146  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e14b  nop
0x18006e14c  lea     rcx, [rsp+0D8h+var_B0]
0x18006e151  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006e156  nop
0x18006e157  test    rsi, rsi
0x18006e15a  jz      short loc_18006E16C
0x18006e15c  mov     rax, [rsi]
0x18006e15f  mov     rcx, rsi
0x18006e162  mov     rax, [rax+10h]
0x18006e166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e16b  nop
0x18006e16c  lea     rcx, [rsp+0D8h+var_A8]
0x18006e171  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18006e176  nop
0x18006e177  lea     rcx, [rsp+0D8h+var_98]
0x18006e17c  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18006e181  nop
0x18006e182  lea     rcx, [rsp+0D8h+var_B8]
0x18006e187  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006e18c  nop
0x18006e18d  mov     rcx, r14
0x18006e190  call    _lambda_c3b9f7a6bf3a675a648bda1db91c274b_____lambda_c3b9f7a6bf3a675a648bda1db91c274b_
0x18006e195  mov     eax, ebx
0x18006e197  jmp     loc_18006E338
0x18006e19c  test    r15d, r15d
0x18006e19f  jz      loc_18006E2DA
0x18006e1a5  mov     rax, [rsp+0D8h+var_98]
0x18006e1aa  test    rax, rax
0x18006e1ad  jz      short loc_18006E1B4
0x18006e1af  mov     rcx, [rax]
0x18006e1b2  jmp     short loc_18006E1B6
0x18006e1b4  xor     ecx, ecx
0x18006e1b6  mov     [rsp+0D8h+Handles], rcx
0x18006e1be  mov     rax, [rsp+0D8h+var_A8]
0x18006e1c3  test    rax, rax
0x18006e1c6  jz      short loc_18006E1CD
0x18006e1c8  mov     rcx, [rax]
0x18006e1cb  jmp     short loc_18006E1CF
0x18006e1cd  xor     ecx, ecx
0x18006e1cf  mov     [rsp+0D8h+var_40], rcx
0x18006e1d7  mov     r9d, r15d; dwMilliseconds
0x18006e1da  xor     r8d, r8d; bWaitAll
0x18006e1dd  lea     rdx, [rsp+0D8h+Handles]; lpHandles
0x18006e1e5  lea     ecx, [r8+2]; nCount
0x18006e1e9  call    cs:__imp_WaitForMultipleObjects
0x18006e1ef  cmp     eax, 102h
0x18006e1f4  jnz     short loc_18006E268
0x18006e1f6  mov     rcx, [rsp+0D8h]; this
0x18006e1fe  mov     ebx, 800705B4h
0x18006e203  mov     r9d, ebx; char *
0x18006e206  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006e20d  mov     edx, 40h ; '@'; void *
0x18006e212  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e217  nop
0x18006e218  lea     rcx, [rsp+0D8h+var_B0]
0x18006e21d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006e222  nop
0x18006e223  test    rsi, rsi
0x18006e226  jz      short loc_18006E238
0x18006e228  mov     rax, [rsi]
0x18006e22b  mov     rcx, rsi
0x18006e22e  mov     rax, [rax+10h]
0x18006e232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e237  nop
0x18006e238  lea     rcx, [rsp+0D8h+var_A8]
0x18006e23d  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18006e242  nop
0x18006e243  lea     rcx, [rsp+0D8h+var_98]
0x18006e248  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18006e24d  nop
0x18006e24e  lea     rcx, [rsp+0D8h+var_B8]
0x18006e253  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006e258  nop
0x18006e259  mov     rcx, r14
0x18006e25c  call    _lambda_c3b9f7a6bf3a675a648bda1db91c274b_____lambda_c3b9f7a6bf3a675a648bda1db91c274b_
0x18006e261  mov     eax, ebx
0x18006e263  jmp     loc_18006E338
0x18006e268  cmp     eax, 1
0x18006e26b  jnz     short loc_18006E2DA
0x18006e26d  mov     rcx, [rsp+0D8h]; this
0x18006e275  mov     ebx, 80004005h
0x18006e27a  mov     r9d, ebx; char *
0x18006e27d  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006e284  lea     edx, [rax+40h]; void *
0x18006e287  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e28c  nop
0x18006e28d  lea     rcx, [rsp+0D8h+var_B0]
0x18006e292  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006e297  nop
0x18006e298  test    rsi, rsi
0x18006e29b  jz      short loc_18006E2AD
0x18006e29d  mov     rax, [rsi]
0x18006e2a0  mov     rcx, rsi
0x18006e2a3  mov     rax, [rax+10h]
0x18006e2a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e2ac  nop
0x18006e2ad  lea     rcx, [rsp+0D8h+var_A8]
0x18006e2b2  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18006e2b7  nop
0x18006e2b8  lea     rcx, [rsp+0D8h+var_98]
0x18006e2bd  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18006e2c2  nop
0x18006e2c3  lea     rcx, [rsp+0D8h+var_B8]
0x18006e2c8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006e2cd  nop
0x18006e2ce  mov     rcx, r14
0x18006e2d1  call    _lambda_c3b9f7a6bf3a675a648bda1db91c274b_____lambda_c3b9f7a6bf3a675a648bda1db91c274b_
0x18006e2d6  mov     eax, ebx
0x18006e2d8  jmp     short loc_18006E338
0x18006e2da  lea     rcx, [rsp+0D8h+var_B0]
0x18006e2df  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006e2e4  nop
0x18006e2e5  test    rsi, rsi
0x18006e2e8  jz      short loc_18006E2FA
0x18006e2ea  mov     rax, [rsi]
0x18006e2ed  mov     rcx, rsi
0x18006e2f0  mov     rax, [rax+10h]
0x18006e2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e2f9  nop
0x18006e2fa  lea     rcx, [rsp+0D8h+var_A8]
0x18006e2ff  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18006e304  nop
0x18006e305  lea     rcx, [rsp+0D8h+var_98]
0x18006e30a  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18006e30f  nop
0x18006e310  lea     rcx, [rsp+0D8h+var_B8]
0x18006e315  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006e31a  nop
0x18006e31b  mov     rcx, r14
0x18006e31e  call    _lambda_c3b9f7a6bf3a675a648bda1db91c274b_____lambda_c3b9f7a6bf3a675a648bda1db91c274b_
0x18006e323  xor     eax, eax
0x18006e325  jmp     short loc_18006E338
0x18006e327  mov     rcx, [rsp+0D8h+var_88]
0x18006e32c  call    _lambda_c3b9f7a6bf3a675a648bda1db91c274b_____lambda_c3b9f7a6bf3a675a648bda1db91c274b_
0x18006e331  mov     eax, dword ptr [rsp+0D8h+Handles]
0x18006e338  mov     rcx, [rsp+0D8h+var_28]
0x18006e340  xor     rcx, rsp; StackCookie
0x18006e343  call    __security_check_cookie
0x18006e348  lea     r11, [rsp+0D8h+var_18]
0x18006e350  mov     rbx, [r11+30h]
0x18006e354  mov     rsi, [r11+38h]
0x18006e358  mov     rsp, r11
0x18006e35b  pop     r15
0x18006e35d  pop     r14
0x18006e35f  pop     rdi
0x18006e360  retn
```
