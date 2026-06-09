# GetAuthHostRegDWORDValue(ushort const *)

- ea: `0x140009214`
- end: `0x1400092c5`
- name: `?GetAuthHostRegDWORDValue@@YAKPEBG@Z`
- size: `177`
- prototype: `unsigned int __fastcall(LPCWSTR lpValueName)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000a4b0`
- `0x14000ad80`
- `0x14000b840`
- `0x140012500`

## callees

- `0x140009214`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400092b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400092b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140009261`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140009261`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000928b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000928b`

## pseudocode

```c
__int64 __fastcall GetAuthHostRegDWORDValue(LPCWSTR lpValueName)
{
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  unsigned int Data; // [rsp+58h] [rbp+18h] BYREF
  DWORD Type; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF

  Data = 0;
  cbData = 4;
  Type = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Image File Execution Options\\authhost.exe",
          0,
          0x20019u,
          &hKey)
    && (RegQueryValueExW(hKey, lpValueName, 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 || cbData != 4) )
  {
    Data = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return Data;
}

```

## disassembly

```asm
0x140009214  mov     [rsp-8+arg_0], rbx
0x140009219  push    rbp
0x14000921a  mov     rbp, rsp
0x14000921d  sub     rsp, 40h
0x140009221  mov     rbx, rcx
0x140009224  mov     [rbp+Data], 0
0x14000922b  lea     rax, [rbp+hKey]
0x14000922f  mov     [rbp+cbData], 4
0x140009236  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000923d  mov     [rsp+40h+phkResult], rax; phkResult
0x140009242  mov     r9d, 20019h; samDesired
0x140009248  mov     [rbp+Type], 0
0x14000924f  xor     r8d, r8d; ulOptions
0x140009252  mov     [rbp+hKey], 0
0x14000925a  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140009261  call    cs:__imp_RegOpenKeyExW
0x140009267  test    eax, eax
0x140009269  jnz     short loc_1400092A8
0x14000926b  mov     rcx, [rbp+hKey]; hKey
0x14000926f  lea     rax, [rbp+cbData]
0x140009273  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140009278  lea     r9, [rbp+Type]; lpType
0x14000927c  lea     rax, [rbp+Data]
0x140009280  xor     r8d, r8d; lpReserved
0x140009283  mov     rdx, rbx; lpValueName
0x140009286  mov     [rsp+40h+phkResult], rax; lpData
0x14000928b  call    cs:__imp_RegQueryValueExW
0x140009291  test    eax, eax
0x140009293  jnz     short loc_1400092A1
0x140009295  cmp     [rbp+Type], 4
0x140009299  jnz     short loc_1400092A1
0x14000929b  cmp     [rbp+cbData], 4
0x14000929f  jz      short loc_1400092A8
0x1400092a1  mov     [rbp+Data], 0
0x1400092a8  mov     rcx, [rbp+hKey]; hKey
0x1400092ac  test    rcx, rcx
0x1400092af  jz      short loc_1400092B7
0x1400092b1  call    cs:__imp_RegCloseKey
0x1400092b7  mov     eax, [rbp+Data]
0x1400092ba  mov     rbx, [rsp+40h+arg_0]
0x1400092bf  add     rsp, 40h
0x1400092c3  pop     rbp
0x1400092c4  retn
```
