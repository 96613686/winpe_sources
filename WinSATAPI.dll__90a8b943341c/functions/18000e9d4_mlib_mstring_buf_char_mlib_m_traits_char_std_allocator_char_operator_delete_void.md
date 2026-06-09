# mlib::mstring_buf<char,mlib::m_traits<char>,std::allocator<char>>::operator delete(void *)

- ea: `0x18000e9d4`
- end: `0x18000e9db`
- name: `??3?$mstring_buf@DV?$m_traits@D@mlib@@V?$allocator@D@std@@@mlib@@CAXPEAX@Z`
- size: `7`
- prototype: `void __fastcall(void *)`
- caller_count: `16`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x18002fe3c`
- `0x18002fe60`
- `0x18002fea0`
- `0x18002fec0`
- `0x18002ff42`
- `0x18002ffc0`
- `0x1800300b0`
- `0x18003012a`
- `0x18003013c`
- `0x1800302f0`
- `0x180030512`
- `0x180030580`
- `0x180030670`
- `0x180030720`
- `0x180030760`
- `0x180030d22`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000e9d4`

## pseudocode

```c
// attributes: thunk
void __fastcall mlib::mstring_buf<char,mlib::m_traits<char>,std::allocator<char>>::operator delete(void *a1)
{
  operator delete(a1);
}

```

## disassembly

```asm
0x18000e9d4  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
