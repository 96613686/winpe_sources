# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180004098`
- end: `0x180004553`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1211`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006234`
- `0x180006ba0`
- `0x180006ca0`

## callees

- `0x180004098`
- `0x180004740`
- `0x180004be8`
- `0x180019760`
- `0x18001b010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180004245`
- `msvcrt!wcscat_s` at `0x180004281`
- `msvcrt!wcscat_s` at `0x1800043b3`
- `msvcrt!wcscat_s` at `0x1800043ef`
- `msvcrt!wcscat_s` at `0x180004245`
- `msvcrt!wcscat_s` at `0x180004281`
- `msvcrt!wcscat_s` at `0x1800043b3`
- `msvcrt!wcscat_s` at `0x1800043ef`
- `msvcrt!wcscpy_s` at `0x180004201`
- `msvcrt!wcscpy_s` at `0x180004377`
- `msvcrt!wcscpy_s` at `0x180004201`
- `msvcrt!wcscpy_s` at `0x180004377`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000413a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000413a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800041e9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800041e9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180004330`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000449c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180004330`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000449c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004340`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004455`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800044ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800044d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800044e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004340`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004455`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800044ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800044d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800044e7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800042e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000443c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800042e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000443c`

## string_xrefs

- `0x1800041ef`: `CLSID\`
- `0x180004365`: `CLSID\`

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
0x180004098  mov     [rsp-8+arg_10], rbx
0x18000409d  mov     [rsp-8+arg_18], rsi
0x1800040a2  push    rbp
0x1800040a3  push    rdi
0x1800040a4  push    r12
0x1800040a6  push    r14
0x1800040a8  push    r15
0x1800040aa  lea     rbp, [rsp-140h]
0x1800040b2  sub     rsp, 240h
0x1800040b9  mov     rax, cs:__security_cookie
0x1800040c0  xor     rax, rsp
0x1800040c3  mov     [rbp+160h+var_30], rax
0x1800040ca  mov     r14d, r8d
0x1800040cd  mov     rdi, rdx
0x1800040d0  mov     rbx, rcx
0x1800040d3  xor     r15d, r15d
0x1800040d6  mov     [rsp+260h+var_1F8], r15
0x1800040db  xorps   xmm0, xmm0
0x1800040de  movups  [rbp+160h+var_1C8], xmm0
0x1800040e2  test    rdx, rdx
0x1800040e5  jnz     short loc_1800040EC
0x1800040e7  jmp     loc_180004505
0x1800040ec  cmp     [rcx], r15d
0x1800040ef  jnz     short loc_180004117
0x1800040f1  mov     eax, dword ptr cs:GUID_NULL.Data2
0x1800040f7  cmp     [rcx+4], eax
0x1800040fa  jnz     short loc_180004117
0x1800040fc  mov     eax, dword ptr cs:GUID_NULL.Data4
0x180004102  cmp     [rcx+8], eax
0x180004105  jnz     short loc_180004117
0x180004107  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x18000410d  cmp     [rcx+0Ch], eax
0x180004110  jnz     short loc_180004117
0x180004112  jmp     loc_180004505
0x180004117  lea     rax, [rsp+260h+var_1F8]
0x18000411c  mov     [rsp+260h+ppv], rax; ppv
0x180004121  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180004128  mov     r12d, 1
0x18000412e  mov     r8d, r12d; dwClsContext
0x180004131  xor     edx, edx; pUnkOuter
0x180004133  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18000413a  call    cs:__imp_CoCreateInstance
0x180004140  test    eax, eax
0x180004142  jns     loc_1800041C8
0x180004148  jmp     loc_1800044EE
0x18000414d  mov     rax, [rdi+8]
0x180004151  movups  xmm0, xmmword ptr [rax]
0x180004154  movdqu  [rbp+160h+var_1C8], xmm0
0x180004159  lea     r9, [rbp+160h+var_1C8]
0x18000415d  mov     r8d, r12d
0x180004160  mov     rdx, rbx
0x180004163  test    r14d, r14d
0x180004166  jz      short loc_1800041A8
0x180004168  cmp     ecx, r12d
0x18000416b  mov     rcx, [rsp+260h+var_1F8]
0x180004170  mov     rax, [rcx]
0x180004173  jnz     short loc_18000417B
0x180004175  mov     rax, [rax+28h]
0x180004179  jmp     short loc_18000417F
0x18000417b  mov     rax, [rax+38h]
0x18000417f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004184  mov     esi, eax
0x180004186  test    eax, eax
0x180004188  jns     short loc_1800041C4
0x18000418a  mov     rcx, [rsp+260h+var_1F8]
0x18000418f  test    rcx, rcx
0x180004192  jz      short loc_1800041A1
0x180004194  mov     rax, [rcx]
0x180004197  mov     rax, [rax+10h]
0x18000419b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041a0  nop
0x1800041a1  mov     eax, esi
0x1800041a3  jmp     loc_180004507
0x1800041a8  cmp     ecx, r12d
0x1800041ab  mov     rcx, [rsp+260h+var_1F8]
0x1800041b0  mov     rax, [rcx]
0x1800041b3  jnz     short loc_1800041BB
0x1800041b5  mov     rax, [rax+30h]
0x1800041b9  jmp     short loc_1800041BF
0x1800041bb  mov     rax, [rax+40h]
0x1800041bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041c4  add     rdi, 10h
0x1800041c8  mov     ecx, [rdi]
0x1800041ca  test    ecx, ecx
0x1800041cc  jnz     loc_18000414D
0x1800041d2  test    r14d, r14d
0x1800041d5  jnz     loc_1800044EE
0x1800041db  lea     r8d, [rcx+40h]; cchMax
0x1800041df  lea     rdx, [rbp+160h+sz]; lpsz
0x1800041e6  mov     rcx, rbx; rguid
0x1800041e9  call    cs:__imp_StringFromGUID2
0x1800041ef  lea     r8, aClsid; "CLSID\\"
0x1800041f6  mov     ebx, 80h
0x1800041fb  mov     edx, ebx; SizeInWords
0x1800041fd  lea     rcx, [rbp+160h+Destination]; Destination
0x180004201  call    cs:__imp_wcscpy_s
0x180004207  lea     r14d, [rbx-74h]
0x18000420b  lea     r12d, [rbx-30h]
0x18000420f  test    eax, eax
0x180004211  jz      short loc_180004237
0x180004213  cmp     eax, r14d
0x180004216  jz      loc_180004532
0x18000421c  cmp     eax, 16h
0x18000421f  jz      loc_180004548
0x180004225  cmp     eax, 22h ; '"'
0x180004228  jz      loc_180004548
0x18000422e  cmp     eax, r12d
0x180004231  jnz     loc_18000453D
0x180004237  lea     r8, [rbp+160h+sz]; Source
0x18000423e  mov     rdx, rbx; SizeInWords
0x180004241  lea     rcx, [rbp+160h+Destination]; Destination
0x180004245  call    cs:__imp_wcscat_s
0x18000424b  test    eax, eax
0x18000424d  jz      short loc_180004273
0x18000424f  cmp     eax, r14d
0x180004252  jz      loc_180004532
0x180004258  cmp     eax, 16h
0x18000425b  jz      loc_180004548
0x180004261  cmp     eax, 22h ; '"'
0x180004264  jz      loc_180004548
0x18000426a  cmp     eax, r12d
0x18000426d  jnz     loc_18000453D
0x180004273  lea     r8, aRequiredCatego; "\\Required Categories"
0x18000427a  mov     rdx, rbx; SizeInWords
0x18000427d  lea     rcx, [rbp+160h+Destination]; Destination
0x180004281  call    cs:__imp_wcscat_s
0x180004287  test    eax, eax
0x180004289  jz      short loc_1800042AF
0x18000428b  cmp     eax, r14d
0x18000428e  jz      loc_180004532
0x180004294  cmp     eax, 16h
0x180004297  jz      loc_180004548
0x18000429d  cmp     eax, 22h ; '"'
0x1800042a0  jz      loc_180004548
0x1800042a6  cmp     eax, r12d
0x1800042a9  jnz     loc_18000453D
0x1800042af  mov     rdi, 0FFFFFFFF80000000h
0x1800042b6  mov     [rbp+160h+var_1E0], rdi
0x1800042ba  mov     [rbp+160h+var_1D8], r15
0x1800042be  mov     [rbp+160h+var_1D0], r15
0x1800042c2  mov     rbx, r15
0x1800042c5  mov     [rsp+260h+cSubKeys], r15d
0x1800042ca  mov     [rsp+260h+phkResult], r15
0x1800042cf  lea     rax, [rsp+260h+phkResult]
0x1800042d4  mov     [rsp+260h+ppv], rax; phkResult
0x1800042d9  mov     r9d, 20019h; samDesired
0x1800042df  xor     r8d, r8d; ulOptions
0x1800042e2  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x1800042e6  mov     rcx, rdi; hKey
0x1800042e9  call    cs:__imp_RegOpenKeyExW
0x1800042ef  test    eax, eax
0x1800042f1  jnz     short loc_180004365
0x1800042f3  mov     rbx, [rsp+260h+phkResult]
0x1800042f8  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800042fd  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180004302  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180004307  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000430c  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180004311  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180004316  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000431b  lea     rax, [rsp+260h+cSubKeys]
0x180004320  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180004325  xor     r9d, r9d; lpReserved
0x180004328  xor     r8d, r8d; lpcchClass
0x18000432b  xor     edx, edx; lpClass
0x18000432d  mov     rcx, rbx; hKey
0x180004330  call    cs:__imp_RegQueryInfoKeyW
0x180004336  mov     esi, eax
0x180004338  test    rbx, rbx
0x18000433b  jz      short loc_180004349
0x18000433d  mov     rcx, rbx; hKey
0x180004340  call    cs:__imp_RegCloseKey
0x180004346  mov     rbx, r15
0x180004349  test    esi, esi
0x18000434b  jnz     short loc_180004365
0x18000434d  cmp     [rsp+260h+cSubKeys], r15d
0x180004352  jnz     short loc_180004365
0x180004354  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x180004358  lea     rcx, [rbp+160h+var_1E0]; this
0x18000435c  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180004361  mov     rdi, [rbp+160h+var_1E0]
0x180004365  lea     r8, aClsid; "CLSID\\"
0x18000436c  mov     esi, 80h
0x180004371  mov     edx, esi; SizeInWords
0x180004373  lea     rcx, [rbp+160h+Destination]; Destination
0x180004377  call    cs:__imp_wcscpy_s
0x18000437d  test    eax, eax
0x18000437f  jz      short loc_1800043A5
0x180004381  cmp     eax, r14d
0x180004384  jz      loc_180004532
0x18000438a  cmp     eax, 16h
0x18000438d  jz      loc_180004548
0x180004393  cmp     eax, 22h ; '"'
0x180004396  jz      loc_180004548
0x18000439c  cmp     eax, r12d
0x18000439f  jnz     loc_18000453D
0x1800043a5  lea     r8, [rbp+160h+sz]; Source
0x1800043ac  mov     rdx, rsi; SizeInWords
0x1800043af  lea     rcx, [rbp+160h+Destination]; Destination
0x1800043b3  call    cs:__imp_wcscat_s
0x1800043b9  test    eax, eax
0x1800043bb  jz      short loc_1800043E1
0x1800043bd  cmp     eax, r14d
0x1800043c0  jz      loc_180004532
0x1800043c6  cmp     eax, 16h
0x1800043c9  jz      loc_180004548
0x1800043cf  cmp     eax, 22h ; '"'
0x1800043d2  jz      loc_180004548
0x1800043d8  cmp     eax, r12d
0x1800043db  jnz     loc_18000453D
0x1800043e1  lea     r8, aImplementedCat; "\\Implemented Categories"
0x1800043e8  mov     rdx, rsi; SizeInWords
0x1800043eb  lea     rcx, [rbp+160h+Destination]; Destination
0x1800043ef  call    cs:__imp_wcscat_s
0x1800043f5  test    eax, eax
0x1800043f7  jz      short loc_18000441D
0x1800043f9  cmp     eax, r14d
0x1800043fc  jz      loc_180004532
0x180004402  cmp     eax, 16h
0x180004405  jz      loc_180004548
0x18000440b  cmp     eax, 22h ; '"'
0x18000440e  jz      loc_180004548
0x180004414  cmp     eax, r12d
0x180004417  jnz     loc_18000453D
0x18000441d  mov     [rsp+260h+hKey], r15
0x180004422  lea     rax, [rsp+260h+hKey]
0x180004427  mov     [rsp+260h+ppv], rax; phkResult
0x18000442c  mov     r9d, 20019h; samDesired
0x180004432  xor     r8d, r8d; ulOptions
0x180004435  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x180004439  mov     rcx, rdi; hKey
0x18000443c  call    cs:__imp_RegOpenKeyExW
0x180004442  test    eax, eax
0x180004444  jnz     loc_1800044D1
0x18000444a  mov     eax, r15d
0x18000444d  test    rbx, rbx
0x180004450  jz      short loc_18000445B
0x180004452  mov     rcx, rbx; hKey
0x180004455  call    cs:__imp_RegCloseKey
0x18000445b  mov     rbx, [rsp+260h+hKey]
0x180004460  test    eax, eax
0x180004462  jnz     short loc_1800044D1
0x180004464  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180004469  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000446e  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180004473  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180004478  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18000447d  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180004482  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180004487  lea     rax, [rsp+260h+cSubKeys]
0x18000448c  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180004491  xor     r9d, r9d; lpReserved
0x180004494  xor     r8d, r8d; lpcchClass
0x180004497  xor     edx, edx; lpClass
0x180004499  mov     rcx, rbx; hKey
0x18000449c  call    cs:__imp_RegQueryInfoKeyW
0x1800044a2  mov     esi, eax
0x1800044a4  test    rbx, rbx
0x1800044a7  jz      short loc_1800044B5
0x1800044a9  mov     rcx, rbx; hKey
0x1800044ac  call    cs:__imp_RegCloseKey
0x1800044b2  mov     rbx, r15
0x1800044b5  test    esi, esi
0x1800044b7  jnz     short loc_1800044DF
0x1800044b9  cmp     [rsp+260h+cSubKeys], r15d
0x1800044be  jnz     short loc_1800044D1
0x1800044c0  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x1800044c4  lea     rcx, [rbp+160h+var_1E0]; this
0x1800044c8  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800044cd  mov     rdi, [rbp+160h+var_1E0]
0x1800044d1  test    rbx, rbx
0x1800044d4  jz      short loc_1800044DF
0x1800044d6  mov     rcx, rbx; hKey
0x1800044d9  call    cs:__imp_RegCloseKey
0x1800044df  test    rdi, rdi
0x1800044e2  jz      short loc_1800044EE
0x1800044e4  mov     rcx, rdi; hKey
0x1800044e7  call    cs:__imp_RegCloseKey
0x1800044ed  nop
0x1800044ee  mov     rcx, [rsp+260h+var_1F8]
0x1800044f3  test    rcx, rcx
0x1800044f6  jz      short loc_180004505
0x1800044f8  mov     rax, [rcx]
0x1800044fb  mov     rax, [rax+10h]
0x1800044ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004504  nop
0x180004505  xor     eax, eax
0x180004507  mov     rcx, [rbp+160h+var_30]
0x18000450e  xor     rcx, rsp; StackCookie
0x180004511  call    __security_check_cookie
0x180004516  lea     r11, [rsp+260h+var_20]
0x18000451e  mov     rbx, [r11+40h]
0x180004522  mov     rsi, [r11+48h]
0x180004526  mov     rsp, r11
0x180004529  pop     r15
0x18000452b  pop     r14
0x18000452d  pop     r12
0x18000452f  pop     rdi
0x180004530  pop     rbp
0x180004531  retn
  ... truncated ...
```
