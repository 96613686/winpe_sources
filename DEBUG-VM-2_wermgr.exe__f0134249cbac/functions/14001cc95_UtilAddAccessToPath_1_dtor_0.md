# _UtilAddAccessToPath_::_1_::dtor$0

- ea: `0x14001cc95`
- end: `0x14001cca1`
- name: `_UtilAddAccessToPath_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140004a14`

## pseudocode

```c
void __fastcall UtilAddAccessToPath_::_1_::dtor_0(__int64 a1, void **a2)
{
  utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::~unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>(
    a2 + 10,
    (const struct std::nothrow_t *)a2);
}

```

## disassembly

```asm
0x14001cc95  lea     rcx, [rdx+50h]
0x14001cc9c  jmp     ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@QEAA@XZ; utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>>::~unique_ptr<uchar [0],utl::default_delete<uchar [0]>>(void)
```
