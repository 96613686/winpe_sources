# std::vector<uchar,std::allocator<uchar>>::_Umove<uchar *>(uchar *,uchar *,uchar *)

- ea: `0x18000d508`
- end: `0x18000d528`
- name: `??$_Umove@PEAE@?$vector@EV?$allocator@E@std@@@std@@IEAAPEAEPEAE00@Z`
- size: `32`
- prototype: `char *__fastcall(__int64, const void *, __int64, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000eb78`
- `0x180010f18`

## callees

- `0x180008982`

## pseudocode

```c
char *__fastcall std::vector<unsigned char>::_Umove<unsigned char *>(__int64 a1, const void *a2, __int64 a3, void *a4)
{
  return (char *)memmove_0(a4, a2, a3 - (_QWORD)a2) + a3 - (_QWORD)a2;
}

```

## disassembly

```asm
0x18000d508  push    rbx
0x18000d50a  sub     rsp, 20h
0x18000d50e  mov     rbx, r8
0x18000d511  mov     rcx, r9; void *
0x18000d514  sub     rbx, rdx
0x18000d517  mov     r8, rbx; Size
0x18000d51a  call    memmove_0
0x18000d51f  add     rax, rbx
0x18000d522  add     rsp, 20h
0x18000d526  pop     rbx
0x18000d527  retn
```
