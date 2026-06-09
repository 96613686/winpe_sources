# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180032898`
- end: `0x1800329d0`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180032b98`

## callees

- `0x18000534c`
- `0x180008bbc`
- `0x18000e108`
- `0x18000e264`
- `0x180032898`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180032961`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180032961`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032970`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032970`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_PEAVAppServiceResponse_AppService_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>'};
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
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
0x180032898  mov     [rsp+arg_10], rbx
0x18003289d  mov     [rsp+arg_18], rsi
0x1800328a2  push    rdi
0x1800328a3  sub     rsp, 20h
0x1800328a7  mov     rsi, rcx
0x1800328aa  mov     qword ptr [rcx], 0
0x1800328b1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800328b8  mov     ecx, 40h ; '@'; unsigned __int64
0x1800328bd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800328c2  mov     rbx, rax
0x1800328c5  mov     [rsp+28h+arg_8], rax
0x1800328ca  test    rax, rax
0x1800328cd  jnz     short loc_1800328D9
0x1800328cf  mov     edi, 8007000Eh
0x1800328d4  jmp     loc_1800329B4
0x1800328d9  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>::`vftable'
0x1800328e0  mov     [rbx], rax
0x1800328e3  lea     rdi, [rbx+8]
0x1800328e7  mov     rcx, rdi; this
0x1800328ea  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800328ef  mov     dword ptr [rbx+2Ch], 1
0x1800328f6  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>'}
0x1800328fd  mov     [rbx], rax
0x180032900  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180032907  mov     [rdi], rax
0x18003290a  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180032911  test    rcx, rcx
0x180032914  jz      short loc_180032923
0x180032916  mov     rax, [rcx]
0x180032919  mov     rax, [rax+8]
0x18003291d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032922  nop
0x180032923  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceResponse *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>'}
0x18003292a  mov     [rbx], rax
0x18003292d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180032934  mov     [rdi], rax
0x180032937  mov     dword ptr [rbx+30h], 0
0x18003293e  mov     qword ptr [rbx+38h], 0
0x180032946  mov     [rsp+28h+arg_0], rbx
0x18003294b  mov     [rsp+28h+arg_8], 0
0x180032954  mov     r9d, 1F0003h; dwDesiredAccess
0x18003295a  xor     r8d, r8d; dwFlags
0x18003295d  xor     edx, edx; lpName
0x18003295f  xor     ecx, ecx; lpEventAttributes
0x180032961  call    cs:__imp_CreateEventExW
0x180032967  mov     [rbx+38h], rax
0x18003296b  test    rax, rax
0x18003296e  jnz     short loc_180032995
0x180032970  call    cs:__imp_GetLastError
0x180032976  mov     edi, eax
0x180032978  test    eax, eax
0x18003297a  jle     short loc_180032985
0x18003297c  movzx   edi, ax
0x18003297f  or      edi, 80070000h
0x180032985  test    edi, edi
0x180032987  jns     short loc_180032995
0x180032989  lea     rcx, [rsp+28h+arg_0]
0x18003298e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180032993  jmp     short loc_1800329B4
0x180032995  mov     rax, [rbx]
0x180032998  mov     rcx, rbx
0x18003299b  mov     rax, [rax+8]
0x18003299f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800329a4  nop
0x1800329a5  mov     [rsi], rbx
0x1800329a8  lea     rcx, [rsp+28h+arg_0]
0x1800329ad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800329b2  xor     edi, edi
0x1800329b4  lea     rcx, [rsp+28h+arg_8]
0x1800329b9  call    ??1?$MakeAllocator@VSetWallpaperTask@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<SetWallpaperTask>::~MakeAllocator<SetWallpaperTask>(void)
0x1800329be  mov     eax, edi
0x1800329c0  mov     rbx, [rsp+28h+arg_10]
0x1800329c5  mov     rsi, [rsp+28h+arg_18]
0x1800329ca  add     rsp, 20h
0x1800329ce  pop     rdi
0x1800329cf  retn
```
