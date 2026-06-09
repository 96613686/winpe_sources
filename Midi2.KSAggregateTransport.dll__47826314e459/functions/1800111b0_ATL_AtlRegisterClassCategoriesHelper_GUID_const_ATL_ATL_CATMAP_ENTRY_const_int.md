# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x1800111b0`
- end: `0x18001166b`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1211`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012050`
- `0x180012140`

## callees

- `0x180005020`
- `0x1800080b8`
- `0x1800087d0`
- `0x1800111b0`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001135d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180011399`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800114cb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180011507`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001135d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180011399`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800114cb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180011507`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180011319`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001148f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180011319`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001148f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011252`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011252`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180011301`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180011301`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011458`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001156d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800115c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800115f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800115ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011458`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001156d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800115c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800115f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800115ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011401`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011554`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011401`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011554`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180011448`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800115b4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180011448`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800115b4`

## string_xrefs

- `0x180011307`: `CLSID\`
- `0x18001147d`: `CLSID\`

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
0x1800111b0  mov     [rsp-8+arg_10], rbx
0x1800111b5  mov     [rsp-8+arg_18], rsi
0x1800111ba  push    rbp
0x1800111bb  push    rdi
0x1800111bc  push    r12
0x1800111be  push    r14
0x1800111c0  push    r15
0x1800111c2  lea     rbp, [rsp-140h]
0x1800111ca  sub     rsp, 240h
0x1800111d1  mov     rax, cs:__security_cookie
0x1800111d8  xor     rax, rsp
0x1800111db  mov     [rbp+160h+var_30], rax
0x1800111e2  mov     r14d, r8d
0x1800111e5  mov     rdi, rdx
0x1800111e8  mov     rbx, rcx
0x1800111eb  xor     r15d, r15d
0x1800111ee  mov     [rsp+260h+var_1F8], r15
0x1800111f3  xorps   xmm0, xmm0
0x1800111f6  movups  [rbp+160h+var_1C8], xmm0
0x1800111fa  test    rdx, rdx
0x1800111fd  jnz     short loc_180011204
0x1800111ff  jmp     loc_18001161D
0x180011204  cmp     [rcx], r15d
0x180011207  jnz     short loc_18001122F
0x180011209  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data2
0x18001120f  cmp     [rcx+4], eax
0x180011212  jnz     short loc_18001122F
0x180011214  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x18001121a  cmp     [rcx+8], eax
0x18001121d  jnz     short loc_18001122F
0x18001121f  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4+4
0x180011225  cmp     [rcx+0Ch], eax
0x180011228  jnz     short loc_18001122F
0x18001122a  jmp     loc_18001161D
0x18001122f  lea     rax, [rsp+260h+var_1F8]
0x180011234  mov     [rsp+260h+ppv], rax; ppv
0x180011239  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180011240  mov     r12d, 1
0x180011246  mov     r8d, r12d; dwClsContext
0x180011249  xor     edx, edx; pUnkOuter
0x18001124b  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180011252  call    cs:__imp_CoCreateInstance
0x180011258  test    eax, eax
0x18001125a  jns     loc_1800112E0
0x180011260  jmp     loc_180011606
0x180011265  mov     rax, [rdi+8]
0x180011269  movups  xmm0, xmmword ptr [rax]
0x18001126c  movdqu  [rbp+160h+var_1C8], xmm0
0x180011271  lea     r9, [rbp+160h+var_1C8]
0x180011275  mov     r8d, r12d
0x180011278  mov     rdx, rbx
0x18001127b  test    r14d, r14d
0x18001127e  jz      short loc_1800112C0
0x180011280  cmp     ecx, r12d
0x180011283  mov     rcx, [rsp+260h+var_1F8]
0x180011288  mov     rax, [rcx]
0x18001128b  jnz     short loc_180011293
0x18001128d  mov     rax, [rax+28h]
0x180011291  jmp     short loc_180011297
0x180011293  mov     rax, [rax+38h]
0x180011297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001129c  mov     esi, eax
0x18001129e  test    eax, eax
0x1800112a0  jns     short loc_1800112DC
0x1800112a2  mov     rcx, [rsp+260h+var_1F8]
0x1800112a7  test    rcx, rcx
0x1800112aa  jz      short loc_1800112B9
0x1800112ac  mov     rax, [rcx]
0x1800112af  mov     rax, [rax+10h]
0x1800112b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112b8  nop
0x1800112b9  mov     eax, esi
0x1800112bb  jmp     loc_18001161F
0x1800112c0  cmp     ecx, r12d
0x1800112c3  mov     rcx, [rsp+260h+var_1F8]
0x1800112c8  mov     rax, [rcx]
0x1800112cb  jnz     short loc_1800112D3
0x1800112cd  mov     rax, [rax+30h]
0x1800112d1  jmp     short loc_1800112D7
0x1800112d3  mov     rax, [rax+40h]
0x1800112d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112dc  add     rdi, 10h
0x1800112e0  mov     ecx, [rdi]
0x1800112e2  test    ecx, ecx
0x1800112e4  jnz     loc_180011265
0x1800112ea  test    r14d, r14d
0x1800112ed  jnz     loc_180011606
0x1800112f3  lea     r8d, [rcx+40h]; cchMax
0x1800112f7  lea     rdx, [rbp+160h+sz]; lpsz
0x1800112fe  mov     rcx, rbx; rguid
0x180011301  call    cs:__imp_StringFromGUID2
0x180011307  lea     r8, aClsid; "CLSID\\"
0x18001130e  mov     ebx, 80h
0x180011313  mov     edx, ebx
0x180011315  lea     rcx, [rbp+160h+SubKey]
0x180011319  call    cs:__imp__o_wcscpy_s
0x18001131f  lea     r14d, [rbx-74h]
0x180011323  lea     r12d, [rbx-30h]
0x180011327  test    eax, eax
0x180011329  jz      short loc_18001134F
0x18001132b  cmp     eax, r14d
0x18001132e  jz      loc_18001164A
0x180011334  cmp     eax, 16h
0x180011337  jz      loc_180011660
0x18001133d  cmp     eax, 22h ; '"'
0x180011340  jz      loc_180011660
0x180011346  cmp     eax, r12d
0x180011349  jnz     loc_180011655
0x18001134f  lea     r8, [rbp+160h+sz]
0x180011356  mov     rdx, rbx
0x180011359  lea     rcx, [rbp+160h+SubKey]
0x18001135d  call    cs:__imp__o_wcscat_s
0x180011363  test    eax, eax
0x180011365  jz      short loc_18001138B
0x180011367  cmp     eax, r14d
0x18001136a  jz      loc_18001164A
0x180011370  cmp     eax, 16h
0x180011373  jz      loc_180011660
0x180011379  cmp     eax, 22h ; '"'
0x18001137c  jz      loc_180011660
0x180011382  cmp     eax, r12d
0x180011385  jnz     loc_180011655
0x18001138b  lea     r8, aRequiredCatego; "\\Required Categories"
0x180011392  mov     rdx, rbx
0x180011395  lea     rcx, [rbp+160h+SubKey]
0x180011399  call    cs:__imp__o_wcscat_s
0x18001139f  test    eax, eax
0x1800113a1  jz      short loc_1800113C7
0x1800113a3  cmp     eax, r14d
0x1800113a6  jz      loc_18001164A
0x1800113ac  cmp     eax, 16h
0x1800113af  jz      loc_180011660
0x1800113b5  cmp     eax, 22h ; '"'
0x1800113b8  jz      loc_180011660
0x1800113be  cmp     eax, r12d
0x1800113c1  jnz     loc_180011655
0x1800113c7  mov     rdi, 0FFFFFFFF80000000h
0x1800113ce  mov     [rbp+160h+var_1E0], rdi
0x1800113d2  mov     [rbp+160h+var_1D8], r15
0x1800113d6  mov     [rbp+160h+var_1D0], r15
0x1800113da  mov     rbx, r15
0x1800113dd  mov     [rsp+260h+cSubKeys], r15d
0x1800113e2  mov     [rsp+260h+phkResult], r15
0x1800113e7  lea     rax, [rsp+260h+phkResult]
0x1800113ec  mov     [rsp+260h+ppv], rax; phkResult
0x1800113f1  mov     r9d, 20019h; samDesired
0x1800113f7  xor     r8d, r8d; ulOptions
0x1800113fa  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x1800113fe  mov     rcx, rdi; hKey
0x180011401  call    cs:__imp_RegOpenKeyExW
0x180011407  test    eax, eax
0x180011409  jnz     short loc_18001147D
0x18001140b  mov     rbx, [rsp+260h+phkResult]
0x180011410  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180011415  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18001141a  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18001141f  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180011424  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180011429  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18001142e  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180011433  lea     rax, [rsp+260h+cSubKeys]
0x180011438  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18001143d  xor     r9d, r9d; lpReserved
0x180011440  xor     r8d, r8d; lpcchClass
0x180011443  xor     edx, edx; lpClass
0x180011445  mov     rcx, rbx; hKey
0x180011448  call    cs:__imp_RegQueryInfoKeyW
0x18001144e  mov     esi, eax
0x180011450  test    rbx, rbx
0x180011453  jz      short loc_180011461
0x180011455  mov     rcx, rbx; hKey
0x180011458  call    cs:__imp_RegCloseKey
0x18001145e  mov     rbx, r15
0x180011461  test    esi, esi
0x180011463  jnz     short loc_18001147D
0x180011465  cmp     [rsp+260h+cSubKeys], r15d
0x18001146a  jnz     short loc_18001147D
0x18001146c  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x180011470  lea     rcx, [rbp+160h+var_1E0]; this
0x180011474  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180011479  mov     rdi, [rbp+160h+var_1E0]
0x18001147d  lea     r8, aClsid; "CLSID\\"
0x180011484  mov     esi, 80h
0x180011489  mov     edx, esi
0x18001148b  lea     rcx, [rbp+160h+SubKey]
0x18001148f  call    cs:__imp__o_wcscpy_s
0x180011495  test    eax, eax
0x180011497  jz      short loc_1800114BD
0x180011499  cmp     eax, r14d
0x18001149c  jz      loc_18001164A
0x1800114a2  cmp     eax, 16h
0x1800114a5  jz      loc_180011660
0x1800114ab  cmp     eax, 22h ; '"'
0x1800114ae  jz      loc_180011660
0x1800114b4  cmp     eax, r12d
0x1800114b7  jnz     loc_180011655
0x1800114bd  lea     r8, [rbp+160h+sz]
0x1800114c4  mov     rdx, rsi
0x1800114c7  lea     rcx, [rbp+160h+SubKey]
0x1800114cb  call    cs:__imp__o_wcscat_s
0x1800114d1  test    eax, eax
0x1800114d3  jz      short loc_1800114F9
0x1800114d5  cmp     eax, r14d
0x1800114d8  jz      loc_18001164A
0x1800114de  cmp     eax, 16h
0x1800114e1  jz      loc_180011660
0x1800114e7  cmp     eax, 22h ; '"'
0x1800114ea  jz      loc_180011660
0x1800114f0  cmp     eax, r12d
0x1800114f3  jnz     loc_180011655
0x1800114f9  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180011500  mov     rdx, rsi
0x180011503  lea     rcx, [rbp+160h+SubKey]
0x180011507  call    cs:__imp__o_wcscat_s
0x18001150d  test    eax, eax
0x18001150f  jz      short loc_180011535
0x180011511  cmp     eax, r14d
0x180011514  jz      loc_18001164A
0x18001151a  cmp     eax, 16h
0x18001151d  jz      loc_180011660
0x180011523  cmp     eax, 22h ; '"'
0x180011526  jz      loc_180011660
0x18001152c  cmp     eax, r12d
0x18001152f  jnz     loc_180011655
0x180011535  mov     [rsp+260h+hKey], r15
0x18001153a  lea     rax, [rsp+260h+hKey]
0x18001153f  mov     [rsp+260h+ppv], rax; phkResult
0x180011544  mov     r9d, 20019h; samDesired
0x18001154a  xor     r8d, r8d; ulOptions
0x18001154d  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x180011551  mov     rcx, rdi; hKey
0x180011554  call    cs:__imp_RegOpenKeyExW
0x18001155a  test    eax, eax
0x18001155c  jnz     loc_1800115E9
0x180011562  mov     eax, r15d
0x180011565  test    rbx, rbx
0x180011568  jz      short loc_180011573
0x18001156a  mov     rcx, rbx; hKey
0x18001156d  call    cs:__imp_RegCloseKey
0x180011573  mov     rbx, [rsp+260h+hKey]
0x180011578  test    eax, eax
0x18001157a  jnz     short loc_1800115E9
0x18001157c  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180011581  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180011586  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18001158b  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180011590  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180011595  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18001159a  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18001159f  lea     rax, [rsp+260h+cSubKeys]
0x1800115a4  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x1800115a9  xor     r9d, r9d; lpReserved
0x1800115ac  xor     r8d, r8d; lpcchClass
0x1800115af  xor     edx, edx; lpClass
0x1800115b1  mov     rcx, rbx; hKey
0x1800115b4  call    cs:__imp_RegQueryInfoKeyW
0x1800115ba  mov     esi, eax
0x1800115bc  test    rbx, rbx
0x1800115bf  jz      short loc_1800115CD
0x1800115c1  mov     rcx, rbx; hKey
0x1800115c4  call    cs:__imp_RegCloseKey
0x1800115ca  mov     rbx, r15
0x1800115cd  test    esi, esi
0x1800115cf  jnz     short loc_1800115F7
0x1800115d1  cmp     [rsp+260h+cSubKeys], r15d
0x1800115d6  jnz     short loc_1800115E9
0x1800115d8  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x1800115dc  lea     rcx, [rbp+160h+var_1E0]; this
0x1800115e0  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800115e5  mov     rdi, [rbp+160h+var_1E0]
0x1800115e9  test    rbx, rbx
0x1800115ec  jz      short loc_1800115F7
0x1800115ee  mov     rcx, rbx; hKey
0x1800115f1  call    cs:__imp_RegCloseKey
0x1800115f7  test    rdi, rdi
0x1800115fa  jz      short loc_180011606
0x1800115fc  mov     rcx, rdi; hKey
0x1800115ff  call    cs:__imp_RegCloseKey
0x180011605  nop
0x180011606  mov     rcx, [rsp+260h+var_1F8]
0x18001160b  test    rcx, rcx
0x18001160e  jz      short loc_18001161D
0x180011610  mov     rax, [rcx]
0x180011613  mov     rax, [rax+10h]
0x180011617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001161c  nop
0x18001161d  xor     eax, eax
0x18001161f  mov     rcx, [rbp+160h+var_30]
0x180011626  xor     rcx, rsp; StackCookie
0x180011629  call    __security_check_cookie
0x18001162e  lea     r11, [rsp+260h+var_20]
0x180011636  mov     rbx, [r11+40h]
0x18001163a  mov     rsi, [r11+48h]
0x18001163e  mov     rsp, r11
0x180011641  pop     r15
0x180011643  pop     r14
0x180011645  pop     r12
0x180011647  pop     rdi
0x180011648  pop     rbp
0x180011649  retn
  ... truncated ...
```
