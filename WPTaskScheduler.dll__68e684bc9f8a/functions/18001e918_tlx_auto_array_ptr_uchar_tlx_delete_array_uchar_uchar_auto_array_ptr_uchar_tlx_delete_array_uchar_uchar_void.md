# tlx::auto_array_ptr<uchar,&tlx::_delete_array<uchar>(uchar *)>::~auto_array_ptr<uchar,&tlx::_delete_array<uchar>(uchar *)>(void)

- ea: `0x18001e918`
- end: `0x18001e92f`
- name: `??1?$auto_array_ptr@E$1??$_delete_array@E@tlx@@YAXPEAE@Z@tlx@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18002146e`
- `0x180021492`
- `0x18002153e`

## callees

- `0x18001e918`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e924`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001e924`

## pseudocode

```c
void __fastcall tlx::auto_array_ptr<unsigned char,&void tlx::_delete_array<unsigned char>(unsigned char *)>::~auto_array_ptr<unsigned char,&void tlx::_delete_array<unsigned char>(unsigned char *)>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete[](v1);
}

```

## disassembly

```asm
0x18001e918  sub     rsp, 28h
0x18001e91c  mov     rcx, [rcx]
0x18001e91f  test    rcx, rcx
0x18001e922  jz      short loc_18001E92A
0x18001e924  call    cs:__imp_??_V@YAXPEAX@Z
0x18001e92a  add     rsp, 28h
0x18001e92e  retn
```
