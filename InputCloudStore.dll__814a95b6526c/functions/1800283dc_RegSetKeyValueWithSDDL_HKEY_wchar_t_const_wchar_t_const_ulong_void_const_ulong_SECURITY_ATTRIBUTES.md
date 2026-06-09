# _RegSetKeyValueWithSDDL(HKEY__ *,wchar_t const *,wchar_t const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x1800283dc`
- end: `0x18002849e`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEB_W1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(HKEY, const wchar_t *, const wchar_t *, DWORD, BYTE *lpData, DWORD cbData)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026db4`
- `0x180028270`

## callees

- `0x1800283dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028473`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028473`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002842d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002842d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002848c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002848c`

## pseudocode

```c
__int64 __fastcall _RegSetKeyValueWithSDDL(
        HKEY a1,
        const wchar_t *a2,
        const wchar_t *a3,
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
0x1800283dc  mov     r11, rsp
0x1800283df  mov     [r11+8], rcx
0x1800283e3  push    rbp
0x1800283e4  push    rsi
0x1800283e5  push    rdi
0x1800283e6  push    r14
0x1800283e8  sub     rsp, 58h
0x1800283ec  xor     r14d, r14d
0x1800283ef  mov     esi, r9d
0x1800283f2  mov     [r11+8], r14
0x1800283f6  mov     rbp, r8
0x1800283f9  test    rdx, rdx
0x1800283fc  jz      short loc_180028443
0x1800283fe  cmp     [rdx], r14w
0x180028402  jz      short loc_180028443
0x180028404  mov     [r11-38h], r14
0x180028408  lea     rax, [r11+8]
0x18002840c  mov     [r11-40h], rax
0x180028410  xor     r9d, r9d; lpClass
0x180028413  mov     [r11-48h], r14
0x180028417  xor     r8d, r8d; Reserved
0x18002841a  mov     [rsp+78h+samDesired], 2; samDesired
0x180028422  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180028429  mov     [r11-58h], r14d
0x18002842d  call    cs:__imp_RegCreateKeyExW
0x180028433  mov     edi, eax
0x180028435  test    eax, eax
0x180028437  jnz     short loc_180028492
0x180028439  mov     rcx, [rsp+78h+hKey]
0x180028441  jmp     short loc_180028452
0x180028443  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002844a  mov     [rsp+78h+hKey], rcx
0x180028452  mov     eax, [rsp+78h+cbData]
0x180028459  mov     r9d, esi; dwType
0x18002845c  mov     [rsp+78h+samDesired], eax; cbData
0x180028460  xor     r8d, r8d; Reserved
0x180028463  mov     rax, [rsp+78h+arg_20]
0x18002846b  mov     rdx, rbp; lpValueName
0x18002846e  mov     [rsp+78h+lpData], rax; lpData
0x180028473  call    cs:__imp_RegSetValueExW
0x180028479  mov     rcx, [rsp+78h+hKey]; hKey
0x180028481  mov     edi, eax
0x180028483  cmp     rcx, 0FFFFFFFF80000001h
0x18002848a  jz      short loc_180028492
0x18002848c  call    cs:__imp_RegCloseKey
0x180028492  mov     eax, edi
0x180028494  add     rsp, 58h
0x180028498  pop     r14
0x18002849a  pop     rdi
0x18002849b  pop     rsi
0x18002849c  pop     rbp
0x18002849d  retn
```
