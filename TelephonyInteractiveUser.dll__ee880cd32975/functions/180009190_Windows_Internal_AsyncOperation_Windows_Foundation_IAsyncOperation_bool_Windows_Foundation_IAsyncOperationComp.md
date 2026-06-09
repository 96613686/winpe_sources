# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<uchar,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Dismiss(void)

- ea: `0x180009190`
- end: `0x1800091b5`
- name: `?Dismiss@?$AsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@V?$CBasicResult@E$0A@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAXXZ`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180009190`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<unsigned char,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Dismiss(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 104) )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 - 184) + 152LL))(a1 - 184);
  return result;
}

```

## disassembly

```asm
0x180009190  sub     rsp, 28h
0x180009194  cmp     byte ptr [rcx+68h], 0
0x180009198  jz      short loc_1800091B0
0x18000919a  add     rcx, 0FFFFFFFFFFFFFF48h
0x1800091a1  mov     rax, [rcx]
0x1800091a4  mov     rax, [rax+98h]
0x1800091ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091b0  add     rsp, 28h
0x1800091b4  retn
```
