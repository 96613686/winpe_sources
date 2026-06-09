# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x1800b9a18`
- end: `0x1800b9ada`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `194`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const void *, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b8cf0`
- `0x1800b8db0`

## callees

- `0x1800b9a18`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b9aaf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b9aaf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b9ac8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b9ac8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b9a69`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b9a69`

## pseudocode

```c
__int64 __fastcall _RegSetKeyValueWithSDDL(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        BYTE *lpData,
        DWORD cbData)
{
  unsigned int v8; // edi
  HKEY v9; // rcx
  HKEY hKey; // [rsp+80h] [rbp+8h] BYREF

  hKey = 0;
  if ( a2 && *a2 )
  {
    v8 = RegCreateKeyExW(HKEY_CURRENT_USER, a2, 0, 0, 0, 2u, 0, &hKey, 0);
    if ( v8 )
      return v8;
    v9 = hKey;
  }
  else
  {
    v9 = HKEY_CURRENT_USER;
    hKey = HKEY_CURRENT_USER;
  }
  v8 = RegSetValueExW(v9, a3, 0, a4, lpData, cbData);
  if ( hKey != HKEY_CURRENT_USER )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x1800b9a18  mov     r11, rsp
0x1800b9a1b  mov     [r11+8], rcx
0x1800b9a1f  push    rbp
0x1800b9a20  push    rsi
0x1800b9a21  push    rdi
0x1800b9a22  push    r14
0x1800b9a24  sub     rsp, 58h
0x1800b9a28  xor     r14d, r14d
0x1800b9a2b  mov     esi, r9d
0x1800b9a2e  mov     [r11+8], r14
0x1800b9a32  mov     rbp, r8
0x1800b9a35  test    rdx, rdx
0x1800b9a38  jz      short loc_1800B9A7F
0x1800b9a3a  cmp     [rdx], r14w
0x1800b9a3e  jz      short loc_1800B9A7F
0x1800b9a40  mov     [r11-38h], r14
0x1800b9a44  lea     rax, [r11+8]
0x1800b9a48  mov     [r11-40h], rax
0x1800b9a4c  xor     r9d, r9d; lpClass
0x1800b9a4f  mov     [r11-48h], r14
0x1800b9a53  xor     r8d, r8d; Reserved
0x1800b9a56  mov     [rsp+78h+samDesired], 2; samDesired
0x1800b9a5e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800b9a65  mov     [r11-58h], r14d
0x1800b9a69  call    cs:__imp_RegCreateKeyExW
0x1800b9a6f  mov     edi, eax
0x1800b9a71  test    eax, eax
0x1800b9a73  jnz     short loc_1800B9ACE
0x1800b9a75  mov     rcx, [rsp+78h+hKey]
0x1800b9a7d  jmp     short loc_1800B9A8E
0x1800b9a7f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800b9a86  mov     [rsp+78h+hKey], rcx
0x1800b9a8e  mov     eax, [rsp+78h+cbData]
0x1800b9a95  mov     r9d, esi; dwType
0x1800b9a98  mov     [rsp+78h+samDesired], eax; cbData
0x1800b9a9c  xor     r8d, r8d; Reserved
0x1800b9a9f  mov     rax, [rsp+78h+arg_20]
0x1800b9aa7  mov     rdx, rbp; lpValueName
0x1800b9aaa  mov     [rsp+78h+lpData], rax; lpData
0x1800b9aaf  call    cs:__imp_RegSetValueExW
0x1800b9ab5  mov     rcx, [rsp+78h+hKey]; hKey
0x1800b9abd  mov     edi, eax
0x1800b9abf  cmp     rcx, 0FFFFFFFF80000001h
0x1800b9ac6  jz      short loc_1800B9ACE
0x1800b9ac8  call    cs:__imp_RegCloseKey
0x1800b9ace  mov     eax, edi
0x1800b9ad0  add     rsp, 58h
0x1800b9ad4  pop     r14
0x1800b9ad6  pop     rdi
0x1800b9ad7  pop     rsi
0x1800b9ad8  pop     rbp
0x1800b9ad9  retn
```
