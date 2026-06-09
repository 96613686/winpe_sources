# std::_Func_impl_no_alloc__lambda_76c43bbe81a798c7cbe5d5cf5684e32d__void_long_MOS_GET_DATA_RESULT_const_&_::_Move

- ea: `0x18000be50`
- end: `0x18000be7f`
- name: `std::_Func_impl_no_alloc__lambda_76c43bbe81a798c7cbe5d5cf5684e32d__void_long_MOS_GET_DATA_RESULT_const_&_::_Move`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000be50`

## pseudocode

```c
_QWORD *__fastcall std::_Func_impl_no_alloc__lambda_76c43bbe81a798c7cbe5d5cf5684e32d__void_long_MOS_GET_DATA_RESULT_const___::_Move(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v2; // rcx

  v2 = (_QWORD *)(a1 + 8);
  *a2 = off_1800131A0;
  a2[1] = 0;
  if ( a2 + 1 != v2 )
  {
    a2[1] = *v2;
    *v2 = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x18000be50  lea     r8, [rdx+8]
0x18000be54  add     rcx, 8
0x18000be58  lea     rax, off_1800131A0
0x18000be5f  mov     [rdx], rax
0x18000be62  mov     qword ptr [r8], 0
0x18000be69  cmp     r8, rcx
0x18000be6c  jz      short loc_18000BE7B
0x18000be6e  mov     rax, [rcx]
0x18000be71  mov     [r8], rax
0x18000be74  mov     qword ptr [rcx], 0
0x18000be7b  mov     rax, rdx
0x18000be7e  retn
```
