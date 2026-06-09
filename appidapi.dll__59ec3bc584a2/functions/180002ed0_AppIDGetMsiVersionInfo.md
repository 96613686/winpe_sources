# AppIDGetMsiVersionInfo

- ea: `0x180002ed0`
- end: `0x180002ed5`
- name: `AppIDGetMsiVersionInfo`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180005740`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall AppIDGetMsiVersionInfo(
        LPCWSTR szDatabasePath,
        _DWORD *a2,
        _DWORD *a3,
        _DWORD *a4,
        _DWORD *a5,
        __int64 a6,
        __int64 a7)
{
  return AiGetMsiVersionInfo(szDatabasePath, a2, a3, a4, a5, a6, a7);
}

```

## disassembly

```asm
0x180002ed0  jmp     AiGetMsiVersionInfo
```
