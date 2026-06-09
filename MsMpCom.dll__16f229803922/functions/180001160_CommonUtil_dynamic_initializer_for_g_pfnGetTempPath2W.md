# CommonUtil::_dynamic_initializer_for__g_pfnGetTempPath2W__

- ea: `0x180001160`
- end: `0x18000116a`
- name: `CommonUtil::_dynamic_initializer_for__g_pfnGetTempPath2W__`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 CommonUtil::_dynamic_initializer_for__g_pfnGetTempPath2W__()
{
  return _InterlockedExchange64(&qword_1800137B8, 0);
}

```

## disassembly

```asm
0x180001160  xor     eax, eax
0x180001162  xchg    rax, cs:qword_1800137B8
0x180001169  retn
```
