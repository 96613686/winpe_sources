# _ExpandRegistryValue_::_1_::dtor$0

- ea: `0x18000ff99`
- end: `0x18000ffa5`
- name: `_ExpandRegistryValue_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000e7b0`

## pseudocode

```c
__int64 __fastcall ExpandRegistryValue_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return SP<wchar_t>::~SP<wchar_t>(a2 + 56);
}

```

## disassembly

```asm
0x18000ff99  lea     rcx, [rdx+38h]
0x18000ffa0  jmp     ??1?$SP@_W@@QEAA@XZ; SP<wchar_t>::~SP<wchar_t>(void)
```
