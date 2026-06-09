# WinREAgent::PrepareWinRE::InternalSave(PushButtonReset::SerializeNode *)

- ea: `0x1800224c0`
- end: `0x1800227e2`
- name: `?InternalSave@PrepareWinRE@WinREAgent@@MEAAJPEAVSerializeNode@PushButtonReset@@@Z`
- size: `802`
- prototype: `__int64 __fastcall(WinREAgent::PrepareWinRE *__hidden this, struct PushButtonReset::SerializeNode *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x1800049a4`
- `0x180005c70`
- `0x180005cc0`
- `0x18000d800`
- `0x18000d92c`
- `0x1800224c0`
- `0x180037344`
- `0x180050e24`
- `0x18005338c`
- `0x180053498`
- `0x18006c690`
- `0x18006f010`

## string_xrefs

- `0x18002261a`: `PackagePath`
- `0x1800226d4`: `InstallSize`
- `0x180022544`: `Failed to create Packages entries node`
- `0x18002276e`: `Failed to create Packages entry node [%u]`
- `0x180022754`: `Failed to save PackagePath of entry node [%u]`
- `0x180022720`: `Failed to save InstallSize of entry node [%u]`
- `0x180022558`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180022782`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x18002255f`: `WinREAgent::PrepareWinRE::InternalSave`
- `0x180022789`: `WinREAgent::PrepareWinRE::InternalSave`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WinREAgent::PrepareWinRE::InternalSave(
        WinREAgent::PrepareWinRE *this,
        PushButtonReset::XmlNode **a2)
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
  int v19; // [rsp+30h] [rbp-29h]
  int v20; // [rsp+30h] [rbp-29h]
  int v21; // [rsp+30h] [rbp-29h]
  int v22; // [rsp+30h] [rbp-29h]
  __int64 v23; // [rsp+40h] [rbp-19h] BYREF
  __int64 v24; // [rsp+48h] [rbp-11h] BYREF
  __int64 v25; // [rsp+50h] [rbp-9h] BYREF
  __int64 v26; // [rsp+58h] [rbp-1h] BYREF
  _QWORD v27[2]; // [rsp+60h] [rbp+7h] BYREF
  _QWORD v28[2]; // [rsp+70h] [rbp+17h] BYREF

  v28[1] = 0;
  v28[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
  v4 = (_QWORD *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v28);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v23,
    (__int64)L"Packages");
  v5 = PushButtonReset::SerializeNode::AddChild(a2, &v23, v4);
  ATL::CStringData::Release((ATL::CStringData *)(v23 - 24));
  if ( v5 >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= *((_QWORD *)this + 20) )
        goto LABEL_15;
      v27[1] = 0;
      v27[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
      v7 = (PushButtonReset::XmlNode **)(*(__int64 (__fastcall **)(_QWORD *))(v28[0] + 24LL))(v28);
      v8 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD *))(v27[0] + 8LL))(v27);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v23,
        (__int64)L"Entry");
      v5 = PushButtonReset::SerializeNode::AddChild(v7, &v23, v8);
      ATL::CStringData::Release((ATL::CStringData *)(v23 - 24));
      if ( v5 < 0 )
      {
        v22 = i;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v5,
          "WinREAgent::PrepareWinRE::InternalSave",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
          776,
          L"Failed to create Packages entry node [%u]",
          v22);
        goto LABEL_14;
      }
      v9 = (*(__int64 (__fastcall **)(_QWORD *))(v27[0] + 24LL))(v27);
      v11 = *(_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                         (char *)this + 152,
                         i,
                         v10);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v24,
        (__int64)L"PackagePath");
      v5 = PushButtonReset::SerializeNode::SetProperty(v9, &v24, v11);
      ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
      if ( v5 < 0 )
      {
        v21 = i;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v5,
          "WinREAgent::PrepareWinRE::InternalSave",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
          779,
          L"Failed to save PackagePath of entry node [%u]",
          v21);
        goto LABEL_14;
      }
      v12 = (*(__int64 (__fastcall **)(_QWORD *))(v27[0] + 24LL))(v27);
      v14 = *(_QWORD *)(*(_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                                     (char *)this + 152,
                                     i,
                                     v13)
                      + 8LL);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v25,
        (__int64)L"PackageSize");
      v5 = PushButtonReset::SerializeNode::SetProperty(v12, &v25, v14);
      ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
      if ( v5 < 0 )
        break;
      v15 = (*(__int64 (__fastcall **)(_QWORD *))(v27[0] + 24LL))(v27);
      v17 = *(_QWORD *)(*(_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                                     (char *)this + 152,
                                     i,
                                     v16)
                      + 16LL);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v26,
        (__int64)L"InstallSize");
      v5 = PushButtonReset::SerializeNode::SetProperty(v15, &v26, v17);
      ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
      if ( v5 < 0 )
      {
        v19 = i;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v5,
          "WinREAgent::PrepareWinRE::InternalSave",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
          785,
          L"Failed to save InstallSize of entry node [%u]",
          v19);
LABEL_14:
        v27[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v27);
        goto LABEL_15;
      }
      v27[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v27);
    }
    v20 = i;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v5,
      "WinREAgent::PrepareWinRE::InternalSave",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
      782,
      L"Failed to save PackageSize of entry node [%u]",
      v20);
    goto LABEL_14;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)v5,
    "WinREAgent::PrepareWinRE::InternalSave",
    "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
    770,
    L"Failed to create Packages entries node");
LABEL_15:
  v28[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
  RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v28);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800224c0  mov     [rsp-8+arg_10], rbx
0x1800224c5  mov     [rsp-8+arg_18], rsi
0x1800224ca  push    rbp
0x1800224cb  push    rdi
0x1800224cc  push    r12
0x1800224ce  push    r14
0x1800224d0  push    r15
0x1800224d2  lea     rbp, [rsp-37h]
0x1800224d7  sub     rsp, 90h
0x1800224de  mov     rax, cs:__security_cookie
0x1800224e5  xor     rax, rsp
0x1800224e8  mov     [rbp+57h+var_30], rax
0x1800224ec  mov     rdi, rdx
0x1800224ef  mov     r14, rcx
0x1800224f2  mov     [rbp+57h+var_38], 0
0x1800224fa  lea     r12, ??_7?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable'
0x180022501  mov     [rbp+57h+var_40], r12
0x180022505  lea     rcx, [rbp+57h+var_40]
0x180022509  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18002250e  mov     rbx, rax
0x180022511  lea     rdx, aPackages; "Packages"
0x180022518  lea     rcx, [rbp+57h+var_70]
0x18002251c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180022521  nop
0x180022522  mov     r8, rbx
0x180022525  lea     rdx, [rbp+57h+var_70]
0x180022529  mov     rcx, rdi
0x18002252c  call    ?AddChild@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::SerializeNode::AddChild(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::SerializeNode * *)
0x180022531  mov     ebx, eax
0x180022533  mov     rcx, [rbp+57h+var_70]
0x180022537  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002253b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180022540  test    ebx, ebx
0x180022542  jns     short loc_180022577
0x180022544  lea     rax, aFailedToCreate_19; "Failed to create Packages entries node"
0x18002254b  mov     [rsp+0B0h+var_88], rax
0x180022550  mov     [rsp+0B0h+var_90], 302h
0x180022558  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002255f  lea     r8, aWinreagentPrep_2; "WinREAgent::PrepareWinRE::InternalSave"
0x180022566  mov     edx, ebx
0x180022568  mov     ecx, 2
0x18002256d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180022572  jmp     loc_1800227AB
0x180022577  xor     esi, esi
0x180022579  cmp     rsi, [r14+0A0h]
0x180022580  jnb     loc_1800227AB
0x180022586  mov     [rbp+57h+var_48], 0
0x18002258e  mov     [rbp+57h+var_50], r12
0x180022592  mov     rax, [rbp+57h+var_40]
0x180022596  lea     rcx, [rbp+57h+var_40]
0x18002259a  mov     rax, [rax+18h]
0x18002259e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225a3  mov     rdi, rax
0x1800225a6  mov     rcx, [rbp+57h+var_50]
0x1800225aa  mov     rax, [rcx+8]
0x1800225ae  lea     rcx, [rbp+57h+var_50]
0x1800225b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225b7  mov     rbx, rax
0x1800225ba  lea     rdx, aEntry; "Entry"
0x1800225c1  lea     rcx, [rbp+57h+var_70]
0x1800225c5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800225ca  nop
0x1800225cb  mov     r8, rbx
0x1800225ce  lea     rdx, [rbp+57h+var_70]
0x1800225d2  mov     rcx, rdi
0x1800225d5  call    ?AddChild@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::SerializeNode::AddChild(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::SerializeNode * *)
0x1800225da  mov     ebx, eax
0x1800225dc  mov     rcx, [rbp+57h+var_70]
0x1800225e0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800225e4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800225e9  test    ebx, ebx
0x1800225eb  js      loc_18002276A
0x1800225f1  mov     rax, [rbp+57h+var_50]
0x1800225f5  lea     rcx, [rbp+57h+var_50]
0x1800225f9  mov     rax, [rax+18h]
0x1800225fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022602  mov     rdi, rax
0x180022605  lea     r15, [r14+98h]
0x18002260c  mov     rdx, rsi
0x18002260f  mov     rcx, r15
0x180022612  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x180022617  mov     rbx, [rax]
0x18002261a  lea     rdx, aPackagepath; "PackagePath"
0x180022621  lea     rcx, [rbp+57h+var_68]
0x180022625  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002262a  nop
0x18002262b  mov     r8, rbx
0x18002262e  lea     rdx, [rbp+57h+var_68]
0x180022632  mov     rcx, rdi
0x180022635  call    ?SetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; PushButtonReset::SerializeNode::SetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002263a  mov     ebx, eax
0x18002263c  mov     rcx, [rbp+57h+var_68]
0x180022640  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180022644  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180022649  test    ebx, ebx
0x18002264b  js      loc_180022750
0x180022651  mov     rax, [rbp+57h+var_50]
0x180022655  lea     rcx, [rbp+57h+var_50]
0x180022659  mov     rax, [rax+18h]
0x18002265d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022662  mov     rdi, rax
0x180022665  mov     rdx, rsi
0x180022668  mov     rcx, r15
0x18002266b  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x180022670  mov     rcx, [rax]
0x180022673  mov     rbx, [rcx+8]
0x180022677  lea     rdx, aPackagesize; "PackageSize"
0x18002267e  lea     rcx, [rbp+57h+var_60]
0x180022682  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180022687  nop
0x180022688  mov     r8, rbx
0x18002268b  lea     rdx, [rbp+57h+var_60]
0x18002268f  mov     rcx, rdi
0x180022692  call    ?SetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_K@Z; PushButtonReset::SerializeNode::SetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64)
0x180022697  mov     ebx, eax
0x180022699  mov     rcx, [rbp+57h+var_60]
0x18002269d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800226a1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800226a6  test    ebx, ebx
0x1800226a8  js      loc_180022736
0x1800226ae  mov     rax, [rbp+57h+var_50]
0x1800226b2  lea     rcx, [rbp+57h+var_50]
0x1800226b6  mov     rax, [rax+18h]
0x1800226ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226bf  mov     rdi, rax
0x1800226c2  mov     rdx, rsi
0x1800226c5  mov     rcx, r15
0x1800226c8  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x1800226cd  mov     rcx, [rax]
0x1800226d0  mov     rbx, [rcx+10h]
0x1800226d4  lea     rdx, aInstallsize; "InstallSize"
0x1800226db  lea     rcx, [rbp+57h+var_58]
0x1800226df  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800226e4  nop
0x1800226e5  mov     r8, rbx
0x1800226e8  lea     rdx, [rbp+57h+var_58]
0x1800226ec  mov     rcx, rdi
0x1800226ef  call    ?SetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_K@Z; PushButtonReset::SerializeNode::SetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64)
0x1800226f4  mov     ebx, eax
0x1800226f6  mov     rcx, [rbp+57h+var_58]
0x1800226fa  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800226fe  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180022703  test    ebx, ebx
0x180022705  js      short loc_18002271C
0x180022707  mov     [rbp+57h+var_50], r12
0x18002270b  lea     rcx, [rbp+57h+var_50]
0x18002270f  call    ?Release@?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(void)
0x180022714  inc     rsi
0x180022717  jmp     loc_180022579
0x18002271c  mov     [rsp+0B0h+var_80], esi
0x180022720  lea     rax, aFailedToSaveIn; "Failed to save InstallSize of entry nod"...
0x180022727  mov     [rsp+0B0h+var_88], rax
0x18002272c  mov     [rsp+0B0h+var_90], 311h
0x180022734  jmp     short loc_180022782
0x180022736  mov     [rsp+0B0h+var_80], esi
0x18002273a  lea     rax, aFailedToSavePa; "Failed to save PackageSize of entry nod"...
0x180022741  mov     [rsp+0B0h+var_88], rax
0x180022746  mov     [rsp+0B0h+var_90], 30Eh
0x18002274e  jmp     short loc_180022782
0x180022750  mov     [rsp+0B0h+var_80], esi
0x180022754  lea     rax, aFailedToSavePa_0; "Failed to save PackagePath of entry nod"...
0x18002275b  mov     [rsp+0B0h+var_88], rax
0x180022760  mov     [rsp+0B0h+var_90], 30Bh
0x180022768  jmp     short loc_180022782
0x18002276a  mov     [rsp+0B0h+var_80], esi
0x18002276e  lea     rax, aFailedToCreate_38; "Failed to create Packages entry node [%"...
0x180022775  mov     [rsp+0B0h+var_88], rax
0x18002277a  mov     [rsp+0B0h+var_90], 308h
0x180022782  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180022789  lea     r8, aWinreagentPrep_2; "WinREAgent::PrepareWinRE::InternalSave"
0x180022790  mov     edx, ebx
0x180022792  mov     ecx, 2
0x180022797  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002279c  nop
0x18002279d  mov     [rbp+57h+var_50], r12
0x1800227a1  lea     rcx, [rbp+57h+var_50]
0x1800227a5  call    ?Release@?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(void)
0x1800227aa  nop
0x1800227ab  mov     [rbp+57h+var_40], r12
0x1800227af  lea     rcx, [rbp+57h+var_40]
0x1800227b3  call    ?Release@?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(void)
0x1800227b8  mov     eax, ebx
0x1800227ba  mov     rcx, [rbp+57h+var_30]
0x1800227be  xor     rcx, rsp; StackCookie
0x1800227c1  call    __security_check_cookie
0x1800227c6  lea     r11, [rsp+0B0h+var_20]
0x1800227ce  mov     rbx, [r11+40h]
0x1800227d2  mov     rsi, [r11+48h]
0x1800227d6  mov     rsp, r11
0x1800227d9  pop     r15
0x1800227db  pop     r14
0x1800227dd  pop     r12
0x1800227df  pop     rdi
0x1800227e0  pop     rbp
0x1800227e1  retn
```
