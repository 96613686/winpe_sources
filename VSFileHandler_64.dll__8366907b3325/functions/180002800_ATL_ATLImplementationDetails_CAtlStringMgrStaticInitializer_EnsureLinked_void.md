# ATL::ATLImplementationDetails::CAtlStringMgrStaticInitializer::EnsureLinked(void)

- ea: `0x180002800`
- end: `0x180002804`
- name: `?EnsureLinked@CAtlStringMgrStaticInitializer@ATLImplementationDetails@ATL@@QEAAPEAXXZ`
- size: `4`
- prototype: `void *__fastcall(ATL::ATLImplementationDetails::CAtlStringMgrStaticInitializer *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800010e0`

## pseudocode

```c
ATL::ATLImplementationDetails::CAtlStringMgrStaticInitializer *__fastcall ATL::ATLImplementationDetails::CAtlStringMgrStaticInitializer::EnsureLinked(
        ATL::ATLImplementationDetails::CAtlStringMgrStaticInitializer *this)
{
  return this;
}

```

## disassembly

```asm
0x180002800  mov     rax, rcx
0x180002803  retn
```
