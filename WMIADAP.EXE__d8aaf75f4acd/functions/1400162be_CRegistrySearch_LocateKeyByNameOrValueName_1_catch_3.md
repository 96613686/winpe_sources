# _CRegistrySearch::LocateKeyByNameOrValueName_::_1_::catch$3

- ea: `0x1400162be`
- end: `0x1400162de`
- name: `_CRegistrySearch::LocateKeyByNameOrValueName_::_1_::catch$3`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000298c`
- `0x140012040`

## pseudocode

```c
void __fastcall __noreturn CRegistrySearch::LocateKeyByNameOrValueName_::_1_::catch_3(__int64 a1, __int64 a2)
{
  CRegistry::Close((CRegistry *)(a2 + 112));
  throw;
}

```

## disassembly

```asm
0x1400162be  mov     [rsp+arg_8], rdx
0x1400162c3  push    rbp
0x1400162c4  sub     rsp, 40h
0x1400162c8  mov     rbp, rdx
0x1400162cb  lea     rcx, [rbp+70h]; this
0x1400162cf  call    ?Close@CRegistry@@QEAAXXZ; CRegistry::Close(void)
0x1400162d4  xor     edx, edx; pThrowInfo
0x1400162d6  xor     ecx, ecx; pExceptionObject
0x1400162d8  call    _CxxThrowException_0
```
