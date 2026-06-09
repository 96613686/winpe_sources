# ATL::CComPtrBase<XPathExpressionBase>::CComPtrBase<XPathExpressionBase>(XPathExpressionBase *)

- ea: `0x1800032c4`
- end: `0x1800032ed`
- name: `??0?$CComPtrBase@VXPathExpressionBase@@@ATL@@IEAA@PEAVXPathExpressionBase@@@Z`
- size: `41`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004aac`
- `0x1800094f4`
- `0x1800097cc`

## callees

- `0x1800032c4`
- `0x180012010`

## pseudocode

```c
_QWORD *__fastcall ATL::CComPtrBase<XPathExpressionBase>::CComPtrBase<XPathExpressionBase>(_QWORD *a1, __int64 a2)
{
  *a1 = a2;
  if ( a2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  return a1;
}

```

## disassembly

```asm
0x1800032c4  push    rbx
0x1800032c6  sub     rsp, 20h
0x1800032ca  mov     [rcx], rdx
0x1800032cd  mov     rbx, rcx
0x1800032d0  test    rdx, rdx
0x1800032d3  jz      short loc_1800032E4
0x1800032d5  mov     rax, [rdx]
0x1800032d8  mov     rcx, rdx
0x1800032db  mov     rax, [rax+8]
0x1800032df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032e4  mov     rax, rbx
0x1800032e7  add     rsp, 20h
0x1800032eb  pop     rbx
0x1800032ec  retn
```
