# PrintConfig::CConfigManager::RetrieveLanguageFilesFromDevice(std::set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,bool)

- ea: `0x18004a814`
- end: `0x18004b0f2`
- name: `?RetrieveLanguageFilesFromDevice@CConfigManager@PrintConfig@@AEAAXAEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@_N@Z`
- size: `2270`
- prototype: `void __fastcall(__int64, __int64 ***, char)`
- caller_count: `3`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003a550`
- `0x180047c18`
- `0x18004dcd8`

## callees

- `0x180003400`
- `0x180003c20`
- `0x180004564`
- `0x18000ded0`
- `0x18000e644`
- `0x18000f830`
- `0x18000fa4c`
- `0x180018f00`
- `0x180018f58`
- `0x180039d64`
- `0x180040204`
- `0x1800416b8`
- `0x180042980`
- `0x18004a814`
- `0x1801b568c`
- `0x1801b56c8`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x18004ae2a`
- `KERNEL32!CompareStringOrdinal` at `0x18004ae2a`
- `ole32!CoCreateInstance` at `0x18004a8aa`
- `ole32!CoCreateInstance` at `0x18004a912`
- `ole32!CoCreateInstance` at `0x18004a980`
- `ole32!CoCreateInstance` at `0x18004a8aa`
- `ole32!CoCreateInstance` at `0x18004a912`
- `ole32!CoCreateInstance` at `0x18004a980`
- `ole32!CoInitializeEx` at `0x18004a861`
- `ole32!CoInitializeEx` at `0x18004a861`
- `ole32!CoUninitialize` at `0x18004ab60`
- `ole32!CoUninitialize` at `0x18004ab60`
- `ole32!CoTaskMemFree` at `0x18004ad7b`
- `ole32!CoTaskMemFree` at `0x18004adaa`
- `ole32!CoTaskMemFree` at `0x18004adc7`
- `ole32!CoTaskMemFree` at `0x18004af23`
- `ole32!CoTaskMemFree` at `0x18004ad7b`
- `ole32!CoTaskMemFree` at `0x18004adaa`
- `ole32!CoTaskMemFree` at `0x18004adc7`
- `ole32!CoTaskMemFree` at `0x18004af23`

## string_xrefs

- `0x18004aafd`: `PrintConfig::CConfigManager::RetrieveLanguageFilesFromDevice`
- `0x18004ae5e`: `PrintConfig::CConfigManager::RetrieveLanguageFilesFromDevice`
- `0x18004aec5`: `PrintConfig::CConfigManager::RetrieveLanguageFilesFromDevice`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall PrintConfig::CConfigManager::RetrieveLanguageFilesFromDevice(__int64 a1, __int64 ***a2, char a3)
{
  int v5; // r15d
  int v6; // edi
  HRESULT v7; // eax
  HRESULT v8; // eax
  int v9; // eax
  LPVOID v10; // rsi
  HRESULT v11; // eax
  _QWORD *v12; // rax
  __int64 *v13; // rbx
  HRESULT v14; // eax
  int v15; // eax
  __int64 *v16; // r8
  int v17; // eax
  int v18; // eax
  LPVOID *v19; // r15
  LPVOID v20; // r14
  LPVOID v21; // rcx
  __int64 **v22; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  int v25; // eax
  LPVOID v26; // rcx
  LPVOID v27; // rcx
  __int64 *v28; // rbx
  __int64 v29; // rsi
  char v30; // di
  __int64 v31; // rcx
  signed int v32; // r12d
  void *v33; // r13
  unsigned int v34; // r14d
  __int64 v35; // r8
  unsigned __int64 v36; // rdx
  LPCWCH *v37; // r15
  __int64 v38; // r14
  char v39; // r14
  const WCHAR *v40; // r8
  const WCHAR *v41; // rcx
  LPCWCH *v42; // r9
  LPCWCH *v43; // r8
  LPCWCH *v44; // r8
  __int64 v45; // r12
  __int64 v46; // rcx
  __int64 **v47; // rcx
  __int64 *k; // rax
  __int64 *v49; // rcx
  bool m; // zf
  LPVOID v51; // rcx
  LPVOID v52; // rsi
  LPVOID v53; // rcx
  LPVOID v55; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  int v57; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v58; // [rsp+60h] [rbp-A0h] BYREF
  int v59; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v60; // [rsp+6Ch] [rbp-94h] BYREF
  int v61; // [rsp+70h] [rbp-90h] BYREF
  int v62; // [rsp+74h] [rbp-8Ch]
  int v63; // [rsp+78h] [rbp-88h]
  __int64 v64; // [rsp+80h] [rbp-80h]
  __int64 *v65; // [rsp+88h] [rbp-78h]
  void **v66; // [rsp+90h] [rbp-70h]
  void *Src; // [rsp+98h] [rbp-68h] BYREF
  void **v68; // [rsp+A0h] [rbp-60h]
  wchar_t *String1; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v70; // [rsp+B0h] [rbp-50h] BYREF
  void **v71; // [rsp+C0h] [rbp-40h]
  void *v72; // [rsp+C8h] [rbp-38h]
  LPVOID v73; // [rsp+D0h] [rbp-30h]
  __int64 v74; // [rsp+D8h] [rbp-28h]
  LPVOID v75; // [rsp+E0h] [rbp-20h]
  LPCWCH lpString1[2]; // [rsp+E8h] [rbp-18h] BYREF
  int cchCount1[2]; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v78; // [rsp+100h] [rbp+0h]
  LPCWCH lpString2[2]; // [rsp+108h] [rbp+8h] BYREF
  int cchCount2; // [rsp+118h] [rbp+18h]
  unsigned __int64 v81; // [rsp+120h] [rbp+20h]
  __int64 v82; // [rsp+128h] [rbp+28h]

  v74 = -2;
  v64 = a1;
  v5 = 0;
  v6 = 0;
  v63 = 0;
  v7 = CoInitializeEx(0, 0);
  if ( v7 >= 0 )
  {
    v6 = 1;
    v63 = 1;
  }
  else if ( v7 != -2147417850 )
  {
    hr_error::hr_error((hr_error *)lpString1, v7);
    throw (hr_error *)lpString1;
  }
  ppv = 0;
  v8 = CoCreateInstance(
         &GUID_2a614240_a4c5_4c33_bd87_1bc709331639,
         0,
         1u,
         &GUID_d580dc0e_de39_4649_baa8_bf0b85a03a97,
         &ppv);
  if ( v8 < 0 )
  {
    hr_error::hr_error((hr_error *)lpString1, v8);
    throw (hr_error *)lpString1;
  }
  v9 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64))(*(_QWORD *)ppv + 24LL))(ppv, *(_QWORD *)(a1 + 16), 2);
  if ( v9 < 0 )
  {
    hr_error::hr_error((hr_error *)lpString1, v9);
    throw (hr_error *)lpString1;
  }
  v10 = ppv;
  v73 = ppv;
  v75 = ppv;
  v58 = 0;
  v11 = CoCreateInstance(
          &GUID_fc5b8a24_db05_4a01_8388_22edf6c2bbba,
          0,
          1u,
          &GUID_d752f6c0_94a8_4275_a77d_8f1d1a1121ae,
          &v58);
  if ( v11 < 0 )
  {
    hr_error::hr_error((hr_error *)lpString1, v11);
    throw (hr_error *)lpString1;
  }
  v70 = 0;
  v12 = operator new(0x48u);
  *v12 = v12;
  v12[1] = v12;
  v12[2] = v12;
  *((_WORD *)v12 + 12) = 257;
  *(_QWORD *)&v70 = v12;
  v13 = **a2;
  while ( !*((_BYTE *)v13 + 25) )
  {
    v55 = 0;
    v14 = CoCreateInstance(
            &GUID_b9162a23_45f9_47cc_80f5_fe0fe9b9e1a2,
            0,
            1u,
            &GUID_8f348bd7_4b47_4755_8a9d_0f422df3dc89,
            &v55);
    if ( v14 < 0 )
    {
      hr_error::hr_error((hr_error *)lpString1, v14);
      throw (hr_error *)lpString1;
    }
    v15 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *))(*(_QWORD *)v55 + 24LL))(v55, L"\\Printer.Resources");
    if ( v15 < 0 )
    {
      hr_error::hr_error((hr_error *)lpString1, v15);
      throw (hr_error *)lpString1;
    }
    if ( (unsigned __int64)v13[7] <= 7 )
      v16 = v13 + 4;
    else
      v16 = (__int64 *)v13[4];
    v17 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *, _QWORD))(*(_QWORD *)v55 + 32LL))(
            v55,
            4,
            v16,
            (unsigned int)(2 * *((_DWORD *)v13 + 12) + 2));
    if ( v17 < 0 )
    {
      hr_error::hr_error((hr_error *)lpString1, v17);
      throw (hr_error *)lpString1;
    }
    v18 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)v58 + 24LL))(v58, v55);
    if ( v18 < 0 )
    {
      hr_error::hr_error((hr_error *)lpString1, v18);
      throw (hr_error *)lpString1;
    }
    v19 = (LPVOID *)std::map<std::wstring,Microsoft::WRL::ComPtr<IBidiRequest>>::operator[](
                      (__int64 *)&v70,
                      (const wchar_t *)v13 + 16);
    v20 = v55;
    if ( *v19 == v55 )
    {
      v5 = 0;
    }
    else
    {
      if ( v55 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v55 + 8LL))(v55);
      v21 = *v19;
      *v19 = v20;
      v5 = 0;
      if ( v21 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v21 + 16LL))(v21);
      v20 = v55;
    }
    if ( v20 )
    {
      v55 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v22 = (__int64 **)v13[2];
    if ( *((_BYTE *)v22 + 25) )
    {
      for ( i = (__int64 *)v13[1]; !*((_BYTE *)i + 25) && v13 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v13 = i;
      v13 = i;
    }
    else
    {
      v13 = (__int64 *)v13[2];
      for ( j = *v22; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v13 = j;
    }
  }
  v25 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, LPVOID))(*(_QWORD *)ppv + 48LL))(
          ppv,
          L"GetWithArgument",
          v58);
  if ( v25 < 0 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "PrintConfig::CConfigManager::RetrieveLanguageFilesFromDevice",
      L"Device resource bidi request failed (hr: 0x%x)",
      (unsigned int)v25);
    std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IBidiRequest>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IBidiRequest>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IBidiRequest>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IBidiRequest>>>,0>>((void **)&v70);
    v26 = v58;
    if ( v58 )
    {
      v58 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 32LL))(v10);
    v27 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
    }
    goto LABEL_40;
  }
  v28 = *(__int64 **)v70;
  v65 = *(__int64 **)v70;
  v29 = v64;
  v30 = a3;
  while ( !*((_BYTE *)v28 + 25) )
  {
    std::wstring::wstring((__int64)lpString2, (__int64)(v28 + 4));
    v31 = v28[8];
    v82 = v31;
    if ( v31 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
      v31 = v82;
    }
    v59 = 50;
    v32 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v31 + 40LL))(v31, &v59);
    if ( v32 >= 0 && v59 )
    {
      if ( v59 > 0 )
        v32 = (unsigned __int16)v59 | 0x80070000;
      else
        v32 = v59;
    }
    v60 = 0;
    if ( v32 >= 0 )
      v32 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v82 + 56LL))(v82, &v60);
    *(_OWORD *)lpString1 = 0;
    *(_QWORD *)cchCount1 = 0;
    v78 = 7;
    LOWORD(lpString1[0]) = 0;
    v71 = &CoTaskMemRAII<unsigned char *>::`vftable';
    v33 = 0;
    v72 = 0;
    v62 = 0;
    v34 = 0;
    LODWORD(v55) = 0;
    if ( v32 >= 0 )
    {
      do
      {
        if ( v34 >= v60 )
          break;
        v68 = &CoTaskMemRAII<unsigned short *>::`vftable';
        String1 = 0;
        v57 = 0;
        v66 = &CoTaskMemRAII<unsigned char *>::`vftable';
        Src = 0;
        v61 = 0;
        v32 = (*(__int64 (__fastcall **)(__int64, _QWORD, wchar_t **, int *, void **, int *))(*(_QWORD *)v82 + 48LL))(
                v82,
                v34,
                &String1,
                &v57,
                &Src,
                &v61);
        if ( v32 >= 0 )
        {
          if ( !wcscmp_0(String1, L"\\Printer.Resources:Language") && v57 == 4 )
          {
            v36 = -1;
            do
              ++v36;
            while ( *((_WORD *)Src + v36) );
            if ( v36 > v78 )
            {
              std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                (char **)lpString1,
                v36,
                v35,
                Src);
            }
            else
            {
              v37 = lpString1;
              if ( v78 > 7 )
                v37 = (LPCWCH *)lpString1[0];
              *(_QWORD *)cchCount1 = v36;
              v38 = 2 * v36;
              memmove_0(v37, Src, 2 * v36);
              *(_WORD *)((char *)v37 + v38) = 0;
              v34 = (unsigned int)v55;
              v5 = v62;
            }
          }
          else if ( !wcscmp_0(String1, L"\\Printer.Resources:Data") && v57 == 7 && Src )
          {
            if ( v33 )
              CoTaskMemFree(v33);
            v33 = Src;
            v72 = Src;
            Src = 0;
            v5 = v61;
            v62 = v61;
          }
        }
        v66 = &CoTaskMemRAII<unsigned char *>::`vftable';
        if ( Src )
        {
          CoTaskMemFree(Src);
          Src = 0;
        }
        v68 = &CoTaskMemRAII<unsigned short *>::`vftable';
        if ( String1 )
        {
          CoTaskMemFree(String1);
          String1 = 0;
        }
        LODWORD(v55) = ++v34;
      }
      while ( v32 >= 0 );
      v28 = v65;
      v29 = v64;
      v30 = a3;
    }
    v39 = 0;
    if ( v32 >= 0 )
    {
      v40 = (const WCHAR *)lpString2;
      if ( v81 > 7 )
        v40 = lpString2[0];
      v41 = (const WCHAR *)lpString1;
      if ( v78 > 7 )
        v41 = lpString1[0];
      if ( CompareStringOrdinal(v41, cchCount1[0], v40, cchCount2, 1) != 2 )
      {
        v42 = lpString1;
        if ( v78 > 7 )
          v42 = (LPCWCH *)lpString1[0];
        v43 = lpString2;
        if ( v81 > 7 )
          v43 = (LPCWCH *)lpString2[0];
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
          "PrintConfig::CConfigManager::RetrieveLanguageFilesFromDevice",
          L"Requested \"%ws\"; retrieved \"%ws\"",
          v43,
          v42);
        v39 = 1;
      }
    }
    if ( v30 )
    {
      PrintConfig::LanguageDatabase::SetLanguageState(*(void **)(v29 + 64), lpString2, 2u);
      if ( v39 )
        PrintConfig::LanguageDatabase::SetLanguageState(*(void **)(v29 + 64), lpString1, 2u);
    }
    if ( v32 < 0 )
      goto LABEL_95;
    if ( !v5 )
    {
      v32 = -2147023728;
LABEL_95:
      v44 = lpString2;
      if ( v81 > 7 )
        v44 = (LPCWCH *)lpString2[0];
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "PrintConfig::CConfigManager::RetrieveLanguageFilesFromDevice",
        L"Failed to retrieve language resources for \"%ws\" (hr: 0x%x)",
        v44,
        (unsigned int)v32);
      goto LABEL_101;
    }
    v45 = v64;
    PrintConfig::CConfigManager::CommitLanguageResources(v64, lpString2, v30, (__int64)v33, v5);
    if ( v39 )
      PrintConfig::CConfigManager::CommitLanguageResources(v45, lpString1, v30, (__int64)v33, v5);
    v29 = v45;
LABEL_101:
    v71 = &CoTaskMemRAII<unsigned char *>::`vftable';
    v5 = 0;
    if ( v33 )
    {
      CoTaskMemFree(v33);
      v72 = 0;
    }
    std::wstring::~wstring((char **)lpString1);
    v46 = v82;
    if ( v82 )
    {
      v82 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    }
    std::wstring::~wstring((char **)lpString2);
    v47 = (__int64 **)v28[2];
    if ( *((_BYTE *)v47 + 25) )
    {
      for ( k = (__int64 *)v28[1]; !*((_BYTE *)k + 25) && v28 == (__int64 *)k[2]; k = (__int64 *)k[1] )
        v28 = k;
      v28 = k;
      v65 = k;
    }
    else
    {
      v28 = (__int64 *)v28[2];
      v49 = *v47;
      for ( m = *((_BYTE *)v49 + 25) == 0; ; m = *((_BYTE *)v49 + 25) == 0 )
      {
        v65 = v28;
        if ( !m )
          break;
        v28 = v49;
        v49 = (__int64 *)*v49;
      }
    }
  }
  std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IBidiRequest>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IBidiRequest>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IBidiRequest>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IBidiRequest>>>,0>>((void **)&v70);
  v51 = v58;
  v6 = v63;
  v52 = v73;
  if ( v58 )
  {
    v58 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v51 + 16LL))(v51);
  }
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v52 + 32LL))(v52);
  v53 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v53 + 16LL))(v53);
  }
LABEL_40:
  if ( v6 )
    CoUninitialize();
}

```

## disassembly

```asm
0x18004a814  push    rbp
0x18004a816  push    rbx
0x18004a817  push    rsi
0x18004a818  push    rdi
0x18004a819  push    r12
0x18004a81b  push    r13
0x18004a81d  push    r14
0x18004a81f  push    r15
0x18004a821  lea     rbp, [rsp-48h]
0x18004a826  sub     rsp, 148h
0x18004a82d  mov     [rbp+80h+var_A8], 0FFFFFFFFFFFFFFFEh
0x18004a835  mov     rax, cs:__security_cookie
0x18004a83c  xor     rax, rsp
0x18004a83f  mov     [rbp+80h+var_50], rax
0x18004a843  mov     [rsp+180h+var_140], r8b
0x18004a848  mov     rbx, rdx
0x18004a84b  mov     r12, rcx
0x18004a84e  mov     [rbp+80h+var_100], rcx
0x18004a852  xor     r15d, r15d
0x18004a855  mov     edi, r15d
0x18004a858  mov     [rsp+180h+var_108], r15d
0x18004a85d  xor     edx, edx; dwCoInit
0x18004a85f  xor     ecx, ecx; pvReserved
0x18004a861  call    cs:__imp_CoInitializeEx
0x18004a868  nop     dword ptr [rax+rax+00h]
0x18004a86d  test    eax, eax
0x18004a86f  jns     short loc_18004A87E
0x18004a871  cmp     eax, 80010106h
0x18004a876  jnz     loc_18004B02E
0x18004a87c  jmp     short loc_18004A887
0x18004a87e  mov     edi, 1
0x18004a883  mov     [rsp+180h+var_108], edi
0x18004a887  mov     [rsp+180h+var_130], r15
0x18004a88c  lea     rax, [rsp+180h+var_130]
0x18004a891  mov     [rsp+180h+ppv], rax; ppv
0x18004a896  lea     r9, _GUID_d580dc0e_de39_4649_baa8_bf0b85a03a97; riid
0x18004a89d  xor     edx, edx; pUnkOuter
0x18004a89f  lea     r8d, [rdx+1]; dwClsContext
0x18004a8a3  lea     rcx, _GUID_2a614240_a4c5_4c33_bd87_1bc709331639; rclsid
0x18004a8aa  call    cs:__imp_CoCreateInstance
0x18004a8b1  nop     dword ptr [rax+rax+00h]
0x18004a8b6  test    eax, eax
0x18004a8b8  js      loc_18004B04A
0x18004a8be  mov     rcx, [rsp+180h+var_130]
0x18004a8c3  mov     rax, [rcx]
0x18004a8c6  mov     r8d, 2
0x18004a8cc  mov     rdx, [r12+10h]
0x18004a8d1  mov     rax, [rax+18h]
0x18004a8d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a8da  test    eax, eax
0x18004a8dc  js      loc_18004B066
0x18004a8e2  mov     rsi, [rsp+180h+var_130]
0x18004a8e7  mov     [rbp+80h+var_B0], rsi
0x18004a8eb  mov     [rbp+80h+var_A0], rsi
0x18004a8ef  mov     [rsp+180h+var_120], r15
0x18004a8f4  lea     rax, [rsp+180h+var_120]
0x18004a8f9  mov     [rsp+180h+ppv], rax; ppv
0x18004a8fe  lea     r9, _GUID_d752f6c0_94a8_4275_a77d_8f1d1a1121ae; riid
0x18004a905  xor     edx, edx; pUnkOuter
0x18004a907  lea     r8d, [rdx+1]; dwClsContext
0x18004a90b  lea     rcx, _GUID_fc5b8a24_db05_4a01_8388_22edf6c2bbba; rclsid
0x18004a912  call    cs:__imp_CoCreateInstance
0x18004a919  nop     dword ptr [rax+rax+00h]
0x18004a91e  test    eax, eax
0x18004a920  js      loc_18004B082
0x18004a926  xorps   xmm0, xmm0
0x18004a929  movdqu  [rbp+80h+var_D0], xmm0
0x18004a92e  mov     ecx, 48h ; 'H'; Size
0x18004a933  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004a938  mov     [rax], rax
0x18004a93b  mov     [rax+8], rax
0x18004a93f  mov     [rax+10h], rax
0x18004a943  mov     word ptr [rax+18h], 101h
0x18004a949  mov     qword ptr [rbp+80h+var_D0], rax
0x18004a94d  mov     rbx, [rbx]
0x18004a950  mov     rbx, [rbx]
0x18004a953  cmp     [rbx+19h], r15b
0x18004a957  jnz     loc_18004AACE
0x18004a95d  mov     [rsp+180h+var_138], r15
0x18004a962  lea     rax, [rsp+180h+var_138]
0x18004a967  mov     [rsp+180h+ppv], rax; ppv
0x18004a96c  lea     r9, _GUID_8f348bd7_4b47_4755_8a9d_0f422df3dc89; riid
0x18004a973  xor     edx, edx; pUnkOuter
0x18004a975  lea     r8d, [rdx+1]; dwClsContext
0x18004a979  lea     rcx, _GUID_b9162a23_45f9_47cc_80f5_fe0fe9b9e1a2; rclsid
0x18004a980  call    cs:__imp_CoCreateInstance
0x18004a987  nop     dword ptr [rax+rax+00h]
0x18004a98c  test    eax, eax
0x18004a98e  js      loc_18004B012
0x18004a994  mov     rcx, [rsp+180h+var_138]
0x18004a999  mov     rax, [rcx]
0x18004a99c  lea     rdx, aPrinterResourc; "\\Printer.Resources"
0x18004a9a3  mov     rax, [rax+18h]
0x18004a9a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a9ac  test    eax, eax
0x18004a9ae  js      loc_18004B0D6
0x18004a9b4  lea     r14, [rbx+20h]
0x18004a9b8  mov     rcx, [rsp+180h+var_138]
0x18004a9bd  mov     rax, [rcx]
0x18004a9c0  mov     r10, [rax+20h]
0x18004a9c4  mov     eax, [r14+10h]
0x18004a9c8  lea     r9d, ds:2[rax*2]
0x18004a9d0  cmp     qword ptr [r14+18h], 7
0x18004a9d5  jbe     short loc_18004A9DC
0x18004a9d7  mov     r8, [r14]
0x18004a9da  jmp     short loc_18004A9DF
0x18004a9dc  mov     r8, r14
0x18004a9df  mov     edx, 4
0x18004a9e4  mov     rax, r10
0x18004a9e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a9ec  test    eax, eax
0x18004a9ee  js      loc_18004B0BA
0x18004a9f4  mov     rcx, [rsp+180h+var_120]
0x18004a9f9  mov     rax, [rcx]
0x18004a9fc  mov     rdx, [rsp+180h+var_138]
0x18004aa01  mov     rax, [rax+18h]
0x18004aa05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa0a  test    eax, eax
0x18004aa0c  js      loc_18004B09E
0x18004aa12  mov     rdx, r14
0x18004aa15  lea     rcx, [rbp+80h+var_D0]
0x18004aa19  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIBidiRequest@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIBidiRequest@@@WRL@Microsoft@@@std@@@2@@std@@QEAAAEAV?$ComPtr@UIBidiRequest@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,Microsoft::WRL::ComPtr<IBidiRequest>>::operator[](std::wstring const &)
0x18004aa1e  mov     r15, rax
0x18004aa21  mov     r14, [rsp+180h+var_138]
0x18004aa26  cmp     [rax], r14
0x18004aa29  jz      short loc_18004AA62
0x18004aa2b  test    r14, r14
0x18004aa2e  jz      short loc_18004AA40
0x18004aa30  mov     rcx, [r14]
0x18004aa33  mov     rax, [rcx+8]
0x18004aa37  mov     rcx, r14
0x18004aa3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa3f  nop
0x18004aa40  mov     rcx, [r15]
0x18004aa43  mov     [r15], r14
0x18004aa46  xor     r15d, r15d
0x18004aa49  test    rcx, rcx
0x18004aa4c  jz      short loc_18004AA5B
0x18004aa4e  mov     rax, [rcx]
0x18004aa51  mov     rax, [rax+10h]
0x18004aa55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa5a  nop
0x18004aa5b  mov     r14, [rsp+180h+var_138]
0x18004aa60  jmp     short loc_18004AA65
0x18004aa62  xor     r15d, r15d
0x18004aa65  test    r14, r14
0x18004aa68  jz      short loc_18004AA7F
0x18004aa6a  mov     [rsp+180h+var_138], r15
0x18004aa6f  mov     rax, [r14]
0x18004aa72  mov     rcx, r14
0x18004aa75  mov     rax, [rax+10h]
0x18004aa79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa7e  nop
0x18004aa7f  mov     rcx, [rbx+10h]
0x18004aa83  cmp     [rcx+19h], r15b
0x18004aa87  jz      short loc_18004AAAA
0x18004aa89  mov     rax, [rbx+8]
0x18004aa8d  jmp     short loc_18004AA9C
0x18004aa8f  cmp     rbx, [rax+10h]
0x18004aa93  jnz     short loc_18004AAA2
0x18004aa95  mov     rbx, rax
0x18004aa98  mov     rax, [rax+8]
0x18004aa9c  cmp     [rax+19h], r15b
0x18004aaa0  jz      short loc_18004AA8F
0x18004aaa2  mov     rbx, rax
0x18004aaa5  jmp     loc_18004A953
0x18004aaaa  mov     rbx, rcx
0x18004aaad  mov     rcx, [rcx]
0x18004aab0  cmp     [rcx+19h], r15b
0x18004aab4  jnz     loc_18004A953
0x18004aaba  mov     rbx, rcx
0x18004aabd  mov     rax, [rcx]
0x18004aac0  mov     rcx, rax
0x18004aac3  cmp     [rax+19h], r15b
0x18004aac7  jz      short loc_18004AABA
0x18004aac9  jmp     loc_18004A953
0x18004aace  mov     rcx, [rsp+180h+var_130]
0x18004aad3  mov     rax, [rcx]
0x18004aad6  mov     r8, [rsp+180h+var_120]
0x18004aadb  lea     rdx, aGetwithargumen; "GetWithArgument"
0x18004aae2  mov     rax, [rax+30h]
0x18004aae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aaeb  test    eax, eax
0x18004aaed  jns     loc_18004AB8D
0x18004aaf3  mov     r8d, eax
0x18004aaf6  lea     rdx, aDeviceResource; "Device resource bidi request failed (hr"...
0x18004aafd  lea     rcx, aPrintconfigCco_1; "PrintConfig::CConfigManager::RetrieveLa"...
0x18004ab04  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18004ab09  nop
0x18004ab0a  lea     rcx, [rbp+80h+var_D0]
0x18004ab0e  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIBidiRequest@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIBidiRequest@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IBidiRequest>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IBidiRequest>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IBidiRequest>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IBidiRequest>>>,0>>(void)
0x18004ab13  nop
0x18004ab14  mov     rcx, [rsp+180h+var_120]
0x18004ab19  test    rcx, rcx
0x18004ab1c  jz      short loc_18004AB30
0x18004ab1e  mov     [rsp+180h+var_120], r15
0x18004ab23  mov     rax, [rcx]
0x18004ab26  mov     rax, [rax+10h]
0x18004ab2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ab2f  nop
0x18004ab30  mov     rax, [rsi]
0x18004ab33  mov     rcx, rsi
0x18004ab36  mov     rax, [rax+20h]
0x18004ab3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ab3f  nop
0x18004ab40  mov     rcx, [rsp+180h+var_130]
0x18004ab45  test    rcx, rcx
0x18004ab48  jz      short loc_18004AB5C
0x18004ab4a  mov     [rsp+180h+var_130], r15
0x18004ab4f  mov     rax, [rcx]
0x18004ab52  mov     rax, [rax+10h]
0x18004ab56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ab5b  nop
0x18004ab5c  test    edi, edi
0x18004ab5e  jz      short loc_18004AB6C
0x18004ab60  call    cs:__imp_CoUninitialize
0x18004ab67  nop     dword ptr [rax+rax+00h]
0x18004ab6c  mov     rcx, [rbp+80h+var_50]
0x18004ab70  xor     rcx, rsp; StackCookie
0x18004ab73  call    __security_check_cookie
0x18004ab78  add     rsp, 148h
0x18004ab7f  pop     r15
0x18004ab81  pop     r14
0x18004ab83  pop     r13
0x18004ab85  pop     r12
0x18004ab87  pop     rdi
0x18004ab88  pop     rsi
0x18004ab89  pop     rbx
0x18004ab8a  pop     rbp
0x18004ab8b  retn
0x18004ab8d  mov     rbx, qword ptr [rbp+80h+var_D0]
0x18004ab91  mov     rbx, [rbx]
0x18004ab94  mov     [rbp+80h+var_F8], rbx
0x18004ab98  mov     rsi, [rbp+80h+var_100]
0x18004ab9c  mov     dil, [rsp+180h+var_140]
0x18004aba1  lea     r13, ??_7?$CoTaskMemRAII@PEAE@@6B@; const CoTaskMemRAII<uchar *>::`vftable'
0x18004aba8  cmp     [rbx+19h], r15b
0x18004abac  jnz     loc_18004AFB3
0x18004abb2  lea     rdx, [rbx+20h]
0x18004abb6  lea     rcx, [rbp+80h+lpString2]
0x18004abba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004abbf  mov     rcx, [rbx+40h]
0x18004abc3  mov     [rbp+80h+var_58], rcx
0x18004abc7  test    rcx, rcx
0x18004abca  jz      short loc_18004ABDC
0x18004abcc  mov     rax, [rcx]
0x18004abcf  mov     rax, [rax+8]
0x18004abd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004abd8  mov     rcx, [rbp+80h+var_58]
0x18004abdc  mov     [rsp+180h+var_118], 32h ; '2'
0x18004abe4  mov     rax, [rcx]
0x18004abe7  lea     rdx, [rsp+180h+var_118]
0x18004abec  mov     rax, [rax+28h]
0x18004abf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004abf5  mov     r12d, eax
0x18004abf8  test    eax, eax
0x18004abfa  js      short loc_18004AC16
0x18004abfc  mov     eax, [rsp+180h+var_118]
0x18004ac00  test    eax, eax
0x18004ac02  jz      short loc_18004AC16
0x18004ac04  jg      short loc_18004AC0B
0x18004ac06  mov     r12d, eax
0x18004ac09  jmp     short loc_18004AC16
0x18004ac0b  movzx   r12d, ax
0x18004ac0f  or      r12d, 80070000h
0x18004ac16  mov     [rsp+180h+var_114], r15d
0x18004ac1b  test    r12d, r12d
0x18004ac1e  js      short loc_18004AC38
0x18004ac20  mov     rcx, [rbp+80h+var_58]
0x18004ac24  mov     rax, [rcx]
0x18004ac27  lea     rdx, [rsp+180h+var_114]
0x18004ac2c  mov     rax, [rax+38h]
0x18004ac30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac35  mov     r12d, eax
0x18004ac38  xorps   xmm0, xmm0
0x18004ac3b  movups  xmmword ptr [rbp+80h+lpString1], xmm0
0x18004ac3f  mov     qword ptr [rbp+80h+cchCount1], r15
0x18004ac43  mov     [rbp+80h+var_80], 7
0x18004ac4b  mov     word ptr [rbp+80h+lpString1], r15w
0x18004ac50  mov     [rbp+80h+var_C0], r13
0x18004ac54  mov     r13, r15
0x18004ac57  mov     [rbp+80h+var_B8], r15
0x18004ac5b  mov     [rsp+180h+var_10C], r15d
0x18004ac60  xor     eax, eax
0x18004ac62  mov     r14d, eax
0x18004ac65  mov     dword ptr [rsp+180h+var_138], eax
0x18004ac69  test    r12d, r12d
0x18004ac6c  js      loc_18004ADF7
0x18004ac72  xor     esi, esi
0x18004ac74  lea     rdi, ??_7?$CoTaskMemRAII@PEAE@@6B@; const CoTaskMemRAII<uchar *>::`vftable'
0x18004ac7b  lea     rbx, ??_7?$CoTaskMemRAII@PEAG@@6B@; const CoTaskMemRAII<ushort *>::`vftable'
0x18004ac82  cmp     r14d, [rsp+180h+var_114]
0x18004ac87  jnb     loc_18004ADE8
0x18004ac8d  mov     [rbp+80h+var_E0], rbx
0x18004ac91  mov     [rbp+80h+String1], rsi
0x18004ac95  mov     [rsp+180h+var_128], esi
0x18004ac99  mov     [rbp+80h+var_F0], rdi
0x18004ac9d  mov     [rbp+80h+Src], rsi
0x18004aca1  mov     [rsp+180h+var_110], esi
0x18004aca5  mov     rcx, [rbp+80h+var_58]
  ... truncated ...
```
