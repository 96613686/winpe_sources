# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x18002aaa0`
- end: `0x18002ab58`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `184`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, DWORD, BYTE *lpData, DWORD cbData)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002a320`
- `0x18002a35c`
- `0x18002a73c`

## callees

- `0x18002aaa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ab3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ab3b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002aaf0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002aaf0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ab29`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002ab29`

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
  HKEY v8; // rbx
  unsigned int v9; // edi
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  hKey = 0;
  v8 = a1;
  if ( a2 && *a2 )
  {
    v9 = RegCreateKeyExW(a1, a2, 0, 0, 0, 2u, 0, &hKey, 0);
    if ( v9 )
      return v9;
    a1 = hKey;
  }
  else
  {
    hKey = a1;
  }
  v9 = RegSetValueExW(a1, a3, 0, a4, lpData, cbData);
  if ( hKey != v8 )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x18002aaa0  mov     r11, rsp
0x18002aaa3  mov     [r11+8], rbx
0x18002aaa7  mov     [r11+18h], rbp
0x18002aaab  push    rsi
0x18002aaac  push    rdi
0x18002aaad  push    r14
0x18002aaaf  sub     rsp, 50h
0x18002aab3  xor     r14d, r14d
0x18002aab6  mov     esi, r9d
0x18002aab9  mov     [r11+10h], r14
0x18002aabd  mov     rbp, r8
0x18002aac0  mov     rbx, rcx
0x18002aac3  test    rdx, rdx
0x18002aac6  jz      short loc_18002AB03
0x18002aac8  cmp     [rdx], r14w
0x18002aacc  jz      short loc_18002AB03
0x18002aace  mov     [r11-28h], r14
0x18002aad2  lea     rax, [r11+10h]
0x18002aad6  mov     [r11-30h], rax
0x18002aada  xor     r9d, r9d; lpClass
0x18002aadd  mov     [r11-38h], r14
0x18002aae1  xor     r8d, r8d; Reserved
0x18002aae4  mov     [rsp+68h+samDesired], 2; samDesired
0x18002aaec  mov     [r11-48h], r14d
0x18002aaf0  call    cs:__imp_RegCreateKeyExW
0x18002aaf6  mov     edi, eax
0x18002aaf8  test    eax, eax
0x18002aafa  jnz     short loc_18002AB41
0x18002aafc  mov     rcx, [rsp+68h+hKey]; hKey
0x18002ab01  jmp     short loc_18002AB08
0x18002ab03  mov     [rsp+68h+hKey], rbx
0x18002ab08  mov     eax, [rsp+68h+cbData]
0x18002ab0f  mov     r9d, esi; dwType
0x18002ab12  mov     [rsp+68h+samDesired], eax; cbData
0x18002ab16  xor     r8d, r8d; Reserved
0x18002ab19  mov     rax, [rsp+68h+arg_20]
0x18002ab21  mov     rdx, rbp; lpValueName
0x18002ab24  mov     [rsp+68h+lpData], rax; lpData
0x18002ab29  call    cs:__imp_RegSetValueExW
0x18002ab2f  mov     rcx, [rsp+68h+hKey]; hKey
0x18002ab34  mov     edi, eax
0x18002ab36  cmp     rcx, rbx
0x18002ab39  jz      short loc_18002AB41
0x18002ab3b  call    cs:__imp_RegCloseKey
0x18002ab41  lea     r11, [rsp+68h+var_18]
0x18002ab46  mov     eax, edi
0x18002ab48  mov     rbx, [r11+20h]
0x18002ab4c  mov     rbp, [r11+30h]
0x18002ab50  mov     rsp, r11
0x18002ab53  pop     r14
0x18002ab55  pop     rdi
0x18002ab56  pop     rsi
0x18002ab57  retn
```
