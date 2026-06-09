# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x18007613c`
- end: `0x180076281`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180076644`

## callees

- `0x1800053e0`
- `0x180009be4`
- `0x18000d678`
- `0x18000da60`
- `0x18007613c`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180076205`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180076205`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007621a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007621a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVAppData_Internal_InstallControl_Preview_Store_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVAppData_Internal_InstallControl_Preview_Store_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_PEAVAppData_Internal_InstallControl_Preview_Store_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVAppData_Internal_InstallControl_Preview_Store_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVAppData_Internal_InstallControl_Preview_Store_ApplicationModel_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVAppData_Internal_InstallControl_Preview_Store_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVAppData_Internal_InstallControl_Preview_Store_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_PEAVAppData_Internal_InstallControl_Preview_Store_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  _DWORD *v2; // rbx
  signed int v3; // edi
  HANDLE Event; // rax
  signed int LastError; // eax
  _DWORD *v7; // [rsp+30h] [rbp+8h] BYREF
  _DWORD *v8; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = &Windows::Storage::Streams::IBufferByteAccess::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>'};
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    v2[12] = 0;
    *((_QWORD *)v2 + 7) = 0;
    v7 = v2;
    v8 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    *((_QWORD *)v2 + 7) = Event;
    if ( Event )
      goto LABEL_10;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_10:
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 8LL))(v2);
      *a1 = v2;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v7);
      v3 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v7);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<EnterpriseDeviceManagement::Enrollment::GetManagementUrlsResults *>,Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::GetManagementUrlsResults *>,Windows::Internal::CMarshaledInterfaceResult<EnterpriseDeviceManagement::Enrollment::IGetManagementUrlsResults>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::~MakeAllocator<Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<EnterpriseDeviceManagement::Enrollment::GetManagementUrlsResults *>,Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::GetManagementUrlsResults *>,Windows::Internal::CMarshaledInterfaceResult<EnterpriseDeviceManagement::Enrollment::IGetManagementUrlsResults>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>(&v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18007613c  mov     [rsp+arg_10], rbx
0x180076141  mov     [rsp+arg_18], rsi
0x180076146  push    rdi
0x180076147  sub     rsp, 20h
0x18007614b  mov     rsi, rcx
0x18007614e  mov     qword ptr [rcx], 0
0x180076155  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007615c  mov     ecx, 40h ; '@'; unsigned __int64
0x180076161  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180076166  mov     rbx, rax
0x180076169  mov     [rsp+28h+arg_8], rax
0x18007616e  test    rax, rax
0x180076171  jnz     short loc_18007617D
0x180076173  mov     edi, 8007000Eh
0x180076178  jmp     loc_180076264
0x18007617d  lea     rax, ??_7IBufferByteAccess@Streams@Storage@Windows@@6B@; const Windows::Storage::Streams::IBufferByteAccess::`vftable'
0x180076184  mov     [rbx], rax
0x180076187  lea     rdi, [rbx+8]
0x18007618b  mov     rcx, rdi; this
0x18007618e  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180076193  mov     dword ptr [rbx+2Ch], 1
0x18007619a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>'}
0x1800761a1  mov     [rbx], rax
0x1800761a4  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800761ab  mov     [rdi], rax
0x1800761ae  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800761b5  test    rcx, rcx
0x1800761b8  jz      short loc_1800761C7
0x1800761ba  mov     rax, [rcx]
0x1800761bd  mov     rax, [rax+8]
0x1800761c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800761c6  nop
0x1800761c7  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>'}
0x1800761ce  mov     [rbx], rax
0x1800761d1  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800761d8  mov     [rdi], rax
0x1800761db  mov     dword ptr [rbx+30h], 0
0x1800761e2  mov     qword ptr [rbx+38h], 0
0x1800761ea  mov     [rsp+28h+arg_0], rbx
0x1800761ef  mov     [rsp+28h+arg_8], 0
0x1800761f8  mov     r9d, 1F0003h; dwDesiredAccess
0x1800761fe  xor     r8d, r8d; dwFlags
0x180076201  xor     edx, edx; lpName
0x180076203  xor     ecx, ecx; lpEventAttributes
0x180076205  call    cs:__imp_CreateEventExW
0x18007620c  nop     dword ptr [rax+rax+00h]
0x180076211  mov     [rbx+38h], rax
0x180076215  test    rax, rax
0x180076218  jnz     short loc_180076245
0x18007621a  call    cs:__imp_GetLastError
0x180076221  nop     dword ptr [rax+rax+00h]
0x180076226  mov     edi, eax
0x180076228  test    eax, eax
0x18007622a  jle     short loc_180076235
0x18007622c  movzx   edi, ax
0x18007622f  or      edi, 80070000h
0x180076235  test    edi, edi
0x180076237  jns     short loc_180076245
0x180076239  lea     rcx, [rsp+28h+arg_0]
0x18007623e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180076243  jmp     short loc_180076264
0x180076245  mov     rax, [rbx]
0x180076248  mov     rcx, rbx
0x18007624b  mov     rax, [rax+8]
0x18007624f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076254  nop
0x180076255  mov     [rsi], rbx
0x180076258  lea     rcx, [rsp+28h+arg_0]
0x18007625d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180076262  xor     edi, edi
0x180076264  lea     rcx, [rsp+28h+arg_8]
0x180076269  call    ??1?$MakeAllocator@V?$AsyncOperation@U?$IAsyncOperation@PEAVGetManagementUrlsResults@Enrollment@EnterpriseDeviceManagement@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVGetManagementUrlsResults@Enrollment@EnterpriseDeviceManagement@@@23@V?$CMarshaledInterfaceResult@UIGetManagementUrlsResults@Enrollment@EnterpriseDeviceManagement@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<EnterpriseDeviceManagement::Enrollment::GetManagementUrlsResults *>,Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::GetManagementUrlsResults *>,Windows::Internal::CMarshaledInterfaceResult<EnterpriseDeviceManagement::Enrollment::IGetManagementUrlsResults>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::~MakeAllocator<Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<EnterpriseDeviceManagement::Enrollment::GetManagementUrlsResults *>,Windows::Foundation::IAsyncOperationCompletedHandler<EnterpriseDeviceManagement::Enrollment::GetManagementUrlsResults *>,Windows::Internal::CMarshaledInterfaceResult<EnterpriseDeviceManagement::Enrollment::IGetManagementUrlsResults>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>(void)
0x18007626e  mov     eax, edi
0x180076270  mov     rbx, [rsp+28h+arg_10]
0x180076275  mov     rsi, [rsp+28h+arg_18]
0x18007627a  add     rsp, 20h
0x18007627e  pop     rdi
0x18007627f  retn
```
