# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x140005836`
- end: `0x14000587a`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: `void *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140001b44`
- `0x140001d18`
- `0x140001e78`
- `0x140005836`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  void *v4; // rax
  size_t v5; // rcx

  v3 = *(_QWORD *)(a2 + 104);
  *(_QWORD *)(a2 + 104) = v3;
  v4 = 0;
  v5 = v3 + 1;
  if ( v5 )
  {
    v4 = operator new(v5);
    if ( !v4 )
      std::_Xbad_alloc();
  }
  *(_QWORD *)(a2 + 120) = v4;
  return &loc_140001DA1;
}

```

## disassembly

```asm
0x140005836  mov     [rsp+arg_8], rdx
0x14000583b  push    rbp
0x14000583c  sub     rsp, 20h
0x140005840  mov     rbp, rdx
0x140005843  mov     rcx, [rbp+68h]
0x140005847  mov     [rbp+68h], rcx
0x14000584b  xor     eax, eax
0x14000584d  add     rcx, 1; Size
0x140005851  jz      short loc_140005868
0x140005853  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140005857  ja      short loc_140005863
0x140005859  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000585e  test    rax, rax
0x140005861  jnz     short loc_140005868
0x140005863  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140005868  mov     [rbp+78h], rax
0x14000586c  lea     rax, loc_140001DA1
0x140005873  add     rsp, 20h
0x140005877  pop     rbp
0x140005878  retn
```
