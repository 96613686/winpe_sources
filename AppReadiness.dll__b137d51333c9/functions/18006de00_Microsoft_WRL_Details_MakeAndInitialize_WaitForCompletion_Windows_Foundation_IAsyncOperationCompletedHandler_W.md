# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x18006de00`
- end: `0x18006df38`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006e1d0`

## callees

- `0x1800028ac`
- `0x180002958`
- `0x180033ff8`
- `0x180040338`
- `0x18006de00`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18006dec9`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18006dec9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ded8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ded8`

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
    *(_QWORD *)v2 = &Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>'};
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = &`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>>'::`2'::FTMEventDelegate::`vftable';
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
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
      v3 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<AppReadiness::Tasks::ResolveStoreCategories>::~MakeAllocator<AppReadiness::Tasks::ResolveStoreCategories>(&v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18006de00  mov     [rsp+arg_10], rbx
0x18006de05  mov     [rsp+arg_18], rsi
0x18006de0a  push    rdi
0x18006de0b  sub     rsp, 20h
0x18006de0f  mov     rsi, rcx
0x18006de12  mov     qword ptr [rcx], 0
0x18006de19  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006de20  mov     ecx, 40h ; '@'; unsigned __int64
0x18006de25  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006de2a  mov     rbx, rax
0x18006de2d  mov     [rsp+28h+arg_8], rax
0x18006de32  test    rax, rax
0x18006de35  jnz     short loc_18006DE41
0x18006de37  mov     edi, 8007000Eh
0x18006de3c  jmp     loc_18006DF1C
0x18006de41  lea     rax, ??_7?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>::`vftable'
0x18006de48  mov     [rbx], rax
0x18006de4b  lea     rdi, [rbx+8]
0x18006de4f  mov     rcx, rdi; this
0x18006de52  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18006de57  mov     dword ptr [rbx+2Ch], 1
0x18006de5e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>'}
0x18006de65  mov     [rbx], rax
0x18006de68  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18006de6f  mov     [rdi], rax
0x18006de72  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18006de79  test    rcx, rcx
0x18006de7c  jz      short loc_18006DE8B
0x18006de7e  mov     rax, [rcx]
0x18006de81  mov     rax, [rax+8]
0x18006de85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006de8a  nop
0x18006de8b  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>'}
0x18006de92  mov     [rbx], rax
0x18006de95  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18006de9c  mov     [rdi], rax
0x18006de9f  mov     dword ptr [rbx+30h], 0
0x18006dea6  mov     qword ptr [rbx+38h], 0
0x18006deae  mov     [rsp+28h+arg_0], rbx
0x18006deb3  mov     [rsp+28h+arg_8], 0
0x18006debc  mov     r9d, 1F0003h; dwDesiredAccess
0x18006dec2  xor     r8d, r8d; dwFlags
0x18006dec5  xor     edx, edx; lpName
0x18006dec7  xor     ecx, ecx; lpEventAttributes
0x18006dec9  call    cs:__imp_CreateEventExW
0x18006decf  mov     [rbx+38h], rax
0x18006ded3  test    rax, rax
0x18006ded6  jnz     short loc_18006DEFD
0x18006ded8  call    cs:__imp_GetLastError
0x18006dede  mov     edi, eax
0x18006dee0  test    eax, eax
0x18006dee2  jle     short loc_18006DEED
0x18006dee4  movzx   edi, ax
0x18006dee7  or      edi, 80070000h
0x18006deed  test    edi, edi
0x18006deef  jns     short loc_18006DEFD
0x18006def1  lea     rcx, [rsp+28h+arg_0]
0x18006def6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006defb  jmp     short loc_18006DF1C
0x18006defd  mov     rax, [rbx]
0x18006df00  mov     rcx, rbx
0x18006df03  mov     rax, [rax+8]
0x18006df07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006df0c  nop
0x18006df0d  mov     [rsi], rbx
0x18006df10  lea     rcx, [rsp+28h+arg_0]
0x18006df15  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006df1a  xor     edi, edi
0x18006df1c  lea     rcx, [rsp+28h+arg_8]
0x18006df21  call    ??1?$MakeAllocator@VResolveStoreCategories@Tasks@AppReadiness@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<AppReadiness::Tasks::ResolveStoreCategories>::~MakeAllocator<AppReadiness::Tasks::ResolveStoreCategories>(void)
0x18006df26  mov     eax, edi
0x18006df28  mov     rbx, [rsp+28h+arg_10]
0x18006df2d  mov     rsi, [rsp+28h+arg_18]
0x18006df32  add     rsp, 20h
0x18006df36  pop     rdi
0x18006df37  retn
```
