# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x18005897c`
- end: `0x180058a3d`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `193`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const void *, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180058928`

## callees

- `0x18005897c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800589cc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800589cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058a25`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058a25`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180058a0f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180058a0f`

## pseudocode

```c
__int64 __fastcall _RegSetKeyValueWithSDDL(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        BYTE *lpData,
        DWORD cbData)
{
  unsigned int v7; // edi
  HKEY v8; // rcx
  HKEY hKey; // [rsp+60h] [rbp+8h] BYREF

  hKey = 0;
  if ( a2 && *a2 )
  {
    v7 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0, 0, 2u, 0, &hKey, 0);
    if ( v7 )
      return v7;
    v8 = hKey;
  }
  else
  {
    v8 = HKEY_LOCAL_MACHINE;
    hKey = HKEY_LOCAL_MACHINE;
  }
  v7 = RegSetValueExW(v8, a3, 0, 1u, lpData, cbData);
  if ( hKey != HKEY_LOCAL_MACHINE )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x18005897c  mov     r11, rsp
0x18005897f  mov     [r11+10h], rbp
0x180058983  mov     [r11+18h], rsi
0x180058987  mov     [r11+8], rcx
0x18005898b  push    rdi
0x18005898c  sub     rsp, 50h
0x180058990  xor     ebp, ebp
0x180058992  mov     rsi, r8
0x180058995  mov     [r11+8], rbp
0x180058999  test    rdx, rdx
0x18005899c  jz      short loc_1800589DF
0x18005899e  cmp     [rdx], bp
0x1800589a1  jz      short loc_1800589DF
0x1800589a3  mov     [r11-18h], rbp
0x1800589a7  lea     rax, [r11+8]
0x1800589ab  mov     [r11-20h], rax
0x1800589af  xor     r9d, r9d; lpClass
0x1800589b2  mov     [r11-28h], rbp
0x1800589b6  xor     r8d, r8d; Reserved
0x1800589b9  mov     [rsp+58h+samDesired], 2; samDesired
0x1800589c1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800589c8  mov     [rsp+58h+dwOptions], ebp; dwOptions
0x1800589cc  call    cs:__imp_RegCreateKeyExW
0x1800589d2  mov     edi, eax
0x1800589d4  test    eax, eax
0x1800589d6  jnz     short loc_180058A2B
0x1800589d8  mov     rcx, [rsp+58h+hKey]
0x1800589dd  jmp     short loc_1800589EB
0x1800589df  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800589e6  mov     [rsp+58h+hKey], rcx
0x1800589eb  mov     eax, [rsp+58h+cbData]
0x1800589f2  mov     r9d, 1; dwType
0x1800589f8  mov     [rsp+58h+samDesired], eax; cbData
0x1800589fc  xor     r8d, r8d; Reserved
0x1800589ff  mov     rax, [rsp+58h+lpData]
0x180058a07  mov     rdx, rsi; lpValueName
0x180058a0a  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180058a0f  call    cs:__imp_RegSetValueExW
0x180058a15  mov     rcx, [rsp+58h+hKey]; hKey
0x180058a1a  mov     edi, eax
0x180058a1c  cmp     rcx, 0FFFFFFFF80000002h
0x180058a23  jz      short loc_180058A2B
0x180058a25  call    cs:__imp_RegCloseKey
0x180058a2b  mov     rbp, [rsp+58h+arg_8]
0x180058a30  mov     eax, edi
0x180058a32  mov     rsi, [rsp+58h+arg_10]
0x180058a37  add     rsp, 50h
0x180058a3b  pop     rdi
0x180058a3c  retn
```
