# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x18003b2b0`
- end: `0x18003b36f`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `191`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const void *, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003b274`
- `0x1800fe694`
- `0x18011a088`
- `0x180192010`

## callees

- `0x18003b2b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003b30c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003b30c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b33e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003b33e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b367`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b367`

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
0x18003b2b0  mov     [rsp+arg_0], rbx
0x18003b2b5  mov     [rsp+arg_10], rbp
0x18003b2ba  push    rsi
0x18003b2bb  push    rdi
0x18003b2bc  push    r14
0x18003b2be  sub     rsp, 50h
0x18003b2c2  xor     r14d, r14d
0x18003b2c5  mov     esi, r9d
0x18003b2c8  mov     [rsp+68h+hKey], r14
0x18003b2cd  mov     rbp, r8
0x18003b2d0  mov     rbx, rcx
0x18003b2d3  test    rdx, rdx
0x18003b2d6  jnz     short loc_18003B2DF
0x18003b2d8  mov     [rsp+68h+hKey], rbx
0x18003b2dd  jmp     short loc_18003B31D
0x18003b2df  cmp     [rdx], r14w
0x18003b2e3  jz      short loc_18003B2D8
0x18003b2e5  mov     [rsp+68h+lpdwDisposition], r14; lpdwDisposition
0x18003b2ea  lea     rax, [rsp+68h+hKey]
0x18003b2ef  mov     [rsp+68h+phkResult], rax; phkResult
0x18003b2f4  xor     r9d, r9d; lpClass
0x18003b2f7  mov     [rsp+68h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18003b2fc  xor     r8d, r8d; Reserved
0x18003b2ff  mov     [rsp+68h+samDesired], 2; samDesired
0x18003b307  mov     [rsp+68h+dwOptions], r14d; dwOptions
0x18003b30c  call    cs:__imp_RegCreateKeyExW
0x18003b312  mov     edi, eax
0x18003b314  test    eax, eax
0x18003b316  jnz     short loc_18003B350
0x18003b318  mov     rcx, [rsp+68h+hKey]; hKey
0x18003b31d  mov     eax, [rsp+68h+cbData]
0x18003b324  mov     r9d, esi; dwType
0x18003b327  mov     [rsp+68h+samDesired], eax; cbData
0x18003b32b  xor     r8d, r8d; Reserved
0x18003b32e  mov     rax, [rsp+68h+lpData]
0x18003b336  mov     rdx, rbp; lpValueName
0x18003b339  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18003b33e  call    cs:__imp_RegSetValueExW
0x18003b344  mov     rcx, [rsp+68h+hKey]; hKey
0x18003b349  mov     edi, eax
0x18003b34b  cmp     rcx, rbx
0x18003b34e  jnz     short loc_18003B367
0x18003b350  lea     r11, [rsp+68h+var_18]
0x18003b355  mov     eax, edi
0x18003b357  mov     rbx, [r11+20h]
0x18003b35b  mov     rbp, [r11+30h]
0x18003b35f  mov     rsp, r11
0x18003b362  pop     r14
0x18003b364  pop     rdi
0x18003b365  pop     rsi
0x18003b366  retn
0x18003b367  call    cs:__imp_RegCloseKey
0x18003b36d  jmp     short loc_18003B350
```
