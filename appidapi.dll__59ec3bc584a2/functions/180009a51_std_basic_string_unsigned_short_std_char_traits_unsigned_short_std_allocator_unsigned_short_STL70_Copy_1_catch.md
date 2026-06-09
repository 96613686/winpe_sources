# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___STL70_::_Copy_::_1_::catch$1

- ea: `0x180009a51`
- end: `0x180009abc`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___STL70_::_Copy_::_1_::catch$1`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001048`
- `0x18000227c`
- `0x180003140`
- `0x180009a51`

## pseudocode

```c
__int64 __fastcall std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___STL70_::_Copy_::_1_::catch_1(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v3; // rcx
  unsigned __int64 v4; // rcx

  v3 = a2[19];
  a2[19] = v3;
  v4 = v3 + 1;
  if ( v4 && 0xFFFFFFFFFFFFFFFFuLL / v4 < 2 )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)(a2 + 7), 0);
    throw (std::bad_alloc *)(a2 + 7);
  }
  a2[21] = operator new(2 * v4);
  return 0;
}

```

## disassembly

```asm
0x180009a51  mov     [rsp+arg_8], rdx
0x180009a56  push    rbp
0x180009a57  sub     rsp, 20h
0x180009a5b  mov     rbp, rdx
0x180009a5e  mov     rcx, [rbp+98h]
0x180009a65  mov     [rbp+98h], rcx
0x180009a6c  add     rcx, 1
0x180009a70  jz      short loc_180009A9C
0x180009a72  xor     edx, edx
0x180009a74  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009a78  div     rcx
0x180009a7b  cmp     rax, 2
0x180009a7f  jnb     short loc_180009A9C
0x180009a81  xor     edx, edx; char *
0x180009a83  lea     rcx, [rbp+38h]; this
0x180009a87  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x180009a8c  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180009a93  lea     rcx, [rbp+38h]; pExceptionObject
0x180009a97  call    _CxxThrowException_0
0x180009a9c  add     rcx, rcx; Size
0x180009a9f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009aa4  mov     [rbp+0A8h], rax
0x180009aab  mov     rax, 0
0x180009ab5  add     rsp, 20h
0x180009ab9  pop     rbp
0x180009aba  retn
```
