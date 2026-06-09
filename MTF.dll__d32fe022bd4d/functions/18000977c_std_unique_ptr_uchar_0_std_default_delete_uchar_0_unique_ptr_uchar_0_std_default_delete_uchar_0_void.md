# std::unique_ptr<uchar [0],std::default_delete<uchar [0]>>::~unique_ptr<uchar [0],std::default_delete<uchar [0]>>(void)

- ea: `0x18000977c`
- end: `0x180009786`
- name: `??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ`
- size: `10`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18002c5d5`
- `0x18002dbaf`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000977f`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(void **a1)
{
  operator delete[](*a1);
}

```

## disassembly

```asm
0x18000977c  mov     rcx, [rcx]
0x18000977f  jmp     cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
```
