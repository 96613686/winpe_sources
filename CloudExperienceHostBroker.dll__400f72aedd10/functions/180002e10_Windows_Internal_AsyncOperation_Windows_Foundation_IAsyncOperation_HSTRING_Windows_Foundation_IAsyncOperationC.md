# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(Windows::Internal::AsyncStage,long)

- ea: `0x180002e10`
- end: `0x18000302c`
- name: `?_Run@?$AsyncOperation@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@VCHSTRINGResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXW4AsyncStage@23@J@Z`
- size: `540`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180005a60`
- `0x18002da50`

## callees

- `0x180002ce0`
- `0x180002e10`
- `0x180003040`
- `0x1800030c0`
- `0x18001f6fc`
- `0x180025fb4`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f0e`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180002f18`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x180002f18`

## pseudocode

```c
void __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  int v4; // edx
  bool v5; // bp
  signed __int32 v6; // ecx
  signed __int32 v7; // eax
  void (__fastcall ***v8)(_QWORD, __int64); // rcx
  int v9; // edi
  bool v10; // cl
  signed __int32 v11; // [rsp+68h] [rbp+10h] BYREF

  if ( (_DWORD)a2 == 2 )
  {
    if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 252)) != 1 )
      return;
    (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(a1 + 264) + 8LL))(
      *(_QWORD *)(a1 + 264),
      2,
      a3,
      a1 + 288);
    v10 = _InterlockedAdd((volatile signed __int32 *)(a1 + 260), 0xFFFFFFFF) == 0;
    if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 256)) == 1 )
    {
      (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(a1 + 264) + 8LL))(
        *(_QWORD *)(a1 + 264),
        1,
        2147943623LL,
        a1 + 288);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 260), 0xFFFFFFFF) != 1 )
        return;
    }
    else if ( !v10 )
    {
      return;
    }
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(a1);
    return;
  }
  if ( (_DWORD)a2 == 1 && _InterlockedIncrement((volatile signed __int32 *)(a1 + 256)) == 1 )
  {
    v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(a1 + 264) + 8LL))(
           *(_QWORD *)(a1 + 264),
           a2,
           a3,
           a1 + 288);
    if ( v4 >= 0 && *(_BYTE *)(a1 + 297) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 280), 0xFFFFFFFF) == 1 )
        Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(
          a1,
          *(unsigned int *)(a1 + 284));
    }
    else
    {
      v5 = _InterlockedAdd((volatile signed __int32 *)(a1 + 260), 0xFFFFFFFF) == 0;
      if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 252)) == 1 )
        v5 = _InterlockedAdd((volatile signed __int32 *)(a1 + 260), 0xFFFFFFFF) == 0;
      v6 = *(_DWORD *)(a1 + 64);
      v11 = -2;
      _InterlockedCompareExchange(&v11, v6, -2);
      if ( v4 < 0 )
      {
        if ( v11 != 2 )
          Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostBroker::Cortana::SetHeyCortanaOptionAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(a1 + 8);
      }
      else if ( v11 || (v7 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 64), 1, 0), v7 != v11) )
      {
        _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 64), 1, 2);
      }
      if ( v5 )
      {
        v8 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 264);
        if ( v8 )
          (**v8)(v8, 1);
        v9 = *(_DWORD *)(a1 + 336);
        *(_QWORD *)(a1 + 264) = 0;
        if ( GetCurrentThreadId() != v9 )
          SHTaskPoolAllowThreadReuse();
        _InterlockedIncrement((volatile signed __int32 *)(a1 + 272));
        if ( *(int *)(a1 + 168) > 0 )
          Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostBroker::Cortana::SetHeyCortanaOptionAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(a1 + 8);
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion((signed __int32 *)(a1 + 8));
      }
    }
  }
}

```

## disassembly

```asm
0x180002e10  push    rbx
0x180002e12  push    rbp
0x180002e13  push    rsi
0x180002e14  push    rdi
0x180002e15  sub     rsp, 38h
0x180002e19  mov     rbx, rcx
0x180002e1c  cmp     edx, 2
0x180002e1f  jz      loc_180002F3D
0x180002e25  cmp     edx, 1
0x180002e28  jnz     loc_180002ECD
0x180002e2e  mov     edi, edx
0x180002e30  mov     eax, edx
0x180002e32  lock xadd [rcx+100h], eax
0x180002e3a  inc     eax
0x180002e3c  cmp     eax, edx
0x180002e3e  jnz     loc_180002ECD
0x180002e44  mov     rcx, [rcx+108h]
0x180002e4b  lea     r9, [rbx+120h]
0x180002e52  mov     rax, [rcx]
0x180002e55  mov     rax, [rax+8]
0x180002e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e5e  mov     edx, eax
0x180002e60  test    eax, eax
0x180002e62  js      short loc_180002E71
0x180002e64  cmp     byte ptr [rbx+129h], 0
0x180002e6b  jnz     loc_180002FDD
0x180002e71  lock add dword ptr [rbx+104h], 0FFFFFFFFh
0x180002e79  setz    bpl
0x180002e7d  mov     eax, edi
0x180002e7f  lock xadd [rbx+0FCh], eax
0x180002e87  inc     eax
0x180002e89  cmp     eax, edi
0x180002e8b  jz      short loc_180002ED6
0x180002e8d  mov     ecx, [rbx+40h]
0x180002e90  mov     [rsp+58h+arg_8], 0FFFFFFFEh
0x180002e98  mov     eax, [rsp+58h+arg_8]
0x180002e9c  lock cmpxchg [rsp+58h+arg_8], ecx
0x180002ea2  test    edx, edx
0x180002ea4  js      loc_180003005
0x180002eaa  cmp     [rsp+58h+arg_8], 0
0x180002eaf  jnz     short loc_180002EBE
0x180002eb1  xor     eax, eax
0x180002eb3  lock cmpxchg [rbx+40h], edi
0x180002eb8  cmp     eax, [rsp+58h+arg_8]
0x180002ebc  jz      short loc_180002EC8
0x180002ebe  mov     eax, 2
0x180002ec3  lock cmpxchg [rbx+40h], edi
0x180002ec8  test    bpl, bpl
0x180002ecb  jnz     short loc_180002EE4
0x180002ecd  add     rsp, 38h
0x180002ed1  pop     rdi
0x180002ed2  pop     rsi
0x180002ed3  pop     rbp
0x180002ed4  pop     rbx
0x180002ed5  retn
0x180002ed6  lock add dword ptr [rbx+104h], 0FFFFFFFFh
0x180002ede  setz    bpl
0x180002ee2  jmp     short loc_180002E8D
0x180002ee4  mov     rcx, [rbx+108h]
0x180002eeb  test    rcx, rcx
0x180002eee  jz      short loc_180002EFD
0x180002ef0  mov     rax, [rcx]
0x180002ef3  mov     edx, edi
0x180002ef5  mov     rax, [rax]
0x180002ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002efd  mov     edi, [rbx+150h]
0x180002f03  mov     qword ptr [rbx+108h], 0
0x180002f0e  call    cs:__imp_GetCurrentThreadId
0x180002f14  cmp     eax, edi
0x180002f16  jz      short loc_180002F1E
0x180002f18  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x180002f1e  lock inc dword ptr [rbx+110h]
0x180002f25  cmp     dword ptr [rbx+0A8h], 0
0x180002f2c  jg      loc_18000301E
0x180002f32  lea     rcx, [rbx+8]
0x180002f36  call    ?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)
0x180002f3b  jmp     short loc_180002ECD
0x180002f3d  mov     edi, 1
0x180002f42  mov     eax, edi
0x180002f44  lock xadd [rcx+0FCh], eax
0x180002f4c  inc     eax
0x180002f4e  cmp     eax, edi
0x180002f50  jnz     loc_180002ECD
0x180002f56  mov     rcx, [rcx+108h]
0x180002f5d  lea     r9, [rbx+120h]
0x180002f64  mov     edx, 2
0x180002f69  mov     rax, [rcx]
0x180002f6c  mov     rax, [rax+8]
0x180002f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f75  mov     esi, 0FFFFFFFFh
0x180002f7a  lock add [rbx+104h], esi
0x180002f81  setz    cl
0x180002f84  mov     eax, edi
0x180002f86  lock xadd [rbx+100h], eax
0x180002f8e  inc     eax
0x180002f90  cmp     eax, edi
0x180002f92  jnz     short loc_180002FC8
0x180002f94  mov     rcx, [rbx+108h]
0x180002f9b  lea     r9, [rbx+120h]
0x180002fa2  mov     r8d, 800704C7h
0x180002fa8  mov     edx, edi
0x180002faa  mov     rax, [rcx]
0x180002fad  mov     rax, [rax+8]
0x180002fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fb6  lock xadd [rbx+104h], esi
0x180002fbe  cmp     esi, edi
0x180002fc0  jnz     loc_180002ECD
0x180002fc6  jmp     short loc_180002FD0
0x180002fc8  test    cl, cl
0x180002fca  jz      loc_180002ECD
0x180002fd0  mov     rcx, rbx
0x180002fd3  call    ?_AfterComplete@?$AsyncOperation@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@VCHSTRINGResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)
0x180002fd8  jmp     loc_180002ECD
0x180002fdd  mov     esi, 0FFFFFFFFh
0x180002fe2  lock xadd [rbx+118h], esi
0x180002fea  cmp     esi, edi
0x180002fec  jnz     loc_180002ECD
0x180002ff2  mov     edx, [rbx+11Ch]
0x180002ff8  mov     rcx, rbx
0x180002ffb  call    ?_AfterExecute@?$AsyncOperation@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@VCHSTRINGResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXJ@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(long)
0x180003000  jmp     loc_180002ECD
0x180003005  cmp     [rsp+58h+arg_8], 2
0x18000300a  jz      loc_180002EC8
0x180003010  lea     rcx, [rbx+8]
0x180003014  call    ?TryTransitionToError@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?SetHeyCortanaOptionAsyncActionName@Cortana@CloudExperienceHostBroker@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostBroker::Cortana::SetHeyCortanaOptionAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x180003019  jmp     loc_180002EC8
0x18000301e  lea     rcx, [rbx+8]
0x180003022  call    ?UnlockProgressDelegate@?$AsyncBaseWithProgressFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncCausalityOptions@$1?SetHeyCortanaOptionAsyncActionName@Cortana@CloudExperienceHostBroker@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostBroker::Cortana::SetHeyCortanaOptionAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(void)
0x180003027  jmp     loc_180002F32
```
