# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(void)

- ea: `0x180005a60`
- end: `0x180005b23`
- name: `?OnStart@?$AsyncOperation@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@VCHSTRINGResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002e10`
- `0x180005a60`
- `0x180025fb4`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a9b`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180005ad3`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180005ad3`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(
        _DWORD *a1)
{
  __int64 v2; // rsi
  int v3; // ebx
  DWORD CurrentThreadId; // eax
  _DWORD *v5; // rdx
  __int64 result; // rax

  v2 = (__int64)(a1 - 2);
  v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _DWORD *))(**((_QWORD **)a1 + 32) + 8LL))(
         *((_QWORD *)a1 + 32),
         0,
         0,
         a1 + 70);
  if ( v3 < 0 )
  {
LABEL_7:
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostBroker::Cortana::SetHeyCortanaOptionAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(a1);
    return (unsigned int)v3;
  }
  CurrentThreadId = GetCurrentThreadId();
  v5 = a1 + 50;
  a1[82] = CurrentThreadId;
  if ( !v2 )
    v5 = 0;
  result = SHTaskPoolQueueTask((unsigned int)a1[80], (unsigned int)a1[81], CurrentThreadId, 0, v5, 0);
  v3 = result;
  if ( (int)result < 0 )
  {
    if ( a1[62] )
    {
      Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostBroker::Cortana::SetHeyCortanaOptionAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(a1);
      return 0;
    }
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(
      v2,
      1,
      (unsigned int)result);
    goto LABEL_7;
  }
  return result;
}

```

## disassembly

```asm
0x180005a60  mov     [rsp+arg_0], rbx
0x180005a65  mov     [rsp+arg_8], rsi
0x180005a6a  push    rdi
0x180005a6b  sub     rsp, 30h
0x180005a6f  mov     rdi, rcx
0x180005a72  lea     rsi, [rcx-8]
0x180005a76  mov     rcx, [rsi+108h]
0x180005a7d  xor     r8d, r8d
0x180005a80  xor     edx, edx
0x180005a82  lea     r9, [rdi+118h]
0x180005a89  mov     rax, [rcx]
0x180005a8c  mov     rax, [rax+8]
0x180005a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a95  mov     ebx, eax
0x180005a97  test    eax, eax
0x180005a99  js      short loc_180005AF9
0x180005a9b  call    cs:__imp_GetCurrentThreadId
0x180005aa1  xor     ecx, ecx
0x180005aa3  lea     rdx, [rdi+0C8h]
0x180005aaa  test    rsi, rsi
0x180005aad  mov     [rdi+148h], eax
0x180005ab3  mov     [rsp+38h+var_10], rcx
0x180005ab8  mov     r8d, eax
0x180005abb  cmovz   rdx, rcx
0x180005abf  mov     ecx, [rdi+140h]
0x180005ac5  mov     [rsp+38h+var_18], rdx
0x180005aca  xor     r9d, r9d
0x180005acd  mov     edx, [rdi+144h]
0x180005ad3  call    cs:__imp_SHTaskPoolQueueTask
0x180005ad9  mov     ebx, eax
0x180005adb  test    eax, eax
0x180005add  jns     short loc_180005B05
0x180005adf  mov     eax, [rdi+0F8h]
0x180005ae5  test    eax, eax
0x180005ae7  jnz     short loc_180005B15
0x180005ae9  mov     r8d, ebx
0x180005aec  mov     edx, 1
0x180005af1  mov     rcx, rsi
0x180005af4  call    ?_Run@?$AsyncOperation@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@VCHSTRINGResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXW4AsyncStage@23@J@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(Windows::Internal::AsyncStage,long)
0x180005af9  mov     edx, ebx
0x180005afb  mov     rcx, rdi
0x180005afe  call    ?TryTransitionToError@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SetHeyCortanaOptionAsyncActionName@Cortana@CloudExperienceHostBroker@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostBroker::Cortana::SetHeyCortanaOptionAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x180005b03  mov     eax, ebx
0x180005b05  mov     rbx, [rsp+38h+arg_0]
0x180005b0a  mov     rsi, [rsp+38h+arg_8]
0x180005b0f  add     rsp, 30h
0x180005b13  pop     rdi
0x180005b14  retn
0x180005b15  mov     edx, ebx
0x180005b17  mov     rcx, rdi
0x180005b1a  call    ?TryTransitionToError@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SetHeyCortanaOptionAsyncActionName@Cortana@CloudExperienceHostBroker@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostBroker::Cortana::SetHeyCortanaOptionAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x180005b1f  xor     eax, eax
0x180005b21  jmp     short loc_180005B05
```
