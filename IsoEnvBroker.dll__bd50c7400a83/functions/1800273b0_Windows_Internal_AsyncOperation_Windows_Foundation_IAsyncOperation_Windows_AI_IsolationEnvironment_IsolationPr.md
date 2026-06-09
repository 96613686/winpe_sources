# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,Windows::Internal::CMarshaledInterfaceResult<Windows::AI::IsolationEnvironment::IIsolationProvisionResult>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(void)

- ea: `0x1800273b0`
- end: `0x1800274cd`
- name: `?OnStart@?$AsyncOperation@U?$IAsyncOperation@PEAVIsolationProvisionResult@IsolationEnvironment@AI@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVIsolationProvisionResult@IsolationEnvironment@AI@Windows@@@23@V?$CMarshaledInterfaceResult@UIIsolationProvisionResult@IsolationEnvironment@AI@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `285`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800273b0`
- `0x1800299c8`
- `0x18002a820`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800273ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800273ef`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18002742e`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18002742e`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,Windows::Internal::CMarshaledInterfaceResult<Windows::AI::IsolationEnvironment::IIsolationProvisionResult>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(
        __int64 a1)
{
  unsigned int v2; // esi
  __int64 v3; // rdi
  DWORD CurrentThreadId; // eax
  int v5; // eax
  int v6; // edx

  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**(_QWORD **)(a1 + 256) + 8LL))(
         *(_QWORD *)(a1 + 256),
         0,
         0,
         a1 + 280);
  if ( (v2 & 0x80000000) != 0 )
    goto LABEL_11;
  v3 = a1 - 8;
  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(a1 + 336) = CurrentThreadId;
  v2 = SHTaskPoolQueueTask(
         *(unsigned int *)(a1 + 328),
         *(unsigned int *)(a1 + 332),
         CurrentThreadId,
         0,
         (a1 + 200) & -(__int64)(a1 != 8),
         0);
  if ( (v2 & 0x80000000) != 0 )
  {
    if ( *(_DWORD *)(a1 + 248) )
    {
      Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
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
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
          a1,
          v2);
        return v2;
      }
      v6 = *(_DWORD *)(v3 + 284);
    }
    else
    {
      v6 = v5;
    }
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,Windows::Internal::CMarshaledInterfaceResult<Windows::AI::IsolationEnvironment::IIsolationProvisionResult>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(
      a1 - 8,
      v6);
    goto LABEL_11;
  }
  return v2;
}

```

## disassembly

```asm
0x1800273b0  mov     [rsp+arg_0], rbx
0x1800273b5  mov     [rsp+arg_8], rsi
0x1800273ba  push    rdi
0x1800273bb  sub     rsp, 30h
0x1800273bf  mov     rbx, rcx
0x1800273c2  xor     r8d, r8d
0x1800273c5  mov     rcx, [rcx+100h]
0x1800273cc  xor     edx, edx
0x1800273ce  lea     r9, [rbx+118h]
0x1800273d5  mov     rax, [rcx]
0x1800273d8  mov     rax, [rax+8]
0x1800273dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273e1  mov     esi, eax
0x1800273e3  test    eax, eax
0x1800273e5  js      loc_1800274A3
0x1800273eb  lea     rdi, [rbx-8]
0x1800273ef  call    cs:__imp_GetCurrentThreadId
0x1800273f5  lea     rdx, [rbx+0C8h]
0x1800273fc  mov     [rsp+38h+var_10], 0
0x180027405  mov     rcx, rdi
0x180027408  mov     [rbx+150h], eax
0x18002740e  neg     rcx
0x180027411  mov     ecx, [rbx+148h]
0x180027417  sbb     r8, r8
0x18002741a  xor     r9d, r9d
0x18002741d  and     r8, rdx
0x180027420  mov     edx, [rbx+14Ch]
0x180027426  mov     [rsp+38h+var_18], r8
0x18002742b  mov     r8d, eax
0x18002742e  call    cs:__imp_SHTaskPoolQueueTask
0x180027434  mov     esi, eax
0x180027436  test    eax, eax
0x180027438  jns     short loc_1800274AD
0x18002743a  mov     eax, [rbx+0F8h]
0x180027440  test    eax, eax
0x180027442  jnz     short loc_1800274BF
0x180027444  lea     edx, [rax+1]
0x180027447  mov     eax, edx
0x180027449  lock xadd [rbx+0F8h], eax
0x180027451  add     eax, edx
0x180027453  cmp     eax, edx
0x180027455  jnz     short loc_1800274A3
0x180027457  mov     rcx, [rdi+108h]
0x18002745e  lea     r9, [rdi+120h]
0x180027465  mov     r8d, esi
0x180027468  mov     rax, [rcx]
0x18002746b  mov     rax, [rax+8]
0x18002746f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027474  test    eax, eax
0x180027476  js      short loc_180027499
0x180027478  cmp     byte ptr [rdi+129h], 0
0x18002747f  jz      short loc_180027499
0x180027481  or      eax, 0FFFFFFFFh
0x180027484  lock xadd [rdi+118h], eax
0x18002748c  cmp     eax, 1
0x18002748f  jnz     short loc_1800274A3
0x180027491  mov     edx, [rdi+11Ch]
0x180027497  jmp     short loc_18002749B
0x180027499  mov     edx, eax
0x18002749b  mov     rcx, rdi
0x18002749e  call    ?_AfterExecute@?$AsyncOperation@U?$IAsyncOperation@PEAVIsolationProvisionResult@IsolationEnvironment@AI@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVIsolationProvisionResult@IsolationEnvironment@AI@Windows@@@23@V?$CMarshaledInterfaceResult@UIIsolationProvisionResult@IsolationEnvironment@AI@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXJ@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,Windows::Internal::CMarshaledInterfaceResult<Windows::AI::IsolationEnvironment::IIsolationProvisionResult>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(long)
0x1800274a3  mov     edx, esi
0x1800274a5  mov     rcx, rbx
0x1800274a8  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVIsolationProvisionResult@IsolationEnvironment@AI@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x1800274ad  mov     rbx, [rsp+38h+arg_0]
0x1800274b2  mov     eax, esi
0x1800274b4  mov     rsi, [rsp+38h+arg_8]
0x1800274b9  add     rsp, 30h
0x1800274bd  pop     rdi
0x1800274be  retn
0x1800274bf  mov     edx, esi
0x1800274c1  mov     rcx, rbx
0x1800274c4  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVIsolationProvisionResult@IsolationEnvironment@AI@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::AI::IsolationEnvironment::IsolationProvisionResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x1800274c9  xor     esi, esi
0x1800274cb  jmp     short loc_1800274AD
```
