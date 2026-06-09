# _CommonUtil::UtilGetFileSecurity_::_1_::dtor$2

- ea: `0x180009ac6`
- end: `0x180009ad4`
- name: `_CommonUtil::UtilGetFileSecurity_::_1_::dtor$2`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009acd`

## pseudocode

```c
void __fastcall CommonUtil::UtilGetFileSecurity_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 56));
}

```

## disassembly

```asm
0x180009ac6  mov     rcx, [rdx+38h]
0x180009acd  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
