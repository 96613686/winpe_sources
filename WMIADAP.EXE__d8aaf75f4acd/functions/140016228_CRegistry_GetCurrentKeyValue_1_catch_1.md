# _CRegistry::GetCurrentKeyValue_::_1_::catch$1

- ea: `0x140016228`
- end: `0x140016249`
- name: `_CRegistry::GetCurrentKeyValue_::_1_::catch$1`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000298c`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140016239`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140016239`

## pseudocode

```c
void __fastcall __noreturn CRegistry::GetCurrentKeyValue_::_1_::catch_1(__int64 a1, __int64 a2)
{
  CWin32DefaultArena::WbemMemFree(*(void **)(a2 + 64));
  throw;
}

```

## disassembly

```asm
0x140016228  mov     [rsp+arg_8], rdx
0x14001622d  push    rbp
0x14001622e  sub     rsp, 30h
0x140016232  mov     rbp, rdx
0x140016235  mov     rcx, [rbp+40h]
0x140016239  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x14001623f  xor     edx, edx; pThrowInfo
0x140016241  xor     ecx, ecx; pExceptionObject
0x140016243  call    _CxxThrowException_0
```
