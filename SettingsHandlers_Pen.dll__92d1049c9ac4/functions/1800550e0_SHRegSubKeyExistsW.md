# SHRegSubKeyExistsW

- ea: `0x1800550e0`
- end: `0x18005512a`
- name: `SHRegSubKeyExistsW`
- size: `74`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180027350`
- `0x180028910`

## callees

- `0x1800550e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180055108`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180055108`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180055117`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180055117`

## pseudocode

```c
__int64 __fastcall SHRegSubKeyExistsW(__int64 a1, const WCHAR *a2)
{
  unsigned int v2; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v2 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 1u, &hKey) )
  {
    RegCloseKey(hKey);
    return 1;
  }
  return v2;
}

```

## disassembly

```asm
0x1800550e0  mov     r11, rsp
0x1800550e3  mov     [r11+8], rcx
0x1800550e7  push    rbx
0x1800550e8  sub     rsp, 30h
0x1800550ec  xor     ebx, ebx
0x1800550ee  lea     rax, [r11+8]
0x1800550f2  xor     r8d, r8d; ulOptions
0x1800550f5  mov     [r11+8], rbx
0x1800550f9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180055100  mov     [r11-18h], rax
0x180055104  lea     r9d, [rbx+1]; samDesired
0x180055108  call    cs:__imp_RegOpenKeyExW
0x18005510e  test    eax, eax
0x180055110  jnz     short loc_180055122
0x180055112  mov     rcx, [rsp+38h+hKey]; hKey
0x180055117  call    cs:__imp_RegCloseKey
0x18005511d  mov     ebx, 1
0x180055122  mov     eax, ebx
0x180055124  add     rsp, 30h
0x180055128  pop     rbx
0x180055129  retn
```
