# utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>>::~unique_ptr<uchar [0],utl::default_delete<uchar [0]>>(void)

- ea: `0x14001aaf0`
- end: `0x14001ab07`
- name: `??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14001ac5c`
- `0x14001bfa8`

## callees

- `0x14001aaf0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x14001aafc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14001aafc`

## pseudocode

```c
void __fastcall utl::unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>::~unique_ptr<unsigned char [0],utl::default_delete<unsigned char [0]>>(
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
0x14001aaf0  sub     rsp, 28h
0x14001aaf4  mov     rcx, [rcx]
0x14001aaf7  test    rcx, rcx
0x14001aafa  jz      short loc_14001AB02
0x14001aafc  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14001ab02  add     rsp, 28h
0x14001ab06  retn
```
