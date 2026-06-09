# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x18000a7b0`
- end: `0x18000ac6b`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1211`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b580`
- `0x18000b670`

## callees

- `0x1800033d0`
- `0x180006018`
- `0x180006730`
- `0x18000a7b0`
- `0x180013010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000a95d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000a999`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000aacb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000ab07`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000a95d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000a999`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000aacb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000ab07`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000a919`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000aa8f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000a919`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000aa8f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a852`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a852`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000a901`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000a901`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000aa01`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ab54`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000aa01`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ab54`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ab6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000abc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000abf1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000abff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ab6d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000abc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000abf1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000abff`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000aa48`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000abb4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000aa48`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000abb4`

## string_xrefs

- `0x18000a907`: `CLSID\`
- `0x18000aa7d`: `CLSID\`

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
0x18000a7b0  mov     [rsp-8+arg_10], rbx
0x18000a7b5  mov     [rsp-8+arg_18], rsi
0x18000a7ba  push    rbp
0x18000a7bb  push    rdi
0x18000a7bc  push    r12
0x18000a7be  push    r14
0x18000a7c0  push    r15
0x18000a7c2  lea     rbp, [rsp-140h]
0x18000a7ca  sub     rsp, 240h
0x18000a7d1  mov     rax, cs:__security_cookie
0x18000a7d8  xor     rax, rsp
0x18000a7db  mov     [rbp+160h+var_30], rax
0x18000a7e2  mov     r14d, r8d
0x18000a7e5  mov     rdi, rdx
0x18000a7e8  mov     rbx, rcx
0x18000a7eb  xor     r15d, r15d
0x18000a7ee  mov     [rsp+260h+var_1F8], r15
0x18000a7f3  xorps   xmm0, xmm0
0x18000a7f6  movups  [rbp+160h+var_1C8], xmm0
0x18000a7fa  test    rdx, rdx
0x18000a7fd  jnz     short loc_18000A804
0x18000a7ff  jmp     loc_18000AC1D
0x18000a804  cmp     [rcx], r15d
0x18000a807  jnz     short loc_18000A82F
0x18000a809  mov     eax, dword ptr cs:GUID_NULL.Data2
0x18000a80f  cmp     [rcx+4], eax
0x18000a812  jnz     short loc_18000A82F
0x18000a814  mov     eax, dword ptr cs:GUID_NULL.Data4
0x18000a81a  cmp     [rcx+8], eax
0x18000a81d  jnz     short loc_18000A82F
0x18000a81f  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x18000a825  cmp     [rcx+0Ch], eax
0x18000a828  jnz     short loc_18000A82F
0x18000a82a  jmp     loc_18000AC1D
0x18000a82f  lea     rax, [rsp+260h+var_1F8]
0x18000a834  mov     [rsp+260h+ppv], rax; ppv
0x18000a839  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18000a840  mov     r12d, 1
0x18000a846  mov     r8d, r12d; dwClsContext
0x18000a849  xor     edx, edx; pUnkOuter
0x18000a84b  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18000a852  call    cs:__imp_CoCreateInstance
0x18000a858  test    eax, eax
0x18000a85a  jns     loc_18000A8E0
0x18000a860  jmp     loc_18000AC06
0x18000a865  mov     rax, [rdi+8]
0x18000a869  movups  xmm0, xmmword ptr [rax]
0x18000a86c  movdqu  [rbp+160h+var_1C8], xmm0
0x18000a871  lea     r9, [rbp+160h+var_1C8]
0x18000a875  mov     r8d, r12d
0x18000a878  mov     rdx, rbx
0x18000a87b  test    r14d, r14d
0x18000a87e  jz      short loc_18000A8C0
0x18000a880  cmp     ecx, r12d
0x18000a883  mov     rcx, [rsp+260h+var_1F8]
0x18000a888  mov     rax, [rcx]
0x18000a88b  jnz     short loc_18000A893
0x18000a88d  mov     rax, [rax+28h]
0x18000a891  jmp     short loc_18000A897
0x18000a893  mov     rax, [rax+38h]
0x18000a897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a89c  mov     esi, eax
0x18000a89e  test    eax, eax
0x18000a8a0  jns     short loc_18000A8DC
0x18000a8a2  mov     rcx, [rsp+260h+var_1F8]
0x18000a8a7  test    rcx, rcx
0x18000a8aa  jz      short loc_18000A8B9
0x18000a8ac  mov     rax, [rcx]
0x18000a8af  mov     rax, [rax+10h]
0x18000a8b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8b8  nop
0x18000a8b9  mov     eax, esi
0x18000a8bb  jmp     loc_18000AC1F
0x18000a8c0  cmp     ecx, r12d
0x18000a8c3  mov     rcx, [rsp+260h+var_1F8]
0x18000a8c8  mov     rax, [rcx]
0x18000a8cb  jnz     short loc_18000A8D3
0x18000a8cd  mov     rax, [rax+30h]
0x18000a8d1  jmp     short loc_18000A8D7
0x18000a8d3  mov     rax, [rax+40h]
0x18000a8d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8dc  add     rdi, 10h
0x18000a8e0  mov     ecx, [rdi]
0x18000a8e2  test    ecx, ecx
0x18000a8e4  jnz     loc_18000A865
0x18000a8ea  test    r14d, r14d
0x18000a8ed  jnz     loc_18000AC06
0x18000a8f3  lea     r8d, [rcx+40h]; cchMax
0x18000a8f7  lea     rdx, [rbp+160h+sz]; lpsz
0x18000a8fe  mov     rcx, rbx; rguid
0x18000a901  call    cs:__imp_StringFromGUID2
0x18000a907  lea     r8, aClsid; "CLSID\\"
0x18000a90e  mov     ebx, 80h
0x18000a913  mov     edx, ebx
0x18000a915  lea     rcx, [rbp+160h+SubKey]
0x18000a919  call    cs:__imp__o_wcscpy_s
0x18000a91f  lea     r14d, [rbx-74h]
0x18000a923  lea     r12d, [rbx-30h]
0x18000a927  test    eax, eax
0x18000a929  jz      short loc_18000A94F
0x18000a92b  cmp     eax, r14d
0x18000a92e  jz      loc_18000AC4A
0x18000a934  cmp     eax, 16h
0x18000a937  jz      loc_18000AC60
0x18000a93d  cmp     eax, 22h ; '"'
0x18000a940  jz      loc_18000AC60
0x18000a946  cmp     eax, r12d
0x18000a949  jnz     loc_18000AC55
0x18000a94f  lea     r8, [rbp+160h+sz]
0x18000a956  mov     rdx, rbx
0x18000a959  lea     rcx, [rbp+160h+SubKey]
0x18000a95d  call    cs:__imp__o_wcscat_s
0x18000a963  test    eax, eax
0x18000a965  jz      short loc_18000A98B
0x18000a967  cmp     eax, r14d
0x18000a96a  jz      loc_18000AC4A
0x18000a970  cmp     eax, 16h
0x18000a973  jz      loc_18000AC60
0x18000a979  cmp     eax, 22h ; '"'
0x18000a97c  jz      loc_18000AC60
0x18000a982  cmp     eax, r12d
0x18000a985  jnz     loc_18000AC55
0x18000a98b  lea     r8, aRequiredCatego; "\\Required Categories"
0x18000a992  mov     rdx, rbx
0x18000a995  lea     rcx, [rbp+160h+SubKey]
0x18000a999  call    cs:__imp__o_wcscat_s
0x18000a99f  test    eax, eax
0x18000a9a1  jz      short loc_18000A9C7
0x18000a9a3  cmp     eax, r14d
0x18000a9a6  jz      loc_18000AC4A
0x18000a9ac  cmp     eax, 16h
0x18000a9af  jz      loc_18000AC60
0x18000a9b5  cmp     eax, 22h ; '"'
0x18000a9b8  jz      loc_18000AC60
0x18000a9be  cmp     eax, r12d
0x18000a9c1  jnz     loc_18000AC55
0x18000a9c7  mov     rdi, 0FFFFFFFF80000000h
0x18000a9ce  mov     [rbp+160h+var_1E0], rdi
0x18000a9d2  mov     [rbp+160h+var_1D8], r15
0x18000a9d6  mov     [rbp+160h+var_1D0], r15
0x18000a9da  mov     rbx, r15
0x18000a9dd  mov     [rsp+260h+cSubKeys], r15d
0x18000a9e2  mov     [rsp+260h+phkResult], r15
0x18000a9e7  lea     rax, [rsp+260h+phkResult]
0x18000a9ec  mov     [rsp+260h+ppv], rax; phkResult
0x18000a9f1  mov     r9d, 20019h; samDesired
0x18000a9f7  xor     r8d, r8d; ulOptions
0x18000a9fa  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x18000a9fe  mov     rcx, rdi; hKey
0x18000aa01  call    cs:__imp_RegOpenKeyExW
0x18000aa07  test    eax, eax
0x18000aa09  jnz     short loc_18000AA7D
0x18000aa0b  mov     rbx, [rsp+260h+phkResult]
0x18000aa10  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000aa15  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000aa1a  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000aa1f  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000aa24  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18000aa29  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000aa2e  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000aa33  lea     rax, [rsp+260h+cSubKeys]
0x18000aa38  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000aa3d  xor     r9d, r9d; lpReserved
0x18000aa40  xor     r8d, r8d; lpcchClass
0x18000aa43  xor     edx, edx; lpClass
0x18000aa45  mov     rcx, rbx; hKey
0x18000aa48  call    cs:__imp_RegQueryInfoKeyW
0x18000aa4e  mov     esi, eax
0x18000aa50  test    rbx, rbx
0x18000aa53  jz      short loc_18000AA61
0x18000aa55  mov     rcx, rbx; hKey
0x18000aa58  call    cs:__imp_RegCloseKey
0x18000aa5e  mov     rbx, r15
0x18000aa61  test    esi, esi
0x18000aa63  jnz     short loc_18000AA7D
0x18000aa65  cmp     [rsp+260h+cSubKeys], r15d
0x18000aa6a  jnz     short loc_18000AA7D
0x18000aa6c  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x18000aa70  lea     rcx, [rbp+160h+var_1E0]; this
0x18000aa74  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000aa79  mov     rdi, [rbp+160h+var_1E0]
0x18000aa7d  lea     r8, aClsid; "CLSID\\"
0x18000aa84  mov     esi, 80h
0x18000aa89  mov     edx, esi
0x18000aa8b  lea     rcx, [rbp+160h+SubKey]
0x18000aa8f  call    cs:__imp__o_wcscpy_s
0x18000aa95  test    eax, eax
0x18000aa97  jz      short loc_18000AABD
0x18000aa99  cmp     eax, r14d
0x18000aa9c  jz      loc_18000AC4A
0x18000aaa2  cmp     eax, 16h
0x18000aaa5  jz      loc_18000AC60
0x18000aaab  cmp     eax, 22h ; '"'
0x18000aaae  jz      loc_18000AC60
0x18000aab4  cmp     eax, r12d
0x18000aab7  jnz     loc_18000AC55
0x18000aabd  lea     r8, [rbp+160h+sz]
0x18000aac4  mov     rdx, rsi
0x18000aac7  lea     rcx, [rbp+160h+SubKey]
0x18000aacb  call    cs:__imp__o_wcscat_s
0x18000aad1  test    eax, eax
0x18000aad3  jz      short loc_18000AAF9
0x18000aad5  cmp     eax, r14d
0x18000aad8  jz      loc_18000AC4A
0x18000aade  cmp     eax, 16h
0x18000aae1  jz      loc_18000AC60
0x18000aae7  cmp     eax, 22h ; '"'
0x18000aaea  jz      loc_18000AC60
0x18000aaf0  cmp     eax, r12d
0x18000aaf3  jnz     loc_18000AC55
0x18000aaf9  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18000ab00  mov     rdx, rsi
0x18000ab03  lea     rcx, [rbp+160h+SubKey]
0x18000ab07  call    cs:__imp__o_wcscat_s
0x18000ab0d  test    eax, eax
0x18000ab0f  jz      short loc_18000AB35
0x18000ab11  cmp     eax, r14d
0x18000ab14  jz      loc_18000AC4A
0x18000ab1a  cmp     eax, 16h
0x18000ab1d  jz      loc_18000AC60
0x18000ab23  cmp     eax, 22h ; '"'
0x18000ab26  jz      loc_18000AC60
0x18000ab2c  cmp     eax, r12d
0x18000ab2f  jnz     loc_18000AC55
0x18000ab35  mov     [rsp+260h+hKey], r15
0x18000ab3a  lea     rax, [rsp+260h+hKey]
0x18000ab3f  mov     [rsp+260h+ppv], rax; phkResult
0x18000ab44  mov     r9d, 20019h; samDesired
0x18000ab4a  xor     r8d, r8d; ulOptions
0x18000ab4d  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x18000ab51  mov     rcx, rdi; hKey
0x18000ab54  call    cs:__imp_RegOpenKeyExW
0x18000ab5a  test    eax, eax
0x18000ab5c  jnz     loc_18000ABE9
0x18000ab62  mov     eax, r15d
0x18000ab65  test    rbx, rbx
0x18000ab68  jz      short loc_18000AB73
0x18000ab6a  mov     rcx, rbx; hKey
0x18000ab6d  call    cs:__imp_RegCloseKey
0x18000ab73  mov     rbx, [rsp+260h+hKey]
0x18000ab78  test    eax, eax
0x18000ab7a  jnz     short loc_18000ABE9
0x18000ab7c  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000ab81  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000ab86  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000ab8b  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000ab90  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18000ab95  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000ab9a  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000ab9f  lea     rax, [rsp+260h+cSubKeys]
0x18000aba4  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000aba9  xor     r9d, r9d; lpReserved
0x18000abac  xor     r8d, r8d; lpcchClass
0x18000abaf  xor     edx, edx; lpClass
0x18000abb1  mov     rcx, rbx; hKey
0x18000abb4  call    cs:__imp_RegQueryInfoKeyW
0x18000abba  mov     esi, eax
0x18000abbc  test    rbx, rbx
0x18000abbf  jz      short loc_18000ABCD
0x18000abc1  mov     rcx, rbx; hKey
0x18000abc4  call    cs:__imp_RegCloseKey
0x18000abca  mov     rbx, r15
0x18000abcd  test    esi, esi
0x18000abcf  jnz     short loc_18000ABF7
0x18000abd1  cmp     [rsp+260h+cSubKeys], r15d
0x18000abd6  jnz     short loc_18000ABE9
0x18000abd8  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x18000abdc  lea     rcx, [rbp+160h+var_1E0]; this
0x18000abe0  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000abe5  mov     rdi, [rbp+160h+var_1E0]
0x18000abe9  test    rbx, rbx
0x18000abec  jz      short loc_18000ABF7
0x18000abee  mov     rcx, rbx; hKey
0x18000abf1  call    cs:__imp_RegCloseKey
0x18000abf7  test    rdi, rdi
0x18000abfa  jz      short loc_18000AC06
0x18000abfc  mov     rcx, rdi; hKey
0x18000abff  call    cs:__imp_RegCloseKey
0x18000ac05  nop
0x18000ac06  mov     rcx, [rsp+260h+var_1F8]
0x18000ac0b  test    rcx, rcx
0x18000ac0e  jz      short loc_18000AC1D
0x18000ac10  mov     rax, [rcx]
0x18000ac13  mov     rax, [rax+10h]
0x18000ac17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac1c  nop
0x18000ac1d  xor     eax, eax
0x18000ac1f  mov     rcx, [rbp+160h+var_30]
0x18000ac26  xor     rcx, rsp; StackCookie
0x18000ac29  call    __security_check_cookie
0x18000ac2e  lea     r11, [rsp+260h+var_20]
0x18000ac36  mov     rbx, [r11+40h]
0x18000ac3a  mov     rsi, [r11+48h]
0x18000ac3e  mov     rsp, r11
0x18000ac41  pop     r15
0x18000ac43  pop     r14
0x18000ac45  pop     r12
0x18000ac47  pop     rdi
0x18000ac48  pop     rbp
0x18000ac49  retn
  ... truncated ...
```
