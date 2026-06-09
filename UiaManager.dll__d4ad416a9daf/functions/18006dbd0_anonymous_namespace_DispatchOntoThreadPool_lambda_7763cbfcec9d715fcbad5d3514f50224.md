# _anonymous_namespace_::DispatchOntoThreadPool__lambda_7763cbfcec9d715fcbad5d3514f50224___

- ea: `0x18006dbd0`
- end: `0x18006df95`
- name: `_anonymous_namespace_::DispatchOntoThreadPool__lambda_7763cbfcec9d715fcbad5d3514f50224___`
- size: `965`
- prototype: `__int64 __fastcall(DWORD dwMilliseconds, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006f310`

## callees

- `0x1800054f8`
- `0x180006edc`
- `0x18001607c`
- `0x18001d9c4`
- `0x180043680`
- `0x18006d9b8`
- `0x18006daf0`
- `0x18006dbd0`
- `0x18006e368`
- `0x18006e988`
- `0x18006ebf8`
- `0x18006ec28`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18006de1d`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18006de1d`

## string_xrefs

- `0x18006dc34`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x18006dceb`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x18006dd6e`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x18006de3a`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x18006deb1`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::DispatchOntoThreadPool__lambda_7763cbfcec9d715fcbad5d3514f50224___(
        DWORD dwMilliseconds,
        const unsigned __int16 *a2)
{
  _QWORD *v4; // rax
  int v5; // eax
  unsigned int v6; // ebx
  __int64 result; // rax
  __int64 v8; // rax
  HANDLE v9; // rsi
  const char *v10; // r9
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HANDLE, __int64 *); // rbx
  int v13; // eax
  unsigned int v14; // ebx
  void *v15; // rcx
  void *v16; // rcx
  DWORD v17; // eax
  int v18[2]; // [rsp+20h] [rbp-B8h] BYREF
  __int64 v19; // [rsp+28h] [rbp-B0h] BYREF
  _QWORD v20[2]; // [rsp+30h] [rbp-A8h] BYREF
  _QWORD v21[2]; // [rsp+40h] [rbp-98h] BYREF
  const unsigned __int16 *v22; // [rsp+50h] [rbp-88h]
  _BYTE v23[56]; // [rsp+58h] [rbp-80h] BYREF
  HANDLE Handles[4]; // [rsp+90h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v22 = a2;
  *(_QWORD *)v18 = 0;
  v4 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                   (HSTRING *)Handles,
                   (const unsigned __int16 (*)[36])a2);
  v5 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Threading::IThreadPoolStatics>>(
         *v4,
         v18);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
      (const char *)(unsigned int)v5,
      v18[0]);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v18);
    lambda_c3b9f7a6bf3a675a648bda1db91c274b_::__lambda_c3b9f7a6bf3a675a648bda1db91c274b_(a2);
    return v6;
  }
  try
  {
    LODWORD(Handles[0]) = 1;
    ____0W4EventOptions_wil_____shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
      v21,
      Handles);
    LODWORD(Handles[0]) = 1;
    ____0W4EventOptions_wil_____shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
      v20,
      Handles);
    v8 = lambda_3d1a2ea0a4679e06f5ff1be96072533d_::_lambda_3d1a2ea0a4679e06f5ff1be96072533d_(v23, a2, v21, v20);
    Microsoft::WRL::Callback_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::System::Threading::IWorkItemHandler_Microsoft::WRL::FtmBase___lambda_1ddc2e9ef88e8669f1009dc0cd1b8f2f___(
      Handles,
      v8);
    lambda_3d1a2ea0a4679e06f5ff1be96072533d_::__lambda_3d1a2ea0a4679e06f5ff1be96072533d_(v23);
    v9 = Handles[0];
    if ( Handles[0] )
    {
      v19 = 0;
      v11 = *(_QWORD *)v18;
      v12 = *(__int64 (__fastcall **)(__int64, HANDLE, __int64 *))(**(_QWORD **)v18 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
      v13 = v12(v11, v9, &v19);
      v14 = v13;
      if ( v13 >= 0 )
      {
        if ( dwMilliseconds )
        {
          if ( v21[0] )
            v15 = *(void **)v21[0];
          else
            v15 = 0;
          Handles[0] = v15;
          if ( v20[0] )
            v16 = *(void **)v20[0];
          else
            v16 = 0;
          Handles[1] = v16;
          v17 = WaitForMultipleObjects(2u, Handles, 0, dwMilliseconds);
          if ( v17 == 258 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x40,
              (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
              (const char *)0x800705B4LL,
              v18[0]);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
            if ( v9 )
              (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v9 + 16LL))(v9);
            std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(v20);
            std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(v21);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v18);
            lambda_c3b9f7a6bf3a675a648bda1db91c274b_::__lambda_c3b9f7a6bf3a675a648bda1db91c274b_(a2);
            return 2147943860LL;
          }
          if ( v17 == 1 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x41,
              (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
              (const char *)0x80004005LL,
              v18[0]);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
            if ( v9 )
              (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v9 + 16LL))(v9);
            std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(v20);
            std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(v21);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v18);
            lambda_c3b9f7a6bf3a675a648bda1db91c274b_::__lambda_c3b9f7a6bf3a675a648bda1db91c274b_(a2);
            return 2147500037LL;
          }
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
        if ( v9 )
          (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v9 + 16LL))(v9);
        std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(v20);
        std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(v21);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v18);
        lambda_c3b9f7a6bf3a675a648bda1db91c274b_::__lambda_c3b9f7a6bf3a675a648bda1db91c274b_(a2);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
        (const char *)(unsigned int)v13,
        v18[0]);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
      if ( v9 )
        (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v9 + 16LL))(v9);
      std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(v20);
      std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(v21);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v18);
      lambda_c3b9f7a6bf3a675a648bda1db91c274b_::__lambda_c3b9f7a6bf3a675a648bda1db91c274b_(a2);
      result = v14;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
        (const char *)0x8007000ELL,
        v18[0]);
      std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(v20);
      std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(v21);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v18);
      lambda_c3b9f7a6bf3a675a648bda1db91c274b_::__lambda_c3b9f7a6bf3a675a648bda1db91c274b_(a2);
      result = 2147942414LL;
    }
  }
  catch ( ... )
  {
    LODWORD(Handles[0]) = wil::details::in1diag3::Return_CaughtException(
                            retaddr,
                            (void *)0x45,
                            (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
                            v10);
    lambda_c3b9f7a6bf3a675a648bda1db91c274b_::__lambda_c3b9f7a6bf3a675a648bda1db91c274b_(v22);
    return LODWORD(Handles[0]);
  }
  return result;
}

```

## disassembly

```asm
0x18006dbd0  mov     r11, rsp
0x18006dbd3  mov     [r11+18h], rbx
0x18006dbd7  mov     [r11+20h], rsi
0x18006dbdb  push    rdi
0x18006dbdc  push    r14
0x18006dbde  push    r15
0x18006dbe0  sub     rsp, 0C0h
0x18006dbe7  mov     rax, cs:__security_cookie
0x18006dbee  xor     rax, rsp
0x18006dbf1  mov     [rsp+0D8h+var_28], rax
0x18006dbf9  mov     r14, rdx
0x18006dbfc  mov     r15d, ecx
0x18006dbff  mov     [rsp+0D8h+var_88], rdx
0x18006dc04  mov     qword ptr [rsp+0D8h+var_B8], 0; int
0x18006dc0d  lea     rcx, [r11-48h]; string
0x18006dc11  call    ??$?0$0CE@@StringReference@Internal@Windows@@QEAA@AEAY0CE@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[36])
0x18006dc16  lea     rdx, [rsp+0D8h+var_B8]
0x18006dc1b  mov     rcx, [rax]
0x18006dc1e  call    ??$GetActivationFactory@V?$ComPtr@UIThreadPoolStatics@Threading@System@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIThreadPoolStatics@Threading@System@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::System::Threading::IThreadPoolStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Threading::IThreadPoolStatics>>)
0x18006dc23  mov     ebx, eax
0x18006dc25  test    eax, eax
0x18006dc27  jns     short loc_18006DC60
0x18006dc29  mov     rcx, [rsp+0D8h]; this
0x18006dc31  mov     r9d, eax; char *
0x18006dc34  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006dc3b  mov     edx, 21h ; '!'; void *
0x18006dc40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006dc45  nop
0x18006dc46  lea     rcx, [rsp+0D8h+var_B8]
0x18006dc4b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006dc50  nop
0x18006dc51  mov     rcx, r14
0x18006dc54  call    _lambda_c3b9f7a6bf3a675a648bda1db91c274b_____lambda_c3b9f7a6bf3a675a648bda1db91c274b_
0x18006dc59  mov     eax, ebx
0x18006dc5b  jmp     loc_18006DF6C
0x18006dc60  mov     dword ptr [rsp+0D8h+Handles], 1
0x18006dc6b  lea     rdx, [rsp+0D8h+Handles]
0x18006dc73  lea     rcx, [rsp+0D8h+var_98]
0x18006dc78  call    ??$?0W4EventOptions@wil@@@?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x18006dc7d  nop
0x18006dc7e  mov     dword ptr [rsp+0D8h+Handles], 1
0x18006dc89  lea     rdx, [rsp+0D8h+Handles]
0x18006dc91  lea     rcx, [rsp+0D8h+var_A8]
0x18006dc96  call    ??$?0W4EventOptions@wil@@@?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x18006dc9b  nop
0x18006dc9c  lea     r9, [rsp+0D8h+var_A8]
0x18006dca1  lea     r8, [rsp+0D8h+var_98]
0x18006dca6  mov     rdx, r14
0x18006dca9  lea     rcx, [rsp+0D8h+var_80]
0x18006dcae  call    _lambda_3d1a2ea0a4679e06f5ff1be96072533d____lambda_3d1a2ea0a4679e06f5ff1be96072533d_
0x18006dcb3  mov     rdx, rax
0x18006dcb6  lea     rcx, [rsp+0D8h+Handles]
0x18006dcbe  call    Microsoft__WRL__Callback_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__Windows__System__Threading__IWorkItemHandler_Microsoft__WRL__FtmBase___lambda_1ddc2e9ef88e8669f1009dc0cd1b8f2f___
0x18006dcc3  nop
0x18006dcc4  lea     rcx, [rsp+0D8h+var_80]
0x18006dcc9  call    _lambda_3d1a2ea0a4679e06f5ff1be96072533d_____lambda_3d1a2ea0a4679e06f5ff1be96072533d_
0x18006dcce  mov     rsi, [rsp+0D8h+Handles]
0x18006dcd6  test    rsi, rsi
0x18006dcd9  jnz     short loc_18006DD2B
0x18006dcdb  mov     rcx, [rsp+0D8h]; this
0x18006dce3  mov     ebx, 8007000Eh
0x18006dce8  mov     r9d, ebx; char *
0x18006dceb  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006dcf2  lea     edx, [rsi+37h]; void *
0x18006dcf5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006dcfa  nop
0x18006dcfb  lea     rcx, [rsp+0D8h+var_A8]
0x18006dd00  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18006dd05  nop
0x18006dd06  lea     rcx, [rsp+0D8h+var_98]
0x18006dd0b  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18006dd10  nop
0x18006dd11  lea     rcx, [rsp+0D8h+var_B8]
0x18006dd16  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006dd1b  nop
0x18006dd1c  mov     rcx, r14
0x18006dd1f  call    _lambda_c3b9f7a6bf3a675a648bda1db91c274b_____lambda_c3b9f7a6bf3a675a648bda1db91c274b_
0x18006dd24  mov     eax, ebx
0x18006dd26  jmp     loc_18006DF6C
0x18006dd2b  mov     [rsp+0D8h+var_B0], 0
0x18006dd34  mov     rdi, qword ptr [rsp+0D8h+var_B8]
0x18006dd39  mov     rax, [rdi]
0x18006dd3c  mov     rbx, [rax+30h]
0x18006dd40  lea     rcx, [rsp+0D8h+var_B0]
0x18006dd45  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006dd4a  lea     r8, [rsp+0D8h+var_B0]
0x18006dd4f  mov     rdx, rsi
0x18006dd52  mov     rcx, rdi
0x18006dd55  mov     rax, rbx
0x18006dd58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dd5d  mov     ebx, eax
0x18006dd5f  test    eax, eax
0x18006dd61  jns     short loc_18006DDD0
0x18006dd63  mov     rcx, [rsp+0D8h]; this
0x18006dd6b  mov     r9d, eax; char *
0x18006dd6e  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006dd75  mov     edx, 3Ah ; ':'; void *
0x18006dd7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006dd7f  nop
0x18006dd80  lea     rcx, [rsp+0D8h+var_B0]
0x18006dd85  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006dd8a  nop
0x18006dd8b  test    rsi, rsi
0x18006dd8e  jz      short loc_18006DDA0
0x18006dd90  mov     rax, [rsi]
0x18006dd93  mov     rcx, rsi
0x18006dd96  mov     rax, [rax+10h]
0x18006dd9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dd9f  nop
0x18006dda0  lea     rcx, [rsp+0D8h+var_A8]
0x18006dda5  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18006ddaa  nop
0x18006ddab  lea     rcx, [rsp+0D8h+var_98]
0x18006ddb0  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18006ddb5  nop
0x18006ddb6  lea     rcx, [rsp+0D8h+var_B8]
0x18006ddbb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006ddc0  nop
0x18006ddc1  mov     rcx, r14
0x18006ddc4  call    _lambda_c3b9f7a6bf3a675a648bda1db91c274b_____lambda_c3b9f7a6bf3a675a648bda1db91c274b_
0x18006ddc9  mov     eax, ebx
0x18006ddcb  jmp     loc_18006DF6C
0x18006ddd0  test    r15d, r15d
0x18006ddd3  jz      loc_18006DF0E
0x18006ddd9  mov     rax, [rsp+0D8h+var_98]
0x18006ddde  test    rax, rax
0x18006dde1  jz      short loc_18006DDE8
0x18006dde3  mov     rcx, [rax]
0x18006dde6  jmp     short loc_18006DDEA
0x18006dde8  xor     ecx, ecx
0x18006ddea  mov     [rsp+0D8h+Handles], rcx
0x18006ddf2  mov     rax, [rsp+0D8h+var_A8]
0x18006ddf7  test    rax, rax
0x18006ddfa  jz      short loc_18006DE01
0x18006ddfc  mov     rcx, [rax]
0x18006ddff  jmp     short loc_18006DE03
0x18006de01  xor     ecx, ecx
0x18006de03  mov     [rsp+0D8h+var_40], rcx
0x18006de0b  mov     r9d, r15d; dwMilliseconds
0x18006de0e  xor     r8d, r8d; bWaitAll
0x18006de11  lea     rdx, [rsp+0D8h+Handles]; lpHandles
0x18006de19  lea     ecx, [r8+2]; nCount
0x18006de1d  call    cs:__imp_WaitForMultipleObjects
0x18006de23  cmp     eax, 102h
0x18006de28  jnz     short loc_18006DE9C
0x18006de2a  mov     rcx, [rsp+0D8h]; this
0x18006de32  mov     ebx, 800705B4h
0x18006de37  mov     r9d, ebx; char *
0x18006de3a  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006de41  mov     edx, 40h ; '@'; void *
0x18006de46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006de4b  nop
0x18006de4c  lea     rcx, [rsp+0D8h+var_B0]
0x18006de51  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006de56  nop
0x18006de57  test    rsi, rsi
0x18006de5a  jz      short loc_18006DE6C
0x18006de5c  mov     rax, [rsi]
0x18006de5f  mov     rcx, rsi
0x18006de62  mov     rax, [rax+10h]
0x18006de66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006de6b  nop
0x18006de6c  lea     rcx, [rsp+0D8h+var_A8]
0x18006de71  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18006de76  nop
0x18006de77  lea     rcx, [rsp+0D8h+var_98]
0x18006de7c  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18006de81  nop
0x18006de82  lea     rcx, [rsp+0D8h+var_B8]
0x18006de87  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006de8c  nop
0x18006de8d  mov     rcx, r14
0x18006de90  call    _lambda_c3b9f7a6bf3a675a648bda1db91c274b_____lambda_c3b9f7a6bf3a675a648bda1db91c274b_
0x18006de95  mov     eax, ebx
0x18006de97  jmp     loc_18006DF6C
0x18006de9c  cmp     eax, 1
0x18006de9f  jnz     short loc_18006DF0E
0x18006dea1  mov     rcx, [rsp+0D8h]; this
0x18006dea9  mov     ebx, 80004005h
0x18006deae  mov     r9d, ebx; char *
0x18006deb1  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006deb8  lea     edx, [rax+40h]; void *
0x18006debb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006dec0  nop
0x18006dec1  lea     rcx, [rsp+0D8h+var_B0]
0x18006dec6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006decb  nop
0x18006decc  test    rsi, rsi
0x18006decf  jz      short loc_18006DEE1
0x18006ded1  mov     rax, [rsi]
0x18006ded4  mov     rcx, rsi
0x18006ded7  mov     rax, [rax+10h]
0x18006dedb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dee0  nop
0x18006dee1  lea     rcx, [rsp+0D8h+var_A8]
0x18006dee6  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18006deeb  nop
0x18006deec  lea     rcx, [rsp+0D8h+var_98]
0x18006def1  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18006def6  nop
0x18006def7  lea     rcx, [rsp+0D8h+var_B8]
0x18006defc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006df01  nop
0x18006df02  mov     rcx, r14
0x18006df05  call    _lambda_c3b9f7a6bf3a675a648bda1db91c274b_____lambda_c3b9f7a6bf3a675a648bda1db91c274b_
0x18006df0a  mov     eax, ebx
0x18006df0c  jmp     short loc_18006DF6C
0x18006df0e  lea     rcx, [rsp+0D8h+var_B0]
0x18006df13  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006df18  nop
0x18006df19  test    rsi, rsi
0x18006df1c  jz      short loc_18006DF2E
0x18006df1e  mov     rax, [rsi]
0x18006df21  mov     rcx, rsi
0x18006df24  mov     rax, [rax+10h]
0x18006df28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006df2d  nop
0x18006df2e  lea     rcx, [rsp+0D8h+var_A8]
0x18006df33  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18006df38  nop
0x18006df39  lea     rcx, [rsp+0D8h+var_98]
0x18006df3e  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18006df43  nop
0x18006df44  lea     rcx, [rsp+0D8h+var_B8]
0x18006df49  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006df4e  nop
0x18006df4f  mov     rcx, r14
0x18006df52  call    _lambda_c3b9f7a6bf3a675a648bda1db91c274b_____lambda_c3b9f7a6bf3a675a648bda1db91c274b_
0x18006df57  xor     eax, eax
0x18006df59  jmp     short loc_18006DF6C
0x18006df5b  mov     rcx, [rsp+0D8h+var_88]
0x18006df60  call    _lambda_c3b9f7a6bf3a675a648bda1db91c274b_____lambda_c3b9f7a6bf3a675a648bda1db91c274b_
0x18006df65  mov     eax, dword ptr [rsp+0D8h+Handles]
0x18006df6c  mov     rcx, [rsp+0D8h+var_28]
0x18006df74  xor     rcx, rsp; StackCookie
0x18006df77  call    __security_check_cookie
0x18006df7c  lea     r11, [rsp+0D8h+var_18]
0x18006df84  mov     rbx, [r11+30h]
0x18006df88  mov     rsi, [r11+38h]
0x18006df8c  mov     rsp, r11
0x18006df8f  pop     r15
0x18006df91  pop     r14
0x18006df93  pop     rdi
0x18006df94  retn
```
