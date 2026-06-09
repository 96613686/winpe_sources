# PrintConfig::CConfigManager::RetrieveLanguageFilesFromDevice(std::set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,bool)

- ea: `0x1800489a4`
- end: `0x180049245`
- name: `?RetrieveLanguageFilesFromDevice@CConfigManager@PrintConfig@@AEAAXAEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@_N@Z`
- size: `2209`
- prototype: ``
- caller_count: `3`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180038fb4`
- `0x180045f4c`
- `0x18004bce4`

## callees

- `0x1800032e0`
- `0x180003b00`
- `0x180004424`
- `0x18000dadc`
- `0x18000e23c`
- `0x18000f380`
- `0x18000f590`
- `0x1800183a0`
- `0x1800183f8`
- `0x1800387e4`
- `0x18003eb04`
- `0x18003ff14`
- `0x180041038`
- `0x1800489a4`
- `0x1801adb1c`
- `0x1801adb58`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x180048f89`
- `KERNEL32!CompareStringOrdinal` at `0x180048f89`
- `ole32!CoCreateInstance` at `0x180048a34`
- `ole32!CoCreateInstance` at `0x180048a96`
- `ole32!CoCreateInstance` at `0x180048afe`
- `ole32!CoCreateInstance` at `0x180048a34`
- `ole32!CoCreateInstance` at `0x180048a96`
- `ole32!CoCreateInstance` at `0x180048afe`
- `ole32!CoInitializeEx` at `0x1800489f1`
- `ole32!CoInitializeEx` at `0x1800489f1`
- `ole32!CoUninitialize` at `0x180048cd8`
- `ole32!CoUninitialize` at `0x180048cd8`
- `ole32!CoTaskMemFree` at `0x180048eec`
- `ole32!CoTaskMemFree` at `0x180048f15`
- `ole32!CoTaskMemFree` at `0x180048f2c`
- `ole32!CoTaskMemFree` at `0x18004907c`
- `ole32!CoTaskMemFree` at `0x180048eec`
- `ole32!CoTaskMemFree` at `0x180048f15`
- `ole32!CoTaskMemFree` at `0x180048f2c`
- `ole32!CoTaskMemFree` at `0x18004907c`

## string_xrefs

- `0x180048c75`: `PrintConfig::CConfigManager::RetrieveLanguageFilesFromDevice`
- `0x180048fb7`: `PrintConfig::CConfigManager::RetrieveLanguageFilesFromDevice`
- `0x18004901e`: `PrintConfig::CConfigManager::RetrieveLanguageFilesFromDevice`

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
  int v32; // r8d
  signed int v33; // r12d
  void *v34; // r13
  unsigned int v35; // r14d
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
  int v46; // r8d
  __int64 v47; // rcx
  __int64 **v48; // rcx
  __int64 *k; // rax
  __int64 *v50; // rcx
  bool m; // zf
  LPVOID v52; // rcx
  LPVOID v53; // rsi
  LPVOID v54; // rcx
  LPVOID v56; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp-B0h] BYREF
  int v58; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v59; // [rsp+60h] [rbp-A0h] BYREF
  int v60; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v61; // [rsp+6Ch] [rbp-94h] BYREF
  int v62; // [rsp+70h] [rbp-90h] BYREF
  int v63; // [rsp+74h] [rbp-8Ch]
  int v64; // [rsp+78h] [rbp-88h]
  __int64 v65; // [rsp+80h] [rbp-80h]
  __int64 *v66; // [rsp+88h] [rbp-78h]
  void **v67; // [rsp+90h] [rbp-70h]
  void *Src; // [rsp+98h] [rbp-68h] BYREF
  void **v69; // [rsp+A0h] [rbp-60h]
  wchar_t *String1; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v71; // [rsp+B0h] [rbp-50h] BYREF
  void **v72; // [rsp+C0h] [rbp-40h]
  void *v73; // [rsp+C8h] [rbp-38h]
  LPVOID v74; // [rsp+D0h] [rbp-30h]
  __int64 v75; // [rsp+D8h] [rbp-28h]
  LPVOID v76; // [rsp+E0h] [rbp-20h]
  LPCWCH lpString1[2]; // [rsp+E8h] [rbp-18h] BYREF
  int cchCount1[2]; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v79; // [rsp+100h] [rbp+0h]
  LPCWCH lpString2[2]; // [rsp+108h] [rbp+8h] BYREF
  int cchCount2; // [rsp+118h] [rbp+18h]
  unsigned __int64 v82; // [rsp+120h] [rbp+20h]
  __int64 v83; // [rsp+128h] [rbp+28h]

  v75 = -2;
  v65 = a1;
  v5 = 0;
  v6 = 0;
  v64 = 0;
  v7 = CoInitializeEx(0, 0);
  if ( v7 >= 0 )
  {
    v6 = 1;
    v64 = 1;
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
  v74 = ppv;
  v76 = ppv;
  v59 = 0;
  v11 = CoCreateInstance(
          &GUID_fc5b8a24_db05_4a01_8388_22edf6c2bbba,
          0,
          1u,
          &GUID_d752f6c0_94a8_4275_a77d_8f1d1a1121ae,
          &v59);
  if ( v11 < 0 )
  {
    hr_error::hr_error((hr_error *)lpString1, v11);
    throw (hr_error *)lpString1;
  }
  v71 = 0;
  v12 = operator new(0x48u);
  *v12 = v12;
  v12[1] = v12;
  v12[2] = v12;
  *((_WORD *)v12 + 12) = 257;
  *(_QWORD *)&v71 = v12;
  v13 = **a2;
  while ( !*((_BYTE *)v13 + 25) )
  {
    v56 = 0;
    v14 = CoCreateInstance(
            &GUID_b9162a23_45f9_47cc_80f5_fe0fe9b9e1a2,
            0,
            1u,
            &GUID_8f348bd7_4b47_4755_8a9d_0f422df3dc89,
            &v56);
    if ( v14 < 0 )
    {
      hr_error::hr_error((hr_error *)lpString1, v14);
      throw (hr_error *)lpString1;
    }
    v15 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *))(*(_QWORD *)v56 + 24LL))(v56, L"\\Printer.Resources");
    if ( v15 < 0 )
    {
      hr_error::hr_error((hr_error *)lpString1, v15);
      throw (hr_error *)lpString1;
    }
    if ( (unsigned __int64)v13[7] <= 7 )
      v16 = v13 + 4;
    else
      v16 = (__int64 *)v13[4];
    v17 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *, _QWORD))(*(_QWORD *)v56 + 32LL))(
            v56,
            4,
            v16,
            (unsigned int)(2 * *((_DWORD *)v13 + 12) + 2));
    if ( v17 < 0 )
    {
      hr_error::hr_error((hr_error *)lpString1, v17);
      throw (hr_error *)lpString1;
    }
    v18 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)v59 + 24LL))(v59, v56);
    if ( v18 < 0 )
    {
      hr_error::hr_error((hr_error *)lpString1, v18);
      throw (hr_error *)lpString1;
    }
    v19 = (LPVOID *)std::map<std::wstring,Microsoft::WRL::ComPtr<IBidiRequest>>::operator[](&v71, v13 + 4);
    v20 = v56;
    if ( *v19 == v56 )
    {
      v5 = 0;
    }
    else
    {
      if ( v56 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v56 + 8LL))(v56);
      v21 = *v19;
      *v19 = v20;
      v5 = 0;
      if ( v21 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v21 + 16LL))(v21);
      v20 = v56;
    }
    if ( v20 )
    {
      v56 = 0;
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
          v59);
  if ( v25 < 0 )
  {
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "PrintConfig::CConfigManager::RetrieveLanguageFilesFromDevice",
      L"Device resource bidi request failed (hr: 0x%x)",
      (unsigned int)v25);
    std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IBidiRequest>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IBidiRequest>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IBidiRequest>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IBidiRequest>>>,0>>((void **)&v71);
    v26 = v59;
    if ( v59 )
    {
      v59 = 0;
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
  v28 = *(__int64 **)v71;
  v66 = *(__int64 **)v71;
  v29 = v65;
  v30 = a3;
  while ( !*((_BYTE *)v28 + 25) )
  {
    std::wstring::wstring((__int64)lpString2, (__int64)(v28 + 4));
    v31 = v28[8];
    v83 = v31;
    if ( v31 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
      v31 = v83;
    }
    v60 = 50;
    v33 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v31 + 40LL))(v31, &v60);
    if ( v33 >= 0 && v60 )
    {
      if ( v60 > 0 )
        v33 = (unsigned __int16)v60 | 0x80070000;
      else
        v33 = v60;
    }
    v61 = 0;
    if ( v33 >= 0 )
      v33 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v83 + 56LL))(v83, &v61);
    *(_OWORD *)lpString1 = 0;
    *(_QWORD *)cchCount1 = 0;
    v79 = 7;
    LOWORD(lpString1[0]) = 0;
    v72 = &CoTaskMemRAII<unsigned char *>::`vftable';
    v34 = 0;
    v73 = 0;
    v63 = 0;
    v35 = 0;
    LODWORD(v56) = 0;
    if ( v33 >= 0 )
    {
      do
      {
        if ( v35 >= v61 )
          break;
        v69 = &CoTaskMemRAII<unsigned short *>::`vftable';
        String1 = 0;
        v58 = 0;
        v67 = &CoTaskMemRAII<unsigned char *>::`vftable';
        Src = 0;
        v62 = 0;
        v33 = (*(__int64 (__fastcall **)(__int64, _QWORD, wchar_t **, int *, void **, int *))(*(_QWORD *)v83 + 48LL))(
                v83,
                v35,
                &String1,
                &v58,
                &Src,
                &v62);
        if ( v33 >= 0 )
        {
          if ( !wcscmp_0(String1, L"\\Printer.Resources:Language") && v58 == 4 )
          {
            v36 = -1;
            do
              ++v36;
            while ( *((_WORD *)Src + v36) );
            if ( v36 > v79 )
            {
              std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(lpString1);
            }
            else
            {
              v37 = lpString1;
              if ( v79 > 7 )
                v37 = (LPCWCH *)lpString1[0];
              *(_QWORD *)cchCount1 = v36;
              v38 = 2 * v36;
              memmove_0(v37, Src, 2 * v36);
              *(_WORD *)((char *)v37 + v38) = 0;
              v35 = (unsigned int)v56;
              v5 = v63;
            }
          }
          else if ( !wcscmp_0(String1, L"\\Printer.Resources:Data") && v58 == 7 && Src )
          {
            if ( v34 )
              CoTaskMemFree(v34);
            v34 = Src;
            v73 = Src;
            Src = 0;
            v5 = v62;
            v63 = v62;
          }
        }
        v67 = &CoTaskMemRAII<unsigned char *>::`vftable';
        if ( Src )
        {
          CoTaskMemFree(Src);
          Src = 0;
        }
        v69 = &CoTaskMemRAII<unsigned short *>::`vftable';
        if ( String1 )
        {
          CoTaskMemFree(String1);
          String1 = 0;
        }
        LODWORD(v56) = ++v35;
      }
      while ( v33 >= 0 );
      v28 = v66;
      v29 = v65;
      v30 = a3;
    }
    v39 = 0;
    if ( v33 >= 0 )
    {
      v40 = (const WCHAR *)lpString2;
      if ( v82 > 7 )
        v40 = lpString2[0];
      v41 = (const WCHAR *)lpString1;
      if ( v79 > 7 )
        v41 = lpString1[0];
      if ( CompareStringOrdinal(v41, cchCount1[0], v40, cchCount2, 1) != 2 )
      {
        v42 = lpString1;
        if ( v79 > 7 )
          v42 = (LPCWCH *)lpString1[0];
        v43 = lpString2;
        if ( v82 > 7 )
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
      PrintConfig::LanguageDatabase::SetLanguageState(*(_QWORD *)(v29 + 64), lpString2, 2);
      if ( v39 )
        PrintConfig::LanguageDatabase::SetLanguageState(*(_QWORD *)(v29 + 64), lpString1, 2);
    }
    if ( v33 < 0 )
      goto LABEL_95;
    if ( !v5 )
    {
      v33 = -2147023728;
LABEL_95:
      v44 = lpString2;
      if ( v82 > 7 )
        v44 = (LPCWCH *)lpString2[0];
      Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
        "PrintConfig::CConfigManager::RetrieveLanguageFilesFromDevice",
        L"Failed to retrieve language resources for \"%ws\" (hr: 0x%x)",
        v44,
        (unsigned int)v33);
      goto LABEL_101;
    }
    LOBYTE(v32) = v30;
    v45 = v65;
    PrintConfig::CConfigManager::CommitLanguageResources(v65, (unsigned int)lpString2, v32, (_DWORD)v34, v5);
    if ( v39 )
    {
      LOBYTE(v46) = v30;
      PrintConfig::CConfigManager::CommitLanguageResources(v45, (unsigned int)lpString1, v46, (_DWORD)v34, v5);
    }
    v29 = v45;
LABEL_101:
    v72 = &CoTaskMemRAII<unsigned char *>::`vftable';
    v5 = 0;
    if ( v34 )
    {
      CoTaskMemFree(v34);
      v73 = 0;
    }
    std::wstring::~wstring(lpString1);
    v47 = v83;
    if ( v83 )
    {
      v83 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    }
    std::wstring::~wstring(lpString2);
    v48 = (__int64 **)v28[2];
    if ( *((_BYTE *)v48 + 25) )
    {
      for ( k = (__int64 *)v28[1]; !*((_BYTE *)k + 25) && v28 == (__int64 *)k[2]; k = (__int64 *)k[1] )
        v28 = k;
      v28 = k;
      v66 = k;
    }
    else
    {
      v28 = (__int64 *)v28[2];
      v50 = *v48;
      for ( m = *((_BYTE *)v50 + 25) == 0; ; m = *((_BYTE *)v50 + 25) == 0 )
      {
        v66 = v28;
        if ( !m )
          break;
        v28 = v50;
        v50 = (__int64 *)*v50;
      }
    }
  }
  std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IBidiRequest>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IBidiRequest>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IBidiRequest>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IBidiRequest>>>,0>>((void **)&v71);
  v52 = v59;
  v6 = v64;
  v53 = v74;
  if ( v59 )
  {
    v59 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v52 + 16LL))(v52);
  }
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v53 + 32LL))(v53);
  v54 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v54 + 16LL))(v54);
  }
LABEL_40:
  if ( v6 )
    CoUninitialize();
}

```

## disassembly

```asm
0x1800489a4  push    rbp
0x1800489a6  push    rbx
0x1800489a7  push    rsi
0x1800489a8  push    rdi
0x1800489a9  push    r12
0x1800489ab  push    r13
0x1800489ad  push    r14
0x1800489af  push    r15
0x1800489b1  lea     rbp, [rsp-48h]
0x1800489b6  sub     rsp, 148h
0x1800489bd  mov     [rbp+80h+var_A8], 0FFFFFFFFFFFFFFFEh
0x1800489c5  mov     rax, cs:__security_cookie
0x1800489cc  xor     rax, rsp
0x1800489cf  mov     [rbp+80h+var_50], rax
0x1800489d3  mov     [rsp+180h+var_140], r8b
0x1800489d8  mov     rbx, rdx
0x1800489db  mov     r12, rcx
0x1800489de  mov     [rbp+80h+var_100], rcx
0x1800489e2  xor     r15d, r15d
0x1800489e5  mov     edi, r15d
0x1800489e8  mov     [rsp+180h+var_108], r15d
0x1800489ed  xor     edx, edx; dwCoInit
0x1800489ef  xor     ecx, ecx; pvReserved
0x1800489f1  call    cs:__imp_CoInitializeEx
0x1800489f7  test    eax, eax
0x1800489f9  jns     short loc_180048A08
0x1800489fb  cmp     eax, 80010106h
0x180048a00  jnz     loc_180049181
0x180048a06  jmp     short loc_180048A11
0x180048a08  mov     edi, 1
0x180048a0d  mov     [rsp+180h+var_108], edi
0x180048a11  mov     [rsp+180h+var_130], r15
0x180048a16  lea     rax, [rsp+180h+var_130]
0x180048a1b  mov     [rsp+180h+ppv], rax; ppv
0x180048a20  lea     r9, _GUID_d580dc0e_de39_4649_baa8_bf0b85a03a97; riid
0x180048a27  xor     edx, edx; pUnkOuter
0x180048a29  lea     r8d, [rdx+1]; dwClsContext
0x180048a2d  lea     rcx, _GUID_2a614240_a4c5_4c33_bd87_1bc709331639; rclsid
0x180048a34  call    cs:__imp_CoCreateInstance
0x180048a3a  test    eax, eax
0x180048a3c  js      loc_18004919D
0x180048a42  mov     rcx, [rsp+180h+var_130]
0x180048a47  mov     rax, [rcx]
0x180048a4a  mov     r8d, 2
0x180048a50  mov     rdx, [r12+10h]
0x180048a55  mov     rax, [rax+18h]
0x180048a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a5e  test    eax, eax
0x180048a60  js      loc_1800491B9
0x180048a66  mov     rsi, [rsp+180h+var_130]
0x180048a6b  mov     [rbp+80h+var_B0], rsi
0x180048a6f  mov     [rbp+80h+var_A0], rsi
0x180048a73  mov     [rsp+180h+var_120], r15
0x180048a78  lea     rax, [rsp+180h+var_120]
0x180048a7d  mov     [rsp+180h+ppv], rax; ppv
0x180048a82  lea     r9, _GUID_d752f6c0_94a8_4275_a77d_8f1d1a1121ae; riid
0x180048a89  xor     edx, edx; pUnkOuter
0x180048a8b  lea     r8d, [rdx+1]; dwClsContext
0x180048a8f  lea     rcx, _GUID_fc5b8a24_db05_4a01_8388_22edf6c2bbba; rclsid
0x180048a96  call    cs:__imp_CoCreateInstance
0x180048a9c  test    eax, eax
0x180048a9e  js      loc_1800491D5
0x180048aa4  xorps   xmm0, xmm0
0x180048aa7  movdqu  [rbp+80h+var_D0], xmm0
0x180048aac  mov     ecx, 48h ; 'H'; Size
0x180048ab1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180048ab6  mov     [rax], rax
0x180048ab9  mov     [rax+8], rax
0x180048abd  mov     [rax+10h], rax
0x180048ac1  mov     word ptr [rax+18h], 101h
0x180048ac7  mov     qword ptr [rbp+80h+var_D0], rax
0x180048acb  mov     rbx, [rbx]
0x180048ace  mov     rbx, [rbx]
0x180048ad1  cmp     [rbx+19h], r15b
0x180048ad5  jnz     loc_180048C46
0x180048adb  mov     [rsp+180h+var_138], r15
0x180048ae0  lea     rax, [rsp+180h+var_138]
0x180048ae5  mov     [rsp+180h+ppv], rax; ppv
0x180048aea  lea     r9, _GUID_8f348bd7_4b47_4755_8a9d_0f422df3dc89; riid
0x180048af1  xor     edx, edx; pUnkOuter
0x180048af3  lea     r8d, [rdx+1]; dwClsContext
0x180048af7  lea     rcx, _GUID_b9162a23_45f9_47cc_80f5_fe0fe9b9e1a2; rclsid
0x180048afe  call    cs:__imp_CoCreateInstance
0x180048b04  test    eax, eax
0x180048b06  js      loc_180049165
0x180048b0c  mov     rcx, [rsp+180h+var_138]
0x180048b11  mov     rax, [rcx]
0x180048b14  lea     rdx, aPrinterResourc; "\\Printer.Resources"
0x180048b1b  mov     rax, [rax+18h]
0x180048b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b24  test    eax, eax
0x180048b26  js      loc_180049229
0x180048b2c  lea     r14, [rbx+20h]
0x180048b30  mov     rcx, [rsp+180h+var_138]
0x180048b35  mov     rax, [rcx]
0x180048b38  mov     r10, [rax+20h]
0x180048b3c  mov     eax, [r14+10h]
0x180048b40  lea     r9d, ds:2[rax*2]
0x180048b48  cmp     qword ptr [r14+18h], 7
0x180048b4d  jbe     short loc_180048B54
0x180048b4f  mov     r8, [r14]
0x180048b52  jmp     short loc_180048B57
0x180048b54  mov     r8, r14
0x180048b57  mov     edx, 4
0x180048b5c  mov     rax, r10
0x180048b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b64  test    eax, eax
0x180048b66  js      loc_18004920D
0x180048b6c  mov     rcx, [rsp+180h+var_120]
0x180048b71  mov     rax, [rcx]
0x180048b74  mov     rdx, [rsp+180h+var_138]
0x180048b79  mov     rax, [rax+18h]
0x180048b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b82  test    eax, eax
0x180048b84  js      loc_1800491F1
0x180048b8a  mov     rdx, r14
0x180048b8d  lea     rcx, [rbp+80h+var_D0]
0x180048b91  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIBidiRequest@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIBidiRequest@@@WRL@Microsoft@@@std@@@2@@std@@QEAAAEAV?$ComPtr@UIBidiRequest@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,Microsoft::WRL::ComPtr<IBidiRequest>>::operator[](std::wstring const &)
0x180048b96  mov     r15, rax
0x180048b99  mov     r14, [rsp+180h+var_138]
0x180048b9e  cmp     [rax], r14
0x180048ba1  jz      short loc_180048BDA
0x180048ba3  test    r14, r14
0x180048ba6  jz      short loc_180048BB8
0x180048ba8  mov     rcx, [r14]
0x180048bab  mov     rax, [rcx+8]
0x180048baf  mov     rcx, r14
0x180048bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048bb7  nop
0x180048bb8  mov     rcx, [r15]
0x180048bbb  mov     [r15], r14
0x180048bbe  xor     r15d, r15d
0x180048bc1  test    rcx, rcx
0x180048bc4  jz      short loc_180048BD3
0x180048bc6  mov     rax, [rcx]
0x180048bc9  mov     rax, [rax+10h]
0x180048bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048bd2  nop
0x180048bd3  mov     r14, [rsp+180h+var_138]
0x180048bd8  jmp     short loc_180048BDD
0x180048bda  xor     r15d, r15d
0x180048bdd  test    r14, r14
0x180048be0  jz      short loc_180048BF7
0x180048be2  mov     [rsp+180h+var_138], r15
0x180048be7  mov     rax, [r14]
0x180048bea  mov     rcx, r14
0x180048bed  mov     rax, [rax+10h]
0x180048bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048bf6  nop
0x180048bf7  mov     rcx, [rbx+10h]
0x180048bfb  cmp     [rcx+19h], r15b
0x180048bff  jz      short loc_180048C22
0x180048c01  mov     rax, [rbx+8]
0x180048c05  jmp     short loc_180048C14
0x180048c07  cmp     rbx, [rax+10h]
0x180048c0b  jnz     short loc_180048C1A
0x180048c0d  mov     rbx, rax
0x180048c10  mov     rax, [rax+8]
0x180048c14  cmp     [rax+19h], r15b
0x180048c18  jz      short loc_180048C07
0x180048c1a  mov     rbx, rax
0x180048c1d  jmp     loc_180048AD1
0x180048c22  mov     rbx, rcx
0x180048c25  mov     rcx, [rcx]
0x180048c28  cmp     [rcx+19h], r15b
0x180048c2c  jnz     loc_180048AD1
0x180048c32  mov     rbx, rcx
0x180048c35  mov     rax, [rcx]
0x180048c38  mov     rcx, rax
0x180048c3b  cmp     [rax+19h], r15b
0x180048c3f  jz      short loc_180048C32
0x180048c41  jmp     loc_180048AD1
0x180048c46  mov     rcx, [rsp+180h+var_130]
0x180048c4b  mov     rax, [rcx]
0x180048c4e  mov     r8, [rsp+180h+var_120]
0x180048c53  lea     rdx, aGetwithargumen; "GetWithArgument"
0x180048c5a  mov     rax, [rax+30h]
0x180048c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c63  test    eax, eax
0x180048c65  jns     loc_180048CFE
0x180048c6b  mov     r8d, eax
0x180048c6e  lea     rdx, aDeviceResource; "Device resource bidi request failed (hr"...
0x180048c75  lea     rcx, aPrintconfigCco_1; "PrintConfig::CConfigManager::RetrieveLa"...
0x180048c7c  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180048c81  nop
0x180048c82  lea     rcx, [rbp+80h+var_D0]
0x180048c86  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIBidiRequest@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIBidiRequest@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IBidiRequest>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IBidiRequest>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IBidiRequest>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IBidiRequest>>>,0>>(void)
0x180048c8b  nop
0x180048c8c  mov     rcx, [rsp+180h+var_120]
0x180048c91  test    rcx, rcx
0x180048c94  jz      short loc_180048CA8
0x180048c96  mov     [rsp+180h+var_120], r15
0x180048c9b  mov     rax, [rcx]
0x180048c9e  mov     rax, [rax+10h]
0x180048ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ca7  nop
0x180048ca8  mov     rax, [rsi]
0x180048cab  mov     rcx, rsi
0x180048cae  mov     rax, [rax+20h]
0x180048cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048cb7  nop
0x180048cb8  mov     rcx, [rsp+180h+var_130]
0x180048cbd  test    rcx, rcx
0x180048cc0  jz      short loc_180048CD4
0x180048cc2  mov     [rsp+180h+var_130], r15
0x180048cc7  mov     rax, [rcx]
0x180048cca  mov     rax, [rax+10h]
0x180048cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048cd3  nop
0x180048cd4  test    edi, edi
0x180048cd6  jz      short loc_180048CDE
0x180048cd8  call    cs:__imp_CoUninitialize
0x180048cde  mov     rcx, [rbp+80h+var_50]
0x180048ce2  xor     rcx, rsp; StackCookie
0x180048ce5  call    __security_check_cookie
0x180048cea  add     rsp, 148h
0x180048cf1  pop     r15
0x180048cf3  pop     r14
0x180048cf5  pop     r13
0x180048cf7  pop     r12
0x180048cf9  pop     rdi
0x180048cfa  pop     rsi
0x180048cfb  pop     rbx
0x180048cfc  pop     rbp
0x180048cfd  retn
0x180048cfe  mov     rbx, qword ptr [rbp+80h+var_D0]
0x180048d02  mov     rbx, [rbx]
0x180048d05  mov     [rbp+80h+var_F8], rbx
0x180048d09  mov     rsi, [rbp+80h+var_100]
0x180048d0d  mov     dil, [rsp+180h+var_140]
0x180048d12  lea     r13, ??_7?$CoTaskMemRAII@PEAE@@6B@; const CoTaskMemRAII<uchar *>::`vftable'
0x180048d19  cmp     [rbx+19h], r15b
0x180048d1d  jnz     loc_180049106
0x180048d23  lea     rdx, [rbx+20h]
0x180048d27  lea     rcx, [rbp+80h+lpString2]
0x180048d2b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180048d30  mov     rcx, [rbx+40h]
0x180048d34  mov     [rbp+80h+var_58], rcx
0x180048d38  test    rcx, rcx
0x180048d3b  jz      short loc_180048D4D
0x180048d3d  mov     rax, [rcx]
0x180048d40  mov     rax, [rax+8]
0x180048d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048d49  mov     rcx, [rbp+80h+var_58]
0x180048d4d  mov     [rsp+180h+var_118], 32h ; '2'
0x180048d55  mov     rax, [rcx]
0x180048d58  lea     rdx, [rsp+180h+var_118]
0x180048d5d  mov     rax, [rax+28h]
0x180048d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048d66  mov     r12d, eax
0x180048d69  test    eax, eax
0x180048d6b  js      short loc_180048D87
0x180048d6d  mov     eax, [rsp+180h+var_118]
0x180048d71  test    eax, eax
0x180048d73  jz      short loc_180048D87
0x180048d75  jg      short loc_180048D7C
0x180048d77  mov     r12d, eax
0x180048d7a  jmp     short loc_180048D87
0x180048d7c  movzx   r12d, ax
0x180048d80  or      r12d, 80070000h
0x180048d87  mov     [rsp+180h+var_114], r15d
0x180048d8c  test    r12d, r12d
0x180048d8f  js      short loc_180048DA9
0x180048d91  mov     rcx, [rbp+80h+var_58]
0x180048d95  mov     rax, [rcx]
0x180048d98  lea     rdx, [rsp+180h+var_114]
0x180048d9d  mov     rax, [rax+38h]
0x180048da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048da6  mov     r12d, eax
0x180048da9  xorps   xmm0, xmm0
0x180048dac  movups  xmmword ptr [rbp+80h+lpString1], xmm0
0x180048db0  mov     qword ptr [rbp+80h+cchCount1], r15
0x180048db4  mov     [rbp+80h+var_80], 7
0x180048dbc  mov     word ptr [rbp+80h+lpString1], r15w
0x180048dc1  mov     [rbp+80h+var_C0], r13
0x180048dc5  mov     r13, r15
0x180048dc8  mov     [rbp+80h+var_B8], r15
0x180048dcc  mov     [rsp+180h+var_10C], r15d
0x180048dd1  xor     eax, eax
0x180048dd3  mov     r14d, eax
0x180048dd6  mov     dword ptr [rsp+180h+var_138], eax
0x180048dda  test    r12d, r12d
0x180048ddd  js      loc_180048F56
0x180048de3  xor     esi, esi
0x180048de5  lea     rdi, ??_7?$CoTaskMemRAII@PEAE@@6B@; const CoTaskMemRAII<uchar *>::`vftable'
0x180048dec  lea     rbx, ??_7?$CoTaskMemRAII@PEAG@@6B@; const CoTaskMemRAII<ushort *>::`vftable'
0x180048df3  cmp     r14d, [rsp+180h+var_114]
0x180048df8  jnb     loc_180048F47
0x180048dfe  mov     [rbp+80h+var_E0], rbx
0x180048e02  mov     [rbp+80h+String1], rsi
0x180048e06  mov     [rsp+180h+var_128], esi
0x180048e0a  mov     [rbp+80h+var_F0], rdi
0x180048e0e  mov     [rbp+80h+Src], rsi
0x180048e12  mov     [rsp+180h+var_110], esi
0x180048e16  mov     rcx, [rbp+80h+var_58]
0x180048e1a  mov     rax, [rcx]
0x180048e1d  lea     rdx, [rsp+180h+var_110]
0x180048e22  mov     [rsp+180h+var_158], rdx
0x180048e27  lea     rdx, [rbp+80h+Src]
0x180048e2b  mov     [rsp+180h+ppv], rdx
  ... truncated ...
```
