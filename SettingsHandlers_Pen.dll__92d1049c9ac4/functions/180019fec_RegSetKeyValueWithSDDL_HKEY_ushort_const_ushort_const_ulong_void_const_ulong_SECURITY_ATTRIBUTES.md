# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x180019fec`
- end: `0x18001a0b6`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `202`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const void *, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001747c`
- `0x18002efec`
- `0x18002f030`

## callees

- `0x180019fec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a08b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001a08b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a045`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a045`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a0a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a0a4`

## pseudocode

```c
__int64 __fastcall _RegSetKeyValueWithSDDL(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        BYTE *lpData,
        DWORD cbData,
        struct _SECURITY_ATTRIBUTES *a7)
{
  unsigned int v9; // edi
  HKEY v10; // rcx
  HKEY hKey; // [rsp+80h] [rbp+8h] BYREF

  hKey = 0;
  if ( a2 && *a2 )
  {
    v9 = RegCreateKeyExW(HKEY_CURRENT_USER, a2, 0, 0, 0, 2u, a7, &hKey, 0);
    if ( v9 )
      return v9;
    v10 = hKey;
  }
  else
  {
    v10 = HKEY_CURRENT_USER;
    hKey = HKEY_CURRENT_USER;
  }
  v9 = RegSetValueExW(v10, a3, 0, a4, lpData, cbData);
  if ( hKey != HKEY_CURRENT_USER )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x180019fec  mov     r11, rsp
0x180019fef  mov     [r11+8], rcx
0x180019ff3  push    rbp
0x180019ff4  push    rsi
0x180019ff5  push    rdi
0x180019ff6  push    r14
0x180019ff8  sub     rsp, 58h
0x180019ffc  xor     r14d, r14d
0x180019fff  mov     esi, r9d
0x18001a002  mov     [r11+8], r14
0x18001a006  mov     rbp, r8
0x18001a009  test    rdx, rdx
0x18001a00c  jz      short loc_18001A05B
0x18001a00e  cmp     [rdx], r14w
0x18001a012  jz      short loc_18001A05B
0x18001a014  mov     [r11-38h], r14
0x18001a018  lea     rax, [r11+8]
0x18001a01c  mov     [r11-40h], rax
0x18001a020  xor     r9d, r9d; lpClass
0x18001a023  mov     rax, [rsp+78h+arg_30]
0x18001a02b  xor     r8d, r8d; Reserved
0x18001a02e  mov     [r11-48h], rax
0x18001a032  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001a039  mov     [rsp+78h+samDesired], 2; samDesired
0x18001a041  mov     [r11-58h], r14d
0x18001a045  call    cs:__imp_RegCreateKeyExW
0x18001a04b  mov     edi, eax
0x18001a04d  test    eax, eax
0x18001a04f  jnz     short loc_18001A0AA
0x18001a051  mov     rcx, [rsp+78h+hKey]
0x18001a059  jmp     short loc_18001A06A
0x18001a05b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001a062  mov     [rsp+78h+hKey], rcx
0x18001a06a  mov     eax, [rsp+78h+cbData]
0x18001a071  mov     r9d, esi; dwType
0x18001a074  mov     [rsp+78h+samDesired], eax; cbData
0x18001a078  xor     r8d, r8d; Reserved
0x18001a07b  mov     rax, [rsp+78h+arg_20]
0x18001a083  mov     rdx, rbp; lpValueName
0x18001a086  mov     [rsp+78h+lpData], rax; lpData
0x18001a08b  call    cs:__imp_RegSetValueExW
0x18001a091  mov     rcx, [rsp+78h+hKey]; hKey
0x18001a099  mov     edi, eax
0x18001a09b  cmp     rcx, 0FFFFFFFF80000001h
0x18001a0a2  jz      short loc_18001A0AA
0x18001a0a4  call    cs:__imp_RegCloseKey
0x18001a0aa  mov     eax, edi
0x18001a0ac  add     rsp, 58h
0x18001a0b0  pop     r14
0x18001a0b2  pop     rdi
0x18001a0b3  pop     rsi
0x18001a0b4  pop     rbp
0x18001a0b5  retn
```
