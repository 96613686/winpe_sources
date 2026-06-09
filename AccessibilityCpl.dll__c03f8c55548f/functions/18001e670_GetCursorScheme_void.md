# GetCursorScheme(void)

- ea: `0x18001e670`
- end: `0x18001e7a8`
- name: `?GetCursorScheme@@YAHXZ`
- size: `312`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x180018954`

## callees

- `0x180002018`
- `0x180002024`
- `0x18001e670`
- `0x18001e7b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e6f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e790`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e6f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e790`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e6e4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e6e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e6b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e6b1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e73a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e73a`

## pseudocode

```c
__int64 GetCursorScheme(void)
{
  _BYTE *v1; // rdi
  unsigned int v2; // ebx
  int i; // edx
  unsigned __int16 *v4; // rcx
  signed __int64 v5; // r8
  unsigned __int16 v6; // ax
  int v7; // eax
  int v8; // ecx
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  DWORD Type; // [rsp+68h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+30h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  if ( RegOpenKeyExW(HKEY_CURRENT_USER, L"Control Panel\\Cursors", 0, 0x20019u, &hKey) )
    return 1;
  if ( RegQueryValueExW(hKey, 0, 0, &Type, 0, &cbData) || (v1 = operator new[](cbData + 1)) == 0 )
  {
    RegCloseKey(hKey);
    return 1;
  }
  v2 = 1;
  LoadCursorSchemeNames();
  if ( !RegGetValueW(hKey, 0, 0, 2u, &Type, v1, &cbData) )
  {
    for ( i = 0; i < 8; ++i )
    {
      v4 = &g_szSchemeNames + 100 * (unsigned int)i;
      v5 = v1 - (_BYTE *)v4;
      while ( 1 )
      {
        v6 = *v4;
        if ( *v4 != *(unsigned __int16 *)((char *)v4 + v5) )
          break;
        ++v4;
        if ( !v6 )
        {
          v7 = 0;
          goto LABEL_13;
        }
      }
      v7 = v6 < *(unsigned __int16 *)((char *)v4 + v5) ? -1 : 1;
LABEL_13:
      v8 = i + 2;
      if ( v7 )
        v8 = v2;
      v2 = v8;
    }
  }
  RegCloseKey(hKey);
  operator delete[](v1);
  return v2;
}

```

## disassembly

```asm
0x18001e670  push    rbp
0x18001e672  push    rbx
0x18001e673  push    rdi
0x18001e674  mov     rbp, rsp
0x18001e677  sub     rsp, 40h
0x18001e67b  lea     rax, [rbp+hKey]
0x18001e67f  mov     [rbp+hKey], 0
0x18001e687  mov     r9d, 20019h; samDesired
0x18001e68d  mov     [rsp+40h+phkResult], rax; phkResult
0x18001e692  xor     r8d, r8d; ulOptions
0x18001e695  mov     [rbp+Type], 0
0x18001e69c  lea     rdx, aControlPanelCu; "Control Panel\\Cursors"
0x18001e6a3  mov     [rbp+cbData], 0
0x18001e6aa  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001e6b1  call    cs:__imp_RegOpenKeyExW
0x18001e6b7  test    eax, eax
0x18001e6b9  jz      short loc_18001E6C5
0x18001e6bb  mov     eax, 1
0x18001e6c0  jmp     loc_18001E7A0
0x18001e6c5  mov     rcx, [rbp+hKey]; hKey
0x18001e6c9  lea     rax, [rbp+cbData]
0x18001e6cd  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18001e6d2  lea     r9, [rbp+Type]; lpType
0x18001e6d6  xor     r8d, r8d; lpReserved
0x18001e6d9  mov     [rsp+40h+phkResult], 0; lpData
0x18001e6e2  xor     edx, edx; lpValueName
0x18001e6e4  call    cs:__imp_RegQueryValueExW
0x18001e6ea  test    eax, eax
0x18001e6ec  jz      short loc_18001E6FA
0x18001e6ee  mov     rcx, [rbp+hKey]; hKey
0x18001e6f2  call    cs:__imp_RegCloseKey
0x18001e6f8  jmp     short loc_18001E6BB
0x18001e6fa  mov     ecx, [rbp+cbData]
0x18001e6fd  inc     ecx; unsigned __int64
0x18001e6ff  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001e704  mov     rdi, rax
0x18001e707  test    rax, rax
0x18001e70a  jz      short loc_18001E6EE
0x18001e70c  mov     ebx, 1
0x18001e711  call    ?LoadCursorSchemeNames@@YAXXZ; LoadCursorSchemeNames(void)
0x18001e716  mov     rcx, [rbp+hKey]; hkey
0x18001e71a  lea     rax, [rbp+cbData]
0x18001e71e  mov     [rsp+40h+pcbData], rax; pcbData
0x18001e723  lea     r9d, [rbx+1]; dwFlags
0x18001e727  lea     rax, [rbp+Type]
0x18001e72b  mov     [rsp+40h+lpcbData], rdi; pvData
0x18001e730  xor     r8d, r8d; lpValue
0x18001e733  mov     [rsp+40h+phkResult], rax; pdwType
0x18001e738  xor     edx, edx; lpSubKey
0x18001e73a  call    cs:__imp_RegGetValueW
0x18001e740  test    eax, eax
0x18001e742  jnz     short loc_18001E78C
0x18001e744  xor     edx, edx
0x18001e746  mov     eax, edx
0x18001e748  mov     r8, rdi
0x18001e74b  imul    rcx, rax, 0C8h
0x18001e752  lea     rax, ?g_szSchemeNames@@3PAY0GE@GA; ushort (near * g_szSchemeNames)[100]
0x18001e759  add     rcx, rax
0x18001e75c  sub     r8, rcx
0x18001e75f  movzx   eax, word ptr [rcx]
0x18001e762  cmp     ax, [rcx+r8]
0x18001e767  jnz     short loc_18001E776
0x18001e769  add     rcx, 2
0x18001e76d  test    ax, ax
0x18001e770  jnz     short loc_18001E75F
0x18001e772  xor     eax, eax
0x18001e774  jmp     short loc_18001E77B
0x18001e776  sbb     eax, eax
0x18001e778  or      eax, 1
0x18001e77b  test    eax, eax
0x18001e77d  lea     ecx, [rdx+2]
0x18001e780  cmovnz  ecx, ebx
0x18001e783  inc     edx
0x18001e785  mov     ebx, ecx
0x18001e787  cmp     edx, 8
0x18001e78a  jl      short loc_18001E746
0x18001e78c  mov     rcx, [rbp+hKey]; hKey
0x18001e790  call    cs:__imp_RegCloseKey
0x18001e796  mov     rcx, rdi; void *
0x18001e799  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18001e79e  mov     eax, ebx
0x18001e7a0  add     rsp, 40h
0x18001e7a4  pop     rdi
0x18001e7a5  pop     rbx
0x18001e7a6  pop     rbp
0x18001e7a7  retn
```
