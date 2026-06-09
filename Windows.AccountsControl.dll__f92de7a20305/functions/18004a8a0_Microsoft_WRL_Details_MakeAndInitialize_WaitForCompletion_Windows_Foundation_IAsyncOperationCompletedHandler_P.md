# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<PhoneInternal::Experiences::Sync::Account *>,Windows::Foundation::IAsyncOperation<PhoneInternal::Experiences::Sync::Account *>>(Windows::Foundation::IAsyncOperation<PhoneInternal::Experiences::Sync::Account *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<PhoneInternal::Experiences::Sync::Account *>,Windows::Foundation::IAsyncOperation<PhoneInternal::Experiences::Sync::Account *>>(Windows::Foundation::IAsyncOperation<PhoneInternal::Experiences::Sync::Account *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<PhoneInternal::Experiences::Sync::Account *>,Windows::Foundation::IAsyncOperation<PhoneInternal::Experiences::Sync::Account *>>(Windows::Foundation::IAsyncOperation<PhoneInternal::Experiences::Sync::Account *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x18004a8a0`
- end: `0x18004a9d8`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAccount@Sync@Experiences@PhoneInternal@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAccount@Sync@Experiences@PhoneInternal@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAccount@Sync@Experiences@PhoneInternal@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAccount@Sync@Experiences@PhoneInternal@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAccount@Sync@Experiences@PhoneInternal@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAccount@Sync@Experiences@PhoneInternal@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAccount@Sync@Experiences@PhoneInternal@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAccount@Sync@Experiences@PhoneInternal@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004ae00`

## callees

- `0x180003918`
- `0x18000b618`
- `0x18000be78`
- `0x180011ffc`
- `0x18004a8a0`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004a969`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18004a969`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a978`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a978`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVAccount_Sync_Experiences_PhoneInternal___Foundation_Windows__U__IAsyncOperation_PEAVAccount_Sync_Experiences_PhoneInternal___23___YAJPEAU__IAsyncOperation_PEAVAccount_Sync_Experiences_PhoneInternal___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVAccount_Sync_Experiences_PhoneInternal___Foundation_Windows__U__IAsyncOperation_PEAVAccount_Sync_Experiences_PhoneInternal___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVAccount_Sync_Experiences_PhoneInternal___Foundation_Windows__U__IAsyncOperation_PEAVAccount_Sync_Experiences_PhoneInternal___23___YAJPEAU__IAsyncOperation_PEAVAccount_Sync_Experiences_PhoneInternal___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
    *(_QWORD *)v2 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStreamWithContentType *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 2));
    v2[11] = 1;
    *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<PhoneInternal::Experiences::Sync::Account *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<PhoneInternal::Experiences::Sync::Account *>'};
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<PhoneInternal::Experiences::Sync::Account *>,Windows::Foundation::IAsyncOperation<PhoneInternal::Experiences::Sync::Account *>>'::`2'::FTMEventDelegate::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v2 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<PhoneInternal::Experiences::Sync::Account *>,Windows::Foundation::IAsyncOperation<PhoneInternal::Experiences::Sync::Account *>>'::`2'::FTMEventDelegate::`vftable';
    *((_QWORD *)v2 + 1) = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<PhoneInternal::Experiences::Sync::Account *>,Windows::Foundation::IAsyncOperation<PhoneInternal::Experiences::Sync::Account *>>'::`2'::FTMEventDelegate::`vftable';
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
  Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>>::~MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>>(&v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18004a8a0  mov     [rsp+arg_10], rbx
0x18004a8a5  mov     [rsp+arg_18], rsi
0x18004a8aa  push    rdi
0x18004a8ab  sub     rsp, 20h
0x18004a8af  mov     rsi, rcx
0x18004a8b2  mov     qword ptr [rcx], 0
0x18004a8b9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004a8c0  mov     ecx, 40h ; '@'; unsigned __int64
0x18004a8c5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004a8ca  mov     rbx, rax
0x18004a8cd  mov     [rsp+28h+arg_8], rax
0x18004a8d2  test    rax, rax
0x18004a8d5  jnz     short loc_18004A8E1
0x18004a8d7  mov     edi, 8007000Eh
0x18004a8dc  jmp     loc_18004A9BC
0x18004a8e1  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStreamWithContentType@Streams@Storage@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStreamWithContentType *>::`vftable'
0x18004a8e8  mov     [rbx], rax
0x18004a8eb  lea     rdi, [rbx+8]
0x18004a8ef  mov     rcx, rdi; this
0x18004a8f2  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18004a8f7  mov     dword ptr [rbx+2Ch], 1
0x18004a8fe  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAVAccount@Sync@Experiences@PhoneInternal@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAVAccount@Sync@Experiences@PhoneInternal@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<PhoneInternal::Experiences::Sync::Account *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<PhoneInternal::Experiences::Sync::Account *>'}
0x18004a905  mov     [rbx], rax
0x18004a908  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAccount@Sync@Experiences@PhoneInternal@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAccount@Sync@Experiences@PhoneInternal@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAccount@Sync@Experiences@PhoneInternal@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<PhoneInternal::Experiences::Sync::Account *>,Windows::Foundation::IAsyncOperation<PhoneInternal::Experiences::Sync::Account *>>(Windows::Foundation::IAsyncOperation<PhoneInternal::Experiences::Sync::Account *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18004a90f  mov     [rdi], rax
0x18004a912  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18004a919  test    rcx, rcx
0x18004a91c  jz      short loc_18004A92B
0x18004a91e  mov     rax, [rcx]
0x18004a921  mov     rax, [rax+8]
0x18004a925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a92a  nop
0x18004a92b  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAccount@Sync@Experiences@PhoneInternal@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAccount@Sync@Experiences@PhoneInternal@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAccount@Sync@Experiences@PhoneInternal@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAVAccount@Sync@Experiences@PhoneInternal@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<PhoneInternal::Experiences::Sync::Account *>,Windows::Foundation::IAsyncOperation<PhoneInternal::Experiences::Sync::Account *>>(Windows::Foundation::IAsyncOperation<PhoneInternal::Experiences::Sync::Account *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<PhoneInternal::Experiences::Sync::Account *>'}
0x18004a932  mov     [rbx], rax
0x18004a935  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVAccount@Sync@Experiences@PhoneInternal@@@Foundation@Windows@@U?$IAsyncOperation@PEAVAccount@Sync@Experiences@PhoneInternal@@@23@@@YAJPEAU?$IAsyncOperation@PEAVAccount@Sync@Experiences@PhoneInternal@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<PhoneInternal::Experiences::Sync::Account *>,Windows::Foundation::IAsyncOperation<PhoneInternal::Experiences::Sync::Account *>>(Windows::Foundation::IAsyncOperation<PhoneInternal::Experiences::Sync::Account *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18004a93c  mov     [rdi], rax
0x18004a93f  mov     dword ptr [rbx+30h], 0
0x18004a946  mov     qword ptr [rbx+38h], 0
0x18004a94e  mov     [rsp+28h+arg_0], rbx
0x18004a953  mov     [rsp+28h+arg_8], 0
0x18004a95c  mov     r9d, 1F0003h; dwDesiredAccess
0x18004a962  xor     r8d, r8d; dwFlags
0x18004a965  xor     edx, edx; lpName
0x18004a967  xor     ecx, ecx; lpEventAttributes
0x18004a969  call    cs:__imp_CreateEventExW
0x18004a96f  mov     [rbx+38h], rax
0x18004a973  test    rax, rax
0x18004a976  jnz     short loc_18004A99D
0x18004a978  call    cs:__imp_GetLastError
0x18004a97e  mov     edi, eax
0x18004a980  test    eax, eax
0x18004a982  jle     short loc_18004A98D
0x18004a984  movzx   edi, ax
0x18004a987  or      edi, 80070000h
0x18004a98d  test    edi, edi
0x18004a98f  jns     short loc_18004A99D
0x18004a991  lea     rcx, [rsp+28h+arg_0]
0x18004a996  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004a99b  jmp     short loc_18004A9BC
0x18004a99d  mov     rax, [rbx]
0x18004a9a0  mov     rcx, rbx
0x18004a9a3  mov     rax, [rax+8]
0x18004a9a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a9ac  nop
0x18004a9ad  mov     [rsi], rbx
0x18004a9b0  lea     rcx, [rsp+28h+arg_0]
0x18004a9b5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004a9ba  xor     edi, edi
0x18004a9bc  lea     rcx, [rsp+28h+arg_8]
0x18004a9c1  call    ??1?$MakeAllocator@V?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>>::~MakeAllocator<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>>(void)
0x18004a9c6  mov     eax, edi
0x18004a9c8  mov     rbx, [rsp+28h+arg_10]
0x18004a9cd  mov     rsi, [rsp+28h+arg_18]
0x18004a9d2  add     rsp, 20h
0x18004a9d6  pop     rdi
0x18004a9d7  retn
```
