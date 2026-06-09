# _CBrowserFactory::CreateInstance_::_1_::dtor$1

- ea: `0x18000be3c`
- end: `0x18000be48`
- name: `_CBrowserFactory::CreateInstance_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800024cc`

## pseudocode

```c
void __fastcall CBrowserFactory::CreateInstance_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  String::~String((String *)(a2 + 136));
}

```

## disassembly

```asm
0x18000be3c  lea     rcx, [rdx+88h]; this
0x18000be43  jmp     ??1String@@QEAA@XZ; String::~String(void)
```
