# _ReadWildcards_::_1_::dtor$0

- ea: `0x18000c064`
- end: `0x18000c070`
- name: `_ReadWildcards_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800024cc`

## pseudocode

```c
void __fastcall ReadWildcards_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  String::~String((String *)(a2 + 32));
}

```

## disassembly

```asm
0x18000c064  lea     rcx, [rdx+20h]; this
0x18000c06b  jmp     ??1String@@QEAA@XZ; String::~String(void)
```
