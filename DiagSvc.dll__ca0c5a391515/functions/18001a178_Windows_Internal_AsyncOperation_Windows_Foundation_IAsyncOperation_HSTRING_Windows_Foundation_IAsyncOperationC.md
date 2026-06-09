# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)

- ea: `0x18001a178`
- end: `0x18001a1dc`
- name: `?_AfterComplete@?$AsyncOperation@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@VCHSTRINGResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ`
- size: `100`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001a1e4`
- `0x18001a3d4`

## callees

- `0x180017a40`
- `0x18001a178`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a1b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a1b2`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x18001a1bc`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x18001a1bc`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(
        __int64 a1)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  int v3; // ebx

  v2 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 264);
  if ( v2 )
    (**v2)(v2, 1);
  v3 = *(_DWORD *)(a1 + 336);
  *(_QWORD *)(a1 + 264) = 0;
  if ( GetCurrentThreadId() != v3 )
    SHTaskPoolAllowThreadReuse();
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 272));
  return Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(a1 + 8);
}

```

## disassembly

```asm
0x18001a178  mov     [rsp+arg_0], rbx
0x18001a17d  push    rdi
0x18001a17e  sub     rsp, 20h
0x18001a182  mov     rdi, rcx
0x18001a185  mov     rcx, [rcx+108h]
0x18001a18c  test    rcx, rcx
0x18001a18f  jz      short loc_18001A1A1
0x18001a191  mov     rax, [rcx]
0x18001a194  mov     edx, 1
0x18001a199  mov     rax, [rax]
0x18001a19c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1a1  mov     ebx, [rdi+150h]
0x18001a1a7  mov     qword ptr [rdi+108h], 0
0x18001a1b2  call    cs:__imp_GetCurrentThreadId
0x18001a1b8  cmp     eax, ebx
0x18001a1ba  jz      short loc_18001A1C2
0x18001a1bc  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x18001a1c2  lock inc dword ptr [rdi+110h]
0x18001a1c9  lea     rcx, [rdi+8]
0x18001a1cd  mov     rbx, [rsp+28h+arg_0]
0x18001a1d2  add     rsp, 20h
0x18001a1d6  pop     rdi
0x18001a1d7  jmp     ?FireCompletion@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)
```
