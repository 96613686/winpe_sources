# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x18001fff0`
- end: `0x1800200a8`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `184`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const void *, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f8d4`
- `0x180022248`

## callees

- `0x18001fff0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020079`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020079`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020040`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180020040`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002008b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002008b`

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
0x18001fff0  mov     r11, rsp
0x18001fff3  mov     [r11+8], rbx
0x18001fff7  mov     [r11+18h], rbp
0x18001fffb  push    rsi
0x18001fffc  push    rdi
0x18001fffd  push    r14
0x18001ffff  sub     rsp, 50h
0x180020003  xor     r14d, r14d
0x180020006  mov     esi, r9d
0x180020009  mov     [r11+10h], r14
0x18002000d  mov     rbp, r8
0x180020010  mov     rbx, rcx
0x180020013  test    rdx, rdx
0x180020016  jz      short loc_180020053
0x180020018  cmp     [rdx], r14w
0x18002001c  jz      short loc_180020053
0x18002001e  mov     [r11-28h], r14
0x180020022  lea     rax, [r11+10h]
0x180020026  mov     [r11-30h], rax
0x18002002a  xor     r9d, r9d; lpClass
0x18002002d  mov     [r11-38h], r14
0x180020031  xor     r8d, r8d; Reserved
0x180020034  mov     [rsp+68h+samDesired], 2; samDesired
0x18002003c  mov     [r11-48h], r14d
0x180020040  call    cs:__imp_RegCreateKeyExW
0x180020046  mov     edi, eax
0x180020048  test    eax, eax
0x18002004a  jnz     short loc_180020091
0x18002004c  mov     rcx, [rsp+68h+hKey]; hKey
0x180020051  jmp     short loc_180020058
0x180020053  mov     [rsp+68h+hKey], rbx
0x180020058  mov     eax, [rsp+68h+cbData]
0x18002005f  mov     r9d, esi; dwType
0x180020062  mov     [rsp+68h+samDesired], eax; cbData
0x180020066  xor     r8d, r8d; Reserved
0x180020069  mov     rax, [rsp+68h+arg_20]
0x180020071  mov     rdx, rbp; lpValueName
0x180020074  mov     [rsp+68h+lpData], rax; lpData
0x180020079  call    cs:__imp_RegSetValueExW
0x18002007f  mov     rcx, [rsp+68h+hKey]; hKey
0x180020084  mov     edi, eax
0x180020086  cmp     rcx, rbx
0x180020089  jz      short loc_180020091
0x18002008b  call    cs:__imp_RegCloseKey
0x180020091  lea     r11, [rsp+68h+var_18]
0x180020096  mov     eax, edi
0x180020098  mov     rbx, [r11+20h]
0x18002009c  mov     rbp, [r11+30h]
0x1800200a0  mov     rsp, r11
0x1800200a3  pop     r14
0x1800200a5  pop     rdi
0x1800200a6  pop     rsi
0x1800200a7  retn
```
