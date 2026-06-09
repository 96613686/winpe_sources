# GetNumberOfValues(ushort const *)

- ea: `0x180006994`
- end: `0x180006a54`
- name: `?GetNumberOfValues@@YAKPEBG@Z`
- size: `192`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callers

- `0x1800080f0`

## callees

- `0x180006994`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180006a45`
- `ADVAPI32!RegCloseKey` at `0x180006a45`
- `ADVAPI32!RegOpenKeyExW` at `0x1800069ce`
- `ADVAPI32!RegOpenKeyExW` at `0x1800069ce`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180006a2e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180006a2e`

## string_xrefs

- `0x1800069c0`: `System\CurrentControlSet\Control\Session Manager\FileRenameOperations`

## pseudocode

```c
__int64 __fastcall GetNumberOfValues(const unsigned __int16 *a1)
{
  DWORD cValues; // [rsp+70h] [rbp+8h] BYREF
  int v3; // [rsp+74h] [rbp+Ch]
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  v3 = HIDWORD(a1);
  hKey = 0;
  cValues = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Control\\Session Manager\\FileRenameOperations",
          0,
          0x20019u,
          &hKey) )
  {
    if ( RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0) )
      cValues = 0;
    RegCloseKey(hKey);
  }
  return cValues;
}

```

## disassembly

```asm
0x180006994  mov     rax, rsp
0x180006997  mov     [rax+8], rcx
0x18000699b  sub     rsp, 68h
0x18000699f  mov     qword ptr [rax+10h], 0
0x1800069a7  mov     r9d, 20019h; samDesired
0x1800069ad  mov     dword ptr [rax+8], 0
0x1800069b4  lea     rax, [rax+10h]
0x1800069b8  xor     r8d, r8d; ulOptions
0x1800069bb  mov     [rsp+68h+phkResult], rax; phkResult
0x1800069c0  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Ses"...
0x1800069c7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800069ce  call    cs:__imp_RegOpenKeyExW
0x1800069d4  test    eax, eax
0x1800069d6  jnz     short loc_180006A4B
0x1800069d8  mov     rcx, [rsp+68h+hKey]; hKey
0x1800069dd  lea     rax, [rsp+68h+cValues]
0x1800069e2  mov     [rsp+68h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800069eb  xor     r9d, r9d; lpReserved
0x1800069ee  mov     [rsp+68h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x1800069f7  xor     r8d, r8d; lpcchClass
0x1800069fa  mov     [rsp+68h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x180006a03  xor     edx, edx; lpClass
0x180006a05  mov     [rsp+68h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x180006a0e  mov     [rsp+68h+lpcValues], rax; lpcValues
0x180006a13  mov     [rsp+68h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x180006a1c  mov     [rsp+68h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x180006a25  mov     [rsp+68h+phkResult], 0; lpcSubKeys
0x180006a2e  call    cs:__imp_RegQueryInfoKeyW
0x180006a34  test    eax, eax
0x180006a36  jz      short loc_180006A40
0x180006a38  mov     [rsp+68h+cValues], 0
0x180006a40  mov     rcx, [rsp+68h+hKey]; hKey
0x180006a45  call    cs:__imp_RegCloseKey
0x180006a4b  mov     eax, [rsp+68h+cValues]
0x180006a4f  add     rsp, 68h
0x180006a53  retn
```
