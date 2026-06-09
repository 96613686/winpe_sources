# OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x180061420`
- end: `0x18006150a`
- name: `?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `234`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18005e8e0`
- `0x180064ea4`

## callees

- `0x180061420`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061472`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061472`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800614d9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800614d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800614a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800614a1`

## pseudocode

```c
__int64 __fastcall OmaDmRegistryGetDWORD(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  signed int v6; // ebx
  LSTATUS v7; // eax
  BYTE Data[4]; // [rsp+30h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-14h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-10h] BYREF
  DWORD Type; // [rsp+70h] [rbp+28h] BYREF

  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  hKey = 0;
  if ( !a1 || !a4 )
    return (unsigned int)-2147024809;
  v7 = RegOpenKeyExW(a1, a2, 0, 0x20119u, &hKey);
  v6 = v7;
  if ( v7 )
  {
    if ( v7 <= 0 )
      goto LABEL_7;
    goto LABEL_6;
  }
  v7 = RegQueryValueExW(hKey, a3, 0, &Type, Data, &cbData);
  if ( v7 == 2 )
  {
    v6 = -2147024894;
  }
  else
  {
    if ( Type == 4 )
    {
      v6 = 0;
      if ( !v7 )
      {
LABEL_8:
        *a4 = *(_DWORD *)Data;
        goto LABEL_9;
      }
      if ( v7 <= 0 )
      {
        v6 = v7;
LABEL_7:
        if ( v6 < 0 )
          goto LABEL_9;
        goto LABEL_8;
      }
LABEL_6:
      v6 = (unsigned __int16)v7 | 0x80070000;
      goto LABEL_7;
    }
    v6 = -2147023267;
  }
LABEL_9:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180061420  push    rbp
0x180061422  push    rbx
0x180061423  push    rsi
0x180061424  push    rdi
0x180061425  mov     rbp, rsp
0x180061428  sub     rsp, 48h
0x18006142c  mov     [rbp+Type], 0
0x180061433  mov     rdi, r9
0x180061436  mov     dword ptr [rbp+Data], 0
0x18006143d  mov     rsi, r8
0x180061440  mov     [rbp+cbData], 4
0x180061447  mov     [rbp+hKey], 0
0x18006144f  test    rcx, rcx
0x180061452  jnz     short loc_18006145B
0x180061454  mov     ebx, 80070057h
0x180061459  jmp     short loc_1800614AD
0x18006145b  test    rdi, rdi
0x18006145e  jz      short loc_180061454
0x180061460  lea     rax, [rbp+hKey]
0x180061464  mov     r9d, 20119h; samDesired
0x18006146a  xor     r8d, r8d; ulOptions
0x18006146d  mov     [rsp+48h+phkResult], rax; phkResult
0x180061472  call    cs:__imp_RegOpenKeyExW
0x180061479  nop     dword ptr [rax+rax+00h]
0x18006147e  mov     ebx, eax
0x180061480  test    eax, eax
0x180061482  jz      short loc_1800614B9
0x180061484  jle     short loc_18006148F
0x180061486  movzx   ebx, ax
0x180061489  or      ebx, 80070000h
0x18006148f  test    ebx, ebx
0x180061491  js      short loc_180061498
0x180061493  mov     ecx, dword ptr [rbp+Data]
0x180061496  mov     [rdi], ecx
0x180061498  mov     rcx, [rbp+hKey]; hKey
0x18006149c  test    rcx, rcx
0x18006149f  jz      short loc_1800614AD
0x1800614a1  call    cs:__imp_RegCloseKey
0x1800614a8  nop     dword ptr [rax+rax+00h]
0x1800614ad  mov     eax, ebx
0x1800614af  add     rsp, 48h
0x1800614b3  pop     rdi
0x1800614b4  pop     rsi
0x1800614b5  pop     rbx
0x1800614b6  pop     rbp
0x1800614b7  retn
0x1800614b9  mov     rcx, [rbp+hKey]; hKey
0x1800614bd  lea     rax, [rbp+cbData]
0x1800614c1  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800614c6  lea     r9, [rbp+Type]; lpType
0x1800614ca  lea     rax, [rbp+Data]
0x1800614ce  xor     r8d, r8d; lpReserved
0x1800614d1  mov     rdx, rsi; lpValueName
0x1800614d4  mov     [rsp+48h+phkResult], rax; lpData
0x1800614d9  call    cs:__imp_RegQueryValueExW
0x1800614e0  nop     dword ptr [rax+rax+00h]
0x1800614e5  cmp     eax, 2
0x1800614e8  jnz     short loc_1800614F1
0x1800614ea  mov     ebx, 80070002h
0x1800614ef  jmp     short loc_180061498
0x1800614f1  cmp     [rbp+Type], 4
0x1800614f5  jz      short loc_1800614FE
0x1800614f7  mov     ebx, 8007065Dh
0x1800614fc  jmp     short loc_180061498
0x1800614fe  xor     ebx, ebx
0x180061500  test    eax, eax
0x180061502  jz      short loc_180061493
0x180061504  jg      short loc_180061486
0x180061506  mov     ebx, eax
0x180061508  jmp     short loc_18006148F
```
