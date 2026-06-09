# WinREAgent::SetupCreatedWinRE::InternalExecute(WinREAgent::ExecutionContext const *,PushButtonReset::ProgressCallback *)

- ea: `0x18002b5e0`
- end: `0x18002b9fb`
- name: `?InternalExecute@SetupCreatedWinRE@WinREAgent@@MEAAJPEBVExecutionContext@2@PEAUProgressCallback@PushButtonReset@@@Z`
- size: `1051`
- prototype: `__int64 __fastcall(WinREAgent::SetupCreatedWinRE *__hidden this, const struct WinREAgent::ExecutionContext *, struct PushButtonReset::ProgressCallback *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x1800074b8`
- `0x18000d92c`
- `0x180011ef4`
- `0x18002b460`
- `0x18002b5e0`
- `0x18002e06c`
- `0x180032480`
- `0x180035cd0`
- `0x18003717c`
- `0x180037344`
- `0x18004d2ac`

## string_xrefs

- `0x18002b6e6`: `BackupWimPath`
- `0x18002b8a3`: `BackupWimPath`
- `0x18002b646`: `base\diagnosis\srt\winreagent\lib\operations\src\setupcreatedwinre.cpp`
- `0x18002b677`: `base\diagnosis\srt\winreagent\lib\operations\src\setupcreatedwinre.cpp`
- `0x18002b632`: `Old WinRE path does not exist`
- `0x18002b64d`: `WinREAgent::SetupCreatedWinRE::InternalExecute`
- `0x18002b67e`: `WinREAgent::SetupCreatedWinRE::InternalExecute`
- `0x18002b6c0`: `SetupCreatedWinRE: Save new WimRE Hash to Rollback info`
- `0x18002b72c`: `Failed to save new WinRE hash into rollback info`
- `0x18002b851`: `SetupCreatedWinRE: Old WinRE is [%s]`
- `0x18002b87d`: `SetupCreatedWinRE: Save old WinRE hash to Rollback info`
- `0x18002b8e9`: `Failed to save old WinRE hash into rollback info`
- `0x18002b96a`: `SetupCreatedWinRE: Will trust the new WinRE hash`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WinREAgent::SetupCreatedWinRE::InternalExecute(
        WinREAgent::SetupCreatedWinRE *this,
        const struct WinREAgent::ExecutionContext *a2,
        struct PushButtonReset::ProgressCallback *a3)
{
  signed int v5; // esi
  int v6; // eax
  char v7; // r12
  __int64 v8; // rbx
  __int64 v9; // rbx
  WinREAgent::TelemetrySession *v10; // rcx
  unsigned int v11; // ebx
  char v12; // al
  const wchar_t *v13; // r8
  __int64 v14; // rdi
  ATL::CStringData *v15; // rcx
  _QWORD *v16; // rcx
  int *v17; // r14
  __int64 v18; // rdi
  ATL::CStringData *v19; // r14
  int *v20; // r15
  __int64 v21; // rdi
  __int64 v23; // [rsp+30h] [rbp-30h] BYREF
  __int64 v24; // [rsp+38h] [rbp-28h] BYREF
  __int64 v25; // [rsp+40h] [rbp-20h] BYREF
  __int64 v26; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v27[2]; // [rsp+50h] [rbp-10h] BYREF
  __int64 v28; // [rsp+A8h] [rbp+48h] BYREF
  __int64 v29; // [rsp+B8h] [rbp+58h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v25);
  LOBYTE(v23) = 0;
  LOBYTE(v29) = 0;
  LOBYTE(v28) = 0;
  if ( !(unsigned __int8)PushButtonReset::File::Exists((char *)a2 + 280) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942402LL,
      "WinREAgent::SetupCreatedWinRE::InternalExecute",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\setupcreatedwinre.cpp",
      87,
      L"Old WinRE path does not exist",
      v23);
    v5 = -2147024894;
LABEL_8:
    v9 = v24;
LABEL_22:
    v15 = (ATL::CStringData *)(v25 - 24);
    goto LABEL_34;
  }
  v6 = GenerateEncodedHash_0((char *)a2 + 280, &v25);
  v7 = 1;
  if ( v6 < 0 )
    PushButtonReset::Logging::TraceErr(
      1,
      (unsigned int)v6,
      "WinREAgent::SetupCreatedWinRE::InternalExecute",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\setupcreatedwinre.cpp",
      93,
      L"Failed to generate hash for new wim",
      v23);
  if ( *((_QWORD *)a2 + 56) )
  {
    PushButtonReset::Logging::Trace(0, L"SetupCreatedWinRE: Save new WimRE Hash to Rollback info");
    v8 = *((_QWORD *)a2 + 56);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)v27,
      (__int64)L"NewWinREHash");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v26,
      (__int64)L"BackupWimPath");
    v5 = WinREAgent::RollbackHelper::WriteToConfig(v8, &v26, v27, &v25);
    ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v27[0] - 24LL));
    if ( v5 < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v5,
        "WinREAgent::SetupCreatedWinRE::InternalExecute",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\setupcreatedwinre.cpp",
        104,
        L"Failed to save new WinRE hash into rollback info");
      goto LABEL_8;
    }
  }
  v5 = WinREAgent::QueryWinREHashStatus(
         (_QWORD *)a2 + 11,
         (__int64 *)a2 + 15,
         (bool *)&v23,
         (bool *)&v29,
         (bool *)&v28,
         &v24);
  v10 = (WinREAgent::TelemetrySession *)*((_QWORD *)this + 14);
  v11 = (unsigned __int8)v29;
  v12 = v28;
  if ( v10 )
  {
    WinREAgent::TelemetrySession::TraceDataPoint(v10, L"ServicingInfoGroup", L"BitLockerActive", (unsigned __int8)v23);
    WinREAgent::TelemetrySession::TraceDataPoint(
      *((WinREAgent::TelemetrySession **)this + 14),
      L"ServicingInfoGroup",
      L"OldWinREIsTrusted",
      v11);
    WinREAgent::TelemetrySession::TraceDataPoint(
      *((WinREAgent::TelemetrySession **)this + 14),
      L"ServicingInfoGroup",
      L"OldWinREIsValidated",
      (unsigned __int8)v28);
    WinREAgent::TelemetrySession::TraceDataPoint(
      *((WinREAgent::TelemetrySession **)this + 14),
      L"ServicingInfoGroup",
      L"QueryWinREHashResult",
      v5);
    v12 = v28;
  }
  if ( v5 < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      1,
      (unsigned int)v5,
      "WinREAgent::SetupCreatedWinRE::InternalExecute",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\setupcreatedwinre.cpp",
      145,
      L"Failed to query WinRE hash status");
    LOBYTE(v11) = 0;
    v12 = 0;
    v5 = 0;
  }
  if ( !(_BYTE)v11 && !v12 )
    v7 = 0;
  *((_BYTE *)this + 120) = v7;
  v13 = L"trusted";
  if ( !v7 )
    v13 = L"not trusted";
  PushButtonReset::Logging::Trace(0, L"SetupCreatedWinRE: Old WinRE is [%s]", v13);
  v9 = v24;
  if ( *((_BYTE *)this + 120) )
  {
    if ( *((_QWORD *)a2 + 56) )
    {
      PushButtonReset::Logging::Trace(0, L"SetupCreatedWinRE: Save old WinRE hash to Rollback info");
      v14 = *((_QWORD *)a2 + 56);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v29,
        (__int64)L"OldWinREHash");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v28,
        (__int64)L"BackupWimPath");
      v5 = WinREAgent::RollbackHelper::WriteToConfig(v14, &v28, &v29, &v24);
      ATL::CStringData::Release((ATL::CStringData *)(v28 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
      if ( v5 < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v5,
          "WinREAgent::SetupCreatedWinRE::InternalExecute",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\setupcreatedwinre.cpp",
          162,
          L"Failed to save old WinRE hash into rollback info");
        goto LABEL_22;
      }
    }
    v16 = (_QWORD *)(v9 - 24);
    v17 = (int *)(*((_QWORD *)this + 16) - 24LL);
    if ( (int *)(v9 - 24) != v17 )
    {
      if ( v17[4] >= 0 && *v16 == *(_QWORD *)v17 )
      {
        v18 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v16);
        ATL::CStringData::Release((ATL::CStringData *)v17);
        *((_QWORD *)this + 16) = v18 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 128, v9, *(unsigned int *)(v9 - 16));
      }
    }
  }
  PushButtonReset::Logging::Trace(0, L"SetupCreatedWinRE: Will trust the new WinRE hash");
  v19 = (ATL::CStringData *)(v25 - 24);
  v20 = (int *)(*((_QWORD *)this + 17) - 24LL);
  if ( (int *)(v25 - 24) != v20 )
  {
    if ( v20[4] >= 0 && *(_QWORD *)v19 == *(_QWORD *)v20 )
    {
      v21 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v25 - 24);
      ATL::CStringData::Release((ATL::CStringData *)v20);
      *((_QWORD *)this + 17) = v21 + 24;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 136, v25, *(unsigned int *)(v25 - 16));
    }
  }
  v15 = v19;
LABEL_34:
  ATL::CStringData::Release(v15);
  ATL::CStringData::Release((ATL::CStringData *)(v9 - 24));
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002b5e0  mov     [rsp-38h+arg_0], rbx
0x18002b5e5  push    rbp
0x18002b5e6  push    rsi
0x18002b5e7  push    rdi
0x18002b5e8  push    r12
0x18002b5ea  push    r13
0x18002b5ec  push    r14
0x18002b5ee  push    r15
0x18002b5f0  mov     rbp, rsp
0x18002b5f3  sub     rsp, 60h
0x18002b5f7  mov     rdi, rdx
0x18002b5fa  mov     r13, rcx
0x18002b5fd  lea     rcx, [rbp+var_28]
0x18002b601  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002b606  nop
0x18002b607  lea     rcx, [rbp+var_20]
0x18002b60b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002b610  nop
0x18002b611  xor     esi, esi
0x18002b613  mov     byte ptr [rbp+var_30], sil
0x18002b617  mov     byte ptr [rbp+arg_18], sil
0x18002b61b  mov     byte ptr [rbp+arg_8], sil
0x18002b61f  lea     rbx, [rdi+118h]
0x18002b626  mov     rcx, rbx
0x18002b629  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002b62e  test    al, al
0x18002b630  jnz     short loc_18002B66B
0x18002b632  lea     rax, aOldWinrePathDo; "Old WinRE path does not exist"
0x18002b639  mov     [rsp+60h+var_38], rax
0x18002b63e  mov     dword ptr [rsp+60h+var_40], 57h ; 'W'
0x18002b646  lea     r9, aBaseDiagnosisS_23; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002b64d  lea     r8, aWinreagentSetu; "WinREAgent::SetupCreatedWinRE::Internal"...
0x18002b654  mov     edx, 80070002h
0x18002b659  lea     ecx, [rsi+2]
0x18002b65c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002b661  mov     esi, 80070002h
0x18002b666  jmp     loc_18002B752
0x18002b66b  lea     rdx, [rbp+var_20]
0x18002b66f  mov     rcx, rbx
0x18002b672  call    GenerateEncodedHash_0
0x18002b677  lea     r14, aBaseDiagnosisS_23; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002b67e  lea     r15, aWinreagentSetu; "WinREAgent::SetupCreatedWinRE::Internal"...
0x18002b685  mov     r12d, 1
0x18002b68b  test    eax, eax
0x18002b68d  jns     short loc_18002B6B3
0x18002b68f  lea     rcx, aFailedToGenera_2; "Failed to generate hash for new wim"
0x18002b696  mov     [rsp+60h+var_38], rcx
0x18002b69b  mov     dword ptr [rsp+60h+var_40], 5Dh ; ']'
0x18002b6a3  mov     r9, r14
0x18002b6a6  mov     r8, r15
0x18002b6a9  mov     edx, eax
0x18002b6ab  mov     ecx, r12d
0x18002b6ae  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002b6b3  cmp     [rdi+1C0h], rsi
0x18002b6ba  jz      loc_18002B75B
0x18002b6c0  lea     rdx, aSetupcreatedwi; "SetupCreatedWinRE: Save new WimRE Hash "...
0x18002b6c7  xor     ecx, ecx
0x18002b6c9  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002b6ce  mov     rbx, [rdi+1C0h]
0x18002b6d5  lea     rdx, aNewwinrehash; "NewWinREHash"
0x18002b6dc  lea     rcx, [rbp+var_10]
0x18002b6e0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002b6e5  nop
0x18002b6e6  lea     rdx, aBackupwimpath; "BackupWimPath"
0x18002b6ed  lea     rcx, [rbp+var_18]
0x18002b6f1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002b6f6  nop
0x18002b6f7  lea     r9, [rbp+var_20]
0x18002b6fb  lea     r8, [rbp+var_10]
0x18002b6ff  lea     rdx, [rbp+var_18]
0x18002b703  mov     rcx, rbx
0x18002b706  call    ?WriteToConfig@RollbackHelper@WinREAgent@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00@Z; WinREAgent::RollbackHelper::WriteToConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002b70b  mov     esi, eax
0x18002b70d  mov     rcx, [rbp+var_18]
0x18002b711  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002b715  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002b71a  nop
0x18002b71b  mov     rcx, [rbp+var_10]
0x18002b71f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002b723  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002b728  test    esi, esi
0x18002b72a  jns     short loc_18002B75B
0x18002b72c  lea     rax, aFailedToSaveNe_0; "Failed to save new WinRE hash into roll"...
0x18002b733  mov     [rsp+60h+var_38], rax
0x18002b738  mov     dword ptr [rsp+60h+var_40], 68h ; 'h'
0x18002b740  mov     r9, r14
0x18002b743  mov     r8, r15
0x18002b746  mov     edx, esi
0x18002b748  mov     ecx, 2
0x18002b74d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002b752  mov     rbx, [rbp+var_28]
0x18002b756  jmp     loc_18002B910
0x18002b75b  lea     rdx, [rdi+78h]
0x18002b75f  lea     rcx, [rdi+58h]
0x18002b763  lea     rax, [rbp+var_28]
0x18002b767  mov     [rsp+60h+var_38], rax
0x18002b76c  lea     rax, [rbp+arg_8]
0x18002b770  mov     [rsp+60h+var_40], rax
0x18002b775  lea     r9, [rbp+arg_18]
0x18002b779  lea     r8, [rbp+var_30]
0x18002b77d  call    ?QueryWinREHashStatus@WinREAgent@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0AEA_N11PEAV23@@Z; WinREAgent::QueryWinREHashStatus(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool &,bool &,bool &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18002b782  mov     esi, eax
0x18002b784  mov     rcx, [r13+70h]; this
0x18002b788  movzx   ebx, byte ptr [rbp+arg_18]
0x18002b78c  mov     al, byte ptr [rbp+arg_8]
0x18002b78f  test    rcx, rcx
0x18002b792  jz      short loc_18002B7FF
0x18002b794  movzx   r9d, byte ptr [rbp+var_30]; unsigned int
0x18002b799  lea     r8, aBitlockeractiv; "BitLockerActive"
0x18002b7a0  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x18002b7a7  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ulong)
0x18002b7ac  mov     r9d, ebx; unsigned int
0x18002b7af  lea     r8, aOldwinreistrus; "OldWinREIsTrusted"
0x18002b7b6  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x18002b7bd  mov     rcx, [r13+70h]; this
0x18002b7c1  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ulong)
0x18002b7c6  movzx   r9d, byte ptr [rbp+arg_8]; unsigned int
0x18002b7cb  lea     r8, aOldwinreisvali; "OldWinREIsValidated"
0x18002b7d2  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x18002b7d9  mov     rcx, [r13+70h]; this
0x18002b7dd  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ulong)
0x18002b7e2  mov     r9d, esi; unsigned int
0x18002b7e5  lea     r8, aQuerywinrehash; "QueryWinREHashResult"
0x18002b7ec  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x18002b7f3  mov     rcx, [r13+70h]; this
0x18002b7f7  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ulong)
0x18002b7fc  mov     al, byte ptr [rbp+arg_8]
0x18002b7ff  test    esi, esi
0x18002b801  jns     short loc_18002B82D
0x18002b803  lea     rax, aFailedToQueryW; "Failed to query WinRE hash status"
0x18002b80a  mov     [rsp+60h+var_38], rax
0x18002b80f  mov     dword ptr [rsp+60h+var_40], 91h
0x18002b817  mov     r9, r14
0x18002b81a  mov     r8, r15
0x18002b81d  mov     edx, esi
0x18002b81f  mov     ecx, r12d
0x18002b822  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002b827  xor     bl, bl
0x18002b829  xor     al, al
0x18002b82b  xor     esi, esi
0x18002b82d  test    bl, bl
0x18002b82f  jnz     short loc_18002B838
0x18002b831  test    al, al
0x18002b833  jnz     short loc_18002B838
0x18002b835  xor     r12b, r12b
0x18002b838  mov     [r13+78h], r12b
0x18002b83c  lea     rax, aNotTrusted; "not trusted"
0x18002b843  lea     r8, aTrusted; "trusted"
0x18002b84a  test    r12b, r12b
0x18002b84d  cmovz   r8, rax
0x18002b851  lea     rdx, aSetupcreatedwi_2; "SetupCreatedWinRE: Old WinRE is [%s]"
0x18002b858  xor     ecx, ecx
0x18002b85a  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002b85f  mov     rbx, [rbp+var_28]
0x18002b863  xor     r12d, r12d
0x18002b866  cmp     [r13+78h], r12b
0x18002b86a  jz      loc_18002B96A
0x18002b870  cmp     [rdi+1C0h], r12
0x18002b877  jz      loc_18002B91D
0x18002b87d  lea     rdx, aSetupcreatedwi_1; "SetupCreatedWinRE: Save old WinRE hash "...
0x18002b884  xor     ecx, ecx
0x18002b886  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002b88b  mov     rdi, [rdi+1C0h]
0x18002b892  lea     rdx, aOldwinrehash; "OldWinREHash"
0x18002b899  lea     rcx, [rbp+arg_18]
0x18002b89d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002b8a2  nop
0x18002b8a3  lea     rdx, aBackupwimpath; "BackupWimPath"
0x18002b8aa  lea     rcx, [rbp+arg_8]
0x18002b8ae  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002b8b3  nop
0x18002b8b4  lea     r9, [rbp+var_28]
0x18002b8b8  lea     r8, [rbp+arg_18]
0x18002b8bc  lea     rdx, [rbp+arg_8]
0x18002b8c0  mov     rcx, rdi
0x18002b8c3  call    ?WriteToConfig@RollbackHelper@WinREAgent@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00@Z; WinREAgent::RollbackHelper::WriteToConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002b8c8  mov     esi, eax
0x18002b8ca  mov     rcx, [rbp+arg_8]
0x18002b8ce  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002b8d2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002b8d7  nop
0x18002b8d8  mov     rcx, [rbp+arg_18]
0x18002b8dc  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002b8e0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002b8e5  test    esi, esi
0x18002b8e7  jns     short loc_18002B91D
0x18002b8e9  lea     rax, aFailedToSaveOl_0; "Failed to save old WinRE hash into roll"...
0x18002b8f0  mov     [rsp+60h+var_38], rax
0x18002b8f5  mov     dword ptr [rsp+60h+var_40], 0A2h
0x18002b8fd  mov     r9, r14
0x18002b900  mov     r8, r15
0x18002b903  mov     edx, esi
0x18002b905  lea     ecx, [r12+2]
0x18002b90a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002b90f  nop
0x18002b910  mov     rcx, [rbp+var_20]
0x18002b914  add     rcx, 0FFFFFFFFFFFFFFE8h
0x18002b918  jmp     loc_18002B9D2
0x18002b91d  lea     r15, [r13+80h]
0x18002b924  lea     rcx, [rbx-18h]
0x18002b928  mov     r14, [r15]
0x18002b92b  add     r14, 0FFFFFFFFFFFFFFE8h
0x18002b92f  cmp     rcx, r14
0x18002b932  jz      short loc_18002B96A
0x18002b934  cmp     [r14+10h], r12d
0x18002b938  jl      short loc_18002B95B
0x18002b93a  mov     rax, [r14]
0x18002b93d  cmp     [rcx], rax
0x18002b940  jnz     short loc_18002B95B
0x18002b942  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18002b947  mov     rdi, rax
0x18002b94a  mov     rcx, r14; this
0x18002b94d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002b952  lea     rax, [rdi+18h]
0x18002b956  mov     [r15], rax
0x18002b959  jmp     short loc_18002B96A
0x18002b95b  mov     r8d, [rbx-10h]
0x18002b95f  mov     rdx, rbx
0x18002b962  mov     rcx, r15
0x18002b965  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002b96a  lea     rdx, aSetupcreatedwi_0; "SetupCreatedWinRE: Will trust the new W"...
0x18002b971  xor     ecx, ecx
0x18002b973  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002b978  mov     rdx, [rbp+var_20]
0x18002b97c  lea     r14, [rdx-18h]
0x18002b980  mov     r15, [r13+88h]
0x18002b987  add     r15, 0FFFFFFFFFFFFFFE8h
0x18002b98b  cmp     r14, r15
0x18002b98e  jz      short loc_18002B9CF
0x18002b990  cmp     [r15+10h], r12d
0x18002b994  jl      short loc_18002B9BE
0x18002b996  mov     rax, [r15]
0x18002b999  cmp     [r14], rax
0x18002b99c  jnz     short loc_18002B9BE
0x18002b99e  mov     rcx, r14
0x18002b9a1  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18002b9a6  mov     rdi, rax
0x18002b9a9  mov     rcx, r15; this
0x18002b9ac  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002b9b1  lea     rax, [rdi+18h]
0x18002b9b5  mov     [r13+88h], rax
0x18002b9bc  jmp     short loc_18002B9CF
0x18002b9be  mov     r8d, [rdx-10h]
0x18002b9c2  lea     rcx, [r13+88h]
0x18002b9c9  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002b9ce  nop
0x18002b9cf  mov     rcx, r14; this
0x18002b9d2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002b9d7  nop
0x18002b9d8  lea     rcx, [rbx-18h]; this
0x18002b9dc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002b9e1  mov     eax, esi
0x18002b9e3  mov     rbx, [rsp+60h+arg_0]
0x18002b9eb  add     rsp, 60h
0x18002b9ef  pop     r15
0x18002b9f1  pop     r14
0x18002b9f3  pop     r13
0x18002b9f5  pop     r12
0x18002b9f7  pop     rdi
0x18002b9f8  pop     rsi
0x18002b9f9  pop     rbp
0x18002b9fa  retn
```
