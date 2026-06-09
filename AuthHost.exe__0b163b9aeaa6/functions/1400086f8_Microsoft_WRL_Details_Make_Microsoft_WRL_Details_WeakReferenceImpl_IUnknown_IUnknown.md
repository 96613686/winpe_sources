# Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(IUnknown * &)

- ea: `0x1400086f8`
- end: `0x1400087b2`
- name: `??$Make@VWeakReferenceImpl@Details@WRL@Microsoft@@AEAPEAUIUnknown@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@12@AEAPEAUIUnknown@@@Z`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140009570`

## callees

- `0x14000289c`
- `0x1400047c4`
- `0x140008150`
- `0x1400086f8`
- `0x140008928`
- `0x140014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(
        _QWORD *a1,
        __int64 *a2)
{
  _DWORD *v4; // rax
  _DWORD *v5; // rbx
  __int64 v6; // rsi
  void *v8; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  v8 = v4;
  if ( v4 )
  {
    v6 = *a2;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>(v4);
    *(_QWORD *)v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v5[4] = 0x3FFFFFFF;
    *(_QWORD *)v5 = &Microsoft::WRL::Details::WeakReferenceImpl::`vftable';
    *((_QWORD *)v5 + 3) = v6;
    v5[3] = 2;
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::AcceleratorKeyEventArgs *>>::Release();
    *a1 = v5;
    v8 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::ICoreDispatcher *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Core::AcceleratorKeyEventArgs *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::*)(Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::AcceleratorKeyEventArgs *>,_lambda_766ca67daaea39a1a461b0c067384f4a_,-1,Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::ICoreDispatcher *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Core::AcceleratorKeyEventArgs *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::*)(Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::AcceleratorKeyEventArgs *>,_lambda_766ca67daaea39a1a461b0c067384f4a_,-1,Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>(&v8);
  return a1;
}

```

## disassembly

```asm
0x1400086f8  mov     [rsp+arg_8], rbx
0x1400086fd  mov     [rsp+arg_10], rsi
0x140008702  push    rdi
0x140008703  sub     rsp, 20h
0x140008707  mov     rsi, rdx
0x14000870a  mov     rdi, rcx
0x14000870d  mov     qword ptr [rcx], 0
0x140008714  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000871b  mov     ecx, 20h ; ' '; unsigned __int64
0x140008720  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140008725  mov     rbx, rax
0x140008728  mov     [rsp+28h+arg_0], rax
0x14000872d  test    rax, rax
0x140008730  jz      short loc_140008795
0x140008732  mov     rsi, [rsi]
0x140008735  mov     rcx, rax
0x140008738  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>(void)
0x14000873d  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIWeakReference@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IWeakReference>::`vftable'
0x140008744  mov     [rbx], rcx
0x140008747  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000874e  test    rcx, rcx
0x140008751  jz      short loc_140008760
0x140008753  mov     rax, [rcx]
0x140008756  mov     rax, [rax+8]
0x14000875a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000875f  nop
0x140008760  mov     dword ptr [rbx+10h], 3FFFFFFFh
0x140008767  lea     rax, ??_7WeakReferenceImpl@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::WeakReferenceImpl::`vftable'
0x14000876e  mov     [rbx], rax
0x140008771  mov     [rbx+18h], rsi
0x140008775  mov     dword ptr [rbx+0Ch], 2
0x14000877c  mov     rcx, [rdi]
0x14000877f  test    rcx, rcx
0x140008782  jz      short loc_140008789
0x140008784  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$ITypedEventHandler@PEAVCoreDispatcher@Core@UI@Windows@@PEAVAcceleratorKeyEventArgs@234@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::AcceleratorKeyEventArgs *>>::Release(void)
0x140008789  mov     [rdi], rbx
0x14000878c  mov     [rsp+28h+arg_0], 0
0x140008795  lea     rcx, [rsp+28h+arg_0]
0x14000879a  call    ??1?$MakeAllocator@U?$DelegateInvokeHelper@U?$ITypedEventHandler@PEAVCoreDispatcher@Core@UI@Windows@@PEAVAcceleratorKeyEventArgs@234@@Foundation@Windows@@V_lambda_766ca67daaea39a1a461b0c067384f4a_@@$0?0PEAUICoreDispatcher@Core@UI@3@PEAUIAcceleratorKeyEventArgs@673@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVCoreDispatcher@Core@UI@Windows@@PEAUICoreDispatcher@234@@Internal@Foundation@Windows@@U?$AggregateType@PEAVAcceleratorKeyEventArgs@Core@UI@Windows@@PEAUIAcceleratorKeyEventArgs@234@@234@@Foundation@Windows@@EAAJPEAUICoreDispatcher@Core@UI@3@PEAUIAcceleratorKeyEventArgs@563@@Z@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::ICoreDispatcher *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Core::AcceleratorKeyEventArgs *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::*)(Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::AcceleratorKeyEventArgs *>,_lambda_766ca67daaea39a1a461b0c067384f4a_,-1,Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::ICoreDispatcher *>,Windows::Foundation::Internal::AggregateType<Windows::UI::Core::AcceleratorKeyEventArgs *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>::*)(Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *)>::DelegateInvokeHelper<Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreDispatcher *,Windows::UI::Core::AcceleratorKeyEventArgs *>,_lambda_766ca67daaea39a1a461b0c067384f4a_,-1,Windows::UI::Core::ICoreDispatcher *,Windows::UI::Core::IAcceleratorKeyEventArgs *>>(void)
0x14000879f  mov     rax, rdi
0x1400087a2  mov     rbx, [rsp+28h+arg_8]
0x1400087a7  mov     rsi, [rsp+28h+arg_10]
0x1400087ac  add     rsp, 20h
0x1400087b0  pop     rdi
0x1400087b1  retn
```
