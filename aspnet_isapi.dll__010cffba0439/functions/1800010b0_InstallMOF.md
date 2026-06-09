# InstallMOF

- ea: `0x1800010b0`
- end: `0x1800010b5`
- name: `InstallMOF`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000113f`

## pseudocode

```c
// attributes: thunk
__int64 InstallMOF()
{
  return InstallAspNetMOF_0();
}

```

## disassembly

```asm
0x1800010b0  jmp     InstallAspNetMOF_0
```
