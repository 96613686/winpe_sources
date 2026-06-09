# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x180035788`
- end: `0x180035840`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `184`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const void *, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035694`
- `0x1800356d8`
- `0x180035730`

## callees

- `0x180035788`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180035811`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180035811`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035823`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035823`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800357d8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800357d8`

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
0x180035788  mov     r11, rsp
0x18003578b  mov     [r11+8], rbx
0x18003578f  mov     [r11+18h], rbp
0x180035793  push    rsi
0x180035794  push    rdi
0x180035795  push    r14
0x180035797  sub     rsp, 50h
0x18003579b  xor     r14d, r14d
0x18003579e  mov     esi, r9d
0x1800357a1  mov     [r11+10h], r14
0x1800357a5  mov     rbp, r8
0x1800357a8  mov     rbx, rcx
0x1800357ab  test    rdx, rdx
0x1800357ae  jz      short loc_1800357EB
0x1800357b0  cmp     [rdx], r14w
0x1800357b4  jz      short loc_1800357EB
0x1800357b6  mov     [r11-28h], r14
0x1800357ba  lea     rax, [r11+10h]
0x1800357be  mov     [r11-30h], rax
0x1800357c2  xor     r9d, r9d; lpClass
0x1800357c5  mov     [r11-38h], r14
0x1800357c9  xor     r8d, r8d; Reserved
0x1800357cc  mov     [rsp+68h+samDesired], 2; samDesired
0x1800357d4  mov     [r11-48h], r14d
0x1800357d8  call    cs:__imp_RegCreateKeyExW
0x1800357de  mov     edi, eax
0x1800357e0  test    eax, eax
0x1800357e2  jnz     short loc_180035829
0x1800357e4  mov     rcx, [rsp+68h+hKey]; hKey
0x1800357e9  jmp     short loc_1800357F0
0x1800357eb  mov     [rsp+68h+hKey], rbx
0x1800357f0  mov     eax, [rsp+68h+cbData]
0x1800357f7  mov     r9d, esi; dwType
0x1800357fa  mov     [rsp+68h+samDesired], eax; cbData
0x1800357fe  xor     r8d, r8d; Reserved
0x180035801  mov     rax, [rsp+68h+arg_20]
0x180035809  mov     rdx, rbp; lpValueName
0x18003580c  mov     [rsp+68h+lpData], rax; lpData
0x180035811  call    cs:__imp_RegSetValueExW
0x180035817  mov     rcx, [rsp+68h+hKey]; hKey
0x18003581c  mov     edi, eax
0x18003581e  cmp     rcx, rbx
0x180035821  jz      short loc_180035829
0x180035823  call    cs:__imp_RegCloseKey
0x180035829  lea     r11, [rsp+68h+var_18]
0x18003582e  mov     eax, edi
0x180035830  mov     rbx, [r11+20h]
0x180035834  mov     rbp, [r11+30h]
0x180035838  mov     rsp, r11
0x18003583b  pop     r14
0x18003583d  pop     rdi
0x18003583e  pop     rsi
0x18003583f  retn
```
