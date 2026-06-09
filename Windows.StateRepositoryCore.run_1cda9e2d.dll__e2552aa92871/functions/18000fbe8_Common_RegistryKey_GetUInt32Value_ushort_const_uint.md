# Common::RegistryKey::GetUInt32Value(ushort const *,uint *)

- ea: `0x18000fbe8`
- end: `0x18000fc23`
- name: `?GetUInt32Value@RegistryKey@Common@@QEAAJPEBGPEAI@Z`
- size: `59`
- prototype: `int(Common::RegistryKey *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cf30`
- `0x18000d4d0`

## callees

- `0x18000fbe8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fc0c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fc0c`

## pseudocode

```c
LSTATUS __fastcall Common::RegistryKey::GetUInt32Value(HKEY *this, const unsigned __int16 *a2, BYTE *lpData)
{
  HKEY v3; // rcx
  LSTATUS result; // eax
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF

  v3 = *this;
  cbData = 4;
  result = RegQueryValueExW(v3, a2, 0, 0, lpData, &cbData);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000fbe8  sub     rsp, 38h
0x18000fbec  mov     rcx, [rcx]; hKey
0x18000fbef  lea     rax, [rsp+38h+cbData]
0x18000fbf4  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000fbf9  xor     r9d, r9d; lpType
0x18000fbfc  mov     [rsp+38h+lpData], r8; lpData
0x18000fc01  xor     r8d, r8d; lpReserved
0x18000fc04  mov     [rsp+38h+cbData], 4
0x18000fc0c  call    cs:__imp_RegQueryValueExW
0x18000fc12  test    eax, eax
0x18000fc14  jle     short loc_18000FC1E
0x18000fc16  movzx   eax, ax
0x18000fc19  or      eax, 80070000h
0x18000fc1e  add     rsp, 38h
0x18000fc22  retn
```
