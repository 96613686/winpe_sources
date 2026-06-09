# UWAInstallWork::_FilterFrameworkTLUs(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x1800f8478`
- end: `0x1800f89be`
- name: `?_FilterFrameworkTLUs@UWAInstallWork@@AEAAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `1350`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800f1240`

## callees

- `0x180009ea0`
- `0x180012368`
- `0x1800123f8`
- `0x18001c144`
- `0x18001c414`
- `0x18001c964`
- `0x1800364f8`
- `0x180044af8`
- `0x18006e914`
- `0x18006eb8c`
- `0x18007eea8`
- `0x1800d996c`
- `0x1800e0608`
- `0x1800e29d0`
- `0x1800e3fd0`
- `0x1800e4bcc`
- `0x1800e4db0`
- `0x1800f8478`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f84da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f8587`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f8628`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f86a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f8741`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f87c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f8857`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f88fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f84da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f8587`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f8628`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f86a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f8741`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f87c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f8857`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f88fe`

## string_xrefs

- `0x1800f8516`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f85b9`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f8663`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f86da`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f8777`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f87f3`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f8937`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800f8509`: `UWAInstallWork::_FilterFrameworkTLUs`
- `0x1800f85ac`: `UWAInstallWork::_FilterFrameworkTLUs`
- `0x1800f8656`: `UWAInstallWork::_FilterFrameworkTLUs`
- `0x1800f86cd`: `UWAInstallWork::_FilterFrameworkTLUs`
- `0x1800f8768`: `UWAInstallWork::_FilterFrameworkTLUs`
- `0x1800f87e6`: `UWAInstallWork::_FilterFrameworkTLUs`
- `0x1800f892a`: `UWAInstallWork::_FilterFrameworkTLUs`
- `0x1800f87d6`: `Installation status check failed for framework package %s, including in download list`
- `0x1800f8867`: `Framework package %s is already installed, skipping download`
- `0x1800f86bd`: `Architecture compatibility check failed for framework package %s, including in download list`
- `0x1800f8751`: `Framework package %s has incompatible architecture, skipping download`
- `0x1800f8916`: `Framework TLU filtering complete: %u of %u TLUs remain after filtering`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UWAInstallWork::_FilterFrameworkTLUs(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  _QWORD *v6; // rdi
  _QWORD *v7; // r13
  _QWORD *v8; // rcx
  int PackageInfoFromHeadRequest; // esi
  _QWORD *v10; // rbx
  const unsigned __int16 *v11; // rax
  __int64 v12; // r9
  char *v13; // rdx
  char *v14; // rbx
  _QWORD *v15; // rsi
  const unsigned __int16 *v16; // rax
  int IsPackageArchitectureCompatible; // esi
  char *v18; // rbx
  const unsigned __int16 *v19; // rax
  __int64 v20; // r9
  char *v21; // rbx
  int IsPackageAlreadyInstalled; // esi
  __int64 v23; // r9
  char *v24; // rbx
  const unsigned __int16 *v25; // rax
  __int64 v26; // r9
  char *v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rdi
  __int64 v30; // rbx
  const unsigned __int16 *v31; // rax
  unsigned __int16 *v33; // [rsp+38h] [rbp-C8h]
  unsigned __int16 *v34; // [rsp+38h] [rbp-C8h]
  __int64 v35; // [rsp+40h] [rbp-C0h]
  __int64 v36; // [rsp+48h] [rbp-B8h]
  char v37[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v38; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h]
  _QWORD v40[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v41[64]; // [rsp+80h] [rbp-80h] BYREF
  char v42; // [rsp+C0h] [rbp-40h] BYREF
  char v43; // [rsp+D0h] [rbp-30h] BYREF
  char v44; // [rsp+E0h] [rbp-20h] BYREF
  char v45; // [rsp+F0h] [rbp-10h] BYREF
  char v46[24]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v47; // [rsp+118h] [rbp+18h]

  v38 = 0;
  v39 = 0;
  std::unordered_map<std::wstring,wsdl::UpdateInfo *>::unordered_map<std::wstring,wsdl::UpdateInfo *>(v41);
  v4 = (__int64)(a2[1] - *a2) >> 5;
  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 472), 0);
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
    0x1355u,
    "UWAInstallWork::_FilterFrameworkTLUs",
    -1,
    L"Filtering framework TLUs: %u candidates",
    (const char *)(a1 + 304),
    StringRawBuffer,
    v4);
  v6 = (_QWORD *)*a2;
  v7 = (_QWORD *)a2[1];
  while ( v6 != v7 )
  {
    std::wstring::wstring(v46);
    v40[0] = 0;
    if ( v6[3] <= 7u )
      v8 = v6;
    else
      v8 = (_QWORD *)*v6;
    PackageInfoFromHeadRequest = GetPackageInfoFromHeadRequest(v8, v46, v40);
    if ( PackageInfoFromHeadRequest < 0 )
    {
      if ( v6[3] <= 7u )
        v10 = v6;
      else
        v10 = (_QWORD *)*v6;
      v11 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 472), 0);
      LogMessage(
        2u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
        0x135Du,
        "UWAInstallWork::_FilterFrameworkTLUs",
        PackageInfoFromHeadRequest,
        L"HEAD request failed for framework TLU, including in download list: %s",
        (const char *)(a1 + 304),
        v11,
        v10);
      if ( *((_QWORD *)&v38 + 1) == v39 )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v38, *((_QWORD *)&v38 + 1), v6, v12);
      }
      else
      {
        std::wstring::wstring(*((_QWORD *)&v38 + 1));
        *((_QWORD *)&v38 + 1) += 32LL;
      }
      v13 = &v42;
LABEL_45:
      v28 = std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Try_emplace<std::wstring const &,>(
              v41,
              v13,
              v6);
      *(_QWORD *)(*(_QWORD *)v28 + 48LL) = v40[0];
      goto LABEL_46;
    }
    v14 = v46;
    if ( v47 > 7 )
      v14 = *(char **)v46;
    if ( v6[3] <= 7u )
      v15 = v6;
    else
      v15 = (_QWORD *)*v6;
    v16 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 472), 0);
    LogMessage(
      4u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
      0x1362u,
      "UWAInstallWork::_FilterFrameworkTLUs",
      -1,
      L"Framework TLU HEAD resolved: url=%s, packageFullName=%s",
      (const char *)(a1 + 304),
      v16,
      v15,
      v14);
    v37[0] = 1;
    IsPackageArchitectureCompatible = Utils::IsPackageArchitectureCompatible(v46, v37);
    if ( IsPackageArchitectureCompatible < 0 )
    {
      v18 = v46;
      if ( v47 > 7 )
        v18 = *(char **)v46;
      v19 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 472), 0);
      LogMessage(
        2u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
        0x1368u,
        "UWAInstallWork::_FilterFrameworkTLUs",
        IsPackageArchitectureCompatible,
        L"Architecture compatibility check failed for framework package %s, including in download list",
        (const char *)(a1 + 304),
        v19,
        v18);
      if ( *((_QWORD *)&v38 + 1) == v39 )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v38, *((_QWORD *)&v38 + 1), v6, v20);
      }
      else
      {
        std::wstring::wstring(*((_QWORD *)&v38 + 1));
        *((_QWORD *)&v38 + 1) += 32LL;
      }
      v13 = &v43;
      goto LABEL_45;
    }
    if ( v37[0] )
    {
      v37[0] = 0;
      IsPackageAlreadyInstalled = Utils::IsPackageAlreadyInstalled(v46);
      if ( IsPackageAlreadyInstalled < 0 )
      {
        v24 = v46;
        if ( v47 > 7 )
          v24 = *(char **)v46;
        v25 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 472), 0);
        LogMessage(
          2u,
          "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
          0x1377u,
          "UWAInstallWork::_FilterFrameworkTLUs",
          IsPackageAlreadyInstalled,
          L"Installation status check failed for framework package %s, including in download list",
          (const char *)(a1 + 304),
          v25,
          v24);
        if ( *((_QWORD *)&v38 + 1) == v39 )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v38, *((_QWORD *)&v38 + 1), v6, v26);
        }
        else
        {
          std::wstring::wstring(*((_QWORD *)&v38 + 1));
          *((_QWORD *)&v38 + 1) += 32LL;
        }
        v13 = &v44;
        goto LABEL_45;
      }
      if ( !v37[0] )
      {
        if ( *((_QWORD *)&v38 + 1) == v39 )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v38, *((_QWORD *)&v38 + 1), v6, v23);
        }
        else
        {
          std::wstring::wstring(*((_QWORD *)&v38 + 1));
          *((_QWORD *)&v38 + 1) += 32LL;
        }
        v13 = &v45;
        goto LABEL_45;
      }
      v27 = v46;
      if ( v47 > 7 )
        v27 = *(char **)v46;
      v34 = (unsigned __int16 *)WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 472), 0);
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
        0x137Eu,
        "UWAInstallWork::_FilterFrameworkTLUs",
        -1,
        L"Framework package %s is already installed, skipping download",
        (const char *)(a1 + 304),
        v34,
        v27);
    }
    else
    {
      v21 = v46;
      if ( v47 > 7 )
        v21 = *(char **)v46;
      v33 = (unsigned __int16 *)WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 472), 0);
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
        0x136Fu,
        "UWAInstallWork::_FilterFrameworkTLUs",
        -1,
        L"Framework package %s has incompatible architecture, skipping download",
        (const char *)(a1 + 304),
        v33,
        v21);
    }
LABEL_46:
    std::wstring::_Tidy_deallocate(v46);
    v6 += 4;
  }
  v29 = (__int64)(a2[1] - *a2) >> 5;
  v30 = (__int64)(*((_QWORD *)&v38 + 1) - v38) >> 5;
  v31 = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 472), 0);
  LODWORD(v36) = v29;
  LODWORD(v35) = v30;
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
    0x1386u,
    "UWAInstallWork::_FilterFrameworkTLUs",
    -1,
    L"Framework TLU filtering complete: %u of %u TLUs remain after filtering",
    (const char *)(a1 + 304),
    v31,
    v35,
    v36);
  std::vector<std::wstring>::operator=(a2, &v38);
  wil::AcquireSRWLockExclusive(v40, a1 + 1048);
  std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::operator=(
    a1 + 856,
    v41);
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)v40);
  std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(v41);
  std::vector<std::wstring>::_Tidy(&v38);
  return 0;
}

```

## disassembly

```asm
0x1800f8478  mov     [rsp-8+arg_10], rbx
0x1800f847d  push    rbp
0x1800f847e  push    rsi
0x1800f847f  push    rdi
0x1800f8480  push    r12
0x1800f8482  push    r13
0x1800f8484  push    r14
0x1800f8486  push    r15
0x1800f8488  lea     rbp, [rsp-30h]
0x1800f848d  sub     rsp, 130h
0x1800f8494  mov     rax, cs:__security_cookie
0x1800f849b  xor     rax, rsp
0x1800f849e  mov     [rbp+60h+var_40], rax
0x1800f84a2  mov     r12, rdx
0x1800f84a5  mov     r14, rcx
0x1800f84a8  xorps   xmm0, xmm0
0x1800f84ab  movdqu  [rsp+160h+var_108], xmm0
0x1800f84b1  mov     [rsp+160h+var_F8], 0
0x1800f84ba  lea     rcx, [rbp+60h+var_E0]
0x1800f84be  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUUpdateInfo@wsdl@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUUpdateInfo@wsdl@@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,wsdl::UpdateInfo *>::unordered_map<std::wstring,wsdl::UpdateInfo *>(void)
0x1800f84c3  nop
0x1800f84c4  mov     rbx, [r12+8]
0x1800f84c9  sub     rbx, [r12]
0x1800f84cd  sar     rbx, 5
0x1800f84d1  xor     edx, edx; length
0x1800f84d3  mov     rcx, [r14+1D8h]; string
0x1800f84da  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f84e0  lea     r15, [r14+130h]
0x1800f84e7  mov     dword ptr [rsp+160h+var_120], ebx
0x1800f84eb  mov     [rsp+160h+var_128], rax; unsigned __int16 *
0x1800f84f0  mov     [rsp+160h+var_130], r15; char *
0x1800f84f5  lea     rax, aFilteringFrame; "Filtering framework TLUs: %u candidates"
0x1800f84fc  mov     [rsp+160h+var_138], rax; unsigned __int16 *
0x1800f8501  mov     [rsp+160h+var_140], 0FFFFFFFFh; int
0x1800f8509  lea     r9, aUwainstallwork_12; "UWAInstallWork::_FilterFrameworkTLUs"
0x1800f8510  mov     r8d, 1355h; unsigned int
0x1800f8516  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800f851d  mov     ecx, 3; unsigned int
0x1800f8522  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800f8527  mov     rdi, [r12]
0x1800f852b  mov     r13, [r12+8]
0x1800f8530  jmp     loc_1800F88D1
0x1800f8535  lea     rcx, [rbp+60h+var_60]
0x1800f8539  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800f853e  nop
0x1800f853f  mov     [rsp+160h+var_F0], 0
0x1800f8548  cmp     qword ptr [rdi+18h], 7
0x1800f854d  jbe     short loc_1800F8554
0x1800f854f  mov     rcx, [rdi]
0x1800f8552  jmp     short loc_1800F8557
0x1800f8554  mov     rcx, rdi
0x1800f8557  lea     r8, [rsp+160h+var_F0]
0x1800f855c  lea     rdx, [rbp+60h+var_60]
0x1800f8560  call    ?GetPackageInfoFromHeadRequest@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_K@Z; GetPackageInfoFromHeadRequest(ushort const *,std::wstring &,unsigned __int64 &)
0x1800f8565  mov     esi, eax
0x1800f8567  test    eax, eax
0x1800f8569  jns     loc_1800F8602
0x1800f856f  cmp     qword ptr [rdi+18h], 7
0x1800f8574  jbe     short loc_1800F857B
0x1800f8576  mov     rbx, [rdi]
0x1800f8579  jmp     short loc_1800F857E
0x1800f857b  mov     rbx, rdi
0x1800f857e  xor     edx, edx; length
0x1800f8580  mov     rcx, [r14+1D8h]; string
0x1800f8587  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f858d  mov     [rsp+160h+var_120], rbx
0x1800f8592  mov     [rsp+160h+var_128], rax; unsigned __int16 *
0x1800f8597  mov     [rsp+160h+var_130], r15; char *
0x1800f859c  lea     rax, aHeadRequestFai; "HEAD request failed for framework TLU, "...
0x1800f85a3  mov     [rsp+160h+var_138], rax; unsigned __int16 *
0x1800f85a8  mov     [rsp+160h+var_140], esi; int
0x1800f85ac  lea     r9, aUwainstallwork_12; "UWAInstallWork::_FilterFrameworkTLUs"
0x1800f85b3  mov     r8d, 135Dh; unsigned int
0x1800f85b9  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800f85c0  mov     ecx, 2; unsigned int
0x1800f85c5  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800f85ca  mov     rax, qword ptr [rsp+160h+var_108+8]
0x1800f85cf  cmp     rax, [rsp+160h+var_F8]
0x1800f85d4  jz      short loc_1800F85E9
0x1800f85d6  mov     rdx, rdi
0x1800f85d9  mov     rcx, rax
0x1800f85dc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800f85e1  add     qword ptr [rsp+160h+var_108+8], 20h ; ' '
0x1800f85e7  jmp     short loc_1800F85F9
0x1800f85e9  mov     r8, rdi
0x1800f85ec  mov     rdx, rax
0x1800f85ef  lea     rcx, [rsp+160h+var_108]
0x1800f85f4  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x1800f85f9  lea     rdx, [rbp+60h+var_A0]
0x1800f85fd  jmp     loc_1800F88AC
0x1800f8602  lea     rbx, [rbp+60h+var_60]
0x1800f8606  cmp     [rbp+60h+var_48], 7
0x1800f860b  cmova   rbx, qword ptr [rbp+60h+var_60]
0x1800f8610  cmp     qword ptr [rdi+18h], 7
0x1800f8615  jbe     short loc_1800F861C
0x1800f8617  mov     rsi, [rdi]
0x1800f861a  jmp     short loc_1800F861F
0x1800f861c  mov     rsi, rdi
0x1800f861f  xor     edx, edx; length
0x1800f8621  mov     rcx, [r14+1D8h]; string
0x1800f8628  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f862e  mov     [rsp+160h+var_118], rbx
0x1800f8633  mov     [rsp+160h+var_120], rsi
0x1800f8638  mov     [rsp+160h+var_128], rax; unsigned __int16 *
0x1800f863d  mov     [rsp+160h+var_130], r15; char *
0x1800f8642  lea     rax, aFrameworkTluHe; "Framework TLU HEAD resolved: url=%s, pa"...
0x1800f8649  mov     [rsp+160h+var_138], rax; unsigned __int16 *
0x1800f864e  mov     [rsp+160h+var_140], 0FFFFFFFFh; int
0x1800f8656  lea     r9, aUwainstallwork_12; "UWAInstallWork::_FilterFrameworkTLUs"
0x1800f865d  mov     r8d, 1362h; unsigned int
0x1800f8663  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800f866a  mov     ecx, 4; unsigned int
0x1800f866f  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800f8674  mov     [rsp+160h+var_110], 1
0x1800f8679  lea     rdx, [rsp+160h+var_110]
0x1800f867e  lea     rcx, [rbp+60h+var_60]
0x1800f8682  call    ?IsPackageArchitectureCompatible@Utils@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_N@Z; Utils::IsPackageArchitectureCompatible(std::wstring const &,bool &)
0x1800f8687  mov     esi, eax
0x1800f8689  test    eax, eax
0x1800f868b  jns     loc_1800F8723
0x1800f8691  lea     rbx, [rbp+60h+var_60]
0x1800f8695  cmp     [rbp+60h+var_48], 7
0x1800f869a  cmova   rbx, qword ptr [rbp+60h+var_60]
0x1800f869f  xor     edx, edx; length
0x1800f86a1  mov     rcx, [r14+1D8h]; string
0x1800f86a8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f86ae  mov     [rsp+160h+var_120], rbx
0x1800f86b3  mov     [rsp+160h+var_128], rax; unsigned __int16 *
0x1800f86b8  mov     [rsp+160h+var_130], r15; char *
0x1800f86bd  lea     rax, aArchitectureCo_0; "Architecture compatibility check failed"...
0x1800f86c4  mov     [rsp+160h+var_138], rax; unsigned __int16 *
0x1800f86c9  mov     [rsp+160h+var_140], esi; int
0x1800f86cd  lea     r9, aUwainstallwork_12; "UWAInstallWork::_FilterFrameworkTLUs"
0x1800f86d4  mov     r8d, 1368h; unsigned int
0x1800f86da  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800f86e1  mov     ecx, 2; unsigned int
0x1800f86e6  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800f86eb  mov     rax, qword ptr [rsp+160h+var_108+8]
0x1800f86f0  cmp     rax, [rsp+160h+var_F8]
0x1800f86f5  jz      short loc_1800F870A
0x1800f86f7  mov     rdx, rdi
0x1800f86fa  mov     rcx, rax
0x1800f86fd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800f8702  add     qword ptr [rsp+160h+var_108+8], 20h ; ' '
0x1800f8708  jmp     short loc_1800F871A
0x1800f870a  mov     r8, rdi
0x1800f870d  mov     rdx, rax
0x1800f8710  lea     rcx, [rsp+160h+var_108]
0x1800f8715  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x1800f871a  lea     rdx, [rbp+60h+var_90]
0x1800f871e  jmp     loc_1800F88AC
0x1800f8723  cmp     [rsp+160h+var_110], 0
0x1800f8728  jnz     short loc_1800F878D
0x1800f872a  lea     rbx, [rbp+60h+var_60]
0x1800f872e  cmp     [rbp+60h+var_48], 7
0x1800f8733  cmova   rbx, qword ptr [rbp+60h+var_60]
0x1800f8738  xor     edx, edx; length
0x1800f873a  mov     rcx, [r14+1D8h]; string
0x1800f8741  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f8747  mov     [rsp+160h+var_120], rbx
0x1800f874c  mov     [rsp+160h+var_128], rax; unsigned __int16 *
0x1800f8751  lea     rax, aFrameworkPacka_0; "Framework package %s has incompatible a"...
0x1800f8758  mov     r8d, 136Fh; unsigned int
0x1800f875e  mov     [rsp+160h+var_130], r15; char *
0x1800f8763  mov     [rsp+160h+var_138], rax; unsigned __int16 *
0x1800f8768  lea     r9, aUwainstallwork_12; "UWAInstallWork::_FilterFrameworkTLUs"
0x1800f876f  mov     [rsp+160h+var_140], 0FFFFFFFFh; int
0x1800f8777  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800f877e  mov     ecx, 3; unsigned int
0x1800f8783  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800f8788  jmp     loc_1800F88C4
0x1800f878d  mov     [rsp+160h+var_110], 0
0x1800f8792  lea     rdx, [rsp+160h+var_110]
0x1800f8797  lea     rcx, [rbp+60h+var_60]; char *
0x1800f879b  call    ?IsPackageAlreadyInstalled@Utils@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_N@Z; Utils::IsPackageAlreadyInstalled(std::wstring const &,bool &)
0x1800f87a0  mov     esi, eax
0x1800f87a2  test    eax, eax
0x1800f87a4  jns     loc_1800F8839
0x1800f87aa  lea     rbx, [rbp+60h+var_60]
0x1800f87ae  cmp     [rbp+60h+var_48], 7
0x1800f87b3  cmova   rbx, qword ptr [rbp+60h+var_60]
0x1800f87b8  xor     edx, edx; length
0x1800f87ba  mov     rcx, [r14+1D8h]; string
0x1800f87c1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f87c7  mov     [rsp+160h+var_120], rbx
0x1800f87cc  mov     [rsp+160h+var_128], rax; unsigned __int16 *
0x1800f87d1  mov     [rsp+160h+var_130], r15; char *
0x1800f87d6  lea     rax, aInstallationSt; "Installation status check failed for fr"...
0x1800f87dd  mov     [rsp+160h+var_138], rax; unsigned __int16 *
0x1800f87e2  mov     [rsp+160h+var_140], esi; int
0x1800f87e6  lea     r9, aUwainstallwork_12; "UWAInstallWork::_FilterFrameworkTLUs"
0x1800f87ed  mov     r8d, 1377h; unsigned int
0x1800f87f3  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800f87fa  mov     ecx, 2; unsigned int
0x1800f87ff  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800f8804  mov     rax, qword ptr [rsp+160h+var_108+8]
0x1800f8809  cmp     rax, [rsp+160h+var_F8]
0x1800f880e  jz      short loc_1800F8823
0x1800f8810  mov     rdx, rdi
0x1800f8813  mov     rcx, rax
0x1800f8816  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800f881b  add     qword ptr [rsp+160h+var_108+8], 20h ; ' '
0x1800f8821  jmp     short loc_1800F8833
0x1800f8823  mov     r8, rdi
0x1800f8826  mov     rdx, rax
0x1800f8829  lea     rcx, [rsp+160h+var_108]
0x1800f882e  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x1800f8833  lea     rdx, [rbp+60h+var_80]
0x1800f8837  jmp     short loc_1800F88AC
0x1800f8839  cmp     [rsp+160h+var_110], 0
0x1800f883e  jz      short loc_1800F8879
0x1800f8840  lea     rbx, [rbp+60h+var_60]
0x1800f8844  cmp     [rbp+60h+var_48], 7
0x1800f8849  cmova   rbx, qword ptr [rbp+60h+var_60]
0x1800f884e  xor     edx, edx; length
0x1800f8850  mov     rcx, [r14+1D8h]; string
0x1800f8857  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f885d  mov     [rsp+160h+var_120], rbx
0x1800f8862  mov     [rsp+160h+var_128], rax
0x1800f8867  lea     rax, aFrameworkPacka; "Framework package %s is already install"...
0x1800f886e  mov     r8d, 137Eh
0x1800f8874  jmp     loc_1800F875E
0x1800f8879  mov     rax, qword ptr [rsp+160h+var_108+8]
0x1800f887e  cmp     rax, [rsp+160h+var_F8]
0x1800f8883  jz      short loc_1800F8898
0x1800f8885  mov     rdx, rdi
0x1800f8888  mov     rcx, rax
0x1800f888b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800f8890  add     qword ptr [rsp+160h+var_108+8], 20h ; ' '
0x1800f8896  jmp     short loc_1800F88A8
0x1800f8898  mov     r8, rdi
0x1800f889b  mov     rdx, rax
0x1800f889e  lea     rcx, [rsp+160h+var_108]
0x1800f88a3  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x1800f88a8  lea     rdx, [rbp+60h+var_70]
0x1800f88ac  mov     r8, rdi
0x1800f88af  lea     rcx, [rbp+60h+var_E0]
0x1800f88b3  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x1800f88b8  mov     rcx, [rax]
0x1800f88bb  mov     rax, [rsp+160h+var_F0]
0x1800f88c0  mov     [rcx+30h], rax
0x1800f88c4  lea     rcx, [rbp+60h+var_60]
0x1800f88c8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f88cd  add     rdi, 20h ; ' '
0x1800f88d1  cmp     rdi, r13
0x1800f88d4  jnz     loc_1800F8535
0x1800f88da  mov     rdi, [r12+8]
0x1800f88df  sub     rdi, [r12]
0x1800f88e3  sar     rdi, 5
0x1800f88e7  mov     rbx, qword ptr [rsp+160h+var_108+8]
0x1800f88ec  sub     rbx, qword ptr [rsp+160h+var_108]
0x1800f88f1  sar     rbx, 5
0x1800f88f5  xor     edx, edx; length
0x1800f88f7  mov     rcx, [r14+1D8h]; string
0x1800f88fe  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f8904  mov     dword ptr [rsp+160h+var_118], edi
0x1800f8908  mov     dword ptr [rsp+160h+var_120], ebx
0x1800f890c  mov     [rsp+160h+var_128], rax; unsigned __int16 *
0x1800f8911  mov     [rsp+160h+var_130], r15; char *
0x1800f8916  lea     rax, aFrameworkTluFi; "Framework TLU filtering complete: %u of"...
0x1800f891d  mov     [rsp+160h+var_138], rax; unsigned __int16 *
0x1800f8922  mov     [rsp+160h+var_140], 0FFFFFFFFh; int
0x1800f892a  lea     r9, aUwainstallwork_12; "UWAInstallWork::_FilterFrameworkTLUs"
0x1800f8931  mov     r8d, 1386h; unsigned int
0x1800f8937  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800f893e  mov     ecx, 3; unsigned int
0x1800f8943  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800f8948  lea     rdx, [rsp+160h+var_108]
0x1800f894d  mov     rcx, r12
0x1800f8950  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> &&)
0x1800f8955  lea     rdx, [r14+418h]
0x1800f895c  lea     rcx, [rsp+160h+var_F0]
0x1800f8961  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1800f8966  lea     rcx, [r14+358h]
0x1800f896d  lea     rdx, [rbp+60h+var_E0]
0x1800f8971  call    ??4?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::operator=(std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>> &&)
0x1800f8976  lea     rcx, [rsp+160h+var_F0]; this
0x1800f897b  call    ?InternalUnlock@SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::InternalUnlock(void)
0x1800f8980  nop
0x1800f8981  lea     rcx, [rbp+60h+var_E0]
0x1800f8985  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Hash<std::_Umap_traits<std::wstring,unsigned __int64,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
0x1800f898a  nop
0x1800f898b  lea     rcx, [rsp+160h+var_108]
0x1800f8990  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800f8995  xor     eax, eax
0x1800f8997  mov     rcx, [rbp+60h+var_40]
0x1800f899b  xor     rcx, rsp; StackCookie
0x1800f899e  call    __security_check_cookie
0x1800f89a3  mov     rbx, [rsp+160h+arg_10]
0x1800f89ab  add     rsp, 130h
0x1800f89b2  pop     r15
0x1800f89b4  pop     r14
0x1800f89b6  pop     r13
0x1800f89b8  pop     r12
0x1800f89ba  pop     rdi
0x1800f89bb  pop     rsi
0x1800f89bc  pop     rbp
0x1800f89bd  retn
```
