# WinREAgent::RollbackHelper::Initialize(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x1800308cc`
- end: `0x180030d45`
- name: `?Initialize@RollbackHelper@WinREAgent@@AEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `1145`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002f85c`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x1800074b8`
- `0x18000d92c`
- `0x180011ef4`
- `0x1800308cc`
- `0x18003717c`
- `0x180037344`
- `0x18004a898`
- `0x18004bb04`
- `0x18004c2b0`
- `0x18004c418`
- `0x18004d1fc`
- `0x18004d2ac`

## import_xrefs

- `msvcrt!free` at `0x180030c36`
- `msvcrt!free` at `0x180030c36`

## string_xrefs

- `0x18003090b`: `Work directory [%s] doesn't exist`
- `0x18003091f`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x18003099a`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x1800309ff`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x180030a6b`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x180030af6`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x180030c8d`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x180030cf0`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x180030926`: `WinREAgent::RollbackHelper::Initialize`
- `0x1800309a1`: `WinREAgent::RollbackHelper::Initialize`
- `0x180030a06`: `WinREAgent::RollbackHelper::Initialize`
- `0x180030a72`: `WinREAgent::RollbackHelper::Initialize`
- `0x180030afd`: `WinREAgent::RollbackHelper::Initialize`
- `0x180030c94`: `WinREAgent::RollbackHelper::Initialize`
- `0x180030cf7`: `WinREAgent::RollbackHelper::Initialize`
- `0x180030950`: `Rollback`
- `0x180030986`: `Failed to combine Rollback directory`
- `0x1800309c7`: `Deleting existing Rollback directory`
- `0x1800309eb`: `Failed to delete existing Rollback directory [%s]`
- `0x180030a57`: `Failed to create Rollback directory [%s]`
- `0x180030aa4`: `Rollback.xml`
- `0x180030ae2`: `Failed to combine state file [%s]`
- `0x180030b2d`: `RollbackInfo.ini`
- `0x180030b6b`: `Failed to combine ini file [%s]`
- `0x180030c54`: `Delete existing state file`
- `0x180030cb7`: `Delete existing state file`
- `0x180030c79`: `Failed to delete existing state file [%s]`
- `0x180030cdc`: `Failed to delete existing state file [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WinREAgent::RollbackHelper::Initialize(_QWORD *a1, _QWORD *a2)
{
  int v5; // r15d
  const WCHAR *v6; // rdx
  int v7; // eax
  __int64 v8; // rbx
  ATL::CStringData *v9; // rcx
  ATL::CStringData *v10; // rcx
  ATL::CStringData *v11; // r13
  int *v12; // r12
  __int64 v13; // rbx
  ATL::CStringData *v14; // rbx
  int *v15; // r12
  __int64 v16; // rbx
  void *v17; // rcx
  _QWORD v18[2]; // [rsp+40h] [rbp-10h] BYREF
  __int64 v19; // [rsp+88h] [rbp+38h] BYREF
  __int64 v20; // [rsp+90h] [rbp+40h] BYREF
  __int64 v21; // [rsp+98h] [rbp+48h] BYREF

  PushButtonReset::Logging::Trace(
    0,
    "I\x00n\x00i\x00t\x00i\x00a\x00l\x00i\x00z\x00e\x00 \x00R\x00o\x00l\x00l\x00b\x00a\x00c\x00k\x00H\x00e\x00l\x00p\x00e\x00r\x00 \x00a\x00t\x00 \x00[\x00%\x00s\x00]",
    *a2);
  if ( !(unsigned __int8)PushButtonReset::Directory::Exists(a2) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147943568LL,
      "WinREAgent::RollbackHelper::Initialize",
      "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
      62,
      L"Work directory [%s] doesn't exist",
      *a2);
    return 2147943568LL;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v19);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v20,
    (__int64)L"Rollback");
  v5 = PushButtonReset::Path::Combine(a2, &v20, &v19);
  ATL::CStringData::Release((ATL::CStringData *)(v20 - 24));
  if ( v5 < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v5,
      "WinREAgent::RollbackHelper::Initialize",
      "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
      68,
      L"Failed to combine Rollback directory");
LABEL_35:
    v9 = (ATL::CStringData *)(v19 - 24);
    goto LABEL_36;
  }
  if ( (unsigned __int8)PushButtonReset::Directory::Exists(&v19) )
  {
    PushButtonReset::Logging::Trace(0, L"Deleting existing Rollback directory");
    v7 = PushButtonReset::Directory::Delete(&v19, v6);
    if ( v7 < 0 )
      PushButtonReset::Logging::TraceErr(
        1,
        (unsigned int)v7,
        "WinREAgent::RollbackHelper::Initialize",
        "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
        76,
        L"Failed to delete existing Rollback directory [%s]",
        v19);
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v20,
    (__int64)&pszFormat);
  v5 = PushButtonReset::Directory::Create(&v19, 0, &v20);
  ATL::CStringData::Release((ATL::CStringData *)(v20 - 24));
  if ( v5 >= 0 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v20);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v21);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)v18,
      (__int64)L"Rollback.xml");
    v5 = PushButtonReset::Path::Combine(a2, v18, &v20);
    ATL::CStringData::Release((ATL::CStringData *)(v18[0] - 24LL));
    if ( v5 >= 0 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)v18,
        (__int64)L"RollbackInfo.ini");
      v5 = PushButtonReset::Path::Combine(a2, v18, &v21);
      ATL::CStringData::Release((ATL::CStringData *)(v18[0] - 24LL));
      if ( v5 >= 0 )
      {
        v11 = (ATL::CStringData *)(v20 - 24);
        v12 = (int *)(*a1 - 24LL);
        if ( (int *)(v20 - 24) != v12 )
        {
          if ( v12[4] >= 0 && *(_QWORD *)v11 == *(_QWORD *)v12 )
          {
            v13 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v20 - 24);
            ATL::CStringData::Release((ATL::CStringData *)v12);
            *a1 = v13 + 24;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(a1, v20, *(unsigned int *)(v20 - 16));
          }
        }
        v14 = (ATL::CStringData *)(v21 - 24);
        v18[0] = v21 - 24;
        v15 = (int *)(a1[1] - 24LL);
        if ( (int *)(v21 - 24) != v15 )
        {
          if ( v15[4] >= 0 && *(_QWORD *)v14 == *(_QWORD *)v15 )
          {
            v16 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v21 - 24);
            ATL::CStringData::Release((ATL::CStringData *)v15);
            a1[1] = v16 + 24;
            v14 = (ATL::CStringData *)v18[0];
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(a1 + 1, v21, *(unsigned int *)(v21 - 16));
          }
        }
        v17 = (void *)a1[2];
        if ( v17 )
        {
          free(v17);
          a1[2] = 0;
        }
        a1[3] = 0;
        a1[4] = 0;
        if ( (unsigned __int8)PushButtonReset::File::Exists(a1) )
        {
          PushButtonReset::Logging::Trace(0, L"Delete existing state file");
          v5 = PushButtonReset::File::Delete(a1);
          if ( v5 < 0 )
          {
            PushButtonReset::Logging::TraceErr(
              1,
              (unsigned int)v5,
              "WinREAgent::RollbackHelper::Initialize",
              "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
              104,
              L"Failed to delete existing state file [%s]",
              *a1);
            v5 = 0;
          }
        }
        if ( (unsigned __int8)PushButtonReset::File::Exists(a1) )
        {
          PushButtonReset::Logging::Trace(0, L"Delete existing state file");
          v5 = PushButtonReset::File::Delete(a1);
          if ( v5 < 0 )
          {
            PushButtonReset::Logging::TraceErr(
              1,
              (unsigned int)v5,
              "WinREAgent::RollbackHelper::Initialize",
              "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
              115,
              L"Failed to delete existing state file [%s]",
              *a1);
            v5 = 0;
          }
        }
        ATL::CStringData::Release(v14);
        v10 = v11;
        goto LABEL_34;
      }
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v5,
        "WinREAgent::RollbackHelper::Initialize",
        "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
        92,
        L"Failed to combine ini file [%s]",
        L"RollbackInfo.ini");
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v5,
        "WinREAgent::RollbackHelper::Initialize",
        "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
        89,
        L"Failed to combine state file [%s]",
        L"Rollback.xml");
    }
    ATL::CStringData::Release((ATL::CStringData *)(v21 - 24));
    v10 = (ATL::CStringData *)(v20 - 24);
LABEL_34:
    ATL::CStringData::Release(v10);
    goto LABEL_35;
  }
  v8 = v19;
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)v5,
    "WinREAgent::RollbackHelper::Initialize",
    "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
    82,
    L"Failed to create Rollback directory [%s]",
    v19);
  v9 = (ATL::CStringData *)(v8 - 24);
LABEL_36:
  ATL::CStringData::Release(v9);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800308cc  mov     [rsp-28h+arg_0], rbx
0x1800308d1  push    rbp
0x1800308d2  push    rdi
0x1800308d3  push    r12
0x1800308d5  push    r13
0x1800308d7  push    r15
0x1800308d9  mov     rbp, rsp
0x1800308dc  sub     rsp, 50h
0x1800308e0  mov     rbx, rdx
0x1800308e3  mov     rdi, rcx
0x1800308e6  mov     r8, [rdx]
0x1800308e9  lea     rdx, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+40h; "I\x00n\x00i\x00t\x00i\x00a\x00l\x00i"...
0x1800308f0  xor     ecx, ecx
0x1800308f2  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800308f7  mov     rcx, rbx
0x1800308fa  call    ?Exists@Directory@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Directory::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800308ff  test    al, al
0x180030901  jnz     short loc_180030946
0x180030903  mov     rax, [rbx]
0x180030906  mov     [rsp+50h+var_20], rax
0x18003090b  lea     rax, aWorkDirectoryS; "Work directory [%s] doesn't exist"
0x180030912  mov     [rsp+50h+var_28], rax
0x180030917  mov     [rsp+50h+var_30], 3Eh ; '>'
0x18003091f  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180030926  lea     r8, aWinreagentRoll_0; "WinREAgent::RollbackHelper::Initialize"
0x18003092d  mov     edx, 80070490h
0x180030932  mov     ecx, 2
0x180030937  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18003093c  mov     eax, 80070490h
0x180030941  jmp     loc_180030D30
0x180030946  lea     rcx, [rbp+arg_8]
0x18003094a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18003094f  nop
0x180030950  lea     rdx, aRollback; "Rollback"
0x180030957  lea     rcx, [rbp+arg_10]
0x18003095b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180030960  nop
0x180030961  lea     r8, [rbp+arg_8]
0x180030965  lea     rdx, [rbp+arg_10]
0x180030969  mov     rcx, rbx
0x18003096c  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180030971  mov     r15d, eax
0x180030974  mov     rcx, [rbp+arg_10]
0x180030978  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003097c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030981  test    r15d, r15d
0x180030984  jns     short loc_1800309BA
0x180030986  lea     rax, aFailedToCombin_1; "Failed to combine Rollback directory"
0x18003098d  mov     [rsp+50h+var_28], rax
0x180030992  mov     [rsp+50h+var_30], 44h ; 'D'
0x18003099a  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800309a1  lea     r8, aWinreagentRoll_0; "WinREAgent::RollbackHelper::Initialize"
0x1800309a8  mov     edx, r15d
0x1800309ab  mov     ecx, 2
0x1800309b0  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800309b5  jmp     loc_180030D20
0x1800309ba  lea     rcx, [rbp+arg_8]
0x1800309be  call    ?Exists@Directory@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Directory::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800309c3  test    al, al
0x1800309c5  jz      short loc_180030A19
0x1800309c7  lea     rdx, aDeletingExisti; "Deleting existing Rollback directory"
0x1800309ce  xor     ecx, ecx
0x1800309d0  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800309d5  lea     rcx, [rbp+arg_8]
0x1800309d9  call    ?Delete@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUProgressCallback@2@@Z; PushButtonReset::Directory::Delete(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::ProgressCallback *)
0x1800309de  test    eax, eax
0x1800309e0  jns     short loc_180030A19
0x1800309e2  mov     rcx, [rbp+arg_8]
0x1800309e6  mov     [rsp+50h+var_20], rcx
0x1800309eb  lea     rcx, aFailedToDelete_13; "Failed to delete existing Rollback dire"...
0x1800309f2  mov     [rsp+50h+var_28], rcx
0x1800309f7  mov     [rsp+50h+var_30], 4Ch ; 'L'
0x1800309ff  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180030a06  lea     r8, aWinreagentRoll_0; "WinREAgent::RollbackHelper::Initialize"
0x180030a0d  mov     edx, eax
0x180030a0f  mov     ecx, 1
0x180030a14  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180030a19  lea     rdx, pszFormat
0x180030a20  lea     rcx, [rbp+arg_10]
0x180030a24  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180030a29  nop
0x180030a2a  lea     r8, [rbp+arg_10]
0x180030a2e  xor     edx, edx
0x180030a30  lea     rcx, [rbp+arg_8]
0x180030a34  call    ?Create@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N0@Z; PushButtonReset::Directory::Create(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180030a39  mov     r15d, eax
0x180030a3c  mov     rcx, [rbp+arg_10]
0x180030a40  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030a44  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030a49  test    r15d, r15d
0x180030a4c  jns     short loc_180030A90
0x180030a4e  mov     rbx, [rbp+arg_8]
0x180030a52  mov     [rsp+50h+var_20], rbx
0x180030a57  lea     rax, aFailedToCreate_30; "Failed to create Rollback directory [%s"...
0x180030a5e  mov     [rsp+50h+var_28], rax
0x180030a63  mov     [rsp+50h+var_30], 52h ; 'R'
0x180030a6b  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180030a72  lea     r8, aWinreagentRoll_0; "WinREAgent::RollbackHelper::Initialize"
0x180030a79  mov     edx, r15d
0x180030a7c  mov     ecx, 2
0x180030a81  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180030a86  nop
0x180030a87  lea     rcx, [rbx-18h]
0x180030a8b  jmp     loc_180030D28
0x180030a90  lea     rcx, [rbp+arg_10]
0x180030a94  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180030a99  nop
0x180030a9a  lea     rcx, [rbp+arg_18]
0x180030a9e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180030aa3  nop
0x180030aa4  lea     r12, aRollbackXml; "Rollback.xml"
0x180030aab  mov     rdx, r12
0x180030aae  lea     rcx, [rbp+var_10]
0x180030ab2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180030ab7  nop
0x180030ab8  lea     r8, [rbp+arg_10]
0x180030abc  lea     rdx, [rbp+var_10]
0x180030ac0  mov     rcx, rbx
0x180030ac3  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180030ac8  mov     r15d, eax
0x180030acb  mov     rcx, [rbp+var_10]
0x180030acf  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030ad3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030ad8  test    r15d, r15d
0x180030adb  jns     short loc_180030B2D
0x180030add  mov     [rsp+50h+var_20], r12
0x180030ae2  lea     rax, aFailedToCombin_3; "Failed to combine state file [%s]"
0x180030ae9  mov     [rsp+50h+var_28], rax
0x180030aee  mov     [rsp+50h+var_30], 59h ; 'Y'
0x180030af6  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180030afd  lea     r8, aWinreagentRoll_0; "WinREAgent::RollbackHelper::Initialize"
0x180030b04  mov     edx, r15d
0x180030b07  mov     ecx, 2
0x180030b0c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180030b11  nop
0x180030b12  mov     rcx, [rbp+arg_18]
0x180030b16  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030b1a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030b1f  nop
0x180030b20  mov     rcx, [rbp+arg_10]
0x180030b24  add     rcx, 0FFFFFFFFFFFFFFE8h
0x180030b28  jmp     loc_180030D1A
0x180030b2d  lea     r12, aRollbackinfoIn; "RollbackInfo.ini"
0x180030b34  mov     rdx, r12
0x180030b37  lea     rcx, [rbp+var_10]
0x180030b3b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180030b40  nop
0x180030b41  lea     r8, [rbp+arg_18]
0x180030b45  lea     rdx, [rbp+var_10]
0x180030b49  mov     rcx, rbx
0x180030b4c  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180030b51  mov     r15d, eax
0x180030b54  mov     rcx, [rbp+var_10]
0x180030b58  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030b5c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030b61  test    r15d, r15d
0x180030b64  jns     short loc_180030B84
0x180030b66  mov     [rsp+50h+var_20], r12
0x180030b6b  lea     rax, aFailedToCombin_2; "Failed to combine ini file [%s]"
0x180030b72  mov     [rsp+50h+var_28], rax
0x180030b77  mov     [rsp+50h+var_30], 5Ch ; '\'
0x180030b7f  jmp     loc_180030AF6
0x180030b84  mov     rdx, [rbp+arg_10]
0x180030b88  lea     r13, [rdx-18h]
0x180030b8c  mov     r12, [rdi]
0x180030b8f  add     r12, 0FFFFFFFFFFFFFFE8h
0x180030b93  cmp     r13, r12
0x180030b96  jz      short loc_180030BD2
0x180030b98  cmp     dword ptr [r12+10h], 0
0x180030b9e  jl      short loc_180030BC6
0x180030ba0  mov     rax, [r12]
0x180030ba4  cmp     [r13+0], rax
0x180030ba8  jnz     short loc_180030BC6
0x180030baa  mov     rcx, r13
0x180030bad  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180030bb2  mov     rbx, rax
0x180030bb5  mov     rcx, r12; this
0x180030bb8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030bbd  lea     rax, [rbx+18h]
0x180030bc1  mov     [rdi], rax
0x180030bc4  jmp     short loc_180030BD2
0x180030bc6  mov     r8d, [rdx-10h]
0x180030bca  mov     rcx, rdi
0x180030bcd  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180030bd2  lea     rcx, [rdi+8]
0x180030bd6  mov     rdx, [rbp+arg_18]
0x180030bda  lea     rbx, [rdx-18h]
0x180030bde  mov     [rbp+var_10], rbx
0x180030be2  mov     r12, [rcx]
0x180030be5  add     r12, 0FFFFFFFFFFFFFFE8h
0x180030be9  cmp     rbx, r12
0x180030bec  jz      short loc_180030C2A
0x180030bee  cmp     dword ptr [r12+10h], 0
0x180030bf4  jl      short loc_180030C20
0x180030bf6  mov     rax, [r12]
0x180030bfa  cmp     [rbx], rax
0x180030bfd  jnz     short loc_180030C20
0x180030bff  mov     rcx, rbx
0x180030c02  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180030c07  mov     rbx, rax
0x180030c0a  mov     rcx, r12; this
0x180030c0d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030c12  lea     rax, [rbx+18h]
0x180030c16  mov     [rdi+8], rax
0x180030c1a  mov     rbx, [rbp+var_10]
0x180030c1e  jmp     short loc_180030C2A
0x180030c20  mov     r8d, [rdx-10h]
0x180030c24  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180030c29  nop
0x180030c2a  mov     rcx, [rdi+10h]; Block
0x180030c2e  xor     r12d, r12d
0x180030c31  test    rcx, rcx
0x180030c34  jz      short loc_180030C40
0x180030c36  call    cs:__imp_free
0x180030c3c  mov     [rdi+10h], r12
0x180030c40  mov     [rdi+18h], r12
0x180030c44  mov     [rdi+20h], r12
0x180030c48  mov     rcx, rdi
0x180030c4b  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180030c50  test    al, al
0x180030c52  jz      short loc_180030CAB
0x180030c54  lea     rdx, aDeleteExisting; "Delete existing state file"
0x180030c5b  xor     ecx, ecx
0x180030c5d  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180030c62  mov     rcx, rdi
0x180030c65  call    ?Delete@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; PushButtonReset::File::Delete(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,int)
0x180030c6a  mov     r15d, eax
0x180030c6d  test    eax, eax
0x180030c6f  jns     short loc_180030CAB
0x180030c71  mov     rax, [rdi]
0x180030c74  mov     [rsp+50h+var_20], rax
0x180030c79  lea     rax, aFailedToDelete_1; "Failed to delete existing state file [%"...
0x180030c80  mov     [rsp+50h+var_28], rax
0x180030c85  mov     [rsp+50h+var_30], 68h ; 'h'
0x180030c8d  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180030c94  lea     r8, aWinreagentRoll_0; "WinREAgent::RollbackHelper::Initialize"
0x180030c9b  mov     edx, r15d
0x180030c9e  mov     ecx, 1
0x180030ca3  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180030ca8  mov     r15d, r12d
0x180030cab  mov     rcx, rdi
0x180030cae  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180030cb3  test    al, al
0x180030cb5  jz      short loc_180030D0E
0x180030cb7  lea     rdx, aDeleteExisting; "Delete existing state file"
0x180030cbe  xor     ecx, ecx
0x180030cc0  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180030cc5  mov     rcx, rdi
0x180030cc8  call    ?Delete@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; PushButtonReset::File::Delete(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,int)
0x180030ccd  mov     r15d, eax
0x180030cd0  test    eax, eax
0x180030cd2  jns     short loc_180030D0E
0x180030cd4  mov     rax, [rdi]
0x180030cd7  mov     [rsp+50h+var_20], rax
0x180030cdc  lea     rax, aFailedToDelete_1; "Failed to delete existing state file [%"...
0x180030ce3  mov     [rsp+50h+var_28], rax
0x180030ce8  mov     [rsp+50h+var_30], 73h ; 's'
0x180030cf0  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180030cf7  lea     r8, aWinreagentRoll_0; "WinREAgent::RollbackHelper::Initialize"
0x180030cfe  mov     edx, r15d
0x180030d01  mov     ecx, 1
0x180030d06  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180030d0b  mov     r15d, r12d
0x180030d0e  mov     rcx, rbx; this
0x180030d11  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030d16  nop
0x180030d17  mov     rcx, r13; this
0x180030d1a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030d1f  nop
0x180030d20  mov     rcx, [rbp+arg_8]
0x180030d24  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030d28  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030d2d  mov     eax, r15d
0x180030d30  mov     rbx, [rsp+50h+arg_0]
0x180030d38  add     rsp, 50h
0x180030d3c  pop     r15
0x180030d3e  pop     r13
0x180030d40  pop     r12
0x180030d42  pop     rdi
0x180030d43  pop     rbp
0x180030d44  retn
```
