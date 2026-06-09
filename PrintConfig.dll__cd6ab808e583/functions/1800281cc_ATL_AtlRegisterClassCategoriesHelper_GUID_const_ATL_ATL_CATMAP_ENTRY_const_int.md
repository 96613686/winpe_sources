# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x1800281cc`
- end: `0x18002868f`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1219`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180029360`
- `0x180029464`
- `0x180031850`
- `0x180031a80`

## callees

- `0x1800032e0`
- `0x18001047c`
- `0x1800281cc`
- `0x180029298`
- `0x1801c3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180028381`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800283bd`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800284ef`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002852b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180028381`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800283bd`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800284ef`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18002852b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002833d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800284b3`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002833d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800284b3`
- `ADVAPI32!RegCloseKey` at `0x18002847c`
- `ADVAPI32!RegCloseKey` at `0x180028591`
- `ADVAPI32!RegCloseKey` at `0x1800285e8`
- `ADVAPI32!RegCloseKey` at `0x180028615`
- `ADVAPI32!RegCloseKey` at `0x180028623`
- `ADVAPI32!RegCloseKey` at `0x18002847c`
- `ADVAPI32!RegCloseKey` at `0x180028591`
- `ADVAPI32!RegCloseKey` at `0x1800285e8`
- `ADVAPI32!RegCloseKey` at `0x180028615`
- `ADVAPI32!RegCloseKey` at `0x180028623`
- `ADVAPI32!RegOpenKeyExW` at `0x180028425`
- `ADVAPI32!RegOpenKeyExW` at `0x180028578`
- `ADVAPI32!RegOpenKeyExW` at `0x180028425`
- `ADVAPI32!RegOpenKeyExW` at `0x180028578`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18002846c`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800285d8`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18002846c`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800285d8`
- `ole32!CoCreateInstance` at `0x180028276`
- `ole32!CoCreateInstance` at `0x180028276`
- `ole32!StringFromGUID2` at `0x180028325`
- `ole32!StringFromGUID2` at `0x180028325`

## string_xrefs

- `0x18002832b`: `CLSID\`
- `0x1800284a1`: `CLSID\`

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
0x1800281cc  mov     rax, rsp
0x1800281cf  push    rbp
0x1800281d0  push    rdi
0x1800281d1  push    r12
0x1800281d3  push    r14
0x1800281d5  push    r15
0x1800281d7  lea     rbp, [rax-168h]
0x1800281de  sub     rsp, 240h
0x1800281e5  mov     [rbp+160h+var_1C8], 0FFFFFFFFFFFFFFFEh
0x1800281ed  mov     [rax+18h], rbx
0x1800281f1  mov     [rax+20h], rsi
0x1800281f5  mov     rax, cs:__security_cookie
0x1800281fc  xor     rax, rsp
0x1800281ff  mov     [rbp+160h+var_30], rax
0x180028206  mov     r14d, r8d
0x180028209  mov     rdi, rdx
0x18002820c  mov     rbx, rcx
0x18002820f  xor     r15d, r15d
0x180028212  mov     [rsp+260h+var_1F8], r15
0x180028217  xorps   xmm0, xmm0
0x18002821a  movups  [rbp+160h+var_1C0], xmm0
0x18002821e  test    rdx, rdx
0x180028221  jnz     short loc_180028228
0x180028223  jmp     loc_180028641
0x180028228  cmp     [rcx], r15d
0x18002822b  jnz     short loc_180028253
0x18002822d  mov     eax, dword ptr cs:GUID_NULL.Data2
0x180028233  cmp     [rcx+4], eax
0x180028236  jnz     short loc_180028253
0x180028238  mov     eax, dword ptr cs:GUID_NULL.Data4
0x18002823e  cmp     [rcx+8], eax
0x180028241  jnz     short loc_180028253
0x180028243  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x180028249  cmp     [rcx+0Ch], eax
0x18002824c  jnz     short loc_180028253
0x18002824e  jmp     loc_180028641
0x180028253  lea     rax, [rsp+260h+var_1F8]
0x180028258  mov     [rsp+260h+ppv], rax; ppv
0x18002825d  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180028264  mov     r12d, 1
0x18002826a  mov     r8d, r12d; dwClsContext
0x18002826d  xor     edx, edx; pUnkOuter
0x18002826f  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180028276  call    cs:__imp_CoCreateInstance
0x18002827c  test    eax, eax
0x18002827e  jns     loc_180028304
0x180028284  jmp     loc_18002862A
0x180028289  mov     rax, [rdi+8]
0x18002828d  movups  xmm0, xmmword ptr [rax]
0x180028290  movdqu  [rbp+160h+var_1C0], xmm0
0x180028295  lea     r9, [rbp+160h+var_1C0]
0x180028299  mov     r8d, r12d
0x18002829c  mov     rdx, rbx
0x18002829f  test    r14d, r14d
0x1800282a2  jz      short loc_1800282E4
0x1800282a4  cmp     ecx, r12d
0x1800282a7  mov     rcx, [rsp+260h+var_1F8]
0x1800282ac  mov     rax, [rcx]
0x1800282af  jnz     short loc_1800282B7
0x1800282b1  mov     rax, [rax+28h]
0x1800282b5  jmp     short loc_1800282BB
0x1800282b7  mov     rax, [rax+38h]
0x1800282bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282c0  mov     esi, eax
0x1800282c2  test    eax, eax
0x1800282c4  jns     short loc_180028300
0x1800282c6  mov     rcx, [rsp+260h+var_1F8]
0x1800282cb  test    rcx, rcx
0x1800282ce  jz      short loc_1800282DD
0x1800282d0  mov     rax, [rcx]
0x1800282d3  mov     rax, [rax+10h]
0x1800282d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282dc  nop
0x1800282dd  mov     eax, esi
0x1800282df  jmp     loc_180028643
0x1800282e4  cmp     ecx, r12d
0x1800282e7  mov     rcx, [rsp+260h+var_1F8]
0x1800282ec  mov     rax, [rcx]
0x1800282ef  jnz     short loc_1800282F7
0x1800282f1  mov     rax, [rax+30h]
0x1800282f5  jmp     short loc_1800282FB
0x1800282f7  mov     rax, [rax+40h]
0x1800282fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028300  add     rdi, 10h
0x180028304  mov     ecx, [rdi]
0x180028306  test    ecx, ecx
0x180028308  jnz     loc_180028289
0x18002830e  test    r14d, r14d
0x180028311  jnz     loc_18002862A
0x180028317  lea     r8d, [rcx+40h]; cchMax
0x18002831b  lea     rdx, [rbp+160h+sz]; lpsz
0x180028322  mov     rcx, rbx; rguid
0x180028325  call    cs:__imp_StringFromGUID2
0x18002832b  lea     r8, aClsid; "CLSID\\"
0x180028332  mov     ebx, 80h
0x180028337  mov     edx, ebx
0x180028339  lea     rcx, [rbp+160h+SubKey]
0x18002833d  call    cs:__imp__o_wcscpy_s
0x180028343  lea     r14d, [rbx-74h]
0x180028347  lea     r12d, [rbx-30h]
0x18002834b  test    eax, eax
0x18002834d  jz      short loc_180028373
0x18002834f  cmp     eax, r14d
0x180028352  jz      loc_18002866E
0x180028358  cmp     eax, 16h
0x18002835b  jz      loc_180028684
0x180028361  cmp     eax, 22h ; '"'
0x180028364  jz      loc_180028684
0x18002836a  cmp     eax, r12d
0x18002836d  jnz     loc_180028679
0x180028373  lea     r8, [rbp+160h+sz]
0x18002837a  mov     rdx, rbx
0x18002837d  lea     rcx, [rbp+160h+SubKey]
0x180028381  call    cs:__imp__o_wcscat_s
0x180028387  test    eax, eax
0x180028389  jz      short loc_1800283AF
0x18002838b  cmp     eax, r14d
0x18002838e  jz      loc_18002866E
0x180028394  cmp     eax, 16h
0x180028397  jz      loc_180028684
0x18002839d  cmp     eax, 22h ; '"'
0x1800283a0  jz      loc_180028684
0x1800283a6  cmp     eax, r12d
0x1800283a9  jnz     loc_180028679
0x1800283af  lea     r8, aRequiredCatego; "\\Required Categories"
0x1800283b6  mov     rdx, rbx
0x1800283b9  lea     rcx, [rbp+160h+SubKey]
0x1800283bd  call    cs:__imp__o_wcscat_s
0x1800283c3  test    eax, eax
0x1800283c5  jz      short loc_1800283EB
0x1800283c7  cmp     eax, r14d
0x1800283ca  jz      loc_18002866E
0x1800283d0  cmp     eax, 16h
0x1800283d3  jz      loc_180028684
0x1800283d9  cmp     eax, 22h ; '"'
0x1800283dc  jz      loc_180028684
0x1800283e2  cmp     eax, r12d
0x1800283e5  jnz     loc_180028679
0x1800283eb  mov     rdi, 0FFFFFFFF80000000h
0x1800283f2  mov     [rbp+160h+var_1E0], rdi
0x1800283f6  mov     [rbp+160h+var_1D8], r15
0x1800283fa  mov     [rbp+160h+var_1D0], r15
0x1800283fe  mov     rbx, r15
0x180028401  mov     [rsp+260h+cSubKeys], r15d
0x180028406  mov     [rsp+260h+phkResult], r15
0x18002840b  lea     rax, [rsp+260h+phkResult]
0x180028410  mov     [rsp+260h+ppv], rax; phkResult
0x180028415  mov     r9d, 20019h; samDesired
0x18002841b  xor     r8d, r8d; ulOptions
0x18002841e  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x180028422  mov     rcx, rdi; hKey
0x180028425  call    cs:__imp_RegOpenKeyExW
0x18002842b  test    eax, eax
0x18002842d  jnz     short loc_1800284A1
0x18002842f  mov     rbx, [rsp+260h+phkResult]
0x180028434  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180028439  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18002843e  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180028443  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180028448  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18002844d  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180028452  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180028457  lea     rax, [rsp+260h+cSubKeys]
0x18002845c  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180028461  xor     r9d, r9d; lpReserved
0x180028464  xor     r8d, r8d; lpcchClass
0x180028467  xor     edx, edx; lpClass
0x180028469  mov     rcx, rbx; hKey
0x18002846c  call    cs:__imp_RegQueryInfoKeyW
0x180028472  mov     esi, eax
0x180028474  test    rbx, rbx
0x180028477  jz      short loc_180028485
0x180028479  mov     rcx, rbx; hKey
0x18002847c  call    cs:__imp_RegCloseKey
0x180028482  mov     rbx, r15
0x180028485  test    esi, esi
0x180028487  jnz     short loc_1800284A1
0x180028489  cmp     [rsp+260h+cSubKeys], r15d
0x18002848e  jnz     short loc_1800284A1
0x180028490  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x180028494  lea     rcx, [rbp+160h+var_1E0]; this
0x180028498  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18002849d  mov     rdi, [rbp+160h+var_1E0]
0x1800284a1  lea     r8, aClsid; "CLSID\\"
0x1800284a8  mov     esi, 80h
0x1800284ad  mov     edx, esi
0x1800284af  lea     rcx, [rbp+160h+SubKey]
0x1800284b3  call    cs:__imp__o_wcscpy_s
0x1800284b9  test    eax, eax
0x1800284bb  jz      short loc_1800284E1
0x1800284bd  cmp     eax, r14d
0x1800284c0  jz      loc_18002866E
0x1800284c6  cmp     eax, 16h
0x1800284c9  jz      loc_180028684
0x1800284cf  cmp     eax, 22h ; '"'
0x1800284d2  jz      loc_180028684
0x1800284d8  cmp     eax, r12d
0x1800284db  jnz     loc_180028679
0x1800284e1  lea     r8, [rbp+160h+sz]
0x1800284e8  mov     rdx, rsi
0x1800284eb  lea     rcx, [rbp+160h+SubKey]
0x1800284ef  call    cs:__imp__o_wcscat_s
0x1800284f5  test    eax, eax
0x1800284f7  jz      short loc_18002851D
0x1800284f9  cmp     eax, r14d
0x1800284fc  jz      loc_18002866E
0x180028502  cmp     eax, 16h
0x180028505  jz      loc_180028684
0x18002850b  cmp     eax, 22h ; '"'
0x18002850e  jz      loc_180028684
0x180028514  cmp     eax, r12d
0x180028517  jnz     loc_180028679
0x18002851d  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180028524  mov     rdx, rsi
0x180028527  lea     rcx, [rbp+160h+SubKey]
0x18002852b  call    cs:__imp__o_wcscat_s
0x180028531  test    eax, eax
0x180028533  jz      short loc_180028559
0x180028535  cmp     eax, r14d
0x180028538  jz      loc_18002866E
0x18002853e  cmp     eax, 16h
0x180028541  jz      loc_180028684
0x180028547  cmp     eax, 22h ; '"'
0x18002854a  jz      loc_180028684
0x180028550  cmp     eax, r12d
0x180028553  jnz     loc_180028679
0x180028559  mov     [rsp+260h+hKey], r15
0x18002855e  lea     rax, [rsp+260h+hKey]
0x180028563  mov     [rsp+260h+ppv], rax; phkResult
0x180028568  mov     r9d, 20019h; samDesired
0x18002856e  xor     r8d, r8d; ulOptions
0x180028571  lea     rdx, [rbp+160h+SubKey]; lpSubKey
0x180028575  mov     rcx, rdi; hKey
0x180028578  call    cs:__imp_RegOpenKeyExW
0x18002857e  test    eax, eax
0x180028580  jnz     loc_18002860D
0x180028586  mov     eax, r15d
0x180028589  test    rbx, rbx
0x18002858c  jz      short loc_180028597
0x18002858e  mov     rcx, rbx; hKey
0x180028591  call    cs:__imp_RegCloseKey
0x180028597  mov     rbx, [rsp+260h+hKey]
0x18002859c  test    eax, eax
0x18002859e  jnz     short loc_18002860D
0x1800285a0  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800285a5  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800285aa  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800285af  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800285b4  mov     [rsp+260h+lpcValues], r15; lpcValues
0x1800285b9  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800285be  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800285c3  lea     rax, [rsp+260h+cSubKeys]
0x1800285c8  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x1800285cd  xor     r9d, r9d; lpReserved
0x1800285d0  xor     r8d, r8d; lpcchClass
0x1800285d3  xor     edx, edx; lpClass
0x1800285d5  mov     rcx, rbx; hKey
0x1800285d8  call    cs:__imp_RegQueryInfoKeyW
0x1800285de  mov     esi, eax
0x1800285e0  test    rbx, rbx
0x1800285e3  jz      short loc_1800285F1
0x1800285e5  mov     rcx, rbx; hKey
0x1800285e8  call    cs:__imp_RegCloseKey
0x1800285ee  mov     rbx, r15
0x1800285f1  test    esi, esi
0x1800285f3  jnz     short loc_18002861B
0x1800285f5  cmp     [rsp+260h+cSubKeys], r15d
0x1800285fa  jnz     short loc_18002860D
0x1800285fc  lea     rdx, [rbp+160h+SubKey]; unsigned __int16 *
0x180028600  lea     rcx, [rbp+160h+var_1E0]; this
0x180028604  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180028609  mov     rdi, [rbp+160h+var_1E0]
0x18002860d  test    rbx, rbx
0x180028610  jz      short loc_18002861B
0x180028612  mov     rcx, rbx; hKey
0x180028615  call    cs:__imp_RegCloseKey
0x18002861b  test    rdi, rdi
0x18002861e  jz      short loc_18002862A
0x180028620  mov     rcx, rdi; hKey
0x180028623  call    cs:__imp_RegCloseKey
0x180028629  nop
0x18002862a  mov     rcx, [rsp+260h+var_1F8]
0x18002862f  test    rcx, rcx
0x180028632  jz      short loc_180028641
0x180028634  mov     rax, [rcx]
0x180028637  mov     rax, [rax+10h]
0x18002863b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028640  nop
0x180028641  xor     eax, eax
0x180028643  mov     rcx, [rbp+160h+var_30]
0x18002864a  xor     rcx, rsp; StackCookie
0x18002864d  call    __security_check_cookie
0x180028652  lea     r11, [rsp+260h+var_20]
0x18002865a  mov     rbx, [r11+40h]
0x18002865e  mov     rsi, [r11+48h]
0x180028662  mov     rsp, r11
0x180028665  pop     r15
0x180028667  pop     r14
0x180028669  pop     r12
0x18002866b  pop     rdi
  ... truncated ...
```
