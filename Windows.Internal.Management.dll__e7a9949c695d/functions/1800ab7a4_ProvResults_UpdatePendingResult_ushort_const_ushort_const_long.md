# ProvResults::UpdatePendingResult(ushort const *,ushort const *,long)

- ea: `0x1800ab7a4`
- end: `0x1800abf3b`
- name: `?UpdatePendingResult@ProvResults@@SA_NPEBG0J@Z`
- size: `1943`
- prototype: `bool __fastcall(LPCOLESTR lpsz, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18006dec0`

## callees

- `0x18000133c`
- `0x180004348`
- `0x180004d50`
- `0x180005904`
- `0x18000cfdc`
- `0x180012ae8`
- `0x180015acc`
- `0x180015b48`
- `0x180015f70`
- `0x1800169b8`
- `0x18003a430`
- `0x18003ec00`
- `0x1800699d0`
- `0x180079d34`
- `0x1800a8d18`
- `0x1800aa99c`
- `0x1800ab39c`
- `0x1800ab7a4`
- `0x1800abf44`
- `0x1800ac5d8`
- `0x1800b1730`
- `0x1800b1a14`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800aba4c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800aba4c`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800abe66`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800abe66`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800abaa7`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800abaa7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800abd98`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800abd98`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800abbc2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800abc60`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800abbc2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800abc60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab8c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab8c9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800abe52`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800abe52`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800ab92f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800ab92f`

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
  __int64 v22; // r8
  const WCHAR *v23; // rcx
  LSTATUS v24; // eax
  __int64 v25; // r8
  __int64 v26; // r9
  bool v27; // sf
  unsigned __int64 v28; // rbx
  LPBYTE v29; // rsi
  unsigned __int64 v30; // rcx
  BYTE *v31; // rax
  size_t v32; // rbx
  LSTATUS v33; // eax
  __int64 v34; // rdx
  __int64 v35; // rcx
  bool v36; // sf
  __int64 v37; // r8
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  __int128 *v41; // rax
  LPCWSTR *v42; // rax
  __int128 *v43; // rax
  LPCWSTR *v44; // r8
  LPCWSTR *v45; // r9
  bool IsStateSeparationEnabled; // al
  const wchar_t *v47; // rdx
  LPCWSTR *v48; // rdx
  const WCHAR *v49; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cchValueName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbMaxValueLen; // [rsp+6Ch] [rbp-94h] BYREF
  HKEY v56; // [rsp+70h] [rbp-90h] BYREF
  DWORD Type[2]; // [rsp+78h] [rbp-88h] BYREF
  DWORD cValues; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  LPBYTE v60[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v61; // [rsp+A0h] [rbp-60h]
  LPWSTR lpValueName[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v63; // [rsp+B8h] [rbp-48h]
  LPBYTE lpData[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v65; // [rsp+D0h] [rbp-30h]
  LPCWSTR *v66; // [rsp+D8h] [rbp-28h] BYREF
  LPCWSTR v67[2]; // [rsp+E0h] [rbp-20h] BYREF
  __m128i v68; // [rsp+F0h] [rbp-10h]
  __int128 v69; // [rsp+100h] [rbp+0h] BYREF
  __m128i v70; // [rsp+110h] [rbp+10h]
  __int128 Src; // [rsp+120h] [rbp+20h] BYREF
  __m128i si128; // [rsp+130h] [rbp+30h]
  GUID iid; // [rsp+140h] [rbp+40h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+150h] [rbp+50h] BYREF
  LPCWSTR v75[2]; // [rsp+170h] [rbp+70h] BYREF
  __m128i v76; // [rsp+180h] [rbp+80h]
  __int128 v77; // [rsp+190h] [rbp+90h] BYREF
  __m128i v78; // [rsp+1A0h] [rbp+A0h]
  _QWORD v79[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int64 v80; // [rsp+1C0h] [rbp+C0h]
  unsigned __int64 v81; // [rsp+1C8h] [rbp+C8h]
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
  *(_OWORD *)v67 = 0;
  v68 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v67[0]) = 0;
  PackageEnroller::GetPackageIdFromEnrollmentId(&Src, v67);
  v9 = (const WCHAR *)v67;
  if ( v68.m128i_i64[1] > 7uLL )
    v9 = v67[0];
  ProvResults::GetPackageKey(&hKey, v9);
  v56 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v56,
    0);
  v10 = RegOpenKeyExW(hKey, L"PendingResults", 0, 0xBu, &v56);
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
  v11 = RegQueryInfoKeyW(v56, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
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
  v63 = 0;
  if ( (_DWORD)v14 )
    std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(lpValueName, (unsigned int)v14, v14, v15);
  *(_OWORD *)lpData = 0;
  v65 = 0;
  if ( (unsigned __int64)(cbMaxValueLen + 1) >> 1 )
    std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(
      lpData,
      (unsigned __int64)(cbMaxValueLen + 1) >> 1,
      v14,
      v15);
  v16 = 0;
  std::wstring::wstring(v79, a2);
  *(_OWORD *)v75 = 0;
  v76 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v75[0]) = 0;
  v69 = 0;
  v70 = v76;
  LOWORD(v69) = 0;
  for ( i = 0; ; i = v16 )
  {
    cbData = cbMaxValueLen;
    cchValueName = cbMaxValueNameLen;
    Type[0] = 0;
    if ( RegEnumValueW(v56, i, lpValueName[0], &cchValueName, 0, Type, lpData[0], &cbData) )
      goto LABEL_32;
    if ( Type[0] == 1 )
    {
      v18 = -1;
      do
        ++v18;
      while ( lpValueName[0][v18] );
      std::wstring::_Assign<unsigned short>(&v69, lpValueName[0]);
      if ( v80 >= v70.m128i_i64[0] )
      {
        v19 = &v69;
        if ( v70.m128i_i64[1] > 7uLL )
          v19 = (__int128 *)v69;
        v20 = v79;
        if ( v81 > 7 )
          v20 = (_QWORD *)v79[0];
        if ( !(unsigned int)_o__wcsicmp((char *)v20 + 2 * (v80 - v70.m128i_i64[0]), v19) )
          break;
      }
    }
    ++v16;
  }
  v22 = -1;
  do
    ++v22;
  while ( *(_WORD *)&lpData[0][2 * v22] );
  std::wstring::_Assign<unsigned short>(v75, lpData[0]);
  v23 = (const WCHAR *)v75;
  if ( v76.m128i_i64[1] > 7uLL )
    v23 = v75[0];
  if ( !ProvResults::UpdatePendingResultInternal(v23, a3) )
  {
LABEL_32:
    std::wstring::_Tidy_deallocate(&v69);
    std::wstring::_Tidy_deallocate(v75);
    std::wstring::_Tidy_deallocate(v79);
    std::vector<unsigned short>::_Tidy(lpData);
    std::vector<unsigned short>::_Tidy(lpValueName);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v56);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::_Tidy_deallocate(v67);
    std::wstring::_Tidy_deallocate(&Src);
    return 0;
  }
  cchValueName = 0;
  *(_OWORD *)v60 = 0;
  v61 = 0;
  v77 = 0;
  v78 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v77) = 0;
  v24 = RegQueryValueExW(hKey, L"Session", 0, 0, 0, &cchValueName);
  v27 = v24 < 0;
  if ( v24 > 0 )
    v27 = 1;
  if ( !v27 )
  {
    v28 = ((unsigned __int64)cchValueName >> 1) + 1;
    v29 = v60[1];
    v30 = (v60[1] - v60[0]) >> 1;
    if ( v28 < v30 )
    {
      v31 = &v60[0][2 * v28];
LABEL_47:
      v60[1] = v31;
      goto LABEL_48;
    }
    if ( v28 > v30 )
    {
      if ( v28 <= (signed __int64)(v61 - (unsigned __int64)v60[0]) >> 1 )
      {
        v32 = 2 * (v28 - v30);
        memset_0(v60[1], 0, v32);
        v31 = &v29[v32];
        goto LABEL_47;
      }
      std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(
        v60,
        ((unsigned __int64)cchValueName >> 1) + 1,
        v25,
        v26);
    }
LABEL_48:
    v33 = RegQueryValueExW(hKey, L"Session", 0, 0, v60[0], &cchValueName);
    v36 = v33 < 0;
    if ( v33 > 0 )
      v36 = 1;
    if ( v36 )
    {
      if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 2) != 0 )
      {
        v45 = v67;
        if ( v68.m128i_i64[1] > 7uLL )
          v45 = (LPCWSTR *)v67[0];
        McTemplateU0dz_EventWriteTransfer(v35, v34, a3, v45);
      }
    }
    else
    {
      v37 = -1;
      do
        ++v37;
      while ( *(_WORD *)&v60[0][2 * v37] );
      std::wstring::_Assign<unsigned short>(&v77, v60[0]);
      if ( (unsigned int)dword_1800FA480 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800FA480, 0x400000000000LL) )
      {
        v41 = &v69;
        if ( v70.m128i_i64[1] > 7uLL )
          v41 = (__int128 *)v69;
        *(_QWORD *)Type = v41;
        cbData = a3;
        v42 = v67;
        if ( v68.m128i_i64[1] > 7uLL )
          v42 = (LPCWSTR *)v67[0];
        v66 = v42;
        v43 = &v77;
        if ( v78.m128i_i64[1] > 7uLL )
          v43 = (__int128 *)v77;
        *(_QWORD *)&iid.Data1 = v43;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v38,
          (unsigned int)qword_1800EA228,
          v39,
          v40,
          (__int64)&iid,
          (__int64)&v66,
          (__int64)&cbData,
          (__int64)Type);
      }
      if ( (Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits & 1) != 0 )
      {
        v44 = v67;
        if ( v68.m128i_i64[1] > 7uLL )
          v44 = (LPCWSTR *)v67[0];
        McTemplateU0z_EventWriteTransfer(
          PROVISIONING_DIAGNOSTICS_Context,
          ProvResultUpdatePendingResultInternalSucceeded,
          v44);
      }
    }
  }
  if ( a3 != 44761091 )
  {
    RegDeleteValueW(v56, lpValueName[0]);
    if ( cValues == 1 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &v56,
        0);
      IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
      v47 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\Results";
      if ( !IsStateSeparationEnabled )
        v47 = L"SOFTWARE\\Microsoft\\Provisioning\\Results";
      std::wstring::wstring(lpSubKey, v47);
      std::wstring::_Append<unsigned short>(lpSubKey);
      v48 = v67;
      if ( v68.m128i_i64[1] > 7uLL )
        v48 = (LPCWSTR *)v67[0];
      do
        ++v6;
      while ( *((_WORD *)v48 + v6) );
      std::wstring::_Append<unsigned short>(lpSubKey);
      std::wstring::_Append<unsigned short>(lpSubKey);
      std::wstring::_Append<unsigned short>(lpSubKey);
      v49 = (const WCHAR *)lpSubKey;
      if ( lpSubKey[3] > (LPCWSTR)7 )
        v49 = lpSubKey[0];
      RegDeleteTreeW(HKEY_LOCAL_MACHINE, v49);
      iid = 0;
      if ( IIDFromString(lpsz, &iid) >= 0 )
        UnregisterCspAlerts(&iid);
      std::wstring::_Tidy_deallocate(lpSubKey);
    }
  }
  std::wstring::_Tidy_deallocate(&v77);
  std::vector<unsigned short>::_Tidy(v60);
  std::wstring::_Tidy_deallocate(&v69);
  std::wstring::_Tidy_deallocate(v75);
  std::wstring::_Tidy_deallocate(v79);
  std::vector<unsigned short>::_Tidy(lpData);
  std::vector<unsigned short>::_Tidy(lpValueName);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v56);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::wstring::_Tidy_deallocate(v67);
  std::wstring::_Tidy_deallocate(&Src);
  return 1;
}

```

## disassembly

```asm
0x1800ab7a4  push    rbp
0x1800ab7a6  push    rbx
0x1800ab7a7  push    rsi
0x1800ab7a8  push    rdi
0x1800ab7a9  push    r12
0x1800ab7ab  push    r14
0x1800ab7ad  push    r15
0x1800ab7af  lea     rbp, [rsp-0E0h]
0x1800ab7b7  sub     rsp, 1E0h
0x1800ab7be  mov     rax, cs:__security_cookie
0x1800ab7c5  xor     rax, rsp
0x1800ab7c8  mov     [rbp+110h+var_40], rax
0x1800ab7cf  mov     r14d, r8d
0x1800ab7d2  mov     rbx, rdx
0x1800ab7d5  mov     r15, rcx
0x1800ab7d8  xorps   xmm0, xmm0
0x1800ab7db  movups  [rbp+110h+Src], xmm0
0x1800ab7df  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800ab7e7  movdqu  [rbp+110h+var_E0], xmm1
0x1800ab7ec  xor     r12d, r12d
0x1800ab7ef  mov     word ptr [rbp+110h+Src], r12w
0x1800ab7f4  lea     esi, [r12+1]
0x1800ab7f9  cmp     word ptr [rcx], 7Bh ; '{'
0x1800ab7fd  jz      short loc_1800AB812
0x1800ab7ff  mov     r8d, esi
0x1800ab802  lea     rdx, asc_1800DFE80; "{"
0x1800ab809  lea     rcx, [rbp+110h+Src]; Src
0x1800ab80d  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800ab812  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800ab816  mov     r8, rdi
0x1800ab819  inc     r8
0x1800ab81c  cmp     [r15+r8*2], r12w
0x1800ab821  jnz     short loc_1800AB819
0x1800ab823  mov     rdx, r15
0x1800ab826  lea     rcx, [rbp+110h+Src]; Src
0x1800ab82a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800ab82f  lea     rcx, [rbp+110h+Src]
0x1800ab833  cmp     qword ptr [rbp+110h+var_E0+8], 7
0x1800ab838  cmova   rcx, qword ptr [rbp+110h+Src]
0x1800ab83d  mov     rax, qword ptr [rbp+110h+var_E0]
0x1800ab841  cmp     word ptr [rcx+rax*2-2], 7Dh ; '}'
0x1800ab847  jz      short loc_1800AB85C
0x1800ab849  mov     r8, rsi
0x1800ab84c  lea     rdx, asc_1800E09F0; "}"
0x1800ab853  lea     rcx, [rbp+110h+Src]; Src
0x1800ab857  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800ab85c  xorps   xmm0, xmm0
0x1800ab85f  movups  xmmword ptr [rbp+110h+var_130], xmm0
0x1800ab863  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800ab86b  movdqu  [rbp+110h+var_120], xmm1
0x1800ab870  mov     word ptr [rbp+110h+var_130], r12w
0x1800ab875  lea     rdx, [rbp+110h+var_130]
0x1800ab879  lea     rcx, [rbp+110h+Src]
0x1800ab87d  call    ?GetPackageIdFromEnrollmentId@PackageEnroller@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; PackageEnroller::GetPackageIdFromEnrollmentId(std::wstring const &,std::wstring &)
0x1800ab882  lea     rdx, [rbp+110h+var_130]
0x1800ab886  cmp     qword ptr [rbp+110h+var_120+8], 7
0x1800ab88b  cmova   rdx, [rbp+110h+var_130]; lpSubKey
0x1800ab890  lea     rcx, [rbp+110h+hKey]; phkResult
0x1800ab894  call    ?GetPackageKey@ProvResults@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGK@Z; ProvResults::GetPackageKey(ushort const *,ulong)
0x1800ab899  nop
0x1800ab89a  mov     [rsp+210h+var_1A0], r12
0x1800ab89f  xor     edx, edx
0x1800ab8a1  lea     rcx, [rsp+210h+var_1A0]
0x1800ab8a6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800ab8ab  lea     rax, [rsp+210h+var_1A0]
0x1800ab8b0  mov     [rsp+210h+phkResult], rax; unsigned int
0x1800ab8b5  mov     r9d, 0Bh; samDesired
0x1800ab8bb  xor     r8d, r8d; ulOptions
0x1800ab8be  lea     rdx, aPendingresults; "PendingResults"
0x1800ab8c5  mov     rcx, [rbp+110h+hKey]; hKey
0x1800ab8c9  call    cs:__imp_RegOpenKeyExW
0x1800ab8cf  mov     rcx, [rbp+118h]; this
0x1800ab8d6  test    eax, eax
0x1800ab8d8  jnz     loc_1800ABF11
0x1800ab8de  mov     [rsp+210h+cbMaxValueNameLen], r12d
0x1800ab8e3  mov     [rsp+210h+cbMaxValueLen], r12d
0x1800ab8e8  mov     [rbp+110h+cValues], r12d
0x1800ab8ec  mov     [rsp+210h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800ab8f1  mov     [rsp+210h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1800ab8f6  lea     rax, [rsp+210h+cbMaxValueLen]
0x1800ab8fb  mov     [rsp+210h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800ab900  lea     rax, [rsp+210h+cbMaxValueNameLen]
0x1800ab905  mov     [rsp+210h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800ab90a  lea     rax, [rbp+110h+cValues]
0x1800ab90e  mov     [rsp+210h+lpcValues], rax; lpcValues
0x1800ab913  mov     [rsp+210h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1800ab918  mov     [rsp+210h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x1800ab91d  mov     [rsp+210h+phkResult], r12; unsigned int
0x1800ab922  xor     r9d, r9d; lpReserved
0x1800ab925  xor     r8d, r8d; lpcchClass
0x1800ab928  xor     edx, edx; lpClass
0x1800ab92a  mov     rcx, [rsp+210h+var_1A0]; hKey
0x1800ab92f  call    cs:__imp_RegQueryInfoKeyW
0x1800ab935  mov     rcx, [rbp+118h]; this
0x1800ab93c  test    eax, eax
0x1800ab93e  jnz     loc_1800ABF26
0x1800ab944  mov     edx, [rsp+210h+cbMaxValueNameLen]
0x1800ab948  lea     eax, [rdx+1]
0x1800ab94b  or      r8d, 0FFFFFFFFh
0x1800ab94f  cmp     eax, edx
0x1800ab951  cmovnb  r8d, eax
0x1800ab955  sbb     r9d, r9d
0x1800ab958  and     r9d, 80070216h; char *
0x1800ab95f  mov     [rsp+210h+cbMaxValueNameLen], r8d
0x1800ab964  mov     rcx, [rbp+118h]; this
0x1800ab96b  cmp     eax, edx
0x1800ab96d  jb      loc_1800ABEFF
0x1800ab973  xorps   xmm0, xmm0
0x1800ab976  movdqu  xmmword ptr [rbp+110h+lpValueName], xmm0
0x1800ab97b  mov     [rbp+110h+var_158], r12
0x1800ab97f  mov     edx, r8d
0x1800ab982  test    r8d, r8d
0x1800ab985  jz      short loc_1800AB990
0x1800ab987  lea     rcx, [rbp+110h+lpValueName]
0x1800ab98b  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800ab990  xorps   xmm0, xmm0
0x1800ab993  movdqu  xmmword ptr [rbp+110h+lpData], xmm0
0x1800ab998  mov     [rbp+110h+var_140], r12
0x1800ab99c  mov     edx, [rsp+210h+cbMaxValueLen]
0x1800ab9a0  inc     edx
0x1800ab9a2  shr     rdx, 1
0x1800ab9a5  jz      short loc_1800AB9B0
0x1800ab9a7  lea     rcx, [rbp+110h+lpData]
0x1800ab9ab  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800ab9b0  mov     esi, r12d
0x1800ab9b3  mov     rdx, rbx
0x1800ab9b6  lea     rcx, [rbp+110h+var_60]
0x1800ab9bd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ab9c2  nop
0x1800ab9c3  xorps   xmm0, xmm0
0x1800ab9c6  movups  xmmword ptr [rbp+110h+var_A0], xmm0
0x1800ab9ca  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800ab9d2  movdqu  [rbp+110h+var_90], xmm1
0x1800ab9da  mov     word ptr [rbp+110h+var_A0], r12w
0x1800ab9df  movups  [rbp+110h+var_110], xmm0
0x1800ab9e3  movdqu  [rbp+110h+var_100], xmm1
0x1800ab9e8  mov     word ptr [rbp+110h+var_110], r12w
0x1800ab9ed  xor     edx, edx
0x1800ab9ef  jmp     short loc_1800ABA62
0x1800ab9f1  cmp     [rsp+210h+Type], 1
0x1800ab9f6  jnz     short loc_1800ABA5E
0x1800ab9f8  mov     rdx, [rbp+110h+lpValueName]
0x1800ab9fc  mov     r8, rdi
0x1800ab9ff  inc     r8
0x1800aba02  cmp     [rdx+r8*2], r12w
0x1800aba07  jnz     short loc_1800AB9FF
0x1800aba09  lea     rcx, [rbp+110h+var_110]
0x1800aba0d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800aba12  mov     rcx, [rbp+110h+var_50]
0x1800aba19  cmp     rcx, qword ptr [rbp+110h+var_100]
0x1800aba1d  jb      short loc_1800ABA5A
0x1800aba1f  lea     rdx, [rbp+110h+var_110]
0x1800aba23  cmp     qword ptr [rbp+110h+var_100+8], 7
0x1800aba28  cmova   rdx, qword ptr [rbp+110h+var_110]
0x1800aba2d  lea     rax, [rbp+110h+var_60]
0x1800aba34  cmp     [rbp+110h+var_48], 7
0x1800aba3c  cmova   rax, [rbp+110h+var_60]
0x1800aba44  sub     rcx, qword ptr [rbp+110h+var_100]
0x1800aba48  lea     rcx, [rax+rcx*2]
0x1800aba4c  call    cs:__imp__o__wcsicmp
0x1800aba52  test    eax, eax
0x1800aba54  jz      loc_1800ABB37
0x1800aba5a  test    ebx, ebx
0x1800aba5c  jnz     short loc_1800ABAB7
0x1800aba5e  inc     esi
0x1800aba60  mov     edx, esi; dwIndex
0x1800aba62  mov     eax, [rsp+210h+cbMaxValueLen]
0x1800aba66  mov     [rsp+210h+cbData], eax
0x1800aba6a  mov     eax, [rsp+210h+cbMaxValueNameLen]
0x1800aba6e  lea     rcx, [rsp+210h+cbData]
0x1800aba73  mov     [rsp+210h+cchValueName], eax
0x1800aba77  mov     [rsp+210h+lpcValues], rcx; lpcbData
0x1800aba7c  mov     rax, [rbp+110h+lpData]
0x1800aba80  mov     [rsp+210h+lpcbMaxClassLen], rax; lpData
0x1800aba85  lea     rax, [rsp+210h+Type]
0x1800aba8a  mov     [rsp+210h+lpcbMaxSubKeyLen], rax; lpType
0x1800aba8f  mov     [rsp+210h+phkResult], r12; lpReserved
0x1800aba94  mov     [rsp+210h+Type], r12d
0x1800aba99  lea     r9, [rsp+210h+cchValueName]; lpcchValueName
0x1800aba9e  mov     r8, [rbp+110h+lpValueName]; lpValueName
0x1800abaa2  mov     rcx, [rsp+210h+var_1A0]; hKey
0x1800abaa7  call    cs:__imp_RegEnumValueW
0x1800abaad  test    eax, eax
0x1800abaaf  mov     ebx, eax
0x1800abab1  jz      loc_1800AB9F1
0x1800abab7  lea     rcx, [rbp+110h+var_110]
0x1800ababb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800abac0  nop
0x1800abac1  lea     rcx, [rbp+110h+var_A0]
0x1800abac5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800abaca  nop
0x1800abacb  lea     rcx, [rbp+110h+var_60]
0x1800abad2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800abad7  nop
0x1800abad8  lea     rcx, [rbp+110h+lpData]
0x1800abadc  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800abae1  nop
0x1800abae2  lea     rcx, [rbp+110h+lpValueName]
0x1800abae6  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800abaeb  nop
0x1800abaec  lea     rcx, [rsp+210h+var_1A0]
0x1800abaf1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800abaf6  nop
0x1800abaf7  lea     rcx, [rbp+110h+hKey]
0x1800abafb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800abb00  nop
0x1800abb01  lea     rcx, [rbp+110h+var_130]
0x1800abb05  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800abb0a  nop
0x1800abb0b  lea     rcx, [rbp+110h+Src]
0x1800abb0f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800abb14  xor     al, al
0x1800abb16  mov     rcx, [rbp+110h+var_40]
0x1800abb1d  xor     rcx, rsp; StackCookie
0x1800abb20  call    __security_check_cookie
0x1800abb25  add     rsp, 1E0h
0x1800abb2c  pop     r15
0x1800abb2e  pop     r14
0x1800abb30  pop     r12
0x1800abb32  pop     rdi
0x1800abb33  pop     rsi
0x1800abb34  pop     rbx
0x1800abb35  pop     rbp
0x1800abb36  retn
0x1800abb37  mov     rdx, [rbp+110h+lpData]
0x1800abb3b  mov     r8, rdi
0x1800abb3e  inc     r8
0x1800abb41  cmp     [rdx+r8*2], r12w
0x1800abb46  jnz     short loc_1800ABB3E
0x1800abb48  lea     rcx, [rbp+110h+var_A0]
0x1800abb4c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800abb51  lea     rcx, [rbp+110h+var_A0]
0x1800abb55  cmp     qword ptr [rbp+110h+var_90+8], 7
0x1800abb5d  cmova   rcx, [rbp+110h+var_A0]; lpSubKey
0x1800abb62  mov     edx, r14d; int
0x1800abb65  call    ?UpdatePendingResultInternal@ProvResults@@CA_NPEBGJ@Z; ProvResults::UpdatePendingResultInternal(ushort const *,long)
0x1800abb6a  test    al, al
0x1800abb6c  jz      loc_1800ABAB7
0x1800abb72  mov     [rsp+210h+cchValueName], r12d
0x1800abb77  xorps   xmm0, xmm0
0x1800abb7a  movdqu  xmmword ptr [rbp+110h+var_180], xmm0
0x1800abb7f  mov     [rbp+110h+var_170], r12
0x1800abb83  movups  [rbp+110h+var_80], xmm0
0x1800abb8a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800abb92  movdqu  [rbp+110h+var_70], xmm1
0x1800abb9a  mov     word ptr [rbp+110h+var_80], r12w
0x1800abba2  lea     rax, [rsp+210h+cchValueName]
0x1800abba7  mov     [rsp+210h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800abbac  mov     [rsp+210h+phkResult], r12; lpData
0x1800abbb1  xor     r9d, r9d; lpType
0x1800abbb4  xor     r8d, r8d; lpReserved
0x1800abbb7  lea     rdx, aSession; "Session"
0x1800abbbe  mov     rcx, [rbp+110h+hKey]; hKey
0x1800abbc2  call    cs:__imp_RegQueryValueExW
0x1800abbc8  test    eax, eax
0x1800abbca  jle     short loc_1800ABBD6
0x1800abbcc  movzx   eax, ax
0x1800abbcf  or      eax, 80070000h
0x1800abbd4  test    eax, eax
0x1800abbd6  js      loc_1800ABD82
0x1800abbdc  mov     ebx, [rsp+210h+cchValueName]
0x1800abbe0  shr     rbx, 1
0x1800abbe3  inc     rbx
0x1800abbe6  mov     rdx, [rbp+110h+var_180]
0x1800abbea  mov     rsi, [rbp+110h+var_180+8]
0x1800abbee  mov     rcx, rsi
0x1800abbf1  sub     rcx, rdx
0x1800abbf4  sar     rcx, 1
0x1800abbf7  cmp     rbx, rcx
0x1800abbfa  jnb     short loc_1800ABC02
0x1800abbfc  lea     rax, [rdx+rbx*2]
0x1800abc00  jmp     short loc_1800ABC38
0x1800abc02  jbe     short loc_1800ABC3C
0x1800abc04  mov     rax, [rbp+110h+var_170]
0x1800abc08  sub     rax, rdx
0x1800abc0b  sar     rax, 1
0x1800abc0e  cmp     rbx, rax
0x1800abc11  jbe     short loc_1800ABC21
0x1800abc13  mov     rdx, rbx
0x1800abc16  lea     rcx, [rbp+110h+var_180]
0x1800abc1a  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800abc1f  jmp     short loc_1800ABC3C
0x1800abc21  sub     rbx, rcx
0x1800abc24  add     rbx, rbx
0x1800abc27  mov     r8, rbx; Size
0x1800abc2a  xor     edx, edx; Val
0x1800abc2c  mov     rcx, rsi; void *
0x1800abc2f  call    memset_0
0x1800abc34  lea     rax, [rbx+rsi]
0x1800abc38  mov     [rbp+110h+var_180+8], rax
0x1800abc3c  mov     rax, [rbp+110h+var_180]
0x1800abc40  lea     rcx, [rsp+210h+cchValueName]
0x1800abc45  mov     [rsp+210h+lpcbMaxSubKeyLen], rcx; lpcbData
0x1800abc4a  mov     [rsp+210h+phkResult], rax; lpData
0x1800abc4f  xor     r9d, r9d; lpType
0x1800abc52  xor     r8d, r8d; lpReserved
0x1800abc55  lea     rdx, aSession; "Session"
0x1800abc5c  mov     rcx, [rbp+110h+hKey]; hKey
0x1800abc60  call    cs:__imp_RegQueryValueExW
0x1800abc66  test    eax, eax
  ... truncated ...
```
