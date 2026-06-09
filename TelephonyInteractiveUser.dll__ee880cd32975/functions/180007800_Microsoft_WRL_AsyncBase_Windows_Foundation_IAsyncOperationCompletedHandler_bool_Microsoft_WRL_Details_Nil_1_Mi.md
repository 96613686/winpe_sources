# Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::_scalar_deleting_destructor_

- ea: `0x180007800`
- end: `0x18000787a`
- name: `Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::_scalar_deleting_destructor_`
- size: `122`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001984`
- `0x180007800`
- `0x18000f588`
- `0x180019010`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::_scalar_deleting_destructor_(
        _DWORD *Block,
        char a2)
{
  bool v2; // zf
  __int64 v5; // rcx
  __int64 v6; // rcx

  v2 = Block[4] == 0;
  *(_QWORD *)Block = &off_18001B648;
  if ( v2 )
    Microsoft::WRL::AsyncBase_Windows::Foundation::IAsyncOperationCompletedHandler_bool__Microsoft::WRL::Details::Nil_1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::TraceOperationComplete((__int64)Block);
  v5 = *((_QWORD *)Block + 6);
  if ( v5 )
  {
    *((_QWORD *)Block + 6) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  v6 = *((_QWORD *)Block + 3);
  if ( v6 )
  {
    *((_QWORD *)Block + 3) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180007800  mov     [rsp+arg_0], rbx
0x180007805  push    rdi
0x180007806  sub     rsp, 20h
0x18000780a  cmp     dword ptr [rcx+10h], 0
0x18000780e  lea     rax, off_18001B648
0x180007815  mov     [rcx], rax
0x180007818  mov     edi, edx
0x18000781a  mov     rbx, rcx
0x18000781d  jnz     short loc_180007824
0x18000781f  call    Microsoft__WRL__AsyncBase_Windows__Foundation__IAsyncOperationCompletedHandler_bool__Microsoft__WRL__Details__Nil_1_Microsoft__WRL__AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2_____TraceOperationComplete
0x180007824  mov     rcx, [rbx+30h]
0x180007828  test    rcx, rcx
0x18000782b  jz      short loc_180007841
0x18000782d  mov     qword ptr [rbx+30h], 0
0x180007835  mov     rax, [rcx]
0x180007838  mov     rax, [rax+10h]
0x18000783c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007841  mov     rcx, [rbx+18h]
0x180007845  test    rcx, rcx
0x180007848  jz      short loc_18000785E
0x18000784a  mov     qword ptr [rbx+18h], 0
0x180007852  mov     rax, [rcx]
0x180007855  mov     rax, [rax+10h]
0x180007859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000785e  test    dil, 1
0x180007862  jz      short loc_18000786C
0x180007864  mov     rcx, rbx; Block
0x180007867  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000786c  mov     rax, rbx
0x18000786f  mov     rbx, [rsp+28h+arg_0]
0x180007874  add     rsp, 20h
0x180007878  pop     rdi
0x180007879  retn
```
