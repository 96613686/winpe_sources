# OmaDmRegistrySetString(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800618d0`
- end: `0x1800619cc`
- name: `?OmaDmRegistrySetString@@YAJPEAUHKEY__@@PEBG11@Z`
- size: `252`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18005f930`

## callees

- `0x18005d530`
- `0x1800618d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061923`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180061923`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180061982`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180061982`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800619b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800619b0`

## pseudocode

```c
__int64 __fastcall OmaDmRegistrySetString(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  unsigned int v7; // ebx
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF
  unsigned __int64 v12; // [rsp+58h] [rbp+10h] BYREF

  hKey = 0;
  v12 = 0;
  if ( !a1 || !a4 )
  {
    v7 = -2147024809;
    goto LABEL_14;
  }
  if ( !a2 )
  {
    hKey = a1;
    goto LABEL_9;
  }
  v8 = RegOpenKeyExW(a1, a2, 0, 0x20106u, &hKey);
  v7 = v8;
  if ( !v8 )
  {
LABEL_9:
    v7 = StringCbLengthW(a4, 0xFFFFFFFE, &v12);
    if ( (v7 & 0x80000000) == 0 )
    {
      v9 = RegSetValueExW(hKey, a3, 0, 1u, (const BYTE *)a4, v12 + 2);
      if ( v9 )
      {
        if ( v9 > 0 )
          v7 = (unsigned __int16)v9 | 0x80070000;
        else
          v7 = v9;
      }
    }
LABEL_14:
    if ( !a2 )
      return v7;
    goto LABEL_15;
  }
  if ( v8 > 0 )
    v7 = (unsigned __int16)v8 | 0x80070000;
LABEL_15:
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x1800618d0  mov     [rsp+arg_10], rbx
0x1800618d5  push    rbp
0x1800618d6  push    rsi
0x1800618d7  push    rdi
0x1800618d8  sub     rsp, 30h
0x1800618dc  mov     [rsp+48h+hKey], 0
0x1800618e5  mov     rsi, r9
0x1800618e8  mov     [rsp+48h+arg_8], 0
0x1800618f1  mov     rbp, r8
0x1800618f4  mov     rdi, rdx
0x1800618f7  test    rcx, rcx
0x1800618fa  jnz     short loc_180061906
0x1800618fc  mov     ebx, 80070057h
0x180061901  jmp     loc_1800619A1
0x180061906  test    rsi, rsi
0x180061909  jz      short loc_1800618FC
0x18006190b  test    rdi, rdi
0x18006190e  jz      short loc_180061942
0x180061910  lea     rax, [rsp+48h+hKey]
0x180061915  mov     r9d, 20106h; samDesired
0x18006191b  xor     r8d, r8d; ulOptions
0x18006191e  mov     [rsp+48h+phkResult], rax; phkResult
0x180061923  call    cs:__imp_RegOpenKeyExW
0x18006192a  nop     dword ptr [rax+rax+00h]
0x18006192f  mov     ebx, eax
0x180061931  test    eax, eax
0x180061933  jz      short loc_180061947
0x180061935  jle     short loc_1800619A6
0x180061937  movzx   ebx, ax
0x18006193a  or      ebx, 80070000h
0x180061940  jmp     short loc_1800619A6
0x180061942  mov     [rsp+48h+hKey], rcx
0x180061947  lea     r8, [rsp+48h+arg_8]; unsigned __int64 *
0x18006194c  mov     edx, 0FFFFFFFEh; unsigned __int64
0x180061951  mov     rcx, rsi; unsigned __int16 *
0x180061954  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180061959  mov     ebx, eax
0x18006195b  test    eax, eax
0x18006195d  js      short loc_1800619A1
0x18006195f  mov     rcx, [rsp+48h+arg_8]
0x180061964  mov     r9d, 1; dwType
0x18006196a  add     rcx, 2
0x18006196e  xor     r8d, r8d; Reserved
0x180061971  mov     [rsp+48h+cbData], ecx; cbData
0x180061975  mov     rdx, rbp; lpValueName
0x180061978  mov     rcx, [rsp+48h+hKey]; hKey
0x18006197d  mov     [rsp+48h+phkResult], rsi; lpData
0x180061982  call    cs:__imp_RegSetValueExW
0x180061989  nop     dword ptr [rax+rax+00h]
0x18006198e  test    eax, eax
0x180061990  jz      short loc_1800619A1
0x180061992  jg      short loc_180061998
0x180061994  mov     ebx, eax
0x180061996  jmp     short loc_1800619A1
0x180061998  movzx   ebx, ax
0x18006199b  or      ebx, 80070000h
0x1800619a1  test    rdi, rdi
0x1800619a4  jz      short loc_1800619BC
0x1800619a6  mov     rcx, [rsp+48h+hKey]; hKey
0x1800619ab  test    rcx, rcx
0x1800619ae  jz      short loc_1800619BC
0x1800619b0  call    cs:__imp_RegCloseKey
0x1800619b7  nop     dword ptr [rax+rax+00h]
0x1800619bc  mov     eax, ebx
0x1800619be  mov     rbx, [rsp+48h+arg_10]
0x1800619c3  add     rsp, 30h
0x1800619c7  pop     rdi
0x1800619c8  pop     rsi
0x1800619c9  pop     rbp
0x1800619ca  retn
```
