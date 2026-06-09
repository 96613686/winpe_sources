# _CRegistry::GetCurrentSubKeyPath_::_1_::dtor$2

- ea: `0x1400161c4`
- end: `0x1400161d0`
- name: `_CRegistry::GetCurrentSubKeyPath_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14000ff40`

## pseudocode

```c
void __fastcall CRegistry::GetCurrentSubKeyPath_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  CHString::~CHString((const unsigned __int16 **)(a2 + 40));
}

```

## disassembly

```asm
0x1400161c4  lea     rcx, [rdx+28h]; this
0x1400161cb  jmp     ??1CHString@@QEAA@XZ; CHString::~CHString(void)
```
