# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x180090918`
- end: `0x1800909d2`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `186`
- prototype: `unsigned int __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, BYTE *lpData, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180090758`

## callees

- `0x180090918`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800909a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800909a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800909bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800909bf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009096f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009096f`

## pseudocode

```c
__int64 __fastcall _RegSetKeyValueWithSDDL(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        BYTE *lpData,
        unsigned int a6,
        struct _SECURITY_ATTRIBUTES *a7)
{
  HKEY v7; // rcx
  unsigned int v8; // edi
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  v7 = HKEY_CURRENT_USER;
  hKey = 0;
  if ( SubKey[0] )
  {
    v8 = RegCreateKeyExW(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\TabletTip\\EmbeddedInkControl",
           0,
           0,
           0,
           2u,
           a7,
           &hKey,
           0);
    if ( v8 )
      return v8;
    v7 = hKey;
  }
  else
  {
    hKey = HKEY_CURRENT_USER;
  }
  v8 = RegSetValueExW(v7, L"HandwritingViewLaunchedBefore", 0, 4u, lpData, 4u);
  if ( hKey != HKEY_CURRENT_USER )
    RegCloseKey(hKey);
  return v8;
}

```

## disassembly

```asm
0x180090918  mov     r11, rsp
0x18009091b  mov     [r11+8], rsi
0x18009091f  mov     [r11+18h], r8
0x180090923  push    rdi
0x180090924  sub     rsp, 50h
0x180090928  xor     esi, esi
0x18009092a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180090931  cmp     word ptr cs:SubKey, si; "Software\\Microsoft\\TabletTip\\Embedde"...
0x180090938  mov     [r11+18h], rsi
0x18009093c  jz      short loc_180090982
0x18009093e  mov     [r11-18h], rsi
0x180090942  lea     rax, [r11+18h]
0x180090946  mov     [r11-20h], rax
0x18009094a  lea     rdx, SubKey; "Software\\Microsoft\\TabletTip\\Embedde"...
0x180090951  mov     rax, [rsp+58h+arg_30]
0x180090959  xor     r9d, r9d; lpClass
0x18009095c  mov     [r11-28h], rax
0x180090960  xor     r8d, r8d; Reserved
0x180090963  mov     [rsp+58h+samDesired], 2; samDesired
0x18009096b  mov     [rsp+58h+dwOptions], esi; dwOptions
0x18009096f  call    cs:__imp_RegCreateKeyExW
0x180090975  mov     edi, eax
0x180090977  test    eax, eax
0x180090979  jnz     short loc_1800909C5
0x18009097b  mov     rcx, [rsp+58h+hKey]
0x180090980  jmp     short loc_180090987
0x180090982  mov     [rsp+58h+hKey], rcx
0x180090987  mov     rax, [rsp+58h+lpData]
0x18009098f  lea     rdx, ValueName; "HandwritingViewLaunchedBefore"
0x180090996  mov     r9d, 4; dwType
0x18009099c  xor     r8d, r8d; Reserved
0x18009099f  mov     [rsp+58h+samDesired], r9d; cbData
0x1800909a4  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x1800909a9  call    cs:__imp_RegSetValueExW
0x1800909af  mov     rcx, [rsp+58h+hKey]; hKey
0x1800909b4  mov     edi, eax
0x1800909b6  cmp     rcx, 0FFFFFFFF80000001h
0x1800909bd  jz      short loc_1800909C5
0x1800909bf  call    cs:__imp_RegCloseKey
0x1800909c5  mov     rsi, [rsp+58h+arg_0]
0x1800909ca  mov     eax, edi
0x1800909cc  add     rsp, 50h
0x1800909d0  pop     rdi
0x1800909d1  retn
```
