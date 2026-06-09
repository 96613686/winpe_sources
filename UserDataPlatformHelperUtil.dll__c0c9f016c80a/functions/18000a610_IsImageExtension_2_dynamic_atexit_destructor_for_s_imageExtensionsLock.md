# _IsImageExtension_::_2_::_dynamic_atexit_destructor_for__s_imageExtensionsLock__

- ea: `0x18000a610`
- end: `0x18000a61e`
- name: `_IsImageExtension_::_2_::_dynamic_atexit_destructor_for__s_imageExtensionsLock__`
- size: `14`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a617`

## pseudocode

```c
void __fastcall IsImageExtension_::_2_::_dynamic_atexit_destructor_for__s_imageExtensionsLock__()
{
  DeleteCriticalSection(&stru_180011A20);
}

```

## disassembly

```asm
0x18000a610  lea     rcx, stru_180011A20
0x18000a617  jmp     cs:__imp_DeleteCriticalSection
```
