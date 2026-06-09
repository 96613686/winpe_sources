# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18000d4f0`
- end: `0x18000d9ab`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1211`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000e390`
- `0x18000e480`

## callees

- `0x180004410`
- `0x180007538`
- `0x180007c50`
- `0x18000d4f0`
- `0x180041010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000d69d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000d6d9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000d80b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000d847`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000d69d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000d6d9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000d80b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000d847`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000d659`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000d7cf`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000d659`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000d7cf`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000d641`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000d641`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d592`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d592`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000d788`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000d8f4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000d788`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000d8f4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d741`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d894`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d741`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000d894`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d798`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d8ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d904`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d931`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d93f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d798`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d8ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d904`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d931`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d93f`

## string_xrefs

- `0x18000d647`: `CLSID\`
- `0x18000d7bd`: `CLSID\`

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
    && *(_DWORD *)&rguid->Data2 == *(_DWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data2
    && *(_DWORD *)rguid->Data4 == *(_DWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4
    && *(_DWORD *)&rguid->Data4[4] == *(_DWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data4[4] )
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
0x18000d4f0  mov     [rsp-8+arg_10], rbx
0x18000d4f5  mov     [rsp-8+arg_18], rsi
0x18000d4fa  push    rbp
0x18000d4fb  push    rdi
0x18000d4fc  push    r12
0x18000d4fe  push    r14
0x18000d500  push    r15
0x18000d502  lea     rbp, [rsp-140h]
0x18000d50a  sub     rsp, 240h
0x18000d511  mov     rax, cs:__security_cookie
0x18000d518  xor     rax, rsp
0x18000d51b  mov     [rbp+160h+var_30], rax
0x18000d522  mov     r14d, r8d
0x18000d525  mov     rdi, rdx
0x18000d528  mov     rbx, rcx
0x18000d52b  xor     r15d, r15d
0x18000d52e  mov     [rsp+260h+var_1F8], r15
0x18000d533  xorps   xmm0, xmm0
0x18000d536  movups  [rbp+160h+var_1C8], xmm0
0x18000d53a  test    rdx, rdx
0x18000d53d  jnz     short loc_18000D544
0x18000d53f  jmp     loc_18000D95D
0x18000d544  cmp     [rcx], r15d
0x18000d547  jnz     short loc_18000D56F
0x18000d549  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data2
0x18000d54f  cmp     [rcx+4], eax
0x18000d552  jnz     short loc_18000D56F
0x18000d554  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x18000d55a  cmp     [rcx+8], eax
0x18000d55d  jnz     short loc_18000D56F
0x18000d55f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4+4
0x18000d565  cmp     [rcx+0Ch], eax
0x18000d568  jnz     short loc_18000D56F
0x18000d56a  jmp     loc_18000D95D
0x18000d56f  lea     rax, [rsp+260h+var_1F8]
0x18000d574  mov     [rsp+260h+ppv], rax; ppv
0x18000d579  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18000d580  mov     r12d, 1
0x18000d586  mov     r8d, r12d; dwClsContext
0x18000d589  xor     edx, edx; pUnkOuter
0x18000d58b  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18000d592  call    cs:__imp_CoCreateInstance
0x18000d598  test    eax, eax
0x18000d59a  jns     loc_18000D620
0x18000d5a0  jmp     loc_18000D946
0x18000d5a5  mov     rax, [rdi+8]
0x18000d5a9  movups  xmm0, xmmword ptr [rax]
0x18000d5ac  movdqu  [rbp+160h+var_1C8], xmm0
0x18000d5b1  lea     r9, [rbp+160h+var_1C8]
0x18000d5b5  mov     r8d, r12d
0x18000d5b8  mov     rdx, rbx
0x18000d5bb  test    r14d, r14d
0x18000d5be  jz      short loc_18000D600
0x18000d5c0  cmp     ecx, r12d
0x18000d5c3  mov     rcx, [rsp+260h+var_1F8]
0x18000d5c8  mov     rax, [rcx]
0x18000d5cb  jnz     short loc_18000D5D3
0x18000d5cd  mov     rax, [rax+28h]
0x18000d5d1  jmp     short loc_18000D5D7
0x18000d5d3  mov     rax, [rax+38h]
0x18000d5d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5dc  mov     esi, eax
0x18000d5de  test    eax, eax
0x18000d5e0  jns     short loc_18000D61C
0x18000d5e2  mov     rcx, [rsp+260h+var_1F8]
0x18000d5e7  test    rcx, rcx
0x18000d5ea  jz      short loc_18000D5F9
0x18000d5ec  mov     rax, [rcx]
0x18000d5ef  mov     rax, [rax+10h]
0x18000d5f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5f8  nop
0x18000d5f9  mov     eax, esi
0x18000d5fb  jmp     loc_18000D95F
0x18000d600  cmp     ecx, r12d
0x18000d603  mov     rcx, [rsp+260h+var_1F8]
0x18000d608  mov     rax, [rcx]
0x18000d60b  jnz     short loc_18000D613
0x18000d60d  mov     rax, [rax+30h]
0x18000d611  jmp     short loc_18000D617
0x18000d613  mov     rax, [rax+40h]
0x18000d617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d61c  add     rdi, 10h
0x18000d620  mov     ecx, [rdi]
0x18000d622  test    ecx, ecx
0x18000d624  jnz     loc_18000D5A5
0x18000d62a  test    r14d, r14d
0x18000d62d  jnz     loc_18000D946
0x18000d633  lea     r8d, [rcx+40h]; cchMax
0x18000d637  lea     rdx, [rbp+160h+sz]; lpsz
0x18000d63e  mov     rcx, rbx; rguid
0x18000d641  call    cs:__imp_StringFromGUID2
0x18000d647  lea     r8, aClsid; "CLSID\\"
0x18000d64e  mov     ebx, 80h
0x18000d653  mov     edx, ebx
0x18000d655  lea     rcx, [rbp+160h+SubKey]
0x18000d659  call    cs:__imp__o_wcscpy_s
0x18000d65f  lea     r14d, [rbx-74h]
0x18000d663  lea     r12d, [rbx-30h]
0x18000d667  test    eax, eax
0x18000d669  jz      short loc_18000D68F
0x18000d66b  cmp     eax, r14d
0x18000d66e  jz      loc_18000D98A
0x18000d674  cmp     eax, 16h
0x18000d677  jz      loc_18000D9A0
0x18000d67d  cmp     eax, 22h ; '"'
0x18000d680  jz      loc_18000D9A0
0x18000d686  cmp     eax, r12d
0x18000d689  jnz     loc_18000D995
0x18000d68f  lea     r8, [rbp+160h+sz]
0x18000d696  mov     rdx, rbx
0x18000d699  lea     rcx, [rbp+160h+SubKey]
0x18000d69d  call    cs:__imp__o_wcscat_s
0x18000d6a3  test    eax, eax
0x18000d6a5  jz      short loc_18000D6CB
0x18000d6a7  cmp     eax, r14d
0x18000d6aa  jz      loc_18000D98A
0x18000d6b0  cmp     eax, 16h
0x18000d6b3  jz      loc_18000D9A0
0x18000d6b9  cmp     eax, 22h ; '"'
0x18000d6bc  jz      loc_18000D9A0
0x18000d6c2  cmp     eax, r12d
0x18000d6c5  jnz     loc_18000D995
0x18000d6cb  lea     r8, aRequiredCatego; "\\Required Categories"
0x18000d6d2  mov     rdx, rbx
0x18000d6d5  lea     rcx, [rbp+160h+SubKey]
0x18000d6d9  call    cs:__imp__o_wcscat_s
0x18000d6df  test    eax, eax
0x18000d6e1  jz      short loc_18000D707
0x18000d6e3  cmp     eax, r14d
0x18000d6e6  jz      loc_18000D98A
0x18000d6ec  cmp     eax, 16h
0x18000d6ef  jz      loc_18000D9A0
0x18000d6f5  cmp     eax, 22h ; '"'
0x18000d6f8  jz      loc_18000D9A0
0x18000d6fe  cmp     eax, r12d
0x18000d701  jnz     loc_18000D995
0x18000d707  mov     rdi, 0FFFFFFFF80000000h
0x18000d70e  mov     [rbp+160h+var_1E0], rdi
0x18000d712  mov     [rbp+160h+var_1D8], r15
0x18000d716  mov     [rbp+160h+var_1D0], r15
0x18000d71a  mov     rbx, r15
0x18000d71d  mov     [rsp+260h+cSubKeys], r15d
0x18000d722  mov     [rsp+260h+phkResult], r15
0x18000d727  lea     rax, [rsp+260h+phkResult]
0x18000d72c  mov     [rsp+260h+ppv], rax; phkResult
0x18000d731  mov     r9d, 20019h; samDesired
0x18000d737  xor     r8d, r8d; ulOptions
0x18000d73a  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x18000d73e  mov     rcx, rdi; hKey
0x18000d741  call    cs:__imp_RegOpenKeyExW
0x18000d747  test    eax, eax
0x18000d749  jnz     short loc_18000D7BD
0x18000d74b  mov     rbx, [rsp+260h+phkResult]
0x18000d750  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000d755  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000d75a  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000d75f  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000d764  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18000d769  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000d76e  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000d773  lea     rax, [rsp+260h+cSubKeys]
0x18000d778  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000d77d  xor     r9d, r9d; lpReserved
0x18000d780  xor     r8d, r8d; lpcchClass
0x18000d783  xor     edx, edx; lpClass
0x18000d785  mov     rcx, rbx; hKey
0x18000d788  call    cs:__imp_RegQueryInfoKeyW
0x18000d78e  mov     esi, eax
0x18000d790  test    rbx, rbx
0x18000d793  jz      short loc_18000D7A1
0x18000d795  mov     rcx, rbx; hKey
0x18000d798  call    cs:__imp_RegCloseKey
0x18000d79e  mov     rbx, r15
0x18000d7a1  test    esi, esi
0x18000d7a3  jnz     short loc_18000D7BD
0x18000d7a5  cmp     [rsp+260h+cSubKeys], r15d
0x18000d7aa  jnz     short loc_18000D7BD
0x18000d7ac  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x18000d7b0  lea     rcx, [rbp+160h+var_1E0]; this
0x18000d7b4  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000d7b9  mov     rdi, [rbp+160h+var_1E0]
0x18000d7bd  lea     r8, aClsid; "CLSID\\"
0x18000d7c4  mov     esi, 80h
0x18000d7c9  mov     edx, esi
0x18000d7cb  lea     rcx, [rbp+160h+SubKey]
0x18000d7cf  call    cs:__imp__o_wcscpy_s
0x18000d7d5  test    eax, eax
0x18000d7d7  jz      short loc_18000D7FD
0x18000d7d9  cmp     eax, r14d
0x18000d7dc  jz      loc_18000D98A
0x18000d7e2  cmp     eax, 16h
0x18000d7e5  jz      loc_18000D9A0
0x18000d7eb  cmp     eax, 22h ; '"'
0x18000d7ee  jz      loc_18000D9A0
0x18000d7f4  cmp     eax, r12d
0x18000d7f7  jnz     loc_18000D995
0x18000d7fd  lea     r8, [rbp+160h+sz]
0x18000d804  mov     rdx, rsi
0x18000d807  lea     rcx, [rbp+160h+SubKey]
0x18000d80b  call    cs:__imp__o_wcscat_s
0x18000d811  test    eax, eax
0x18000d813  jz      short loc_18000D839
0x18000d815  cmp     eax, r14d
0x18000d818  jz      loc_18000D98A
0x18000d81e  cmp     eax, 16h
0x18000d821  jz      loc_18000D9A0
0x18000d827  cmp     eax, 22h ; '"'
0x18000d82a  jz      loc_18000D9A0
0x18000d830  cmp     eax, r12d
0x18000d833  jnz     loc_18000D995
0x18000d839  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18000d840  mov     rdx, rsi
0x18000d843  lea     rcx, [rbp+160h+SubKey]
0x18000d847  call    cs:__imp__o_wcscat_s
0x18000d84d  test    eax, eax
0x18000d84f  jz      short loc_18000D875
0x18000d851  cmp     eax, r14d
0x18000d854  jz      loc_18000D98A
0x18000d85a  cmp     eax, 16h
0x18000d85d  jz      loc_18000D9A0
0x18000d863  cmp     eax, 22h ; '"'
0x18000d866  jz      loc_18000D9A0
0x18000d86c  cmp     eax, r12d
0x18000d86f  jnz     loc_18000D995
0x18000d875  mov     [rsp+260h+hKey], r15
0x18000d87a  lea     rax, [rsp+260h+hKey]
0x18000d87f  mov     [rsp+260h+ppv], rax; phkResult
0x18000d884  mov     r9d, 20019h; samDesired
0x18000d88a  xor     r8d, r8d; ulOptions
0x18000d88d  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x18000d891  mov     rcx, rdi; hKey
0x18000d894  call    cs:__imp_RegOpenKeyExW
0x18000d89a  test    eax, eax
0x18000d89c  jnz     loc_18000D929
0x18000d8a2  mov     eax, r15d
0x18000d8a5  test    rbx, rbx
0x18000d8a8  jz      short loc_18000D8B3
0x18000d8aa  mov     rcx, rbx; hKey
0x18000d8ad  call    cs:__imp_RegCloseKey
0x18000d8b3  mov     rbx, [rsp+260h+hKey]
0x18000d8b8  test    eax, eax
0x18000d8ba  jnz     short loc_18000D929
0x18000d8bc  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000d8c1  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000d8c6  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000d8cb  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000d8d0  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18000d8d5  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000d8da  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000d8df  lea     rax, [rsp+260h+cSubKeys]
0x18000d8e4  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000d8e9  xor     r9d, r9d; lpReserved
0x18000d8ec  xor     r8d, r8d; lpcchClass
0x18000d8ef  xor     edx, edx; lpClass
0x18000d8f1  mov     rcx, rbx; hKey
0x18000d8f4  call    cs:__imp_RegQueryInfoKeyW
0x18000d8fa  mov     esi, eax
0x18000d8fc  test    rbx, rbx
0x18000d8ff  jz      short loc_18000D90D
0x18000d901  mov     rcx, rbx; hKey
0x18000d904  call    cs:__imp_RegCloseKey
0x18000d90a  mov     rbx, r15
0x18000d90d  test    esi, esi
0x18000d90f  jnz     short loc_18000D937
0x18000d911  cmp     [rsp+260h+cSubKeys], r15d
0x18000d916  jnz     short loc_18000D929
0x18000d918  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x18000d91c  lea     rcx, [rbp+160h+var_1E0]; this
0x18000d920  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000d925  mov     rdi, [rbp+160h+var_1E0]
0x18000d929  test    rbx, rbx
0x18000d92c  jz      short loc_18000D937
0x18000d92e  mov     rcx, rbx; hKey
0x18000d931  call    cs:__imp_RegCloseKey
0x18000d937  test    rdi, rdi
0x18000d93a  jz      short loc_18000D946
0x18000d93c  mov     rcx, rdi; hKey
0x18000d93f  call    cs:__imp_RegCloseKey
0x18000d945  nop
0x18000d946  mov     rcx, [rsp+260h+var_1F8]
0x18000d94b  test    rcx, rcx
0x18000d94e  jz      short loc_18000D95D
0x18000d950  mov     rax, [rcx]
0x18000d953  mov     rax, [rax+10h]
0x18000d957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d95c  nop
0x18000d95d  xor     eax, eax
0x18000d95f  mov     rcx, [rbp+160h+var_30]
0x18000d966  xor     rcx, rsp; StackCookie
0x18000d969  call    __security_check_cookie
0x18000d96e  lea     r11, [rsp+260h+var_20]
0x18000d976  mov     rbx, [r11+40h]
0x18000d97a  mov     rsi, [r11+48h]
0x18000d97e  mov     rsp, r11
0x18000d981  pop     r15
0x18000d983  pop     r14
0x18000d985  pop     r12
0x18000d987  pop     rdi
0x18000d988  pop     rbp
0x18000d989  retn
  ... truncated ...
```
