# std::vector<Windows::AutoNewPtr<FeatureDescriptor>,std::allocator<Windows::AutoNewPtr<FeatureDescriptor>>>::_Xlength(void)

- ea: `0x18000a85c`
- end: `0x18000a86e`
- name: `?_Xlength@?$vector@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@V?$allocator@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@@std@@@std@@CAXXZ`
- size: `18`
- prototype: `void __noreturn()`
- caller_count: `18`
- callee_count: `0`
- tags: ``

## callers

- `0x180005a14`
- `0x18000ca94`
- `0x18000cca4`
- `0x18000cef4`
- `0x18000d11c`
- `0x18000d2b4`
- `0x18000d4a8`
- `0x18000ebfc`
- `0x18000ed90`
- `0x18000ef00`
- `0x180010e3c`
- `0x18001142c`
- `0x180013e1c`
- `0x18001ec00`
- `0x18001ed30`
- `0x1800247bc`
- `0x18002621c`
- `0x1800263b4`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a867`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a867`

## pseudocode

```c
void __noreturn std::vector<Windows::AutoNewPtr<FeatureDescriptor>>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x18000a85c  sub     rsp, 28h
0x18000a860  lea     rcx, aVectorTooLong; "vector too long"
0x18000a867  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
