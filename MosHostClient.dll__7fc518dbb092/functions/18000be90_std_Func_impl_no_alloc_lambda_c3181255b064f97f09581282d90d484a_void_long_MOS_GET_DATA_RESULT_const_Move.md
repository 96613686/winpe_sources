# std::_Func_impl_no_alloc__lambda_c3181255b064f97f09581282d90d484a__void_long_MOS_GET_DATA_RESULT_const_&_::_Move

- ea: `0x18000be90`
- end: `0x18000bebf`
- name: `std::_Func_impl_no_alloc__lambda_c3181255b064f97f09581282d90d484a__void_long_MOS_GET_DATA_RESULT_const_&_::_Move`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000be90`

## pseudocode

```c
_QWORD *__fastcall std::_Func_impl_no_alloc__lambda_c3181255b064f97f09581282d90d484a__void_long_MOS_GET_DATA_RESULT_const___::_Move(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v2; // rcx

  v2 = (_QWORD *)(a1 + 8);
  *a2 = off_180013170;
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
0x18000be90  lea     r8, [rdx+8]
0x18000be94  add     rcx, 8
0x18000be98  lea     rax, off_180013170
0x18000be9f  mov     [rdx], rax
0x18000bea2  mov     qword ptr [r8], 0
0x18000bea9  cmp     r8, rcx
0x18000beac  jz      short loc_18000BEBB
0x18000beae  mov     rax, [rcx]
0x18000beb1  mov     [r8], rax
0x18000beb4  mov     qword ptr [rcx], 0
0x18000bebb  mov     rax, rdx
0x18000bebe  retn
```
