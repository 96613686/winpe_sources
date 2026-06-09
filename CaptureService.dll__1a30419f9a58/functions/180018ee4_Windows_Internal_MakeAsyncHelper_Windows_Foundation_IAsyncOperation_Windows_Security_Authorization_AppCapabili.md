# Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncOperation<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::INilDelegate,Windows::Internal::CBasicResult<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> * *,Windows::Internal::ComTaskPoolHandler &&,ushort const * const,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CBasicResult<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>> *)

- ea: `0x180018ee4`
- end: `0x180018fb5`
- name: `??$MakeAsyncHelper@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@23@UINilDelegate@Internal@3@V?$CBasicResult@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@$02@63@VComTaskPoolHandler@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@YAJPEAPEAU?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@1@$$QEAVComTaskPoolHandler@01@QEBGW4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CBasicResult@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@$02@Internal@Windows@@@01@@Z`
- size: `209`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64, void (__fastcall ***)(_QWORD, __int64))`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180019eb0`

## callees

- `0x18000335c`
- `0x18000dc98`
- `0x180018ee4`
- `0x180019114`
- `0x18001a010`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncOperation<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::INilDelegate,Windows::Internal::CBasicResult<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
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
  v10 = (void (__fastcall ***)(_QWORD, __int64))operator new(0x150u, (const struct std::nothrow_t *)std::nothrow);
  a5 = v10;
  v11 = 0;
  if ( v10 )
  {
    v11 = Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::CBasicResult<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperation<Windows::Foundation::IAsyncOperation<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::CBasicResult<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
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
  v12 = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(v11 + 8);
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
0x180018ee4  push    rbx
0x180018ee6  push    rbp
0x180018ee7  push    rsi
0x180018ee8  push    rdi
0x180018ee9  push    r14
0x180018eeb  sub     rsp, 20h
0x180018eef  mov     rbp, r8
0x180018ef2  mov     r14, rdx
0x180018ef5  mov     rsi, rcx
0x180018ef8  mov     qword ptr [rcx], 0
0x180018eff  mov     rdi, [rsp+48h+arg_20]
0x180018f04  test    rdi, rdi
0x180018f07  jnz     short loc_180018F13
0x180018f09  mov     eax, 8007000Eh
0x180018f0e  jmp     loc_180018FAA
0x180018f13  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018f1a  mov     ecx, 150h; unsigned __int64
0x180018f1f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180018f24  mov     [rsp+48h+arg_20], rax
0x180018f29  xor     ebx, ebx
0x180018f2b  test    rax, rax
0x180018f2e  jz      short loc_180018F4D
0x180018f30  xor     r9d, r9d
0x180018f33  mov     r8, rbp
0x180018f36  mov     rdx, r14
0x180018f39  mov     rcx, rax
0x180018f3c  call    ??0?$AsyncOperation@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@23@V?$CBasicResult@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@$02@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAA@$$QEAVComTaskPoolHandler@12@QEBGW4TrustLevel@@@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::CBasicResult<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::CBasicResult<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(Windows::Internal::ComTaskPoolHandler &&,ushort const * const,TrustLevel)
0x180018f41  mov     rbx, rax
0x180018f44  mov     [rsp+48h+arg_20], 0
0x180018f4d  lea     rcx, [rsp+48h+arg_20]
0x180018f52  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x180018f57  test    rbx, rbx
0x180018f5a  jnz     short loc_180018F70
0x180018f5c  mov     rax, [rdi]
0x180018f5f  lea     edx, [rbx+1]
0x180018f62  mov     rcx, rdi
0x180018f65  mov     rax, [rax]
0x180018f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018f6d  nop
0x180018f6e  jmp     short loc_180018F09
0x180018f70  mov     [rbx+108h], rdi
0x180018f77  lea     rcx, [rbx+8]
0x180018f7b  call    ?Start@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@MEAAJXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(void)
0x180018f80  mov     edi, eax
0x180018f82  test    eax, eax
0x180018f84  js      short loc_180018F92
0x180018f86  lea     rcx, [rbx+0B8h]
0x180018f8d  mov     [rsi], rcx
0x180018f90  xor     ebx, ebx
0x180018f92  test    rbx, rbx
0x180018f95  jz      short loc_180018FA8
0x180018f97  lea     rcx, [rbx+8]
0x180018f9b  mov     rax, [rcx]
0x180018f9e  mov     rax, [rax+10h]
0x180018fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fa7  nop
0x180018fa8  mov     eax, edi
0x180018faa  add     rsp, 20h
0x180018fae  pop     r14
0x180018fb0  pop     rdi
0x180018fb1  pop     rsi
0x180018fb2  pop     rbp
0x180018fb3  pop     rbx
0x180018fb4  retn
```
