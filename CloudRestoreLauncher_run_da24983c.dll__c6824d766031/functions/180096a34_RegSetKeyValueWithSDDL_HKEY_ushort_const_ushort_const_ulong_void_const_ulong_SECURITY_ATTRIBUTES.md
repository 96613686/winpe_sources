# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x180096a34`
- end: `0x180096aec`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `184`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, DWORD, BYTE *lpData, DWORD cbData)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180095d1c`
- `0x18009cbec`
- `0x1800a0f70`
- `0x180105780`

## callees

- `0x180096a34`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180096abd`
- `ADVAPI32!RegSetValueExW` at `0x180096abd`
- `ADVAPI32!RegCloseKey` at `0x180096acf`
- `ADVAPI32!RegCloseKey` at `0x180096acf`
- `ADVAPI32!RegCreateKeyExW` at `0x180096a84`
- `ADVAPI32!RegCreateKeyExW` at `0x180096a84`

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
0x180096a34  mov     r11, rsp
0x180096a37  mov     [r11+8], rbx
0x180096a3b  mov     [r11+18h], rbp
0x180096a3f  push    rsi
0x180096a40  push    rdi
0x180096a41  push    r14
0x180096a43  sub     rsp, 50h
0x180096a47  xor     r14d, r14d
0x180096a4a  mov     esi, r9d
0x180096a4d  mov     [r11+10h], r14
0x180096a51  mov     rbp, r8
0x180096a54  mov     rbx, rcx
0x180096a57  test    rdx, rdx
0x180096a5a  jz      short loc_180096A97
0x180096a5c  cmp     [rdx], r14w
0x180096a60  jz      short loc_180096A97
0x180096a62  mov     [r11-28h], r14
0x180096a66  lea     rax, [r11+10h]
0x180096a6a  mov     [r11-30h], rax
0x180096a6e  xor     r9d, r9d; lpClass
0x180096a71  mov     [r11-38h], r14
0x180096a75  xor     r8d, r8d; Reserved
0x180096a78  mov     [rsp+68h+samDesired], 2; samDesired
0x180096a80  mov     [r11-48h], r14d
0x180096a84  call    cs:__imp_RegCreateKeyExW
0x180096a8a  mov     edi, eax
0x180096a8c  test    eax, eax
0x180096a8e  jnz     short loc_180096AD5
0x180096a90  mov     rcx, [rsp+68h+hKey]; hKey
0x180096a95  jmp     short loc_180096A9C
0x180096a97  mov     [rsp+68h+hKey], rbx
0x180096a9c  mov     eax, [rsp+68h+cbData]
0x180096aa3  mov     r9d, esi; dwType
0x180096aa6  mov     [rsp+68h+samDesired], eax; cbData
0x180096aaa  xor     r8d, r8d; Reserved
0x180096aad  mov     rax, [rsp+68h+arg_20]
0x180096ab5  mov     rdx, rbp; lpValueName
0x180096ab8  mov     [rsp+68h+lpData], rax; lpData
0x180096abd  call    cs:__imp_RegSetValueExW
0x180096ac3  mov     rcx, [rsp+68h+hKey]; hKey
0x180096ac8  mov     edi, eax
0x180096aca  cmp     rcx, rbx
0x180096acd  jz      short loc_180096AD5
0x180096acf  call    cs:__imp_RegCloseKey
0x180096ad5  lea     r11, [rsp+68h+var_18]
0x180096ada  mov     eax, edi
0x180096adc  mov     rbx, [r11+20h]
0x180096ae0  mov     rbp, [r11+30h]
0x180096ae4  mov     rsp, r11
0x180096ae7  pop     r14
0x180096ae9  pop     rdi
0x180096aea  pop     rsi
0x180096aeb  retn
```
