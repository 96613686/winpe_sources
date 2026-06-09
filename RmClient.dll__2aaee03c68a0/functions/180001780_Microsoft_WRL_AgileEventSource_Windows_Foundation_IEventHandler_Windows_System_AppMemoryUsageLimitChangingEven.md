# Microsoft::WRL::AgileEventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::Add(Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *> *,EventRegistrationToken *)

- ea: `0x180001780`
- end: `0x1800018bc`
- name: `?Add@?$AgileEventSource@U?$IEventHandler@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAU?$IEventHandler@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Foundation@Windows@@PEAUEventRegistrationToken@@@Z`
- size: `316`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001f30`

## callees

- `0x180001780`
- `0x1800018c4`
- `0x1800018f0`
- `0x1800136c4`
- `0x180013ce8`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800017d3`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x1800017d3`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AgileEventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::Add(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  int AgileReference; // edi
  void *v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 v10; // rcx
  __int64 v11; // [rsp+50h] [rbp+30h] BYREF
  __int64 v12; // [rsp+58h] [rbp+38h] BYREF
  __int64 v13; // [rsp+68h] [rbp+48h] BYREF

  v11 = a1;
  if ( !a2 )
    return 2147942487LL;
  v11 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
  v11 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
  AgileReference = RoGetAgileReference(0, &GUID_6030e7c3_f93f_5e9c_9ba2_9a018d2b09c0, a2, &v11);
  if ( AgileReference < 0 )
  {
    v10 = v11;
    if ( v11 )
    {
      v11 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
  else
  {
    v12 = v11;
    v11 = 0;
    v6 = operator new(0x48u, (const struct std::nothrow_t *)std::nothrow);
    if ( v6 )
      v7 = Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::AppMemoryUsageLimitChangingEventArgs *,Windows::System::IAppMemoryUsageLimitChangingEventArgs *>>::*)(IInspectable *,Windows::System::IAppMemoryUsageLimitChangingEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_2a07431b028f5ee37e3077b9dff53ccb_,-1,IInspectable *,Windows::System::IAppMemoryUsageLimitChangingEventArgs *>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_2a07431b028f5ee37e3077b9dff53ccb_,-1,IInspectable *,Windows::System::IAppMemoryUsageLimitChangingEventArgs *>(
             v6,
             &v12);
    else
      v7 = 0;
    v13 = v7;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
    if ( v7 )
    {
      v8 = v11;
      if ( v11 )
      {
        v11 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      AgileReference = Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(
                         v8,
                         v7,
                         *(_QWORD *)(*(_QWORD *)a2 + 24LL),
                         a3);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v11);
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)AgileReference;
}

```

## disassembly

```asm
0x180001780  mov     [rsp-28h+arg_0], rcx
0x180001785  push    rbp
0x180001786  push    rbx
0x180001787  push    rsi
0x180001788  push    rdi
0x180001789  push    r14
0x18000178b  mov     rbp, rsp
0x18000178e  sub     rsp, 20h
0x180001792  mov     r14, r8
0x180001795  mov     rsi, rdx
0x180001798  test    rdx, rdx
0x18000179b  jz      loc_1800018A1
0x1800017a1  lea     rcx, [rbp+arg_0]
0x1800017a5  mov     [rbp+arg_0], 0
0x1800017ad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800017b2  lea     rcx, [rbp+arg_0]
0x1800017b6  mov     [rbp+arg_0], 0
0x1800017be  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800017c3  lea     r9, [rbp+arg_0]
0x1800017c7  mov     r8, rsi
0x1800017ca  lea     rdx, _GUID_6030e7c3_f93f_5e9c_9ba2_9a018d2b09c0
0x1800017d1  xor     ecx, ecx
0x1800017d3  call    cs:__imp_RoGetAgileReference
0x1800017d9  mov     edi, eax
0x1800017db  test    eax, eax
0x1800017dd  js      loc_18000186E
0x1800017e3  mov     rax, [rbp+arg_0]
0x1800017e7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800017ee  mov     ecx, 48h ; 'H'; unsigned __int64
0x1800017f3  mov     [rbp+arg_8], rax
0x1800017f7  mov     [rbp+arg_0], 0
0x1800017ff  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180001804  test    rax, rax
0x180001807  jnz     loc_1800018A8
0x18000180d  xor     ebx, ebx
0x18000180f  lea     rcx, [rbp+arg_8]
0x180001813  mov     [rbp+arg_18], rbx
0x180001817  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000181c  test    rbx, rbx
0x18000181f  jz      short loc_180001888
0x180001821  mov     rcx, [rbp+arg_0]
0x180001825  test    rcx, rcx
0x180001828  jz      short loc_18000183E
0x18000182a  mov     [rbp+arg_0], 0
0x180001832  mov     rax, [rcx]
0x180001835  mov     rax, [rax+10h]
0x180001839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000183e  mov     r8, [rsi]
0x180001841  mov     r9, r14
0x180001844  mov     rdx, rbx
0x180001847  mov     r8, [r8+18h]
0x18000184b  call    ?AddInternal@?$EventSource@U?$IEventHandler@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@AEAAJPEAU?$IEventHandler@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Foundation@Windows@@PEAXPEAUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *> *,void *,EventRegistrationToken *)
0x180001850  mov     rcx, [rbx]
0x180001853  mov     edi, eax
0x180001855  mov     rax, [rcx+10h]
0x180001859  mov     rcx, rbx
0x18000185c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001861  mov     eax, edi
0x180001863  add     rsp, 20h
0x180001867  pop     r14
0x180001869  pop     rdi
0x18000186a  pop     rsi
0x18000186b  pop     rbx
0x18000186c  pop     rbp
0x18000186d  retn
0x18000186e  mov     rcx, [rbp+arg_0]
0x180001872  test    rcx, rcx
0x180001875  jz      short loc_180001861
0x180001877  mov     [rbp+arg_0], 0
0x18000187f  mov     rax, [rcx]
0x180001882  mov     rax, [rax+10h]
0x180001886  jmp     short loc_18000185C
0x180001888  lea     rcx, [rbp+arg_18]
0x18000188c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180001891  lea     rcx, [rbp+arg_0]
0x180001895  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000189a  mov     edi, 8007000Eh
0x18000189f  jmp     short loc_180001861
0x1800018a1  mov     eax, 80070057h
0x1800018a6  jmp     short loc_180001863
0x1800018a8  lea     rdx, [rbp+arg_8]
0x1800018ac  mov     rcx, rax
0x1800018af  call    ??0?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IEventHandler@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_2a07431b028f5ee37e3077b9dff53ccb_@@$0?0PEAUIInspectable@@PEAUIAppMemoryUsageLimitChangingEventArgs@System@Windows@@@?$DelegateArgTraits@P8?$IEventHandler_impl@U?$AggregateType@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@PEAUIAppMemoryUsageLimitChangingEventArgs@23@@Internal@Foundation@Windows@@@Foundation@Windows@@EAAJPEAUIInspectable@@PEAUIAppMemoryUsageLimitChangingEventArgs@System@3@@Z@Details@WRL@Microsoft@@QEAA@$$QEAV_lambda_2a07431b028f5ee37e3077b9dff53ccb_@@@Z; Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::IEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::AppMemoryUsageLimitChangingEventArgs *,Windows::System::IAppMemoryUsageLimitChangingEventArgs *>>::*)(IInspectable *,Windows::System::IAppMemoryUsageLimitChangingEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_2a07431b028f5ee37e3077b9dff53ccb_,-1,IInspectable *,Windows::System::IAppMemoryUsageLimitChangingEventArgs *>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_2a07431b028f5ee37e3077b9dff53ccb_,-1,IInspectable *,Windows::System::IAppMemoryUsageLimitChangingEventArgs *>(_lambda_2a07431b028f5ee37e3077b9dff53ccb_ &&)
0x1800018b4  mov     rbx, rax
0x1800018b7  jmp     loc_18000180F
```
