# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::basic_string<char,std::char_traits<char>,std::allocator<char>>(char const *)

- ea: `0x140002f2c`
- end: `0x140002f56`
- name: `??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD@Z`
- size: `42`
- prototype: `_QWORD *__fastcall(_QWORD *, void *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140007d40`
- `0x140007d80`
- `0x140007dc0`
- `0x140008130`

## callees

- `0x140007704`

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
0x140002f2c  push    rbx
0x140002f2e  sub     rsp, 20h
0x140002f32  mov     qword ptr [rcx+18h], 0Fh
0x140002f3a  mov     rbx, rcx
0x140002f3d  mov     qword ptr [rcx+10h], 0
0x140002f45  mov     byte ptr [rcx], 0
0x140002f48  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD@Z; std::string::assign(char const *)
0x140002f4d  mov     rax, rbx
0x140002f50  add     rsp, 20h
0x140002f54  pop     rbx
0x140002f55  retn
```
