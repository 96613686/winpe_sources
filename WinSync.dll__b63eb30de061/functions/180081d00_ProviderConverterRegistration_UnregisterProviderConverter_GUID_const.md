# ProviderConverterRegistration::UnregisterProviderConverter(_GUID const &)

- ea: `0x180081d00`
- end: `0x180081e39`
- name: `?UnregisterProviderConverter@ProviderConverterRegistration@@UEAAJAEBU_GUID@@@Z`
- size: `313`
- prototype: `int(ProviderConverterRegistration *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001a038`
- `0x180081d00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081de2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081de2`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x180081d62`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x180081d62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081df2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081df2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180081d8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180081d8f`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180081db7`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180081db7`

## pseudocode

```c
__int64 __fastcall ProviderConverterRegistration::UnregisterProviderConverter(
        ProviderConverterRegistration *this,
        const struct _GUID *a2)
{
  int v3; // ebx
  LSTATUS v4; // eax
  LSTATUS v5; // eax
  LPOLESTR lpsz; // [rsp+50h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      WPP_5820a2c240bc3bbeeb9e2f00b019b4aa_Traceguids,
      "ProviderConverterRegistration::UnregisterProviderConverter");
  }
  hKey = 0;
  lpsz = 0;
  v3 = StringFromIID(a2, &lpsz);
  if ( v3 >= 0 )
  {
    v4 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Sync Framework\\ProviderConverterRegistration",
           0,
           0x20006u,
           &hKey);
    v3 = v4;
    if ( v4 == 2 )
    {
LABEL_11:
      v3 = -2147024809;
      goto LABEL_14;
    }
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    if ( v3 >= 0 )
    {
      v5 = RegDeleteKeyW(hKey, lpsz);
      v3 = v5;
      if ( v5 == 2 )
        goto LABEL_11;
      if ( v5 > 0 )
        v3 = (unsigned __int16)v5 | 0x80070000;
    }
  }
LABEL_14:
  if ( lpsz )
    CoTaskMemFree(lpsz);
  if ( hKey )
    RegCloseKey(hKey);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      WPP_5820a2c240bc3bbeeb9e2f00b019b4aa_Traceguids,
      "ProviderConverterRegistration::UnregisterProviderConverter");
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180081d00  mov     [rsp+arg_0], rbx
0x180081d05  push    rsi
0x180081d06  sub     rsp, 30h
0x180081d0a  mov     rbx, rdx
0x180081d0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180081d14  lea     rsi, WPP_GLOBAL_Control
0x180081d1b  cmp     rcx, rsi
0x180081d1e  jz      short loc_180081D48
0x180081d20  test    byte ptr [rcx+1Ch], 4
0x180081d24  jz      short loc_180081D48
0x180081d26  cmp     byte ptr [rcx+19h], 5
0x180081d2a  jb      short loc_180081D48
0x180081d2c  mov     rcx, [rcx+10h]
0x180081d30  lea     r9, aProviderconver_2; "ProviderConverterRegistration::Unregist"...
0x180081d37  mov     edx, 0Eh
0x180081d3c  lea     r8, WPP_5820a2c240bc3bbeeb9e2f00b019b4aa_Traceguids
0x180081d43  call    WPP_SF_s
0x180081d48  lea     rdx, [rsp+38h+lpsz]; lplpsz
0x180081d4d  mov     [rsp+38h+hKey], 0
0x180081d56  mov     rcx, rbx; rclsid
0x180081d59  mov     [rsp+38h+lpsz], 0
0x180081d62  call    cs:__imp_StringFromIID
0x180081d68  mov     ebx, eax
0x180081d6a  test    eax, eax
0x180081d6c  js      short loc_180081DD8
0x180081d6e  lea     rax, [rsp+38h+hKey]
0x180081d73  mov     r9d, 20006h; samDesired
0x180081d79  xor     r8d, r8d; ulOptions
0x180081d7c  mov     [rsp+38h+phkResult], rax; phkResult
0x180081d81  lea     rdx, ?g_pszProviderConverterRegistrationSubKey@ProviderConverterRegistration@@0QBGB; "Software\\Microsoft\\Sync Framework\\Pr"...
0x180081d88  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180081d8f  call    cs:__imp_RegOpenKeyExW
0x180081d95  mov     ebx, eax
0x180081d97  cmp     eax, 2
0x180081d9a  jz      short loc_180081DC4
0x180081d9c  test    eax, eax
0x180081d9e  jle     short loc_180081DA9
0x180081da0  movzx   ebx, ax
0x180081da3  or      ebx, 80070000h
0x180081da9  test    ebx, ebx
0x180081dab  js      short loc_180081DD8
0x180081dad  mov     rdx, [rsp+38h+lpsz]; lpSubKey
0x180081db2  mov     rcx, [rsp+38h+hKey]; hKey
0x180081db7  call    cs:__imp_RegDeleteKeyW
0x180081dbd  mov     ebx, eax
0x180081dbf  cmp     eax, 2
0x180081dc2  jnz     short loc_180081DCB
0x180081dc4  mov     ebx, 80070057h
0x180081dc9  jmp     short loc_180081DD8
0x180081dcb  test    eax, eax
0x180081dcd  jle     short loc_180081DD8
0x180081dcf  movzx   ebx, ax
0x180081dd2  or      ebx, 80070000h
0x180081dd8  mov     rcx, [rsp+38h+lpsz]; pv
0x180081ddd  test    rcx, rcx
0x180081de0  jz      short loc_180081DE8
0x180081de2  call    cs:__imp_CoTaskMemFree
0x180081de8  mov     rcx, [rsp+38h+hKey]; hKey
0x180081ded  test    rcx, rcx
0x180081df0  jz      short loc_180081DF8
0x180081df2  call    cs:__imp_RegCloseKey
0x180081df8  mov     rcx, cs:WPP_GLOBAL_Control
0x180081dff  cmp     rcx, rsi
0x180081e02  jz      short loc_180081E2C
0x180081e04  test    byte ptr [rcx+1Ch], 4
0x180081e08  jz      short loc_180081E2C
0x180081e0a  cmp     byte ptr [rcx+19h], 5
0x180081e0e  jb      short loc_180081E2C
0x180081e10  mov     rcx, [rcx+10h]
0x180081e14  lea     r9, aProviderconver_2; "ProviderConverterRegistration::Unregist"...
0x180081e1b  mov     edx, 0Fh
0x180081e20  lea     r8, WPP_5820a2c240bc3bbeeb9e2f00b019b4aa_Traceguids
0x180081e27  call    WPP_SF_s
0x180081e2c  mov     eax, ebx
0x180081e2e  mov     rbx, [rsp+38h+arg_0]
0x180081e33  add     rsp, 30h
0x180081e37  pop     rsi
0x180081e38  retn
```
