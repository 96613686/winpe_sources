# SetVariantValueToSet(DeclaredConfigurationScopeData *,DCDocument *,DCCSP *,DCURI *,ushort const *,tagVARIANT *)

- ea: `0x1800c4fe4`
- end: `0x1800c57ee`
- name: `?SetVariantValueToSet@@YAJPEAUDeclaredConfigurationScopeData@@PEAVDCDocument@@PEAVDCCSP@@PEAVDCURI@@PEBGPEAUtagVARIANT@@@Z`
- size: `2058`
- prototype: `__int64 __usercall@<rax>(struct DeclaredConfigurationScopeData *@<rcx>, struct DCDocument *@<rdx>, struct DCCSP *@<r8>, struct DCURI *@<r9>, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800ae150`
- `0x1800bd94c`
- `0x1800e4848`
- `0x1800e82c0`

## callees

- `0x1800117bc`
- `0x1800117dc`
- `0x180018b30`
- `0x18001ce5c`
- `0x18001d0b0`
- `0x18004b920`
- `0x180058630`
- `0x18005eeb8`
- `0x18005feac`
- `0x1800a1878`
- `0x1800c4fe4`
- `0x1801006c8`
- `0x180102a34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c527e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c52cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c54f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c555d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c572e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c577c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c527e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c52cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c54f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c555d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c572e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c577c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c520f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c546d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c56bf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c520f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c546d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800c56bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c51ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c5270`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c52be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c545d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c54e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c554f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c56af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c5720`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c576e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c51ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c5270`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c52be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c545d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c54e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c554f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c56af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c5720`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c576e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800c524f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800c54ba`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800c56ff`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800c524f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800c54ba`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800c56ff`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c51bd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c5424`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c5672`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c51bd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c5424`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800c5672`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c52b4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c52ef`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c5764`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c579f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c52b4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c52ef`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c5764`
- `OLEAUT32!__imp_SysAllocString` at `0x1800c579f`

## string_xrefs

- `0x1800c514b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800c51da`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800c5229`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800c525d`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800c529a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800c5441`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800c5488`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800c54c8`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800c5513`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800c568f`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800c56d9`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800c570d`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`
- `0x1800c574a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\providercsp.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SetVariantValueToSet(
        struct DeclaredConfigurationScopeData *a1,
        struct DCDocument *a2,
        struct DCCSP *a3,
        struct DCURI *a4,
        const unsigned __int16 *a5,
        struct tagVARIANT *a6)
{
  struct DCDocument *v7; // rbx
  int LastError; // ebx
  __int64 v10; // rdx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // eax
  unsigned __int64 v16; // r9
  struct tagVARIANT *v17; // rcx
  struct tagVARIANT *v18; // rcx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  const unsigned __int16 *v23; // r8
  DWORD v24; // ebx
  const WCHAR *v25; // rcx
  HANDLE v26; // rax
  const char *v27; // r9
  HANDLE *p_nNumberOfBytesToRead; // rcx
  HANDLE v29; // rax
  void *v30; // rax
  void *v31; // rdi
  const char *v32; // r9
  HANDLE v33; // rax
  struct tagVARIANT *v34; // rbx
  HANDLE v35; // rax
  const OLECHAR *v36; // rcx
  struct tagVARIANT *v37; // rcx
  const unsigned __int16 *v38; // r8
  unsigned __int16 v39; // dx
  DWORD v40; // ebx
  const WCHAR *v41; // rcx
  HANDLE FileW; // rax
  const char *v43; // r9
  HANDLE ProcessHeap; // rax
  void *v45; // rax
  unsigned __int16 v46; // dx
  const char *v47; // r9
  void *v48; // rdi
  HANDLE v49; // rax
  __int64 v50; // r9
  __int64 v51; // rdx
  struct tagVARIANT *v52; // rsi
  int v53; // eax
  void *v54; // rbx
  HANDLE v55; // rax
  char *v56; // rdi
  int v57; // eax
  const unsigned __int16 *v58; // r8
  DWORD v59; // ebx
  const WCHAR *v60; // rcx
  HANDLE v61; // rax
  const char *v62; // r9
  HANDLE v63; // rax
  void *v64; // rax
  void *v65; // rdi
  const char *v66; // r9
  HANDLE v67; // rax
  HANDLE v68; // rax
  const OLECHAR *v69; // rcx
  int dwCreationDisposition; // [rsp+20h] [rbp-50h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-50h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-50h]
  int dwCreationDispositionc; // [rsp+20h] [rbp-50h]
  int dwCreationDispositiond; // [rsp+20h] [rbp-50h]
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-30h] BYREF
  HKEY v77; // [rsp+48h] [rbp-28h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-20h] BYREF
  void *p_lpMem; // [rsp+58h] [rbp-18h] BYREF
  HKEY v80; // [rsp+60h] [rbp-10h] BYREF
  char v81; // [rsp+68h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  __int64 nNumberOfBytesToRead; // [rsp+B0h] [rbp+40h] BYREF
  HANDLE hFile; // [rsp+B8h] [rbp+48h] BYREF

  HIDWORD(nNumberOfBytesToRead) = HIDWORD(a3);
  v7 = a2;
  LODWORD(nNumberOfBytesToRead) = 0;
  v77 = 0;
  if ( *((_DWORD *)a4 + 46) != 1 )
  {
    LastError = -2147418113;
    v10 = 4008;
LABEL_25:
    v16 = (unsigned int)LastError;
    goto LABEL_26;
  }
  v11 = *((_DWORD *)a4 + 41);
  if ( v11 > 7 )
  {
    v19 = v11 - 8;
    if ( !v19 )
    {
      a6->vt = 0;
      goto LABEL_115;
    }
    v20 = v19 - 1;
    if ( !v20 )
    {
LABEL_115:
      LastError = 0;
      goto LABEL_116;
    }
    v21 = v20 - 2;
    if ( !v21 )
      goto LABEL_48;
    v22 = v21 - 1;
    if ( !v22 )
    {
LABEL_50:
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
      {
LABEL_51:
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
          goto LABEL_52;
        p_lpMem = &v77;
        v80 = 0;
        v81 = 1;
        v38 = (const unsigned __int16 *)((char *)v7 + 96);
        if ( *((_QWORD *)v7 + 15) > 7u )
          v38 = *(const unsigned __int16 **)v38;
        if ( *((_QWORD *)v7 + 3) > 7u )
          v7 = *(struct DCDocument **)v7;
        LastError = DCGetEnrollmentIdSidStateDocIdVersionKey(a1, (const unsigned __int16 *)v7, v38, &v80, 0);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpMem);
        if ( LastError < 0 )
        {
          v10 = 4204;
          goto LABEL_25;
        }
        if ( DCCDNUtil_GetRegistryDWORD(v77, a5, L"valueSize", (unsigned int *)&nNumberOfBytesToRead) >= 0
          && (v40 = nNumberOfBytesToRead) != 0 )
        {
          nNumberOfBytesToRead = -1;
          v41 = (const WCHAR *)((char *)a4 + 32);
          if ( *((_QWORD *)a4 + 7) > 7u )
            v41 = *(const WCHAR **)v41;
          FileW = CreateFileW(v41, 0x80000000, 0, 0, 3u, 0x80u, 0);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &nNumberOfBytesToRead,
            FileW);
          if ( nNumberOfBytesToRead == -1 )
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x107E,
                          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
                          v43);
            goto LABEL_99;
          }
          LODWORD(hFile) = 0;
          ProcessHeap = GetProcessHeap();
          v45 = HeapAlloc(ProcessHeap, 8u, v40 + 2);
          lpMem = v45;
          if ( !v45 )
          {
            LastError = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1085,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
              (const char *)0x8007000ELL,
              dwCreationDispositionb);
LABEL_99:
            p_nNumberOfBytesToRead = (HANDLE *)&nNumberOfBytesToRead;
            goto LABEL_34;
          }
          p_lpMem = &lpMem;
          LOBYTE(v80) = 1;
          if ( !ReadFile((HANDLE)nNumberOfBytesToRead, v45, v40, (LPDWORD)&hFile, 0) )
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x1094,
                          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
                          v47);
            goto LABEL_70;
          }
          if ( (_DWORD)hFile != v40 )
          {
            LastError = -2147418113;
            v50 = 2147549183LL;
            v51 = 4248;
LABEL_74:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v51,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
              (const char *)v50,
              dwCreationDispositionc);
LABEL_70:
            v48 = lpMem;
            if ( lpMem )
            {
              v49 = GetProcessHeap();
              HeapFree(v49, 0, v48);
            }
            goto LABEL_99;
          }
          v52 = a6;
          v53 = MultiStringToSafeArray((OLECHAR *)lpMem, v46, &a6->parray);
          LastError = v53;
          if ( v53 < 0 )
          {
            v50 = (unsigned int)v53;
            v51 = 4251;
            goto LABEL_74;
          }
          v54 = lpMem;
          if ( lpMem )
          {
            v55 = GetProcessHeap();
            HeapFree(v55, 0, v54);
          }
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&nNumberOfBytesToRead);
        }
        else
        {
          v56 = (char *)a4 + 32;
          if ( *((_QWORD *)v56 + 2) < 2u )
            std::wstring::append(v56, 2);
          if ( *((_QWORD *)v56 + 3) > 7u )
            v56 = *(char **)v56;
          v52 = a6;
          v57 = MultiStringToSafeArray((OLECHAR *)v56, v39, &a6->parray);
          LastError = v57;
          if ( v57 < 0 )
          {
            v16 = (unsigned int)v57;
            v10 = 4259;
            goto LABEL_26;
          }
        }
        v52->vt = 8200;
        goto LABEL_115;
      }
      p_lpMem = &v77;
      v80 = 0;
      v81 = 1;
      v58 = (const unsigned __int16 *)((char *)v7 + 96);
      if ( *((_QWORD *)v7 + 15) > 7u )
        v58 = *(const unsigned __int16 **)v58;
      if ( *((_QWORD *)v7 + 3) > 7u )
        v7 = *(struct DCDocument **)v7;
      LastError = DCGetEnrollmentIdSidStateDocIdVersionKey(a1, (const unsigned __int16 *)v7, v58, &v80, 0);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpMem);
      if ( LastError < 0 )
      {
        v10 = 4129;
        goto LABEL_25;
      }
      if ( DCCDNUtil_GetRegistryDWORD(v77, a5, L"valueSize", (unsigned int *)&nNumberOfBytesToRead) >= 0
        && (v59 = nNumberOfBytesToRead) != 0 )
      {
        nNumberOfBytesToRead = -1;
        v60 = (const WCHAR *)((char *)a4 + 32);
        if ( *((_QWORD *)a4 + 7) > 7u )
          v60 = *(const WCHAR **)v60;
        v61 = CreateFileW(v60, 0x80000000, 0, 0, 3u, 0x80u, 0);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &nNumberOfBytesToRead,
          v61);
        if ( nNumberOfBytesToRead == -1 )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x1033,
                        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
                        v62);
          goto LABEL_99;
        }
        NumberOfBytesRead = 0;
        v63 = GetProcessHeap();
        v64 = HeapAlloc(v63, 8u, v59 + 2);
        v65 = v64;
        if ( !v64 )
        {
          LastError = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x103A,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
            (const char *)0x8007000ELL,
            dwCreationDispositiond);
          goto LABEL_99;
        }
        if ( !ReadFile((HANDLE)nNumberOfBytesToRead, v64, v59, &NumberOfBytesRead, 0) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x1049,
                        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
                        v66);
LABEL_104:
          v67 = GetProcessHeap();
          HeapFree(v67, 0, v65);
          goto LABEL_99;
        }
        if ( NumberOfBytesRead != v59 )
        {
          LastError = -2147418113;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x104D,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
            (const char *)0x8000FFFFLL,
            dwCreationDisposition);
          goto LABEL_104;
        }
        v34 = a6;
        v34->llVal = (LONGLONG)SysAllocString((const OLECHAR *)v65);
        v68 = GetProcessHeap();
        HeapFree(v68, 0, v65);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&nNumberOfBytesToRead);
      }
      else
      {
        v69 = (const OLECHAR *)((char *)a4 + 32);
        if ( *((_QWORD *)a4 + 7) > 7u )
          v69 = *(const OLECHAR **)v69;
        v34 = a6;
        v34->llVal = (LONGLONG)SysAllocString(v69);
      }
      if ( !v34->llVal )
      {
        LastError = -2147024882;
        v10 = 4190;
        goto LABEL_25;
      }
LABEL_113:
      v34->vt = 8;
      goto LABEL_115;
    }
    if ( v22 != 1 )
      goto LABEL_52;
LABEL_19:
    p_lpMem = &v77;
    v80 = 0;
    v81 = 1;
    v23 = (const unsigned __int16 *)((char *)a2 + 96);
    if ( *((_QWORD *)a2 + 15) > 7u )
      v23 = *(const unsigned __int16 **)v23;
    if ( *((_QWORD *)a2 + 3) > 7u )
      v7 = *(struct DCDocument **)a2;
    LastError = DCGetEnrollmentIdSidStateDocIdVersionKey(a1, (const unsigned __int16 *)v7, v23, &v80, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpMem);
    if ( LastError < 0 )
    {
      v10 = 4026;
      goto LABEL_25;
    }
    if ( DCCDNUtil_GetRegistryDWORD(v77, a5, L"valueSize", (unsigned int *)&nNumberOfBytesToRead) >= 0
      && (v24 = nNumberOfBytesToRead) != 0 )
    {
      hFile = (HANDLE)-1LL;
      v25 = (const WCHAR *)((char *)a4 + 32);
      if ( *((_QWORD *)a4 + 7) > 7u )
        v25 = *(const WCHAR **)v25;
      v26 = CreateFileW(v25, 0x80000000, 0, 0, 3u, 0x80u, 0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hFile,
        v26);
      if ( hFile == (HANDLE)-1LL )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xFCC,
                      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
                      v27);
LABEL_33:
        p_nNumberOfBytesToRead = &hFile;
LABEL_34:
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(p_nNumberOfBytesToRead);
        goto LABEL_116;
      }
      LODWORD(nNumberOfBytesToRead) = 0;
      v29 = GetProcessHeap();
      v30 = HeapAlloc(v29, 8u, v24 + 2);
      v31 = v30;
      if ( !v30 )
      {
        LastError = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFD3,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
          (const char *)0x8007000ELL,
          dwCreationDispositiona);
        goto LABEL_33;
      }
      if ( !ReadFile(hFile, v30, v24, (LPDWORD)&nNumberOfBytesToRead, 0) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xFE2,
                      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
                      v32);
LABEL_39:
        v33 = GetProcessHeap();
        HeapFree(v33, 0, v31);
        goto LABEL_33;
      }
      if ( (_DWORD)nNumberOfBytesToRead != v24 )
      {
        LastError = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFE6,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
          (const char *)0x8000FFFFLL,
          dwCreationDisposition);
        goto LABEL_39;
      }
      v34 = a6;
      v34->llVal = (LONGLONG)SysAllocString((const OLECHAR *)v31);
      v35 = GetProcessHeap();
      HeapFree(v35, 0, v31);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
    }
    else
    {
      v36 = (const OLECHAR *)((char *)a4 + 32);
      if ( *((_QWORD *)a4 + 7) > 7u )
        v36 = *(const OLECHAR **)v36;
      v34 = a6;
      v34->llVal = (LONGLONG)SysAllocString(v36);
    }
    if ( !v34->llVal )
    {
      LastError = -2147024882;
      v10 = 4087;
      goto LABEL_25;
    }
    goto LABEL_113;
  }
  if ( v11 == 7 )
    goto LABEL_51;
  if ( !v11 )
  {
    v18 = a6;
    a6->lVal = *((_DWORD *)a4 + 98);
    v18->vt = 3;
    goto LABEL_115;
  }
  v12 = v11 - 1;
  if ( !v12 )
    goto LABEL_19;
  v13 = v12 - 1;
  if ( !v13 )
  {
LABEL_48:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
    {
      v37 = a6;
      a6->llVal = *((_QWORD *)a4 + 49);
      v37->vt = 20;
      goto LABEL_115;
    }
    goto LABEL_50;
  }
  v14 = v13 - 3;
  if ( !v14 )
  {
    v17 = a6;
    a6->lVal = *((_DWORD *)a4 + 98);
    v17->vt = 11;
    goto LABEL_115;
  }
  if ( v14 != 1 )
  {
LABEL_52:
    LastError = -2147418113;
    v10 = 4271;
    goto LABEL_25;
  }
  v15 = DCSetBinaryToVariant(*((unsigned __int8 **)a4 + 49), *((unsigned int *)a4 + 100), a6);
  LastError = v15;
  if ( v15 >= 0 )
    goto LABEL_115;
  v16 = (unsigned int)v15;
  v10 = 4097;
LABEL_26:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\providercsp.cpp",
    (const char *)v16,
    dwCreationDisposition);
LABEL_116:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v77);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800c4fe4  mov     [rsp-28h+arg_0], rbx
0x1800c4fe9  mov     [rsp-28h+nNumberOfBytesToRead], r8
0x1800c4fee  push    rbp
0x1800c4fef  push    rsi
0x1800c4ff0  push    rdi
0x1800c4ff1  push    r13
0x1800c4ff3  push    r14
0x1800c4ff5  mov     rbp, rsp
0x1800c4ff8  sub     rsp, 70h
0x1800c4ffc  mov     rdi, r9
0x1800c4fff  mov     rbx, rdx
0x1800c5002  mov     rsi, rcx
0x1800c5005  xor     r14d, r14d
0x1800c5008  mov     dword ptr [rbp+nNumberOfBytesToRead], r14d
0x1800c500c  mov     [rbp+var_28], r14
0x1800c5010  cmp     dword ptr [r9+0B8h], 1
0x1800c5018  jz      short loc_1800C5029
0x1800c501a  mov     ebx, 8000FFFFh
0x1800c501f  mov     edx, 0FA8h
0x1800c5024  jmp     loc_1800C5144
0x1800c5029  mov     ecx, [r9+0A4h]
0x1800c5030  mov     r13d, 8
0x1800c5036  cmp     ecx, 7
0x1800c5039  jg      loc_1800C50C7
0x1800c503f  jz      loc_1800C534F
0x1800c5045  test    ecx, ecx
0x1800c5047  jz      short loc_1800C50AF
0x1800c5049  sub     ecx, 1
0x1800c504c  jz      loc_1800C50F4
0x1800c5052  sub     ecx, 1
0x1800c5055  jz      loc_1800C5312
0x1800c505b  sub     ecx, 3
0x1800c505e  jz      short loc_1800C5097
0x1800c5060  cmp     ecx, 1
0x1800c5063  jnz     loc_1800C535F
0x1800c5069  mov     r8, [rbp+arg_28]; struct tagVARIANT *
0x1800c506d  mov     edx, [r9+190h]; Size
0x1800c5074  mov     rcx, [r9+188h]; Src
0x1800c507b  call    ?DCSetBinaryToVariant@@YAJPEAEKPEAUtagVARIANT@@@Z; DCSetBinaryToVariant(uchar *,ulong,tagVARIANT *)
0x1800c5080  mov     ebx, eax
0x1800c5082  test    eax, eax
0x1800c5084  jns     loc_1800C57CC
0x1800c508a  mov     r9d, eax
0x1800c508d  mov     edx, 1001h
0x1800c5092  jmp     loc_1800C5147
0x1800c5097  mov     eax, [r9+188h]
0x1800c509e  mov     rcx, [rbp+arg_28]
0x1800c50a2  mov     [rcx+8], eax
0x1800c50a5  mov     word ptr [rcx], 0Bh
0x1800c50aa  jmp     loc_1800C57CC
0x1800c50af  mov     eax, [r9+188h]
0x1800c50b6  mov     rcx, [rbp+arg_28]
0x1800c50ba  mov     [rcx+8], eax
0x1800c50bd  mov     word ptr [rcx], 3
0x1800c50c2  jmp     loc_1800C57CC
0x1800c50c7  sub     ecx, r13d
0x1800c50ca  jz      loc_1800C57C4
0x1800c50d0  sub     ecx, 1
0x1800c50d3  jz      loc_1800C57CC
0x1800c50d9  sub     ecx, 2
0x1800c50dc  jz      loc_1800C5312
0x1800c50e2  sub     ecx, 1
0x1800c50e5  jz      loc_1800C533B
0x1800c50eb  cmp     ecx, 1
0x1800c50ee  jnz     loc_1800C535F
0x1800c50f4  lea     rax, [rbp+var_28]
0x1800c50f8  mov     [rbp+var_18], rax
0x1800c50fc  mov     [rbp+var_10], r14
0x1800c5100  mov     [rbp+var_8], 1
0x1800c5104  lea     r8, [rdx+60h]
0x1800c5108  cmp     qword ptr [r8+18h], 7
0x1800c510d  jbe     short loc_1800C5112
0x1800c510f  mov     r8, [r8]; unsigned __int16 *
0x1800c5112  cmp     qword ptr [rdx+18h], 7
0x1800c5117  jbe     short loc_1800C511C
0x1800c5119  mov     rbx, [rdx]
0x1800c511c  mov     [rsp+70h+dwCreationDisposition], r14d; int
0x1800c5121  lea     r9, [rbp+var_10]; HKEY *
0x1800c5125  mov     rdx, rbx; unsigned __int16 *
0x1800c5128  mov     rcx, rsi; struct DeclaredConfigurationScopeData *
0x1800c512b  call    ?DCGetEnrollmentIdSidStateDocIdVersionKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBG1PEAPEAUHKEY__@@H@Z; DCGetEnrollmentIdSidStateDocIdVersionKey(DeclaredConfigurationScopeData *,ushort const *,ushort const *,HKEY__ * *,int)
0x1800c5130  mov     ebx, eax
0x1800c5132  lea     rcx, [rbp+var_18]
0x1800c5136  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800c513b  test    ebx, ebx
0x1800c513d  jns     short loc_1800C515C
0x1800c513f  mov     edx, 0FBAh; void *
0x1800c5144  mov     r9d, ebx; char *
0x1800c5147  mov     rcx, [rbp+28h]; this
0x1800c514b  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800c5152  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c5157  jmp     loc_1800C57CF
0x1800c515c  lea     r9, [rbp+nNumberOfBytesToRead]; unsigned int *
0x1800c5160  lea     r8, aValuesize; "valueSize"
0x1800c5167  mov     rdx, [rbp+arg_20]; unsigned __int16 *
0x1800c516b  mov     rcx, [rbp+var_28]; HKEY
0x1800c516f  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800c5174  test    eax, eax
0x1800c5176  js      loc_1800C52DD
0x1800c517c  mov     ebx, dword ptr [rbp+nNumberOfBytesToRead]
0x1800c517f  test    ebx, ebx
0x1800c5181  jz      loc_1800C52DD
0x1800c5187  mov     [rbp+hFile], 0FFFFFFFFFFFFFFFFh
0x1800c518f  lea     rcx, [rdi+20h]
0x1800c5193  cmp     qword ptr [rcx+18h], 7
0x1800c5198  jbe     short loc_1800C519D
0x1800c519a  mov     rcx, [rcx]; lpFileName
0x1800c519d  mov     [rsp+70h+hTemplateFile], r14; hTemplateFile
0x1800c51a2  mov     [rsp+70h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800c51aa  mov     [rsp+70h+dwCreationDisposition], 3; int
0x1800c51b2  xor     r9d, r9d; lpSecurityAttributes
0x1800c51b5  xor     r8d, r8d; dwShareMode
0x1800c51b8  mov     edx, 80000000h; dwDesiredAccess
0x1800c51bd  call    cs:__imp_CreateFileW
0x1800c51c3  mov     rdx, rax
0x1800c51c6  lea     rcx, [rbp+hFile]
0x1800c51ca  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800c51cf  cmp     [rbp+hFile], 0FFFFFFFFFFFFFFFFh
0x1800c51d4  jnz     short loc_1800C51FB
0x1800c51d6  mov     rcx, [rbp+28h]; this
0x1800c51da  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800c51e1  mov     edx, 0FCCh; void *
0x1800c51e6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c51eb  mov     ebx, eax
0x1800c51ed  lea     rcx, [rbp+hFile]
0x1800c51f1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800c51f6  jmp     loc_1800C57CF
0x1800c51fb  mov     dword ptr [rbp+nNumberOfBytesToRead], r14d
0x1800c51ff  call    cs:__imp_GetProcessHeap
0x1800c5205  lea     r8d, [rbx+2]; dwBytes
0x1800c5209  mov     edx, r13d; dwFlags
0x1800c520c  mov     rcx, rax; hHeap
0x1800c520f  call    cs:__imp_HeapAlloc
0x1800c5215  mov     rdi, rax
0x1800c5218  test    rax, rax
0x1800c521b  jnz     short loc_1800C523C
0x1800c521d  mov     rcx, [rbp+28h]; this
0x1800c5221  mov     ebx, 8007000Eh
0x1800c5226  mov     r9d, ebx; char *
0x1800c5229  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800c5230  mov     edx, 0FD3h; void *
0x1800c5235  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c523a  jmp     short loc_1800C51ED
0x1800c523c  mov     qword ptr [rsp+70h+dwCreationDisposition], r14; int
0x1800c5241  lea     r9, [rbp+nNumberOfBytesToRead]; lpNumberOfBytesRead
0x1800c5245  mov     r8d, ebx; nNumberOfBytesToRead
0x1800c5248  mov     rdx, rdi; lpBuffer
0x1800c524b  mov     rcx, [rbp+hFile]; hFile
0x1800c524f  call    cs:__imp_ReadFile
0x1800c5255  test    eax, eax
0x1800c5257  jnz     short loc_1800C5289
0x1800c5259  mov     rcx, [rbp+28h]; this
0x1800c525d  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800c5264  mov     edx, 0FE2h; void *
0x1800c5269  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c526e  mov     ebx, eax
0x1800c5270  call    cs:__imp_GetProcessHeap
0x1800c5276  mov     r8, rdi; lpMem
0x1800c5279  xor     edx, edx; dwFlags
0x1800c527b  mov     rcx, rax; hHeap
0x1800c527e  call    cs:__imp_HeapFree
0x1800c5284  jmp     loc_1800C51ED
0x1800c5289  cmp     dword ptr [rbp+nNumberOfBytesToRead], ebx
0x1800c528c  jz      short loc_1800C52AD
0x1800c528e  mov     rcx, [rbp+28h]; this
0x1800c5292  mov     ebx, 8000FFFFh
0x1800c5297  mov     r9d, ebx; char *
0x1800c529a  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800c52a1  mov     edx, 0FE6h; void *
0x1800c52a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c52ab  jmp     short loc_1800C5270
0x1800c52ad  mov     rbx, [rbp+arg_28]
0x1800c52b1  mov     rcx, rdi; psz
0x1800c52b4  call    cs:__imp_SysAllocString
0x1800c52ba  mov     [rbx+8], rax
0x1800c52be  call    cs:__imp_GetProcessHeap
0x1800c52c4  mov     r8, rdi; lpMem
0x1800c52c7  xor     edx, edx; dwFlags
0x1800c52c9  mov     rcx, rax; hHeap
0x1800c52cc  call    cs:__imp_HeapFree
0x1800c52d2  lea     rcx, [rbp+hFile]
0x1800c52d6  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800c52db  jmp     short loc_1800C52F9
0x1800c52dd  lea     rcx, [rdi+20h]
0x1800c52e1  cmp     qword ptr [rcx+18h], 7
0x1800c52e6  jbe     short loc_1800C52EB
0x1800c52e8  mov     rcx, [rcx]; psz
0x1800c52eb  mov     rbx, [rbp+arg_28]
0x1800c52ef  call    cs:__imp_SysAllocString
0x1800c52f5  mov     [rbx+8], rax
0x1800c52f9  cmp     [rbx+8], r14
0x1800c52fd  jnz     loc_1800C57BE
0x1800c5303  mov     ebx, 8007000Eh
0x1800c5308  mov     edx, 0FF7h
0x1800c530d  jmp     loc_1800C5144
0x1800c5312  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1800c5319  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800c531e  test    al, al
0x1800c5320  jz      short loc_1800C533B
0x1800c5322  mov     rax, [rdi+188h]
0x1800c5329  mov     rcx, [rbp+arg_28]
0x1800c532d  mov     [rcx+8], rax
0x1800c5331  mov     word ptr [rcx], 14h
0x1800c5336  jmp     loc_1800C57CC
0x1800c533b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1800c5342  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800c5347  test    al, al
0x1800c5349  jnz     loc_1800C55BC
0x1800c534f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1800c5356  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800c535b  test    al, al
0x1800c535d  jnz     short loc_1800C536E
0x1800c535f  mov     ebx, 8000FFFFh
0x1800c5364  mov     edx, 10AFh
0x1800c5369  jmp     loc_1800C5144
0x1800c536e  lea     rax, [rbp+var_28]
0x1800c5372  mov     [rbp+var_18], rax
0x1800c5376  mov     [rbp+var_10], r14
0x1800c537a  mov     [rbp+var_8], 1
0x1800c537e  lea     r8, [rbx+60h]
0x1800c5382  cmp     qword ptr [r8+18h], 7
0x1800c5387  jbe     short loc_1800C538C
0x1800c5389  mov     r8, [r8]; unsigned __int16 *
0x1800c538c  cmp     qword ptr [rbx+18h], 7
0x1800c5391  jbe     short loc_1800C5396
0x1800c5393  mov     rbx, [rbx]
0x1800c5396  mov     [rsp+70h+dwCreationDisposition], r14d; int
0x1800c539b  lea     r9, [rbp+var_10]; HKEY *
0x1800c539f  mov     rdx, rbx; unsigned __int16 *
0x1800c53a2  mov     rcx, rsi; struct DeclaredConfigurationScopeData *
0x1800c53a5  call    ?DCGetEnrollmentIdSidStateDocIdVersionKey@@YAJPEAUDeclaredConfigurationScopeData@@PEBG1PEAPEAUHKEY__@@H@Z; DCGetEnrollmentIdSidStateDocIdVersionKey(DeclaredConfigurationScopeData *,ushort const *,ushort const *,HKEY__ * *,int)
0x1800c53aa  mov     ebx, eax
0x1800c53ac  lea     rcx, [rbp+var_18]
0x1800c53b0  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800c53b5  test    ebx, ebx
0x1800c53b7  jns     short loc_1800C53C3
0x1800c53b9  mov     edx, 106Ch
0x1800c53be  jmp     loc_1800C5144
0x1800c53c3  lea     r9, [rbp+nNumberOfBytesToRead]; unsigned int *
0x1800c53c7  lea     r8, aValuesize; "valueSize"
0x1800c53ce  mov     rdx, [rbp+arg_20]; unsigned __int16 *
0x1800c53d2  mov     rcx, [rbp+var_28]; HKEY
0x1800c53d6  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800c53db  test    eax, eax
0x1800c53dd  js      loc_1800C5577
0x1800c53e3  mov     ebx, dword ptr [rbp+nNumberOfBytesToRead]
0x1800c53e6  test    ebx, ebx
0x1800c53e8  jz      loc_1800C5577
0x1800c53ee  mov     [rbp+nNumberOfBytesToRead], 0FFFFFFFFFFFFFFFFh
0x1800c53f6  lea     rcx, [rdi+20h]
0x1800c53fa  cmp     qword ptr [rcx+18h], 7
0x1800c53ff  jbe     short loc_1800C5404
0x1800c5401  mov     rcx, [rcx]; lpFileName
0x1800c5404  mov     [rsp+70h+hTemplateFile], r14; hTemplateFile
0x1800c5409  mov     [rsp+70h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800c5411  mov     [rsp+70h+dwCreationDisposition], 3; int
0x1800c5419  xor     r9d, r9d; lpSecurityAttributes
0x1800c541c  xor     r8d, r8d; dwShareMode
0x1800c541f  mov     edx, 80000000h; dwDesiredAccess
0x1800c5424  call    cs:__imp_CreateFileW
0x1800c542a  mov     rdx, rax
0x1800c542d  lea     rcx, [rbp+nNumberOfBytesToRead]
0x1800c5431  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800c5436  cmp     [rbp+nNumberOfBytesToRead], 0FFFFFFFFFFFFFFFFh
0x1800c543b  jnz     short loc_1800C5459
0x1800c543d  mov     rcx, [rbp+28h]; this
0x1800c5441  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800c5448  mov     edx, 107Eh; void *
0x1800c544d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c5452  mov     ebx, eax
0x1800c5454  jmp     loc_1800C56A2
0x1800c5459  mov     dword ptr [rbp+hFile], r14d
0x1800c545d  call    cs:__imp_GetProcessHeap
0x1800c5463  lea     r8d, [rbx+2]; dwBytes
0x1800c5467  mov     edx, r13d; dwFlags
0x1800c546a  mov     rcx, rax; hHeap
0x1800c546d  call    cs:__imp_HeapAlloc
0x1800c5473  mov     [rbp+lpMem], rax
0x1800c5477  test    rax, rax
0x1800c547a  jnz     short loc_1800C549B
0x1800c547c  mov     rcx, [rbp+28h]; this
0x1800c5480  mov     ebx, 8007000Eh
0x1800c5485  mov     r9d, ebx; char *
0x1800c5488  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800c548f  mov     edx, 1085h; void *
0x1800c5494  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c5499  jmp     short loc_1800C5454
0x1800c549b  lea     rcx, [rbp+lpMem]
0x1800c549f  mov     [rbp+var_18], rcx
0x1800c54a3  mov     byte ptr [rbp+var_10], 1
0x1800c54a7  mov     qword ptr [rsp+70h+dwCreationDisposition], r14; int
0x1800c54ac  lea     r9, [rbp+hFile]; lpNumberOfBytesRead
0x1800c54b0  mov     r8d, ebx; nNumberOfBytesToRead
0x1800c54b3  mov     rdx, rax; lpBuffer
0x1800c54b6  mov     rcx, [rbp+nNumberOfBytesToRead]; hFile
0x1800c54ba  call    cs:__imp_ReadFile
0x1800c54c0  test    eax, eax
0x1800c54c2  jnz     short loc_1800C5501
0x1800c54c4  mov     rcx, [rbp+28h]; this
0x1800c54c8  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\enterprisemgmt\\decl"...
  ... truncated ...
```
