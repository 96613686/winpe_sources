# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::CBasicResult<Windows::System::AutoUpdateTimeZoneStatus,2>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)

- ea: `0x18001740c`
- end: `0x180017470`
- name: `?_AfterComplete@?$AsyncOperation@U?$IAsyncOperation@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@23@V?$CBasicResult@W4AutoUpdateTimeZoneStatus@System@Windows@@$01@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180017478`
- `0x180017628`

## callees

- `0x180015590`
- `0x18001740c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017446`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017446`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180017450`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180017450`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::CBasicResult<enum Windows::System::AutoUpdateTimeZoneStatus,2>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(
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
  return Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(a1 + 8);
}

```

## disassembly

```asm
0x18001740c  mov     [rsp+arg_0], rbx
0x180017411  push    rdi
0x180017412  sub     rsp, 20h
0x180017416  mov     rdi, rcx
0x180017419  mov     rcx, [rcx+108h]
0x180017420  test    rcx, rcx
0x180017423  jz      short loc_180017435
0x180017425  mov     rax, [rcx]
0x180017428  mov     edx, 1
0x18001742d  mov     rax, [rax]
0x180017430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017435  mov     ebx, [rdi+148h]
0x18001743b  mov     qword ptr [rdi+108h], 0
0x180017446  call    cs:__imp_GetCurrentThreadId
0x18001744c  cmp     eax, ebx
0x18001744e  jz      short loc_180017456
0x180017450  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x180017456  lock inc dword ptr [rdi+110h]
0x18001745d  lea     rcx, [rdi+8]
0x180017461  mov     rbx, [rsp+28h+arg_0]
0x180017466  add     rsp, 20h
0x18001746a  pop     rdi
0x18001746b  jmp     ?FireCompletion@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)
```
