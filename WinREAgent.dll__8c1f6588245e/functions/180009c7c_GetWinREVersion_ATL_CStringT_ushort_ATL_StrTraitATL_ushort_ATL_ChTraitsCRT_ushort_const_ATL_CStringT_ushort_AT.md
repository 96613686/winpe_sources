# GetWinREVersion(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)

- ea: `0x180009c7c`
- end: `0x180009fd1`
- name: `?GetWinREVersion@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00PEAV12@@Z`
- size: `853`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180007570`
- `0x180012050`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x180005cc0`
- `0x1800074b8`
- `0x1800089d0`
- `0x180009c7c`
- `0x18000d570`
- `0x18000d640`
- `0x18000d92c`
- `0x180011ef4`
- `0x18003717c`
- `0x180037344`
- `0x18004bb04`
- `0x18004c2b0`
- `0x18004d1fc`
- `0x180050390`
- `0x18006f010`

## import_xrefs

- `DismApi!DismGetImageInfo` at `0x180009e0e`
- `DismApi!DismGetImageInfo` at `0x180009e0e`

## string_xrefs

- `0x180009cba`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180009cfc`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180009ce6`: `GetWinREVersion: WinRE path [%s]`
- `0x180009d11`: `GetWinREVersion: Scratch directory didn't exist, create it`
- `0x180009d5b`: `Failed to create [%s]`
- `0x180009db4`: `Failed to open DISM session`
- `0x180009e36`: `GetWinREVersion: Deleting the scratch directory`
- `0x180009e58`: `Failed to delete [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetWinREVersion(_QWORD *a1, __int64 a2, __int64 *a3, _QWORD *a4)
{
  char v8; // r13
  int v9; // r14d
  __int64 v10; // rax
  int ImageInfo; // r14d
  __int64 v12; // rax
  const WCHAR *v13; // rdx
  int v14; // eax
  int v15; // esi
  int v16; // edi
  unsigned int v17; // ebx
  __int64 v18; // rax
  LPCWSTR v19; // rbx
  ATL::CStringData *v20; // rsi
  int *v21; // rdi
  __int64 v22; // rbx
  __int64 v23; // [rsp+20h] [rbp-50h]
  __int64 v24; // [rsp+28h] [rbp-48h]
  LPCWSTR v25; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v26[2]; // [rsp+48h] [rbp-28h] BYREF
  _QWORD v27[3]; // [rsp+58h] [rbp-18h] BYREF
  int v29; // [rsp+C8h] [rbp+58h] BYREF

  if ( a4 )
  {
    v8 = 0;
    PushButtonReset::Logging::Trace(0, L"GetWinREVersion: WinRE path [%s]", *a1);
    if ( !(unsigned __int8)PushButtonReset::Directory::Exists(a3) )
    {
      v8 = 1;
      PushButtonReset::Logging::Trace(0, L"GetWinREVersion: Scratch directory didn't exist, create it");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v25,
        (__int64)&pszFormat);
      v9 = PushButtonReset::Directory::Create(a3, 0, &v25);
      ATL::CStringData::Release((ATL::CStringData *)(v25 - 12));
      if ( v9 < 0 )
        PushButtonReset::Logging::TraceErr(
          1,
          (unsigned int)v9,
          "GetWinREVersion",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          1533,
          L"Failed to create [%s]",
          *a3);
    }
    v27[1] = 0;
    v27[0] = &RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::`vftable';
    v10 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v27);
    ImageInfo = PushButtonReset::DismAutoShutdown::Create(a2, a3, v10);
    if ( ImageInfo >= 0 )
    {
      v26[1] = 0;
      v26[0] = &RAII::CAutoDismDelete<_DismImageInfo *>::`vftable';
      v29 = 0;
      v12 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v26);
      ImageInfo = DismGetImageInfo(*a1, v12, &v29);
      if ( ImageInfo >= 0 && !v29 )
        ImageInfo = -2147467259;
      RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::Release(v27);
      if ( v8 )
      {
        PushButtonReset::Logging::Trace(0, L"GetWinREVersion: Deleting the scratch directory");
        v14 = PushButtonReset::Directory::Delete(a3, v13);
        if ( v14 < 0 )
          PushButtonReset::Logging::TraceErr(
            1,
            (unsigned int)v14,
            "GetWinREVersion",
            "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
            1559,
            L"Failed to delete [%s]",
            *a3);
      }
      if ( ImageInfo >= 0 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v25);
        v15 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD *))(v26[0] + 32LL))(v26) + 96);
        v16 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD *))(v26[0] + 32LL))(v26) + 92);
        v17 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD *))(v26[0] + 32LL))(v26) + 88);
        v18 = (*(__int64 (__fastcall **)(_QWORD *))(v26[0] + 32LL))(v26);
        LODWORD(v24) = v15;
        LODWORD(v23) = v16;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v25,
          L"%u.%u.%u.%u",
          *(unsigned int *)(v18 + 84),
          v17,
          v23,
          v24);
        v19 = v25;
        PushButtonReset::Logging::Trace(0, L"GetWinREVersion: Version [%s]", v25);
        v20 = (ATL::CStringData *)(v19 - 12);
        v21 = (int *)(*a4 - 24LL);
        if ( v19 - 12 != (LPCWSTR)v21 )
        {
          if ( v21[4] >= 0 && *(_QWORD *)v20 == *(_QWORD *)v21 )
          {
            v22 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v19 - 12);
            ATL::CStringData::Release((ATL::CStringData *)v21);
            *a4 = v22 + 24;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(a4, v19, *((unsigned int *)v19 - 4));
          }
        }
        ATL::CStringData::Release(v20);
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)ImageInfo,
          "GetWinREVersion",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          1565,
          L"Failed to get image info");
      }
      v26[0] = &RAII::CAutoDismDelete<_DismImageInfo *>::`vftable';
      RAII::CAutoDismDelete<_DismPackageInfo *>::Release(v26);
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)ImageInfo,
        "GetWinREVersion",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        1540,
        L"Failed to open DISM session");
    }
    v27[0] = &RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::Release(v27);
    return (unsigned int)ImageInfo;
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942487LL,
      "GetWinREVersion",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      1520,
      L"Invalid argument");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180009c7c  mov     [rsp-38h+arg_0], rbx
0x180009c81  mov     [rsp-38h+arg_8], rdx
0x180009c86  push    rbp
0x180009c87  push    rsi
0x180009c88  push    rdi
0x180009c89  push    r12
0x180009c8b  push    r13
0x180009c8d  push    r14
0x180009c8f  push    r15
0x180009c91  mov     rbp, rsp
0x180009c94  sub     rsp, 70h
0x180009c98  mov     r15, r9
0x180009c9b  mov     rsi, r8
0x180009c9e  mov     r12, rcx
0x180009ca1  test    r9, r9
0x180009ca4  jnz     short loc_180009CE0
0x180009ca6  lea     rax, aInvalidArgumen; "Invalid argument"
0x180009cad  mov     [rsp+70h+var_48], rax
0x180009cb2  mov     dword ptr [rsp+70h+var_50], 5F0h
0x180009cba  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180009cc1  lea     r8, aGetwinreversio_4; "GetWinREVersion"
0x180009cc8  mov     edx, 80070057h
0x180009ccd  lea     ecx, [r15+2]
0x180009cd1  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180009cd6  mov     eax, 80070057h
0x180009cdb  jmp     loc_180009FB9
0x180009ce0  xor     r13b, r13b
0x180009ce3  mov     r8, [rcx]
0x180009ce6  lea     rdx, aGetwinreversio_5; "GetWinREVersion: WinRE path [%s]"
0x180009ced  xor     ecx, ecx
0x180009cef  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180009cf4  mov     rcx, rsi
0x180009cf7  call    ?Exists@Directory@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Directory::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180009cfc  lea     rbx, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180009d03  lea     rdi, aGetwinreversio_4; "GetWinREVersion"
0x180009d0a  test    al, al
0x180009d0c  jnz     short loc_180009D82
0x180009d0e  mov     r13b, 1
0x180009d11  lea     rdx, aGetwinreversio_2; "GetWinREVersion: Scratch directory didn"...
0x180009d18  xor     ecx, ecx
0x180009d1a  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180009d1f  lea     rdx, pszFormat
0x180009d26  lea     rcx, [rbp+var_30]
0x180009d2a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180009d2f  nop
0x180009d30  lea     r8, [rbp+var_30]
0x180009d34  xor     edx, edx
0x180009d36  mov     rcx, rsi
0x180009d39  call    ?Create@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N0@Z; PushButtonReset::Directory::Create(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180009d3e  mov     r14d, eax
0x180009d41  mov     rcx, [rbp+var_30]
0x180009d45  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180009d49  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180009d4e  test    r14d, r14d
0x180009d51  jns     short loc_180009D82
0x180009d53  mov     rcx, [rsi]
0x180009d56  mov     [rsp+70h+var_40], rcx
0x180009d5b  lea     rax, aFailedToCreate_3; "Failed to create [%s]"
0x180009d62  mov     [rsp+70h+var_48], rax
0x180009d67  mov     dword ptr [rsp+70h+var_50], 5FDh
0x180009d6f  mov     r9, rbx
0x180009d72  mov     r8, rdi
0x180009d75  mov     edx, r14d
0x180009d78  mov     ecx, 1
0x180009d7d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180009d82  mov     [rbp+var_10], 0
0x180009d8a  lea     rax, ??_7?$CAutoPbrDelete@PEAVDismAutoShutdown@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::`vftable'
0x180009d91  mov     [rbp+var_18], rax
0x180009d95  lea     rcx, [rbp+var_18]
0x180009d99  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180009d9e  mov     r8, rax
0x180009da1  mov     rdx, rsi
0x180009da4  mov     rcx, [rbp+arg_8]
0x180009da8  call    ?Create@DismAutoShutdown@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAPEAV12@@Z; PushButtonReset::DismAutoShutdown::Create(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::DismAutoShutdown * *)
0x180009dad  mov     r14d, eax
0x180009db0  test    eax, eax
0x180009db2  jns     short loc_180009DE0
0x180009db4  lea     rax, aFailedToOpenDi_1; "Failed to open DISM session"
0x180009dbb  mov     [rsp+70h+var_48], rax
0x180009dc0  mov     dword ptr [rsp+70h+var_50], 604h
0x180009dc8  mov     r9, rbx
0x180009dcb  mov     r8, rdi
0x180009dce  mov     edx, r14d
0x180009dd1  mov     ecx, 2
0x180009dd6  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180009ddb  jmp     loc_180009FA2
0x180009de0  mov     [rbp+var_20], 0
0x180009de8  lea     rax, ??_7?$CAutoDismDelete@PEAU_DismImageInfo@@@RAII@@6B@; const RAII::CAutoDismDelete<_DismImageInfo *>::`vftable'
0x180009def  mov     [rbp+var_28], rax
0x180009df3  mov     [rbp+arg_18], 0
0x180009dfa  lea     rcx, [rbp+var_28]
0x180009dfe  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180009e03  lea     r8, [rbp+arg_18]
0x180009e07  mov     rdx, rax
0x180009e0a  mov     rcx, [r12]
0x180009e0e  call    cs:__imp_DismGetImageInfo
0x180009e14  mov     r14d, eax
0x180009e17  test    eax, eax
0x180009e19  js      short loc_180009E28
0x180009e1b  mov     eax, 80004005h
0x180009e20  cmp     [rbp+arg_18], 0
0x180009e24  cmovz   r14d, eax
0x180009e28  lea     rcx, [rbp+var_18]
0x180009e2c  call    ?Release@?$CAutoPbrDelete@PEAVDismAutoShutdown@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::Release(void)
0x180009e31  test    r13b, r13b
0x180009e34  jz      short loc_180009E7E
0x180009e36  lea     rdx, aGetwinreversio_3; "GetWinREVersion: Deleting the scratch d"...
0x180009e3d  xor     ecx, ecx
0x180009e3f  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180009e44  mov     rcx, rsi
0x180009e47  call    ?Delete@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUProgressCallback@2@@Z; PushButtonReset::Directory::Delete(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::ProgressCallback *)
0x180009e4c  test    eax, eax
0x180009e4e  jns     short loc_180009E7E
0x180009e50  mov     rdx, [rsi]
0x180009e53  mov     [rsp+70h+var_40], rdx
0x180009e58  lea     rdx, aFailedToDelete_19; "Failed to delete [%s]"
0x180009e5f  mov     [rsp+70h+var_48], rdx
0x180009e64  mov     dword ptr [rsp+70h+var_50], 617h
0x180009e6c  mov     r9, rbx
0x180009e6f  mov     r8, rdi
0x180009e72  mov     edx, eax
0x180009e74  mov     ecx, 1
0x180009e79  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180009e7e  test    r14d, r14d
0x180009e81  jns     short loc_180009EAF
0x180009e83  lea     rax, aFailedToGetIma_0; "Failed to get image info"
0x180009e8a  mov     [rsp+70h+var_48], rax
0x180009e8f  mov     dword ptr [rsp+70h+var_50], 61Dh
0x180009e97  mov     r9, rbx
0x180009e9a  mov     r8, rdi
0x180009e9d  mov     edx, r14d
0x180009ea0  mov     ecx, 2
0x180009ea5  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180009eaa  jmp     loc_180009F8D
0x180009eaf  lea     rcx, [rbp+var_30]
0x180009eb3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180009eb8  nop
0x180009eb9  mov     rax, [rbp+var_28]
0x180009ebd  lea     rcx, [rbp+var_28]
0x180009ec1  mov     rax, [rax+20h]
0x180009ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009eca  mov     esi, [rax+60h]
0x180009ecd  mov     rax, [rbp+var_28]
0x180009ed1  lea     rcx, [rbp+var_28]
0x180009ed5  mov     rax, [rax+20h]
0x180009ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ede  mov     edi, [rax+5Ch]
0x180009ee1  mov     rax, [rbp+var_28]
0x180009ee5  lea     rcx, [rbp+var_28]
0x180009ee9  mov     rax, [rax+20h]
0x180009eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ef2  mov     ebx, [rax+58h]
0x180009ef5  mov     rax, [rbp+var_28]
0x180009ef9  lea     rcx, [rbp+var_28]
0x180009efd  mov     rax, [rax+20h]
0x180009f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f06  mov     dword ptr [rsp+70h+var_48], esi
0x180009f0a  mov     dword ptr [rsp+70h+var_50], edi
0x180009f0e  mov     r9d, ebx
0x180009f11  mov     r8d, [rax+54h]
0x180009f15  lea     rdx, aUUUU; "%u.%u.%u.%u"
0x180009f1c  lea     rcx, [rbp+var_30]
0x180009f20  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180009f25  mov     rbx, [rbp+var_30]
0x180009f29  mov     r8, rbx
0x180009f2c  lea     rdx, aGetwinreversio_0; "GetWinREVersion: Version [%s]"
0x180009f33  xor     ecx, ecx
0x180009f35  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180009f3a  lea     rsi, [rbx-18h]
0x180009f3e  mov     rdi, [r15]
0x180009f41  add     rdi, 0FFFFFFFFFFFFFFE8h
0x180009f45  cmp     rsi, rdi
0x180009f48  jz      short loc_180009F84
0x180009f4a  cmp     dword ptr [rdi+10h], 0
0x180009f4e  jl      short loc_180009F74
0x180009f50  mov     rax, [rdi]
0x180009f53  cmp     [rsi], rax
0x180009f56  jnz     short loc_180009F74
0x180009f58  mov     rcx, rsi
0x180009f5b  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180009f60  mov     rbx, rax
0x180009f63  mov     rcx, rdi; this
0x180009f66  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180009f6b  lea     rax, [rbx+18h]
0x180009f6f  mov     [r15], rax
0x180009f72  jmp     short loc_180009F84
0x180009f74  mov     r8d, [rbx-10h]
0x180009f78  mov     rdx, rbx
0x180009f7b  mov     rcx, r15
0x180009f7e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180009f83  nop
0x180009f84  mov     rcx, rsi; this
0x180009f87  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180009f8c  nop
0x180009f8d  lea     rax, ??_7?$CAutoDismDelete@PEAU_DismImageInfo@@@RAII@@6B@; const RAII::CAutoDismDelete<_DismImageInfo *>::`vftable'
0x180009f94  mov     [rbp+var_28], rax
0x180009f98  lea     rcx, [rbp+var_28]
0x180009f9c  call    ?Release@?$CAutoDismDelete@PEAU_DismPackageInfo@@@RAII@@UEAAXXZ; RAII::CAutoDismDelete<_DismPackageInfo *>::Release(void)
0x180009fa1  nop
0x180009fa2  lea     rax, ??_7?$CAutoPbrDelete@PEAVDismAutoShutdown@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::`vftable'
0x180009fa9  mov     [rbp+var_18], rax
0x180009fad  lea     rcx, [rbp+var_18]
0x180009fb1  call    ?Release@?$CAutoPbrDelete@PEAVDismAutoShutdown@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::DismAutoShutdown *>::Release(void)
0x180009fb6  mov     eax, r14d
0x180009fb9  mov     rbx, [rsp+70h+arg_0]
0x180009fc1  add     rsp, 70h
0x180009fc5  pop     r15
0x180009fc7  pop     r14
0x180009fc9  pop     r13
0x180009fcb  pop     r12
0x180009fcd  pop     rdi
0x180009fce  pop     rsi
0x180009fcf  pop     rbp
0x180009fd0  retn
```
