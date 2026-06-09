# Udm::_dynamic_atexit_destructor_for__s_serviceDll__

- ea: `0x18000b170`
- end: `0x18000b18b`
- name: `Udm::_dynamic_atexit_destructor_for__s_serviceDll__`
- size: `27`
- prototype: `BOOL()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b170`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b180`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b180`

## pseudocode

```c
BOOL Udm::_dynamic_atexit_destructor_for__s_serviceDll__()
{
  BOOL result; // eax

  if ( hLibModule )
    return FreeLibrary(hLibModule);
  return result;
}

```

## disassembly

```asm
0x18000b170  sub     rsp, 28h
0x18000b174  mov     rcx, cs:hLibModule; hLibModule
0x18000b17b  test    rcx, rcx
0x18000b17e  jz      short loc_18000B186
0x18000b180  call    cs:__imp_FreeLibrary
0x18000b186  add     rsp, 28h
0x18000b18a  retn
```
