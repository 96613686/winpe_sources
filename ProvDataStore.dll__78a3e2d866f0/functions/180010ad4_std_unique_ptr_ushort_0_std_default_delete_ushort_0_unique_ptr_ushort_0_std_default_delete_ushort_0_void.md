# std::unique_ptr<ushort [0],std::default_delete<ushort [0]>>::~unique_ptr<ushort [0],std::default_delete<ushort [0]>>(void)

- ea: `0x180010ad4`
- end: `0x180010ade`
- name: `??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180011e05`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180010ad7`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(void **a1)
{
  operator delete[](*a1);
}

```

## disassembly

```asm
0x180010ad4  mov     rcx, [rcx]
0x180010ad7  jmp     cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
```
