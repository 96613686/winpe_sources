# _std::basic_string_char_std::char_traits_char__std::allocator_char___STL70_::_Copy_::_1_::catch$1

- ea: `0x180009682`
- end: `0x1800096e7`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___STL70_::_Copy_::_1_::catch$1`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001048`
- `0x180001444`
- `0x18000227c`
- `0x180003140`
- `0x180009682`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall std::basic_string_char_std::char_traits_char__std::allocator_char___STL70_::_Copy_::_1_::catch_1(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v3; // rcx
  size_t v4; // rcx

  v3 = a2[19];
  a2[19] = v3;
  v4 = v3 + 1;
  if ( v4 && !(0xFFFFFFFFFFFFFFFFuLL / v4) )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)(a2 + 8), 0);
    throw (std::bad_alloc *)(a2 + 8);
  }
  a2[21] = operator new(v4);
  return &loc_1800014D5;
}

```

## disassembly

```asm
0x180009682  mov     [rsp+arg_8], rdx
0x180009687  push    rbp
0x180009688  sub     rsp, 20h
0x18000968c  mov     rbp, rdx
0x18000968f  mov     rcx, [rbp+98h]
0x180009696  mov     [rbp+98h], rcx
0x18000969d  add     rcx, 1; Size
0x1800096a1  jz      short loc_1800096CD
0x1800096a3  xor     edx, edx
0x1800096a5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800096a9  div     rcx
0x1800096ac  cmp     rax, 1
0x1800096b0  jnb     short loc_1800096CD
0x1800096b2  xor     edx, edx; char *
0x1800096b4  lea     rcx, [rbp+40h]; this
0x1800096b8  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x1800096bd  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800096c4  lea     rcx, [rbp+40h]; pExceptionObject
0x1800096c8  call    _CxxThrowException_0
0x1800096cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800096d2  mov     [rbp+0A8h], rax
0x1800096d9  lea     rax, loc_1800014D5
0x1800096e0  add     rsp, 20h
0x1800096e4  pop     rbp
0x1800096e5  retn
```
