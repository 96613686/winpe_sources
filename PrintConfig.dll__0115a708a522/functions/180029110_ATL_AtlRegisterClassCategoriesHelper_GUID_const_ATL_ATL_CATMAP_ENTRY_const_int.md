# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180029110`
- end: `0x18002963a`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1322`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002a390`
- `0x18002a494`
- `0x1800327e0`
- `0x180032a10`

## callees

- `0x180003400`
- `0x1800109e8`
- `0x180029110`
- `0x18002a2ac`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800292d7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180029319`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180029469`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800294ab`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800292d7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180029319`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180029469`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800294ab`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002928d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180029427`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002928d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180029427`
- `ADVAPI32!RegCloseKey` at `0x1800293ea`
- `ADVAPI32!RegCloseKey` at `0x18002951d`
- `ADVAPI32!RegCloseKey` at `0x180029580`
- `ADVAPI32!RegCloseKey` at `0x1800295b3`
- `ADVAPI32!RegCloseKey` at `0x1800295c7`
- `ADVAPI32!RegCloseKey` at `0x1800293ea`
- `ADVAPI32!RegCloseKey` at `0x18002951d`
- `ADVAPI32!RegCloseKey` at `0x180029580`
- `ADVAPI32!RegCloseKey` at `0x1800295b3`
- `ADVAPI32!RegCloseKey` at `0x1800295c7`
- `ADVAPI32!RegOpenKeyExW` at `0x180029387`
- `ADVAPI32!RegOpenKeyExW` at `0x1800294fe`
- `ADVAPI32!RegOpenKeyExW` at `0x180029387`
- `ADVAPI32!RegOpenKeyExW` at `0x1800294fe`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800293d4`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18002956a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800293d4`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18002956a`
- `ole32!CoCreateInstance` at `0x1800291ba`
- `ole32!CoCreateInstance` at `0x1800291ba`
- `ole32!StringFromGUID2` at `0x18002926f`
- `ole32!StringFromGUID2` at `0x18002926f`

## string_xrefs

- `0x18002927b`: `CLSID\`
- `0x180029415`: `CLSID\`

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
0x180029110  mov     rax, rsp
0x180029113  push    rbp
0x180029114  push    rdi
0x180029115  push    r12
0x180029117  push    r14
0x180029119  push    r15
0x18002911b  lea     rbp, [rax-168h]
0x180029122  sub     rsp, 240h
0x180029129  mov     [rbp+160h+var_1C8], 0FFFFFFFFFFFFFFFEh
0x180029131  mov     [rax+18h], rbx
0x180029135  mov     [rax+20h], rsi
0x180029139  mov     rax, cs:__security_cookie
0x180029140  xor     rax, rsp
0x180029143  mov     [rbp+160h+var_30], rax
0x18002914a  mov     r14d, r8d
0x18002914d  mov     rdi, rdx
0x180029150  mov     rbx, rcx
0x180029153  xor     r15d, r15d
0x180029156  mov     [rsp+260h+var_1F8], r15
0x18002915b  xorps   xmm0, xmm0
0x18002915e  movups  [rbp+160h+var_1C0], xmm0
0x180029162  test    rdx, rdx
0x180029165  jnz     short loc_18002916C
0x180029167  jmp     loc_1800295EB
0x18002916c  cmp     [rcx], r15d
0x18002916f  jnz     short loc_180029197
0x180029171  mov     eax, dword ptr cs:GUID_NULL.Data2
0x180029177  cmp     [rcx+4], eax
0x18002917a  jnz     short loc_180029197
0x18002917c  mov     eax, dword ptr cs:GUID_NULL.Data4
0x180029182  cmp     [rcx+8], eax
0x180029185  jnz     short loc_180029197
0x180029187  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x18002918d  cmp     [rcx+0Ch], eax
0x180029190  jnz     short loc_180029197
0x180029192  jmp     loc_1800295EB
0x180029197  lea     rax, [rsp+260h+var_1F8]
0x18002919c  mov     [rsp+260h+ppv], rax; ppv
0x1800291a1  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x1800291a8  mov     r12d, 1
0x1800291ae  mov     r8d, r12d; dwClsContext
0x1800291b1  xor     edx, edx; pUnkOuter
0x1800291b3  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x1800291ba  call    cs:__imp_CoCreateInstance
0x1800291c1  nop     dword ptr [rax+rax+00h]
0x1800291c6  test    eax, eax
0x1800291c8  jns     loc_18002924E
0x1800291ce  jmp     loc_1800295D4
0x1800291d3  mov     rax, [rdi+8]
0x1800291d7  movups  xmm0, xmmword ptr [rax]
0x1800291da  movdqu  [rbp+160h+var_1C0], xmm0
0x1800291df  lea     r9, [rbp+160h+var_1C0]
0x1800291e3  mov     r8d, r12d
0x1800291e6  mov     rdx, rbx
0x1800291e9  test    r14d, r14d
0x1800291ec  jz      short loc_18002922E
0x1800291ee  cmp     ecx, r12d
0x1800291f1  mov     rcx, [rsp+260h+var_1F8]
0x1800291f6  mov     rax, [rcx]
0x1800291f9  jnz     short loc_180029201
0x1800291fb  mov     rax, [rax+28h]
0x1800291ff  jmp     short loc_180029205
0x180029201  mov     rax, [rax+38h]
0x180029205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002920a  mov     esi, eax
0x18002920c  test    eax, eax
0x18002920e  jns     short loc_18002924A
0x180029210  mov     rcx, [rsp+260h+var_1F8]
0x180029215  test    rcx, rcx
0x180029218  jz      short loc_180029227
0x18002921a  mov     rax, [rcx]
0x18002921d  mov     rax, [rax+10h]
0x180029221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029226  nop
0x180029227  mov     eax, esi
0x180029229  jmp     loc_1800295ED
0x18002922e  cmp     ecx, r12d
0x180029231  mov     rcx, [rsp+260h+var_1F8]
0x180029236  mov     rax, [rcx]
0x180029239  jnz     short loc_180029241
0x18002923b  mov     rax, [rax+30h]
0x18002923f  jmp     short loc_180029245
0x180029241  mov     rax, [rax+40h]
0x180029245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002924a  add     rdi, 10h
0x18002924e  mov     ecx, [rdi]
0x180029250  test    ecx, ecx
0x180029252  jnz     loc_1800291D3
0x180029258  test    r14d, r14d
0x18002925b  jnz     loc_1800295D4
0x180029261  lea     r8d, [rcx+40h]; cchMax
0x180029265  lea     rdx, [rbp+160h+sz]; lpsz
0x18002926c  mov     rcx, rbx; rguid
0x18002926f  call    cs:__imp_StringFromGUID2
0x180029276  nop     dword ptr [rax+rax+00h]
0x18002927b  lea     r8, aClsid; "CLSID\\"
0x180029282  mov     ebx, 80h
0x180029287  mov     edx, ebx
0x180029289  lea     rcx, [rbp+160h+SubKey]
0x18002928d  call    cs:__imp__o_wcscpy_s
0x180029294  nop     dword ptr [rax+rax+00h]
0x180029299  lea     r14d, [rbx-74h]
0x18002929d  lea     r12d, [rbx-30h]
0x1800292a1  test    eax, eax
0x1800292a3  jz      short loc_1800292C9
0x1800292a5  cmp     eax, r14d
0x1800292a8  jz      loc_180029619
0x1800292ae  cmp     eax, 16h
0x1800292b1  jz      loc_18002962F
0x1800292b7  cmp     eax, 22h ; '"'
0x1800292ba  jz      loc_18002962F
0x1800292c0  cmp     eax, r12d
0x1800292c3  jnz     loc_180029624
0x1800292c9  lea     r8, [rbp+160h+sz]
0x1800292d0  mov     rdx, rbx
0x1800292d3  lea     rcx, [rbp+160h+SubKey]
0x1800292d7  call    cs:__imp__o_wcscat_s
0x1800292de  nop     dword ptr [rax+rax+00h]
0x1800292e3  test    eax, eax
0x1800292e5  jz      short loc_18002930B
0x1800292e7  cmp     eax, r14d
0x1800292ea  jz      loc_180029619
0x1800292f0  cmp     eax, 16h
0x1800292f3  jz      loc_18002962F
0x1800292f9  cmp     eax, 22h ; '"'
0x1800292fc  jz      loc_18002962F
0x180029302  cmp     eax, r12d
0x180029305  jnz     loc_180029624
0x18002930b  lea     r8, aRequiredCatego; "\\Required Categories"
0x180029312  mov     rdx, rbx
0x180029315  lea     rcx, [rbp+160h+SubKey]
0x180029319  call    cs:__imp__o_wcscat_s
0x180029320  nop     dword ptr [rax+rax+00h]
0x180029325  test    eax, eax
0x180029327  jz      short loc_18002934D
0x180029329  cmp     eax, r14d
0x18002932c  jz      loc_180029619
0x180029332  cmp     eax, 16h
0x180029335  jz      loc_18002962F
0x18002933b  cmp     eax, 22h ; '"'
0x18002933e  jz      loc_18002962F
0x180029344  cmp     eax, r12d
0x180029347  jnz     loc_180029624
0x18002934d  mov     rdi, 0FFFFFFFF80000000h
0x180029354  mov     [rbp+160h+var_1E0], rdi
0x180029358  mov     [rbp+160h+var_1D8], r15
0x18002935c  mov     [rbp+160h+var_1D0], r15
0x180029360  mov     rbx, r15
0x180029363  mov     [rsp+260h+cSubKeys], r15d
0x180029368  mov     [rsp+260h+phkResult], r15
0x18002936d  lea     rax, [rsp+260h+phkResult]
0x180029372  mov     [rsp+260h+ppv], rax; phkResult
0x180029377  mov     r9d, 20019h; samDesired
0x18002937d  xor     r8d, r8d; ulOptions
0x180029380  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x180029384  mov     rcx, rdi; hKey
0x180029387  call    cs:__imp_RegOpenKeyExW
0x18002938e  nop     dword ptr [rax+rax+00h]
0x180029393  test    eax, eax
0x180029395  jnz     short loc_180029415
0x180029397  mov     rbx, [rsp+260h+phkResult]
0x18002939c  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800293a1  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800293a6  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800293ab  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800293b0  mov     [rsp+260h+lpcValues], r15; lpcValues
0x1800293b5  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800293ba  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800293bf  lea     rax, [rsp+260h+cSubKeys]
0x1800293c4  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x1800293c9  xor     r9d, r9d; lpReserved
0x1800293cc  xor     r8d, r8d; lpcchClass
0x1800293cf  xor     edx, edx; lpClass
0x1800293d1  mov     rcx, rbx; hKey
0x1800293d4  call    cs:__imp_RegQueryInfoKeyW
0x1800293db  nop     dword ptr [rax+rax+00h]
0x1800293e0  mov     esi, eax
0x1800293e2  test    rbx, rbx
0x1800293e5  jz      short loc_1800293F9
0x1800293e7  mov     rcx, rbx; hKey
0x1800293ea  call    cs:__imp_RegCloseKey
0x1800293f1  nop     dword ptr [rax+rax+00h]
0x1800293f6  mov     rbx, r15
0x1800293f9  test    esi, esi
0x1800293fb  jnz     short loc_180029415
0x1800293fd  cmp     [rsp+260h+cSubKeys], r15d
0x180029402  jnz     short loc_180029415
0x180029404  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x180029408  lea     rcx, [rbp+160h+var_1E0]; this
0x18002940c  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180029411  mov     rdi, [rbp+160h+var_1E0]
0x180029415  lea     r8, aClsid; "CLSID\\"
0x18002941c  mov     esi, 80h
0x180029421  mov     edx, esi
0x180029423  lea     rcx, [rbp+160h+SubKey]
0x180029427  call    cs:__imp__o_wcscpy_s
0x18002942e  nop     dword ptr [rax+rax+00h]
0x180029433  test    eax, eax
0x180029435  jz      short loc_18002945B
0x180029437  cmp     eax, r14d
0x18002943a  jz      loc_180029619
0x180029440  cmp     eax, 16h
0x180029443  jz      loc_18002962F
0x180029449  cmp     eax, 22h ; '"'
0x18002944c  jz      loc_18002962F
0x180029452  cmp     eax, r12d
0x180029455  jnz     loc_180029624
0x18002945b  lea     r8, [rbp+160h+sz]
0x180029462  mov     rdx, rsi
0x180029465  lea     rcx, [rbp+160h+SubKey]
0x180029469  call    cs:__imp__o_wcscat_s
0x180029470  nop     dword ptr [rax+rax+00h]
0x180029475  test    eax, eax
0x180029477  jz      short loc_18002949D
0x180029479  cmp     eax, r14d
0x18002947c  jz      loc_180029619
0x180029482  cmp     eax, 16h
0x180029485  jz      loc_18002962F
0x18002948b  cmp     eax, 22h ; '"'
0x18002948e  jz      loc_18002962F
0x180029494  cmp     eax, r12d
0x180029497  jnz     loc_180029624
0x18002949d  lea     r8, aImplementedCat; "\\Implemented Categories"
0x1800294a4  mov     rdx, rsi
0x1800294a7  lea     rcx, [rbp+160h+SubKey]
0x1800294ab  call    cs:__imp__o_wcscat_s
0x1800294b2  nop     dword ptr [rax+rax+00h]
0x1800294b7  test    eax, eax
0x1800294b9  jz      short loc_1800294DF
0x1800294bb  cmp     eax, r14d
0x1800294be  jz      loc_180029619
0x1800294c4  cmp     eax, 16h
0x1800294c7  jz      loc_18002962F
0x1800294cd  cmp     eax, 22h ; '"'
0x1800294d0  jz      loc_18002962F
0x1800294d6  cmp     eax, r12d
0x1800294d9  jnz     loc_180029624
0x1800294df  mov     [rsp+260h+hKey], r15
0x1800294e4  lea     rax, [rsp+260h+hKey]
0x1800294e9  mov     [rsp+260h+ppv], rax; phkResult
0x1800294ee  mov     r9d, 20019h; samDesired
0x1800294f4  xor     r8d, r8d; ulOptions
0x1800294f7  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x1800294fb  mov     rcx, rdi; hKey
0x1800294fe  call    cs:__imp_RegOpenKeyExW
0x180029505  nop     dword ptr [rax+rax+00h]
0x18002950a  test    eax, eax
0x18002950c  jnz     loc_1800295AB
0x180029512  mov     eax, r15d
0x180029515  test    rbx, rbx
0x180029518  jz      short loc_180029529
0x18002951a  mov     rcx, rbx; hKey
0x18002951d  call    cs:__imp_RegCloseKey
0x180029524  nop     dword ptr [rax+rax+00h]
0x180029529  mov     rbx, [rsp+260h+hKey]
0x18002952e  test    eax, eax
0x180029530  jnz     short loc_1800295AB
0x180029532  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180029537  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18002953c  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180029541  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180029546  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18002954b  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180029550  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180029555  lea     rax, [rsp+260h+cSubKeys]
0x18002955a  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18002955f  xor     r9d, r9d; lpReserved
0x180029562  xor     r8d, r8d; lpcchClass
0x180029565  xor     edx, edx; lpClass
0x180029567  mov     rcx, rbx; hKey
0x18002956a  call    cs:__imp_RegQueryInfoKeyW
0x180029571  nop     dword ptr [rax+rax+00h]
0x180029576  mov     esi, eax
0x180029578  test    rbx, rbx
0x18002957b  jz      short loc_18002958F
0x18002957d  mov     rcx, rbx; hKey
0x180029580  call    cs:__imp_RegCloseKey
0x180029587  nop     dword ptr [rax+rax+00h]
0x18002958c  mov     rbx, r15
0x18002958f  test    esi, esi
0x180029591  jnz     short loc_1800295BF
0x180029593  cmp     [rsp+260h+cSubKeys], r15d
0x180029598  jnz     short loc_1800295AB
0x18002959a  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x18002959e  lea     rcx, [rbp+160h+var_1E0]; this
0x1800295a2  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800295a7  mov     rdi, [rbp+160h+var_1E0]
0x1800295ab  test    rbx, rbx
0x1800295ae  jz      short loc_1800295BF
0x1800295b0  mov     rcx, rbx; hKey
0x1800295b3  call    cs:__imp_RegCloseKey
0x1800295ba  nop     dword ptr [rax+rax+00h]
0x1800295bf  test    rdi, rdi
0x1800295c2  jz      short loc_1800295D4
0x1800295c4  mov     rcx, rdi; hKey
0x1800295c7  call    cs:__imp_RegCloseKey
0x1800295ce  nop     dword ptr [rax+rax+00h]
0x1800295d3  nop
0x1800295d4  mov     rcx, [rsp+260h+var_1F8]
0x1800295d9  test    rcx, rcx
  ... truncated ...
```
