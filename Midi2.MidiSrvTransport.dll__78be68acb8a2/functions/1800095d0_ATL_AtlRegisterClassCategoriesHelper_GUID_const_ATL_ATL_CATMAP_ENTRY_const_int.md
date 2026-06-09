# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x1800095d0`
- end: `0x180009a90`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1216`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000a470`
- `0x18000a560`

## callees

- `0x180002470`
- `0x180004eb8`
- `0x1800055d0`
- `0x1800095d0`
- `0x180015010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180009782`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800097be`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800098f0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000992c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180009782`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800097be`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800098f0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000992c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000973e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800098b4`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000973e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800098b4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009677`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009677`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009726`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009726`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009826`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009979`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009826`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009979`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000987d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009992`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800099e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009a16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009a24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000987d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009992`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800099e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009a16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009a24`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000986d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800099d9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000986d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800099d9`

## string_xrefs

- `0x18000972c`: `CLSID\`
- `0x1800098a2`: `CLSID\`

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
0x1800095d0  mov     [rsp-8+arg_10], rbx
0x1800095d5  mov     [rsp-8+arg_18], rsi
0x1800095da  push    rbp
0x1800095db  push    rdi
0x1800095dc  push    r12
0x1800095de  push    r14
0x1800095e0  push    r15
0x1800095e2  lea     rbp, [rsp-140h]
0x1800095ea  sub     rsp, 240h
0x1800095f1  mov     rax, cs:__security_cookie
0x1800095f8  xor     rax, rsp
0x1800095fb  mov     [rbp+160h+var_30], rax
0x180009602  mov     r14d, r8d
0x180009605  mov     rdi, rdx
0x180009608  mov     rbx, rcx
0x18000960b  xor     r15d, r15d
0x18000960e  mov     [rsp+260h+var_1F8], r15
0x180009613  xorps   xmm0, xmm0
0x180009616  movups  [rbp+160h+var_1C8], xmm0
0x18000961a  test    rdx, rdx
0x18000961d  jnz     short loc_180009624
0x18000961f  jmp     loc_180009A42
0x180009624  mov     eax, cs:GUID_NULL.Data1
0x18000962a  cmp     [rcx], eax
0x18000962c  jnz     short loc_180009654
0x18000962e  mov     eax, dword ptr cs:GUID_NULL.Data2
0x180009634  cmp     [rcx+4], eax
0x180009637  jnz     short loc_180009654
0x180009639  mov     eax, dword ptr cs:GUID_NULL.Data4
0x18000963f  cmp     [rcx+8], eax
0x180009642  jnz     short loc_180009654
0x180009644  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x18000964a  cmp     [rcx+0Ch], eax
0x18000964d  jnz     short loc_180009654
0x18000964f  jmp     loc_180009A42
0x180009654  lea     rax, [rsp+260h+var_1F8]
0x180009659  mov     [rsp+260h+ppv], rax; ppv
0x18000965e  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180009665  mov     r12d, 1
0x18000966b  mov     r8d, r12d; dwClsContext
0x18000966e  xor     edx, edx; pUnkOuter
0x180009670  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180009677  call    cs:__imp_CoCreateInstance
0x18000967d  test    eax, eax
0x18000967f  jns     loc_180009705
0x180009685  jmp     loc_180009A2B
0x18000968a  mov     rax, [rdi+8]
0x18000968e  movups  xmm0, xmmword ptr [rax]
0x180009691  movdqu  [rbp+160h+var_1C8], xmm0
0x180009696  lea     r9, [rbp+160h+var_1C8]
0x18000969a  mov     r8d, r12d
0x18000969d  mov     rdx, rbx
0x1800096a0  test    r14d, r14d
0x1800096a3  jz      short loc_1800096E5
0x1800096a5  cmp     ecx, r12d
0x1800096a8  mov     rcx, [rsp+260h+var_1F8]
0x1800096ad  mov     rax, [rcx]
0x1800096b0  jnz     short loc_1800096B8
0x1800096b2  mov     rax, [rax+28h]
0x1800096b6  jmp     short loc_1800096BC
0x1800096b8  mov     rax, [rax+38h]
0x1800096bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096c1  mov     esi, eax
0x1800096c3  test    eax, eax
0x1800096c5  jns     short loc_180009701
0x1800096c7  mov     rcx, [rsp+260h+var_1F8]
0x1800096cc  test    rcx, rcx
0x1800096cf  jz      short loc_1800096DE
0x1800096d1  mov     rax, [rcx]
0x1800096d4  mov     rax, [rax+10h]
0x1800096d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096dd  nop
0x1800096de  mov     eax, esi
0x1800096e0  jmp     loc_180009A44
0x1800096e5  cmp     ecx, r12d
0x1800096e8  mov     rcx, [rsp+260h+var_1F8]
0x1800096ed  mov     rax, [rcx]
0x1800096f0  jnz     short loc_1800096F8
0x1800096f2  mov     rax, [rax+30h]
0x1800096f6  jmp     short loc_1800096FC
0x1800096f8  mov     rax, [rax+40h]
0x1800096fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009701  add     rdi, 10h
0x180009705  mov     ecx, [rdi]
0x180009707  test    ecx, ecx
0x180009709  jnz     loc_18000968A
0x18000970f  test    r14d, r14d
0x180009712  jnz     loc_180009A2B
0x180009718  lea     r8d, [rcx+40h]; cchMax
0x18000971c  lea     rdx, [rbp+160h+sz]; lpsz
0x180009723  mov     rcx, rbx; rguid
0x180009726  call    cs:__imp_StringFromGUID2
0x18000972c  lea     r8, aClsid; "CLSID\\"
0x180009733  mov     ebx, 80h
0x180009738  mov     edx, ebx
0x18000973a  lea     rcx, [rbp+160h+SubKey]
0x18000973e  call    cs:__imp__o_wcscpy_s
0x180009744  lea     r14d, [rbx-74h]
0x180009748  lea     r12d, [rbx-30h]
0x18000974c  test    eax, eax
0x18000974e  jz      short loc_180009774
0x180009750  cmp     eax, r14d
0x180009753  jz      loc_180009A6F
0x180009759  cmp     eax, 16h
0x18000975c  jz      loc_180009A85
0x180009762  cmp     eax, 22h ; '"'
0x180009765  jz      loc_180009A85
0x18000976b  cmp     eax, r12d
0x18000976e  jnz     loc_180009A7A
0x180009774  lea     r8, [rbp+160h+sz]
0x18000977b  mov     rdx, rbx
0x18000977e  lea     rcx, [rbp+160h+SubKey]
0x180009782  call    cs:__imp__o_wcscat_s
0x180009788  test    eax, eax
0x18000978a  jz      short loc_1800097B0
0x18000978c  cmp     eax, r14d
0x18000978f  jz      loc_180009A6F
0x180009795  cmp     eax, 16h
0x180009798  jz      loc_180009A85
0x18000979e  cmp     eax, 22h ; '"'
0x1800097a1  jz      loc_180009A85
0x1800097a7  cmp     eax, r12d
0x1800097aa  jnz     loc_180009A7A
0x1800097b0  lea     r8, aRequiredCatego; "\\Required Categories"
0x1800097b7  mov     rdx, rbx
0x1800097ba  lea     rcx, [rbp+160h+SubKey]
0x1800097be  call    cs:__imp__o_wcscat_s
0x1800097c4  test    eax, eax
0x1800097c6  jz      short loc_1800097EC
0x1800097c8  cmp     eax, r14d
0x1800097cb  jz      loc_180009A6F
0x1800097d1  cmp     eax, 16h
0x1800097d4  jz      loc_180009A85
0x1800097da  cmp     eax, 22h ; '"'
0x1800097dd  jz      loc_180009A85
0x1800097e3  cmp     eax, r12d
0x1800097e6  jnz     loc_180009A7A
0x1800097ec  mov     rdi, 0FFFFFFFF80000000h
0x1800097f3  mov     [rbp+160h+var_1E0], rdi
0x1800097f7  mov     [rbp+160h+var_1D8], r15
0x1800097fb  mov     [rbp+160h+var_1D0], r15
0x1800097ff  mov     rbx, r15
0x180009802  mov     [rsp+260h+cSubKeys], r15d
0x180009807  mov     [rsp+260h+phkResult], r15
0x18000980c  lea     rax, [rsp+260h+phkResult]
0x180009811  mov     [rsp+260h+ppv], rax; phkResult
0x180009816  mov     r9d, 20019h; samDesired
0x18000981c  xor     r8d, r8d; ulOptions
0x18000981f  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x180009823  mov     rcx, rdi; hKey
0x180009826  call    cs:__imp_RegOpenKeyExW
0x18000982c  test    eax, eax
0x18000982e  jnz     short loc_1800098A2
0x180009830  mov     rbx, [rsp+260h+phkResult]
0x180009835  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000983a  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000983f  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180009844  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180009849  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18000984e  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180009853  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180009858  lea     rax, [rsp+260h+cSubKeys]
0x18000985d  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180009862  xor     r9d, r9d; lpReserved
0x180009865  xor     r8d, r8d; lpcchClass
0x180009868  xor     edx, edx; lpClass
0x18000986a  mov     rcx, rbx; hKey
0x18000986d  call    cs:__imp_RegQueryInfoKeyW
0x180009873  mov     esi, eax
0x180009875  test    rbx, rbx
0x180009878  jz      short loc_180009886
0x18000987a  mov     rcx, rbx; hKey
0x18000987d  call    cs:__imp_RegCloseKey
0x180009883  mov     rbx, r15
0x180009886  test    esi, esi
0x180009888  jnz     short loc_1800098A2
0x18000988a  cmp     [rsp+260h+cSubKeys], r15d
0x18000988f  jnz     short loc_1800098A2
0x180009891  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x180009895  lea     rcx, [rbp+160h+var_1E0]; this
0x180009899  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000989e  mov     rdi, [rbp+160h+var_1E0]
0x1800098a2  lea     r8, aClsid; "CLSID\\"
0x1800098a9  mov     esi, 80h
0x1800098ae  mov     edx, esi
0x1800098b0  lea     rcx, [rbp+160h+SubKey]
0x1800098b4  call    cs:__imp__o_wcscpy_s
0x1800098ba  test    eax, eax
0x1800098bc  jz      short loc_1800098E2
0x1800098be  cmp     eax, r14d
0x1800098c1  jz      loc_180009A6F
0x1800098c7  cmp     eax, 16h
0x1800098ca  jz      loc_180009A85
0x1800098d0  cmp     eax, 22h ; '"'
0x1800098d3  jz      loc_180009A85
0x1800098d9  cmp     eax, r12d
0x1800098dc  jnz     loc_180009A7A
0x1800098e2  lea     r8, [rbp+160h+sz]
0x1800098e9  mov     rdx, rsi
0x1800098ec  lea     rcx, [rbp+160h+SubKey]
0x1800098f0  call    cs:__imp__o_wcscat_s
0x1800098f6  test    eax, eax
0x1800098f8  jz      short loc_18000991E
0x1800098fa  cmp     eax, r14d
0x1800098fd  jz      loc_180009A6F
0x180009903  cmp     eax, 16h
0x180009906  jz      loc_180009A85
0x18000990c  cmp     eax, 22h ; '"'
0x18000990f  jz      loc_180009A85
0x180009915  cmp     eax, r12d
0x180009918  jnz     loc_180009A7A
0x18000991e  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180009925  mov     rdx, rsi
0x180009928  lea     rcx, [rbp+160h+SubKey]
0x18000992c  call    cs:__imp__o_wcscat_s
0x180009932  test    eax, eax
0x180009934  jz      short loc_18000995A
0x180009936  cmp     eax, r14d
0x180009939  jz      loc_180009A6F
0x18000993f  cmp     eax, 16h
0x180009942  jz      loc_180009A85
0x180009948  cmp     eax, 22h ; '"'
0x18000994b  jz      loc_180009A85
0x180009951  cmp     eax, r12d
0x180009954  jnz     loc_180009A7A
0x18000995a  mov     [rsp+260h+hKey], r15
0x18000995f  lea     rax, [rsp+260h+hKey]
0x180009964  mov     [rsp+260h+ppv], rax; phkResult
0x180009969  mov     r9d, 20019h; samDesired
0x18000996f  xor     r8d, r8d; ulOptions
0x180009972  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x180009976  mov     rcx, rdi; hKey
0x180009979  call    cs:__imp_RegOpenKeyExW
0x18000997f  test    eax, eax
0x180009981  jnz     loc_180009A0E
0x180009987  mov     eax, r15d
0x18000998a  test    rbx, rbx
0x18000998d  jz      short loc_180009998
0x18000998f  mov     rcx, rbx; hKey
0x180009992  call    cs:__imp_RegCloseKey
0x180009998  mov     rbx, [rsp+260h+hKey]
0x18000999d  test    eax, eax
0x18000999f  jnz     short loc_180009A0E
0x1800099a1  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800099a6  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800099ab  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800099b0  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800099b5  mov     [rsp+260h+lpcValues], r15; lpcValues
0x1800099ba  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800099bf  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800099c4  lea     rax, [rsp+260h+cSubKeys]
0x1800099c9  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x1800099ce  xor     r9d, r9d; lpReserved
0x1800099d1  xor     r8d, r8d; lpcchClass
0x1800099d4  xor     edx, edx; lpClass
0x1800099d6  mov     rcx, rbx; hKey
0x1800099d9  call    cs:__imp_RegQueryInfoKeyW
0x1800099df  mov     esi, eax
0x1800099e1  test    rbx, rbx
0x1800099e4  jz      short loc_1800099F2
0x1800099e6  mov     rcx, rbx; hKey
0x1800099e9  call    cs:__imp_RegCloseKey
0x1800099ef  mov     rbx, r15
0x1800099f2  test    esi, esi
0x1800099f4  jnz     short loc_180009A1C
0x1800099f6  cmp     [rsp+260h+cSubKeys], r15d
0x1800099fb  jnz     short loc_180009A0E
0x1800099fd  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x180009a01  lea     rcx, [rbp+160h+var_1E0]; this
0x180009a05  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180009a0a  mov     rdi, [rbp+160h+var_1E0]
0x180009a0e  test    rbx, rbx
0x180009a11  jz      short loc_180009A1C
0x180009a13  mov     rcx, rbx; hKey
0x180009a16  call    cs:__imp_RegCloseKey
0x180009a1c  test    rdi, rdi
0x180009a1f  jz      short loc_180009A2B
0x180009a21  mov     rcx, rdi; hKey
0x180009a24  call    cs:__imp_RegCloseKey
0x180009a2a  nop
0x180009a2b  mov     rcx, [rsp+260h+var_1F8]
0x180009a30  test    rcx, rcx
0x180009a33  jz      short loc_180009A42
0x180009a35  mov     rax, [rcx]
0x180009a38  mov     rax, [rax+10h]
0x180009a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a41  nop
0x180009a42  xor     eax, eax
0x180009a44  mov     rcx, [rbp+160h+var_30]
0x180009a4b  xor     rcx, rsp; StackCookie
0x180009a4e  call    __security_check_cookie
0x180009a53  lea     r11, [rsp+260h+var_20]
0x180009a5b  mov     rbx, [r11+40h]
0x180009a5f  mov     rsi, [r11+48h]
0x180009a63  mov     rsp, r11
0x180009a66  pop     r15
0x180009a68  pop     r14
0x180009a6a  pop     r12
0x180009a6c  pop     rdi
0x180009a6d  pop     rbp
  ... truncated ...
```
