# CAutoTask<DBCOLUMNUPDATEINFO>::~CAutoTask<DBCOLUMNUPDATEINFO>(void)

- ea: `0x180002690`
- end: `0x18000269a`
- name: `??1?$CAutoTask@UDBCOLUMNUPDATEINFO@@@@QEAA@XZ`
- size: `10`
- prototype: ``
- caller_count: `12`
- callee_count: `0`
- tags: `service_task, installer_update`

## callers

- `0x18002e5a4`
- `0x18002e5b6`
- `0x18002e5c8`
- `0x18002e634`
- `0x18002e646`
- `0x18002e6df`
- `0x18002eb1c`
- `0x18002eb5e`
- `0x18002eb70`
- `0x18002eb82`
- `0x18002efc4`
- `0x18002efd6`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180002693`

## pseudocode

```c
void __fastcall CAutoTask<DBCOLUMNUPDATEINFO>::~CAutoTask<DBCOLUMNUPDATEINFO>(LPVOID *a1)
{
  CoTaskMemFree(*a1);
}

```

## disassembly

```asm
0x180002690  mov     rcx, [rcx]
0x180002693  jmp     cs:__imp_CoTaskMemFree
```
