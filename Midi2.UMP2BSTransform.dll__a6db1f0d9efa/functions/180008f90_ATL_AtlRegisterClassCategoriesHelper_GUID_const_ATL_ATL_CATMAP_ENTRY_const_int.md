# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180008f90`
- end: `0x18000944b`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1211`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009d60`
- `0x180009e50`

## callees

- `0x180001ef0`
- `0x1800047f8`
- `0x180004f10`
- `0x180008f90`
- `0x18000f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000913d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180009179`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800092ab`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800092e7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000913d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180009179`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800092ab`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800092e7`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800090f9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000926f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800090f9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000926f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009032`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009032`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800090e1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800090e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800091e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009334`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800091e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009334`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009238`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000934d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800093a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800093d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800093df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009238`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000934d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800093a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800093d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800093df`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009228`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009394`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009228`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009394`

## string_xrefs

- `0x1800090e7`: `CLSID\`
- `0x18000925d`: `CLSID\`

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
0x180008f90  mov     [rsp-8+arg_10], rbx
0x180008f95  mov     [rsp-8+arg_18], rsi
0x180008f9a  push    rbp
0x180008f9b  push    rdi
0x180008f9c  push    r12
0x180008f9e  push    r14
0x180008fa0  push    r15
0x180008fa2  lea     rbp, [rsp-140h]
0x180008faa  sub     rsp, 240h
0x180008fb1  mov     rax, cs:__security_cookie
0x180008fb8  xor     rax, rsp
0x180008fbb  mov     [rbp+160h+var_30], rax
0x180008fc2  mov     r14d, r8d
0x180008fc5  mov     rdi, rdx
0x180008fc8  mov     rbx, rcx
0x180008fcb  xor     r15d, r15d
0x180008fce  mov     [rsp+260h+var_1F8], r15
0x180008fd3  xorps   xmm0, xmm0
0x180008fd6  movups  [rbp+160h+var_1C8], xmm0
0x180008fda  test    rdx, rdx
0x180008fdd  jnz     short loc_180008FE4
0x180008fdf  jmp     loc_1800093FD
0x180008fe4  cmp     [rcx], r15d
0x180008fe7  jnz     short loc_18000900F
0x180008fe9  mov     eax, dword ptr cs:GUID_NULL.Data2
0x180008fef  cmp     [rcx+4], eax
0x180008ff2  jnz     short loc_18000900F
0x180008ff4  mov     eax, dword ptr cs:GUID_NULL.Data4
0x180008ffa  cmp     [rcx+8], eax
0x180008ffd  jnz     short loc_18000900F
0x180008fff  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x180009005  cmp     [rcx+0Ch], eax
0x180009008  jnz     short loc_18000900F
0x18000900a  jmp     loc_1800093FD
0x18000900f  lea     rax, [rsp+260h+var_1F8]
0x180009014  mov     [rsp+260h+ppv], rax; ppv
0x180009019  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180009020  mov     r12d, 1
0x180009026  mov     r8d, r12d; dwClsContext
0x180009029  xor     edx, edx; pUnkOuter
0x18000902b  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180009032  call    cs:__imp_CoCreateInstance
0x180009038  test    eax, eax
0x18000903a  jns     loc_1800090C0
0x180009040  jmp     loc_1800093E6
0x180009045  mov     rax, [rdi+8]
0x180009049  movups  xmm0, xmmword ptr [rax]
0x18000904c  movdqu  [rbp+160h+var_1C8], xmm0
0x180009051  lea     r9, [rbp+160h+var_1C8]
0x180009055  mov     r8d, r12d
0x180009058  mov     rdx, rbx
0x18000905b  test    r14d, r14d
0x18000905e  jz      short loc_1800090A0
0x180009060  cmp     ecx, r12d
0x180009063  mov     rcx, [rsp+260h+var_1F8]
0x180009068  mov     rax, [rcx]
0x18000906b  jnz     short loc_180009073
0x18000906d  mov     rax, [rax+28h]
0x180009071  jmp     short loc_180009077
0x180009073  mov     rax, [rax+38h]
0x180009077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000907c  mov     esi, eax
0x18000907e  test    eax, eax
0x180009080  jns     short loc_1800090BC
0x180009082  mov     rcx, [rsp+260h+var_1F8]
0x180009087  test    rcx, rcx
0x18000908a  jz      short loc_180009099
0x18000908c  mov     rax, [rcx]
0x18000908f  mov     rax, [rax+10h]
0x180009093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009098  nop
0x180009099  mov     eax, esi
0x18000909b  jmp     loc_1800093FF
0x1800090a0  cmp     ecx, r12d
0x1800090a3  mov     rcx, [rsp+260h+var_1F8]
0x1800090a8  mov     rax, [rcx]
0x1800090ab  jnz     short loc_1800090B3
0x1800090ad  mov     rax, [rax+30h]
0x1800090b1  jmp     short loc_1800090B7
0x1800090b3  mov     rax, [rax+40h]
0x1800090b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090bc  add     rdi, 10h
0x1800090c0  mov     ecx, [rdi]
0x1800090c2  test    ecx, ecx
0x1800090c4  jnz     loc_180009045
0x1800090ca  test    r14d, r14d
0x1800090cd  jnz     loc_1800093E6
0x1800090d3  lea     r8d, [rcx+40h]; cchMax
0x1800090d7  lea     rdx, [rbp+160h+sz]; lpsz
0x1800090de  mov     rcx, rbx; rguid
0x1800090e1  call    cs:__imp_StringFromGUID2
0x1800090e7  lea     r8, aClsid; "CLSID\\"
0x1800090ee  mov     ebx, 80h
0x1800090f3  mov     edx, ebx
0x1800090f5  lea     rcx, [rbp+160h+SubKey]
0x1800090f9  call    cs:__imp__o_wcscpy_s
0x1800090ff  lea     r14d, [rbx-74h]
0x180009103  lea     r12d, [rbx-30h]
0x180009107  test    eax, eax
0x180009109  jz      short loc_18000912F
0x18000910b  cmp     eax, r14d
0x18000910e  jz      loc_18000942A
0x180009114  cmp     eax, 16h
0x180009117  jz      loc_180009440
0x18000911d  cmp     eax, 22h ; '"'
0x180009120  jz      loc_180009440
0x180009126  cmp     eax, r12d
0x180009129  jnz     loc_180009435
0x18000912f  lea     r8, [rbp+160h+sz]
0x180009136  mov     rdx, rbx
0x180009139  lea     rcx, [rbp+160h+SubKey]
0x18000913d  call    cs:__imp__o_wcscat_s
0x180009143  test    eax, eax
0x180009145  jz      short loc_18000916B
0x180009147  cmp     eax, r14d
0x18000914a  jz      loc_18000942A
0x180009150  cmp     eax, 16h
0x180009153  jz      loc_180009440
0x180009159  cmp     eax, 22h ; '"'
0x18000915c  jz      loc_180009440
0x180009162  cmp     eax, r12d
0x180009165  jnz     loc_180009435
0x18000916b  lea     r8, aRequiredCatego; "\\Required Categories"
0x180009172  mov     rdx, rbx
0x180009175  lea     rcx, [rbp+160h+SubKey]
0x180009179  call    cs:__imp__o_wcscat_s
0x18000917f  test    eax, eax
0x180009181  jz      short loc_1800091A7
0x180009183  cmp     eax, r14d
0x180009186  jz      loc_18000942A
0x18000918c  cmp     eax, 16h
0x18000918f  jz      loc_180009440
0x180009195  cmp     eax, 22h ; '"'
0x180009198  jz      loc_180009440
0x18000919e  cmp     eax, r12d
0x1800091a1  jnz     loc_180009435
0x1800091a7  mov     rdi, 0FFFFFFFF80000000h
0x1800091ae  mov     [rbp+160h+var_1E0], rdi
0x1800091b2  mov     [rbp+160h+var_1D8], r15
0x1800091b6  mov     [rbp+160h+var_1D0], r15
0x1800091ba  mov     rbx, r15
0x1800091bd  mov     [rsp+260h+cSubKeys], r15d
0x1800091c2  mov     [rsp+260h+phkResult], r15
0x1800091c7  lea     rax, [rsp+260h+phkResult]
0x1800091cc  mov     [rsp+260h+ppv], rax; phkResult
0x1800091d1  mov     r9d, 20019h; samDesired
0x1800091d7  xor     r8d, r8d; ulOptions
0x1800091da  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x1800091de  mov     rcx, rdi; hKey
0x1800091e1  call    cs:__imp_RegOpenKeyExW
0x1800091e7  test    eax, eax
0x1800091e9  jnz     short loc_18000925D
0x1800091eb  mov     rbx, [rsp+260h+phkResult]
0x1800091f0  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800091f5  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800091fa  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800091ff  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180009204  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180009209  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000920e  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180009213  lea     rax, [rsp+260h+cSubKeys]
0x180009218  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000921d  xor     r9d, r9d; lpReserved
0x180009220  xor     r8d, r8d; lpcchClass
0x180009223  xor     edx, edx; lpClass
0x180009225  mov     rcx, rbx; hKey
0x180009228  call    cs:__imp_RegQueryInfoKeyW
0x18000922e  mov     esi, eax
0x180009230  test    rbx, rbx
0x180009233  jz      short loc_180009241
0x180009235  mov     rcx, rbx; hKey
0x180009238  call    cs:__imp_RegCloseKey
0x18000923e  mov     rbx, r15
0x180009241  test    esi, esi
0x180009243  jnz     short loc_18000925D
0x180009245  cmp     [rsp+260h+cSubKeys], r15d
0x18000924a  jnz     short loc_18000925D
0x18000924c  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x180009250  lea     rcx, [rbp+160h+var_1E0]; this
0x180009254  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180009259  mov     rdi, [rbp+160h+var_1E0]
0x18000925d  lea     r8, aClsid; "CLSID\\"
0x180009264  mov     esi, 80h
0x180009269  mov     edx, esi
0x18000926b  lea     rcx, [rbp+160h+SubKey]
0x18000926f  call    cs:__imp__o_wcscpy_s
0x180009275  test    eax, eax
0x180009277  jz      short loc_18000929D
0x180009279  cmp     eax, r14d
0x18000927c  jz      loc_18000942A
0x180009282  cmp     eax, 16h
0x180009285  jz      loc_180009440
0x18000928b  cmp     eax, 22h ; '"'
0x18000928e  jz      loc_180009440
0x180009294  cmp     eax, r12d
0x180009297  jnz     loc_180009435
0x18000929d  lea     r8, [rbp+160h+sz]
0x1800092a4  mov     rdx, rsi
0x1800092a7  lea     rcx, [rbp+160h+SubKey]
0x1800092ab  call    cs:__imp__o_wcscat_s
0x1800092b1  test    eax, eax
0x1800092b3  jz      short loc_1800092D9
0x1800092b5  cmp     eax, r14d
0x1800092b8  jz      loc_18000942A
0x1800092be  cmp     eax, 16h
0x1800092c1  jz      loc_180009440
0x1800092c7  cmp     eax, 22h ; '"'
0x1800092ca  jz      loc_180009440
0x1800092d0  cmp     eax, r12d
0x1800092d3  jnz     loc_180009435
0x1800092d9  lea     r8, aImplementedCat; "\\Implemented Categories"
0x1800092e0  mov     rdx, rsi
0x1800092e3  lea     rcx, [rbp+160h+SubKey]
0x1800092e7  call    cs:__imp__o_wcscat_s
0x1800092ed  test    eax, eax
0x1800092ef  jz      short loc_180009315
0x1800092f1  cmp     eax, r14d
0x1800092f4  jz      loc_18000942A
0x1800092fa  cmp     eax, 16h
0x1800092fd  jz      loc_180009440
0x180009303  cmp     eax, 22h ; '"'
0x180009306  jz      loc_180009440
0x18000930c  cmp     eax, r12d
0x18000930f  jnz     loc_180009435
0x180009315  mov     [rsp+260h+hKey], r15
0x18000931a  lea     rax, [rsp+260h+hKey]
0x18000931f  mov     [rsp+260h+ppv], rax; phkResult
0x180009324  mov     r9d, 20019h; samDesired
0x18000932a  xor     r8d, r8d; ulOptions
0x18000932d  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x180009331  mov     rcx, rdi; hKey
0x180009334  call    cs:__imp_RegOpenKeyExW
0x18000933a  test    eax, eax
0x18000933c  jnz     loc_1800093C9
0x180009342  mov     eax, r15d
0x180009345  test    rbx, rbx
0x180009348  jz      short loc_180009353
0x18000934a  mov     rcx, rbx; hKey
0x18000934d  call    cs:__imp_RegCloseKey
0x180009353  mov     rbx, [rsp+260h+hKey]
0x180009358  test    eax, eax
0x18000935a  jnz     short loc_1800093C9
0x18000935c  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180009361  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180009366  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000936b  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180009370  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180009375  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000937a  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000937f  lea     rax, [rsp+260h+cSubKeys]
0x180009384  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180009389  xor     r9d, r9d; lpReserved
0x18000938c  xor     r8d, r8d; lpcchClass
0x18000938f  xor     edx, edx; lpClass
0x180009391  mov     rcx, rbx; hKey
0x180009394  call    cs:__imp_RegQueryInfoKeyW
0x18000939a  mov     esi, eax
0x18000939c  test    rbx, rbx
0x18000939f  jz      short loc_1800093AD
0x1800093a1  mov     rcx, rbx; hKey
0x1800093a4  call    cs:__imp_RegCloseKey
0x1800093aa  mov     rbx, r15
0x1800093ad  test    esi, esi
0x1800093af  jnz     short loc_1800093D7
0x1800093b1  cmp     [rsp+260h+cSubKeys], r15d
0x1800093b6  jnz     short loc_1800093C9
0x1800093b8  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x1800093bc  lea     rcx, [rbp+160h+var_1E0]; this
0x1800093c0  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800093c5  mov     rdi, [rbp+160h+var_1E0]
0x1800093c9  test    rbx, rbx
0x1800093cc  jz      short loc_1800093D7
0x1800093ce  mov     rcx, rbx; hKey
0x1800093d1  call    cs:__imp_RegCloseKey
0x1800093d7  test    rdi, rdi
0x1800093da  jz      short loc_1800093E6
0x1800093dc  mov     rcx, rdi; hKey
0x1800093df  call    cs:__imp_RegCloseKey
0x1800093e5  nop
0x1800093e6  mov     rcx, [rsp+260h+var_1F8]
0x1800093eb  test    rcx, rcx
0x1800093ee  jz      short loc_1800093FD
0x1800093f0  mov     rax, [rcx]
0x1800093f3  mov     rax, [rax+10h]
0x1800093f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093fc  nop
0x1800093fd  xor     eax, eax
0x1800093ff  mov     rcx, [rbp+160h+var_30]
0x180009406  xor     rcx, rsp; StackCookie
0x180009409  call    __security_check_cookie
0x18000940e  lea     r11, [rsp+260h+var_20]
0x180009416  mov     rbx, [r11+40h]
0x18000941a  mov     rsi, [r11+48h]
0x18000941e  mov     rsp, r11
0x180009421  pop     r15
0x180009423  pop     r14
0x180009425  pop     r12
0x180009427  pop     rdi
0x180009428  pop     rbp
0x180009429  retn
  ... truncated ...
```
