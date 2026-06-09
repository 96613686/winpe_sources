# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Graphics::Capture::Server::ICapturableItem>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(Windows::Internal::AsyncStage,long)

- ea: `0x180017c6c`
- end: `0x180017d83`
- name: `?_Run@?$AsyncOperation@U?$IAsyncOperation@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@23@V?$CMarshaledInterfaceResult@UICapturableItem@Server@Capture@Graphics@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXW4AsyncStage@23@J@Z`
- size: `279`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180012d20`
- `0x180012e30`
- `0x180014870`

## callees

- `0x18001791c`
- `0x180017974`
- `0x180017c6c`
- `0x180022010`

## pseudocode

```c
void __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Graphics::Capture::Server::ICapturableItem>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(
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
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Graphics::Capture::Server::ICapturableItem>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(a1);
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
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Graphics::Capture::Server::ICapturableItem>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(
      (volatile signed __int32 *)a1,
      v7);
  }
}

```

## disassembly

```asm
0x180017c6c  mov     [rsp+arg_0], rbx
0x180017c71  mov     [rsp+arg_8], rbp
0x180017c76  push    rdi
0x180017c77  sub     rsp, 30h
0x180017c7b  mov     rbx, rcx
0x180017c7e  mov     edi, 1
0x180017c83  cmp     edx, 2
0x180017c86  jnz     loc_180017D15
0x180017c8c  mov     eax, edi
0x180017c8e  lock xadd [rcx+0FCh], eax
0x180017c96  add     eax, edi
0x180017c98  cmp     eax, edi
0x180017c9a  jnz     loc_180017D73
0x180017ca0  lea     rbp, [rcx+120h]
0x180017ca7  mov     rcx, [rcx+108h]
0x180017cae  mov     r9, rbp
0x180017cb1  mov     rax, [rcx]
0x180017cb4  mov     rax, [rax+8]
0x180017cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cbd  lock add dword ptr [rbx+104h], 0FFFFFFFFh
0x180017cc5  setz    cl
0x180017cc8  mov     eax, edi
0x180017cca  lock xadd [rbx+100h], eax
0x180017cd2  add     eax, edi
0x180017cd4  cmp     eax, edi
0x180017cd6  jnz     short loc_180017D07
0x180017cd8  mov     rcx, [rbx+108h]
0x180017cdf  mov     r9, rbp
0x180017ce2  mov     r8d, 800704C7h
0x180017ce8  mov     edx, edi
0x180017cea  mov     rax, [rcx]
0x180017ced  mov     rax, [rax+8]
0x180017cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cf6  or      eax, 0FFFFFFFFh
0x180017cf9  lock xadd [rbx+104h], eax
0x180017d01  cmp     eax, edi
0x180017d03  jnz     short loc_180017D73
0x180017d05  jmp     short loc_180017D0B
0x180017d07  test    cl, cl
0x180017d09  jz      short loc_180017D73
0x180017d0b  mov     rcx, rbx
0x180017d0e  call    ?_AfterComplete@?$AsyncOperation@U?$IAsyncOperation@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@23@V?$CMarshaledInterfaceResult@UICapturableItem@Server@Capture@Graphics@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Graphics::Capture::Server::ICapturableItem>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)
0x180017d13  jmp     short loc_180017D73
0x180017d15  cmp     edx, edi
0x180017d17  jnz     short loc_180017D73
0x180017d19  mov     eax, edi
0x180017d1b  lock xadd [rcx+100h], eax
0x180017d23  add     eax, edi
0x180017d25  cmp     eax, edi
0x180017d27  jnz     short loc_180017D73
0x180017d29  mov     rcx, [rcx+108h]
0x180017d30  lea     r9, [rbx+120h]
0x180017d37  mov     edx, edi
0x180017d39  mov     rax, [rcx]
0x180017d3c  mov     rax, [rax+8]
0x180017d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d45  test    eax, eax
0x180017d47  js      short loc_180017D69
0x180017d49  cmp     byte ptr [rbx+129h], 0
0x180017d50  jz      short loc_180017D69
0x180017d52  or      eax, 0FFFFFFFFh
0x180017d55  lock xadd [rbx+118h], eax
0x180017d5d  cmp     eax, edi
0x180017d5f  jnz     short loc_180017D73
0x180017d61  mov     edx, [rbx+11Ch]
0x180017d67  jmp     short loc_180017D6B
0x180017d69  mov     edx, eax
0x180017d6b  mov     rcx, rbx
0x180017d6e  call    ?_AfterExecute@?$AsyncOperation@U?$IAsyncOperation@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@23@V?$CMarshaledInterfaceResult@UICapturableItem@Server@Capture@Graphics@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXJ@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Graphics::Capture::Server::ICapturableItem>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(long)
0x180017d73  mov     rbx, [rsp+38h+arg_0]
0x180017d78  mov     rbp, [rsp+38h+arg_8]
0x180017d7d  add     rsp, 30h
0x180017d81  pop     rdi
0x180017d82  retn
```
