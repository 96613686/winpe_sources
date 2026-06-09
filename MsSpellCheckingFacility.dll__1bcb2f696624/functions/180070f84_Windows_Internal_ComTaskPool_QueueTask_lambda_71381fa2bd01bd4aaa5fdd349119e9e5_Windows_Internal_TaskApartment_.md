# Windows::Internal::ComTaskPool::QueueTask<_lambda_71381fa2bd01bd4aaa5fdd349119e9e5_>(Windows::Internal::TaskApartment,_lambda_71381fa2bd01bd4aaa5fdd349119e9e5_ &&)

- ea: `0x180070f84`
- end: `0x180071017`
- name: `??$QueueTask@V_lambda_71381fa2bd01bd4aaa5fdd349119e9e5_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@$$QEAV_lambda_71381fa2bd01bd4aaa5fdd349119e9e5_@@@Z`
- size: `147`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800719c0`

## callees

- `0x180044fbc`
- `0x18006183c`
- `0x180070c84`
- `0x180070f84`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180070fcf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180070fcf`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180070fed`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180070fed`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask<_lambda_71381fa2bd01bd4aaa5fdd349119e9e5_>(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  DWORD CurrentThreadId; // eax
  unsigned int v6; // edi
  _QWORD *v8; // [rsp+50h] [rbp+18h] BYREF

  v3 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  v8 = v3;
  v4 = 0;
  if ( v3 )
  {
    v4 = Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_71381fa2bd01bd4aaa5fdd349119e9e5_>::CTaskWrapper<_lambda_71381fa2bd01bd4aaa5fdd349119e9e5_>(
           v3,
           a2);
    v8 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::UserWatcher *,Windows::System::IUserWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::System::UserChangedEventArgs *,Windows::System::IUserChangedEventArgs *>>::*)(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_88f340da8e3d9318e274dc95da2b1a9f_,-1,Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::UserWatcher *,Windows::System::IUserWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::System::UserChangedEventArgs *,Windows::System::IUserChangedEventArgs *>>::*)(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_88f340da8e3d9318e274dc95da2b1a9f_,-1,Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *>>(&v8);
  CurrentThreadId = GetCurrentThreadId();
  v6 = SHTaskPoolQueueTask(0, 0, CurrentThreadId, 0, v4, 0);
  if ( v4 )
    (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
  return v6;
}

```

## disassembly

```asm
0x180070f84  mov     [rsp+arg_0], rbx
0x180070f89  push    rdi
0x180070f8a  sub     rsp, 30h
0x180070f8e  mov     rdi, rdx
0x180070f91  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180070f98  mov     ecx, 28h ; '('; unsigned __int64
0x180070f9d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180070fa2  mov     [rsp+38h+arg_10], rax
0x180070fa7  xor     ebx, ebx
0x180070fa9  test    rax, rax
0x180070fac  jz      short loc_180070FC5
0x180070fae  mov     rdx, rdi
0x180070fb1  mov     rcx, rax
0x180070fb4  call    ??$?0V_lambda_71381fa2bd01bd4aaa5fdd349119e9e5_@@@?$CTaskWrapper@V_lambda_71381fa2bd01bd4aaa5fdd349119e9e5_@@@ComTaskPool@Internal@Windows@@QEAA@$$QEAV_lambda_71381fa2bd01bd4aaa5fdd349119e9e5_@@@Z; Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_71381fa2bd01bd4aaa5fdd349119e9e5_>::CTaskWrapper<_lambda_71381fa2bd01bd4aaa5fdd349119e9e5_>(_lambda_71381fa2bd01bd4aaa5fdd349119e9e5_ &&)
0x180070fb9  mov     rbx, rax
0x180070fbc  mov     [rsp+38h+arg_10], 0
0x180070fc5  lea     rcx, [rsp+38h+arg_10]
0x180070fca  call    ??1?$MakeAllocator@U?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@VFtmBase@23@@WRL@Microsoft@@V_lambda_88f340da8e3d9318e274dc95da2b1a9f_@@$0?0PEAUIUserWatcher@System@Windows@@PEAUIUserChangedEventArgs@67@@?$DelegateArgTraits@P8?$ITypedEventHandler_impl@U?$AggregateType@PEAVUserWatcher@System@Windows@@PEAUIUserWatcher@23@@Internal@Foundation@Windows@@U?$AggregateType@PEAVUserChangedEventArgs@System@Windows@@PEAUIUserChangedEventArgs@23@@234@@Foundation@Windows@@EAAJPEAUIUserWatcher@System@3@PEAUIUserChangedEventArgs@53@@Z@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::UserWatcher *,Windows::System::IUserWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::System::UserChangedEventArgs *,Windows::System::IUserChangedEventArgs *>>::*)(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_88f340da8e3d9318e274dc95da2b1a9f_,-1,Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::Foundation::ITypedEventHandler_impl<Windows::Foundation::Internal::AggregateType<Windows::System::UserWatcher *,Windows::System::IUserWatcher *>,Windows::Foundation::Internal::AggregateType<Windows::System::UserChangedEventArgs *,Windows::System::IUserChangedEventArgs *>>::*)(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>,_lambda_88f340da8e3d9318e274dc95da2b1a9f_,-1,Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *>>(void)
0x180070fcf  call    cs:__imp_GetCurrentThreadId
0x180070fd5  mov     [rsp+38h+var_10], 0
0x180070fde  mov     [rsp+38h+var_18], rbx
0x180070fe3  xor     r9d, r9d
0x180070fe6  mov     r8d, eax
0x180070fe9  xor     edx, edx
0x180070feb  xor     ecx, ecx
0x180070fed  call    cs:__imp_SHTaskPoolQueueTask
0x180070ff3  mov     edi, eax
0x180070ff5  test    rbx, rbx
0x180070ff8  jz      short loc_18007100A
0x180070ffa  mov     rdx, [rbx]
0x180070ffd  mov     rcx, rbx
0x180071000  mov     rax, [rdx+10h]
0x180071004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071009  nop
0x18007100a  mov     eax, edi
0x18007100c  mov     rbx, [rsp+38h+arg_0]
0x180071011  add     rsp, 30h
0x180071015  pop     rdi
0x180071016  retn
```
