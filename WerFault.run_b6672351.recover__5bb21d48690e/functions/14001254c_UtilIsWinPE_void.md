# UtilIsWinPE(void)

- ea: `0x14001254c`
- end: `0x1400125e3`
- name: `?UtilIsWinPE@@YA_NXZ`
- size: `151`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000ddb8`
- `0x14005e9f8`

## callees

- `0x14001254c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400125b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400125ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400125b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400125ce`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001258b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001258b`

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
0x14001254c  mov     r11, rsp
0x14001254f  push    rbx
0x140012550  sub     rsp, 50h
0x140012554  lea     rax, [r11+8]
0x140012558  mov     qword ptr [r11-28h], 0
0x140012560  mov     [r11-20h], rax
0x140012564  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Min"...
0x14001256b  lea     rax, [r11-28h]
0x14001256f  mov     qword ptr [r11+8], 0
0x140012577  mov     r9d, 20019h; samDesired
0x14001257d  mov     [r11-38h], rax
0x140012581  xor     r8d, r8d; ulOptions
0x140012584  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14001258b  call    cs:__imp_RegOpenKeyExW
0x140012592  nop     dword ptr [rax+rax+00h]
0x140012597  mov     r8, [rsp+58h+var_28]
0x14001259c  mov     ebx, eax
0x14001259e  test    r8, r8
0x1400125a1  jz      short loc_1400125BF
0x1400125a3  mov     rdx, [rsp+58h+var_20]
0x1400125a8  mov     rcx, [rdx]; hKey
0x1400125ab  mov     [rdx], r8
0x1400125ae  test    rcx, rcx
0x1400125b1  jz      short loc_1400125BF
0x1400125b3  call    cs:__imp_RegCloseKey
0x1400125ba  nop     dword ptr [rax+rax+00h]
0x1400125bf  mov     rcx, [rsp+58h+hKey]; hKey
0x1400125c4  test    ebx, ebx
0x1400125c6  setz    bl
0x1400125c9  test    rcx, rcx
0x1400125cc  jz      short loc_1400125DA
0x1400125ce  call    cs:__imp_RegCloseKey
0x1400125d5  nop     dword ptr [rax+rax+00h]
0x1400125da  mov     al, bl
0x1400125dc  add     rsp, 50h
0x1400125e0  pop     rbx
0x1400125e1  retn
```
