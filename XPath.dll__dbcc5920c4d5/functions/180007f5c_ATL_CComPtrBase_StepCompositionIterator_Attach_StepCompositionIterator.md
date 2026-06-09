# ATL::CComPtrBase<StepCompositionIterator>::Attach(StepCompositionIterator *)

- ea: `0x180007f5c`
- end: `0x180007f8e`
- name: `?Attach@?$CComPtrBase@VStepCompositionIterator@@@ATL@@QEAAXPEAVStepCompositionIterator@@@Z`
- size: `50`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008f04`
- `0x180009290`
- `0x1800096d8`
- `0x1800097cc`
- `0x180009d30`
- `0x180009ec0`
- `0x180009f24`
- `0x18000c8d0`

## callees

- `0x180007f5c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<StepCompositionIterator>::Attach(__int64 *a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 result; // rax

  v4 = *a1;
  if ( v4 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  *a1 = a2;
  return result;
}

```

## disassembly

```asm
0x180007f5c  mov     [rsp+arg_0], rbx
0x180007f61  push    rdi
0x180007f62  sub     rsp, 20h
0x180007f66  mov     rbx, rcx
0x180007f69  mov     rdi, rdx
0x180007f6c  mov     rcx, [rcx]
0x180007f6f  test    rcx, rcx
0x180007f72  jz      short loc_180007F80
0x180007f74  mov     rax, [rcx]
0x180007f77  mov     rax, [rax+10h]
0x180007f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f80  mov     [rbx], rdi
0x180007f83  mov     rbx, [rsp+28h+arg_0]
0x180007f88  add     rsp, 20h
0x180007f8c  pop     rdi
0x180007f8d  retn
```
