# InternalReadRegistryValue

- ea: `0x18000d2e0`
- end: `0x18000d4cb`
- name: `InternalReadRegistryValue`
- size: `491`
- prototype: `__int64 __fastcall(PHKEY phkResult, LPCWSTR lpSubKey, LPCWSTR lpValue, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000dcc8`

## callees

- `0x18000d2e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d362`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d3fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d4a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d362`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d3fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d4a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d34f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d490`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d34f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d3eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d490`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d3ad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d46d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d3ad`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000d46d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d331`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d423`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d331`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d423`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d35a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d3f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d49b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d35a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d3f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d49b`

## pseudocode

```c
__int64 __fastcall InternalReadRegistryValue(PHKEY phkResult, LPCWSTR lpSubKey, LPCWSTR lpValue, _DWORD *a4)
{
  bool v4; // zf
  LSTATUS v9; // eax
  signed int v10; // esi
  HKEY v11; // rbp
  DWORD v12; // ebx
  HKEY v14; // rcx
  int ValueW; // eax
  bool v16; // sf
  unsigned int v17; // esi
  HKEY v18; // rsi
  DWORD LastError; // ebx
  int v20; // eax
  bool v21; // sf
  HKEY v22; // rcx
  bool v23; // sf
  HKEY v24; // rbp
  DWORD v25; // ebx
  DWORD pcbData[4]; // [rsp+40h] [rbp-38h] BYREF
  int pvData; // [rsp+80h] [rbp+8h] BYREF

  v4 = *phkResult == 0;
  pvData = 0;
  if ( !v4 )
    goto LABEL_8;
  *phkResult = 0;
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, phkResult);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( v10 >= 0 )
  {
LABEL_8:
    v14 = *phkResult;
    pcbData[0] = 4;
    ValueW = RegGetValueW(v14, 0, lpValue, 0x10u, 0, &pvData, pcbData);
    v16 = ValueW < 0;
    if ( ValueW > 0 )
    {
      ValueW = (unsigned __int16)ValueW | 0x80070000;
      v16 = ValueW < 0;
    }
    if ( !v16 )
      goto LABEL_11;
    v17 = (unsigned __int16)ValueW;
    if ( (unsigned __int16)ValueW != 2 )
    {
      v18 = *phkResult;
      if ( *phkResult )
      {
        LastError = GetLastError();
        RegCloseKey(v18);
        SetLastError(LastError);
      }
      *phkResult = 0;
      v20 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, phkResult);
      v21 = v20 < 0;
      if ( v20 > 0 )
      {
        v20 = (unsigned __int16)v20 | 0x80070000;
        v21 = v20 < 0;
      }
      if ( !v21 )
      {
        v22 = *phkResult;
        pcbData[0] = 4;
        v20 = RegGetValueW(v22, 0, lpValue, 0x10u, 0, &pvData, pcbData);
        v23 = v20 < 0;
        if ( v20 > 0 )
        {
          v20 = (unsigned __int16)v20 | 0x80070000;
          v23 = v20 < 0;
        }
        if ( !v23 )
        {
LABEL_11:
          *a4 = pvData != 0;
          return 0;
        }
      }
      v24 = *phkResult;
      v17 = (unsigned __int16)v20;
      if ( *phkResult )
      {
        v25 = GetLastError();
        RegCloseKey(v24);
        SetLastError(v25);
      }
      *phkResult = 0;
    }
    return v17;
  }
  v11 = *phkResult;
  if ( *phkResult )
  {
    v12 = GetLastError();
    RegCloseKey(v11);
    SetLastError(v12);
  }
  *phkResult = 0;
  return (unsigned __int16)v10;
}

```

## disassembly

```asm
0x18000d2e0  mov     rax, rsp
0x18000d2e3  mov     [rax+10h], rbx
0x18000d2e7  mov     [rax+18h], rbp
0x18000d2eb  push    rsi
0x18000d2ec  push    rdi
0x18000d2ed  push    r13
0x18000d2ef  push    r14
0x18000d2f1  push    r15
0x18000d2f3  sub     rsp, 50h
0x18000d2f7  cmp     qword ptr [rcx], 0
0x18000d2fb  mov     r14, r9
0x18000d2fe  mov     r15, r8
0x18000d301  mov     dword ptr [rax+8], 0
0x18000d308  mov     rbp, rdx
0x18000d30b  mov     rdi, rcx
0x18000d30e  mov     r13d, 80070000h
0x18000d314  jnz     short loc_18000D377
0x18000d316  mov     qword ptr [rcx], 0
0x18000d31d  mov     r9d, 20019h; samDesired
0x18000d323  mov     [rax-58h], rcx
0x18000d327  xor     r8d, r8d; ulOptions
0x18000d32a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d331  call    cs:__imp_RegOpenKeyExW
0x18000d337  mov     esi, eax
0x18000d339  test    eax, eax
0x18000d33b  jle     short loc_18000D343
0x18000d33d  movzx   esi, ax
0x18000d340  or      esi, r13d
0x18000d343  test    esi, esi
0x18000d345  jns     short loc_18000D377
0x18000d347  mov     rbp, [rdi]
0x18000d34a  test    rbp, rbp
0x18000d34d  jz      short loc_18000D368
0x18000d34f  call    cs:__imp_GetLastError
0x18000d355  mov     rcx, rbp; hKey
0x18000d358  mov     ebx, eax
0x18000d35a  call    cs:__imp_RegCloseKey
0x18000d360  mov     ecx, ebx; dwErrCode
0x18000d362  call    cs:__imp_SetLastError
0x18000d368  mov     qword ptr [rdi], 0
0x18000d36f  movzx   eax, si
0x18000d372  jmp     loc_18000D4B2
0x18000d377  mov     rcx, [rdi]; hkey
0x18000d37a  lea     rax, [rsp+78h+var_38]
0x18000d37f  mov     [rsp+78h+pcbData], rax; pcbData
0x18000d384  mov     r9d, 10h; dwFlags
0x18000d38a  lea     rax, [rsp+78h+arg_0]
0x18000d392  mov     [rsp+78h+var_38], 4
0x18000d39a  mov     [rsp+78h+pvData], rax; pvData
0x18000d39f  mov     r8, r15; lpValue
0x18000d3a2  xor     edx, edx; lpSubKey
0x18000d3a4  mov     [rsp+78h+pdwType], 0; pdwType
0x18000d3ad  call    cs:__imp_RegGetValueW
0x18000d3b3  test    eax, eax
0x18000d3b5  jle     short loc_18000D3BF
0x18000d3b7  movzx   eax, ax
0x18000d3ba  or      eax, r13d
0x18000d3bd  test    eax, eax
0x18000d3bf  js      short loc_18000D3D7
0x18000d3c1  xor     eax, eax
0x18000d3c3  cmp     [rsp+78h+arg_0], eax
0x18000d3ca  setnbe  al
0x18000d3cd  mov     [r14], eax
0x18000d3d0  xor     eax, eax
0x18000d3d2  jmp     loc_18000D4B2
0x18000d3d7  movzx   esi, ax
0x18000d3da  cmp     esi, 2
0x18000d3dd  jz      loc_18000D4B0
0x18000d3e3  mov     rsi, [rdi]
0x18000d3e6  test    rsi, rsi
0x18000d3e9  jz      short loc_18000D404
0x18000d3eb  call    cs:__imp_GetLastError
0x18000d3f1  mov     rcx, rsi; hKey
0x18000d3f4  mov     ebx, eax
0x18000d3f6  call    cs:__imp_RegCloseKey
0x18000d3fc  mov     ecx, ebx; dwErrCode
0x18000d3fe  call    cs:__imp_SetLastError
0x18000d404  mov     r9d, 20019h; samDesired
0x18000d40a  mov     qword ptr [rdi], 0
0x18000d411  xor     r8d, r8d; ulOptions
0x18000d414  mov     [rsp+78h+pdwType], rdi; phkResult
0x18000d419  mov     rdx, rbp; lpSubKey
0x18000d41c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d423  call    cs:__imp_RegOpenKeyExW
0x18000d429  test    eax, eax
0x18000d42b  jle     short loc_18000D435
0x18000d42d  movzx   eax, ax
0x18000d430  or      eax, r13d
0x18000d433  test    eax, eax
0x18000d435  js      short loc_18000D485
0x18000d437  mov     rcx, [rdi]; hkey
0x18000d43a  lea     rax, [rsp+78h+var_38]
0x18000d43f  mov     [rsp+78h+pcbData], rax; pcbData
0x18000d444  mov     r9d, 10h; dwFlags
0x18000d44a  lea     rax, [rsp+78h+arg_0]
0x18000d452  mov     [rsp+78h+var_38], 4
0x18000d45a  mov     [rsp+78h+pvData], rax; pvData
0x18000d45f  mov     r8, r15; lpValue
0x18000d462  xor     edx, edx; lpSubKey
0x18000d464  mov     [rsp+78h+pdwType], 0; pdwType
0x18000d46d  call    cs:__imp_RegGetValueW
0x18000d473  test    eax, eax
0x18000d475  jle     short loc_18000D47F
0x18000d477  movzx   eax, ax
0x18000d47a  or      eax, r13d
0x18000d47d  test    eax, eax
0x18000d47f  jns     loc_18000D3C1
0x18000d485  mov     rbp, [rdi]
0x18000d488  movzx   esi, ax
0x18000d48b  test    rbp, rbp
0x18000d48e  jz      short loc_18000D4A9
0x18000d490  call    cs:__imp_GetLastError
0x18000d496  mov     rcx, rbp; hKey
0x18000d499  mov     ebx, eax
0x18000d49b  call    cs:__imp_RegCloseKey
0x18000d4a1  mov     ecx, ebx; dwErrCode
0x18000d4a3  call    cs:__imp_SetLastError
0x18000d4a9  mov     qword ptr [rdi], 0
0x18000d4b0  mov     eax, esi
0x18000d4b2  lea     r11, [rsp+78h+var_28]
0x18000d4b7  mov     rbx, [r11+38h]
0x18000d4bb  mov     rbp, [r11+40h]
0x18000d4bf  mov     rsp, r11
0x18000d4c2  pop     r15
0x18000d4c4  pop     r14
0x18000d4c6  pop     r13
0x18000d4c8  pop     rdi
0x18000d4c9  pop     rsi
0x18000d4ca  retn
```
