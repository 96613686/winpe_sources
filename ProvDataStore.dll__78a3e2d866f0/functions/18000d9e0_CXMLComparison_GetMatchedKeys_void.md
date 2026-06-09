# CXMLComparison::GetMatchedKeys(void)

- ea: `0x18000d9e0`
- end: `0x18000d9e4`
- name: `?GetMatchedKeys@CXMLComparison@@UEBA?AW4OperatorKeys@@XZ`
- size: `4`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c
__int64 __fastcall CXMLComparison::GetMatchedKeys(__int64 a1)
{
  return *(unsigned int *)(a1 + 84);
}

```

## disassembly

```asm
0x18000d9e0  mov     eax, [rcx+54h]
0x18000d9e3  retn
```
