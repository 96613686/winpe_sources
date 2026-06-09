# InvasivePtr<XPathNodeIteratorBase>::`vector deleting destructor'(uint)

- ea: `0x180006918`
- end: `0x180006947`
- name: `??_E?$InvasivePtr@VXPathNodeIteratorBase@@@@QEAAPEAXI@Z`
- size: `47`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180008000`
- `0x18000cb64`

## callees

- `0x1800010b8`
- `0x1800019b8`

## pseudocode

```c
char *__fastcall InvasivePtr<XPathNodeIteratorBase>::`vector deleting destructor'(char *a1)
{
  char *v1; // rbx

  v1 = a1 - 8;
  `vector destructor iterator'(
    a1,
    8u,
    *((_QWORD *)a1 - 1),
    InvasivePtr<XPathNodeIteratorBase>::~InvasivePtr<XPathNodeIteratorBase>);
  operator delete(v1);
  return v1;
}

```

## disassembly

```asm
0x180006918  push    rbx
0x18000691a  sub     rsp, 20h
0x18000691e  lea     rbx, [rcx-8]
0x180006922  mov     edx, 8; unsigned __int64
0x180006927  mov     r8, [rbx]; unsigned __int64
0x18000692a  lea     r9, ??1?$InvasivePtr@VXPathNodeIteratorBase@@@@QEAA@XZ; void (*)(void *)
0x180006931  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180006936  mov     rcx, rbx; Block
0x180006939  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000693e  mov     rax, rbx
0x180006941  add     rsp, 20h
0x180006945  pop     rbx
0x180006946  retn
```
