# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<uchar,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::InvokeFireCompletion(void)

- ea: `0x18000c900`
- end: `0x18000c957`
- name: `?InvokeFireCompletion@?$AsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@V?$CBasicResult@E$0A@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180009bc0`
- `0x18000c900`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<unsigned char,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::InvokeFireCompletion(
        __int64 a1)
{
  __int64 v1; // rbx
  __int64 v2; // rcx
  signed __int32 v4[10]; // [rsp+0h] [rbp-28h] BYREF

  v1 = a1 - 208;
  if ( *(int *)(a1 - 208 + 160) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 160), 0xFFFFFFFF) == 1 )
  {
    _InterlockedOr(v4, 0);
    v2 = *(_QWORD *)(v1 + 144);
    *(_QWORD *)(v1 + 144) = 0;
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(v1);
}

```

## disassembly

```asm
0x18000c900  push    rbx
0x18000c902  sub     rsp, 20h
0x18000c906  lea     rbx, [rcx-0D0h]
0x18000c90d  xor     edx, edx
0x18000c90f  cmp     [rbx+0A0h], edx
0x18000c915  jle     short loc_18000C94A
0x18000c917  or      eax, 0FFFFFFFFh
0x18000c91a  lock xadd [rbx+0A0h], eax
0x18000c922  cmp     eax, 1
0x18000c925  jnz     short loc_18000C94A
0x18000c927  lock or [rsp+28h+var_28], edx
0x18000c92b  mov     rcx, [rbx+90h]
0x18000c932  mov     [rbx+90h], rdx
0x18000c939  test    rcx, rcx
0x18000c93c  jz      short loc_18000C94A
0x18000c93e  mov     rax, [rcx]
0x18000c941  mov     rax, [rax+10h]
0x18000c945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c94a  mov     rcx, rbx
0x18000c94d  add     rsp, 20h
0x18000c951  pop     rbx
0x18000c952  jmp     ?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)
```
