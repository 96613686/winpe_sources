# _GetAppUriHandlerJsonFromFile_::_1_::dtor$0

- ea: `0x14001175e`
- end: `0x14001176a`
- name: `_GetAppUriHandlerJsonFromFile_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x14000a5d8`

## pseudocode

```c
__int64 __fastcall GetAppUriHandlerJsonFromFile_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::basic_ifstream<unsigned short>::`vbase destructor'(a2 + 320);
}

```

## disassembly

```asm
0x14001175e  lea     rcx, [rdx+140h]
0x140011765  jmp     ??_D?$basic_ifstream@GU?$char_traits@G@std@@@std@@QEAAXXZ; std::basic_ifstream<ushort>::`vbase destructor'(void)
```
