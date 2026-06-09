# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::CBasicResult<Windows::System::AutoUpdateTimeZoneStatus,2>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(void)

- ea: `0x1800160f0`
- end: `0x1800161b6`
- name: `?OnStart@?$AsyncOperation@U?$IAsyncOperation@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@23@V?$CBasicResult@W4AutoUpdateTimeZoneStatus@System@Windows@@$01@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800160f0`
- `0x1800172b8`
- `0x180017628`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016127`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016127`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180016167`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180016167`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::CBasicResult<enum Windows::System::AutoUpdateTimeZoneStatus,2>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(
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
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::ProcessLauncherResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
      a1,
      v2);
    return v2;
  }
  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(a1 + 320) = CurrentThreadId;
  v2 = SHTaskPoolQueueTask(
         *(unsigned int *)(a1 + 312),
         *(unsigned int *)(a1 + 316),
         CurrentThreadId,
         0,
         (a1 + 200) & -(__int64)(a1 != 8),
         0);
  if ( (v2 & 0x80000000) != 0 )
  {
    if ( *(_DWORD *)(a1 + 248) )
    {
      Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::ProcessLauncherResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
        a1,
        v2);
      return 0;
    }
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::CBasicResult<enum Windows::System::AutoUpdateTimeZoneStatus,2>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(
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
0x1800160f0  mov     [rsp+arg_0], rbx
0x1800160f5  mov     [rsp+arg_8], rsi
0x1800160fa  push    rdi
0x1800160fb  sub     rsp, 30h
0x1800160ff  mov     rdi, rcx
0x180016102  xor     r8d, r8d
0x180016105  mov     rcx, [rcx+100h]
0x18001610c  xor     edx, edx
0x18001610e  lea     r9, [rdi+118h]
0x180016115  mov     rax, [rcx]
0x180016118  mov     rax, [rax+8]
0x18001611c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016121  mov     ebx, eax
0x180016123  test    eax, eax
0x180016125  js      short loc_18001618C
0x180016127  call    cs:__imp_GetCurrentThreadId
0x18001612d  lea     rdx, [rdi+0C8h]
0x180016134  mov     [rsp+38h+var_10], 0
0x18001613d  lea     rcx, [rdi-8]
0x180016141  mov     [rdi+140h], eax
0x180016147  neg     rcx
0x18001614a  mov     ecx, [rdi+138h]
0x180016150  sbb     r8, r8
0x180016153  xor     r9d, r9d
0x180016156  and     r8, rdx
0x180016159  mov     edx, [rdi+13Ch]
0x18001615f  mov     [rsp+38h+var_18], r8
0x180016164  mov     r8d, eax
0x180016167  call    cs:__imp_SHTaskPoolQueueTask
0x18001616d  mov     ebx, eax
0x18001616f  test    eax, eax
0x180016171  jns     short loc_180016196
0x180016173  mov     eax, [rdi+0F8h]
0x180016179  test    eax, eax
0x18001617b  jnz     short loc_1800161A8
0x18001617d  mov     r8d, ebx
0x180016180  lea     edx, [rax+1]
0x180016183  lea     rcx, [rdi-8]
0x180016187  call    ?_Run@?$AsyncOperation@U?$IAsyncOperation@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@23@V?$CBasicResult@W4AutoUpdateTimeZoneStatus@System@Windows@@$01@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXW4AsyncStage@23@J@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::CBasicResult<Windows::System::AutoUpdateTimeZoneStatus,2>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(Windows::Internal::AsyncStage,long)
0x18001618c  mov     edx, ebx
0x18001618e  mov     rcx, rdi
0x180016191  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVProcessLauncherResult@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::ProcessLauncherResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x180016196  mov     rsi, [rsp+38h+arg_8]
0x18001619b  mov     eax, ebx
0x18001619d  mov     rbx, [rsp+38h+arg_0]
0x1800161a2  add     rsp, 30h
0x1800161a6  pop     rdi
0x1800161a7  retn
0x1800161a8  mov     edx, ebx
0x1800161aa  mov     rcx, rdi
0x1800161ad  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVProcessLauncherResult@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::ProcessLauncherResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x1800161b2  xor     ebx, ebx
0x1800161b4  jmp     short loc_180016196
```
