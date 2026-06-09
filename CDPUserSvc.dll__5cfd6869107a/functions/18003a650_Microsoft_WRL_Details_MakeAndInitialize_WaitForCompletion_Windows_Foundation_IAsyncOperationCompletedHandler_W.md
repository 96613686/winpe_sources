# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x18003a650`
- end: `0x18003a788`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18003afb0`

## callees

- `0x180003678`
- `0x18000c864`
- `0x180024b8c`
- `0x18002c5e4`
- `0x18003a650`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003a719`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003a719`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a728`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a728`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_W4AppServiceConnectionStatus_AppService_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  _DWORD *v2; // rbx
  signed int v3; // edi
  HANDLE Event; // rax
  signed int LastError; // eax
  _DWORD *v7; // [rsp+30h] [rbp+8h] BYREF
  _DWORD *v8; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v8 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = &Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>'};
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>'::`2'::FTMEventDelegate::`vftable';
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
  Microsoft::WRL::Details::MakeAllocator<CDPComActivityStore>::~MakeAllocator<CDPComActivityStore>(&v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003a650  mov     [rsp+arg_10], rbx
0x18003a655  mov     [rsp+arg_18], rsi
0x18003a65a  push    rdi
0x18003a65b  sub     rsp, 20h
0x18003a65f  mov     rsi, rcx
0x18003a662  mov     qword ptr [rcx], 0
0x18003a669  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003a670  mov     ecx, 40h ; '@'; unsigned __int64
0x18003a675  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003a67a  mov     rbx, rax
0x18003a67d  mov     [rsp+28h+arg_8], rax
0x18003a682  test    rax, rax
0x18003a685  jnz     short loc_18003A691
0x18003a687  mov     edi, 8007000Eh
0x18003a68c  jmp     loc_18003A76C
0x18003a691  lea     rax, ??_7?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>::`vftable'
0x18003a698  mov     [rbx], rax
0x18003a69b  lea     rdi, [rbx+8]
0x18003a69f  mov     rcx, rdi; this
0x18003a6a2  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18003a6a7  mov     dword ptr [rbx+2Ch], 1
0x18003a6ae  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>'}
0x18003a6b5  mov     [rbx], rax
0x18003a6b8  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003a6bf  mov     [rdi], rax
0x18003a6c2  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18003a6c9  test    rcx, rcx
0x18003a6cc  jz      short loc_18003A6DB
0x18003a6ce  mov     rax, [rcx]
0x18003a6d1  mov     rax, [rax+8]
0x18003a6d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a6da  nop
0x18003a6db  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>'}
0x18003a6e2  mov     [rbx], rax
0x18003a6e5  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003a6ec  mov     [rdi], rax
0x18003a6ef  mov     dword ptr [rbx+30h], 0
0x18003a6f6  mov     qword ptr [rbx+38h], 0
0x18003a6fe  mov     [rsp+28h+arg_0], rbx
0x18003a703  mov     [rsp+28h+arg_8], 0
0x18003a70c  mov     r9d, 1F0003h; dwDesiredAccess
0x18003a712  xor     r8d, r8d; dwFlags
0x18003a715  xor     edx, edx; lpName
0x18003a717  xor     ecx, ecx; lpEventAttributes
0x18003a719  call    cs:__imp_CreateEventExW
0x18003a71f  mov     [rbx+38h], rax
0x18003a723  test    rax, rax
0x18003a726  jnz     short loc_18003A74D
0x18003a728  call    cs:__imp_GetLastError
0x18003a72e  mov     edi, eax
0x18003a730  test    eax, eax
0x18003a732  jle     short loc_18003A73D
0x18003a734  movzx   edi, ax
0x18003a737  or      edi, 80070000h
0x18003a73d  test    edi, edi
0x18003a73f  jns     short loc_18003A74D
0x18003a741  lea     rcx, [rsp+28h+arg_0]
0x18003a746  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a74b  jmp     short loc_18003A76C
0x18003a74d  mov     rax, [rbx]
0x18003a750  mov     rcx, rbx
0x18003a753  mov     rax, [rax+8]
0x18003a757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a75c  nop
0x18003a75d  mov     [rsi], rbx
0x18003a760  lea     rcx, [rsp+28h+arg_0]
0x18003a765  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003a76a  xor     edi, edi
0x18003a76c  lea     rcx, [rsp+28h+arg_8]
0x18003a771  call    ??1?$MakeAllocator@VCDPComActivityStore@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CDPComActivityStore>::~MakeAllocator<CDPComActivityStore>(void)
0x18003a776  mov     eax, edi
0x18003a778  mov     rbx, [rsp+28h+arg_10]
0x18003a77d  mov     rsi, [rsp+28h+arg_18]
0x18003a782  add     rsp, 20h
0x18003a786  pop     rdi
0x18003a787  retn
```
