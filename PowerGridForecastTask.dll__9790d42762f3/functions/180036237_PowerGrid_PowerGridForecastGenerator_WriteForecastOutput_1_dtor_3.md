# _PowerGrid::PowerGridForecastGenerator::WriteForecastOutput_::_1_::dtor$3

- ea: `0x180036237`
- end: `0x180036243`
- name: `_PowerGrid::PowerGridForecastGenerator::WriteForecastOutput_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180031944`

## pseudocode

```c
__int64 __fastcall PowerGrid::PowerGridForecastGenerator::WriteForecastOutput_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(a2 + 208);
}

```

## disassembly

```asm
0x180036237  lea     rcx, [rdx+0D0h]
0x18003623e  jmp     ??1?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
```
