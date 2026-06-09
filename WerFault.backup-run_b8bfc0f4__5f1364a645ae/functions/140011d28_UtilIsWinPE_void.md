# UtilIsWinPE(void)

- ea: `0x140011d28`
- end: `0x140011dac`
- name: `?UtilIsWinPE@@YA_NXZ`
- size: `132`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000d9f0`
- `0x14005acd0`

## callees

- `0x140011d28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011d89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011d9e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011d89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140011d9e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011d67`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140011d67`

## pseudocode

```c
bool UtilIsWinPE(void)
{
  LSTATUS v0; // ebx
  HKEY v1; // rcx
  bool v2; // bl
  HKEY v4; // [rsp+30h] [rbp-28h] BYREF
  HKEY *p_hKey; // [rsp+38h] [rbp-20h]
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  v4 = 0;
  p_hKey = &hKey;
  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MiniNT", 0, 0x20019u, &v4);
  if ( v4 )
  {
    v1 = *p_hKey;
    *p_hKey = v4;
    if ( v1 )
      RegCloseKey(v1);
  }
  v2 = v0 == 0;
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x140011d28  mov     r11, rsp
0x140011d2b  push    rbx
0x140011d2c  sub     rsp, 50h
0x140011d30  lea     rax, [r11+8]
0x140011d34  mov     qword ptr [r11-28h], 0
0x140011d3c  mov     [r11-20h], rax
0x140011d40  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x140011d47  lea     rax, [r11-28h]
0x140011d4b  mov     qword ptr [r11+8], 0
0x140011d53  mov     r9d, 20019h; samDesired
0x140011d59  mov     [r11-38h], rax
0x140011d5d  xor     r8d, r8d; ulOptions
0x140011d60  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140011d67  call    cs:__imp_RegOpenKeyExW
0x140011d6d  mov     r8, [rsp+58h+var_28]
0x140011d72  mov     ebx, eax
0x140011d74  test    r8, r8
0x140011d77  jz      short loc_140011D8F
0x140011d79  mov     rdx, [rsp+58h+var_20]
0x140011d7e  mov     rcx, [rdx]; hKey
0x140011d81  mov     [rdx], r8
0x140011d84  test    rcx, rcx
0x140011d87  jz      short loc_140011D8F
0x140011d89  call    cs:__imp_RegCloseKey
0x140011d8f  mov     rcx, [rsp+58h+hKey]; hKey
0x140011d94  test    ebx, ebx
0x140011d96  setz    bl
0x140011d99  test    rcx, rcx
0x140011d9c  jz      short loc_140011DA4
0x140011d9e  call    cs:__imp_RegCloseKey
0x140011da4  mov     al, bl
0x140011da6  add     rsp, 50h
0x140011daa  pop     rbx
0x140011dab  retn
```
