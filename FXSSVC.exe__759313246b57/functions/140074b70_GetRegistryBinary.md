# GetRegistryBinary

- ea: `0x140074b70`
- end: `0x140074cab`
- name: `GetRegistryBinary`
- size: `315`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400513e4`
- `0x14007fb00`
- `0x140080314`

## callees

- `0x1400698ec`
- `0x14006998c`
- `0x140074b70`
- `0x140076758`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x140074c72`
- `ADVAPI32!RegSetValueExW` at `0x140074c72`
- `ADVAPI32!RegQueryValueExW` at `0x140074bb4`
- `ADVAPI32!RegQueryValueExW` at `0x140074c37`
- `ADVAPI32!RegQueryValueExW` at `0x140074bb4`
- `ADVAPI32!RegQueryValueExW` at `0x140074c37`

## string_xrefs

- `0x140074c85`: `RegSetValueEx() failed[%s], ec=%d`

## pseudocode

```c
void *__fastcall GetRegistryBinary(HKEY hKey, LPCWSTR lpValueName, DWORD *a3)
{
  unsigned int v6; // eax
  void *lpData; // rbx
  DWORD v9; // eax
  unsigned int v10; // eax
  DWORD Type[4]; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF

  cbData = 0;
  Type[0] = 3;
  v6 = RegQueryValueExW(hKey, lpValueName, 0, Type, 0, &cbData);
  if ( v6 )
  {
    if ( v6 != 2 )
    {
      lpData = 0;
LABEL_4:
      fax_dprintf(L"RegQueryValueEx() failed, ec=%d", v6);
LABEL_5:
      pMemFree(lpData);
      return 0;
    }
    goto LABEL_9;
  }
  if ( Type[0] != 3 )
    return 0;
  v9 = cbData;
  if ( !cbData )
  {
LABEL_9:
    v9 = 1;
    cbData = 1;
  }
  lpData = (void *)pMemAlloc(v9 + 1);
  if ( !lpData )
    goto LABEL_5;
  v6 = RegQueryValueExW(hKey, lpValueName, 0, Type, (LPBYTE)lpData, &cbData);
  *((_BYTE *)lpData + cbData) = 0;
  if ( v6 )
  {
    if ( v6 != 2 )
      goto LABEL_4;
    v10 = RegSetValueExW(hKey, lpValueName, 0, 3u, (const BYTE *)lpData, cbData);
    if ( v10 )
    {
      fax_dprintf(L"RegSetValueEx() failed[%s], ec=%d", lpValueName, v10);
      goto LABEL_5;
    }
  }
  if ( a3 )
    *a3 = cbData;
  return lpData;
}

```

## disassembly

```asm
0x140074b70  mov     r11, rsp
0x140074b73  mov     [r11+8], rbx
0x140074b77  mov     [r11+10h], rsi
0x140074b7b  push    rbp
0x140074b7c  push    rdi
0x140074b7d  push    r14
0x140074b7f  mov     rbp, rsp
0x140074b82  sub     rsp, 40h
0x140074b86  lea     rax, [rbp+cbData]
0x140074b8a  mov     [rbp+cbData], 0
0x140074b91  mov     rdi, r8
0x140074b94  mov     [r11-30h], rax
0x140074b98  lea     r9, [rbp+Type]; lpType
0x140074b9c  mov     qword ptr [r11-38h], 0
0x140074ba4  xor     r8d, r8d; lpReserved
0x140074ba7  mov     [rbp+Type], 3
0x140074bae  mov     rsi, rdx
0x140074bb1  mov     r14, rcx
0x140074bb4  call    cs:__imp_RegQueryValueExW
0x140074bbb  nop     dword ptr [rax+rax+00h]
0x140074bc0  test    eax, eax
0x140074bc2  jz      short loc_140074BF7
0x140074bc4  cmp     eax, 2
0x140074bc7  jz      short loc_140074C04
0x140074bc9  xor     ebx, ebx
0x140074bcb  mov     edx, eax
0x140074bcd  lea     rcx, aRegqueryvaluee_1; "RegQueryValueEx() failed, ec=%d"
0x140074bd4  call    fax_dprintf
0x140074bd9  mov     rcx, rbx; lpMem
0x140074bdc  call    pMemFree
0x140074be1  xor     eax, eax
0x140074be3  mov     rbx, [rsp+40h+arg_0]
0x140074be8  mov     rsi, [rsp+40h+arg_8]
0x140074bed  add     rsp, 40h
0x140074bf1  pop     r14
0x140074bf3  pop     rdi
0x140074bf4  pop     rbp
0x140074bf5  retn
0x140074bf7  cmp     [rbp+Type], 3
0x140074bfb  jnz     short loc_140074BE1
0x140074bfd  mov     eax, [rbp+cbData]
0x140074c00  test    eax, eax
0x140074c02  jnz     short loc_140074C0C
0x140074c04  mov     eax, 1
0x140074c09  mov     [rbp+cbData], eax
0x140074c0c  lea     ecx, [rax+1]; dwBytes
0x140074c0f  call    pMemAlloc
0x140074c14  mov     rbx, rax
0x140074c17  test    rax, rax
0x140074c1a  jz      short loc_140074BD9
0x140074c1c  lea     rax, [rbp+cbData]
0x140074c20  xor     r8d, r8d; lpReserved
0x140074c23  mov     [rsp+40h+lpcbData], rax; lpcbData
0x140074c28  lea     r9, [rbp+Type]; lpType
0x140074c2c  mov     rdx, rsi; lpValueName
0x140074c2f  mov     [rsp+40h+lpData], rbx; lpData
0x140074c34  mov     rcx, r14; hKey
0x140074c37  call    cs:__imp_RegQueryValueExW
0x140074c3e  nop     dword ptr [rax+rax+00h]
0x140074c43  mov     ecx, [rbp+cbData]
0x140074c46  mov     byte ptr [rcx+rbx], 0
0x140074c4a  test    eax, eax
0x140074c4c  jz      short loc_140074C99
0x140074c4e  cmp     eax, 2
0x140074c51  jnz     loc_140074BCB
0x140074c57  mov     eax, [rbp+cbData]
0x140074c5a  mov     r9d, 3; dwType
0x140074c60  mov     dword ptr [rsp+40h+lpcbData], eax; cbData
0x140074c64  xor     r8d, r8d; Reserved
0x140074c67  mov     rdx, rsi; lpValueName
0x140074c6a  mov     [rsp+40h+lpData], rbx; lpData
0x140074c6f  mov     rcx, r14; hKey
0x140074c72  call    cs:__imp_RegSetValueExW
0x140074c79  nop     dword ptr [rax+rax+00h]
0x140074c7e  test    eax, eax
0x140074c80  jz      short loc_140074C99
0x140074c82  mov     r8d, eax
0x140074c85  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed[%s], ec=%d"
0x140074c8c  mov     rdx, rsi
0x140074c8f  call    fax_dprintf
0x140074c94  jmp     loc_140074BD9
0x140074c99  test    rdi, rdi
0x140074c9c  jz      short loc_140074CA3
0x140074c9e  mov     eax, [rbp+cbData]
0x140074ca1  mov     [rdi], eax
0x140074ca3  mov     rax, rbx
0x140074ca6  jmp     loc_140074BE3
```
