# WinREAgent::CreateExecutionContext(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *,WinREAgent::ExecutionContext * *)

- ea: `0x18001e51c`
- end: `0x18001eb53`
- name: `?CreateExecutionContext@WinREAgent@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEAPEAVExecutionContext@1@@Z`
- size: `1591`
- prototype: ``
- caller_count: `5`
- callee_count: `21`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000dcc8`
- `0x18000f254`
- `0x180011118`
- `0x180018820`
- `0x1800191d0`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x180005c00`
- `0x180005cc0`
- `0x1800074b8`
- `0x18000d6f0`
- `0x18000d92c`
- `0x180011ef4`
- `0x18001b1c0`
- `0x18001e170`
- `0x18001e51c`
- `0x18001f0e4`
- `0x18001f194`
- `0x18001f2c4`
- `0x180037344`
- `0x18004e5a4`
- `0x1800536bc`
- `0x180053830`
- `0x180053afc`
- `0x18006c690`
- `0x18006f010`

## string_xrefs

- `0x18001e6cf`: `Failed to build log path`
- `0x18001e5d9`: `Failed to read WinRE configuration`
- `0x18001e640`: `Failed to read WinRE configuration`
- `0x18001ea1b`: `Failed to get winre path`
- `0x18001e588`: `base\diagnosis\srt\winreagent\lib\operations\src\executioncontext.cpp`
- `0x18001e5ed`: `base\diagnosis\srt\winreagent\lib\operations\src\executioncontext.cpp`
- `0x18001e686`: `base\diagnosis\srt\winreagent\lib\operations\src\executioncontext.cpp`
- `0x18001e6e3`: `base\diagnosis\srt\winreagent\lib\operations\src\executioncontext.cpp`
- `0x18001e73d`: `base\diagnosis\srt\winreagent\lib\operations\src\executioncontext.cpp`
- `0x18001e797`: `base\diagnosis\srt\winreagent\lib\operations\src\executioncontext.cpp`
- `0x18001ea2f`: `base\diagnosis\srt\winreagent\lib\operations\src\executioncontext.cpp`
- `0x18001e58f`: `WinREAgent::CreateExecutionContext`
- `0x18001e5f4`: `WinREAgent::CreateExecutionContext`
- `0x18001e68d`: `WinREAgent::CreateExecutionContext`
- `0x18001e6ea`: `WinREAgent::CreateExecutionContext`
- `0x18001e744`: `WinREAgent::CreateExecutionContext`
- `0x18001e79e`: `WinREAgent::CreateExecutionContext`
- `0x18001ea36`: `WinREAgent::CreateExecutionContext`
- `0x18001e729`: `Failed to build scratch path`
- `0x18001e783`: `Failed to build backup path`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall WinREAgent::CreateExecutionContext(__int64 *a1, __int64 a2, __int64 *a3)
{
  int Volume; // edi
  struct PushButtonReset::WindowsRE::Config **v6; // rax
  struct PushButtonReset::WindowsRE::Config **v7; // rbx
  _QWORD *v8; // r14
  __int64 v9; // rdx
  int *v10; // rcx
  int *v11; // rsi
  __int64 v12; // rbx
  _QWORD *v13; // r14
  ATL::CStringData *v14; // r13
  int *v15; // rsi
  __int64 v16; // rbx
  bool v17; // bl
  _QWORD *v18; // r14
  _QWORD *v19; // rcx
  int *v20; // rsi
  __int64 v21; // rbx
  _QWORD *v22; // r14
  ATL::CStringData *v23; // r12
  int *v24; // rsi
  __int64 v25; // rbx
  _QWORD *v26; // r14
  ATL::CStringData *v27; // r15
  int *v28; // rsi
  __int64 v29; // rbx
  __int64 v30; // rax
  _QWORD *v31; // rcx
  ATL::CStringData *v32; // r14
  int *v33; // rsi
  __int64 v34; // rbx
  __int64 v35; // rax
  __int64 v37; // [rsp+30h] [rbp-49h] BYREF
  __int64 v38; // [rsp+38h] [rbp-41h] BYREF
  __int64 v39; // [rsp+40h] [rbp-39h] BYREF
  __int64 v40; // [rsp+48h] [rbp-31h] BYREF
  __int64 v41; // [rsp+50h] [rbp-29h] BYREF
  ATL::CStringData *v42; // [rsp+58h] [rbp-21h]
  _QWORD *v43; // [rsp+60h] [rbp-19h]
  __int64 *v44; // [rsp+68h] [rbp-11h]
  _QWORD v45[2]; // [rsp+70h] [rbp-9h] BYREF
  void **v46; // [rsp+80h] [rbp+7h] BYREF
  __int64 v47; // [rsp+88h] [rbp+Fh]

  v44 = a3;
  v47 = PbrNew<WinREAgent::ExecutionContext,>();
  v46 = &RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::`vftable';
  if ( !(unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!((__int64 *)&v46) )
  {
    v45[1] = 0;
    v45[0] = &RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable';
    v6 = (struct PushButtonReset::WindowsRE::Config **)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v45);
    if ( a2 )
    {
      v7 = v6;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v38,
        a2);
      Volume = PushButtonReset::WindowsRE::OpenConfig(&v38, v7);
      ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
      if ( Volume < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Volume,
          "WinREAgent::CreateExecutionContext",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\executioncontext.cpp",
          87,
          L"Failed to read WinRE configuration");
        goto LABEL_6;
      }
    }
    else
    {
      Volume = PushButtonReset::WindowsRE::OpenConfig(v6);
      if ( Volume < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Volume,
          "WinREAgent::CreateExecutionContext",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\executioncontext.cpp",
          82,
          L"Failed to read WinRE configuration");
LABEL_6:
        v45[0] = &RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable';
LABEL_56:
        RAII::CAutoPbrHeapFree<unsigned short *>::Release(v45);
        goto LABEL_57;
      }
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v37);
    Volume = PushButtonReset::Path::GetVolume(a1, &v37);
    if ( Volume < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Volume,
        "WinREAgent::CreateExecutionContext",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\executioncontext.cpp",
        92,
        L"Failed to get target volume");
LABEL_11:
      ATL::CStringData::Release((ATL::CStringData *)(v37 - 24));
      goto LABEL_6;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v39);
    Volume = WinREAgent::WorkDir::GetLogDir((__int64)a1, (__int64)&v39);
    if ( Volume < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Volume,
        "WinREAgent::CreateExecutionContext",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\executioncontext.cpp",
        96,
        L"Failed to build log path");
LABEL_14:
      ATL::CStringData::Release((ATL::CStringData *)(v39 - 24));
      goto LABEL_11;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v40);
    Volume = WinREAgent::WorkDir::GetScratchDir((__int64)a1, (__int64)&v40);
    if ( Volume < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Volume,
        "WinREAgent::CreateExecutionContext",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\executioncontext.cpp",
        100,
        L"Failed to build scratch path");
LABEL_17:
      ATL::CStringData::Release((ATL::CStringData *)(v40 - 24));
      goto LABEL_14;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v41);
    Volume = WinREAgent::WorkDir::GetBackupDir(a1, &v41);
    if ( Volume < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Volume,
        "WinREAgent::CreateExecutionContext",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\executioncontext.cpp",
        104,
        L"Failed to build backup path");
      ATL::CStringData::Release((ATL::CStringData *)(v41 - 24));
      goto LABEL_17;
    }
    v8 = (_QWORD *)(((__int64 (__fastcall *)(void ***))v46[3])(&v46) + 56);
    v9 = *a1;
    v10 = (int *)(*a1 - 24);
    v11 = (int *)(*v8 - 24LL);
    if ( v10 != v11 )
    {
      if ( v11[4] >= 0 && *(_QWORD *)v10 == *(_QWORD *)v11 )
      {
        v12 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v10);
        ATL::CStringData::Release((ATL::CStringData *)v11);
        *v8 = v12 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(v8, v9, *(unsigned int *)(v9 - 16));
      }
    }
    v13 = (_QWORD *)(((__int64 (__fastcall *)(void ***))v46[3])(&v46) + 88);
    v14 = (ATL::CStringData *)(v37 - 24);
    v15 = (int *)(*v13 - 24LL);
    if ( (int *)(v37 - 24) != v15 )
    {
      if ( v15[4] >= 0 && *(_QWORD *)v14 == *(_QWORD *)v15 )
      {
        v16 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v37 - 24);
        ATL::CStringData::Release((ATL::CStringData *)v15);
        *v13 = v16 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(v13, v37, *(unsigned int *)(v37 - 16));
      }
    }
    v17 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD *))(v45[0] + 24LL))(v45) + 8) == 1;
    *(_BYTE *)(((__int64 (__fastcall *)(void ***))v46[3])(&v46) + 152) = v17;
    v18 = (_QWORD *)(((__int64 (__fastcall *)(void ***))v46[3])(&v46) + 184);
    v19 = (_QWORD *)(v40 - 24);
    v42 = (ATL::CStringData *)(v40 - 24);
    v20 = (int *)(*v18 - 24LL);
    if ( (int *)(v40 - 24) != v20 )
    {
      if ( v20[4] >= 0 && *v19 == *(_QWORD *)v20 )
      {
        v21 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v19);
        ATL::CStringData::Release((ATL::CStringData *)v20);
        *v18 = v21 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(v18, v40, *(unsigned int *)(v40 - 16));
      }
    }
    v22 = (_QWORD *)(((__int64 (__fastcall *)(void ***))v46[3])(&v46) + 216);
    v23 = (ATL::CStringData *)(v39 - 24);
    v24 = (int *)(*v22 - 24LL);
    if ( (int *)(v39 - 24) != v24 )
    {
      if ( v24[4] >= 0 && *(_QWORD *)v23 == *(_QWORD *)v24 )
      {
        v25 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v39 - 24);
        ATL::CStringData::Release((ATL::CStringData *)v24);
        *v22 = v25 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(v22, v39, *(unsigned int *)(v39 - 16));
      }
    }
    v26 = (_QWORD *)(((__int64 (__fastcall *)(void ***))v46[3])(&v46) + 248);
    v27 = (ATL::CStringData *)(v41 - 24);
    v28 = (int *)(*v26 - 24LL);
    if ( (int *)(v41 - 24) != v28 )
    {
      if ( v28[4] >= 0 && *(_QWORD *)v27 == *(_QWORD *)v28 )
      {
        v29 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v41 - 24);
        ATL::CStringData::Release((ATL::CStringData *)v28);
        *v26 = v29 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(v26, v41, *(unsigned int *)(v41 - 16));
      }
    }
    if ( *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD *))(v45[0] + 24LL))(v45) + 8) == 1 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v38);
      v30 = (*(__int64 (__fastcall **)(_QWORD *))(v45[0] + 24LL))(v45);
      Volume = PushButtonReset::WindowsRE::Config::GetCurrentWimPath(v30, &v38);
      if ( Volume < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Volume,
          "WinREAgent::CreateExecutionContext",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\executioncontext.cpp",
          117,
          L"Failed to get winre path");
        ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
LABEL_55:
        ATL::CStringData::Release(v27);
        ATL::CStringData::Release(v42);
        ATL::CStringData::Release(v23);
        ATL::CStringData::Release(v14);
        v45[0] = &RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable';
        goto LABEL_56;
      }
      v31 = (_QWORD *)(((__int64 (__fastcall *)(void ***))v46[3])(&v46) + 120);
      v43 = v31;
      v32 = (ATL::CStringData *)(v38 - 24);
      v33 = (int *)(*v31 - 24LL);
      if ( (int *)(v38 - 24) != v33 )
      {
        if ( v33[4] >= 0 && *(_QWORD *)v32 == *(_QWORD *)v33 )
        {
          v34 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v38 - 24);
          ATL::CStringData::Release((ATL::CStringData *)v33);
          *v43 = v34 + 24;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(v31, v38, *(unsigned int *)(v38 - 16));
        }
      }
      ATL::CStringData::Release(v32);
    }
    v35 = v47;
    v47 = 0;
    *v44 = v35;
    goto LABEL_55;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    2147942414LL,
    "WinREAgent::CreateExecutionContext",
    "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\executioncontext.cpp",
    76,
    L"Failed to allocate context");
  Volume = -2147024882;
LABEL_57:
  v46 = &RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::`vftable';
  RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::Release(&v46);
  return (unsigned int)Volume;
}

```

## disassembly

```asm
0x18001e51c  mov     [rsp-8+arg_18], rbx
0x18001e521  push    rbp
0x18001e522  push    rsi
0x18001e523  push    rdi
0x18001e524  push    r12
0x18001e526  push    r13
0x18001e528  push    r14
0x18001e52a  push    r15
0x18001e52c  lea     rbp, [rsp-27h]
0x18001e531  sub     rsp, 0A0h
0x18001e538  mov     rax, cs:__security_cookie
0x18001e53f  xor     rax, rsp
0x18001e542  mov     [rbp+57h+var_40], rax
0x18001e546  mov     [rbp+57h+var_68], r8
0x18001e54a  mov     rdi, rdx
0x18001e54d  mov     rsi, rcx
0x18001e550  call    ??$PbrNew@VExecutionContext@WinREAgent@@$$V@@YAPEAVExecutionContext@WinREAgent@@XZ; PbrNew<WinREAgent::ExecutionContext,>(void)
0x18001e555  mov     [rbp+57h+var_48], rax
0x18001e559  lea     rax, ??_7?$CAutoPbrDelete@PEAVExecutionContext@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::ExecutionContext *>::`vftable'
0x18001e560  mov     [rbp+57h+var_50], rax
0x18001e564  lea     rcx, [rbp+57h+var_50]
0x18001e568  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x18001e56d  xor     r15d, r15d
0x18001e570  test    al, al
0x18001e572  jz      short loc_18001E5AE
0x18001e574  lea     rax, aFailedToAlloca_35; "Failed to allocate context"
0x18001e57b  mov     [rsp+0D0h+var_A8], rax
0x18001e580  mov     [rsp+0D0h+var_B0], 4Ch ; 'L'
0x18001e588  lea     r9, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18001e58f  lea     r8, aWinreagentCrea; "WinREAgent::CreateExecutionContext"
0x18001e596  mov     edx, 8007000Eh
0x18001e59b  lea     ecx, [r15+2]
0x18001e59f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001e5a4  mov     edi, 8007000Eh
0x18001e5a9  jmp     loc_18001EB16
0x18001e5ae  mov     [rbp+57h+var_58], r15
0x18001e5b2  lea     r14, ??_7?$CAutoPbrDelete@PEAVConfig@WindowsRE@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable'
0x18001e5b9  mov     [rbp+57h+var_60], r14
0x18001e5bd  lea     rcx, [rbp+57h+var_60]
0x18001e5c1  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18001e5c6  test    rdi, rdi
0x18001e5c9  jnz     short loc_18001E611
0x18001e5cb  mov     rcx, rax; struct PushButtonReset::WindowsRE::Config **
0x18001e5ce  call    ?OpenConfig@WindowsRE@PushButtonReset@@SAJPEAPEAVConfig@12@@Z; PushButtonReset::WindowsRE::OpenConfig(PushButtonReset::WindowsRE::Config * *)
0x18001e5d3  mov     edi, eax
0x18001e5d5  test    eax, eax
0x18001e5d7  jns     short loc_18001E656
0x18001e5d9  lea     rax, aFailedToReadWi_0; "Failed to read WinRE configuration"
0x18001e5e0  mov     [rsp+0D0h+var_A8], rax
0x18001e5e5  mov     [rsp+0D0h+var_B0], 52h ; 'R'
0x18001e5ed  lea     r9, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18001e5f4  lea     r8, aWinreagentCrea; "WinREAgent::CreateExecutionContext"
0x18001e5fb  mov     edx, edi
0x18001e5fd  mov     ecx, 2
0x18001e602  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001e607  nop
0x18001e608  mov     [rbp+57h+var_60], r14
0x18001e60c  jmp     loc_18001EB0C
0x18001e611  mov     rbx, rax
0x18001e614  mov     rdx, rdi
0x18001e617  lea     rcx, [rbp+57h+var_98]
0x18001e61b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001e620  nop
0x18001e621  mov     rdx, rbx
0x18001e624  lea     rcx, [rbp+57h+var_98]
0x18001e628  call    ?OpenConfig@WindowsRE@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAVConfig@12@@Z; PushButtonReset::WindowsRE::OpenConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::WindowsRE::Config * *)
0x18001e62d  mov     edi, eax
0x18001e62f  mov     rcx, [rbp+57h+var_98]
0x18001e633  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001e637  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001e63c  test    edi, edi
0x18001e63e  jns     short loc_18001E656
0x18001e640  lea     rax, aFailedToReadWi_0; "Failed to read WinRE configuration"
0x18001e647  mov     [rsp+0D0h+var_A8], rax
0x18001e64c  mov     [rsp+0D0h+var_B0], 57h ; 'W'
0x18001e654  jmp     short loc_18001E5ED
0x18001e656  lea     rcx, [rbp+57h+var_A0]
0x18001e65a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001e65f  nop
0x18001e660  lea     rdx, [rbp+57h+var_A0]
0x18001e664  mov     rcx, rsi
0x18001e667  call    ?GetVolume@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetVolume(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18001e66c  mov     edi, eax
0x18001e66e  test    eax, eax
0x18001e670  jns     short loc_18001E6B3
0x18001e672  lea     rax, aFailedToGetTar; "Failed to get target volume"
0x18001e679  mov     [rsp+0D0h+var_A8], rax
0x18001e67e  mov     [rsp+0D0h+var_B0], 5Ch ; '\'
0x18001e686  lea     r9, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18001e68d  lea     r8, aWinreagentCrea; "WinREAgent::CreateExecutionContext"
0x18001e694  mov     edx, edi
0x18001e696  mov     ecx, 2
0x18001e69b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001e6a0  nop
0x18001e6a1  mov     rcx, [rbp+57h+var_A0]
0x18001e6a5  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001e6a9  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001e6ae  jmp     loc_18001E608
0x18001e6b3  lea     rcx, [rbp+57h+var_90]
0x18001e6b7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001e6bc  nop
0x18001e6bd  lea     rdx, [rbp+57h+var_90]
0x18001e6c1  mov     rcx, rsi
0x18001e6c4  call    ?GetLogDir@WorkDir@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV34@@Z; WinREAgent::WorkDir::GetLogDir(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18001e6c9  mov     edi, eax
0x18001e6cb  test    eax, eax
0x18001e6cd  jns     short loc_18001E70D
0x18001e6cf  lea     rax, aFailedToBuildL; "Failed to build log path"
0x18001e6d6  mov     [rsp+0D0h+var_A8], rax
0x18001e6db  mov     [rsp+0D0h+var_B0], 60h ; '`'
0x18001e6e3  lea     r9, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18001e6ea  lea     r8, aWinreagentCrea; "WinREAgent::CreateExecutionContext"
0x18001e6f1  mov     edx, edi
0x18001e6f3  mov     ecx, 2
0x18001e6f8  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001e6fd  nop
0x18001e6fe  mov     rcx, [rbp+57h+var_90]
0x18001e702  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001e706  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001e70b  jmp     short loc_18001E6A1
0x18001e70d  lea     rcx, [rbp+57h+var_88]
0x18001e711  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001e716  nop
0x18001e717  lea     rdx, [rbp+57h+var_88]
0x18001e71b  mov     rcx, rsi
0x18001e71e  call    ?GetScratchDir@WorkDir@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV34@@Z; WinREAgent::WorkDir::GetScratchDir(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18001e723  mov     edi, eax
0x18001e725  test    eax, eax
0x18001e727  jns     short loc_18001E767
0x18001e729  lea     rax, aFailedToBuildS; "Failed to build scratch path"
0x18001e730  mov     [rsp+0D0h+var_A8], rax
0x18001e735  mov     [rsp+0D0h+var_B0], 64h ; 'd'
0x18001e73d  lea     r9, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18001e744  lea     r8, aWinreagentCrea; "WinREAgent::CreateExecutionContext"
0x18001e74b  mov     edx, edi
0x18001e74d  mov     ecx, 2
0x18001e752  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001e757  nop
0x18001e758  mov     rcx, [rbp+57h+var_88]
0x18001e75c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001e760  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001e765  jmp     short loc_18001E6FE
0x18001e767  lea     rcx, [rbp+57h+var_80]
0x18001e76b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001e770  nop
0x18001e771  lea     rdx, [rbp+57h+var_80]
0x18001e775  mov     rcx, rsi
0x18001e778  call    ?GetBackupDir@WorkDir@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV34@@Z; WinREAgent::WorkDir::GetBackupDir(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18001e77d  mov     edi, eax
0x18001e77f  test    eax, eax
0x18001e781  jns     short loc_18001E7C1
0x18001e783  lea     rax, aFailedToBuildB; "Failed to build backup path"
0x18001e78a  mov     [rsp+0D0h+var_A8], rax
0x18001e78f  mov     [rsp+0D0h+var_B0], 68h ; 'h'
0x18001e797  lea     r9, aBaseDiagnosisS_3; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18001e79e  lea     r8, aWinreagentCrea; "WinREAgent::CreateExecutionContext"
0x18001e7a5  mov     edx, edi
0x18001e7a7  mov     ecx, 2
0x18001e7ac  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001e7b1  nop
0x18001e7b2  mov     rcx, [rbp+57h+var_80]
0x18001e7b6  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001e7ba  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001e7bf  jmp     short loc_18001E758
0x18001e7c1  mov     rax, [rbp+57h+var_50]
0x18001e7c5  lea     rcx, [rbp+57h+var_50]
0x18001e7c9  mov     rax, [rax+18h]
0x18001e7cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7d2  lea     r14, [rax+38h]
0x18001e7d6  mov     rdx, [rsi]
0x18001e7d9  lea     rcx, [rdx-18h]
0x18001e7dd  mov     rsi, [r14]
0x18001e7e0  add     rsi, 0FFFFFFFFFFFFFFE8h
0x18001e7e4  cmp     rcx, rsi
0x18001e7e7  jz      short loc_18001E81C
0x18001e7e9  cmp     [rsi+10h], r15d
0x18001e7ed  jl      short loc_18001E810
0x18001e7ef  mov     rax, [rsi]
0x18001e7f2  cmp     [rcx], rax
0x18001e7f5  jnz     short loc_18001E810
0x18001e7f7  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001e7fc  mov     rbx, rax
0x18001e7ff  mov     rcx, rsi; this
0x18001e802  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001e807  lea     rax, [rbx+18h]
0x18001e80b  mov     [r14], rax
0x18001e80e  jmp     short loc_18001E81C
0x18001e810  mov     r8d, [rdx-10h]
0x18001e814  mov     rcx, r14
0x18001e817  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001e81c  mov     rax, [rbp+57h+var_50]
0x18001e820  lea     rcx, [rbp+57h+var_50]
0x18001e824  mov     rax, [rax+18h]
0x18001e828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e82d  lea     r14, [rax+58h]
0x18001e831  mov     rdx, [rbp+57h+var_A0]
0x18001e835  lea     r13, [rdx-18h]
0x18001e839  mov     rsi, [r14]
0x18001e83c  add     rsi, 0FFFFFFFFFFFFFFE8h
0x18001e840  cmp     r13, rsi
0x18001e843  jz      short loc_18001E87C
0x18001e845  cmp     [rsi+10h], r15d
0x18001e849  jl      short loc_18001E870
0x18001e84b  mov     rax, [rsi]
0x18001e84e  cmp     [r13+0], rax
0x18001e852  jnz     short loc_18001E870
0x18001e854  mov     rcx, r13
0x18001e857  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001e85c  mov     rbx, rax
0x18001e85f  mov     rcx, rsi; this
0x18001e862  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001e867  lea     rax, [rbx+18h]
0x18001e86b  mov     [r14], rax
0x18001e86e  jmp     short loc_18001E87C
0x18001e870  mov     r8d, [rdx-10h]
0x18001e874  mov     rcx, r14
0x18001e877  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001e87c  mov     rax, [rbp+57h+var_60]
0x18001e880  lea     rcx, [rbp+57h+var_60]
0x18001e884  mov     rax, [rax+18h]
0x18001e888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e88d  cmp     dword ptr [rax+8], 1
0x18001e891  setz    bl
0x18001e894  mov     rax, [rbp+57h+var_50]
0x18001e898  lea     rcx, [rbp+57h+var_50]
0x18001e89c  mov     rax, [rax+18h]
0x18001e8a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8a5  mov     [rax+98h], bl
0x18001e8ab  mov     rax, [rbp+57h+var_50]
0x18001e8af  lea     rcx, [rbp+57h+var_50]
0x18001e8b3  mov     rax, [rax+18h]
0x18001e8b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8bc  lea     r14, [rax+0B8h]
0x18001e8c3  mov     rdx, [rbp+57h+var_88]
0x18001e8c7  lea     rcx, [rdx-18h]
0x18001e8cb  mov     [rbp+57h+var_78], rcx
0x18001e8cf  mov     rsi, [r14]
0x18001e8d2  add     rsi, 0FFFFFFFFFFFFFFE8h
0x18001e8d6  cmp     rcx, rsi
0x18001e8d9  jz      short loc_18001E90E
0x18001e8db  cmp     [rsi+10h], r15d
0x18001e8df  jl      short loc_18001E902
0x18001e8e1  mov     rax, [rsi]
0x18001e8e4  cmp     [rcx], rax
0x18001e8e7  jnz     short loc_18001E902
0x18001e8e9  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001e8ee  mov     rbx, rax
0x18001e8f1  mov     rcx, rsi; this
0x18001e8f4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001e8f9  lea     rax, [rbx+18h]
0x18001e8fd  mov     [r14], rax
0x18001e900  jmp     short loc_18001E90E
0x18001e902  mov     r8d, [rdx-10h]
0x18001e906  mov     rcx, r14
0x18001e909  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001e90e  mov     rax, [rbp+57h+var_50]
0x18001e912  lea     rcx, [rbp+57h+var_50]
0x18001e916  mov     rax, [rax+18h]
0x18001e91a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e91f  lea     r14, [rax+0D8h]
0x18001e926  mov     rdx, [rbp+57h+var_90]
0x18001e92a  lea     r12, [rdx-18h]
0x18001e92e  mov     rsi, [r14]
0x18001e931  add     rsi, 0FFFFFFFFFFFFFFE8h
0x18001e935  cmp     r12, rsi
0x18001e938  jz      short loc_18001E971
0x18001e93a  cmp     [rsi+10h], r15d
0x18001e93e  jl      short loc_18001E965
0x18001e940  mov     rax, [rsi]
0x18001e943  cmp     [r12], rax
0x18001e947  jnz     short loc_18001E965
0x18001e949  mov     rcx, r12
0x18001e94c  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18001e951  mov     rbx, rax
0x18001e954  mov     rcx, rsi; this
0x18001e957  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001e95c  lea     rax, [rbx+18h]
0x18001e960  mov     [r14], rax
0x18001e963  jmp     short loc_18001E971
0x18001e965  mov     r8d, [rdx-10h]
0x18001e969  mov     rcx, r14
0x18001e96c  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001e971  mov     rax, [rbp+57h+var_50]
0x18001e975  lea     rcx, [rbp+57h+var_50]
0x18001e979  mov     rax, [rax+18h]
0x18001e97d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e982  lea     r14, [rax+0F8h]
0x18001e989  mov     rdx, [rbp+57h+var_80]
0x18001e98d  lea     r15, [rdx-18h]
0x18001e991  mov     rsi, [r14]
0x18001e994  add     rsi, 0FFFFFFFFFFFFFFE8h
0x18001e998  cmp     r15, rsi
0x18001e99b  jz      short loc_18001E9D3
0x18001e99d  cmp     dword ptr [rsi+10h], 0
0x18001e9a1  jl      short loc_18001E9C7
0x18001e9a3  mov     rax, [rsi]
0x18001e9a6  cmp     [r15], rax
0x18001e9a9  jnz     short loc_18001E9C7
0x18001e9ab  mov     rcx, r15
0x18001e9ae  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
  ... truncated ...
```
