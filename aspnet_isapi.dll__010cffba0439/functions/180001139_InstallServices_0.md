# InstallServices_0

- ea: `0x180001139`
- end: `0x18000113f`
- name: `InstallServices_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, installer_update`

## callers

- `0x1800010c0`

## import_xrefs

- `webengine4!InstallServices` at `0x180001139`

## pseudocode

```c
// attributes: thunk
__int64 InstallServices_0()
{
  return InstallServices();
}

```

## disassembly

```asm
0x180001139  jmp     cs:__imp_InstallServices
```
