# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x1800090b0`
- end: `0x18000956b`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1211`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009e80`
- `0x180009f70`

## callees

- `0x180002000`
- `0x180004908`
- `0x180005020`
- `0x1800090b0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000925d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180009299`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800093cb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180009407`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000925d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180009299`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800093cb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180009407`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180009219`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000938f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180009219`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000938f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009152`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009152`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009201`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009201`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009348`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800094b4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180009348`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800094b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009358`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000946d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800094c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800094f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800094ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009358`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000946d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800094c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800094f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800094ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009301`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009454`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009301`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009454`

## string_xrefs

- `0x180009207`: `CLSID\`
- `0x18000937d`: `CLSID\`

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
0x1800090b0  mov     [rsp-8+arg_10], rbx
0x1800090b5  mov     [rsp-8+arg_18], rsi
0x1800090ba  push    rbp
0x1800090bb  push    rdi
0x1800090bc  push    r12
0x1800090be  push    r14
0x1800090c0  push    r15
0x1800090c2  lea     rbp, [rsp-140h]
0x1800090ca  sub     rsp, 240h
0x1800090d1  mov     rax, cs:__security_cookie
0x1800090d8  xor     rax, rsp
0x1800090db  mov     [rbp+160h+var_30], rax
0x1800090e2  mov     r14d, r8d
0x1800090e5  mov     rdi, rdx
0x1800090e8  mov     rbx, rcx
0x1800090eb  xor     r15d, r15d
0x1800090ee  mov     [rsp+260h+var_1F8], r15
0x1800090f3  xorps   xmm0, xmm0
0x1800090f6  movups  [rbp+160h+var_1C8], xmm0
0x1800090fa  test    rdx, rdx
0x1800090fd  jnz     short loc_180009104
0x1800090ff  jmp     loc_18000951D
0x180009104  cmp     [rcx], r15d
0x180009107  jnz     short loc_18000912F
0x180009109  mov     eax, dword ptr cs:GUID_NULL.Data2
0x18000910f  cmp     [rcx+4], eax
0x180009112  jnz     short loc_18000912F
0x180009114  mov     eax, dword ptr cs:GUID_NULL.Data4
0x18000911a  cmp     [rcx+8], eax
0x18000911d  jnz     short loc_18000912F
0x18000911f  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x180009125  cmp     [rcx+0Ch], eax
0x180009128  jnz     short loc_18000912F
0x18000912a  jmp     loc_18000951D
0x18000912f  lea     rax, [rsp+260h+var_1F8]
0x180009134  mov     [rsp+260h+ppv], rax; ppv
0x180009139  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180009140  mov     r12d, 1
0x180009146  mov     r8d, r12d; dwClsContext
0x180009149  xor     edx, edx; pUnkOuter
0x18000914b  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180009152  call    cs:__imp_CoCreateInstance
0x180009158  test    eax, eax
0x18000915a  jns     loc_1800091E0
0x180009160  jmp     loc_180009506
0x180009165  mov     rax, [rdi+8]
0x180009169  movups  xmm0, xmmword ptr [rax]
0x18000916c  movdqu  [rbp+160h+var_1C8], xmm0
0x180009171  lea     r9, [rbp+160h+var_1C8]
0x180009175  mov     r8d, r12d
0x180009178  mov     rdx, rbx
0x18000917b  test    r14d, r14d
0x18000917e  jz      short loc_1800091C0
0x180009180  cmp     ecx, r12d
0x180009183  mov     rcx, [rsp+260h+var_1F8]
0x180009188  mov     rax, [rcx]
0x18000918b  jnz     short loc_180009193
0x18000918d  mov     rax, [rax+28h]
0x180009191  jmp     short loc_180009197
0x180009193  mov     rax, [rax+38h]
0x180009197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000919c  mov     esi, eax
0x18000919e  test    eax, eax
0x1800091a0  jns     short loc_1800091DC
0x1800091a2  mov     rcx, [rsp+260h+var_1F8]
0x1800091a7  test    rcx, rcx
0x1800091aa  jz      short loc_1800091B9
0x1800091ac  mov     rax, [rcx]
0x1800091af  mov     rax, [rax+10h]
0x1800091b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091b8  nop
0x1800091b9  mov     eax, esi
0x1800091bb  jmp     loc_18000951F
0x1800091c0  cmp     ecx, r12d
0x1800091c3  mov     rcx, [rsp+260h+var_1F8]
0x1800091c8  mov     rax, [rcx]
0x1800091cb  jnz     short loc_1800091D3
0x1800091cd  mov     rax, [rax+30h]
0x1800091d1  jmp     short loc_1800091D7
0x1800091d3  mov     rax, [rax+40h]
0x1800091d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091dc  add     rdi, 10h
0x1800091e0  mov     ecx, [rdi]
0x1800091e2  test    ecx, ecx
0x1800091e4  jnz     loc_180009165
0x1800091ea  test    r14d, r14d
0x1800091ed  jnz     loc_180009506
0x1800091f3  lea     r8d, [rcx+40h]; cchMax
0x1800091f7  lea     rdx, [rbp+160h+sz]; lpsz
0x1800091fe  mov     rcx, rbx; rguid
0x180009201  call    cs:__imp_StringFromGUID2
0x180009207  lea     r8, aClsid; "CLSID\\"
0x18000920e  mov     ebx, 80h
0x180009213  mov     edx, ebx
0x180009215  lea     rcx, [rbp+160h+SubKey]
0x180009219  call    cs:__imp__o_wcscpy_s
0x18000921f  lea     r14d, [rbx-74h]
0x180009223  lea     r12d, [rbx-30h]
0x180009227  test    eax, eax
0x180009229  jz      short loc_18000924F
0x18000922b  cmp     eax, r14d
0x18000922e  jz      loc_18000954A
0x180009234  cmp     eax, 16h
0x180009237  jz      loc_180009560
0x18000923d  cmp     eax, 22h ; '"'
0x180009240  jz      loc_180009560
0x180009246  cmp     eax, r12d
0x180009249  jnz     loc_180009555
0x18000924f  lea     r8, [rbp+160h+sz]
0x180009256  mov     rdx, rbx
0x180009259  lea     rcx, [rbp+160h+SubKey]
0x18000925d  call    cs:__imp__o_wcscat_s
0x180009263  test    eax, eax
0x180009265  jz      short loc_18000928B
0x180009267  cmp     eax, r14d
0x18000926a  jz      loc_18000954A
0x180009270  cmp     eax, 16h
0x180009273  jz      loc_180009560
0x180009279  cmp     eax, 22h ; '"'
0x18000927c  jz      loc_180009560
0x180009282  cmp     eax, r12d
0x180009285  jnz     loc_180009555
0x18000928b  lea     r8, aRequiredCatego; "\\Required Categories"
0x180009292  mov     rdx, rbx
0x180009295  lea     rcx, [rbp+160h+SubKey]
0x180009299  call    cs:__imp__o_wcscat_s
0x18000929f  test    eax, eax
0x1800092a1  jz      short loc_1800092C7
0x1800092a3  cmp     eax, r14d
0x1800092a6  jz      loc_18000954A
0x1800092ac  cmp     eax, 16h
0x1800092af  jz      loc_180009560
0x1800092b5  cmp     eax, 22h ; '"'
0x1800092b8  jz      loc_180009560
0x1800092be  cmp     eax, r12d
0x1800092c1  jnz     loc_180009555
0x1800092c7  mov     rdi, 0FFFFFFFF80000000h
0x1800092ce  mov     [rbp+160h+var_1E0], rdi
0x1800092d2  mov     [rbp+160h+var_1D8], r15
0x1800092d6  mov     [rbp+160h+var_1D0], r15
0x1800092da  mov     rbx, r15
0x1800092dd  mov     [rsp+260h+cSubKeys], r15d
0x1800092e2  mov     [rsp+260h+phkResult], r15
0x1800092e7  lea     rax, [rsp+260h+phkResult]
0x1800092ec  mov     [rsp+260h+ppv], rax; phkResult
0x1800092f1  mov     r9d, 20019h; samDesired
0x1800092f7  xor     r8d, r8d; ulOptions
0x1800092fa  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x1800092fe  mov     rcx, rdi; hKey
0x180009301  call    cs:__imp_RegOpenKeyExW
0x180009307  test    eax, eax
0x180009309  jnz     short loc_18000937D
0x18000930b  mov     rbx, [rsp+260h+phkResult]
0x180009310  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180009315  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000931a  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000931f  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180009324  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180009329  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000932e  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180009333  lea     rax, [rsp+260h+cSubKeys]
0x180009338  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000933d  xor     r9d, r9d; lpReserved
0x180009340  xor     r8d, r8d; lpcchClass
0x180009343  xor     edx, edx; lpClass
0x180009345  mov     rcx, rbx; hKey
0x180009348  call    cs:__imp_RegQueryInfoKeyW
0x18000934e  mov     esi, eax
0x180009350  test    rbx, rbx
0x180009353  jz      short loc_180009361
0x180009355  mov     rcx, rbx; hKey
0x180009358  call    cs:__imp_RegCloseKey
0x18000935e  mov     rbx, r15
0x180009361  test    esi, esi
0x180009363  jnz     short loc_18000937D
0x180009365  cmp     [rsp+260h+cSubKeys], r15d
0x18000936a  jnz     short loc_18000937D
0x18000936c  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x180009370  lea     rcx, [rbp+160h+var_1E0]; this
0x180009374  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180009379  mov     rdi, [rbp+160h+var_1E0]
0x18000937d  lea     r8, aClsid; "CLSID\\"
0x180009384  mov     esi, 80h
0x180009389  mov     edx, esi
0x18000938b  lea     rcx, [rbp+160h+SubKey]
0x18000938f  call    cs:__imp__o_wcscpy_s
0x180009395  test    eax, eax
0x180009397  jz      short loc_1800093BD
0x180009399  cmp     eax, r14d
0x18000939c  jz      loc_18000954A
0x1800093a2  cmp     eax, 16h
0x1800093a5  jz      loc_180009560
0x1800093ab  cmp     eax, 22h ; '"'
0x1800093ae  jz      loc_180009560
0x1800093b4  cmp     eax, r12d
0x1800093b7  jnz     loc_180009555
0x1800093bd  lea     r8, [rbp+160h+sz]
0x1800093c4  mov     rdx, rsi
0x1800093c7  lea     rcx, [rbp+160h+SubKey]
0x1800093cb  call    cs:__imp__o_wcscat_s
0x1800093d1  test    eax, eax
0x1800093d3  jz      short loc_1800093F9
0x1800093d5  cmp     eax, r14d
0x1800093d8  jz      loc_18000954A
0x1800093de  cmp     eax, 16h
0x1800093e1  jz      loc_180009560
0x1800093e7  cmp     eax, 22h ; '"'
0x1800093ea  jz      loc_180009560
0x1800093f0  cmp     eax, r12d
0x1800093f3  jnz     loc_180009555
0x1800093f9  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180009400  mov     rdx, rsi
0x180009403  lea     rcx, [rbp+160h+SubKey]
0x180009407  call    cs:__imp__o_wcscat_s
0x18000940d  test    eax, eax
0x18000940f  jz      short loc_180009435
0x180009411  cmp     eax, r14d
0x180009414  jz      loc_18000954A
0x18000941a  cmp     eax, 16h
0x18000941d  jz      loc_180009560
0x180009423  cmp     eax, 22h ; '"'
0x180009426  jz      loc_180009560
0x18000942c  cmp     eax, r12d
0x18000942f  jnz     loc_180009555
0x180009435  mov     [rsp+260h+hKey], r15
0x18000943a  lea     rax, [rsp+260h+hKey]
0x18000943f  mov     [rsp+260h+ppv], rax; phkResult
0x180009444  mov     r9d, 20019h; samDesired
0x18000944a  xor     r8d, r8d; ulOptions
0x18000944d  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x180009451  mov     rcx, rdi; hKey
0x180009454  call    cs:__imp_RegOpenKeyExW
0x18000945a  test    eax, eax
0x18000945c  jnz     loc_1800094E9
0x180009462  mov     eax, r15d
0x180009465  test    rbx, rbx
0x180009468  jz      short loc_180009473
0x18000946a  mov     rcx, rbx; hKey
0x18000946d  call    cs:__imp_RegCloseKey
0x180009473  mov     rbx, [rsp+260h+hKey]
0x180009478  test    eax, eax
0x18000947a  jnz     short loc_1800094E9
0x18000947c  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180009481  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180009486  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000948b  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180009490  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180009495  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000949a  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000949f  lea     rax, [rsp+260h+cSubKeys]
0x1800094a4  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x1800094a9  xor     r9d, r9d; lpReserved
0x1800094ac  xor     r8d, r8d; lpcchClass
0x1800094af  xor     edx, edx; lpClass
0x1800094b1  mov     rcx, rbx; hKey
0x1800094b4  call    cs:__imp_RegQueryInfoKeyW
0x1800094ba  mov     esi, eax
0x1800094bc  test    rbx, rbx
0x1800094bf  jz      short loc_1800094CD
0x1800094c1  mov     rcx, rbx; hKey
0x1800094c4  call    cs:__imp_RegCloseKey
0x1800094ca  mov     rbx, r15
0x1800094cd  test    esi, esi
0x1800094cf  jnz     short loc_1800094F7
0x1800094d1  cmp     [rsp+260h+cSubKeys], r15d
0x1800094d6  jnz     short loc_1800094E9
0x1800094d8  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x1800094dc  lea     rcx, [rbp+160h+var_1E0]; this
0x1800094e0  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800094e5  mov     rdi, [rbp+160h+var_1E0]
0x1800094e9  test    rbx, rbx
0x1800094ec  jz      short loc_1800094F7
0x1800094ee  mov     rcx, rbx; hKey
0x1800094f1  call    cs:__imp_RegCloseKey
0x1800094f7  test    rdi, rdi
0x1800094fa  jz      short loc_180009506
0x1800094fc  mov     rcx, rdi; hKey
0x1800094ff  call    cs:__imp_RegCloseKey
0x180009505  nop
0x180009506  mov     rcx, [rsp+260h+var_1F8]
0x18000950b  test    rcx, rcx
0x18000950e  jz      short loc_18000951D
0x180009510  mov     rax, [rcx]
0x180009513  mov     rax, [rax+10h]
0x180009517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000951c  nop
0x18000951d  xor     eax, eax
0x18000951f  mov     rcx, [rbp+160h+var_30]
0x180009526  xor     rcx, rsp; StackCookie
0x180009529  call    __security_check_cookie
0x18000952e  lea     r11, [rsp+260h+var_20]
0x180009536  mov     rbx, [r11+40h]
0x18000953a  mov     rsi, [r11+48h]
0x18000953e  mov     rsp, r11
0x180009541  pop     r15
0x180009543  pop     r14
0x180009545  pop     r12
0x180009547  pop     rdi
0x180009548  pop     rbp
0x180009549  retn
  ... truncated ...
```
