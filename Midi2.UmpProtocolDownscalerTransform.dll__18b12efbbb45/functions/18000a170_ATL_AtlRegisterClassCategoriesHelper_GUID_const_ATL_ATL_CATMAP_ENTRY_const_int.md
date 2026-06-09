# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18000a170`
- end: `0x18000a62b`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1211`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000af40`
- `0x18000b030`

## callees

- `0x180002e70`
- `0x1800059d8`
- `0x1800060f0`
- `0x18000a170`
- `0x180013010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000a31d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000a359`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000a48b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000a4c7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000a31d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000a359`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000a48b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000a4c7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000a2d9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000a44f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000a2d9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000a44f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000a2c1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000a2c1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a212`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a212`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a3c1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a514`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a3c1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a514`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a418`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a52d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a584`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a5b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a5bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a418`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a52d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a584`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a5b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a5bf`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a408`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a574`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a408`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a574`

## string_xrefs

- `0x18000a2c7`: `CLSID\`
- `0x18000a43d`: `CLSID\`

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
0x18000a170  mov     [rsp-8+arg_10], rbx
0x18000a175  mov     [rsp-8+arg_18], rsi
0x18000a17a  push    rbp
0x18000a17b  push    rdi
0x18000a17c  push    r12
0x18000a17e  push    r14
0x18000a180  push    r15
0x18000a182  lea     rbp, [rsp-140h]
0x18000a18a  sub     rsp, 240h
0x18000a191  mov     rax, cs:__security_cookie
0x18000a198  xor     rax, rsp
0x18000a19b  mov     [rbp+160h+var_30], rax
0x18000a1a2  mov     r14d, r8d
0x18000a1a5  mov     rdi, rdx
0x18000a1a8  mov     rbx, rcx
0x18000a1ab  xor     r15d, r15d
0x18000a1ae  mov     [rsp+260h+var_1F8], r15
0x18000a1b3  xorps   xmm0, xmm0
0x18000a1b6  movups  [rbp+160h+var_1C8], xmm0
0x18000a1ba  test    rdx, rdx
0x18000a1bd  jnz     short loc_18000A1C4
0x18000a1bf  jmp     loc_18000A5DD
0x18000a1c4  cmp     [rcx], r15d
0x18000a1c7  jnz     short loc_18000A1EF
0x18000a1c9  mov     eax, dword ptr cs:GUID_NULL.Data2
0x18000a1cf  cmp     [rcx+4], eax
0x18000a1d2  jnz     short loc_18000A1EF
0x18000a1d4  mov     eax, dword ptr cs:GUID_NULL.Data4
0x18000a1da  cmp     [rcx+8], eax
0x18000a1dd  jnz     short loc_18000A1EF
0x18000a1df  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x18000a1e5  cmp     [rcx+0Ch], eax
0x18000a1e8  jnz     short loc_18000A1EF
0x18000a1ea  jmp     loc_18000A5DD
0x18000a1ef  lea     rax, [rsp+260h+var_1F8]
0x18000a1f4  mov     [rsp+260h+ppv], rax; ppv
0x18000a1f9  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18000a200  mov     r12d, 1
0x18000a206  mov     r8d, r12d; dwClsContext
0x18000a209  xor     edx, edx; pUnkOuter
0x18000a20b  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18000a212  call    cs:__imp_CoCreateInstance
0x18000a218  test    eax, eax
0x18000a21a  jns     loc_18000A2A0
0x18000a220  jmp     loc_18000A5C6
0x18000a225  mov     rax, [rdi+8]
0x18000a229  movups  xmm0, xmmword ptr [rax]
0x18000a22c  movdqu  [rbp+160h+var_1C8], xmm0
0x18000a231  lea     r9, [rbp+160h+var_1C8]
0x18000a235  mov     r8d, r12d
0x18000a238  mov     rdx, rbx
0x18000a23b  test    r14d, r14d
0x18000a23e  jz      short loc_18000A280
0x18000a240  cmp     ecx, r12d
0x18000a243  mov     rcx, [rsp+260h+var_1F8]
0x18000a248  mov     rax, [rcx]
0x18000a24b  jnz     short loc_18000A253
0x18000a24d  mov     rax, [rax+28h]
0x18000a251  jmp     short loc_18000A257
0x18000a253  mov     rax, [rax+38h]
0x18000a257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a25c  mov     esi, eax
0x18000a25e  test    eax, eax
0x18000a260  jns     short loc_18000A29C
0x18000a262  mov     rcx, [rsp+260h+var_1F8]
0x18000a267  test    rcx, rcx
0x18000a26a  jz      short loc_18000A279
0x18000a26c  mov     rax, [rcx]
0x18000a26f  mov     rax, [rax+10h]
0x18000a273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a278  nop
0x18000a279  mov     eax, esi
0x18000a27b  jmp     loc_18000A5DF
0x18000a280  cmp     ecx, r12d
0x18000a283  mov     rcx, [rsp+260h+var_1F8]
0x18000a288  mov     rax, [rcx]
0x18000a28b  jnz     short loc_18000A293
0x18000a28d  mov     rax, [rax+30h]
0x18000a291  jmp     short loc_18000A297
0x18000a293  mov     rax, [rax+40h]
0x18000a297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a29c  add     rdi, 10h
0x18000a2a0  mov     ecx, [rdi]
0x18000a2a2  test    ecx, ecx
0x18000a2a4  jnz     loc_18000A225
0x18000a2aa  test    r14d, r14d
0x18000a2ad  jnz     loc_18000A5C6
0x18000a2b3  lea     r8d, [rcx+40h]; cchMax
0x18000a2b7  lea     rdx, [rbp+160h+sz]; lpsz
0x18000a2be  mov     rcx, rbx; rguid
0x18000a2c1  call    cs:__imp_StringFromGUID2
0x18000a2c7  lea     r8, aClsid; "CLSID\\"
0x18000a2ce  mov     ebx, 80h
0x18000a2d3  mov     edx, ebx
0x18000a2d5  lea     rcx, [rbp+160h+SubKey]
0x18000a2d9  call    cs:__imp__o_wcscpy_s
0x18000a2df  lea     r14d, [rbx-74h]
0x18000a2e3  lea     r12d, [rbx-30h]
0x18000a2e7  test    eax, eax
0x18000a2e9  jz      short loc_18000A30F
0x18000a2eb  cmp     eax, r14d
0x18000a2ee  jz      loc_18000A60A
0x18000a2f4  cmp     eax, 16h
0x18000a2f7  jz      loc_18000A620
0x18000a2fd  cmp     eax, 22h ; '"'
0x18000a300  jz      loc_18000A620
0x18000a306  cmp     eax, r12d
0x18000a309  jnz     loc_18000A615
0x18000a30f  lea     r8, [rbp+160h+sz]
0x18000a316  mov     rdx, rbx
0x18000a319  lea     rcx, [rbp+160h+SubKey]
0x18000a31d  call    cs:__imp__o_wcscat_s
0x18000a323  test    eax, eax
0x18000a325  jz      short loc_18000A34B
0x18000a327  cmp     eax, r14d
0x18000a32a  jz      loc_18000A60A
0x18000a330  cmp     eax, 16h
0x18000a333  jz      loc_18000A620
0x18000a339  cmp     eax, 22h ; '"'
0x18000a33c  jz      loc_18000A620
0x18000a342  cmp     eax, r12d
0x18000a345  jnz     loc_18000A615
0x18000a34b  lea     r8, aRequiredCatego; "\\Required Categories"
0x18000a352  mov     rdx, rbx
0x18000a355  lea     rcx, [rbp+160h+SubKey]
0x18000a359  call    cs:__imp__o_wcscat_s
0x18000a35f  test    eax, eax
0x18000a361  jz      short loc_18000A387
0x18000a363  cmp     eax, r14d
0x18000a366  jz      loc_18000A60A
0x18000a36c  cmp     eax, 16h
0x18000a36f  jz      loc_18000A620
0x18000a375  cmp     eax, 22h ; '"'
0x18000a378  jz      loc_18000A620
0x18000a37e  cmp     eax, r12d
0x18000a381  jnz     loc_18000A615
0x18000a387  mov     rdi, 0FFFFFFFF80000000h
0x18000a38e  mov     [rbp+160h+var_1E0], rdi
0x18000a392  mov     [rbp+160h+var_1D8], r15
0x18000a396  mov     [rbp+160h+var_1D0], r15
0x18000a39a  mov     rbx, r15
0x18000a39d  mov     [rsp+260h+cSubKeys], r15d
0x18000a3a2  mov     [rsp+260h+phkResult], r15
0x18000a3a7  lea     rax, [rsp+260h+phkResult]
0x18000a3ac  mov     [rsp+260h+ppv], rax; phkResult
0x18000a3b1  mov     r9d, 20019h; samDesired
0x18000a3b7  xor     r8d, r8d; ulOptions
0x18000a3ba  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x18000a3be  mov     rcx, rdi; hKey
0x18000a3c1  call    cs:__imp_RegOpenKeyExW
0x18000a3c7  test    eax, eax
0x18000a3c9  jnz     short loc_18000A43D
0x18000a3cb  mov     rbx, [rsp+260h+phkResult]
0x18000a3d0  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000a3d5  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000a3da  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000a3df  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000a3e4  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18000a3e9  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000a3ee  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000a3f3  lea     rax, [rsp+260h+cSubKeys]
0x18000a3f8  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000a3fd  xor     r9d, r9d; lpReserved
0x18000a400  xor     r8d, r8d; lpcchClass
0x18000a403  xor     edx, edx; lpClass
0x18000a405  mov     rcx, rbx; hKey
0x18000a408  call    cs:__imp_RegQueryInfoKeyW
0x18000a40e  mov     esi, eax
0x18000a410  test    rbx, rbx
0x18000a413  jz      short loc_18000A421
0x18000a415  mov     rcx, rbx; hKey
0x18000a418  call    cs:__imp_RegCloseKey
0x18000a41e  mov     rbx, r15
0x18000a421  test    esi, esi
0x18000a423  jnz     short loc_18000A43D
0x18000a425  cmp     [rsp+260h+cSubKeys], r15d
0x18000a42a  jnz     short loc_18000A43D
0x18000a42c  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x18000a430  lea     rcx, [rbp+160h+var_1E0]; this
0x18000a434  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000a439  mov     rdi, [rbp+160h+var_1E0]
0x18000a43d  lea     r8, aClsid; "CLSID\\"
0x18000a444  mov     esi, 80h
0x18000a449  mov     edx, esi
0x18000a44b  lea     rcx, [rbp+160h+SubKey]
0x18000a44f  call    cs:__imp__o_wcscpy_s
0x18000a455  test    eax, eax
0x18000a457  jz      short loc_18000A47D
0x18000a459  cmp     eax, r14d
0x18000a45c  jz      loc_18000A60A
0x18000a462  cmp     eax, 16h
0x18000a465  jz      loc_18000A620
0x18000a46b  cmp     eax, 22h ; '"'
0x18000a46e  jz      loc_18000A620
0x18000a474  cmp     eax, r12d
0x18000a477  jnz     loc_18000A615
0x18000a47d  lea     r8, [rbp+160h+sz]
0x18000a484  mov     rdx, rsi
0x18000a487  lea     rcx, [rbp+160h+SubKey]
0x18000a48b  call    cs:__imp__o_wcscat_s
0x18000a491  test    eax, eax
0x18000a493  jz      short loc_18000A4B9
0x18000a495  cmp     eax, r14d
0x18000a498  jz      loc_18000A60A
0x18000a49e  cmp     eax, 16h
0x18000a4a1  jz      loc_18000A620
0x18000a4a7  cmp     eax, 22h ; '"'
0x18000a4aa  jz      loc_18000A620
0x18000a4b0  cmp     eax, r12d
0x18000a4b3  jnz     loc_18000A615
0x18000a4b9  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18000a4c0  mov     rdx, rsi
0x18000a4c3  lea     rcx, [rbp+160h+SubKey]
0x18000a4c7  call    cs:__imp__o_wcscat_s
0x18000a4cd  test    eax, eax
0x18000a4cf  jz      short loc_18000A4F5
0x18000a4d1  cmp     eax, r14d
0x18000a4d4  jz      loc_18000A60A
0x18000a4da  cmp     eax, 16h
0x18000a4dd  jz      loc_18000A620
0x18000a4e3  cmp     eax, 22h ; '"'
0x18000a4e6  jz      loc_18000A620
0x18000a4ec  cmp     eax, r12d
0x18000a4ef  jnz     loc_18000A615
0x18000a4f5  mov     [rsp+260h+hKey], r15
0x18000a4fa  lea     rax, [rsp+260h+hKey]
0x18000a4ff  mov     [rsp+260h+ppv], rax; phkResult
0x18000a504  mov     r9d, 20019h; samDesired
0x18000a50a  xor     r8d, r8d; ulOptions
0x18000a50d  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x18000a511  mov     rcx, rdi; hKey
0x18000a514  call    cs:__imp_RegOpenKeyExW
0x18000a51a  test    eax, eax
0x18000a51c  jnz     loc_18000A5A9
0x18000a522  mov     eax, r15d
0x18000a525  test    rbx, rbx
0x18000a528  jz      short loc_18000A533
0x18000a52a  mov     rcx, rbx; hKey
0x18000a52d  call    cs:__imp_RegCloseKey
0x18000a533  mov     rbx, [rsp+260h+hKey]
0x18000a538  test    eax, eax
0x18000a53a  jnz     short loc_18000A5A9
0x18000a53c  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000a541  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000a546  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000a54b  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000a550  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18000a555  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000a55a  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000a55f  lea     rax, [rsp+260h+cSubKeys]
0x18000a564  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000a569  xor     r9d, r9d; lpReserved
0x18000a56c  xor     r8d, r8d; lpcchClass
0x18000a56f  xor     edx, edx; lpClass
0x18000a571  mov     rcx, rbx; hKey
0x18000a574  call    cs:__imp_RegQueryInfoKeyW
0x18000a57a  mov     esi, eax
0x18000a57c  test    rbx, rbx
0x18000a57f  jz      short loc_18000A58D
0x18000a581  mov     rcx, rbx; hKey
0x18000a584  call    cs:__imp_RegCloseKey
0x18000a58a  mov     rbx, r15
0x18000a58d  test    esi, esi
0x18000a58f  jnz     short loc_18000A5B7
0x18000a591  cmp     [rsp+260h+cSubKeys], r15d
0x18000a596  jnz     short loc_18000A5A9
0x18000a598  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x18000a59c  lea     rcx, [rbp+160h+var_1E0]; this
0x18000a5a0  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000a5a5  mov     rdi, [rbp+160h+var_1E0]
0x18000a5a9  test    rbx, rbx
0x18000a5ac  jz      short loc_18000A5B7
0x18000a5ae  mov     rcx, rbx; hKey
0x18000a5b1  call    cs:__imp_RegCloseKey
0x18000a5b7  test    rdi, rdi
0x18000a5ba  jz      short loc_18000A5C6
0x18000a5bc  mov     rcx, rdi; hKey
0x18000a5bf  call    cs:__imp_RegCloseKey
0x18000a5c5  nop
0x18000a5c6  mov     rcx, [rsp+260h+var_1F8]
0x18000a5cb  test    rcx, rcx
0x18000a5ce  jz      short loc_18000A5DD
0x18000a5d0  mov     rax, [rcx]
0x18000a5d3  mov     rax, [rax+10h]
0x18000a5d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5dc  nop
0x18000a5dd  xor     eax, eax
0x18000a5df  mov     rcx, [rbp+160h+var_30]
0x18000a5e6  xor     rcx, rsp; StackCookie
0x18000a5e9  call    __security_check_cookie
0x18000a5ee  lea     r11, [rsp+260h+var_20]
0x18000a5f6  mov     rbx, [r11+40h]
0x18000a5fa  mov     rsi, [r11+48h]
0x18000a5fe  mov     rsp, r11
0x18000a601  pop     r15
0x18000a603  pop     r14
0x18000a605  pop     r12
0x18000a607  pop     rdi
0x18000a608  pop     rbp
0x18000a609  retn
  ... truncated ...
```
