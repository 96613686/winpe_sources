# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x18004ae80`
- end: `0x18004afb8`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUICdpLaunchResult@Internal@Contracts@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUICdpLaunchResult@Internal@Contracts@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUICdpLaunchResult@Internal@Contracts@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUICdpLaunchResult@Internal@Contracts@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUICdpLaunchResult@Internal@Contracts@ApplicationModel@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUICdpLaunchResult@Internal@Contracts@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUICdpLaunchResult@Internal@Contracts@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUICdpLaunchResult@Internal@Contracts@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `312`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004b288`

## callees

- `0x180003678`
- `0x18000c864`
- `0x180024b8c`
- `0x18002c5e4`
- `0x18004ae80`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004af49`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004af49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004af58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004af58`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUICdpLaunchResult_Internal_Contracts_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAUICdpLaunchResult_Internal_Contracts_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_PEAUICdpLaunchResult_Internal_Contracts_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUICdpLaunchResult_Internal_Contracts_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAUICdpLaunchResult_Internal_Contracts_ApplicationModel_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUICdpLaunchResult_Internal_Contracts_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAUICdpLaunchResult_Internal_Contracts_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_PEAUICdpLaunchResult_Internal_Contracts_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
    *(_QWORD *)v2 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>'};
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>>'::`2'::FTMEventDelegate::`vftable';
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
0x18004ae80  mov     [rsp+arg_10], rbx
0x18004ae85  mov     [rsp+arg_18], rsi
0x18004ae8a  push    rdi
0x18004ae8b  sub     rsp, 20h
0x18004ae8f  mov     rsi, rcx
0x18004ae92  mov     qword ptr [rcx], 0
0x18004ae99  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004aea0  mov     ecx, 40h ; '@'; unsigned __int64
0x18004aea5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004aeaa  mov     rbx, rax
0x18004aead  mov     [rsp+28h+arg_8], rax
0x18004aeb2  test    rax, rax
0x18004aeb5  jnz     short loc_18004AEC1
0x18004aeb7  mov     edi, 8007000Eh
0x18004aebc  jmp     loc_18004AF9C
0x18004aec1  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAUICdpLaunchResult@Internal@Contracts@ApplicationModel@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>::`vftable'
0x18004aec8  mov     [rbx], rax
0x18004aecb  lea     rdi, [rbx+8]
0x18004aecf  mov     rcx, rdi; this
0x18004aed2  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18004aed7  mov     dword ptr [rbx+2Ch], 1
0x18004aede  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUICdpLaunchResult@Internal@Contracts@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAUICdpLaunchResult@Internal@Contracts@ApplicationModel@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>'}
0x18004aee5  mov     [rbx], rax
0x18004aee8  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUICdpLaunchResult@Internal@Contracts@ApplicationModel@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18004aeef  mov     [rdi], rax
0x18004aef2  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18004aef9  test    rcx, rcx
0x18004aefc  jz      short loc_18004AF0B
0x18004aefe  mov     rax, [rcx]
0x18004af01  mov     rax, [rax+8]
0x18004af05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af0a  nop
0x18004af0b  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUICdpLaunchResult@Internal@Contracts@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUICdpLaunchResult@Internal@Contracts@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUICdpLaunchResult@Internal@Contracts@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAUICdpLaunchResult@Internal@Contracts@ApplicationModel@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>'}
0x18004af12  mov     [rbx], rax
0x18004af15  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUICdpLaunchResult@Internal@Contracts@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUICdpLaunchResult@Internal@Contracts@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUICdpLaunchResult@Internal@Contracts@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Contracts::Internal::ICdpLaunchResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18004af1c  mov     [rdi], rax
0x18004af1f  mov     dword ptr [rbx+30h], 0
0x18004af26  mov     qword ptr [rbx+38h], 0
0x18004af2e  mov     [rsp+28h+arg_0], rbx
0x18004af33  mov     [rsp+28h+arg_8], 0
0x18004af3c  mov     r9d, 1F0003h; dwDesiredAccess
0x18004af42  xor     r8d, r8d; dwFlags
0x18004af45  xor     edx, edx; lpName
0x18004af47  xor     ecx, ecx; lpEventAttributes
0x18004af49  call    cs:__imp_CreateEventExW
0x18004af4f  mov     [rbx+38h], rax
0x18004af53  test    rax, rax
0x18004af56  jnz     short loc_18004AF7D
0x18004af58  call    cs:__imp_GetLastError
0x18004af5e  mov     edi, eax
0x18004af60  test    eax, eax
0x18004af62  jle     short loc_18004AF6D
0x18004af64  movzx   edi, ax
0x18004af67  or      edi, 80070000h
0x18004af6d  test    edi, edi
0x18004af6f  jns     short loc_18004AF7D
0x18004af71  lea     rcx, [rsp+28h+arg_0]
0x18004af76  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004af7b  jmp     short loc_18004AF9C
0x18004af7d  mov     rax, [rbx]
0x18004af80  mov     rcx, rbx
0x18004af83  mov     rax, [rax+8]
0x18004af87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004af8c  nop
0x18004af8d  mov     [rsi], rbx
0x18004af90  lea     rcx, [rsp+28h+arg_0]
0x18004af95  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004af9a  xor     edi, edi
0x18004af9c  lea     rcx, [rsp+28h+arg_8]
0x18004afa1  call    ??1?$MakeAllocator@VCDPComActivityStore@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CDPComActivityStore>::~MakeAllocator<CDPComActivityStore>(void)
0x18004afa6  mov     eax, edi
0x18004afa8  mov     rbx, [rsp+28h+arg_10]
0x18004afad  mov     rsi, [rsp+28h+arg_18]
0x18004afb2  add     rsp, 20h
0x18004afb6  pop     rdi
0x18004afb7  retn
```
