# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180003c7c`
- end: `0x18000413c`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1216`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006b20`
- `0x180006c20`

## callees

- `0x180003c7c`
- `0x180004328`
- `0x180004998`
- `0x18000a9d0`
- `0x18000c010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180003e2e`
- `msvcrt!wcscat_s` at `0x180003e6a`
- `msvcrt!wcscat_s` at `0x180003f9c`
- `msvcrt!wcscat_s` at `0x180003fd8`
- `msvcrt!wcscat_s` at `0x180003e2e`
- `msvcrt!wcscat_s` at `0x180003e6a`
- `msvcrt!wcscat_s` at `0x180003f9c`
- `msvcrt!wcscat_s` at `0x180003fd8`
- `msvcrt!wcscpy_s` at `0x180003dea`
- `msvcrt!wcscpy_s` at `0x180003f60`
- `msvcrt!wcscpy_s` at `0x180003dea`
- `msvcrt!wcscpy_s` at `0x180003f60`
- `ADVAPI32!RegOpenKeyExW` at `0x180003ed2`
- `ADVAPI32!RegOpenKeyExW` at `0x180004025`
- `ADVAPI32!RegOpenKeyExW` at `0x180003ed2`
- `ADVAPI32!RegOpenKeyExW` at `0x180004025`
- `ADVAPI32!RegCloseKey` at `0x180003f29`
- `ADVAPI32!RegCloseKey` at `0x18000403e`
- `ADVAPI32!RegCloseKey` at `0x180004095`
- `ADVAPI32!RegCloseKey` at `0x1800040c2`
- `ADVAPI32!RegCloseKey` at `0x1800040d0`
- `ADVAPI32!RegCloseKey` at `0x180003f29`
- `ADVAPI32!RegCloseKey` at `0x18000403e`
- `ADVAPI32!RegCloseKey` at `0x180004095`
- `ADVAPI32!RegCloseKey` at `0x1800040c2`
- `ADVAPI32!RegCloseKey` at `0x1800040d0`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003f19`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180004085`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003f19`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180004085`
- `ole32!CoCreateInstance` at `0x180003d23`
- `ole32!CoCreateInstance` at `0x180003d23`
- `ole32!StringFromGUID2` at `0x180003dd2`
- `ole32!StringFromGUID2` at `0x180003dd2`

## string_xrefs

- `0x180003dd8`: `CLSID\`
- `0x180003f4e`: `CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rdi
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // esi
  __int64 v10; // rax
  int v11; // ecx
  errno_t v12; // eax
  errno_t v13; // eax
  errno_t v14; // eax
  HKEY v15; // rdi
  HKEY v16; // rbx
  LSTATUS v17; // esi
  errno_t v18; // eax
  errno_t v19; // eax
  errno_t v20; // eax
  HKEY v21; // rbx
  LSTATUS v22; // esi
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v27[3]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v28; // [rsp+98h] [rbp-68h] BYREF
  wchar_t Destination[128]; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR sz[64]; // [rsp+1B0h] [rbp+B0h] BYREF

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
      v12 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      if ( v12 )
      {
        if ( v12 == 12 )
          goto LABEL_69;
        if ( v12 == 22 || v12 == 34 )
          goto LABEL_71;
        if ( v12 != 80 )
          goto LABEL_70;
      }
      v13 = wcscat_s(Destination, 0x80u, sz);
      if ( v13 )
      {
        if ( v13 == 12 )
          goto LABEL_69;
        if ( v13 == 22 || v13 == 34 )
          goto LABEL_71;
        if ( v13 != 80 )
          goto LABEL_70;
      }
      v14 = wcscat_s(Destination, 0x80u, L"\\Required Categories");
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
      cSubKeys = 0;
      phkResult = 0;
      if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, Destination, 0, 0x20019u, &phkResult) )
      {
        v16 = phkResult;
        v17 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        if ( v16 )
          RegCloseKey(v16);
        if ( !v17 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v27, Destination);
          v15 = (HKEY)v27[0];
        }
      }
      v18 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      if ( v18 )
      {
        if ( v18 == 12 )
          goto LABEL_69;
        if ( v18 == 22 || v18 == 34 )
          goto LABEL_71;
        if ( v18 != 80 )
          goto LABEL_70;
      }
      v19 = wcscat_s(Destination, 0x80u, sz);
      if ( v19 )
      {
        if ( v19 == 12 )
          goto LABEL_69;
        if ( v19 == 22 || v19 == 34 )
          goto LABEL_71;
        if ( v19 != 80 )
          goto LABEL_70;
      }
      v20 = wcscat_s(Destination, 0x80u, L"\\Implemented Categories");
      if ( !v20 )
      {
LABEL_58:
        hKey = 0;
        if ( !RegOpenKeyExW(v15, Destination, 0, 0x20019u, &hKey) )
        {
          v21 = hKey;
          v22 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
          if ( v21 )
            RegCloseKey(v21);
          if ( !v22 && !cSubKeys )
          {
            ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v27, Destination);
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
0x180003c7c  mov     [rsp-8+arg_10], rbx
0x180003c81  mov     [rsp-8+arg_18], rsi
0x180003c86  push    rbp
0x180003c87  push    rdi
0x180003c88  push    r12
0x180003c8a  push    r14
0x180003c8c  push    r15
0x180003c8e  lea     rbp, [rsp-140h]
0x180003c96  sub     rsp, 240h
0x180003c9d  mov     rax, cs:__security_cookie
0x180003ca4  xor     rax, rsp
0x180003ca7  mov     [rbp+160h+var_30], rax
0x180003cae  mov     r14d, r8d
0x180003cb1  mov     rdi, rdx
0x180003cb4  mov     rbx, rcx
0x180003cb7  xor     r15d, r15d
0x180003cba  mov     [rsp+260h+var_1F8], r15
0x180003cbf  xorps   xmm0, xmm0
0x180003cc2  movups  [rbp+160h+var_1C8], xmm0
0x180003cc6  test    rdx, rdx
0x180003cc9  jnz     short loc_180003CD0
0x180003ccb  jmp     loc_1800040EE
0x180003cd0  mov     eax, cs:GUID_NULL.Data1
0x180003cd6  cmp     [rcx], eax
0x180003cd8  jnz     short loc_180003D00
0x180003cda  mov     eax, dword ptr cs:GUID_NULL.Data2
0x180003ce0  cmp     [rcx+4], eax
0x180003ce3  jnz     short loc_180003D00
0x180003ce5  mov     eax, dword ptr cs:GUID_NULL.Data4
0x180003ceb  cmp     [rcx+8], eax
0x180003cee  jnz     short loc_180003D00
0x180003cf0  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x180003cf6  cmp     [rcx+0Ch], eax
0x180003cf9  jnz     short loc_180003D00
0x180003cfb  jmp     loc_1800040EE
0x180003d00  lea     rax, [rsp+260h+var_1F8]
0x180003d05  mov     [rsp+260h+ppv], rax; ppv
0x180003d0a  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180003d11  mov     r12d, 1
0x180003d17  mov     r8d, r12d; dwClsContext
0x180003d1a  xor     edx, edx; pUnkOuter
0x180003d1c  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180003d23  call    cs:__imp_CoCreateInstance
0x180003d29  test    eax, eax
0x180003d2b  jns     loc_180003DB1
0x180003d31  jmp     loc_1800040D7
0x180003d36  mov     rax, [rdi+8]
0x180003d3a  movups  xmm0, xmmword ptr [rax]
0x180003d3d  movdqu  [rbp+160h+var_1C8], xmm0
0x180003d42  lea     r9, [rbp+160h+var_1C8]
0x180003d46  mov     r8d, r12d
0x180003d49  mov     rdx, rbx
0x180003d4c  test    r14d, r14d
0x180003d4f  jz      short loc_180003D91
0x180003d51  cmp     ecx, r12d
0x180003d54  mov     rcx, [rsp+260h+var_1F8]
0x180003d59  mov     rax, [rcx]
0x180003d5c  jnz     short loc_180003D64
0x180003d5e  mov     rax, [rax+28h]
0x180003d62  jmp     short loc_180003D68
0x180003d64  mov     rax, [rax+38h]
0x180003d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d6d  mov     esi, eax
0x180003d6f  test    eax, eax
0x180003d71  jns     short loc_180003DAD
0x180003d73  mov     rcx, [rsp+260h+var_1F8]
0x180003d78  test    rcx, rcx
0x180003d7b  jz      short loc_180003D8A
0x180003d7d  mov     rax, [rcx]
0x180003d80  mov     rax, [rax+10h]
0x180003d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d89  nop
0x180003d8a  mov     eax, esi
0x180003d8c  jmp     loc_1800040F0
0x180003d91  cmp     ecx, r12d
0x180003d94  mov     rcx, [rsp+260h+var_1F8]
0x180003d99  mov     rax, [rcx]
0x180003d9c  jnz     short loc_180003DA4
0x180003d9e  mov     rax, [rax+30h]
0x180003da2  jmp     short loc_180003DA8
0x180003da4  mov     rax, [rax+40h]
0x180003da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dad  add     rdi, 10h
0x180003db1  mov     ecx, [rdi]
0x180003db3  test    ecx, ecx
0x180003db5  jnz     loc_180003D36
0x180003dbb  test    r14d, r14d
0x180003dbe  jnz     loc_1800040D7
0x180003dc4  lea     r8d, [rcx+40h]; cchMax
0x180003dc8  lea     rdx, [rbp+160h+sz]; lpsz
0x180003dcf  mov     rcx, rbx; rguid
0x180003dd2  call    cs:__imp_StringFromGUID2
0x180003dd8  lea     r8, aClsid; "CLSID\\"
0x180003ddf  mov     ebx, 80h
0x180003de4  mov     edx, ebx; SizeInWords
0x180003de6  lea     rcx, [rbp+160h+Destination]; Destination
0x180003dea  call    cs:__imp_wcscpy_s
0x180003df0  lea     r14d, [rbx-74h]
0x180003df4  lea     r12d, [rbx-30h]
0x180003df8  test    eax, eax
0x180003dfa  jz      short loc_180003E20
0x180003dfc  cmp     eax, r14d
0x180003dff  jz      loc_18000411B
0x180003e05  cmp     eax, 16h
0x180003e08  jz      loc_180004131
0x180003e0e  cmp     eax, 22h ; '"'
0x180003e11  jz      loc_180004131
0x180003e17  cmp     eax, r12d
0x180003e1a  jnz     loc_180004126
0x180003e20  lea     r8, [rbp+160h+sz]; Source
0x180003e27  mov     rdx, rbx; SizeInWords
0x180003e2a  lea     rcx, [rbp+160h+Destination]; Destination
0x180003e2e  call    cs:__imp_wcscat_s
0x180003e34  test    eax, eax
0x180003e36  jz      short loc_180003E5C
0x180003e38  cmp     eax, r14d
0x180003e3b  jz      loc_18000411B
0x180003e41  cmp     eax, 16h
0x180003e44  jz      loc_180004131
0x180003e4a  cmp     eax, 22h ; '"'
0x180003e4d  jz      loc_180004131
0x180003e53  cmp     eax, r12d
0x180003e56  jnz     loc_180004126
0x180003e5c  lea     r8, aRequiredCatego; "\\Required Categories"
0x180003e63  mov     rdx, rbx; SizeInWords
0x180003e66  lea     rcx, [rbp+160h+Destination]; Destination
0x180003e6a  call    cs:__imp_wcscat_s
0x180003e70  test    eax, eax
0x180003e72  jz      short loc_180003E98
0x180003e74  cmp     eax, r14d
0x180003e77  jz      loc_18000411B
0x180003e7d  cmp     eax, 16h
0x180003e80  jz      loc_180004131
0x180003e86  cmp     eax, 22h ; '"'
0x180003e89  jz      loc_180004131
0x180003e8f  cmp     eax, r12d
0x180003e92  jnz     loc_180004126
0x180003e98  mov     rdi, 0FFFFFFFF80000000h
0x180003e9f  mov     [rbp+160h+var_1E0], rdi
0x180003ea3  mov     [rbp+160h+var_1D8], r15
0x180003ea7  mov     [rbp+160h+var_1D0], r15
0x180003eab  mov     rbx, r15
0x180003eae  mov     [rsp+260h+cSubKeys], r15d
0x180003eb3  mov     [rsp+260h+phkResult], r15
0x180003eb8  lea     rax, [rsp+260h+phkResult]
0x180003ebd  mov     [rsp+260h+ppv], rax; phkResult
0x180003ec2  mov     r9d, 20019h; samDesired
0x180003ec8  xor     r8d, r8d; ulOptions
0x180003ecb  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x180003ecf  mov     rcx, rdi; hKey
0x180003ed2  call    cs:__imp_RegOpenKeyExW
0x180003ed8  test    eax, eax
0x180003eda  jnz     short loc_180003F4E
0x180003edc  mov     rbx, [rsp+260h+phkResult]
0x180003ee1  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180003ee6  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180003eeb  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180003ef0  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180003ef5  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180003efa  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180003eff  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180003f04  lea     rax, [rsp+260h+cSubKeys]
0x180003f09  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180003f0e  xor     r9d, r9d; lpReserved
0x180003f11  xor     r8d, r8d; lpcchClass
0x180003f14  xor     edx, edx; lpClass
0x180003f16  mov     rcx, rbx; hKey
0x180003f19  call    cs:__imp_RegQueryInfoKeyW
0x180003f1f  mov     esi, eax
0x180003f21  test    rbx, rbx
0x180003f24  jz      short loc_180003F32
0x180003f26  mov     rcx, rbx; hKey
0x180003f29  call    cs:__imp_RegCloseKey
0x180003f2f  mov     rbx, r15
0x180003f32  test    esi, esi
0x180003f34  jnz     short loc_180003F4E
0x180003f36  cmp     [rsp+260h+cSubKeys], r15d
0x180003f3b  jnz     short loc_180003F4E
0x180003f3d  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x180003f41  lea     rcx, [rbp+160h+var_1E0]; this
0x180003f45  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180003f4a  mov     rdi, [rbp+160h+var_1E0]
0x180003f4e  lea     r8, aClsid; "CLSID\\"
0x180003f55  mov     esi, 80h
0x180003f5a  mov     edx, esi; SizeInWords
0x180003f5c  lea     rcx, [rbp+160h+Destination]; Destination
0x180003f60  call    cs:__imp_wcscpy_s
0x180003f66  test    eax, eax
0x180003f68  jz      short loc_180003F8E
0x180003f6a  cmp     eax, r14d
0x180003f6d  jz      loc_18000411B
0x180003f73  cmp     eax, 16h
0x180003f76  jz      loc_180004131
0x180003f7c  cmp     eax, 22h ; '"'
0x180003f7f  jz      loc_180004131
0x180003f85  cmp     eax, r12d
0x180003f88  jnz     loc_180004126
0x180003f8e  lea     r8, [rbp+160h+sz]; Source
0x180003f95  mov     rdx, rsi; SizeInWords
0x180003f98  lea     rcx, [rbp+160h+Destination]; Destination
0x180003f9c  call    cs:__imp_wcscat_s
0x180003fa2  test    eax, eax
0x180003fa4  jz      short loc_180003FCA
0x180003fa6  cmp     eax, r14d
0x180003fa9  jz      loc_18000411B
0x180003faf  cmp     eax, 16h
0x180003fb2  jz      loc_180004131
0x180003fb8  cmp     eax, 22h ; '"'
0x180003fbb  jz      loc_180004131
0x180003fc1  cmp     eax, r12d
0x180003fc4  jnz     loc_180004126
0x180003fca  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180003fd1  mov     rdx, rsi; SizeInWords
0x180003fd4  lea     rcx, [rbp+160h+Destination]; Destination
0x180003fd8  call    cs:__imp_wcscat_s
0x180003fde  test    eax, eax
0x180003fe0  jz      short loc_180004006
0x180003fe2  cmp     eax, r14d
0x180003fe5  jz      loc_18000411B
0x180003feb  cmp     eax, 16h
0x180003fee  jz      loc_180004131
0x180003ff4  cmp     eax, 22h ; '"'
0x180003ff7  jz      loc_180004131
0x180003ffd  cmp     eax, r12d
0x180004000  jnz     loc_180004126
0x180004006  mov     [rsp+260h+hKey], r15
0x18000400b  lea     rax, [rsp+260h+hKey]
0x180004010  mov     [rsp+260h+ppv], rax; phkResult
0x180004015  mov     r9d, 20019h; samDesired
0x18000401b  xor     r8d, r8d; ulOptions
0x18000401e  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x180004022  mov     rcx, rdi; hKey
0x180004025  call    cs:__imp_RegOpenKeyExW
0x18000402b  test    eax, eax
0x18000402d  jnz     loc_1800040BA
0x180004033  mov     eax, r15d
0x180004036  test    rbx, rbx
0x180004039  jz      short loc_180004044
0x18000403b  mov     rcx, rbx; hKey
0x18000403e  call    cs:__imp_RegCloseKey
0x180004044  mov     rbx, [rsp+260h+hKey]
0x180004049  test    eax, eax
0x18000404b  jnz     short loc_1800040BA
0x18000404d  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180004052  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180004057  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000405c  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180004061  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180004066  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000406b  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180004070  lea     rax, [rsp+260h+cSubKeys]
0x180004075  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000407a  xor     r9d, r9d; lpReserved
0x18000407d  xor     r8d, r8d; lpcchClass
0x180004080  xor     edx, edx; lpClass
0x180004082  mov     rcx, rbx; hKey
0x180004085  call    cs:__imp_RegQueryInfoKeyW
0x18000408b  mov     esi, eax
0x18000408d  test    rbx, rbx
0x180004090  jz      short loc_18000409E
0x180004092  mov     rcx, rbx; hKey
0x180004095  call    cs:__imp_RegCloseKey
0x18000409b  mov     rbx, r15
0x18000409e  test    esi, esi
0x1800040a0  jnz     short loc_1800040C8
0x1800040a2  cmp     [rsp+260h+cSubKeys], r15d
0x1800040a7  jnz     short loc_1800040BA
0x1800040a9  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x1800040ad  lea     rcx, [rbp+160h+var_1E0]; this
0x1800040b1  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800040b6  mov     rdi, [rbp+160h+var_1E0]
0x1800040ba  test    rbx, rbx
0x1800040bd  jz      short loc_1800040C8
0x1800040bf  mov     rcx, rbx; hKey
0x1800040c2  call    cs:__imp_RegCloseKey
0x1800040c8  test    rdi, rdi
0x1800040cb  jz      short loc_1800040D7
0x1800040cd  mov     rcx, rdi; hKey
0x1800040d0  call    cs:__imp_RegCloseKey
0x1800040d6  nop
0x1800040d7  mov     rcx, [rsp+260h+var_1F8]
0x1800040dc  test    rcx, rcx
0x1800040df  jz      short loc_1800040EE
0x1800040e1  mov     rax, [rcx]
0x1800040e4  mov     rax, [rax+10h]
0x1800040e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040ed  nop
0x1800040ee  xor     eax, eax
0x1800040f0  mov     rcx, [rbp+160h+var_30]
0x1800040f7  xor     rcx, rsp; StackCookie
0x1800040fa  call    __security_check_cookie
0x1800040ff  lea     r11, [rsp+260h+var_20]
0x180004107  mov     rbx, [r11+40h]
0x18000410b  mov     rsi, [r11+48h]
0x18000410f  mov     rsp, r11
0x180004112  pop     r15
0x180004114  pop     r14
0x180004116  pop     r12
0x180004118  pop     rdi
0x180004119  pop     rbp
  ... truncated ...
```
