# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(void)

- ea: `0x180018840`
- end: `0x180018906`
- name: `?OnStart@?$AsyncOperation@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@VCHSTRINGResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180018840`
- `0x180019d04`
- `0x18001a3d4`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018877`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018877`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800188b7`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800188b7`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(
        __int64 a1)
{
  unsigned int v2; // ebx
  DWORD CurrentThreadId; // eax

  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**(_QWORD **)(a1 + 256) + 8LL))(
         *(_QWORD *)(a1 + 256),
         0,
         0,
         a1 + 280);
  if ( (v2 & 0x80000000) != 0 )
  {
LABEL_5:
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
      a1,
      v2);
    return v2;
  }
  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(a1 + 328) = CurrentThreadId;
  v2 = SHTaskPoolQueueTask(
         *(unsigned int *)(a1 + 320),
         *(unsigned int *)(a1 + 324),
         CurrentThreadId,
         0,
         (a1 + 200) & -(__int64)(a1 != 8),
         0);
  if ( (v2 & 0x80000000) != 0 )
  {
    if ( *(_DWORD *)(a1 + 248) )
    {
      Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
        a1,
        v2);
      return 0;
    }
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(
      a1 - 8,
      1,
      v2);
    goto LABEL_5;
  }
  return v2;
}

```

## disassembly

```asm
0x180018840  mov     [rsp+arg_0], rbx
0x180018845  mov     [rsp+arg_8], rsi
0x18001884a  push    rdi
0x18001884b  sub     rsp, 30h
0x18001884f  mov     rdi, rcx
0x180018852  xor     r8d, r8d
0x180018855  mov     rcx, [rcx+100h]
0x18001885c  xor     edx, edx
0x18001885e  lea     r9, [rdi+118h]
0x180018865  mov     rax, [rcx]
0x180018868  mov     rax, [rax+8]
0x18001886c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018871  mov     ebx, eax
0x180018873  test    eax, eax
0x180018875  js      short loc_1800188DC
0x180018877  call    cs:__imp_GetCurrentThreadId
0x18001887d  lea     rdx, [rdi+0C8h]
0x180018884  mov     [rsp+38h+var_10], 0
0x18001888d  lea     rcx, [rdi-8]
0x180018891  mov     [rdi+148h], eax
0x180018897  neg     rcx
0x18001889a  mov     ecx, [rdi+140h]
0x1800188a0  sbb     r8, r8
0x1800188a3  xor     r9d, r9d
0x1800188a6  and     r8, rdx
0x1800188a9  mov     edx, [rdi+144h]
0x1800188af  mov     [rsp+38h+var_18], r8
0x1800188b4  mov     r8d, eax
0x1800188b7  call    cs:__imp_SHTaskPoolQueueTask
0x1800188bd  mov     ebx, eax
0x1800188bf  test    eax, eax
0x1800188c1  jns     short loc_1800188E6
0x1800188c3  mov     eax, [rdi+0F8h]
0x1800188c9  test    eax, eax
0x1800188cb  jnz     short loc_1800188F8
0x1800188cd  mov     r8d, ebx
0x1800188d0  lea     edx, [rax+1]
0x1800188d3  lea     rcx, [rdi-8]
0x1800188d7  call    ?_Run@?$AsyncOperation@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@VCHSTRINGResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXW4AsyncStage@23@J@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(Windows::Internal::AsyncStage,long)
0x1800188dc  mov     edx, ebx
0x1800188de  mov     rcx, rdi
0x1800188e1  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x1800188e6  mov     rsi, [rsp+38h+arg_8]
0x1800188eb  mov     eax, ebx
0x1800188ed  mov     rbx, [rsp+38h+arg_0]
0x1800188f2  add     rsp, 30h
0x1800188f6  pop     rdi
0x1800188f7  retn
0x1800188f8  mov     edx, ebx
0x1800188fa  mov     rcx, rdi
0x1800188fd  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x180018902  xor     ebx, ebx
0x180018904  jmp     short loc_1800188E6
```
