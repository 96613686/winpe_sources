# GetLocalDTCProfileInt(char const *,ulong)

- ea: `0x18000f370`
- end: `0x18000f423`
- name: `?GetLocalDTCProfileInt@@YAKPEBDK@Z`
- size: `179`
- prototype: `unsigned int __fastcall(LPCSTR lpValueName, unsigned int)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d3d0`
- `0x180010b40`
- `0x180013e24`
- `0x18001db80`
- `0x18002511c`
- `0x180084698`
- `0x180084880`

## callees

- `0x18000f370`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000f3b7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000f3b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000f3e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000f3e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f40a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f40a`

## pseudocode

```c
__int64 __fastcall GetLocalDTCProfileInt(LPCSTR lpValueName, unsigned int a2)
{
  unsigned int v2; // edi
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  unsigned int Data; // [rsp+58h] [rbp+10h] BYREF
  DWORD Type; // [rsp+60h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+20h] BYREF

  Data = a2;
  hKey = 0;
  v2 = a2;
  Type = 0;
  cbData = 4;
  if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, "Software\\Microsoft\\MSDTC", 0, 0x20119u, &hKey)
    || RegQueryValueExA(hKey, lpValueName, 0, &Type, (LPBYTE)&Data, &cbData)
    || Type != 4 )
  {
    Data = v2;
  }
  else
  {
    v2 = Data;
  }
  if ( !hKey )
    return v2;
  RegCloseKey(hKey);
  return Data;
}

```

## disassembly

```asm
0x18000f370  mov     [rsp+arg_0], rbx
0x18000f375  push    rdi
0x18000f376  sub     rsp, 40h
0x18000f37a  xor     eax, eax
0x18000f37c  mov     [rsp+48h+Data], edx
0x18000f380  mov     [rsp+48h+hKey], rax
0x18000f385  mov     edi, edx
0x18000f387  mov     [rsp+48h+Type], eax
0x18000f38b  lea     rdx, SubKey; "Software\\Microsoft\\MSDTC"
0x18000f392  lea     rax, [rsp+48h+hKey]
0x18000f397  mov     [rsp+48h+cbData], 4
0x18000f39f  mov     rbx, rcx
0x18000f3a2  mov     [rsp+48h+phkResult], rax; phkResult
0x18000f3a7  mov     r9d, 20119h; samDesired
0x18000f3ad  xor     r8d, r8d; ulOptions
0x18000f3b0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f3b7  call    cs:__imp_RegOpenKeyExA
0x18000f3bd  test    eax, eax
0x18000f3bf  jnz     short loc_18000F3FC
0x18000f3c1  mov     rcx, [rsp+48h+hKey]; hKey
0x18000f3c6  lea     rax, [rsp+48h+cbData]
0x18000f3cb  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18000f3d0  lea     r9, [rsp+48h+Type]; lpType
0x18000f3d5  lea     rax, [rsp+48h+Data]
0x18000f3da  xor     r8d, r8d; lpReserved
0x18000f3dd  mov     rdx, rbx; lpValueName
0x18000f3e0  mov     [rsp+48h+phkResult], rax; lpData
0x18000f3e5  call    cs:__imp_RegQueryValueExA
0x18000f3eb  test    eax, eax
0x18000f3ed  jnz     short loc_18000F3FC
0x18000f3ef  cmp     [rsp+48h+Type], 4
0x18000f3f4  jnz     short loc_18000F3FC
0x18000f3f6  mov     edi, [rsp+48h+Data]
0x18000f3fa  jmp     short loc_18000F400
0x18000f3fc  mov     [rsp+48h+Data], edi
0x18000f400  mov     rcx, [rsp+48h+hKey]; hKey
0x18000f405  test    rcx, rcx
0x18000f408  jz      short loc_18000F416
0x18000f40a  call    cs:__imp_RegCloseKey
0x18000f410  mov     eax, [rsp+48h+Data]
0x18000f414  jmp     short loc_18000F418
0x18000f416  mov     eax, edi
0x18000f418  mov     rbx, [rsp+48h+arg_0]
0x18000f41d  add     rsp, 40h
0x18000f421  pop     rdi
0x18000f422  retn
```
