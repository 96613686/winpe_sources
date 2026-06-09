# EEDBManager::OpenHKEY(ushort const *,ulong,HKEY__ * *)

- ea: `0x180018c14`
- end: `0x180018c4e`
- name: `?OpenHKEY@EEDBManager@@SAJPEBGKPEAPEAUHKEY__@@@Z`
- size: `58`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, unsigned int, HKEY *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180018bf0`
- `0x180019044`
- `0x180019a90`

## callees

- `0x180018c14`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018c30`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018c30`

## pseudocode

```c
LSTATUS __fastcall EEDBManager::OpenHKEY(LPCWSTR lpSubKey, __int64 a2, HKEY *phkResult)
{
  LSTATUS result; // eax

  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, phkResult);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180018c14  sub     rsp, 38h
0x180018c18  mov     [rsp+38h+phkResult], r8; phkResult
0x180018c1d  mov     rdx, rcx; lpSubKey
0x180018c20  xor     r8d, r8d; ulOptions
0x180018c23  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018c2a  mov     r9d, 20119h; samDesired
0x180018c30  call    cs:__imp_RegOpenKeyExW
0x180018c37  nop     dword ptr [rax+rax+00h]
0x180018c3c  test    eax, eax
0x180018c3e  jle     short loc_180018C48
0x180018c40  movzx   eax, ax
0x180018c43  or      eax, 80070000h
0x180018c48  add     rsp, 38h
0x180018c4c  retn
```
