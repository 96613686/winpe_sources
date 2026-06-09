# std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)

- ea: `0x140003ad4`
- end: `0x140003b2b`
- name: `??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z`
- size: `87`
- prototype: `_QWORD *__fastcall(size_t)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140003b34`
- `0x140003b64`
- `0x140003c10`
- `0x140003ddc`
- `0x14000923c`
- `0x1400092ec`
- `0x1400094ac`

## callees

- `0x140002250`
- `0x140003ad4`
- `0x1400076e8`

## pseudocode

```c
_QWORD *__fastcall std::_Allocate<16,std::_Default_allocate_traits>(size_t a1)
{
  _QWORD *result; // rax
  void *v2; // rax
  void *v3; // rcx

  if ( !a1 )
    return 0;
  if ( a1 < 0x1000 )
    return operator new(a1);
  if ( a1 + 39 < a1 )
    std::_Throw_bad_array_new_length();
  v2 = operator new(a1 + 39);
  v3 = v2;
  if ( !v2 )
    __fastfail(5u);
  result = (_QWORD *)(((unsigned __int64)v2 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(result - 1) = v3;
  return result;
}

```

## disassembly

```asm
0x140003ad4  sub     rsp, 28h
0x140003ad8  test    rcx, rcx
0x140003adb  jnz     short loc_140003AE4
0x140003add  xor     eax, eax
0x140003adf  add     rsp, 28h
0x140003ae3  retn
0x140003ae4  cmp     rcx, 1000h
0x140003aeb  jb      short loc_140003B1C
0x140003aed  lea     rax, [rcx+27h]
0x140003af1  cmp     rax, rcx
0x140003af4  jbe     short loc_140003B25
0x140003af6  mov     rcx, rax; Size
0x140003af9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140003afe  mov     rcx, rax
0x140003b01  test    rax, rax
0x140003b04  jnz     short loc_140003B0B
0x140003b06  lea     ecx, [rax+5]; Size
0x140003b09  int     29h; Win8: RtlFailFast(ecx)
0x140003b0b  add     rax, 27h ; '''
0x140003b0f  and     rax, 0FFFFFFFFFFFFFFE0h
0x140003b13  mov     [rax-8], rcx
0x140003b17  add     rsp, 28h
0x140003b1b  retn
0x140003b1c  add     rsp, 28h
0x140003b20  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140003b25  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
