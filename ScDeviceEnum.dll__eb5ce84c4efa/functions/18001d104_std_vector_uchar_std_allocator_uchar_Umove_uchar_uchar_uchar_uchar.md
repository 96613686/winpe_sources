# std::vector<uchar,std::allocator<uchar>>::_Umove<uchar *>(uchar *,uchar *,uchar *)

- ea: `0x18001d104`
- end: `0x18001d124`
- name: `??$_Umove@PEAE@?$vector@EV?$allocator@E@std@@@std@@IEAAPEAEPEAE00@Z`
- size: `32`
- prototype: `char *__fastcall(__int64, const void *, __int64, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001cfb4`
- `0x18001d5c8`

## callees

- `0x180001f32`

## pseudocode

```c
char *__fastcall std::vector<unsigned char>::_Umove<unsigned char *>(__int64 a1, const void *a2, __int64 a3, void *a4)
{
  return (char *)memmove_0(a4, a2, a3 - (_QWORD)a2) + a3 - (_QWORD)a2;
}

```

## disassembly

```asm
0x18001d104  push    rbx
0x18001d106  sub     rsp, 20h
0x18001d10a  mov     rbx, r8
0x18001d10d  mov     rcx, r9; void *
0x18001d110  sub     rbx, rdx
0x18001d113  mov     r8, rbx; Size
0x18001d116  call    memmove_0
0x18001d11b  add     rax, rbx
0x18001d11e  add     rsp, 20h
0x18001d122  pop     rbx
0x18001d123  retn
```
