# _DxDbFileCompression::DecompressDatabaseFile_::_1_::dtor$1

- ea: `0x1400190ca`
- end: `0x1400190d6`
- name: `_DxDbFileCompression::DecompressDatabaseFile_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140014784`

## pseudocode

```c
__int64 __fastcall DxDbFileCompression::DecompressDatabaseFile_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::ifstream::`vbase destructor'(a2 + 96);
}

```

## disassembly

```asm
0x1400190ca  lea     rcx, [rdx+60h]
0x1400190d1  jmp     ??_D?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAAXXZ; std::ifstream::`vbase destructor'(void)
```
