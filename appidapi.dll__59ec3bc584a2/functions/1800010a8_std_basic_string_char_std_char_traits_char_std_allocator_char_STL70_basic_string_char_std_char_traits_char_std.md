# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>(char const *)

- ea: `0x1800010a8`
- end: `0x1800010dd`
- name: `??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800016a4`
- `0x180001700`

## callees

- `0x1800010a8`
- `0x180001850`

## pseudocode

```c
__int64 __fastcall std::string::string(__int64 a1, __int64 a2)
{
  __int64 v3; // r8

  *(_QWORD *)(a1 + 32) = 15;
  *(_QWORD *)(a1 + 24) = 0;
  *(_BYTE *)(a1 + 8) = 0;
  v3 = -1;
  do
    ++v3;
  while ( *(_BYTE *)(a2 + v3) );
  std::string::assign();
  return a1;
}

```

## disassembly

```asm
0x1800010a8  push    rbx
0x1800010aa  sub     rsp, 20h
0x1800010ae  xor     eax, eax
0x1800010b0  mov     qword ptr [rcx+20h], 0Fh
0x1800010b8  mov     [rcx+18h], rax
0x1800010bc  mov     rbx, rcx
0x1800010bf  mov     [rcx+8], al
0x1800010c2  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800010c6  inc     r8
0x1800010c9  cmp     [rdx+r8], al
0x1800010cd  jnz     short loc_1800010C6
0x1800010cf  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@PEBD_K@Z; std::string::assign(char const *,unsigned __int64)
0x1800010d4  mov     rax, rbx
0x1800010d7  add     rsp, 20h
0x1800010db  pop     rbx
0x1800010dc  retn
```
