# GetPackagesToBeInstalled

- ea: `0x180020c28`
- end: `0x180021492`
- name: `GetPackagesToBeInstalled`
- size: `2154`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180021590`

## callees

- `0x180003c94`
- `0x1800049a4`
- `0x180004af8`
- `0x18000509c`
- `0x1800050bc`
- `0x180005c00`
- `0x180005c70`
- `0x180005cc0`
- `0x1800064a0`
- `0x180006500`
- `0x18000d570`
- `0x18000d5a0`
- `0x18000d92c`
- `0x180020418`
- `0x180020c28`
- `0x180023500`
- `0x180037344`
- `0x18004a898`
- `0x180050588`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180021111`
- `msvcrt!_wcsicmp` at `0x180021228`
- `msvcrt!_wcsicmp` at `0x180021111`
- `msvcrt!_wcsicmp` at `0x180021228`
- `DismApi!DismGetPackageInfo` at `0x180020dd4`
- `DismApi!DismGetPackageInfo` at `0x1800210cb`
- `DismApi!DismGetPackageInfo` at `0x180020dd4`
- `DismApi!DismGetPackageInfo` at `0x1800210cb`
- `DismApi!DismGetPackages` at `0x180020d07`
- `DismApi!DismGetPackages` at `0x180020fc3`
- `DismApi!DismGetPackages` at `0x180020d07`
- `DismApi!DismGetPackages` at `0x180020fc3`

## string_xrefs

- `0x180020c9b`: `Failed to open DISM session`
- `0x180020f5c`: `Failed to open DISM session`
- `0x180020caf`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180020d27`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180020e49`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180020f05`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180020f70`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180020fe3`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x1800212d3`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180021314`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180021374`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180020cb6`: `GetPackagesToBeInstalled`
- `0x180020d2e`: `GetPackagesToBeInstalled`
- `0x180020e50`: `GetPackagesToBeInstalled`
- `0x180020f0c`: `GetPackagesToBeInstalled`
- `0x180020f77`: `GetPackagesToBeInstalled`
- `0x180020fea`: `GetPackagesToBeInstalled`
- `0x1800212da`: `GetPackagesToBeInstalled`
- `0x18002131b`: `GetPackagesToBeInstalled`
- `0x18002137b`: `GetPackagesToBeInstalled`
- `0x1800212bf`: `Failed to create package path %ws.`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall GetPackagesToBeInstalled(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rax
  int v7; // eax
  int PackageInfo; // ebx
  __int64 v9; // rbx
  __int64 v10; // rax
  int Packages; // eax
  unsigned int i; // esi
  __int64 v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rbx
  __int64 v21; // rax
  int v22; // eax
  unsigned int v23; // esi
  __int64 v24; // rdi
  __int64 v25; // rbx
  __int64 v26; // rax
  unsigned __int64 j; // rdi
  const wchar_t *v28; // rbx
  __int64 v29; // r8
  const wchar_t **v30; // rax
  __int64 v31; // rbx
  __int64 v32; // rax
  __int64 v33; // rax
  int v34; // edx
  __int64 (__fastcall *v35)(void ***); // rax
  __int64 v36; // rax
  void **v37; // rcx
  __int64 v38; // rax
  bool v39; // zf
  __int64 (__fastcall *v40)(void ***); // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v44; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v45; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v46; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v47; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v48; // [rsp+60h] [rbp-A0h]
  __int64 v49; // [rsp+68h] [rbp-98h]
  int v50; // [rsp+70h] [rbp-90h]
  void *v51[3]; // [rsp+78h] [rbp-88h] BYREF
  int v52; // [rsp+90h] [rbp-70h]
  void *v53[3]; // [rsp+98h] [rbp-68h] BYREF
  int v54; // [rsp+B0h] [rbp-50h]
  void *v55[3]; // [rsp+B8h] [rbp-48h] BYREF
  int v56; // [rsp+D0h] [rbp-30h]
  void *v57[3]; // [rsp+D8h] [rbp-28h] BYREF
  int v58; // [rsp+F0h] [rbp-10h]
  void *v59[3]; // [rsp+F8h] [rbp-8h] BYREF
  int v60; // [rsp+110h] [rbp+10h]
  void **v61; // [rsp+118h] [rbp+18h] BYREF
  __int64 v62; // [rsp+120h] [rbp+20h]
  void **v63; // [rsp+128h] [rbp+28h] BYREF
  _QWORD *v64; // [rsp+130h] [rbp+30h]
  _QWORD v65[2]; // [rsp+138h] [rbp+38h] BYREF
  void **v66; // [rsp+148h] [rbp+48h] BYREF
  __int64 v67; // [rsp+150h] [rbp+50h]
  _QWORD v68[2]; // [rsp+158h] [rbp+58h] BYREF
  unsigned int v69; // [rsp+168h] [rbp+68h] BYREF

  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v65[1] = 0;
  v65[0] = &RAII::CAutoPbrDelete<PushButtonReset::DISMSession *>::`vftable';
  v6 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v65);
  v7 = PushButtonReset::DISMSession::Open(a1, v6);
  PackageInfo = v7;
  if ( v7 >= 0 )
  {
    v62 = 0;
    v61 = &RAII::CAutoDismDelete<_DismImageInfo *>::`vftable';
    v69 = 0;
    v9 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v61);
    v10 = (*(__int64 (__fastcall **)(_QWORD *))(v65[0] + 24LL))(v65);
    Packages = DismGetPackages(*(unsigned int *)(v10 + 4), v9, &v69);
    PackageInfo = Packages;
    if ( Packages >= 0 )
    {
      for ( i = 0; i < v69; ++i )
      {
        if ( *(_DWORD *)(((__int64 (__fastcall *)(void ***))v61[4])(&v61) + 32LL * i + 8) == 4 )
        {
          v67 = 0;
          v66 = &RAII::CAutoDismDelete<_DismImageInfo *>::`vftable';
          v13 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v66);
          v14 = *(_QWORD *)(((__int64 (__fastcall *)(void ***))v61[4])(&v61) + 32LL * i);
          v15 = (*(__int64 (__fastcall **)(_QWORD *))(v65[0] + 24LL))(v65);
          PackageInfo = DismGetPackageInfo(*(unsigned int *)(v15 + 4), v14, 1, v13);
          if ( PackageInfo < 0 )
          {
            v17 = ((__int64 (__fastcall *)(void ***))v61[4])(&v61);
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)PackageInfo,
              "GetPackagesToBeInstalled",
              "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
              388,
              L"Failed to get package info for package %ws.",
              *(_QWORD *)(v17 + 32LL * i));
            v66 = &RAII::CAutoDismDelete<_DismImageInfo *>::`vftable';
            RAII::CAutoDismDelete<_DismPackageInfo *>::Release(&v66);
            v61 = &RAII::CAutoDismDelete<_DismImageInfo *>::`vftable';
            RAII::CAutoDismDelete<_DismPackageInfo *>::Release(&v61);
            goto LABEL_45;
          }
          v16 = ((__int64 (__fastcall *)(void ***))v66[3])(&v66);
          ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Add(
            &v47,
            *(_QWORD *)(v16 + 116));
          v66 = &RAII::CAutoDismDelete<_DismImageInfo *>::`vftable';
          RAII::CAutoDismDelete<_DismPackageInfo *>::Release(&v66);
        }
      }
      v61 = &RAII::CAutoDismDelete<_DismImageInfo *>::`vftable';
      RAII::CAutoDismDelete<_DismPackageInfo *>::Release(&v61);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v45);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v46,
        (__int64)L"\\windows\\servicing\\packages");
      PackageInfo = PushButtonReset::Path::Combine(a2, &v46, &v45);
      ATL::CStringData::Release((ATL::CStringData *)(v46 - 24));
      if ( PackageInfo >= 0 )
      {
        v68[1] = 0;
        v68[0] = &RAII::CAutoPbrDelete<PushButtonReset::DISMSession *>::`vftable';
        v18 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v68);
        v19 = PushButtonReset::DISMSession::Open(a2, v18);
        PackageInfo = v19;
        if ( v19 >= 0 )
        {
          v67 = 0;
          v66 = &RAII::CAutoDismDelete<_DismImageInfo *>::`vftable';
          v69 = 0;
          v20 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v66);
          v21 = (*(__int64 (__fastcall **)(_QWORD *))(v68[0] + 24LL))(v68);
          v22 = DismGetPackages(*(unsigned int *)(v21 + 4), v20, &v69);
          PackageInfo = v22;
          if ( v22 >= 0 )
          {
            memset(v59, 0, sizeof(v59));
            v60 = 0;
            memset(v57, 0, sizeof(v57));
            v58 = 0;
            memset(v55, 0, sizeof(v55));
            v56 = 0;
            memset(v53, 0, sizeof(v53));
            v54 = 0;
            memset(v51, 0, sizeof(v51));
            v52 = 0;
            v23 = 0;
            while ( 2 )
            {
              if ( v23 >= v69 )
              {
                ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Append(
                  a3,
                  v59);
                ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Append(
                  a3,
                  v57);
                ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Append(
                  a3,
                  v55);
                ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Append(
                  a3,
                  v51);
                ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Append(
                  a3,
                  v53);
                PackageInfo = 0;
              }
              else
              {
                v62 = 0;
                v61 = &RAII::CAutoDismDelete<_DismImageInfo *>::`vftable';
                v24 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v61);
                v25 = *(_QWORD *)(((__int64 (__fastcall *)(void ***))v66[4])(&v66) + 32LL * v23);
                v26 = (*(__int64 (__fastcall **)(_QWORD *))(v68[0] + 24LL))(v68);
                PackageInfo = DismGetPackageInfo(*(unsigned int *)(v26 + 4), v25, 1, v24);
                if ( PackageInfo < 0 )
                {
                  v42 = ((__int64 (__fastcall *)(void ***))v66[4])(&v66);
                  PushButtonReset::Logging::TraceErr(
                    2,
                    (unsigned int)PackageInfo,
                    "GetPackagesToBeInstalled",
                    "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
                    422,
                    L"Failed to get package info for package %ws.",
                    *(_QWORD *)(v42 + 32LL * v23));
                }
                else
                {
                  for ( j = 0; ; ++j )
                  {
                    if ( j >= v48 )
                      goto LABEL_37;
                    v28 = *(const wchar_t **)(((__int64 (__fastcall *)(void ***))v61[3])(&v61) + 116);
                    v30 = (const wchar_t **)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                                              &v47,
                                              j,
                                              v29);
                    if ( !_wcsicmp(*v30, v28) )
                      break;
                  }
                  v64 = PbrNew<WinREAgent::PACKAGE_INFO,>();
                  v63 = &RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::`vftable';
                  if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!((__int64 *)&v63) )
                  {
                    PushButtonReset::Logging::TraceErr(
                      2,
                      2147942414LL,
                      "GetPackagesToBeInstalled",
                      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
                      432,
                      L"Failed to allocate package");
                    v63 = &RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::`vftable';
                    RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::Release(&v63);
                    PackageInfo = -2147024882;
                  }
                  else
                  {
                    v31 = ((__int64 (__fastcall *)(void ***))v63[3])(&v63);
                    v32 = ((__int64 (__fastcall *)(void ***))v61[3])(&v61);
                    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                      (__int64)&v46,
                      *(_QWORD *)(v32 + 92));
                    PackageInfo = PushButtonReset::Path::Combine(&v45, &v46, v31);
                    ATL::CStringData::Release((ATL::CStringData *)(v46 - 24));
                    if ( PackageInfo >= 0 )
                    {
                      *(_QWORD *)(((__int64 (__fastcall *)(void ***))v63[3])(&v63) + 16) = 0;
                      *(_QWORD *)(((__int64 (__fastcall *)(void ***))v63[3])(&v63) + 8) = 0;
                      v33 = ((__int64 (__fastcall *)(void ***))v61[3])(&v61);
                      if ( *(_DWORD *)(v33 + 12) == 2 )
                      {
                        v36 = ((__int64 (__fastcall *)(void ***))v63[4])(&v63);
                        v37 = v55;
                      }
                      else
                      {
                        v34 = *(_DWORD *)(v33 + 12) - 8;
                        if ( *(_DWORD *)(v33 + 12) == 8 )
                        {
                          v38 = ((__int64 (__fastcall *)(void ***))v61[3])(&v61);
                          v39 = _wcsicmp(
                                  L"Microsoft-Windows-WinPE-LanguagePack-Package",
                                  *(const wchar_t **)(v38 + 116)) == 0;
                          v40 = (__int64 (__fastcall *)(void ***))v63[4];
                          if ( v39 )
                          {
                            v36 = v40(&v63);
                            v37 = v57;
                          }
                          else
                          {
                            v36 = v40(&v63);
                            v37 = v53;
                          }
                        }
                        else
                        {
                          v35 = (__int64 (__fastcall *)(void ***))v63[4];
                          if ( v34 == 1 )
                          {
                            v36 = v35(&v63);
                            v37 = v59;
                          }
                          else
                          {
                            v36 = v35(&v63);
                            v37 = v51;
                          }
                        }
                      }
                      v44 = v36;
                      ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
                        v37,
                        &v44);
                      v64 = 0;
                      v63 = &RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::`vftable';
                      RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::Release(&v63);
LABEL_37:
                      v61 = &RAII::CAutoDismDelete<_DismImageInfo *>::`vftable';
                      RAII::CAutoDismDelete<_DismPackageInfo *>::Release(&v61);
                      ++v23;
                      continue;
                    }
                    v41 = ((__int64 (__fastcall *)(void ***))v61[3])(&v61);
                    PushButtonReset::Logging::TraceErr(
                      2,
                      (unsigned int)PackageInfo,
                      "GetPackagesToBeInstalled",
                      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
                      435,
                      L"Failed to create package path %ws.",
                      *(_QWORD *)(v41 + 92));
                    v63 = &RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::`vftable';
                    RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::Release(&v63);
                  }
                }
                v61 = &RAII::CAutoDismDelete<_DismImageInfo *>::`vftable';
                RAII::CAutoDismDelete<_DismPackageInfo *>::Release(&v61);
              }
              break;
            }
            ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::~CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>(v51);
            ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::~CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>(v53);
            ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::~CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>(v55);
            ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::~CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>(v57);
            ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::~CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>(v59);
            v66 = &RAII::CAutoDismDelete<_DismImageInfo *>::`vftable';
            RAII::CAutoDismDelete<_DismPackageInfo *>::Release(&v66);
          }
          else
          {
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)v22,
              "GetPackagesToBeInstalled",
              "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
              409,
              L"Failed to get packages.");
            v66 = &RAII::CAutoDismDelete<_DismImageInfo *>::`vftable';
            RAII::CAutoDismDelete<_DismPackageInfo *>::Release(&v66);
          }
        }
        else
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)v19,
            "GetPackagesToBeInstalled",
            "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
            402,
            L"Failed to open DISM session");
        }
        v68[0] = &RAII::CAutoPbrDelete<PushButtonReset::DISMSession *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::DISMSession *>::Release(v68);
        ATL::CStringData::Release((ATL::CStringData *)(v45 - 24));
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)PackageInfo,
          "GetPackagesToBeInstalled",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
          398,
          L"Failed to get package dir.");
        ATL::CStringData::Release((ATL::CStringData *)(v45 - 24));
      }
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Packages,
        "GetPackagesToBeInstalled",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
        379,
        L"Failed to get packages.");
      v61 = &RAII::CAutoDismDelete<_DismImageInfo *>::`vftable';
      RAII::CAutoDismDelete<_DismPackageInfo *>::Release(&v61);
    }
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v7,
      "GetPackagesToBeInstalled",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
      369,
      L"Failed to open DISM session");
  }
LABEL_45:
  v65[0] = &RAII::CAutoPbrDelete<PushButtonReset::DISMSession *>::`vftable';
  RAII::CAutoPbrDelete<PushButtonReset::DISMSession *>::Release(v65);
  ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v47);
  return (unsigned int)PackageInfo;
}

```

## disassembly

```asm
0x180020c28  mov     [rsp-8+arg_18], rbx
0x180020c2d  push    rbp
0x180020c2e  push    rsi
0x180020c2f  push    rdi
0x180020c30  push    r12
0x180020c32  push    r13
0x180020c34  push    r14
0x180020c36  push    r15
0x180020c38  lea     rbp, [rsp-80h]
0x180020c3d  sub     rsp, 180h
0x180020c44  mov     rax, cs:__security_cookie
0x180020c4b  xor     rax, rsp
0x180020c4e  mov     [rbp+0B0h+var_40], rax
0x180020c52  mov     r15, r8
0x180020c55  mov     r12, rdx
0x180020c58  mov     rbx, rcx
0x180020c5b  xor     r13d, r13d
0x180020c5e  mov     [rsp+1B0h+var_158], r13
0x180020c63  mov     [rsp+1B0h+var_150], r13
0x180020c68  mov     [rsp+1B0h+var_148], r13
0x180020c6d  mov     [rsp+1B0h+var_140], r13d
0x180020c72  mov     [rbp+0B0h+var_70], r13
0x180020c76  lea     rdi, ??_7?$CAutoPbrDelete@PEAVDISMSession@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::DISMSession *>::`vftable'
0x180020c7d  mov     [rbp+0B0h+var_78], rdi
0x180020c81  lea     rcx, [rbp+0B0h+var_78]
0x180020c85  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180020c8a  mov     rdx, rax
0x180020c8d  mov     rcx, rbx
0x180020c90  call    ?Open@DISMSession@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::DISMSession::Open(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::DISMSession * *)
0x180020c95  mov     ebx, eax
0x180020c97  test    eax, eax
0x180020c99  jns     short loc_180020CCD
0x180020c9b  lea     rcx, aFailedToOpenDi_1; "Failed to open DISM session"
0x180020ca2  mov     [rsp+1B0h+var_188], rcx
0x180020ca7  mov     [rsp+1B0h+var_190], 171h
0x180020caf  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180020cb6  lea     r8, aGetpackagestob; "GetPackagesToBeInstalled"
0x180020cbd  mov     edx, eax
0x180020cbf  lea     ecx, [r13+2]
0x180020cc3  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180020cc8  jmp     loc_180021451
0x180020ccd  mov     [rbp+0B0h+var_90], r13
0x180020cd1  lea     r14, ??_7?$CAutoDismDelete@PEAU_DismImageInfo@@@RAII@@6B@; const RAII::CAutoDismDelete<_DismImageInfo *>::`vftable'
0x180020cd8  mov     [rbp+0B0h+var_98], r14
0x180020cdc  mov     [rbp+0B0h+var_48], r13d
0x180020ce0  lea     rcx, [rbp+0B0h+var_98]
0x180020ce4  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180020ce9  mov     rbx, rax
0x180020cec  mov     rcx, [rbp+0B0h+var_78]
0x180020cf0  mov     rax, [rcx+18h]
0x180020cf4  lea     rcx, [rbp+0B0h+var_78]
0x180020cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cfd  lea     r8, [rbp+0B0h+var_48]
0x180020d01  mov     rdx, rbx
0x180020d04  mov     ecx, [rax+4]
0x180020d07  call    cs:__imp_DismGetPackages
0x180020d0d  mov     ebx, eax
0x180020d0f  test    eax, eax
0x180020d11  jns     short loc_180020D54
0x180020d13  lea     rcx, aFailedToGetPac; "Failed to get packages."
0x180020d1a  mov     [rsp+1B0h+var_188], rcx
0x180020d1f  mov     [rsp+1B0h+var_190], 17Bh
0x180020d27  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180020d2e  lea     r8, aGetpackagestob; "GetPackagesToBeInstalled"
0x180020d35  mov     edx, eax
0x180020d37  mov     ecx, 2
0x180020d3c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180020d41  nop
0x180020d42  mov     [rbp+0B0h+var_98], r14
0x180020d46  lea     rcx, [rbp+0B0h+var_98]
0x180020d4a  call    ?Release@?$CAutoDismDelete@PEAU_DismPackageInfo@@@RAII@@UEAAXXZ; RAII::CAutoDismDelete<_DismPackageInfo *>::Release(void)
0x180020d4f  jmp     loc_180021451
0x180020d54  mov     esi, r13d
0x180020d57  lea     rbx, ??_7?$CAutoDismDelete@PEAU_DismImageInfo@@@RAII@@6B@; const RAII::CAutoDismDelete<_DismImageInfo *>::`vftable'
0x180020d5e  cmp     esi, [rbp+0B0h+var_48]
0x180020d61  jnb     loc_180020E9A
0x180020d67  mov     r14d, esi
0x180020d6a  shl     r14, 5
0x180020d6e  mov     rax, [rbp+0B0h+var_98]
0x180020d72  lea     rcx, [rbp+0B0h+var_98]
0x180020d76  mov     rax, [rax+20h]
0x180020d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d7f  cmp     dword ptr [rax+r14+8], 4
0x180020d85  jnz     loc_180020E14
0x180020d8b  mov     [rbp+0B0h+var_60], r13
0x180020d8f  mov     [rbp+0B0h+var_68], rbx
0x180020d93  lea     rcx, [rbp+0B0h+var_68]
0x180020d97  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180020d9c  mov     rdi, rax
0x180020d9f  mov     rcx, [rbp+0B0h+var_98]
0x180020da3  mov     rax, [rcx+20h]
0x180020da7  lea     rcx, [rbp+0B0h+var_98]
0x180020dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020db0  mov     rbx, [rax+r14]
0x180020db4  mov     rcx, [rbp+0B0h+var_78]
0x180020db8  mov     rax, [rcx+18h]
0x180020dbc  lea     rcx, [rbp+0B0h+var_78]
0x180020dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020dc5  mov     r9, rdi
0x180020dc8  mov     r8d, 1
0x180020dce  mov     rdx, rbx
0x180020dd1  mov     ecx, [rax+4]
0x180020dd4  call    cs:__imp_DismGetPackageInfo
0x180020dda  mov     ebx, eax
0x180020ddc  test    eax, eax
0x180020dde  js      short loc_180020E1B
0x180020de0  mov     rax, [rbp+0B0h+var_68]
0x180020de4  lea     rcx, [rbp+0B0h+var_68]
0x180020de8  mov     rax, [rax+18h]
0x180020dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020df1  mov     rdx, [rax+74h]
0x180020df5  lea     rcx, [rsp+1B0h+var_158]
0x180020dfa  call    ?Add@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA_KPEBG@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Add(ushort const *)
0x180020dff  nop
0x180020e00  lea     rbx, ??_7?$CAutoDismDelete@PEAU_DismImageInfo@@@RAII@@6B@; const RAII::CAutoDismDelete<_DismImageInfo *>::`vftable'
0x180020e07  mov     [rbp+0B0h+var_68], rbx
0x180020e0b  lea     rcx, [rbp+0B0h+var_68]
0x180020e0f  call    ?Release@?$CAutoDismDelete@PEAU_DismPackageInfo@@@RAII@@UEAAXXZ; RAII::CAutoDismDelete<_DismPackageInfo *>::Release(void)
0x180020e14  inc     esi
0x180020e16  jmp     loc_180020D5E
0x180020e1b  mov     rax, [rbp+0B0h+var_98]
0x180020e1f  lea     rcx, [rbp+0B0h+var_98]
0x180020e23  mov     rax, [rax+20h]
0x180020e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e2c  mov     rcx, [rax+r14]
0x180020e30  mov     [rsp+1B0h+var_180], rcx
0x180020e35  lea     rax, aFailedToGetPac_3; "Failed to get package info for package "...
0x180020e3c  mov     [rsp+1B0h+var_188], rax
0x180020e41  mov     [rsp+1B0h+var_190], 184h
0x180020e49  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180020e50  lea     r8, aGetpackagestob; "GetPackagesToBeInstalled"
0x180020e57  mov     edx, ebx
0x180020e59  mov     ecx, 2
0x180020e5e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180020e63  nop
0x180020e64  lea     rax, ??_7?$CAutoDismDelete@PEAU_DismImageInfo@@@RAII@@6B@; const RAII::CAutoDismDelete<_DismImageInfo *>::`vftable'
0x180020e6b  mov     [rbp+0B0h+var_68], rax
0x180020e6f  lea     rcx, [rbp+0B0h+var_68]
0x180020e73  call    ?Release@?$CAutoDismDelete@PEAU_DismPackageInfo@@@RAII@@UEAAXXZ; RAII::CAutoDismDelete<_DismPackageInfo *>::Release(void)
0x180020e78  nop
0x180020e79  lea     rax, ??_7?$CAutoDismDelete@PEAU_DismImageInfo@@@RAII@@6B@; const RAII::CAutoDismDelete<_DismImageInfo *>::`vftable'
0x180020e80  mov     [rbp+0B0h+var_98], rax
0x180020e84  lea     rcx, [rbp+0B0h+var_98]
0x180020e88  call    ?Release@?$CAutoDismDelete@PEAU_DismPackageInfo@@@RAII@@UEAAXXZ; RAII::CAutoDismDelete<_DismPackageInfo *>::Release(void)
0x180020e8d  nop
0x180020e8e  lea     rdi, ??_7?$CAutoPbrDelete@PEAVDISMSession@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::DISMSession *>::`vftable'
0x180020e95  jmp     loc_180021451
0x180020e9a  lea     r14, ??_7?$CAutoDismDelete@PEAU_DismImageInfo@@@RAII@@6B@; const RAII::CAutoDismDelete<_DismImageInfo *>::`vftable'
0x180020ea1  mov     [rbp+0B0h+var_98], r14
0x180020ea5  lea     rcx, [rbp+0B0h+var_98]
0x180020ea9  call    ?Release@?$CAutoDismDelete@PEAU_DismPackageInfo@@@RAII@@UEAAXXZ; RAII::CAutoDismDelete<_DismPackageInfo *>::Release(void)
0x180020eae  lea     rcx, [rsp+1B0h+var_168]
0x180020eb3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180020eb8  nop
0x180020eb9  lea     rdx, aWindowsServici; "\\windows\\servicing\\packages"
0x180020ec0  lea     rcx, [rsp+1B0h+var_160]
0x180020ec5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180020eca  nop
0x180020ecb  lea     r8, [rsp+1B0h+var_168]
0x180020ed0  lea     rdx, [rsp+1B0h+var_160]
0x180020ed5  mov     rcx, r12
0x180020ed8  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180020edd  mov     ebx, eax
0x180020edf  mov     rcx, [rsp+1B0h+var_160]
0x180020ee4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180020ee8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180020eed  test    ebx, ebx
0x180020eef  jns     short loc_180020F33
0x180020ef1  lea     rax, aFailedToGetPac_2; "Failed to get package dir."
0x180020ef8  mov     [rsp+1B0h+var_188], rax
0x180020efd  mov     [rsp+1B0h+var_190], 18Eh
0x180020f05  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180020f0c  lea     r8, aGetpackagestob; "GetPackagesToBeInstalled"
0x180020f13  mov     edx, ebx
0x180020f15  mov     ecx, 2
0x180020f1a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180020f1f  nop
0x180020f20  mov     rcx, [rsp+1B0h+var_168]
0x180020f25  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180020f29  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180020f2e  jmp     loc_180020E8E
0x180020f33  mov     [rbp+0B0h+var_50], r13
0x180020f37  lea     rdi, ??_7?$CAutoPbrDelete@PEAVDISMSession@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::DISMSession *>::`vftable'
0x180020f3e  mov     [rbp+0B0h+var_58], rdi
0x180020f42  lea     rcx, [rbp+0B0h+var_58]
0x180020f46  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180020f4b  mov     rdx, rax
0x180020f4e  mov     rcx, r12
0x180020f51  call    ?Open@DISMSession@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::DISMSession::Open(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::DISMSession * *)
0x180020f56  mov     ebx, eax
0x180020f58  test    eax, eax
0x180020f5a  jns     short loc_180020F90
0x180020f5c  lea     rcx, aFailedToOpenDi_1; "Failed to open DISM session"
0x180020f63  mov     [rsp+1B0h+var_188], rcx
0x180020f68  mov     [rsp+1B0h+var_190], 192h
0x180020f70  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180020f77  lea     r8, aGetpackagestob; "GetPackagesToBeInstalled"
0x180020f7e  mov     edx, eax
0x180020f80  mov     ecx, 2
0x180020f85  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180020f8a  nop
0x180020f8b  jmp     loc_180021434
0x180020f90  mov     [rbp+0B0h+var_60], r13
0x180020f94  mov     [rbp+0B0h+var_68], r14
0x180020f98  mov     [rbp+0B0h+var_48], r13d
0x180020f9c  lea     rcx, [rbp+0B0h+var_68]
0x180020fa0  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180020fa5  mov     rbx, rax
0x180020fa8  mov     rcx, [rbp+0B0h+var_58]
0x180020fac  mov     rax, [rcx+18h]
0x180020fb0  lea     rcx, [rbp+0B0h+var_58]
0x180020fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020fb9  lea     r8, [rbp+0B0h+var_48]
0x180020fbd  mov     rdx, rbx
0x180020fc0  mov     ecx, [rax+4]
0x180020fc3  call    cs:__imp_DismGetPackages
0x180020fc9  mov     ebx, eax
0x180020fcb  test    eax, eax
0x180020fcd  jns     short loc_180021010
0x180020fcf  lea     rcx, aFailedToGetPac; "Failed to get packages."
0x180020fd6  mov     [rsp+1B0h+var_188], rcx
0x180020fdb  mov     [rsp+1B0h+var_190], 199h
0x180020fe3  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180020fea  lea     r8, aGetpackagestob; "GetPackagesToBeInstalled"
0x180020ff1  mov     edx, eax
0x180020ff3  mov     ecx, 2
0x180020ff8  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180020ffd  nop
0x180020ffe  mov     [rbp+0B0h+var_68], r14
0x180021002  lea     rcx, [rbp+0B0h+var_68]
0x180021006  call    ?Release@?$CAutoDismDelete@PEAU_DismPackageInfo@@@RAII@@UEAAXXZ; RAII::CAutoDismDelete<_DismPackageInfo *>::Release(void)
0x18002100b  jmp     loc_180020F8B
0x180021010  mov     [rbp+0B0h+var_B8], r13
0x180021014  mov     [rbp+0B0h+var_B0], r13
0x180021018  mov     [rbp+0B0h+var_A8], r13
0x18002101c  mov     [rbp+0B0h+var_A0], r13d
0x180021020  mov     [rbp+0B0h+var_D8], r13
0x180021024  mov     [rbp+0B0h+var_D0], r13
0x180021028  mov     [rbp+0B0h+var_C8], r13
0x18002102c  mov     [rbp+0B0h+var_C0], r13d
0x180021030  mov     [rbp+0B0h+var_F8], r13
0x180021034  mov     [rbp+0B0h+var_F0], r13
0x180021038  mov     [rbp+0B0h+var_E8], r13
0x18002103c  mov     [rbp+0B0h+var_E0], r13d
0x180021040  mov     [rbp+0B0h+var_118], r13
0x180021044  mov     [rbp+0B0h+var_110], r13
0x180021048  mov     [rbp+0B0h+var_108], r13
0x18002104c  mov     [rbp+0B0h+var_100], r13d
0x180021050  mov     [rsp+1B0h+var_138], r13
0x180021055  mov     [rbp+0B0h+var_130], r13
0x180021059  mov     [rbp+0B0h+var_128], r13
0x18002105d  mov     [rbp+0B0h+var_120], r13d
0x180021061  mov     esi, r13d
0x180021064  lea     r12, ??_7?$CAutoPbrDelete@PEAUPACKAGE_INFO@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::`vftable'
0x18002106b  cmp     esi, [rbp+0B0h+var_48]
0x18002106e  jnb     loc_1800213A5
0x180021074  mov     [rbp+0B0h+var_90], r13
0x180021078  lea     rax, ??_7?$CAutoDismDelete@PEAU_DismImageInfo@@@RAII@@6B@; const RAII::CAutoDismDelete<_DismImageInfo *>::`vftable'
0x18002107f  mov     [rbp+0B0h+var_98], rax
0x180021083  lea     rcx, [rbp+0B0h+var_98]
0x180021087  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18002108c  mov     rdi, rax
0x18002108f  mov     r14d, esi
0x180021092  shl     r14, 5
0x180021096  mov     rcx, [rbp+0B0h+var_68]
0x18002109a  mov     rax, [rcx+20h]
0x18002109e  lea     rcx, [rbp+0B0h+var_68]
0x1800210a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210a7  mov     rbx, [rax+r14]
0x1800210ab  mov     rcx, [rbp+0B0h+var_58]
0x1800210af  mov     rax, [rcx+18h]
0x1800210b3  lea     rcx, [rbp+0B0h+var_58]
0x1800210b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210bc  mov     r9, rdi
0x1800210bf  mov     r8d, 1
0x1800210c5  mov     rdx, rbx
0x1800210c8  mov     ecx, [rax+4]
0x1800210cb  call    cs:__imp_DismGetPackageInfo
0x1800210d1  mov     ebx, eax
0x1800210d3  test    eax, eax
0x1800210d5  js      loc_180021346
0x1800210db  mov     rdi, r13
0x1800210de  cmp     rdi, [rsp+1B0h+var_150]
0x1800210e3  jnb     loc_18002128A
0x1800210e9  mov     rax, [rbp+0B0h+var_98]
0x1800210ed  lea     rcx, [rbp+0B0h+var_98]
0x1800210f1  mov     rax, [rax+18h]
0x1800210f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800210fa  mov     rbx, [rax+74h]
0x1800210fe  mov     rdx, rdi
0x180021101  lea     rcx, [rsp+1B0h+var_158]
0x180021106  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x18002110b  mov     rdx, rbx; String2
0x18002110e  mov     rcx, [rax]; String1
0x180021111  call    cs:__imp__wcsicmp
0x180021117  test    eax, eax
0x180021119  jz      short loc_180021120
0x18002111b  inc     rdi
0x18002111e  jmp     short loc_1800210DE
0x180021120  call    ??$PbrNew@UPACKAGE_INFO@WinREAgent@@$$V@@YAPEAUPACKAGE_INFO@WinREAgent@@XZ; PbrNew<WinREAgent::PACKAGE_INFO,>(void)
  ... truncated ...
```
