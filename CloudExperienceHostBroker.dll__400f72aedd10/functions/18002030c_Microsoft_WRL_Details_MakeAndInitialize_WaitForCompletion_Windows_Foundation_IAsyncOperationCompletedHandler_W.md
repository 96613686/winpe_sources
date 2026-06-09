# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x18002030c`
- end: `0x180020444`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020dd8`

## callees

- `0x180002980`
- `0x180002a3c`
- `0x180009668`
- `0x18000ba24`
- `0x18002030c`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800203d5`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800203d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800203e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800203e4`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUIBuffer_Streams_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PEAUIBuffer_Streams_Storage_Windows___23___YAJPEAU__IAsyncOperation_PEAUIBuffer_Streams_Storage_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUIBuffer_Streams_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PEAUIBuffer_Streams_Storage_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUIBuffer_Streams_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PEAUIBuffer_Streams_Storage_Windows___23___YAJPEAU__IAsyncOperation_PEAUIBuffer_Streams_Storage_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
    *(_QWORD *)v2 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>'};
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *>>'::`2'::FTMEventDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = &`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *>>'::`2'::FTMEventDelegate::`vftable';
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
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostBroker::RetailDemo::ConfigureRetailDemoExitRetailDemo,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::~MakeAllocator<Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostBroker::RetailDemo::ConfigureRetailDemoExitRetailDemo,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>(&v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002030c  mov     [rsp+arg_10], rbx
0x180020311  mov     [rsp+arg_18], rsi
0x180020316  push    rdi
0x180020317  sub     rsp, 20h
0x18002031b  mov     rsi, rcx
0x18002031e  mov     qword ptr [rcx], 0
0x180020325  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002032c  mov     ecx, 40h ; '@'; unsigned __int64
0x180020331  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180020336  mov     rbx, rax
0x180020339  mov     [rsp+28h+arg_8], rax
0x18002033e  test    rax, rax
0x180020341  jnz     short loc_18002034D
0x180020343  mov     edi, 8007000Eh
0x180020348  jmp     loc_180020428
0x18002034d  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>::`vftable'
0x180020354  mov     [rbx], rax
0x180020357  lea     rdi, [rbx+8]
0x18002035b  mov     rcx, rdi; this
0x18002035e  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180020363  mov     dword ptr [rbx+2Ch], 1
0x18002036a  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>'}
0x180020371  mov     [rbx], rax
0x180020374  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18002037b  mov     [rdi], rax
0x18002037e  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180020385  test    rcx, rcx
0x180020388  jz      short loc_180020397
0x18002038a  mov     rax, [rcx]
0x18002038d  mov     rax, [rax+8]
0x180020391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020396  nop
0x180020397  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>'}
0x18002039e  mov     [rbx], rax
0x1800203a1  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800203a8  mov     [rdi], rax
0x1800203ab  mov     dword ptr [rbx+30h], 0
0x1800203b2  mov     qword ptr [rbx+38h], 0
0x1800203ba  mov     [rsp+28h+arg_0], rbx
0x1800203bf  mov     [rsp+28h+arg_8], 0
0x1800203c8  mov     r9d, 1F0003h; dwDesiredAccess
0x1800203ce  xor     r8d, r8d; dwFlags
0x1800203d1  xor     edx, edx; lpName
0x1800203d3  xor     ecx, ecx; lpEventAttributes
0x1800203d5  call    cs:__imp_CreateEventExW
0x1800203db  mov     [rbx+38h], rax
0x1800203df  test    rax, rax
0x1800203e2  jnz     short loc_180020409
0x1800203e4  call    cs:__imp_GetLastError
0x1800203ea  mov     edi, eax
0x1800203ec  test    eax, eax
0x1800203ee  jle     short loc_1800203F9
0x1800203f0  movzx   edi, ax
0x1800203f3  or      edi, 80070000h
0x1800203f9  test    edi, edi
0x1800203fb  jns     short loc_180020409
0x1800203fd  lea     rcx, [rsp+28h+arg_0]
0x180020402  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020407  jmp     short loc_180020428
0x180020409  mov     rax, [rbx]
0x18002040c  mov     rcx, rbx
0x18002040f  mov     rax, [rax+8]
0x180020413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020418  nop
0x180020419  mov     [rsi], rbx
0x18002041c  lea     rcx, [rsp+28h+arg_0]
0x180020421  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020426  xor     edi, edi
0x180020428  lea     rcx, [rsp+28h+arg_8]
0x18002042d  call    ??1?$MakeAllocator@V?$AsyncOperation@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@VCNoResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncCausalityOptions@$1?ConfigureRetailDemoExitRetailDemo@RetailDemo@CloudExperienceHostBroker@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostBroker::RetailDemo::ConfigureRetailDemoExitRetailDemo,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::~MakeAllocator<Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostBroker::RetailDemo::ConfigureRetailDemoExitRetailDemo,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>(void)
0x180020432  mov     eax, edi
0x180020434  mov     rbx, [rsp+28h+arg_10]
0x180020439  mov     rsi, [rsp+28h+arg_18]
0x18002043e  add     rsp, 20h
0x180020442  pop     rdi
0x180020443  retn
```
