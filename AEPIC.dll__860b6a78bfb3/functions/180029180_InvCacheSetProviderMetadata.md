# InvCacheSetProviderMetadata

- ea: `0x180029180`
- end: `0x180029229`
- name: `InvCacheSetProviderMetadata`
- size: `169`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800196e0`
- `0x180019730`
- `0x180019760`

## callees

- `0x180029180`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002920b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002920b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800291c2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800291c2`

## pseudocode

```c
LSTATUS __fastcall InvCacheSetProviderMetadata(__int64 a1, const WCHAR *a2, int a3, const BYTE *a4, DWORD cbData)
{
  DWORD v6; // r9d
  __int64 v7; // rax
  HKEY v8; // rcx
  LSTATUS result; // eax
  int v10; // r8d
  int v11; // r8d

  if ( !a1 )
    return -2147024809;
  v6 = 1;
  if ( *(_DWORD *)a1 != 1 )
    return -2147024809;
  if ( !a2 )
    return -2147024809;
  if ( !*a2 )
    return -2147024809;
  v7 = *(_QWORD *)(a1 + 8);
  if ( !v7 )
    return -2147024809;
  v8 = *(HKEY *)(v7 + 8);
  if ( !v8 )
    return -2147024809;
  if ( a4 )
  {
    if ( a3 )
    {
      v10 = a3 - 1;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
          if ( v11 != 1 )
            return -2147023266;
          v6 = 3;
        }
      }
      else
      {
        v6 = 11;
      }
    }
    else
    {
      v6 = 4;
    }
    result = RegSetValueExW(v8, a2, 0, v6, a4, cbData);
  }
  else
  {
    result = RegDeleteValueW(v8, a2);
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180029180  sub     rsp, 38h
0x180029184  mov     r10, r9
0x180029187  test    rcx, rcx
0x18002918a  jz      loc_18002921F
0x180029190  mov     r9d, 1
0x180029196  cmp     [rcx], r9d
0x180029199  jnz     loc_18002921F
0x18002919f  test    rdx, rdx
0x1800291a2  jz      short loc_18002921F
0x1800291a4  xor     eax, eax
0x1800291a6  cmp     ax, [rdx]
0x1800291a9  jz      short loc_18002921F
0x1800291ab  mov     rax, [rcx+8]
0x1800291af  test    rax, rax
0x1800291b2  jz      short loc_18002921F
0x1800291b4  mov     rcx, [rax+8]; hKey
0x1800291b8  test    rcx, rcx
0x1800291bb  jz      short loc_18002921F
0x1800291bd  test    r10, r10
0x1800291c0  jnz     short loc_1800291CA
0x1800291c2  call    cs:__imp_RegDeleteValueW
0x1800291c8  jmp     short loc_180029211
0x1800291ca  test    r8d, r8d
0x1800291cd  jz      short loc_1800291F5
0x1800291cf  sub     r8d, r9d
0x1800291d2  jz      short loc_1800291ED
0x1800291d4  sub     r8d, r9d
0x1800291d7  jz      short loc_1800291FB
0x1800291d9  cmp     r8d, r9d
0x1800291dc  jz      short loc_1800291E5
0x1800291de  mov     eax, 8007065Eh
0x1800291e3  jmp     short loc_180029224
0x1800291e5  mov     r9d, 3
0x1800291eb  jmp     short loc_1800291FB
0x1800291ed  mov     r9d, 0Bh
0x1800291f3  jmp     short loc_1800291FB
0x1800291f5  mov     r9d, 4; dwType
0x1800291fb  mov     eax, [rsp+38h+arg_20]
0x1800291ff  xor     r8d, r8d; Reserved
0x180029202  mov     [rsp+38h+cbData], eax; cbData
0x180029206  mov     [rsp+38h+lpData], r10; lpData
0x18002920b  call    cs:__imp_RegSetValueExW
0x180029211  test    eax, eax
0x180029213  jle     short loc_180029224
0x180029215  movzx   eax, ax
0x180029218  or      eax, 80070000h
0x18002921d  jmp     short loc_180029224
0x18002921f  mov     eax, 80070057h
0x180029224  add     rsp, 38h
0x180029228  retn
```
