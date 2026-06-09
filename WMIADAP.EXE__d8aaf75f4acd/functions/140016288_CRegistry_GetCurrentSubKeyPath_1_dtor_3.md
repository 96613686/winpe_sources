# _CRegistry::GetCurrentSubKeyPath_::_1_::dtor$3

- ea: `0x140016288`
- end: `0x140016294`
- name: `_CRegistry::GetCurrentSubKeyPath_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ff40`

## pseudocode

```c
void __fastcall CRegistry::GetCurrentSubKeyPath_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  CHString::~CHString((const unsigned __int16 **)(a2 + 32));
}

```

## disassembly

```asm
0x140016288  lea     rcx, [rdx+20h]; this
0x14001628f  jmp     ??1CHString@@QEAA@XZ; CHString::~CHString(void)
```
