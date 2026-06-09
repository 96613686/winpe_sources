# ProviderConverterRegistration::ReadProviderConverterEntries(void)

- ea: `0x180081978`
- end: `0x180081cb7`
- name: `?ReadProviderConverterEntries@ProviderConverterRegistration@@AEAAJXZ`
- size: `831`
- prototype: `__int64 __fastcall(ProviderConverterRegistration *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180081704`

## callees

- `0x18000a0f0`
- `0x18000f810`
- `0x18001a038`
- `0x180081978`
- `0x180093270`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180081b54`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180081be1`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180081b54`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180081be1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081bf3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081c40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081c50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081bf3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081c40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081c50`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180081bc3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180081bc3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180081b2a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180081b2a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180081a2d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180081b80`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180081a2d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180081b80`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180081a92`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180081a92`

## string_xrefs

- `0x180081ba5`: `ConverterClassId`
- `0x1800819cb`: `ProviderConverterRegistration::ReadProviderConverterEntries`
- `0x180081c7a`: `ProviderConverterRegistration::ReadProviderConverterEntries`

## pseudocode

```c
__int64 __fastcall ProviderConverterRegistration::ReadProviderConverterEntries(ProviderConverterRegistration *this)
{
  bool v2; // zf
  IID *v3; // r15
  int v4; // ebx
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  DWORD v7; // eax
  DWORD v8; // edi
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[64]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR Data[64]; // [rsp+100h] [rbp+0h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      WPP_5820a2c240bc3bbeeb9e2f00b019b4aa_Traceguids,
      "ProviderConverterRegistration::ReadProviderConverterEntries");
  }
  v2 = *((_DWORD *)this + 2) == 1;
  v3 = 0;
  hKey = 0;
  phkResult = 0;
  cSubKeys = 0;
  if ( v2 )
  {
    v4 = -2147217379;
    goto LABEL_43;
  }
  v4 = 0;
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Sync Framework\\ProviderConverterRegistration",
         0,
         0x20019u,
         &hKey);
  if ( v5 == 2 )
  {
    v7 = cSubKeys;
LABEL_38:
    *((_QWORD *)this + 2) = v3;
    v3 = 0;
    *((_DWORD *)this + 2) = 1;
    *((_DWORD *)this + 6) = v7;
    goto LABEL_39;
  }
  if ( v5 > 0 )
    v4 = (unsigned __int16)v5 | 0x80070000;
  else
    v4 = v5;
  if ( v4 < 0 )
    goto LABEL_39;
  v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  v4 = v6;
  if ( v6 > 0 )
    v4 = (unsigned __int16)v6 | 0x80070000;
  if ( v4 < 0 )
    goto LABEL_39;
  v7 = cSubKeys;
  if ( !cSubKeys )
    goto LABEL_38;
  v3 = (IID *)SeAlloc(saturated_mul(cSubKeys, 0x20u));
  if ( v3 )
  {
    v7 = cSubKeys;
    if ( cSubKeys )
    {
      v8 = 0;
      while ( v8 < v7 )
      {
        cchName = 64;
        v9 = RegEnumKeyExW(hKey, v8, Name, &cchName, 0, 0, 0, 0);
        v4 = v9;
        if ( v9 > 0 )
          v4 = (unsigned __int16)v9 | 0x80070000;
        if ( v4 >= 0 )
        {
          v4 = IIDFromString(Name, &v3[2 * v8]);
          if ( v4 >= 0 )
          {
            v10 = RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult);
            v4 = v10;
            if ( v10 > 0 )
              v4 = (unsigned __int16)v10 | 0x80070000;
            if ( v4 >= 0 )
            {
              cchName = 128;
              v11 = RegQueryValueExW(phkResult, L"ConverterClassId", 0, 0, (LPBYTE)Data, &cchName);
              v4 = v11;
              if ( v11 > 0 )
                v4 = (unsigned __int16)v11 | 0x80070000;
              if ( v4 >= 0 )
                v4 = IIDFromString(Data, &v3[2 * v8 + 1]);
            }
          }
        }
        if ( phkResult )
        {
          RegCloseKey(phkResult);
          phkResult = 0;
        }
        ++v8;
        if ( v4 < 0 )
          goto LABEL_39;
        v7 = cSubKeys;
      }
    }
    goto LABEL_38;
  }
  v4 = -2147024882;
LABEL_39:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
LABEL_43:
  SeFree(v3);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      WPP_5820a2c240bc3bbeeb9e2f00b019b4aa_Traceguids,
      "ProviderConverterRegistration::ReadProviderConverterEntries");
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180081978  push    rbp
0x18008197a  push    rbx
0x18008197b  push    rsi
0x18008197c  push    rdi
0x18008197d  push    r12
0x18008197f  push    r13
0x180081981  push    r14
0x180081983  push    r15
0x180081985  lea     rbp, [rsp-98h]
0x18008198d  sub     rsp, 198h
0x180081994  mov     rax, cs:__security_cookie
0x18008199b  xor     rax, rsp
0x18008199e  mov     [rbp+0D0h+var_50], rax
0x1800819a5  mov     r14, rcx
0x1800819a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800819af  lea     rsi, WPP_GLOBAL_Control
0x1800819b6  cmp     rcx, rsi
0x1800819b9  jz      short loc_1800819E3
0x1800819bb  test    byte ptr [rcx+1Ch], 4
0x1800819bf  jz      short loc_1800819E3
0x1800819c1  cmp     byte ptr [rcx+19h], 5
0x1800819c5  jb      short loc_1800819E3
0x1800819c7  mov     rcx, [rcx+10h]
0x1800819cb  lea     r9, aProviderconver_1; "ProviderConverterRegistration::ReadProv"...
0x1800819d2  mov     edx, 12h
0x1800819d7  lea     r8, WPP_5820a2c240bc3bbeeb9e2f00b019b4aa_Traceguids
0x1800819de  call    WPP_SF_s
0x1800819e3  xor     r12d, r12d
0x1800819e6  cmp     dword ptr [r14+8], 1
0x1800819eb  mov     r15d, r12d
0x1800819ee  mov     [rsp+1D0h+hKey], r12
0x1800819f3  mov     [rsp+1D0h+var_168], r12
0x1800819f8  mov     [rsp+1D0h+cSubKeys], r12d
0x1800819fd  jnz     short loc_180081A09
0x1800819ff  mov     ebx, 8004101Dh
0x180081a04  jmp     loc_180081C56
0x180081a09  lea     rax, [rsp+1D0h+hKey]
0x180081a0e  mov     r9d, 20019h; samDesired
0x180081a14  xor     r8d, r8d; ulOptions
0x180081a17  mov     [rsp+1D0h+phkResult], rax; phkResult
0x180081a1c  lea     rdx, ?g_pszProviderConverterRegistrationSubKey@ProviderConverterRegistration@@0QBGB; "Software\\Microsoft\\Sync Framework\\Pr"...
0x180081a23  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180081a2a  mov     ebx, r12d
0x180081a2d  call    cs:__imp_RegOpenKeyExW
0x180081a33  cmp     eax, 2
0x180081a36  jz      loc_180081C16
0x180081a3c  mov     r13d, 80070000h
0x180081a42  test    eax, eax
0x180081a44  jg      short loc_180081A4A
0x180081a46  mov     ebx, eax
0x180081a48  jmp     short loc_180081A50
0x180081a4a  movzx   ebx, ax
0x180081a4d  or      ebx, r13d
0x180081a50  test    ebx, ebx
0x180081a52  js      loc_180081C36
0x180081a58  mov     rcx, [rsp+1D0h+hKey]; hKey
0x180081a5d  lea     rax, [rsp+1D0h+cSubKeys]
0x180081a62  mov     [rsp+1D0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180081a67  xor     r9d, r9d; lpReserved
0x180081a6a  mov     [rsp+1D0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180081a6f  xor     r8d, r8d; lpcchClass
0x180081a72  mov     [rsp+1D0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180081a77  xor     edx, edx; lpClass
0x180081a79  mov     [rsp+1D0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180081a7e  mov     [rsp+1D0h+lpcValues], r12; lpcValues
0x180081a83  mov     [rsp+1D0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180081a88  mov     [rsp+1D0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x180081a8d  mov     [rsp+1D0h+phkResult], rax; lpcSubKeys
0x180081a92  call    cs:__imp_RegQueryInfoKeyW
0x180081a98  mov     ebx, eax
0x180081a9a  test    eax, eax
0x180081a9c  jle     short loc_180081AA4
0x180081a9e  movzx   ebx, ax
0x180081aa1  or      ebx, r13d
0x180081aa4  test    ebx, ebx
0x180081aa6  js      loc_180081C36
0x180081aac  mov     eax, [rsp+1D0h+cSubKeys]
0x180081ab0  test    eax, eax
0x180081ab2  jz      loc_180081C23
0x180081ab8  mov     ecx, eax
0x180081aba  mov     eax, 20h ; ' '
0x180081abf  mul     rcx
0x180081ac2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180081ac9  cmovb   rax, rcx
0x180081acd  mov     rcx, rax; unsigned __int64
0x180081ad0  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180081ad5  mov     r15, rax
0x180081ad8  test    rax, rax
0x180081adb  jnz     short loc_180081AE7
0x180081add  mov     ebx, 8007000Eh
0x180081ae2  jmp     loc_180081C36
0x180081ae7  mov     eax, [rsp+1D0h+cSubKeys]
0x180081aeb  test    eax, eax
0x180081aed  jz      loc_180081C23
0x180081af3  mov     edi, r12d
0x180081af6  cmp     edi, eax
0x180081af8  jnb     loc_180081C1C
0x180081afe  mov     rcx, [rsp+1D0h+hKey]; hKey
0x180081b03  lea     r9, [rsp+1D0h+cchName]; lpcchName
0x180081b08  mov     [rsp+1D0h+lpcValues], r12; lpftLastWriteTime
0x180081b0d  lea     r8, [rbp+0D0h+Name]; lpName
0x180081b11  mov     [rsp+1D0h+lpcbMaxClassLen], r12; lpcchClass
0x180081b16  mov     edx, edi; dwIndex
0x180081b18  mov     [rsp+1D0h+lpcbMaxSubKeyLen], r12; lpClass
0x180081b1d  mov     [rsp+1D0h+phkResult], r12; lpReserved
0x180081b22  mov     [rsp+1D0h+cchName], 40h ; '@'
0x180081b2a  call    cs:__imp_RegEnumKeyExW
0x180081b30  mov     ebx, eax
0x180081b32  test    eax, eax
0x180081b34  jle     short loc_180081B3C
0x180081b36  movzx   ebx, ax
0x180081b39  or      ebx, r13d
0x180081b3c  test    ebx, ebx
0x180081b3e  js      loc_180081BE9
0x180081b44  mov     esi, edi
0x180081b46  lea     rcx, [rbp+0D0h+Name]; lpsz
0x180081b4a  shl     rsi, 5
0x180081b4e  add     rsi, r15
0x180081b51  mov     rdx, rsi; lpiid
0x180081b54  call    cs:__imp_IIDFromString
0x180081b5a  mov     ebx, eax
0x180081b5c  test    eax, eax
0x180081b5e  js      loc_180081BE9
0x180081b64  mov     rcx, [rsp+1D0h+hKey]; hKey
0x180081b69  lea     rax, [rsp+1D0h+var_168]
0x180081b6e  mov     r9d, 20019h; samDesired
0x180081b74  mov     [rsp+1D0h+phkResult], rax; phkResult
0x180081b79  xor     r8d, r8d; ulOptions
0x180081b7c  lea     rdx, [rbp+0D0h+Name]; lpSubKey
0x180081b80  call    cs:__imp_RegOpenKeyExW
0x180081b86  mov     ebx, eax
0x180081b88  test    eax, eax
0x180081b8a  jle     short loc_180081B92
0x180081b8c  movzx   ebx, ax
0x180081b8f  or      ebx, r13d
0x180081b92  test    ebx, ebx
0x180081b94  js      short loc_180081BE9
0x180081b96  mov     rcx, [rsp+1D0h+var_168]; hKey
0x180081b9b  lea     rax, [rsp+1D0h+cchName]
0x180081ba0  mov     [rsp+1D0h+lpcbMaxSubKeyLen], rax; lpcbData
0x180081ba5  lea     rdx, ?g_pszConverterClassId@ProviderConverterRegistration@@0QBGB; "ConverterClassId"
0x180081bac  lea     rax, [rbp+0D0h+Data]
0x180081bb0  mov     [rsp+1D0h+cchName], 80h
0x180081bb8  xor     r9d, r9d; lpType
0x180081bbb  mov     [rsp+1D0h+phkResult], rax; lpData
0x180081bc0  xor     r8d, r8d; lpReserved
0x180081bc3  call    cs:__imp_RegQueryValueExW
0x180081bc9  mov     ebx, eax
0x180081bcb  test    eax, eax
0x180081bcd  jle     short loc_180081BD5
0x180081bcf  movzx   ebx, ax
0x180081bd2  or      ebx, r13d
0x180081bd5  test    ebx, ebx
0x180081bd7  js      short loc_180081BE9
0x180081bd9  lea     rdx, [rsi+10h]; lpiid
0x180081bdd  lea     rcx, [rbp+0D0h+Data]; lpsz
0x180081be1  call    cs:__imp_IIDFromString
0x180081be7  mov     ebx, eax
0x180081be9  mov     rcx, [rsp+1D0h+var_168]; hKey
0x180081bee  test    rcx, rcx
0x180081bf1  jz      short loc_180081BFE
0x180081bf3  call    cs:__imp_RegCloseKey
0x180081bf9  mov     [rsp+1D0h+var_168], r12
0x180081bfe  inc     edi
0x180081c00  test    ebx, ebx
0x180081c02  js      short loc_180081C0D
0x180081c04  mov     eax, [rsp+1D0h+cSubKeys]
0x180081c08  jmp     loc_180081AF6
0x180081c0d  lea     rsi, WPP_GLOBAL_Control
0x180081c14  jmp     short loc_180081C36
0x180081c16  mov     eax, [rsp+1D0h+cSubKeys]
0x180081c1a  jmp     short loc_180081C23
0x180081c1c  lea     rsi, WPP_GLOBAL_Control
0x180081c23  mov     [r14+10h], r15
0x180081c27  mov     r15, r12
0x180081c2a  mov     dword ptr [r14+8], 1
0x180081c32  mov     [r14+18h], eax
0x180081c36  mov     rcx, [rsp+1D0h+var_168]; hKey
0x180081c3b  test    rcx, rcx
0x180081c3e  jz      short loc_180081C46
0x180081c40  call    cs:__imp_RegCloseKey
0x180081c46  mov     rcx, [rsp+1D0h+hKey]; hKey
0x180081c4b  test    rcx, rcx
0x180081c4e  jz      short loc_180081C56
0x180081c50  call    cs:__imp_RegCloseKey
0x180081c56  mov     rcx, r15; void *
0x180081c59  call    ?SeFree@@YAXPEAX@Z; SeFree(void *)
0x180081c5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180081c65  cmp     rcx, rsi
0x180081c68  jz      short loc_180081C92
0x180081c6a  test    byte ptr [rcx+1Ch], 4
0x180081c6e  jz      short loc_180081C92
0x180081c70  cmp     byte ptr [rcx+19h], 5
0x180081c74  jb      short loc_180081C92
0x180081c76  mov     rcx, [rcx+10h]
0x180081c7a  lea     r9, aProviderconver_1; "ProviderConverterRegistration::ReadProv"...
0x180081c81  mov     edx, 13h
0x180081c86  lea     r8, WPP_5820a2c240bc3bbeeb9e2f00b019b4aa_Traceguids
0x180081c8d  call    WPP_SF_s
0x180081c92  mov     eax, ebx
0x180081c94  mov     rcx, [rbp+0D0h+var_50]
0x180081c9b  xor     rcx, rsp; StackCookie
0x180081c9e  call    __security_check_cookie
0x180081ca3  add     rsp, 198h
0x180081caa  pop     r15
0x180081cac  pop     r14
0x180081cae  pop     r13
0x180081cb0  pop     r12
0x180081cb2  pop     rdi
0x180081cb3  pop     rsi
0x180081cb4  pop     rbx
0x180081cb5  pop     rbp
0x180081cb6  retn
```
