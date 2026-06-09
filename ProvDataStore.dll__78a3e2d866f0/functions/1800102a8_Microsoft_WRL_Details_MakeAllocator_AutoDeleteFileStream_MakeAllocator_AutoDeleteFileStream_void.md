# Microsoft::WRL::Details::MakeAllocator<AutoDeleteFileStream>::~MakeAllocator<AutoDeleteFileStream>(void)

- ea: `0x1800102a8`
- end: `0x1800102bf`
- name: `??1?$MakeAllocator@VAutoDeleteFileStream@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180011d6f`

## callees

- `0x1800102a8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800102b4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800102b4`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::MakeAllocator<AutoDeleteFileStream>::~MakeAllocator<AutoDeleteFileStream>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x1800102a8  sub     rsp, 28h
0x1800102ac  mov     rcx, [rcx]
0x1800102af  test    rcx, rcx
0x1800102b2  jz      short loc_1800102BA
0x1800102b4  call    cs:__imp_??3@YAXPEAX@Z
0x1800102ba  add     rsp, 28h
0x1800102be  retn
```
