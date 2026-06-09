# ATL::CRegKey::SetQWORDValue(ushort const *,unsigned __int64)

- ea: `0x18003a0dc`
- end: `0x18003a10e`
- name: `?SetQWORDValue@CRegKey@ATL@@QEAAJPEBG_K@Z`
- size: `50`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18003415c`
- `0x18003c92c`
- `0x180060f8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003a103`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003a103`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::SetQWORDValue(HKEY *this, const unsigned __int16 *a2, __int64 a3)
{
  __int64 Data; // [rsp+50h] [rbp+18h] BYREF

  Data = a3;
  return RegSetValueExW(*this, a2, 0, 0xBu, (const BYTE *)&Data, 8u);
}

```

## disassembly

```asm
0x18003a0dc  mov     [rsp+Data], r8
0x18003a0e1  sub     rsp, 38h
0x18003a0e5  mov     rcx, [rcx]; hKey
0x18003a0e8  lea     rax, [rsp+38h+Data]
0x18003a0ed  mov     [rsp+38h+cbData], 8; cbData
0x18003a0f5  mov     r9d, 0Bh; dwType
0x18003a0fb  xor     r8d, r8d; Reserved
0x18003a0fe  mov     [rsp+38h+lpData], rax; lpData
0x18003a103  call    cs:__imp_RegSetValueExW
0x18003a109  add     rsp, 38h
0x18003a10d  retn
```
