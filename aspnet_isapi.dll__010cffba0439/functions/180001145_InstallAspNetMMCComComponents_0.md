# InstallAspNetMMCComComponents_0

- ea: `0x180001145`
- end: `0x18000114b`
- name: `InstallAspNetMMCComComponents_0`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800010a0`

## import_xrefs

- `webengine4!InstallAspNetMMCComComponents` at `0x180001145`

## pseudocode

```c
// attributes: thunk
__int64 InstallAspNetMMCComComponents_0()
{
  return InstallAspNetMMCComComponents();
}

```

## disassembly

```asm
0x180001145  jmp     cs:__imp_InstallAspNetMMCComComponents
```
