# _CSession::_DoReadrmonNodeDiff_::_1_::dtor$3

- ea: `0x18001ee00`
- end: `0x18001ee0e`
- name: `_CSession::_DoReadrmonNodeDiff_::_1_::dtor$3`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001ee07`

## pseudocode

```c
void __fastcall CSession::_DoReadrmonNodeDiff_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 48));
}

```

## disassembly

```asm
0x18001ee00  mov     rcx, [rdx+30h]
0x18001ee07  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
