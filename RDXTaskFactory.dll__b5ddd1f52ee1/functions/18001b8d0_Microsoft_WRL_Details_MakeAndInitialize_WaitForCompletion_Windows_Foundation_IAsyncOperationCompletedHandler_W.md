# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>,Windows::Foundation::IAsyncOperation<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>>(Windows::Foundation::IAsyncOperation<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>,Windows::Foundation::IAsyncOperation<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>>(Windows::Foundation::IAsyncOperation<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>,Windows::Foundation::IAsyncOperation<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>>(Windows::Foundation::IAsyncOperation<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x18001b8d0`
- end: `0x18001ba08`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4EnrollmentReturnResult@DataModel@BioEnrollment@UI@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4EnrollmentReturnResult@DataModel@BioEnrollment@UI@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4EnrollmentReturnResult@DataModel@BioEnrollment@UI@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4EnrollmentReturnResult@DataModel@BioEnrollment@UI@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4EnrollmentReturnResult@DataModel@BioEnrollment@UI@Internal@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4EnrollmentReturnResult@DataModel@BioEnrollment@UI@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4EnrollmentReturnResult@DataModel@BioEnrollment@UI@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4EnrollmentReturnResult@DataModel@BioEnrollment@UI@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001bb2c`

## callees

- `0x18000534c`
- `0x180008bbc`
- `0x18000e108`
- `0x18000e264`
- `0x18001b8d0`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001b999`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001b999`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b9a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b9a8`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_W4EnrollmentReturnResult_DataModel_BioEnrollment_UI_Internal_Windows___Foundation_Windows__U__IAsyncOperation_W4EnrollmentReturnResult_DataModel_BioEnrollment_UI_Internal_Windows___23___YAJPEAU__IAsyncOperation_W4EnrollmentReturnResult_DataModel_BioEnrollment_UI_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_W4EnrollmentReturnResult_DataModel_BioEnrollment_UI_Internal_Windows___Foundation_Windows__U__IAsyncOperation_W4EnrollmentReturnResult_DataModel_BioEnrollment_UI_Internal_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_W4EnrollmentReturnResult_DataModel_BioEnrollment_UI_Internal_Windows___Foundation_Windows__U__IAsyncOperation_W4EnrollmentReturnResult_DataModel_BioEnrollment_UI_Internal_Windows___23___YAJPEAU__IAsyncOperation_W4EnrollmentReturnResult_DataModel_BioEnrollment_UI_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  _DWORD *v2; // rbx
  signed int v3; // edi
  HANDLE Event; // rax
  signed int LastError; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8
  _DWORD *v11; // [rsp+30h] [rbp+8h] BYREF
  _DWORD *v12; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>'};
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>,Windows::Foundation::IAsyncOperation<enum Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>>'::`2'::FTMEventDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>,Windows::Foundation::IAsyncOperation<enum Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>,Windows::Foundation::IAsyncOperation<enum Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>>'::`2'::FTMEventDelegate::`vftable';
    v2[12] = 0;
    *((_QWORD *)v2 + 7) = 0;
    v11 = v2;
    v12 = 0;
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
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11, v8, v9);
      v3 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11, v6, v7);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<SetWallpaperTask>::~MakeAllocator<SetWallpaperTask>(&v12);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001b8d0  mov     [rsp+arg_10], rbx
0x18001b8d5  mov     [rsp+arg_18], rsi
0x18001b8da  push    rdi
0x18001b8db  sub     rsp, 20h
0x18001b8df  mov     rsi, rcx
0x18001b8e2  mov     qword ptr [rcx], 0
0x18001b8e9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b8f0  mov     ecx, 40h ; '@'; unsigned __int64
0x18001b8f5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001b8fa  mov     rbx, rax
0x18001b8fd  mov     [rsp+28h+arg_8], rax
0x18001b902  test    rax, rax
0x18001b905  jnz     short loc_18001B911
0x18001b907  mov     edi, 8007000Eh
0x18001b90c  jmp     loc_18001B9EC
0x18001b911  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>::`vftable'
0x18001b918  mov     [rbx], rax
0x18001b91b  lea     rdi, [rbx+8]
0x18001b91f  mov     rcx, rdi; this
0x18001b922  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18001b927  mov     dword ptr [rbx+2Ch], 1
0x18001b92e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4EnrollmentReturnResult@DataModel@BioEnrollment@UI@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@W4EnrollmentReturnResult@DataModel@BioEnrollment@UI@Internal@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>'}
0x18001b935  mov     [rbx], rax
0x18001b938  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4EnrollmentReturnResult@DataModel@BioEnrollment@UI@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4EnrollmentReturnResult@DataModel@BioEnrollment@UI@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4EnrollmentReturnResult@DataModel@BioEnrollment@UI@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>,Windows::Foundation::IAsyncOperation<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>>(Windows::Foundation::IAsyncOperation<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001b93f  mov     [rdi], rax
0x18001b942  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001b949  test    rcx, rcx
0x18001b94c  jz      short loc_18001B95B
0x18001b94e  mov     rax, [rcx]
0x18001b951  mov     rax, [rax+8]
0x18001b955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b95a  nop
0x18001b95b  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4EnrollmentReturnResult@DataModel@BioEnrollment@UI@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4EnrollmentReturnResult@DataModel@BioEnrollment@UI@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4EnrollmentReturnResult@DataModel@BioEnrollment@UI@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@W4EnrollmentReturnResult@DataModel@BioEnrollment@UI@Internal@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>,Windows::Foundation::IAsyncOperation<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>>(Windows::Foundation::IAsyncOperation<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>'}
0x18001b962  mov     [rbx], rax
0x18001b965  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4EnrollmentReturnResult@DataModel@BioEnrollment@UI@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4EnrollmentReturnResult@DataModel@BioEnrollment@UI@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4EnrollmentReturnResult@DataModel@BioEnrollment@UI@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>,Windows::Foundation::IAsyncOperation<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult>>(Windows::Foundation::IAsyncOperation<Windows::Internal::UI::BioEnrollment::DataModel::EnrollmentReturnResult> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001b96c  mov     [rdi], rax
0x18001b96f  mov     dword ptr [rbx+30h], 0
0x18001b976  mov     qword ptr [rbx+38h], 0
0x18001b97e  mov     [rsp+28h+arg_0], rbx
0x18001b983  mov     [rsp+28h+arg_8], 0
0x18001b98c  mov     r9d, 1F0003h; dwDesiredAccess
0x18001b992  xor     r8d, r8d; dwFlags
0x18001b995  xor     edx, edx; lpName
0x18001b997  xor     ecx, ecx; lpEventAttributes
0x18001b999  call    cs:__imp_CreateEventExW
0x18001b99f  mov     [rbx+38h], rax
0x18001b9a3  test    rax, rax
0x18001b9a6  jnz     short loc_18001B9CD
0x18001b9a8  call    cs:__imp_GetLastError
0x18001b9ae  mov     edi, eax
0x18001b9b0  test    eax, eax
0x18001b9b2  jle     short loc_18001B9BD
0x18001b9b4  movzx   edi, ax
0x18001b9b7  or      edi, 80070000h
0x18001b9bd  test    edi, edi
0x18001b9bf  jns     short loc_18001B9CD
0x18001b9c1  lea     rcx, [rsp+28h+arg_0]
0x18001b9c6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b9cb  jmp     short loc_18001B9EC
0x18001b9cd  mov     rax, [rbx]
0x18001b9d0  mov     rcx, rbx
0x18001b9d3  mov     rax, [rax+8]
0x18001b9d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9dc  nop
0x18001b9dd  mov     [rsi], rbx
0x18001b9e0  lea     rcx, [rsp+28h+arg_0]
0x18001b9e5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b9ea  xor     edi, edi
0x18001b9ec  lea     rcx, [rsp+28h+arg_8]
0x18001b9f1  call    ??1?$MakeAllocator@VSetWallpaperTask@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<SetWallpaperTask>::~MakeAllocator<SetWallpaperTask>(void)
0x18001b9f6  mov     eax, edi
0x18001b9f8  mov     rbx, [rsp+28h+arg_10]
0x18001b9fd  mov     rsi, [rsp+28h+arg_18]
0x18001ba02  add     rsp, 20h
0x18001ba06  pop     rdi
0x18001ba07  retn
```
