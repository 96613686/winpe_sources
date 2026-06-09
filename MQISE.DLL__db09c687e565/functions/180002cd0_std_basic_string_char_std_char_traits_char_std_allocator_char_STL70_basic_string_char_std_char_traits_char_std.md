# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>(char const *)

- ea: `0x180002cd0`
- end: `0x180002d05`
- name: `??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z`
- size: `53`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180001434`
- `0x180001490`
- `0x18000b40c`
- `0x18000bc60`
- `0x18000c614`

## callees

- `0x180002cd0`
- `0x18000c000`

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
0x180002cd0  push    rbx
0x180002cd2  sub     rsp, 20h
0x180002cd6  xor     eax, eax
0x180002cd8  mov     qword ptr [rcx+20h], 0Fh
0x180002ce0  mov     [rcx+18h], rax
0x180002ce4  mov     rbx, rcx
0x180002ce7  mov     [rcx+8], al
0x180002cea  or      r8, 0FFFFFFFFFFFFFFFFh
0x180002cee  inc     r8
0x180002cf1  cmp     [rdx+r8], al
0x180002cf5  jnz     short loc_180002CEE
0x180002cf7  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@PEBD_K@Z; std::string::assign(char const *,unsigned __int64)
0x180002cfc  mov     rax, rbx
0x180002cff  add     rsp, 20h
0x180002d03  pop     rbx
0x180002d04  retn
```
