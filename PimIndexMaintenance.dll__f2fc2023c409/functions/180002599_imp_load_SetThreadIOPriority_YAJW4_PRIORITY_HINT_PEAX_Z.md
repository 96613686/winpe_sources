# __imp_load_?SetThreadIOPriority@@YAJW4_PRIORITY_HINT@@PEAX@Z

- ea: `0x180002599`
- end: `0x1800025a5`
- name: `__imp_load_?SetThreadIOPriority@@YAJW4_PRIORITY_HINT@@PEAX@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800024f6`

## import_xrefs

- `UserDataPlatformHelperUtil!SetThreadIOPriority` at `0x180002599`

## pseudocode

```c
__int64 load__SetThreadIOPriority__YAJW4_PRIORITY_HINT__PEAX_Z()
{
  return _tailMerge_userdataplatformhelperutil_dll();
}

```

## disassembly

```asm
0x180002599  lea     rax, __imp_?SetThreadIOPriority@@YAJW4_PRIORITY_HINT@@PEAX@Z; SetThreadIOPriority(_PRIORITY_HINT,void *)
0x1800025a0  jmp     __tailMerge_userdataplatformhelperutil_dll
```
