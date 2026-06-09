# GetRegValueSize(ushort const *,ushort const *)

- ea: `0x180006a5c`
- end: `0x180006aef`
- name: `?GetRegValueSize@@YAKPEBG0@Z`
- size: `147`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callers

- `0x1800080f0`

## callees

- `0x180006a5c`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180006ac9`
- `ADVAPI32!RegQueryValueExW` at `0x180006ac9`
- `ADVAPI32!RegCloseKey` at `0x180006ae0`
- `ADVAPI32!RegCloseKey` at `0x180006ae0`
- `ADVAPI32!RegOpenKeyExW` at `0x180006a9a`
- `ADVAPI32!RegOpenKeyExW` at `0x180006a9a`

## string_xrefs

- `0x180006ab3`: `PendingFileRenameOperations`

## pseudocode

```c
__int64 __fastcall GetRegValueSize(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  int v5; // [rsp+4Ch] [rbp+14h]

  v5 = HIDWORD(a2);
  hKey = 0;
  cbData = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Session Manager", 0, 0x20019u, &hKey) )
  {
    if ( RegQueryValueExW(hKey, L"PendingFileRenameOperations", 0, 0, 0, &cbData) )
      cbData = 0;
    RegCloseKey(hKey);
  }
  return cbData;
}

```

## disassembly

```asm
0x180006a5c  mov     rax, rsp
0x180006a5f  mov     [rax+10h], rdx
0x180006a63  mov     [rax+8], rcx
0x180006a67  sub     rsp, 38h
0x180006a6b  mov     qword ptr [rax+8], 0
0x180006a73  mov     r9d, 20019h; samDesired
0x180006a79  mov     dword ptr [rax+10h], 0
0x180006a80  lea     rax, [rax+8]
0x180006a84  xor     r8d, r8d; ulOptions
0x180006a87  mov     [rsp+38h+phkResult], rax; phkResult
0x180006a8c  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Ses"...
0x180006a93  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006a9a  call    cs:__imp_RegOpenKeyExW
0x180006aa0  test    eax, eax
0x180006aa2  jnz     short loc_180006AE6
0x180006aa4  mov     rcx, [rsp+38h+hKey]; hKey
0x180006aa9  lea     rax, [rsp+38h+cbData]
0x180006aae  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180006ab3  lea     rdx, aPendingfileren; "PendingFileRenameOperations"
0x180006aba  xor     r9d, r9d; lpType
0x180006abd  mov     [rsp+38h+phkResult], 0; lpData
0x180006ac6  xor     r8d, r8d; lpReserved
0x180006ac9  call    cs:__imp_RegQueryValueExW
0x180006acf  test    eax, eax
0x180006ad1  jz      short loc_180006ADB
0x180006ad3  mov     [rsp+38h+cbData], 0
0x180006adb  mov     rcx, [rsp+38h+hKey]; hKey
0x180006ae0  call    cs:__imp_RegCloseKey
0x180006ae6  mov     eax, [rsp+38h+cbData]
0x180006aea  add     rsp, 38h
0x180006aee  retn
```
