# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x1800093f8`
- end: `0x1800098b8`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1216`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009b74`
- `0x180009e20`

## callees

- `0x180004684`
- `0x180004d78`
- `0x1800093f8`
- `0x18000fc30`
- `0x180012010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x1800095aa`
- `msvcrt!wcscat_s` at `0x1800095e6`
- `msvcrt!wcscat_s` at `0x180009718`
- `msvcrt!wcscat_s` at `0x180009754`
- `msvcrt!wcscat_s` at `0x1800095aa`
- `msvcrt!wcscat_s` at `0x1800095e6`
- `msvcrt!wcscat_s` at `0x180009718`
- `msvcrt!wcscat_s` at `0x180009754`
- `msvcrt!wcscpy_s` at `0x180009566`
- `msvcrt!wcscpy_s` at `0x1800096dc`
- `msvcrt!wcscpy_s` at `0x180009566`
- `msvcrt!wcscpy_s` at `0x1800096dc`
- `ADVAPI32!RegOpenKeyExW` at `0x18000964e`
- `ADVAPI32!RegOpenKeyExW` at `0x1800097a1`
- `ADVAPI32!RegOpenKeyExW` at `0x18000964e`
- `ADVAPI32!RegOpenKeyExW` at `0x1800097a1`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180009695`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180009801`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180009695`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180009801`
- `ADVAPI32!RegCloseKey` at `0x1800096a5`
- `ADVAPI32!RegCloseKey` at `0x1800097ba`
- `ADVAPI32!RegCloseKey` at `0x180009811`
- `ADVAPI32!RegCloseKey` at `0x18000983e`
- `ADVAPI32!RegCloseKey` at `0x18000984c`
- `ADVAPI32!RegCloseKey` at `0x1800096a5`
- `ADVAPI32!RegCloseKey` at `0x1800097ba`
- `ADVAPI32!RegCloseKey` at `0x180009811`
- `ADVAPI32!RegCloseKey` at `0x18000983e`
- `ADVAPI32!RegCloseKey` at `0x18000984c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000949f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000949f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000954e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000954e`

## string_xrefs

- `0x180009554`: `CLSID\`
- `0x1800096ca`: `CLSID\`

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
0x1800093f8  mov     [rsp-8+arg_10], rbx
0x1800093fd  mov     [rsp-8+arg_18], rsi
0x180009402  push    rbp
0x180009403  push    rdi
0x180009404  push    r12
0x180009406  push    r14
0x180009408  push    r15
0x18000940a  lea     rbp, [rsp-140h]
0x180009412  sub     rsp, 240h
0x180009419  mov     rax, cs:__security_cookie
0x180009420  xor     rax, rsp
0x180009423  mov     [rbp+160h+var_30], rax
0x18000942a  mov     r14d, r8d
0x18000942d  mov     rdi, rdx
0x180009430  mov     rbx, rcx
0x180009433  xor     r15d, r15d
0x180009436  mov     [rsp+260h+var_1F8], r15
0x18000943b  xorps   xmm0, xmm0
0x18000943e  movups  [rbp+160h+var_1C8], xmm0
0x180009442  test    rdx, rdx
0x180009445  jnz     short loc_18000944C
0x180009447  jmp     loc_18000986A
0x18000944c  mov     eax, cs:GUID_NULL.Data1
0x180009452  cmp     [rcx], eax
0x180009454  jnz     short loc_18000947C
0x180009456  mov     eax, dword ptr cs:GUID_NULL.Data2
0x18000945c  cmp     [rcx+4], eax
0x18000945f  jnz     short loc_18000947C
0x180009461  mov     eax, dword ptr cs:GUID_NULL.Data4
0x180009467  cmp     [rcx+8], eax
0x18000946a  jnz     short loc_18000947C
0x18000946c  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x180009472  cmp     [rcx+0Ch], eax
0x180009475  jnz     short loc_18000947C
0x180009477  jmp     loc_18000986A
0x18000947c  lea     rax, [rsp+260h+var_1F8]
0x180009481  mov     [rsp+260h+ppv], rax; ppv
0x180009486  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18000948d  mov     r12d, 1
0x180009493  mov     r8d, r12d; dwClsContext
0x180009496  xor     edx, edx; pUnkOuter
0x180009498  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18000949f  call    cs:__imp_CoCreateInstance
0x1800094a5  test    eax, eax
0x1800094a7  jns     loc_18000952D
0x1800094ad  jmp     loc_180009853
0x1800094b2  mov     rax, [rdi+8]
0x1800094b6  movups  xmm0, xmmword ptr [rax]
0x1800094b9  movdqu  [rbp+160h+var_1C8], xmm0
0x1800094be  lea     r9, [rbp+160h+var_1C8]
0x1800094c2  mov     r8d, r12d
0x1800094c5  mov     rdx, rbx
0x1800094c8  test    r14d, r14d
0x1800094cb  jz      short loc_18000950D
0x1800094cd  cmp     ecx, r12d
0x1800094d0  mov     rcx, [rsp+260h+var_1F8]
0x1800094d5  mov     rax, [rcx]
0x1800094d8  jnz     short loc_1800094E0
0x1800094da  mov     rax, [rax+28h]
0x1800094de  jmp     short loc_1800094E4
0x1800094e0  mov     rax, [rax+38h]
0x1800094e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094e9  mov     esi, eax
0x1800094eb  test    eax, eax
0x1800094ed  jns     short loc_180009529
0x1800094ef  mov     rcx, [rsp+260h+var_1F8]
0x1800094f4  test    rcx, rcx
0x1800094f7  jz      short loc_180009506
0x1800094f9  mov     rax, [rcx]
0x1800094fc  mov     rax, [rax+10h]
0x180009500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009505  nop
0x180009506  mov     eax, esi
0x180009508  jmp     loc_18000986C
0x18000950d  cmp     ecx, r12d
0x180009510  mov     rcx, [rsp+260h+var_1F8]
0x180009515  mov     rax, [rcx]
0x180009518  jnz     short loc_180009520
0x18000951a  mov     rax, [rax+30h]
0x18000951e  jmp     short loc_180009524
0x180009520  mov     rax, [rax+40h]
0x180009524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009529  add     rdi, 10h
0x18000952d  mov     ecx, [rdi]
0x18000952f  test    ecx, ecx
0x180009531  jnz     loc_1800094B2
0x180009537  test    r14d, r14d
0x18000953a  jnz     loc_180009853
0x180009540  lea     r8d, [rcx+40h]; cchMax
0x180009544  lea     rdx, [rbp+160h+sz]; lpsz
0x18000954b  mov     rcx, rbx; rguid
0x18000954e  call    cs:__imp_StringFromGUID2
0x180009554  lea     r8, aClsid; "CLSID\\"
0x18000955b  mov     ebx, 80h
0x180009560  mov     edx, ebx; SizeInWords
0x180009562  lea     rcx, [rbp+160h+Destination]; Destination
0x180009566  call    cs:__imp_wcscpy_s
0x18000956c  lea     r14d, [rbx-74h]
0x180009570  lea     r12d, [rbx-30h]
0x180009574  test    eax, eax
0x180009576  jz      short loc_18000959C
0x180009578  cmp     eax, r14d
0x18000957b  jz      loc_180009897
0x180009581  cmp     eax, 16h
0x180009584  jz      loc_1800098AD
0x18000958a  cmp     eax, 22h ; '"'
0x18000958d  jz      loc_1800098AD
0x180009593  cmp     eax, r12d
0x180009596  jnz     loc_1800098A2
0x18000959c  lea     r8, [rbp+160h+sz]; Source
0x1800095a3  mov     rdx, rbx; SizeInWords
0x1800095a6  lea     rcx, [rbp+160h+Destination]; Destination
0x1800095aa  call    cs:__imp_wcscat_s
0x1800095b0  test    eax, eax
0x1800095b2  jz      short loc_1800095D8
0x1800095b4  cmp     eax, r14d
0x1800095b7  jz      loc_180009897
0x1800095bd  cmp     eax, 16h
0x1800095c0  jz      loc_1800098AD
0x1800095c6  cmp     eax, 22h ; '"'
0x1800095c9  jz      loc_1800098AD
0x1800095cf  cmp     eax, r12d
0x1800095d2  jnz     loc_1800098A2
0x1800095d8  lea     r8, aRequiredCatego; "\\Required Categories"
0x1800095df  mov     rdx, rbx; SizeInWords
0x1800095e2  lea     rcx, [rbp+160h+Destination]; Destination
0x1800095e6  call    cs:__imp_wcscat_s
0x1800095ec  test    eax, eax
0x1800095ee  jz      short loc_180009614
0x1800095f0  cmp     eax, r14d
0x1800095f3  jz      loc_180009897
0x1800095f9  cmp     eax, 16h
0x1800095fc  jz      loc_1800098AD
0x180009602  cmp     eax, 22h ; '"'
0x180009605  jz      loc_1800098AD
0x18000960b  cmp     eax, r12d
0x18000960e  jnz     loc_1800098A2
0x180009614  mov     rdi, 0FFFFFFFF80000000h
0x18000961b  mov     [rbp+160h+var_1E0], rdi
0x18000961f  mov     [rbp+160h+var_1D8], r15
0x180009623  mov     [rbp+160h+var_1D0], r15
0x180009627  mov     rbx, r15
0x18000962a  mov     [rsp+260h+cSubKeys], r15d
0x18000962f  mov     [rsp+260h+phkResult], r15
0x180009634  lea     rax, [rsp+260h+phkResult]
0x180009639  mov     [rsp+260h+ppv], rax; phkResult
0x18000963e  mov     r9d, 20019h; samDesired
0x180009644  xor     r8d, r8d; ulOptions
0x180009647  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x18000964b  mov     rcx, rdi; hKey
0x18000964e  call    cs:__imp_RegOpenKeyExW
0x180009654  test    eax, eax
0x180009656  jnz     short loc_1800096CA
0x180009658  mov     rbx, [rsp+260h+phkResult]
0x18000965d  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180009662  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180009667  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000966c  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180009671  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180009676  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000967b  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180009680  lea     rax, [rsp+260h+cSubKeys]
0x180009685  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000968a  xor     r9d, r9d; lpReserved
0x18000968d  xor     r8d, r8d; lpcchClass
0x180009690  xor     edx, edx; lpClass
0x180009692  mov     rcx, rbx; hKey
0x180009695  call    cs:__imp_RegQueryInfoKeyW
0x18000969b  mov     esi, eax
0x18000969d  test    rbx, rbx
0x1800096a0  jz      short loc_1800096AE
0x1800096a2  mov     rcx, rbx; hKey
0x1800096a5  call    cs:__imp_RegCloseKey
0x1800096ab  mov     rbx, r15
0x1800096ae  test    esi, esi
0x1800096b0  jnz     short loc_1800096CA
0x1800096b2  cmp     [rsp+260h+cSubKeys], r15d
0x1800096b7  jnz     short loc_1800096CA
0x1800096b9  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x1800096bd  lea     rcx, [rbp+160h+var_1E0]; this
0x1800096c1  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800096c6  mov     rdi, [rbp+160h+var_1E0]
0x1800096ca  lea     r8, aClsid; "CLSID\\"
0x1800096d1  mov     esi, 80h
0x1800096d6  mov     edx, esi; SizeInWords
0x1800096d8  lea     rcx, [rbp+160h+Destination]; Destination
0x1800096dc  call    cs:__imp_wcscpy_s
0x1800096e2  test    eax, eax
0x1800096e4  jz      short loc_18000970A
0x1800096e6  cmp     eax, r14d
0x1800096e9  jz      loc_180009897
0x1800096ef  cmp     eax, 16h
0x1800096f2  jz      loc_1800098AD
0x1800096f8  cmp     eax, 22h ; '"'
0x1800096fb  jz      loc_1800098AD
0x180009701  cmp     eax, r12d
0x180009704  jnz     loc_1800098A2
0x18000970a  lea     r8, [rbp+160h+sz]; Source
0x180009711  mov     rdx, rsi; SizeInWords
0x180009714  lea     rcx, [rbp+160h+Destination]; Destination
0x180009718  call    cs:__imp_wcscat_s
0x18000971e  test    eax, eax
0x180009720  jz      short loc_180009746
0x180009722  cmp     eax, r14d
0x180009725  jz      loc_180009897
0x18000972b  cmp     eax, 16h
0x18000972e  jz      loc_1800098AD
0x180009734  cmp     eax, 22h ; '"'
0x180009737  jz      loc_1800098AD
0x18000973d  cmp     eax, r12d
0x180009740  jnz     loc_1800098A2
0x180009746  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18000974d  mov     rdx, rsi; SizeInWords
0x180009750  lea     rcx, [rbp+160h+Destination]; Destination
0x180009754  call    cs:__imp_wcscat_s
0x18000975a  test    eax, eax
0x18000975c  jz      short loc_180009782
0x18000975e  cmp     eax, r14d
0x180009761  jz      loc_180009897
0x180009767  cmp     eax, 16h
0x18000976a  jz      loc_1800098AD
0x180009770  cmp     eax, 22h ; '"'
0x180009773  jz      loc_1800098AD
0x180009779  cmp     eax, r12d
0x18000977c  jnz     loc_1800098A2
0x180009782  mov     [rsp+260h+hKey], r15
0x180009787  lea     rax, [rsp+260h+hKey]
0x18000978c  mov     [rsp+260h+ppv], rax; phkResult
0x180009791  mov     r9d, 20019h; samDesired
0x180009797  xor     r8d, r8d; ulOptions
0x18000979a  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x18000979e  mov     rcx, rdi; hKey
0x1800097a1  call    cs:__imp_RegOpenKeyExW
0x1800097a7  test    eax, eax
0x1800097a9  jnz     loc_180009836
0x1800097af  mov     eax, r15d
0x1800097b2  test    rbx, rbx
0x1800097b5  jz      short loc_1800097C0
0x1800097b7  mov     rcx, rbx; hKey
0x1800097ba  call    cs:__imp_RegCloseKey
0x1800097c0  mov     rbx, [rsp+260h+hKey]
0x1800097c5  test    eax, eax
0x1800097c7  jnz     short loc_180009836
0x1800097c9  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800097ce  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800097d3  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800097d8  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800097dd  mov     [rsp+260h+lpcValues], r15; lpcValues
0x1800097e2  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800097e7  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800097ec  lea     rax, [rsp+260h+cSubKeys]
0x1800097f1  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x1800097f6  xor     r9d, r9d; lpReserved
0x1800097f9  xor     r8d, r8d; lpcchClass
0x1800097fc  xor     edx, edx; lpClass
0x1800097fe  mov     rcx, rbx; hKey
0x180009801  call    cs:__imp_RegQueryInfoKeyW
0x180009807  mov     esi, eax
0x180009809  test    rbx, rbx
0x18000980c  jz      short loc_18000981A
0x18000980e  mov     rcx, rbx; hKey
0x180009811  call    cs:__imp_RegCloseKey
0x180009817  mov     rbx, r15
0x18000981a  test    esi, esi
0x18000981c  jnz     short loc_180009844
0x18000981e  cmp     [rsp+260h+cSubKeys], r15d
0x180009823  jnz     short loc_180009836
0x180009825  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x180009829  lea     rcx, [rbp+160h+var_1E0]; this
0x18000982d  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180009832  mov     rdi, [rbp+160h+var_1E0]
0x180009836  test    rbx, rbx
0x180009839  jz      short loc_180009844
0x18000983b  mov     rcx, rbx; hKey
0x18000983e  call    cs:__imp_RegCloseKey
0x180009844  test    rdi, rdi
0x180009847  jz      short loc_180009853
0x180009849  mov     rcx, rdi; hKey
0x18000984c  call    cs:__imp_RegCloseKey
0x180009852  nop
0x180009853  mov     rcx, [rsp+260h+var_1F8]
0x180009858  test    rcx, rcx
0x18000985b  jz      short loc_18000986A
0x18000985d  mov     rax, [rcx]
0x180009860  mov     rax, [rax+10h]
0x180009864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009869  nop
0x18000986a  xor     eax, eax
0x18000986c  mov     rcx, [rbp+160h+var_30]
0x180009873  xor     rcx, rsp; StackCookie
0x180009876  call    __security_check_cookie
0x18000987b  lea     r11, [rsp+260h+var_20]
0x180009883  mov     rbx, [r11+40h]
0x180009887  mov     rsi, [r11+48h]
0x18000988b  mov     rsp, r11
0x18000988e  pop     r15
0x180009890  pop     r14
0x180009892  pop     r12
0x180009894  pop     rdi
0x180009895  pop     rbp
  ... truncated ...
```
