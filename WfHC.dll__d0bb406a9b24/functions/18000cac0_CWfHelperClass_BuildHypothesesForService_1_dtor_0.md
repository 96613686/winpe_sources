# _CWfHelperClass::BuildHypothesesForService_::_1_::dtor$0

- ea: `0x18000cac0`
- end: `0x18000cace`
- name: `_CWfHelperClass::BuildHypothesesForService_::_1_::dtor$0`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, service_task`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000cac7`

## pseudocode

```c
void __fastcall CWfHelperClass::BuildHypothesesForService_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete[](*(void **)(a2 + 224));
}

```

## disassembly

```asm
0x18000cac0  mov     rcx, [rdx+0E0h]
0x18000cac7  jmp     cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
```
