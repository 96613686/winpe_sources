# SettingsCopier::SetRegKeyValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar const *,ulong)

- ea: `0x180241b4c`
- end: `0x180241ce0`
- name: `?SetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBG1KPEBEK@Z`
- size: `404`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, DWORD dwType, BYTE *lpData, DWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, registry_config`

## callers

- `0x180240ee0`

## callees

- `0x180241b4c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180241cb0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180241cb0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180241bbc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180241bbc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180241c3e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180241c3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241be3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241c59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241c80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241cc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241be3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241c59`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241c80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180241cc2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180241c0a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180241c0a`

## string_xrefs

- `0x180241c37`: `SymbolicLinkValue`

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
0x180241b4c  push    rbp
0x180241b4e  push    rbx
0x180241b4f  push    rsi
0x180241b50  push    rdi
0x180241b51  push    r14
0x180241b53  mov     rbp, rsp
0x180241b56  sub     rsp, 70h
0x180241b5a  lea     rax, [rbp+dwDisposition]
0x180241b5e  mov     [rbp+hKey], 0
0x180241b66  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x180241b6b  mov     esi, r9d
0x180241b6e  lea     rax, [rbp+hKey]
0x180241b72  mov     [rbp+var_10], 0
0x180241b7a  mov     [rsp+70h+phkResult], rax; phkResult
0x180241b7f  mov     r14, r8
0x180241b82  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180241b8b  xor     r9d, r9d; lpClass
0x180241b8e  mov     [rsp+70h+samDesired], 2001Fh; samDesired
0x180241b96  xor     r8d, r8d; Reserved
0x180241b99  mov     [rsp+70h+dwOptions], 1; dwOptions
0x180241ba1  mov     rbx, rdx
0x180241ba4  mov     rdi, rcx
0x180241ba7  mov     [rbp+dwDisposition], 0
0x180241bae  mov     [rbp+Type], 0
0x180241bb5  mov     [rbp+cbData], 0
0x180241bbc  call    cs:__imp_RegCreateKeyExW
0x180241bc3  nop     dword ptr [rax+rax+00h]
0x180241bc8  test    eax, eax
0x180241bca  jz      short loc_180241BDF
0x180241bcc  jle     loc_180241CD4
0x180241bd2  movzx   eax, ax
0x180241bd5  or      eax, 80070000h
0x180241bda  jmp     loc_180241CD4
0x180241bdf  mov     rcx, [rbp+hKey]; hKey
0x180241be3  call    cs:__imp_RegCloseKey
0x180241bea  nop     dword ptr [rax+rax+00h]
0x180241bef  lea     rax, [rbp+var_10]
0x180241bf3  mov     r9d, 2001Fh; samDesired
0x180241bf9  mov     r8d, 8; ulOptions
0x180241bff  mov     qword ptr [rsp+70h+dwOptions], rax; phkResult
0x180241c04  mov     rdx, rbx; lpSubKey
0x180241c07  mov     rcx, rdi; hKey
0x180241c0a  call    cs:__imp_RegOpenKeyExW
0x180241c11  nop     dword ptr [rax+rax+00h]
0x180241c16  test    eax, eax
0x180241c18  jnz     short loc_180241BCC
0x180241c1a  mov     rcx, [rbp+var_10]; hKey
0x180241c1e  lea     rax, [rbp+cbData]
0x180241c22  mov     qword ptr [rsp+70h+samDesired], rax; lpcbData
0x180241c27  lea     r9, [rbp+Type]; lpType
0x180241c2b  xor     r8d, r8d; lpReserved
0x180241c2e  mov     qword ptr [rsp+70h+dwOptions], 0; lpData
0x180241c37  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x180241c3e  call    cs:__imp_RegQueryValueExW
0x180241c45  nop     dword ptr [rax+rax+00h]
0x180241c4a  mov     ebx, eax
0x180241c4c  test    eax, eax
0x180241c4e  jz      short loc_180241C76
0x180241c50  cmp     eax, 2
0x180241c53  jz      short loc_180241C93
0x180241c55  mov     rcx, [rbp+var_10]; hKey
0x180241c59  call    cs:__imp_RegCloseKey
0x180241c60  nop     dword ptr [rax+rax+00h]
0x180241c65  test    ebx, ebx
0x180241c67  jle     short loc_180241C72
0x180241c69  movzx   ebx, bx
0x180241c6c  or      ebx, 80070000h
0x180241c72  mov     eax, ebx
0x180241c74  jmp     short loc_180241CD4
0x180241c76  cmp     [rbp+Type], 6
0x180241c7a  jnz     short loc_180241C93
0x180241c7c  mov     rcx, [rbp+var_10]; hKey
0x180241c80  call    cs:__imp_RegCloseKey
0x180241c87  nop     dword ptr [rax+rax+00h]
0x180241c8c  mov     eax, 800705B8h
0x180241c91  jmp     short loc_180241CD4
0x180241c93  mov     eax, [rbp+arg_28]
0x180241c96  mov     r9d, esi; dwType
0x180241c99  mov     rcx, [rbp+var_10]; hKey
0x180241c9d  xor     r8d, r8d; Reserved
0x180241ca0  mov     [rsp+70h+samDesired], eax; cbData
0x180241ca4  mov     rdx, r14; lpValueName
0x180241ca7  mov     rax, [rbp+lpData]
0x180241cab  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x180241cb0  call    cs:__imp_RegSetValueExW
0x180241cb7  nop     dword ptr [rax+rax+00h]
0x180241cbc  mov     rcx, [rbp+var_10]; hKey
0x180241cc0  mov     ebx, eax
0x180241cc2  call    cs:__imp_RegCloseKey
0x180241cc9  nop     dword ptr [rax+rax+00h]
0x180241cce  test    ebx, ebx
0x180241cd0  jnz     short loc_180241C67
0x180241cd2  xor     eax, eax
0x180241cd4  add     rsp, 70h
0x180241cd8  pop     r14
0x180241cda  pop     rdi
0x180241cdb  pop     rsi
0x180241cdc  pop     rbx
0x180241cdd  pop     rbp
0x180241cde  retn
```
