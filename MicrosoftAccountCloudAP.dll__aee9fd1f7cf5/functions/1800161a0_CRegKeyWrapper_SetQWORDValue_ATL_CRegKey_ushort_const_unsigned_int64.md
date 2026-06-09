# CRegKeyWrapper::SetQWORDValue(ATL::CRegKey *,ushort const *,unsigned __int64)

- ea: `0x1800161a0`
- end: `0x1800161db`
- name: `?SetQWORDValue@CRegKeyWrapper@@UEAAJPEAVCRegKey@ATL@@PEBG_K@Z`
- size: `59`
- prototype: `int(CRegKeyWrapper *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800161d0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800161d0`

## pseudocode

```c
LSTATUS __fastcall CRegKeyWrapper::SetQWORDValue(
        CRegKeyWrapper *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        __int64 a4)
{
  __int64 Data; // [rsp+48h] [rbp+10h] BYREF

  Data = a4;
  return RegSetValueExW(*a2, a3, 0, 0xBu, (const BYTE *)&Data, 8u);
}

```

## disassembly

```asm
0x1800161a0  sub     rsp, 38h
0x1800161a4  mov     r10, rdx
0x1800161a7  mov     [rsp+38h+Data], r9
0x1800161ac  mov     rax, r8
0x1800161af  mov     [rsp+38h+cbData], 8; cbData
0x1800161b7  lea     rcx, [rsp+38h+Data]
0x1800161bc  mov     r9d, 0Bh; dwType
0x1800161c2  mov     [rsp+38h+lpData], rcx; lpData
0x1800161c7  xor     r8d, r8d; Reserved
0x1800161ca  mov     rcx, [r10]; hKey
0x1800161cd  mov     rdx, rax; lpValueName
0x1800161d0  call    cs:__imp_RegSetValueExW
0x1800161d6  add     rsp, 38h
0x1800161da  retn
```
