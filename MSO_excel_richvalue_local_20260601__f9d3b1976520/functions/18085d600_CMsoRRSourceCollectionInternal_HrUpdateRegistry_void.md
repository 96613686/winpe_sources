# CMsoRRSourceCollectionInternal::HrUpdateRegistry(void)

- ea: `0x18085d600`
- end: `0x18085de3f`
- name: `?HrUpdateRegistry@CMsoRRSourceCollectionInternal@@UEAAJXZ`
- size: `2111`
- prototype: `__int64 __fastcall(CMsoRRSourceCollectionInternal *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x181533210`

## callees

- `0x18001aeb0`
- `0x180485240`
- `0x18085d3a4`
- `0x18085d600`
- `0x18085e3dc`
- `0x180b9c8d0`

## import_xrefs

- `Mso20Win32Client!__imp_?MsoAdjustRegSamForWow@@YAKK@Z` at `0x18085d6ee`
- `Mso20Win32Client!__imp_?MsoAdjustRegSamForWow@@YAKK@Z` at `0x18085d758`
- `Mso20Win32Client!__imp_?MsoAdjustRegSamForWow@@YAKK@Z` at `0x18085d6ee`
- `Mso20Win32Client!__imp_?MsoAdjustRegSamForWow@@YAKK@Z` at `0x18085d758`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18085dac6`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18085db21`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18085dcab`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18085dd07`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18085de07`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18085dac6`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18085db21`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18085dcab`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18085dd07`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18085de07`
- `Mso20Win32Client!__imp_?MsoRegOpenKey@@YAJPEBU_msoreg@@PEAPEAUHKEY__@@@Z` at `0x18085d666`
- `Mso20Win32Client!__imp_?MsoRegOpenKey@@YAJPEBU_msoreg@@PEAPEAUHKEY__@@@Z` at `0x18085d666`
- `Mso20Win32Client!__imp_?MsoRegCreateKey@@YAJPEBU_msoreg@@PEAPEAUHKEY__@@@Z` at `0x18085dc98`
- `Mso20Win32Client!__imp_?MsoRegCreateKey@@YAJPEBU_msoreg@@PEAPEAUHKEY__@@@Z` at `0x18085dc98`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x18085d8b7`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x18085d92e`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x18085d9a5`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x18085d8b7`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x18085d92e`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x18085d9a5`
- `ole32!CoTaskMemFree` at `0x18085d726`
- `ole32!CoTaskMemFree` at `0x18085dbf4`
- `ole32!CoTaskMemFree` at `0x18085dcbb`
- `ole32!CoTaskMemFree` at `0x18085de12`
- `ole32!CoTaskMemFree` at `0x18085d726`
- `ole32!CoTaskMemFree` at `0x18085dbf4`
- `ole32!CoTaskMemFree` at `0x18085dcbb`
- `ole32!CoTaskMemFree` at `0x18085de12`
- `ole32!StringFromCLSID` at `0x18085d6cf`
- `ole32!StringFromCLSID` at `0x18085d739`
- `ole32!StringFromCLSID` at `0x18085d6cf`
- `ole32!StringFromCLSID` at `0x18085d739`
- `ADVAPI32!RegOpenKeyExW` at `0x18085d70a`
- `ADVAPI32!RegOpenKeyExW` at `0x18085d774`
- `ADVAPI32!RegOpenKeyExW` at `0x18085d70a`
- `ADVAPI32!RegOpenKeyExW` at `0x18085d774`
- `ADVAPI32!RegCloseKey` at `0x18085d68a`
- `ADVAPI32!RegCloseKey` at `0x18085d69f`
- `ADVAPI32!RegCloseKey` at `0x18085de1d`
- `ADVAPI32!RegCloseKey` at `0x18085de28`
- `ADVAPI32!RegCloseKey` at `0x18085de33`
- `ADVAPI32!RegCloseKey` at `0x18085d68a`
- `ADVAPI32!RegCloseKey` at `0x18085d69f`
- `ADVAPI32!RegCloseKey` at `0x18085de1d`
- `ADVAPI32!RegCloseKey` at `0x18085de28`
- `ADVAPI32!RegCloseKey` at `0x18085de33`
- `ADVAPI32!RegSetValueExW` at `0x18085d7d1`
- `ADVAPI32!RegSetValueExW` at `0x18085d853`
- `ADVAPI32!RegSetValueExW` at `0x18085d885`
- `ADVAPI32!RegSetValueExW` at `0x18085d8f9`
- `ADVAPI32!RegSetValueExW` at `0x18085d970`
- `ADVAPI32!RegSetValueExW` at `0x18085d9e7`
- `ADVAPI32!RegSetValueExW` at `0x18085da1e`
- `ADVAPI32!RegSetValueExW` at `0x18085da68`
- `ADVAPI32!RegSetValueExW` at `0x18085dab1`
- `ADVAPI32!RegSetValueExW` at `0x18085db05`
- `ADVAPI32!RegSetValueExW` at `0x18085db5e`
- `ADVAPI32!RegSetValueExW` at `0x18085dbd0`
- `ADVAPI32!RegSetValueExW` at `0x18085dd49`
- `ADVAPI32!RegSetValueExW` at `0x18085d7d1`
- `ADVAPI32!RegSetValueExW` at `0x18085d853`
- `ADVAPI32!RegSetValueExW` at `0x18085d885`
- `ADVAPI32!RegSetValueExW` at `0x18085d8f9`
- `ADVAPI32!RegSetValueExW` at `0x18085d970`
- `ADVAPI32!RegSetValueExW` at `0x18085d9e7`
- `ADVAPI32!RegSetValueExW` at `0x18085da1e`
- `ADVAPI32!RegSetValueExW` at `0x18085da68`
- `ADVAPI32!RegSetValueExW` at `0x18085dab1`
- `ADVAPI32!RegSetValueExW` at `0x18085db05`
- `ADVAPI32!RegSetValueExW` at `0x18085db5e`
- `ADVAPI32!RegSetValueExW` at `0x18085dbd0`
- `ADVAPI32!RegSetValueExW` at `0x18085dd49`

## string_xrefs

- `0x18085dbbc`: `AboutPath`
- `0x18085da9d`: `TermsOfUsePath`
- `0x18085dd35`: `OptionsPath`
- `0x18085d7bd`: `ServiceName`
- `0x18085dd8a`: `Deleted`

## pseudocode

```c
__int64 __fastcall CMsoRRSourceCollectionInternal::HrUpdateRegistry(CMsoRRSourceCollectionInternal *this)
{
  HRESULT v2; // esi
  unsigned int SourceDataCount; // r13d
  unsigned int i; // r15d
  struct SOURCEDATA *SourceDataByIndex; // r14
  const WCHAR *v6; // rbx
  HKEY v7; // rdi
  REGSAM v8; // eax
  const WCHAR *v9; // rbx
  HKEY v10; // rdi
  REGSAM v11; // eax
  const wchar_t *v12; // r8
  unsigned int v13; // r9d
  const BYTE *v14; // rcx
  __int64 v15; // rax
  LSTATUS v16; // ebx
  const BYTE *v17; // rcx
  const BYTE *v18; // rcx
  const BYTE *v19; // rcx
  const BYTE *v20; // rcx
  const BYTE *v21; // rcx
  const BYTE *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  const wchar_t *v25; // r8
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v34; // rcx
  __int64 v35; // rax
  const wchar_t *v36; // rcx
  const wchar_t *v37; // rcx
  __int64 v38; // rcx
  struct _SECURITY_ATTRIBUTES *cbData; // [rsp+30h] [rbp-D8h]
  HKEY phkResult; // [rsp+48h] [rbp-C0h] BYREF
  LPOLESTR lpsz; // [rsp+50h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-B0h] BYREF
  HKEY v43; // [rsp+60h] [rbp-A8h] BYREF
  wchar_t Destination[256]; // [rsp+68h] [rbp-A0h] BYREF

  v43 = 0;
  v2 = 0;
  hKey = 0;
  phkResult = 0;
  SourceDataCount = CMsoRRSourceCollectionInternal::GetSourceDataCount(this);
  lpsz = 0;
  if ( !MsoRegOpenKey((const struct _msoreg *)&vmsoridResearchLibrarySources, &v43)
    || !MsoRegCreateKey((const struct _msoreg *)&vmsoridResearchLibrarySources, &v43) )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= SourceDataCount )
        goto LABEL_76;
      if ( hKey )
        RegCloseKey(hKey);
      hKey = 0;
      if ( phkResult )
        RegCloseKey(phkResult);
      phkResult = 0;
      SourceDataByIndex = CMsoRRSourceCollectionInternal::GetSourceDataByIndex(this, i);
      if ( lpsz )
      {
        CoTaskMemFree(lpsz);
        lpsz = 0;
      }
      v2 = StringFromCLSID((const IID *const)((char *)SourceDataByIndex + 36), &lpsz);
      if ( v2 < 0 )
      {
        v38 = 504467473;
        goto LABEL_113;
      }
      v6 = lpsz;
      v7 = v43;
      v8 = MsoAdjustRegSamForWow(0x20006u);
      v2 = RegOpenKeyExW(v7, v6, 0, v8, &hKey);
      if ( v2 )
      {
        MsoShipAssertTagProc(504467472);
        continue;
      }
      if ( lpsz )
      {
        CoTaskMemFree(lpsz);
        lpsz = 0;
      }
      v2 = StringFromCLSID((const IID *const)SourceDataByIndex, &lpsz);
      if ( v2 < 0 )
      {
        v38 = 504467471;
LABEL_113:
        MsoShipAssertTagProc(v38);
        goto LABEL_76;
      }
      v9 = lpsz;
      v10 = hKey;
      v11 = MsoAdjustRegSamForWow(0x20006u);
      if ( RegOpenKeyExW(v10, v9, 0, v11, &phkResult) )
      {
        v2 = MsoRegCreateKeyExW(hKey, lpsz, v12, v13, 0x2001Fu, cbData, &phkResult, 0);
        if ( v2 < 0 )
          break;
      }
      if ( lpsz )
      {
        CoTaskMemFree(lpsz);
        lpsz = 0;
      }
      v14 = (const BYTE *)*((_QWORD *)SourceDataByIndex + 7);
      if ( !v14 )
      {
        v34 = 504467469;
        goto LABEL_90;
      }
      v15 = -1;
      do
        ++v15;
      while ( *(_WORD *)&v14[2 * v15] );
      v16 = RegSetValueExW(phkResult, L"ServiceName", 0, 1u, v14, 2 * v15 + 2);
      if ( v16 )
      {
        v28 = 504467468;
      }
      else
      {
        v17 = (const BYTE *)*((_QWORD *)SourceDataByIndex + 8);
        if ( !v17 )
          goto LABEL_23;
        v30 = -1;
        do
          ++v30;
        while ( *(_WORD *)&v17[2 * v30] );
        v16 = RegSetValueExW(phkResult, L"SourceData", 0, 1u, v17, 2 * v30 + 2);
        if ( v16 )
        {
          v28 = 504467467;
        }
        else
        {
LABEL_23:
          v18 = (const BYTE *)*((_QWORD *)SourceDataByIndex + 9);
          if ( !v18 )
            goto LABEL_24;
          v27 = -1;
          do
            ++v27;
          while ( *(_WORD *)&v18[2 * v27] );
          v16 = RegSetValueExW(phkResult, L"Description", 0, 1u, v18, 2 * v27 + 2);
          if ( v16 )
          {
            v28 = 504467466;
          }
          else
          {
LABEL_24:
            v19 = (const BYTE *)*((_QWORD *)SourceDataByIndex + 10);
            if ( !v19 )
              goto LABEL_25;
            v32 = -1;
            do
              ++v32;
            while ( *(_WORD *)&v19[2 * v32] );
            v16 = RegSetValueExW(phkResult, L"AboutPath", 0, 1u, v19, 2 * v32 + 2);
            if ( v16 )
            {
              v28 = 504467465;
            }
            else
            {
LABEL_25:
              v20 = (const BYTE *)*((_QWORD *)SourceDataByIndex + 11);
              if ( !v20 )
                goto LABEL_26;
              v31 = -1;
              do
                ++v31;
              while ( *(_WORD *)&v20[2 * v31] );
              v16 = RegSetValueExW(phkResult, L"TermsOfUse", 0, 1u, v20, 2 * v31 + 2);
              if ( v16 )
              {
                v28 = 504467464;
              }
              else
              {
LABEL_26:
                v21 = (const BYTE *)*((_QWORD *)SourceDataByIndex + 12);
                if ( !v21 )
                  goto LABEL_27;
                v29 = -1;
                do
                  ++v29;
                while ( *(_WORD *)&v21[2 * v29] );
                v16 = RegSetValueExW(phkResult, L"TermsOfUsePath", 0, 1u, v21, 2 * v29 + 2);
                if ( v16 )
                {
                  v28 = 504467463;
                }
                else
                {
LABEL_27:
                  v22 = (const BYTE *)*((_QWORD *)SourceDataByIndex + 14);
                  if ( !v22 )
                    goto LABEL_28;
                  v35 = -1;
                  do
                    ++v35;
                  while ( *(_WORD *)&v22[2 * v35] );
                  v16 = RegSetValueExW(phkResult, L"OptionsPath", 0, 1u, v22, 2 * v35 + 2);
                  if ( v16 )
                  {
                    v28 = 504467461;
                  }
                  else
                  {
LABEL_28:
                    v16 = RegSetValueExW(phkResult, L"CategoryID", 0, 4u, (const BYTE *)SourceDataByIndex + 32, 4u);
                    if ( v16 )
                    {
                      v28 = 504467460;
                    }
                    else
                    {
                      v16 = RegSetValueExW(phkResult, L"SortOrder", 0, 4u, (const BYTE *)SourceDataByIndex + 120, 4u);
                      if ( v16 )
                      {
                        v28 = 504467459;
                      }
                      else
                      {
                        if ( *((_DWORD *)SourceDataByIndex + 31) == 1 )
                        {
                          wcsncpy_s(Destination, 0x100u, L"Enabled", 0xFFFFFFFFFFFFFFFFuLL);
                        }
                        else
                        {
                          if ( *((_DWORD *)SourceDataByIndex + 31) == 2 )
                          {
                            v36 = L"Disabled";
                          }
                          else if ( *((_DWORD *)SourceDataByIndex + 31) == 3
                                 || (unsigned int)(*((_DWORD *)SourceDataByIndex + 31) - 4) < 2 )
                          {
                            v36 = L"Deleted";
                          }
                          else
                          {
                            v36 = L"Unknown";
                          }
                          MsoWzCopy(v36, Destination, 256);
                        }
                        v23 = -1;
                        do
                          ++v23;
                        while ( Destination[v23] );
                        v16 = RegSetValueExW(phkResult, L"Status", 0, 1u, (const BYTE *)Destination, 2 * v23 + 2);
                        if ( v16 )
                        {
                          v28 = 504467458;
                        }
                        else
                        {
                          if ( *((_DWORD *)SourceDataByIndex + 32) == 1 )
                          {
                            wcsncpy_s(Destination, 0x100u, L"On", 0xFFFFFFFFFFFFFFFFuLL);
                          }
                          else
                          {
                            if ( *((_DWORD *)SourceDataByIndex + 32) == 2 )
                            {
                              v37 = L"Off";
                            }
                            else if ( *((_DWORD *)SourceDataByIndex + 32) == 3 )
                            {
                              v37 = L"Hidden";
                            }
                            else
                            {
                              v37 = L"Unknown";
                            }
                            MsoWzCopy(v37, Destination, 256);
                          }
                          v24 = -1;
                          do
                            ++v24;
                          while ( Destination[v24] );
                          v16 = RegSetValueExW(phkResult, L"Display", 0, 1u, (const BYTE *)Destination, 2 * v24 + 2);
                          if ( v16 )
                          {
                            v28 = 504467457;
                          }
                          else
                          {
                            if ( *((_DWORD *)SourceDataByIndex + 33) == 1 )
                            {
                              v25 = L"Supported";
                            }
                            else if ( *((_DWORD *)SourceDataByIndex + 33) == 2 )
                            {
                              v25 = L"Unsupported";
                            }
                            else
                            {
                              v25 = L"Unknown";
                            }
                            wcsncpy_s(Destination, 0x100u, v25, 0xFFFFFFFFFFFFFFFFuLL);
                            v26 = -1;
                            do
                              ++v26;
                            while ( Destination[v26] );
                            v16 = RegSetValueExW(phkResult, L"Parental", 0, 1u, (const BYTE *)Destination, 2 * v26 + 2);
                            if ( v16 )
                            {
                              v28 = 504467456;
                            }
                            else
                            {
                              v16 = RegSetValueExW(
                                      phkResult,
                                      L"PersistData",
                                      0,
                                      4u,
                                      (const BYTE *)SourceDataByIndex + 136,
                                      4u);
                              if ( !v16 )
                                continue;
                              v28 = 504465635;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      MsoShipAssertTagProc(v28);
      v2 = v16;
LABEL_46:
      ;
    }
    v34 = 504467470;
LABEL_90:
    MsoShipAssertTagProc(v34);
    v2 = -2147418113;
    goto LABEL_46;
  }
  MsoShipAssertTagProc(504467474);
  v2 = -2147418113;
LABEL_76:
  if ( lpsz )
    CoTaskMemFree(lpsz);
  if ( v43 )
    RegCloseKey(v43);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18085d600  mov     rax, rsp
0x18085d603  mov     [rax+10h], rbx
0x18085d607  mov     [rax+18h], rsi
0x18085d60b  mov     [rax+20h], rdi
0x18085d60f  push    rbp
0x18085d610  push    r12
0x18085d612  push    r13
0x18085d614  push    r14
0x18085d616  push    r15
0x18085d618  lea     rbp, [rax-198h]
0x18085d61f  sub     rsp, 270h
0x18085d626  mov     rax, cs:__security_cookie
0x18085d62d  xor     rax, rsp
0x18085d630  mov     [rbp+190h+var_30], rax
0x18085d637  mov     r12, rcx
0x18085d63a  call    ?GetSourceDataCount@CMsoRRSourceCollectionInternal@@AEBAKXZ; CMsoRRSourceCollectionInternal::GetSourceDataCount(void)
0x18085d63f  xor     edi, edi
0x18085d641  lea     rdx, [rsp+290h+var_238]
0x18085d646  lea     rcx, ?vmsoridResearchLibrarySources@@3U_msoreg@@B; _msoreg const vmsoridResearchLibrarySources
0x18085d64d  mov     [rsp+290h+var_238], rdi
0x18085d652  mov     esi, edi
0x18085d654  mov     [rsp+290h+hKey], rdi
0x18085d659  mov     [rsp+290h+var_250], rdi
0x18085d65e  mov     r13d, eax
0x18085d661  mov     [rsp+290h+lpsz], rdi
0x18085d666  call    cs:__imp_?MsoRegOpenKey@@YAJPEBU_msoreg@@PEAPEAUHKEY__@@@Z; MsoRegOpenKey(_msoreg const *,HKEY__ * *)
0x18085d66c  test    eax, eax
0x18085d66e  jnz     loc_18085DC8C
0x18085d674  mov     r15d, edi
0x18085d677  cmp     r15d, r13d
0x18085d67a  jnb     loc_18085DC22
0x18085d680  mov     rcx, [rsp+290h+hKey]; hKey
0x18085d685  test    rcx, rcx
0x18085d688  jz      short loc_18085D690
0x18085d68a  call    cs:__imp_RegCloseKey
0x18085d690  mov     rcx, [rsp+290h+var_250]; hKey
0x18085d695  mov     [rsp+290h+hKey], rdi
0x18085d69a  test    rcx, rcx
0x18085d69d  jz      short loc_18085D6A5
0x18085d69f  call    cs:__imp_RegCloseKey
0x18085d6a5  mov     edx, r15d; unsigned int
0x18085d6a8  mov     [rsp+290h+var_250], rdi
0x18085d6ad  mov     rcx, r12; this
0x18085d6b0  call    ?GetSourceDataByIndex@CMsoRRSourceCollectionInternal@@AEAAPEAUSOURCEDATA@@K@Z; CMsoRRSourceCollectionInternal::GetSourceDataByIndex(ulong)
0x18085d6b5  mov     rcx, [rsp+290h+lpsz]; pv
0x18085d6ba  mov     r14, rax
0x18085d6bd  test    rcx, rcx
0x18085d6c0  jnz     loc_18085DCBB
0x18085d6c6  lea     rcx, [r14+24h]; rclsid
0x18085d6ca  lea     rdx, [rsp+290h+lpsz]; lplpsz
0x18085d6cf  call    cs:__imp_StringFromCLSID
0x18085d6d5  mov     esi, eax
0x18085d6d7  test    eax, eax
0x18085d6d9  js      loc_18085DE02
0x18085d6df  mov     rbx, [rsp+290h+lpsz]
0x18085d6e4  mov     ecx, 20006h
0x18085d6e9  mov     rdi, [rsp+290h+var_238]
0x18085d6ee  call    cs:__imp_?MsoAdjustRegSamForWow@@YAKK@Z; MsoAdjustRegSamForWow(ulong)
0x18085d6f4  xor     r8d, r8d; ulOptions
0x18085d6f7  mov     rdx, rbx; lpSubKey
0x18085d6fa  mov     r9d, eax; samDesired
0x18085d6fd  mov     rcx, rdi; hKey
0x18085d700  lea     rax, [rsp+290h+hKey]
0x18085d705  mov     [rsp+290h+phkResult], rax; phkResult
0x18085d70a  call    cs:__imp_RegOpenKeyExW
0x18085d710  xor     edi, edi
0x18085d712  mov     esi, eax
0x18085d714  test    eax, eax
0x18085d716  jnz     loc_18085DB1C
0x18085d71c  mov     rcx, [rsp+290h+lpsz]; pv
0x18085d721  test    rcx, rcx
0x18085d724  jz      short loc_18085D731
0x18085d726  call    cs:__imp_CoTaskMemFree
0x18085d72c  mov     [rsp+290h+lpsz], rdi
0x18085d731  lea     rdx, [rsp+290h+lpsz]; lplpsz
0x18085d736  mov     rcx, r14; rclsid
0x18085d739  call    cs:__imp_StringFromCLSID
0x18085d73f  mov     esi, eax
0x18085d741  test    eax, eax
0x18085d743  js      loc_18085DDFB
0x18085d749  mov     rbx, [rsp+290h+lpsz]
0x18085d74e  mov     ecx, 20006h
0x18085d753  mov     rdi, [rsp+290h+hKey]
0x18085d758  call    cs:__imp_?MsoAdjustRegSamForWow@@YAKK@Z; MsoAdjustRegSamForWow(ulong)
0x18085d75e  xor     r8d, r8d; ulOptions
0x18085d761  mov     rdx, rbx; lpSubKey
0x18085d764  mov     r9d, eax; samDesired
0x18085d767  mov     rcx, rdi; hKey
0x18085d76a  lea     rax, [rsp+290h+var_250]
0x18085d76f  mov     [rsp+290h+phkResult], rax; phkResult
0x18085d774  call    cs:__imp_RegOpenKeyExW
0x18085d77a  xor     edi, edi
0x18085d77c  test    eax, eax
0x18085d77e  jnz     loc_18085DCCB
0x18085d784  mov     rcx, [rsp+290h+lpsz]; pv
0x18085d789  test    rcx, rcx
0x18085d78c  jnz     loc_18085DBF4
0x18085d792  mov     rcx, [r14+38h]
0x18085d796  test    rcx, rcx
0x18085d799  jz      loc_18085DD02
0x18085d79f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18085d7a3  inc     rax
0x18085d7a6  cmp     [rcx+rax*2], di
0x18085d7aa  jnz     short loc_18085D7A3
0x18085d7ac  lea     eax, ds:2[rax*2]
0x18085d7b3  mov     r9d, 1; dwType
0x18085d7b9  mov     [rsp+290h+cbData], eax; cbData
0x18085d7bd  lea     rdx, aServicename; "ServiceName"
0x18085d7c4  mov     [rsp+290h+phkResult], rcx; lpData
0x18085d7c9  xor     r8d, r8d; Reserved
0x18085d7cc  mov     rcx, [rsp+290h+var_250]; hKey
0x18085d7d1  call    cs:__imp_RegSetValueExW
0x18085d7d7  mov     ebx, eax
0x18085d7d9  test    eax, eax
0x18085d7db  jnz     loc_18085DC18
0x18085d7e1  mov     rcx, [r14+40h]
0x18085d7e5  test    rcx, rcx
0x18085d7e8  jnz     loc_18085DAD3
0x18085d7ee  mov     rcx, [r14+48h]
0x18085d7f2  test    rcx, rcx
0x18085d7f5  jnz     loc_18085DA36
0x18085d7fb  mov     rcx, [r14+50h]
0x18085d7ff  test    rcx, rcx
0x18085d802  jnz     loc_18085DB9E
0x18085d808  mov     rcx, [r14+58h]
0x18085d80c  test    rcx, rcx
0x18085d80f  jnz     loc_18085DB2C
0x18085d815  mov     rcx, [r14+60h]
0x18085d819  test    rcx, rcx
0x18085d81c  jnz     loc_18085DA7F
0x18085d822  mov     rcx, [r14+70h]
0x18085d826  test    rcx, rcx
0x18085d829  jnz     loc_18085DD17
0x18085d82f  mov     ecx, 4
0x18085d834  lea     rax, [r14+20h]
0x18085d838  mov     [rsp+290h+cbData], ecx; cbData
0x18085d83c  lea     rdx, aCategoryid_3; "CategoryID"
0x18085d843  mov     r9d, ecx; dwType
0x18085d846  mov     [rsp+290h+phkResult], rax; lpData
0x18085d84b  mov     rcx, [rsp+290h+var_250]; hKey
0x18085d850  xor     r8d, r8d; Reserved
0x18085d853  call    cs:__imp_RegSetValueExW
0x18085d859  mov     ebx, eax
0x18085d85b  test    eax, eax
0x18085d85d  jnz     loc_18085DD63
0x18085d863  lea     ecx, [rbx+4]
0x18085d866  xor     r8d, r8d; Reserved
0x18085d869  mov     [rsp+290h+cbData], ecx; cbData
0x18085d86d  lea     rax, [r14+78h]
0x18085d871  mov     r9d, ecx; dwType
0x18085d874  mov     [rsp+290h+phkResult], rax; lpData
0x18085d879  mov     rcx, [rsp+290h+var_250]; hKey
0x18085d87e  lea     rdx, aSortorder; "SortOrder"
0x18085d885  call    cs:__imp_RegSetValueExW
0x18085d88b  mov     ebx, eax
0x18085d88d  test    eax, eax
0x18085d88f  jnz     loc_18085DC0E
0x18085d895  mov     ecx, [r14+7Ch]
0x18085d899  sub     ecx, 1
0x18085d89c  jnz     loc_18085DD6D
0x18085d8a2  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18085d8a6  lea     r8, aEnabled; "Enabled"
0x18085d8ad  mov     edx, 100h; SizeInWords
0x18085d8b2  lea     rcx, [rsp+290h+Destination]; Destination
0x18085d8b7  call    cs:__imp_wcsncpy_s
0x18085d8bd  lea     rcx, [rsp+290h+Destination]
0x18085d8c2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18085d8c6  inc     rax
0x18085d8c9  cmp     [rcx+rax*2], di
0x18085d8cd  jnz     short loc_18085D8C6
0x18085d8cf  mov     rcx, [rsp+290h+var_250]; hKey
0x18085d8d4  lea     eax, ds:2[rax*2]
0x18085d8db  mov     [rsp+290h+cbData], eax; cbData
0x18085d8df  lea     rdx, aStatus_0; "Status"
0x18085d8e6  lea     rax, [rsp+290h+Destination]
0x18085d8eb  mov     r9d, 1; dwType
0x18085d8f1  xor     r8d, r8d; Reserved
0x18085d8f4  mov     [rsp+290h+phkResult], rax; lpData
0x18085d8f9  call    cs:__imp_RegSetValueExW
0x18085d8ff  mov     ebx, eax
0x18085d901  test    eax, eax
0x18085d903  jnz     loc_18085DC04
0x18085d909  mov     ecx, [r14+80h]
0x18085d910  sub     ecx, 1
0x18085d913  jnz     loc_18085DDAF
0x18085d919  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18085d91d  lea     r8, aOn; "On"
0x18085d924  mov     edx, 100h; SizeInWords
0x18085d929  lea     rcx, [rsp+290h+Destination]; Destination
0x18085d92e  call    cs:__imp_wcsncpy_s
0x18085d934  lea     rcx, [rsp+290h+Destination]
0x18085d939  or      rax, 0FFFFFFFFFFFFFFFFh
0x18085d93d  inc     rax
0x18085d940  cmp     [rcx+rax*2], di
0x18085d944  jnz     short loc_18085D93D
0x18085d946  mov     rcx, [rsp+290h+var_250]; hKey
0x18085d94b  lea     eax, ds:2[rax*2]
0x18085d952  mov     [rsp+290h+cbData], eax; cbData
0x18085d956  lea     rdx, aDisplay_2; "Display"
0x18085d95d  lea     rax, [rsp+290h+Destination]
0x18085d962  mov     r9d, 1; dwType
0x18085d968  xor     r8d, r8d; Reserved
0x18085d96b  mov     [rsp+290h+phkResult], rax; lpData
0x18085d970  call    cs:__imp_RegSetValueExW
0x18085d976  mov     ebx, eax
0x18085d978  test    eax, eax
0x18085d97a  jnz     loc_18085DBEA
0x18085d980  mov     ecx, [r14+84h]
0x18085d987  mov     edx, 100h; SizeInWords
0x18085d98c  sub     ecx, 1
0x18085d98f  jnz     loc_18085DB78
0x18085d995  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18085d999  lea     r8, aSupported_0; "Supported"
0x18085d9a0  lea     rcx, [rsp+290h+Destination]; Destination
0x18085d9a5  call    cs:__imp_wcsncpy_s
0x18085d9ab  lea     rcx, [rsp+290h+Destination]
0x18085d9b0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18085d9b4  inc     rax
0x18085d9b7  cmp     [rcx+rax*2], di
0x18085d9bb  jnz     short loc_18085D9B4
0x18085d9bd  mov     rcx, [rsp+290h+var_250]; hKey
0x18085d9c2  lea     eax, ds:2[rax*2]
0x18085d9c9  mov     [rsp+290h+cbData], eax; cbData
0x18085d9cd  lea     rdx, aParental; "Parental"
0x18085d9d4  lea     rax, [rsp+290h+Destination]
0x18085d9d9  mov     r9d, 1; dwType
0x18085d9df  xor     r8d, r8d; Reserved
0x18085d9e2  mov     [rsp+290h+phkResult], rax; lpData
0x18085d9e7  call    cs:__imp_RegSetValueExW
0x18085d9ed  mov     ebx, eax
0x18085d9ef  test    eax, eax
0x18085d9f1  jnz     loc_18085DDE7
0x18085d9f7  mov     rcx, [rsp+290h+var_250]; hKey
0x18085d9fc  lea     rax, [r14+88h]
0x18085da03  lea     r14d, [rbx+4]
0x18085da07  xor     r8d, r8d; Reserved
0x18085da0a  mov     [rsp+290h+cbData], r14d; cbData
0x18085da0f  lea     rdx, aPersistdata; "PersistData"
0x18085da16  mov     r9d, r14d; dwType
0x18085da19  mov     [rsp+290h+phkResult], rax; lpData
0x18085da1e  call    cs:__imp_RegSetValueExW
0x18085da24  mov     ebx, eax
0x18085da26  test    eax, eax
0x18085da28  jnz     loc_18085DDF1
0x18085da2e  inc     r15d
0x18085da31  jmp     loc_18085D677
0x18085da36  or      rax, 0FFFFFFFFFFFFFFFFh
0x18085da3a  inc     rax
0x18085da3d  cmp     [rcx+rax*2], di
0x18085da41  jnz     short loc_18085DA3A
0x18085da43  lea     eax, ds:2[rax*2]
0x18085da4a  mov     r9d, 1; dwType
0x18085da50  mov     [rsp+290h+cbData], eax; cbData
0x18085da54  lea     rdx, aDescription; "Description"
0x18085da5b  mov     [rsp+290h+phkResult], rcx; lpData
0x18085da60  xor     r8d, r8d; Reserved
0x18085da63  mov     rcx, [rsp+290h+var_250]; hKey
0x18085da68  call    cs:__imp_RegSetValueExW
0x18085da6e  mov     ebx, eax
0x18085da70  test    eax, eax
0x18085da72  jz      loc_18085D7FB
0x18085da78  mov     ecx, 1E11900Ah
0x18085da7d  jmp     short loc_18085DAC6
0x18085da7f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18085da83  inc     rax
0x18085da86  cmp     [rcx+rax*2], di
0x18085da8a  jnz     short loc_18085DA83
0x18085da8c  lea     eax, ds:2[rax*2]
0x18085da93  mov     r9d, 1; dwType
0x18085da99  mov     [rsp+290h+cbData], eax; cbData
0x18085da9d  lea     rdx, aTermsofusepath; "TermsOfUsePath"
0x18085daa4  mov     [rsp+290h+phkResult], rcx; lpData
0x18085daa9  xor     r8d, r8d; Reserved
0x18085daac  mov     rcx, [rsp+290h+var_250]; hKey
0x18085dab1  call    cs:__imp_RegSetValueExW
0x18085dab7  mov     ebx, eax
0x18085dab9  test    eax, eax
0x18085dabb  jz      loc_18085D822
0x18085dac1  mov     ecx, 1E119007h
0x18085dac6  call    cs:__imp_MsoShipAssertTagProc
0x18085dacc  mov     esi, ebx
0x18085dace  jmp     loc_18085DA2E
0x18085dad3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18085dad7  inc     rax
0x18085dada  cmp     [rcx+rax*2], di
0x18085dade  jnz     short loc_18085DAD7
0x18085dae0  lea     eax, ds:2[rax*2]
0x18085dae7  mov     r9d, 1; dwType
0x18085daed  mov     [rsp+290h+cbData], eax; cbData
0x18085daf1  lea     rdx, aSourcedata; "SourceData"
0x18085daf8  mov     [rsp+290h+phkResult], rcx; lpData
0x18085dafd  xor     r8d, r8d; Reserved
0x18085db00  mov     rcx, [rsp+290h+var_250]; hKey
0x18085db05  call    cs:__imp_RegSetValueExW
0x18085db0b  mov     ebx, eax
0x18085db0d  test    eax, eax
0x18085db0f  jz      loc_18085D7EE
0x18085db15  mov     ecx, 1E11900Bh
0x18085db1a  jmp     short loc_18085DAC6
0x18085db1c  mov     ecx, 1E119010h
  ... truncated ...
```
