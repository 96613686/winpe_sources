# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>(char const *)

- ea: `0x14000cf6c`
- end: `0x14000cfa1`
- name: `??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z`
- size: `53`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140002754`
- `0x1400027b0`
- `0x14000f6b4`
- `0x14000fe40`

## callees

- `0x14000cf6c`
- `0x14000fb30`

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
0x14000cf6c  push    rbx
0x14000cf6e  sub     rsp, 20h
0x14000cf72  xor     eax, eax
0x14000cf74  mov     qword ptr [rcx+20h], 0Fh
0x14000cf7c  mov     [rcx+18h], rax
0x14000cf80  mov     rbx, rcx
0x14000cf83  mov     [rcx+8], al
0x14000cf86  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000cf8a  inc     r8
0x14000cf8d  cmp     [rdx+r8], al
0x14000cf91  jnz     short loc_14000CF8A
0x14000cf93  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@PEBD_K@Z; std::string::assign(char const *,unsigned __int64)
0x14000cf98  mov     rax, rbx
0x14000cf9b  add     rsp, 20h
0x14000cf9f  pop     rbx
0x14000cfa0  retn
```
