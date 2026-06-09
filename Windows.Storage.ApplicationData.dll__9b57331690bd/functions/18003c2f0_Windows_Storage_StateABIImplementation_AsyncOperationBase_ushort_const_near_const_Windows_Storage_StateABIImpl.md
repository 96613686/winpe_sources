# Windows::Storage::StateABIImplementation::AsyncOperationBase<&ushort const near * const Windows::Storage::StateABIImplementation::ClearOperationDefaultName>::OnStart(void)

- ea: `0x18003c2f0`
- end: `0x18003c419`
- name: `?OnStart@?$AsyncOperationBase@$1?ClearOperationDefaultName@StateABIImplementation@Storage@Windows@@3QBGB@StateABIImplementation@Storage@Windows@@UEAAJXZ`
- size: `297`
- prototype: `HRESULT __fastcall(Windows::Storage::StateABIImplementation::AsyncOperationBase<&Windows::Storage::StateABIImplementation::ClearOperationDefaultName> *this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800022b0`
- `0x180002ff0`
- `0x180009778`
- `0x180021efc`
- `0x18003ba30`
- `0x18003c2f0`
- `0x18003c8a0`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003c3c8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003c3c8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18003c385`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18003c385`

## string_xrefs

- `0x18003c319`: `create ready`
- `0x18003c357`: `create cancel`
- `0x18003c3a9`: `CreateThreadpoolWork`

## pseudocode

```c
__int64 __fastcall Windows::Storage::StateABIImplementation::AsyncOperationBase<&unsigned short const near * const Windows::Storage::StateABIImplementation::ClearOperationDefaultName>::OnStart(
        Windows::Storage::StateABIImplementation::AsyncOperationBase<&Windows::Storage::StateABIImplementation::ClearOperationDefaultName> *this,
        __int64 a2,
        const wchar_t *a3,
        _SECURITY_ATTRIBUTES *a4)
{
  wil::event_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> *v4; // rsi
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // ebx
  const wchar_t *v7; // r8
  _SECURITY_ATTRIBUTES *v8; // r9
  wil::unique_any_t<wil::event_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> > *p_cancelEvent; // rbx
  _TP_WORK *ThreadpoolWork; // rax
  unsigned int v11; // edx
  int v12; // r8d
  void *retaddr; // [rsp+38h] [rbp+0h]
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (__cdecl*)(_TP_WORK *),&CloseThreadpoolWork,wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t> > > pWork; // [rsp+40h] [rbp+8h] BYREF

  v4 = (wil::event_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> *)&this->gap80;
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((wil::event_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> *)&this->gap80, None, a3, a4);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
  {
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((wil::event_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> *)&this->refCount_, None, v7, v8);
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
    {
      p_cancelEvent = &this[-1].cancelEvent;
      (*((void (__fastcall **)(wil::unique_any_t<wil::event_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> > *))this[-1].cancelEvent.m_ptr
       + 1))(&this[-1].cancelEvent);
      ThreadpoolWork = CreateThreadpoolWork(
                         Windows::Storage::StateABIImplementation::AsyncOperationBase<&unsigned short const near * const Windows::Storage::StateABIImplementation::SetVersionAsyncOperationName>::DoWorkStub,
                         &this[-1].cancelEvent,
                         0);
      pWork.m_ptr = ThreadpoolWork;
      if ( ThreadpoolWork )
      {
        SubmitThreadpoolWork(ThreadpoolWork);
        _wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_NKH_Z(
          v4,
          v11,
          v12);
        event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = (int)p_cancelEvent[20].m_ptr;
        if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
          event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = 0;
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            0x7Bu,
            "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\Windows.Storage.AsyncOperationBase.hpp",
            event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z);
      }
      else
      {
        (*((void (__fastcall **)(wil::unique_any_t<wil::event_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__cdecl*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> > *))p_cancelEvent->m_ptr
         + 2))(&this[-1].cancelEvent);
        event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = wil::details::in1diag3::Return_GetLastErrorMsg(retaddr, 0x6Cu, "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\Windows.Storage.AsyncOperationBase.hpp", "CreateThreadpoolWork");
      }
      wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&void CloseThreadpoolWork(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&void CloseThreadpoolWork(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(&pWork);
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x61u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\Windows.Storage.AsyncOperationBase.hpp",
        event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
        "create cancel");
    }
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x60u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\Windows.Storage.AsyncOperationBase.hpp",
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
      "create ready");
  }
  return (unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
}

```

## disassembly

```asm
0x18003c2f0  mov     [rsp+arg_8], rbx
0x18003c2f5  mov     [rsp+arg_10], rsi
0x18003c2fa  push    rdi
0x18003c2fb  sub     rsp, 30h
0x18003c2ff  lea     rsi, [this+80h]
0x18003c306  mov     rdi, this
0x18003c309  mov     this, rsi; this
0x18003c30c  xor     edx, edx; options
0x18003c30e  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18003c313  mov     ebx, eax
0x18003c315  test    eax, eax
0x18003c317  jns     short loc_18003C343
0x18003c319  lea     rax, aCreateReady; "create ready"
0x18003c320  mov     edx, 60h ; '`'; lineNumber
0x18003c325  mov     this, [rsp+38h]; callerReturnAddress
0x18003c32a  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003c331  mov     r9d, ebx; hr
0x18003c334  mov     [rsp+38h+formatString], rax; formatString
0x18003c339  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003c33e  jmp     loc_18003C407
0x18003c343  lea     this, [rdi+88h]; this
0x18003c34a  xor     edx, edx; options
0x18003c34c  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18003c351  mov     ebx, eax
0x18003c353  test    eax, eax
0x18003c355  jns     short loc_18003C365
0x18003c357  lea     rax, aCreateCancel; "create cancel"
0x18003c35e  mov     edx, 61h ; 'a'
0x18003c363  jmp     short loc_18003C325
0x18003c365  lea     rbx, [rdi-10h]
0x18003c369  mov     rax, [rbx]
0x18003c36c  mov     this, rbx
0x18003c36f  mov     rax, [rax+8]
0x18003c373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c378  xor     r8d, r8d; pcbe
0x18003c37b  lea     this, ?DoWorkStub@?$AsyncOperationBase@$1?SetVersionAsyncOperationName@StateABIImplementation@Storage@Windows@@3QBGB@StateABIImplementation@Storage@Windows@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18003c382  mov     rdx, rbx; pv
0x18003c385  call    cs:__imp_CreateThreadpoolWork
0x18003c38b  mov     [rsp+38h+pWork.m_ptr], rax
0x18003c390  test    rax, rax
0x18003c393  jnz     short loc_18003C3C5
0x18003c395  mov     rax, [rbx]
0x18003c398  mov     this, rbx
0x18003c39b  mov     rax, [rax+10h]
0x18003c39f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3a4  mov     this, [rsp+38h]; callerReturnAddress
0x18003c3a9  lea     r9, aCreatethreadpo_0; "CreateThreadpoolWork"
0x18003c3b0  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003c3b7  mov     edx, 6Ch ; 'l'; lineNumber
0x18003c3bc  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18003c3c1  mov     ebx, eax
0x18003c3c3  jmp     short loc_18003C3FD
0x18003c3c5  mov     this, rax; pwk
0x18003c3c8  call    cs:__imp_SubmitThreadpoolWork
0x18003c3ce  mov     this, rsi; this
0x18003c3d1  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA_NKH@Z
0x18003c3d6  mov     ebx, [rbx+0A0h]
0x18003c3dc  test    ebx, ebx
0x18003c3de  jns     short loc_18003C3FB
0x18003c3e0  mov     this, [rsp+38h]; callerReturnAddress
0x18003c3e5  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003c3ec  mov     r9d, ebx; hr
0x18003c3ef  mov     edx, 7Bh ; '{'; lineNumber
0x18003c3f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c3f9  jmp     short loc_18003C3FD
0x18003c3fb  xor     ebx, ebx
0x18003c3fd  lea     this, [rsp+38h+pWork]; this
0x18003c402  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?CloseThreadpoolWork@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&CloseThreadpoolWork(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&CloseThreadpoolWork(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)
0x18003c407  mov     rsi, [rsp+38h+arg_10]
0x18003c40c  mov     eax, ebx
0x18003c40e  mov     rbx, [rsp+38h+arg_8]
0x18003c413  add     rsp, 30h
0x18003c417  pop     rdi
0x18003c418  retn
```
