# InstallMMCComComponents

- ea: `0x1800010a0`
- end: `0x1800010a5`
- name: `InstallMMCComComponents`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001145`

## pseudocode

```c
// attributes: thunk
__int64 InstallMMCComComponents()
{
  return InstallAspNetMMCComComponents_0();
}

```

## disassembly

```asm
0x1800010a0  jmp     InstallAspNetMMCComComponents_0
```
