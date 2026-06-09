# MsiEvaluateConditionW

- ea: `0x1000996e`
- end: `0x10009974`
- name: `MsiEvaluateConditionW`
- size: `6`
- prototype: `MSICONDITION __stdcall(MSIHANDLE hInstall, LPCWSTR szCondition)`
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x100015c4`

## import_xrefs

- `msi!__imp_MsiEvaluateConditionW` at `0x1000996e`

## pseudocode

```c
// attributes: thunk
MSICONDITION __stdcall MsiEvaluateConditionW(MSIHANDLE hInstall, LPCWSTR szCondition)
{
  return __imp_MsiEvaluateConditionW(hInstall, szCondition);
}

```

## disassembly

```asm
0x1000996e  jmp     ds:__imp_MsiEvaluateConditionW
```
