# ProviderConverterRegistration::RegisterProviderConverter(_GUID const &,_GUID const &)

- ea: `0x18002a290`
- end: `0x18002a528`
- name: `?RegisterProviderConverter@ProviderConverterRegistration@@UEAAJAEBU_GUID@@0@Z`
- size: `664`
- prototype: `__int64 __fastcall(ProviderConverterRegistration *this, const struct _GUID *, const struct _GUID *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18001a038`
- `0x18002a290`
- `0x180093270`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a498`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a4a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a498`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a4a8`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002a333`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18002a333`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18002a31b`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18002a31b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002a377`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002a3ca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002a377`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002a3ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a4b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a4c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a4b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a4c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a461`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a461`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a421`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a421`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18002a47f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18002a47f`

## string_xrefs

- `0x18002a410`: `ConverterClassId`
- `0x18002a443`: `ConverterClassId`

## pseudocode

```c
__int64 __fastcall ProviderConverterRegistration::RegisterProviderConverter(
        ProviderConverterRegistration *this,
        const struct _GUID *a2,
        const struct _GUID *a3)
{
  int v5; // ebx
  LSTATUS v6; // eax
  LSTATUS v7; // eax
  __int64 v8; // rax
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  LPOLESTR v13; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  LPOLESTR lpsz; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Data[64]; // [rsp+80h] [rbp-80h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_5820a2c240bc3bbeeb9e2f00b019b4aa_Traceguids,
      "ProviderConverterRegistration::RegisterProviderConverter");
  }
  dwDisposition = 0;
  hKey = 0;
  phkResult = 0;
  lpsz = 0;
  v13 = 0;
  v5 = StringFromIID(a2, &lpsz);
  if ( v5 >= 0 )
  {
    v5 = StringFromCLSID(a3, &v13);
    if ( v5 >= 0 )
    {
      v6 = RegCreateKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Sync Framework\\ProviderConverterRegistration",
             0,
             0,
             0,
             0x2001Fu,
             0,
             &hKey,
             0);
      v5 = v6;
      if ( v6 > 0 )
        v5 = (unsigned __int16)v6 | 0x80070000;
      if ( v5 >= 0 )
      {
        v7 = RegCreateKeyExW(hKey, lpsz, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
        v5 = v7;
        if ( v7 > 0 )
          v5 = (unsigned __int16)v7 | 0x80070000;
        if ( v5 >= 0 )
        {
          if ( dwDisposition == 1 )
          {
            v8 = -1;
            do
              ++v8;
            while ( v13[v8] );
            v9 = RegSetValueExW(phkResult, L"ConverterClassId", 0, 1u, (const BYTE *)v13, 2 * v8 + 2);
            v5 = v9;
            if ( v9 > 0 )
              v5 = (unsigned __int16)v9 | 0x80070000;
          }
          else
          {
            cbData = 128;
            v10 = RegQueryValueExW(phkResult, L"ConverterClassId", 0, 0, (LPBYTE)Data, &cbData);
            v5 = v10;
            if ( v10 > 0 )
              v5 = (unsigned __int16)v10 | 0x80070000;
            if ( v5 >= 0 && lstrcmpW(v13, Data) )
              v5 = -2147024809;
          }
        }
      }
    }
  }
  if ( v13 )
    CoTaskMemFree(v13);
  if ( lpsz )
    CoTaskMemFree(lpsz);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      WPP_5820a2c240bc3bbeeb9e2f00b019b4aa_Traceguids,
      "ProviderConverterRegistration::RegisterProviderConverter");
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002a290  mov     [rsp-8+arg_0], rbx
0x18002a295  mov     [rsp-8+arg_18], rsi
0x18002a29a  push    rbp
0x18002a29b  push    rdi
0x18002a29c  push    r15
0x18002a29e  lea     rbp, [rsp-10h]
0x18002a2a3  sub     rsp, 110h
0x18002a2aa  mov     rax, cs:__security_cookie
0x18002a2b1  xor     rax, rsp
0x18002a2b4  mov     [rbp+20h+var_20], rax
0x18002a2b8  mov     rdi, r8
0x18002a2bb  mov     rbx, rdx
0x18002a2be  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a2c5  lea     r15, WPP_GLOBAL_Control
0x18002a2cc  cmp     rcx, r15
0x18002a2cf  jz      short loc_18002A2F9
0x18002a2d1  test    byte ptr [rcx+1Ch], 4
0x18002a2d5  jz      short loc_18002A2F9
0x18002a2d7  cmp     byte ptr [rcx+19h], 5
0x18002a2db  jb      short loc_18002A2F9
0x18002a2dd  mov     rcx, [rcx+10h]
0x18002a2e1  lea     r9, aProviderconver; "ProviderConverterRegistration::Register"...
0x18002a2e8  mov     edx, 0Ch
0x18002a2ed  lea     r8, WPP_5820a2c240bc3bbeeb9e2f00b019b4aa_Traceguids
0x18002a2f4  call    WPP_SF_s
0x18002a2f9  xor     esi, esi
0x18002a2fb  lea     rdx, [rsp+120h+lpsz]; lplpsz
0x18002a300  mov     rcx, rbx; rclsid
0x18002a303  mov     [rsp+120h+dwDisposition], esi
0x18002a307  mov     [rsp+120h+hKey], rsi
0x18002a30c  mov     [rsp+120h+var_C0], rsi
0x18002a311  mov     [rsp+120h+lpsz], rsi
0x18002a316  mov     [rsp+120h+var_C8], rsi
0x18002a31b  call    cs:__imp_StringFromIID
0x18002a321  mov     ebx, eax
0x18002a323  test    eax, eax
0x18002a325  js      loc_18002A48E
0x18002a32b  lea     rdx, [rsp+120h+var_C8]; lplpsz
0x18002a330  mov     rcx, rdi; rclsid
0x18002a333  call    cs:__imp_StringFromCLSID
0x18002a339  mov     ebx, eax
0x18002a33b  test    eax, eax
0x18002a33d  js      loc_18002A48E
0x18002a343  mov     [rsp+120h+lpdwDisposition], rsi; lpdwDisposition
0x18002a348  lea     rax, [rsp+120h+hKey]
0x18002a34d  mov     [rsp+120h+phkResult], rax; phkResult
0x18002a352  lea     rdx, ?g_pszProviderConverterRegistrationSubKey@ProviderConverterRegistration@@0QBGB; "Software\\Microsoft\\Sync Framework\\Pr"...
0x18002a359  mov     [rsp+120h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18002a35e  xor     r9d, r9d; lpClass
0x18002a361  mov     [rsp+120h+samDesired], 2001Fh; samDesired
0x18002a369  xor     r8d, r8d; Reserved
0x18002a36c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a373  mov     [rsp+120h+dwOptions], esi; dwOptions
0x18002a377  call    cs:__imp_RegCreateKeyExW
0x18002a37d  mov     ebx, eax
0x18002a37f  mov     edi, 80070000h
0x18002a384  test    eax, eax
0x18002a386  jle     short loc_18002A38D
0x18002a388  movzx   ebx, ax
0x18002a38b  or      ebx, edi
0x18002a38d  test    ebx, ebx
0x18002a38f  js      loc_18002A48E
0x18002a395  mov     rdx, [rsp+120h+lpsz]; lpSubKey
0x18002a39a  lea     rax, [rsp+120h+dwDisposition]
0x18002a39f  mov     rcx, [rsp+120h+hKey]; hKey
0x18002a3a4  xor     r9d, r9d; lpClass
0x18002a3a7  mov     [rsp+120h+lpdwDisposition], rax; lpdwDisposition
0x18002a3ac  xor     r8d, r8d; Reserved
0x18002a3af  lea     rax, [rsp+120h+var_C0]
0x18002a3b4  mov     [rsp+120h+phkResult], rax; phkResult
0x18002a3b9  mov     [rsp+120h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18002a3be  mov     [rsp+120h+samDesired], 2001Fh; samDesired
0x18002a3c6  mov     [rsp+120h+dwOptions], esi; dwOptions
0x18002a3ca  call    cs:__imp_RegCreateKeyExW
0x18002a3d0  mov     ebx, eax
0x18002a3d2  test    eax, eax
0x18002a3d4  jle     short loc_18002A3DB
0x18002a3d6  movzx   ebx, ax
0x18002a3d9  or      ebx, edi
0x18002a3db  test    ebx, ebx
0x18002a3dd  js      loc_18002A48E
0x18002a3e3  mov     r9d, 1; dwType
0x18002a3e9  cmp     [rsp+120h+dwDisposition], r9d
0x18002a3ee  jnz     short loc_18002A434
0x18002a3f0  mov     rcx, [rsp+120h+var_C8]
0x18002a3f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a3f9  inc     rax
0x18002a3fc  cmp     [rcx+rax*2], si
0x18002a400  jnz     short loc_18002A3F9
0x18002a402  lea     eax, ds:2[rax*2]
0x18002a409  xor     r8d, r8d; Reserved
0x18002a40c  mov     [rsp+120h+samDesired], eax; cbData
0x18002a410  lea     rdx, ?g_pszConverterClassId@ProviderConverterRegistration@@0QBGB; "ConverterClassId"
0x18002a417  mov     qword ptr [rsp+120h+dwOptions], rcx; lpData
0x18002a41c  mov     rcx, [rsp+120h+var_C0]; hKey
0x18002a421  call    cs:__imp_RegSetValueExW
0x18002a427  mov     ebx, eax
0x18002a429  test    eax, eax
0x18002a42b  jle     short loc_18002A48E
0x18002a42d  movzx   ebx, ax
0x18002a430  or      ebx, edi
0x18002a432  jmp     short loc_18002A48E
0x18002a434  mov     rcx, [rsp+120h+var_C0]; hKey
0x18002a439  lea     rax, [rsp+120h+cbData]
0x18002a43e  mov     qword ptr [rsp+120h+samDesired], rax; lpcbData
0x18002a443  lea     rdx, ?g_pszConverterClassId@ProviderConverterRegistration@@0QBGB; "ConverterClassId"
0x18002a44a  lea     rax, [rbp+20h+Data]
0x18002a44e  mov     [rsp+120h+cbData], 80h
0x18002a456  xor     r9d, r9d; lpType
0x18002a459  mov     qword ptr [rsp+120h+dwOptions], rax; lpData
0x18002a45e  xor     r8d, r8d; lpReserved
0x18002a461  call    cs:__imp_RegQueryValueExW
0x18002a467  mov     ebx, eax
0x18002a469  test    eax, eax
0x18002a46b  jle     short loc_18002A472
0x18002a46d  movzx   ebx, ax
0x18002a470  or      ebx, edi
0x18002a472  test    ebx, ebx
0x18002a474  js      short loc_18002A48E
0x18002a476  mov     rcx, [rsp+120h+var_C8]; lpString1
0x18002a47b  lea     rdx, [rbp+20h+Data]; lpString2
0x18002a47f  call    cs:__imp_lstrcmpW
0x18002a485  test    eax, eax
0x18002a487  jz      short loc_18002A48E
0x18002a489  mov     ebx, 80070057h
0x18002a48e  mov     rcx, [rsp+120h+var_C8]; pv
0x18002a493  test    rcx, rcx
0x18002a496  jz      short loc_18002A49E
0x18002a498  call    cs:__imp_CoTaskMemFree
0x18002a49e  mov     rcx, [rsp+120h+lpsz]; pv
0x18002a4a3  test    rcx, rcx
0x18002a4a6  jz      short loc_18002A4AE
0x18002a4a8  call    cs:__imp_CoTaskMemFree
0x18002a4ae  mov     rcx, [rsp+120h+var_C0]; hKey
0x18002a4b3  test    rcx, rcx
0x18002a4b6  jz      short loc_18002A4BE
0x18002a4b8  call    cs:__imp_RegCloseKey
0x18002a4be  mov     rcx, [rsp+120h+hKey]; hKey
0x18002a4c3  test    rcx, rcx
0x18002a4c6  jz      short loc_18002A4CE
0x18002a4c8  call    cs:__imp_RegCloseKey
0x18002a4ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a4d5  cmp     rcx, r15
0x18002a4d8  jz      short loc_18002A502
0x18002a4da  test    byte ptr [rcx+1Ch], 4
0x18002a4de  jz      short loc_18002A502
0x18002a4e0  cmp     byte ptr [rcx+19h], 5
0x18002a4e4  jb      short loc_18002A502
0x18002a4e6  mov     rcx, [rcx+10h]
0x18002a4ea  lea     r9, aProviderconver; "ProviderConverterRegistration::Register"...
0x18002a4f1  mov     edx, 0Dh
0x18002a4f6  lea     r8, WPP_5820a2c240bc3bbeeb9e2f00b019b4aa_Traceguids
0x18002a4fd  call    WPP_SF_s
0x18002a502  mov     eax, ebx
0x18002a504  mov     rcx, [rbp+20h+var_20]
0x18002a508  xor     rcx, rsp; StackCookie
0x18002a50b  call    __security_check_cookie
0x18002a510  lea     r11, [rsp+120h+var_10]
0x18002a518  mov     rbx, [r11+20h]
0x18002a51c  mov     rsi, [r11+38h]
0x18002a520  mov     rsp, r11
0x18002a523  pop     r15
0x18002a525  pop     rdi
0x18002a526  pop     rbp
0x18002a527  retn
```
