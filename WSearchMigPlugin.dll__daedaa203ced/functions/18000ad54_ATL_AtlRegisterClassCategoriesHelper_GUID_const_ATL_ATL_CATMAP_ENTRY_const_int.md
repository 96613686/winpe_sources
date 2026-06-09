# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18000ad54`
- end: `0x18000b21c`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1224`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000be14`
- `0x18000c120`

## callees

- `0x1800026f0`
- `0x18000ad54`
- `0x18000b410`
- `0x18000b438`
- `0x180018010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000af0e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000af4a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000b07c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000b0b8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000af0e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000af4a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000b07c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000b0b8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000aeca`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000b040`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000aeca`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000b040`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000aff9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000b165`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000aff9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000b165`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000afb2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b105`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000afb2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b105`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b009`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b11e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b175`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b1a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b1b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b009`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b11e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b175`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b1a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b1b0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ae03`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ae03`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000aeb2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000aeb2`

## string_xrefs

- `0x18000aeb8`: `CLSID\`
- `0x18000b02e`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rdi
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // esi
  __int64 v10; // rax
  int v11; // ecx
  int v12; // eax
  int v13; // eax
  int v14; // eax
  HKEY v15; // rdi
  HKEY v16; // rbx
  LSTATUS InfoKeyW; // esi
  int v18; // eax
  int v19; // eax
  int v20; // eax
  HKEY v21; // rbx
  LSTATUS v22; // esi
  DWORD cSubKeys[2]; // [rsp+68h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-88h] BYREF
  _QWORD v27[4]; // [rsp+88h] [rbp-80h] BYREF
  __int128 v28; // [rsp+A8h] [rbp-60h] BYREF
  WCHAR SubKey[128]; // [rsp+B8h] [rbp-50h] BYREF
  OLECHAR sz[64]; // [rsp+1B8h] [rbp+B0h] BYREF

  v27[3] = -2;
  v4 = a2;
  ppv = 0;
  v28 = 0;
  if ( !a2
    || rguid->Data1 == GUID_NULL.Data1
    && *(_DWORD *)&rguid->Data2 == *(_DWORD *)&GUID_NULL.Data2
    && *(_DWORD *)rguid->Data4 == *(_DWORD *)GUID_NULL.Data4
    && *(_DWORD *)&rguid->Data4[4] == *(_DWORD *)&GUID_NULL.Data4[4] )
  {
    return 0;
  }
  if ( CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) < 0 )
  {
LABEL_66:
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return 0;
  }
  while ( 1 )
  {
    v11 = *(_DWORD *)v4;
    if ( !*(_DWORD *)v4 )
    {
      if ( a3 )
        goto LABEL_66;
      StringFromGUID2(rguid, sz, 64);
      v12 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      if ( v12 )
      {
        if ( v12 == 12 )
          goto LABEL_69;
        if ( v12 == 22 || v12 == 34 )
          goto LABEL_71;
        if ( v12 != 80 )
          goto LABEL_70;
      }
      v13 = _o_wcscat_s(SubKey, 128, sz);
      if ( v13 )
      {
        if ( v13 == 12 )
          goto LABEL_69;
        if ( v13 == 22 || v13 == 34 )
          goto LABEL_71;
        if ( v13 != 80 )
          goto LABEL_70;
      }
      v14 = _o_wcscat_s(SubKey, 128, L"\\Required Categories");
      if ( v14 )
      {
        if ( v14 == 12 )
          goto LABEL_69;
        if ( v14 == 22 || v14 == 34 )
          goto LABEL_71;
        if ( v14 != 80 )
          goto LABEL_70;
      }
      v15 = HKEY_CLASSES_ROOT;
      v27[0] = 0xFFFFFFFF80000000uLL;
      v27[1] = 0;
      v27[2] = 0;
      cSubKeys[0] = 0;
      phkResult = 0;
      if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &phkResult) )
      {
        v16 = phkResult;
        InfoKeyW = RegQueryInfoKeyW(phkResult, 0, 0, 0, cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        if ( v16 )
          RegCloseKey(v16);
        if ( !InfoKeyW && !cSubKeys[0] )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v27, SubKey);
          v15 = (HKEY)v27[0];
        }
      }
      v18 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      if ( v18 )
      {
        if ( v18 == 12 )
          goto LABEL_69;
        if ( v18 == 22 || v18 == 34 )
          goto LABEL_71;
        if ( v18 != 80 )
          goto LABEL_70;
      }
      v19 = _o_wcscat_s(SubKey, 128, sz);
      if ( v19 )
      {
        if ( v19 == 12 )
          goto LABEL_69;
        if ( v19 == 22 || v19 == 34 )
          goto LABEL_71;
        if ( v19 != 80 )
          goto LABEL_70;
      }
      v20 = _o_wcscat_s(SubKey, 128, L"\\Implemented Categories");
      if ( !v20 )
      {
LABEL_58:
        hKey = 0;
        if ( !RegOpenKeyExW(v15, SubKey, 0, 0x20019u, &hKey) )
        {
          v21 = hKey;
          v22 = RegQueryInfoKeyW(hKey, 0, 0, 0, cSubKeys, 0, 0, 0, 0, 0, 0, 0);
          if ( v21 )
            RegCloseKey(v21);
          if ( !v22 && !cSubKeys[0] )
          {
            ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v27, SubKey);
            v15 = (HKEY)v27[0];
          }
        }
        if ( v15 )
          RegCloseKey(v15);
        goto LABEL_66;
      }
      if ( v20 != 12 )
      {
        if ( v20 != 22 && v20 != 34 )
        {
          if ( v20 == 80 )
            goto LABEL_58;
LABEL_70:
          ATL::AtlThrowImpl(-2147467259);
        }
LABEL_71:
        ATL::AtlThrowImpl(-2147024809);
      }
LABEL_69:
      ATL::AtlThrowImpl(-2147024882);
    }
    v28 = *(_OWORD *)*((_QWORD *)v4 + 1);
    if ( !a3 )
    {
      v10 = *(_QWORD *)ppv;
      if ( v11 == 1 )
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v10 + 48))(ppv, rguid, 1, &v28);
      else
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v10 + 64))(ppv, rguid, 1, &v28);
      goto LABEL_19;
    }
    v6 = *(_QWORD *)ppv;
    v7 = v11 == 1
       ? (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v28)
       : (*(unsigned __int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v28);
    v8 = v7;
    if ( v7 < 0 )
      break;
LABEL_19:
    v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v8;
}

```

## disassembly

```asm
0x18000ad54  mov     rax, rsp
0x18000ad57  push    rbp
0x18000ad58  push    rdi
0x18000ad59  push    r12
0x18000ad5b  push    r14
0x18000ad5d  push    r15
0x18000ad5f  lea     rbp, [rax-168h]
0x18000ad66  sub     rsp, 240h
0x18000ad6d  mov     [rbp+160h+var_1C8], 0FFFFFFFFFFFFFFFEh
0x18000ad75  mov     [rax+18h], rbx
0x18000ad79  mov     [rax+20h], rsi
0x18000ad7d  mov     rax, cs:__security_cookie
0x18000ad84  xor     rax, rsp
0x18000ad87  mov     [rbp+160h+var_30], rax
0x18000ad8e  mov     r14d, r8d
0x18000ad91  mov     rdi, rdx
0x18000ad94  mov     rbx, rcx
0x18000ad97  xor     r15d, r15d
0x18000ad9a  mov     [rsp+260h+var_1F8], r15
0x18000ad9f  xorps   xmm0, xmm0
0x18000ada2  movups  [rbp+160h+var_1C0], xmm0
0x18000ada6  test    rdx, rdx
0x18000ada9  jnz     short loc_18000ADB0
0x18000adab  jmp     loc_18000B1CE
0x18000adb0  mov     eax, cs:GUID_NULL.Data1
0x18000adb6  cmp     [rcx], eax
0x18000adb8  jnz     short loc_18000ADE0
0x18000adba  mov     eax, dword ptr cs:GUID_NULL.Data2
0x18000adc0  cmp     [rcx+4], eax
0x18000adc3  jnz     short loc_18000ADE0
0x18000adc5  mov     eax, dword ptr cs:GUID_NULL.Data4
0x18000adcb  cmp     [rcx+8], eax
0x18000adce  jnz     short loc_18000ADE0
0x18000add0  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x18000add6  cmp     [rcx+0Ch], eax
0x18000add9  jnz     short loc_18000ADE0
0x18000addb  jmp     loc_18000B1CE
0x18000ade0  lea     rax, [rsp+260h+var_1F8]
0x18000ade5  mov     [rsp+260h+ppv], rax; ppv
0x18000adea  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18000adf1  mov     r12d, 1
0x18000adf7  mov     r8d, r12d; dwClsContext
0x18000adfa  xor     edx, edx; pUnkOuter
0x18000adfc  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18000ae03  call    cs:__imp_CoCreateInstance
0x18000ae09  test    eax, eax
0x18000ae0b  jns     loc_18000AE91
0x18000ae11  jmp     loc_18000B1B7
0x18000ae16  mov     rax, [rdi+8]
0x18000ae1a  movups  xmm0, xmmword ptr [rax]
0x18000ae1d  movdqu  [rbp+160h+var_1C0], xmm0
0x18000ae22  lea     r9, [rbp+160h+var_1C0]
0x18000ae26  mov     r8d, r12d
0x18000ae29  mov     rdx, rbx
0x18000ae2c  test    r14d, r14d
0x18000ae2f  jz      short loc_18000AE71
0x18000ae31  cmp     ecx, r12d
0x18000ae34  mov     rcx, [rsp+260h+var_1F8]
0x18000ae39  mov     rax, [rcx]
0x18000ae3c  jnz     short loc_18000AE44
0x18000ae3e  mov     rax, [rax+28h]
0x18000ae42  jmp     short loc_18000AE48
0x18000ae44  mov     rax, [rax+38h]
0x18000ae48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae4d  mov     esi, eax
0x18000ae4f  test    eax, eax
0x18000ae51  jns     short loc_18000AE8D
0x18000ae53  mov     rcx, [rsp+260h+var_1F8]
0x18000ae58  test    rcx, rcx
0x18000ae5b  jz      short loc_18000AE6A
0x18000ae5d  mov     rax, [rcx]
0x18000ae60  mov     rax, [rax+10h]
0x18000ae64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae69  nop
0x18000ae6a  mov     eax, esi
0x18000ae6c  jmp     loc_18000B1D0
0x18000ae71  cmp     ecx, r12d
0x18000ae74  mov     rcx, [rsp+260h+var_1F8]
0x18000ae79  mov     rax, [rcx]
0x18000ae7c  jnz     short loc_18000AE84
0x18000ae7e  mov     rax, [rax+30h]
0x18000ae82  jmp     short loc_18000AE88
0x18000ae84  mov     rax, [rax+40h]
0x18000ae88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae8d  add     rdi, 10h
0x18000ae91  mov     ecx, [rdi]
0x18000ae93  test    ecx, ecx
0x18000ae95  jnz     loc_18000AE16
0x18000ae9b  test    r14d, r14d
0x18000ae9e  jnz     loc_18000B1B7
0x18000aea4  lea     r8d, [rcx+40h]; cchMax
0x18000aea8  lea     rdx, [rbp+160h+sz]; lpsz
0x18000aeaf  mov     rcx, rbx; rguid
0x18000aeb2  call    cs:__imp_StringFromGUID2
0x18000aeb8  lea     r8, aClsid; "CLSID\\"
0x18000aebf  mov     ebx, 80h
0x18000aec4  mov     edx, ebx
0x18000aec6  lea     rcx, [rbp+160h+SubKey]
0x18000aeca  call    cs:__imp__o_wcscpy_s
0x18000aed0  lea     r14d, [rbx-74h]
0x18000aed4  lea     r12d, [rbx-30h]
0x18000aed8  test    eax, eax
0x18000aeda  jz      short loc_18000AF00
0x18000aedc  cmp     eax, r14d
0x18000aedf  jz      loc_18000B1FB
0x18000aee5  cmp     eax, 16h
0x18000aee8  jz      loc_18000B211
0x18000aeee  cmp     eax, 22h ; '"'
0x18000aef1  jz      loc_18000B211
0x18000aef7  cmp     eax, r12d
0x18000aefa  jnz     loc_18000B206
0x18000af00  lea     r8, [rbp+160h+sz]
0x18000af07  mov     rdx, rbx
0x18000af0a  lea     rcx, [rbp+160h+SubKey]
0x18000af0e  call    cs:__imp__o_wcscat_s
0x18000af14  test    eax, eax
0x18000af16  jz      short loc_18000AF3C
0x18000af18  cmp     eax, r14d
0x18000af1b  jz      loc_18000B1FB
0x18000af21  cmp     eax, 16h
0x18000af24  jz      loc_18000B211
0x18000af2a  cmp     eax, 22h ; '"'
0x18000af2d  jz      loc_18000B211
0x18000af33  cmp     eax, r12d
0x18000af36  jnz     loc_18000B206
0x18000af3c  lea     r8, aRequiredCatego; "\\Required Categories"
0x18000af43  mov     rdx, rbx
0x18000af46  lea     rcx, [rbp+160h+SubKey]
0x18000af4a  call    cs:__imp__o_wcscat_s
0x18000af50  test    eax, eax
0x18000af52  jz      short loc_18000AF78
0x18000af54  cmp     eax, r14d
0x18000af57  jz      loc_18000B1FB
0x18000af5d  cmp     eax, 16h
0x18000af60  jz      loc_18000B211
0x18000af66  cmp     eax, 22h ; '"'
0x18000af69  jz      loc_18000B211
0x18000af6f  cmp     eax, r12d
0x18000af72  jnz     loc_18000B206
0x18000af78  mov     rdi, 0FFFFFFFF80000000h
0x18000af7f  mov     [rbp+160h+var_1E0], rdi
0x18000af83  mov     [rbp+160h+var_1D8], r15
0x18000af87  mov     [rbp+160h+var_1D0], r15
0x18000af8b  mov     rbx, r15
0x18000af8e  mov     [rsp+260h+cSubKeys], r15d
0x18000af93  mov     [rsp+260h+phkResult], r15
0x18000af98  lea     rax, [rsp+260h+phkResult]
0x18000af9d  mov     [rsp+260h+ppv], rax; phkResult
0x18000afa2  mov     r9d, 20019h; samDesired
0x18000afa8  xor     r8d, r8d; ulOptions
0x18000afab  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x18000afaf  mov     rcx, rdi; hKey
0x18000afb2  call    cs:__imp_RegOpenKeyExW
0x18000afb8  test    eax, eax
0x18000afba  jnz     short loc_18000B02E
0x18000afbc  mov     rbx, [rsp+260h+phkResult]
0x18000afc1  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000afc6  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000afcb  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000afd0  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000afd5  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18000afda  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000afdf  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000afe4  lea     rax, [rsp+260h+cSubKeys]
0x18000afe9  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000afee  xor     r9d, r9d; lpReserved
0x18000aff1  xor     r8d, r8d; lpcchClass
0x18000aff4  xor     edx, edx; lpClass
0x18000aff6  mov     rcx, rbx; hKey
0x18000aff9  call    cs:__imp_RegQueryInfoKeyW
0x18000afff  mov     esi, eax
0x18000b001  test    rbx, rbx
0x18000b004  jz      short loc_18000B012
0x18000b006  mov     rcx, rbx; hKey
0x18000b009  call    cs:__imp_RegCloseKey
0x18000b00f  mov     rbx, r15
0x18000b012  test    esi, esi
0x18000b014  jnz     short loc_18000B02E
0x18000b016  cmp     [rsp+260h+cSubKeys], r15d
0x18000b01b  jnz     short loc_18000B02E
0x18000b01d  lea     rdx, [rbp+160h+SubKey]; wchar_t *
0x18000b021  lea     rcx, [rbp+160h+var_1E0]; this
0x18000b025  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x18000b02a  mov     rdi, [rbp+160h+var_1E0]
0x18000b02e  lea     r8, aClsid; "CLSID\\"
0x18000b035  mov     esi, 80h
0x18000b03a  mov     edx, esi
0x18000b03c  lea     rcx, [rbp+160h+SubKey]
0x18000b040  call    cs:__imp__o_wcscpy_s
0x18000b046  test    eax, eax
0x18000b048  jz      short loc_18000B06E
0x18000b04a  cmp     eax, r14d
0x18000b04d  jz      loc_18000B1FB
0x18000b053  cmp     eax, 16h
0x18000b056  jz      loc_18000B211
0x18000b05c  cmp     eax, 22h ; '"'
0x18000b05f  jz      loc_18000B211
0x18000b065  cmp     eax, r12d
0x18000b068  jnz     loc_18000B206
0x18000b06e  lea     r8, [rbp+160h+sz]
0x18000b075  mov     rdx, rsi
0x18000b078  lea     rcx, [rbp+160h+SubKey]
0x18000b07c  call    cs:__imp__o_wcscat_s
0x18000b082  test    eax, eax
0x18000b084  jz      short loc_18000B0AA
0x18000b086  cmp     eax, r14d
0x18000b089  jz      loc_18000B1FB
0x18000b08f  cmp     eax, 16h
0x18000b092  jz      loc_18000B211
0x18000b098  cmp     eax, 22h ; '"'
0x18000b09b  jz      loc_18000B211
0x18000b0a1  cmp     eax, r12d
0x18000b0a4  jnz     loc_18000B206
0x18000b0aa  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18000b0b1  mov     rdx, rsi
0x18000b0b4  lea     rcx, [rbp+160h+SubKey]
0x18000b0b8  call    cs:__imp__o_wcscat_s
0x18000b0be  test    eax, eax
0x18000b0c0  jz      short loc_18000B0E6
0x18000b0c2  cmp     eax, r14d
0x18000b0c5  jz      loc_18000B1FB
0x18000b0cb  cmp     eax, 16h
0x18000b0ce  jz      loc_18000B211
0x18000b0d4  cmp     eax, 22h ; '"'
0x18000b0d7  jz      loc_18000B211
0x18000b0dd  cmp     eax, r12d
0x18000b0e0  jnz     loc_18000B206
0x18000b0e6  mov     [rsp+260h+hKey], r15
0x18000b0eb  lea     rax, [rsp+260h+hKey]
0x18000b0f0  mov     [rsp+260h+ppv], rax; phkResult
0x18000b0f5  mov     r9d, 20019h; samDesired
0x18000b0fb  xor     r8d, r8d; ulOptions
0x18000b0fe  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x18000b102  mov     rcx, rdi; hKey
0x18000b105  call    cs:__imp_RegOpenKeyExW
0x18000b10b  test    eax, eax
0x18000b10d  jnz     loc_18000B19A
0x18000b113  mov     eax, r15d
0x18000b116  test    rbx, rbx
0x18000b119  jz      short loc_18000B124
0x18000b11b  mov     rcx, rbx; hKey
0x18000b11e  call    cs:__imp_RegCloseKey
0x18000b124  mov     rbx, [rsp+260h+hKey]
0x18000b129  test    eax, eax
0x18000b12b  jnz     short loc_18000B19A
0x18000b12d  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000b132  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000b137  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000b13c  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000b141  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18000b146  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000b14b  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000b150  lea     rax, [rsp+260h+cSubKeys]
0x18000b155  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000b15a  xor     r9d, r9d; lpReserved
0x18000b15d  xor     r8d, r8d; lpcchClass
0x18000b160  xor     edx, edx; lpClass
0x18000b162  mov     rcx, rbx; hKey
0x18000b165  call    cs:__imp_RegQueryInfoKeyW
0x18000b16b  mov     esi, eax
0x18000b16d  test    rbx, rbx
0x18000b170  jz      short loc_18000B17E
0x18000b172  mov     rcx, rbx; hKey
0x18000b175  call    cs:__imp_RegCloseKey
0x18000b17b  mov     rbx, r15
0x18000b17e  test    esi, esi
0x18000b180  jnz     short loc_18000B1A8
0x18000b182  cmp     [rsp+260h+cSubKeys], r15d
0x18000b187  jnz     short loc_18000B19A
0x18000b189  lea     rdx, [rbp+160h+SubKey]; wchar_t *
0x18000b18d  lea     rcx, [rbp+160h+var_1E0]; this
0x18000b191  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x18000b196  mov     rdi, [rbp+160h+var_1E0]
0x18000b19a  test    rbx, rbx
0x18000b19d  jz      short loc_18000B1A8
0x18000b19f  mov     rcx, rbx; hKey
0x18000b1a2  call    cs:__imp_RegCloseKey
0x18000b1a8  test    rdi, rdi
0x18000b1ab  jz      short loc_18000B1B7
0x18000b1ad  mov     rcx, rdi; hKey
0x18000b1b0  call    cs:__imp_RegCloseKey
0x18000b1b6  nop
0x18000b1b7  mov     rcx, [rsp+260h+var_1F8]
0x18000b1bc  test    rcx, rcx
0x18000b1bf  jz      short loc_18000B1CE
0x18000b1c1  mov     rax, [rcx]
0x18000b1c4  mov     rax, [rax+10h]
0x18000b1c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1cd  nop
0x18000b1ce  xor     eax, eax
0x18000b1d0  mov     rcx, [rbp+160h+var_30]
0x18000b1d7  xor     rcx, rsp; StackCookie
0x18000b1da  call    __security_check_cookie
0x18000b1df  lea     r11, [rsp+260h+var_20]
0x18000b1e7  mov     rbx, [r11+40h]
0x18000b1eb  mov     rsi, [r11+48h]
0x18000b1ef  mov     rsp, r11
0x18000b1f2  pop     r15
0x18000b1f4  pop     r14
0x18000b1f6  pop     r12
  ... truncated ...
```
