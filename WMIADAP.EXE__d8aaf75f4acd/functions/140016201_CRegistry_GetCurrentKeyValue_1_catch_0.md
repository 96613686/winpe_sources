# _CRegistry::GetCurrentKeyValue_::_1_::catch$0

- ea: `0x140016201`
- end: `0x140016222`
- name: `_CRegistry::GetCurrentKeyValue_::_1_::catch$0`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000298c`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140016212`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140016212`

## pseudocode

```c
void __fastcall __noreturn CRegistry::GetCurrentKeyValue_::_1_::catch_0(__int64 a1, __int64 a2)
{
  CWin32DefaultArena::WbemMemFree(*(void **)(a2 + 72));
  throw;
}

```

## disassembly

```asm
0x140016201  mov     [rsp+arg_8], rdx
0x140016206  push    rbp
0x140016207  sub     rsp, 30h
0x14001620b  mov     rbp, rdx
0x14001620e  mov     rcx, [rbp+48h]
0x140016212  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140016218  xor     edx, edx; pThrowInfo
0x14001621a  xor     ecx, ecx; pExceptionObject
0x14001621c  call    _CxxThrowException_0
```
