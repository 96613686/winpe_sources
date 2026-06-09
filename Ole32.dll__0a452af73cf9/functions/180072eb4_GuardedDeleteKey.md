# GuardedDeleteKey

- ea: `0x180072eb4`
- end: `0x180072fa9`
- name: `GuardedDeleteKey`
- size: `245`
- prototype: `void __fastcall(HKEY__ *hKey, const wchar_t *szSubKey)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18007317c`

## callees

- `0x180072eb4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072f67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072f95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072f67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072f95`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180072f8d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180072f8d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180072f58`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyA` at `0x180072f58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180072edf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180072edf`

## pseudocode

```c
void __fastcall GuardedDeleteKey(HKEY hKey, const wchar_t *szSubKey)
{
  HKEY__ *hSubkey; // [rsp+60h] [rbp-18h] BYREF
  unsigned int cSubKeys; // [rsp+90h] [rbp+18h] BYREF
  unsigned int cValues; // [rsp+98h] [rbp+20h] BYREF

  hSubkey = 0;
  if ( !RegOpenKeyExW(hKey, szSubKey, 0, 0x20019u, &hSubkey) )
  {
    cSubKeys = 0;
    cValues = 0;
    if ( RegQueryInfoKeyA(hSubkey, 0, 0, 0, &cSubKeys, 0, 0, &cValues, 0, 0, 0, 0) )
    {
      RegCloseKey(hSubkey);
    }
    else
    {
      RegCloseKey(hSubkey);
      if ( !cSubKeys && cValues <= 1 )
        RegDeleteKeyExW(hKey, szSubKey, 0, 0);
    }
  }
}

```

## disassembly

```asm
0x180072eb4  mov     r11, rsp
0x180072eb7  mov     [r11+8], rbx
0x180072ebb  push    rdi
0x180072ebc  sub     rsp, 70h
0x180072ec0  lea     rax, [r11-18h]
0x180072ec4  mov     qword ptr [r11-18h], 0
0x180072ecc  mov     r9d, 20019h; samDesired
0x180072ed2  mov     [r11-58h], rax
0x180072ed6  xor     r8d, r8d; ulOptions
0x180072ed9  mov     rbx, szSubKey
0x180072edc  mov     rdi, hKey
0x180072edf  call    cs:__imp_RegOpenKeyExW
0x180072ee5  test    eax, eax
0x180072ee7  jnz     loc_180072F9B
0x180072eed  mov     hKey, [rsp+78h+hSubkey]; hKey
0x180072ef2  xor     r9d, r9d; lpReserved
0x180072ef5  mov     [rsp+78h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180072efe  xor     r8d, r8d; lpcchClass
0x180072f01  mov     [rsp+78h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x180072f0a  xor     edx, edx; lpClass
0x180072f0c  mov     [rsp+78h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x180072f15  mov     [rsp+78h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x180072f1e  mov     [rsp+78h+cSubKeys], eax
0x180072f25  mov     [rsp+78h+cValues], eax
0x180072f2c  lea     rax, [rsp+78h+cValues]
0x180072f34  mov     [rsp+78h+lpcValues], rax; lpcValues
0x180072f39  lea     rax, [rsp+78h+cSubKeys]
0x180072f41  mov     [rsp+78h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x180072f4a  mov     [rsp+78h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x180072f53  mov     [rsp+78h+lpcSubKeys], rax; lpcSubKeys
0x180072f58  call    cs:__imp_RegQueryInfoKeyA
0x180072f5e  mov     hKey, [rsp+78h+hSubkey]; hKey
0x180072f63  test    eax, eax
0x180072f65  jnz     short loc_180072F95
0x180072f67  call    cs:__imp_RegCloseKey
0x180072f6d  cmp     [rsp+78h+cSubKeys], 0
0x180072f75  ja      short loc_180072F9B
0x180072f77  cmp     [rsp+78h+cValues], 1
0x180072f7f  ja      short loc_180072F9B
0x180072f81  xor     r9d, r9d; Reserved
0x180072f84  xor     r8d, r8d; samDesired
0x180072f87  mov     szSubKey, rbx; lpSubKey
0x180072f8a  mov     hKey, rdi; hKey
0x180072f8d  call    cs:__imp_RegDeleteKeyExW
0x180072f93  jmp     short loc_180072F9B
0x180072f95  call    cs:__imp_RegCloseKey
0x180072f9b  mov     rbx, [rsp+78h+arg_0]
0x180072fa3  add     rsp, 70h
0x180072fa7  pop     rdi
0x180072fa8  retn
```
