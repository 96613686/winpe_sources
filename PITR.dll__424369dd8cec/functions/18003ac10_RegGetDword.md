# RegGetDword

- ea: `0x18003ac10`
- end: `0x18003acf0`
- name: `RegGetDword`
- size: `224`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800170f0`
- `0x180020e50`
- `0x1800212c0`
- `0x180049e58`

## callees

- `0x18003ac10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ac73`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ac73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003accf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003accf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003acaa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003acaa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ac4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003acd7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003ac4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003acd7`

## pseudocode

```c
__int64 __fastcall RegGetDword(HKEY a1, const WCHAR *a2, const WCHAR *a3)
{
  DWORD v5; // ecx
  LSTATUS v7; // eax
  LSTATUS v8; // edi
  DWORD Type; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  unsigned int Data; // [rsp+50h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF

  hKey = 0;
  Data = 0;
  cbData = 4;
  Type = 0;
  if ( !a1 )
  {
    v5 = 87;
LABEL_3:
    SetLastError(v5);
    return 0;
  }
  if ( a2 )
  {
    v7 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
    if ( v7 || (a1 = hKey) == 0 )
    {
      v5 = v7;
      goto LABEL_3;
    }
  }
  else
  {
    hKey = a1;
  }
  v8 = RegQueryValueExW(a1, a3, 0, &Type, (LPBYTE)&Data, &cbData);
  if ( v8 )
    goto LABEL_12;
  if ( cbData != 4 )
  {
    v8 = 13;
LABEL_12:
    Data = 0;
  }
  if ( a2 )
    RegCloseKey(hKey);
  SetLastError(v8);
  return Data;
}

```

## disassembly

```asm
0x18003ac10  mov     [rsp-8+arg_8], rbx
0x18003ac15  mov     [rsp-8+arg_10], rdi
0x18003ac1a  push    rbp
0x18003ac1b  mov     rbp, rsp
0x18003ac1e  sub     rsp, 40h
0x18003ac22  mov     [rbp+hKey], 0
0x18003ac2a  mov     rdi, r8
0x18003ac2d  mov     [rbp+Data], 0
0x18003ac34  mov     rbx, rdx
0x18003ac37  mov     [rbp+cbData], 4
0x18003ac3e  mov     [rbp+Type], 0
0x18003ac45  test    rcx, rcx
0x18003ac48  jnz     short loc_18003AC5C
0x18003ac4a  mov     ecx, 57h ; 'W'; dwErrCode
0x18003ac4f  call    cs:__imp_SetLastError
0x18003ac55  xor     eax, eax
0x18003ac57  jmp     loc_18003ACE0
0x18003ac5c  test    rbx, rbx
0x18003ac5f  jz      short loc_18003AC8A
0x18003ac61  lea     rax, [rbp+hKey]
0x18003ac65  mov     r9d, 20019h; samDesired
0x18003ac6b  xor     r8d, r8d; ulOptions
0x18003ac6e  mov     [rsp+40h+phkResult], rax; phkResult
0x18003ac73  call    cs:__imp_RegOpenKeyExW
0x18003ac79  test    eax, eax
0x18003ac7b  jnz     short loc_18003AC86
0x18003ac7d  mov     rcx, [rbp+hKey]
0x18003ac81  test    rcx, rcx
0x18003ac84  jnz     short loc_18003AC8E
0x18003ac86  mov     ecx, eax; hKey
0x18003ac88  jmp     short loc_18003AC4F
0x18003ac8a  mov     [rbp+hKey], rcx
0x18003ac8e  lea     rax, [rbp+cbData]
0x18003ac92  xor     r8d, r8d; lpReserved
0x18003ac95  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18003ac9a  lea     r9, [rbp+Type]; lpType
0x18003ac9e  lea     rax, [rbp+Data]
0x18003aca2  mov     rdx, rdi; lpValueName
0x18003aca5  mov     [rsp+40h+phkResult], rax; lpData
0x18003acaa  call    cs:__imp_RegQueryValueExW
0x18003acb0  mov     edi, eax
0x18003acb2  test    eax, eax
0x18003acb4  jnz     short loc_18003ACBF
0x18003acb6  cmp     [rbp+cbData], 4
0x18003acba  jz      short loc_18003ACC6
0x18003acbc  lea     edi, [rax+0Dh]
0x18003acbf  mov     [rbp+Data], 0
0x18003acc6  test    rbx, rbx
0x18003acc9  jz      short loc_18003ACD5
0x18003accb  mov     rcx, [rbp+hKey]; hKey
0x18003accf  call    cs:__imp_RegCloseKey
0x18003acd5  mov     ecx, edi; dwErrCode
0x18003acd7  call    cs:__imp_SetLastError
0x18003acdd  mov     eax, [rbp+Data]
0x18003ace0  mov     rbx, [rsp+40h+arg_8]
0x18003ace5  mov     rdi, [rsp+40h+arg_10]
0x18003acea  add     rsp, 40h
0x18003acee  pop     rbp
0x18003acef  retn
```
