# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>(Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>(Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>(Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x18027364c`
- end: `0x180273782`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180273788`

## callees

- `0x180048d5c`
- `0x18012a0a8`
- `0x18013bf4c`
- `0x1801dfc5c`
- `0x18027364c`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180273714`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180273714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180273723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180273723`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUIUICommand_Popups_UI_Windows___Foundation_Windows__U__IAsyncOperation_PEAUIUICommand_Popups_UI_Windows___23___YAJPEAU__IAsyncOperation_PEAUIUICommand_Popups_UI_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUIUICommand_Popups_UI_Windows___Foundation_Windows__U__IAsyncOperation_PEAUIUICommand_Popups_UI_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAUIUICommand_Popups_UI_Windows___Foundation_Windows__U__IAsyncOperation_PEAUIUICommand_Popups_UI_Windows___23___YAJPEAU__IAsyncOperation_PEAUIUICommand_Popups_UI_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
    *v10 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Internal::Text::Core::CoreTextRichContentUpdatingEventArgs *>::`vftable';
    Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v2 + 1));
    v5 = Microsoft::WRL::Details::ModuleBase::module_;
    *v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>'};
    v2[1] = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>'::`2'::FTMEventDelegate::`vftable';
    *((_DWORD *)v2 + 11) = 1;
    if ( v5 )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v5 + 8LL))(v5);
    *((_DWORD *)v2 + 12) = 0;
    *v2 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>'::`2'::FTMEventDelegate::`vftable';
    v2[7] = 0;
    *v4 = `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>'::`2'::FTMEventDelegate::`vftable';
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
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
      v3 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::ICoreTextEditContext *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>::*)(Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *>,_lambda_0dc445f034a1f32a7567697cfa885cc1_,-1,Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::ICoreTextEditContext *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>::*)(Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *>,_lambda_0dc445f034a1f32a7567697cfa885cc1_,-1,Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>(&v10);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18027364c  mov     [rsp+arg_10], rbx
0x180273651  mov     [rsp+arg_18], rsi
0x180273656  push    rdi
0x180273657  sub     rsp, 20h
0x18027365b  mov     rsi, rcx
0x18027365e  mov     qword ptr [rcx], 0
0x180273665  mov     ecx, 40h ; '@'; unsigned __int64
0x18027366a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180273671  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180273676  mov     [rsp+28h+arg_8], rax
0x18027367b  mov     rdi, rax
0x18027367e  test    rax, rax
0x180273681  jnz     short loc_18027368D
0x180273683  mov     ebx, 8007000Eh
0x180273688  jmp     loc_180273766
0x18027368d  lea     rax, ??_7?$ITypedEventHandler@PEAVCoreTextEditContext@Core@Text@UI@Windows@@PEAVCoreTextRichContentUpdatingEventArgs@23Internal@45@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Internal::Text::Core::CoreTextRichContentUpdatingEventArgs *>::`vftable'
0x180273694  lea     rbx, [rdi+8]
0x180273698  mov     [rdi], rax
0x18027369b  mov     rcx, rbx; this
0x18027369e  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x1802736a3  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1802736aa  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Microsoft::WRL::FtmBase>::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>'}
0x1802736b1  mov     [rdi], rax
0x1802736b4  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>(Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1802736bb  mov     [rbx], rax
0x1802736be  mov     dword ptr [rdi+2Ch], 1
0x1802736c5  test    rcx, rcx
0x1802736c8  jz      short loc_1802736D6
0x1802736ca  mov     rax, [rcx]
0x1802736cd  mov     rax, [rax+8]
0x1802736d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802736d6  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@23@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>(Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>'}
0x1802736dd  mov     dword ptr [rdi+30h], 0
0x1802736e4  mov     [rdi], rax
0x1802736e7  mov     r9d, 1F0003h; dwDesiredAccess
0x1802736ed  lea     rax, ??_7FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>(Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1802736f4  mov     qword ptr [rdi+38h], 0
0x1802736fc  xor     r8d, r8d; dwFlags
0x1802736ff  mov     [rbx], rax
0x180273702  xor     edx, edx; lpName
0x180273704  mov     [rsp+28h+arg_0], rdi
0x180273709  xor     ecx, ecx; lpEventAttributes
0x18027370b  mov     [rsp+28h+arg_8], 0
0x180273714  call    cs:__imp_CreateEventExW
0x18027371a  mov     [rdi+38h], rax
0x18027371e  test    rax, rax
0x180273721  jnz     short loc_180273748
0x180273723  call    cs:__imp_GetLastError
0x180273729  mov     ebx, eax
0x18027372b  test    eax, eax
0x18027372d  jle     short loc_180273738
0x18027372f  movzx   ebx, ax
0x180273732  or      ebx, 80070000h
0x180273738  test    ebx, ebx
0x18027373a  jns     short loc_180273748
0x18027373c  lea     rcx, [rsp+28h+arg_0]
0x180273741  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180273746  jmp     short loc_180273766
0x180273748  mov     rax, [rdi]
0x18027374b  mov     rcx, rdi
0x18027374e  mov     rax, [rax+8]
0x180273752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180273757  lea     rcx, [rsp+28h+arg_0]
0x18027375c  mov     [rsi], rdi
0x18027375f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180273764  xor     ebx, ebx
0x180273766  lea     rcx, [rsp+28h+arg_8]
0x18027376b  call    ??1?$MakeAllocator@U?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVCoreTextEditContext@Core@Text@UI@Windows@@PEAVCoreTextSelectionUpdatingEventArgs@2345@@Foundation@Windows@@V_lambda_0dc445f034a1f32a7567697cfa885cc1_@@$0?0PEAUICoreTextEditContext@Core@Text@UI@3@PEAUICoreTextSelectionUpdatingEventArgs@6783@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVCoreTextEditContext@Core@Text@UI@Windows@@PEAUICoreTextEditContext@2345@@Internal@Foundation@Windows@@U?$AggregateType@PEAVCoreTextSelectionUpdatingEventArgs@Core@Text@UI@Windows@@PEAUICoreTextSelectionUpdatingEventArgs@2345@@234@@Foundation@Windows@@EAAJPEAUICoreTextEditContext@Core@Text@UI@3@PEAUICoreTextSelectionUpdatingEventArgs@5673@@Z@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::ICoreTextEditContext *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>::*)(Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *>,_lambda_0dc445f034a1f32a7567697cfa885cc1_,-1,Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::ICoreTextEditContext *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>::*)(Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Text::Core::CoreTextEditContext *,Windows::UI::Text::Core::CoreTextSelectionUpdatingEventArgs *>,_lambda_0dc445f034a1f32a7567697cfa885cc1_,-1,Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextSelectionUpdatingEventArgs *>>(void)
0x180273770  mov     rsi, [rsp+28h+arg_18]
0x180273775  mov     eax, ebx
0x180273777  mov     rbx, [rsp+28h+arg_10]
0x18027377c  add     rsp, 20h
0x180273780  pop     rdi
0x180273781  retn
```
