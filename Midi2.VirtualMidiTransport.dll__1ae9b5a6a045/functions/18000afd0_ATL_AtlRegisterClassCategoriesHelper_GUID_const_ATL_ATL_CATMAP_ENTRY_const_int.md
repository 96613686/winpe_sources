# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18000afd0`
- end: `0x18000b48b`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1211`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000bda0`
- `0x18000be90`

## callees

- `0x1800038f0`
- `0x1800066a8`
- `0x180006dc0`
- `0x18000afd0`
- `0x180021010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000b17d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000b1b9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000b2eb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000b327`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000b17d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000b1b9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000b2eb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000b327`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000b139`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000b2af`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000b139`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000b2af`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b072`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b072`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000b121`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000b121`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b278`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b38d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b3e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b411`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b41f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b278`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b38d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b3e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b411`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b41f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b221`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b374`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b221`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b374`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000b268`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000b3d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000b268`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000b3d4`

## string_xrefs

- `0x18000b127`: `CLSID\`
- `0x18000b29d`: `CLSID\`

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
  int v12; // eax
  int v13; // eax
  int v14; // eax
  HKEY v15; // rdi
  HKEY v16; // rbx
  LSTATUS v17; // esi
  int v18; // eax
  int v19; // eax
  int v20; // eax
  HKEY v21; // rbx
  LSTATUS v22; // esi
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v27[3]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v28; // [rsp+98h] [rbp-68h] BYREF
  WCHAR SubKey[128]; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR sz[64]; // [rsp+1B0h] [rbp+B0h] BYREF

  v4 = a2;
  ppv = 0;
  v28 = 0;
  if ( !a2
    || !rguid->Data1
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
      cSubKeys = 0;
      phkResult = 0;
      if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &phkResult) )
      {
        v16 = phkResult;
        v17 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        if ( v16 )
          RegCloseKey(v16);
        if ( !v17 && !cSubKeys )
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
          v22 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
          if ( v21 )
            RegCloseKey(v21);
          if ( !v22 && !cSubKeys )
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
0x18000afd0  mov     [rsp-8+arg_10], rbx
0x18000afd5  mov     [rsp-8+arg_18], rsi
0x18000afda  push    rbp
0x18000afdb  push    rdi
0x18000afdc  push    r12
0x18000afde  push    r14
0x18000afe0  push    r15
0x18000afe2  lea     rbp, [rsp-140h]
0x18000afea  sub     rsp, 240h
0x18000aff1  mov     rax, cs:__security_cookie
0x18000aff8  xor     rax, rsp
0x18000affb  mov     [rbp+160h+var_30], rax
0x18000b002  mov     r14d, r8d
0x18000b005  mov     rdi, rdx
0x18000b008  mov     rbx, rcx
0x18000b00b  xor     r15d, r15d
0x18000b00e  mov     [rsp+260h+var_1F8], r15
0x18000b013  xorps   xmm0, xmm0
0x18000b016  movups  [rbp+160h+var_1C8], xmm0
0x18000b01a  test    rdx, rdx
0x18000b01d  jnz     short loc_18000B024
0x18000b01f  jmp     loc_18000B43D
0x18000b024  cmp     [rcx], r15d
0x18000b027  jnz     short loc_18000B04F
0x18000b029  mov     eax, dword ptr cs:GUID_NULL.Data2
0x18000b02f  cmp     [rcx+4], eax
0x18000b032  jnz     short loc_18000B04F
0x18000b034  mov     eax, dword ptr cs:GUID_NULL.Data4
0x18000b03a  cmp     [rcx+8], eax
0x18000b03d  jnz     short loc_18000B04F
0x18000b03f  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x18000b045  cmp     [rcx+0Ch], eax
0x18000b048  jnz     short loc_18000B04F
0x18000b04a  jmp     loc_18000B43D
0x18000b04f  lea     rax, [rsp+260h+var_1F8]
0x18000b054  mov     [rsp+260h+ppv], rax; ppv
0x18000b059  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18000b060  mov     r12d, 1
0x18000b066  mov     r8d, r12d; dwClsContext
0x18000b069  xor     edx, edx; pUnkOuter
0x18000b06b  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18000b072  call    cs:__imp_CoCreateInstance
0x18000b078  test    eax, eax
0x18000b07a  jns     loc_18000B100
0x18000b080  jmp     loc_18000B426
0x18000b085  mov     rax, [rdi+8]
0x18000b089  movups  xmm0, xmmword ptr [rax]
0x18000b08c  movdqu  [rbp+160h+var_1C8], xmm0
0x18000b091  lea     r9, [rbp+160h+var_1C8]
0x18000b095  mov     r8d, r12d
0x18000b098  mov     rdx, rbx
0x18000b09b  test    r14d, r14d
0x18000b09e  jz      short loc_18000B0E0
0x18000b0a0  cmp     ecx, r12d
0x18000b0a3  mov     rcx, [rsp+260h+var_1F8]
0x18000b0a8  mov     rax, [rcx]
0x18000b0ab  jnz     short loc_18000B0B3
0x18000b0ad  mov     rax, [rax+28h]
0x18000b0b1  jmp     short loc_18000B0B7
0x18000b0b3  mov     rax, [rax+38h]
0x18000b0b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0bc  mov     esi, eax
0x18000b0be  test    eax, eax
0x18000b0c0  jns     short loc_18000B0FC
0x18000b0c2  mov     rcx, [rsp+260h+var_1F8]
0x18000b0c7  test    rcx, rcx
0x18000b0ca  jz      short loc_18000B0D9
0x18000b0cc  mov     rax, [rcx]
0x18000b0cf  mov     rax, [rax+10h]
0x18000b0d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0d8  nop
0x18000b0d9  mov     eax, esi
0x18000b0db  jmp     loc_18000B43F
0x18000b0e0  cmp     ecx, r12d
0x18000b0e3  mov     rcx, [rsp+260h+var_1F8]
0x18000b0e8  mov     rax, [rcx]
0x18000b0eb  jnz     short loc_18000B0F3
0x18000b0ed  mov     rax, [rax+30h]
0x18000b0f1  jmp     short loc_18000B0F7
0x18000b0f3  mov     rax, [rax+40h]
0x18000b0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0fc  add     rdi, 10h
0x18000b100  mov     ecx, [rdi]
0x18000b102  test    ecx, ecx
0x18000b104  jnz     loc_18000B085
0x18000b10a  test    r14d, r14d
0x18000b10d  jnz     loc_18000B426
0x18000b113  lea     r8d, [rcx+40h]; cchMax
0x18000b117  lea     rdx, [rbp+160h+sz]; lpsz
0x18000b11e  mov     rcx, rbx; rguid
0x18000b121  call    cs:__imp_StringFromGUID2
0x18000b127  lea     r8, aClsid; "CLSID\\"
0x18000b12e  mov     ebx, 80h
0x18000b133  mov     edx, ebx
0x18000b135  lea     rcx, [rbp+160h+SubKey]
0x18000b139  call    cs:__imp__o_wcscpy_s
0x18000b13f  lea     r14d, [rbx-74h]
0x18000b143  lea     r12d, [rbx-30h]
0x18000b147  test    eax, eax
0x18000b149  jz      short loc_18000B16F
0x18000b14b  cmp     eax, r14d
0x18000b14e  jz      loc_18000B46A
0x18000b154  cmp     eax, 16h
0x18000b157  jz      loc_18000B480
0x18000b15d  cmp     eax, 22h ; '"'
0x18000b160  jz      loc_18000B480
0x18000b166  cmp     eax, r12d
0x18000b169  jnz     loc_18000B475
0x18000b16f  lea     r8, [rbp+160h+sz]
0x18000b176  mov     rdx, rbx
0x18000b179  lea     rcx, [rbp+160h+SubKey]
0x18000b17d  call    cs:__imp__o_wcscat_s
0x18000b183  test    eax, eax
0x18000b185  jz      short loc_18000B1AB
0x18000b187  cmp     eax, r14d
0x18000b18a  jz      loc_18000B46A
0x18000b190  cmp     eax, 16h
0x18000b193  jz      loc_18000B480
0x18000b199  cmp     eax, 22h ; '"'
0x18000b19c  jz      loc_18000B480
0x18000b1a2  cmp     eax, r12d
0x18000b1a5  jnz     loc_18000B475
0x18000b1ab  lea     r8, aRequiredCatego; "\\Required Categories"
0x18000b1b2  mov     rdx, rbx
0x18000b1b5  lea     rcx, [rbp+160h+SubKey]
0x18000b1b9  call    cs:__imp__o_wcscat_s
0x18000b1bf  test    eax, eax
0x18000b1c1  jz      short loc_18000B1E7
0x18000b1c3  cmp     eax, r14d
0x18000b1c6  jz      loc_18000B46A
0x18000b1cc  cmp     eax, 16h
0x18000b1cf  jz      loc_18000B480
0x18000b1d5  cmp     eax, 22h ; '"'
0x18000b1d8  jz      loc_18000B480
0x18000b1de  cmp     eax, r12d
0x18000b1e1  jnz     loc_18000B475
0x18000b1e7  mov     rdi, 0FFFFFFFF80000000h
0x18000b1ee  mov     [rbp+160h+var_1E0], rdi
0x18000b1f2  mov     [rbp+160h+var_1D8], r15
0x18000b1f6  mov     [rbp+160h+var_1D0], r15
0x18000b1fa  mov     rbx, r15
0x18000b1fd  mov     [rsp+260h+cSubKeys], r15d
0x18000b202  mov     [rsp+260h+phkResult], r15
0x18000b207  lea     rax, [rsp+260h+phkResult]
0x18000b20c  mov     [rsp+260h+ppv], rax; phkResult
0x18000b211  mov     r9d, 20019h; samDesired
0x18000b217  xor     r8d, r8d; ulOptions
0x18000b21a  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x18000b21e  mov     rcx, rdi; hKey
0x18000b221  call    cs:__imp_RegOpenKeyExW
0x18000b227  test    eax, eax
0x18000b229  jnz     short loc_18000B29D
0x18000b22b  mov     rbx, [rsp+260h+phkResult]
0x18000b230  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000b235  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000b23a  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000b23f  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000b244  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18000b249  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000b24e  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000b253  lea     rax, [rsp+260h+cSubKeys]
0x18000b258  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000b25d  xor     r9d, r9d; lpReserved
0x18000b260  xor     r8d, r8d; lpcchClass
0x18000b263  xor     edx, edx; lpClass
0x18000b265  mov     rcx, rbx; hKey
0x18000b268  call    cs:__imp_RegQueryInfoKeyW
0x18000b26e  mov     esi, eax
0x18000b270  test    rbx, rbx
0x18000b273  jz      short loc_18000B281
0x18000b275  mov     rcx, rbx; hKey
0x18000b278  call    cs:__imp_RegCloseKey
0x18000b27e  mov     rbx, r15
0x18000b281  test    esi, esi
0x18000b283  jnz     short loc_18000B29D
0x18000b285  cmp     [rsp+260h+cSubKeys], r15d
0x18000b28a  jnz     short loc_18000B29D
0x18000b28c  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x18000b290  lea     rcx, [rbp+160h+var_1E0]; this
0x18000b294  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000b299  mov     rdi, [rbp+160h+var_1E0]
0x18000b29d  lea     r8, aClsid; "CLSID\\"
0x18000b2a4  mov     esi, 80h
0x18000b2a9  mov     edx, esi
0x18000b2ab  lea     rcx, [rbp+160h+SubKey]
0x18000b2af  call    cs:__imp__o_wcscpy_s
0x18000b2b5  test    eax, eax
0x18000b2b7  jz      short loc_18000B2DD
0x18000b2b9  cmp     eax, r14d
0x18000b2bc  jz      loc_18000B46A
0x18000b2c2  cmp     eax, 16h
0x18000b2c5  jz      loc_18000B480
0x18000b2cb  cmp     eax, 22h ; '"'
0x18000b2ce  jz      loc_18000B480
0x18000b2d4  cmp     eax, r12d
0x18000b2d7  jnz     loc_18000B475
0x18000b2dd  lea     r8, [rbp+160h+sz]
0x18000b2e4  mov     rdx, rsi
0x18000b2e7  lea     rcx, [rbp+160h+SubKey]
0x18000b2eb  call    cs:__imp__o_wcscat_s
0x18000b2f1  test    eax, eax
0x18000b2f3  jz      short loc_18000B319
0x18000b2f5  cmp     eax, r14d
0x18000b2f8  jz      loc_18000B46A
0x18000b2fe  cmp     eax, 16h
0x18000b301  jz      loc_18000B480
0x18000b307  cmp     eax, 22h ; '"'
0x18000b30a  jz      loc_18000B480
0x18000b310  cmp     eax, r12d
0x18000b313  jnz     loc_18000B475
0x18000b319  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18000b320  mov     rdx, rsi
0x18000b323  lea     rcx, [rbp+160h+SubKey]
0x18000b327  call    cs:__imp__o_wcscat_s
0x18000b32d  test    eax, eax
0x18000b32f  jz      short loc_18000B355
0x18000b331  cmp     eax, r14d
0x18000b334  jz      loc_18000B46A
0x18000b33a  cmp     eax, 16h
0x18000b33d  jz      loc_18000B480
0x18000b343  cmp     eax, 22h ; '"'
0x18000b346  jz      loc_18000B480
0x18000b34c  cmp     eax, r12d
0x18000b34f  jnz     loc_18000B475
0x18000b355  mov     [rsp+260h+hKey], r15
0x18000b35a  lea     rax, [rsp+260h+hKey]
0x18000b35f  mov     [rsp+260h+ppv], rax; phkResult
0x18000b364  mov     r9d, 20019h; samDesired
0x18000b36a  xor     r8d, r8d; ulOptions
0x18000b36d  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x18000b371  mov     rcx, rdi; hKey
0x18000b374  call    cs:__imp_RegOpenKeyExW
0x18000b37a  test    eax, eax
0x18000b37c  jnz     loc_18000B409
0x18000b382  mov     eax, r15d
0x18000b385  test    rbx, rbx
0x18000b388  jz      short loc_18000B393
0x18000b38a  mov     rcx, rbx; hKey
0x18000b38d  call    cs:__imp_RegCloseKey
0x18000b393  mov     rbx, [rsp+260h+hKey]
0x18000b398  test    eax, eax
0x18000b39a  jnz     short loc_18000B409
0x18000b39c  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000b3a1  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000b3a6  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000b3ab  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000b3b0  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18000b3b5  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000b3ba  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000b3bf  lea     rax, [rsp+260h+cSubKeys]
0x18000b3c4  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000b3c9  xor     r9d, r9d; lpReserved
0x18000b3cc  xor     r8d, r8d; lpcchClass
0x18000b3cf  xor     edx, edx; lpClass
0x18000b3d1  mov     rcx, rbx; hKey
0x18000b3d4  call    cs:__imp_RegQueryInfoKeyW
0x18000b3da  mov     esi, eax
0x18000b3dc  test    rbx, rbx
0x18000b3df  jz      short loc_18000B3ED
0x18000b3e1  mov     rcx, rbx; hKey
0x18000b3e4  call    cs:__imp_RegCloseKey
0x18000b3ea  mov     rbx, r15
0x18000b3ed  test    esi, esi
0x18000b3ef  jnz     short loc_18000B417
0x18000b3f1  cmp     [rsp+260h+cSubKeys], r15d
0x18000b3f6  jnz     short loc_18000B409
0x18000b3f8  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x18000b3fc  lea     rcx, [rbp+160h+var_1E0]; this
0x18000b400  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000b405  mov     rdi, [rbp+160h+var_1E0]
0x18000b409  test    rbx, rbx
0x18000b40c  jz      short loc_18000B417
0x18000b40e  mov     rcx, rbx; hKey
0x18000b411  call    cs:__imp_RegCloseKey
0x18000b417  test    rdi, rdi
0x18000b41a  jz      short loc_18000B426
0x18000b41c  mov     rcx, rdi; hKey
0x18000b41f  call    cs:__imp_RegCloseKey
0x18000b425  nop
0x18000b426  mov     rcx, [rsp+260h+var_1F8]
0x18000b42b  test    rcx, rcx
0x18000b42e  jz      short loc_18000B43D
0x18000b430  mov     rax, [rcx]
0x18000b433  mov     rax, [rax+10h]
0x18000b437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b43c  nop
0x18000b43d  xor     eax, eax
0x18000b43f  mov     rcx, [rbp+160h+var_30]
0x18000b446  xor     rcx, rsp; StackCookie
0x18000b449  call    __security_check_cookie
0x18000b44e  lea     r11, [rsp+260h+var_20]
0x18000b456  mov     rbx, [r11+40h]
0x18000b45a  mov     rsi, [r11+48h]
0x18000b45e  mov     rsp, r11
0x18000b461  pop     r15
0x18000b463  pop     r14
0x18000b465  pop     r12
0x18000b467  pop     rdi
0x18000b468  pop     rbp
0x18000b469  retn
  ... truncated ...
```
