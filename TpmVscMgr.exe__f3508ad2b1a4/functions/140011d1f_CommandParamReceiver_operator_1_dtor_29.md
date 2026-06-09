# _CommandParamReceiver::operator()_::_1_::dtor$29

- ea: `0x140011d1f`
- end: `0x140011d2b`
- name: `_CommandParamReceiver::operator()_::_1_::dtor$29`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140008150`

## pseudocode

```c
__int64 __fastcall CommandParamReceiver::operator()_::_1_::dtor_29(__int64 a1, __int64 a2)
{
  return TpmVscMgrMeta::basic_formatter<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_formatter<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2 + 448);
}

```

## disassembly

```asm
0x140011d1f  lea     rcx, [rdx+1C0h]
0x140011d26  jmp     ??1?$basic_formatter@GU?$char_traits@G@std@@V?$allocator@G@2@@TpmVscMgrMeta@@QEAA@XZ; TpmVscMgrMeta::basic_formatter<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_formatter<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
```
