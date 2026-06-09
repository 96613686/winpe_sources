# FSToastUserInfo::InternalInitialize(ushort const *)

- ea: `0x18004c470`
- end: `0x18004caae`
- name: `?InternalInitialize@FSToastUserInfo@@AEAAJPEBG@Z`
- size: `1598`
- prototype: `int(FSToastUserInfo *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004c1ac`

## callees

- `0x180003e20`
- `0x180009608`
- `0x18000a648`
- `0x180015b40`
- `0x180016714`
- `0x180017014`
- `0x180017a3c`
- `0x180017ab8`
- `0x180026ecc`
- `0x18002b510`
- `0x180036b0c`
- `0x18004a648`
- `0x18004a820`
- `0x18004c39c`
- `0x18004c470`
- `0x18004cbc4`
- `0x18004cda8`
- `0x18004d164`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004c663`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004c6be`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004c663`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004c6be`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004c576`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004c613`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004c576`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004c613`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004c5cf`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004c77e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004c5cf`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004c77e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004c91d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004c91d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18004c868`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18004c868`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18004c899`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18004c899`

## pseudocode

```c
__int64 __fastcall FSToastUserInfo::InternalInitialize(FSToastUserInfo *this, const unsigned __int16 *a2)
{
  int v4; // eax
  signed int v5; // edi
  __int64 v6; // rax
  __int64 v7; // rdx
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  DWORD v10; // r13d
  char v11; // r15
  HKEY *v12; // r12
  HKEY v13; // rcx
  LPOLESTR v14; // rbx
  HKEY v15; // rcx
  LPOLESTR v16; // rbx
  HKEY v17; // rcx
  int v18; // ecx
  int v19; // edx
  int v20; // r8d
  HRESULT v21; // eax
  __int64 v22; // rdx
  int v23; // edx
  int v24; // r8d
  LSTATUS v25; // eax
  HKEY *v26; // rbx
  const unsigned __int16 *v27; // rdx
  HKEY v28; // rcx
  HKEY v29; // rcx
  unsigned int v30; // ebx
  unsigned int v31; // eax
  bool v32; // cf
  LPOLESTR lpsz; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v36; // [rsp+5Ch] [rbp-A4h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  void **v38; // [rsp+68h] [rbp-98h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+70h] [rbp-90h] BYREF
  __int64 v40; // [rsp+88h] [rbp-78h] BYREF
  GUID pguid; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Name[264]; // [rsp+A0h] [rbp-60h] BYREF

  hKey = 0;
  v40 = 0;
  v4 = StringCchLengthW(a2, 0x7FFFFFFFu, (unsigned __int64 *)&lpsz);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_281fcaa017f93033d1a9e1dde7e889c3_Traceguids, this, v4);
    goto LABEL_66;
  }
  v6 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
         &lpsz,
         a2,
         -1);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    (char *)this + 80,
    v6);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
  if ( !*((_QWORD *)this + 10) )
  {
    v5 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_66;
    v7 = 18;
LABEL_7:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_281fcaa017f93033d1a9e1dde7e889c3_Traceguids, this, v5);
    goto LABEL_66;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v8 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows Media Foundation\\FrameServer\\FSToast",
         0,
         0x2001Fu,
         &hKey);
  v5 = v8;
  if ( v8 > 0 )
    v5 = (unsigned __int16)v8 | 0x80070000;
  if ( v5 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_66;
    v7 = 19;
    goto LABEL_7;
  }
  cchName = 260;
  v9 = RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, 0);
  if ( v9 == 259 )
    goto LABEL_34;
  v10 = 0;
  v11 = 1;
  v12 = (HKEY *)((char *)this + 64);
  while ( 1 )
  {
    if ( v9 )
      goto LABEL_28;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      (char *)this + 64,
      0);
    if ( RegOpenKeyExW(hKey, Name, 0, 0x2001Fu, (PHKEY)this + 8) )
      goto LABEL_28;
    v13 = *v12;
    v36 = 0;
    lpsz = 0;
    if ( (int)FSToastUserInfo::QueryRegValue(v13, L"TroubleshootToastTime", 8u, (unsigned __int8 **)&lpsz, &v36) >= 0 )
    {
      v14 = lpsz;
      if ( !(unsigned int)_o__wcsicmp(lpsz + 4, a2) )
      {
        v11 = 0;
        *((_QWORD *)this + 11) = *(_QWORD *)v14;
      }
    }
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&lpsz);
    v15 = *v12;
    v36 = 0;
    if ( (int)FSToastUserInfo::QueryRegValue(v15, L"DiscoveryToastTime", 8u, (unsigned __int8 **)&lpsz, &v36) >= 0 )
    {
      v16 = lpsz;
      if ( !(unsigned int)_o__wcsicmp(lpsz + 4, a2) )
      {
        v11 = 0;
        *((_QWORD *)this + 12) = *(_QWORD *)v16;
      }
    }
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&lpsz);
    v17 = *v12;
    v36 = 0;
    v18 = (int)FSToastUserInfo::QueryRegValue(v17, L"EffectsDiscoveredToast", 0x10u, (unsigned __int8 **)&lpsz, &v36) < 0
        ? 0
        : *(_DWORD *)lpsz;
    *((_DWORD *)this + 27) = v18;
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&lpsz);
    if ( !v11 )
      break;
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&lpsz);
LABEL_28:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      (char *)this + 64,
      0);
    ++v10;
    cchName = 260;
    v9 = RegEnumKeyExW(hKey, v10, Name, &cchName, 0, 0, 0, 0);
    if ( v9 == 259 )
      goto LABEL_33;
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_Sii(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v19,
      v20,
      (_DWORD)a2,
      *((_QWORD *)this + 11),
      *((_QWORD *)this + 12));
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&lpsz);
LABEL_33:
  if ( !v11 )
    goto LABEL_56;
LABEL_34:
  pguid = GUID_00000000_0000_0000_0000_000000000000;
  lpsz = 0;
  v38 = &AutoSecurityAttributes::`vftable';
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  v21 = AutoSecurityAttributes::Set(
          (AutoSecurityAttributes *)&v38,
          L"D:(A;;GA;;;BA)(A;;GA;;;OW)(A;;GA;;;LS)(A;;GRGX;;;WD)(A;;GRGX;;;S-1-15-3-3845273463-1331427702-1186551195-1148109977)");
  v5 = v21;
  if ( v21 >= 0 )
  {
    v21 = CoCreateGuid(&pguid);
    v5 = v21;
    if ( v21 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_38;
      v22 = 22;
      goto LABEL_37;
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &lpsz,
      0);
    v21 = StringFromCLSID(&pguid, &lpsz);
    v5 = v21;
    if ( v21 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_38;
      v22 = 23;
      goto LABEL_37;
    }
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
      WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 27), v23, v24, (_DWORD)lpsz, (__int64)a2);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      (char *)this + 64,
      0);
    v25 = RegCreateKeyExW(hKey, lpsz, 0, 0, 0, 0x20006u, &SecurityAttributes, (PHKEY)this + 8, 0);
    v5 = v25;
    if ( v25 > 0 )
      v5 = (unsigned __int16)v25 | 0x80070000;
    if ( v5 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_281fcaa017f93033d1a9e1dde7e889c3_Traceguids, this, v5);
      goto LABEL_38;
    }
    v21 = FSToastUserInfo::SaveToastInfo(this, 1, 0, L"TroubleshootToastTime");
    v5 = v21;
    if ( v21 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_38;
      v22 = 26;
LABEL_37:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, &WPP_281fcaa017f93033d1a9e1dde7e889c3_Traceguids, this, v21);
      goto LABEL_38;
    }
    v38 = &AutoSecurityAttributes::`vftable';
    AutoSecurityAttributes::Reset((AutoSecurityAttributes *)&v38);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
LABEL_56:
    v26 = (HKEY *)((char *)this + 72);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      (char *)this + 72,
      0);
    if ( FSToastUserInfo::GetUserRegKey(a2, v27, 0x20019u, (HKEY *)this + 9) >= 0 )
    {
      v28 = *v26;
      lpsz = 0;
      cchName = 0;
      if ( (int)FSToastUserInfo::QueryRegValue(
                  v28,
                  L"EffectsDiscoveredToastTime",
                  8u,
                  (unsigned __int8 **)&lpsz,
                  &cchName) >= 0
        && *(_QWORD *)lpsz )
      {
        *((_BYTE *)this + 104) = 1;
      }
      wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&lpsz);
      v29 = *v26;
      cchName = 0;
      if ( (int)FSToastUserInfo::QueryRegValue(
                  v29,
                  L"EffectsDiscoveredToast",
                  0x10u,
                  (unsigned __int8 **)&lpsz,
                  &cchName) < 0 )
        v30 = 0;
      else
        v30 = *(_DWORD *)lpsz;
      wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&lpsz);
      v31 = *((_DWORD *)this + 27);
      if ( v31 <= v30 )
        v31 = v30;
      v32 = v31 < *((_DWORD *)this + 14);
      *((_DWORD *)this + 27) = v31;
      *((_BYTE *)this + 104) |= !v32;
      wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&lpsz);
    }
    goto LABEL_66;
  }
  if ( g_wppLevels )
  {
    v22 = 21;
    goto LABEL_37;
  }
LABEL_38:
  v38 = &AutoSecurityAttributes::`vftable';
  AutoSecurityAttributes::Reset((AutoSecurityAttributes *)&v38);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
LABEL_66:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v40);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004c470  mov     [rsp-8+arg_10], rbx
0x18004c475  push    rbp
0x18004c476  push    rsi
0x18004c477  push    rdi
0x18004c478  push    r12
0x18004c47a  push    r13
0x18004c47c  push    r14
0x18004c47e  push    r15
0x18004c480  lea     rbp, [rsp-1C0h]
0x18004c488  sub     rsp, 2C0h
0x18004c48f  mov     rax, cs:__security_cookie
0x18004c496  xor     rax, rsp
0x18004c499  mov     [rbp+1F0h+var_40], rax
0x18004c4a0  mov     r14, rdx
0x18004c4a3  lea     r8, [rsp+2F0h+lpsz]; unsigned __int64 *
0x18004c4a8  mov     rsi, rcx
0x18004c4ab  xor     r12d, r12d
0x18004c4ae  mov     rcx, r14; unsigned __int16 *
0x18004c4b1  mov     [rsp+2F0h+hKey], r12
0x18004c4b6  mov     edx, 7FFFFFFFh; unsigned __int64
0x18004c4bb  mov     [rbp+1F0h+var_268], r12
0x18004c4bf  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18004c4c4  mov     edi, eax
0x18004c4c6  test    eax, eax
0x18004c4c8  jns     short loc_18004C4FF
0x18004c4ca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c4d1  jb      loc_18004CA6F
0x18004c4d7  lea     edx, [r12+11h]
0x18004c4dc  mov     dword ptr [rsp+2F0h+phkResult], eax
0x18004c4e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c4e7  lea     r8, WPP_281fcaa017f93033d1a9e1dde7e889c3_Traceguids
0x18004c4ee  mov     r9, rsi
0x18004c4f1  mov     rcx, [rcx+10h]
0x18004c4f5  call    WPP_SF_qD
0x18004c4fa  jmp     loc_18004CA6F
0x18004c4ff  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004c503  lea     rcx, [rsp+2F0h+lpsz]
0x18004c508  mov     rdx, r14
0x18004c50b  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18004c510  mov     rdx, rax
0x18004c513  lea     rcx, [rsi+50h]
0x18004c517  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18004c51c  lea     rcx, [rsp+2F0h+lpsz]
0x18004c521  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004c526  cmp     [rsi+50h], r12
0x18004c52a  jnz     short loc_18004C549
0x18004c52c  mov     edi, 8007000Eh
0x18004c531  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c538  jb      loc_18004CA6F
0x18004c53e  mov     edx, 12h
0x18004c543  mov     dword ptr [rsp+2F0h+phkResult], edi
0x18004c547  jmp     short loc_18004C4E0
0x18004c549  xor     edx, edx
0x18004c54b  lea     rcx, [rsp+2F0h+hKey]
0x18004c550  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004c555  lea     rax, [rsp+2F0h+hKey]
0x18004c55a  mov     r9d, 2001Fh; samDesired
0x18004c560  xor     r8d, r8d; ulOptions
0x18004c563  mov     [rsp+2F0h+phkResult], rax; phkResult
0x18004c568  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows Media Foun"...
0x18004c56f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004c576  call    cs:__imp_RegOpenKeyExW
0x18004c57c  mov     edi, eax
0x18004c57e  test    eax, eax
0x18004c580  jle     short loc_18004C58B
0x18004c582  movzx   edi, ax
0x18004c585  or      edi, 80070000h
0x18004c58b  test    edi, edi
0x18004c58d  jns     short loc_18004C5A3
0x18004c58f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c596  jb      loc_18004CA6F
0x18004c59c  mov     edx, 13h
0x18004c5a1  jmp     short loc_18004C543
0x18004c5a3  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18004c5a8  lea     r9, [rsp+2F0h+cchName]; lpcchName
0x18004c5ad  mov     [rsp+2F0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18004c5b2  lea     r8, [rbp+1F0h+Name]; lpName
0x18004c5b6  mov     [rsp+2F0h+lpcchClass], r12; lpcchClass
0x18004c5bb  xor     edx, edx; dwIndex
0x18004c5bd  mov     [rsp+2F0h+lpClass], r12; lpClass
0x18004c5c2  mov     [rsp+2F0h+phkResult], r12; lpReserved
0x18004c5c7  mov     [rsp+2F0h+cchName], 104h
0x18004c5cf  call    cs:__imp_RegEnumKeyExW
0x18004c5d5  cmp     eax, 103h
0x18004c5da  jz      loc_18004C7D8
0x18004c5e0  mov     r13d, r12d
0x18004c5e3  mov     r15b, 1
0x18004c5e6  lea     r12, [rsi+40h]
0x18004c5ea  test    eax, eax
0x18004c5ec  jnz     loc_18004C734
0x18004c5f2  xor     edx, edx
0x18004c5f4  mov     rcx, r12
0x18004c5f7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004c5fc  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18004c601  lea     rdx, [rbp+1F0h+Name]; lpSubKey
0x18004c605  mov     r9d, 2001Fh; samDesired
0x18004c60b  mov     [rsp+2F0h+phkResult], r12; phkResult
0x18004c610  xor     r8d, r8d; ulOptions
0x18004c613  call    cs:__imp_RegOpenKeyExW
0x18004c619  test    eax, eax
0x18004c61b  jnz     loc_18004C734
0x18004c621  mov     rcx, [r12]; hkey
0x18004c625  lea     r9, [rsp+2F0h+lpsz]; unsigned __int8 **
0x18004c62a  mov     [rsp+2F0h+var_294], eax
0x18004c62e  lea     rdx, aTroubleshootto; "TroubleshootToastTime"
0x18004c635  lea     rax, [rsp+2F0h+var_294]
0x18004c63a  mov     [rsp+2F0h+lpsz], 0
0x18004c643  mov     r8d, 8; dwFlags
0x18004c649  mov     [rsp+2F0h+phkResult], rax; unsigned int *
0x18004c64e  call    ?QueryRegValue@FSToastUserInfo@@SAJPEAUHKEY__@@PEBGKPEAPEAEPEAK@Z; FSToastUserInfo::QueryRegValue(HKEY__ *,ushort const *,ulong,uchar * *,ulong *)
0x18004c653  test    eax, eax
0x18004c655  js      short loc_18004C677
0x18004c657  mov     rbx, [rsp+2F0h+lpsz]
0x18004c65c  mov     rdx, r14
0x18004c65f  lea     rcx, [rbx+8]
0x18004c663  call    cs:__imp__o__wcsicmp
0x18004c669  test    eax, eax
0x18004c66b  jnz     short loc_18004C677
0x18004c66d  mov     rax, [rbx]
0x18004c670  xor     r15b, r15b
0x18004c673  mov     [rsi+58h], rax
0x18004c677  lea     rcx, [rsp+2F0h+lpsz]
0x18004c67c  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18004c681  mov     rcx, [r12]; hkey
0x18004c685  lea     rax, [rsp+2F0h+var_294]
0x18004c68a  lea     r9, [rsp+2F0h+lpsz]; unsigned __int8 **
0x18004c68f  mov     [rsp+2F0h+phkResult], rax; unsigned int *
0x18004c694  mov     r8d, 8; dwFlags
0x18004c69a  mov     [rsp+2F0h+var_294], 0
0x18004c6a2  lea     rdx, aDiscoverytoast_0; "DiscoveryToastTime"
0x18004c6a9  call    ?QueryRegValue@FSToastUserInfo@@SAJPEAUHKEY__@@PEBGKPEAPEAEPEAK@Z; FSToastUserInfo::QueryRegValue(HKEY__ *,ushort const *,ulong,uchar * *,ulong *)
0x18004c6ae  test    eax, eax
0x18004c6b0  js      short loc_18004C6D2
0x18004c6b2  mov     rbx, [rsp+2F0h+lpsz]
0x18004c6b7  mov     rdx, r14
0x18004c6ba  lea     rcx, [rbx+8]
0x18004c6be  call    cs:__imp__o__wcsicmp
0x18004c6c4  test    eax, eax
0x18004c6c6  jnz     short loc_18004C6D2
0x18004c6c8  mov     rax, [rbx]
0x18004c6cb  xor     r15b, r15b
0x18004c6ce  mov     [rsi+60h], rax
0x18004c6d2  lea     rcx, [rsp+2F0h+lpsz]
0x18004c6d7  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18004c6dc  mov     rcx, [r12]; hkey
0x18004c6e0  lea     rax, [rsp+2F0h+var_294]
0x18004c6e5  lea     r9, [rsp+2F0h+lpsz]; unsigned __int8 **
0x18004c6ea  mov     [rsp+2F0h+phkResult], rax; unsigned int *
0x18004c6ef  mov     r8d, 10h; dwFlags
0x18004c6f5  mov     [rsp+2F0h+var_294], 0
0x18004c6fd  lea     rdx, ValueName; "EffectsDiscoveredToast"
0x18004c704  call    ?QueryRegValue@FSToastUserInfo@@SAJPEAUHKEY__@@PEBGKPEAPEAEPEAK@Z; FSToastUserInfo::QueryRegValue(HKEY__ *,ushort const *,ulong,uchar * *,ulong *)
0x18004c709  test    eax, eax
0x18004c70b  js      short loc_18004C716
0x18004c70d  mov     rax, [rsp+2F0h+lpsz]
0x18004c712  mov     ecx, [rax]
0x18004c714  jmp     short loc_18004C718
0x18004c716  xor     ecx, ecx
0x18004c718  mov     [rsi+6Ch], ecx
0x18004c71b  lea     rcx, [rsp+2F0h+lpsz]
0x18004c720  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18004c725  test    r15b, r15b
0x18004c728  jz      short loc_18004C791
0x18004c72a  lea     rcx, [rsp+2F0h+lpsz]
0x18004c72f  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18004c734  xor     edx, edx
0x18004c736  mov     rcx, r12
0x18004c739  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004c73e  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18004c743  lea     r9, [rsp+2F0h+cchName]; lpcchName
0x18004c748  mov     [rsp+2F0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18004c751  lea     r8, [rbp+1F0h+Name]; lpName
0x18004c755  mov     [rsp+2F0h+lpcchClass], 0; lpcchClass
0x18004c75e  inc     r13d
0x18004c761  mov     [rsp+2F0h+lpClass], 0; lpClass
0x18004c76a  mov     edx, r13d; dwIndex
0x18004c76d  mov     [rsp+2F0h+phkResult], 0; lpReserved
0x18004c776  mov     [rsp+2F0h+cchName], 104h
0x18004c77e  call    cs:__imp_RegEnumKeyExW
0x18004c784  cmp     eax, 103h
0x18004c789  jnz     loc_18004C5EA
0x18004c78f  jmp     short loc_18004C7CC
0x18004c791  cmp     cs:byte_18010EC4D, 8
0x18004c798  jb      short loc_18004C7C2
0x18004c79a  mov     rax, [rsi+60h]
0x18004c79e  mov     r9, r14
0x18004c7a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c7a8  mov     [rsp+2F0h+lpClass], rax
0x18004c7ad  mov     rax, [rsi+58h]
0x18004c7b1  mov     [rsp+2F0h+phkResult], rax
0x18004c7b6  mov     rcx, [rcx+0D8h]
0x18004c7bd  call    WPP_SF_Sii
0x18004c7c2  lea     rcx, [rsp+2F0h+lpsz]
0x18004c7c7  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18004c7cc  xor     r12d, r12d
0x18004c7cf  test    r15b, r15b
0x18004c7d2  jz      loc_18004C99D
0x18004c7d8  movaps  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18004c7df  lea     r15, ??_7AutoSecurityAttributes@@6B@; const AutoSecurityAttributes::`vftable'
0x18004c7e6  movdqu  xmmword ptr [rbp+1F0h+pguid.Data1], xmm0
0x18004c7eb  mov     [rsp+2F0h+lpsz], r12
0x18004c7f0  xor     eax, eax
0x18004c7f2  xorps   xmm0, xmm0
0x18004c7f5  mov     [rsp+2F0h+var_288], r15
0x18004c7fa  lea     rdx, aDAGaBaAGaOwAGa; "D:(A;;GA;;;BA)(A;;GA;;;OW)(A;;GA;;;LS)("...
0x18004c801  mov     qword ptr [rbp+1F0h+SecurityAttributes.bInheritHandle], rax
0x18004c805  lea     rcx, [rsp+2F0h+var_288]; this
0x18004c80a  movups  xmmword ptr [rsp+2F0h+SecurityAttributes.nLength], xmm0
0x18004c80f  call    ?Set@AutoSecurityAttributes@@QEAAJPEBG@Z; AutoSecurityAttributes::Set(ushort const *)
0x18004c814  mov     edi, eax
0x18004c816  test    eax, eax
0x18004c818  jns     short loc_18004C864
0x18004c81a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c821  jb      short loc_18004C846
0x18004c823  mov     edx, 15h
0x18004c828  mov     dword ptr [rsp+2F0h+phkResult], eax
0x18004c82c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c833  lea     r8, WPP_281fcaa017f93033d1a9e1dde7e889c3_Traceguids
0x18004c83a  mov     r9, rsi
0x18004c83d  mov     rcx, [rcx+10h]
0x18004c841  call    WPP_SF_qD
0x18004c846  lea     rcx, [rsp+2F0h+var_288]; this
0x18004c84b  mov     [rsp+2F0h+var_288], r15
0x18004c850  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x18004c855  lea     rcx, [rsp+2F0h+lpsz]
0x18004c85a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004c85f  jmp     loc_18004CA6F
0x18004c864  lea     rcx, [rbp+1F0h+pguid]; pguid
0x18004c868  call    cs:__imp_CoCreateGuid
0x18004c86e  mov     edi, eax
0x18004c870  test    eax, eax
0x18004c872  jns     short loc_18004C884
0x18004c874  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c87b  jb      short loc_18004C846
0x18004c87d  mov     edx, 16h
0x18004c882  jmp     short loc_18004C828
0x18004c884  xor     edx, edx
0x18004c886  lea     rcx, [rsp+2F0h+lpsz]
0x18004c88b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18004c890  lea     rdx, [rsp+2F0h+lpsz]; lplpsz
0x18004c895  lea     rcx, [rbp+1F0h+pguid]; rclsid
0x18004c899  call    cs:__imp_StringFromCLSID
0x18004c89f  mov     edi, eax
0x18004c8a1  test    eax, eax
0x18004c8a3  jns     short loc_18004C8B8
0x18004c8a5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c8ac  jb      short loc_18004C846
0x18004c8ae  mov     edx, 17h
0x18004c8b3  jmp     loc_18004C828
0x18004c8b8  cmp     cs:byte_18010EC4D, 8
0x18004c8bf  jb      short loc_18004C8DE
0x18004c8c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c8c8  mov     r9, [rsp+2F0h+lpsz]
0x18004c8cd  mov     [rsp+2F0h+phkResult], r14
0x18004c8d2  mov     rcx, [rcx+0D8h]
0x18004c8d9  call    WPP_SF_SS
0x18004c8de  lea     rbx, [rsi+40h]
0x18004c8e2  xor     edx, edx
0x18004c8e4  mov     rcx, rbx
0x18004c8e7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004c8ec  mov     rdx, [rsp+2F0h+lpsz]; lpSubKey
0x18004c8f1  lea     rax, [rsp+2F0h+SecurityAttributes]
0x18004c8f6  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18004c8fb  xor     r9d, r9d; lpClass
0x18004c8fe  mov     [rsp+2F0h+lpdwDisposition], r12; lpdwDisposition
0x18004c903  xor     r8d, r8d; Reserved
0x18004c906  mov     [rsp+2F0h+lpftLastWriteTime], rbx; phkResult
0x18004c90b  mov     [rsp+2F0h+lpcchClass], rax; lpSecurityAttributes
0x18004c910  mov     dword ptr [rsp+2F0h+lpClass], 20006h; samDesired
0x18004c918  mov     dword ptr [rsp+2F0h+phkResult], r12d; dwOptions
0x18004c91d  call    cs:__imp_RegCreateKeyExW
0x18004c923  mov     edi, eax
0x18004c925  test    eax, eax
0x18004c927  jle     short loc_18004C932
0x18004c929  movzx   edi, ax
0x18004c92c  or      edi, 80070000h
0x18004c932  test    edi, edi
0x18004c934  jns     short loc_18004C951
0x18004c936  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c93d  jb      loc_18004C846
0x18004c943  mov     edx, 19h
0x18004c948  mov     dword ptr [rsp+2F0h+phkResult], edi
0x18004c94c  jmp     loc_18004C82C
0x18004c951  xor     r8d, r8d
0x18004c954  lea     r9, aTroubleshootto; "TroubleshootToastTime"
0x18004c95b  mov     rcx, rsi
0x18004c95e  lea     edx, [r8+1]
0x18004c962  call    ?SaveToastInfo@FSToastUserInfo@@QEAAJW4__MIDL___MIDL_itf_fsserviceapi_0000_0000_0006@@_KPEBG@Z; FSToastUserInfo::SaveToastInfo(__MIDL___MIDL_itf_fsserviceapi_0000_0000_0006,unsigned __int64,ushort const *)
0x18004c967  mov     edi, eax
0x18004c969  test    eax, eax
0x18004c96b  jns     short loc_18004C984
0x18004c96d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004c974  jb      loc_18004C846
0x18004c97a  mov     edx, 1Ah
0x18004c97f  jmp     loc_18004C828
0x18004c984  lea     rcx, [rsp+2F0h+var_288]; this
0x18004c989  mov     [rsp+2F0h+var_288], r15
0x18004c98e  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x18004c993  lea     rcx, [rsp+2F0h+lpsz]
0x18004c998  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
  ... truncated ...
```
