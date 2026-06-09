# Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::_scalar_deleting_destructor_

- ea: `0x180007900`
- end: `0x180007950`
- name: `Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::_scalar_deleting_destructor_`
- size: `80`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001984`
- `0x180007264`
- `0x180007900`
- `0x180019010`

## pseudocode

```c
_QWORD *__fastcall Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::_scalar_deleting_destructor_(
        _QWORD *Block,
        char a2)
{
  __int64 v4; // rcx

  v4 = Block[15];
  if ( v4 )
  {
    Block[15] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  Microsoft::WRL::Details::ImplementsHelper_Microsoft::WRL::RuntimeClassFlags_3__1_Microsoft::WRL::Details::ImplementsMarker_Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2______Microsoft::WRL::FtmBase_::_ImplementsHelper_Microsoft::WRL::RuntimeClassFlags_3__1_Microsoft::WRL::Details::ImplementsMarker_Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2______Microsoft::WRL::FtmBase_((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180007900  mov     [rsp+arg_0], rbx
0x180007905  push    rdi
0x180007906  sub     rsp, 20h
0x18000790a  mov     rbx, rcx
0x18000790d  mov     edi, edx
0x18000790f  mov     rcx, [rcx+78h]
0x180007913  test    rcx, rcx
0x180007916  jz      short loc_18000792C
0x180007918  mov     qword ptr [rbx+78h], 0
0x180007920  mov     rax, [rcx]
0x180007923  mov     rax, [rax+10h]
0x180007927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000792c  mov     rcx, rbx
0x18000792f  call    Microsoft__WRL__Details__ImplementsHelper_Microsoft__WRL__RuntimeClassFlags_3__1_Microsoft__WRL__Details__ImplementsMarker_Microsoft__WRL__AsyncBase_Windows__Foundation__IAsyncOperationCompletedHandler_bool__Microsoft__WRL__Details__Nil_1_Microsoft__WRL__AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2______Microsoft__WRL__FtmBase____ImplementsHelper_Microsoft__WRL__RuntimeClassFlags_3__1_Microsoft__WRL__Details__ImplementsMarker_Microsoft__WRL__AsyncBase_Windows__Foundation__IAsyncOperationCompletedHandler_bool__Microsoft__WRL__Details__Nil_1_Microsoft__WRL__AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2______Microsoft__WRL__FtmBase_
0x180007934  test    dil, 1
0x180007938  jz      short loc_180007942
0x18000793a  mov     rcx, rbx; Block
0x18000793d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007942  mov     rax, rbx
0x180007945  mov     rbx, [rsp+28h+arg_0]
0x18000794a  add     rsp, 20h
0x18000794e  pop     rdi
0x18000794f  retn
```
