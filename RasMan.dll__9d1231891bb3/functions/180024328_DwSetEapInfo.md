# DwSetEapInfo

- ea: `0x180024328`
- end: `0x180024351`
- name: `DwSetEapInfo`
- size: `41`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180024140`
- `0x18002420c`
- `0x180024358`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180024346`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180024346`

## pseudocode

```c
LSTATUS __fastcall DwSetEapInfo(HKEY a1, const BYTE *lpData, DWORD cbData)
{
  return RegSetValueExW(a1, L"EapInfo", 0, 3u, lpData, cbData);
}

```

## disassembly

```asm
0x180024328  sub     rsp, 38h
0x18002432c  mov     [rsp+38h+cbData], r8d; cbData
0x180024331  mov     r9d, 3; dwType
0x180024337  mov     [rsp+38h+lpData], rdx; lpData
0x18002433c  xor     r8d, r8d; Reserved
0x18002433f  lea     rdx, aEapinfo; "EapInfo"
0x180024346  call    cs:__imp_RegSetValueExW
0x18002434c  add     rsp, 38h
0x180024350  retn
```
