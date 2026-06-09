# _CRegistry::SetCurrentKeyValue_::_1_::catch$2

- ea: `0x14001624f`
- end: `0x140016270`
- name: `_CRegistry::SetCurrentKeyValue_::_1_::catch$2`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000298c`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140016260`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140016260`

## pseudocode

```c
void __fastcall __noreturn CRegistry::SetCurrentKeyValue_::_1_::catch_2(__int64 a1, __int64 a2)
{
  CWin32DefaultArena::WbemMemFree(*(void **)(a2 + 56));
  throw;
}

```

## disassembly

```asm
0x14001624f  mov     [rsp+arg_8], rdx
0x140016254  push    rbp
0x140016255  sub     rsp, 30h
0x140016259  mov     rbp, rdx
0x14001625c  mov     rcx, [rbp+38h]
0x140016260  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140016266  xor     edx, edx; pThrowInfo
0x140016268  xor     ecx, ecx; pExceptionObject
0x14001626a  call    _CxxThrowException_0
```
