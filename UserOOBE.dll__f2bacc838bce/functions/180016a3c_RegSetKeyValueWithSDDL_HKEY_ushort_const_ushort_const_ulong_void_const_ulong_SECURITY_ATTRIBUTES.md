# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x180016a3c`
- end: `0x180016af4`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `184`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const void *, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015434`
- `0x180015478`
- `0x18001b61c`
- `0x18002d5fc`

## callees

- `0x180016a3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016a8c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016a8c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016ac5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016ac5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016ad7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016ad7`

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
0x180016a3c  mov     r11, rsp
0x180016a3f  mov     [r11+8], rbx
0x180016a43  mov     [r11+18h], rbp
0x180016a47  push    rsi
0x180016a48  push    rdi
0x180016a49  push    r14
0x180016a4b  sub     rsp, 50h
0x180016a4f  xor     r14d, r14d
0x180016a52  mov     esi, r9d
0x180016a55  mov     [r11+10h], r14
0x180016a59  mov     rbp, r8
0x180016a5c  mov     rbx, rcx
0x180016a5f  test    rdx, rdx
0x180016a62  jz      short loc_180016A9F
0x180016a64  cmp     [rdx], r14w
0x180016a68  jz      short loc_180016A9F
0x180016a6a  mov     [r11-28h], r14
0x180016a6e  lea     rax, [r11+10h]
0x180016a72  mov     [r11-30h], rax
0x180016a76  xor     r9d, r9d; lpClass
0x180016a79  mov     [r11-38h], r14
0x180016a7d  xor     r8d, r8d; Reserved
0x180016a80  mov     [rsp+68h+samDesired], 2; samDesired
0x180016a88  mov     [r11-48h], r14d
0x180016a8c  call    cs:__imp_RegCreateKeyExW
0x180016a92  mov     edi, eax
0x180016a94  test    eax, eax
0x180016a96  jnz     short loc_180016ADD
0x180016a98  mov     rcx, [rsp+68h+hKey]; hKey
0x180016a9d  jmp     short loc_180016AA4
0x180016a9f  mov     [rsp+68h+hKey], rbx
0x180016aa4  mov     eax, [rsp+68h+cbData]
0x180016aab  mov     r9d, esi; dwType
0x180016aae  mov     [rsp+68h+samDesired], eax; cbData
0x180016ab2  xor     r8d, r8d; Reserved
0x180016ab5  mov     rax, [rsp+68h+arg_20]
0x180016abd  mov     rdx, rbp; lpValueName
0x180016ac0  mov     [rsp+68h+lpData], rax; lpData
0x180016ac5  call    cs:__imp_RegSetValueExW
0x180016acb  mov     rcx, [rsp+68h+hKey]; hKey
0x180016ad0  mov     edi, eax
0x180016ad2  cmp     rcx, rbx
0x180016ad5  jz      short loc_180016ADD
0x180016ad7  call    cs:__imp_RegCloseKey
0x180016add  lea     r11, [rsp+68h+var_18]
0x180016ae2  mov     eax, edi
0x180016ae4  mov     rbx, [r11+20h]
0x180016ae8  mov     rbp, [r11+30h]
0x180016aec  mov     rsp, r11
0x180016aef  pop     r14
0x180016af1  pop     rdi
0x180016af2  pop     rsi
0x180016af3  retn
```
