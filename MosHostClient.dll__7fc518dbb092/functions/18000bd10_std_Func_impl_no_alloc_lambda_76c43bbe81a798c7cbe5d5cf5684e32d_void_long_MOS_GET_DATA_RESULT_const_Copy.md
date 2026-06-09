# std::_Func_impl_no_alloc__lambda_76c43bbe81a798c7cbe5d5cf5684e32d__void_long_MOS_GET_DATA_RESULT_const_&_::_Copy

- ea: `0x18000bd10`
- end: `0x18000bd47`
- name: `std::_Func_impl_no_alloc__lambda_76c43bbe81a798c7cbe5d5cf5684e32d__void_long_MOS_GET_DATA_RESULT_const_&_::_Copy`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000bd10`

## pseudocode

```c
_QWORD *__fastcall std::_Func_impl_no_alloc__lambda_76c43bbe81a798c7cbe5d5cf5684e32d__void_long_MOS_GET_DATA_RESULT_const___::_Copy(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v2; // r8
  signed __int32 v3; // eax

  *a2 = off_1800131A0;
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
0x18000bd10  lea     rax, off_1800131A0
0x18000bd17  mov     [rdx], rax
0x18000bd1a  mov     r8, [rcx+8]
0x18000bd1e  mov     [rdx+8], r8
0x18000bd22  test    r8, r8
0x18000bd25  jz      short loc_18000BD43
0x18000bd27  mov     r9d, 7FFFFFFFh
0x18000bd2d  jmp     short loc_18000BD3A
0x18000bd2f  lea     ecx, [rax+1]
0x18000bd32  lock cmpxchg [r8+0Ch], ecx
0x18000bd38  jz      short loc_18000BD43
0x18000bd3a  mov     eax, [r8+0Ch]
0x18000bd3e  cmp     eax, r9d
0x18000bd41  jnz     short loc_18000BD2F
0x18000bd43  mov     rax, rdx
0x18000bd46  retn
```
