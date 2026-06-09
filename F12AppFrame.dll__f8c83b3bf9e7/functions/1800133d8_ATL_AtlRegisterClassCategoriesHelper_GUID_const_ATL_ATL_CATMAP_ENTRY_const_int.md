# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x1800133d8`
- end: `0x180013898`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1216`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800173c4`
- `0x180017ca0`
- `0x180017da0`

## callees

- `0x180001800`
- `0x180003858`
- `0x1800133d8`
- `0x180014148`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001358a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800135c6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800136f8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180013734`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001358a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800135c6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800136f8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180013734`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180013546`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800136bc`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180013546`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800136bc`
- `ADVAPI32!RegCloseKey` at `0x180013685`
- `ADVAPI32!RegCloseKey` at `0x18001379a`
- `ADVAPI32!RegCloseKey` at `0x1800137f1`
- `ADVAPI32!RegCloseKey` at `0x18001381e`
- `ADVAPI32!RegCloseKey` at `0x18001382c`
- `ADVAPI32!RegCloseKey` at `0x180013685`
- `ADVAPI32!RegCloseKey` at `0x18001379a`
- `ADVAPI32!RegCloseKey` at `0x1800137f1`
- `ADVAPI32!RegCloseKey` at `0x18001381e`
- `ADVAPI32!RegCloseKey` at `0x18001382c`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180013675`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800137e1`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180013675`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800137e1`
- `ADVAPI32!RegOpenKeyExW` at `0x18001362e`
- `ADVAPI32!RegOpenKeyExW` at `0x180013781`
- `ADVAPI32!RegOpenKeyExW` at `0x18001362e`
- `ADVAPI32!RegOpenKeyExW` at `0x180013781`
- `ole32!StringFromGUID2` at `0x18001352e`
- `ole32!StringFromGUID2` at `0x18001352e`
- `ole32!CoCreateInstance` at `0x18001347f`
- `ole32!CoCreateInstance` at `0x18001347f`

## string_xrefs

- `0x180013534`: `CLSID\`
- `0x1800136aa`: `CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x1800133d8  mov     [rsp-8+arg_10], rbx
0x1800133dd  mov     [rsp-8+arg_18], rsi
0x1800133e2  push    rbp
0x1800133e3  push    rdi
0x1800133e4  push    r12
0x1800133e6  push    r14
0x1800133e8  push    r15
0x1800133ea  lea     rbp, [rsp-140h]
0x1800133f2  sub     rsp, 240h
0x1800133f9  mov     rax, cs:__security_cookie
0x180013400  xor     rax, rsp
0x180013403  mov     [rbp+160h+var_30], rax
0x18001340a  mov     r14d, r8d
0x18001340d  mov     rdi, rdx
0x180013410  mov     rbx, rcx
0x180013413  xor     r15d, r15d
0x180013416  mov     [rsp+260h+var_1F8], r15
0x18001341b  xorps   xmm0, xmm0
0x18001341e  movups  [rbp+160h+var_1C8], xmm0
0x180013422  test    rdx, rdx
0x180013425  jnz     short loc_18001342C
0x180013427  jmp     loc_18001384A
0x18001342c  mov     eax, cs:GUID_NULL.Data1
0x180013432  cmp     [rcx], eax
0x180013434  jnz     short loc_18001345C
0x180013436  mov     eax, dword ptr cs:GUID_NULL.Data2
0x18001343c  cmp     [rcx+4], eax
0x18001343f  jnz     short loc_18001345C
0x180013441  mov     eax, dword ptr cs:GUID_NULL.Data4
0x180013447  cmp     [rcx+8], eax
0x18001344a  jnz     short loc_18001345C
0x18001344c  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x180013452  cmp     [rcx+0Ch], eax
0x180013455  jnz     short loc_18001345C
0x180013457  jmp     loc_18001384A
0x18001345c  lea     rax, [rsp+260h+var_1F8]
0x180013461  mov     [rsp+260h+ppv], rax; ppv
0x180013466  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18001346d  mov     r12d, 1
0x180013473  mov     r8d, r12d; dwClsContext
0x180013476  xor     edx, edx; pUnkOuter
0x180013478  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18001347f  call    cs:__imp_CoCreateInstance
0x180013485  test    eax, eax
0x180013487  jns     loc_18001350D
0x18001348d  jmp     loc_180013833
0x180013492  mov     rax, [rdi+8]
0x180013496  movups  xmm0, xmmword ptr [rax]
0x180013499  movdqu  [rbp+160h+var_1C8], xmm0
0x18001349e  lea     r9, [rbp+160h+var_1C8]
0x1800134a2  mov     r8d, r12d
0x1800134a5  mov     rdx, rbx
0x1800134a8  test    r14d, r14d
0x1800134ab  jz      short loc_1800134ED
0x1800134ad  cmp     ecx, r12d
0x1800134b0  mov     rcx, [rsp+260h+var_1F8]
0x1800134b5  mov     rax, [rcx]
0x1800134b8  jnz     short loc_1800134C0
0x1800134ba  mov     rax, [rax+28h]
0x1800134be  jmp     short loc_1800134C4
0x1800134c0  mov     rax, [rax+38h]
0x1800134c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134c9  mov     esi, eax
0x1800134cb  test    eax, eax
0x1800134cd  jns     short loc_180013509
0x1800134cf  mov     rcx, [rsp+260h+var_1F8]
0x1800134d4  test    rcx, rcx
0x1800134d7  jz      short loc_1800134E6
0x1800134d9  mov     rax, [rcx]
0x1800134dc  mov     rax, [rax+10h]
0x1800134e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134e5  nop
0x1800134e6  mov     eax, esi
0x1800134e8  jmp     loc_18001384C
0x1800134ed  cmp     ecx, r12d
0x1800134f0  mov     rcx, [rsp+260h+var_1F8]
0x1800134f5  mov     rax, [rcx]
0x1800134f8  jnz     short loc_180013500
0x1800134fa  mov     rax, [rax+30h]
0x1800134fe  jmp     short loc_180013504
0x180013500  mov     rax, [rax+40h]
0x180013504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013509  add     rdi, 10h
0x18001350d  mov     ecx, [rdi]
0x18001350f  test    ecx, ecx
0x180013511  jnz     loc_180013492
0x180013517  test    r14d, r14d
0x18001351a  jnz     loc_180013833
0x180013520  lea     r8d, [rcx+40h]; cchMax
0x180013524  lea     rdx, [rbp+160h+sz]; lpsz
0x18001352b  mov     rcx, rbx; rguid
0x18001352e  call    cs:__imp_StringFromGUID2
0x180013534  lea     r8, aClsid; "CLSID\\"
0x18001353b  mov     ebx, 80h
0x180013540  mov     edx, ebx
0x180013542  lea     rcx, [rbp+160h+SubKey]
0x180013546  call    cs:__imp__o_wcscpy_s
0x18001354c  lea     r14d, [rbx-74h]
0x180013550  lea     r12d, [rbx-30h]
0x180013554  test    eax, eax
0x180013556  jz      short loc_18001357C
0x180013558  cmp     eax, r14d
0x18001355b  jz      loc_180013877
0x180013561  cmp     eax, 16h
0x180013564  jz      loc_18001388D
0x18001356a  cmp     eax, 22h ; '"'
0x18001356d  jz      loc_18001388D
0x180013573  cmp     eax, r12d
0x180013576  jnz     loc_180013882
0x18001357c  lea     r8, [rbp+160h+sz]
0x180013583  mov     rdx, rbx
0x180013586  lea     rcx, [rbp+160h+SubKey]
0x18001358a  call    cs:__imp__o_wcscat_s
0x180013590  test    eax, eax
0x180013592  jz      short loc_1800135B8
0x180013594  cmp     eax, r14d
0x180013597  jz      loc_180013877
0x18001359d  cmp     eax, 16h
0x1800135a0  jz      loc_18001388D
0x1800135a6  cmp     eax, 22h ; '"'
0x1800135a9  jz      loc_18001388D
0x1800135af  cmp     eax, r12d
0x1800135b2  jnz     loc_180013882
0x1800135b8  lea     r8, aRequiredCatego; "\\Required Categories"
0x1800135bf  mov     rdx, rbx
0x1800135c2  lea     rcx, [rbp+160h+SubKey]
0x1800135c6  call    cs:__imp__o_wcscat_s
0x1800135cc  test    eax, eax
0x1800135ce  jz      short loc_1800135F4
0x1800135d0  cmp     eax, r14d
0x1800135d3  jz      loc_180013877
0x1800135d9  cmp     eax, 16h
0x1800135dc  jz      loc_18001388D
0x1800135e2  cmp     eax, 22h ; '"'
0x1800135e5  jz      loc_18001388D
0x1800135eb  cmp     eax, r12d
0x1800135ee  jnz     loc_180013882
0x1800135f4  mov     rdi, 0FFFFFFFF80000000h
0x1800135fb  mov     [rbp+160h+var_1E0], rdi
0x1800135ff  mov     [rbp+160h+var_1D8], r15
0x180013603  mov     [rbp+160h+var_1D0], r15
0x180013607  mov     rbx, r15
0x18001360a  mov     [rsp+260h+cSubKeys], r15d
0x18001360f  mov     [rsp+260h+phkResult], r15
0x180013614  lea     rax, [rsp+260h+phkResult]
0x180013619  mov     [rsp+260h+ppv], rax; phkResult
0x18001361e  mov     r9d, 20019h; samDesired
0x180013624  xor     r8d, r8d; ulOptions
0x180013627  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x18001362b  mov     rcx, rdi; hKey
0x18001362e  call    cs:__imp_RegOpenKeyExW
0x180013634  test    eax, eax
0x180013636  jnz     short loc_1800136AA
0x180013638  mov     rbx, [rsp+260h+phkResult]
0x18001363d  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180013642  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180013647  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18001364c  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180013651  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180013656  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18001365b  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180013660  lea     rax, [rsp+260h+cSubKeys]
0x180013665  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18001366a  xor     r9d, r9d; lpReserved
0x18001366d  xor     r8d, r8d; lpcchClass
0x180013670  xor     edx, edx; lpClass
0x180013672  mov     rcx, rbx; hKey
0x180013675  call    cs:__imp_RegQueryInfoKeyW
0x18001367b  mov     esi, eax
0x18001367d  test    rbx, rbx
0x180013680  jz      short loc_18001368E
0x180013682  mov     rcx, rbx; hKey
0x180013685  call    cs:__imp_RegCloseKey
0x18001368b  mov     rbx, r15
0x18001368e  test    esi, esi
0x180013690  jnz     short loc_1800136AA
0x180013692  cmp     [rsp+260h+cSubKeys], r15d
0x180013697  jnz     short loc_1800136AA
0x180013699  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x18001369d  lea     rcx, [rbp+160h+var_1E0]; this
0x1800136a1  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800136a6  mov     rdi, [rbp+160h+var_1E0]
0x1800136aa  lea     r8, aClsid; "CLSID\\"
0x1800136b1  mov     esi, 80h
0x1800136b6  mov     edx, esi
0x1800136b8  lea     rcx, [rbp+160h+SubKey]
0x1800136bc  call    cs:__imp__o_wcscpy_s
0x1800136c2  test    eax, eax
0x1800136c4  jz      short loc_1800136EA
0x1800136c6  cmp     eax, r14d
0x1800136c9  jz      loc_180013877
0x1800136cf  cmp     eax, 16h
0x1800136d2  jz      loc_18001388D
0x1800136d8  cmp     eax, 22h ; '"'
0x1800136db  jz      loc_18001388D
0x1800136e1  cmp     eax, r12d
0x1800136e4  jnz     loc_180013882
0x1800136ea  lea     r8, [rbp+160h+sz]
0x1800136f1  mov     rdx, rsi
0x1800136f4  lea     rcx, [rbp+160h+SubKey]
0x1800136f8  call    cs:__imp__o_wcscat_s
0x1800136fe  test    eax, eax
0x180013700  jz      short loc_180013726
0x180013702  cmp     eax, r14d
0x180013705  jz      loc_180013877
0x18001370b  cmp     eax, 16h
0x18001370e  jz      loc_18001388D
0x180013714  cmp     eax, 22h ; '"'
0x180013717  jz      loc_18001388D
0x18001371d  cmp     eax, r12d
0x180013720  jnz     loc_180013882
0x180013726  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18001372d  mov     rdx, rsi
0x180013730  lea     rcx, [rbp+160h+SubKey]
0x180013734  call    cs:__imp__o_wcscat_s
0x18001373a  test    eax, eax
0x18001373c  jz      short loc_180013762
0x18001373e  cmp     eax, r14d
0x180013741  jz      loc_180013877
0x180013747  cmp     eax, 16h
0x18001374a  jz      loc_18001388D
0x180013750  cmp     eax, 22h ; '"'
0x180013753  jz      loc_18001388D
0x180013759  cmp     eax, r12d
0x18001375c  jnz     loc_180013882
0x180013762  mov     [rsp+260h+hKey], r15
0x180013767  lea     rax, [rsp+260h+hKey]
0x18001376c  mov     [rsp+260h+ppv], rax; phkResult
0x180013771  mov     r9d, 20019h; samDesired
0x180013777  xor     r8d, r8d; ulOptions
0x18001377a  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x18001377e  mov     rcx, rdi; hKey
0x180013781  call    cs:__imp_RegOpenKeyExW
0x180013787  test    eax, eax
0x180013789  jnz     loc_180013816
0x18001378f  mov     eax, r15d
0x180013792  test    rbx, rbx
0x180013795  jz      short loc_1800137A0
0x180013797  mov     rcx, rbx; hKey
0x18001379a  call    cs:__imp_RegCloseKey
0x1800137a0  mov     rbx, [rsp+260h+hKey]
0x1800137a5  test    eax, eax
0x1800137a7  jnz     short loc_180013816
0x1800137a9  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800137ae  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800137b3  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800137b8  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800137bd  mov     [rsp+260h+lpcValues], r15; lpcValues
0x1800137c2  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800137c7  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800137cc  lea     rax, [rsp+260h+cSubKeys]
0x1800137d1  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x1800137d6  xor     r9d, r9d; lpReserved
0x1800137d9  xor     r8d, r8d; lpcchClass
0x1800137dc  xor     edx, edx; lpClass
0x1800137de  mov     rcx, rbx; hKey
0x1800137e1  call    cs:__imp_RegQueryInfoKeyW
0x1800137e7  mov     esi, eax
0x1800137e9  test    rbx, rbx
0x1800137ec  jz      short loc_1800137FA
0x1800137ee  mov     rcx, rbx; hKey
0x1800137f1  call    cs:__imp_RegCloseKey
0x1800137f7  mov     rbx, r15
0x1800137fa  test    esi, esi
0x1800137fc  jnz     short loc_180013824
0x1800137fe  cmp     [rsp+260h+cSubKeys], r15d
0x180013803  jnz     short loc_180013816
0x180013805  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x180013809  lea     rcx, [rbp+160h+var_1E0]; this
0x18001380d  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180013812  mov     rdi, [rbp+160h+var_1E0]
0x180013816  test    rbx, rbx
0x180013819  jz      short loc_180013824
0x18001381b  mov     rcx, rbx; hKey
0x18001381e  call    cs:__imp_RegCloseKey
0x180013824  test    rdi, rdi
0x180013827  jz      short loc_180013833
0x180013829  mov     rcx, rdi; hKey
0x18001382c  call    cs:__imp_RegCloseKey
0x180013832  nop
0x180013833  mov     rcx, [rsp+260h+var_1F8]
0x180013838  test    rcx, rcx
0x18001383b  jz      short loc_18001384A
0x18001383d  mov     rax, [rcx]
0x180013840  mov     rax, [rax+10h]
0x180013844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013849  nop
0x18001384a  xor     eax, eax
0x18001384c  mov     rcx, [rbp+160h+var_30]
0x180013853  xor     rcx, rsp; StackCookie
0x180013856  call    __security_check_cookie
0x18001385b  lea     r11, [rsp+260h+var_20]
0x180013863  mov     rbx, [r11+40h]
0x180013867  mov     rsi, [r11+48h]
0x18001386b  mov     rsp, r11
0x18001386e  pop     r15
0x180013870  pop     r14
0x180013872  pop     r12
0x180013874  pop     rdi
0x180013875  pop     rbp
  ... truncated ...
```
