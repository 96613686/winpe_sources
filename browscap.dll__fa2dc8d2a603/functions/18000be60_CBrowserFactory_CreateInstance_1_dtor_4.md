# _CBrowserFactory::CreateInstance_::_1_::dtor$4

- ea: `0x18000be60`
- end: `0x18000be6c`
- name: `_CBrowserFactory::CreateInstance_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800024cc`

## pseudocode

```c
void __fastcall CBrowserFactory::CreateInstance_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  String::~String((String *)(a2 + 88));
}

```

## disassembly

```asm
0x18000be60  lea     rcx, [rdx+58h]; this
0x18000be67  jmp     ??1String@@QEAA@XZ; String::~String(void)
```
