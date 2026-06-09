# ATL::CRegObject::ClearReplacements(void)

- ea: `0x180004f90`
- end: `0x180004f99`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `9`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004ee0`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::ClearReplacements(ATL::CRegObject *this, unsigned int a2)
{
  return ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)this + 8), a2);
}

```

## disassembly

```asm
0x180004f90  add     rcx, 8; this
0x180004f94  jmp     ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
```
