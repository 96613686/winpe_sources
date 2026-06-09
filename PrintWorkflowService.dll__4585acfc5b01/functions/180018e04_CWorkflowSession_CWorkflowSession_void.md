# CWorkflowSession::~CWorkflowSession(void)

- ea: `0x180018e04`
- end: `0x180018f89`
- name: `??1CWorkflowSession@@UEAA@XZ`
- size: `389`
- prototype: `void __fastcall(CWorkflowSession *this, __int64, int, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180016840`

## callees

- `0x180001614`
- `0x180003cc4`
- `0x1800075ac`
- `0x18000a128`
- `0x18001665c`
- `0x1800166a8`
- `0x180018e04`
- `0x180019e24`
- `0x18002397c`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018ed8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180018ed8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018f52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018f64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018f52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018f64`

## pseudocode

```c
void __fastcall CWorkflowSession::~CWorkflowSession(CWorkflowSession *this, __int64 a2, int a3, int a4)
{
  unsigned __int64 v5; // rdx
  void *v6; // rcx
  _QWORD *v7; // rsi
  _QWORD *i; // rdi
  __int64 v9; // rcx
  int v10; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = &CWorkflowSession::`vftable'{for `IInspectable'};
  *((_QWORD *)this + 1) = &CWorkflowSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IFastRundown>,IWeakReferenceSource,Windows::Graphics::Internal::Printing::Workflow::IWorkflowSession>'};
  *((_QWORD *)this + 2) = &CWorkflowSession::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 3) = &CWorkflowSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Graphics::Internal::Printing::Workflow::IWorkflowSession>'};
  if ( (unsigned int)dword_180083038 > 5 )
  {
    v10 = *((_DWORD *)this + 88);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180083038,
      (unsigned int)&byte_18007049F,
      a3,
      a4,
      (__int64)&v10);
  }
  CWorkflowSession::RemoveFromSessionMap(this);
  v6 = (void *)*((_QWORD *)this + 13);
  if ( v6 )
    operator delete(v6, v5);
  v7 = (_QWORD *)*((_QWORD *)this + 24);
  for ( i = (_QWORD *)*((_QWORD *)this + 23); i != v7; ++i )
  {
    if ( *i )
      (**(void (__fastcall ***)(_QWORD, __int64))*i)(*i, 1);
  }
  WorkflowSessionCommon::~WorkflowSessionCommon((CWorkflowSession *)((char *)this + 280));
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 256);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
  v9 = *((_QWORD *)this + 23);
  if ( v9 )
  {
    std::_Deallocate<16>(v9, (*((_QWORD *)this + 25) - v9) & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)this + 23) = 0;
    *((_QWORD *)this + 24) = 0;
    *((_QWORD *)this + 25) = 0;
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 176);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 168);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 160);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ((char *)this + 152);
  WindowsDeleteString(*((HSTRING *)this + 7));
  *((_QWORD *)this + 7) = 0;
  WindowsDeleteString(*((HSTRING *)this + 6));
  *((_QWORD *)this + 6) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::CloakedIid<IFastRundown>,Windows::Graphics::Internal::Printing::Workflow::IWorkflowSession>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::CloakedIid<IFastRundown>,Windows::Graphics::Internal::Printing::Workflow::IWorkflowSession>(this);
}

```

## disassembly

```asm
0x180018e04  mov     r11, rsp
0x180018e07  mov     [r11+10h], rbx
0x180018e0b  mov     [r11+18h], rsi
0x180018e0f  push    rdi
0x180018e10  sub     rsp, 30h
0x180018e14  mov     rbx, rcx
0x180018e17  lea     rax, ??_7CWorkflowSession@@6BIInspectable@@@; const CWorkflowSession::`vftable'{for `IInspectable'}
0x180018e1e  mov     [rcx], rax
0x180018e21  lea     rax, ??_7CWorkflowSession@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UIFastRundown@@@23@UIWeakReferenceSource@@UIWorkflowSession@Workflow@Printing@Internal@Graphics@Windows@@@Details@WRL@Microsoft@@@; const CWorkflowSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IFastRundown>,IWeakReferenceSource,Windows::Graphics::Internal::Printing::Workflow::IWorkflowSession>'}
0x180018e28  mov     [rcx+8], rax
0x180018e2c  lea     rax, ??_7CWorkflowSession@@6BIWeakReferenceSource@@@; const CWorkflowSession::`vftable'{for `IWeakReferenceSource'}
0x180018e33  mov     [rcx+10h], rax
0x180018e37  lea     rax, ??_7CWorkflowSession@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWorkflowSession@Workflow@Printing@Internal@Graphics@Windows@@@Details@WRL@Microsoft@@@; const CWorkflowSession::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Graphics::Internal::Printing::Workflow::IWorkflowSession>'}
0x180018e3e  mov     [rcx+18h], rax
0x180018e42  mov     eax, cs:dword_180083038
0x180018e48  cmp     eax, 5
0x180018e4b  jbe     short loc_180018E72
0x180018e4d  mov     eax, [rcx+160h]
0x180018e53  mov     [rsp+38h+arg_0], eax
0x180018e57  lea     rax, [r11+8]
0x180018e5b  mov     [r11-18h], rax
0x180018e5f  lea     rdx, byte_18007049F
0x180018e66  lea     rcx, dword_180083038
0x180018e6d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180018e72  mov     rcx, rbx; this
0x180018e75  call    ?RemoveFromSessionMap@CWorkflowSession@@QEAAXXZ; CWorkflowSession::RemoveFromSessionMap(void)
0x180018e7a  mov     rcx, [rbx+68h]; void *
0x180018e7e  test    rcx, rcx
0x180018e81  jz      short loc_180018E88
0x180018e83  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018e88  mov     rsi, [rbx+0C0h]
0x180018e8f  mov     rdi, [rbx+0B8h]
0x180018e96  jmp     short loc_180018EB4
0x180018e98  mov     rcx, [rdi]
0x180018e9b  test    rcx, rcx
0x180018e9e  jz      short loc_180018EB0
0x180018ea0  mov     rax, [rcx]
0x180018ea3  mov     edx, 1
0x180018ea8  mov     rax, [rax]
0x180018eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018eb0  add     rdi, 8
0x180018eb4  cmp     rdi, rsi
0x180018eb7  jnz     short loc_180018E98
0x180018eb9  lea     rcx, [rbx+118h]; this
0x180018ec0  call    ??1WorkflowSessionCommon@@UEAA@XZ; WorkflowSessionCommon::~WorkflowSessionCommon(void)
0x180018ec5  lea     rcx, [rbx+100h]
0x180018ecc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180018ed1  lea     rcx, [rbx+0D0h]; lpCriticalSection
0x180018ed8  call    cs:__imp_DeleteCriticalSection
0x180018ede  mov     rcx, [rbx+0B8h]
0x180018ee5  test    rcx, rcx
0x180018ee8  jz      short loc_180018F1E
0x180018eea  mov     rdx, [rbx+0C8h]
0x180018ef1  sub     rdx, rcx
0x180018ef4  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180018ef8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180018efd  mov     qword ptr [rbx+0B8h], 0
0x180018f08  mov     qword ptr [rbx+0C0h], 0
0x180018f13  mov     qword ptr [rbx+0C8h], 0
0x180018f1e  lea     rcx, [rbx+0B0h]
0x180018f25  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018f2a  lea     rcx, [rbx+0A8h]
0x180018f31  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018f36  lea     rcx, [rbx+0A0h]
0x180018f3d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018f42  lea     rcx, [rbx+98h]
0x180018f49  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018f4e  mov     rcx, [rbx+38h]; string
0x180018f52  call    cs:__imp_WindowsDeleteString
0x180018f58  mov     qword ptr [rbx+38h], 0
0x180018f60  mov     rcx, [rbx+30h]; string
0x180018f64  call    cs:__imp_WindowsDeleteString
0x180018f6a  mov     qword ptr [rbx+30h], 0
0x180018f72  mov     rcx, rbx
0x180018f75  mov     rbx, [rsp+38h+arg_8]
0x180018f7a  mov     rsi, [rsp+38h+arg_10]
0x180018f7f  add     rsp, 30h
0x180018f83  pop     rdi
0x180018f84  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$CloakedIid@UIFastRundown@@@23@UIWorkflowSession@Workflow@Printing@Internal@Graphics@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::CloakedIid<IFastRundown>,Windows::Graphics::Internal::Printing::Workflow::IWorkflowSession>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::CloakedIid<IFastRundown>,Windows::Graphics::Internal::Printing::Workflow::IWorkflowSession>(void)
```
