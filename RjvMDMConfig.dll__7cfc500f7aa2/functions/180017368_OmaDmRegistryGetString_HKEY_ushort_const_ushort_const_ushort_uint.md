# OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)

- ea: `0x180017368`
- end: `0x180017455`
- name: `?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z`
- size: `237`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180005bfc`
- `0x180017088`

## callees

- `0x180017368`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800173c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800173c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001740b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001740b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017439`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017439`

## pseudocode

```c
__int64 __fastcall OmaDmRegistryGetString(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        BYTE *a4,
        DWORD cbData)
{
  unsigned int v8; // ebx
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  DWORD Type; // [rsp+50h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+10h] BYREF

  Type = 1;
  hKey = 0;
  cbData *= 2;
  if ( !a1 || !a4 )
  {
    v8 = -2147024809;
    goto LABEL_14;
  }
  if ( !a2 )
  {
    hKey = a1;
LABEL_10:
    v8 = 0;
    v10 = RegQueryValueExW(a1, a3, 0, &Type, a4, &cbData);
    if ( v10 )
    {
      if ( v10 > 0 )
        v8 = (unsigned __int16)v10 | 0x80070000;
      else
        v8 = v10;
    }
LABEL_14:
    if ( !a2 )
      return v8;
    goto LABEL_15;
  }
  v9 = RegOpenKeyExW(a1, a2, 0, 0x20119u, &hKey);
  v8 = v9;
  if ( !v9 )
  {
    a1 = hKey;
    goto LABEL_10;
  }
  if ( v9 > 0 )
    v8 = (unsigned __int16)v9 | 0x80070000;
LABEL_15:
  if ( hKey )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x180017368  mov     [rsp+arg_10], rbx
0x18001736d  push    rbp
0x18001736e  push    rsi
0x18001736f  push    rdi
0x180017370  sub     rsp, 30h
0x180017374  mov     eax, [rsp+48h+cbData]
0x180017378  mov     rsi, r9
0x18001737b  add     eax, eax
0x18001737d  mov     [rsp+48h+Type], 1
0x180017385  mov     [rsp+48h+hKey], 0
0x18001738e  mov     rbp, r8
0x180017391  mov     [rsp+48h+cbData], eax
0x180017395  mov     rdi, rdx
0x180017398  test    rcx, rcx
0x18001739b  jnz     short loc_1800173A7
0x18001739d  mov     ebx, 80070057h
0x1800173a2  jmp     loc_18001742A
0x1800173a7  test    rsi, rsi
0x1800173aa  jz      short loc_18001739D
0x1800173ac  test    rdi, rdi
0x1800173af  jz      short loc_1800173EA
0x1800173b1  lea     rax, [rsp+48h+hKey]
0x1800173b6  mov     r9d, 20119h; samDesired
0x1800173bc  xor     r8d, r8d; ulOptions
0x1800173bf  mov     [rsp+48h+phkResult], rax; phkResult
0x1800173c4  call    cs:__imp_RegOpenKeyExW
0x1800173cb  nop     dword ptr [rax+rax+00h]
0x1800173d0  mov     ebx, eax
0x1800173d2  test    eax, eax
0x1800173d4  jz      short loc_1800173E3
0x1800173d6  jle     short loc_18001742F
0x1800173d8  movzx   ebx, ax
0x1800173db  or      ebx, 80070000h
0x1800173e1  jmp     short loc_18001742F
0x1800173e3  mov     rcx, [rsp+48h+hKey]; hKey
0x1800173e8  jmp     short loc_1800173EF
0x1800173ea  mov     [rsp+48h+hKey], rcx
0x1800173ef  lea     rax, [rsp+48h+cbData]
0x1800173f4  xor     r8d, r8d; lpReserved
0x1800173f7  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800173fc  lea     r9, [rsp+48h+Type]; lpType
0x180017401  mov     rdx, rbp; lpValueName
0x180017404  mov     [rsp+48h+phkResult], rsi; lpData
0x180017409  xor     ebx, ebx
0x18001740b  call    cs:__imp_RegQueryValueExW
0x180017412  nop     dword ptr [rax+rax+00h]
0x180017417  test    eax, eax
0x180017419  jz      short loc_18001742A
0x18001741b  jg      short loc_180017421
0x18001741d  mov     ebx, eax
0x18001741f  jmp     short loc_18001742A
0x180017421  movzx   ebx, ax
0x180017424  or      ebx, 80070000h
0x18001742a  test    rdi, rdi
0x18001742d  jz      short loc_180017445
0x18001742f  mov     rcx, [rsp+48h+hKey]; hKey
0x180017434  test    rcx, rcx
0x180017437  jz      short loc_180017445
0x180017439  call    cs:__imp_RegCloseKey
0x180017440  nop     dword ptr [rax+rax+00h]
0x180017445  mov     eax, ebx
0x180017447  mov     rbx, [rsp+48h+arg_10]
0x18001744c  add     rsp, 30h
0x180017450  pop     rdi
0x180017451  pop     rsi
0x180017452  pop     rbp
0x180017453  retn
```
