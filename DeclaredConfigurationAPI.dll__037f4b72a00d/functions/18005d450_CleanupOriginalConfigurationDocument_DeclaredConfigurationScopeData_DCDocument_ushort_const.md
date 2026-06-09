# CleanupOriginalConfigurationDocument(DeclaredConfigurationScopeData *,DCDocument *,ushort const *)

- ea: `0x18005d450`
- end: `0x18005dac3`
- name: `?CleanupOriginalConfigurationDocument@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@PEBG@Z`
- size: `1651`
- prototype: `__int64 __fastcall(unsigned __int16 **, struct DCDocument *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800595dc`

## callees

- `0x18000b9e0`
- `0x18000c8f4`
- `0x1800117dc`
- `0x18001438c`
- `0x180018ac0`
- `0x18001924c`
- `0x18001cce4`
- `0x18001cfa4`
- `0x18001d020`
- `0x18001def8`
- `0x18001df44`
- `0x18001e090`
- `0x1800556cc`
- `0x180058148`
- `0x18005d450`
- `0x1800600bc`
- `0x1800a03e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005d9c8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005d9c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d67e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d67e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18005d8b3`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18005d8b3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005d9e4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005d9e4`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18005d9fa`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18005d9fa`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18005da0b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18005da0b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005d674`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005d674`

## string_xrefs

- `0x18005d7f8`: `%s\Microsoft\DC\HostOS\%s_%s_%s_%s_%s.xml`
- `0x18005d6ff`: `%s\Microsoft\DC\HostOS\%s_%s_%s_%s.xml`
- `0x18005d72a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18005d821`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18005d883`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\declaredconfigurationapi.cpp`
- `0x18005d66d`: `%ProgramData%`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CleanupOriginalConfigurationDocument(
        unsigned __int16 **a1,
        struct DCDocument *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rax
  unsigned __int16 *v7; // rcx
  int v8; // esi
  int v9; // ebx
  unsigned __int16 v10; // ax
  int v11; // ebx
  struct DCDocument *v12; // rcx
  unsigned __int16 v13; // ax
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // rsi
  _QWORD *v17; // rax
  signed int LastError; // eax
  signed int v19; // edi
  struct DCDocument *v20; // rax
  char *v21; // rbx
  char *v22; // rcx
  int v23; // r14d
  int v24; // ebx
  signed int v25; // ebx
  HANDLE FirstFileW; // rsi
  int v27; // ebx
  signed int v28; // ebx
  __int64 v29; // rdi
  __int64 v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rax
  void *p_p_lpFileName; // rcx
  const WCHAR *v34; // rcx
  int v35; // ebx
  signed int v36; // ebx
  int v38; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+20h] [rbp-E0h]
  char v40[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v41; // [rsp+58h] [rbp-A8h] BYREF
  int v42; // [rsp+60h] [rbp-A0h] BYREF
  signed int v43; // [rsp+64h] [rbp-9Ch] BYREF
  LPCWSTR lpFileName; // [rsp+68h] [rbp-98h] BYREF
  __int64 v45; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v46[4]; // [rsp+78h] [rbp-88h] BYREF
  char v47; // [rsp+98h] [rbp-68h]
  LPCWSTR p_lpFileName; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v49; // [rsp+A8h] [rbp-58h] BYREF
  char v50; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v51; // [rsp+B8h] [rbp-48h]
  _BYTE v52[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v53[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v54[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v55[32]; // [rsp+120h] [rbp+20h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+140h] [rbp+40h] BYREF
  WCHAR Dst[264]; // [rsp+390h] [rbp+290h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5E8h] [rbp+4E8h]

  v41 = 0;
  v6 = tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>>(v40);
  wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::operator=(
    &v41,
    v6);
  wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(v40);
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                           &v41,
                           v40)
            + 272LL) = 51;
  tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(v40);
  v7 = *a1;
  v8 = -2128831035;
  v9 = -2128831035;
  if ( *a1 )
  {
    while ( 1 )
    {
      v10 = *v7;
      if ( !*v7 )
        break;
      ++v7;
      v9 = 16777619 * (v10 ^ v9);
    }
  }
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                           &v41,
                           v40)
            + 288LL) = v9;
  tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(v40);
  v11 = *((_DWORD *)a1 + 5);
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                           &v41,
                           v40)
            + 292LL) = v11;
  tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(v40);
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v12 = a2;
  else
    v12 = *(struct DCDocument **)a2;
  if ( v12 )
  {
    while ( 1 )
    {
      v13 = *(_WORD *)v12;
      if ( !*(_WORD *)v12 )
        break;
      v12 = (struct DCDocument *)((char *)v12 + 2);
      v8 = 16777619 * (v13 ^ v8);
    }
  }
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                           &v41,
                           v40)
            + 284LL) = v8;
  tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(v40);
  v14 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                    &v41,
                    v40);
  std::wstring::operator=(*v14 + 304LL, a2);
  tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(v40);
  v15 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                    &v41,
                    v40);
  v16 = (_QWORD *)((char *)a2 + 96);
  std::wstring::operator=(*v15 + 368LL, (char *)a2 + 96);
  tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(v40);
  if ( *((_QWORD *)a2 + 18) )
  {
    v17 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                      &v41,
                      v40);
    std::wstring::operator=(*v17 + 336LL, (char *)a2 + 128);
    tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(v40);
  }
  v43 = 0;
  v42 = 0;
  v46[1] = &v41;
  v46[2] = &v42;
  v46[3] = &v43;
  v47 = 1;
  Dst[0] = 0;
  if ( !ExpandEnvironmentStringsW(L"%ProgramData%", Dst, 0x104u) )
  {
    LastError = GetLastError();
    v19 = LastError;
    if ( LastError > 0 )
      v19 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_48;
  }
  lpFileName = 0;
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v20 = a2;
  else
    v20 = *(struct DCDocument **)a2;
  v21 = (char *)a2 + 32;
  if ( *((_QWORD *)a2 + 7) <= 7u )
    v22 = (char *)a2 + 32;
  else
    v22 = *(char **)v21;
  p_lpFileName = (LPCWSTR)&lpFileName;
  v49 = 0;
  v50 = 1;
  v23 = DCStringCchPrintfAllStrings(&v49, L"%s\\Microsoft\\DC\\HostOS\\%s_%s_%s_%s.xml", 5, Dst, *a1, v22, v20, L"*");
  wil::details::out_param_t<std::unique_ptr<unsigned char [0]>>::~out_param_t<std::unique_ptr<unsigned char [0]>>(&p_lpFileName);
  if ( v23 >= 0 )
  {
    v45 = 0;
    if ( *((_QWORD *)a2 + 15) > 7u )
      v16 = (_QWORD *)*v16;
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(struct DCDocument **)a2;
    if ( *((_QWORD *)v21 + 3) > 7u )
      v21 = *(char **)v21;
    p_lpFileName = (LPCWSTR)&v45;
    v49 = 0;
    v50 = 1;
    v19 = DCStringCchPrintfAllStrings(
            &v49,
            L"%s\\Microsoft\\DC\\HostOS\\%s_%s_%s_%s_%s.xml",
            6,
            Dst,
            *a1,
            v21,
            a2,
            v16,
            a3);
    wil::details::out_param_t<std::unique_ptr<unsigned char [0]>>::~out_param_t<std::unique_ptr<unsigned char [0]>>(&p_lpFileName);
    if ( v19 >= 0 )
    {
      v46[0] = 0;
      p_lpFileName = (LPCWSTR)v46;
      v49 = 0;
      v50 = 1;
      v19 = DCStringCchPrintfAllStrings(&v49, L"%s\\Microsoft\\DC\\HostOS", 1, Dst);
      wil::details::out_param_t<std::unique_ptr<unsigned char [0]>>::~out_param_t<std::unique_ptr<unsigned char [0]>>(&p_lpFileName);
      if ( v19 >= 0 )
      {
        memset_0(&FindFileData, 0, sizeof(FindFileData));
        FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
        if ( FirstFileW == (HANDLE)-1LL )
        {
          std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v46);
          std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v45);
          std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpFileName);
          v27 = v42;
          *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                                   &v41,
                                   v40)
                    + 280LL) = v27;
          tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(v40);
          v28 = v43;
          *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                                   &v41,
                                   v40)
                    + 300LL) = v28;
          tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(v40);
          v19 = 0;
          goto LABEL_49;
        }
        do
        {
          v29 = std::wstring::wstring(v55, FindFileData.cFileName);
          v30 = std::wstring::wstring(v54, L"\\");
          v31 = std::wstring::wstring(v53, v46[0]);
          v32 = std::operator+<unsigned short>(v52, v31, v30);
          std::operator+<unsigned short>(&p_lpFileName, v32, v29);
          std::wstring::_Tidy_deallocate(v52);
          std::wstring::_Tidy_deallocate(v53);
          std::wstring::_Tidy_deallocate(v54);
          std::wstring::_Tidy_deallocate(v55);
          if ( !a3 )
            goto LABEL_41;
          p_p_lpFileName = &p_lpFileName;
          if ( v51 > 7 )
            p_p_lpFileName = (void *)p_lpFileName;
          if ( (unsigned int)_o__wcsicmp(p_p_lpFileName, v45) )
          {
LABEL_41:
            ++v42;
            v34 = (const WCHAR *)&p_lpFileName;
            if ( v51 > 7 )
              v34 = p_lpFileName;
            DeleteFileW(v34);
          }
          std::wstring::_Tidy_deallocate(&p_lpFileName);
        }
        while ( FindNextFileW(FirstFileW, &FindFileData) );
        FindClose(FirstFileW);
        v19 = v43;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5696,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
          (const char *)(unsigned int)v19,
          v39);
      }
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v46);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x568F,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
        (const char *)(unsigned int)v19,
        v39);
    }
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v45);
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpFileName);
LABEL_48:
    v35 = v42;
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                             &v41,
                             v40)
              + 280LL) = v35;
    tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(v40);
    v36 = v43;
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                             &v41,
                             v40)
              + 300LL) = v36;
    tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(v40);
    goto LABEL_49;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5683,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\declaredconfigurationapi.cpp",
    (const char *)(unsigned int)v23,
    v38);
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&lpFileName);
  v24 = v42;
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                           &v41,
                           v40)
            + 280LL) = v24;
  tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(v40);
  v25 = v43;
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(
                           &v41,
                           v40)
            + 300LL) = v25;
  tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(v40);
  v19 = v23;
LABEL_49:
  tip2::tip_test<tip2::details::merged_data<_tip_OsConfigDriftDetectionTipTest,_tip_OsConfigDriftDetectionTipTest>>::complete(&v41);
  wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(&v41);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18005d450  mov     [rsp-8+arg_18], rbx
0x18005d455  push    rbp
0x18005d456  push    rsi
0x18005d457  push    rdi
0x18005d458  push    r12
0x18005d45a  push    r13
0x18005d45c  push    r14
0x18005d45e  push    r15
0x18005d460  lea     rbp, [rsp-4B0h]
0x18005d468  sub     rsp, 5B0h
0x18005d46f  mov     rax, cs:__security_cookie
0x18005d476  xor     rax, rsp
0x18005d479  mov     [rbp+4E0h+var_40], rax
0x18005d480  mov     r12, r8
0x18005d483  mov     rdi, rdx
0x18005d486  mov     r15, rcx
0x18005d489  xor     r13d, r13d
0x18005d48c  mov     [rsp+5E0h+var_588], r13
0x18005d491  lea     rcx, [rsp+5E0h+var_590]
0x18005d496  call    ??$start@V?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>>(void)
0x18005d49b  mov     rdx, rax
0x18005d49e  lea     rcx, [rsp+5E0h+var_588]
0x18005d4a3  call    ??4?$com_ptr_t@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy> &&)
0x18005d4a8  lea     rcx, [rsp+5E0h+var_590]
0x18005d4ad  call    ??1?$com_ptr_t@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>,wil::err_returncode_policy>(void)
0x18005d4b2  lea     rdx, [rsp+5E0h+var_590]
0x18005d4b7  lea     rcx, [rsp+5E0h+var_588]
0x18005d4bc  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x18005d4c1  mov     rcx, [rax]
0x18005d4c4  mov     dword ptr [rcx+110h], 33h ; '3'
0x18005d4ce  lea     rcx, [rsp+5E0h+var_590]
0x18005d4d3  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x18005d4d8  mov     rcx, [r15]
0x18005d4db  mov     esi, 811C9DC5h
0x18005d4e0  mov     ebx, esi
0x18005d4e2  test    rcx, rcx
0x18005d4e5  jz      short loc_18005D500
0x18005d4e7  jmp     short loc_18005D4F8
0x18005d4e9  movzx   eax, ax
0x18005d4ec  lea     rcx, [rcx+2]
0x18005d4f0  xor     ebx, eax
0x18005d4f2  imul    ebx, 1000193h
0x18005d4f8  movzx   eax, word ptr [rcx]
0x18005d4fb  test    ax, ax
0x18005d4fe  jnz     short loc_18005D4E9
0x18005d500  lea     rdx, [rsp+5E0h+var_590]
0x18005d505  lea     rcx, [rsp+5E0h+var_588]
0x18005d50a  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x18005d50f  mov     rcx, [rax]
0x18005d512  mov     [rcx+120h], ebx
0x18005d518  lea     rcx, [rsp+5E0h+var_590]
0x18005d51d  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x18005d522  mov     ebx, [r15+14h]
0x18005d526  lea     rdx, [rsp+5E0h+var_590]
0x18005d52b  lea     rcx, [rsp+5E0h+var_588]
0x18005d530  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x18005d535  mov     rcx, [rax]
0x18005d538  mov     [rcx+124h], ebx
0x18005d53e  lea     rcx, [rsp+5E0h+var_590]
0x18005d543  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x18005d548  cmp     qword ptr [rdi+18h], 7
0x18005d54d  jbe     short loc_18005D554
0x18005d54f  mov     rcx, [rdi]
0x18005d552  jmp     short loc_18005D557
0x18005d554  mov     rcx, rdi
0x18005d557  test    rcx, rcx
0x18005d55a  jz      short loc_18005D575
0x18005d55c  jmp     short loc_18005D56D
0x18005d55e  movzx   eax, ax
0x18005d561  lea     rcx, [rcx+2]
0x18005d565  xor     esi, eax
0x18005d567  imul    esi, 1000193h
0x18005d56d  movzx   eax, word ptr [rcx]
0x18005d570  test    ax, ax
0x18005d573  jnz     short loc_18005D55E
0x18005d575  lea     rdx, [rsp+5E0h+var_590]
0x18005d57a  lea     rcx, [rsp+5E0h+var_588]
0x18005d57f  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x18005d584  mov     rcx, [rax]
0x18005d587  mov     [rcx+11Ch], esi
0x18005d58d  lea     rcx, [rsp+5E0h+var_590]
0x18005d592  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x18005d597  lea     rdx, [rsp+5E0h+var_590]
0x18005d59c  lea     rcx, [rsp+5E0h+var_588]
0x18005d5a1  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x18005d5a6  nop
0x18005d5a7  mov     rcx, [rax]
0x18005d5aa  add     rcx, 130h
0x18005d5b1  mov     rdx, rdi
0x18005d5b4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18005d5b9  nop
0x18005d5ba  lea     rcx, [rsp+5E0h+var_590]
0x18005d5bf  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x18005d5c4  lea     rdx, [rsp+5E0h+var_590]
0x18005d5c9  lea     rcx, [rsp+5E0h+var_588]
0x18005d5ce  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x18005d5d3  nop
0x18005d5d4  lea     rsi, [rdi+60h]
0x18005d5d8  mov     rcx, [rax]
0x18005d5db  add     rcx, 170h
0x18005d5e2  mov     rdx, rsi
0x18005d5e5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18005d5ea  nop
0x18005d5eb  lea     rcx, [rsp+5E0h+var_590]
0x18005d5f0  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x18005d5f5  lea     rbx, [rdi+80h]
0x18005d5fc  cmp     [rbx+10h], r13
0x18005d600  jz      short loc_18005D62F
0x18005d602  lea     rdx, [rsp+5E0h+var_590]
0x18005d607  lea     rcx, [rsp+5E0h+var_588]
0x18005d60c  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x18005d611  nop
0x18005d612  mov     rcx, [rax]
0x18005d615  add     rcx, 150h
0x18005d61c  mov     rdx, rbx
0x18005d61f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18005d624  nop
0x18005d625  lea     rcx, [rsp+5E0h+var_590]
0x18005d62a  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x18005d62f  mov     [rsp+5E0h+var_57C], r13d
0x18005d634  mov     [rsp+5E0h+var_580], r13d
0x18005d639  lea     rax, [rsp+5E0h+var_588]
0x18005d63e  mov     [rbp+4E0h+var_560], rax
0x18005d642  lea     rax, [rsp+5E0h+var_580]
0x18005d647  mov     [rbp+4E0h+var_558], rax
0x18005d64b  lea     rax, [rsp+5E0h+var_57C]
0x18005d650  mov     [rbp+4E0h+var_550], rax
0x18005d654  mov     [rbp+4E0h+var_548], 1
0x18005d658  mov     [rbp+4E0h+Dst], r13w
0x18005d660  mov     r8d, 104h; nSize
0x18005d666  lea     rdx, [rbp+4E0h+Dst]; lpDst
0x18005d66d  lea     rcx, Src; "%ProgramData%"
0x18005d674  call    cs:__imp_ExpandEnvironmentStringsW
0x18005d67a  test    eax, eax
0x18005d67c  jnz     short loc_18005D69C
0x18005d67e  call    cs:__imp_GetLastError
0x18005d684  mov     edi, eax
0x18005d686  test    eax, eax
0x18005d688  jle     loc_18005DA36
0x18005d68e  movzx   edi, ax
0x18005d691  or      edi, 80070000h
0x18005d697  jmp     loc_18005DA36
0x18005d69c  mov     [rsp+5E0h+lpFileName], r13
0x18005d6a1  cmp     qword ptr [rdi+18h], 7
0x18005d6a6  jbe     short loc_18005D6AD
0x18005d6a8  mov     rax, [rdi]
0x18005d6ab  jmp     short loc_18005D6B0
0x18005d6ad  mov     rax, rdi
0x18005d6b0  lea     rbx, [rdi+20h]
0x18005d6b4  cmp     qword ptr [rbx+18h], 7
0x18005d6b9  jbe     short loc_18005D6C0
0x18005d6bb  mov     rcx, [rbx]
0x18005d6be  jmp     short loc_18005D6C3
0x18005d6c0  mov     rcx, rbx
0x18005d6c3  lea     rdx, [rsp+5E0h+lpFileName]
0x18005d6c8  mov     [rbp+4E0h+var_540], rdx
0x18005d6cc  mov     [rbp+4E0h+var_538], r13
0x18005d6d0  mov     [rbp+4E0h+var_530], 1
0x18005d6d4  lea     rdx, asc_180143B14; "*"
0x18005d6db  mov     [rsp+5E0h+var_5A8], rdx
0x18005d6e0  mov     [rsp+5E0h+var_5B0], rax
0x18005d6e5  mov     [rsp+5E0h+var_5B8], rcx
0x18005d6ea  mov     rax, [r15]
0x18005d6ed  mov     qword ptr [rsp+5E0h+var_5C0], rax; int
0x18005d6f2  lea     r9, [rbp+4E0h+Dst]
0x18005d6f9  mov     r8d, 5
0x18005d6ff  lea     rdx, aSMicrosoftDcHo; "%s\\Microsoft\\DC\\HostOS\\%s_%s_%s_%s."...
0x18005d706  lea     rcx, [rbp+4E0h+var_538]
0x18005d70a  call    DCStringCchPrintfAllStrings
0x18005d70f  mov     r14d, eax
0x18005d712  lea     rcx, [rbp+4E0h+var_540]
0x18005d716  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<uchar [0]>>::~out_param_t<std::unique_ptr<uchar [0]>>(void)
0x18005d71b  test    r14d, r14d
0x18005d71e  jns     short loc_18005D79B
0x18005d720  mov     rcx, [rbp+4E8h]; this
0x18005d727  mov     r9d, r14d; char *
0x18005d72a  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18005d731  mov     edx, 5683h; void *
0x18005d736  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d73b  nop
0x18005d73c  lea     rcx, [rsp+5E0h+lpFileName]
0x18005d741  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18005d746  nop
0x18005d747  mov     ebx, [rsp+5E0h+var_580]
0x18005d74b  lea     rdx, [rsp+5E0h+var_590]
0x18005d750  lea     rcx, [rsp+5E0h+var_588]
0x18005d755  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x18005d75a  mov     rcx, [rax]
0x18005d75d  mov     [rcx+118h], ebx
0x18005d763  lea     rcx, [rsp+5E0h+var_590]
0x18005d768  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x18005d76d  mov     ebx, [rsp+5E0h+var_57C]
0x18005d771  lea     rdx, [rsp+5E0h+var_590]
0x18005d776  lea     rcx, [rsp+5E0h+var_588]
0x18005d77b  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x18005d780  mov     rcx, [rax]
0x18005d783  mov     [rcx+12Ch], ebx
0x18005d789  lea     rcx, [rsp+5E0h+var_590]
0x18005d78e  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x18005d793  mov     edi, r14d
0x18005d796  jmp     loc_18005DA82
0x18005d79b  mov     [rsp+5E0h+var_570], r13
0x18005d7a0  cmp     qword ptr [rsi+18h], 7
0x18005d7a5  jbe     short loc_18005D7AA
0x18005d7a7  mov     rsi, [rsi]
0x18005d7aa  cmp     qword ptr [rdi+18h], 7
0x18005d7af  jbe     short loc_18005D7B4
0x18005d7b1  mov     rdi, [rdi]
0x18005d7b4  cmp     qword ptr [rbx+18h], 7
0x18005d7b9  jbe     short loc_18005D7BE
0x18005d7bb  mov     rbx, [rbx]
0x18005d7be  lea     rax, [rsp+5E0h+var_570]
0x18005d7c3  mov     [rbp+4E0h+var_540], rax
0x18005d7c7  mov     [rbp+4E0h+var_538], r13
0x18005d7cb  mov     [rbp+4E0h+var_530], 1
0x18005d7cf  mov     [rsp+5E0h+var_5A0], r12
0x18005d7d4  mov     [rsp+5E0h+var_5A8], rsi
0x18005d7d9  mov     [rsp+5E0h+var_5B0], rdi
0x18005d7de  mov     [rsp+5E0h+var_5B8], rbx
0x18005d7e3  mov     rax, [r15]
0x18005d7e6  mov     qword ptr [rsp+5E0h+var_5C0], rax; int
0x18005d7eb  lea     r9, [rbp+4E0h+Dst]
0x18005d7f2  mov     r8d, 6
0x18005d7f8  lea     rdx, aSMicrosoftDcHo_0; "%s\\Microsoft\\DC\\HostOS\\%s_%s_%s_%s_"...
0x18005d7ff  lea     rcx, [rbp+4E0h+var_538]
0x18005d803  call    DCStringCchPrintfAllStrings
0x18005d808  mov     edi, eax
0x18005d80a  lea     rcx, [rbp+4E0h+var_540]
0x18005d80e  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<uchar [0]>>::~out_param_t<std::unique_ptr<uchar [0]>>(void)
0x18005d813  test    edi, edi
0x18005d815  jns     short loc_18005D837
0x18005d817  mov     rcx, [rbp+4E8h]; this
0x18005d81e  mov     r9d, edi; char *
0x18005d821  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18005d828  mov     edx, 568Fh; void *
0x18005d82d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d832  jmp     loc_18005DA20
0x18005d837  mov     [rsp+5E0h+var_568], r13
0x18005d83c  lea     rax, [rsp+5E0h+var_568]
0x18005d841  mov     [rbp+4E0h+var_540], rax
0x18005d845  mov     [rbp+4E0h+var_538], r13
0x18005d849  mov     [rbp+4E0h+var_530], 1
0x18005d84d  lea     r9, [rbp+4E0h+Dst]
0x18005d854  mov     r8d, 1
0x18005d85a  lea     rdx, aSMicrosoftDcHo_1; "%s\\Microsoft\\DC\\HostOS"
0x18005d861  lea     rcx, [rbp+4E0h+var_538]
0x18005d865  call    DCStringCchPrintfAllStrings
0x18005d86a  mov     edi, eax
0x18005d86c  lea     rcx, [rbp+4E0h+var_540]
0x18005d870  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<uchar [0]>>::~out_param_t<std::unique_ptr<uchar [0]>>(void)
0x18005d875  test    edi, edi
0x18005d877  jns     short loc_18005D899
0x18005d879  mov     rcx, [rbp+4E8h]; this
0x18005d880  mov     r9d, edi; char *
0x18005d883  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x18005d88a  mov     edx, 5696h; void *
0x18005d88f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d894  jmp     loc_18005DA15
0x18005d899  xor     edx, edx; Val
0x18005d89b  mov     r8d, 250h; Size
0x18005d8a1  lea     rcx, [rbp+4E0h+FindFileData]; void *
0x18005d8a5  call    memset_0
0x18005d8aa  lea     rdx, [rbp+4E0h+FindFileData]; lpFindFileData
0x18005d8ae  mov     rcx, [rsp+5E0h+lpFileName]; lpFileName
0x18005d8b3  call    cs:__imp_FindFirstFileW
0x18005d8b9  mov     rsi, rax
0x18005d8bc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005d8c0  jnz     short loc_18005D937
0x18005d8c2  lea     rcx, [rsp+5E0h+var_568]
0x18005d8c7  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18005d8cc  nop
0x18005d8cd  lea     rcx, [rsp+5E0h+var_570]
0x18005d8d2  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18005d8d7  nop
0x18005d8d8  lea     rcx, [rsp+5E0h+lpFileName]
0x18005d8dd  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18005d8e2  nop
0x18005d8e3  mov     ebx, [rsp+5E0h+var_580]
0x18005d8e7  lea     rdx, [rsp+5E0h+var_590]
0x18005d8ec  lea     rcx, [rsp+5E0h+var_588]
0x18005d8f1  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x18005d8f6  mov     rcx, [rax]
0x18005d8f9  mov     [rcx+118h], ebx
0x18005d8ff  lea     rcx, [rsp+5E0h+var_590]
0x18005d904  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x18005d909  mov     ebx, [rsp+5E0h+var_57C]
0x18005d90d  lea     rdx, [rsp+5E0h+var_590]
0x18005d912  lea     rcx, [rsp+5E0h+var_588]
0x18005d917  call    ??C?$tip_test@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::operator->(void)
0x18005d91c  mov     rcx, [rax]
0x18005d91f  mov     [rcx+12Ch], ebx
0x18005d925  lea     rcx, [rsp+5E0h+var_590]
0x18005d92a  call    ??1?$test_data_control@V?$merged_data@U_tip_OsConfigApiTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>::~test_data_control<tip2::details::merged_data<_tip_OsConfigApiTipTest,_tip_OsConfigApiTipTest>>(void)
0x18005d92f  mov     edi, r13d
0x18005d932  jmp     loc_18005DA82
0x18005d937  lea     rdx, [rbp+4E0h+FindFileData.cFileName]
0x18005d93b  lea     rcx, [rbp+4E0h+var_4C0]
0x18005d93f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005d944  mov     rdi, rax
0x18005d947  lea     rdx, StringValue; "\\"
  ... truncated ...
```
