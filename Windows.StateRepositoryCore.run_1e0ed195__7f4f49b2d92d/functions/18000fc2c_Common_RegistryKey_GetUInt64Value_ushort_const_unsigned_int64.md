# Common::RegistryKey::GetUInt64Value(ushort const *,unsigned __int64 *)

- ea: `0x18000fc2c`
- end: `0x18000fc67`
- name: `?GetUInt64Value@RegistryKey@Common@@QEAAJPEBGPEA_K@Z`
- size: `59`
- prototype: `int(Common::RegistryKey *__hidden this, const unsigned __int16 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cfa0`
- `0x18000d810`

## callees

- `0x18000fc2c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fc50`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fc50`

## pseudocode

```c
LSTATUS __fastcall Common::RegistryKey::GetUInt64Value(HKEY *this, const unsigned __int16 *a2, BYTE *lpData)
{
  HKEY v3; // rcx
  LSTATUS result; // eax
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF

  v3 = *this;
  cbData = 8;
  result = RegQueryValueExW(v3, a2, 0, 0, lpData, &cbData);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000fc2c  sub     rsp, 38h
0x18000fc30  mov     rcx, [rcx]; hKey
0x18000fc33  lea     rax, [rsp+38h+cbData]
0x18000fc38  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000fc3d  xor     r9d, r9d; lpType
0x18000fc40  mov     [rsp+38h+lpData], r8; lpData
0x18000fc45  xor     r8d, r8d; lpReserved
0x18000fc48  mov     [rsp+38h+cbData], 8
0x18000fc50  call    cs:__imp_RegQueryValueExW
0x18000fc56  test    eax, eax
0x18000fc58  jle     short loc_18000FC62
0x18000fc5a  movzx   eax, ax
0x18000fc5d  or      eax, 80070000h
0x18000fc62  add     rsp, 38h
0x18000fc66  retn
```
