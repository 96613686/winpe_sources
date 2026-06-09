# _std::basic_string_char_std::char_traits_char__std::allocator_static_char___STL70_::_Copy_::_1_::catch$2

- ea: `0x18000fd38`
- end: `0x18000fda0`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_static_char___STL70_::_Copy_::_1_::catch$2`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001c0c`
- `0x18000310c`
- `0x18000e61c`
- `0x18000fd38`

## pseudocode

```c
__int64 __fastcall std::basic_string_char_std::char_traits_char__std::allocator_static_char___STL70_::_Copy_::_1_::catch_2(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v3; // rcx
  unsigned __int64 v4; // rcx

  v3 = a2[17];
  a2[17] = v3;
  v4 = v3 + 1;
  if ( v4 && !(0xFFFFFFFFFFFFFFFFuLL / v4) )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)(a2 + 7), 0);
    throw (std::bad_alloc *)(a2 + 7);
  }
  a2[19] = MmAllocate(v4);
  return 0;
}

```

## disassembly

```asm
0x18000fd38  mov     [rsp+arg_8], rdx
0x18000fd3d  push    rbp
0x18000fd3e  sub     rsp, 20h
0x18000fd42  mov     rbp, rdx
0x18000fd45  mov     rcx, [rbp+88h]
0x18000fd4c  mov     [rbp+88h], rcx
0x18000fd53  add     rcx, 1; unsigned __int64
0x18000fd57  jz      short loc_18000FD83
0x18000fd59  xor     edx, edx
0x18000fd5b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fd5f  div     rcx
0x18000fd62  cmp     rax, 1
0x18000fd66  jnb     short loc_18000FD83
0x18000fd68  xor     edx, edx; char *
0x18000fd6a  lea     rcx, [rbp+38h]; this
0x18000fd6e  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x18000fd73  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000fd7a  lea     rcx, [rbp+38h]; pExceptionObject
0x18000fd7e  call    _CxxThrowException_0
0x18000fd83  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18000fd88  mov     [rbp+98h], rax
0x18000fd8f  mov     rax, 0
0x18000fd99  add     rsp, 20h
0x18000fd9d  pop     rbp
0x18000fd9e  retn
```
