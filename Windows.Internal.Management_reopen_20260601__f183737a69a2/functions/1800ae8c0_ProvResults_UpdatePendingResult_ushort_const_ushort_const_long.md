# ProvResults::UpdatePendingResult(ushort const *,ushort const *,long)

- ea: `0x1800ae8c0`
- end: `0x1800af08e`
- name: `?UpdatePendingResult@ProvResults@@SA_NPEBG0J@Z`
- size: `1998`
- prototype: `bool __fastcall(LPCOLESTR lpsz, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18006f2f0`

## callees

- `0x180001350`
- `0x180004458`
- `0x180004eb0`
- `0x180005a74`
- `0x18000d50c`
- `0x1800131a8`
- `0x1800161ec`
- `0x180016268`
- `0x180016698`
- `0x180017118`
- `0x18003973c`
- `0x18003e5d4`
- `0x18006ac14`
- `0x18007b580`
- `0x1800ac230`
- `0x1800ada70`
- `0x1800ae49c`
- `0x1800ae8c0`
- `0x1800af094`
- `0x1800af770`
- `0x1800b4b04`
- `0x1800b4e14`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800aeb74`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800aeb74`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800aefb3`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800aefb3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800aeed9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800aeed9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800aef99`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800aef99`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aecf7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aed9b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aecf7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aed9b`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800aebd5`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800aebd5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ae9e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ae9e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800aea51`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800aea51`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
char __fastcall ProvResults::UpdatePendingResult(LPCOLESTR lpsz, const unsigned __int16 *a2, DWORD a3)
{
  __int64 v6; // rdi
  __int64 v7; // r8
  __int128 *p_Src; // rcx
  const WCHAR *v9; // rdx
  unsigned int v10; // eax
  unsigned int v11; // eax
  DWORD v12; // edx
  DWORD v13; // eax
  __int64 v14; // r8
  const char *v15; // r9
  DWORD v16; // esi
  DWORD i; // edx
  __int64 v18; // r8
  __int128 *v19; // rdx
  _QWORD *v20; // rax
  __int64 v23; // r8
  const WCHAR *v24; // rcx
  LSTATUS v25; // eax
  __int64 v26; // r8
  __int64 v27; // r9
  bool v28; // sf
  unsigned __int64 v29; // rbx
  LPBYTE v30; // rsi
  unsigned __int64 v31; // rcx
  BYTE *v32; // rax
  size_t v33; // rbx
  LSTATUS v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rcx
  bool v37; // sf
  __int64 v38; // r8
  int v39; // ecx
  int v40; // r8d
  int v41; // r9d
  __int128 *v42; // rax
  LPCWSTR *v43; // rax
  __int128 *v44; // rax
  LPCWSTR *v45; // r8
  LPCWSTR *v46; // r9
  bool IsStateSeparationEnabled; // al
  const wchar_t *v48; // rdx
  LPCWSTR *v49; // rdx
  const WCHAR *v50; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cchValueName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbMaxValueLen; // [rsp+6Ch] [rbp-94h] BYREF
  HKEY v57; // [rsp+70h] [rbp-90h] BYREF
  DWORD Type[2]; // [rsp+78h] [rbp-88h] BYREF
  DWORD cValues; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  LPBYTE v61[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v62; // [rsp+A0h] [rbp-60h]
  LPWSTR lpValueName[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v64; // [rsp+B8h] [rbp-48h]
  LPBYTE lpData[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v66; // [rsp+D0h] [rbp-30h]
  LPCWSTR *v67; // [rsp+D8h] [rbp-28h] BYREF
  LPCWSTR v68[2]; // [rsp+E0h] [rbp-20h] BYREF
  __m128i v69; // [rsp+F0h] [rbp-10h]
  __int128 v70; // [rsp+100h] [rbp+0h] BYREF
  __m128i v71; // [rsp+110h] [rbp+10h]
  __int128 Src; // [rsp+120h] [rbp+20h] BYREF
  __m128i si128; // [rsp+130h] [rbp+30h]
  GUID iid; // [rsp+140h] [rbp+40h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+150h] [rbp+50h] BYREF
  LPCWSTR v76[2]; // [rsp+170h] [rbp+70h] BYREF
  __m128i v77; // [rsp+180h] [rbp+80h]
  __int128 v78; // [rsp+190h] [rbp+90h] BYREF
  __m128i v79; // [rsp+1A0h] [rbp+A0h]
  _QWORD v80[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int64 v81; // [rsp+1C0h] [rbp+C0h]
  unsigned __int64 v82; // [rsp+1C8h] [rbp+C8h]
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src) = 0;
  if ( *lpsz != 123 )
    std::wstring::_Append<unsigned short>(&Src);
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( lpsz[v7] );
  std::wstring::_Append<unsigned short>(&Src);
  p_Src = &Src;
  if ( si128.m128i_i64[1] > 7uLL )
    p_Src = (__int128 *)Src;
  if ( *((_WORD *)p_Src + si128.m128i_i64[0] - 1) != 125 )
    std::wstring::_Append<unsigned short>(&Src);
  *(_OWORD *)v68 = 0;
  v69 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v68[0]) = 0;
  PackageEnroller::GetPackageIdFromEnrollmentId(&Src, v68);
  v9 = (const WCHAR *)v68;
  if ( v69.m128i_i64[1] > 7uLL )
    v9 = v68[0];
  ProvResults::GetPackageKey(&hKey, v9);
  v57 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v57,
    0);
  v10 = RegOpenKeyExW(hKey, L"PendingResults", 0, 0xBu, &v57);
  if ( v10 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x14A,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      (const char *)v10,
      phkResult);
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cValues = 0;
  v11 = RegQueryInfoKeyW(v57, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  if ( v11 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x150,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      (const char *)v11,
      phkResulta);
  v12 = cbMaxValueNameLen;
  v13 = cbMaxValueNameLen + 1;
  v14 = 0xFFFFFFFFLL;
  if ( cbMaxValueNameLen + 1 >= cbMaxValueNameLen )
    v14 = v13;
  v15 = v13 < cbMaxValueNameLen ? (const char *)0x80070216LL : 0LL;
  cbMaxValueNameLen = v14;
  if ( v13 < v12 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x153,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provresults.cpp",
      v15,
      phkResulta);
  *(_OWORD *)lpValueName = 0;
  v64 = 0;
  if ( (_DWORD)v14 )
    std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(lpValueName, (unsigned int)v14, v14, v15);
  *(_OWORD *)lpData = 0;
  v66 = 0;
  if ( (unsigned __int64)(cbMaxValueLen + 1) >> 1 )
    std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(
      lpData,
      (unsigned __int64)(cbMaxValueLen + 1) >> 1,
      v14,
      v15);
  v16 = 0;
  std::wstring::wstring(v80, a2);
  *(_OWORD *)v76 = 0;
  v77 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v76[0]) = 0;
  v70 = 0;
  v71 = v77;
  LOWORD(v70) = 0;
  for ( i = 0; ; i = v16 )
  {
    cbData = cbMaxValueLen;
    cchValueName = cbMaxValueNameLen;
    Type[0] = 0;
    if ( RegEnumValueW(v57, i, lpValueName[0], &cchValueName, 0, Type, lpData[0], &cbData) )
      goto LABEL_32;
    if ( Type[0] == 1 )
    {
      v18 = -1;
      do
        ++v18;
      while ( lpValueName[0][v18] );
      std::wstring::_Assign<unsigned short>(&v70, lpValueName[0]);
      if ( v81 >= v71.m128i_i64[0] )
      {
        v19 = &v70;
        if ( v71.m128i_i64[1] > 7uLL )
          v19 = (__int128 *)v70;
        v20 = v80;
        if ( v82 > 7 )
          v20 = (_QWORD *)v80[0];
        if ( !(unsigned int)_o__wcsicmp((char *)v20 + 2 * (v81 - v71.m128i_i64[0]), v19) )
          break;
      }
    }
    ++v16;
  }
  v23 = -1;
  do
    ++v23;
  while ( *(_WORD *)&lpData[0][2 * v23] );
  std::wstring::_Assign<unsigned short>(v76, lpData[0]);
  v24 = (const WCHAR *)v76;
  if ( v77.m128i_i64[1] > 7uLL )
    v24 = v76[0];
  if ( !ProvResults::UpdatePendingResultInternal(v24, a3) )
  {
LABEL_32:
    std::wstring::_Tidy_deallocate(&v70);
    std::wstring::_Tidy_deallocate(v76);
    std::wstring::_Tidy_deallocate(v80);
    std::vector<unsigned short>::_Tidy(lpData);
    std::vector<unsigned short>::_Tidy(lpValueName);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v57);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::_Tidy_deallocate(v68);
    std::wstring::_Tidy_deallocate(&Src);
    return 0;
  }
  cchValueName = 0;
  *(_OWORD *)v61 = 0;
  v62 = 0;
  v78 = 0;
  v79 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v78) = 0;
  v25 = RegQueryValueExW(hKey, L"Session", 0, 0, 0, &cchValueName);
  v28 = v25 < 0;
  if ( v25 > 0 )
    v28 = 1;
  if ( !v28 )
  {
    v29 = ((unsigned __int64)cchValueName >> 1) + 1;
    v30 = v61[1];
    v31 = (v61[1] - v61[0]) >> 1;
    if ( v29 < v31 )
    {
      v32 = &v61[0][2 * v29];
LABEL_47:
      v61[1] = v32;
      goto LABEL_48;
    }
    if ( v29 > v31 )
    {
      if ( v29 <= (signed __int64)(v62 - (unsigned __int64)v61[0]) >> 1 )
      {
        v33 = 2 * (v29 - v31);
        memset_0(v61[1], 0, v33);
        v32 = &v30[v33];
        goto LABEL_47;
      }
      std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(
        v61,
        ((unsigned __int64)cchValueName >> 1) + 1,
        v26,
        v27);
    }
LABEL_48:
    v34 = RegQueryValueExW(hKey, L"Session", 0, 0, v61[0], &cchValueName);
    v37 = v34 < 0;
    if ( v34 > 0 )
      v37 = 1;
    if ( v37 )
    {
      if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 2) != 0 )
      {
        v46 = v68;
        if ( v69.m128i_i64[1] > 7uLL )
          v46 = (LPCWSTR *)v68[0];
        McTemplateU0dz_EventWriteTransfer(v36, v35, a3, v46);
      }
    }
    else
    {
      v38 = -1;
      do
        ++v38;
      while ( *(_WORD *)&v61[0][2 * v38] );
      std::wstring::_Assign<unsigned short>(&v78, v61[0]);
      if ( (unsigned int)dword_1800FE488 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800FE488, 0x400000000000LL) )
      {
        v42 = &v70;
        if ( v71.m128i_i64[1] > 7uLL )
          v42 = (__int128 *)v70;
        *(_QWORD *)Type = v42;
        cbData = a3;
        v43 = v68;
        if ( v69.m128i_i64[1] > 7uLL )
          v43 = (LPCWSTR *)v68[0];
        v67 = v43;
        v44 = &v78;
        if ( v79.m128i_i64[1] > 7uLL )
          v44 = (__int128 *)v78;
        *(_QWORD *)&iid.Data1 = v44;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v39,
          (unsigned int)qword_1800EE008,
          v40,
          v41,
          (__int64)&iid,
          (__int64)&v67,
          (__int64)&cbData,
          (__int64)Type);
      }
      if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 1) != 0 )
      {
        v45 = v68;
        if ( v69.m128i_i64[1] > 7uLL )
          v45 = (LPCWSTR *)v68[0];
        McTemplateU0z_EventWriteTransfer(
          PROVISIONING_DIAGNOSTICS_Context,
          ProvResultUpdatePendingResultInternalSucceeded,
          v45);
      }
    }
  }
  if ( a3 != 44761091 )
  {
    RegDeleteValueW(v57, lpValueName[0]);
    if ( cValues == 1 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v57,
        0);
      IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
      v48 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\Results";
      if ( !IsStateSeparationEnabled )
        v48 = L"SOFTWARE\\Microsoft\\Provisioning\\Results";
      std::wstring::wstring(lpSubKey, v48);
      std::wstring::_Append<unsigned short>(lpSubKey);
      v49 = v68;
      if ( v69.m128i_i64[1] > 7uLL )
        v49 = (LPCWSTR *)v68[0];
      do
        ++v6;
      while ( *((_WORD *)v49 + v6) );
      std::wstring::_Append<unsigned short>(lpSubKey);
      std::wstring::_Append<unsigned short>(lpSubKey);
      std::wstring::_Append<unsigned short>(lpSubKey);
      v50 = (const WCHAR *)lpSubKey;
      if ( lpSubKey[3] > (LPCWSTR)7 )
        v50 = lpSubKey[0];
      RegDeleteTreeW(HKEY_LOCAL_MACHINE, v50);
      iid = 0;
      if ( IIDFromString(lpsz, &iid) >= 0 )
        UnregisterCspAlerts(&iid);
      std::wstring::_Tidy_deallocate(lpSubKey);
    }
  }
  std::wstring::_Tidy_deallocate(&v78);
  std::vector<unsigned short>::_Tidy(v61);
  std::wstring::_Tidy_deallocate(&v70);
  std::wstring::_Tidy_deallocate(v76);
  std::wstring::_Tidy_deallocate(v80);
  std::vector<unsigned short>::_Tidy(lpData);
  std::vector<unsigned short>::_Tidy(lpValueName);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v57);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::wstring::_Tidy_deallocate(v68);
  std::wstring::_Tidy_deallocate(&Src);
  return 1;
}

```

## disassembly

```asm
0x1800ae8c0  push    rbp
0x1800ae8c2  push    rbx
0x1800ae8c3  push    rsi
0x1800ae8c4  push    rdi
0x1800ae8c5  push    r12
0x1800ae8c7  push    r14
0x1800ae8c9  push    r15
0x1800ae8cb  lea     rbp, [rsp-0E0h]
0x1800ae8d3  sub     rsp, 1E0h
0x1800ae8da  mov     rax, cs:__security_cookie
0x1800ae8e1  xor     rax, rsp
0x1800ae8e4  mov     [rbp+110h+var_40], rax
0x1800ae8eb  mov     r14d, r8d
0x1800ae8ee  mov     rbx, rdx
0x1800ae8f1  mov     r15, rcx
0x1800ae8f4  xorps   xmm0, xmm0
0x1800ae8f7  movups  [rbp+110h+Src], xmm0
0x1800ae8fb  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800ae903  movdqu  [rbp+110h+var_E0], xmm1
0x1800ae908  xor     r12d, r12d
0x1800ae90b  mov     word ptr [rbp+110h+Src], r12w
0x1800ae910  lea     esi, [r12+1]
0x1800ae915  cmp     word ptr [rcx], 7Bh ; '{'
0x1800ae919  jz      short loc_1800AE92E
0x1800ae91b  mov     r8d, esi
0x1800ae91e  lea     rdx, asc_1800E3DD0; "{"
0x1800ae925  lea     rcx, [rbp+110h+Src]; Src
0x1800ae929  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800ae92e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800ae932  mov     r8, rdi
0x1800ae935  inc     r8
0x1800ae938  cmp     [r15+r8*2], r12w
0x1800ae93d  jnz     short loc_1800AE935
0x1800ae93f  mov     rdx, r15
0x1800ae942  lea     rcx, [rbp+110h+Src]; Src
0x1800ae946  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800ae94b  lea     rcx, [rbp+110h+Src]
0x1800ae94f  cmp     qword ptr [rbp+110h+var_E0+8], 7
0x1800ae954  cmova   rcx, qword ptr [rbp+110h+Src]
0x1800ae959  mov     rax, qword ptr [rbp+110h+var_E0]
0x1800ae95d  cmp     word ptr [rcx+rax*2-2], 7Dh ; '}'
0x1800ae963  jz      short loc_1800AE978
0x1800ae965  mov     r8, rsi
0x1800ae968  lea     rdx, asc_1800E4980; "}"
0x1800ae96f  lea     rcx, [rbp+110h+Src]; Src
0x1800ae973  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800ae978  xorps   xmm0, xmm0
0x1800ae97b  movups  xmmword ptr [rbp+110h+var_130], xmm0
0x1800ae97f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800ae987  movdqu  [rbp+110h+var_120], xmm1
0x1800ae98c  mov     word ptr [rbp+110h+var_130], r12w
0x1800ae991  lea     rdx, [rbp+110h+var_130]
0x1800ae995  lea     rcx, [rbp+110h+Src]
0x1800ae999  call    ?GetPackageIdFromEnrollmentId@PackageEnroller@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; PackageEnroller::GetPackageIdFromEnrollmentId(std::wstring const &,std::wstring &)
0x1800ae99e  lea     rdx, [rbp+110h+var_130]
0x1800ae9a2  cmp     qword ptr [rbp+110h+var_120+8], 7
0x1800ae9a7  cmova   rdx, [rbp+110h+var_130]; lpSubKey
0x1800ae9ac  lea     rcx, [rbp+110h+hKey]; phkResult
0x1800ae9b0  call    ?GetPackageKey@ProvResults@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGK@Z; ProvResults::GetPackageKey(ushort const *,ulong)
0x1800ae9b5  nop
0x1800ae9b6  mov     [rsp+210h+var_1A0], r12
0x1800ae9bb  xor     edx, edx
0x1800ae9bd  lea     rcx, [rsp+210h+var_1A0]
0x1800ae9c2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800ae9c7  lea     rax, [rsp+210h+var_1A0]
0x1800ae9cc  mov     [rsp+210h+phkResult], rax; unsigned int
0x1800ae9d1  mov     r9d, 0Bh; samDesired
0x1800ae9d7  xor     r8d, r8d; ulOptions
0x1800ae9da  lea     rdx, aPendingresults; "PendingResults"
0x1800ae9e1  mov     rcx, [rbp+110h+hKey]; hKey
0x1800ae9e5  call    cs:__imp_RegOpenKeyExW
0x1800ae9ec  nop     dword ptr [rax+rax+00h]
0x1800ae9f1  mov     rcx, [rbp+118h]; this
0x1800ae9f8  test    eax, eax
0x1800ae9fa  jnz     loc_1800AF064
0x1800aea00  mov     [rsp+210h+cbMaxValueNameLen], r12d
0x1800aea05  mov     [rsp+210h+cbMaxValueLen], r12d
0x1800aea0a  mov     [rbp+110h+cValues], r12d
0x1800aea0e  mov     [rsp+210h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800aea13  mov     [rsp+210h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1800aea18  lea     rax, [rsp+210h+cbMaxValueLen]
0x1800aea1d  mov     [rsp+210h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800aea22  lea     rax, [rsp+210h+cbMaxValueNameLen]
0x1800aea27  mov     [rsp+210h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800aea2c  lea     rax, [rbp+110h+cValues]
0x1800aea30  mov     [rsp+210h+lpcValues], rax; lpcValues
0x1800aea35  mov     [rsp+210h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1800aea3a  mov     [rsp+210h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x1800aea3f  mov     [rsp+210h+phkResult], r12; unsigned int
0x1800aea44  xor     r9d, r9d; lpReserved
0x1800aea47  xor     r8d, r8d; lpcchClass
0x1800aea4a  xor     edx, edx; lpClass
0x1800aea4c  mov     rcx, [rsp+210h+var_1A0]; hKey
0x1800aea51  call    cs:__imp_RegQueryInfoKeyW
0x1800aea58  nop     dword ptr [rax+rax+00h]
0x1800aea5d  mov     rcx, [rbp+118h]; this
0x1800aea64  test    eax, eax
0x1800aea66  jnz     loc_1800AF079
0x1800aea6c  mov     edx, [rsp+210h+cbMaxValueNameLen]
0x1800aea70  lea     eax, [rdx+1]
0x1800aea73  or      r8d, 0FFFFFFFFh
0x1800aea77  cmp     eax, edx
0x1800aea79  cmovnb  r8d, eax
0x1800aea7d  sbb     r9d, r9d
0x1800aea80  and     r9d, 80070216h; char *
0x1800aea87  mov     [rsp+210h+cbMaxValueNameLen], r8d
0x1800aea8c  mov     rcx, [rbp+118h]; this
0x1800aea93  cmp     eax, edx
0x1800aea95  jb      loc_1800AF052
0x1800aea9b  xorps   xmm0, xmm0
0x1800aea9e  movdqu  xmmword ptr [rbp+110h+lpValueName], xmm0
0x1800aeaa3  mov     [rbp+110h+var_158], r12
0x1800aeaa7  mov     edx, r8d
0x1800aeaaa  test    r8d, r8d
0x1800aeaad  jz      short loc_1800AEAB8
0x1800aeaaf  lea     rcx, [rbp+110h+lpValueName]
0x1800aeab3  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800aeab8  xorps   xmm0, xmm0
0x1800aeabb  movdqu  xmmword ptr [rbp+110h+lpData], xmm0
0x1800aeac0  mov     [rbp+110h+var_140], r12
0x1800aeac4  mov     edx, [rsp+210h+cbMaxValueLen]
0x1800aeac8  inc     edx
0x1800aeaca  shr     rdx, 1
0x1800aeacd  jz      short loc_1800AEAD8
0x1800aeacf  lea     rcx, [rbp+110h+lpData]
0x1800aead3  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800aead8  mov     esi, r12d
0x1800aeadb  mov     rdx, rbx
0x1800aeade  lea     rcx, [rbp+110h+var_60]
0x1800aeae5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800aeaea  nop
0x1800aeaeb  xorps   xmm0, xmm0
0x1800aeaee  movups  xmmword ptr [rbp+110h+var_A0], xmm0
0x1800aeaf2  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800aeafa  movdqu  [rbp+110h+var_90], xmm1
0x1800aeb02  mov     word ptr [rbp+110h+var_A0], r12w
0x1800aeb07  movups  [rbp+110h+var_110], xmm0
0x1800aeb0b  movdqu  [rbp+110h+var_100], xmm1
0x1800aeb10  mov     word ptr [rbp+110h+var_110], r12w
0x1800aeb15  xor     edx, edx
0x1800aeb17  jmp     short loc_1800AEB90
0x1800aeb19  cmp     [rsp+210h+Type], 1
0x1800aeb1e  jnz     short loc_1800AEB8C
0x1800aeb20  mov     rdx, [rbp+110h+lpValueName]
0x1800aeb24  mov     r8, rdi
0x1800aeb27  inc     r8
0x1800aeb2a  cmp     [rdx+r8*2], r12w
0x1800aeb2f  jnz     short loc_1800AEB27
0x1800aeb31  lea     rcx, [rbp+110h+var_110]
0x1800aeb35  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800aeb3a  mov     rcx, [rbp+110h+var_50]
0x1800aeb41  cmp     rcx, qword ptr [rbp+110h+var_100]
0x1800aeb45  jb      short loc_1800AEB88
0x1800aeb47  lea     rdx, [rbp+110h+var_110]
0x1800aeb4b  cmp     qword ptr [rbp+110h+var_100+8], 7
0x1800aeb50  cmova   rdx, qword ptr [rbp+110h+var_110]
0x1800aeb55  lea     rax, [rbp+110h+var_60]
0x1800aeb5c  cmp     [rbp+110h+var_48], 7
0x1800aeb64  cmova   rax, [rbp+110h+var_60]
0x1800aeb6c  sub     rcx, qword ptr [rbp+110h+var_100]
0x1800aeb70  lea     rcx, [rax+rcx*2]
0x1800aeb74  call    cs:__imp__o__wcsicmp
0x1800aeb7b  nop     dword ptr [rax+rax+00h]
0x1800aeb80  test    eax, eax
0x1800aeb82  jz      loc_1800AEC6C
0x1800aeb88  test    ebx, ebx
0x1800aeb8a  jnz     short loc_1800AEBEB
0x1800aeb8c  inc     esi
0x1800aeb8e  mov     edx, esi; dwIndex
0x1800aeb90  mov     eax, [rsp+210h+cbMaxValueLen]
0x1800aeb94  mov     [rsp+210h+cbData], eax
0x1800aeb98  mov     eax, [rsp+210h+cbMaxValueNameLen]
0x1800aeb9c  lea     rcx, [rsp+210h+cbData]
0x1800aeba1  mov     [rsp+210h+cchValueName], eax
0x1800aeba5  mov     [rsp+210h+lpcValues], rcx; lpcbData
0x1800aebaa  mov     rax, [rbp+110h+lpData]
0x1800aebae  mov     [rsp+210h+lpcbMaxClassLen], rax; lpData
0x1800aebb3  lea     rax, [rsp+210h+Type]
0x1800aebb8  mov     [rsp+210h+lpcbMaxSubKeyLen], rax; lpType
0x1800aebbd  mov     [rsp+210h+phkResult], r12; lpReserved
0x1800aebc2  mov     [rsp+210h+Type], r12d
0x1800aebc7  lea     r9, [rsp+210h+cchValueName]; lpcchValueName
0x1800aebcc  mov     r8, [rbp+110h+lpValueName]; lpValueName
0x1800aebd0  mov     rcx, [rsp+210h+var_1A0]; hKey
0x1800aebd5  call    cs:__imp_RegEnumValueW
0x1800aebdc  nop     dword ptr [rax+rax+00h]
0x1800aebe1  test    eax, eax
0x1800aebe3  mov     ebx, eax
0x1800aebe5  jz      loc_1800AEB19
0x1800aebeb  lea     rcx, [rbp+110h+var_110]
0x1800aebef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800aebf4  nop
0x1800aebf5  lea     rcx, [rbp+110h+var_A0]
0x1800aebf9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800aebfe  nop
0x1800aebff  lea     rcx, [rbp+110h+var_60]
0x1800aec06  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800aec0b  nop
0x1800aec0c  lea     rcx, [rbp+110h+lpData]
0x1800aec10  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800aec15  nop
0x1800aec16  lea     rcx, [rbp+110h+lpValueName]
0x1800aec1a  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800aec1f  nop
0x1800aec20  lea     rcx, [rsp+210h+var_1A0]
0x1800aec25  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800aec2a  nop
0x1800aec2b  lea     rcx, [rbp+110h+hKey]
0x1800aec2f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800aec34  nop
0x1800aec35  lea     rcx, [rbp+110h+var_130]
0x1800aec39  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800aec3e  nop
0x1800aec3f  lea     rcx, [rbp+110h+Src]
0x1800aec43  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800aec48  xor     al, al
0x1800aec4a  mov     rcx, [rbp+110h+var_40]
0x1800aec51  xor     rcx, rsp; StackCookie
0x1800aec54  call    __security_check_cookie
0x1800aec59  add     rsp, 1E0h
0x1800aec60  pop     r15
0x1800aec62  pop     r14
0x1800aec64  pop     r12
0x1800aec66  pop     rdi
0x1800aec67  pop     rsi
0x1800aec68  pop     rbx
0x1800aec69  pop     rbp
0x1800aec6a  retn
0x1800aec6c  mov     rdx, [rbp+110h+lpData]
0x1800aec70  mov     r8, rdi
0x1800aec73  inc     r8
0x1800aec76  cmp     [rdx+r8*2], r12w
0x1800aec7b  jnz     short loc_1800AEC73
0x1800aec7d  lea     rcx, [rbp+110h+var_A0]
0x1800aec81  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800aec86  lea     rcx, [rbp+110h+var_A0]
0x1800aec8a  cmp     qword ptr [rbp+110h+var_90+8], 7
0x1800aec92  cmova   rcx, [rbp+110h+var_A0]; lpSubKey
0x1800aec97  mov     edx, r14d; int
0x1800aec9a  call    ?UpdatePendingResultInternal@ProvResults@@CA_NPEBGJ@Z; ProvResults::UpdatePendingResultInternal(ushort const *,long)
0x1800aec9f  test    al, al
0x1800aeca1  jz      loc_1800AEBEB
0x1800aeca7  mov     [rsp+210h+cchValueName], r12d
0x1800aecac  xorps   xmm0, xmm0
0x1800aecaf  movdqu  xmmword ptr [rbp+110h+var_180], xmm0
0x1800aecb4  mov     [rbp+110h+var_170], r12
0x1800aecb8  movups  [rbp+110h+var_80], xmm0
0x1800aecbf  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800aecc7  movdqu  [rbp+110h+var_70], xmm1
0x1800aeccf  mov     word ptr [rbp+110h+var_80], r12w
0x1800aecd7  lea     rax, [rsp+210h+cchValueName]
0x1800aecdc  mov     [rsp+210h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800aece1  mov     [rsp+210h+phkResult], r12; lpData
0x1800aece6  xor     r9d, r9d; lpType
0x1800aece9  xor     r8d, r8d; lpReserved
0x1800aecec  lea     rdx, aSession; "Session"
0x1800aecf3  mov     rcx, [rbp+110h+hKey]; hKey
0x1800aecf7  call    cs:__imp_RegQueryValueExW
0x1800aecfe  nop     dword ptr [rax+rax+00h]
0x1800aed03  test    eax, eax
0x1800aed05  jle     short loc_1800AED11
0x1800aed07  movzx   eax, ax
0x1800aed0a  or      eax, 80070000h
0x1800aed0f  test    eax, eax
0x1800aed11  js      loc_1800AEEC3
0x1800aed17  mov     ebx, [rsp+210h+cchValueName]
0x1800aed1b  shr     rbx, 1
0x1800aed1e  inc     rbx
0x1800aed21  mov     rdx, [rbp+110h+var_180]
0x1800aed25  mov     rsi, [rbp+110h+var_180+8]
0x1800aed29  mov     rcx, rsi
0x1800aed2c  sub     rcx, rdx
0x1800aed2f  sar     rcx, 1
0x1800aed32  cmp     rbx, rcx
0x1800aed35  jnb     short loc_1800AED3D
0x1800aed37  lea     rax, [rdx+rbx*2]
0x1800aed3b  jmp     short loc_1800AED73
0x1800aed3d  jbe     short loc_1800AED77
0x1800aed3f  mov     rax, [rbp+110h+var_170]
0x1800aed43  sub     rax, rdx
0x1800aed46  sar     rax, 1
0x1800aed49  cmp     rbx, rax
0x1800aed4c  jbe     short loc_1800AED5C
0x1800aed4e  mov     rdx, rbx
0x1800aed51  lea     rcx, [rbp+110h+var_180]
0x1800aed55  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800aed5a  jmp     short loc_1800AED77
0x1800aed5c  sub     rbx, rcx
0x1800aed5f  add     rbx, rbx
0x1800aed62  mov     r8, rbx; Size
0x1800aed65  xor     edx, edx; Val
0x1800aed67  mov     rcx, rsi; void *
0x1800aed6a  call    memset_0
0x1800aed6f  lea     rax, [rbx+rsi]
0x1800aed73  mov     [rbp+110h+var_180+8], rax
0x1800aed77  mov     rax, [rbp+110h+var_180]
0x1800aed7b  lea     rcx, [rsp+210h+cchValueName]
0x1800aed80  mov     [rsp+210h+lpcbMaxSubKeyLen], rcx; lpcbData
0x1800aed85  mov     [rsp+210h+phkResult], rax; lpData
0x1800aed8a  xor     r9d, r9d; lpType
  ... truncated ...
```
