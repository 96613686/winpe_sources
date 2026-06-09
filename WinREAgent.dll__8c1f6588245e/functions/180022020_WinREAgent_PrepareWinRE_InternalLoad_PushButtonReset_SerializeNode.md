# WinREAgent::PrepareWinRE::InternalLoad(PushButtonReset::SerializeNode *)

- ea: `0x180022020`
- end: `0x1800224b5`
- name: `?InternalLoad@PrepareWinRE@WinREAgent@@MEAAJPEAVSerializeNode@PushButtonReset@@@Z`
- size: `1173`
- prototype: `int(WinREAgent::PrepareWinRE *__hidden this, struct PushButtonReset::SerializeNode *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x180003c94`
- `0x1800049a4`
- `0x180004af8`
- `0x180005c00`
- `0x180005cc0`
- `0x1800064a0`
- `0x1800074b8`
- `0x18000d5a0`
- `0x18000d800`
- `0x18000d860`
- `0x18000d92c`
- `0x180011ef4`
- `0x180022020`
- `0x180037344`
- `0x1800517d8`
- `0x180052194`
- `0x1800521f8`
- `0x180052a7c`
- `0x18006c690`
- `0x18006f010`

## string_xrefs

- `0x180022152`: `PackagePath`
- `0x18002241b`: `Failed to load PackagePath of entry node [%u]`
- `0x1800221ea`: `InstallSize`
- `0x180022375`: `Failed to load InstallSize of entry node [%u]`
- `0x180022097`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x18002233f`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180022389`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x18002242f`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180022471`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x18002209e`: `WinREAgent::PrepareWinRE::InternalLoad`
- `0x180022346`: `WinREAgent::PrepareWinRE::InternalLoad`
- `0x180022390`: `WinREAgent::PrepareWinRE::InternalLoad`
- `0x180022436`: `WinREAgent::PrepareWinRE::InternalLoad`
- `0x180022478`: `WinREAgent::PrepareWinRE::InternalLoad`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WinREAgent::PrepareWinRE::InternalLoad(
        WinREAgent::PrepareWinRE *this,
        struct PushButtonReset::SerializeNode *a2)
{
  struct PushButtonReset::SerializeNodeList **v4; // rax
  int Property; // edi
  unsigned int i; // esi
  PushButtonReset::SerializeNodeList *v7; // rbx
  struct PushButtonReset::SerializeNode **v8; // rax
  int Node; // ebx
  __int64 v10; // rbx
  __int64 v11; // rbx
  __int64 v12; // rbx
  _QWORD *v13; // rax
  _QWORD *v14; // r12
  ATL::CStringData *v15; // r15
  int *v16; // r14
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rax
  _QWORD *v20; // rax
  unsigned int v22; // [rsp+30h] [rbp-59h]
  unsigned int v23; // [rsp+30h] [rbp-59h]
  unsigned int v24; // [rsp+30h] [rbp-59h]
  unsigned int v25; // [rsp+30h] [rbp-59h]
  __int64 v26; // [rsp+40h] [rbp-49h] BYREF
  _QWORD *v27; // [rsp+48h] [rbp-41h] BYREF
  __int64 v28; // [rsp+50h] [rbp-39h] BYREF
  __int64 v29; // [rsp+58h] [rbp-31h] BYREF
  __int64 v30; // [rsp+60h] [rbp-29h] BYREF
  __int64 v31; // [rsp+68h] [rbp-21h] BYREF
  _QWORD v32[2]; // [rsp+70h] [rbp-19h] BYREF
  _QWORD v33[2]; // [rsp+80h] [rbp-9h] BYREF
  void **v34; // [rsp+90h] [rbp+7h] BYREF
  _QWORD *v35; // [rsp+98h] [rbp+Fh]

  v33[1] = 0;
  v33[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable';
  v4 = (struct PushButtonReset::SerializeNodeList **)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v33);
  Property = PushButtonReset::SerializeNode::SelectChildren(a2, v4, L"Packages/Entry");
  if ( Property >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= *(_DWORD *)(*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD *))(v33[0] + 24LL))(v33) + 8LL) )
        goto LABEL_19;
      v32[1] = 0;
      v32[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
      v7 = (PushButtonReset::SerializeNodeList *)(*(__int64 (__fastcall **)(_QWORD *))(v33[0] + 24LL))(v33);
      v8 = (struct PushButtonReset::SerializeNode **)(*(__int64 (__fastcall **)(_QWORD *))(v32[0] + 8LL))(v32);
      Node = PushButtonReset::SerializeNodeList::GetNode(v7, i, v8);
      if ( Node < 0 )
        break;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v26);
      v31 = 0;
      v27 = 0;
      v10 = (*(__int64 (__fastcall **)(_QWORD *))(v32[0] + 24LL))(v32);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v28,
        (__int64)L"PackagePath");
      Node = PushButtonReset::SerializeNode::GetProperty(v10, &v28, &v26);
      ATL::CStringData::Release((ATL::CStringData *)(v28 - 24));
      if ( Node < 0 )
      {
        v24 = i;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Node,
          "WinREAgent::PrepareWinRE::InternalLoad",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
          812,
          L"Failed to load PackagePath of entry node [%u]",
          v24);
        goto LABEL_23;
      }
      v11 = (*(__int64 (__fastcall **)(_QWORD *))(v32[0] + 24LL))(v32);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v29,
        (__int64)L"PackageSize");
      Node = PushButtonReset::SerializeNode::GetProperty(v11, &v29, &v31);
      ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
      if ( Node < 0 )
      {
        v23 = i;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Node,
          "WinREAgent::PrepareWinRE::InternalLoad",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
          815,
          L"Failed to load PackageSize of entry node [%u]",
          v23);
LABEL_23:
        ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
        goto LABEL_25;
      }
      v12 = (*(__int64 (__fastcall **)(_QWORD *))(v32[0] + 24LL))(v32);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v30,
        (__int64)L"InstallSize");
      Property = PushButtonReset::SerializeNode::GetProperty(v12, &v30, &v27);
      ATL::CStringData::Release((ATL::CStringData *)(v30 - 24));
      if ( Property < 0 )
      {
        v22 = i;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Property,
          "WinREAgent::PrepareWinRE::InternalLoad",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
          818,
          L"Failed to load InstallSize of entry node [%u]",
          v22);
        goto LABEL_18;
      }
      v35 = PbrNew<WinREAgent::PACKAGE_INFO,>();
      v34 = &RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::`vftable';
      if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!((__int64 *)&v34) )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          2147942414LL,
          "WinREAgent::PrepareWinRE::InternalLoad",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
          821,
          L"Failed to allocate package");
        v34 = &RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::Release(&v34);
        Property = -2147024882;
LABEL_18:
        ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
        v32[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v32);
LABEL_19:
        v33[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable';
        goto LABEL_20;
      }
      v13 = (_QWORD *)((__int64 (__fastcall *)(void ***))v34[3])(&v34);
      v14 = v13;
      v15 = (ATL::CStringData *)(v26 - 24);
      v16 = (int *)(*v13 - 24LL);
      if ( (int *)(v26 - 24) != v16 )
      {
        if ( v16[4] >= 0 && *(_QWORD *)v15 == *(_QWORD *)v16 )
        {
          v17 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v26 - 24);
          ATL::CStringData::Release((ATL::CStringData *)v16);
          *v14 = v17 + 24;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(v13, v26, *(unsigned int *)(v26 - 16));
        }
      }
      v18 = ((__int64 (__fastcall *)(void ***))v34[3])(&v34);
      *(_QWORD *)(v18 + 8) = v31;
      v19 = ((__int64 (__fastcall *)(void ***))v34[3])(&v34);
      *(_QWORD *)(v19 + 16) = v27;
      v20 = v35;
      v35 = 0;
      v27 = v20;
      ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
        (_QWORD *)this + 19,
        &v27);
      v34 = &RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::Release(&v34);
      ATL::CStringData::Release(v15);
      v32[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v32);
    }
    v25 = i;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Node,
      "WinREAgent::PrepareWinRE::InternalLoad",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
      805,
      L"Failed to retrieve Packages entry node [%u]",
      v25);
LABEL_25:
    v32[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v32);
    v33[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::Release(v33);
    return (unsigned int)Node;
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Property,
      "WinREAgent::PrepareWinRE::InternalLoad",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
      798,
      L"Failed to look up Packages entries");
    v33[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable';
LABEL_20:
    RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::Release(v33);
    return (unsigned int)Property;
  }
}

```

## disassembly

```asm
0x180022020  mov     [rsp-8+arg_10], rbx
0x180022025  push    rbp
0x180022026  push    rsi
0x180022027  push    rdi
0x180022028  push    r12
0x18002202a  push    r13
0x18002202c  push    r14
0x18002202e  push    r15
0x180022030  lea     rbp, [rsp-27h]
0x180022035  sub     rsp, 0B0h
0x18002203c  mov     rax, cs:__security_cookie
0x180022043  xor     rax, rsp
0x180022046  mov     [rbp+57h+var_40], rax
0x18002204a  mov     rbx, rdx
0x18002204d  mov     r13, rcx
0x180022050  xor     r14d, r14d
0x180022053  mov     [rbp+57h+var_58], r14
0x180022057  lea     r15, ??_7?$CAutoPbrDelete@PEAVSerializeNodeList@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable'
0x18002205e  mov     [rbp+57h+var_60], r15
0x180022062  lea     rcx, [rbp+57h+var_60]
0x180022066  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18002206b  mov     rdx, rax; struct PushButtonReset::SerializeNodeList **
0x18002206e  lea     r8, aPackagesEntry; "Packages/Entry"
0x180022075  mov     rcx, rbx; this
0x180022078  call    ?SelectChildren@SerializeNode@PushButtonReset@@QEAAJPEAPEAVSerializeNodeList@2@PEBGZZ; PushButtonReset::SerializeNode::SelectChildren(PushButtonReset::SerializeNodeList * *,ushort const *,...)
0x18002207d  mov     edi, eax
0x18002207f  test    eax, eax
0x180022081  jns     short loc_1800220BA
0x180022083  lea     rax, aFailedToLookUp_1; "Failed to look up Packages entries"
0x18002208a  mov     [rsp+0E0h+var_B8], rax
0x18002208f  mov     [rsp+0E0h+var_C0], 31Eh
0x180022097  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002209e  lea     r8, aWinreagentPrep_1; "WinREAgent::PrepareWinRE::InternalLoad"
0x1800220a5  mov     edx, edi
0x1800220a7  lea     ecx, [r14+2]
0x1800220ab  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800220b0  nop
0x1800220b1  mov     [rbp+57h+var_60], r15
0x1800220b5  jmp     loc_1800223CB
0x1800220ba  mov     esi, r14d
0x1800220bd  lea     r15, ??_7?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable'
0x1800220c4  lea     r12, ??_7?$CAutoPbrDelete@PEAUPACKAGE_INFO@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::`vftable'
0x1800220cb  mov     rax, [rbp+57h+var_60]
0x1800220cf  lea     rcx, [rbp+57h+var_60]
0x1800220d3  mov     rax, [rax+18h]
0x1800220d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220dc  mov     rcx, [rax]
0x1800220df  cmp     esi, [rcx+8]
0x1800220e2  jnb     loc_1800223C0
0x1800220e8  mov     [rbp+57h+var_68], r14
0x1800220ec  mov     [rbp+57h+var_70], r15
0x1800220f0  mov     rax, [rbp+57h+var_60]
0x1800220f4  lea     rcx, [rbp+57h+var_60]
0x1800220f8  mov     rax, [rax+18h]
0x1800220fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022101  mov     rbx, rax
0x180022104  mov     rcx, [rbp+57h+var_70]
0x180022108  mov     rax, [rcx+8]
0x18002210c  lea     rcx, [rbp+57h+var_70]
0x180022110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022115  mov     r8, rax; struct PushButtonReset::SerializeNode **
0x180022118  mov     edx, esi; unsigned int
0x18002211a  mov     rcx, rbx; this
0x18002211d  call    ?GetNode@SerializeNodeList@PushButtonReset@@QEAAJKPEAPEAVSerializeNode@2@@Z; PushButtonReset::SerializeNodeList::GetNode(ulong,PushButtonReset::SerializeNode * *)
0x180022122  mov     ebx, eax
0x180022124  test    eax, eax
0x180022126  js      loc_180022459
0x18002212c  lea     rcx, [rbp+57h+var_A0]
0x180022130  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180022135  nop
0x180022136  mov     [rbp+57h+var_78], r14
0x18002213a  mov     [rbp+57h+var_98], r14
0x18002213e  mov     rax, [rbp+57h+var_70]
0x180022142  lea     rcx, [rbp+57h+var_70]
0x180022146  mov     rax, [rax+18h]
0x18002214a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002214f  mov     rbx, rax
0x180022152  lea     rdx, aPackagepath; "PackagePath"
0x180022159  lea     rcx, [rbp+57h+var_90]
0x18002215d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180022162  nop
0x180022163  lea     r8, [rbp+57h+var_A0]
0x180022167  lea     rdx, [rbp+57h+var_90]
0x18002216b  mov     rcx, rbx
0x18002216e  call    ?GetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::SerializeNode::GetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180022173  mov     ebx, eax
0x180022175  mov     rcx, [rbp+57h+var_90]
0x180022179  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002217d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180022182  test    ebx, ebx
0x180022184  js      loc_180022417
0x18002218a  mov     rax, [rbp+57h+var_70]
0x18002218e  lea     rcx, [rbp+57h+var_70]
0x180022192  mov     rax, [rax+18h]
0x180022196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002219b  mov     rbx, rax
0x18002219e  lea     rdx, aPackagesize; "PackageSize"
0x1800221a5  lea     rcx, [rbp+57h+var_88]
0x1800221a9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800221ae  nop
0x1800221af  lea     r8, [rbp+57h+var_78]
0x1800221b3  lea     rdx, [rbp+57h+var_88]
0x1800221b7  mov     rcx, rbx
0x1800221ba  call    ?GetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_K@Z; PushButtonReset::SerializeNode::GetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64 *)
0x1800221bf  mov     ebx, eax
0x1800221c1  mov     rcx, [rbp+57h+var_88]
0x1800221c5  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800221c9  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800221ce  test    ebx, ebx
0x1800221d0  js      loc_1800223FD
0x1800221d6  mov     rax, [rbp+57h+var_70]
0x1800221da  lea     rcx, [rbp+57h+var_70]
0x1800221de  mov     rax, [rax+18h]
0x1800221e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221e7  mov     rbx, rax
0x1800221ea  lea     rdx, aInstallsize; "InstallSize"
0x1800221f1  lea     rcx, [rbp+57h+var_80]
0x1800221f5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800221fa  nop
0x1800221fb  lea     r8, [rbp+57h+var_98]
0x1800221ff  lea     rdx, [rbp+57h+var_80]
0x180022203  mov     rcx, rbx
0x180022206  call    ?GetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_K@Z; PushButtonReset::SerializeNode::GetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64 *)
0x18002220b  mov     edi, eax
0x18002220d  mov     rcx, [rbp+57h+var_80]
0x180022211  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180022215  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002221a  test    edi, edi
0x18002221c  js      loc_180022371
0x180022222  call    ??$PbrNew@UPACKAGE_INFO@WinREAgent@@$$V@@YAPEAUPACKAGE_INFO@WinREAgent@@XZ; PbrNew<WinREAgent::PACKAGE_INFO,>(void)
0x180022227  mov     [rbp+57h+var_48], rax
0x18002222b  mov     [rbp+57h+var_50], r12
0x18002222f  lea     rcx, [rbp+57h+var_50]
0x180022233  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x180022238  test    al, al
0x18002223a  jnz     loc_18002232B
0x180022240  mov     rax, [rbp+57h+var_50]
0x180022244  lea     rcx, [rbp+57h+var_50]
0x180022248  mov     rax, [rax+18h]
0x18002224c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022251  mov     r12, rax
0x180022254  mov     rdx, [rbp+57h+var_A0]
0x180022258  lea     r15, [rdx-18h]
0x18002225c  mov     r14, [rax]
0x18002225f  add     r14, 0FFFFFFFFFFFFFFE8h
0x180022263  cmp     r15, r14
0x180022266  jz      short loc_1800222A0
0x180022268  cmp     dword ptr [r14+10h], 0
0x18002226d  jl      short loc_180022294
0x18002226f  mov     r8, [r14]
0x180022272  cmp     [r15], r8
0x180022275  jnz     short loc_180022294
0x180022277  mov     rcx, r15
0x18002227a  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18002227f  mov     rbx, rax
0x180022282  mov     rcx, r14; this
0x180022285  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002228a  lea     rax, [rbx+18h]
0x18002228e  mov     [r12], rax
0x180022292  jmp     short loc_1800222A0
0x180022294  mov     r8d, [rdx-10h]
0x180022298  mov     rcx, r12
0x18002229b  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800222a0  mov     rax, [rbp+57h+var_50]
0x1800222a4  lea     rcx, [rbp+57h+var_50]
0x1800222a8  mov     rax, [rax+18h]
0x1800222ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222b1  mov     rcx, [rbp+57h+var_78]
0x1800222b5  mov     [rax+8], rcx
0x1800222b9  mov     rax, [rbp+57h+var_50]
0x1800222bd  lea     rcx, [rbp+57h+var_50]
0x1800222c1  mov     rax, [rax+18h]
0x1800222c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222ca  mov     rdx, [rbp+57h+var_98]
0x1800222ce  mov     [rax+10h], rdx
0x1800222d2  mov     rax, [rbp+57h+var_48]
0x1800222d6  xor     r14d, r14d
0x1800222d9  mov     [rbp+57h+var_48], r14
0x1800222dd  mov     [rbp+57h+var_98], rax
0x1800222e1  lea     rcx, [r13+98h]
0x1800222e8  lea     rdx, [rbp+57h+var_98]
0x1800222ec  call    ?Add@?$CAtlArray@PEAUPACKAGE_INFO@WinREAgent@@V?$CElementTraits@PEAUPACKAGE_INFO@WinREAgent@@@ATL@@@ATL@@QEAA_KAEBQEAUPACKAGE_INFO@WinREAgent@@@Z; ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(WinREAgent::PACKAGE_INFO * const &)
0x1800222f1  nop
0x1800222f2  lea     r12, ??_7?$CAutoPbrDelete@PEAUPACKAGE_INFO@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::`vftable'
0x1800222f9  mov     [rbp+57h+var_50], r12
0x1800222fd  lea     rcx, [rbp+57h+var_50]
0x180022301  call    ?Release@?$CAutoPbrDelete@PEAUPACKAGE_INFO@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::Release(void)
0x180022306  nop
0x180022307  mov     rcx, r15; this
0x18002230a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002230f  nop
0x180022310  lea     r15, ??_7?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable'
0x180022317  mov     [rbp+57h+var_70], r15
0x18002231b  lea     rcx, [rbp+57h+var_70]
0x18002231f  call    ?Release@?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(void)
0x180022324  inc     esi
0x180022326  jmp     loc_1800220CB
0x18002232b  lea     rax, aFailedToAlloca_23; "Failed to allocate package"
0x180022332  mov     [rsp+0E0h+var_B8], rax
0x180022337  mov     [rsp+0E0h+var_C0], 335h
0x18002233f  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180022346  lea     r8, aWinreagentPrep_1; "WinREAgent::PrepareWinRE::InternalLoad"
0x18002234d  mov     edx, 8007000Eh
0x180022352  mov     ecx, 2
0x180022357  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002235c  nop
0x18002235d  mov     [rbp+57h+var_50], r12
0x180022361  lea     rcx, [rbp+57h+var_50]
0x180022365  call    ?Release@?$CAutoPbrDelete@PEAUPACKAGE_INFO@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::PACKAGE_INFO *>::Release(void)
0x18002236a  mov     edi, 8007000Eh
0x18002236f  jmp     short loc_1800223A4
0x180022371  mov     [rsp+0E0h+var_B0], esi
0x180022375  lea     rax, aFailedToLoadIn; "Failed to load InstallSize of entry nod"...
0x18002237c  mov     [rsp+0E0h+var_B8], rax
0x180022381  mov     [rsp+0E0h+var_C0], 332h
0x180022389  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180022390  lea     r8, aWinreagentPrep_1; "WinREAgent::PrepareWinRE::InternalLoad"
0x180022397  mov     edx, edi
0x180022399  mov     ecx, 2
0x18002239e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800223a3  nop
0x1800223a4  mov     rcx, [rbp+57h+var_A0]
0x1800223a8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800223ac  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800223b1  nop
0x1800223b2  mov     [rbp+57h+var_70], r15
0x1800223b6  lea     rcx, [rbp+57h+var_70]
0x1800223ba  call    ?Release@?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(void)
0x1800223bf  nop
0x1800223c0  lea     rax, ??_7?$CAutoPbrDelete@PEAVSerializeNodeList@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable'
0x1800223c7  mov     [rbp+57h+var_60], rax
0x1800223cb  lea     rcx, [rbp+57h+var_60]
0x1800223cf  call    ?Release@?$CAutoPbrDelete@PEAVSerializeNodeList@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::Release(void)
0x1800223d4  mov     eax, edi
0x1800223d6  mov     rcx, [rbp+57h+var_40]
0x1800223da  xor     rcx, rsp; StackCookie
0x1800223dd  call    __security_check_cookie
0x1800223e2  mov     rbx, [rsp+0E0h+arg_10]
0x1800223ea  add     rsp, 0B0h
0x1800223f1  pop     r15
0x1800223f3  pop     r14
0x1800223f5  pop     r13
0x1800223f7  pop     r12
0x1800223f9  pop     rdi
0x1800223fa  pop     rsi
0x1800223fb  pop     rbp
0x1800223fc  retn
0x1800223fd  mov     [rsp+0E0h+var_B0], esi
0x180022401  lea     rax, aFailedToLoadPa; "Failed to load PackageSize of entry nod"...
0x180022408  mov     [rsp+0E0h+var_B8], rax
0x18002240d  mov     [rsp+0E0h+var_C0], 32Fh
0x180022415  jmp     short loc_18002242F
0x180022417  mov     [rsp+0E0h+var_B0], esi
0x18002241b  lea     rax, aFailedToLoadPa_0; "Failed to load PackagePath of entry nod"...
0x180022422  mov     [rsp+0E0h+var_B8], rax
0x180022427  mov     [rsp+0E0h+var_C0], 32Ch
0x18002242f  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180022436  lea     r8, aWinreagentPrep_1; "WinREAgent::PrepareWinRE::InternalLoad"
0x18002243d  mov     edx, ebx
0x18002243f  mov     ecx, 2
0x180022444  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180022449  nop
0x18002244a  mov     rcx, [rbp+57h+var_A0]
0x18002244e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180022452  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180022457  jmp     short loc_18002248C
0x180022459  mov     [rsp+0E0h+var_B0], esi
0x18002245d  lea     rax, aFailedToRetrie; "Failed to retrieve Packages entry node "...
0x180022464  mov     [rsp+0E0h+var_B8], rax
0x180022469  mov     [rsp+0E0h+var_C0], 325h
0x180022471  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180022478  lea     r8, aWinreagentPrep_1; "WinREAgent::PrepareWinRE::InternalLoad"
0x18002247f  mov     edx, ebx
0x180022481  mov     ecx, 2
0x180022486  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002248b  nop
0x18002248c  mov     [rbp+57h+var_70], r15
0x180022490  lea     rcx, [rbp+57h+var_70]
0x180022494  call    ?Release@?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(void)
0x180022499  nop
0x18002249a  lea     rax, ??_7?$CAutoPbrDelete@PEAVSerializeNodeList@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable'
0x1800224a1  mov     [rbp+57h+var_60], rax
0x1800224a5  lea     rcx, [rbp+57h+var_60]
0x1800224a9  call    ?Release@?$CAutoPbrDelete@PEAVSerializeNodeList@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::Release(void)
0x1800224ae  mov     eax, ebx
0x1800224b0  jmp     loc_1800223D6
```
