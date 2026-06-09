# _CRegistry::GetCurrentSubKeyPath_::_1_::dtor$0

- ea: `0x140015f5f`
- end: `0x140015f6b`
- name: `_CRegistry::GetCurrentSubKeyPath_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ff40`

## pseudocode

```c
void __fastcall CRegistry::GetCurrentSubKeyPath_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CHString::~CHString((const unsigned __int16 **)(a2 + 80));
}

```

## disassembly

```asm
0x140015f5f  lea     rcx, [rdx+50h]; this
0x140015f66  jmp     ??1CHString@@QEAA@XZ; CHString::~CHString(void)
```
