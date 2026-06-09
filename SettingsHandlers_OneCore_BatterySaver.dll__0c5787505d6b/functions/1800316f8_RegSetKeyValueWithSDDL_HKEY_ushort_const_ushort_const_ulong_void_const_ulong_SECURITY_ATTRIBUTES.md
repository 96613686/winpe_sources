# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x1800316f8`
- end: `0x1800317aa`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `178`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, __int64, BYTE *lpData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800313b4`

## callees

- `0x1800316f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031747`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031747`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031797`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031797`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031781`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031781`

## pseudocode

```c
__int64 __fastcall _RegSetKeyValueWithSDDL(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        BYTE *lpData)
{
  HKEY v5; // rcx
  unsigned int v6; // edi
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  v5 = HKEY_CURRENT_USER;
  hKey = 0;
  if ( aSoftwareMicros_1[0] )
  {
    v6 = RegCreateKeyExW(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
           0,
           0,
           0,
           2u,
           0,
           &hKey,
           0);
    if ( v6 )
      return v6;
    v5 = hKey;
  }
  else
  {
    hKey = HKEY_CURRENT_USER;
  }
  v6 = RegSetValueExW(v5, L"IsBatteryPercentageEnabled", 0, 4u, lpData, 4u);
  if ( hKey != HKEY_CURRENT_USER )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x1800316f8  mov     r11, rsp
0x1800316fb  mov     [r11+8], rsi
0x1800316ff  mov     [r11+18h], r8
0x180031703  push    rdi
0x180031704  sub     rsp, 50h
0x180031708  xor     esi, esi
0x18003170a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180031711  cmp     word ptr cs:aSoftwareMicros_1, si; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180031718  mov     [r11+18h], rsi
0x18003171c  jz      short loc_18003175A
0x18003171e  mov     [r11-18h], rsi
0x180031722  lea     rax, [r11+18h]
0x180031726  mov     [r11-20h], rax
0x18003172a  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180031731  mov     [r11-28h], rsi
0x180031735  xor     r9d, r9d; lpClass
0x180031738  mov     [rsp+58h+samDesired], 2; samDesired
0x180031740  xor     r8d, r8d; Reserved
0x180031743  mov     [rsp+58h+dwOptions], esi; dwOptions
0x180031747  call    cs:__imp_RegCreateKeyExW
0x18003174d  mov     edi, eax
0x18003174f  test    eax, eax
0x180031751  jnz     short loc_18003179D
0x180031753  mov     rcx, [rsp+58h+hKey]
0x180031758  jmp     short loc_18003175F
0x18003175a  mov     [rsp+58h+hKey], rcx
0x18003175f  mov     rax, [rsp+58h+lpData]
0x180031767  lea     rdx, aIsbatteryperce; "IsBatteryPercentageEnabled"
0x18003176e  mov     r9d, 4; dwType
0x180031774  xor     r8d, r8d; Reserved
0x180031777  mov     [rsp+58h+samDesired], r9d; cbData
0x18003177c  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180031781  call    cs:__imp_RegSetValueExW
0x180031787  mov     rcx, [rsp+58h+hKey]; hKey
0x18003178c  mov     edi, eax
0x18003178e  cmp     rcx, 0FFFFFFFF80000001h
0x180031795  jz      short loc_18003179D
0x180031797  call    cs:__imp_RegCloseKey
0x18003179d  mov     rsi, [rsp+58h+arg_0]
0x1800317a2  mov     eax, edi
0x1800317a4  add     rsp, 50h
0x1800317a8  pop     rdi
0x1800317a9  retn
```
