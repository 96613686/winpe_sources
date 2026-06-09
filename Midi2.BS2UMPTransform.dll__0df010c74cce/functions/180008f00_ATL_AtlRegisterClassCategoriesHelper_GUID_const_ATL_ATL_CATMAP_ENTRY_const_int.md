# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180008f00`
- end: `0x1800093bb`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1211`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009cd0`
- `0x180009dc0`

## callees

- `0x180001e60`
- `0x180004768`
- `0x180004e80`
- `0x180008f00`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800090ad`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800090e9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000921b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180009257`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800090ad`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800090e9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000921b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180009257`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180009069`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800091df`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180009069`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800091df`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008fa2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008fa2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009051`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009051`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009198`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009304`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009198`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009304`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800091a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800092bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009314`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009341`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000934f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800091a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800092bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009314`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009341`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000934f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009151`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800092a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009151`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800092a4`

## string_xrefs

- `0x180009057`: `CLSID\`
- `0x1800091cd`: `CLSID\`

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
0x180008f00  mov     [rsp-8+arg_10], rbx
0x180008f05  mov     [rsp-8+arg_18], rsi
0x180008f0a  push    rbp
0x180008f0b  push    rdi
0x180008f0c  push    r12
0x180008f0e  push    r14
0x180008f10  push    r15
0x180008f12  lea     rbp, [rsp-140h]
0x180008f1a  sub     rsp, 240h
0x180008f21  mov     rax, cs:__security_cookie
0x180008f28  xor     rax, rsp
0x180008f2b  mov     [rbp+160h+var_30], rax
0x180008f32  mov     r14d, r8d
0x180008f35  mov     rdi, rdx
0x180008f38  mov     rbx, rcx
0x180008f3b  xor     r15d, r15d
0x180008f3e  mov     [rsp+260h+var_1F8], r15
0x180008f43  xorps   xmm0, xmm0
0x180008f46  movups  [rbp+160h+var_1C8], xmm0
0x180008f4a  test    rdx, rdx
0x180008f4d  jnz     short loc_180008F54
0x180008f4f  jmp     loc_18000936D
0x180008f54  cmp     [rcx], r15d
0x180008f57  jnz     short loc_180008F7F
0x180008f59  mov     eax, dword ptr cs:GUID_NULL.Data2
0x180008f5f  cmp     [rcx+4], eax
0x180008f62  jnz     short loc_180008F7F
0x180008f64  mov     eax, dword ptr cs:GUID_NULL.Data4
0x180008f6a  cmp     [rcx+8], eax
0x180008f6d  jnz     short loc_180008F7F
0x180008f6f  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x180008f75  cmp     [rcx+0Ch], eax
0x180008f78  jnz     short loc_180008F7F
0x180008f7a  jmp     loc_18000936D
0x180008f7f  lea     rax, [rsp+260h+var_1F8]
0x180008f84  mov     [rsp+260h+ppv], rax; ppv
0x180008f89  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180008f90  mov     r12d, 1
0x180008f96  mov     r8d, r12d; dwClsContext
0x180008f99  xor     edx, edx; pUnkOuter
0x180008f9b  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180008fa2  call    cs:__imp_CoCreateInstance
0x180008fa8  test    eax, eax
0x180008faa  jns     loc_180009030
0x180008fb0  jmp     loc_180009356
0x180008fb5  mov     rax, [rdi+8]
0x180008fb9  movups  xmm0, xmmword ptr [rax]
0x180008fbc  movdqu  [rbp+160h+var_1C8], xmm0
0x180008fc1  lea     r9, [rbp+160h+var_1C8]
0x180008fc5  mov     r8d, r12d
0x180008fc8  mov     rdx, rbx
0x180008fcb  test    r14d, r14d
0x180008fce  jz      short loc_180009010
0x180008fd0  cmp     ecx, r12d
0x180008fd3  mov     rcx, [rsp+260h+var_1F8]
0x180008fd8  mov     rax, [rcx]
0x180008fdb  jnz     short loc_180008FE3
0x180008fdd  mov     rax, [rax+28h]
0x180008fe1  jmp     short loc_180008FE7
0x180008fe3  mov     rax, [rax+38h]
0x180008fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fec  mov     esi, eax
0x180008fee  test    eax, eax
0x180008ff0  jns     short loc_18000902C
0x180008ff2  mov     rcx, [rsp+260h+var_1F8]
0x180008ff7  test    rcx, rcx
0x180008ffa  jz      short loc_180009009
0x180008ffc  mov     rax, [rcx]
0x180008fff  mov     rax, [rax+10h]
0x180009003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009008  nop
0x180009009  mov     eax, esi
0x18000900b  jmp     loc_18000936F
0x180009010  cmp     ecx, r12d
0x180009013  mov     rcx, [rsp+260h+var_1F8]
0x180009018  mov     rax, [rcx]
0x18000901b  jnz     short loc_180009023
0x18000901d  mov     rax, [rax+30h]
0x180009021  jmp     short loc_180009027
0x180009023  mov     rax, [rax+40h]
0x180009027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000902c  add     rdi, 10h
0x180009030  mov     ecx, [rdi]
0x180009032  test    ecx, ecx
0x180009034  jnz     loc_180008FB5
0x18000903a  test    r14d, r14d
0x18000903d  jnz     loc_180009356
0x180009043  lea     r8d, [rcx+40h]; cchMax
0x180009047  lea     rdx, [rbp+160h+sz]; lpsz
0x18000904e  mov     rcx, rbx; rguid
0x180009051  call    cs:__imp_StringFromGUID2
0x180009057  lea     r8, aClsid; "CLSID\\"
0x18000905e  mov     ebx, 80h
0x180009063  mov     edx, ebx
0x180009065  lea     rcx, [rbp+160h+SubKey]
0x180009069  call    cs:__imp__o_wcscpy_s
0x18000906f  lea     r14d, [rbx-74h]
0x180009073  lea     r12d, [rbx-30h]
0x180009077  test    eax, eax
0x180009079  jz      short loc_18000909F
0x18000907b  cmp     eax, r14d
0x18000907e  jz      loc_18000939A
0x180009084  cmp     eax, 16h
0x180009087  jz      loc_1800093B0
0x18000908d  cmp     eax, 22h ; '"'
0x180009090  jz      loc_1800093B0
0x180009096  cmp     eax, r12d
0x180009099  jnz     loc_1800093A5
0x18000909f  lea     r8, [rbp+160h+sz]
0x1800090a6  mov     rdx, rbx
0x1800090a9  lea     rcx, [rbp+160h+SubKey]
0x1800090ad  call    cs:__imp__o_wcscat_s
0x1800090b3  test    eax, eax
0x1800090b5  jz      short loc_1800090DB
0x1800090b7  cmp     eax, r14d
0x1800090ba  jz      loc_18000939A
0x1800090c0  cmp     eax, 16h
0x1800090c3  jz      loc_1800093B0
0x1800090c9  cmp     eax, 22h ; '"'
0x1800090cc  jz      loc_1800093B0
0x1800090d2  cmp     eax, r12d
0x1800090d5  jnz     loc_1800093A5
0x1800090db  lea     r8, aRequiredCatego; "\\Required Categories"
0x1800090e2  mov     rdx, rbx
0x1800090e5  lea     rcx, [rbp+160h+SubKey]
0x1800090e9  call    cs:__imp__o_wcscat_s
0x1800090ef  test    eax, eax
0x1800090f1  jz      short loc_180009117
0x1800090f3  cmp     eax, r14d
0x1800090f6  jz      loc_18000939A
0x1800090fc  cmp     eax, 16h
0x1800090ff  jz      loc_1800093B0
0x180009105  cmp     eax, 22h ; '"'
0x180009108  jz      loc_1800093B0
0x18000910e  cmp     eax, r12d
0x180009111  jnz     loc_1800093A5
0x180009117  mov     rdi, 0FFFFFFFF80000000h
0x18000911e  mov     [rbp+160h+var_1E0], rdi
0x180009122  mov     [rbp+160h+var_1D8], r15
0x180009126  mov     [rbp+160h+var_1D0], r15
0x18000912a  mov     rbx, r15
0x18000912d  mov     [rsp+260h+cSubKeys], r15d
0x180009132  mov     [rsp+260h+phkResult], r15
0x180009137  lea     rax, [rsp+260h+phkResult]
0x18000913c  mov     [rsp+260h+ppv], rax; phkResult
0x180009141  mov     r9d, 20019h; samDesired
0x180009147  xor     r8d, r8d; ulOptions
0x18000914a  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x18000914e  mov     rcx, rdi; hKey
0x180009151  call    cs:__imp_RegOpenKeyExW
0x180009157  test    eax, eax
0x180009159  jnz     short loc_1800091CD
0x18000915b  mov     rbx, [rsp+260h+phkResult]
0x180009160  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180009165  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000916a  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000916f  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180009174  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180009179  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000917e  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180009183  lea     rax, [rsp+260h+cSubKeys]
0x180009188  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000918d  xor     r9d, r9d; lpReserved
0x180009190  xor     r8d, r8d; lpcchClass
0x180009193  xor     edx, edx; lpClass
0x180009195  mov     rcx, rbx; hKey
0x180009198  call    cs:__imp_RegQueryInfoKeyW
0x18000919e  mov     esi, eax
0x1800091a0  test    rbx, rbx
0x1800091a3  jz      short loc_1800091B1
0x1800091a5  mov     rcx, rbx; hKey
0x1800091a8  call    cs:__imp_RegCloseKey
0x1800091ae  mov     rbx, r15
0x1800091b1  test    esi, esi
0x1800091b3  jnz     short loc_1800091CD
0x1800091b5  cmp     [rsp+260h+cSubKeys], r15d
0x1800091ba  jnz     short loc_1800091CD
0x1800091bc  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x1800091c0  lea     rcx, [rbp+160h+var_1E0]; this
0x1800091c4  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800091c9  mov     rdi, [rbp+160h+var_1E0]
0x1800091cd  lea     r8, aClsid; "CLSID\\"
0x1800091d4  mov     esi, 80h
0x1800091d9  mov     edx, esi
0x1800091db  lea     rcx, [rbp+160h+SubKey]
0x1800091df  call    cs:__imp__o_wcscpy_s
0x1800091e5  test    eax, eax
0x1800091e7  jz      short loc_18000920D
0x1800091e9  cmp     eax, r14d
0x1800091ec  jz      loc_18000939A
0x1800091f2  cmp     eax, 16h
0x1800091f5  jz      loc_1800093B0
0x1800091fb  cmp     eax, 22h ; '"'
0x1800091fe  jz      loc_1800093B0
0x180009204  cmp     eax, r12d
0x180009207  jnz     loc_1800093A5
0x18000920d  lea     r8, [rbp+160h+sz]
0x180009214  mov     rdx, rsi
0x180009217  lea     rcx, [rbp+160h+SubKey]
0x18000921b  call    cs:__imp__o_wcscat_s
0x180009221  test    eax, eax
0x180009223  jz      short loc_180009249
0x180009225  cmp     eax, r14d
0x180009228  jz      loc_18000939A
0x18000922e  cmp     eax, 16h
0x180009231  jz      loc_1800093B0
0x180009237  cmp     eax, 22h ; '"'
0x18000923a  jz      loc_1800093B0
0x180009240  cmp     eax, r12d
0x180009243  jnz     loc_1800093A5
0x180009249  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180009250  mov     rdx, rsi
0x180009253  lea     rcx, [rbp+160h+SubKey]
0x180009257  call    cs:__imp__o_wcscat_s
0x18000925d  test    eax, eax
0x18000925f  jz      short loc_180009285
0x180009261  cmp     eax, r14d
0x180009264  jz      loc_18000939A
0x18000926a  cmp     eax, 16h
0x18000926d  jz      loc_1800093B0
0x180009273  cmp     eax, 22h ; '"'
0x180009276  jz      loc_1800093B0
0x18000927c  cmp     eax, r12d
0x18000927f  jnz     loc_1800093A5
0x180009285  mov     [rsp+260h+hKey], r15
0x18000928a  lea     rax, [rsp+260h+hKey]
0x18000928f  mov     [rsp+260h+ppv], rax; phkResult
0x180009294  mov     r9d, 20019h; samDesired
0x18000929a  xor     r8d, r8d; ulOptions
0x18000929d  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x1800092a1  mov     rcx, rdi; hKey
0x1800092a4  call    cs:__imp_RegOpenKeyExW
0x1800092aa  test    eax, eax
0x1800092ac  jnz     loc_180009339
0x1800092b2  mov     eax, r15d
0x1800092b5  test    rbx, rbx
0x1800092b8  jz      short loc_1800092C3
0x1800092ba  mov     rcx, rbx; hKey
0x1800092bd  call    cs:__imp_RegCloseKey
0x1800092c3  mov     rbx, [rsp+260h+hKey]
0x1800092c8  test    eax, eax
0x1800092ca  jnz     short loc_180009339
0x1800092cc  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800092d1  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800092d6  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800092db  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800092e0  mov     [rsp+260h+lpcValues], r15; lpcValues
0x1800092e5  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800092ea  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800092ef  lea     rax, [rsp+260h+cSubKeys]
0x1800092f4  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x1800092f9  xor     r9d, r9d; lpReserved
0x1800092fc  xor     r8d, r8d; lpcchClass
0x1800092ff  xor     edx, edx; lpClass
0x180009301  mov     rcx, rbx; hKey
0x180009304  call    cs:__imp_RegQueryInfoKeyW
0x18000930a  mov     esi, eax
0x18000930c  test    rbx, rbx
0x18000930f  jz      short loc_18000931D
0x180009311  mov     rcx, rbx; hKey
0x180009314  call    cs:__imp_RegCloseKey
0x18000931a  mov     rbx, r15
0x18000931d  test    esi, esi
0x18000931f  jnz     short loc_180009347
0x180009321  cmp     [rsp+260h+cSubKeys], r15d
0x180009326  jnz     short loc_180009339
0x180009328  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x18000932c  lea     rcx, [rbp+160h+var_1E0]; this
0x180009330  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180009335  mov     rdi, [rbp+160h+var_1E0]
0x180009339  test    rbx, rbx
0x18000933c  jz      short loc_180009347
0x18000933e  mov     rcx, rbx; hKey
0x180009341  call    cs:__imp_RegCloseKey
0x180009347  test    rdi, rdi
0x18000934a  jz      short loc_180009356
0x18000934c  mov     rcx, rdi; hKey
0x18000934f  call    cs:__imp_RegCloseKey
0x180009355  nop
0x180009356  mov     rcx, [rsp+260h+var_1F8]
0x18000935b  test    rcx, rcx
0x18000935e  jz      short loc_18000936D
0x180009360  mov     rax, [rcx]
0x180009363  mov     rax, [rax+10h]
0x180009367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000936c  nop
0x18000936d  xor     eax, eax
0x18000936f  mov     rcx, [rbp+160h+var_30]
0x180009376  xor     rcx, rsp; StackCookie
0x180009379  call    __security_check_cookie
0x18000937e  lea     r11, [rsp+260h+var_20]
0x180009386  mov     rbx, [r11+40h]
0x18000938a  mov     rsi, [r11+48h]
0x18000938e  mov     rsp, r11
0x180009391  pop     r15
0x180009393  pop     r14
0x180009395  pop     r12
0x180009397  pop     rdi
0x180009398  pop     rbp
0x180009399  retn
  ... truncated ...
```
