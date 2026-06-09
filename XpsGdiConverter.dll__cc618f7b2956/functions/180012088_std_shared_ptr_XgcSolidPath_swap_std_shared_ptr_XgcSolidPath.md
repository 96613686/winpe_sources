# std::shared_ptr<XgcSolidPath>::swap(std::shared_ptr<XgcSolidPath> &)

- ea: `0x180012088`
- end: `0x18001208d`
- name: `?swap@?$shared_ptr@VXgcSolidPath@@@std@@QEAAXAEAV12@@Z`
- size: `5`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e06c`
- `0x18000e934`
- `0x180017a20`
- `0x1800184e8`
- `0x1800185f0`
- `0x18001dff0`
- `0x18002f6e8`
- `0x180031574`
- `0x180031de0`
- `0x1800328f4`
- `0x18003a18c`
- `0x18003c2d4`
- `0x1800432dc`
- `0x180043d74`

## callees

- `0x180011cd0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall std::shared_ptr<XgcSolidPath>::swap(__int64 a1, __int64 a2)
{
  return std::_Ptr_base<CXgcPenStyle>::_Swap(a1, a2);
}

```

## disassembly

```asm
0x180012088  jmp     ?_Swap@?$_Ptr_base@VCXgcPenStyle@@@std@@IEAAXAEAV12@@Z; std::_Ptr_base<CXgcPenStyle>::_Swap(std::_Ptr_base<CXgcPenStyle> &)
```
