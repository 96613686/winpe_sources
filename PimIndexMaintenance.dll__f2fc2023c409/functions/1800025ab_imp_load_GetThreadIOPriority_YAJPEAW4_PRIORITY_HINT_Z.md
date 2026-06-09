# __imp_load_?GetThreadIOPriority@@YAJPEAW4_PRIORITY_HINT@@@Z

- ea: `0x1800025ab`
- end: `0x1800025b7`
- name: `__imp_load_?GetThreadIOPriority@@YAJPEAW4_PRIORITY_HINT@@@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800024f6`

## import_xrefs

- `UserDataPlatformHelperUtil!GetThreadIOPriority` at `0x1800025ab`

## pseudocode

```c
__int64 load__GetThreadIOPriority__YAJPEAW4_PRIORITY_HINT___Z()
{
  return _tailMerge_userdataplatformhelperutil_dll();
}

```

## disassembly

```asm
0x1800025ab  lea     rax, __imp_?GetThreadIOPriority@@YAJPEAW4_PRIORITY_HINT@@@Z; GetThreadIOPriority(_PRIORITY_HINT *)
0x1800025b2  jmp     __tailMerge_userdataplatformhelperutil_dll
```
