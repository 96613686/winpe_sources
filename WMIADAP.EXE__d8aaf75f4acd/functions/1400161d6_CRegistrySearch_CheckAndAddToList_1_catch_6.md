# _CRegistrySearch::CheckAndAddToList_::_1_::catch$6

- ea: `0x1400161d6`
- end: `0x1400161fb`
- name: `_CRegistrySearch::CheckAndAddToList_::_1_::catch$6`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000298c`
- `0x14001057c`

## pseudocode

```c
void __fastcall __noreturn CRegistrySearch::CheckAndAddToList_::_1_::catch_6(__int64 a1, __int64 a2)
{
  CHString::`scalar deleting destructor'(*(CHString **)(a2 + 40), 1u);
  throw;
}

```

## disassembly

```asm
0x1400161d6  mov     [rsp+arg_8], rdx
0x1400161db  push    rbp
0x1400161dc  sub     rsp, 20h
0x1400161e0  mov     rbp, rdx
0x1400161e3  mov     edx, 1; unsigned int
0x1400161e8  mov     rcx, [rbp+28h]; this
0x1400161ec  call    ??_GCHString@@QEAAPEAXI@Z; CHString::`scalar deleting destructor'(uint)
0x1400161f1  xor     edx, edx; pThrowInfo
0x1400161f3  xor     ecx, ecx; pExceptionObject
0x1400161f5  call    _CxxThrowException_0
```
