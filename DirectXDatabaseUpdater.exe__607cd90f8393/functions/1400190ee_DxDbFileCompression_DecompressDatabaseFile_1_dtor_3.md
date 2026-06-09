# _DxDbFileCompression::DecompressDatabaseFile_::_1_::dtor$3

- ea: `0x1400190ee`
- end: `0x1400190fa`
- name: `_DxDbFileCompression::DecompressDatabaseFile_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400147b0`

## pseudocode

```c
__int64 __fastcall DxDbFileCompression::DecompressDatabaseFile_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return std::ofstream::`vbase destructor'(a2 + 368);
}

```

## disassembly

```asm
0x1400190ee  lea     rcx, [rdx+170h]
0x1400190f5  jmp     ??_D?$basic_ofstream@DU?$char_traits@D@std@@@std@@QEAAXXZ; std::ofstream::`vbase destructor'(void)
```
