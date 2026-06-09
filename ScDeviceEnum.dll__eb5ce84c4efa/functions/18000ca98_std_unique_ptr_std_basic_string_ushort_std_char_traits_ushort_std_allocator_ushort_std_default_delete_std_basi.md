# std::unique_ptr<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::default_delete<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::~unique_ptr<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::default_delete<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>(void)

- ea: `0x18000ca98`
- end: `0x18000ca9d`
- name: `??1?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ee14`
- `0x18001f061`
- `0x18001f077`

## callees

- `0x18000db20`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(__int64 a1)
{
  return std::unique_ptr<std::wstring>::_Delete(a1);
}

```

## disassembly

```asm
0x18000ca98  jmp     ?_Delete@?$unique_ptr@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$default_delete@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::wstring>::_Delete(void)
```
