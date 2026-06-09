# ConnectedStorage::GetStorageServiceTestFlags(void)

- ea: `0x180014f34`
- end: `0x180014fd3`
- name: `?GetStorageServiceTestFlags@ConnectedStorage@@YAKXZ`
- size: `159`
- prototype: `unsigned int __fastcall(ConnectedStorage *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180014280`
- `0x180014444`
- `0x1800558c0`

## callees

- `0x180014f34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014f6c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014f6c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014faf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014faf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014fc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014fc4`

## string_xrefs

- `0x180014f5e`: `System\CurrentControlSet\Services\XblGameSave\Parameters`

## pseudocode

```c
__int64 __fastcall ConnectedStorage::GetStorageServiceTestFlags(ConnectedStorage *this)
{
  unsigned int pvData; // [rsp+50h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+18h] BYREF
  DWORD pdwType; // [rsp+60h] [rbp+20h] BYREF
  HKEY hkey; // [rsp+68h] [rbp+28h] BYREF

  pvData = 0;
  hkey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\XblGameSave\\Parameters",
          0,
          0x20019u,
          &hkey) )
  {
    pdwType = 4;
    pcbData = 4;
    if ( RegGetValueW(hkey, 0, L"TestFlags", 0x10u, &pdwType, &pvData, &pcbData) )
      pvData = 0;
    RegCloseKey(hkey);
  }
  return pvData;
}

```

## disassembly

```asm
0x180014f34  push    rbp
0x180014f36  mov     rbp, rsp
0x180014f39  sub     rsp, 40h
0x180014f3d  lea     rax, [rbp+hkey]
0x180014f41  mov     [rbp+arg_0], 0
0x180014f48  mov     r9d, 20019h; samDesired
0x180014f4e  mov     [rsp+40h+phkResult], rax; phkResult
0x180014f53  xor     r8d, r8d; ulOptions
0x180014f56  mov     [rbp+hkey], 0
0x180014f5e  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Xb"...
0x180014f65  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014f6c  call    cs:__imp_RegOpenKeyExW
0x180014f72  test    eax, eax
0x180014f74  jnz     short loc_180014FCA
0x180014f76  mov     rcx, [rbp+hkey]; hkey
0x180014f7a  lea     r8, aTestflags; "TestFlags"
0x180014f81  mov     eax, 4
0x180014f86  mov     r9d, 10h; dwFlags
0x180014f8c  mov     [rbp+pdwType], eax
0x180014f8f  xor     edx, edx; lpSubKey
0x180014f91  mov     [rbp+arg_8], eax
0x180014f94  lea     rax, [rbp+arg_8]
0x180014f98  mov     [rsp+40h+pcbData], rax; pcbData
0x180014f9d  lea     rax, [rbp+arg_0]
0x180014fa1  mov     [rsp+40h+pvData], rax; pvData
0x180014fa6  lea     rax, [rbp+pdwType]
0x180014faa  mov     [rsp+40h+phkResult], rax; pdwType
0x180014faf  call    cs:__imp_RegGetValueW
0x180014fb5  test    eax, eax
0x180014fb7  jz      short loc_180014FC0
0x180014fb9  mov     [rbp+arg_0], 0
0x180014fc0  mov     rcx, [rbp+hkey]; hKey
0x180014fc4  call    cs:__imp_RegCloseKey
0x180014fca  mov     eax, [rbp+arg_0]
0x180014fcd  add     rsp, 40h
0x180014fd1  pop     rbp
0x180014fd2  retn
```
