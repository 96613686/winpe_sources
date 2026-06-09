# CXMLComparison::GetLegacyAltitude(void)

- ea: `0x18000d9c0`
- end: `0x18000d9c4`
- name: `?GetLegacyAltitude@CXMLComparison@@UEBAKXZ`
- size: `4`
- prototype: `__int64 __fastcall(CXMLComparison *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c
__int64 __fastcall CXMLComparison::GetLegacyAltitude(CXMLComparison *this)
{
  return *((unsigned int *)this + 20);
}

```

## disassembly

```asm
0x18000d9c0  mov     eax, [rcx+50h]
0x18000d9c3  retn
```
