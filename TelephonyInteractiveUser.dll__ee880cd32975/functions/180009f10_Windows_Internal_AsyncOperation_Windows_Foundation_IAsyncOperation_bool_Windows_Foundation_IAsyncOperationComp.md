# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<uchar,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180009f10`
- end: `0x180009f4a`
- name: `?FireCompletion@?$AsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@V?$CBasicResult@E$0A@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180009f10`
- `0x180009f50`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<unsigned char,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  unsigned int v1; // edx

  v1 = 0;
  if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 264)) == 2 )
    return (unsigned int)Windows::Internal::ComTaskPoolHandler::FireCompletion(
                           (Windows::Internal::ComTaskPoolHandler *)(a1 + 208),
                           (struct Windows::Internal::IAsyncFireCompletion *)((a1 + 208)
                                                                            & ((unsigned __int128)-(__int128)(unsigned __int64)(a1 - 8) >> 64)));
  return v1;
}

```

## disassembly

```asm
0x180009f10  sub     rsp, 28h
0x180009f14  xor     edx, edx
0x180009f16  lea     eax, [rdx+1]
0x180009f19  lock xadd [rcx+108h], eax
0x180009f21  inc     eax
0x180009f23  cmp     eax, 2
0x180009f26  jnz     short loc_180009F43
0x180009f28  lea     rax, [rcx-8]
0x180009f2c  add     rcx, 0D0h; this
0x180009f33  neg     rax
0x180009f36  sbb     rdx, rdx
0x180009f39  and     rdx, rcx; struct Windows::Internal::IAsyncFireCompletion *
0x180009f3c  call    ?FireCompletion@ComTaskPoolHandler@Internal@Windows@@QEAAJPEAUIAsyncFireCompletion@23@@Z; Windows::Internal::ComTaskPoolHandler::FireCompletion(Windows::Internal::IAsyncFireCompletion *)
0x180009f41  mov     edx, eax
0x180009f43  mov     eax, edx
0x180009f45  add     rsp, 28h
0x180009f49  retn
```
