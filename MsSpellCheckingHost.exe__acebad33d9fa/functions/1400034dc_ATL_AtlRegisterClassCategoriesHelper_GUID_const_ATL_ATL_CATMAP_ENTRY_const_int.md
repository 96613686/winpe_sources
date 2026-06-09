# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x1400034dc`
- end: `0x14000399c`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1216`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140004210`
- `0x140005dc8`

## callees

- `0x1400034dc`
- `0x140003b88`
- `0x140003ca4`
- `0x140011e10`
- `0x140013010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x14000368e`
- `msvcrt!wcscat_s` at `0x1400036ca`
- `msvcrt!wcscat_s` at `0x1400037fc`
- `msvcrt!wcscat_s` at `0x140003838`
- `msvcrt!wcscat_s` at `0x14000368e`
- `msvcrt!wcscat_s` at `0x1400036ca`
- `msvcrt!wcscat_s` at `0x1400037fc`
- `msvcrt!wcscat_s` at `0x140003838`
- `msvcrt!wcscpy_s` at `0x14000364a`
- `msvcrt!wcscpy_s` at `0x1400037c0`
- `msvcrt!wcscpy_s` at `0x14000364a`
- `msvcrt!wcscpy_s` at `0x1400037c0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140003632`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140003632`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140003583`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140003583`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003732`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003885`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003732`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140003885`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140003779`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400038e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140003779`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400038e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003789`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000389e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400038f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003922`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003930`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003789`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000389e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400038f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003922`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003930`

## string_xrefs

- `0x140003638`: `CLSID\`
- `0x1400037ae`: `CLSID\`

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
0x1400034dc  mov     [rsp-8+arg_10], rbx
0x1400034e1  mov     [rsp-8+arg_18], rsi
0x1400034e6  push    rbp
0x1400034e7  push    rdi
0x1400034e8  push    r12
0x1400034ea  push    r14
0x1400034ec  push    r15
0x1400034ee  lea     rbp, [rsp-140h]
0x1400034f6  sub     rsp, 240h
0x1400034fd  mov     rax, cs:__security_cookie
0x140003504  xor     rax, rsp
0x140003507  mov     [rbp+160h+var_30], rax
0x14000350e  mov     r14d, r8d
0x140003511  mov     rdi, rdx
0x140003514  mov     rbx, rcx
0x140003517  xor     r15d, r15d
0x14000351a  mov     [rsp+260h+var_1F8], r15
0x14000351f  xorps   xmm0, xmm0
0x140003522  movups  [rbp+160h+var_1C8], xmm0
0x140003526  test    rdx, rdx
0x140003529  jnz     short loc_140003530
0x14000352b  jmp     loc_14000394E
0x140003530  mov     eax, cs:GUID_NULL.Data1
0x140003536  cmp     [rcx], eax
0x140003538  jnz     short loc_140003560
0x14000353a  mov     eax, dword ptr cs:GUID_NULL.Data2
0x140003540  cmp     [rcx+4], eax
0x140003543  jnz     short loc_140003560
0x140003545  mov     eax, dword ptr cs:GUID_NULL.Data4
0x14000354b  cmp     [rcx+8], eax
0x14000354e  jnz     short loc_140003560
0x140003550  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x140003556  cmp     [rcx+0Ch], eax
0x140003559  jnz     short loc_140003560
0x14000355b  jmp     loc_14000394E
0x140003560  lea     rax, [rsp+260h+var_1F8]
0x140003565  mov     [rsp+260h+ppv], rax; ppv
0x14000356a  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x140003571  mov     r12d, 1
0x140003577  mov     r8d, r12d; dwClsContext
0x14000357a  xor     edx, edx; pUnkOuter
0x14000357c  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x140003583  call    cs:__imp_CoCreateInstance
0x140003589  test    eax, eax
0x14000358b  jns     loc_140003611
0x140003591  jmp     loc_140003937
0x140003596  mov     rax, [rdi+8]
0x14000359a  movups  xmm0, xmmword ptr [rax]
0x14000359d  movdqu  [rbp+160h+var_1C8], xmm0
0x1400035a2  lea     r9, [rbp+160h+var_1C8]
0x1400035a6  mov     r8d, r12d
0x1400035a9  mov     rdx, rbx
0x1400035ac  test    r14d, r14d
0x1400035af  jz      short loc_1400035F1
0x1400035b1  cmp     ecx, r12d
0x1400035b4  mov     rcx, [rsp+260h+var_1F8]
0x1400035b9  mov     rax, [rcx]
0x1400035bc  jnz     short loc_1400035C4
0x1400035be  mov     rax, [rax+28h]
0x1400035c2  jmp     short loc_1400035C8
0x1400035c4  mov     rax, [rax+38h]
0x1400035c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400035cd  mov     esi, eax
0x1400035cf  test    eax, eax
0x1400035d1  jns     short loc_14000360D
0x1400035d3  mov     rcx, [rsp+260h+var_1F8]
0x1400035d8  test    rcx, rcx
0x1400035db  jz      short loc_1400035EA
0x1400035dd  mov     rax, [rcx]
0x1400035e0  mov     rax, [rax+10h]
0x1400035e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400035e9  nop
0x1400035ea  mov     eax, esi
0x1400035ec  jmp     loc_140003950
0x1400035f1  cmp     ecx, r12d
0x1400035f4  mov     rcx, [rsp+260h+var_1F8]
0x1400035f9  mov     rax, [rcx]
0x1400035fc  jnz     short loc_140003604
0x1400035fe  mov     rax, [rax+30h]
0x140003602  jmp     short loc_140003608
0x140003604  mov     rax, [rax+40h]
0x140003608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000360d  add     rdi, 10h
0x140003611  mov     ecx, [rdi]
0x140003613  test    ecx, ecx
0x140003615  jnz     loc_140003596
0x14000361b  test    r14d, r14d
0x14000361e  jnz     loc_140003937
0x140003624  lea     r8d, [rcx+40h]; cchMax
0x140003628  lea     rdx, [rbp+160h+sz]; lpsz
0x14000362f  mov     rcx, rbx; rguid
0x140003632  call    cs:__imp_StringFromGUID2
0x140003638  lea     r8, aClsid; "CLSID\\"
0x14000363f  mov     ebx, 80h
0x140003644  mov     edx, ebx; SizeInWords
0x140003646  lea     rcx, [rbp+160h+Destination]; Destination
0x14000364a  call    cs:__imp_wcscpy_s
0x140003650  lea     r14d, [rbx-74h]
0x140003654  lea     r12d, [rbx-30h]
0x140003658  test    eax, eax
0x14000365a  jz      short loc_140003680
0x14000365c  cmp     eax, r14d
0x14000365f  jz      loc_14000397B
0x140003665  cmp     eax, 16h
0x140003668  jz      loc_140003991
0x14000366e  cmp     eax, 22h ; '"'
0x140003671  jz      loc_140003991
0x140003677  cmp     eax, r12d
0x14000367a  jnz     loc_140003986
0x140003680  lea     r8, [rbp+160h+sz]; Source
0x140003687  mov     rdx, rbx; SizeInWords
0x14000368a  lea     rcx, [rbp+160h+Destination]; Destination
0x14000368e  call    cs:__imp_wcscat_s
0x140003694  test    eax, eax
0x140003696  jz      short loc_1400036BC
0x140003698  cmp     eax, r14d
0x14000369b  jz      loc_14000397B
0x1400036a1  cmp     eax, 16h
0x1400036a4  jz      loc_140003991
0x1400036aa  cmp     eax, 22h ; '"'
0x1400036ad  jz      loc_140003991
0x1400036b3  cmp     eax, r12d
0x1400036b6  jnz     loc_140003986
0x1400036bc  lea     r8, aRequiredCatego; "\\Required Categories"
0x1400036c3  mov     rdx, rbx; SizeInWords
0x1400036c6  lea     rcx, [rbp+160h+Destination]; Destination
0x1400036ca  call    cs:__imp_wcscat_s
0x1400036d0  test    eax, eax
0x1400036d2  jz      short loc_1400036F8
0x1400036d4  cmp     eax, r14d
0x1400036d7  jz      loc_14000397B
0x1400036dd  cmp     eax, 16h
0x1400036e0  jz      loc_140003991
0x1400036e6  cmp     eax, 22h ; '"'
0x1400036e9  jz      loc_140003991
0x1400036ef  cmp     eax, r12d
0x1400036f2  jnz     loc_140003986
0x1400036f8  mov     rdi, 0FFFFFFFF80000000h
0x1400036ff  mov     [rbp+160h+var_1E0], rdi
0x140003703  mov     [rbp+160h+var_1D8], r15
0x140003707  mov     [rbp+160h+var_1D0], r15
0x14000370b  mov     rbx, r15
0x14000370e  mov     [rsp+260h+cSubKeys], r15d
0x140003713  mov     [rsp+260h+phkResult], r15
0x140003718  lea     rax, [rsp+260h+phkResult]
0x14000371d  mov     [rsp+260h+ppv], rax; phkResult
0x140003722  mov     r9d, 20019h; samDesired
0x140003728  xor     r8d, r8d; ulOptions
0x14000372b  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x14000372f  mov     rcx, rdi; hKey
0x140003732  call    cs:__imp_RegOpenKeyExW
0x140003738  test    eax, eax
0x14000373a  jnz     short loc_1400037AE
0x14000373c  mov     rbx, [rsp+260h+phkResult]
0x140003741  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x140003746  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x14000374b  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x140003750  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x140003755  mov     [rsp+260h+lpcValues], r15; lpcValues
0x14000375a  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x14000375f  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x140003764  lea     rax, [rsp+260h+cSubKeys]
0x140003769  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x14000376e  xor     r9d, r9d; lpReserved
0x140003771  xor     r8d, r8d; lpcchClass
0x140003774  xor     edx, edx; lpClass
0x140003776  mov     rcx, rbx; hKey
0x140003779  call    cs:__imp_RegQueryInfoKeyW
0x14000377f  mov     esi, eax
0x140003781  test    rbx, rbx
0x140003784  jz      short loc_140003792
0x140003786  mov     rcx, rbx; hKey
0x140003789  call    cs:__imp_RegCloseKey
0x14000378f  mov     rbx, r15
0x140003792  test    esi, esi
0x140003794  jnz     short loc_1400037AE
0x140003796  cmp     [rsp+260h+cSubKeys], r15d
0x14000379b  jnz     short loc_1400037AE
0x14000379d  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x1400037a1  lea     rcx, [rbp+160h+var_1E0]; this
0x1400037a5  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1400037aa  mov     rdi, [rbp+160h+var_1E0]
0x1400037ae  lea     r8, aClsid; "CLSID\\"
0x1400037b5  mov     esi, 80h
0x1400037ba  mov     edx, esi; SizeInWords
0x1400037bc  lea     rcx, [rbp+160h+Destination]; Destination
0x1400037c0  call    cs:__imp_wcscpy_s
0x1400037c6  test    eax, eax
0x1400037c8  jz      short loc_1400037EE
0x1400037ca  cmp     eax, r14d
0x1400037cd  jz      loc_14000397B
0x1400037d3  cmp     eax, 16h
0x1400037d6  jz      loc_140003991
0x1400037dc  cmp     eax, 22h ; '"'
0x1400037df  jz      loc_140003991
0x1400037e5  cmp     eax, r12d
0x1400037e8  jnz     loc_140003986
0x1400037ee  lea     r8, [rbp+160h+sz]; Source
0x1400037f5  mov     rdx, rsi; SizeInWords
0x1400037f8  lea     rcx, [rbp+160h+Destination]; Destination
0x1400037fc  call    cs:__imp_wcscat_s
0x140003802  test    eax, eax
0x140003804  jz      short loc_14000382A
0x140003806  cmp     eax, r14d
0x140003809  jz      loc_14000397B
0x14000380f  cmp     eax, 16h
0x140003812  jz      loc_140003991
0x140003818  cmp     eax, 22h ; '"'
0x14000381b  jz      loc_140003991
0x140003821  cmp     eax, r12d
0x140003824  jnz     loc_140003986
0x14000382a  lea     r8, aImplementedCat; "\\Implemented Categories"
0x140003831  mov     rdx, rsi; SizeInWords
0x140003834  lea     rcx, [rbp+160h+Destination]; Destination
0x140003838  call    cs:__imp_wcscat_s
0x14000383e  test    eax, eax
0x140003840  jz      short loc_140003866
0x140003842  cmp     eax, r14d
0x140003845  jz      loc_14000397B
0x14000384b  cmp     eax, 16h
0x14000384e  jz      loc_140003991
0x140003854  cmp     eax, 22h ; '"'
0x140003857  jz      loc_140003991
0x14000385d  cmp     eax, r12d
0x140003860  jnz     loc_140003986
0x140003866  mov     [rsp+260h+hKey], r15
0x14000386b  lea     rax, [rsp+260h+hKey]
0x140003870  mov     [rsp+260h+ppv], rax; phkResult
0x140003875  mov     r9d, 20019h; samDesired
0x14000387b  xor     r8d, r8d; ulOptions
0x14000387e  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x140003882  mov     rcx, rdi; hKey
0x140003885  call    cs:__imp_RegOpenKeyExW
0x14000388b  test    eax, eax
0x14000388d  jnz     loc_14000391A
0x140003893  mov     eax, r15d
0x140003896  test    rbx, rbx
0x140003899  jz      short loc_1400038A4
0x14000389b  mov     rcx, rbx; hKey
0x14000389e  call    cs:__imp_RegCloseKey
0x1400038a4  mov     rbx, [rsp+260h+hKey]
0x1400038a9  test    eax, eax
0x1400038ab  jnz     short loc_14000391A
0x1400038ad  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1400038b2  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1400038b7  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1400038bc  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1400038c1  mov     [rsp+260h+lpcValues], r15; lpcValues
0x1400038c6  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1400038cb  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1400038d0  lea     rax, [rsp+260h+cSubKeys]
0x1400038d5  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x1400038da  xor     r9d, r9d; lpReserved
0x1400038dd  xor     r8d, r8d; lpcchClass
0x1400038e0  xor     edx, edx; lpClass
0x1400038e2  mov     rcx, rbx; hKey
0x1400038e5  call    cs:__imp_RegQueryInfoKeyW
0x1400038eb  mov     esi, eax
0x1400038ed  test    rbx, rbx
0x1400038f0  jz      short loc_1400038FE
0x1400038f2  mov     rcx, rbx; hKey
0x1400038f5  call    cs:__imp_RegCloseKey
0x1400038fb  mov     rbx, r15
0x1400038fe  test    esi, esi
0x140003900  jnz     short loc_140003928
0x140003902  cmp     [rsp+260h+cSubKeys], r15d
0x140003907  jnz     short loc_14000391A
0x140003909  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x14000390d  lea     rcx, [rbp+160h+var_1E0]; this
0x140003911  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x140003916  mov     rdi, [rbp+160h+var_1E0]
0x14000391a  test    rbx, rbx
0x14000391d  jz      short loc_140003928
0x14000391f  mov     rcx, rbx; hKey
0x140003922  call    cs:__imp_RegCloseKey
0x140003928  test    rdi, rdi
0x14000392b  jz      short loc_140003937
0x14000392d  mov     rcx, rdi; hKey
0x140003930  call    cs:__imp_RegCloseKey
0x140003936  nop
0x140003937  mov     rcx, [rsp+260h+var_1F8]
0x14000393c  test    rcx, rcx
0x14000393f  jz      short loc_14000394E
0x140003941  mov     rax, [rcx]
0x140003944  mov     rax, [rax+10h]
0x140003948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000394d  nop
0x14000394e  xor     eax, eax
0x140003950  mov     rcx, [rbp+160h+var_30]
0x140003957  xor     rcx, rsp; StackCookie
0x14000395a  call    __security_check_cookie
0x14000395f  lea     r11, [rsp+260h+var_20]
0x140003967  mov     rbx, [r11+40h]
0x14000396b  mov     rsi, [r11+48h]
0x14000396f  mov     rsp, r11
0x140003972  pop     r15
0x140003974  pop     r14
0x140003976  pop     r12
0x140003978  pop     rdi
0x140003979  pop     rbp
  ... truncated ...
```
