# std::_Temp_iterator<Speller::CSuggestion>::~_Temp_iterator<Speller::CSuggestion>(void)

- ea: `0x180092438`
- end: `0x18009244f`
- name: `??1?$_Temp_iterator@VCSuggestion@Speller@@@std@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **)`
- caller_count: `22`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18008f424`
- `0x18008f970`
- `0x18008fb80`
- `0x1800908d4`
- `0x180090cb0`
- `0x180092270`
- `0x1800af791`
- `0x1800af7a3`
- `0x1800af7b5`
- `0x1800af7c7`
- `0x1800af7d9`
- `0x1800af7eb`
- `0x1800af7fd`
- `0x1800af80f`
- `0x1800af821`
- `0x1800af833`
- `0x1800af862`
- `0x1800af874`
- `0x1800af886`
- `0x1800af8b5`
- `0x1800af8c7`
- `0x1800af8f6`

## callees

- `0x180092438`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180092444`
- `msvcrt!??3@YAXPEAX@Z` at `0x180092444`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall std::_Temp_iterator<Speller::CSuggestion>::~_Temp_iterator<Speller::CSuggestion>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x180092438  sub     rsp, 28h
0x18009243c  mov     rcx, [rcx]
0x18009243f  test    rcx, rcx
0x180092442  jz      short loc_18009244A
0x180092444  call    cs:__imp_??3@YAXPEAX@Z
0x18009244a  add     rsp, 28h
0x18009244e  retn
```
