# WinREAgent::RollbackHelper::Load(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x180030d4c`
- end: `0x1800314c4`
- name: `?Load@RollbackHelper@WinREAgent@@AEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `1912`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800314cc`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x180005cc0`
- `0x1800074b8`
- `0x18000d800`
- `0x18000d860`
- `0x18000d92c`
- `0x180011ef4`
- `0x18001b1e0`
- `0x18002f720`
- `0x180030d4c`
- `0x18003717c`
- `0x180037344`
- `0x18004a898`
- `0x18004d1fc`
- `0x18004d2ac`
- `0x1800517d8`
- `0x1800520a4`
- `0x180052400`
- `0x180052528`
- `0x180052a7c`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `msvcrt!free` at `0x180031024`
- `msvcrt!free` at `0x180031024`

## string_xrefs

- `0x180030ddf`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x180030e27`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x180030eb2`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x180030f3f`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x18003109e`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x180031139`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x1800311d3`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x180031318`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x1800313b6`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x180031481`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x180030d97`: `Rollback`
- `0x180030dcb`: `Failed to combine Rollback directory`
- `0x180030e62`: `Rollback.xml`
- `0x180030e9e`: `Failed to combine state file [%s]`
- `0x180030eed`: `RollbackInfo.ini`
- `0x180030f2b`: `Failed to combine ini file [%s]`
- `0x180030d7f`: `Load RollbackHelper from [%s]`
- `0x180030de6`: `WinREAgent::RollbackHelper::Load`
- `0x180030e2e`: `WinREAgent::RollbackHelper::Load`
- `0x180030eb9`: `WinREAgent::RollbackHelper::Load`
- `0x180030f46`: `WinREAgent::RollbackHelper::Load`
- `0x1800310a5`: `WinREAgent::RollbackHelper::Load`
- `0x180031140`: `WinREAgent::RollbackHelper::Load`
- `0x1800311da`: `WinREAgent::RollbackHelper::Load`
- `0x18003131f`: `WinREAgent::RollbackHelper::Load`
- `0x1800313bd`: `WinREAgent::RollbackHelper::Load`
- `0x180031488`: `WinREAgent::RollbackHelper::Load`
- `0x180030e13`: `Rollback directory [%s] doesn't exist`
- `0x18003104b`: `Loading Rollback checkpoints from [%s]`
- `0x18003108a`: `Failed to load rollback state file from [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall WinREAgent::RollbackHelper::Load(_QWORD *a1, _QWORD *a2)
{
  int Root; // ebx
  ATL::CStringData *v5; // rcx
  int Property; // r15d
  ATL::CStringData *v7; // rcx
  ATL::CStringData *v8; // rsi
  int *v9; // r14
  __int64 v10; // rbx
  ATL::CStringData *v11; // r14
  int *v12; // r12
  __int64 v13; // rbx
  _QWORD *v14; // r12
  void *v15; // rcx
  __int64 v16; // rax
  PushButtonReset::SerializeDocument *v17; // rbx
  struct PushButtonReset::SerializeNode **v18; // rax
  PushButtonReset::SerializeNode *v19; // rbx
  struct PushButtonReset::SerializeNodeList **v20; // rax
  unsigned int i; // edi
  PushButtonReset::SerializeNodeList *v22; // rbx
  struct PushButtonReset::SerializeNode **v23; // rax
  __int64 v24; // rbx
  int v26; // [rsp+30h] [rbp-59h]
  unsigned int v27; // [rsp+30h] [rbp-59h]
  unsigned int v28; // [rsp+30h] [rbp-59h]
  __int64 v29; // [rsp+40h] [rbp-49h] BYREF
  __int64 v30; // [rsp+48h] [rbp-41h] BYREF
  __int64 v31; // [rsp+50h] [rbp-39h] BYREF
  __int64 v32; // [rsp+58h] [rbp-31h] BYREF
  __int64 v33; // [rsp+60h] [rbp-29h] BYREF
  _QWORD v34[2]; // [rsp+68h] [rbp-21h] BYREF
  _QWORD v35[2]; // [rsp+78h] [rbp-11h] BYREF
  _QWORD v36[2]; // [rsp+88h] [rbp-1h] BYREF
  _QWORD v37[2]; // [rsp+98h] [rbp+Fh] BYREF

  PushButtonReset::Logging::Trace(0, L"Load RollbackHelper from [%s]", *a2);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v32);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v30,
    (__int64)L"Rollback");
  Root = PushButtonReset::Path::Combine(a2, &v30, &v32);
  ATL::CStringData::Release((ATL::CStringData *)(v30 - 24));
  if ( Root >= 0 )
  {
    if ( !(unsigned __int8)PushButtonReset::Directory::Exists(&v32) )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147943568LL,
        "WinREAgent::RollbackHelper::Load",
        "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
        138,
        L"Rollback directory [%s] doesn't exist",
        *a2);
      Root = -2147023728;
      goto LABEL_43;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v31);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v30);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v29,
      (__int64)L"Rollback.xml");
    Root = PushButtonReset::Path::Combine(a2, &v29, &v31);
    ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
    if ( Root < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Root,
        "WinREAgent::RollbackHelper::Load",
        "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
        146,
        L"Failed to combine state file [%s]",
        L"Rollback.xml");
      ATL::CStringData::Release((ATL::CStringData *)(v30 - 24));
      v5 = (ATL::CStringData *)(v31 - 24);
LABEL_7:
      ATL::CStringData::Release(v5);
      goto LABEL_43;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v29,
      (__int64)L"RollbackInfo.ini");
    Property = PushButtonReset::Path::Combine(a2, &v29, &v30);
    ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
    if ( Property < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Property,
        "WinREAgent::RollbackHelper::Load",
        "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
        149,
        L"Failed to combine ini file [%s]",
        L"RollbackInfo.ini");
      ATL::CStringData::Release((ATL::CStringData *)(v30 - 24));
      v7 = (ATL::CStringData *)(v31 - 24);
LABEL_42:
      ATL::CStringData::Release(v7);
      Root = Property;
      goto LABEL_43;
    }
    v8 = (ATL::CStringData *)(v31 - 24);
    v9 = (int *)(*a1 - 24LL);
    if ( (int *)(v31 - 24) != v9 )
    {
      if ( v9[4] >= 0 && *(_QWORD *)v8 == *(_QWORD *)v9 )
      {
        v10 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v31 - 24);
        ATL::CStringData::Release((ATL::CStringData *)v9);
        *a1 = v10 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(a1, v31, *(unsigned int *)(v31 - 16));
      }
    }
    v11 = (ATL::CStringData *)(v30 - 24);
    v12 = (int *)(a1[1] - 24LL);
    if ( (int *)(v30 - 24) != v12 )
    {
      if ( v12[4] >= 0 && *(_QWORD *)v11 == *(_QWORD *)v12 )
      {
        v13 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v30 - 24);
        ATL::CStringData::Release((ATL::CStringData *)v12);
        a1[1] = v13 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(a1 + 1, v30, *(unsigned int *)(v30 - 16));
      }
    }
    v14 = a1 + 2;
    v15 = (void *)a1[2];
    if ( v15 )
    {
      free(v15);
      *v14 = 0;
    }
    a1[3] = 0;
    a1[4] = 0;
    if ( (unsigned __int8)PushButtonReset::File::Exists(a1) )
    {
      PushButtonReset::Logging::Trace(0, L"Loading Rollback checkpoints from [%s]", *a1);
      v34[1] = 0;
      v34[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable';
      v16 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v34);
      Root = PushButtonReset::SerializeDocument::Load(a1, v16);
      if ( Root < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Root,
          "WinREAgent::RollbackHelper::Load",
          "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
          162,
          L"Failed to load rollback state file from [%s]",
          *a1);
        v34[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable';
LABEL_25:
        RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::Release(v34);
        ATL::CStringData::Release(v11);
        v5 = v8;
        goto LABEL_7;
      }
      v36[1] = 0;
      v36[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
      v17 = (PushButtonReset::SerializeDocument *)(*(__int64 (__fastcall **)(_QWORD *))(v34[0] + 24LL))(v34);
      v18 = (struct PushButtonReset::SerializeNode **)(*(__int64 (__fastcall **)(_QWORD *))(v36[0] + 8LL))(v36);
      Root = PushButtonReset::SerializeDocument::GetRoot(v17, v18);
      if ( Root < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Root,
          "WinREAgent::RollbackHelper::Load",
          "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
          167,
          L"Failed to get root node from [%s]",
          *a1);
LABEL_28:
        v36[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v36);
        v34[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable';
        goto LABEL_25;
      }
      v35[1] = 0;
      v35[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable';
      v19 = (PushButtonReset::SerializeNode *)(*(__int64 (__fastcall **)(_QWORD *))(v36[0] + 24LL))(v36);
      v20 = (struct PushButtonReset::SerializeNodeList **)(*(__int64 (__fastcall **)(_QWORD *))(v35[0] + 8LL))(v35);
      Property = PushButtonReset::SerializeNode::SelectChildren(v19, v20, L"Checkpoint");
      if ( Property >= 0 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= *(_DWORD *)(*(_QWORD *)(*(__int64 (__fastcall **)(_QWORD *))(v35[0] + 24LL))(v35) + 8LL) )
            goto LABEL_39;
          v37[1] = 0;
          v37[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
          v22 = (PushButtonReset::SerializeNodeList *)(*(__int64 (__fastcall **)(_QWORD *))(v35[0] + 24LL))(v35);
          v23 = (struct PushButtonReset::SerializeNode **)(*(__int64 (__fastcall **)(_QWORD *))(v37[0] + 8LL))(v37);
          Root = PushButtonReset::SerializeNodeList::GetNode(v22, i, v23);
          if ( Root < 0 )
            break;
          LODWORD(v29) = 0;
          v24 = (*(__int64 (__fastcall **)(_QWORD *))(v37[0] + 24LL))(v37);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64)&v33,
            (__int64)L"Value");
          Property = PushButtonReset::SerializeNode::GetProperty(v24, &v33, &v29);
          ATL::CStringData::Release((ATL::CStringData *)(v33 - 24));
          if ( Property < 0 )
          {
            v27 = i;
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)Property,
              "WinREAgent::RollbackHelper::Load",
              "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
              182,
              L"Failed to get Value from Checkpoint node [%u]",
              v27);
            v37[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
            RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v37);
LABEL_39:
            v35[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable';
            RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::Release(v35);
            goto LABEL_40;
          }
          if ( (unsigned int)v29 >= 0xA )
          {
            v26 = v29;
            PushButtonReset::Logging::TraceErr(
              2,
              2147500037LL,
              "WinREAgent::RollbackHelper::Load",
              "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
              186,
              L"Get invalid Checkppoint value [%u]",
              v26);
            v37[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
            RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v37);
            v35[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable';
            RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::Release(v35);
            v36[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
            RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v36);
            v34[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable';
            RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::Release(v34);
            ATL::CStringData::Release(v11);
            ATL::CStringData::Release(v8);
            Root = -2147467259;
            goto LABEL_43;
          }
          ATL::CAtlArray<enum WinREAgent::RollbackCheckpoint,ATL::CElementTraits<enum WinREAgent::RollbackCheckpoint>>::Add(
            v14,
            &v29);
          v37[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
          RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v37);
        }
        v28 = i;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Root,
          "WinREAgent::RollbackHelper::Load",
          "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
          178,
          L"Failed to retrieve Checkpoint node [%u]",
          v28);
        v37[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v37);
        v35[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::Release(v35);
        goto LABEL_28;
      }
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Property,
        "WinREAgent::RollbackHelper::Load",
        "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
        172,
        L"Failed to enumerate Checkpoint subnodes");
      v35[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::Release(v35);
LABEL_40:
      v36[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(v36);
      v34[0] = &RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::Release(v34);
    }
    ATL::CStringData::Release(v11);
    v7 = v8;
    goto LABEL_42;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)Root,
    "WinREAgent::RollbackHelper::Load",
    "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
    132,
    L"Failed to combine Rollback directory");
LABEL_43:
  ATL::CStringData::Release((ATL::CStringData *)(v32 - 24));
  return (unsigned int)Root;
}

```

## disassembly

```asm
0x180030d4c  mov     [rsp-8+arg_10], rbx
0x180030d51  push    rbp
0x180030d52  push    rsi
0x180030d53  push    rdi
0x180030d54  push    r12
0x180030d56  push    r13
0x180030d58  push    r14
0x180030d5a  push    r15
0x180030d5c  lea     rbp, [rsp-27h]
0x180030d61  sub     rsp, 0B0h
0x180030d68  mov     rax, cs:__security_cookie
0x180030d6f  xor     rax, rsp
0x180030d72  mov     [rbp+57h+var_38], rax
0x180030d76  mov     rsi, rdx
0x180030d79  mov     rdi, rcx
0x180030d7c  mov     r8, [rdx]
0x180030d7f  lea     rdx, aLoadRollbackhe; "Load RollbackHelper from [%s]"
0x180030d86  xor     ecx, ecx
0x180030d88  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180030d8d  lea     rcx, [rbp+57h+var_88]
0x180030d91  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180030d96  nop
0x180030d97  lea     rdx, aRollback; "Rollback"
0x180030d9e  lea     rcx, [rbp+57h+var_98]
0x180030da2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180030da7  nop
0x180030da8  lea     r8, [rbp+57h+var_88]
0x180030dac  lea     rdx, [rbp+57h+var_98]
0x180030db0  mov     rcx, rsi
0x180030db3  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180030db8  mov     ebx, eax
0x180030dba  mov     rcx, [rbp+57h+var_98]
0x180030dbe  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030dc2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030dc7  test    ebx, ebx
0x180030dc9  jns     short loc_180030DFE
0x180030dcb  lea     rax, aFailedToCombin_1; "Failed to combine Rollback directory"
0x180030dd2  mov     [rsp+0E0h+var_B8], rax
0x180030dd7  mov     [rsp+0E0h+var_C0], 84h
0x180030ddf  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180030de6  lea     r8, aWinreagentRoll_4; "WinREAgent::RollbackHelper::Load"
0x180030ded  mov     edx, ebx
0x180030def  mov     ecx, 2
0x180030df4  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180030df9  jmp     loc_180031433
0x180030dfe  lea     rcx, [rbp+57h+var_88]
0x180030e02  call    ?Exists@Directory@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Directory::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180030e07  test    al, al
0x180030e09  jnz     short loc_180030E4E
0x180030e0b  mov     rax, [rsi]
0x180030e0e  mov     qword ptr [rsp+0E0h+var_B0], rax
0x180030e13  lea     rax, aRollbackDirect; "Rollback directory [%s] doesn't exist"
0x180030e1a  mov     [rsp+0E0h+var_B8], rax
0x180030e1f  mov     [rsp+0E0h+var_C0], 8Ah
0x180030e27  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180030e2e  lea     r8, aWinreagentRoll_4; "WinREAgent::RollbackHelper::Load"
0x180030e35  mov     edx, 80070490h
0x180030e3a  mov     ecx, 2
0x180030e3f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180030e44  mov     ebx, 80070490h
0x180030e49  jmp     loc_180031433
0x180030e4e  lea     rcx, [rbp+57h+var_90]
0x180030e52  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180030e57  nop
0x180030e58  lea     rcx, [rbp+57h+var_98]
0x180030e5c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180030e61  nop
0x180030e62  lea     r14, aRollbackXml; "Rollback.xml"
0x180030e69  mov     rdx, r14
0x180030e6c  lea     rcx, [rbp+57h+var_A0]
0x180030e70  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180030e75  nop
0x180030e76  lea     r8, [rbp+57h+var_90]
0x180030e7a  lea     rdx, [rbp+57h+var_A0]
0x180030e7e  mov     rcx, rsi
0x180030e81  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180030e86  mov     ebx, eax
0x180030e88  mov     rcx, [rbp+57h+var_A0]
0x180030e8c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030e90  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030e95  test    ebx, ebx
0x180030e97  jns     short loc_180030EED
0x180030e99  mov     qword ptr [rsp+0E0h+var_B0], r14
0x180030e9e  lea     rax, aFailedToCombin_3; "Failed to combine state file [%s]"
0x180030ea5  mov     [rsp+0E0h+var_B8], rax
0x180030eaa  mov     [rsp+0E0h+var_C0], 92h
0x180030eb2  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180030eb9  lea     r8, aWinreagentRoll_4; "WinREAgent::RollbackHelper::Load"
0x180030ec0  mov     edx, ebx
0x180030ec2  mov     ecx, 2
0x180030ec7  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180030ecc  nop
0x180030ecd  mov     rcx, [rbp+57h+var_98]
0x180030ed1  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030ed5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030eda  nop
0x180030edb  mov     rcx, [rbp+57h+var_90]
0x180030edf  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030ee3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030ee8  jmp     loc_180031433
0x180030eed  lea     rbx, aRollbackinfoIn; "RollbackInfo.ini"
0x180030ef4  mov     rdx, rbx
0x180030ef7  lea     rcx, [rbp+57h+var_A0]
0x180030efb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180030f00  nop
0x180030f01  lea     r8, [rbp+57h+var_98]
0x180030f05  lea     rdx, [rbp+57h+var_A0]
0x180030f09  mov     rcx, rsi
0x180030f0c  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180030f11  mov     r15d, eax
0x180030f14  mov     rcx, [rbp+57h+var_A0]
0x180030f18  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030f1c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030f21  test    r15d, r15d
0x180030f24  jns     short loc_180030F76
0x180030f26  mov     qword ptr [rsp+0E0h+var_B0], rbx
0x180030f2b  lea     rax, aFailedToCombin_2; "Failed to combine ini file [%s]"
0x180030f32  mov     [rsp+0E0h+var_B8], rax
0x180030f37  mov     [rsp+0E0h+var_C0], 95h
0x180030f3f  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180030f46  lea     r8, aWinreagentRoll_4; "WinREAgent::RollbackHelper::Load"
0x180030f4d  mov     edx, r15d
0x180030f50  mov     ecx, 2
0x180030f55  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180030f5a  nop
0x180030f5b  mov     rcx, [rbp+57h+var_98]
0x180030f5f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030f63  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030f68  nop
0x180030f69  mov     rcx, [rbp+57h+var_90]
0x180030f6d  add     rcx, 0FFFFFFFFFFFFFFE8h
0x180030f71  jmp     loc_18003142B
0x180030f76  mov     rdx, [rbp+57h+var_90]
0x180030f7a  lea     rsi, [rdx-18h]
0x180030f7e  mov     r14, [rdi]
0x180030f81  add     r14, 0FFFFFFFFFFFFFFE8h
0x180030f85  cmp     rsi, r14
0x180030f88  jz      short loc_180030FC1
0x180030f8a  cmp     dword ptr [r14+10h], 0
0x180030f8f  jl      short loc_180030FB5
0x180030f91  mov     rax, [r14]
0x180030f94  cmp     [rsi], rax
0x180030f97  jnz     short loc_180030FB5
0x180030f99  mov     rcx, rsi
0x180030f9c  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180030fa1  mov     rbx, rax
0x180030fa4  mov     rcx, r14; this
0x180030fa7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030fac  lea     rax, [rbx+18h]
0x180030fb0  mov     [rdi], rax
0x180030fb3  jmp     short loc_180030FC1
0x180030fb5  mov     r8d, [rdx-10h]
0x180030fb9  mov     rcx, rdi
0x180030fbc  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180030fc1  lea     r13, [rdi+8]
0x180030fc5  mov     rdx, [rbp+57h+var_98]
0x180030fc9  lea     r14, [rdx-18h]
0x180030fcd  mov     r12, [r13+0]
0x180030fd1  add     r12, 0FFFFFFFFFFFFFFE8h
0x180030fd5  cmp     r14, r12
0x180030fd8  jz      short loc_180031014
0x180030fda  cmp     dword ptr [r12+10h], 0
0x180030fe0  jl      short loc_180031008
0x180030fe2  mov     rax, [r12]
0x180030fe6  cmp     [r14], rax
0x180030fe9  jnz     short loc_180031008
0x180030feb  mov     rcx, r14
0x180030fee  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180030ff3  mov     rbx, rax
0x180030ff6  mov     rcx, r12; this
0x180030ff9  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030ffe  lea     rax, [rbx+18h]
0x180031002  mov     [r13+0], rax
0x180031006  jmp     short loc_180031014
0x180031008  mov     r8d, [rdx-10h]
0x18003100c  mov     rcx, r13
0x18003100f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180031014  lea     r12, [rdi+10h]
0x180031018  mov     rcx, [r12]; Block
0x18003101c  xor     r13d, r13d
0x18003101f  test    rcx, rcx
0x180031022  jz      short loc_18003102E
0x180031024  call    cs:__imp_free
0x18003102a  mov     [r12], r13
0x18003102e  mov     [r12+8], r13
0x180031033  mov     [r12+10h], r13
0x180031038  mov     rcx, rdi
0x18003103b  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180031040  test    al, al
0x180031042  jz      loc_18003141F
0x180031048  mov     r8, [rdi]
0x18003104b  lea     rdx, aLoadingRollbac; "Loading Rollback checkpoints from [%s]"
0x180031052  xor     ecx, ecx
0x180031054  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180031059  mov     [rbp+57h+var_70], r13
0x18003105d  lea     r15, ??_7?$CAutoPbrDelete@PEAVSerializeDocument@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable'
0x180031064  mov     [rbp+57h+var_78], r15
0x180031068  lea     rcx, [rbp+57h+var_78]
0x18003106c  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180031071  mov     rdx, rax
0x180031074  mov     rcx, rdi
0x180031077  call    ?Load@SerializeDocument@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::SerializeDocument::Load(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::SerializeDocument * *)
0x18003107c  mov     ebx, eax
0x18003107e  test    eax, eax
0x180031080  jns     short loc_1800310D8
0x180031082  mov     rcx, [rdi]
0x180031085  mov     qword ptr [rsp+0E0h+var_B0], rcx
0x18003108a  lea     rax, aFailedToLoadRo_0; "Failed to load rollback state file from"...
0x180031091  mov     [rsp+0E0h+var_B8], rax
0x180031096  mov     [rsp+0E0h+var_C0], 0A2h
0x18003109e  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800310a5  lea     r8, aWinreagentRoll_4; "WinREAgent::RollbackHelper::Load"
0x1800310ac  mov     edx, ebx
0x1800310ae  mov     ecx, 2
0x1800310b3  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800310b8  nop
0x1800310b9  mov     [rbp+57h+var_78], r15
0x1800310bd  lea     rcx, [rbp+57h+var_78]
0x1800310c1  call    ?Release@?$CAutoPbrDelete@PEAVSerializeDocument@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::Release(void)
0x1800310c6  nop
0x1800310c7  mov     rcx, r14; this
0x1800310ca  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800310cf  nop
0x1800310d0  mov     rcx, rsi
0x1800310d3  jmp     loc_180030EE3
0x1800310d8  mov     [rbp+57h+var_50], r13
0x1800310dc  lea     r15, ??_7?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable'
0x1800310e3  mov     [rbp+57h+var_58], r15
0x1800310e7  mov     rax, [rbp+57h+var_78]
0x1800310eb  lea     rcx, [rbp+57h+var_78]
0x1800310ef  mov     rax, [rax+18h]
0x1800310f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800310f8  mov     rbx, rax
0x1800310fb  mov     rcx, [rbp+57h+var_58]
0x1800310ff  mov     rax, [rcx+8]
0x180031103  lea     rcx, [rbp+57h+var_58]
0x180031107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003110c  mov     rdx, rax; struct PushButtonReset::SerializeNode **
0x18003110f  mov     rcx, rbx; this
0x180031112  call    ?GetRoot@SerializeDocument@PushButtonReset@@QEAAJPEAPEAVSerializeNode@2@@Z; PushButtonReset::SerializeDocument::GetRoot(PushButtonReset::SerializeNode * *)
0x180031117  mov     ebx, eax
0x180031119  test    eax, eax
0x18003111b  jns     short loc_180031172
0x18003111d  mov     rcx, [rdi]
0x180031120  mov     qword ptr [rsp+0E0h+var_B0], rcx
0x180031125  lea     rax, aFailedToGetRoo_2; "Failed to get root node from [%s]"
0x18003112c  mov     [rsp+0E0h+var_B8], rax
0x180031131  mov     [rsp+0E0h+var_C0], 0A7h
0x180031139  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180031140  lea     r8, aWinreagentRoll_4; "WinREAgent::RollbackHelper::Load"
0x180031147  mov     edx, ebx
0x180031149  mov     ecx, 2
0x18003114e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180031153  nop
0x180031154  mov     [rbp+57h+var_58], r15
0x180031158  lea     rcx, [rbp+57h+var_58]
0x18003115c  call    ?Release@?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::Release(void)
0x180031161  nop
0x180031162  lea     rax, ??_7?$CAutoPbrDelete@PEAVSerializeDocument@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeDocument *>::`vftable'
0x180031169  mov     [rbp+57h+var_78], rax
0x18003116d  jmp     loc_1800310BD
0x180031172  mov     [rbp+57h+var_60], r13
0x180031176  lea     rdi, ??_7?$CAutoPbrDelete@PEAVSerializeNodeList@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::`vftable'
0x18003117d  mov     [rbp+57h+var_68], rdi
0x180031181  mov     rax, [rbp+57h+var_58]
0x180031185  lea     rcx, [rbp+57h+var_58]
0x180031189  mov     rax, [rax+18h]
0x18003118d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031192  mov     rbx, rax
0x180031195  mov     rcx, [rbp+57h+var_68]
0x180031199  mov     rax, [rcx+8]
0x18003119d  lea     rcx, [rbp+57h+var_68]
0x1800311a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800311a6  lea     r8, aCheckpoint; "Checkpoint"
0x1800311ad  mov     rdx, rax; struct PushButtonReset::SerializeNodeList **
0x1800311b0  mov     rcx, rbx; this
0x1800311b3  call    ?SelectChildren@SerializeNode@PushButtonReset@@QEAAJPEAPEAVSerializeNodeList@2@PEBGZZ; PushButtonReset::SerializeNode::SelectChildren(PushButtonReset::SerializeNodeList * *,ushort const *,...)
0x1800311b8  mov     r15d, eax
0x1800311bb  test    eax, eax
0x1800311bd  jns     short loc_180031209
0x1800311bf  lea     rax, aFailedToEnumer; "Failed to enumerate Checkpoint subnodes"
0x1800311c6  mov     [rsp+0E0h+var_B8], rax
0x1800311cb  mov     [rsp+0E0h+var_C0], 0ACh
0x1800311d3  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800311da  lea     r8, aWinreagentRoll_4; "WinREAgent::RollbackHelper::Load"
0x1800311e1  mov     edx, r15d
0x1800311e4  mov     ecx, 2
0x1800311e9  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800311ee  nop
0x1800311ef  mov     [rbp+57h+var_68], rdi
0x1800311f3  lea     rcx, [rbp+57h+var_68]
0x1800311f7  call    ?Release@?$CAutoPbrDelete@PEAVSerializeNodeList@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::SerializeNodeList *>::Release(void)
0x1800311fc  nop
0x1800311fd  lea     rbx, ??_7?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable'
0x180031204  jmp     loc_1800313FC
0x180031209  mov     edi, r13d
0x18003120c  lea     rbx, ??_7?$CAutoPbrDelete@PEAVSerializeNode@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::SerializeNode *>::`vftable'
0x180031213  mov     rax, [rbp+57h+var_68]
0x180031217  lea     rcx, [rbp+57h+var_68]
0x18003121b  mov     rax, [rax+18h]
  ... truncated ...
```
