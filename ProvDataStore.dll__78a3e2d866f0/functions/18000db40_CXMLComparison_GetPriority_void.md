# CXMLComparison::GetPriority(void)

- ea: `0x18000db40`
- end: `0x18000db44`
- name: `?GetPriority@CXMLComparison@@UEBAKXZ`
- size: `4`
- prototype: `__int64 __fastcall(CXMLComparison *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c
__int64 __fastcall CXMLComparison::GetPriority(CXMLComparison *this)
{
  return *((unsigned int *)this + 22);
}

```

## disassembly

```asm
0x18000db40  mov     eax, [rcx+58h]
0x18000db43  retn
```
