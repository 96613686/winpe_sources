# GetRefCountFrReg(ushort const *)

- ea: `0x180015e48`
- end: `0x180015eef`
- name: `?GetRefCountFrReg@@YAKPEBG@Z`
- size: `167`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016268`
- `0x180016c0c`

## callees

- `0x180015e48`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180015ec6`
- `ADVAPI32!RegQueryValueExW` at `0x180015ec6`
- `ADVAPI32!RegCloseKey` at `0x180015edb`
- `ADVAPI32!RegCloseKey` at `0x180015edb`
- `ADVAPI32!RegOpenKeyExW` at `0x180015e95`
- `ADVAPI32!RegOpenKeyExW` at `0x180015e95`

## string_xrefs

- `0x180015e8e`: `Software\Microsoft\Windows\CurrentVersion\SharedDlls`

## pseudocode

```c
__int64 __fastcall GetRefCountFrReg(LPCWSTR lpValueName)
{
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  unsigned int Data; // [rsp+58h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  DWORD Type; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  Data = 0;
  Type = 0;
  cbData = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\SharedDlls",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 4;
    if ( RegQueryValueExW(hKey, lpValueName, 0, &Type, (LPBYTE)&Data, &cbData) )
      Data = 0;
    RegCloseKey(hKey);
  }
  return Data;
}

```

## disassembly

```asm
0x180015e48  mov     [rsp-8+arg_0], rbx
0x180015e4d  push    rbp
0x180015e4e  mov     rbp, rsp
0x180015e51  sub     rsp, 40h
0x180015e55  mov     rbx, rcx
0x180015e58  mov     [rbp+hKey], 0
0x180015e60  lea     rax, [rbp+hKey]
0x180015e64  mov     [rbp+Data], 0
0x180015e6b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015e72  mov     [rsp+40h+phkResult], rax; phkResult
0x180015e77  mov     r9d, 20019h; samDesired
0x180015e7d  mov     [rbp+Type], 0
0x180015e84  xor     r8d, r8d; ulOptions
0x180015e87  mov     [rbp+cbData], 0
0x180015e8e  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180015e95  call    cs:__imp_RegOpenKeyExW
0x180015e9b  test    eax, eax
0x180015e9d  jnz     short loc_180015EE1
0x180015e9f  mov     rcx, [rbp+hKey]; hKey
0x180015ea3  lea     rax, [rbp+cbData]
0x180015ea7  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180015eac  lea     r9, [rbp+Type]; lpType
0x180015eb0  lea     rax, [rbp+Data]
0x180015eb4  mov     [rbp+cbData], 4
0x180015ebb  xor     r8d, r8d; lpReserved
0x180015ebe  mov     [rsp+40h+phkResult], rax; lpData
0x180015ec3  mov     rdx, rbx; lpValueName
0x180015ec6  call    cs:__imp_RegQueryValueExW
0x180015ecc  test    eax, eax
0x180015ece  jz      short loc_180015ED7
0x180015ed0  mov     [rbp+Data], 0
0x180015ed7  mov     rcx, [rbp+hKey]; hKey
0x180015edb  call    cs:__imp_RegCloseKey
0x180015ee1  mov     eax, [rbp+Data]
0x180015ee4  mov     rbx, [rsp+40h+arg_0]
0x180015ee9  add     rsp, 40h
0x180015eed  pop     rbp
0x180015eee  retn
```
