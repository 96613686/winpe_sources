# GetExtensionVersion$dtor$0

- ea: `0x18000fe56`
- end: `0x18000fe62`
- name: `GetExtensionVersion$dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003704`

## pseudocode

```c
__int64 __fastcall GetExtensionVersion_dtor_0(__int64 a1, __int64 a2)
{
  return std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::~basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(a2 + 40);
}

```

## disassembly

```asm
0x18000fe56  lea     rcx, [rdx+28h]
0x18000fe5d  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::~basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>(void)
```
