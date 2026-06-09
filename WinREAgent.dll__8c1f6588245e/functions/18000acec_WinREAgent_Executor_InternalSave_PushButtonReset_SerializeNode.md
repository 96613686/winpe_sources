# WinREAgent::Executor::InternalSave(PushButtonReset::SerializeNode *)

- ea: `0x18000acec`
- end: `0x18000b2fa`
- name: `?InternalSave@Executor@WinREAgent@@AEAAJPEAVSerializeNode@PushButtonReset@@@Z`
- size: `1550`
- prototype: `__int64 __fastcall(WinREAgent::Executor *__hidden this, struct PushButtonReset::SerializeNode *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000e9c0`

## callees

- `0x1800049a4`
- `0x180005c70`
- `0x180005cc0`
- `0x18000acec`
- `0x18000d800`
- `0x18000d92c`
- `0x18001ec68`
- `0x180029b0c`
- `0x180037344`
- `0x180050e24`
- `0x18005338c`
- `0x1800533dc`
- `0x180053498`
- `0x18006f010`

## string_xrefs

- `0x18000ad71`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000af47`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000b06d`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000b0a1`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000b16d`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000b1a1`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000b2a7`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000ae2a`: `PackagePath`
- `0x18000aee4`: `InstallSize`
- `0x18000b0de`: `CommitOperation`
- `0x18000ad5d`: `Failed to create Packages entries node`
- `0x18000ad78`: `WinREAgent::Executor::InternalSave`
- `0x18000af4e`: `WinREAgent::Executor::InternalSave`
- `0x18000b074`: `WinREAgent::Executor::InternalSave`
- `0x18000b0a8`: `WinREAgent::Executor::InternalSave`
- `0x18000b174`: `WinREAgent::Executor::InternalSave`
- `0x18000b1a8`: `WinREAgent::Executor::InternalSave`
- `0x18000b2ae`: `WinREAgent::Executor::InternalSave`
- `0x18000afa7`: `Failed to create Packages entry node [%u]`
- `0x18000af8d`: `Failed to save PackagePath of entry node [%u]`
- `0x18000af33`: `Failed to save InstallSize of entry node [%u]`
- `0x18000b159`: `Failed to save commit operation [%u]`
- `0x18000b204`: `Failed to create Execution context node`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall WinREAgent::Executor::InternalSave(WinREAgent::Executor *this, PushButtonReset::XmlNode **a2)
{
  _QWORD *v4; // rbx
  int v5; // ebx
  unsigned __int64 i; // rsi
  PushButtonReset::XmlNode **v7; // rdi
  _QWORD *v8; // rbx
  __int64 v9; // rdi
  __int64 v10; // r8
  __int64 v11; // rbx
  __int64 v12; // rdi
  __int64 v13; // r8
  __int64 v14; // rbx
  __int64 v15; // rdi
  __int64 v16; // r8
  __int64 v17; // rbx
  void ***v18; // rcx
  unsigned int j; // edi
  _QWORD *v20; // rbx
  __int64 v21; // r8
  struct WinREAgent::Operation *v22; // rbx
  struct PushButtonReset::SerializeNode *v23; // rax
  unsigned int k; // edi
  _QWORD *v25; // rbx
  __int64 v26; // r8
  struct WinREAgent::Operation *v27; // rbx
  struct PushButtonReset::SerializeNode *v28; // rax
  _QWORD *v29; // rbx
  struct PushButtonReset::SerializeNode *v30; // rax
  unsigned int v31; // ebx
  int v33; // [rsp+30h] [rbp-50h]
  int v34; // [rsp+30h] [rbp-50h]
  int v35; // [rsp+30h] [rbp-50h]
  int v36; // [rsp+30h] [rbp-50h]
  int v37; // [rsp+30h] [rbp-50h]
  int v38; // [rsp+30h] [rbp-50h]
  __int64 v39; // [rsp+40h] [rbp-40h] BYREF
  __int64 v40; // [rsp+48h] [rbp-38h] BYREF
  _QWORD v41[2]; // [rsp+50h] [rbp-30h] BYREF
  void **v42; // [rsp+60h] [rbp-20h] BYREF
  __int64 v43; // [rsp+68h] [rbp-18h]
  _QWORD v44[2]; // [rsp+70h] [rbp-10h] BYREF
  __int64 v45; // [rsp+D0h] [rbp+50h] BYREF
  __int64 v46; // [rsp+D8h] [rbp+58h] BYREF

  v41[1] = 0;
  v41[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
  v4 = (_QWORD *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v41);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v45,
    (__int64)L"Package");
  v5 = PushButtonReset::SerializeNode::AddChild(a2, &v45, v4);
  ATL::CStringData::Release((ATL::CStringData *)(v45 - 24));
  if ( v5 >= 0 )
  {
    for ( i = 0; i < *((_QWORD *)this + 13); ++i )
    {
      v43 = 0;
      v42 = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
      v7 = (PushButtonReset::XmlNode **)(*(__int64 (__fastcall **)(_QWORD *))(v41[0] + 24LL))(v41);
      v8 = (_QWORD *)((__int64 (__fastcall *)(void ***))v42[1])(&v42);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v45,
        (__int64)L"Entry");
      v5 = PushButtonReset::SerializeNode::AddChild(v7, &v45, v8);
      ATL::CStringData::Release((ATL::CStringData *)(v45 - 24));
      if ( v5 < 0 )
      {
        v36 = i;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v5,
          "WinREAgent::Executor::InternalSave",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2374,
          L"Failed to create Packages entry node [%u]",
          v36);
        goto LABEL_11;
      }
      v9 = ((__int64 (__fastcall *)(void ***))v42[3])(&v42);
      v11 = *(_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                         (char *)this + 96,
                         i,
                         v10);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v46,
        (__int64)L"PackagePath");
      v5 = PushButtonReset::SerializeNode::SetProperty(v9, &v46, v11);
      ATL::CStringData::Release((ATL::CStringData *)(v46 - 24));
      if ( v5 < 0 )
      {
        v35 = i;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v5,
          "WinREAgent::Executor::InternalSave",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2377,
          L"Failed to save PackagePath of entry node [%u]",
          v35);
        goto LABEL_11;
      }
      v12 = ((__int64 (__fastcall *)(void ***))v42[3])(&v42);
      v14 = *(_QWORD *)(*(_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                                     (char *)this + 96,
                                     i,
                                     v13)
                      + 8LL);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v39,
        (__int64)L"PackageSize");
      v5 = PushButtonReset::SerializeNode::SetProperty(v12, &v39, v14);
      ATL::CStringData::Release((ATL::CStringData *)(v39 - 24));
      if ( v5 < 0 )
      {
        v34 = i;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v5,
          "WinREAgent::Executor::InternalSave",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2380,
          L"Failed to save PackageSize of entry node [%u]",
          v34);
        goto LABEL_11;
      }
      v15 = ((__int64 (__fastcall *)(void ***))v42[3])(&v42);
      v17 = *(_QWORD *)(*(_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                                     (char *)this + 96,
                                     i,
                                     v16)
                      + 16LL);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v40,
        (__int64)L"InstallSize");
      v5 = PushButtonReset::SerializeNode::SetProperty(v15, &v40, v17);
      ATL::CStringData::Release((ATL::CStringData *)(v40 - 24));
      if ( v5 < 0 )
      {
        v33 = i;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v5,
          "WinREAgent::Executor::InternalSave",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2383,
          L"Failed to save InstallSize of entry node [%u]",
          v33);
LABEL_11:
        v42 = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
        v18 = &v42;
        goto LABEL_36;
      }
      v42 = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(&v42);
    }
    for ( j = 0; j < *((_DWORD *)this + 10); ++j )
    {
      v43 = 0;
      v42 = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
      v20 = (_QWORD *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v42);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v45,
        (__int64)L"StageOperation");
      v5 = PushButtonReset::SerializeNode::AddChild(a2, &v45, v20);
      ATL::CStringData::Release((ATL::CStringData *)(v45 - 24));
      if ( v5 < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v5,
          "WinREAgent::Executor::InternalSave",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2391,
          L"Failed to add empty operation node to operation queue node");
        goto LABEL_11;
      }
      v22 = *(struct WinREAgent::Operation **)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                                                (char *)this + 32,
                                                j,
                                                v21);
      v23 = (struct PushButtonReset::SerializeNode *)((__int64 (__fastcall *)(void ***))v42[4])(&v42);
      v5 = WinREAgent::Operation::Save(v22, v23);
      if ( v5 < 0 )
      {
        v37 = j;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v5,
          "WinREAgent::Executor::InternalSave",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2395,
          L"Failed to save stage operation [%u]",
          v37);
        goto LABEL_11;
      }
      v42 = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(&v42);
    }
    for ( k = 0; k < *((_DWORD *)this + 18); ++k )
    {
      v43 = 0;
      v42 = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
      v25 = (_QWORD *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v42);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v45,
        (__int64)L"CommitOperation");
      v5 = PushButtonReset::SerializeNode::AddChild(a2, &v45, v25);
      ATL::CStringData::Release((ATL::CStringData *)(v45 - 24));
      if ( v5 < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v5,
          "WinREAgent::Executor::InternalSave",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2402,
          L"Failed to add empty operation node to operation queue node");
        goto LABEL_11;
      }
      v27 = *(struct WinREAgent::Operation **)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                                                (char *)this + 64,
                                                k,
                                                v26);
      v28 = (struct PushButtonReset::SerializeNode *)((__int64 (__fastcall *)(void ***))v42[4])(&v42);
      v5 = WinREAgent::Operation::Save(v27, v28);
      if ( v5 < 0 )
      {
        v38 = k;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v5,
          "WinREAgent::Executor::InternalSave",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2406,
          L"Failed to save commit operation [%u]",
          v38);
        goto LABEL_11;
      }
      v42 = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(&v42);
    }
    v44[1] = 0;
    v44[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
    v29 = (_QWORD *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v44);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v45,
      (__int64)L"ExecutionContext");
    v5 = PushButtonReset::SerializeNode::AddChild(a2, &v45, v29);
    ATL::CStringData::Release((ATL::CStringData *)(v45 - 24));
    if ( v5 >= 0 )
    {
      v30 = (struct PushButtonReset::SerializeNode *)(*(__int64 (__fastcall **)(_QWORD *))(v44[0] + 32LL))(v44);
      v5 = WinREAgent::ExecutionContext::Save(*((struct WinREAgent::ExecutionContext **)this + 51), v30);
      if ( v5 >= 0 )
      {
        v31 = *((_DWORD *)this + 108);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          (__int64)&v45,
          (__int64)L"ScenarioType");
        v5 = PushButtonReset::SerializeNode::SetProperty(a2, &v45, v31);
        ATL::CStringData::Release((ATL::CStringData *)(v45 - 24));
        if ( v5 < 0 )
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)v5,
            "WinREAgent::Executor::InternalSave",
            "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
            2419,
            L"Failed to save ScenarioType");
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v5,
          "WinREAgent::Executor::InternalSave",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2415,
          L"Failed to save ExecutionContext");
      }
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v5,
        "WinREAgent::Executor::InternalSave",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        2412,
        L"Failed to create Execution context node");
    }
    v18 = (void ***)v44;
    v44[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
LABEL_36:
    RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v18);
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v5,
      "WinREAgent::Executor::InternalSave",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      2368,
      L"Failed to create Packages entries node");
  }
  v41[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
  RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v41);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000acec  mov     [rsp-38h+arg_0], rbx
0x18000acf1  push    rbp
0x18000acf2  push    rsi
0x18000acf3  push    rdi
0x18000acf4  push    r12
0x18000acf6  push    r13
0x18000acf8  push    r14
0x18000acfa  push    r15
0x18000acfc  mov     rbp, rsp
0x18000acff  sub     rsp, 80h
0x18000ad06  mov     r15, rdx
0x18000ad09  mov     r14, rcx
0x18000ad0c  xor     r12d, r12d
0x18000ad0f  mov     [rbp+var_28], r12
0x18000ad13  lea     r13, ??_7?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable'
0x18000ad1a  mov     [rbp+var_30], r13
0x18000ad1e  lea     rcx, [rbp+var_30]
0x18000ad22  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18000ad27  mov     rbx, rax
0x18000ad2a  lea     rdx, aPackage; "Package"
0x18000ad31  lea     rcx, [rbp+arg_10]
0x18000ad35  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000ad3a  nop
0x18000ad3b  mov     r8, rbx
0x18000ad3e  lea     rdx, [rbp+arg_10]
0x18000ad42  mov     rcx, r15
0x18000ad45  call    ?AddChild@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::SerializeNode::AddChild(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::SerializeNode * *)
0x18000ad4a  mov     ebx, eax
0x18000ad4c  mov     rcx, [rbp+arg_10]
0x18000ad50  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000ad54  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000ad59  test    ebx, ebx
0x18000ad5b  jns     short loc_18000AD90
0x18000ad5d  lea     rax, aFailedToCreate_19; "Failed to create Packages entries node"
0x18000ad64  mov     [rsp+80h+var_58], rax
0x18000ad69  mov     [rsp+80h+var_60], 940h
0x18000ad71  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000ad78  lea     r8, aWinreagentExec_0; "WinREAgent::Executor::InternalSave"
0x18000ad7f  mov     edx, ebx
0x18000ad81  lea     ecx, [r12+2]
0x18000ad86  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000ad8b  jmp     loc_18000B2D0
0x18000ad90  mov     rsi, r12
0x18000ad93  cmp     rsi, [r14+68h]
0x18000ad97  jnb     loc_18000AFBD
0x18000ad9d  mov     [rbp+var_18], r12
0x18000ada1  mov     [rbp+var_20], r13
0x18000ada5  mov     rax, [rbp+var_30]
0x18000ada9  lea     rcx, [rbp+var_30]
0x18000adad  mov     rax, [rax+18h]
0x18000adb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adb6  mov     rdi, rax
0x18000adb9  mov     rcx, [rbp+var_20]
0x18000adbd  mov     rax, [rcx+8]
0x18000adc1  lea     rcx, [rbp+var_20]
0x18000adc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adca  mov     rbx, rax
0x18000adcd  lea     rdx, aEntry; "Entry"
0x18000add4  lea     rcx, [rbp+arg_10]
0x18000add8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000addd  nop
0x18000adde  mov     r8, rbx
0x18000ade1  lea     rdx, [rbp+arg_10]
0x18000ade5  mov     rcx, rdi
0x18000ade8  call    ?AddChild@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::SerializeNode::AddChild(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::SerializeNode * *)
0x18000aded  mov     ebx, eax
0x18000adef  mov     rcx, [rbp+arg_10]
0x18000adf3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000adf7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000adfc  test    ebx, ebx
0x18000adfe  js      loc_18000AFA3
0x18000ae04  mov     rax, [rbp+var_20]
0x18000ae08  lea     rcx, [rbp+var_20]
0x18000ae0c  mov     rax, [rax+18h]
0x18000ae10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae15  mov     rdi, rax
0x18000ae18  lea     r12, [r14+60h]
0x18000ae1c  mov     rdx, rsi
0x18000ae1f  mov     rcx, r12
0x18000ae22  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x18000ae27  mov     rbx, [rax]
0x18000ae2a  lea     rdx, aPackagepath; "PackagePath"
0x18000ae31  lea     rcx, [rbp+arg_18]
0x18000ae35  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000ae3a  nop
0x18000ae3b  mov     r8, rbx
0x18000ae3e  lea     rdx, [rbp+arg_18]
0x18000ae42  mov     rcx, rdi
0x18000ae45  call    ?SetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; PushButtonReset::SerializeNode::SetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000ae4a  mov     ebx, eax
0x18000ae4c  mov     rcx, [rbp+arg_18]
0x18000ae50  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000ae54  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000ae59  test    ebx, ebx
0x18000ae5b  js      loc_18000AF89
0x18000ae61  mov     rax, [rbp+var_20]
0x18000ae65  lea     rcx, [rbp+var_20]
0x18000ae69  mov     rax, [rax+18h]
0x18000ae6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae72  mov     rdi, rax
0x18000ae75  mov     rdx, rsi
0x18000ae78  mov     rcx, r12
0x18000ae7b  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x18000ae80  mov     rcx, [rax]
0x18000ae83  mov     rbx, [rcx+8]
0x18000ae87  lea     rdx, aPackagesize; "PackageSize"
0x18000ae8e  lea     rcx, [rbp+var_40]
0x18000ae92  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000ae97  nop
0x18000ae98  mov     r8, rbx
0x18000ae9b  lea     rdx, [rbp+var_40]
0x18000ae9f  mov     rcx, rdi
0x18000aea2  call    ?SetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_K@Z; PushButtonReset::SerializeNode::SetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64)
0x18000aea7  mov     ebx, eax
0x18000aea9  mov     rcx, [rbp+var_40]
0x18000aead  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000aeb1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000aeb6  test    ebx, ebx
0x18000aeb8  js      loc_18000AF6F
0x18000aebe  mov     rax, [rbp+var_20]
0x18000aec2  lea     rcx, [rbp+var_20]
0x18000aec6  mov     rax, [rax+18h]
0x18000aeca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aecf  mov     rdi, rax
0x18000aed2  mov     rdx, rsi
0x18000aed5  mov     rcx, r12
0x18000aed8  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x18000aedd  mov     rcx, [rax]
0x18000aee0  mov     rbx, [rcx+10h]
0x18000aee4  lea     rdx, aInstallsize; "InstallSize"
0x18000aeeb  lea     rcx, [rbp+var_38]
0x18000aeef  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000aef4  nop
0x18000aef5  mov     r8, rbx
0x18000aef8  lea     rdx, [rbp+var_38]
0x18000aefc  mov     rcx, rdi
0x18000aeff  call    ?SetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_K@Z; PushButtonReset::SerializeNode::SetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64)
0x18000af04  mov     ebx, eax
0x18000af06  mov     rcx, [rbp+var_38]
0x18000af0a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000af0e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000af13  xor     r12d, r12d
0x18000af16  test    ebx, ebx
0x18000af18  js      short loc_18000AF2F
0x18000af1a  mov     [rbp+var_20], r13
0x18000af1e  lea     rcx, [rbp+var_20]
0x18000af22  call    ?Release@?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(void)
0x18000af27  inc     rsi
0x18000af2a  jmp     loc_18000AD93
0x18000af2f  mov     [rsp+80h+var_50], esi
0x18000af33  lea     rax, aFailedToSaveIn; "Failed to save InstallSize of entry nod"...
0x18000af3a  mov     [rsp+80h+var_58], rax
0x18000af3f  mov     [rsp+80h+var_60], 94Fh
0x18000af47  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000af4e  lea     r8, aWinreagentExec_0; "WinREAgent::Executor::InternalSave"
0x18000af55  mov     edx, ebx
0x18000af57  mov     ecx, 2
0x18000af5c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000af61  nop
0x18000af62  mov     [rbp+var_20], r13
0x18000af66  lea     rcx, [rbp+var_20]
0x18000af6a  jmp     loc_18000B2CA
0x18000af6f  mov     [rsp+80h+var_50], esi
0x18000af73  lea     rax, aFailedToSavePa; "Failed to save PackageSize of entry nod"...
0x18000af7a  mov     [rsp+80h+var_58], rax
0x18000af7f  mov     [rsp+80h+var_60], 94Ch
0x18000af87  jmp     short loc_18000AF47
0x18000af89  mov     [rsp+80h+var_50], esi
0x18000af8d  lea     rax, aFailedToSavePa_0; "Failed to save PackagePath of entry nod"...
0x18000af94  mov     [rsp+80h+var_58], rax
0x18000af99  mov     [rsp+80h+var_60], 949h
0x18000afa1  jmp     short loc_18000AF47
0x18000afa3  mov     [rsp+80h+var_50], esi
0x18000afa7  lea     rax, aFailedToCreate_38; "Failed to create Packages entry node [%"...
0x18000afae  mov     [rsp+80h+var_58], rax
0x18000afb3  mov     [rsp+80h+var_60], 946h
0x18000afbb  jmp     short loc_18000AF47
0x18000afbd  mov     edi, r12d
0x18000afc0  cmp     edi, [r14+28h]
0x18000afc4  jnb     loc_18000B0BD
0x18000afca  mov     [rbp+var_18], r12
0x18000afce  mov     [rbp+var_20], r13
0x18000afd2  lea     rcx, [rbp+var_20]
0x18000afd6  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18000afdb  mov     rbx, rax
0x18000afde  lea     rdx, aStageoperation; "StageOperation"
0x18000afe5  lea     rcx, [rbp+arg_10]
0x18000afe9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000afee  nop
0x18000afef  mov     r8, rbx
0x18000aff2  lea     rdx, [rbp+arg_10]
0x18000aff6  mov     rcx, r15
0x18000aff9  call    ?AddChild@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::SerializeNode::AddChild(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::SerializeNode * *)
0x18000affe  mov     ebx, eax
0x18000b000  mov     rcx, [rbp+arg_10]
0x18000b004  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000b008  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000b00d  test    ebx, ebx
0x18000b00f  js      short loc_18000B08D
0x18000b011  mov     edx, edi
0x18000b013  lea     rcx, [r14+20h]
0x18000b017  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x18000b01c  mov     rbx, [rax]
0x18000b01f  mov     rax, [rbp+var_20]
0x18000b023  lea     rcx, [rbp+var_20]
0x18000b027  mov     rax, [rax+20h]
0x18000b02b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b030  mov     rdx, rax; struct PushButtonReset::SerializeNode *
0x18000b033  mov     rcx, rbx; struct WinREAgent::Operation *
0x18000b036  call    ?Save@Operation@WinREAgent@@SAJPEAV12@PEAVSerializeNode@PushButtonReset@@@Z; WinREAgent::Operation::Save(WinREAgent::Operation *,PushButtonReset::SerializeNode *)
0x18000b03b  mov     ebx, eax
0x18000b03d  test    eax, eax
0x18000b03f  js      short loc_18000B055
0x18000b041  mov     [rbp+var_20], r13
0x18000b045  lea     rcx, [rbp+var_20]
0x18000b049  call    ?Release@?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(void)
0x18000b04e  inc     edi
0x18000b050  jmp     loc_18000AFC0
0x18000b055  mov     [rsp+80h+var_50], edi
0x18000b059  lea     rax, aFailedToSaveSt; "Failed to save stage operation [%u]"
0x18000b060  mov     [rsp+80h+var_58], rax
0x18000b065  mov     [rsp+80h+var_60], 95Bh
0x18000b06d  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000b074  lea     r8, aWinreagentExec_0; "WinREAgent::Executor::InternalSave"
0x18000b07b  mov     edx, ebx
0x18000b07d  mov     ecx, 2
0x18000b082  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000b087  nop
0x18000b088  jmp     loc_18000AF62
0x18000b08d  lea     rax, aFailedToAddEmp; "Failed to add empty operation node to o"...
0x18000b094  mov     [rsp+80h+var_58], rax
0x18000b099  mov     [rsp+80h+var_60], 957h
0x18000b0a1  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000b0a8  lea     r8, aWinreagentExec_0; "WinREAgent::Executor::InternalSave"
0x18000b0af  mov     edx, ebx
0x18000b0b1  mov     ecx, 2
0x18000b0b6  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000b0bb  jmp     short loc_18000B088
0x18000b0bd  mov     edi, r12d
0x18000b0c0  cmp     edi, [r14+48h]
0x18000b0c4  jnb     loc_18000B1BD
0x18000b0ca  mov     [rbp+var_18], r12
0x18000b0ce  mov     [rbp+var_20], r13
0x18000b0d2  lea     rcx, [rbp+var_20]
0x18000b0d6  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18000b0db  mov     rbx, rax
0x18000b0de  lea     rdx, aCommitoperatio; "CommitOperation"
0x18000b0e5  lea     rcx, [rbp+arg_10]
0x18000b0e9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000b0ee  nop
0x18000b0ef  mov     r8, rbx
0x18000b0f2  lea     rdx, [rbp+arg_10]
0x18000b0f6  mov     rcx, r15
0x18000b0f9  call    ?AddChild@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::SerializeNode::AddChild(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::SerializeNode * *)
0x18000b0fe  mov     ebx, eax
0x18000b100  mov     rcx, [rbp+arg_10]
0x18000b104  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000b108  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000b10d  test    ebx, ebx
0x18000b10f  js      short loc_18000B18D
0x18000b111  mov     edx, edi
0x18000b113  lea     rcx, [r14+40h]
0x18000b117  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x18000b11c  mov     rbx, [rax]
0x18000b11f  mov     rax, [rbp+var_20]
0x18000b123  lea     rcx, [rbp+var_20]
0x18000b127  mov     rax, [rax+20h]
0x18000b12b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b130  mov     rdx, rax; struct PushButtonReset::SerializeNode *
0x18000b133  mov     rcx, rbx; struct WinREAgent::Operation *
0x18000b136  call    ?Save@Operation@WinREAgent@@SAJPEAV12@PEAVSerializeNode@PushButtonReset@@@Z; WinREAgent::Operation::Save(WinREAgent::Operation *,PushButtonReset::SerializeNode *)
0x18000b13b  mov     ebx, eax
0x18000b13d  test    eax, eax
0x18000b13f  js      short loc_18000B155
0x18000b141  mov     [rbp+var_20], r13
0x18000b145  lea     rcx, [rbp+var_20]
0x18000b149  call    ?Release@?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(void)
0x18000b14e  inc     edi
0x18000b150  jmp     loc_18000B0C0
0x18000b155  mov     [rsp+80h+var_50], edi
0x18000b159  lea     rax, aFailedToSaveCo_1; "Failed to save commit operation [%u]"
0x18000b160  mov     [rsp+80h+var_58], rax
0x18000b165  mov     [rsp+80h+var_60], 966h
0x18000b16d  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000b174  lea     r8, aWinreagentExec_0; "WinREAgent::Executor::InternalSave"
0x18000b17b  mov     edx, ebx
0x18000b17d  mov     ecx, 2
0x18000b182  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000b187  nop
0x18000b188  jmp     loc_18000AF62
0x18000b18d  lea     rax, aFailedToAddEmp; "Failed to add empty operation node to o"...
0x18000b194  mov     [rsp+80h+var_58], rax
0x18000b199  mov     [rsp+80h+var_60], 962h
0x18000b1a1  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000b1a8  lea     r8, aWinreagentExec_0; "WinREAgent::Executor::InternalSave"
0x18000b1af  mov     edx, ebx
0x18000b1b1  mov     ecx, 2
0x18000b1b6  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000b1bb  jmp     short loc_18000B188
0x18000b1bd  mov     [rbp+var_8], r12
  ... truncated ...
```
