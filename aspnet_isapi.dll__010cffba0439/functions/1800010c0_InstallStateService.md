# InstallStateService

- ea: `0x1800010c0`
- end: `0x1800010c5`
- name: `InstallStateService`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update`

## callees

- `0x180001139`

## pseudocode

```c
// attributes: thunk
__int64 InstallStateService()
{
  return InstallServices_0();
}

```

## disassembly

```asm
0x1800010c0  jmp     InstallServices_0
```
