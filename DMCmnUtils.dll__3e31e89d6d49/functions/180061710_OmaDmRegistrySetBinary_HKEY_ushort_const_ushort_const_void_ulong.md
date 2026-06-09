# OmaDmRegistrySetBinary(HKEY__ *,ushort const *,ushort const *,void *,ulong)

- ea: `0x180061710`
- end: `0x1800617e4`
- name: `?OmaDmRegistrySetBinary@@YAJPEAUHKEY__@@PEBG1PEAXK@Z`
- size: `212`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180061710`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061757`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061757`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006179e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006179e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800617cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800617cc`

## pseudocode

```c
__int64 __fastcall OmaDmRegistrySetBinary(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const BYTE *a4,
        DWORD cbData)
{
  unsigned int v8; // ebx
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  hKey = 0;
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
    v10 = RegSetValueExW(a1, a3, 0, 3u, a4, cbData);
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
  v9 = RegOpenKeyExW(a1, a2, 0, 0x20106u, &hKey);
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
0x180061710  push    rbx
0x180061712  push    rbp
0x180061713  push    rsi
0x180061714  push    rdi
0x180061715  sub     rsp, 38h
0x180061719  mov     [rsp+58h+hKey], 0
0x180061722  mov     rsi, r9
0x180061725  mov     rbp, r8
0x180061728  mov     rdi, rdx
0x18006172b  test    rcx, rcx
0x18006172e  jnz     short loc_18006173A
0x180061730  mov     ebx, 80070057h
0x180061735  jmp     loc_1800617BD
0x18006173a  test    rsi, rsi
0x18006173d  jz      short loc_180061730
0x18006173f  test    rdi, rdi
0x180061742  jz      short loc_18006177D
0x180061744  lea     rax, [rsp+58h+hKey]
0x180061749  mov     r9d, 20106h; samDesired
0x18006174f  xor     r8d, r8d; ulOptions
0x180061752  mov     [rsp+58h+phkResult], rax; phkResult
0x180061757  call    cs:__imp_RegOpenKeyExW
0x18006175e  nop     dword ptr [rax+rax+00h]
0x180061763  mov     ebx, eax
0x180061765  test    eax, eax
0x180061767  jz      short loc_180061776
0x180061769  jle     short loc_1800617C2
0x18006176b  movzx   ebx, ax
0x18006176e  or      ebx, 80070000h
0x180061774  jmp     short loc_1800617C2
0x180061776  mov     rcx, [rsp+58h+hKey]; hKey
0x18006177b  jmp     short loc_180061782
0x18006177d  mov     [rsp+58h+hKey], rcx
0x180061782  mov     eax, [rsp+58h+arg_20]
0x180061789  xor     ebx, ebx
0x18006178b  mov     [rsp+58h+cbData], eax; cbData
0x18006178f  xor     r8d, r8d; Reserved
0x180061792  mov     rdx, rbp; lpValueName
0x180061795  mov     [rsp+58h+phkResult], rsi; lpData
0x18006179a  lea     r9d, [rbx+3]; dwType
0x18006179e  call    cs:__imp_RegSetValueExW
0x1800617a5  nop     dword ptr [rax+rax+00h]
0x1800617aa  test    eax, eax
0x1800617ac  jz      short loc_1800617BD
0x1800617ae  jg      short loc_1800617B4
0x1800617b0  mov     ebx, eax
0x1800617b2  jmp     short loc_1800617BD
0x1800617b4  movzx   ebx, ax
0x1800617b7  or      ebx, 80070000h
0x1800617bd  test    rdi, rdi
0x1800617c0  jz      short loc_1800617D8
0x1800617c2  mov     rcx, [rsp+58h+hKey]; hKey
0x1800617c7  test    rcx, rcx
0x1800617ca  jz      short loc_1800617D8
0x1800617cc  call    cs:__imp_RegCloseKey
0x1800617d3  nop     dword ptr [rax+rax+00h]
0x1800617d8  mov     eax, ebx
0x1800617da  add     rsp, 38h
0x1800617de  pop     rdi
0x1800617df  pop     rsi
0x1800617e0  pop     rbp
0x1800617e1  pop     rbx
0x1800617e2  retn
```
