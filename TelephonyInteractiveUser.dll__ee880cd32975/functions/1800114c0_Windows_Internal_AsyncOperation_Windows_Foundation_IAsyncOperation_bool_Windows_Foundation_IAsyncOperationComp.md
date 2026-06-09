# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<uchar,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::put_Completed(Windows::Foundation::IAsyncOperationCompletedHandler<bool> *)

- ea: `0x1800114c0`
- end: `0x180011516`
- name: `?put_Completed@?$AsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@V?$CBasicResult@E$0A@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAU?$IAsyncOperationCompletedHandler@_N@Foundation@3@@Z`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000d600`
- `0x1800114c0`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<unsigned char,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::put_Completed(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbx
  unsigned int v4; // edi

  v2 = a1 - 176;
  if ( a1 != 176 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(a1 - 176);
  v4 = Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(
         v2,
         a2);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  return v4;
}

```

## disassembly

```asm
0x1800114c0  mov     [rsp+arg_10], rbx
0x1800114c5  push    rdi
0x1800114c6  sub     rsp, 20h
0x1800114ca  lea     rbx, [rcx-0B0h]
0x1800114d1  mov     rdi, rdx
0x1800114d4  test    rbx, rbx
0x1800114d7  jz      short loc_1800114E8
0x1800114d9  mov     rax, [rbx]
0x1800114dc  mov     rcx, rbx
0x1800114df  mov     rax, [rax+8]
0x1800114e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114e8  mov     rdx, rdi
0x1800114eb  mov     rcx, rbx
0x1800114ee  call    ?PutOnComplete@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAU?$IAsyncOperationCompletedHandler@_N@Foundation@3@@Z; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(Windows::Foundation::IAsyncOperationCompletedHandler<bool> *)
0x1800114f3  mov     edi, eax
0x1800114f5  test    rbx, rbx
0x1800114f8  jz      short loc_180011509
0x1800114fa  mov     rdx, [rbx]
0x1800114fd  mov     rcx, rbx
0x180011500  mov     rax, [rdx+10h]
0x180011504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011509  mov     rbx, [rsp+28h+arg_10]
0x18001150e  mov     eax, edi
0x180011510  add     rsp, 20h
0x180011514  pop     rdi
0x180011515  retn
```
