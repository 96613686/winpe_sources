# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x18006dcc0`
- end: `0x18006ddf8`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006e040`

## callees

- `0x1800028ac`
- `0x180002958`
- `0x180033ff8`
- `0x180040338`
- `0x18006dcc0`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18006dd89`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18006dd89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dd98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006dd98`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVAppData_Internal_InstallControl_Preview_Store_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVAppData_Internal_InstallControl_Preview_Store_ApplicationModel_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVAppData_Internal_InstallControl_Preview_Store_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVAppData_Internal_InstallControl_Preview_Store_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVAppData_Internal_InstallControl_Preview_Store_ApplicationModel_Windows___Collections_Foundation_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAU__IVectorView_PEAVAppData_Internal_InstallControl_Preview_Store_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows__U__IAsyncOperation_PEAU__IVectorView_PEAVAppData_Internal_InstallControl_Preview_Store_ApplicationModel_Windows___Collections_Foundation_Windows___23___YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVAppData_Internal_InstallControl_Preview_Store_ApplicationModel_Windows___Collections_Foundation_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *>'};
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *>>'::`2'::FTMEventDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = &`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *>>'::`2'::FTMEventDelegate::`vftable';
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
0x18006dcc0  mov     [rsp+arg_10], rbx
0x18006dcc5  mov     [rsp+arg_18], rsi
0x18006dcca  push    rdi
0x18006dccb  sub     rsp, 20h
0x18006dccf  mov     rsi, rcx
0x18006dcd2  mov     qword ptr [rcx], 0
0x18006dcd9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006dce0  mov     ecx, 40h ; '@'; unsigned __int64
0x18006dce5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006dcea  mov     rbx, rax
0x18006dced  mov     [rsp+28h+arg_8], rax
0x18006dcf2  test    rax, rax
0x18006dcf5  jnz     short loc_18006DD01
0x18006dcf7  mov     edi, 8007000Eh
0x18006dcfc  jmp     loc_18006DDDC
0x18006dd01  lea     rax, ??_7?$IAsyncOperationWithProgressCompletedHandler@PEAVDeploymentResult@Deployment@Management@Windows@@UDeploymentProgress@234@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Management::Deployment::DeploymentResult *,Windows::Management::Deployment::DeploymentProgress>::`vftable'
0x18006dd08  mov     [rbx], rax
0x18006dd0b  lea     rdi, [rbx+8]
0x18006dd0f  mov     rcx, rdi; this
0x18006dd12  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18006dd17  mov     dword ptr [rbx+2Ch], 1
0x18006dd1e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *>'}
0x18006dd25  mov     [rbx], rax
0x18006dd28  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18006dd2f  mov     [rdi], rax
0x18006dd32  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18006dd39  test    rcx, rcx
0x18006dd3c  jz      short loc_18006DD4B
0x18006dd3e  mov     rax, [rcx]
0x18006dd41  mov     rax, [rax+8]
0x18006dd45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dd4a  nop
0x18006dd4b  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *>'}
0x18006dd52  mov     [rbx], rax
0x18006dd55  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::ApplicationModel::Store::Preview::InstallControl::Internal::AppData *> *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18006dd5c  mov     [rdi], rax
0x18006dd5f  mov     dword ptr [rbx+30h], 0
0x18006dd66  mov     qword ptr [rbx+38h], 0
0x18006dd6e  mov     [rsp+28h+arg_0], rbx
0x18006dd73  mov     [rsp+28h+arg_8], 0
0x18006dd7c  mov     r9d, 1F0003h; dwDesiredAccess
0x18006dd82  xor     r8d, r8d; dwFlags
0x18006dd85  xor     edx, edx; lpName
0x18006dd87  xor     ecx, ecx; lpEventAttributes
0x18006dd89  call    cs:__imp_CreateEventExW
0x18006dd8f  mov     [rbx+38h], rax
0x18006dd93  test    rax, rax
0x18006dd96  jnz     short loc_18006DDBD
0x18006dd98  call    cs:__imp_GetLastError
0x18006dd9e  mov     edi, eax
0x18006dda0  test    eax, eax
0x18006dda2  jle     short loc_18006DDAD
0x18006dda4  movzx   edi, ax
0x18006dda7  or      edi, 80070000h
0x18006ddad  test    edi, edi
0x18006ddaf  jns     short loc_18006DDBD
0x18006ddb1  lea     rcx, [rsp+28h+arg_0]
0x18006ddb6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006ddbb  jmp     short loc_18006DDDC
0x18006ddbd  mov     rax, [rbx]
0x18006ddc0  mov     rcx, rbx
0x18006ddc3  mov     rax, [rax+8]
0x18006ddc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ddcc  nop
0x18006ddcd  mov     [rsi], rbx
0x18006ddd0  lea     rcx, [rsp+28h+arg_0]
0x18006ddd5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006ddda  xor     edi, edi
0x18006dddc  lea     rcx, [rsp+28h+arg_8]
0x18006dde1  call    ??1?$MakeAllocator@VResolveStoreCategories@Tasks@AppReadiness@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<AppReadiness::Tasks::ResolveStoreCategories>::~MakeAllocator<AppReadiness::Tasks::ResolveStoreCategories>(void)
0x18006dde6  mov     eax, edi
0x18006dde8  mov     rbx, [rsp+28h+arg_10]
0x18006dded  mov     rsi, [rsp+28h+arg_18]
0x18006ddf2  add     rsp, 20h
0x18006ddf6  pop     rdi
0x18006ddf7  retn
```
