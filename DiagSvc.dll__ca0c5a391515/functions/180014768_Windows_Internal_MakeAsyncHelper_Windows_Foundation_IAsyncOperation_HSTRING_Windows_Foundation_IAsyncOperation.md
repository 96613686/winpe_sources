# Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::INilDelegate,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> * *,Windows::Internal::ComTaskPoolHandler &&,ushort const * const,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CHSTRINGResult> *)

- ea: `0x180014768`
- end: `0x180014839`
- name: `??$MakeAsyncHelper@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@UINilDelegate@Internal@3@VCHSTRINGResult@63@VComTaskPoolHandler@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@YAJPEAPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@1@$$QEAVComTaskPoolHandler@01@QEBGW4TrustLevel@@PEAV?$AsyncCallbackBase@VCHSTRINGResult@Internal@Windows@@@01@@Z`
- size: `209`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64, void (__fastcall ***)(_QWORD, __int64))`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180014840`

## callees

- `0x18000446c`
- `0x180006574`
- `0x180014768`
- `0x180015110`
- `0x180019a00`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::INilDelegate,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
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
  v10 = (void (__fastcall ***)(_QWORD, __int64))operator new(0x158u, (const struct std::nothrow_t *)&std::nothrow);
  a5 = v10;
  v11 = 0;
  if ( v10 )
  {
    v11 = Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
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
  v12 = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(v11 + 8);
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
0x180014768  push    rbx
0x18001476a  push    rbp
0x18001476b  push    rsi
0x18001476c  push    rdi
0x18001476d  push    r14
0x18001476f  sub     rsp, 20h
0x180014773  mov     rbp, r8
0x180014776  mov     r14, rdx
0x180014779  mov     rsi, rcx
0x18001477c  mov     qword ptr [rcx], 0
0x180014783  mov     rdi, [rsp+48h+arg_20]
0x180014788  test    rdi, rdi
0x18001478b  jnz     short loc_180014797
0x18001478d  mov     eax, 8007000Eh
0x180014792  jmp     loc_18001482E
0x180014797  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001479e  mov     ecx, 158h; unsigned __int64
0x1800147a3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800147a8  mov     [rsp+48h+arg_20], rax
0x1800147ad  xor     ebx, ebx
0x1800147af  test    rax, rax
0x1800147b2  jz      short loc_1800147D1
0x1800147b4  xor     r9d, r9d
0x1800147b7  mov     r8, rbp
0x1800147ba  mov     rdx, r14
0x1800147bd  mov     rcx, rax
0x1800147c0  call    ??0?$AsyncOperation@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@VCHSTRINGResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAA@$$QEAVComTaskPoolHandler@12@QEBGW4TrustLevel@@@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(Windows::Internal::ComTaskPoolHandler &&,ushort const * const,TrustLevel)
0x1800147c5  mov     rbx, rax
0x1800147c8  mov     [rsp+48h+arg_20], 0
0x1800147d1  lea     rcx, [rsp+48h+arg_20]
0x1800147d6  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x1800147db  test    rbx, rbx
0x1800147de  jnz     short loc_1800147F4
0x1800147e0  mov     rax, [rdi]
0x1800147e3  lea     edx, [rbx+1]
0x1800147e6  mov     rcx, rdi
0x1800147e9  mov     rax, [rax]
0x1800147ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147f1  nop
0x1800147f2  jmp     short loc_18001478D
0x1800147f4  mov     [rbx+108h], rdi
0x1800147fb  lea     rcx, [rbx+8]
0x1800147ff  call    ?Start@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@MEAAJXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(void)
0x180014804  mov     edi, eax
0x180014806  test    eax, eax
0x180014808  js      short loc_180014816
0x18001480a  lea     rcx, [rbx+0B8h]
0x180014811  mov     [rsi], rcx
0x180014814  xor     ebx, ebx
0x180014816  test    rbx, rbx
0x180014819  jz      short loc_18001482C
0x18001481b  lea     rcx, [rbx+8]
0x18001481f  mov     rax, [rcx]
0x180014822  mov     rax, [rax+10h]
0x180014826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001482b  nop
0x18001482c  mov     eax, edi
0x18001482e  add     rsp, 20h
0x180014832  pop     r14
0x180014834  pop     rdi
0x180014835  pop     rsi
0x180014836  pop     rbp
0x180014837  pop     rbx
0x180014838  retn
```
