# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180002ebc`
- end: `0x180003370`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1204`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180004a74`
- `0x180004f60`

## callees

- `0x180002ebc`
- `0x180003558`
- `0x180003640`
- `0x180005f60`
- `0x180007010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180003064`
- `msvcrt!wcscat_s` at `0x1800030a0`
- `msvcrt!wcscat_s` at `0x1800031d2`
- `msvcrt!wcscat_s` at `0x18000320e`
- `msvcrt!wcscat_s` at `0x180003064`
- `msvcrt!wcscat_s` at `0x1800030a0`
- `msvcrt!wcscat_s` at `0x1800031d2`
- `msvcrt!wcscat_s` at `0x18000320e`
- `msvcrt!wcscpy_s` at `0x180003020`
- `msvcrt!wcscpy_s` at `0x180003196`
- `msvcrt!wcscpy_s` at `0x180003020`
- `msvcrt!wcscpy_s` at `0x180003196`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000314f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800032bb`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000314f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800032bb`
- `ADVAPI32!RegOpenKeyExW` at `0x180003108`
- `ADVAPI32!RegOpenKeyExW` at `0x18000325b`
- `ADVAPI32!RegOpenKeyExW` at `0x180003108`
- `ADVAPI32!RegOpenKeyExW` at `0x18000325b`
- `ADVAPI32!RegCloseKey` at `0x18000315f`
- `ADVAPI32!RegCloseKey` at `0x180003274`
- `ADVAPI32!RegCloseKey` at `0x1800032cb`
- `ADVAPI32!RegCloseKey` at `0x1800032f8`
- `ADVAPI32!RegCloseKey` at `0x180003306`
- `ADVAPI32!RegCloseKey` at `0x18000315f`
- `ADVAPI32!RegCloseKey` at `0x180003274`
- `ADVAPI32!RegCloseKey` at `0x1800032cb`
- `ADVAPI32!RegCloseKey` at `0x1800032f8`
- `ADVAPI32!RegCloseKey` at `0x180003306`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180003008`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180003008`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002f61`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002f61`

## string_xrefs

- `0x180003013`: `CLSID\`
- `0x180003189`: `CLSID\`

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
0x180002ebc  mov     [rsp-8+arg_10], rbx
0x180002ec1  mov     [rsp-8+arg_18], rsi
0x180002ec6  push    rbp
0x180002ec7  push    rdi
0x180002ec8  push    r12
0x180002eca  push    r14
0x180002ecc  push    r15
0x180002ece  lea     rbp, [rsp-140h]
0x180002ed6  sub     rsp, 240h
0x180002edd  mov     rax, cs:__security_cookie
0x180002ee4  xor     rax, rsp
0x180002ee7  mov     [rbp+160h+var_30], rax
0x180002eee  xor     r15d, r15d
0x180002ef1  xorps   xmm0, xmm0
0x180002ef4  mov     [rsp+260h+var_1F8], r15
0x180002ef9  mov     r14d, r8d
0x180002efc  mov     rdi, rdx
0x180002eff  mov     rbx, rcx
0x180002f02  movups  [rbp+160h+var_1C8], xmm0
0x180002f06  test    rdx, rdx
0x180002f09  jz      loc_180003322
0x180002f0f  mov     eax, cs:GUID_NULL.Data1
0x180002f15  cmp     [rcx], eax
0x180002f17  jnz     short loc_180002F3E
0x180002f19  mov     eax, dword ptr cs:GUID_NULL.Data2
0x180002f1f  cmp     [rcx+4], eax
0x180002f22  jnz     short loc_180002F3E
0x180002f24  mov     eax, dword ptr cs:GUID_NULL.Data4
0x180002f2a  cmp     [rcx+8], eax
0x180002f2d  jnz     short loc_180002F3E
0x180002f2f  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x180002f35  cmp     [rcx+0Ch], eax
0x180002f38  jz      loc_180003322
0x180002f3e  lea     rax, [rsp+260h+var_1F8]
0x180002f43  mov     r12d, 1
0x180002f49  mov     r8d, r12d; dwClsContext
0x180002f4c  mov     [rsp+260h+ppv], rax; ppv
0x180002f51  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180002f58  xor     edx, edx; pUnkOuter
0x180002f5a  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180002f61  call    cs:__imp_CoCreateInstance
0x180002f67  test    eax, eax
0x180002f69  js      loc_18000330C
0x180002f6f  jmp     short loc_180002FEB
0x180002f71  mov     rax, [rdi+8]
0x180002f75  lea     r9, [rbp+160h+var_1C8]
0x180002f79  mov     r8d, r12d
0x180002f7c  mov     rdx, rbx
0x180002f7f  movups  xmm0, xmmword ptr [rax]
0x180002f82  movdqu  [rbp+160h+var_1C8], xmm0
0x180002f87  test    r14d, r14d
0x180002f8a  jz      short loc_180002FCB
0x180002f8c  cmp     ecx, r12d
0x180002f8f  mov     rcx, [rsp+260h+var_1F8]
0x180002f94  mov     rax, [rcx]
0x180002f97  jnz     short loc_180002F9F
0x180002f99  mov     rax, [rax+28h]
0x180002f9d  jmp     short loc_180002FA3
0x180002f9f  mov     rax, [rax+38h]
0x180002fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fa8  mov     esi, eax
0x180002faa  test    eax, eax
0x180002fac  jns     short loc_180002FE7
0x180002fae  mov     rcx, [rsp+260h+var_1F8]
0x180002fb3  test    rcx, rcx
0x180002fb6  jz      short loc_180002FC4
0x180002fb8  mov     rax, [rcx]
0x180002fbb  mov     rax, [rax+10h]
0x180002fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fc4  mov     eax, esi
0x180002fc6  jmp     loc_180003324
0x180002fcb  cmp     ecx, r12d
0x180002fce  mov     rcx, [rsp+260h+var_1F8]
0x180002fd3  mov     rax, [rcx]
0x180002fd6  jnz     short loc_180002FDE
0x180002fd8  mov     rax, [rax+30h]
0x180002fdc  jmp     short loc_180002FE2
0x180002fde  mov     rax, [rax+40h]
0x180002fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fe7  add     rdi, 10h
0x180002feb  mov     ecx, [rdi]
0x180002fed  test    ecx, ecx
0x180002fef  jnz     short loc_180002F71
0x180002ff1  test    r14d, r14d
0x180002ff4  jnz     loc_18000330C
0x180002ffa  lea     r8d, [rcx+40h]; cchMax
0x180002ffe  mov     rcx, rbx; rguid
0x180003001  lea     rdx, [rbp+160h+sz]; lpsz
0x180003008  call    cs:__imp_StringFromGUID2
0x18000300e  mov     ebx, 80h
0x180003013  lea     r8, aClsid; "CLSID\\"
0x18000301a  mov     edx, ebx; SizeInWords
0x18000301c  lea     rcx, [rbp+160h+Destination]; Destination
0x180003020  call    cs:__imp_wcscpy_s
0x180003026  lea     r14d, [rbx-74h]
0x18000302a  lea     r12d, [rbx-30h]
0x18000302e  test    eax, eax
0x180003030  jz      short loc_180003056
0x180003032  cmp     eax, r14d
0x180003035  jz      loc_18000334F
0x18000303b  cmp     eax, 16h
0x18000303e  jz      loc_180003365
0x180003044  cmp     eax, 22h ; '"'
0x180003047  jz      loc_180003365
0x18000304d  cmp     eax, r12d
0x180003050  jnz     loc_18000335A
0x180003056  lea     r8, [rbp+160h+sz]; Source
0x18000305d  mov     rdx, rbx; SizeInWords
0x180003060  lea     rcx, [rbp+160h+Destination]; Destination
0x180003064  call    cs:__imp_wcscat_s
0x18000306a  test    eax, eax
0x18000306c  jz      short loc_180003092
0x18000306e  cmp     eax, r14d
0x180003071  jz      loc_18000334F
0x180003077  cmp     eax, 16h
0x18000307a  jz      loc_180003365
0x180003080  cmp     eax, 22h ; '"'
0x180003083  jz      loc_180003365
0x180003089  cmp     eax, r12d
0x18000308c  jnz     loc_18000335A
0x180003092  lea     r8, aRequiredCatego; "\\Required Categories"
0x180003099  mov     rdx, rbx; SizeInWords
0x18000309c  lea     rcx, [rbp+160h+Destination]; Destination
0x1800030a0  call    cs:__imp_wcscat_s
0x1800030a6  test    eax, eax
0x1800030a8  jz      short loc_1800030CE
0x1800030aa  cmp     eax, r14d
0x1800030ad  jz      loc_18000334F
0x1800030b3  cmp     eax, 16h
0x1800030b6  jz      loc_180003365
0x1800030bc  cmp     eax, 22h ; '"'
0x1800030bf  jz      loc_180003365
0x1800030c5  cmp     eax, r12d
0x1800030c8  jnz     loc_18000335A
0x1800030ce  mov     rdi, 0FFFFFFFF80000000h
0x1800030d5  mov     [rbp+160h+var_1D8], r15
0x1800030d9  lea     rax, [rsp+260h+phkResult]
0x1800030de  mov     [rbp+160h+var_1E0], rdi
0x1800030e2  mov     rcx, rdi; hKey
0x1800030e5  mov     [rbp+160h+var_1D0], r15
0x1800030e9  mov     r9d, 20019h; samDesired
0x1800030ef  mov     [rsp+260h+cSubKeys], r15d
0x1800030f4  xor     r8d, r8d; ulOptions
0x1800030f7  mov     [rsp+260h+phkResult], r15
0x1800030fc  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x180003100  mov     [rsp+260h+ppv], rax; phkResult
0x180003105  mov     rbx, r15
0x180003108  call    cs:__imp_RegOpenKeyExW
0x18000310e  test    eax, eax
0x180003110  jnz     short loc_180003184
0x180003112  mov     rbx, [rsp+260h+phkResult]
0x180003117  lea     rax, [rsp+260h+cSubKeys]
0x18000311c  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180003121  xor     r9d, r9d; lpReserved
0x180003124  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180003129  xor     r8d, r8d; lpcchClass
0x18000312c  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180003131  xor     edx, edx; lpClass
0x180003133  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180003138  mov     rcx, rbx; hKey
0x18000313b  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180003140  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180003145  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000314a  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000314f  call    cs:__imp_RegQueryInfoKeyW
0x180003155  mov     esi, eax
0x180003157  test    rbx, rbx
0x18000315a  jz      short loc_180003168
0x18000315c  mov     rcx, rbx; hKey
0x18000315f  call    cs:__imp_RegCloseKey
0x180003165  mov     rbx, r15
0x180003168  test    esi, esi
0x18000316a  jnz     short loc_180003184
0x18000316c  cmp     [rsp+260h+cSubKeys], r15d
0x180003171  jnz     short loc_180003184
0x180003173  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x180003177  lea     rcx, [rbp+160h+var_1E0]; this
0x18000317b  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180003180  mov     rdi, [rbp+160h+var_1E0]
0x180003184  mov     esi, 80h
0x180003189  lea     r8, aClsid; "CLSID\\"
0x180003190  mov     edx, esi; SizeInWords
0x180003192  lea     rcx, [rbp+160h+Destination]; Destination
0x180003196  call    cs:__imp_wcscpy_s
0x18000319c  test    eax, eax
0x18000319e  jz      short loc_1800031C4
0x1800031a0  cmp     eax, r14d
0x1800031a3  jz      loc_18000334F
0x1800031a9  cmp     eax, 16h
0x1800031ac  jz      loc_180003365
0x1800031b2  cmp     eax, 22h ; '"'
0x1800031b5  jz      loc_180003365
0x1800031bb  cmp     eax, r12d
0x1800031be  jnz     loc_18000335A
0x1800031c4  lea     r8, [rbp+160h+sz]; Source
0x1800031cb  mov     rdx, rsi; SizeInWords
0x1800031ce  lea     rcx, [rbp+160h+Destination]; Destination
0x1800031d2  call    cs:__imp_wcscat_s
0x1800031d8  test    eax, eax
0x1800031da  jz      short loc_180003200
0x1800031dc  cmp     eax, r14d
0x1800031df  jz      loc_18000334F
0x1800031e5  cmp     eax, 16h
0x1800031e8  jz      loc_180003365
0x1800031ee  cmp     eax, 22h ; '"'
0x1800031f1  jz      loc_180003365
0x1800031f7  cmp     eax, r12d
0x1800031fa  jnz     loc_18000335A
0x180003200  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180003207  mov     rdx, rsi; SizeInWords
0x18000320a  lea     rcx, [rbp+160h+Destination]; Destination
0x18000320e  call    cs:__imp_wcscat_s
0x180003214  test    eax, eax
0x180003216  jz      short loc_18000323C
0x180003218  cmp     eax, r14d
0x18000321b  jz      loc_18000334F
0x180003221  cmp     eax, 16h
0x180003224  jz      loc_180003365
0x18000322a  cmp     eax, 22h ; '"'
0x18000322d  jz      loc_180003365
0x180003233  cmp     eax, r12d
0x180003236  jnz     loc_18000335A
0x18000323c  lea     rax, [rsp+260h+hKey]
0x180003241  mov     [rsp+260h+hKey], r15
0x180003246  mov     r9d, 20019h; samDesired
0x18000324c  mov     [rsp+260h+ppv], rax; phkResult
0x180003251  xor     r8d, r8d; ulOptions
0x180003254  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x180003258  mov     rcx, rdi; hKey
0x18000325b  call    cs:__imp_RegOpenKeyExW
0x180003261  test    eax, eax
0x180003263  jnz     loc_1800032F0
0x180003269  mov     eax, r15d
0x18000326c  test    rbx, rbx
0x18000326f  jz      short loc_18000327A
0x180003271  mov     rcx, rbx; hKey
0x180003274  call    cs:__imp_RegCloseKey
0x18000327a  mov     rbx, [rsp+260h+hKey]
0x18000327f  test    eax, eax
0x180003281  jnz     short loc_1800032F0
0x180003283  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180003288  lea     rax, [rsp+260h+cSubKeys]
0x18000328d  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180003292  xor     r9d, r9d; lpReserved
0x180003295  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000329a  xor     r8d, r8d; lpcchClass
0x18000329d  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800032a2  xor     edx, edx; lpClass
0x1800032a4  mov     [rsp+260h+lpcValues], r15; lpcValues
0x1800032a9  mov     rcx, rbx; hKey
0x1800032ac  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800032b1  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800032b6  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x1800032bb  call    cs:__imp_RegQueryInfoKeyW
0x1800032c1  mov     esi, eax
0x1800032c3  test    rbx, rbx
0x1800032c6  jz      short loc_1800032D4
0x1800032c8  mov     rcx, rbx; hKey
0x1800032cb  call    cs:__imp_RegCloseKey
0x1800032d1  mov     rbx, r15
0x1800032d4  test    esi, esi
0x1800032d6  jnz     short loc_1800032FE
0x1800032d8  cmp     [rsp+260h+cSubKeys], r15d
0x1800032dd  jnz     short loc_1800032F0
0x1800032df  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x1800032e3  lea     rcx, [rbp+160h+var_1E0]; this
0x1800032e7  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800032ec  mov     rdi, [rbp+160h+var_1E0]
0x1800032f0  test    rbx, rbx
0x1800032f3  jz      short loc_1800032FE
0x1800032f5  mov     rcx, rbx; hKey
0x1800032f8  call    cs:__imp_RegCloseKey
0x1800032fe  test    rdi, rdi
0x180003301  jz      short loc_18000330C
0x180003303  mov     rcx, rdi; hKey
0x180003306  call    cs:__imp_RegCloseKey
0x18000330c  mov     rcx, [rsp+260h+var_1F8]
0x180003311  test    rcx, rcx
0x180003314  jz      short loc_180003322
0x180003316  mov     rax, [rcx]
0x180003319  mov     rax, [rax+10h]
0x18000331d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003322  xor     eax, eax
0x180003324  mov     rcx, [rbp+160h+var_30]
0x18000332b  xor     rcx, rsp; StackCookie
0x18000332e  call    __security_check_cookie
0x180003333  lea     r11, [rsp+260h+var_20]
0x18000333b  mov     rbx, [r11+40h]
0x18000333f  mov     rsi, [r11+48h]
0x180003343  mov     rsp, r11
0x180003346  pop     r15
0x180003348  pop     r14
0x18000334a  pop     r12
0x18000334c  pop     rdi
0x18000334d  pop     rbp
0x18000334e  retn
0x18000334f  mov     ecx, 8007000Eh; int
0x180003354  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000335a  mov     ecx, 80004005h; int
0x18000335f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
  ... truncated ...
```
