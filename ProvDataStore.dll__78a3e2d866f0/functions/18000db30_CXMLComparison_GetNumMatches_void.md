# CXMLComparison::GetNumMatches(void)

- ea: `0x18000db30`
- end: `0x18000db34`
- name: `?GetNumMatches@CXMLComparison@@UEBAKXZ`
- size: `4`
- prototype: `__int64 __fastcall(CXMLComparison *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c
__int64 __fastcall CXMLComparison::GetNumMatches(CXMLComparison *this)
{
  return *((unsigned int *)this + 23);
}

```

## disassembly

```asm
0x18000db30  mov     eax, [rcx+5Ch]
0x18000db33  retn
```
