# UtilIsWinPE(void)

- ea: `0x140018390`
- end: `0x140018414`
- name: `?UtilIsWinPE@@YA_NXZ`
- size: `132`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000e49c`
- `0x14001b9dc`

## callees

- `0x140018390`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400183f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018406`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400183f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140018406`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400183cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400183cf`

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
0x140018390  mov     r11, rsp
0x140018393  push    rbx
0x140018394  sub     rsp, 50h
0x140018398  lea     rax, [r11+8]
0x14001839c  mov     qword ptr [r11-28h], 0
0x1400183a4  mov     [r11-20h], rax
0x1400183a8  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x1400183af  lea     rax, [r11-28h]
0x1400183b3  mov     qword ptr [r11+8], 0
0x1400183bb  mov     r9d, 20019h; samDesired
0x1400183c1  mov     [r11-38h], rax
0x1400183c5  xor     r8d, r8d; ulOptions
0x1400183c8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400183cf  call    cs:__imp_RegOpenKeyExW
0x1400183d5  mov     r8, [rsp+58h+var_28]
0x1400183da  mov     ebx, eax
0x1400183dc  test    r8, r8
0x1400183df  jz      short loc_1400183F7
0x1400183e1  mov     rdx, [rsp+58h+var_20]
0x1400183e6  mov     rcx, [rdx]; hKey
0x1400183e9  mov     [rdx], r8
0x1400183ec  test    rcx, rcx
0x1400183ef  jz      short loc_1400183F7
0x1400183f1  call    cs:__imp_RegCloseKey
0x1400183f7  mov     rcx, [rsp+58h+hKey]; hKey
0x1400183fc  test    ebx, ebx
0x1400183fe  setz    bl
0x140018401  test    rcx, rcx
0x140018404  jz      short loc_14001840C
0x140018406  call    cs:__imp_RegCloseKey
0x14001840c  mov     al, bl
0x14001840e  add     rsp, 50h
0x140018412  pop     rbx
0x140018413  retn
```
