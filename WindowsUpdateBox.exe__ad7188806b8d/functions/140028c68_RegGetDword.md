# RegGetDword

- ea: `0x140028c68`
- end: `0x140028d56`
- name: `RegGetDword`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140059c90`

## callees

- `0x140028c68`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x140028cf9`
- `ADVAPI32!RegQueryValueExW` at `0x140028cf9`
- `ADVAPI32!RegOpenKeyExW` at `0x140028cc0`
- `ADVAPI32!RegOpenKeyExW` at `0x140028cc0`
- `ADVAPI32!RegCloseKey` at `0x140028d1f`
- `ADVAPI32!RegCloseKey` at `0x140028d1f`
- `KERNEL32!SetLastError` at `0x140028d2d`
- `KERNEL32!SetLastError` at `0x140028d40`
- `KERNEL32!SetLastError` at `0x140028d2d`
- `KERNEL32!SetLastError` at `0x140028d40`

## pseudocode

```c
__int64 __fastcall RegGetDword(HKEY a1, __int64 a2, __int64 a3)
{
  DWORD v3; // ecx
  LSTATUS v4; // eax
  LSTATUS v5; // ebx
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF
  int v9; // [rsp+5Ch] [rbp+24h]
  unsigned int Data; // [rsp+60h] [rbp+28h] BYREF
  int v11; // [rsp+64h] [rbp+2Ch]
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  v11 = HIDWORD(a3);
  v9 = HIDWORD(a2);
  hKey = 0;
  Data = 0;
  cbData = 4;
  Type = 0;
  if ( a1 )
  {
    v4 = RegOpenKeyExW(a1, L"Select", 0, 0x20019u, &hKey);
    if ( v4 || !hKey )
    {
      v3 = v4;
      goto LABEL_11;
    }
    v5 = RegQueryValueExW(hKey, L"Current", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v5 )
    {
      if ( cbData == 4 )
      {
LABEL_9:
        RegCloseKey(hKey);
        SetLastError(v5);
        return Data;
      }
      v5 = 13;
    }
    Data = 0;
    goto LABEL_9;
  }
  v3 = 87;
LABEL_11:
  SetLastError(v3);
  return 0;
}

```

## disassembly

```asm
0x140028c68  mov     qword ptr [rsp-10h+Data], r8
0x140028c6d  mov     qword ptr [rsp-10h+cbData], rdx
0x140028c72  push    rbp
0x140028c73  push    rbx
0x140028c74  mov     rbp, rsp
0x140028c77  sub     rsp, 38h
0x140028c7b  mov     [rbp+hKey], 0
0x140028c83  mov     [rbp+Data], 0
0x140028c8a  mov     [rbp+cbData], 4
0x140028c91  mov     [rbp+Type], 0
0x140028c98  test    rcx, rcx
0x140028c9b  jnz     short loc_140028CA7
0x140028c9d  mov     ecx, 57h ; 'W'; hKey
0x140028ca2  jmp     loc_140028D40
0x140028ca7  lea     rax, [rbp+hKey]
0x140028cab  mov     r9d, 20019h; samDesired
0x140028cb1  xor     r8d, r8d; ulOptions
0x140028cb4  mov     [rsp+38h+phkResult], rax; phkResult
0x140028cb9  lea     rdx, aSelect; "Select"
0x140028cc0  call    cs:__imp_RegOpenKeyExW
0x140028cc7  nop     dword ptr [rax+rax+00h]
0x140028ccc  test    eax, eax
0x140028cce  jnz     short loc_140028D3E
0x140028cd0  mov     rcx, [rbp+hKey]; hKey
0x140028cd4  test    rcx, rcx
0x140028cd7  jz      short loc_140028D3E
0x140028cd9  lea     rax, [rbp+cbData]
0x140028cdd  xor     r8d, r8d; lpReserved
0x140028ce0  mov     [rsp+38h+lpcbData], rax; lpcbData
0x140028ce5  lea     r9, [rbp+Type]; lpType
0x140028ce9  lea     rax, [rbp+Data]
0x140028ced  lea     rdx, aCurrent; "Current"
0x140028cf4  mov     [rsp+38h+phkResult], rax; lpData
0x140028cf9  call    cs:__imp_RegQueryValueExW
0x140028d00  nop     dword ptr [rax+rax+00h]
0x140028d05  mov     ebx, eax
0x140028d07  test    eax, eax
0x140028d09  jnz     short loc_140028D14
0x140028d0b  cmp     [rbp+cbData], 4
0x140028d0f  jz      short loc_140028D1B
0x140028d11  lea     ebx, [rax+0Dh]
0x140028d14  mov     [rbp+Data], 0
0x140028d1b  mov     rcx, [rbp+hKey]; hKey
0x140028d1f  call    cs:__imp_RegCloseKey
0x140028d26  nop     dword ptr [rax+rax+00h]
0x140028d2b  mov     ecx, ebx; dwErrCode
0x140028d2d  call    cs:__imp_SetLastError
0x140028d34  nop     dword ptr [rax+rax+00h]
0x140028d39  mov     eax, [rbp+Data]
0x140028d3c  jmp     short loc_140028D4E
0x140028d3e  mov     ecx, eax; dwErrCode
0x140028d40  call    cs:__imp_SetLastError
0x140028d47  nop     dword ptr [rax+rax+00h]
0x140028d4c  xor     eax, eax
0x140028d4e  add     rsp, 38h
0x140028d52  pop     rbx
0x140028d53  pop     rbp
0x140028d54  retn
```
