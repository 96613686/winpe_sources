# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(long)

- ea: `0x180002ce0`
- end: `0x180002dd9`
- name: `?_AfterExecute@?$AsyncOperation@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@VCHSTRINGResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXJ@Z`
- size: `249`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180002b50`
- `0x180002e10`
- `0x18002c350`

## callees

- `0x180002ce0`
- `0x1800030c0`
- `0x18001f6fc`
- `0x180025fb4`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d8e`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180002d98`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180002d98`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(
        __int64 a1,
        int a2)
{
  bool v3; // di
  signed __int32 v4; // ecx
  __int64 result; // rax
  void (__fastcall ***v6)(_QWORD, __int64); // rcx
  int v7; // edi
  signed __int32 v8; // [rsp+58h] [rbp+10h] BYREF

  v3 = _InterlockedAdd((volatile signed __int32 *)(a1 + 260), 0xFFFFFFFF) == 0;
  if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 252)) == 1 )
    v3 = _InterlockedAdd((volatile signed __int32 *)(a1 + 260), 0xFFFFFFFF) == 0;
  v4 = *(_DWORD *)(a1 + 64);
  v8 = -2;
  result = (unsigned int)_InterlockedCompareExchange(&v8, v4, -2);
  if ( a2 < 0 )
  {
    if ( v8 != 2 )
      result = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostBroker::Cortana::SetHeyCortanaOptionAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(a1 + 8);
  }
  else if ( v8
         || (result = (unsigned int)_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 64), 1, 0),
             (_DWORD)result != v8) )
  {
    result = (unsigned int)_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 64), 1, 2);
  }
  if ( v3 )
  {
    v6 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 264);
    if ( v6 )
      (**v6)(v6, 1);
    v7 = *(_DWORD *)(a1 + 336);
    *(_QWORD *)(a1 + 264) = 0;
    if ( GetCurrentThreadId() != v7 )
      SHTaskPoolAllowThreadReuse();
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 272));
    if ( *(int *)(a1 + 168) > 0 )
      Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostBroker::Cortana::SetHeyCortanaOptionAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(a1 + 8);
    return Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion((signed __int32 *)(a1 + 8));
  }
  return result;
}

```

## disassembly

```asm
0x180002ce0  push    rbx
0x180002ce2  push    rbp
0x180002ce3  push    rsi
0x180002ce4  push    rdi
0x180002ce5  sub     rsp, 28h
0x180002ce9  mov     rbx, rcx
0x180002cec  lock add dword ptr [rcx+104h], 0FFFFFFFFh
0x180002cf4  mov     ebp, 1
0x180002cf9  setz    dil
0x180002cfd  mov     eax, ebp
0x180002cff  lock xadd [rcx+0FCh], eax
0x180002d07  inc     eax
0x180002d09  cmp     eax, ebp
0x180002d0b  jz      short loc_180002D56
0x180002d0d  mov     ecx, [rcx+40h]
0x180002d10  mov     [rsp+48h+arg_8], 0FFFFFFFEh
0x180002d18  mov     eax, [rsp+48h+arg_8]
0x180002d1c  lock cmpxchg [rsp+48h+arg_8], ecx
0x180002d22  test    edx, edx
0x180002d24  js      loc_180002DB9
0x180002d2a  cmp     [rsp+48h+arg_8], 0
0x180002d2f  jnz     short loc_180002D3E
0x180002d31  xor     eax, eax
0x180002d33  lock cmpxchg [rbx+40h], ebp
0x180002d38  cmp     eax, [rsp+48h+arg_8]
0x180002d3c  jz      short loc_180002D48
0x180002d3e  mov     eax, 2
0x180002d43  lock cmpxchg [rbx+40h], ebp
0x180002d48  test    dil, dil
0x180002d4b  jnz     short loc_180002D64
0x180002d4d  add     rsp, 28h
0x180002d51  pop     rdi
0x180002d52  pop     rsi
0x180002d53  pop     rbp
0x180002d54  pop     rbx
0x180002d55  retn
0x180002d56  lock add dword ptr [rcx+104h], 0FFFFFFFFh
0x180002d5e  setz    dil
0x180002d62  jmp     short loc_180002D0D
0x180002d64  mov     rcx, [rbx+108h]
0x180002d6b  test    rcx, rcx
0x180002d6e  jz      short loc_180002D7D
0x180002d70  mov     rax, [rcx]
0x180002d73  mov     edx, ebp
0x180002d75  mov     rax, [rax]
0x180002d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d7d  mov     edi, [rbx+150h]
0x180002d83  mov     qword ptr [rbx+108h], 0
0x180002d8e  call    cs:__imp_GetCurrentThreadId
0x180002d94  cmp     eax, edi
0x180002d96  jz      short loc_180002D9E
0x180002d98  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x180002d9e  lock inc dword ptr [rbx+110h]
0x180002da5  cmp     dword ptr [rbx+0A8h], 0
0x180002dac  jg      short loc_180002DCE
0x180002dae  lea     rcx, [rbx+8]
0x180002db2  call    ?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)
0x180002db7  jmp     short loc_180002D4D
0x180002db9  cmp     [rsp+48h+arg_8], 2
0x180002dbe  jz      short loc_180002D48
0x180002dc0  lea     rcx, [rbx+8]
0x180002dc4  call    ?TryTransitionToError@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SetHeyCortanaOptionAsyncActionName@Cortana@CloudExperienceHostBroker@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostBroker::Cortana::SetHeyCortanaOptionAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x180002dc9  jmp     loc_180002D48
0x180002dce  lea     rcx, [rbx+8]
0x180002dd2  call    ?UnlockProgressDelegate@?$AsyncBaseWithProgressFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncCausalityOptions@$1?SetHeyCortanaOptionAsyncActionName@Cortana@CloudExperienceHostBroker@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostBroker::Cortana::SetHeyCortanaOptionAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(void)
0x180002dd7  jmp     short loc_180002DAE
```
