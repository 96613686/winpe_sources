# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,Windows::Internal::CMarshaledInterfaceResult<Windows::AI::IsolationEnvironment::IIsolationProvisionResult>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)

- ea: `0x18002a774`
- end: `0x18002a81a`
- name: `?_AfterComplete@?$AsyncOperation@U?$IAsyncOperation@PEAVIsolationProvisionResult@IsolationEnvironment@AI@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVIsolationProvisionResult@IsolationEnvironment@AI@Windows@@@23@V?$CMarshaledInterfaceResult@UIIsolationProvisionResult@IsolationEnvironment@AI@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ`
- size: `166`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002a820`
- `0x18002e0ec`

## callees

- `0x180024510`
- `0x18002a774`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a7ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a7ae`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x18002a7b8`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x18002a7b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,Windows::Internal::CMarshaledInterfaceResult<Windows::AI::IsolationEnvironment::IIsolationProvisionResult>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(
        __int64 a1)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  int v3; // ebx
  __int64 v4; // rcx
  signed __int32 v6[10]; // [rsp+0h] [rbp-28h] BYREF

  v2 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 264);
  if ( v2 )
    (**v2)(v2, 1);
  *(_QWORD *)(a1 + 264) = 0;
  v3 = *(_DWORD *)(a1 + 344);
  if ( GetCurrentThreadId() != v3 )
    SHTaskPoolAllowThreadReuse();
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 272));
  if ( *(int *)(a1 + 168) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 168), 0xFFFFFFFF) == 1 )
  {
    _InterlockedOr(v6, 0);
    v4 = *(_QWORD *)(a1 + 152);
    *(_QWORD *)(a1 + 152) = 0;
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(a1 + 8);
}

```

## disassembly

```asm
0x18002a774  mov     [rsp+arg_0], rbx
0x18002a779  push    rdi
0x18002a77a  sub     rsp, 20h
0x18002a77e  mov     rdi, rcx
0x18002a781  mov     rcx, [rcx+108h]
0x18002a788  test    rcx, rcx
0x18002a78b  jz      short loc_18002A79D
0x18002a78d  mov     rax, [rcx]
0x18002a790  mov     edx, 1
0x18002a795  mov     rax, [rax]
0x18002a798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a79d  mov     qword ptr [rdi+108h], 0
0x18002a7a8  mov     ebx, [rdi+158h]
0x18002a7ae  call    cs:__imp_GetCurrentThreadId
0x18002a7b4  cmp     eax, ebx
0x18002a7b6  jz      short loc_18002A7BE
0x18002a7b8  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x18002a7be  lock inc dword ptr [rdi+110h]
0x18002a7c5  cmp     dword ptr [rdi+0A8h], 0
0x18002a7cc  jle     short loc_18002A807
0x18002a7ce  or      eax, 0FFFFFFFFh
0x18002a7d1  lock xadd [rdi+0A8h], eax
0x18002a7d9  cmp     eax, 1
0x18002a7dc  jnz     short loc_18002A807
0x18002a7de  lock or [rsp+28h+var_28], 0
0x18002a7e3  mov     rcx, [rdi+98h]
0x18002a7ea  mov     qword ptr [rdi+98h], 0
0x18002a7f5  test    rcx, rcx
0x18002a7f8  jz      short loc_18002A807
0x18002a7fa  mov     rax, [rcx]
0x18002a7fd  mov     rax, [rax+10h]
0x18002a801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a806  nop
0x18002a807  lea     rcx, [rdi+8]
0x18002a80b  mov     rbx, [rsp+28h+arg_0]
0x18002a810  add     rsp, 20h
0x18002a814  pop     rdi
0x18002a815  jmp     ?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVIsolationProvisionResult@IsolationEnvironment@AI@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)
```
