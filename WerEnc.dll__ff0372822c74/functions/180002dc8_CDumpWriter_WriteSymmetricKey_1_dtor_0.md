# _CDumpWriter::WriteSymmetricKey_::_1_::dtor$0

- ea: `0x180002dc8`
- end: `0x180002dd4`
- name: `_CDumpWriter::WriteSymmetricKey_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002278`

## pseudocode

```c
void __fastcall CDumpWriter::WriteSymmetricKey_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::~unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>((void **)(a2 + 128));
}

```

## disassembly

```asm
0x180002dc8  lea     rcx, [rdx+80h]
0x180002dcf  jmp     ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@QEAA@XZ; utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>>::~unique_ptr<uchar [0],utl::default_delete<uchar [0]>>(void)
```
