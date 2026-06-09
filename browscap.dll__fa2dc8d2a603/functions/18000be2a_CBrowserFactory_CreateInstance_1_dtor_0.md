# _CBrowserFactory::CreateInstance_::_1_::dtor$0

- ea: `0x18000be2a`
- end: `0x18000be36`
- name: `_CBrowserFactory::CreateInstance_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800074ec`

## pseudocode

```c
void __fastcall CBrowserFactory::CreateInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CContext::~CContext((CContext *)(a2 + 296));
}

```

## disassembly

```asm
0x18000be2a  lea     rcx, [rdx+128h]; this
0x18000be31  jmp     ??1CContext@@QEAA@XZ; CContext::~CContext(void)
```
