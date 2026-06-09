# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::basic_string<char,std::char_traits<char>,std::allocator<char>>(char const *)

- ea: `0x180002c38`
- end: `0x180002c76`
- name: `??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD@Z`
- size: `62`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180006440`
- `0x180006480`
- `0x1800064c0`

## callees

- `0x180002c38`
- `0x180006004`

## pseudocode

```c
_QWORD *__fastcall std::string::string(_QWORD *a1, _BYTE *a2)
{
  size_t v3; // r8

  a1[3] = 15;
  a1[2] = 0;
  *(_BYTE *)a1 = 0;
  if ( *a2 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a2[v3] );
  }
  else
  {
    v3 = 0;
  }
  std::string::assign(a1, a2, v3);
  return a1;
}

```

## disassembly

```asm
0x180002c38  push    rbx
0x180002c3a  sub     rsp, 20h
0x180002c3e  xor     eax, eax
0x180002c40  mov     qword ptr [rcx+18h], 0Fh
0x180002c48  mov     [rcx+10h], rax
0x180002c4c  mov     rbx, rcx
0x180002c4f  mov     [rcx], al
0x180002c51  cmp     [rdx], al
0x180002c53  jnz     short loc_180002C5A
0x180002c55  mov     r8d, eax
0x180002c58  jmp     short loc_180002C67
0x180002c5a  or      r8, 0FFFFFFFFFFFFFFFFh
0x180002c5e  inc     r8; Size
0x180002c61  cmp     [rdx+r8], al
0x180002c65  jnz     short loc_180002C5E
0x180002c67  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z; std::string::assign(char const *,unsigned __int64)
0x180002c6c  mov     rax, rbx
0x180002c6f  add     rsp, 20h
0x180002c73  pop     rbx
0x180002c74  retn
```
