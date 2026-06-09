# WinREAgent::RollbackHelper::ResumeExecutionContext(WinREAgent::ExecutionContext *)

- ea: `0x180031810`
- end: `0x180032074`
- name: `?ResumeExecutionContext@RollbackHelper@WinREAgent@@AEAAJPEAVExecutionContext@2@@Z`
- size: `2148`
- prototype: `__int64 __fastcall(WinREAgent::RollbackHelper *__hidden this, struct WinREAgent::ExecutionContext *)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002f978`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x180005cc0`
- `0x180008104`
- `0x18000d92c`
- `0x180031720`
- `0x180031810`
- `0x1800323c0`
- `0x18003717c`
- `0x180037344`
- `0x18004d2ac`
- `0x180054cc4`
- `0x18005556c`
- `0x18005563c`
- `0x180055b2c`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180031f32`
- `KERNEL32!GetLastError` at `0x180031f32`
- `ReAgent!WinReHashWimFile` at `0x180031f21`
- `ReAgent!WinReHashWimFile` at `0x180031f21`

## string_xrefs

- `0x180031a9c`: `CurrentWimPath`
- `0x180031b11`: `CurrentWimPath`
- `0x180031931`: `BackupWimPath`
- `0x1800319a6`: `BackupWimPath`
- `0x180031864`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x1800318fe`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x180031a11`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x180031b7c`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x180031cd5`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x180031e33`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x180031f5d`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x180031fb4`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x18003183d`: `RollbackHelper::ResumeExecutionContext: Start`
- `0x18003186b`: `WinREAgent::RollbackHelper::ResumeExecutionContext`
- `0x180031905`: `WinREAgent::RollbackHelper::ResumeExecutionContext`
- `0x180031a18`: `WinREAgent::RollbackHelper::ResumeExecutionContext`
- `0x180031b83`: `WinREAgent::RollbackHelper::ResumeExecutionContext`
- `0x180031cdc`: `WinREAgent::RollbackHelper::ResumeExecutionContext`
- `0x180031e3a`: `WinREAgent::RollbackHelper::ResumeExecutionContext`
- `0x180031f64`: `WinREAgent::RollbackHelper::ResumeExecutionContext`
- `0x180031fbb`: `WinREAgent::RollbackHelper::ResumeExecutionContext`
- `0x18003189b`: `RollbackHelper: InI file [%s] doesn't exist`
- `0x1800319fd`: `Failed to get backup WinRE wim path from rollback info`
- `0x180031a64`: `RollbackHelper: Update Backup WinRE.wim path from [%s] to [%s]`
- `0x180031a72`: `Backup Wim Path is consistent, no need to update`
- `0x180031b68`: `Failed to get current WinRE wim path from rollback info`
- `0x180031bbd`: `RollbackHelper: Update current WinRE.wim path from [%s] to [%s]`
- `0x180031bcb`: `Current Wim Path is consistent, no need to update`
- `0x180031cc1`: `Failed to get new WinRE hash from rollback info`
- `0x180031d1b`: `RollbackHelper: Update new WinRE hash from [%s] to [%s]`
- `0x180031d29`: `New WinRE hash is consistent, no need to update`
- `0x180031e1f`: `Failed to get old WinRE hash from rollback info`
- `0x180031e79`: `RollbackHelper: Update old WinRE hash from [%s] to [%s]`
- `0x180031e87`: `Old WinRE hash is consistent, no need to update`
- `0x180031ecc`: `There is no backup Wim path`
- `0x180031efc`: `Backup Wim path [%s] doesn't exist`
- `0x180032032`: `RollbackHelper::ResumeExecutionContext: Completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall WinREAgent::RollbackHelper::ResumeExecutionContext(
        WinREAgent::RollbackHelper *this,
        struct WinREAgent::ExecutionContext *a2)
{
  __int64 v5; // rax
  int Value; // edi
  __int64 v7; // rbx
  __int64 v8; // rbx
  __int64 v9; // r8
  char v10; // al
  __int64 v11; // rbx
  __int64 v12; // rbx
  __int64 v13; // rbx
  __int64 v14; // r8
  char v15; // al
  __int64 v16; // rbx
  __int64 v17; // rbx
  __int64 v18; // rbx
  char v19; // al
  __int64 v20; // rbx
  __int64 v21; // rbx
  __int64 v22; // rbx
  char v23; // al
  __int64 v24; // rbx
  _QWORD *v25; // r15
  char v26; // al
  __int64 v27; // rcx
  __int64 v28; // rbx
  signed int LastError; // eax
  char v30; // r14
  __int64 v31; // rdx
  unsigned __int16 *v32; // rbx
  unsigned __int16 *v33; // rax
  int v34; // r9d
  int v35; // ecx
  __int64 v36; // [rsp+40h] [rbp-19h] BYREF
  unsigned __int16 *v37; // [rsp+48h] [rbp-11h] BYREF
  __int64 v38; // [rsp+50h] [rbp-9h] BYREF
  _QWORD v39[2]; // [rsp+58h] [rbp-1h] BYREF
  _OWORD v40[2]; // [rsp+68h] [rbp+Fh] BYREF

  PushButtonReset::Logging::Trace(0, L"RollbackHelper::ResumeExecutionContext: Start");
  if ( !a2 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942487LL,
      "WinREAgent::RollbackHelper::ResumeExecutionContext",
      "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
      449,
      L"executionContext cannot be null");
    return 2147942487LL;
  }
  if ( !(unsigned __int8)PushButtonReset::File::Exists((char *)this + 8) )
  {
    PushButtonReset::Logging::Trace(0, L"RollbackHelper: InI file [%s] doesn't exist", *((_QWORD *)this + 1));
    return 1;
  }
  v39[1] = 0;
  v39[0] = &RAII::CAutoPbrDelete<PushButtonReset::IniFile *>::`vftable';
  v5 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v39);
  Value = PushButtonReset::IniFile::Load((char *)this + 8, v5);
  if ( Value >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD *))(v39[0] + 24LL))(v39);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v36,
      (__int64)L"BackupWimPath");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v38,
      (__int64)L"GeneralInfo");
    LOBYTE(v7) = PushButtonReset::IniFile::HasKey(v7, &v38, &v36);
    ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
    if ( (_BYTE)v7 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v38);
      v8 = (*(__int64 (__fastcall **)(_QWORD *))(v39[0] + 24LL))(v39);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v37,
        (__int64)L"BackupWimPath");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v36,
        (__int64)L"GeneralInfo");
      Value = PushButtonReset::IniFile::GetValue(v8, &v36, &v37, &v38);
      ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v37 - 12));
      if ( Value < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Value,
          "WinREAgent::RollbackHelper::ResumeExecutionContext",
          "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
          467,
          L"Failed to get backup WinRE wim path from rollback info");
LABEL_10:
        ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
        goto LABEL_56;
      }
      LOBYTE(v9) = 1;
      v10 = ShouldUpdate((char *)a2 + 312, &v38, v9);
      v11 = v38;
      if ( v10 )
        PushButtonReset::Logging::Trace(
          0,
          L"RollbackHelper: Update Backup WinRE.wim path from [%s] to [%s]",
          *((_QWORD *)a2 + 39),
          v38);
      else
        PushButtonReset::Logging::Trace(0, L"Backup Wim Path is consistent, no need to update");
      ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
    }
    v12 = (*(__int64 (__fastcall **)(_QWORD *))(v39[0] + 24LL))(v39);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v36,
      (__int64)L"CurrentWimPath");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v37,
      (__int64)L"GeneralInfo");
    LOBYTE(v12) = PushButtonReset::IniFile::HasKey(v12, &v37, &v36);
    ATL::CStringData::Release((ATL::CStringData *)(v37 - 12));
    ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
    if ( (_BYTE)v12 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v38);
      v13 = (*(__int64 (__fastcall **)(_QWORD *))(v39[0] + 24LL))(v39);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v36,
        (__int64)L"CurrentWimPath");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v37,
        (__int64)L"GeneralInfo");
      Value = PushButtonReset::IniFile::GetValue(v13, &v37, &v36, &v38);
      ATL::CStringData::Release((ATL::CStringData *)(v37 - 12));
      ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
      if ( Value < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Value,
          "WinREAgent::RollbackHelper::ResumeExecutionContext",
          "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
          486,
          L"Failed to get current WinRE wim path from rollback info");
        goto LABEL_10;
      }
      LOBYTE(v14) = 1;
      v15 = ShouldUpdate((char *)a2 + 120, &v38, v14);
      v16 = v38;
      if ( v15 )
        PushButtonReset::Logging::Trace(
          0,
          L"RollbackHelper: Update current WinRE.wim path from [%s] to [%s]",
          *((_QWORD *)a2 + 15),
          v38);
      else
        PushButtonReset::Logging::Trace(0, L"Current Wim Path is consistent, no need to update");
      ATL::CStringData::Release((ATL::CStringData *)(v16 - 24));
    }
    v17 = (*(__int64 (__fastcall **)(_QWORD *))(v39[0] + 24LL))(v39);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v36,
      (__int64)L"NewWinREHash");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v37,
      (__int64)L"GeneralInfo");
    LOBYTE(v17) = PushButtonReset::IniFile::HasKey(v17, &v37, &v36);
    ATL::CStringData::Release((ATL::CStringData *)(v37 - 12));
    ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
    if ( (_BYTE)v17 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v38);
      v18 = (*(__int64 (__fastcall **)(_QWORD *))(v39[0] + 24LL))(v39);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v36,
        (__int64)L"NewWinREHash");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v37,
        (__int64)L"GeneralInfo");
      Value = PushButtonReset::IniFile::GetValue(v18, &v37, &v36, &v38);
      ATL::CStringData::Release((ATL::CStringData *)(v37 - 12));
      ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
      if ( Value < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Value,
          "WinREAgent::RollbackHelper::ResumeExecutionContext",
          "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
          505,
          L"Failed to get new WinRE hash from rollback info");
        goto LABEL_10;
      }
      v19 = ShouldUpdate((char *)a2 + 408, &v38, 0);
      v20 = v38;
      if ( v19 )
        PushButtonReset::Logging::Trace(
          0,
          L"RollbackHelper: Update new WinRE hash from [%s] to [%s]",
          *((_QWORD *)a2 + 51),
          v38);
      else
        PushButtonReset::Logging::Trace(0, L"New WinRE hash is consistent, no need to update");
      ATL::CStringData::Release((ATL::CStringData *)(v20 - 24));
    }
    v21 = (*(__int64 (__fastcall **)(_QWORD *))(v39[0] + 24LL))(v39);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v36,
      (__int64)L"OldWinREHash");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v37,
      (__int64)L"GeneralInfo");
    LOBYTE(v21) = PushButtonReset::IniFile::HasKey(v21, &v37, &v36);
    ATL::CStringData::Release((ATL::CStringData *)(v37 - 12));
    ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
    if ( (_BYTE)v21 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v38);
      v22 = (*(__int64 (__fastcall **)(_QWORD *))(v39[0] + 24LL))(v39);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v36,
        (__int64)L"OldWinREHash");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v37,
        (__int64)L"GeneralInfo");
      Value = PushButtonReset::IniFile::GetValue(v22, &v37, &v36, &v38);
      ATL::CStringData::Release((ATL::CStringData *)(v37 - 12));
      ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
      if ( Value < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Value,
          "WinREAgent::RollbackHelper::ResumeExecutionContext",
          "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
          524,
          L"Failed to get old WinRE hash from rollback info");
        goto LABEL_10;
      }
      v23 = ShouldUpdate((char *)a2 + 376, &v38, 0);
      v24 = v38;
      if ( v23 )
        PushButtonReset::Logging::Trace(
          0,
          L"RollbackHelper: Update old WinRE hash from [%s] to [%s]",
          *((_QWORD *)a2 + 47),
          v38);
      else
        PushButtonReset::Logging::Trace(0, L"Old WinRE hash is consistent, no need to update");
      ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
    }
    v25 = (_QWORD *)((char *)a2 + 376);
    if ( *(_DWORD *)(*((_QWORD *)a2 + 47) - 16LL) )
    {
      PushButtonReset::Logging::Trace(0, L"Verify Old WinRE hash");
      if ( *(_DWORD *)(*((_QWORD *)a2 + 39) - 16LL) )
      {
        v26 = PushButtonReset::File::Exists((char *)a2 + 312);
        v27 = *((_QWORD *)a2 + 39);
        if ( v26 )
        {
          memset(v40, 0, sizeof(v40));
          if ( (unsigned int)WinReHashWimFile(v27, v40) )
          {
            v30 = 0;
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v37);
            Value = PushButtonReset::Encode::EncodeBase64(v40, v31, &v37);
            v32 = v37;
            if ( Value >= 0 )
            {
              v33 = v37;
              do
              {
                v34 = *(unsigned __int16 *)((char *)v33 + *v25 - (_QWORD)v37);
                v35 = *v33 - v34;
                if ( v35 )
                  break;
                ++v33;
              }
              while ( v34 );
              if ( v35 )
                PushButtonReset::Logging::Trace(0, L"Old Wim hash [%s] doesn't match backup wim hash [%s]", *v25, v37);
              else
                v30 = 1;
            }
            else
            {
              PushButtonReset::Logging::TraceErr(
                1,
                (unsigned int)Value,
                "WinREAgent::RollbackHelper::ResumeExecutionContext",
                "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
                567,
                L"Failed to encode hash");
              Value = 0;
            }
            ATL::CStringData::Release((ATL::CStringData *)(v32 - 12));
            if ( v30 )
              goto LABEL_55;
          }
          else
          {
            v28 = *((_QWORD *)a2 + 39);
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            PushButtonReset::Logging::TraceErr(
              1,
              (unsigned int)LastError,
              "WinREAgent::RollbackHelper::ResumeExecutionContext",
              "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
              559,
              L"Failed to hash wim file [%s]",
              v28);
          }
        }
        else
        {
          PushButtonReset::Logging::Trace(1, L"Backup Wim path [%s] doesn't exist", *((_QWORD *)a2 + 39));
        }
      }
      else
      {
        PushButtonReset::Logging::Trace(1, L"There is no backup Wim path");
      }
      PushButtonReset::Logging::Trace(0, L"Old WinRE hash is invalid, empty it");
      ATL::CSimpleStringT<unsigned short,0>::Empty(v25);
    }
LABEL_55:
    PushButtonReset::Logging::Trace(0, L"RollbackHelper::ResumeExecutionContext: Completed");
    goto LABEL_56;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)Value,
    "WinREAgent::RollbackHelper::ResumeExecutionContext",
    "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
    460,
    L"Failed to load INI file [%s]",
    *((_QWORD *)this + 1));
LABEL_56:
  v39[0] = &RAII::CAutoPbrDelete<PushButtonReset::IniFile *>::`vftable';
  RAII::CAutoPbrDelete<PushButtonReset::IniFile *>::Release(v39);
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x180031810  mov     [rsp-8+arg_10], rbx
0x180031815  push    rbp
0x180031816  push    rdi
0x180031817  push    r13
0x180031819  push    r14
0x18003181b  push    r15
0x18003181d  lea     rbp, [rsp-37h]
0x180031822  sub     rsp, 90h
0x180031829  mov     rax, cs:__security_cookie
0x180031830  xor     rax, rsp
0x180031833  mov     [rbp+57h+var_28], rax
0x180031837  mov     r14, rdx
0x18003183a  mov     rbx, rcx
0x18003183d  lea     rdx, aRollbackhelper_13; "RollbackHelper::ResumeExecutionContext:"...
0x180031844  xor     ecx, ecx
0x180031846  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18003184b  test    r14, r14
0x18003184e  jnz     short loc_18003188A
0x180031850  lea     rax, aExecutionconte_0; "executionContext cannot be null"
0x180031857  mov     [rsp+0B0h+var_88], rax
0x18003185c  mov     [rsp+0B0h+var_90], 1C1h
0x180031864  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18003186b  lea     r8, aWinreagentRoll_7; "WinREAgent::RollbackHelper::ResumeExecu"...
0x180031872  mov     edx, 80070057h
0x180031877  lea     ecx, [r14+2]
0x18003187b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180031880  mov     eax, 80070057h
0x180031885  jmp     loc_180032050
0x18003188a  lea     rcx, [rbx+8]
0x18003188e  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180031893  test    al, al
0x180031895  jnz     short loc_1800318B3
0x180031897  mov     r8, [rbx+8]
0x18003189b  lea     rdx, aRollbackhelper_7; "RollbackHelper: InI file [%s] doesn't e"...
0x1800318a2  xor     ecx, ecx
0x1800318a4  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800318a9  mov     eax, 1
0x1800318ae  jmp     loc_180032050
0x1800318b3  mov     [rbp+57h+var_50], 0
0x1800318bb  lea     r13, ??_7?$CAutoPbrDelete@PEAVIniFile@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::IniFile *>::`vftable'
0x1800318c2  mov     [rbp+57h+var_58], r13
0x1800318c6  lea     rcx, [rbp+57h+var_58]
0x1800318ca  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x1800318cf  mov     rdx, rax
0x1800318d2  lea     rcx, [rbx+8]
0x1800318d6  call    ?Load@IniFile@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::IniFile::Load(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::IniFile * *)
0x1800318db  mov     edi, eax
0x1800318dd  test    eax, eax
0x1800318df  jns     short loc_18003191D
0x1800318e1  mov     rcx, [rbx+8]
0x1800318e5  mov     [rsp+0B0h+var_80], rcx
0x1800318ea  lea     rax, aFailedToLoadIn_0; "Failed to load INI file [%s]"
0x1800318f1  mov     [rsp+0B0h+var_88], rax
0x1800318f6  mov     [rsp+0B0h+var_90], 1CCh
0x1800318fe  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180031905  lea     r8, aWinreagentRoll_7; "WinREAgent::RollbackHelper::ResumeExecu"...
0x18003190c  mov     edx, edi
0x18003190e  mov     ecx, 2
0x180031913  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180031918  jmp     loc_180032041
0x18003191d  mov     rax, [rbp+57h+var_58]
0x180031921  lea     rcx, [rbp+57h+var_58]
0x180031925  mov     rax, [rax+18h]
0x180031929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003192e  mov     rbx, rax
0x180031931  lea     rdx, aBackupwimpath; "BackupWimPath"
0x180031938  lea     rcx, [rbp+57h+var_70]
0x18003193c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180031941  nop
0x180031942  lea     rdx, aGeneralinfo; "GeneralInfo"
0x180031949  lea     rcx, [rbp+57h+var_60]
0x18003194d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180031952  nop
0x180031953  lea     r8, [rbp+57h+var_70]
0x180031957  lea     rdx, [rbp+57h+var_60]
0x18003195b  mov     rcx, rbx
0x18003195e  call    ?HasKey@IniFile@PushButtonReset@@QEBA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; PushButtonReset::IniFile::HasKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180031963  mov     bl, al
0x180031965  mov     rcx, [rbp+57h+var_60]
0x180031969  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003196d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031972  nop
0x180031973  mov     rcx, [rbp+57h+var_70]
0x180031977  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003197b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031980  test    bl, bl
0x180031982  jz      loc_180031A88
0x180031988  lea     rcx, [rbp+57h+var_60]
0x18003198c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180031991  nop
0x180031992  mov     rax, [rbp+57h+var_58]
0x180031996  lea     rcx, [rbp+57h+var_58]
0x18003199a  mov     rax, [rax+18h]
0x18003199e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800319a3  mov     rbx, rax
0x1800319a6  lea     rdx, aBackupwimpath; "BackupWimPath"
0x1800319ad  lea     rcx, [rbp+57h+var_68]
0x1800319b1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800319b6  nop
0x1800319b7  lea     rdx, aGeneralinfo; "GeneralInfo"
0x1800319be  lea     rcx, [rbp+57h+var_70]
0x1800319c2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800319c7  nop
0x1800319c8  lea     r9, [rbp+57h+var_60]
0x1800319cc  lea     r8, [rbp+57h+var_68]
0x1800319d0  lea     rdx, [rbp+57h+var_70]
0x1800319d4  mov     rcx, rbx
0x1800319d7  call    ?GetValue@IniFile@PushButtonReset@@QEBAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::IniFile::GetValue(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x1800319dc  mov     edi, eax
0x1800319de  mov     rcx, [rbp+57h+var_70]
0x1800319e2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800319e6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800319eb  nop
0x1800319ec  mov     rcx, [rbp+57h+var_68]
0x1800319f0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800319f4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800319f9  test    edi, edi
0x1800319fb  jns     short loc_180031A3E
0x1800319fd  lea     rax, aFailedToGetBac; "Failed to get backup WinRE wim path fro"...
0x180031a04  mov     [rsp+0B0h+var_88], rax
0x180031a09  mov     [rsp+0B0h+var_90], 1D3h
0x180031a11  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180031a18  lea     r8, aWinreagentRoll_7; "WinREAgent::RollbackHelper::ResumeExecu"...
0x180031a1f  mov     edx, edi
0x180031a21  mov     ecx, 2
0x180031a26  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180031a2b  nop
0x180031a2c  mov     rcx, [rbp+57h+var_60]
0x180031a30  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180031a34  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031a39  jmp     loc_180032041
0x180031a3e  lea     r15, [r14+138h]
0x180031a45  mov     r8b, 1
0x180031a48  lea     rdx, [rbp+57h+var_60]
0x180031a4c  mov     rcx, r15
0x180031a4f  call    ShouldUpdate
0x180031a54  mov     rbx, [rbp+57h+var_60]
0x180031a58  xor     ecx, ecx
0x180031a5a  test    al, al
0x180031a5c  jz      short loc_180031A72
0x180031a5e  mov     r9, rbx
0x180031a61  mov     r8, [r15]
0x180031a64  lea     rdx, aRollbackhelper_3; "RollbackHelper: Update Backup WinRE.wim"...
0x180031a6b  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180031a70  jmp     short loc_180031A7F
0x180031a72  lea     rdx, aBackupWimPathI; "Backup Wim Path is consistent, no need "...
0x180031a79  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180031a7e  nop
0x180031a7f  lea     rcx, [rbx-18h]; this
0x180031a83  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031a88  mov     rax, [rbp+57h+var_58]
0x180031a8c  lea     rcx, [rbp+57h+var_58]
0x180031a90  mov     rax, [rax+18h]
0x180031a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a99  mov     rbx, rax
0x180031a9c  lea     rdx, aCurrentwimpath; "CurrentWimPath"
0x180031aa3  lea     rcx, [rbp+57h+var_70]
0x180031aa7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180031aac  nop
0x180031aad  lea     rdx, aGeneralinfo; "GeneralInfo"
0x180031ab4  lea     rcx, [rbp+57h+var_68]
0x180031ab8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180031abd  nop
0x180031abe  lea     r8, [rbp+57h+var_70]
0x180031ac2  lea     rdx, [rbp+57h+var_68]
0x180031ac6  mov     rcx, rbx
0x180031ac9  call    ?HasKey@IniFile@PushButtonReset@@QEBA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; PushButtonReset::IniFile::HasKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180031ace  mov     bl, al
0x180031ad0  mov     rcx, [rbp+57h+var_68]
0x180031ad4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180031ad8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031add  nop
0x180031ade  mov     rcx, [rbp+57h+var_70]
0x180031ae2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180031ae6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031aeb  test    bl, bl
0x180031aed  jz      loc_180031BE1
0x180031af3  lea     rcx, [rbp+57h+var_60]
0x180031af7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180031afc  nop
0x180031afd  mov     rax, [rbp+57h+var_58]
0x180031b01  lea     rcx, [rbp+57h+var_58]
0x180031b05  mov     rax, [rax+18h]
0x180031b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b0e  mov     rbx, rax
0x180031b11  lea     rdx, aCurrentwimpath; "CurrentWimPath"
0x180031b18  lea     rcx, [rbp+57h+var_70]
0x180031b1c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180031b21  nop
0x180031b22  lea     rdx, aGeneralinfo; "GeneralInfo"
0x180031b29  lea     rcx, [rbp+57h+var_68]
0x180031b2d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180031b32  nop
0x180031b33  lea     r9, [rbp+57h+var_60]
0x180031b37  lea     r8, [rbp+57h+var_70]
0x180031b3b  lea     rdx, [rbp+57h+var_68]
0x180031b3f  mov     rcx, rbx
0x180031b42  call    ?GetValue@IniFile@PushButtonReset@@QEBAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::IniFile::GetValue(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180031b47  mov     edi, eax
0x180031b49  mov     rcx, [rbp+57h+var_68]
0x180031b4d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180031b51  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031b56  nop
0x180031b57  mov     rcx, [rbp+57h+var_70]
0x180031b5b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180031b5f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031b64  test    edi, edi
0x180031b66  jns     short loc_180031B9C
0x180031b68  lea     rax, aFailedToGetCur_0; "Failed to get current WinRE wim path fr"...
0x180031b6f  mov     [rsp+0B0h+var_88], rax
0x180031b74  mov     [rsp+0B0h+var_90], 1E6h
0x180031b7c  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180031b83  lea     r8, aWinreagentRoll_7; "WinREAgent::RollbackHelper::ResumeExecu"...
0x180031b8a  mov     edx, edi
0x180031b8c  mov     ecx, 2
0x180031b91  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180031b96  nop
0x180031b97  jmp     loc_180031A2C
0x180031b9c  mov     r8b, 1
0x180031b9f  lea     rdx, [rbp+57h+var_60]
0x180031ba3  lea     rcx, [r14+78h]
0x180031ba7  call    ShouldUpdate
0x180031bac  mov     rbx, [rbp+57h+var_60]
0x180031bb0  xor     ecx, ecx
0x180031bb2  test    al, al
0x180031bb4  jz      short loc_180031BCB
0x180031bb6  mov     r9, rbx
0x180031bb9  mov     r8, [r14+78h]
0x180031bbd  lea     rdx, aRollbackhelper_5; "RollbackHelper: Update current WinRE.wi"...
0x180031bc4  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180031bc9  jmp     short loc_180031BD8
0x180031bcb  lea     rdx, aCurrentWimPath; "Current Wim Path is consistent, no need"...
0x180031bd2  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180031bd7  nop
0x180031bd8  lea     rcx, [rbx-18h]; this
0x180031bdc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031be1  mov     rax, [rbp+57h+var_58]
0x180031be5  lea     rcx, [rbp+57h+var_58]
0x180031be9  mov     rax, [rax+18h]
0x180031bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031bf2  mov     rbx, rax
0x180031bf5  lea     rdx, aNewwinrehash; "NewWinREHash"
0x180031bfc  lea     rcx, [rbp+57h+var_70]
0x180031c00  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180031c05  nop
0x180031c06  lea     rdx, aGeneralinfo; "GeneralInfo"
0x180031c0d  lea     rcx, [rbp+57h+var_68]
0x180031c11  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180031c16  nop
0x180031c17  lea     r8, [rbp+57h+var_70]
0x180031c1b  lea     rdx, [rbp+57h+var_68]
0x180031c1f  mov     rcx, rbx
0x180031c22  call    ?HasKey@IniFile@PushButtonReset@@QEBA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; PushButtonReset::IniFile::HasKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180031c27  mov     bl, al
0x180031c29  mov     rcx, [rbp+57h+var_68]
0x180031c2d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180031c31  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031c36  nop
0x180031c37  mov     rcx, [rbp+57h+var_70]
0x180031c3b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180031c3f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031c44  test    bl, bl
0x180031c46  jz      loc_180031D3F
0x180031c4c  lea     rcx, [rbp+57h+var_60]
0x180031c50  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180031c55  nop
0x180031c56  mov     rax, [rbp+57h+var_58]
0x180031c5a  lea     rcx, [rbp+57h+var_58]
0x180031c5e  mov     rax, [rax+18h]
0x180031c62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c67  mov     rbx, rax
0x180031c6a  lea     rdx, aNewwinrehash; "NewWinREHash"
0x180031c71  lea     rcx, [rbp+57h+var_70]
0x180031c75  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180031c7a  nop
0x180031c7b  lea     rdx, aGeneralinfo; "GeneralInfo"
0x180031c82  lea     rcx, [rbp+57h+var_68]
0x180031c86  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180031c8b  nop
0x180031c8c  lea     r9, [rbp+57h+var_60]
0x180031c90  lea     r8, [rbp+57h+var_70]
0x180031c94  lea     rdx, [rbp+57h+var_68]
0x180031c98  mov     rcx, rbx
0x180031c9b  call    ?GetValue@IniFile@PushButtonReset@@QEBAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::IniFile::GetValue(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180031ca0  mov     edi, eax
0x180031ca2  mov     rcx, [rbp+57h+var_68]
0x180031ca6  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180031caa  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031caf  nop
0x180031cb0  mov     rcx, [rbp+57h+var_70]
0x180031cb4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180031cb8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180031cbd  test    edi, edi
0x180031cbf  jns     short loc_180031CF5
0x180031cc1  lea     rax, aFailedToGetNew; "Failed to get new WinRE hash from rollb"...
0x180031cc8  mov     [rsp+0B0h+var_88], rax
0x180031ccd  mov     [rsp+0B0h+var_90], 1F9h
0x180031cd5  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180031cdc  lea     r8, aWinreagentRoll_7; "WinREAgent::RollbackHelper::ResumeExecu"...
0x180031ce3  mov     edx, edi
  ... truncated ...
```
