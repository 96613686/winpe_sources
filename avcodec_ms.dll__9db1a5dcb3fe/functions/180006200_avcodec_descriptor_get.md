# avcodec_descriptor_get

- ea: `0x180006200`
- end: `0x180006236`
- name: `avcodec_descriptor_get`
- size: `54`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004150`
- `0x180005cc0`
- `0x180006320`
- `0x180012aa0`
- `0x180012b10`

## callees

- `0x1800229a2`

## pseudocode

```c
void *__fastcall avcodec_descriptor_get(int a1)
{
  int Key; // [rsp+40h] [rbp+8h] BYREF

  Key = a1;
  return bsearch(&Key, &qword_180026D20, 0x212u, 0x30u, CompareFunction);
}

```

## disassembly

```asm
0x180006200  mov     [rsp+Key], ecx
0x180006204  sub     rsp, 38h
0x180006208  lea     rax, CompareFunction
0x18000620f  mov     r9d, 30h ; '0'; SizeOfElements
0x180006215  mov     r8d, 212h; NumOfElements
0x18000621b  mov     [rsp+38h+CompareFunction], rax; CompareFunction
0x180006220  lea     rdx, qword_180026D20; Base
0x180006227  lea     rcx, [rsp+38h+Key]; Key
0x18000622c  call    bsearch
0x180006231  add     rsp, 38h
0x180006235  retn
```
