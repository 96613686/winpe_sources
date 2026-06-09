# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<uchar,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(void)

- ea: `0x18000cff0`
- end: `0x18000d10d`
- name: `?OnStart@?$AsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@V?$CBasicResult@E$0A@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `285`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000cff0`
- `0x18000fa28`
- `0x180010524`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d02f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d02f`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18000d06e`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18000d06e`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<unsigned char,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(
        __int64 a1)
{
  unsigned int v2; // esi
  __int64 v3; // rdi
  DWORD CurrentThreadId; // eax
  int v5; // eax
  __int64 v6; // rdx

  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**(_QWORD **)(a1 + 256) + 8LL))(
         *(_QWORD *)(a1 + 256),
         0,
         0,
         a1 + 280);
  if ( (v2 & 0x80000000) != 0 )
    goto LABEL_11;
  v3 = a1 - 8;
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
      Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
        a1,
        v2);
      return 0;
    }
    if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 248)) != 1 )
      goto LABEL_11;
    v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**(_QWORD **)(v3 + 264) + 8LL))(
           *(_QWORD *)(v3 + 264),
           1,
           v2,
           v3 + 288);
    if ( v5 >= 0 && *(_BYTE *)(v3 + 297) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 280), 0xFFFFFFFF) != 1 )
      {
LABEL_11:
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
          a1,
          v2);
        return v2;
      }
      v6 = *(unsigned int *)(v3 + 284);
    }
    else
    {
      v6 = (unsigned int)v5;
    }
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<unsigned char,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(
      a1 - 8,
      v6);
    goto LABEL_11;
  }
  return v2;
}

```

## disassembly

```asm
0x18000cff0  mov     [rsp+arg_0], rbx
0x18000cff5  mov     [rsp+arg_8], rsi
0x18000cffa  push    rdi
0x18000cffb  sub     rsp, 30h
0x18000cfff  mov     rbx, rcx
0x18000d002  xor     r8d, r8d
0x18000d005  mov     rcx, [rcx+100h]
0x18000d00c  xor     edx, edx
0x18000d00e  lea     r9, [rbx+118h]
0x18000d015  mov     rax, [rcx]
0x18000d018  mov     rax, [rax+8]
0x18000d01c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d021  mov     esi, eax
0x18000d023  test    eax, eax
0x18000d025  js      loc_18000D0E3
0x18000d02b  lea     rdi, [rbx-8]
0x18000d02f  call    cs:__imp_GetCurrentThreadId
0x18000d035  lea     rdx, [rbx+0C8h]
0x18000d03c  mov     [rsp+38h+var_10], 0
0x18000d045  mov     rcx, rdi
0x18000d048  mov     [rbx+140h], eax
0x18000d04e  neg     rcx
0x18000d051  mov     ecx, [rbx+138h]
0x18000d057  sbb     r8, r8
0x18000d05a  xor     r9d, r9d
0x18000d05d  and     r8, rdx
0x18000d060  mov     edx, [rbx+13Ch]
0x18000d066  mov     [rsp+38h+var_18], r8
0x18000d06b  mov     r8d, eax
0x18000d06e  call    cs:__imp_SHTaskPoolQueueTask
0x18000d074  mov     esi, eax
0x18000d076  test    eax, eax
0x18000d078  jns     short loc_18000D0ED
0x18000d07a  mov     eax, [rbx+0F8h]
0x18000d080  test    eax, eax
0x18000d082  jnz     short loc_18000D0FF
0x18000d084  lea     edx, [rax+1]
0x18000d087  mov     eax, edx
0x18000d089  lock xadd [rbx+0F8h], eax
0x18000d091  add     eax, edx
0x18000d093  cmp     eax, edx
0x18000d095  jnz     short loc_18000D0E3
0x18000d097  mov     rcx, [rdi+108h]
0x18000d09e  lea     r9, [rdi+120h]
0x18000d0a5  mov     r8d, esi
0x18000d0a8  mov     rax, [rcx]
0x18000d0ab  mov     rax, [rax+8]
0x18000d0af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0b4  test    eax, eax
0x18000d0b6  js      short loc_18000D0D9
0x18000d0b8  cmp     byte ptr [rdi+129h], 0
0x18000d0bf  jz      short loc_18000D0D9
0x18000d0c1  or      eax, 0FFFFFFFFh
0x18000d0c4  lock xadd [rdi+118h], eax
0x18000d0cc  cmp     eax, 1
0x18000d0cf  jnz     short loc_18000D0E3
0x18000d0d1  mov     edx, [rdi+11Ch]
0x18000d0d7  jmp     short loc_18000D0DB
0x18000d0d9  mov     edx, eax
0x18000d0db  mov     rcx, rdi
0x18000d0de  call    ?_AfterExecute@?$AsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@V?$CBasicResult@E$0A@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXJ@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<uchar,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(long)
0x18000d0e3  mov     edx, esi
0x18000d0e5  mov     rcx, rbx
0x18000d0e8  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x18000d0ed  mov     rbx, [rsp+38h+arg_0]
0x18000d0f2  mov     eax, esi
0x18000d0f4  mov     rsi, [rsp+38h+arg_8]
0x18000d0f9  add     rsp, 30h
0x18000d0fd  pop     rdi
0x18000d0fe  retn
0x18000d0ff  mov     edx, esi
0x18000d101  mov     rcx, rbx
0x18000d104  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x18000d109  xor     esi, esi
0x18000d10b  jmp     short loc_18000D0ED
```
