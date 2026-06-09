# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180009474`
- end: `0x1800095aa`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800096e8`

## callees

- `0x180001d84`
- `0x180003c7c`
- `0x180003ee4`
- `0x1800071a4`
- `0x180009474`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000953c`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000953c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000954b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000954b`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVStorageFile_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PEAVStorageFile_Storage_Windows___23___YAJPEAU__IAsyncOperation_PEAVStorageFile_Storage_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVStorageFile_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PEAVStorageFile_Storage_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVStorageFile_Storage_Windows___Foundation_Windows__U__IAsyncOperation_PEAVStorageFile_Storage_Windows___23___YAJPEAU__IAsyncOperation_PEAVStorageFile_Storage_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  _QWORD *v2; // rdi
  signed int v3; // ebx
  _QWORD *v4; // rbx
  struct Microsoft::WRL::Details::ModuleBase *v5; // rcx
  HANDLE Event; // rax
  signed int LastError; // eax
  _QWORD *v9; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v10; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v10 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v2 = v10;
  if ( v10 )
  {
    v4 = v10 + 1;
    *v10 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 1));
    v5 = Microsoft::WRL::Details::ModuleBase::module_;
    *v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>'};
    v2[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    *((_DWORD *)v2 + 11) = 1;
    if ( v5 )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v5 + 8LL))(v5);
    *((_DWORD *)v2 + 12) = 0;
    *v2 = &`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>'::`2'::FTMEventDelegate::`vftable';
    v2[7] = 0;
    *v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    v9 = v2;
    v10 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    v2[7] = Event;
    if ( Event )
      goto LABEL_10;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_10:
      (*(void (__fastcall **)(_QWORD *))(*v2 + 8LL))(v2);
      *a1 = v2;
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v9);
      v3 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(&v9);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>>::~MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>>(&v10);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180009474  mov     [rsp+arg_10], rbx
0x180009479  mov     [rsp+arg_18], rsi
0x18000947e  push    rdi
0x18000947f  sub     rsp, 20h
0x180009483  mov     rsi, rcx
0x180009486  mov     qword ptr [rcx], 0
0x18000948d  mov     ecx, 40h ; '@'; unsigned __int64
0x180009492  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009499  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000949e  mov     [rsp+28h+arg_8], rax
0x1800094a3  mov     rdi, rax
0x1800094a6  test    rax, rax
0x1800094a9  jnz     short loc_1800094B5
0x1800094ab  mov     ebx, 8007000Eh
0x1800094b0  jmp     loc_18000958E
0x1800094b5  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>::`vftable'
0x1800094bc  lea     rbx, [rdi+8]
0x1800094c0  mov     [rdi], rax
0x1800094c3  mov     rcx, rbx; this
0x1800094c6  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1800094cb  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800094d2  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>'}
0x1800094d9  mov     [rdi], rax
0x1800094dc  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800094e3  mov     [rbx], rax
0x1800094e6  mov     dword ptr [rdi+2Ch], 1
0x1800094ed  test    rcx, rcx
0x1800094f0  jz      short loc_1800094FE
0x1800094f2  mov     rax, [rcx]
0x1800094f5  mov     rax, [rax+8]
0x1800094f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094fe  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>'}
0x180009505  mov     dword ptr [rdi+30h], 0
0x18000950c  mov     [rdi], rax
0x18000950f  mov     r9d, 1F0003h; dwDesiredAccess
0x180009515  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000951c  mov     qword ptr [rdi+38h], 0
0x180009524  xor     r8d, r8d; dwFlags
0x180009527  mov     [rbx], rax
0x18000952a  xor     edx, edx; lpName
0x18000952c  mov     [rsp+28h+arg_0], rdi
0x180009531  xor     ecx, ecx; lpEventAttributes
0x180009533  mov     [rsp+28h+arg_8], 0
0x18000953c  call    cs:__imp_CreateEventExW
0x180009542  mov     [rdi+38h], rax
0x180009546  test    rax, rax
0x180009549  jnz     short loc_180009570
0x18000954b  call    cs:__imp_GetLastError
0x180009551  mov     ebx, eax
0x180009553  test    eax, eax
0x180009555  jle     short loc_180009560
0x180009557  movzx   ebx, ax
0x18000955a  or      ebx, 80070000h
0x180009560  test    ebx, ebx
0x180009562  jns     short loc_180009570
0x180009564  lea     rcx, [rsp+28h+arg_0]
0x180009569  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x18000956e  jmp     short loc_18000958E
0x180009570  mov     rax, [rdi]
0x180009573  mov     rcx, rdi
0x180009576  mov     rax, [rax+8]
0x18000957a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000957f  lea     rcx, [rsp+28h+arg_0]
0x180009584  mov     [rsi], rdi
0x180009587  call    ?InternalRelease@?$ComPtr@UIMrtPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IMrtPackageStatics>::InternalRelease(void)
0x18000958c  xor     ebx, ebx
0x18000958e  lea     rcx, [rsp+28h+arg_8]
0x180009593  call    ??1?$MakeAllocator@V?$SimpleSealedActivationFactory@VAppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>>::~MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>>(void)
0x180009598  mov     rsi, [rsp+28h+arg_18]
0x18000959d  mov     eax, ebx
0x18000959f  mov     rbx, [rsp+28h+arg_10]
0x1800095a4  add     rsp, 20h
0x1800095a8  pop     rdi
0x1800095a9  retn
```
