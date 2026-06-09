# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x1800062a8`
- end: `0x18000675c`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1204`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800092f0`
- `0x1800093e0`

## callees

- `0x1800062a8`
- `0x180006764`
- `0x180006e00`
- `0x180012e00`
- `0x180014010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180006450`
- `msvcrt!wcscat_s` at `0x18000648c`
- `msvcrt!wcscat_s` at `0x1800065be`
- `msvcrt!wcscat_s` at `0x1800065fa`
- `msvcrt!wcscat_s` at `0x180006450`
- `msvcrt!wcscat_s` at `0x18000648c`
- `msvcrt!wcscat_s` at `0x1800065be`
- `msvcrt!wcscat_s` at `0x1800065fa`
- `msvcrt!wcscpy_s` at `0x18000640c`
- `msvcrt!wcscpy_s` at `0x180006582`
- `msvcrt!wcscpy_s` at `0x18000640c`
- `msvcrt!wcscpy_s` at `0x180006582`
- `ADVAPI32!RegOpenKeyExW` at `0x1800064f4`
- `ADVAPI32!RegOpenKeyExW` at `0x180006647`
- `ADVAPI32!RegOpenKeyExW` at `0x1800064f4`
- `ADVAPI32!RegOpenKeyExW` at `0x180006647`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000653b`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800066a7`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000653b`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800066a7`
- `ADVAPI32!RegCloseKey` at `0x18000654b`
- `ADVAPI32!RegCloseKey` at `0x180006660`
- `ADVAPI32!RegCloseKey` at `0x1800066b7`
- `ADVAPI32!RegCloseKey` at `0x1800066e4`
- `ADVAPI32!RegCloseKey` at `0x1800066f2`
- `ADVAPI32!RegCloseKey` at `0x18000654b`
- `ADVAPI32!RegCloseKey` at `0x180006660`
- `ADVAPI32!RegCloseKey` at `0x1800066b7`
- `ADVAPI32!RegCloseKey` at `0x1800066e4`
- `ADVAPI32!RegCloseKey` at `0x1800066f2`
- `ole32!StringFromGUID2` at `0x1800063f4`
- `ole32!StringFromGUID2` at `0x1800063f4`
- `ole32!CoCreateInstance` at `0x18000634d`
- `ole32!CoCreateInstance` at `0x18000634d`

## string_xrefs

- `0x1800063ff`: `CLSID\`
- `0x180006575`: `CLSID\`

## pseudocode

```c
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

  ppv = 0;
  v4 = a2;
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
    goto LABEL_66;
  while ( 1 )
  {
    v11 = *(_DWORD *)v4;
    if ( !*(_DWORD *)v4 )
    {
      if ( !a3 )
      {
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
        v27[1] = 0;
        v27[0] = 0xFFFFFFFF80000000uLL;
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
LABEL_66:
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return 0;
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
0x1800062a8  mov     [rsp-8+arg_10], rbx
0x1800062ad  mov     [rsp-8+arg_18], rsi
0x1800062b2  push    rbp
0x1800062b3  push    rdi
0x1800062b4  push    r12
0x1800062b6  push    r14
0x1800062b8  push    r15
0x1800062ba  lea     rbp, [rsp-140h]
0x1800062c2  sub     rsp, 240h
0x1800062c9  mov     rax, cs:__security_cookie
0x1800062d0  xor     rax, rsp
0x1800062d3  mov     [rbp+160h+var_30], rax
0x1800062da  xor     r15d, r15d
0x1800062dd  xorps   xmm0, xmm0
0x1800062e0  mov     [rsp+260h+var_1F8], r15
0x1800062e5  mov     r14d, r8d
0x1800062e8  mov     rdi, rdx
0x1800062eb  mov     rbx, rcx
0x1800062ee  movups  [rbp+160h+var_1C8], xmm0
0x1800062f2  test    rdx, rdx
0x1800062f5  jz      loc_18000670E
0x1800062fb  mov     eax, cs:GUID_NULL.Data1
0x180006301  cmp     [rcx], eax
0x180006303  jnz     short loc_18000632A
0x180006305  mov     eax, dword ptr cs:GUID_NULL.Data2
0x18000630b  cmp     [rcx+4], eax
0x18000630e  jnz     short loc_18000632A
0x180006310  mov     eax, dword ptr cs:GUID_NULL.Data4
0x180006316  cmp     [rcx+8], eax
0x180006319  jnz     short loc_18000632A
0x18000631b  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x180006321  cmp     [rcx+0Ch], eax
0x180006324  jz      loc_18000670E
0x18000632a  lea     rax, [rsp+260h+var_1F8]
0x18000632f  mov     r12d, 1
0x180006335  mov     r8d, r12d; dwClsContext
0x180006338  mov     [rsp+260h+ppv], rax; ppv
0x18000633d  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180006344  xor     edx, edx; pUnkOuter
0x180006346  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18000634d  call    cs:__imp_CoCreateInstance
0x180006353  test    eax, eax
0x180006355  js      loc_1800066F8
0x18000635b  jmp     short loc_1800063D7
0x18000635d  mov     rax, [rdi+8]
0x180006361  lea     r9, [rbp+160h+var_1C8]
0x180006365  mov     r8d, r12d
0x180006368  mov     rdx, rbx
0x18000636b  movups  xmm0, xmmword ptr [rax]
0x18000636e  movdqu  [rbp+160h+var_1C8], xmm0
0x180006373  test    r14d, r14d
0x180006376  jz      short loc_1800063B7
0x180006378  cmp     ecx, r12d
0x18000637b  mov     rcx, [rsp+260h+var_1F8]
0x180006380  mov     rax, [rcx]
0x180006383  jnz     short loc_18000638B
0x180006385  mov     rax, [rax+28h]
0x180006389  jmp     short loc_18000638F
0x18000638b  mov     rax, [rax+38h]
0x18000638f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006394  mov     esi, eax
0x180006396  test    eax, eax
0x180006398  jns     short loc_1800063D3
0x18000639a  mov     rcx, [rsp+260h+var_1F8]
0x18000639f  test    rcx, rcx
0x1800063a2  jz      short loc_1800063B0
0x1800063a4  mov     rax, [rcx]
0x1800063a7  mov     rax, [rax+10h]
0x1800063ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063b0  mov     eax, esi
0x1800063b2  jmp     loc_180006710
0x1800063b7  cmp     ecx, r12d
0x1800063ba  mov     rcx, [rsp+260h+var_1F8]
0x1800063bf  mov     rax, [rcx]
0x1800063c2  jnz     short loc_1800063CA
0x1800063c4  mov     rax, [rax+30h]
0x1800063c8  jmp     short loc_1800063CE
0x1800063ca  mov     rax, [rax+40h]
0x1800063ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063d3  add     rdi, 10h
0x1800063d7  mov     ecx, [rdi]
0x1800063d9  test    ecx, ecx
0x1800063db  jnz     short loc_18000635D
0x1800063dd  test    r14d, r14d
0x1800063e0  jnz     loc_1800066F8
0x1800063e6  lea     r8d, [rcx+40h]; cchMax
0x1800063ea  mov     rcx, rbx; rguid
0x1800063ed  lea     rdx, [rbp+160h+sz]; lpsz
0x1800063f4  call    cs:__imp_StringFromGUID2
0x1800063fa  mov     ebx, 80h
0x1800063ff  lea     r8, aClsid; "CLSID\\"
0x180006406  mov     edx, ebx; SizeInWords
0x180006408  lea     rcx, [rbp+160h+Destination]; Destination
0x18000640c  call    cs:__imp_wcscpy_s
0x180006412  lea     r14d, [rbx-74h]
0x180006416  lea     r12d, [rbx-30h]
0x18000641a  test    eax, eax
0x18000641c  jz      short loc_180006442
0x18000641e  cmp     eax, r14d
0x180006421  jz      loc_18000673B
0x180006427  cmp     eax, 16h
0x18000642a  jz      loc_180006751
0x180006430  cmp     eax, 22h ; '"'
0x180006433  jz      loc_180006751
0x180006439  cmp     eax, r12d
0x18000643c  jnz     loc_180006746
0x180006442  lea     r8, [rbp+160h+sz]; Source
0x180006449  mov     rdx, rbx; SizeInWords
0x18000644c  lea     rcx, [rbp+160h+Destination]; Destination
0x180006450  call    cs:__imp_wcscat_s
0x180006456  test    eax, eax
0x180006458  jz      short loc_18000647E
0x18000645a  cmp     eax, r14d
0x18000645d  jz      loc_18000673B
0x180006463  cmp     eax, 16h
0x180006466  jz      loc_180006751
0x18000646c  cmp     eax, 22h ; '"'
0x18000646f  jz      loc_180006751
0x180006475  cmp     eax, r12d
0x180006478  jnz     loc_180006746
0x18000647e  lea     r8, aRequiredCatego; "\\Required Categories"
0x180006485  mov     rdx, rbx; SizeInWords
0x180006488  lea     rcx, [rbp+160h+Destination]; Destination
0x18000648c  call    cs:__imp_wcscat_s
0x180006492  test    eax, eax
0x180006494  jz      short loc_1800064BA
0x180006496  cmp     eax, r14d
0x180006499  jz      loc_18000673B
0x18000649f  cmp     eax, 16h
0x1800064a2  jz      loc_180006751
0x1800064a8  cmp     eax, 22h ; '"'
0x1800064ab  jz      loc_180006751
0x1800064b1  cmp     eax, r12d
0x1800064b4  jnz     loc_180006746
0x1800064ba  mov     rdi, 0FFFFFFFF80000000h
0x1800064c1  mov     [rbp+160h+var_1D8], r15
0x1800064c5  lea     rax, [rsp+260h+phkResult]
0x1800064ca  mov     [rbp+160h+var_1E0], rdi
0x1800064ce  mov     rcx, rdi; hKey
0x1800064d1  mov     [rbp+160h+var_1D0], r15
0x1800064d5  mov     r9d, 20019h; samDesired
0x1800064db  mov     [rsp+260h+cSubKeys], r15d
0x1800064e0  xor     r8d, r8d; ulOptions
0x1800064e3  mov     [rsp+260h+phkResult], r15
0x1800064e8  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x1800064ec  mov     [rsp+260h+ppv], rax; phkResult
0x1800064f1  mov     rbx, r15
0x1800064f4  call    cs:__imp_RegOpenKeyExW
0x1800064fa  test    eax, eax
0x1800064fc  jnz     short loc_180006570
0x1800064fe  mov     rbx, [rsp+260h+phkResult]
0x180006503  lea     rax, [rsp+260h+cSubKeys]
0x180006508  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000650d  xor     r9d, r9d; lpReserved
0x180006510  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180006515  xor     r8d, r8d; lpcchClass
0x180006518  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000651d  xor     edx, edx; lpClass
0x18000651f  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180006524  mov     rcx, rbx; hKey
0x180006527  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18000652c  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180006531  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180006536  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000653b  call    cs:__imp_RegQueryInfoKeyW
0x180006541  mov     esi, eax
0x180006543  test    rbx, rbx
0x180006546  jz      short loc_180006554
0x180006548  mov     rcx, rbx; hKey
0x18000654b  call    cs:__imp_RegCloseKey
0x180006551  mov     rbx, r15
0x180006554  test    esi, esi
0x180006556  jnz     short loc_180006570
0x180006558  cmp     [rsp+260h+cSubKeys], r15d
0x18000655d  jnz     short loc_180006570
0x18000655f  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x180006563  lea     rcx, [rbp+160h+var_1E0]; this
0x180006567  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000656c  mov     rdi, [rbp+160h+var_1E0]
0x180006570  mov     esi, 80h
0x180006575  lea     r8, aClsid; "CLSID\\"
0x18000657c  mov     edx, esi; SizeInWords
0x18000657e  lea     rcx, [rbp+160h+Destination]; Destination
0x180006582  call    cs:__imp_wcscpy_s
0x180006588  test    eax, eax
0x18000658a  jz      short loc_1800065B0
0x18000658c  cmp     eax, r14d
0x18000658f  jz      loc_18000673B
0x180006595  cmp     eax, 16h
0x180006598  jz      loc_180006751
0x18000659e  cmp     eax, 22h ; '"'
0x1800065a1  jz      loc_180006751
0x1800065a7  cmp     eax, r12d
0x1800065aa  jnz     loc_180006746
0x1800065b0  lea     r8, [rbp+160h+sz]; Source
0x1800065b7  mov     rdx, rsi; SizeInWords
0x1800065ba  lea     rcx, [rbp+160h+Destination]; Destination
0x1800065be  call    cs:__imp_wcscat_s
0x1800065c4  test    eax, eax
0x1800065c6  jz      short loc_1800065EC
0x1800065c8  cmp     eax, r14d
0x1800065cb  jz      loc_18000673B
0x1800065d1  cmp     eax, 16h
0x1800065d4  jz      loc_180006751
0x1800065da  cmp     eax, 22h ; '"'
0x1800065dd  jz      loc_180006751
0x1800065e3  cmp     eax, r12d
0x1800065e6  jnz     loc_180006746
0x1800065ec  lea     r8, aImplementedCat; "\\Implemented Categories"
0x1800065f3  mov     rdx, rsi; SizeInWords
0x1800065f6  lea     rcx, [rbp+160h+Destination]; Destination
0x1800065fa  call    cs:__imp_wcscat_s
0x180006600  test    eax, eax
0x180006602  jz      short loc_180006628
0x180006604  cmp     eax, r14d
0x180006607  jz      loc_18000673B
0x18000660d  cmp     eax, 16h
0x180006610  jz      loc_180006751
0x180006616  cmp     eax, 22h ; '"'
0x180006619  jz      loc_180006751
0x18000661f  cmp     eax, r12d
0x180006622  jnz     loc_180006746
0x180006628  lea     rax, [rsp+260h+hKey]
0x18000662d  mov     [rsp+260h+hKey], r15
0x180006632  mov     r9d, 20019h; samDesired
0x180006638  mov     [rsp+260h+ppv], rax; phkResult
0x18000663d  xor     r8d, r8d; ulOptions
0x180006640  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x180006644  mov     rcx, rdi; hKey
0x180006647  call    cs:__imp_RegOpenKeyExW
0x18000664d  test    eax, eax
0x18000664f  jnz     loc_1800066DC
0x180006655  mov     eax, r15d
0x180006658  test    rbx, rbx
0x18000665b  jz      short loc_180006666
0x18000665d  mov     rcx, rbx; hKey
0x180006660  call    cs:__imp_RegCloseKey
0x180006666  mov     rbx, [rsp+260h+hKey]
0x18000666b  test    eax, eax
0x18000666d  jnz     short loc_1800066DC
0x18000666f  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180006674  lea     rax, [rsp+260h+cSubKeys]
0x180006679  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000667e  xor     r9d, r9d; lpReserved
0x180006681  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180006686  xor     r8d, r8d; lpcchClass
0x180006689  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000668e  xor     edx, edx; lpClass
0x180006690  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180006695  mov     rcx, rbx; hKey
0x180006698  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000669d  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800066a2  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x1800066a7  call    cs:__imp_RegQueryInfoKeyW
0x1800066ad  mov     esi, eax
0x1800066af  test    rbx, rbx
0x1800066b2  jz      short loc_1800066C0
0x1800066b4  mov     rcx, rbx; hKey
0x1800066b7  call    cs:__imp_RegCloseKey
0x1800066bd  mov     rbx, r15
0x1800066c0  test    esi, esi
0x1800066c2  jnz     short loc_1800066EA
0x1800066c4  cmp     [rsp+260h+cSubKeys], r15d
0x1800066c9  jnz     short loc_1800066DC
0x1800066cb  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x1800066cf  lea     rcx, [rbp+160h+var_1E0]; this
0x1800066d3  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800066d8  mov     rdi, [rbp+160h+var_1E0]
0x1800066dc  test    rbx, rbx
0x1800066df  jz      short loc_1800066EA
0x1800066e1  mov     rcx, rbx; hKey
0x1800066e4  call    cs:__imp_RegCloseKey
0x1800066ea  test    rdi, rdi
0x1800066ed  jz      short loc_1800066F8
0x1800066ef  mov     rcx, rdi; hKey
0x1800066f2  call    cs:__imp_RegCloseKey
0x1800066f8  mov     rcx, [rsp+260h+var_1F8]
0x1800066fd  test    rcx, rcx
0x180006700  jz      short loc_18000670E
0x180006702  mov     rax, [rcx]
0x180006705  mov     rax, [rax+10h]
0x180006709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000670e  xor     eax, eax
0x180006710  mov     rcx, [rbp+160h+var_30]
0x180006717  xor     rcx, rsp; StackCookie
0x18000671a  call    __security_check_cookie
0x18000671f  lea     r11, [rsp+260h+var_20]
0x180006727  mov     rbx, [r11+40h]
0x18000672b  mov     rsi, [r11+48h]
0x18000672f  mov     rsp, r11
0x180006732  pop     r15
0x180006734  pop     r14
0x180006736  pop     r12
0x180006738  pop     rdi
0x180006739  pop     rbp
0x18000673a  retn
0x18000673b  mov     ecx, 8007000Eh; int
0x180006740  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006746  mov     ecx, 80004005h; int
0x18000674b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
  ... truncated ...
```
