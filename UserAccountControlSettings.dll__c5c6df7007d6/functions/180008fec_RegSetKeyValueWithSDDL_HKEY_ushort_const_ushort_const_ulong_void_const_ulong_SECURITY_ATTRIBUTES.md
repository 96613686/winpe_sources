# _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)

- ea: `0x180008fec`
- end: `0x180009099`
- name: `?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `173`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, __int64, BYTE *lpData)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008e18`
- `0x180008e50`

## callees

- `0x180008fec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009070`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180009070`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009043`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180009043`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009086`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009086`

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
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
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
    if ( hKey != HKEY_LOCAL_MACHINE )
      RegCloseKey(hKey);
  }
  return v6;
}

```

## disassembly

```asm
0x180008fec  mov     r11, rsp
0x180008fef  mov     [r11+8], rbx
0x180008ff3  mov     [r11+10h], rdx
0x180008ff7  push    rdi
0x180008ff8  sub     rsp, 50h
0x180008ffc  mov     qword ptr [r11-18h], 0
0x180009004  lea     rax, [r11+10h]
0x180009008  mov     [r11-20h], rax
0x18000900c  lea     rdx, psz; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180009013  mov     qword ptr [r11-28h], 0
0x18000901b  mov     rdi, r8
0x18000901e  mov     [rsp+58h+samDesired], 2; samDesired
0x180009026  xor     r9d, r9d; lpClass
0x180009029  xor     r8d, r8d; Reserved
0x18000902c  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180009034  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000903b  mov     qword ptr [r11+10h], 0
0x180009043  call    cs:__imp_RegCreateKeyExW
0x180009049  mov     ebx, eax
0x18000904b  test    eax, eax
0x18000904d  jnz     short loc_18000908C
0x18000904f  mov     rcx, [rsp+58h+hKey]; hKey
0x180009054  lea     r9d, [rax+4]; dwType
0x180009058  mov     rax, [rsp+58h+lpData]
0x180009060  xor     r8d, r8d; Reserved
0x180009063  mov     [rsp+58h+samDesired], r9d; cbData
0x180009068  mov     rdx, rdi; lpValueName
0x18000906b  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180009070  call    cs:__imp_RegSetValueExW
0x180009076  mov     rcx, [rsp+58h+hKey]; hKey
0x18000907b  mov     ebx, eax
0x18000907d  cmp     rcx, 0FFFFFFFF80000002h
0x180009084  jz      short loc_18000908C
0x180009086  call    cs:__imp_RegCloseKey
0x18000908c  mov     eax, ebx
0x18000908e  mov     rbx, [rsp+58h+arg_0]
0x180009093  add     rsp, 50h
0x180009097  pop     rdi
0x180009098  retn
```
