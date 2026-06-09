# ATL::CRegObject::ClearReplacements(void)

- ea: `0x1800048d0`
- end: `0x1800048d9`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `9`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004820`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::ClearReplacements(ATL::CRegObject *this, unsigned int a2)
{
  return ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)this + 8), a2);
}

```

## disassembly

```asm
0x1800048d0  add     rcx, 8; this
0x1800048d4  jmp     ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
```
