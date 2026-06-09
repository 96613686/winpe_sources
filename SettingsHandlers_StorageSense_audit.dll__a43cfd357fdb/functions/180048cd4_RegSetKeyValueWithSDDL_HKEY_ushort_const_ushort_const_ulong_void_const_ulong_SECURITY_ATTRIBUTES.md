# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x180048cd4`
- end: `0x180048d81`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `173`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const void *, unsigned int, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180044d60`

## callees

- `0x180048cd4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048d6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180048d6e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180048d58`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180048d58`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180048d2b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180048d2b`

## pseudocode

```c
__int64 __fastcall _RegSetKeyValueWithSDDL(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        BYTE *lpData)
{
  unsigned int v6; // ebx
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  v6 = RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Apps",
         0,
         0,
         0,
         2u,
         0,
         &hKey,
         0);
  if ( !v6 )
  {
    v6 = RegSetValueExW(hKey, a3, 0, 4u, lpData, 4u);
    if ( hKey != HKEY_CURRENT_USER )
      RegCloseKey(hKey);
  }
  return v6;
}

```

## disassembly

```asm
0x180048cd4  mov     r11, rsp
0x180048cd7  mov     [r11+8], rbx
0x180048cdb  mov     [r11+10h], rdx
0x180048cdf  push    rdi
0x180048ce0  sub     rsp, 50h
0x180048ce4  mov     qword ptr [r11-18h], 0
0x180048cec  lea     rax, [r11+10h]
0x180048cf0  mov     [r11-20h], rax
0x180048cf4  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180048cfb  mov     qword ptr [r11-28h], 0
0x180048d03  mov     rdi, r8
0x180048d06  mov     [rsp+58h+samDesired], 2; samDesired
0x180048d0e  xor     r9d, r9d; lpClass
0x180048d11  xor     r8d, r8d; Reserved
0x180048d14  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180048d1c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180048d23  mov     qword ptr [r11+10h], 0
0x180048d2b  call    cs:__imp_RegCreateKeyExW
0x180048d31  mov     ebx, eax
0x180048d33  test    eax, eax
0x180048d35  jnz     short loc_180048D74
0x180048d37  mov     rcx, [rsp+58h+hKey]; hKey
0x180048d3c  lea     r9d, [rax+4]; dwType
0x180048d40  mov     rax, [rsp+58h+lpData]
0x180048d48  xor     r8d, r8d; Reserved
0x180048d4b  mov     [rsp+58h+samDesired], r9d; cbData
0x180048d50  mov     rdx, rdi; lpValueName
0x180048d53  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180048d58  call    cs:__imp_RegSetValueExW
0x180048d5e  mov     rcx, [rsp+58h+hKey]; hKey
0x180048d63  mov     ebx, eax
0x180048d65  cmp     rcx, 0FFFFFFFF80000001h
0x180048d6c  jz      short loc_180048D74
0x180048d6e  call    cs:__imp_RegCloseKey
0x180048d74  mov     eax, ebx
0x180048d76  mov     rbx, [rsp+58h+arg_0]
0x180048d7b  add     rsp, 50h
0x180048d7f  pop     rdi
0x180048d80  retn
```
