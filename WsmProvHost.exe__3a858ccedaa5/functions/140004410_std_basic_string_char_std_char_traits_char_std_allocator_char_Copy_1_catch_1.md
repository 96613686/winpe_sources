# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x140004410`
- end: `0x140004454`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: `void *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140001208`
- `0x140001368`
- `0x140002d50`
- `0x140004410`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rcx

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
  return &loc_140001291;
}

```

## disassembly

```asm
0x140004410  mov     [rsp+arg_8], rdx
0x140004415  push    rbp
0x140004416  sub     rsp, 20h
0x14000441a  mov     rbp, rdx
0x14000441d  mov     rcx, [rbp+68h]
0x140004421  mov     [rbp+68h], rcx
0x140004425  xor     eax, eax
0x140004427  add     rcx, 1; unsigned __int64
0x14000442b  jz      short loc_140004442
0x14000442d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140004431  ja      short loc_14000443D
0x140004433  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140004438  test    rax, rax
0x14000443b  jnz     short loc_140004442
0x14000443d  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140004442  mov     [rbp+78h], rax
0x140004446  lea     rax, loc_140001291
0x14000444d  add     rsp, 20h
0x140004451  pop     rbp
0x140004452  retn
```
