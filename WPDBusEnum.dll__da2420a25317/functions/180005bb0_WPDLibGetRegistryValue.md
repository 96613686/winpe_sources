# WPDLibGetRegistryValue

- ea: `0x180005bb0`
- end: `0x180005d2d`
- name: `WPDLibGetRegistryValue`
- size: `381`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180001210`
- `0x180002c70`
- `0x1800069d0`
- `0x18000fac4`

## callees

- `0x180005bb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005d08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005d08`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005c19`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005c19`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005c78`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005cc7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005c78`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005cc7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005c9a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005c9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005ce2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005ce2`

## pseudocode

```c
LSTATUS __fastcall WPDLibGetRegistryValue(
        HKEY a1,
        __int64 a2,
        const WCHAR *a3,
        const WCHAR *a4,
        int a5,
        BYTE **a6,
        DWORD *a7)
{
  HKEY v8; // rbx
  BYTE **v9; // r14
  DWORD *v10; // r15
  LSTATUS result; // eax
  LSTATUS v12; // edi
  BYTE *v13; // rbp
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  DWORD Type; // [rsp+70h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+10h] BYREF
  int v17; // [rsp+7Ch] [rbp+14h]

  v17 = HIDWORD(a2);
  cbData = 0;
  Type = 0;
  v8 = a1;
  hKey = 0;
  if ( !a1 )
  {
    if ( a3 )
    {
      v9 = a6;
      v10 = a7;
      *a6 = 0;
      *v10 = 0;
      result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x20019u, &hKey);
      if ( result )
        return result;
      a1 = hKey;
      goto LABEL_7;
    }
    return 87;
  }
  if ( a3 )
    return 87;
  v9 = a6;
  v10 = a7;
  hKey = a1;
  *a6 = 0;
  *v10 = 0;
LABEL_7:
  cbData = 0;
  v12 = RegQueryValueExW(a1, a4, 0, &Type, 0, &cbData);
  if ( !v12 )
  {
    if ( Type == a5 )
    {
      v13 = (BYTE *)LocalAlloc(0x40u, cbData);
      if ( v13 )
      {
        v12 = RegQueryValueExW(hKey, a4, 0, &Type, v13, &cbData);
        if ( v12 )
        {
          LocalFree(v13);
        }
        else
        {
          *v10 = cbData;
          *v9 = v13;
        }
      }
      else
      {
        v12 = 8;
      }
    }
    else
    {
      v12 = 87;
    }
  }
  if ( !v8 )
    RegCloseKey(hKey);
  return v12;
}

```

## disassembly

```asm
0x180005bb0  mov     qword ptr [rsp+cbData], rdx
0x180005bb5  push    rbx
0x180005bb6  push    rsi
0x180005bb7  push    rdi
0x180005bb8  push    r14
0x180005bba  push    r15
0x180005bbc  sub     rsp, 40h
0x180005bc0  xor     edi, edi
0x180005bc2  mov     rsi, r9
0x180005bc5  mov     [rsp+68h+cbData], edi
0x180005bc9  mov     rax, r8
0x180005bcc  mov     [rsp+68h+Type], edi
0x180005bd0  mov     rbx, rcx
0x180005bd3  mov     [rsp+68h+hKey], rdi
0x180005bd8  test    rcx, rcx
0x180005bdb  jnz     short loc_180005C2E
0x180005bdd  test    rax, rax
0x180005be0  jz      loc_180005D1C
0x180005be6  mov     r14, [rsp+68h+arg_28]
0x180005bee  lea     rcx, [rsp+68h+hKey]
0x180005bf3  mov     r15, [rsp+68h+arg_30]
0x180005bfb  mov     r9d, 20019h; samDesired
0x180005c01  mov     [rsp+68h+phkResult], rcx; phkResult
0x180005c06  xor     r8d, r8d; ulOptions
0x180005c09  mov     rdx, rax; lpSubKey
0x180005c0c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005c13  mov     [r14], rdi
0x180005c16  mov     [r15], edi
0x180005c19  call    cs:__imp_RegOpenKeyExW
0x180005c1f  test    eax, eax
0x180005c21  jnz     loc_180005D21
0x180005c27  mov     rcx, [rsp+68h+hKey]; hKey
0x180005c2c  jmp     short loc_180005C52
0x180005c2e  test    rax, rax
0x180005c31  jnz     loc_180005D1C
0x180005c37  mov     r14, [rsp+68h+arg_28]
0x180005c3f  mov     r15, [rsp+68h+arg_30]
0x180005c47  mov     [rsp+68h+hKey], rbx
0x180005c4c  mov     [r14], rdi
0x180005c4f  mov     [r15], edi
0x180005c52  lea     rax, [rsp+68h+cbData]
0x180005c57  mov     [rsp+68h+arg_10], rbp
0x180005c5f  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180005c64  lea     r9, [rsp+68h+Type]; lpType
0x180005c69  xor     r8d, r8d; lpReserved
0x180005c6c  mov     [rsp+68h+phkResult], rdi; lpData
0x180005c71  mov     rdx, rsi; lpValueName
0x180005c74  mov     [rsp+68h+cbData], edi
0x180005c78  call    cs:__imp_RegQueryValueExW
0x180005c7e  mov     edi, eax
0x180005c80  test    eax, eax
0x180005c82  jnz     short loc_180005CF6
0x180005c84  mov     eax, [rsp+68h+arg_20]
0x180005c8b  cmp     [rsp+68h+Type], eax
0x180005c8f  jnz     short loc_180005CF1
0x180005c91  mov     edx, [rsp+68h+cbData]; uBytes
0x180005c95  mov     ecx, 40h ; '@'; uFlags
0x180005c9a  call    cs:__imp_LocalAlloc
0x180005ca0  mov     rbp, rax
0x180005ca3  test    rax, rax
0x180005ca6  jz      short loc_180005CEA
0x180005ca8  mov     rcx, [rsp+68h+hKey]; hKey
0x180005cad  lea     rax, [rsp+68h+cbData]
0x180005cb2  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180005cb7  lea     r9, [rsp+68h+Type]; lpType
0x180005cbc  xor     r8d, r8d; lpReserved
0x180005cbf  mov     [rsp+68h+phkResult], rbp; lpData
0x180005cc4  mov     rdx, rsi; lpValueName
0x180005cc7  call    cs:__imp_RegQueryValueExW
0x180005ccd  mov     edi, eax
0x180005ccf  test    eax, eax
0x180005cd1  jnz     short loc_180005CDF
0x180005cd3  mov     eax, [rsp+68h+cbData]
0x180005cd7  mov     [r15], eax
0x180005cda  mov     [r14], rbp
0x180005cdd  jmp     short loc_180005CF6
0x180005cdf  mov     rcx, rbp; hMem
0x180005ce2  call    cs:__imp_LocalFree
0x180005ce8  jmp     short loc_180005CF6
0x180005cea  mov     edi, 8
0x180005cef  jmp     short loc_180005CF6
0x180005cf1  mov     edi, 57h ; 'W'
0x180005cf6  mov     rbp, [rsp+68h+arg_10]
0x180005cfe  test    rbx, rbx
0x180005d01  jnz     short loc_180005D0E
0x180005d03  mov     rcx, [rsp+68h+hKey]; hKey
0x180005d08  call    cs:__imp_RegCloseKey
0x180005d0e  mov     eax, edi
0x180005d10  add     rsp, 40h
0x180005d14  pop     r15
0x180005d16  pop     r14
0x180005d18  pop     rdi
0x180005d19  pop     rsi
0x180005d1a  pop     rbx
0x180005d1b  retn
0x180005d1c  mov     eax, 57h ; 'W'
0x180005d21  add     rsp, 40h
0x180005d25  pop     r15
0x180005d27  pop     r14
0x180005d29  pop     rdi
0x180005d2a  pop     rsi
0x180005d2b  pop     rbx
0x180005d2c  retn
```
