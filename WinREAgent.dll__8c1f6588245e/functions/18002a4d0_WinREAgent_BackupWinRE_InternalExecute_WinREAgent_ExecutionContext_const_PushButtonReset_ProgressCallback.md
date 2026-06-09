# WinREAgent::BackupWinRE::InternalExecute(WinREAgent::ExecutionContext const *,PushButtonReset::ProgressCallback *)

- ea: `0x18002a4d0`
- end: `0x18002a83a`
- name: `?InternalExecute@BackupWinRE@WinREAgent@@MEAAJPEBVExecutionContext@2@PEAUProgressCallback@PushButtonReset@@@Z`
- size: `874`
- prototype: `__int64 __fastcall(WinREAgent::BackupWinRE *__hidden this, const struct WinREAgent::ExecutionContext *, struct PushButtonReset::ProgressCallback *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800049a4`
- `0x18000d92c`
- `0x18002a4d0`
- `0x180032480`
- `0x18003717c`
- `0x180037344`
- `0x18004a898`
- `0x18004bb04`
- `0x18004d1fc`
- `0x18004d2ac`
- `0x18006c690`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002a657`
- `KERNEL32!GetLastError` at `0x18002a699`
- `KERNEL32!GetLastError` at `0x18002a657`
- `KERNEL32!GetLastError` at `0x18002a699`
- `ReAgent!WinReSetupBackupWinRE` at `0x18002a64d`
- `ReAgent!WinReSetupBackupWinRE` at `0x18002a64d`

## string_xrefs

- `0x18002a603`: `Failed to create backup directory [%s]`
- `0x18002a787`: `BackupWimPath`
- `0x18002a511`: `Does not have path to current wim`
- `0x18002a525`: `base\diagnosis\srt\winreagent\lib\operations\src\backupwinre.cpp`
- `0x18002a569`: `base\diagnosis\srt\winreagent\lib\operations\src\backupwinre.cpp`
- `0x18002a617`: `base\diagnosis\srt\winreagent\lib\operations\src\backupwinre.cpp`
- `0x18002a67f`: `base\diagnosis\srt\winreagent\lib\operations\src\backupwinre.cpp`
- `0x18002a742`: `base\diagnosis\srt\winreagent\lib\operations\src\backupwinre.cpp`
- `0x18002a7f7`: `base\diagnosis\srt\winreagent\lib\operations\src\backupwinre.cpp`
- `0x18002a52c`: `WinREAgent::BackupWinRE::InternalExecute`
- `0x18002a570`: `WinREAgent::BackupWinRE::InternalExecute`
- `0x18002a61e`: `WinREAgent::BackupWinRE::InternalExecute`
- `0x18002a686`: `WinREAgent::BackupWinRE::InternalExecute`
- `0x18002a749`: `WinREAgent::BackupWinRE::InternalExecute`
- `0x18002a7fe`: `WinREAgent::BackupWinRE::InternalExecute`
- `0x18002a5b8`: `BackupWinRE: Create backup directory`
- `0x18002a701`: `Failed to generate backup WinRE wim path`
- `0x18002a772`: `BackupWinRE: Save Backup WinRE wim path to Rollback info`
- `0x18002a7e3`: `Failed to save backup WinRE wim path into Rollback info`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
signed int __fastcall WinREAgent::BackupWinRE::InternalExecute(
        WinREAgent::BackupWinRE *this,
        const struct WinREAgent::ExecutionContext *a2,
        struct PushButtonReset::ProgressCallback *a3)
{
  signed int result; // eax
  _QWORD *v6; // rbx
  int v7; // esi
  signed int LastError; // eax
  int v9; // ebx
  __int64 v10; // rbx
  LPCWSTR v11; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v12; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v13[528]; // [rsp+50h] [rbp-B0h] BYREF

  if ( !*(_DWORD *)(*((_QWORD *)a2 + 15) - 16LL) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942487LL,
      "WinREAgent::BackupWinRE::InternalExecute",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\backupwinre.cpp",
      73,
      L"Does not have path to current wim");
    return -2147024809;
  }
  if ( !(unsigned __int8)PushButtonReset::File::Exists((char *)a2 + 120) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147943568LL,
      "WinREAgent::BackupWinRE::InternalExecute",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\backupwinre.cpp",
      79,
      L"Current WinRE doesn't exist");
    return -2147023728;
  }
  v6 = (_QWORD *)((char *)a2 + 248);
  PushButtonReset::Logging::Trace(0, L"BackupWinRE: Backup WinRE to [%s]", *((_QWORD *)a2 + 31));
  if ( (unsigned __int8)PushButtonReset::Directory::Exists((char *)a2 + 248)
    || (PushButtonReset::Logging::Trace(0, L"BackupWinRE: Create backup directory"),
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          (__int64)&v11,
          (__int64)&pszFormat),
        v7 = PushButtonReset::Directory::Create((_QWORD *)a2 + 31, 0, &v11),
        ATL::CStringData::Release((ATL::CStringData *)(v11 - 12)),
        v7 >= 0) )
  {
    if ( (unsigned int)WinReSetupBackupWinRE(0, *v6, 0, v13, 260) )
    {
      PushButtonReset::Logging::Trace(0, L"BackupWinRE: WinReSetupBackupWinRE succeed. WinRE location: [%s]", v13);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v11,
        (__int64)L"WinRE.wim");
      v9 = PushButtonReset::Path::Combine((char *)a2 + 248, &v11, (char *)this + 176);
      ATL::CStringData::Release((ATL::CStringData *)(v11 - 12));
      if ( v9 >= 0 )
      {
        if ( !(unsigned __int8)PushButtonReset::File::Exists((char *)this + 176) )
        {
          PushButtonReset::Logging::TraceErr(
            2,
            2147943568LL,
            "WinREAgent::BackupWinRE::InternalExecute",
            "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\backupwinre.cpp",
            107,
            L"Backup WinRE wim [%s] doesn't exist",
            *((_QWORD *)this + 22));
          return -2147023728;
        }
        if ( *((_QWORD *)a2 + 56) )
        {
          PushButtonReset::Logging::Trace(0, L"BackupWinRE: Save Backup WinRE wim path to Rollback info");
          v10 = *((_QWORD *)a2 + 56);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64)&v12,
            (__int64)L"BackupWimPath");
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64)&v11,
            (__int64)L"GeneralInfo");
          v9 = WinREAgent::RollbackHelper::WriteToConfig(v10, &v11, &v12, (char *)this + 176);
          ATL::CStringData::Release((ATL::CStringData *)(v11 - 12));
          ATL::CStringData::Release((ATL::CStringData *)(v12 - 24));
          if ( v9 < 0 )
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)v9,
              "WinREAgent::BackupWinRE::InternalExecute",
              "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\backupwinre.cpp",
              117,
              L"Failed to save backup WinRE wim path into Rollback info");
        }
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v9,
          "WinREAgent::BackupWinRE::InternalExecute",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\backupwinre.cpp",
          101,
          L"Failed to generate backup WinRE wim path");
      }
      return v9;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LastError,
        "WinREAgent::BackupWinRE::InternalExecute",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\backupwinre.cpp",
        94,
        L"WinReSetupBackupWinRE failed");
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v7,
      "WinREAgent::BackupWinRE::InternalExecute",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\backupwinre.cpp",
      87,
      L"Failed to create backup directory [%s]",
      *v6);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x18002a4d0  mov     [rsp-8+arg_10], rbx
0x18002a4d5  mov     [rsp-8+arg_18], rsi
0x18002a4da  push    rbp
0x18002a4db  push    rdi
0x18002a4dc  push    r14
0x18002a4de  lea     rbp, [rsp-170h]
0x18002a4e6  sub     rsp, 270h
0x18002a4ed  mov     rax, cs:__security_cookie
0x18002a4f4  xor     rax, rsp
0x18002a4f7  mov     [rbp+180h+var_20], rax
0x18002a4fe  mov     rdi, rdx
0x18002a501  mov     r14, rcx
0x18002a504  lea     rcx, [rdx+78h]
0x18002a508  mov     rax, [rcx]
0x18002a50b  cmp     dword ptr [rax-10h], 0
0x18002a50f  jnz     short loc_18002A54C
0x18002a511  lea     rax, aDoesNotHavePat_0; "Does not have path to current wim"
0x18002a518  mov     [rsp+280h+var_258], rax
0x18002a51d  mov     [rsp+280h+var_260], 49h ; 'I'
0x18002a525  lea     r9, aBaseDiagnosisS_17; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002a52c  lea     r8, aWinreagentBack; "WinREAgent::BackupWinRE::InternalExecut"...
0x18002a533  mov     edx, 80070057h
0x18002a538  mov     ecx, 2
0x18002a53d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002a542  mov     eax, 80070057h
0x18002a547  jmp     loc_18002A813
0x18002a54c  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002a551  test    al, al
0x18002a553  jnz     short loc_18002A590
0x18002a555  lea     rax, aCurrentWinreDo; "Current WinRE doesn't exist"
0x18002a55c  mov     [rsp+280h+var_258], rax
0x18002a561  mov     [rsp+280h+var_260], 4Fh ; 'O'
0x18002a569  lea     r9, aBaseDiagnosisS_17; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002a570  lea     r8, aWinreagentBack; "WinREAgent::BackupWinRE::InternalExecut"...
0x18002a577  mov     edx, 80070490h
0x18002a57c  mov     ecx, 2
0x18002a581  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002a586  mov     eax, 80070490h
0x18002a58b  jmp     loc_18002A813
0x18002a590  lea     rbx, [rdi+0F8h]
0x18002a597  mov     r8, [rbx]
0x18002a59a  lea     rdx, aBackupwinreBac; "BackupWinRE: Backup WinRE to [%s]"
0x18002a5a1  xor     ecx, ecx
0x18002a5a3  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002a5a8  mov     rcx, rbx
0x18002a5ab  call    ?Exists@Directory@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Directory::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002a5b0  test    al, al
0x18002a5b2  jnz     loc_18002A638
0x18002a5b8  lea     rdx, aBackupwinreCre; "BackupWinRE: Create backup directory"
0x18002a5bf  xor     ecx, ecx
0x18002a5c1  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002a5c6  lea     rdx, pszFormat
0x18002a5cd  lea     rcx, [rsp+280h+var_240]
0x18002a5d2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002a5d7  nop
0x18002a5d8  lea     r8, [rsp+280h+var_240]
0x18002a5dd  xor     edx, edx
0x18002a5df  mov     rcx, rbx
0x18002a5e2  call    ?Create@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N0@Z; PushButtonReset::Directory::Create(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002a5e7  mov     esi, eax
0x18002a5e9  mov     rcx, [rsp+280h+var_240]
0x18002a5ee  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002a5f2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002a5f7  test    esi, esi
0x18002a5f9  jns     short loc_18002A638
0x18002a5fb  mov     rcx, [rbx]
0x18002a5fe  mov     [rsp+280h+var_250], rcx
0x18002a603  lea     rax, aFailedToCreate_42; "Failed to create backup directory [%s]"
0x18002a60a  mov     [rsp+280h+var_258], rax
0x18002a60f  mov     [rsp+280h+var_260], 57h ; 'W'
0x18002a617  lea     r9, aBaseDiagnosisS_17; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002a61e  lea     r8, aWinreagentBack; "WinREAgent::BackupWinRE::InternalExecut"...
0x18002a625  mov     edx, esi
0x18002a627  mov     ecx, 2
0x18002a62c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002a631  mov     eax, esi
0x18002a633  jmp     loc_18002A813
0x18002a638  mov     [rsp+280h+var_260], 104h
0x18002a640  lea     r9, [rsp+280h+var_230]
0x18002a645  xor     r8d, r8d
0x18002a648  mov     rdx, [rbx]
0x18002a64b  xor     ecx, ecx
0x18002a64d  call    cs:__imp_WinReSetupBackupWinRE
0x18002a653  test    eax, eax
0x18002a655  jnz     short loc_18002A6B1
0x18002a657  call    cs:__imp_GetLastError
0x18002a65d  mov     ebx, 80070000h
0x18002a662  test    eax, eax
0x18002a664  jle     short loc_18002A66B
0x18002a666  movzx   eax, ax
0x18002a669  or      eax, ebx
0x18002a66b  lea     rcx, aWinresetupback; "WinReSetupBackupWinRE failed"
0x18002a672  mov     [rsp+280h+var_258], rcx
0x18002a677  mov     [rsp+280h+var_260], 5Eh ; '^'
0x18002a67f  lea     r9, aBaseDiagnosisS_17; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002a686  lea     r8, aWinreagentBack; "WinREAgent::BackupWinRE::InternalExecut"...
0x18002a68d  mov     edx, eax
0x18002a68f  mov     ecx, 2
0x18002a694  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002a699  call    cs:__imp_GetLastError
0x18002a69f  test    eax, eax
0x18002a6a1  jle     loc_18002A813
0x18002a6a7  movzx   eax, ax
0x18002a6aa  or      eax, ebx
0x18002a6ac  jmp     loc_18002A813
0x18002a6b1  lea     r8, [rsp+280h+var_230]
0x18002a6b6  lea     rdx, aBackupwinreWin; "BackupWinRE: WinReSetupBackupWinRE succ"...
0x18002a6bd  xor     ecx, ecx
0x18002a6bf  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002a6c4  lea     rsi, [r14+0B0h]
0x18002a6cb  lea     rdx, aWinreWim; "WinRE.wim"
0x18002a6d2  lea     rcx, [rsp+280h+var_240]
0x18002a6d7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002a6dc  nop
0x18002a6dd  mov     r8, rsi
0x18002a6e0  lea     rdx, [rsp+280h+var_240]
0x18002a6e5  mov     rcx, rbx
0x18002a6e8  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18002a6ed  mov     ebx, eax
0x18002a6ef  mov     rcx, [rsp+280h+var_240]
0x18002a6f4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002a6f8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002a6fd  test    ebx, ebx
0x18002a6ff  jns     short loc_18002A71A
0x18002a701  lea     rax, aFailedToGenera_0; "Failed to generate backup WinRE wim pat"...
0x18002a708  mov     [rsp+280h+var_258], rax
0x18002a70d  mov     [rsp+280h+var_260], 65h ; 'e'
0x18002a715  jmp     loc_18002A7F7
0x18002a71a  mov     rcx, rsi
0x18002a71d  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002a722  test    al, al
0x18002a724  jnz     short loc_18002A764
0x18002a726  mov     rax, [rsi]
0x18002a729  mov     [rsp+280h+var_250], rax
0x18002a72e  lea     rax, aBackupWinreWim; "Backup WinRE wim [%s] doesn't exist"
0x18002a735  mov     [rsp+280h+var_258], rax
0x18002a73a  mov     [rsp+280h+var_260], 6Bh ; 'k'
0x18002a742  lea     r9, aBaseDiagnosisS_17; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002a749  lea     r8, aWinreagentBack; "WinREAgent::BackupWinRE::InternalExecut"...
0x18002a750  mov     edx, 80070490h
0x18002a755  mov     ecx, 2
0x18002a75a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002a75f  jmp     loc_18002A586
0x18002a764  cmp     qword ptr [rdi+1C0h], 0
0x18002a76c  jz      loc_18002A811
0x18002a772  lea     rdx, aBackupwinreSav; "BackupWinRE: Save Backup WinRE wim path"...
0x18002a779  xor     ecx, ecx
0x18002a77b  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002a780  mov     rbx, [rdi+1C0h]
0x18002a787  lea     rdx, aBackupwimpath; "BackupWimPath"
0x18002a78e  lea     rcx, [rsp+280h+var_238]
0x18002a793  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002a798  nop
0x18002a799  lea     rdx, aGeneralinfo; "GeneralInfo"
0x18002a7a0  lea     rcx, [rsp+280h+var_240]
0x18002a7a5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002a7aa  nop
0x18002a7ab  mov     r9, rsi
0x18002a7ae  lea     r8, [rsp+280h+var_238]
0x18002a7b3  lea     rdx, [rsp+280h+var_240]
0x18002a7b8  mov     rcx, rbx
0x18002a7bb  call    ?WriteToConfig@RollbackHelper@WinREAgent@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00@Z; WinREAgent::RollbackHelper::WriteToConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002a7c0  mov     ebx, eax
0x18002a7c2  mov     rcx, [rsp+280h+var_240]
0x18002a7c7  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002a7cb  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002a7d0  nop
0x18002a7d1  mov     rcx, [rsp+280h+var_238]
0x18002a7d6  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002a7da  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002a7df  test    ebx, ebx
0x18002a7e1  jns     short loc_18002A811
0x18002a7e3  lea     rax, aFailedToSaveBa; "Failed to save backup WinRE wim path in"...
0x18002a7ea  mov     [rsp+280h+var_258], rax
0x18002a7ef  mov     [rsp+280h+var_260], 75h ; 'u'
0x18002a7f7  lea     r9, aBaseDiagnosisS_17; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002a7fe  lea     r8, aWinreagentBack; "WinREAgent::BackupWinRE::InternalExecut"...
0x18002a805  mov     edx, ebx
0x18002a807  mov     ecx, 2
0x18002a80c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002a811  mov     eax, ebx
0x18002a813  mov     rcx, [rbp+180h+var_20]
0x18002a81a  xor     rcx, rsp; StackCookie
0x18002a81d  call    __security_check_cookie
0x18002a822  lea     r11, [rsp+280h+var_10]
0x18002a82a  mov     rbx, [r11+30h]
0x18002a82e  mov     rsi, [r11+38h]
0x18002a832  mov     rsp, r11
0x18002a835  pop     r14
0x18002a837  pop     rdi
0x18002a838  pop     rbp
0x18002a839  retn
```
