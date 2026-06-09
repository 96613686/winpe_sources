# _CRegistry::SetCurrentKeyValue_::_1_::dtor$1

- ea: `0x140016386`
- end: `0x140016392`
- name: `_CRegistry::SetCurrentKeyValue_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ff40`

## pseudocode

```c
void __fastcall CRegistry::SetCurrentKeyValue_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CHString::~CHString((const unsigned __int16 **)(a2 + 136));
}

```

## disassembly

```asm
0x140016386  lea     rcx, [rdx+88h]; this
0x14001638d  jmp     ??1CHString@@QEAA@XZ; CHString::~CHString(void)
```
