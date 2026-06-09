# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::Streams::IRandomAccessStream>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)

- ea: `0x180057f6c`
- end: `0x180057fd0`
- name: `?_AfterComplete@?$AsyncOperation@U?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@23@V?$CMarshaledInterfaceResult@UIRandomAccessStream@Streams@Storage@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180057e4c`
- `0x180058230`

## callees

- `0x180057f6c`
- `0x180057fe0`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057fa6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057fa6`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180057fb0`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180057fb0`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::Streams::IRandomAccessStream>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(
        __int64 a1)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  int v3; // ebx

  v2 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 264);
  if ( v2 )
    (**v2)(v2, 1);
  v3 = *(_DWORD *)(a1 + 344);
  *(_QWORD *)(a1 + 264) = 0;
  if ( GetCurrentThreadId() != v3 )
    SHTaskPoolAllowThreadReuse();
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 272));
  return Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(a1 + 8);
}

```

## disassembly

```asm
0x180057f6c  mov     [rsp+arg_0], rbx
0x180057f71  push    rdi
0x180057f72  sub     rsp, 20h
0x180057f76  mov     rdi, rcx
0x180057f79  mov     rcx, [rcx+108h]
0x180057f80  test    rcx, rcx
0x180057f83  jz      short loc_180057F95
0x180057f85  mov     rax, [rcx]
0x180057f88  mov     edx, 1
0x180057f8d  mov     rax, [rax]
0x180057f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f95  mov     ebx, [rdi+158h]
0x180057f9b  mov     qword ptr [rdi+108h], 0
0x180057fa6  call    cs:__imp_GetCurrentThreadId
0x180057fac  cmp     eax, ebx
0x180057fae  jz      short loc_180057FB6
0x180057fb0  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x180057fb6  lock inc dword ptr [rdi+110h]
0x180057fbd  lea     rcx, [rdi+8]
0x180057fc1  mov     rbx, [rsp+28h+arg_0]
0x180057fc6  add     rsp, 20h
0x180057fca  pop     rdi
0x180057fcb  jmp     ?FireCompletion@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)
```
