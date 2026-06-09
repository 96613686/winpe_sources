# XPathExpressionBase::IsNodeSet(void)

- ea: `0x180008bdc`
- end: `0x180008bf7`
- name: `?IsNodeSet@XPathExpressionBase@@QEAA_NXZ`
- size: `27`
- prototype: `bool __fastcall(XPathExpressionBase *__hidden this)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x180003b80`
- `0x180003d20`
- `0x180003e00`
- `0x180003ee0`
- `0x180004750`
- `0x180005a3c`
- `0x180005b60`
- `0x180005c7c`
- `0x1800080b8`
- `0x180008c24`
- `0x180008f04`
- `0x1800096d8`
- `0x180009890`
- `0x180009d84`
- `0x180009f24`
- `0x18000a280`

## callees

- `0x180012010`

## pseudocode

```c
bool __fastcall XPathExpressionBase::IsNodeSet(XPathExpressionBase *this)
{
  return (*(unsigned int (__fastcall **)(XPathExpressionBase *))(*(_QWORD *)this + 88LL))(this) == 3;
}

```

## disassembly

```asm
0x180008bdc  sub     rsp, 28h
0x180008be0  mov     rax, [rcx]
0x180008be3  mov     rax, [rax+58h]
0x180008be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bec  cmp     eax, 3
0x180008bef  setz    al
0x180008bf2  add     rsp, 28h
0x180008bf6  retn
```
