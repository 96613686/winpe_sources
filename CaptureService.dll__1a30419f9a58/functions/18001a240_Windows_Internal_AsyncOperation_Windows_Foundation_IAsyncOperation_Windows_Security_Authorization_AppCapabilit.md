# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::CBasicResult<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(Windows::Internal::AsyncStage,long)

- ea: `0x18001a240`
- end: `0x18001a357`
- name: `?_Run@?$AsyncOperation@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@23@V?$CBasicResult@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@$02@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXW4AsyncStage@23@J@Z`
- size: `279`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180019bc0`
- `0x180019bf0`
- `0x180019f60`

## callees

- `0x18001a140`
- `0x18001a198`
- `0x18001a240`
- `0x180022010`

## pseudocode

```c
void __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::CBasicResult<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rbp
  bool v5; // cl
  int v6; // eax
  int v7; // edx

  if ( (_DWORD)a2 == 2 )
  {
    if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 252)) != 1 )
      return;
    v4 = a1 + 288;
    (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(a1 + 264) + 8LL))(
      *(_QWORD *)(a1 + 264),
      a2,
      a3,
      a1 + 288);
    v5 = _InterlockedAdd((volatile signed __int32 *)(a1 + 260), 0xFFFFFFFF) == 0;
    if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 256)) == 1 )
    {
      (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(a1 + 264) + 8LL))(
        *(_QWORD *)(a1 + 264),
        1,
        2147943623LL,
        v4);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 260), 0xFFFFFFFF) != 1 )
        return;
    }
    else if ( !v5 )
    {
      return;
    }
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::CBasicResult<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(a1);
  }
  else if ( (_DWORD)a2 == 1 && _InterlockedIncrement((volatile signed __int32 *)(a1 + 256)) == 1 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(a1 + 264) + 8LL))(
           *(_QWORD *)(a1 + 264),
           1,
           a3,
           a1 + 288);
    if ( v6 >= 0 && *(_BYTE *)(a1 + 297) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 280), 0xFFFFFFFF) != 1 )
        return;
      v7 = *(_DWORD *)(a1 + 284);
    }
    else
    {
      v7 = v6;
    }
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::CBasicResult<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(
      (volatile signed __int32 *)a1,
      v7);
  }
}

```

## disassembly

```asm
0x18001a240  mov     [rsp+arg_0], rbx
0x18001a245  mov     [rsp+arg_8], rbp
0x18001a24a  push    rdi
0x18001a24b  sub     rsp, 30h
0x18001a24f  mov     rbx, rcx
0x18001a252  mov     edi, 1
0x18001a257  cmp     edx, 2
0x18001a25a  jnz     loc_18001A2E9
0x18001a260  mov     eax, edi
0x18001a262  lock xadd [rcx+0FCh], eax
0x18001a26a  add     eax, edi
0x18001a26c  cmp     eax, edi
0x18001a26e  jnz     loc_18001A347
0x18001a274  lea     rbp, [rcx+120h]
0x18001a27b  mov     rcx, [rcx+108h]
0x18001a282  mov     r9, rbp
0x18001a285  mov     rax, [rcx]
0x18001a288  mov     rax, [rax+8]
0x18001a28c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a291  lock add dword ptr [rbx+104h], 0FFFFFFFFh
0x18001a299  setz    cl
0x18001a29c  mov     eax, edi
0x18001a29e  lock xadd [rbx+100h], eax
0x18001a2a6  add     eax, edi
0x18001a2a8  cmp     eax, edi
0x18001a2aa  jnz     short loc_18001A2DB
0x18001a2ac  mov     rcx, [rbx+108h]
0x18001a2b3  mov     r9, rbp
0x18001a2b6  mov     r8d, 800704C7h
0x18001a2bc  mov     edx, edi
0x18001a2be  mov     rax, [rcx]
0x18001a2c1  mov     rax, [rax+8]
0x18001a2c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2ca  or      eax, 0FFFFFFFFh
0x18001a2cd  lock xadd [rbx+104h], eax
0x18001a2d5  cmp     eax, edi
0x18001a2d7  jnz     short loc_18001A347
0x18001a2d9  jmp     short loc_18001A2DF
0x18001a2db  test    cl, cl
0x18001a2dd  jz      short loc_18001A347
0x18001a2df  mov     rcx, rbx
0x18001a2e2  call    ?_AfterComplete@?$AsyncOperation@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@23@V?$CBasicResult@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@$02@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::CBasicResult<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)
0x18001a2e7  jmp     short loc_18001A347
0x18001a2e9  cmp     edx, edi
0x18001a2eb  jnz     short loc_18001A347
0x18001a2ed  mov     eax, edi
0x18001a2ef  lock xadd [rcx+100h], eax
0x18001a2f7  add     eax, edi
0x18001a2f9  cmp     eax, edi
0x18001a2fb  jnz     short loc_18001A347
0x18001a2fd  mov     rcx, [rcx+108h]
0x18001a304  lea     r9, [rbx+120h]
0x18001a30b  mov     edx, edi
0x18001a30d  mov     rax, [rcx]
0x18001a310  mov     rax, [rax+8]
0x18001a314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a319  test    eax, eax
0x18001a31b  js      short loc_18001A33D
0x18001a31d  cmp     byte ptr [rbx+129h], 0
0x18001a324  jz      short loc_18001A33D
0x18001a326  or      eax, 0FFFFFFFFh
0x18001a329  lock xadd [rbx+118h], eax
0x18001a331  cmp     eax, edi
0x18001a333  jnz     short loc_18001A347
0x18001a335  mov     edx, [rbx+11Ch]
0x18001a33b  jmp     short loc_18001A33F
0x18001a33d  mov     edx, eax
0x18001a33f  mov     rcx, rbx
0x18001a342  call    ?_AfterExecute@?$AsyncOperation@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@23@V?$CBasicResult@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@$02@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXJ@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::CBasicResult<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(long)
0x18001a347  mov     rbx, [rsp+38h+arg_0]
0x18001a34c  mov     rbp, [rsp+38h+arg_8]
0x18001a351  add     rsp, 30h
0x18001a355  pop     rdi
0x18001a356  retn
```
