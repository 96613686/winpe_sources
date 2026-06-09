# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::basic_string<char,std::char_traits<char>,std::allocator<char>>(char const *)

- ea: `0x180008808`
- end: `0x180008832`
- name: `??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD@Z`
- size: `42`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d4a0`
- `0x18000d4e0`
- `0x18000d520`

## callees

- `0x18000d0a4`

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
0x180008808  push    rbx
0x18000880a  sub     rsp, 20h
0x18000880e  mov     qword ptr [rcx+18h], 0Fh
0x180008816  mov     rbx, rcx
0x180008819  mov     qword ptr [rcx+10h], 0
0x180008821  mov     byte ptr [rcx], 0
0x180008824  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD@Z; std::string::assign(char const *)
0x180008829  mov     rax, rbx
0x18000882c  add     rsp, 20h
0x180008830  pop     rbx
0x180008831  retn
```
