# HrRegOpenKeyExW

- ea: `0x18000bba0`
- end: `0x18000bbc5`
- name: `HrRegOpenKeyExW`
- size: `37`
- prototype: `__int64 __fastcall(int, int, int, int, PHKEY)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000b9e0`

## callees

- `0x18000bba0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18000bbae`
- `ADVAPI32!RegOpenKeyExW` at `0x18000bbae`

## pseudocode

```c
LSTATUS __fastcall HrRegOpenKeyExW(HKEY a1, const WCHAR *a2, DWORD a3, REGSAM a4, PHKEY phkResult)
{
  LSTATUS result; // eax

  result = RegOpenKeyExW(a1, a2, a3, a4, phkResult);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000bba0  sub     rsp, 38h
0x18000bba4  mov     rax, [rsp+38h+arg_20]
0x18000bba9  mov     [rsp+38h+phkResult], rax; phkResult
0x18000bbae  call    cs:__imp_RegOpenKeyExW
0x18000bbb4  test    eax, eax
0x18000bbb6  jle     short loc_18000BBC0
0x18000bbb8  movzx   eax, ax
0x18000bbbb  or      eax, 80070000h
0x18000bbc0  add     rsp, 38h
0x18000bbc4  retn
```
