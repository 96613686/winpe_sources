# InstallAspNetMOF_0

- ea: `0x18000113f`
- end: `0x180001145`
- name: `InstallAspNetMOF_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800010b0`

## import_xrefs

- `webengine4!InstallAspNetMOF` at `0x18000113f`

## pseudocode

```c
// attributes: thunk
__int64 InstallAspNetMOF_0()
{
  return InstallAspNetMOF();
}

```

## disassembly

```asm
0x18000113f  jmp     cs:__imp_InstallAspNetMOF
```
