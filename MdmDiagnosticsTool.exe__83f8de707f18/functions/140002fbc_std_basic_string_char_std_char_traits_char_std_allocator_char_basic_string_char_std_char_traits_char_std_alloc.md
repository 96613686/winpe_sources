# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::basic_string<char,std::char_traits<char>,std::allocator<char>>(char const *)

- ea: `0x140002fbc`
- end: `0x140002fe7`
- name: `??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD@Z`
- size: `43`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140008170`
- `0x1400081b0`
- `0x1400081f0`
- `0x140008694`

## callees

- `0x140007b1c`

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
0x140002fbc  push    rbx
0x140002fbe  sub     rsp, 20h
0x140002fc2  mov     qword ptr [rcx+18h], 0Fh
0x140002fca  mov     rbx, rcx
0x140002fcd  mov     qword ptr [rcx+10h], 0
0x140002fd5  mov     byte ptr [rcx], 0
0x140002fd8  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD@Z; std::string::assign(char const *)
0x140002fdd  mov     rax, rbx
0x140002fe0  add     rsp, 20h
0x140002fe4  pop     rbx
0x140002fe5  retn
```
