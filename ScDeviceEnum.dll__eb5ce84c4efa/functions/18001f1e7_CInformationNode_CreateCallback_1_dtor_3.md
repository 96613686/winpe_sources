# _CInformationNode::_CreateCallback_::_1_::dtor$3

- ea: `0x18001f1e7`
- end: `0x18001f1f5`
- name: `_CInformationNode::_CreateCallback_::_1_::dtor$3`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001f1ee`

## pseudocode

```c
void __fastcall CInformationNode::_CreateCallback_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 152));
}

```

## disassembly

```asm
0x18001f1e7  mov     rcx, [rdx+98h]
0x18001f1ee  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
