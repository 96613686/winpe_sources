# std::unique_ptr<uchar,std::default_delete<uchar>>::~unique_ptr<uchar,std::default_delete<uchar>>(void)

- ea: `0x18000ca78`
- end: `0x18000ca8f`
- name: `??1?$unique_ptr@EU?$default_delete@E@std@@@std@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18001ee6e`

## callees

- `0x18000ca78`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000ca84`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ca84`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18000ca78  sub     rsp, 28h
0x18000ca7c  mov     rcx, [rcx]
0x18000ca7f  test    rcx, rcx
0x18000ca82  jz      short loc_18000CA8A
0x18000ca84  call    cs:__imp_??3@YAXPEAX@Z
0x18000ca8a  add     rsp, 28h
0x18000ca8e  retn
```
