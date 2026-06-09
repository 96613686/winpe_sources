# std::_Func_impl_no_alloc__lambda_c3181255b064f97f09581282d90d484a__void_long_MOS_GET_DATA_RESULT_const_&_::_Copy

- ea: `0x18000bd50`
- end: `0x18000bd87`
- name: `std::_Func_impl_no_alloc__lambda_c3181255b064f97f09581282d90d484a__void_long_MOS_GET_DATA_RESULT_const_&_::_Copy`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000bd50`

## pseudocode

```c
_QWORD *__fastcall std::_Func_impl_no_alloc__lambda_c3181255b064f97f09581282d90d484a__void_long_MOS_GET_DATA_RESULT_const___::_Copy(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v2; // r8
  signed __int32 v3; // eax

  *a2 = off_180013170;
  v2 = *(_QWORD *)(a1 + 8);
  a2[1] = v2;
  if ( v2 )
  {
    do
      v3 = *(_DWORD *)(v2 + 12);
    while ( v3 != 0x7FFFFFFF && v3 != _InterlockedCompareExchange((volatile signed __int32 *)(v2 + 12), v3 + 1, v3) );
  }
  return a2;
}

```

## disassembly

```asm
0x18000bd50  lea     rax, off_180013170
0x18000bd57  mov     [rdx], rax
0x18000bd5a  mov     r8, [rcx+8]
0x18000bd5e  mov     [rdx+8], r8
0x18000bd62  test    r8, r8
0x18000bd65  jz      short loc_18000BD83
0x18000bd67  mov     r9d, 7FFFFFFFh
0x18000bd6d  jmp     short loc_18000BD7A
0x18000bd6f  lea     ecx, [rax+1]
0x18000bd72  lock cmpxchg [r8+0Ch], ecx
0x18000bd78  jz      short loc_18000BD83
0x18000bd7a  mov     eax, [r8+0Ch]
0x18000bd7e  cmp     eax, r9d
0x18000bd81  jnz     short loc_18000BD6F
0x18000bd83  mov     rax, rdx
0x18000bd86  retn
```
