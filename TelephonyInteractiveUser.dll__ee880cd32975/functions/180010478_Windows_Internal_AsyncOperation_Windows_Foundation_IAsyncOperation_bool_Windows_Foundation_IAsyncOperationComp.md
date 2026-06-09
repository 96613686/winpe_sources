# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<uchar,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)

- ea: `0x180010478`
- end: `0x18001051d`
- name: `?_AfterComplete@?$AsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@V?$CBasicResult@E$0A@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ`
- size: `165`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180010524`
- `0x180010c40`

## callees

- `0x180009bc0`
- `0x180010478`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800104b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800104b2`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x1800104bc`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x1800104bc`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<unsigned char,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(
        __int64 a1)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  int v3; // ebx
  __int64 v4; // rcx
  signed __int32 v6[10]; // [rsp+0h] [rbp-28h] BYREF

  v2 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 264);
  if ( v2 )
    (**v2)(v2, 1);
  v3 = *(_DWORD *)(a1 + 328);
  *(_QWORD *)(a1 + 264) = 0;
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
  return Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(a1 + 8);
}

```

## disassembly

```asm
0x180010478  mov     [rsp+arg_0], rbx
0x18001047d  push    rdi
0x18001047e  sub     rsp, 20h
0x180010482  mov     rdi, rcx
0x180010485  mov     rcx, [rcx+108h]
0x18001048c  test    rcx, rcx
0x18001048f  jz      short loc_1800104A1
0x180010491  mov     rax, [rcx]
0x180010494  mov     edx, 1
0x180010499  mov     rax, [rax]
0x18001049c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104a1  mov     ebx, [rdi+148h]
0x1800104a7  mov     qword ptr [rdi+108h], 0
0x1800104b2  call    cs:__imp_GetCurrentThreadId
0x1800104b8  cmp     eax, ebx
0x1800104ba  jz      short loc_1800104C2
0x1800104bc  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x1800104c2  lock inc dword ptr [rdi+110h]
0x1800104c9  cmp     dword ptr [rdi+0A8h], 0
0x1800104d0  jle     short loc_18001050A
0x1800104d2  or      eax, 0FFFFFFFFh
0x1800104d5  lock xadd [rdi+0A8h], eax
0x1800104dd  cmp     eax, 1
0x1800104e0  jnz     short loc_18001050A
0x1800104e2  lock or [rsp+28h+var_28], 0
0x1800104e7  mov     rcx, [rdi+98h]
0x1800104ee  mov     qword ptr [rdi+98h], 0
0x1800104f9  test    rcx, rcx
0x1800104fc  jz      short loc_18001050A
0x1800104fe  mov     rax, [rcx]
0x180010501  mov     rax, [rax+10h]
0x180010505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001050a  lea     rcx, [rdi+8]
0x18001050e  mov     rbx, [rsp+28h+arg_0]
0x180010513  add     rsp, 20h
0x180010517  pop     rdi
0x180010518  jmp     ?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)
```
