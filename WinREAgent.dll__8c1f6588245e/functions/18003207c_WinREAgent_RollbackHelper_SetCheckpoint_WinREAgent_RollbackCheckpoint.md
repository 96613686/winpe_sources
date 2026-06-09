# WinREAgent::RollbackHelper::SetCheckpoint(WinREAgent::RollbackCheckpoint)

- ea: `0x18003207c`
- end: `0x1800323ba`
- name: `?SetCheckpoint@RollbackHelper@WinREAgent@@QEAAJW4RollbackCheckpoint@2@@Z`
- size: `830`
- prototype: ``
- caller_count: `8`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180012050`
- `0x180023ea0`
- `0x180025180`
- `0x1800258b8`
- `0x180025c74`
- `0x180029df0`
- `0x18002a950`
- `0x18002bb80`

## callees

- `0x1800049a4`
- `0x180005cc0`
- `0x18000d800`
- `0x18000d92c`
- `0x18001b1e0`
- `0x18002f720`
- `0x1800304b4`
- `0x18003207c`
- `0x180037344`
- `0x180050e24`
- `0x180050fe8`
- `0x180052400`
- `0x1800528ac`
- `0x1800533dc`
- `0x18006c690`
- `0x18006f010`

## string_xrefs

- `0x180032347`: `Failed to write document to [%s]`
- `0x180032120`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x18003219c`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x1800322c0`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x180032301`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x18003235b`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x1800320dc`: `RollbackHelper`
- `0x18003210c`: `Failed to create serialize document`
- `0x180032127`: `WinREAgent::RollbackHelper::SetCheckpoint`
- `0x1800321a3`: `WinREAgent::RollbackHelper::SetCheckpoint`
- `0x1800322c7`: `WinREAgent::RollbackHelper::SetCheckpoint`
- `0x180032308`: `WinREAgent::RollbackHelper::SetCheckpoint`
- `0x180032362`: `WinREAgent::RollbackHelper::SetCheckpoint`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WinREAgent::RollbackHelper::SetCheckpoint(_QWORD *a1, int a2)
{
  _QWORD *v3; // r15
  __int64 v4; // rbx
  int Root; // ebx
  PushButtonReset::SerializeDocument *v6; // rbx
  struct PushButtonReset::SerializeNode **v7; // rax
  unsigned __int64 i; // rsi
  PushButtonReset::XmlNode **v9; // rdi
  _QWORD *v10; // rbx
  __int64 v11; // rdi
  unsigned int v12; // ebx
  __int64 v13; // rax
  int v15; // [rsp+30h] [rbp-39h]
  __int64 v16; // [rsp+40h] [rbp-29h] BYREF
  __int64 v17; // [rsp+48h] [rbp-21h] BYREF
  _QWORD v18[2]; // [rsp+50h] [rbp-19h] BYREF
  _QWORD v19[2]; // [rsp+60h] [rbp-9h] BYREF
  _QWORD v20[2]; // [rsp+70h] [rbp+7h] BYREF
  int v21; // [rsp+D8h] [rbp+6Fh] BYREF

  v21 = a2;
  v3 = a1 + 2;
  ATL::CAtlArray<enum WinREAgent::RollbackCheckpoint,ATL::CElementTraits<enum WinREAgent::RollbackCheckpoint>>::Add(
    a1 + 2,
    &v21);
  v18[1] = 0;
  v18[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable';
  v4 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v18);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v16,
    (__int64)L"RollbackHelper");
  Root = PushButtonReset::SerializeDocument::Create(&v16, v4);
  ATL::CStringData::Release((ATL::CStringData *)(v16 - 24));
  if ( Root >= 0 )
  {
    v19[1] = 0;
    v19[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
    v6 = (PushButtonReset::SerializeDocument *)(*(__int64 (__fastcall **)(_QWORD *))(v18[0] + 24LL))(v18);
    v7 = (struct PushButtonReset::SerializeNode **)(*(__int64 (__fastcall **)(_QWORD *))(v19[0] + 8LL))(v19);
    Root = PushButtonReset::SerializeDocument::GetRoot(v6, v7);
    if ( Root >= 0 )
    {
      for ( i = 0; i < a1[3]; ++i )
      {
        v20[1] = 0;
        v20[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
        v9 = (PushButtonReset::XmlNode **)(*(__int64 (__fastcall **)(_QWORD *))(v19[0] + 24LL))(v19);
        v10 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD *))(v20[0] + 8LL))(v20);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          (__int64)&v16,
          (__int64)L"Checkpoint");
        Root = PushButtonReset::SerializeNode::AddChild(v9, &v16, v10);
        ATL::CStringData::Release((ATL::CStringData *)(v16 - 24));
        if ( Root < 0 )
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)Root,
            "WinREAgent::RollbackHelper::SetCheckpoint",
            "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
            240,
            L"Failed to add empty operation node to operation queue node");
          goto LABEL_11;
        }
        v11 = (*(__int64 (__fastcall **)(_QWORD *))(v20[0] + 24LL))(v20);
        v12 = *(_DWORD *)ATL::CAtlArray<enum WinREAgent::RollbackCheckpoint,ATL::CElementTraits<enum WinREAgent::RollbackCheckpoint>>::GetAt(
                           v3,
                           i);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          (__int64)&v17,
          (__int64)L"Value");
        Root = PushButtonReset::SerializeNode::SetProperty(v11, &v17, v12);
        ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
        if ( Root < 0 )
        {
          v15 = *(_DWORD *)ATL::CAtlArray<enum WinREAgent::RollbackCheckpoint,ATL::CElementTraits<enum WinREAgent::RollbackCheckpoint>>::GetAt(
                             v3,
                             i);
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)Root,
            "WinREAgent::RollbackHelper::SetCheckpoint",
            "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
            243,
            L"Failed to set Value of Checkpoint to [%u]",
            v15);
LABEL_11:
          v20[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
          RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v20);
          goto LABEL_15;
        }
        v20[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v20);
      }
      v13 = (*(__int64 (__fastcall **)(_QWORD *))(v18[0] + 24LL))(v18);
      Root = PushButtonReset::SerializeDocument::Save(v13, a1);
      if ( Root < 0 )
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Root,
          "WinREAgent::RollbackHelper::SetCheckpoint",
          "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
          248,
          L"Failed to write document to [%s]",
          *a1);
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Root,
        "WinREAgent::RollbackHelper::SetCheckpoint",
        "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
        234,
        L"Failed to get root node from serialize document");
    }
LABEL_15:
    v19[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v19);
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Root,
      "WinREAgent::RollbackHelper::SetCheckpoint",
      "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
      230,
      L"Failed to create serialize document");
  }
  v18[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable';
  RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::Release(v18);
  return (unsigned int)Root;
}

```

## disassembly

```asm
0x18003207c  mov     [rsp-8+arg_10], rbx
0x180032081  mov     [rsp-8+arg_8], edx
0x180032085  push    rbp
0x180032086  push    rsi
0x180032087  push    rdi
0x180032088  push    r12
0x18003208a  push    r13
0x18003208c  push    r14
0x18003208e  push    r15
0x180032090  lea     rbp, [rsp-27h]
0x180032095  sub     rsp, 90h
0x18003209c  mov     rax, cs:__security_cookie
0x1800320a3  xor     rax, rsp
0x1800320a6  mov     [rbp+57h+var_40], rax
0x1800320aa  mov     r14, rcx
0x1800320ad  lea     r15, [rcx+10h]
0x1800320b1  lea     rdx, [rbp+57h+arg_8]
0x1800320b5  mov     rcx, r15
0x1800320b8  call    ?Add@?$CAtlArray@W4RollbackCheckpoint@WinREAgent@@V?$CElementTraits@W4RollbackCheckpoint@WinREAgent@@@ATL@@@ATL@@QEAA_KAEBW4RollbackCheckpoint@WinREAgent@@@Z; ATL::CAtlArray<WinREAgent::RollbackCheckpoint,ATL::CElementTraits<WinREAgent::RollbackCheckpoint>>::Add(WinREAgent::RollbackCheckpoint const &)
0x1800320bd  mov     [rbp+57h+var_68], 0
0x1800320c5  lea     r13, ??_7?$CAutoPbrDelete@PEAVSerializeDocument@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable'
0x1800320cc  mov     [rbp+57h+var_70], r13
0x1800320d0  lea     rcx, [rbp+57h+var_70]
0x1800320d4  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x1800320d9  mov     rbx, rax
0x1800320dc  lea     rdx, aRollbackhelper; "RollbackHelper"
0x1800320e3  lea     rcx, [rbp+57h+var_80]
0x1800320e7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800320ec  nop
0x1800320ed  mov     rdx, rbx
0x1800320f0  lea     rcx, [rbp+57h+var_80]
0x1800320f4  call    ?Create@SerializeDocument@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::SerializeDocument::Create(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::SerializeDocument * *)
0x1800320f9  mov     ebx, eax
0x1800320fb  mov     rcx, [rbp+57h+var_80]
0x1800320ff  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180032103  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180032108  test    ebx, ebx
0x18003210a  jns     short loc_18003213F
0x18003210c  lea     rax, aFailedToCreate_32; "Failed to create serialize document"
0x180032113  mov     [rsp+0C0h+var_98], rax
0x180032118  mov     [rsp+0C0h+var_A0], 0E6h
0x180032120  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180032127  lea     r8, aWinreagentRoll_9; "WinREAgent::RollbackHelper::SetCheckpoi"...
0x18003212e  mov     edx, ebx
0x180032130  mov     ecx, 2
0x180032135  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18003213a  jmp     loc_180032384
0x18003213f  mov     [rbp+57h+var_58], 0
0x180032147  lea     r12, ??_7?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable'
0x18003214e  mov     [rbp+57h+var_60], r12
0x180032152  mov     rax, [rbp+57h+var_70]
0x180032156  lea     rcx, [rbp+57h+var_70]
0x18003215a  mov     rax, [rax+18h]
0x18003215e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032163  mov     rbx, rax
0x180032166  mov     rcx, [rbp+57h+var_60]
0x18003216a  mov     rax, [rcx+8]
0x18003216e  lea     rcx, [rbp+57h+var_60]
0x180032172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032177  mov     rdx, rax; struct PushButtonReset::SerializeNode **
0x18003217a  mov     rcx, rbx; this
0x18003217d  call    ?GetRoot@SerializeDocument@PushButtonReset@@QEAAJPEAPEAVSerializeNode@2@@Z; PushButtonReset::SerializeDocument::GetRoot(PushButtonReset::SerializeNode * *)
0x180032182  mov     ebx, eax
0x180032184  test    eax, eax
0x180032186  jns     short loc_1800321BB
0x180032188  lea     rax, aFailedToGetRoo; "Failed to get root node from serialize "...
0x18003218f  mov     [rsp+0C0h+var_98], rax
0x180032194  mov     [rsp+0C0h+var_A0], 0EAh
0x18003219c  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800321a3  lea     r8, aWinreagentRoll_9; "WinREAgent::RollbackHelper::SetCheckpoi"...
0x1800321aa  mov     edx, ebx
0x1800321ac  mov     ecx, 2
0x1800321b1  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800321b6  jmp     loc_180032376
0x1800321bb  xor     esi, esi
0x1800321bd  cmp     rsi, [r14+18h]
0x1800321c1  jnb     loc_18003231D
0x1800321c7  mov     [rbp+57h+var_48], 0
0x1800321cf  mov     [rbp+57h+var_50], r12
0x1800321d3  mov     rax, [rbp+57h+var_60]
0x1800321d7  lea     rcx, [rbp+57h+var_60]
0x1800321db  mov     rax, [rax+18h]
0x1800321df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800321e4  mov     rdi, rax
0x1800321e7  mov     rcx, [rbp+57h+var_50]
0x1800321eb  mov     rax, [rcx+8]
0x1800321ef  lea     rcx, [rbp+57h+var_50]
0x1800321f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800321f8  mov     rbx, rax
0x1800321fb  lea     rdx, aCheckpoint; "Checkpoint"
0x180032202  lea     rcx, [rbp+57h+var_80]
0x180032206  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18003220b  nop
0x18003220c  mov     r8, rbx
0x18003220f  lea     rdx, [rbp+57h+var_80]
0x180032213  mov     rcx, rdi
0x180032216  call    ?AddChild@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::SerializeNode::AddChild(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::SerializeNode * *)
0x18003221b  mov     ebx, eax
0x18003221d  mov     rcx, [rbp+57h+var_80]
0x180032221  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180032225  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003222a  test    ebx, ebx
0x18003222c  js      loc_1800322ED
0x180032232  mov     rax, [rbp+57h+var_50]
0x180032236  lea     rcx, [rbp+57h+var_50]
0x18003223a  mov     rax, [rax+18h]
0x18003223e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032243  mov     rdi, rax
0x180032246  mov     rdx, rsi
0x180032249  mov     rcx, r15
0x18003224c  call    ?GetAt@?$CAtlArray@W4RollbackCheckpoint@WinREAgent@@V?$CElementTraits@W4RollbackCheckpoint@WinREAgent@@@ATL@@@ATL@@QEAAAEAW4RollbackCheckpoint@WinREAgent@@_K@Z; ATL::CAtlArray<WinREAgent::RollbackCheckpoint,ATL::CElementTraits<WinREAgent::RollbackCheckpoint>>::GetAt(unsigned __int64)
0x180032251  mov     ebx, [rax]
0x180032253  lea     rdx, aValue; "Value"
0x18003225a  lea     rcx, [rbp+57h+var_78]
0x18003225e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180032263  nop
0x180032264  mov     r8d, ebx
0x180032267  lea     rdx, [rbp+57h+var_78]
0x18003226b  mov     rcx, rdi
0x18003226e  call    ?SetProperty@SerializeNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@K@Z; PushButtonReset::SerializeNode::SetProperty(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong)
0x180032273  mov     ebx, eax
0x180032275  mov     rcx, [rbp+57h+var_78]
0x180032279  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003227d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180032282  test    ebx, ebx
0x180032284  js      short loc_18003229B
0x180032286  mov     [rbp+57h+var_50], r12
0x18003228a  lea     rcx, [rbp+57h+var_50]
0x18003228e  call    ?Release@?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(void)
0x180032293  inc     rsi
0x180032296  jmp     loc_1800321BD
0x18003229b  mov     rdx, rsi
0x18003229e  mov     rcx, r15
0x1800322a1  call    ?GetAt@?$CAtlArray@W4RollbackCheckpoint@WinREAgent@@V?$CElementTraits@W4RollbackCheckpoint@WinREAgent@@@ATL@@@ATL@@QEAAAEAW4RollbackCheckpoint@WinREAgent@@_K@Z; ATL::CAtlArray<WinREAgent::RollbackCheckpoint,ATL::CElementTraits<WinREAgent::RollbackCheckpoint>>::GetAt(unsigned __int64)
0x1800322a6  mov     ecx, [rax]
0x1800322a8  mov     [rsp+0C0h+var_90], ecx
0x1800322ac  lea     rax, aFailedToSetVal; "Failed to set Value of Checkpoint to [%"...
0x1800322b3  mov     [rsp+0C0h+var_98], rax
0x1800322b8  mov     [rsp+0C0h+var_A0], 0F3h
0x1800322c0  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800322c7  lea     r8, aWinreagentRoll_9; "WinREAgent::RollbackHelper::SetCheckpoi"...
0x1800322ce  mov     edx, ebx
0x1800322d0  mov     ecx, 2
0x1800322d5  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800322da  nop
0x1800322db  mov     [rbp+57h+var_50], r12
0x1800322df  lea     rcx, [rbp+57h+var_50]
0x1800322e3  call    ?Release@?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(void)
0x1800322e8  jmp     loc_180032376
0x1800322ed  lea     rax, aFailedToAddEmp; "Failed to add empty operation node to o"...
0x1800322f4  mov     [rsp+0C0h+var_98], rax
0x1800322f9  mov     [rsp+0C0h+var_A0], 0F0h
0x180032301  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180032308  lea     r8, aWinreagentRoll_9; "WinREAgent::RollbackHelper::SetCheckpoi"...
0x18003230f  mov     edx, ebx
0x180032311  mov     ecx, 2
0x180032316  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18003231b  jmp     short loc_1800322DB
0x18003231d  mov     rax, [rbp+57h+var_70]
0x180032321  lea     rcx, [rbp+57h+var_70]
0x180032325  mov     rax, [rax+18h]
0x180032329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003232e  mov     rdx, r14
0x180032331  mov     rcx, rax
0x180032334  call    ?Save@SerializeDocument@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::SerializeDocument::Save(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180032339  mov     ebx, eax
0x18003233b  test    eax, eax
0x18003233d  jns     short loc_180032376
0x18003233f  mov     rcx, [r14]
0x180032342  mov     qword ptr [rsp+0C0h+var_90], rcx
0x180032347  lea     rax, aFailedToWriteD; "Failed to write document to [%s]"
0x18003234e  mov     [rsp+0C0h+var_98], rax
0x180032353  mov     [rsp+0C0h+var_A0], 0F8h
0x18003235b  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180032362  lea     r8, aWinreagentRoll_9; "WinREAgent::RollbackHelper::SetCheckpoi"...
0x180032369  mov     edx, ebx
0x18003236b  mov     ecx, 2
0x180032370  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180032375  nop
0x180032376  mov     [rbp+57h+var_60], r12
0x18003237a  lea     rcx, [rbp+57h+var_60]
0x18003237e  call    ?Release@?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(void)
0x180032383  nop
0x180032384  mov     [rbp+57h+var_70], r13
0x180032388  lea     rcx, [rbp+57h+var_70]
0x18003238c  call    ?Release@?$CAutoPbrDelete@PEAVSerializeDocument@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::Release(void)
0x180032391  mov     eax, ebx
0x180032393  mov     rcx, [rbp+57h+var_40]
0x180032397  xor     rcx, rsp; StackCookie
0x18003239a  call    __security_check_cookie
0x18003239f  mov     rbx, [rsp+0C0h+arg_10]
0x1800323a7  add     rsp, 90h
0x1800323ae  pop     r15
0x1800323b0  pop     r14
0x1800323b2  pop     r13
0x1800323b4  pop     r12
0x1800323b6  pop     rdi
0x1800323b7  pop     rsi
0x1800323b8  pop     rbp
0x1800323b9  retn
```
