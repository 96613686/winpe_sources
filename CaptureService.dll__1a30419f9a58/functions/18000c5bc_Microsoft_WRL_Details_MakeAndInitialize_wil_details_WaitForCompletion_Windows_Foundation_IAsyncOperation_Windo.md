# Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::Capture::CapturableItem *> *>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::Capture::CapturableItem *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::Capture::CapturableItem *> *>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::Capture::CapturableItem *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::Capture::CapturableItem *> *>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::Capture::CapturableItem *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)

- ea: `0x18000c5bc`
- end: `0x18000c70b`
- name: `??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z`
- size: `335`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000cd90`

## callees

- `0x18000335c`
- `0x180006e38`
- `0x180007630`
- `0x18000907c`
- `0x18000acac`
- `0x18000c5bc`
- `0x18000d740`
- `0x18000dc98`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000c682`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000c682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c690`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c690`

## string_xrefs

- `0x18000c6ee`: `onecore\internal\sdk\inc\wil\opensource/wil/winrt.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVCapturableItem_Capture_PlatformExtensions_Internal_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVCapturableItem_Capture_PlatformExtensions_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperation_PEAVCapturableItem_Capture_PlatformExtensions_Internal_Windows___Foundation_Windows___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAVCapturableItem_Capture_PlatformExtensions_Internal_Windows___Foundation_Windows___details_wil__YAJPEAU__IAsyncOperation_PEAVCapturableItem_Capture_PlatformExtensions_Internal_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(
        _QWORD *a1)
{
  _DWORD *v2; // rbx
  unsigned int v3; // edi
  wil::details *v4; // rcx
  HANDLE Event; // rbp
  int LastErrorFailHr; // eax
  int v8; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  _DWORD *v10; // [rsp+40h] [rbp+8h] BYREF
  _DWORD *v11; // [rsp+48h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v11 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>'};
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = &`wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::Capture::CapturableItem *> *>'::`2'::CompletionDelegate::`vftable';
    *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
    v2[12] = 0;
    *((_QWORD *)v2 + 7) = 0;
    v10 = v2;
    v11 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    if ( Event )
    {
      GetLastError();
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        v2 + 14,
        Event);
    }
    else
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v4);
      v3 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x62B,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/winrt.h",
          (const char *)(unsigned int)LastErrorFailHr,
          v8);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
        goto LABEL_8;
      }
    }
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 8LL))(v2);
    *a1 = v2;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
    v3 = 0;
  }
  else
  {
    v3 = -2147024882;
  }
LABEL_8:
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(&v11);
  return v3;
}

```

## disassembly

```asm
0x18000c5bc  mov     [rsp+arg_10], rbx
0x18000c5c1  push    rbp
0x18000c5c2  push    rsi
0x18000c5c3  push    rdi; int
0x18000c5c4  sub     rsp, 20h
0x18000c5c8  mov     rsi, rcx
0x18000c5cb  mov     qword ptr [rcx], 0
0x18000c5d2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c5d9  mov     ecx, 40h ; '@'; unsigned __int64
0x18000c5de  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c5e3  mov     rbx, rax
0x18000c5e6  mov     [rsp+38h+arg_8], rax
0x18000c5eb  test    rax, rax
0x18000c5ee  jnz     short loc_18000C5FA
0x18000c5f0  mov     edi, 8007000Eh
0x18000c5f5  jmp     loc_18000C6C2
0x18000c5fa  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>::`vftable'
0x18000c601  mov     [rbx], rax
0x18000c604  lea     rdi, [rbx+8]
0x18000c608  mov     rcx, rdi; this
0x18000c60b  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000c610  mov     dword ptr [rbx+2Ch], 1
0x18000c617  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>'}
0x18000c61e  mov     [rbx], rax
0x18000c621  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000c628  mov     [rdi], rax
0x18000c62b  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000c632  test    rcx, rcx
0x18000c635  jz      short loc_18000C644
0x18000c637  mov     rax, [rcx]
0x18000c63a  mov     rax, [rax+8]
0x18000c63e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c643  nop
0x18000c644  lea     rax, ??_7CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@6B?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@45@@; const `wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::Capture::CapturableItem *> *>(Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::Capture::CapturableItem *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>'}
0x18000c64b  mov     [rbx], rax
0x18000c64e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000c655  mov     [rdi], rax
0x18000c658  mov     dword ptr [rbx+30h], 0
0x18000c65f  mov     qword ptr [rbx+38h], 0
0x18000c667  mov     [rsp+38h+arg_0], rbx
0x18000c66c  mov     [rsp+38h+arg_8], 0
0x18000c675  mov     r9d, 1F0003h; dwDesiredAccess
0x18000c67b  xor     r8d, r8d; dwFlags
0x18000c67e  xor     edx, edx; lpName
0x18000c680  xor     ecx, ecx; lpEventAttributes
0x18000c682  call    cs:__imp_CreateEventExW
0x18000c688  mov     rbp, rax
0x18000c68b  test    rax, rax
0x18000c68e  jz      short loc_18000C6DB
0x18000c690  call    cs:__imp_GetLastError
0x18000c696  mov     rdx, rbp
0x18000c699  lea     rcx, [rbx+38h]
0x18000c69d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000c6a2  nop
0x18000c6a3  mov     rax, [rbx]
0x18000c6a6  mov     rcx, rbx
0x18000c6a9  mov     rax, [rax+8]
0x18000c6ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6b2  nop
0x18000c6b3  mov     [rsi], rbx
0x18000c6b6  lea     rcx, [rsp+38h+arg_0]
0x18000c6bb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c6c0  xor     edi, edi
0x18000c6c2  lea     rcx, [rsp+38h+arg_8]
0x18000c6c7  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x18000c6cc  mov     eax, edi
0x18000c6ce  mov     rbx, [rsp+38h+arg_10]
0x18000c6d3  add     rsp, 20h
0x18000c6d7  pop     rdi
0x18000c6d8  pop     rsi
0x18000c6d9  pop     rbp
0x18000c6da  retn
0x18000c6db  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000c6e0  mov     edi, eax
0x18000c6e2  test    eax, eax
0x18000c6e4  jns     short loc_18000C6A3
0x18000c6e6  mov     rcx, [rsp+38h]; this
0x18000c6eb  mov     r9d, eax; char *
0x18000c6ee  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c6f5  mov     edx, 62Bh; void *
0x18000c6fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c6ff  lea     rcx, [rsp+38h+arg_0]
0x18000c704  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c709  jmp     short loc_18000C6C2
```
