# CXMLComparisonUI::IsExactMatch(void)

- ea: `0x18000dd40`
- end: `0x18000dd44`
- name: `?IsExactMatch@CXMLComparisonUI@@UEBAHXZ`
- size: `4`
- prototype: `__int64 __fastcall(CXMLComparisonUI *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c
__int64 __fastcall CXMLComparisonUI::IsExactMatch(CXMLComparisonUI *this)
{
  return *((unsigned int *)this + 29);
}

```

## disassembly

```asm
0x18000dd40  mov     eax, [rcx+74h]
0x18000dd43  retn
```
