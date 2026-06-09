# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Windows::Internal::CBasicResult<Windows::Internal::AI::Agents::Mcp::McpAccessStatus,4>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(void)

- ea: `0x18009cb40`
- end: `0x18009cc06`
- name: `?OnStart@?$AsyncOperation@U?$IAsyncOperation@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@@23@V?$CBasicResult@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@$03@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18009cb40`
- `0x18009df84`
- `0x18009e350`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009cb77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009cb77`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18009cbb7`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18009cbb7`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<enum Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Windows::Internal::CBasicResult<enum Windows::Internal::AI::Agents::Mcp::McpAccessStatus,4>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(
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
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
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
      Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
        a1,
        v2);
      return 0;
    }
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<enum Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Windows::Internal::CBasicResult<enum Windows::Internal::AI::Agents::Mcp::McpAccessStatus,4>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(
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
0x18009cb40  mov     [rsp+arg_0], rbx
0x18009cb45  mov     [rsp+arg_8], rsi
0x18009cb4a  push    rdi
0x18009cb4b  sub     rsp, 30h
0x18009cb4f  mov     rdi, rcx
0x18009cb52  xor     r8d, r8d
0x18009cb55  mov     rcx, [rcx+100h]
0x18009cb5c  xor     edx, edx
0x18009cb5e  lea     r9, [rdi+118h]
0x18009cb65  mov     rax, [rcx]
0x18009cb68  mov     rax, [rax+8]
0x18009cb6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009cb71  mov     ebx, eax
0x18009cb73  test    eax, eax
0x18009cb75  js      short loc_18009CBDC
0x18009cb77  call    cs:__imp_GetCurrentThreadId
0x18009cb7d  lea     rdx, [rdi+0C8h]
0x18009cb84  mov     [rsp+38h+var_10], 0
0x18009cb8d  lea     rcx, [rdi-8]
0x18009cb91  mov     [rdi+140h], eax
0x18009cb97  neg     rcx
0x18009cb9a  mov     ecx, [rdi+138h]
0x18009cba0  sbb     r8, r8
0x18009cba3  xor     r9d, r9d
0x18009cba6  and     r8, rdx
0x18009cba9  mov     edx, [rdi+13Ch]
0x18009cbaf  mov     [rsp+38h+var_18], r8
0x18009cbb4  mov     r8d, eax
0x18009cbb7  call    cs:__imp_SHTaskPoolQueueTask
0x18009cbbd  mov     ebx, eax
0x18009cbbf  test    eax, eax
0x18009cbc1  jns     short loc_18009CBE6
0x18009cbc3  mov     eax, [rdi+0F8h]
0x18009cbc9  test    eax, eax
0x18009cbcb  jnz     short loc_18009CBF8
0x18009cbcd  mov     r8d, ebx
0x18009cbd0  lea     edx, [rax+1]
0x18009cbd3  lea     rcx, [rdi-8]
0x18009cbd7  call    ?_Run@?$AsyncOperation@U?$IAsyncOperation@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@@23@V?$CBasicResult@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@$03@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXW4AsyncStage@23@J@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Windows::Internal::CBasicResult<Windows::Internal::AI::Agents::Mcp::McpAccessStatus,4>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(Windows::Internal::AsyncStage,long)
0x18009cbdc  mov     edx, ebx
0x18009cbde  mov     rcx, rdi
0x18009cbe1  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x18009cbe6  mov     rsi, [rsp+38h+arg_8]
0x18009cbeb  mov     eax, ebx
0x18009cbed  mov     rbx, [rsp+38h+arg_0]
0x18009cbf2  add     rsp, 30h
0x18009cbf6  pop     rdi
0x18009cbf7  retn
0x18009cbf8  mov     edx, ebx
0x18009cbfa  mov     rcx, rdi
0x18009cbfd  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x18009cc02  xor     ebx, ebx
0x18009cc04  jmp     short loc_18009CBE6
```
