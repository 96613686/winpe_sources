# OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x180017278`
- end: `0x180017362`
- name: `?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `234`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180005fbc`
- `0x1800060d8`
- `0x18000649c`

## callees

- `0x180017278`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800172ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800172ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017331`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017331`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800172f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800172f9`

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
0x180017278  push    rbp
0x18001727a  push    rbx
0x18001727b  push    rsi
0x18001727c  push    rdi
0x18001727d  mov     rbp, rsp
0x180017280  sub     rsp, 48h
0x180017284  mov     [rbp+Type], 0
0x18001728b  mov     rdi, r9
0x18001728e  mov     dword ptr [rbp+Data], 0
0x180017295  mov     rsi, r8
0x180017298  mov     [rbp+cbData], 4
0x18001729f  mov     [rbp+hKey], 0
0x1800172a7  test    rcx, rcx
0x1800172aa  jnz     short loc_1800172B3
0x1800172ac  mov     ebx, 80070057h
0x1800172b1  jmp     short loc_180017305
0x1800172b3  test    rdi, rdi
0x1800172b6  jz      short loc_1800172AC
0x1800172b8  lea     rax, [rbp+hKey]
0x1800172bc  mov     r9d, 20119h; samDesired
0x1800172c2  xor     r8d, r8d; ulOptions
0x1800172c5  mov     [rsp+48h+phkResult], rax; phkResult
0x1800172ca  call    cs:__imp_RegOpenKeyExW
0x1800172d1  nop     dword ptr [rax+rax+00h]
0x1800172d6  mov     ebx, eax
0x1800172d8  test    eax, eax
0x1800172da  jz      short loc_180017311
0x1800172dc  jle     short loc_1800172E7
0x1800172de  movzx   ebx, ax
0x1800172e1  or      ebx, 80070000h
0x1800172e7  test    ebx, ebx
0x1800172e9  js      short loc_1800172F0
0x1800172eb  mov     ecx, dword ptr [rbp+Data]
0x1800172ee  mov     [rdi], ecx
0x1800172f0  mov     rcx, [rbp+hKey]; hKey
0x1800172f4  test    rcx, rcx
0x1800172f7  jz      short loc_180017305
0x1800172f9  call    cs:__imp_RegCloseKey
0x180017300  nop     dword ptr [rax+rax+00h]
0x180017305  mov     eax, ebx
0x180017307  add     rsp, 48h
0x18001730b  pop     rdi
0x18001730c  pop     rsi
0x18001730d  pop     rbx
0x18001730e  pop     rbp
0x18001730f  retn
0x180017311  mov     rcx, [rbp+hKey]; hKey
0x180017315  lea     rax, [rbp+cbData]
0x180017319  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18001731e  lea     r9, [rbp+Type]; lpType
0x180017322  lea     rax, [rbp+Data]
0x180017326  xor     r8d, r8d; lpReserved
0x180017329  mov     rdx, rsi; lpValueName
0x18001732c  mov     [rsp+48h+phkResult], rax; lpData
0x180017331  call    cs:__imp_RegQueryValueExW
0x180017338  nop     dword ptr [rax+rax+00h]
0x18001733d  cmp     eax, 2
0x180017340  jnz     short loc_180017349
0x180017342  mov     ebx, 80070002h
0x180017347  jmp     short loc_1800172F0
0x180017349  cmp     [rbp+Type], 4
0x18001734d  jz      short loc_180017356
0x18001734f  mov     ebx, 8007065Dh
0x180017354  jmp     short loc_1800172F0
0x180017356  xor     ebx, ebx
0x180017358  test    eax, eax
0x18001735a  jz      short loc_1800172EB
0x18001735c  jg      short loc_1800172DE
0x18001735e  mov     ebx, eax
0x180017360  jmp     short loc_1800172E7
```
