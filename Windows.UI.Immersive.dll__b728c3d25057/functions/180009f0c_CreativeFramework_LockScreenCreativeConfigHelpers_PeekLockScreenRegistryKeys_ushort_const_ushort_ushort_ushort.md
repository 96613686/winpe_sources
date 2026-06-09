# CreativeFramework::LockScreenCreativeConfigHelpers::PeekLockScreenRegistryKeys(ushort const *,ushort * *,ushort * *,ushort * *,bool *)

- ea: `0x180009f0c`
- end: `0x18000a710`
- name: `?PeekLockScreenRegistryKeys@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEBGPEAPEAG11PEA_N@Z`
- size: `2052`
- prototype: `int(CreativeFramework::LockScreenCreativeConfigHelpers *__hidden this, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, bool *)`
- caller_count: `4`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180009320`
- `0x18000b774`
- `0x1800358d0`
- `0x18003feb0`

## callees

- `0x180008d80`
- `0x180008e90`
- `0x180009ce4`
- `0x180009eec`
- `0x180009f0c`
- `0x18000a718`
- `0x18000a910`
- `0x18000af94`
- `0x18000bb20`
- `0x180034c6c`
- `0x180034db4`
- `0x180050ba0`
- `0x180051524`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x18000a1be`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x18000a1be`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a145`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a145`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a1a7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000a1a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a6c2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a6c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a097`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a097`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a280`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a311`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a429`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a5b9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a280`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a311`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a429`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a5b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a3a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a536`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a3a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a536`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a0f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a104`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a6b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a0f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a104`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a6b3`

## string_xrefs

- `0x180009fd0`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18000a051`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18000a154`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18000a219`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18000a349`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`
- `0x18000a695`: `onecoreuap\internal\shell\inc\LockScreenCreativeConfigHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CreativeFramework::LockScreenCreativeConfigHelpers::PeekLockScreenRegistryKeys(
        CreativeFramework::LockScreenCreativeConfigHelpers *this,
        unsigned __int16 *a2,
        DWORD *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5)
{
  DWORD *v5; // r12
  HKEY v7; // rdi
  unsigned __int64 v8; // r13
  unsigned __int64 v9; // r8
  void *v10; // rbx
  unsigned int v11; // esi
  __int64 v12; // r9
  __int64 v13; // rdx
  int CurrentUserSidString; // eax
  int v15; // eax
  WCHAR *v16; // r14
  LSTATUS v17; // eax
  unsigned int v18; // eax
  __int64 v19; // rdx
  unsigned __int64 v20; // rbx
  DWORD i; // esi
  unsigned __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rdx
  unsigned __int64 v25; // r9
  LSTATUS ValueW; // eax
  __int64 v27; // rdx
  __int64 v28; // rcx
  LSTATUS v29; // eax
  unsigned int v30; // ebx
  __int64 v31; // rdx
  unsigned __int64 v32; // r15
  unsigned __int64 v33; // r14
  _WORD *v34; // rax
  _WORD *v35; // rdx
  _QWORD *v36; // r15
  LSTATUS v37; // eax
  __int16 *v38; // rcx
  unsigned __int64 v39; // r8
  __int64 v40; // r10
  __int16 v41; // r9
  __int64 v42; // r9
  _WORD *v43; // rcx
  __int64 v44; // r14
  bool v45; // cf
  unsigned __int64 v46; // r14
  WCHAR *v47; // rdx
  unsigned int v48; // ebx
  _BYTE *v49; // rbx
  LSTATUS v50; // eax
  WCHAR *v51; // r9
  unsigned __int64 v52; // r8
  WCHAR *v53; // rax
  DWORD *v54; // rcx
  WCHAR v55; // r10
  DWORD *v56; // r9
  WCHAR *v57; // rcx
  unsigned __int64 v58; // r14
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpSubKey; // [rsp+68h] [rbp-98h] BYREF
  __int64 v65; // [rsp+70h] [rbp-90h]
  __int64 v66; // [rsp+78h] [rbp-88h]
  HKEY v67; // [rsp+80h] [rbp-80h] BYREF
  DWORD cSubKeys; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 **v69; // [rsp+90h] [rbp-70h] BYREF
  __int64 v70; // [rsp+98h] [rbp-68h] BYREF
  DWORD cchName; // [rsp+A0h] [rbp-60h] BYREF
  DWORD pcbData; // [rsp+A4h] [rbp-5Ch] BYREF
  HKEY v73; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 **v74; // [rsp+B0h] [rbp-50h]
  _WORD v75[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR v76[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR Name[256]; // [rsp+4E0h] [rbp+3E0h] BYREF
  WCHAR pvData[264]; // [rsp+6E0h] [rbp+5E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+948h] [rbp+848h]

  v69 = a4;
  v5 = a3;
  v74 = a5;
  if ( a2 )
    *(_QWORD *)a2 = 0;
  if ( a3 )
    *(_QWORD *)a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *(_BYTE *)a5 = 0;
  v7 = 0;
  v73 = 0;
  pv = 0;
  v8 = -1;
  if ( this )
  {
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)this + v9) );
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v70,
      (char *)this,
      v9,
      (const char *)a4);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &pv,
      &v70);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v70);
    v10 = pv;
    if ( !pv )
    {
      v11 = -2147024882;
      v12 = 2147942414LL;
      v13 = 412;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
        (const char *)v12,
        phkResult);
LABEL_15:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
LABEL_124:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v73);
      return v11;
    }
  }
  else
  {
    pv = 0;
    CurrentUserSidString = CreativeFramework::LockScreenCreativeConfigHelpers::GetCurrentUserSidString(
                             (CreativeFramework::LockScreenCreativeConfigHelpers *)&pv,
                             a5);
    v11 = CurrentUserSidString;
    if ( CurrentUserSidString < 0 )
    {
      v12 = (unsigned int)CurrentUserSidString;
      v13 = 417;
      goto LABEL_14;
    }
    v10 = pv;
  }
  lpSubKey = 0;
  v65 = 0;
  v66 = 0;
  v15 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
          &lpSubKey,
          L"%s\\%s",
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Creative",
          v10);
  v11 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A5,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
      (const char *)(unsigned int)v15,
      phkResult);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSubKey);
    goto LABEL_15;
  }
  v67 = 0;
  v16 = (WCHAR *)lpSubKey;
  v17 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x2001Fu, &v67);
  v11 = v17;
  if ( v17 )
  {
    if ( v17 > 0 )
      v11 = (unsigned __int16)v17 | 0x80070000;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v67);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSubKey);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
    if ( (v11 & 0x80000000) != 0 )
      goto LABEL_124;
  }
  else
  {
    v7 = v67;
    v67 = 0;
    v73 = v7;
    if ( v16 )
      CoTaskMemFree(v16);
    if ( v10 )
      CoTaskMemFree(v10);
  }
  cSubKeys = 0;
  v18 = RegQueryInfoKeyW(v7, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( v18 )
  {
    v19 = 441;
LABEL_32:
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v19,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
            (const char *)v18,
            phkResulta);
    goto LABEL_124;
  }
  v20 = 0;
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName = 256;
    v18 = RegEnumKeyExW(v7, i, Name, &cchName, 0, 0, 0, 0);
    if ( v18 )
    {
      v19 = 447;
      goto LABEL_32;
    }
    v22 = _o__wcstoui64(Name, 0, 10);
    if ( v22 > v20 )
      v20 = v22;
  }
  if ( !v20 )
  {
    v11 = -2147024894;
    goto LABEL_124;
  }
  lpSubKey = 0;
  v65 = 0;
  v66 = 0;
  v23 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
          &lpSubKey,
          L"%llu",
          v20);
  v11 = v23;
  if ( v23 < 0 )
  {
    v24 = 459;
LABEL_44:
    v25 = (unsigned int)v23;
LABEL_45:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
      (const char *)v25,
      phkResulta);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSubKey);
    goto LABEL_124;
  }
  if ( a2 )
  {
    pcbData = 522;
    ValueW = RegGetValueW(v7, lpSubKey, L"contentId", 0x20000002u, 0, pvData, &pcbData);
    v11 = ValueW;
    if ( ValueW > 0 )
      v11 = (unsigned __int16)ValueW | 0x80070000;
    if ( ((v11 + 0x80000000) & 0x80000000) == 0 && v11 != -2147024894 )
    {
      v25 = v11;
      v24 = 465;
      goto LABEL_45;
    }
    v23 = _AllocString<CTCoAllocPolicy>(v28, v27, pvData, a2);
    v11 = v23;
    if ( v23 < 0 )
    {
      v24 = 466;
      goto LABEL_44;
    }
  }
  if ( !v5 )
    goto LABEL_70;
  LODWORD(v70) = 522;
  v29 = RegGetValueW(v7, lpSubKey, L"landscapeImage", 0x20000002u, 0, v75, (LPDWORD)&v70);
  v30 = v29;
  if ( v29 > 0 )
    v30 = (unsigned __int16)v29 | 0x80070000;
  if ( (int)(v30 + 0x80000000) >= 0 && v30 != -2147024894 )
  {
    v31 = 473;
LABEL_60:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
      (const char *)v30,
      phkResultb);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSubKey);
    v11 = v30;
    goto LABEL_124;
  }
  v32 = -1;
  do
    ++v32;
  while ( v75[v32] );
  *(_QWORD *)v5 = 0;
  v33 = v32 + 1;
  if ( v32 + 1 < v32 || (pv = 0, !is_mul_ok(v33, 2u)) )
  {
    v30 = -2147024362;
    goto LABEL_89;
  }
  v34 = CoTaskMemAlloc(2 * v33);
  v35 = v34;
  *(_QWORD *)v5 = v34;
  v30 = v34 == 0 ? 0x8007000E : 0;
  v5 = 0;
  if ( !v34 )
  {
LABEL_89:
    v31 = 474;
    goto LABEL_60;
  }
  if ( v33 > 0x7FFFFFFF )
  {
LABEL_69:
    *v34 = 0;
    goto LABEL_70;
  }
  if ( v32 >= 0x7FFFFFFF )
  {
    if ( v32 == -1 )
      goto LABEL_70;
    goto LABEL_69;
  }
  v38 = v75;
  v39 = v32 + 1;
  v40 = 0;
  do
  {
    if ( !v32 )
      break;
    v41 = *v38;
    if ( !*v38 )
      break;
    ++v38;
    *v34++ = v41;
    --v32;
    ++v40;
    --v39;
  }
  while ( v39 );
  v42 = v40 - 1;
  if ( v39 )
    v42 = v40;
  v43 = v34 - 1;
  if ( v39 )
    v43 = v34;
  *v43 = 0;
  if ( v39 )
  {
    v45 = v33 == v42;
    v44 = v33 - v42;
    if ( !v45 && v44 != 1 && (unsigned __int64)(2 * v44) > 2 )
      memset_0(&v35[v42 + 1], 0, 2 * v44 - 2);
  }
LABEL_70:
  v36 = v69;
  if ( !v69 )
    goto LABEL_98;
  LODWORD(v67) = 522;
  v37 = RegGetValueW(v7, lpSubKey, L"portraitImage", 0x20000002u, v5, v76, (LPDWORD)&v67);
  v30 = v37;
  if ( v37 > 0 )
    v30 = (unsigned __int16)v37 | 0x80070000;
  if ( (int)(v30 + 0x80000000) >= 0 && v30 != -2147024894 )
  {
    v31 = 481;
    goto LABEL_60;
  }
  do
    ++v8;
  while ( v76[v8] != (_WORD)v5 );
  *v36 = v5;
  v46 = v8 + 1;
  if ( v8 + 1 >= v8 && (pv = v5, is_mul_ok(v46, 2u)) )
  {
    v47 = (WCHAR *)CoTaskMemAlloc(2 * v46);
    *v36 = v47;
    v48 = v47 == 0 ? 0x8007000E : 0;
    if ( v47 )
    {
      if ( v46 <= 0x7FFFFFFF )
      {
        if ( v8 < 0x7FFFFFFF )
        {
          v51 = v76;
          v52 = v8 + 1;
          v53 = v47;
          v54 = v5;
          do
          {
            if ( !v8 )
              break;
            v55 = *v51;
            if ( !*v51 )
              break;
            ++v51;
            *v53++ = v55;
            --v8;
            v54 = (DWORD *)((char *)v54 + 1);
            --v52;
          }
          while ( v52 );
          v56 = (DWORD *)((char *)v54 - 1);
          if ( v52 )
            v56 = v54;
          v57 = v53 - 1;
          if ( v52 )
            v57 = v53;
          *v57 = (unsigned __int16)v5;
          if ( v52 )
          {
            v45 = v46 == (_QWORD)v56;
            v58 = v46 - (_QWORD)v56;
            if ( !v45 && v58 != 1 && 2 * v58 > 2 )
              memset_0(&v47[(_QWORD)v56 + 1], 0, 2 * v58 - 2);
          }
LABEL_98:
          v49 = v74;
          if ( v74 )
          {
            LODWORD(v69) = (_DWORD)v5;
            LODWORD(pv) = 4;
            v50 = RegGetValueW(v7, lpSubKey, L"showImageOnSecureLock", 0x20000010u, v5, &v69, (LPDWORD)&pv);
            v11 = v50;
            if ( v50 > 0 )
              v11 = (unsigned __int16)v50 | 0x80070000;
            if ( (int)(v11 + 0x80000000) >= 0 && v11 != -2147024894 )
            {
              v25 = v11;
              v24 = 489;
              goto LABEL_45;
            }
            *v49 = (_DWORD)v69 != (_DWORD)v5;
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSubKey);
          v11 = (unsigned int)v5;
          goto LABEL_124;
        }
        if ( v8 == -1 )
          goto LABEL_98;
      }
      *v47 = (unsigned __int16)v5;
      goto LABEL_98;
    }
  }
  else
  {
    v48 = -2147024362;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E2,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\LockScreenCreativeConfigHelpers.h",
    (const char *)v48,
    phkResultb);
  if ( lpSubKey != (LPCWSTR)v5 )
    CoTaskMemFree((LPVOID)lpSubKey);
  if ( v7 )
    RegCloseKey(v7);
  return v48;
}

```

## disassembly

```asm
0x180009f0c  push    rbp
0x180009f0e  push    rbx
0x180009f0f  push    rsi
0x180009f10  push    rdi
0x180009f11  push    r12
0x180009f13  push    r13
0x180009f15  push    r14
0x180009f17  push    r15
0x180009f19  lea     rbp, [rsp-808h]
0x180009f21  sub     rsp, 908h
0x180009f28  mov     rax, cs:__security_cookie
0x180009f2f  xor     rax, rsp
0x180009f32  mov     [rbp+840h+var_50], rax
0x180009f39  mov     rax, r9
0x180009f3c  mov     [rbp+840h+var_8B0], rax
0x180009f40  mov     r12, r8
0x180009f43  mov     r15, rdx
0x180009f46  mov     rdx, [rbp+840h+arg_20]; unsigned __int16 **
0x180009f4d  mov     [rbp+840h+var_890], rdx
0x180009f51  xor     r14d, r14d
0x180009f54  test    r15, r15
0x180009f57  jz      short loc_180009F5C
0x180009f59  mov     [r15], r14
0x180009f5c  test    r12, r12
0x180009f5f  jz      short loc_180009F64
0x180009f61  mov     [r8], r14
0x180009f64  test    rax, rax
0x180009f67  jz      short loc_180009F6C
0x180009f69  mov     [r9], r14
0x180009f6c  test    rdx, rdx
0x180009f6f  jz      short loc_180009F74
0x180009f71  mov     [rdx], r14b
0x180009f74  mov     rdi, r14
0x180009f77  mov     [rbp+840h+var_898], r14
0x180009f7b  mov     [rsp+940h+pv], r14
0x180009f80  or      r13, 0FFFFFFFFFFFFFFFFh
0x180009f84  test    rcx, rcx
0x180009f87  jz      short loc_180009FF3
0x180009f89  mov     r8, r13
0x180009f8c  inc     r8
0x180009f8f  cmp     [rcx+r8*2], r14w
0x180009f94  jnz     short loc_180009F8C
0x180009f96  mov     rdx, rcx
0x180009f99  lea     rcx, [rbp+840h+var_8A8]
0x180009f9d  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180009fa2  lea     rdx, [rbp+840h+var_8A8]
0x180009fa6  lea     rcx, [rsp+940h+pv]
0x180009fab  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180009fb0  lea     rcx, [rbp+840h+var_8A8]
0x180009fb4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180009fb9  mov     rbx, [rsp+940h+pv]
0x180009fbe  test    rbx, rbx
0x180009fc1  jnz     short loc_18000A017
0x180009fc3  mov     esi, 8007000Eh
0x180009fc8  mov     r9d, esi; char *
0x180009fcb  mov     edx, 19Ch; void *
0x180009fd0  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x180009fd7  mov     rcx, [rbp+848h]; this
0x180009fde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009fe3  nop
0x180009fe4  lea     rcx, [rsp+940h+pv]
0x180009fe9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180009fee  jmp     loc_18000A6E2
0x180009ff3  mov     [rsp+940h+pv], r14
0x180009ff8  lea     rcx, [rsp+940h+pv]; this
0x180009ffd  call    ?GetCurrentUserSidString@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEAPEAG@Z; CreativeFramework::LockScreenCreativeConfigHelpers::GetCurrentUserSidString(ushort * *)
0x18000a002  mov     esi, eax
0x18000a004  test    eax, eax
0x18000a006  jns     short loc_18000A012
0x18000a008  mov     r9d, eax
0x18000a00b  mov     edx, 1A1h
0x18000a010  jmp     short loc_180009FD0
0x18000a012  mov     rbx, [rsp+940h+pv]
0x18000a017  mov     [rsp+940h+lpSubKey], r14
0x18000a01c  mov     [rsp+940h+var_8D0], r14
0x18000a021  mov     [rsp+940h+var_8C8], r14
0x18000a026  mov     r9, rbx
0x18000a029  lea     r8, ?c_logonUICreativeKeyPath@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000a030  lea     rdx, aSS_1; "%s\\%s"
0x18000a037  lea     rcx, [rsp+940h+lpSubKey]
0x18000a03c  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18000a041  mov     esi, eax
0x18000a043  test    eax, eax
0x18000a045  jns     short loc_18000A072
0x18000a047  mov     rcx, [rbp+848h]; this
0x18000a04e  mov     r9d, eax; char *
0x18000a051  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18000a058  mov     edx, 1A5h; void *
0x18000a05d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a062  nop
0x18000a063  lea     rcx, [rsp+940h+lpSubKey]
0x18000a068  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000a06d  jmp     loc_180009FE4
0x18000a072  mov     [rbp+840h+var_8C0], r14
0x18000a076  lea     rax, [rbp+840h+var_8C0]
0x18000a07a  mov     [rsp+940h+phkResult], rax; phkResult
0x18000a07f  mov     r9d, 2001Fh; samDesired
0x18000a085  xor     r8d, r8d; ulOptions
0x18000a088  mov     r14, [rsp+940h+lpSubKey]
0x18000a08d  mov     rdx, r14; lpSubKey
0x18000a090  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a097  call    cs:__imp_RegOpenKeyExW
0x18000a09d  mov     esi, eax
0x18000a09f  xor     ecx, ecx
0x18000a0a1  test    eax, eax
0x18000a0a3  jz      short loc_18000A0DE
0x18000a0a5  xor     r14d, r14d
0x18000a0a8  test    eax, eax
0x18000a0aa  jle     short loc_18000A0B5
0x18000a0ac  movzx   esi, ax
0x18000a0af  or      esi, 80070000h
0x18000a0b5  lea     rcx, [rbp+840h+var_8C0]
0x18000a0b9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000a0be  nop
0x18000a0bf  lea     rcx, [rsp+940h+lpSubKey]
0x18000a0c4  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000a0c9  nop
0x18000a0ca  lea     rcx, [rsp+940h+pv]
0x18000a0cf  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000a0d4  test    esi, esi
0x18000a0d6  js      loc_18000A6E2
0x18000a0dc  jmp     short loc_18000A10A
0x18000a0de  mov     rdi, [rbp+840h+var_8C0]
0x18000a0e2  mov     [rbp+840h+var_8C0], rcx
0x18000a0e6  mov     [rbp+840h+var_898], rdi
0x18000a0ea  test    r14, r14
0x18000a0ed  jz      short loc_18000A0F9
0x18000a0ef  mov     rcx, r14; pv
0x18000a0f2  call    cs:__imp_CoTaskMemFree
0x18000a0f8  nop
0x18000a0f9  xor     r14d, r14d
0x18000a0fc  test    rbx, rbx
0x18000a0ff  jz      short loc_18000A10A
0x18000a101  mov     rcx, rbx; pv
0x18000a104  call    cs:__imp_CoTaskMemFree
0x18000a10a  mov     [rbp+840h+cSubKeys], r14d
0x18000a10e  mov     [rsp+940h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18000a113  mov     [rsp+940h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18000a118  mov     [rsp+940h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18000a11d  mov     [rsp+940h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18000a122  mov     [rsp+940h+lpcValues], r14; lpcValues
0x18000a127  mov     [rsp+940h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18000a12c  mov     [rsp+940h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x18000a131  lea     rax, [rbp+840h+cSubKeys]
0x18000a135  mov     [rsp+940h+phkResult], rax; int
0x18000a13a  xor     r9d, r9d; lpReserved
0x18000a13d  xor     r8d, r8d; lpcchClass
0x18000a140  xor     edx, edx; lpClass
0x18000a142  mov     rcx, rdi; hKey
0x18000a145  call    cs:__imp_RegQueryInfoKeyW
0x18000a14b  test    eax, eax
0x18000a14d  jz      short loc_18000A171
0x18000a14f  mov     edx, 1B9h; void *
0x18000a154  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18000a15b  mov     r9d, eax; char *
0x18000a15e  mov     rcx, [rbp+848h]; this
0x18000a165  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000a16a  mov     esi, eax
0x18000a16c  jmp     loc_18000A6E2
0x18000a171  mov     rbx, r14
0x18000a174  mov     esi, r14d
0x18000a177  cmp     esi, [rbp+840h+cSubKeys]
0x18000a17a  jnb     short loc_18000A1D9
0x18000a17c  mov     [rbp+840h+cchName], 100h
0x18000a183  mov     [rsp+940h+lpcValues], r14; lpftLastWriteTime
0x18000a188  mov     [rsp+940h+lpcbMaxClassLen], r14; lpcchClass
0x18000a18d  mov     [rsp+940h+lpcbMaxSubKeyLen], r14; lpClass
0x18000a192  mov     [rsp+940h+phkResult], r14; lpReserved
0x18000a197  lea     r9, [rbp+840h+cchName]; lpcchName
0x18000a19b  lea     r8, [rbp+840h+Name]; lpName
0x18000a1a2  mov     edx, esi; dwIndex
0x18000a1a4  mov     rcx, rdi; hKey
0x18000a1a7  call    cs:__imp_RegEnumKeyExW
0x18000a1ad  test    eax, eax
0x18000a1af  jnz     short loc_18000A1CF
0x18000a1b1  xor     edx, edx
0x18000a1b3  lea     r8d, [rax+0Ah]
0x18000a1b7  lea     rcx, [rbp+840h+Name]
0x18000a1be  call    cs:__imp__o__wcstoui64
0x18000a1c4  cmp     rax, rbx
0x18000a1c7  cmova   rbx, rax
0x18000a1cb  inc     esi
0x18000a1cd  jmp     short loc_18000A177
0x18000a1cf  mov     edx, 1BFh
0x18000a1d4  jmp     loc_18000A154
0x18000a1d9  test    rbx, rbx
0x18000a1dc  jnz     short loc_18000A1E8
0x18000a1de  mov     esi, 80070002h
0x18000a1e3  jmp     loc_18000A6E2
0x18000a1e8  mov     [rsp+940h+lpSubKey], r14
0x18000a1ed  mov     [rsp+940h+var_8D0], r14
0x18000a1f2  mov     [rsp+940h+var_8C8], r14
0x18000a1f7  mov     r8, rbx
0x18000a1fa  lea     rdx, aLlu; "%llu"
0x18000a201  lea     rcx, [rsp+940h+lpSubKey]
0x18000a206  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18000a20b  mov     esi, eax
0x18000a20d  test    eax, eax
0x18000a20f  jns     short loc_18000A23C
0x18000a211  mov     edx, 1CBh; void *
0x18000a216  mov     r9d, eax; char *
0x18000a219  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18000a220  mov     rcx, [rbp+848h]; this
0x18000a227  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a22c  nop
0x18000a22d  lea     rcx, [rsp+940h+lpSubKey]
0x18000a232  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000a237  jmp     loc_18000A6E2
0x18000a23c  mov     ebx, 80000000h
0x18000a241  test    r15, r15
0x18000a244  jz      loc_18000A2D0
0x18000a24a  mov     [rbp+840h+pcbData], 20Ah
0x18000a251  lea     rax, [rbp+840h+pcbData]
0x18000a255  mov     [rsp+940h+lpcbMaxClassLen], rax; pcbData
0x18000a25a  lea     rax, [rbp+840h+pvData]
0x18000a261  mov     [rsp+940h+lpcbMaxSubKeyLen], rax; pvData
0x18000a266  mov     [rsp+940h+phkResult], r14; pdwType
0x18000a26b  mov     r9d, 20000002h; dwFlags
0x18000a271  lea     r8, ?c_contentIdRegKey@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "contentId"
0x18000a278  mov     rdx, [rsp+940h+lpSubKey]; lpSubKey
0x18000a27d  mov     rcx, rdi; hkey
0x18000a280  call    cs:__imp_RegGetValueW
0x18000a286  mov     esi, eax
0x18000a288  test    eax, eax
0x18000a28a  jle     short loc_18000A295
0x18000a28c  movzx   esi, ax
0x18000a28f  or      esi, 80070000h
0x18000a295  lea     eax, [rsi+rbx]
0x18000a298  test    ebx, eax
0x18000a29a  jnz     short loc_18000A2B1
0x18000a29c  cmp     esi, 80070002h
0x18000a2a2  jz      short loc_18000A2B1
0x18000a2a4  mov     r9d, esi
0x18000a2a7  mov     edx, 1D1h
0x18000a2ac  jmp     loc_18000A219
0x18000a2b1  mov     r9, r15
0x18000a2b4  lea     r8, [rbp+840h+pvData]
0x18000a2bb  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18000a2c0  mov     esi, eax
0x18000a2c2  test    eax, eax
0x18000a2c4  jns     short loc_18000A2D0
0x18000a2c6  mov     edx, 1D2h
0x18000a2cb  jmp     loc_18000A216
0x18000a2d0  mov     esi, 8007000Eh
0x18000a2d5  test    r12, r12
0x18000a2d8  jz      loc_18000A3E6
0x18000a2de  mov     dword ptr [rbp+840h+var_8A8], 20Ah
0x18000a2e5  lea     rax, [rbp+840h+var_8A8]
0x18000a2e9  mov     [rsp+940h+lpcbMaxClassLen], rax; pcbData
0x18000a2ee  lea     rax, [rbp+840h+var_880]
0x18000a2f2  mov     [rsp+940h+lpcbMaxSubKeyLen], rax; pvData
0x18000a2f7  mov     [rsp+940h+phkResult], r14; int
0x18000a2fc  mov     r9d, 20000002h; dwFlags
0x18000a302  lea     r8, ?c_landscapeRegKey@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "landscapeImage"
0x18000a309  mov     rdx, [rsp+940h+lpSubKey]; lpSubKey
0x18000a30e  mov     rcx, rdi; hkey
0x18000a311  call    cs:__imp_RegGetValueW
0x18000a317  mov     ebx, eax
0x18000a319  test    eax, eax
0x18000a31b  jle     short loc_18000A326
0x18000a31d  movzx   ebx, ax
0x18000a320  or      ebx, 80070000h
0x18000a326  mov     ecx, 80000000h
0x18000a32b  lea     eax, [rbx+rcx]
0x18000a32e  test    ecx, eax
0x18000a330  jnz     short loc_18000A367
0x18000a332  cmp     ebx, 80070002h
0x18000a338  jz      short loc_18000A367
0x18000a33a  mov     edx, 1D9h; void *
0x18000a33f  mov     rcx, [rbp+848h]; this
0x18000a346  mov     r9d, ebx; char *
0x18000a349  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\LockS"...
0x18000a350  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a355  nop
0x18000a356  lea     rcx, [rsp+940h+lpSubKey]
0x18000a35b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000a360  mov     esi, ebx
0x18000a362  jmp     loc_18000A6E2
0x18000a367  lea     rax, [rbp+840h+var_880]
0x18000a36b  mov     r15, r13
0x18000a36e  inc     r15
0x18000a371  cmp     [rax+r15*2], r14w
0x18000a376  jnz     short loc_18000A36E
0x18000a378  mov     [r12], r14
0x18000a37c  lea     r14, [r15+1]
0x18000a380  cmp     r14, r15
0x18000a383  jb      loc_18000A4ED
0x18000a389  xor     ecx, ecx
0x18000a38b  mov     [rsp+940h+pv], rcx
0x18000a390  lea     eax, [rcx+2]
0x18000a393  mul     r14
0x18000a396  test    rdx, rdx
0x18000a399  jnz     loc_18000A4ED
0x18000a39f  mov     rcx, rax; cb
0x18000a3a2  call    cs:__imp_CoTaskMemAlloc
0x18000a3a8  mov     rdx, rax
0x18000a3ab  mov     [r12], rax
0x18000a3af  mov     rcx, rax
0x18000a3b2  neg     rcx
0x18000a3b5  sbb     ebx, ebx
  ... truncated ...
```
