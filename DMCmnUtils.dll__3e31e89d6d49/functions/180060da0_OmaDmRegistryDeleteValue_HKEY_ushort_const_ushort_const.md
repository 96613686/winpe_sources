# OmaDmRegistryDeleteValue(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180060da0`
- end: `0x180060e5e`
- name: `?OmaDmRegistryDeleteValue@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `190`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180060da0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060dde`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060dde`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060e3a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060e3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060e11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060e11`

## pseudocode

```c
__int64 __fastcall OmaDmRegistryDeleteValue(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = a1;
  if ( a1 )
  {
    if ( a2 && (v6 = RegOpenKeyExW(a1, a2, 0, 0x20106u, &hKey), (v5 = v6) != 0) )
    {
      if ( v6 != 2 )
      {
        if ( v6 <= 0 )
          goto LABEL_8;
LABEL_7:
        v5 = (unsigned __int16)v6 | 0x80070000;
        goto LABEL_8;
      }
    }
    else
    {
      v5 = 0;
      v6 = RegDeleteValueW(hKey, a3);
      if ( !v6 )
        goto LABEL_8;
      if ( v6 != 2 )
      {
        if ( v6 <= 0 )
        {
          v5 = v6;
          goto LABEL_8;
        }
        goto LABEL_7;
      }
    }
    v5 = 1;
    goto LABEL_8;
  }
  v5 = -2147024809;
LABEL_8:
  if ( hKey && hKey != a1 )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x180060da0  mov     [rsp+arg_8], rbx
0x180060da5  mov     [rsp+arg_10], rsi
0x180060daa  push    rdi
0x180060dab  sub     rsp, 30h
0x180060daf  mov     [rsp+38h+hKey], rcx
0x180060db4  mov     rsi, r8
0x180060db7  mov     rdi, rcx
0x180060dba  test    rcx, rcx
0x180060dbd  jnz     short loc_180060DC6
0x180060dbf  mov     ebx, 80070057h
0x180060dc4  jmp     short loc_180060E02
0x180060dc6  test    rdx, rdx
0x180060dc9  jz      short loc_180060E30
0x180060dcb  lea     rax, [rsp+38h+hKey]
0x180060dd0  mov     r9d, 20106h; samDesired
0x180060dd6  xor     r8d, r8d; ulOptions
0x180060dd9  mov     [rsp+38h+phkResult], rax; phkResult
0x180060dde  call    cs:__imp_RegOpenKeyExW
0x180060de5  nop     dword ptr [rax+rax+00h]
0x180060dea  mov     ebx, eax
0x180060dec  test    eax, eax
0x180060dee  jz      short loc_180060E30
0x180060df0  cmp     eax, 2
0x180060df3  jz      short loc_180060E4F
0x180060df5  test    eax, eax
0x180060df7  jle     short loc_180060E02
0x180060df9  movzx   ebx, ax
0x180060dfc  or      ebx, 80070000h
0x180060e02  mov     rcx, [rsp+38h+hKey]; hKey
0x180060e07  test    rcx, rcx
0x180060e0a  jz      short loc_180060E1D
0x180060e0c  cmp     rcx, rdi
0x180060e0f  jz      short loc_180060E1D
0x180060e11  call    cs:__imp_RegCloseKey
0x180060e18  nop     dword ptr [rax+rax+00h]
0x180060e1d  mov     rsi, [rsp+38h+arg_10]
0x180060e22  mov     eax, ebx
0x180060e24  mov     rbx, [rsp+38h+arg_8]
0x180060e29  add     rsp, 30h
0x180060e2d  pop     rdi
0x180060e2e  retn
0x180060e30  mov     rcx, [rsp+38h+hKey]; hKey
0x180060e35  mov     rdx, rsi; lpValueName
0x180060e38  xor     ebx, ebx
0x180060e3a  call    cs:__imp_RegDeleteValueW
0x180060e41  nop     dword ptr [rax+rax+00h]
0x180060e46  test    eax, eax
0x180060e48  jz      short loc_180060E02
0x180060e4a  cmp     eax, 2
0x180060e4d  jnz     short loc_180060E56
0x180060e4f  mov     ebx, 1
0x180060e54  jmp     short loc_180060E02
0x180060e56  test    eax, eax
0x180060e58  jg      short loc_180060DF9
0x180060e5a  mov     ebx, eax
0x180060e5c  jmp     short loc_180060E02
```
