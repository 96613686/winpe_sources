# _IsImageExtension_::_2_::_dynamic_atexit_destructor_for__s_imageExtensions__

- ea: `0x18000a5e0`
- end: `0x18000a5fb`
- name: `_IsImageExtension_::_2_::_dynamic_atexit_destructor_for__s_imageExtensions__`
- size: `27`
- prototype: `void __fastcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a5e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a5f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a5f0`

## pseudocode

```c
void __fastcall IsImageExtension_::_2_::_dynamic_atexit_destructor_for__s_imageExtensions__()
{
  if ( hMem )
    LocalFree(hMem);
}

```

## disassembly

```asm
0x18000a5e0  sub     rsp, 28h
0x18000a5e4  mov     rcx, cs:hMem; hMem
0x18000a5eb  test    rcx, rcx
0x18000a5ee  jz      short loc_18000A5F6
0x18000a5f0  call    cs:__imp_LocalFree
0x18000a5f6  add     rsp, 28h
0x18000a5fa  retn
```
