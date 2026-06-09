# CAudioSessionPropertyStore::LoadPropertyStore(void)

- ea: `0x1800137b0`
- end: `0x18001400c`
- name: `?LoadPropertyStore@CAudioSessionPropertyStore@@AEAAJXZ`
- size: `2140`
- prototype: `__int64 __fastcall(CAudioSessionPropertyStore *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800136c0`

## callees

- `0x18000a384`
- `0x180012844`
- `0x1800137b0`
- `0x180015370`
- `0x180015394`
- `0x180023e98`
- `0x180025db0`
- `0x1800272f8`
- `0x18002cae8`
- `0x180031960`
- `0x180031e00`
- `0x180031eb0`
- `0x1800327e0`
- `0x1800360e0`
- `0x18003d2e0`
- `0x18003d900`
- `0x18003d9b4`
- `0x18003da28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180013a05`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180013a05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013b24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013b78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013bd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013b24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013b78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013bd2`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001383e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001383e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800138b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800138b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013882`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013c4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013c94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013d60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013dd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013e24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013f3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013fa1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013882`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013c4a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013c94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013d60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013dd2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013e24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013f3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013fa1`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800139c2`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800139c2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180013816`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180013816`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013916`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013916`
- `RPCRT4!RpcRevertToSelf` at `0x1800138c3`
- `RPCRT4!RpcRevertToSelf` at `0x180013f91`
- `RPCRT4!RpcRevertToSelf` at `0x1800138c3`
- `RPCRT4!RpcRevertToSelf` at `0x180013f91`
- `RPCRT4!RpcImpersonateClient` at `0x180013855`
- `RPCRT4!RpcImpersonateClient` at `0x180013855`
- `OLEAUT32!__imp_SysAllocString` at `0x180013c0b`
- `OLEAUT32!__imp_SysAllocString` at `0x180013c0b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180013ce9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180013d33`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180013da5`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180013ce9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180013d33`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180013da5`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180013b0b`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180013cd8`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180013d26`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180013d98`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180013b0b`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180013cd8`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180013d26`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x180013d98`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAudioSessionPropertyStore::LoadPropertyStore(CAudioSessionPropertyStore *this)
{
  CAudioSessionPropertyStore *v1; // r13
  DWORD v2; // esi
  unsigned int v3; // eax
  HRESULT v4; // eax
  unsigned int v5; // ebx
  RPC_STATUS v6; // eax
  HKEY v7; // rdi
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned __int64 v10; // rax
  WCHAR *v11; // rdi
  BYTE *v12; // r14
  DWORD i; // ecx
  unsigned int v14; // eax
  char *v15; // rbx
  unsigned __int64 v16; // rdx
  __int64 v17; // xmm1_8
  unsigned __int64 v18; // r12
  unsigned __int64 v19; // r12
  __int64 v20; // r15
  int v21; // esi
  BYTE *v22; // rdx
  unsigned int j; // r13d
  char *v24; // r15
  SAFEARRAY *v25; // rsi
  LPVOID v26; // rax
  const unsigned __int16 *v27; // r15
  LPVOID v28; // rax
  __int64 v29; // rdx
  const char *v30; // r15
  LPVOID v31; // rax
  BSTR v32; // rax
  bool v33; // sf
  __int64 v34; // rdx
  SAFEARRAY *v35; // rbx
  __int64 v36; // rdx
  SAFEARRAY *v37; // rbx
  SAFEARRAY *v39; // rbx
  __int64 v40; // rdx
  unsigned int v41; // edi
  unsigned int lpReserved; // [rsp+20h] [rbp-E0h]
  unsigned int lpReserveda; // [rsp+20h] [rbp-E0h]
  unsigned int lpReservedb; // [rsp+20h] [rbp-E0h]
  unsigned int lpReservedc; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  BYTE *v47; // [rsp+68h] [rbp-98h] BYREF
  WCHAR *v48; // [rsp+70h] [rbp-90h] BYREF
  SAFEARRAY *psa; // [rsp+78h] [rbp-88h] BYREF
  char *v50; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+88h] [rbp-78h] BYREF
  DWORD cbMaxValueLen; // [rsp+8Ch] [rbp-74h] BYREF
  DWORD cchName; // [rsp+90h] [rbp-70h] BYREF
  DWORD cbData; // [rsp+94h] [rbp-6Ch] BYREF
  DWORD cValues; // [rsp+98h] [rbp-68h] BYREF
  DWORD v56; // [rsp+9Ch] [rbp-64h]
  DWORD v57; // [rsp+A0h] [rbp-60h]
  int v58; // [rsp+A4h] [rbp-5Ch] BYREF
  char v59[8]; // [rsp+A8h] [rbp-58h] BYREF
  CAudioSessionPropertyStore *v60; // [rsp+B0h] [rbp-50h]
  GUID pclsid; // [rsp+B8h] [rbp-48h] BYREF
  WCHAR Name[104]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  v1 = this;
  v60 = this;
  v2 = 0;
LABEL_2:
  v57 = v2;
  cchName = 100;
  v3 = RegEnumKeyExW(*((HKEY *)v1 + 7), v2, Name, &cchName, 0, 0, 0, 0);
  if ( v3 == 259 )
    return 0;
  if ( v3 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x354,
             (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
             (const char *)v3,
             lpReserved);
  pclsid = 0;
  v4 = CLSIDFromString(Name, &pclsid);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x357,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
      (const char *)(unsigned int)v4,
      lpReserved);
    return v5;
  }
  hKey = 0;
  v6 = RpcImpersonateClient(0);
  v5 = v6;
  if ( v6 && v6 != 1725 )
  {
    v33 = v6 < 0;
    if ( v6 > 0 )
    {
      v5 = (unsigned __int16)v6 | 0x80070000;
      v33 = 1;
    }
    if ( v33 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x35F,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
        (const char *)v5,
        lpReserved);
    goto LABEL_57;
  }
  v7 = hKey;
  if ( hKey )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v59);
    RegCloseKey(v7);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v59);
  }
  hKey = 0;
  v8 = RegOpenKeyExW(*((HKEY *)v1 + 7), Name, 0, 0x20019u, &hKey);
  if ( v8 )
  {
    v41 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x361,
            (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
            (const char *)v8,
            lpReserveda);
    if ( !v5 )
      RpcRevertToSelf();
    if ( hKey )
      RegCloseKey(hKey);
    return v41;
  }
  if ( !v5 )
    RpcRevertToSelf();
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  v9 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  if ( v9 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x368,
           (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
           (const char *)v9,
           lpReservedb);
LABEL_57:
    if ( hKey )
      RegCloseKey(hKey);
    return v5;
  }
  v10 = 2LL * ++cbMaxValueNameLen;
  if ( !is_mul_ok(cbMaxValueNameLen, 2u) )
    v10 = -1;
  v11 = (WCHAR *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
  v48 = v11;
  if ( !v11 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36D,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
      (const char *)0x8007000ELL,
      lpReservedb);
LABEL_95:
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942414LL;
  }
  v12 = (BYTE *)operator new[](cbMaxValueLen, (const struct std::nothrow_t *)&std::nothrow);
  v47 = v12;
  if ( !v12 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x370,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
      (const char *)0x8007000ELL,
      lpReservedb);
LABEL_84:
    std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&v47);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v48);
    goto LABEL_95;
  }
  for ( i = 0; ; i = v56 + 1 )
  {
    v56 = i;
    if ( i >= cValues
      || (cchName = cbMaxValueNameLen,
          cbData = cbMaxValueLen,
          v14 = RegEnumValueW(hKey, i, v11, &cchName, 0, 0, v12, &cbData),
          v14 == 259) )
    {
      std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&v47);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v48);
      if ( hKey )
        RegCloseKey(hKey);
      v2 = v57 + 1;
      goto LABEL_2;
    }
    if ( v14 )
    {
      v5 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x37A,
             (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
             (const char *)v14,
             lpReservedc);
      operator delete(v12, (const struct std::nothrow_t *)1);
      operator delete(v11, (const struct std::nothrow_t *)2);
      goto LABEL_57;
    }
    v15 = (char *)operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v50 = v15;
    if ( !v15 )
    {
      v40 = 893;
      goto LABEL_83;
    }
    *((_QWORD *)v15 + 6) = *((_QWORD *)v1 + 6);
    *((_DWORD *)v15 + 4) = _o__wtoi(v11);
    *(GUID *)v15 = pclsid;
    v17 = *((_QWORD *)v12 + 2);
    *(_OWORD *)(v15 + 24) = *(_OWORD *)v12;
    *((_QWORD *)v15 + 5) = v17;
    if ( *((_WORD *)v15 + 12) == 8 )
    {
      v32 = SysAllocString((const OLECHAR *)&v12[*((_QWORD *)v15 + 4)]);
      *((_QWORD *)v15 + 4) = v32;
      if ( !v32 )
      {
        v40 = 974;
        goto LABEL_83;
      }
      goto LABEL_49;
    }
    if ( *((_WORD *)v15 + 12) != 30 )
      break;
    psa = 0;
    v30 = (const char *)&v12[*((_QWORD *)v15 + 4)];
    v21 = StringCbLengthA(v30, v16, (unsigned __int64 *)&psa);
    if ( v21 < 0 )
    {
      v29 = 982;
LABEL_87:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
        (const char *)(unsigned int)v21,
        lpReservedc);
      goto LABEL_75;
    }
    v31 = CoTaskMemAlloc((SIZE_T)psa);
    if ( !v31 )
    {
      v40 = 985;
      goto LABEL_83;
    }
    *((_QWORD *)v15 + 4) = v31;
    v21 = StringCchCopyA(0, (unsigned __int64)psa, v30);
    if ( v21 < 0 )
    {
      v29 = 988;
      goto LABEL_87;
    }
LABEL_49:
    *((_QWORD *)v1 + 6) = v15;
  }
  if ( *((_WORD *)v15 + 12) == 31 )
  {
    psa = 0;
    v27 = (const unsigned __int16 *)&v12[*((_QWORD *)v15 + 4)];
    v21 = StringCbLengthW(v27, 0x7FFFFFFFu, (unsigned __int64 *)&psa);
    if ( v21 < 0 )
    {
      v29 = 958;
      goto LABEL_87;
    }
    v28 = CoTaskMemAlloc((SIZE_T)psa);
    if ( !v28 )
    {
      v40 = 961;
      goto LABEL_83;
    }
    *((_QWORD *)v15 + 4) = v28;
    v21 = StringCbCopyW(0, (unsigned __int64)psa, v27);
    if ( v21 < 0 )
    {
      v29 = 964;
      goto LABEL_87;
    }
    goto LABEL_49;
  }
  if ( *((_WORD *)v15 + 12) == 65 || *((_WORD *)v15 + 12) == 70 )
  {
    v26 = CoTaskMemAlloc(*((unsigned int *)v15 + 8));
    if ( !v26 )
    {
      v40 = 908;
LABEL_83:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v40,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
        (const char *)0x8007000ELL,
        lpReservedc);
      std::unique_ptr<propstoreinfo_tag>::~unique_ptr<propstoreinfo_tag>(&v50);
      goto LABEL_84;
    }
    *((_QWORD *)v15 + 5) = v26;
    memcpy_0(0, &v12[(_QWORD)v26], *((unsigned int *)v15 + 8));
    goto LABEL_49;
  }
  if ( *((_WORD *)v15 + 12) != 8196 )
    goto LABEL_49;
  v18 = cbData - 24LL;
  if ( (v18 & 3) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A2,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
      (const char *)0x80070057LL,
      lpReservedc);
LABEL_79:
    std::unique_ptr<propstoreinfo_tag>::~unique_ptr<propstoreinfo_tag>(&v50);
    std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&v47);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v48);
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942487LL;
  }
  else
  {
    v19 = v18 >> 2;
    v20 = *((_QWORD *)v15 + 4);
    psa = 0;
    v21 = ATL::CComSafeArray<float,4>::Create(&psa, (unsigned int)v19);
    if ( v21 < 0 )
    {
      v34 = 934;
LABEL_72:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v34,
        (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
        (const char *)(unsigned int)v21,
        lpReservedc);
      v39 = psa;
      if ( psa && SafeArrayUnlock(psa) >= 0 )
        SafeArrayDestroy(v39);
LABEL_75:
      std::unique_ptr<propstoreinfo_tag>::~unique_ptr<propstoreinfo_tag>(&v50);
      std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&v47);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v48);
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)v21;
    }
    v22 = &v12[v20];
    for ( j = 0; ; ++j )
    {
      if ( j >= v19 )
      {
        v25 = psa;
        SafeArrayUnlock(psa);
        *((_QWORD *)v15 + 4) = v25;
        v1 = v60;
        goto LABEL_49;
      }
      v24 = (char *)(v22 + 4);
      if ( v22 + 4 < v22 )
        break;
      if ( v24 < (char *)v12 )
      {
        v36 = 941;
        goto LABEL_65;
      }
      if ( v24 - (char *)v12 > (unsigned __int64)cbData )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3AF,
          (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
          (const char *)0x80070057LL,
          lpReservedc);
        v35 = psa;
        if ( psa && SafeArrayUnlock(psa) >= 0 )
          SafeArrayDestroy(v35);
        goto LABEL_79;
      }
      v58 = *(_DWORD *)v22;
      v21 = ATL::CComSafeArray<float,4>::SetAt(&psa, j, &v58);
      if ( v21 < 0 )
      {
        v34 = 946;
        goto LABEL_72;
      }
      v22 = (BYTE *)v24;
    }
    v36 = 939;
LABEL_65:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v36,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\audiosessionstore.cpp",
      (const char *)0x80070216LL,
      lpReservedc);
    v37 = psa;
    if ( psa && SafeArrayUnlock(psa) >= 0 )
      SafeArrayDestroy(v37);
    std::unique_ptr<propstoreinfo_tag>::~unique_ptr<propstoreinfo_tag>(&v50);
    std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&v47);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v48);
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942934LL;
  }
}

```

## disassembly

```asm
0x1800137b0  push    rbp
0x1800137b2  push    rbx
0x1800137b3  push    rsi
0x1800137b4  push    rdi
0x1800137b5  push    r12
0x1800137b7  push    r13
0x1800137b9  push    r14
0x1800137bb  push    r15
0x1800137bd  lea     rbp, [rsp-0B8h]
0x1800137c5  sub     rsp, 1B8h
0x1800137cc  mov     rax, cs:__security_cookie
0x1800137d3  xor     rax, rsp
0x1800137d6  mov     [rbp+0F0h+var_50], rax
0x1800137dd  mov     r13, rcx
0x1800137e0  mov     [rbp+0F0h+var_140], rcx
0x1800137e4  xor     r12d, r12d
0x1800137e7  mov     esi, r12d
0x1800137ea  mov     [rbp+0F0h+var_150], esi
0x1800137ed  mov     [rbp+0F0h+cchName], 64h ; 'd'
0x1800137f4  mov     [rsp+1F0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800137f9  mov     [rsp+1F0h+lpcchClass], r12; lpcchClass
0x1800137fe  mov     [rsp+1F0h+lpClass], r12; lpClass
0x180013803  mov     [rsp+1F0h+lpReserved], r12; unsigned int
0x180013808  lea     r9, [rbp+0F0h+cchName]; lpcchName
0x18001380c  lea     r8, [rbp+0F0h+Name]; lpName
0x180013810  mov     edx, esi; dwIndex
0x180013812  mov     rcx, [r13+38h]; hKey
0x180013816  call    cs:__imp_RegEnumKeyExW
0x18001381c  cmp     eax, 103h
0x180013821  jz      loc_180013FE7
0x180013827  test    eax, eax
0x180013829  jnz     loc_180013FCA
0x18001382f  xorps   xmm0, xmm0
0x180013832  movups  xmmword ptr [rbp+0F0h+pclsid.Data1], xmm0
0x180013836  lea     rdx, [rbp+0F0h+pclsid]; pclsid
0x18001383a  lea     rcx, [rbp+0F0h+Name]; lpsz
0x18001383e  call    cs:__imp_CLSIDFromString
0x180013844  mov     ebx, eax
0x180013846  test    eax, eax
0x180013848  js      loc_180013FAB
0x18001384e  mov     [rsp+1F0h+hKey], r12
0x180013853  xor     ecx, ecx; BindingHandle
0x180013855  call    cs:__imp_RpcImpersonateClient
0x18001385b  mov     ebx, eax
0x18001385d  test    eax, eax
0x18001385f  jz      short loc_18001386C
0x180013861  cmp     eax, 6BDh
0x180013866  jnz     loc_180013C5A
0x18001386c  mov     rdi, [rsp+1F0h+hKey]
0x180013871  test    rdi, rdi
0x180013874  jz      short loc_180013891
0x180013876  lea     rcx, [rbp+0F0h+var_148]; this
0x18001387a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001387f  mov     rcx, rdi; hKey
0x180013882  call    cs:__imp_RegCloseKey
0x180013888  lea     rcx, [rbp+0F0h+var_148]; this
0x18001388c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180013891  mov     [rsp+1F0h+hKey], r12
0x180013896  lea     rax, [rsp+1F0h+hKey]
0x18001389b  mov     [rsp+1F0h+lpReserved], rax; unsigned int
0x1800138a0  mov     r9d, 20019h; samDesired
0x1800138a6  xor     r8d, r8d; ulOptions
0x1800138a9  lea     rdx, [rbp+0F0h+Name]; lpSubKey
0x1800138ad  mov     rcx, [r13+38h]; hKey
0x1800138b1  call    cs:__imp_RegOpenKeyExW
0x1800138b7  test    eax, eax
0x1800138b9  jnz     loc_180013F70
0x1800138bf  test    ebx, ebx
0x1800138c1  jnz     short loc_1800138C9
0x1800138c3  call    cs:__imp_RpcRevertToSelf
0x1800138c9  mov     [rbp+0F0h+cValues], r12d
0x1800138cd  mov     [rbp+0F0h+cbMaxValueNameLen], r12d
0x1800138d1  mov     [rbp+0F0h+cbMaxValueLen], r12d
0x1800138d5  mov     [rsp+1F0h+var_198], r12; lpftLastWriteTime
0x1800138da  mov     [rsp+1F0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1800138df  lea     rax, [rbp+0F0h+cbMaxValueLen]
0x1800138e3  mov     [rsp+1F0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800138e8  lea     rax, [rbp+0F0h+cbMaxValueNameLen]
0x1800138ec  mov     [rsp+1F0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800138f1  lea     rax, [rbp+0F0h+cValues]
0x1800138f5  mov     [rsp+1F0h+lpftLastWriteTime], rax; lpcValues
0x1800138fa  mov     [rsp+1F0h+lpcchClass], r12; lpcbMaxClassLen
0x1800138ff  mov     [rsp+1F0h+lpClass], r12; lpcbMaxSubKeyLen
0x180013904  mov     [rsp+1F0h+lpReserved], r12; unsigned int
0x180013909  xor     r9d, r9d; lpReserved
0x18001390c  xor     r8d, r8d; lpcchClass
0x18001390f  xor     edx, edx; lpClass
0x180013911  mov     rcx, [rsp+1F0h+hKey]; hKey
0x180013916  call    cs:__imp_RegQueryInfoKeyW
0x18001391c  test    eax, eax
0x18001391e  jnz     loc_180013F4E
0x180013924  mov     eax, [rbp+0F0h+cbMaxValueNameLen]
0x180013927  inc     eax
0x180013929  mov     [rbp+0F0h+cbMaxValueNameLen], eax
0x18001392c  mov     ecx, eax
0x18001392e  mov     eax, 2
0x180013933  mul     rcx
0x180013936  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001393d  cmovb   rax, rcx
0x180013941  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180013948  mov     rcx, rax; unsigned __int64
0x18001394b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180013950  mov     rdi, rax
0x180013953  mov     [rsp+1F0h+var_180], rax
0x180013958  test    rax, rax
0x18001395b  jz      loc_180013F16
0x180013961  mov     ecx, [rbp+0F0h+cbMaxValueLen]; unsigned __int64
0x180013964  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001396b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180013970  mov     r14, rax
0x180013973  mov     [rsp+1F0h+var_188], rax
0x180013978  test    rax, rax
0x18001397b  jz      loc_180013EF3
0x180013981  mov     ecx, r12d
0x180013984  mov     [rbp+0F0h+var_154], ecx
0x180013987  cmp     ecx, [rbp+0F0h+cValues]
0x18001398a  jnb     loc_180013C2C
0x180013990  mov     eax, [rbp+0F0h+cbMaxValueNameLen]
0x180013993  mov     [rbp+0F0h+cchName], eax
0x180013996  mov     eax, [rbp+0F0h+cbMaxValueLen]
0x180013999  mov     [rbp+0F0h+cbData], eax
0x18001399c  lea     rax, [rbp+0F0h+cbData]
0x1800139a0  mov     [rsp+1F0h+lpftLastWriteTime], rax; lpcbData
0x1800139a5  mov     [rsp+1F0h+lpcchClass], r14; lpData
0x1800139aa  mov     [rsp+1F0h+lpClass], r12; lpType
0x1800139af  mov     [rsp+1F0h+lpReserved], r12; unsigned int
0x1800139b4  lea     r9, [rbp+0F0h+cchName]; lpcchValueName
0x1800139b8  mov     r8, rdi; lpValueName
0x1800139bb  mov     edx, ecx; dwIndex
0x1800139bd  mov     rcx, [rsp+1F0h+hKey]; hKey
0x1800139c2  call    cs:__imp_RegEnumValueW
0x1800139c8  cmp     eax, 103h
0x1800139cd  jz      loc_180013C2C
0x1800139d3  test    eax, eax
0x1800139d5  jnz     loc_180013EB7
0x1800139db  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800139e2  lea     ecx, [rax+38h]; unsigned __int64
0x1800139e5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800139ea  mov     rbx, rax
0x1800139ed  mov     [rbp+0F0h+var_170], rax
0x1800139f1  test    rax, rax
0x1800139f4  jz      loc_180013EB0
0x1800139fa  mov     rax, [r13+30h]
0x1800139fe  mov     [rbx+30h], rax
0x180013a02  mov     rcx, rdi
0x180013a05  call    cs:__imp__o__wtoi
0x180013a0b  mov     [rbx+10h], eax
0x180013a0e  movups  xmm0, xmmword ptr [rbp+0F0h+pclsid.Data1]
0x180013a12  movdqu  xmmword ptr [rbx], xmm0
0x180013a16  movups  xmm0, xmmword ptr [r14]
0x180013a1a  movsd   xmm1, qword ptr [r14+10h]
0x180013a20  movups  xmmword ptr [rbx+18h], xmm0
0x180013a24  movsd   qword ptr [rbx+28h], xmm1
0x180013a29  movzx   ecx, word ptr [rbx+18h]
0x180013a2d  sub     ecx, 8
0x180013a30  jz      loc_180013C04
0x180013a36  sub     ecx, 16h
0x180013a39  jz      loc_180013BAA
0x180013a3f  sub     ecx, 1
0x180013a42  jz      loc_180013B4B
0x180013a48  sub     ecx, 22h ; '"'
0x180013a4b  jz      loc_180013B21
0x180013a51  sub     ecx, 5
0x180013a54  jz      loc_180013B21
0x180013a5a  cmp     ecx, 1FBEh
0x180013a60  jnz     loc_180013C1E
0x180013a66  mov     r12d, [rbp+0F0h+cbData]
0x180013a6a  add     r12, 0FFFFFFFFFFFFFFE8h
0x180013a6e  test    r12b, 3
0x180013a72  jnz     loc_180013DDF
0x180013a78  shr     r12, 2
0x180013a7c  mov     r15, [rbx+20h]
0x180013a80  mov     [rsp+1F0h+psa], 0
0x180013a89  mov     edx, r12d
0x180013a8c  lea     rcx, [rsp+1F0h+psa]
0x180013a91  call    ?Create@?$CComSafeArray@M$03@ATL@@QEAAJKJ@Z; ATL::CComSafeArray<float,4>::Create(ulong,long)
0x180013a96  mov     esi, eax
0x180013a98  test    eax, eax
0x180013a9a  js      loc_180013D70
0x180013aa0  lea     rdx, [r15+r14]
0x180013aa4  xor     r13d, r13d
0x180013aa7  mov     eax, r13d
0x180013aaa  cmp     rax, r12
0x180013aad  jnb     short loc_180013B03
0x180013aaf  lea     r15, [rdx+4]
0x180013ab3  cmp     r15, rdx
0x180013ab6  jb      loc_180013CFB
0x180013abc  cmp     r15, r14
0x180013abf  jb      loc_180013CF4
0x180013ac5  mov     rcx, r15
0x180013ac8  sub     rcx, r14
0x180013acb  mov     eax, [rbp+0F0h+cbData]
0x180013ace  cmp     rcx, rax
0x180013ad1  ja      loc_180013CA9
0x180013ad7  movss   xmm0, dword ptr [rdx]
0x180013adb  movss   [rbp+0F0h+var_14C], xmm0
0x180013ae0  lea     r8, [rbp+0F0h+var_14C]
0x180013ae4  mov     edx, r13d
0x180013ae7  lea     rcx, [rsp+1F0h+psa]
0x180013aec  call    ?SetAt@?$CComSafeArray@M$03@ATL@@QEAAJJAEBMH@Z; ATL::CComSafeArray<float,4>::SetAt(long,float const &,int)
0x180013af1  mov     esi, eax
0x180013af3  test    eax, eax
0x180013af5  js      loc_180013C9F
0x180013afb  mov     rdx, r15
0x180013afe  inc     r13d
0x180013b01  jmp     short loc_180013AA7
0x180013b03  mov     rsi, [rsp+1F0h+psa]
0x180013b08  mov     rcx, rsi; psa
0x180013b0b  call    cs:__imp_SafeArrayUnlock
0x180013b11  mov     [rbx+20h], rsi
0x180013b15  mov     r13, [rbp+0F0h+var_140]
0x180013b19  xor     r12d, r12d
0x180013b1c  jmp     loc_180013C1E
0x180013b21  mov     ecx, [rbx+20h]; cb
0x180013b24  call    cs:__imp_CoTaskMemAlloc
0x180013b2a  test    rax, rax
0x180013b2d  jz      loc_180013E34
0x180013b33  mov     [rbx+28h], rax
0x180013b37  mov     r8d, [rbx+20h]; Size
0x180013b3b  lea     rdx, [rax+r14]; Src
0x180013b3f  xor     ecx, ecx; void *
0x180013b41  call    memcpy_0
0x180013b46  jmp     loc_180013C1E
0x180013b4b  mov     [rsp+1F0h+psa], r12
0x180013b50  mov     r15, [rbx+20h]
0x180013b54  add     r15, r14
0x180013b57  lea     r8, [rsp+1F0h+psa]; unsigned __int64 *
0x180013b5c  mov     edx, 7FFFFFFFh; unsigned __int64
0x180013b61  mov     rcx, r15; unsigned __int16 *
0x180013b64  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180013b69  mov     esi, eax
0x180013b6b  test    eax, eax
0x180013b6d  js      loc_180013E7B
0x180013b73  mov     rcx, [rsp+1F0h+psa]; cb
0x180013b78  call    cs:__imp_CoTaskMemAlloc
0x180013b7e  test    rax, rax
0x180013b81  jz      loc_180013E74
0x180013b87  mov     [rbx+20h], rax
0x180013b8b  mov     r8, r15; unsigned __int16 *
0x180013b8e  mov     rdx, [rsp+1F0h+psa]; unsigned __int64
0x180013b93  xor     ecx, ecx; unsigned __int16 *
0x180013b95  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180013b9a  mov     esi, eax
0x180013b9c  test    eax, eax
0x180013b9e  jns     short loc_180013C1E
0x180013ba0  mov     edx, 3C4h
0x180013ba5  jmp     loc_180013E80
0x180013baa  mov     [rsp+1F0h+psa], r12
0x180013baf  mov     r15, [rbx+20h]
0x180013bb3  add     r15, r14
0x180013bb6  lea     r8, [rsp+1F0h+psa]; unsigned __int64 *
0x180013bbb  mov     rcx, r15; char *
0x180013bbe  call    ?StringCbLengthA@@YAJPEBD_KPEA_K@Z; StringCbLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x180013bc3  mov     esi, eax
0x180013bc5  test    eax, eax
0x180013bc7  js      loc_180013EA2
0x180013bcd  mov     rcx, [rsp+1F0h+psa]; cb
0x180013bd2  call    cs:__imp_CoTaskMemAlloc
0x180013bd8  test    rax, rax
0x180013bdb  jz      loc_180013E9B
0x180013be1  mov     [rbx+20h], rax
0x180013be5  mov     r8, r15; char *
0x180013be8  mov     rdx, [rsp+1F0h+psa]; unsigned __int64
0x180013bed  xor     ecx, ecx; char *
0x180013bef  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180013bf4  mov     esi, eax
0x180013bf6  test    eax, eax
0x180013bf8  jns     short loc_180013C1E
0x180013bfa  mov     edx, 3DCh
0x180013bff  jmp     loc_180013E80
0x180013c04  mov     rcx, [rbx+20h]
0x180013c08  add     rcx, r14; psz
0x180013c0b  call    cs:__imp_SysAllocString
0x180013c11  mov     [rbx+20h], rax
0x180013c15  test    rax, rax
0x180013c18  jz      loc_180013EA9
0x180013c1e  mov     [r13+30h], rbx
0x180013c22  mov     ecx, [rbp+0F0h+var_154]
0x180013c25  inc     ecx
0x180013c27  jmp     loc_180013984
0x180013c2c  lea     rcx, [rsp+1F0h+var_188]
0x180013c31  call    ??1?$unique_ptr@EU?$default_delete@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar>::~unique_ptr<uchar>(void)
0x180013c36  lea     rcx, [rsp+1F0h+var_180]
0x180013c3b  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x180013c40  mov     rcx, [rsp+1F0h+hKey]; hKey
0x180013c45  test    rcx, rcx
0x180013c48  jz      short loc_180013C50
0x180013c4a  call    cs:__imp_RegCloseKey
0x180013c50  mov     esi, [rbp+0F0h+var_150]
0x180013c53  inc     esi
0x180013c55  jmp     loc_1800137EA
0x180013c5a  test    ebx, ebx
0x180013c5c  jle     short loc_180013C69
0x180013c5e  movzx   ebx, bx
0x180013c61  or      ebx, 80070000h
0x180013c67  test    ebx, ebx
0x180013c69  jns     short loc_180013C86
0x180013c6b  mov     rcx, [rbp+0F8h]; this
0x180013c72  mov     r9d, ebx; char *
0x180013c75  lea     r8, aClientcoreMult_1; "clientcore\\multimedia\\audiocore\\serv"...
  ... truncated ...
```
