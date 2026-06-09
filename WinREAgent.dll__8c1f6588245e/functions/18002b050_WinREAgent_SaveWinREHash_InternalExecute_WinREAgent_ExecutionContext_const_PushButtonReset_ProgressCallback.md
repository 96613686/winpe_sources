# WinREAgent::SaveWinREHash::InternalExecute(WinREAgent::ExecutionContext const *,PushButtonReset::ProgressCallback *)

- ea: `0x18002b050`
- end: `0x18002b404`
- name: `?InternalExecute@SaveWinREHash@WinREAgent@@MEAAJPEBVExecutionContext@2@PEAUProgressCallback@PushButtonReset@@@Z`
- size: `948`
- prototype: `__int64 __fastcall(WinREAgent::SaveWinREHash *__hidden this, const struct WinREAgent::ExecutionContext *, struct PushButtonReset::ProgressCallback *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x1800074b8`
- `0x18000d92c`
- `0x180011ef4`
- `0x18002ade8`
- `0x18002b050`
- `0x18002e06c`
- `0x180032480`
- `0x180035cd0`
- `0x18003717c`
- `0x180037344`

## string_xrefs

- `0x18002b107`: `BackupWimPath`
- `0x18002b29d`: `BackupWimPath`
- `0x18002b0bc`: `base\diagnosis\srt\winreagent\lib\operations\src\savewinrehash.cpp`
- `0x18002b21d`: `base\diagnosis\srt\winreagent\lib\operations\src\savewinrehash.cpp`
- `0x18002b2f7`: `base\diagnosis\srt\winreagent\lib\operations\src\savewinrehash.cpp`
- `0x18002b0c3`: `WinREAgent::SaveWinREHash::InternalExecute`
- `0x18002b224`: `WinREAgent::SaveWinREHash::InternalExecute`
- `0x18002b2fe`: `WinREAgent::SaveWinREHash::InternalExecute`
- `0x18002b0e1`: `SaveWinREHash: Save new WimRE Hash to Rollback info`
- `0x18002b277`: `SaveWinREHash: Save old WinRE hash to Rollback info`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WinREAgent::SaveWinREHash::InternalExecute(
        WinREAgent::SaveWinREHash *this,
        const struct WinREAgent::ExecutionContext *a2,
        struct PushButtonReset::ProgressCallback *a3)
{
  int v5; // eax
  char v6; // r14
  __int64 v7; // rbx
  signed int v8; // edi
  WinREAgent::TelemetrySession *v9; // rcx
  unsigned int v10; // ebx
  unsigned int v11; // r15d
  __int64 v12; // rbx
  ATL::CStringData *v13; // rcx
  ATL::CStringData *v14; // r15
  int *v15; // rsi
  __int64 v16; // rbx
  ATL::CStringData *v17; // rsi
  int *v18; // r14
  __int64 v19; // rbx
  bool v21; // [rsp+30h] [rbp-30h] BYREF
  __int64 v22; // [rsp+38h] [rbp-28h] BYREF
  __int64 v23; // [rsp+40h] [rbp-20h] BYREF
  __int64 v24; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v25[2]; // [rsp+50h] [rbp-10h] BYREF
  __int64 v26; // [rsp+A8h] [rbp+48h] BYREF
  __int64 v27; // [rsp+B8h] [rbp+58h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v22);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v23);
  v21 = 0;
  LOBYTE(v26) = 0;
  LOBYTE(v27) = 0;
  v5 = GenerateEncodedHash((char *)a2 + 280, &v23);
  v6 = 1;
  if ( v5 < 0 )
    PushButtonReset::Logging::TraceErr(
      1,
      (unsigned int)v5,
      "WinREAgent::SaveWinREHash::InternalExecute",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\savewinrehash.cpp",
      87,
      L"Failed to generate hash for new wim");
  if ( *((_QWORD *)a2 + 56) )
  {
    PushButtonReset::Logging::Trace(0, L"SaveWinREHash: Save new WimRE Hash to Rollback info");
    v7 = *((_QWORD *)a2 + 56);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)v25,
      (__int64)L"NewWinREHash");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v24,
      (__int64)L"BackupWimPath");
    v8 = WinREAgent::RollbackHelper::WriteToConfig(v7, &v24, v25, &v23);
    ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v25[0] - 24LL));
    if ( v8 < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v8,
        "WinREAgent::SaveWinREHash::InternalExecute",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\savewinrehash.cpp",
        98,
        L"Failed to save new WinRE hash into rolblack info");
LABEL_18:
      ATL::CStringData::Release((ATL::CStringData *)(v23 - 24));
      v13 = (ATL::CStringData *)(v22 - 24);
      goto LABEL_30;
    }
  }
  v8 = WinREAgent::QueryWinREHashStatus((_QWORD *)a2 + 11, (__int64 *)a2 + 15, &v21, (bool *)&v26, (bool *)&v27, &v22);
  v9 = (WinREAgent::TelemetrySession *)*((_QWORD *)this + 14);
  v10 = (unsigned __int8)v26;
  v11 = (unsigned __int8)v27;
  if ( v9 )
  {
    WinREAgent::TelemetrySession::TraceDataPoint(v9, L"ServicingInfoGroup", L"BitLockerActive", v21);
    WinREAgent::TelemetrySession::TraceDataPoint(
      *((WinREAgent::TelemetrySession **)this + 14),
      L"ServicingInfoGroup",
      L"OldWinREIsTrusted",
      v10);
    WinREAgent::TelemetrySession::TraceDataPoint(
      *((WinREAgent::TelemetrySession **)this + 14),
      L"ServicingInfoGroup",
      L"OldWinREIsValidated",
      v11);
    WinREAgent::TelemetrySession::TraceDataPoint(
      *((WinREAgent::TelemetrySession **)this + 14),
      L"ServicingInfoGroup",
      L"QueryWinREHashResult",
      v8);
  }
  if ( v8 < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      1,
      (unsigned int)v8,
      "WinREAgent::SaveWinREHash::InternalExecute",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\savewinrehash.cpp",
      139,
      L"Failed to query WinRE hash status");
    LOBYTE(v10) = 0;
    LOBYTE(v11) = 0;
    v8 = 0;
  }
  if ( !(_BYTE)v10 && !(_BYTE)v11 )
    v6 = 0;
  *((_BYTE *)this + 120) = v6;
  if ( !v6 )
  {
    PushButtonReset::Logging::Trace(0, L"SaveWinREHash: Old wim is not trusted");
    v8 = 0;
    goto LABEL_18;
  }
  if ( *((_QWORD *)a2 + 56) )
  {
    PushButtonReset::Logging::Trace(0, L"SaveWinREHash: Save old WinRE hash to Rollback info");
    v12 = *((_QWORD *)a2 + 56);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v27,
      (__int64)L"OldWinREHash");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v26,
      (__int64)L"BackupWimPath");
    v8 = WinREAgent::RollbackHelper::WriteToConfig(v12, &v26, &v27, &v22);
    ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
    if ( v8 < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v8,
        "WinREAgent::SaveWinREHash::InternalExecute",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\savewinrehash.cpp",
        161,
        L"Failed to save old WinRE hash into rolblack info");
      goto LABEL_18;
    }
  }
  v14 = (ATL::CStringData *)(v22 - 24);
  v15 = (int *)(*((_QWORD *)this + 16) - 24LL);
  if ( (int *)(v22 - 24) != v15 )
  {
    if ( v15[4] >= 0 && *(_QWORD *)v14 == *(_QWORD *)v15 )
    {
      v16 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v22 - 24);
      ATL::CStringData::Release((ATL::CStringData *)v15);
      *((_QWORD *)this + 16) = v16 + 24;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 128, v22, *(unsigned int *)(v22 - 16));
    }
  }
  v17 = (ATL::CStringData *)(v23 - 24);
  v18 = (int *)(*((_QWORD *)this + 17) - 24LL);
  if ( (int *)(v23 - 24) != v18 )
  {
    if ( v18[4] >= 0 && *(_QWORD *)v17 == *(_QWORD *)v18 )
    {
      v19 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v23 - 24);
      ATL::CStringData::Release((ATL::CStringData *)v18);
      *((_QWORD *)this + 17) = v19 + 24;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 136, v23, *(unsigned int *)(v23 - 16));
    }
  }
  ATL::CStringData::Release(v17);
  v13 = v14;
LABEL_30:
  ATL::CStringData::Release(v13);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002b050  mov     [rsp-38h+arg_0], rbx
0x18002b055  push    rbp
0x18002b056  push    rsi
0x18002b057  push    rdi
0x18002b058  push    r12
0x18002b05a  push    r13
0x18002b05c  push    r14
0x18002b05e  push    r15
0x18002b060  mov     rbp, rsp
0x18002b063  sub     rsp, 60h
0x18002b067  mov     rsi, rdx
0x18002b06a  mov     r12, rcx
0x18002b06d  lea     rcx, [rbp+var_28]
0x18002b071  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002b076  nop
0x18002b077  lea     rcx, [rbp+var_20]
0x18002b07b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002b080  nop
0x18002b081  xor     r13d, r13d
0x18002b084  mov     [rbp+var_30], r13b
0x18002b088  mov     byte ptr [rbp+arg_8], r13b
0x18002b08c  mov     byte ptr [rbp+arg_18], r13b
0x18002b090  lea     rcx, [rsi+118h]
0x18002b097  lea     rdx, [rbp+var_20]
0x18002b09b  call    GenerateEncodedHash
0x18002b0a0  lea     r14d, [r13+1]
0x18002b0a4  test    eax, eax
0x18002b0a6  jns     short loc_18002B0D4
0x18002b0a8  lea     rcx, aFailedToGenera_2; "Failed to generate hash for new wim"
0x18002b0af  mov     [rsp+60h+var_38], rcx
0x18002b0b4  mov     dword ptr [rsp+60h+var_40], 57h ; 'W'
0x18002b0bc  lea     r9, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002b0c3  lea     r8, aWinreagentSave; "WinREAgent::SaveWinREHash::InternalExec"...
0x18002b0ca  mov     edx, eax
0x18002b0cc  mov     ecx, r14d
0x18002b0cf  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002b0d4  cmp     [rsi+1C0h], r13
0x18002b0db  jz      loc_18002B166
0x18002b0e1  lea     rdx, aSavewinrehashS_0; "SaveWinREHash: Save new WimRE Hash to R"...
0x18002b0e8  xor     ecx, ecx
0x18002b0ea  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002b0ef  mov     rbx, [rsi+1C0h]
0x18002b0f6  lea     rdx, aNewwinrehash; "NewWinREHash"
0x18002b0fd  lea     rcx, [rbp+var_10]
0x18002b101  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002b106  nop
0x18002b107  lea     rdx, aBackupwimpath; "BackupWimPath"
0x18002b10e  lea     rcx, [rbp+var_18]
0x18002b112  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002b117  nop
0x18002b118  lea     r9, [rbp+var_20]
0x18002b11c  lea     r8, [rbp+var_10]
0x18002b120  lea     rdx, [rbp+var_18]
0x18002b124  mov     rcx, rbx
0x18002b127  call    ?WriteToConfig@RollbackHelper@WinREAgent@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00@Z; WinREAgent::RollbackHelper::WriteToConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002b12c  mov     edi, eax
0x18002b12e  mov     rcx, [rbp+var_18]
0x18002b132  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002b136  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002b13b  nop
0x18002b13c  mov     rcx, [rbp+var_10]
0x18002b140  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002b144  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002b149  test    edi, edi
0x18002b14b  jns     short loc_18002B166
0x18002b14d  lea     rax, aFailedToSaveNe; "Failed to save new WinRE hash into rolb"...
0x18002b154  mov     [rsp+60h+var_38], rax
0x18002b159  mov     dword ptr [rsp+60h+var_40], 62h ; 'b'
0x18002b161  jmp     loc_18002B2F7
0x18002b166  lea     rdx, [rsi+78h]
0x18002b16a  lea     rcx, [rsi+58h]
0x18002b16e  lea     rax, [rbp+var_28]
0x18002b172  mov     [rsp+60h+var_38], rax
0x18002b177  lea     rax, [rbp+arg_18]
0x18002b17b  mov     [rsp+60h+var_40], rax
0x18002b180  lea     r9, [rbp+arg_8]
0x18002b184  lea     r8, [rbp+var_30]
0x18002b188  call    ?QueryWinREHashStatus@WinREAgent@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0AEA_N11PEAV23@@Z; WinREAgent::QueryWinREHashStatus(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool &,bool &,bool &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18002b18d  mov     edi, eax
0x18002b18f  mov     rcx, [r12+70h]; this
0x18002b194  movzx   ebx, byte ptr [rbp+arg_8]
0x18002b198  movzx   r15d, byte ptr [rbp+arg_18]
0x18002b19d  test    rcx, rcx
0x18002b1a0  jz      short loc_18002B205
0x18002b1a2  movzx   r9d, [rbp+var_30]; unsigned int
0x18002b1a7  lea     r8, aBitlockeractiv; "BitLockerActive"
0x18002b1ae  lea     r13, aServicinginfog; "ServicingInfoGroup"
0x18002b1b5  mov     rdx, r13; unsigned __int16 *
0x18002b1b8  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ulong)
0x18002b1bd  mov     r9d, ebx; unsigned int
0x18002b1c0  lea     r8, aOldwinreistrus; "OldWinREIsTrusted"
0x18002b1c7  mov     rdx, r13; unsigned __int16 *
0x18002b1ca  mov     rcx, [r12+70h]; this
0x18002b1cf  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ulong)
0x18002b1d4  mov     r9d, r15d; unsigned int
0x18002b1d7  lea     r8, aOldwinreisvali; "OldWinREIsValidated"
0x18002b1de  mov     rdx, r13; unsigned __int16 *
0x18002b1e1  mov     rcx, [r12+70h]; this
0x18002b1e6  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ulong)
0x18002b1eb  mov     r9d, edi; unsigned int
0x18002b1ee  lea     r8, aQuerywinrehash; "QueryWinREHashResult"
0x18002b1f5  mov     rdx, r13; unsigned __int16 *
0x18002b1f8  mov     rcx, [r12+70h]; this
0x18002b1fd  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ulong)
0x18002b202  xor     r13d, r13d
0x18002b205  test    edi, edi
0x18002b207  jns     short loc_18002B23E
0x18002b209  lea     rax, aFailedToQueryW; "Failed to query WinRE hash status"
0x18002b210  mov     [rsp+60h+var_38], rax
0x18002b215  mov     dword ptr [rsp+60h+var_40], 8Bh
0x18002b21d  lea     r9, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002b224  lea     r8, aWinreagentSave; "WinREAgent::SaveWinREHash::InternalExec"...
0x18002b22b  mov     edx, edi
0x18002b22d  mov     ecx, r14d
0x18002b230  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002b235  mov     bl, r13b
0x18002b238  mov     r15b, r13b
0x18002b23b  mov     edi, r13d
0x18002b23e  test    bl, bl
0x18002b240  jnz     short loc_18002B24A
0x18002b242  test    r15b, r15b
0x18002b245  jnz     short loc_18002B24A
0x18002b247  mov     r14b, r13b
0x18002b24a  mov     [r12+78h], r14b
0x18002b24f  test    r14b, r14b
0x18002b252  jnz     short loc_18002B26A
0x18002b254  lea     rdx, aSavewinrehashO; "SaveWinREHash: Old wim is not trusted"
0x18002b25b  xor     ecx, ecx
0x18002b25d  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002b262  mov     edi, r13d
0x18002b265  jmp     loc_18002B312
0x18002b26a  cmp     [rsi+1C0h], r13
0x18002b271  jz      loc_18002B32D
0x18002b277  lea     rdx, aSavewinrehashS; "SaveWinREHash: Save old WinRE hash to R"...
0x18002b27e  xor     ecx, ecx
0x18002b280  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002b285  mov     rbx, [rsi+1C0h]
0x18002b28c  lea     rdx, aOldwinrehash; "OldWinREHash"
0x18002b293  lea     rcx, [rbp+arg_18]
0x18002b297  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002b29c  nop
0x18002b29d  lea     rdx, aBackupwimpath; "BackupWimPath"
0x18002b2a4  lea     rcx, [rbp+arg_8]
0x18002b2a8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002b2ad  nop
0x18002b2ae  lea     r9, [rbp+var_28]
0x18002b2b2  lea     r8, [rbp+arg_18]
0x18002b2b6  lea     rdx, [rbp+arg_8]
0x18002b2ba  mov     rcx, rbx
0x18002b2bd  call    ?WriteToConfig@RollbackHelper@WinREAgent@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00@Z; WinREAgent::RollbackHelper::WriteToConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002b2c2  mov     edi, eax
0x18002b2c4  mov     rcx, [rbp+arg_8]
0x18002b2c8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002b2cc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002b2d1  nop
0x18002b2d2  mov     rcx, [rbp+arg_18]
0x18002b2d6  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002b2da  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002b2df  test    edi, edi
0x18002b2e1  jns     short loc_18002B32D
0x18002b2e3  lea     rax, aFailedToSaveOl; "Failed to save old WinRE hash into rolb"...
0x18002b2ea  mov     [rsp+60h+var_38], rax
0x18002b2ef  mov     dword ptr [rsp+60h+var_40], 0A1h
0x18002b2f7  lea     r9, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002b2fe  lea     r8, aWinreagentSave; "WinREAgent::SaveWinREHash::InternalExec"...
0x18002b305  mov     edx, edi
0x18002b307  mov     ecx, 2
0x18002b30c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002b311  nop
0x18002b312  mov     rcx, [rbp+var_20]
0x18002b316  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002b31a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002b31f  nop
0x18002b320  mov     rcx, [rbp+var_28]
0x18002b324  add     rcx, 0FFFFFFFFFFFFFFE8h
0x18002b328  jmp     loc_18002B3E5
0x18002b32d  lea     r14, [r12+80h]
0x18002b335  mov     rdx, [rbp+var_28]
0x18002b339  lea     r15, [rdx-18h]
0x18002b33d  mov     rsi, [r14]
0x18002b340  add     rsi, 0FFFFFFFFFFFFFFE8h
0x18002b344  cmp     r15, rsi
0x18002b347  jz      short loc_18002B37F
0x18002b349  cmp     [rsi+10h], r13d
0x18002b34d  jl      short loc_18002B373
0x18002b34f  mov     rax, [rsi]
0x18002b352  cmp     [r15], rax
0x18002b355  jnz     short loc_18002B373
0x18002b357  mov     rcx, r15
0x18002b35a  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18002b35f  mov     rbx, rax
0x18002b362  mov     rcx, rsi; this
0x18002b365  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002b36a  lea     rax, [rbx+18h]
0x18002b36e  mov     [r14], rax
0x18002b371  jmp     short loc_18002B37F
0x18002b373  mov     r8d, [rdx-10h]
0x18002b377  mov     rcx, r14
0x18002b37a  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002b37f  mov     rdx, [rbp+var_20]
0x18002b383  lea     rsi, [rdx-18h]
0x18002b387  mov     r14, [r12+88h]
0x18002b38f  add     r14, 0FFFFFFFFFFFFFFE8h
0x18002b393  cmp     rsi, r14
0x18002b396  jz      short loc_18002B3D9
0x18002b398  cmp     [r14+10h], r13d
0x18002b39c  jl      short loc_18002B3C7
0x18002b39e  mov     rax, [r14]
0x18002b3a1  cmp     [rsi], rax
0x18002b3a4  jnz     short loc_18002B3C7
0x18002b3a6  mov     rcx, rsi
0x18002b3a9  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18002b3ae  mov     rbx, rax
0x18002b3b1  mov     rcx, r14; this
0x18002b3b4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002b3b9  lea     rax, [rbx+18h]
0x18002b3bd  mov     [r12+88h], rax
0x18002b3c5  jmp     short loc_18002B3D9
0x18002b3c7  mov     r8d, [rdx-10h]
0x18002b3cb  lea     rcx, [r12+88h]
0x18002b3d3  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18002b3d8  nop
0x18002b3d9  mov     rcx, rsi; this
0x18002b3dc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002b3e1  nop
0x18002b3e2  mov     rcx, r15; this
0x18002b3e5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002b3ea  mov     eax, edi
0x18002b3ec  mov     rbx, [rsp+60h+arg_0]
0x18002b3f4  add     rsp, 60h
0x18002b3f8  pop     r15
0x18002b3fa  pop     r14
0x18002b3fc  pop     r13
0x18002b3fe  pop     r12
0x18002b400  pop     rdi
0x18002b401  pop     rsi
0x18002b402  pop     rbp
0x18002b403  retn
```
