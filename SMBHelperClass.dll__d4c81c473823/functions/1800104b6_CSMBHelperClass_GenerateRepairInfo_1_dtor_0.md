# _CSMBHelperClass::GenerateRepairInfo_::_1_::dtor$0

- ea: `0x1800104b6`
- end: `0x1800104c4`
- name: `_CSMBHelperClass::GenerateRepairInfo_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, installer_update`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800104bd`

## pseudocode

```c
void __fastcall CSMBHelperClass::GenerateRepairInfo_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 168));
}

```

## disassembly

```asm
0x1800104b6  mov     rcx, [rdx+0A8h]
0x1800104bd  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
