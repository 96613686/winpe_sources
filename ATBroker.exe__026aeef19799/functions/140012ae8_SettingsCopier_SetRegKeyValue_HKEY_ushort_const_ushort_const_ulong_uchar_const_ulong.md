# SettingsCopier::SetRegKeyValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar const *,ulong)

- ea: `0x140012ae8`
- end: `0x140012c4b`
- name: `?SetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBG1KPEBEK@Z`
- size: `355`
- prototype: `LSTATUS __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, DWORD dwType, BYTE *lpData, DWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, registry_config`

## callers

- `0x140011c60`

## callees

- `0x140012ae8`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x140012bc8`
- `ADVAPI32!RegQueryValueExW` at `0x140012bc8`
- `ADVAPI32!RegOpenKeyExW` at `0x140012b9a`
- `ADVAPI32!RegOpenKeyExW` at `0x140012b9a`
- `ADVAPI32!RegCloseKey` at `0x140012b79`
- `ADVAPI32!RegCloseKey` at `0x140012bdd`
- `ADVAPI32!RegCloseKey` at `0x140012bfe`
- `ADVAPI32!RegCloseKey` at `0x140012c34`
- `ADVAPI32!RegCloseKey` at `0x140012b79`
- `ADVAPI32!RegCloseKey` at `0x140012bdd`
- `ADVAPI32!RegCloseKey` at `0x140012bfe`
- `ADVAPI32!RegCloseKey` at `0x140012c34`
- `KERNEL32!RegCreateKeyExW` at `0x140012b58`
- `KERNEL32!RegCreateKeyExW` at `0x140012b58`
- `KERNEL32!RegSetValueExW` at `0x140012c28`
- `KERNEL32!RegSetValueExW` at `0x140012c28`

## string_xrefs

- `0x140012bc1`: `SymbolicLinkValue`

## pseudocode

```c
LSTATUS __fastcall SettingsCopier::SetRegKeyValue(
        HKEY hKey,
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        DWORD dwType,
        BYTE *lpData,
        DWORD a6)
{
  LSTATUS result; // eax
  bool v11; // cc
  LSTATUS v12; // eax
  LSTATUS v13; // ebx
  bool v14; // cc
  DWORD Type; // [rsp+50h] [rbp-20h] BYREF
  DWORD dwDisposition; // [rsp+54h] [rbp-1Ch] BYREF
  DWORD cbData; // [rsp+58h] [rbp-18h] BYREF
  HKEY v18; // [rsp+60h] [rbp-10h] BYREF
  HKEY hKeya; // [rsp+68h] [rbp-8h] BYREF

  hKeya = 0;
  v18 = 0;
  dwDisposition = 0;
  Type = 0;
  cbData = 0;
  result = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 1u, 0x2001Fu, 0, &hKeya, &dwDisposition);
  v11 = result <= 0;
  if ( result
    || (RegCloseKey(hKeya), result = RegOpenKeyExW(hKey, lpSubKey, 8u, 0x2001Fu, &v18), v11 = result <= 0, result) )
  {
    if ( !v11 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v12 = RegQueryValueExW(v18, L"SymbolicLinkValue", 0, &Type, 0, &cbData);
  v13 = v12;
  if ( !v12 )
  {
    if ( Type == 6 )
    {
      RegCloseKey(v18);
      return -2147023432;
    }
LABEL_13:
    v13 = RegSetValueExW(v18, lpValueName, 0, dwType, lpData, a6);
    RegCloseKey(v18);
    v14 = v13 <= 0;
    if ( !v13 )
      return 0;
    goto LABEL_8;
  }
  if ( v12 == 2 )
    goto LABEL_13;
  RegCloseKey(v18);
  v14 = v13 <= 0;
LABEL_8:
  if ( !v14 )
    return (unsigned __int16)v13 | 0x80070000;
  return v13;
}

```

## disassembly

```asm
0x140012ae8  push    rbp
0x140012aea  push    rbx
0x140012aeb  push    rsi
0x140012aec  push    rdi
0x140012aed  push    r14
0x140012aef  mov     rbp, rsp
0x140012af2  sub     rsp, 70h
0x140012af6  lea     rax, [rbp+dwDisposition]
0x140012afa  mov     [rbp+hKey], 0
0x140012b02  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x140012b07  mov     esi, r9d
0x140012b0a  lea     rax, [rbp+hKey]
0x140012b0e  mov     [rbp+var_10], 0
0x140012b16  mov     [rsp+70h+phkResult], rax; phkResult
0x140012b1b  mov     r14, r8
0x140012b1e  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140012b27  xor     r9d, r9d; lpClass
0x140012b2a  mov     [rsp+70h+samDesired], 2001Fh; samDesired
0x140012b32  xor     r8d, r8d; Reserved
0x140012b35  mov     [rsp+70h+dwOptions], 1; dwOptions
0x140012b3d  mov     rbx, rdx
0x140012b40  mov     rdi, rcx
0x140012b43  mov     [rbp+dwDisposition], 0
0x140012b4a  mov     [rbp+Type], 0
0x140012b51  mov     [rbp+cbData], 0
0x140012b58  call    cs:__imp_RegCreateKeyExW
0x140012b5e  test    eax, eax
0x140012b60  jz      short loc_140012B75
0x140012b62  jle     loc_140012C40
0x140012b68  movzx   eax, ax
0x140012b6b  or      eax, 80070000h
0x140012b70  jmp     loc_140012C40
0x140012b75  mov     rcx, [rbp+hKey]; hKey
0x140012b79  call    cs:__imp_RegCloseKey
0x140012b7f  lea     rax, [rbp+var_10]
0x140012b83  mov     r9d, 2001Fh; samDesired
0x140012b89  mov     r8d, 8; ulOptions
0x140012b8f  mov     qword ptr [rsp+70h+dwOptions], rax; phkResult
0x140012b94  mov     rdx, rbx; lpSubKey
0x140012b97  mov     rcx, rdi; hKey
0x140012b9a  call    cs:__imp_RegOpenKeyExW
0x140012ba0  test    eax, eax
0x140012ba2  jnz     short loc_140012B62
0x140012ba4  mov     rcx, [rbp+var_10]; hKey
0x140012ba8  lea     rax, [rbp+cbData]
0x140012bac  mov     qword ptr [rsp+70h+samDesired], rax; lpcbData
0x140012bb1  lea     r9, [rbp+Type]; lpType
0x140012bb5  xor     r8d, r8d; lpReserved
0x140012bb8  mov     qword ptr [rsp+70h+dwOptions], 0; lpData
0x140012bc1  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x140012bc8  call    cs:__imp_RegQueryValueExW
0x140012bce  mov     ebx, eax
0x140012bd0  test    eax, eax
0x140012bd2  jz      short loc_140012BF4
0x140012bd4  cmp     eax, 2
0x140012bd7  jz      short loc_140012C0B
0x140012bd9  mov     rcx, [rbp+var_10]; hKey
0x140012bdd  call    cs:__imp_RegCloseKey
0x140012be3  test    ebx, ebx
0x140012be5  jle     short loc_140012BF0
0x140012be7  movzx   ebx, bx
0x140012bea  or      ebx, 80070000h
0x140012bf0  mov     eax, ebx
0x140012bf2  jmp     short loc_140012C40
0x140012bf4  cmp     [rbp+Type], 6
0x140012bf8  jnz     short loc_140012C0B
0x140012bfa  mov     rcx, [rbp+var_10]; hKey
0x140012bfe  call    cs:__imp_RegCloseKey
0x140012c04  mov     eax, 800705B8h
0x140012c09  jmp     short loc_140012C40
0x140012c0b  mov     eax, [rbp+arg_28]
0x140012c0e  mov     r9d, esi; dwType
0x140012c11  mov     rcx, [rbp+var_10]; hKey
0x140012c15  xor     r8d, r8d; Reserved
0x140012c18  mov     [rsp+70h+samDesired], eax; cbData
0x140012c1c  mov     rdx, r14; lpValueName
0x140012c1f  mov     rax, [rbp+lpData]
0x140012c23  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x140012c28  call    cs:__imp_RegSetValueExW
0x140012c2e  mov     rcx, [rbp+var_10]; hKey
0x140012c32  mov     ebx, eax
0x140012c34  call    cs:__imp_RegCloseKey
0x140012c3a  test    ebx, ebx
0x140012c3c  jnz     short loc_140012BE5
0x140012c3e  xor     eax, eax
0x140012c40  add     rsp, 70h
0x140012c44  pop     r14
0x140012c46  pop     rdi
0x140012c47  pop     rsi
0x140012c48  pop     rbx
0x140012c49  pop     rbp
0x140012c4a  retn
```
