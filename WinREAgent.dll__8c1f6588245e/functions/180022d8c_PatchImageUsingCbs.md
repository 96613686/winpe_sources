# PatchImageUsingCbs

- ea: `0x180022d8c`
- end: `0x18002342f`
- name: `PatchImageUsingCbs`
- size: `1699`
- prototype: `__int64 __fastcall(const unsigned __int16 **, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180021590`

## callees

- `0x1800028f0`
- `0x1800049a4`
- `0x180004af8`
- `0x18000509c`
- `0x180005c00`
- `0x180005c70`
- `0x180005cc0`
- `0x180006828`
- `0x18000d6f0`
- `0x18000d92c`
- `0x180011a84`
- `0x18001f6e8`
- `0x18001fc04`
- `0x180022d8c`
- `0x1800234c0`
- `0x18002c904`
- `0x18002cb84`
- `0x18002cfb8`
- `0x18002d1f4`
- `0x18002d4b4`
- `0x18003717c`
- `0x180037344`
- `0x18004a898`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `ServicingCommon!CbsGetSsBinaryPathFromTargetImage` at `0x180022e71`
- `ServicingCommon!CbsGetSsBinaryPathFromTargetImage` at `0x180022e71`

## string_xrefs

- `0x180022e18`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180022e91`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180022f2b`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180023265`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x1800232f2`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x18002334d`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x1800233ef`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180022e04`: `Failed to create windows dir path.`
- `0x180022f17`: `Failed to create windows dir path.`
- `0x180022e7d`: `Failed to get servicing stack path.`
- `0x1800232a6`: `Failed to install package %ws.`
- `0x1800232de`: `Failed to check if package %ws needs to be installed.`
- `0x180023205`: `Packages to be Installed : %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PatchImageUsingCbs(const unsigned __int16 **a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v8; // ebx
  unsigned __int64 v9; // r14
  __int64 v11; // rax
  __int64 v12; // rbx
  int SsBinaryPathFromTargetImage; // edi
  int v14; // esi
  unsigned __int16 *v15; // rdi
  unsigned __int64 n; // r15
  _OWORD *v17; // rax
  CWinreCbsClient *v18; // r14
  const unsigned __int16 *v19; // rsi
  const unsigned __int16 *v20; // rax
  unsigned __int64 i; // r14
  CWinreCbsClient *v22; // rsi
  __int64 v23; // r8
  const unsigned __int16 **v24; // rax
  __int64 v25; // r8
  unsigned __int64 j; // r14
  CWinreCbsClient *v27; // rax
  __int64 v28; // r8
  CWinreCbsClient *v29; // rsi
  _QWORD *v30; // rax
  __int64 v31; // r8
  const unsigned __int16 ***v32; // rax
  int v33; // r8d
  __int64 v34; // r8
  unsigned __int64 k; // r14
  CWinreCbsClient *v36; // rsi
  __int64 v37; // r8
  _QWORD *v38; // rax
  __int64 v39; // r8
  const unsigned __int16 ***v40; // rax
  __int64 v41; // r8
  _QWORD *v42; // rax
  unsigned __int64 v43; // r15
  unsigned __int64 v44; // r14
  __int64 v45; // rdx
  __int64 v46; // r8
  unsigned __int64 m; // rcx
  unsigned __int64 v48; // r14
  _QWORD *v49; // rax
  __int64 v50; // r8
  _QWORD **v51; // rax
  _QWORD *v52; // rax
  __int64 v53; // r8
  _QWORD *v54; // rax
  __int64 v55; // r8
  _QWORD **v56; // rax
  const unsigned __int16 *v57; // [rsp+20h] [rbp-A1h]
  const unsigned __int16 *v58; // [rsp+28h] [rbp-99h]
  struct ICbsUIHandler *v59; // [rsp+30h] [rbp-91h]
  __int64 v60; // [rsp+30h] [rbp-91h]
  __int64 v61; // [rsp+30h] [rbp-91h]
  bool v62; // [rsp+40h] [rbp-81h] BYREF
  _BYTE v63[4]; // [rsp+44h] [rbp-7Dh] BYREF
  _OWORD *v64; // [rsp+48h] [rbp-79h] BYREF
  __int64 v65; // [rsp+50h] [rbp-71h] BYREF
  unsigned __int64 v66; // [rsp+58h] [rbp-69h]
  __int64 v67; // [rsp+60h] [rbp-61h]
  int v68; // [rsp+68h] [rbp-59h]
  __int64 v69; // [rsp+70h] [rbp-51h] BYREF
  unsigned __int16 *v70; // [rsp+78h] [rbp-49h] BYREF
  __int64 v71; // [rsp+80h] [rbp-41h] BYREF
  unsigned __int64 v72; // [rsp+88h] [rbp-39h]
  __int64 v73; // [rsp+90h] [rbp-31h]
  int v74; // [rsp+98h] [rbp-29h]
  const unsigned __int16 **v75; // [rsp+A0h] [rbp-21h]
  _QWORD v76[2]; // [rsp+A8h] [rbp-19h] BYREF
  _QWORD v77[2]; // [rsp+B8h] [rbp-9h] BYREF

  v75 = a1;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v69);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v64,
    L"\\windows\\");
  v8 = PushButtonReset::Path::Combine(a2, &v64, &v69);
  ATL::CStringData::Release((ATL::CStringData *)((char *)v64 - 24));
  v9 = 0;
  if ( v8 >= 0 )
  {
    v77[1] = 0;
    v77[0] = &RAII::CAutoHeapFree<unsigned short *>::`vftable';
    v11 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(v77);
    v12 = v69;
    SsBinaryPathFromTargetImage = CbsGetSsBinaryPathFromTargetImage(0, v69, &pszFormat, v11);
    if ( SsBinaryPathFromTargetImage >= 0 )
    {
      v63[0] = 0;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v70);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v64,
        L"\\windows\\");
      v14 = PushButtonReset::Path::Combine(a1, &v64, &v70);
      ATL::CStringData::Release((ATL::CStringData *)((char *)v64 - 24));
      v15 = v70;
      if ( v14 >= 0 )
      {
        v65 = 0;
        n = 0;
        v66 = 0;
        v67 = 0;
        v68 = 0;
        if ( *(_QWORD *)(a3 + 8) )
        {
          do
            ATL::CAtlArray<__int64,ATL::CElementTraits<__int64>>::Add(&v65, v9++);
          while ( v9 < *(_QWORD *)(a3 + 8) );
          n = v66;
        }
        while ( 1 )
        {
          if ( !n )
            goto LABEL_45;
          PushButtonReset::Logging::Trace(0, L"*********** Remaining packages %d*************\n", (unsigned int)n);
          v17 = operator new(0x30u);
          v64 = v17;
          if ( v17 )
          {
            *v17 = 0;
            v17[1] = 0;
            v17[2] = 0;
            *((_QWORD *)v17 + 1) = 0;
            *(_QWORD *)v17 = &RAII::CAutoRelease<ICbsSession *>::`vftable';
            *((_QWORD *)v17 + 3) = 0;
            *((_QWORD *)v17 + 2) = &RAII::CAutoRelease<ICbsSession *>::`vftable';
            *((_QWORD *)v17 + 5) = 0;
            *((_QWORD *)v17 + 4) = &RAII::CAutoRelease<ICbsSession *>::`vftable';
          }
          else
          {
            v17 = 0;
          }
          v76[1] = v17;
          v76[0] = &RAII::CAutoDelete<CWinreCbsClient *>::`vftable';
          if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(v76) )
            break;
          v18 = (CWinreCbsClient *)(*(__int64 (__fastcall **)(_QWORD *))(v76[0] + 24LL))(v76);
          v19 = *v75;
          v20 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD *))(v77[0] + 32LL))(v77);
          v14 = CWinreCbsClient::Initialize(v18, v20, v19, v15, v57, v58, v59);
          if ( v14 < 0 )
          {
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)v14,
              "PatchImageUsingCbs",
              "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
              246,
              L"Failed to initialize cbs client.");
            goto LABEL_44;
          }
          for ( i = 0; i < *(_QWORD *)(a4 + 8); ++i )
          {
            v22 = (CWinreCbsClient *)(*(__int64 (__fastcall **)(_QWORD *))(v76[0] + 24LL))(v76);
            v24 = (const unsigned __int16 **)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                                               a4,
                                               i,
                                               v23);
            v14 = CWinreCbsClient::AddSource(v22, *v24);
            if ( v14 < 0 )
            {
              v60 = *(_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                                 a4,
                                 i,
                                 v25);
              PushButtonReset::Logging::TraceErr(
                2,
                (unsigned int)v14,
                "PatchImageUsingCbs",
                "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
                251,
                L"Failed to add source %ws.",
                v60);
              goto LABEL_44;
            }
          }
          for ( j = 0; ; ++j )
          {
            v27 = (CWinreCbsClient *)(*(__int64 (__fastcall **)(_QWORD *))(v76[0] + 24LL))(v76);
            if ( j >= n )
              break;
            v29 = v27;
            v30 = (_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                              &v65,
                              j,
                              v28);
            v32 = (const unsigned __int16 ***)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                                                a3,
                                                *v30,
                                                v31);
            v14 = CWinreCbsClient::InstallPackage(v29, **v32, v33);
            if ( v14 < 0 )
            {
              v52 = (_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                                &v65,
                                j,
                                v34);
              v61 = **(_QWORD **)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                                   a3,
                                   *v52,
                                   v53);
              PushButtonReset::Logging::TraceErr(
                2,
                (unsigned int)v14,
                "PatchImageUsingCbs",
                "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
                257,
                L"Failed to install package %ws.",
                v61);
              goto LABEL_44;
            }
          }
          v14 = CWinreCbsClient::Finalize(v27);
          if ( v14 < 0 )
          {
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)v14,
              "PatchImageUsingCbs",
              "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
              261,
              L"Failed to finalize cbs session");
LABEL_44:
            v76[0] = &RAII::CAutoDelete<CWinreCbsClient *>::`vftable';
            RAII::CAutoDelete<CWinreCbsClient *>::Release(v76);
LABEL_45:
            ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::~CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>(&v65);
            goto LABEL_46;
          }
          v71 = 0;
          v72 = 0;
          v73 = 0;
          v74 = 0;
          for ( k = 0; k < n; ++k )
          {
            v62 = 0;
            v36 = (CWinreCbsClient *)(*(__int64 (__fastcall **)(_QWORD *))(v76[0] + 24LL))(v76);
            v38 = (_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                              &v65,
                              k,
                              v37);
            v40 = (const unsigned __int16 ***)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                                                a3,
                                                *v38,
                                                v39);
            v14 = CWinreCbsClient::CheckIfNeedsInstall(v36, **v40, &v62);
            if ( v14 < 0 )
            {
              v54 = (_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                                &v65,
                                k,
                                v41);
              v56 = (_QWORD **)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                                 a3,
                                 *v54,
                                 v55);
              PushButtonReset::Logging::TraceErr(
                2,
                (unsigned int)v14,
                "PatchImageUsingCbs",
                "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
                268,
                L"Failed to check if package %ws needs to be installed.",
                **v56);
              ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::~CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>(&v71);
              goto LABEL_44;
            }
            if ( v62 )
            {
              v42 = (_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                                &v65,
                                k,
                                v41);
              ATL::CAtlArray<__int64,ATL::CElementTraits<__int64>>::Add(&v71, *v42);
            }
          }
          ATL::CAtlArray<unsigned __int64,ATL::CElementTraits<unsigned __int64>>::SetCount(&v65, 0);
          v43 = v66;
          v44 = v72;
          if ( !(unsigned __int8)ATL::CAtlArray<unsigned __int64,ATL::CElementTraits<unsigned __int64>>::SetCount(
                                   &v65,
                                   v72 + v66) )
            ATL::AtlThrowImpl(-2147024882);
          v45 = v71;
          v46 = v65 + 8 * v43;
          for ( m = 0; m < v44; ++m )
            *(_QWORD *)(v46 + 8 * m) = *(_QWORD *)(v45 + 8 * m);
          v48 = 0;
          for ( n = v66; v48 < n; ++v48 )
          {
            v49 = (_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                              &v65,
                              v48,
                              v46);
            v51 = (_QWORD **)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                               a3,
                               *v49,
                               v50);
            PushButtonReset::Logging::Trace(0, L"Packages to be Installed : %ws", **v51);
          }
          ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::~CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>(&v71);
          v76[0] = &RAII::CAutoDelete<CWinreCbsClient *>::`vftable';
          RAII::CAutoDelete<CWinreCbsClient *>::Release(v76);
        }
        PushButtonReset::Logging::TraceErr(
          2,
          2147942414LL,
          "PatchImageUsingCbs",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
          243,
          L"Failed to allocate pCbsClient");
        v76[0] = &RAII::CAutoDelete<CWinreCbsClient *>::`vftable';
        RAII::CAutoDelete<CWinreCbsClient *>::Release(v76);
        ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::~CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>(&v65);
        v14 = -2147024882;
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v14,
          "PatchImageUsingCbs",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
          214,
          L"Failed to create windows dir path.");
      }
LABEL_46:
      ATL::CStringData::Release((ATL::CStringData *)(v15 - 12));
      ScopeGuardImplBase::SafeExecute_ScopeGuardImpl0__lambda_899927f386f77de8697426e28675e0ad_____(v63);
      v77[0] = &RAII::CAutoHeapFree<unsigned short *>::`vftable';
      RAII::CAutoPbrHeapFree<unsigned short *>::Release(v77);
      ATL::CStringData::Release((ATL::CStringData *)(v12 - 24));
      return (unsigned int)v14;
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)SsBinaryPathFromTargetImage,
        "PatchImageUsingCbs",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
        207,
        L"Failed to get servicing stack path.");
      v77[0] = &RAII::CAutoHeapFree<unsigned short *>::`vftable';
      RAII::CAutoPbrHeapFree<unsigned short *>::Release(v77);
      ATL::CStringData::Release((ATL::CStringData *)(v12 - 24));
      return (unsigned int)SsBinaryPathFromTargetImage;
    }
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v8,
      "PatchImageUsingCbs",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
      202,
      L"Failed to create windows dir path.");
    ATL::CStringData::Release((ATL::CStringData *)(v69 - 24));
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x180022d8c  push    rbp
0x180022d8e  push    rbx
0x180022d8f  push    rsi
0x180022d90  push    rdi
0x180022d91  push    r12
0x180022d93  push    r13
0x180022d95  push    r14
0x180022d97  push    r15
0x180022d99  lea     rbp, [rsp-17h]
0x180022d9e  sub     rsp, 0D8h
0x180022da5  mov     rax, cs:__security_cookie
0x180022dac  xor     rax, rsp
0x180022daf  mov     [rbp+4Fh+var_48], rax
0x180022db3  mov     r13, r9
0x180022db6  mov     r12, r8
0x180022db9  mov     rbx, rdx
0x180022dbc  mov     rsi, rcx
0x180022dbf  mov     [rbp+4Fh+var_70], rcx
0x180022dc3  lea     rcx, [rbp+4Fh+var_A0]
0x180022dc7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180022dcc  nop
0x180022dcd  lea     rdx, aWindows; "\\windows\\"
0x180022dd4  lea     rcx, [rbp+4Fh+var_C8]
0x180022dd8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180022ddd  nop
0x180022dde  lea     r8, [rbp+4Fh+var_A0]
0x180022de2  lea     rdx, [rbp+4Fh+var_C8]
0x180022de6  mov     rcx, rbx
0x180022de9  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180022dee  mov     ebx, eax
0x180022df0  mov     rcx, [rbp+4Fh+var_C8]
0x180022df4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180022df8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180022dfd  xor     r14d, r14d
0x180022e00  test    ebx, ebx
0x180022e02  jns     short loc_180022E46
0x180022e04  lea     rcx, aFailedToCreate_45; "Failed to create windows dir path."
0x180022e0b  mov     [rsp+110h+var_E8], rcx
0x180022e10  mov     dword ptr [rsp+110h+var_F0], 0CAh
0x180022e18  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180022e1f  lea     r8, aPatchimageusin; "PatchImageUsingCbs"
0x180022e26  mov     edx, ebx
0x180022e28  lea     ecx, [r14+2]
0x180022e2c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180022e31  nop
0x180022e32  mov     rcx, [rbp+4Fh+var_A0]
0x180022e36  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180022e3a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180022e3f  mov     eax, ebx
0x180022e41  jmp     loc_1800233BB
0x180022e46  mov     [rbp+4Fh+var_50], r14
0x180022e4a  lea     rax, ??_7?$CAutoHeapFree@PEAG@RAII@@6B@; const RAII::CAutoHeapFree<ushort *>::`vftable'
0x180022e51  mov     [rbp+4Fh+var_58], rax
0x180022e55  lea     rcx, [rbp+4Fh+var_58]
0x180022e59  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180022e5e  mov     r9, rax
0x180022e61  lea     r8, pszFormat
0x180022e68  mov     rbx, [rbp+4Fh+var_A0]
0x180022e6c  mov     rdx, rbx
0x180022e6f  xor     ecx, ecx
0x180022e71  call    cs:__imp_CbsGetSsBinaryPathFromTargetImage
0x180022e77  mov     edi, eax
0x180022e79  test    eax, eax
0x180022e7b  jns     short loc_180022ED1
0x180022e7d  lea     rax, aFailedToGetSer; "Failed to get servicing stack path."
0x180022e84  mov     [rsp+110h+var_E8], rax
0x180022e89  mov     dword ptr [rsp+110h+var_F0], 0CFh
0x180022e91  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180022e98  lea     r8, aPatchimageusin; "PatchImageUsingCbs"
0x180022e9f  mov     edx, edi
0x180022ea1  mov     ecx, 2
0x180022ea6  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180022eab  nop
0x180022eac  lea     rax, ??_7?$CAutoHeapFree@PEAG@RAII@@6B@; const RAII::CAutoHeapFree<ushort *>::`vftable'
0x180022eb3  mov     [rbp+4Fh+var_58], rax
0x180022eb7  lea     rcx, [rbp+4Fh+var_58]
0x180022ebb  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x180022ec0  nop
0x180022ec1  lea     rcx, [rbx-18h]; this
0x180022ec5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180022eca  mov     eax, edi
0x180022ecc  jmp     loc_1800233BB
0x180022ed1  mov     [rbp+4Fh+var_CC], r14b
0x180022ed5  lea     rcx, [rbp+4Fh+var_98]
0x180022ed9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180022ede  nop
0x180022edf  lea     rdx, aWindows; "\\windows\\"
0x180022ee6  lea     rcx, [rbp+4Fh+var_C8]
0x180022eea  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180022eef  nop
0x180022ef0  lea     r8, [rbp+4Fh+var_98]
0x180022ef4  lea     rdx, [rbp+4Fh+var_C8]
0x180022ef8  mov     rcx, rsi
0x180022efb  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180022f00  mov     esi, eax
0x180022f02  mov     rcx, [rbp+4Fh+var_C8]
0x180022f06  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180022f0a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180022f0f  mov     rdi, [rbp+4Fh+var_98]
0x180022f13  test    esi, esi
0x180022f15  jns     short loc_180022F4A
0x180022f17  lea     rcx, aFailedToCreate_45; "Failed to create windows dir path."
0x180022f1e  mov     [rsp+110h+var_E8], rcx
0x180022f23  mov     dword ptr [rsp+110h+var_F0], 0D6h
0x180022f2b  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180022f32  lea     r8, aPatchimageusin; "PatchImageUsingCbs"
0x180022f39  mov     edx, esi
0x180022f3b  mov     ecx, 2
0x180022f40  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180022f45  jmp     loc_180023387
0x180022f4a  mov     [rbp+4Fh+var_C0], r14
0x180022f4e  mov     r15, r14
0x180022f51  mov     [rbp+4Fh+var_B8], r14
0x180022f55  mov     [rbp+4Fh+var_B0], r14
0x180022f59  mov     [rbp+4Fh+var_A8], r14d
0x180022f5d  cmp     qword ptr [r12+8], 0
0x180022f63  jbe     short loc_180022F7F
0x180022f65  mov     rdx, r14
0x180022f68  lea     rcx, [rbp+4Fh+var_C0]
0x180022f6c  call    ?Add@?$CAtlArray@_JV?$CElementTraits@_J@ATL@@@ATL@@QEAA_K_J@Z; ATL::CAtlArray<__int64,ATL::CElementTraits<__int64>>::Add(__int64)
0x180022f71  inc     r14
0x180022f74  cmp     r14, [r12+8]
0x180022f79  jb      short loc_180022F65
0x180022f7b  mov     r15, [rbp+4Fh+var_B8]
0x180022f7f  xor     r14d, r14d
0x180022f82  test    r15, r15
0x180022f85  jz      loc_18002337D
0x180022f8b  mov     r8d, r15d
0x180022f8e  lea     rdx, aRemainingPacka; "*********** Remaining packages %d******"...
0x180022f95  xor     ecx, ecx
0x180022f97  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180022f9c  lea     ecx, [r14+30h]; Size
0x180022fa0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022fa5  mov     [rbp+4Fh+var_C8], rax
0x180022fa9  test    rax, rax
0x180022fac  jz      short loc_180022FEA
0x180022fae  xorps   xmm0, xmm0
0x180022fb1  movups  xmmword ptr [rax], xmm0
0x180022fb4  movups  xmmword ptr [rax+10h], xmm0
0x180022fb8  movups  xmmword ptr [rax+20h], xmm0
0x180022fbc  mov     [rax+8], r14
0x180022fc0  lea     rcx, ??_7?$CAutoRelease@PEAUICbsSession@@@RAII@@6B@; const RAII::CAutoRelease<ICbsSession *>::`vftable'
0x180022fc7  mov     [rax], rcx
0x180022fca  mov     [rax+18h], r14
0x180022fce  lea     rcx, ??_7?$CAutoRelease@PEAUICbsSession@@@RAII@@6B@; const RAII::CAutoRelease<ICbsSession *>::`vftable'
0x180022fd5  mov     [rax+10h], rcx
0x180022fd9  mov     [rax+28h], r14
0x180022fdd  lea     rcx, ??_7?$CAutoRelease@PEAUICbsSession@@@RAII@@6B@; const RAII::CAutoRelease<ICbsSession *>::`vftable'
0x180022fe4  mov     [rax+20h], rcx
0x180022fe8  jmp     short loc_180022FED
0x180022fea  mov     rax, r14
0x180022fed  mov     [rbp+4Fh+var_60], rax
0x180022ff1  lea     rsi, ??_7?$CAutoDelete@PEAVCWinreCbsClient@@@RAII@@6B@; const RAII::CAutoDelete<CWinreCbsClient *>::`vftable'
0x180022ff8  mov     [rbp+4Fh+var_68], rsi
0x180022ffc  lea     rcx, [rbp+4Fh+var_68]
0x180023000  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x180023005  test    al, al
0x180023007  jnz     loc_1800233DB
0x18002300d  mov     rax, [rbp+4Fh+var_68]
0x180023011  lea     rcx, [rbp+4Fh+var_68]
0x180023015  mov     rax, [rax+18h]
0x180023019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002301e  mov     r14, rax
0x180023021  mov     rax, [rbp+4Fh+var_70]
0x180023025  mov     rsi, [rax]
0x180023028  mov     rcx, [rbp+4Fh+var_58]
0x18002302c  mov     rax, [rcx+20h]
0x180023030  lea     rcx, [rbp+4Fh+var_58]
0x180023034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023039  mov     r9, rdi; unsigned __int16 *
0x18002303c  mov     r8, rsi; unsigned __int16 *
0x18002303f  mov     rdx, rax; unsigned __int16 *
0x180023042  mov     rcx, r14; this
0x180023045  call    ?Initialize@CWinreCbsClient@@QEAAJPEBG0000PEAUICbsUIHandler@@@Z; CWinreCbsClient::Initialize(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ICbsUIHandler *)
0x18002304a  mov     esi, eax
0x18002304c  test    eax, eax
0x18002304e  js      loc_180023339
0x180023054  xor     r14d, r14d
0x180023057  cmp     r14, [r13+8]
0x18002305b  jnb     short loc_180023096
0x18002305d  mov     rax, [rbp+4Fh+var_68]
0x180023061  lea     rcx, [rbp+4Fh+var_68]
0x180023065  mov     rax, [rax+18h]
0x180023069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002306e  mov     rsi, rax
0x180023071  mov     rdx, r14
0x180023074  mov     rcx, r13
0x180023077  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x18002307c  mov     rdx, [rax]; unsigned __int16 *
0x18002307f  mov     rcx, rsi; this
0x180023082  call    ?AddSource@CWinreCbsClient@@QEAAJPEBG@Z; CWinreCbsClient::AddSource(ushort const *)
0x180023087  mov     esi, eax
0x180023089  test    eax, eax
0x18002308b  js      loc_18002323E
0x180023091  inc     r14
0x180023094  jmp     short loc_180023057
0x180023096  xor     r14d, r14d
0x180023099  mov     rax, [rbp+4Fh+var_68]
0x18002309d  lea     rcx, [rbp+4Fh+var_68]
0x1800230a1  mov     rax, [rax+18h]
0x1800230a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800230aa  cmp     r14, r15
0x1800230ad  jnb     short loc_1800230E6
0x1800230af  mov     rsi, rax
0x1800230b2  mov     rdx, r14
0x1800230b5  lea     rcx, [rbp+4Fh+var_C0]
0x1800230b9  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x1800230be  mov     rdx, [rax]
0x1800230c1  mov     rcx, r12
0x1800230c4  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x1800230c9  mov     rdx, [rax]
0x1800230cc  mov     rdx, [rdx]; unsigned __int16 *
0x1800230cf  mov     rcx, rsi; this
0x1800230d2  call    ?InstallPackage@CWinreCbsClient@@QEAAJPEBGH@Z; CWinreCbsClient::InstallPackage(ushort const *,int)
0x1800230d7  mov     esi, eax
0x1800230d9  test    eax, eax
0x1800230db  js      loc_180023284
0x1800230e1  inc     r14
0x1800230e4  jmp     short loc_180023099
0x1800230e6  mov     rcx, rax; this
0x1800230e9  call    ?Finalize@CWinreCbsClient@@QEAAJXZ; CWinreCbsClient::Finalize(void)
0x1800230ee  mov     esi, eax
0x1800230f0  test    eax, eax
0x1800230f2  js      loc_180023323
0x1800230f8  mov     [rbp+4Fh+var_90], 0
0x180023100  mov     [rbp+4Fh+var_88], 0
0x180023108  mov     [rbp+4Fh+var_80], 0
0x180023110  mov     [rbp+4Fh+var_78], 0
0x180023117  xor     r14d, r14d
0x18002311a  cmp     r14, r15
0x18002311d  jnb     short loc_180023190
0x18002311f  mov     [rsp+110h+var_D0], 0
0x180023124  mov     rax, [rbp+4Fh+var_68]
0x180023128  lea     rcx, [rbp+4Fh+var_68]
0x18002312c  mov     rax, [rax+18h]
0x180023130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023135  mov     rsi, rax
0x180023138  mov     rdx, r14
0x18002313b  lea     rcx, [rbp+4Fh+var_C0]
0x18002313f  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x180023144  mov     rdx, [rax]
0x180023147  mov     rcx, r12
0x18002314a  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x18002314f  mov     rdx, [rax]
0x180023152  lea     r8, [rsp+110h+var_D0]; bool *
0x180023157  mov     rdx, [rdx]; unsigned __int16 *
0x18002315a  mov     rcx, rsi; this
0x18002315d  call    ?CheckIfNeedsInstall@CWinreCbsClient@@QEAAJPEBGPEA_N@Z; CWinreCbsClient::CheckIfNeedsInstall(ushort const *,bool *)
0x180023162  mov     esi, eax
0x180023164  test    eax, eax
0x180023166  js      loc_1800232BC
0x18002316c  cmp     [rsp+110h+var_D0], 0
0x180023171  jz      short loc_18002318B
0x180023173  mov     rdx, r14
0x180023176  lea     rcx, [rbp+4Fh+var_C0]
0x18002317a  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x18002317f  mov     rdx, [rax]
0x180023182  lea     rcx, [rbp+4Fh+var_90]
0x180023186  call    ?Add@?$CAtlArray@_JV?$CElementTraits@_J@ATL@@@ATL@@QEAA_K_J@Z; ATL::CAtlArray<__int64,ATL::CElementTraits<__int64>>::Add(__int64)
0x18002318b  inc     r14
0x18002318e  jmp     short loc_18002311A
0x180023190  xor     edx, edx
0x180023192  lea     rcx, [rbp+4Fh+var_C0]
0x180023196  call    ?SetCount@?$CAtlArray@_KV?$CElementTraits@_K@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<unsigned __int64,ATL::CElementTraits<unsigned __int64>>::SetCount(unsigned __int64,int)
0x18002319b  nop
0x18002319c  mov     r15, [rbp+4Fh+var_B8]
0x1800231a0  mov     r14, [rbp+4Fh+var_88]
0x1800231a4  lea     rdx, [r14+r15]
0x1800231a8  lea     rcx, [rbp+4Fh+var_C0]
0x1800231ac  call    ?SetCount@?$CAtlArray@_KV?$CElementTraits@_K@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<unsigned __int64,ATL::CElementTraits<unsigned __int64>>::SetCount(unsigned __int64,int)
0x1800231b1  test    al, al
0x1800231b3  jz      loc_180023318
0x1800231b9  mov     rdx, [rbp+4Fh+var_90]
0x1800231bd  mov     rax, [rbp+4Fh+var_C0]
0x1800231c1  lea     r8, [rax+r15*8]
0x1800231c5  xor     ecx, ecx
0x1800231c7  test    r14, r14
0x1800231ca  jz      short loc_1800231DC
0x1800231cc  mov     rax, [rdx+rcx*8]
0x1800231d0  mov     [r8+rcx*8], rax
0x1800231d4  inc     rcx
0x1800231d7  cmp     rcx, r14
0x1800231da  jb      short loc_1800231CC
0x1800231dc  xor     r14d, r14d
0x1800231df  mov     r15, [rbp+4Fh+var_B8]
0x1800231e3  test    r15, r15
0x1800231e6  jz      short loc_18002321B
0x1800231e8  mov     rdx, r14
0x1800231eb  lea     rcx, [rbp+4Fh+var_C0]
0x1800231ef  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x1800231f4  mov     rdx, [rax]
0x1800231f7  mov     rcx, r12
0x1800231fa  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x1800231ff  mov     r8, [rax]
0x180023202  mov     r8, [r8]
0x180023205  lea     rdx, aPackagesToBeIn; "Packages to be Installed : %ws"
0x18002320c  xor     ecx, ecx
0x18002320e  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180023213  inc     r14
0x180023216  cmp     r14, r15
  ... truncated ...
```
