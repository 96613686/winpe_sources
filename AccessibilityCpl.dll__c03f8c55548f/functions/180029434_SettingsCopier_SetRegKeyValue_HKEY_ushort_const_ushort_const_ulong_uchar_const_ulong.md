# SettingsCopier::SetRegKeyValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar const *,ulong)

- ea: `0x180029434`
- end: `0x180029597`
- name: `?SetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBG1KPEBEK@Z`
- size: `355`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, DWORD dwType, BYTE *lpData, DWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, registry_config`

## callers

- `0x1800288dc`

## callees

- `0x180029434`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800294c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029529`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002954a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029580`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800294c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029529`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002954a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180029580`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800294a4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800294a4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029574`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180029574`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029514`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180029514`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800294e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800294e6`

## string_xrefs

- `0x18002950d`: `SymbolicLinkValue`

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
0x180029434  push    rbp
0x180029436  push    rbx
0x180029437  push    rsi
0x180029438  push    rdi
0x180029439  push    r14
0x18002943b  mov     rbp, rsp
0x18002943e  sub     rsp, 70h
0x180029442  lea     rax, [rbp+dwDisposition]
0x180029446  mov     [rbp+hKey], 0
0x18002944e  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x180029453  mov     esi, r9d
0x180029456  lea     rax, [rbp+hKey]
0x18002945a  mov     [rbp+var_10], 0
0x180029462  mov     [rsp+70h+phkResult], rax; phkResult
0x180029467  mov     r14, r8
0x18002946a  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180029473  xor     r9d, r9d; lpClass
0x180029476  mov     [rsp+70h+samDesired], 2001Fh; samDesired
0x18002947e  xor     r8d, r8d; Reserved
0x180029481  mov     [rsp+70h+dwOptions], 1; dwOptions
0x180029489  mov     rbx, rdx
0x18002948c  mov     rdi, rcx
0x18002948f  mov     [rbp+dwDisposition], 0
0x180029496  mov     [rbp+Type], 0
0x18002949d  mov     [rbp+cbData], 0
0x1800294a4  call    cs:__imp_RegCreateKeyExW
0x1800294aa  test    eax, eax
0x1800294ac  jz      short loc_1800294C1
0x1800294ae  jle     loc_18002958C
0x1800294b4  movzx   eax, ax
0x1800294b7  or      eax, 80070000h
0x1800294bc  jmp     loc_18002958C
0x1800294c1  mov     rcx, [rbp+hKey]; hKey
0x1800294c5  call    cs:__imp_RegCloseKey
0x1800294cb  lea     rax, [rbp+var_10]
0x1800294cf  mov     r9d, 2001Fh; samDesired
0x1800294d5  mov     r8d, 8; ulOptions
0x1800294db  mov     qword ptr [rsp+70h+dwOptions], rax; phkResult
0x1800294e0  mov     rdx, rbx; lpSubKey
0x1800294e3  mov     rcx, rdi; hKey
0x1800294e6  call    cs:__imp_RegOpenKeyExW
0x1800294ec  test    eax, eax
0x1800294ee  jnz     short loc_1800294AE
0x1800294f0  mov     rcx, [rbp+var_10]; hKey
0x1800294f4  lea     rax, [rbp+cbData]
0x1800294f8  mov     qword ptr [rsp+70h+samDesired], rax; lpcbData
0x1800294fd  lea     r9, [rbp+Type]; lpType
0x180029501  xor     r8d, r8d; lpReserved
0x180029504  mov     qword ptr [rsp+70h+dwOptions], 0; lpData
0x18002950d  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x180029514  call    cs:__imp_RegQueryValueExW
0x18002951a  mov     ebx, eax
0x18002951c  test    eax, eax
0x18002951e  jz      short loc_180029540
0x180029520  cmp     eax, 2
0x180029523  jz      short loc_180029557
0x180029525  mov     rcx, [rbp+var_10]; hKey
0x180029529  call    cs:__imp_RegCloseKey
0x18002952f  test    ebx, ebx
0x180029531  jle     short loc_18002953C
0x180029533  movzx   ebx, bx
0x180029536  or      ebx, 80070000h
0x18002953c  mov     eax, ebx
0x18002953e  jmp     short loc_18002958C
0x180029540  cmp     [rbp+Type], 6
0x180029544  jnz     short loc_180029557
0x180029546  mov     rcx, [rbp+var_10]; hKey
0x18002954a  call    cs:__imp_RegCloseKey
0x180029550  mov     eax, 800705B8h
0x180029555  jmp     short loc_18002958C
0x180029557  mov     eax, [rbp+arg_28]
0x18002955a  mov     r9d, esi; dwType
0x18002955d  mov     rcx, [rbp+var_10]; hKey
0x180029561  xor     r8d, r8d; Reserved
0x180029564  mov     [rsp+70h+samDesired], eax; cbData
0x180029568  mov     rdx, r14; lpValueName
0x18002956b  mov     rax, [rbp+lpData]
0x18002956f  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x180029574  call    cs:__imp_RegSetValueExW
0x18002957a  mov     rcx, [rbp+var_10]; hKey
0x18002957e  mov     ebx, eax
0x180029580  call    cs:__imp_RegCloseKey
0x180029586  test    ebx, ebx
0x180029588  jnz     short loc_180029531
0x18002958a  xor     eax, eax
0x18002958c  add     rsp, 70h
0x180029590  pop     r14
0x180029592  pop     rdi
0x180029593  pop     rsi
0x180029594  pop     rbx
0x180029595  pop     rbp
0x180029596  retn
```
