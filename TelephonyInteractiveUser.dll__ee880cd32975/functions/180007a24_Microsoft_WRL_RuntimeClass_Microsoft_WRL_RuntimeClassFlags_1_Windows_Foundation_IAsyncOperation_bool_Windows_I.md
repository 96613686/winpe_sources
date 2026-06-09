# Microsoft::WRL::RuntimeClass_Microsoft::WRL::RuntimeClassFlags_1__Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____::_scalar_deleting_destructor_

- ea: `0x180007a24`
- end: `0x180007a53`
- name: `Microsoft::WRL::RuntimeClass_Microsoft::WRL::RuntimeClassFlags_1__Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____::_scalar_deleting_destructor_`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180007a60`

## callees

- `0x180001984`
- `0x180007438`
- `0x180007a24`

## pseudocode

```c
void *__fastcall Microsoft::WRL::RuntimeClass_Microsoft::WRL::RuntimeClassFlags_1__Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____::_scalar_deleting_destructor_(
        void *Block,
        char a2)
{
  Microsoft::WRL::Details::RuntimeClassImpl_Microsoft::WRL::RuntimeClassFlags_1__1_1_0_Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____::_RuntimeClassImpl_Microsoft::WRL::RuntimeClassFlags_1__1_1_0_Windows::Foundation::IAsyncOperation_bool__Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180007a24  mov     [rsp+arg_0], rbx
0x180007a29  push    rdi
0x180007a2a  sub     rsp, 20h
0x180007a2e  mov     ebx, edx
0x180007a30  mov     rdi, rcx
0x180007a33  call    Microsoft__WRL__Details__RuntimeClassImpl_Microsoft__WRL__RuntimeClassFlags_1__1_1_0_Windows__Foundation__IAsyncOperation_bool__Windows__Internal__AsyncBaseFTM_Windows__Foundation__IAsyncOperationCompletedHandler_bool__1_Microsoft__WRL__AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2________RuntimeClassImpl_Microsoft__WRL__RuntimeClassFlags_1__1_1_0_Windows__Foundation__IAsyncOperation_bool__Windows__Internal__AsyncBaseFTM_Windows__Foundation__IAsyncOperationCompletedHandler_bool__1_Microsoft__WRL__AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____
0x180007a38  test    bl, 1
0x180007a3b  jz      short loc_180007A45
0x180007a3d  mov     rcx, rdi; Block
0x180007a40  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007a45  mov     rbx, [rsp+28h+arg_0]
0x180007a4a  mov     rax, rdi
0x180007a4d  add     rsp, 20h
0x180007a51  pop     rdi
0x180007a52  retn
```
