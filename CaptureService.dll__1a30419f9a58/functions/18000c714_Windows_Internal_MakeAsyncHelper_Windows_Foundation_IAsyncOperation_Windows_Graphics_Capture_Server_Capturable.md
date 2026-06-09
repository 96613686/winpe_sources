# Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::INilDelegate,Windows::Internal::CMarshaledInterfaceResult<Windows::Graphics::Capture::Server::ICapturableItem>,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *> * *,Windows::Internal::ComTaskPoolHandler &&,ushort const * const,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CMarshaledInterfaceResult<Windows::Graphics::Capture::Server::ICapturableItem>> *)

- ea: `0x18000c714`
- end: `0x18000c7e5`
- name: `??$MakeAsyncHelper@U?$IAsyncOperation@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@23@UINilDelegate@Internal@3@V?$CMarshaledInterfaceResult@UICapturableItem@Server@Capture@Graphics@Windows@@@63@VComTaskPoolHandler@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@YAJPEAPEAU?$IAsyncOperation@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@1@$$QEAVComTaskPoolHandler@01@QEBGW4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CMarshaledInterfaceResult@UICapturableItem@Server@Capture@Graphics@Windows@@@Internal@Windows@@@01@@Z`
- size: `209`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64, void (__fastcall ***)(_QWORD, __int64))`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c7ec`

## callees

- `0x18000335c`
- `0x18000c714`
- `0x18000d0ec`
- `0x18000dc98`
- `0x180014d10`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::INilDelegate,Windows::Internal::CMarshaledInterfaceResult<Windows::Graphics::Capture::Server::ICapturableItem>,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        void (__fastcall ***a5)(_QWORD, __int64))
{
  void (__fastcall ***v8)(_QWORD, __int64); // rdi
  void (__fastcall ***v10)(_QWORD, __int64); // rax
  __int64 v11; // rbx
  int v12; // edi

  *a1 = 0;
  v8 = a5;
  if ( !a5 )
    return 2147942414LL;
  v10 = (void (__fastcall ***)(_QWORD, __int64))operator new(0x160u, (const struct std::nothrow_t *)std::nothrow);
  a5 = v10;
  v11 = 0;
  if ( v10 )
  {
    v11 = Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Graphics::Capture::Server::ICapturableItem>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Graphics::Capture::Server::ICapturableItem>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
            v10,
            a2,
            a3,
            0);
    a5 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(&a5);
  if ( !v11 )
  {
    (**v8)(v8, 1);
    return 2147942414LL;
  }
  *(_QWORD *)(v11 + 264) = v8;
  v12 = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(v11 + 8);
  if ( v12 >= 0 )
  {
    *a1 = v11 + 184;
    v11 = 0;
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v11 + 8) + 16LL))(v11 + 8);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000c714  push    rbx
0x18000c716  push    rbp
0x18000c717  push    rsi
0x18000c718  push    rdi
0x18000c719  push    r14
0x18000c71b  sub     rsp, 20h
0x18000c71f  mov     rbp, r8
0x18000c722  mov     r14, rdx
0x18000c725  mov     rsi, rcx
0x18000c728  mov     qword ptr [rcx], 0
0x18000c72f  mov     rdi, [rsp+48h+arg_20]
0x18000c734  test    rdi, rdi
0x18000c737  jnz     short loc_18000C743
0x18000c739  mov     eax, 8007000Eh
0x18000c73e  jmp     loc_18000C7DA
0x18000c743  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c74a  mov     ecx, 160h; unsigned __int64
0x18000c74f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c754  mov     [rsp+48h+arg_20], rax
0x18000c759  xor     ebx, ebx
0x18000c75b  test    rax, rax
0x18000c75e  jz      short loc_18000C77D
0x18000c760  xor     r9d, r9d
0x18000c763  mov     r8, rbp
0x18000c766  mov     rdx, r14
0x18000c769  mov     rcx, rax
0x18000c76c  call    ??0?$AsyncOperation@U?$IAsyncOperation@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@23@V?$CMarshaledInterfaceResult@UICapturableItem@Server@Capture@Graphics@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAA@$$QEAVComTaskPoolHandler@12@QEBGW4TrustLevel@@@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Graphics::Capture::Server::ICapturableItem>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Graphics::Capture::Server::ICapturableItem>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(Windows::Internal::ComTaskPoolHandler &&,ushort const * const,TrustLevel)
0x18000c771  mov     rbx, rax
0x18000c774  mov     [rsp+48h+arg_20], 0
0x18000c77d  lea     rcx, [rsp+48h+arg_20]
0x18000c782  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x18000c787  test    rbx, rbx
0x18000c78a  jnz     short loc_18000C7A0
0x18000c78c  mov     rax, [rdi]
0x18000c78f  lea     edx, [rbx+1]
0x18000c792  mov     rcx, rdi
0x18000c795  mov     rax, [rax]
0x18000c798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c79d  nop
0x18000c79e  jmp     short loc_18000C739
0x18000c7a0  mov     [rbx+108h], rdi
0x18000c7a7  lea     rcx, [rbx+8]
0x18000c7ab  call    ?Start@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@MEAAJXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(void)
0x18000c7b0  mov     edi, eax
0x18000c7b2  test    eax, eax
0x18000c7b4  js      short loc_18000C7C2
0x18000c7b6  lea     rcx, [rbx+0B8h]
0x18000c7bd  mov     [rsi], rcx
0x18000c7c0  xor     ebx, ebx
0x18000c7c2  test    rbx, rbx
0x18000c7c5  jz      short loc_18000C7D8
0x18000c7c7  lea     rcx, [rbx+8]
0x18000c7cb  mov     rax, [rcx]
0x18000c7ce  mov     rax, [rax+10h]
0x18000c7d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7d7  nop
0x18000c7d8  mov     eax, edi
0x18000c7da  add     rsp, 20h
0x18000c7de  pop     r14
0x18000c7e0  pop     rdi
0x18000c7e1  pop     rsi
0x18000c7e2  pop     rbp
0x18000c7e3  pop     rbx
0x18000c7e4  retn
```
