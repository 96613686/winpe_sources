# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18000c6b0`
- end: `0x18000cb6b`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1211`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000d480`
- `0x18000d570`

## callees

- `0x180004180`
- `0x1800070b8`
- `0x1800077f0`
- `0x18000c6b0`
- `0x180032010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000c85d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000c899`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000c9cb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000ca07`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000c85d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000c899`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000c9cb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000ca07`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000c819`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000c98f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000c819`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000c98f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c801`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c801`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c752`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000c752`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000c948`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000cab4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000c948`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000cab4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c958`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ca6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cac4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000caf1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000caff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c958`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ca6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cac4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000caf1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000caff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c901`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ca54`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c901`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ca54`

## string_xrefs

- `0x18000c807`: `CLSID\`
- `0x18000c97d`: `CLSID\`

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
0x18000c6b0  mov     [rsp-8+arg_10], rbx
0x18000c6b5  mov     [rsp-8+arg_18], rsi
0x18000c6ba  push    rbp
0x18000c6bb  push    rdi
0x18000c6bc  push    r12
0x18000c6be  push    r14
0x18000c6c0  push    r15
0x18000c6c2  lea     rbp, [rsp-140h]
0x18000c6ca  sub     rsp, 240h
0x18000c6d1  mov     rax, cs:__security_cookie
0x18000c6d8  xor     rax, rsp
0x18000c6db  mov     [rbp+160h+var_30], rax
0x18000c6e2  mov     r14d, r8d
0x18000c6e5  mov     rdi, rdx
0x18000c6e8  mov     rbx, rcx
0x18000c6eb  xor     r15d, r15d
0x18000c6ee  mov     [rsp+260h+var_1F8], r15
0x18000c6f3  xorps   xmm0, xmm0
0x18000c6f6  movups  [rbp+160h+var_1C8], xmm0
0x18000c6fa  test    rdx, rdx
0x18000c6fd  jnz     short loc_18000C704
0x18000c6ff  jmp     loc_18000CB1D
0x18000c704  cmp     [rcx], r15d
0x18000c707  jnz     short loc_18000C72F
0x18000c709  mov     eax, dword ptr cs:GUID_NULL.Data2
0x18000c70f  cmp     [rcx+4], eax
0x18000c712  jnz     short loc_18000C72F
0x18000c714  mov     eax, dword ptr cs:GUID_NULL.Data4
0x18000c71a  cmp     [rcx+8], eax
0x18000c71d  jnz     short loc_18000C72F
0x18000c71f  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x18000c725  cmp     [rcx+0Ch], eax
0x18000c728  jnz     short loc_18000C72F
0x18000c72a  jmp     loc_18000CB1D
0x18000c72f  lea     rax, [rsp+260h+var_1F8]
0x18000c734  mov     [rsp+260h+ppv], rax; ppv
0x18000c739  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18000c740  mov     r12d, 1
0x18000c746  mov     r8d, r12d; dwClsContext
0x18000c749  xor     edx, edx; pUnkOuter
0x18000c74b  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18000c752  call    cs:__imp_CoCreateInstance
0x18000c758  test    eax, eax
0x18000c75a  jns     loc_18000C7E0
0x18000c760  jmp     loc_18000CB06
0x18000c765  mov     rax, [rdi+8]
0x18000c769  movups  xmm0, xmmword ptr [rax]
0x18000c76c  movdqu  [rbp+160h+var_1C8], xmm0
0x18000c771  lea     r9, [rbp+160h+var_1C8]
0x18000c775  mov     r8d, r12d
0x18000c778  mov     rdx, rbx
0x18000c77b  test    r14d, r14d
0x18000c77e  jz      short loc_18000C7C0
0x18000c780  cmp     ecx, r12d
0x18000c783  mov     rcx, [rsp+260h+var_1F8]
0x18000c788  mov     rax, [rcx]
0x18000c78b  jnz     short loc_18000C793
0x18000c78d  mov     rax, [rax+28h]
0x18000c791  jmp     short loc_18000C797
0x18000c793  mov     rax, [rax+38h]
0x18000c797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c79c  mov     esi, eax
0x18000c79e  test    eax, eax
0x18000c7a0  jns     short loc_18000C7DC
0x18000c7a2  mov     rcx, [rsp+260h+var_1F8]
0x18000c7a7  test    rcx, rcx
0x18000c7aa  jz      short loc_18000C7B9
0x18000c7ac  mov     rax, [rcx]
0x18000c7af  mov     rax, [rax+10h]
0x18000c7b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7b8  nop
0x18000c7b9  mov     eax, esi
0x18000c7bb  jmp     loc_18000CB1F
0x18000c7c0  cmp     ecx, r12d
0x18000c7c3  mov     rcx, [rsp+260h+var_1F8]
0x18000c7c8  mov     rax, [rcx]
0x18000c7cb  jnz     short loc_18000C7D3
0x18000c7cd  mov     rax, [rax+30h]
0x18000c7d1  jmp     short loc_18000C7D7
0x18000c7d3  mov     rax, [rax+40h]
0x18000c7d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7dc  add     rdi, 10h
0x18000c7e0  mov     ecx, [rdi]
0x18000c7e2  test    ecx, ecx
0x18000c7e4  jnz     loc_18000C765
0x18000c7ea  test    r14d, r14d
0x18000c7ed  jnz     loc_18000CB06
0x18000c7f3  lea     r8d, [rcx+40h]; cchMax
0x18000c7f7  lea     rdx, [rbp+160h+sz]; lpsz
0x18000c7fe  mov     rcx, rbx; rguid
0x18000c801  call    cs:__imp_StringFromGUID2
0x18000c807  lea     r8, aClsid; "CLSID\\"
0x18000c80e  mov     ebx, 80h
0x18000c813  mov     edx, ebx
0x18000c815  lea     rcx, [rbp+160h+SubKey]
0x18000c819  call    cs:__imp__o_wcscpy_s
0x18000c81f  lea     r14d, [rbx-74h]
0x18000c823  lea     r12d, [rbx-30h]
0x18000c827  test    eax, eax
0x18000c829  jz      short loc_18000C84F
0x18000c82b  cmp     eax, r14d
0x18000c82e  jz      loc_18000CB4A
0x18000c834  cmp     eax, 16h
0x18000c837  jz      loc_18000CB60
0x18000c83d  cmp     eax, 22h ; '"'
0x18000c840  jz      loc_18000CB60
0x18000c846  cmp     eax, r12d
0x18000c849  jnz     loc_18000CB55
0x18000c84f  lea     r8, [rbp+160h+sz]
0x18000c856  mov     rdx, rbx
0x18000c859  lea     rcx, [rbp+160h+SubKey]
0x18000c85d  call    cs:__imp__o_wcscat_s
0x18000c863  test    eax, eax
0x18000c865  jz      short loc_18000C88B
0x18000c867  cmp     eax, r14d
0x18000c86a  jz      loc_18000CB4A
0x18000c870  cmp     eax, 16h
0x18000c873  jz      loc_18000CB60
0x18000c879  cmp     eax, 22h ; '"'
0x18000c87c  jz      loc_18000CB60
0x18000c882  cmp     eax, r12d
0x18000c885  jnz     loc_18000CB55
0x18000c88b  lea     r8, aRequiredCatego; "\\Required Categories"
0x18000c892  mov     rdx, rbx
0x18000c895  lea     rcx, [rbp+160h+SubKey]
0x18000c899  call    cs:__imp__o_wcscat_s
0x18000c89f  test    eax, eax
0x18000c8a1  jz      short loc_18000C8C7
0x18000c8a3  cmp     eax, r14d
0x18000c8a6  jz      loc_18000CB4A
0x18000c8ac  cmp     eax, 16h
0x18000c8af  jz      loc_18000CB60
0x18000c8b5  cmp     eax, 22h ; '"'
0x18000c8b8  jz      loc_18000CB60
0x18000c8be  cmp     eax, r12d
0x18000c8c1  jnz     loc_18000CB55
0x18000c8c7  mov     rdi, 0FFFFFFFF80000000h
0x18000c8ce  mov     [rbp+160h+var_1E0], rdi
0x18000c8d2  mov     [rbp+160h+var_1D8], r15
0x18000c8d6  mov     [rbp+160h+var_1D0], r15
0x18000c8da  mov     rbx, r15
0x18000c8dd  mov     [rsp+260h+cSubKeys], r15d
0x18000c8e2  mov     [rsp+260h+phkResult], r15
0x18000c8e7  lea     rax, [rsp+260h+phkResult]
0x18000c8ec  mov     [rsp+260h+ppv], rax; phkResult
0x18000c8f1  mov     r9d, 20019h; samDesired
0x18000c8f7  xor     r8d, r8d; ulOptions
0x18000c8fa  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x18000c8fe  mov     rcx, rdi; hKey
0x18000c901  call    cs:__imp_RegOpenKeyExW
0x18000c907  test    eax, eax
0x18000c909  jnz     short loc_18000C97D
0x18000c90b  mov     rbx, [rsp+260h+phkResult]
0x18000c910  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000c915  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000c91a  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000c91f  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000c924  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18000c929  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000c92e  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000c933  lea     rax, [rsp+260h+cSubKeys]
0x18000c938  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000c93d  xor     r9d, r9d; lpReserved
0x18000c940  xor     r8d, r8d; lpcchClass
0x18000c943  xor     edx, edx; lpClass
0x18000c945  mov     rcx, rbx; hKey
0x18000c948  call    cs:__imp_RegQueryInfoKeyW
0x18000c94e  mov     esi, eax
0x18000c950  test    rbx, rbx
0x18000c953  jz      short loc_18000C961
0x18000c955  mov     rcx, rbx; hKey
0x18000c958  call    cs:__imp_RegCloseKey
0x18000c95e  mov     rbx, r15
0x18000c961  test    esi, esi
0x18000c963  jnz     short loc_18000C97D
0x18000c965  cmp     [rsp+260h+cSubKeys], r15d
0x18000c96a  jnz     short loc_18000C97D
0x18000c96c  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x18000c970  lea     rcx, [rbp+160h+var_1E0]; this
0x18000c974  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000c979  mov     rdi, [rbp+160h+var_1E0]
0x18000c97d  lea     r8, aClsid; "CLSID\\"
0x18000c984  mov     esi, 80h
0x18000c989  mov     edx, esi
0x18000c98b  lea     rcx, [rbp+160h+SubKey]
0x18000c98f  call    cs:__imp__o_wcscpy_s
0x18000c995  test    eax, eax
0x18000c997  jz      short loc_18000C9BD
0x18000c999  cmp     eax, r14d
0x18000c99c  jz      loc_18000CB4A
0x18000c9a2  cmp     eax, 16h
0x18000c9a5  jz      loc_18000CB60
0x18000c9ab  cmp     eax, 22h ; '"'
0x18000c9ae  jz      loc_18000CB60
0x18000c9b4  cmp     eax, r12d
0x18000c9b7  jnz     loc_18000CB55
0x18000c9bd  lea     r8, [rbp+160h+sz]
0x18000c9c4  mov     rdx, rsi
0x18000c9c7  lea     rcx, [rbp+160h+SubKey]
0x18000c9cb  call    cs:__imp__o_wcscat_s
0x18000c9d1  test    eax, eax
0x18000c9d3  jz      short loc_18000C9F9
0x18000c9d5  cmp     eax, r14d
0x18000c9d8  jz      loc_18000CB4A
0x18000c9de  cmp     eax, 16h
0x18000c9e1  jz      loc_18000CB60
0x18000c9e7  cmp     eax, 22h ; '"'
0x18000c9ea  jz      loc_18000CB60
0x18000c9f0  cmp     eax, r12d
0x18000c9f3  jnz     loc_18000CB55
0x18000c9f9  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18000ca00  mov     rdx, rsi
0x18000ca03  lea     rcx, [rbp+160h+SubKey]
0x18000ca07  call    cs:__imp__o_wcscat_s
0x18000ca0d  test    eax, eax
0x18000ca0f  jz      short loc_18000CA35
0x18000ca11  cmp     eax, r14d
0x18000ca14  jz      loc_18000CB4A
0x18000ca1a  cmp     eax, 16h
0x18000ca1d  jz      loc_18000CB60
0x18000ca23  cmp     eax, 22h ; '"'
0x18000ca26  jz      loc_18000CB60
0x18000ca2c  cmp     eax, r12d
0x18000ca2f  jnz     loc_18000CB55
0x18000ca35  mov     [rsp+260h+hKey], r15
0x18000ca3a  lea     rax, [rsp+260h+hKey]
0x18000ca3f  mov     [rsp+260h+ppv], rax; phkResult
0x18000ca44  mov     r9d, 20019h; samDesired
0x18000ca4a  xor     r8d, r8d; ulOptions
0x18000ca4d  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x18000ca51  mov     rcx, rdi; hKey
0x18000ca54  call    cs:__imp_RegOpenKeyExW
0x18000ca5a  test    eax, eax
0x18000ca5c  jnz     loc_18000CAE9
0x18000ca62  mov     eax, r15d
0x18000ca65  test    rbx, rbx
0x18000ca68  jz      short loc_18000CA73
0x18000ca6a  mov     rcx, rbx; hKey
0x18000ca6d  call    cs:__imp_RegCloseKey
0x18000ca73  mov     rbx, [rsp+260h+hKey]
0x18000ca78  test    eax, eax
0x18000ca7a  jnz     short loc_18000CAE9
0x18000ca7c  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000ca81  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000ca86  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000ca8b  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000ca90  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18000ca95  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000ca9a  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000ca9f  lea     rax, [rsp+260h+cSubKeys]
0x18000caa4  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000caa9  xor     r9d, r9d; lpReserved
0x18000caac  xor     r8d, r8d; lpcchClass
0x18000caaf  xor     edx, edx; lpClass
0x18000cab1  mov     rcx, rbx; hKey
0x18000cab4  call    cs:__imp_RegQueryInfoKeyW
0x18000caba  mov     esi, eax
0x18000cabc  test    rbx, rbx
0x18000cabf  jz      short loc_18000CACD
0x18000cac1  mov     rcx, rbx; hKey
0x18000cac4  call    cs:__imp_RegCloseKey
0x18000caca  mov     rbx, r15
0x18000cacd  test    esi, esi
0x18000cacf  jnz     short loc_18000CAF7
0x18000cad1  cmp     [rsp+260h+cSubKeys], r15d
0x18000cad6  jnz     short loc_18000CAE9
0x18000cad8  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x18000cadc  lea     rcx, [rbp+160h+var_1E0]; this
0x18000cae0  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000cae5  mov     rdi, [rbp+160h+var_1E0]
0x18000cae9  test    rbx, rbx
0x18000caec  jz      short loc_18000CAF7
0x18000caee  mov     rcx, rbx; hKey
0x18000caf1  call    cs:__imp_RegCloseKey
0x18000caf7  test    rdi, rdi
0x18000cafa  jz      short loc_18000CB06
0x18000cafc  mov     rcx, rdi; hKey
0x18000caff  call    cs:__imp_RegCloseKey
0x18000cb05  nop
0x18000cb06  mov     rcx, [rsp+260h+var_1F8]
0x18000cb0b  test    rcx, rcx
0x18000cb0e  jz      short loc_18000CB1D
0x18000cb10  mov     rax, [rcx]
0x18000cb13  mov     rax, [rax+10h]
0x18000cb17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb1c  nop
0x18000cb1d  xor     eax, eax
0x18000cb1f  mov     rcx, [rbp+160h+var_30]
0x18000cb26  xor     rcx, rsp; StackCookie
0x18000cb29  call    __security_check_cookie
0x18000cb2e  lea     r11, [rsp+260h+var_20]
0x18000cb36  mov     rbx, [r11+40h]
0x18000cb3a  mov     rsi, [r11+48h]
0x18000cb3e  mov     rsp, r11
0x18000cb41  pop     r15
0x18000cb43  pop     r14
0x18000cb45  pop     r12
0x18000cb47  pop     rdi
0x18000cb48  pop     rbp
0x18000cb49  retn
  ... truncated ...
```
