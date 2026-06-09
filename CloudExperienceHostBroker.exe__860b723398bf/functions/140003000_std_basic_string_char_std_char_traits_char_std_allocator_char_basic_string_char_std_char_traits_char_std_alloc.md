# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::basic_string<char,std::char_traits<char>,std::allocator<char>>(char const *)

- ea: `0x140003000`
- end: `0x14000302a`
- name: `??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD@Z`
- size: `42`
- prototype: `_QWORD *__fastcall(_QWORD *, void *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140005e50`
- `0x140005e90`
- `0x140005ed0`

## callees

- `0x140005b0c`

## pseudocode

```c
_QWORD *__fastcall std::string::string(_QWORD *a1, void *a2)
{
  a1[3] = 15;
  a1[2] = 0;
  *(_BYTE *)a1 = 0;
  std::string::assign(a1, a2);
  return a1;
}

```

## disassembly

```asm
0x140003000  push    rbx
0x140003002  sub     rsp, 20h
0x140003006  mov     qword ptr [rcx+18h], 0Fh
0x14000300e  mov     rbx, rcx
0x140003011  mov     qword ptr [rcx+10h], 0
0x140003019  mov     byte ptr [rcx], 0
0x14000301c  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD@Z; std::string::assign(char const *)
0x140003021  mov     rax, rbx
0x140003024  add     rsp, 20h
0x140003028  pop     rbx
0x140003029  retn
```
