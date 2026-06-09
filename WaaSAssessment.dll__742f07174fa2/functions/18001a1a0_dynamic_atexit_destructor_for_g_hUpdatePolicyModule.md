# _dynamic_atexit_destructor_for__g_hUpdatePolicyModule__

- ea: `0x18001a1a0`
- end: `0x18001a1bb`
- name: `_dynamic_atexit_destructor_for__g_hUpdatePolicyModule__`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18001a1a0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001a1b0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001a1b0`

## pseudocode

```c
BOOL dynamic_atexit_destructor_for__g_hUpdatePolicyModule__()
{
  BOOL result; // eax

  if ( g_hUpdatePolicyModule )
    return FreeLibrary(g_hUpdatePolicyModule);
  return result;
}

```

## disassembly

```asm
0x18001a1a0  sub     rsp, 28h
0x18001a1a4  mov     rcx, cs:?g_hUpdatePolicyModule@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; hLibModule
0x18001a1ab  test    rcx, rcx
0x18001a1ae  jz      short loc_18001A1B6
0x18001a1b0  call    cs:__imp_FreeLibrary
0x18001a1b6  add     rsp, 28h
0x18001a1ba  retn
```
