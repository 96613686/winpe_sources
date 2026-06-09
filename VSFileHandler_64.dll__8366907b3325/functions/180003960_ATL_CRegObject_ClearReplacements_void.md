# ATL::CRegObject::ClearReplacements(void)

- ea: `0x180003960`
- end: `0x180003969`
- name: `?ClearReplacements@CRegObject@ATL@@UEAAJXZ`
- size: `9`
- prototype: `__int64 __fastcall(ATL::CRegObject *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800038c4`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::ClearReplacements(ATL::CRegObject *this)
{
  return ATL::CExpansionVector::ClearReplacements((ATL::CRegObject *)((char *)this + 8));
}

```

## disassembly

```asm
0x180003960  add     rcx, 8; this
0x180003964  jmp     ?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ; ATL::CExpansionVector::ClearReplacements(void)
```
