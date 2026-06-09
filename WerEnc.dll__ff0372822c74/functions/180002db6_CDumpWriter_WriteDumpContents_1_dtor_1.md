# _CDumpWriter::WriteDumpContents_::_1_::dtor$1

- ea: `0x180002db6`
- end: `0x180002dc2`
- name: `_CDumpWriter::WriteDumpContents_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002278`

## pseudocode

```c
void __fastcall CDumpWriter::WriteDumpContents_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::~unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>((void **)(a2 + 88));
}

```

## disassembly

```asm
0x180002db6  lea     rcx, [rdx+58h]
0x180002dbd  jmp     ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@QEAA@XZ; utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>>::~unique_ptr<uchar [0],utl::default_delete<uchar [0]>>(void)
```
