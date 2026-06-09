# ATL::CComPtr<XPathExpressionBase>::`vector deleting destructor'(uint)

- ea: `0x180003498`
- end: `0x1800034c7`
- name: `??_E?$CComPtr@VXPathExpressionBase@@@ATL@@QEAAPEAXI@Z`
- size: `47`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004bdc`
- `0x180004c30`

## callees

- `0x1800010b8`
- `0x1800019b8`

## pseudocode

```c
char *__fastcall ATL::CComPtr<XPathExpressionBase>::`vector deleting destructor'(char *a1)
{
  char *v1; // rbx

  v1 = a1 - 8;
  `vector destructor iterator'(
    a1,
    8u,
    *((_QWORD *)a1 - 1),
    ATL::CComPtr<XPathExpressionBase>::~CComPtr<XPathExpressionBase>);
  operator delete(v1);
  return v1;
}

```

## disassembly

```asm
0x180003498  push    rbx
0x18000349a  sub     rsp, 20h
0x18000349e  lea     rbx, [rcx-8]
0x1800034a2  mov     edx, 8; unsigned __int64
0x1800034a7  mov     r8, [rbx]; unsigned __int64
0x1800034aa  lea     r9, ??1?$CComPtr@VXPathExpressionBase@@@ATL@@QEAA@XZ; void (*)(void *)
0x1800034b1  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800034b6  mov     rcx, rbx; Block
0x1800034b9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800034be  mov     rax, rbx
0x1800034c1  add     rsp, 20h
0x1800034c5  pop     rbx
0x1800034c6  retn
```
