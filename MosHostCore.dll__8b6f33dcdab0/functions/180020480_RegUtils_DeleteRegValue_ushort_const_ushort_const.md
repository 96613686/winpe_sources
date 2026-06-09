# RegUtils::DeleteRegValue(ushort const *,ushort const *)

- ea: `0x180020480`
- end: `0x1800204b7`
- name: `?DeleteRegValue@RegUtils@@SAJPEBG0@Z`
- size: `55`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001dee8`
- `0x1800203f0`

## callees

- `0x180020480`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180020491`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180020491`

## pseudocode

```c
__int64 __fastcall RegUtils::DeleteRegValue(LPCWSTR lpSubKey, LPCWSTR lpValueName)
{
  LSTATUS v2; // ecx

  v2 = RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, lpSubKey, lpValueName);
  if ( v2 == 2 )
    return 0;
  if ( v2 > 0 )
    return (unsigned __int16)v2 | 0x80070000;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180020480  sub     rsp, 28h
0x180020484  mov     r8, rdx; lpValueName
0x180020487  mov     rdx, rcx; lpSubKey
0x18002048a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180020491  call    cs:__imp_RegDeleteKeyValueW
0x180020497  mov     ecx, eax
0x180020499  cmp     eax, 2
0x18002049c  jnz     short loc_1800204A2
0x18002049e  xor     eax, eax
0x1800204a0  jmp     short loc_1800204B2
0x1800204a2  test    ecx, ecx
0x1800204a4  jg      short loc_1800204AA
0x1800204a6  mov     eax, ecx
0x1800204a8  jmp     short loc_1800204B2
0x1800204aa  movzx   eax, cx
0x1800204ad  or      eax, 80070000h
0x1800204b2  add     rsp, 28h
0x1800204b6  retn
```
