# _GetAppUriHandlerJsonFromFile_::_1_::dtor$1

- ea: `0x140011770`
- end: `0x14001177c`
- name: `_GetAppUriHandlerJsonFromFile_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x14000a604`

## pseudocode

```c
__int64 __fastcall GetAppUriHandlerJsonFromFile_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::basic_ostringstream<unsigned short>::`vbase destructor'(a2 + 80);
}

```

## disassembly

```asm
0x140011770  lea     rcx, [rdx+50h]
0x140011777  jmp     ??_D?$basic_ostringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_ostringstream<ushort>::`vbase destructor'(void)
```
