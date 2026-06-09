# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Windows::Internal::CBasicResult<Windows::Internal::AI::Agents::Mcp::McpAccessStatus,4>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)

- ea: `0x18009e0b4`
- end: `0x18009e118`
- name: `?_AfterComplete@?$AsyncOperation@U?$IAsyncOperation@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@@23@V?$CBasicResult@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@$03@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18009e120`
- `0x18009e350`

## callees

- `0x18009bc80`
- `0x18009e0b4`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009e0ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009e0ee`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x18009e0f8`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x18009e0f8`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<enum Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Windows::Internal::CBasicResult<enum Windows::Internal::AI::Agents::Mcp::McpAccessStatus,4>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(
        __int64 a1)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  int v3; // ebx

  v2 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 264);
  if ( v2 )
    (**v2)(v2, 1);
  v3 = *(_DWORD *)(a1 + 328);
  *(_QWORD *)(a1 + 264) = 0;
  if ( GetCurrentThreadId() != v3 )
    SHTaskPoolAllowThreadReuse();
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 272));
  return Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(a1 + 8);
}

```

## disassembly

```asm
0x18009e0b4  mov     [rsp+arg_0], rbx
0x18009e0b9  push    rdi
0x18009e0ba  sub     rsp, 20h
0x18009e0be  mov     rdi, rcx
0x18009e0c1  mov     rcx, [rcx+108h]
0x18009e0c8  test    rcx, rcx
0x18009e0cb  jz      short loc_18009E0DD
0x18009e0cd  mov     rax, [rcx]
0x18009e0d0  mov     edx, 1
0x18009e0d5  mov     rax, [rax]
0x18009e0d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e0dd  mov     ebx, [rdi+148h]
0x18009e0e3  mov     qword ptr [rdi+108h], 0
0x18009e0ee  call    cs:__imp_GetCurrentThreadId
0x18009e0f4  cmp     eax, ebx
0x18009e0f6  jz      short loc_18009E0FE
0x18009e0f8  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x18009e0fe  lock inc dword ptr [rdi+110h]
0x18009e105  lea     rcx, [rdi+8]
0x18009e109  mov     rbx, [rsp+28h+arg_0]
0x18009e10e  add     rsp, 20h
0x18009e112  pop     rdi
0x18009e113  jmp     ?FireCompletion@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@W4McpAccessStatus@Mcp@Agents@AI@Internal@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::AI::Agents::Mcp::McpAccessStatus>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)
```
