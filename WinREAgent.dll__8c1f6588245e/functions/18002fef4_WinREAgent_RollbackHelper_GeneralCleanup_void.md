# WinREAgent::RollbackHelper::GeneralCleanup(void)

- ea: `0x18002fef4`
- end: `0x1800304ad`
- name: `?GeneralCleanup@RollbackHelper@WinREAgent@@AEAAJXZ`
- size: `1465`
- prototype: `__int64 __fastcall(WinREAgent::RollbackHelper *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x18002f978`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x180005cc0`
- `0x18000d92c`
- `0x18002fef4`
- `0x180031720`
- `0x18003717c`
- `0x180037344`
- `0x18004c418`
- `0x18004d2ac`
- `0x18005556c`
- `0x18005563c`
- `0x180055b2c`
- `0x18006c690`
- `0x18006f010`

## string_xrefs

- `0x180030170`: `CopiedWimPath`
- `0x1800301ef`: `CopiedWimPath`
- `0x180030302`: `ExportedWimPath`
- `0x180030381`: `ExportedWimPath`
- `0x18002ffcf`: `DestNewWimPath`
- `0x180030055`: `DestNewWimPath`
- `0x18002ff9c`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x1800300bc`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x18003011d`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x180030256`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x1800302af`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x1800303e8`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x180030441`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x18002ff1a`: `RollbackHelper: General cleanup based on rollback info`
- `0x18002ff39`: `RollbackHelper: InI file [%s] doesn't exist, skip cleanup`
- `0x18002ffa3`: `WinREAgent::RollbackHelper::GeneralCleanup`
- `0x1800300c3`: `WinREAgent::RollbackHelper::GeneralCleanup`
- `0x180030124`: `WinREAgent::RollbackHelper::GeneralCleanup`
- `0x18003025d`: `WinREAgent::RollbackHelper::GeneralCleanup`
- `0x1800302b6`: `WinREAgent::RollbackHelper::GeneralCleanup`
- `0x1800303ef`: `WinREAgent::RollbackHelper::GeneralCleanup`
- `0x180030448`: `WinREAgent::RollbackHelper::GeneralCleanup`
- `0x180030029`: `RollbackHelper: Delete copied new WinRE wim`
- `0x1800300a8`: `Failed to get new WinRE wim destination path from rollback info`
- `0x180030109`: `Failed to delete copied new winRE wim [%s]`
- `0x180030144`: `RollbackHelper: Copied new WinRE wim [%s] doesn't exist`
- `0x1800301c3`: `RollbackHelper: Delete copied WinRE wim`
- `0x180030242`: `Failed to get copied WinRE wim path from rollback info`
- `0x18003029b`: `Failed to delete copied winRE wim [%s]`
- `0x1800302d6`: `RollbackHelper: Copied WinRE wim [%s] doesn't exist`
- `0x180030355`: `RollbackHelper: Delete exported WinRE wim`
- `0x1800303d4`: `Failed to get exported WinRE wim path from rollback info`
- `0x18003042d`: `Failed to delete exported winRE wim [%s]`
- `0x180030464`: `RollbackHelper: Exported WinRE wim [%s] doesn't exist`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall WinREAgent::RollbackHelper::GeneralCleanup(WinREAgent::RollbackHelper *this)
{
  __int64 v3; // rax
  int Value; // edi
  __int64 v5; // rbx
  __int64 v6; // rbx
  ATL::CStringData *v7; // rcx
  __int64 v8; // rbx
  __int64 v9; // rbx
  __int64 v10; // rbx
  __int64 v11; // rbx
  __int64 v12; // rbx
  __int64 v13; // [rsp+40h] [rbp-30h] BYREF
  __int64 v14; // [rsp+48h] [rbp-28h] BYREF
  __int64 v15; // [rsp+50h] [rbp-20h] BYREF
  _QWORD v16[2]; // [rsp+58h] [rbp-18h] BYREF

  PushButtonReset::Logging::Trace(0, L"RollbackHelper: General cleanup based on rollback info");
  if ( !(unsigned __int8)PushButtonReset::File::Exists((char *)this + 8) )
  {
    PushButtonReset::Logging::Trace(
      0,
      L"RollbackHelper: InI file [%s] doesn't exist, skip cleanup",
      *((_QWORD *)this + 1));
    return 1;
  }
  v16[1] = 0;
  v16[0] = &RAII::CAutoPbrDelete<PushButtonReset::IniFile *>::`vftable';
  v3 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v16);
  Value = PushButtonReset::IniFile::Load((char *)this + 8, v3);
  if ( Value >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD *))(v16[0] + 24LL))(v16);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v14,
      (__int64)L"DestNewWimPath");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v13,
      (__int64)L"GeneralInfo");
    LOBYTE(v5) = PushButtonReset::IniFile::HasKey(v5, &v13, &v14);
    ATL::CStringData::Release((ATL::CStringData *)(v13 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v14 - 24));
    if ( (_BYTE)v5 )
    {
      PushButtonReset::Logging::Trace(0, L"RollbackHelper: Delete copied new WinRE wim");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v13);
      v6 = (*(__int64 (__fastcall **)(_QWORD *))(v16[0] + 24LL))(v16);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v15,
        (__int64)L"DestNewWimPath");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v14,
        (__int64)L"GeneralInfo");
      Value = PushButtonReset::IniFile::GetValue(v6, &v14, &v15, &v13);
      ATL::CStringData::Release((ATL::CStringData *)(v14 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
      if ( Value < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Value,
          "WinREAgent::RollbackHelper::GeneralCleanup",
          "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
          354,
          L"Failed to get new WinRE wim destination path from rollback info");
LABEL_8:
        v7 = (ATL::CStringData *)(v13 - 24);
LABEL_30:
        ATL::CStringData::Release(v7);
        goto LABEL_31;
      }
      if ( (unsigned __int8)PushButtonReset::File::Exists(&v13) )
      {
        Value = PushButtonReset::File::Delete(&v13);
        v8 = v13;
        if ( Value < 0 )
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)Value,
            "WinREAgent::RollbackHelper::GeneralCleanup",
            "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
            359,
            L"Failed to delete copied new winRE wim [%s]",
            v13);
          goto LABEL_29;
        }
      }
      else
      {
        v8 = v13;
        PushButtonReset::Logging::Trace(0, L"RollbackHelper: Copied new WinRE wim [%s] doesn't exist", v13);
      }
      ATL::CStringData::Release((ATL::CStringData *)(v8 - 24));
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD *))(v16[0] + 24LL))(v16);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v14,
      (__int64)L"CopiedWimPath");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v15,
      (__int64)L"GeneralInfo");
    LOBYTE(v9) = PushButtonReset::IniFile::HasKey(v9, &v15, &v14);
    ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v14 - 24));
    if ( (_BYTE)v9 )
    {
      PushButtonReset::Logging::Trace(0, L"RollbackHelper: Delete copied WinRE wim");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v13);
      v10 = (*(__int64 (__fastcall **)(_QWORD *))(v16[0] + 24LL))(v16);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v14,
        (__int64)L"CopiedWimPath");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64)&v15,
        (__int64)L"GeneralInfo");
      Value = PushButtonReset::IniFile::GetValue(v10, &v15, &v14, &v13);
      ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v14 - 24));
      if ( Value < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Value,
          "WinREAgent::RollbackHelper::GeneralCleanup",
          "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
          373,
          L"Failed to get copied WinRE wim path from rollback info");
        goto LABEL_8;
      }
      if ( (unsigned __int8)PushButtonReset::File::Exists(&v13) )
      {
        Value = PushButtonReset::File::Delete(&v13);
        v8 = v13;
        if ( Value < 0 )
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)Value,
            "WinREAgent::RollbackHelper::GeneralCleanup",
            "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
            378,
            L"Failed to delete copied winRE wim [%s]",
            v13);
          goto LABEL_29;
        }
      }
      else
      {
        v8 = v13;
        PushButtonReset::Logging::Trace(0, L"RollbackHelper: Copied WinRE wim [%s] doesn't exist", v13);
      }
      ATL::CStringData::Release((ATL::CStringData *)(v8 - 24));
    }
    v11 = (*(__int64 (__fastcall **)(_QWORD *))(v16[0] + 24LL))(v16);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v14,
      (__int64)L"ExportedWimPath");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v15,
      (__int64)L"GeneralInfo");
    LOBYTE(v11) = PushButtonReset::IniFile::HasKey(v11, &v15, &v14);
    ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v14 - 24));
    if ( !(_BYTE)v11 )
      goto LABEL_31;
    PushButtonReset::Logging::Trace(0, L"RollbackHelper: Delete exported WinRE wim");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v13);
    v12 = (*(__int64 (__fastcall **)(_QWORD *))(v16[0] + 24LL))(v16);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v14,
      (__int64)L"ExportedWimPath");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v15,
      (__int64)L"GeneralInfo");
    Value = PushButtonReset::IniFile::GetValue(v12, &v15, &v14, &v13);
    ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v14 - 24));
    if ( Value < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Value,
        "WinREAgent::RollbackHelper::GeneralCleanup",
        "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
        392,
        L"Failed to get exported WinRE wim path from rollback info");
      goto LABEL_8;
    }
    if ( (unsigned __int8)PushButtonReset::File::Exists(&v13) )
    {
      Value = PushButtonReset::File::Delete(&v13);
      v8 = v13;
      if ( Value < 0 )
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Value,
          "WinREAgent::RollbackHelper::GeneralCleanup",
          "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
          397,
          L"Failed to delete exported winRE wim [%s]",
          v13);
    }
    else
    {
      v8 = v13;
      PushButtonReset::Logging::Trace(0, L"RollbackHelper: Exported WinRE wim [%s] doesn't exist", v13);
    }
LABEL_29:
    v7 = (ATL::CStringData *)(v8 - 24);
    goto LABEL_30;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)Value,
    "WinREAgent::RollbackHelper::GeneralCleanup",
    "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
    346,
    L"Failed to load INI file [%s]",
    *((_QWORD *)this + 1));
LABEL_31:
  v16[0] = &RAII::CAutoPbrDelete<PushButtonReset::IniFile *>::`vftable';
  RAII::CAutoPbrDelete<PushButtonReset::IniFile *>::Release(v16);
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x18002fef4  mov     [rsp-18h+arg_8], rbx
0x18002fef9  mov     [rsp-18h+arg_10], rsi
0x18002fefe  push    rbp
0x18002feff  push    rdi
0x18002ff00  push    r14
0x18002ff02  mov     rbp, rsp
0x18002ff05  sub     rsp, 70h
0x18002ff09  mov     rax, cs:__security_cookie
0x18002ff10  xor     rax, rsp
0x18002ff13  mov     [rbp+var_8], rax
0x18002ff17  mov     rbx, rcx
0x18002ff1a  lea     rdx, aRollbackhelper_10; "RollbackHelper: General cleanup based o"...
0x18002ff21  xor     ecx, ecx
0x18002ff23  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002ff28  lea     rcx, [rbx+8]
0x18002ff2c  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002ff31  test    al, al
0x18002ff33  jnz     short loc_18002FF51
0x18002ff35  mov     r8, [rbx+8]
0x18002ff39  lea     rdx, aRollbackhelper_0; "RollbackHelper: InI file [%s] doesn't e"...
0x18002ff40  xor     ecx, ecx
0x18002ff42  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002ff47  mov     eax, 1
0x18002ff4c  jmp     loc_18003048C
0x18002ff51  mov     [rbp+var_10], 0
0x18002ff59  lea     rsi, ??_7?$CAutoPbrDelete@PEAVIniFile@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::IniFile *>::`vftable'
0x18002ff60  mov     [rbp+var_18], rsi
0x18002ff64  lea     rcx, [rbp+var_18]
0x18002ff68  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18002ff6d  mov     rdx, rax
0x18002ff70  lea     rcx, [rbx+8]
0x18002ff74  call    ?Load@IniFile@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::IniFile::Load(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::IniFile * *)
0x18002ff79  mov     edi, eax
0x18002ff7b  test    eax, eax
0x18002ff7d  jns     short loc_18002FFBB
0x18002ff7f  mov     rcx, [rbx+8]
0x18002ff83  mov     [rsp+70h+var_40], rcx
0x18002ff88  lea     rax, aFailedToLoadIn_0; "Failed to load INI file [%s]"
0x18002ff8f  mov     [rsp+70h+var_48], rax
0x18002ff94  mov     [rsp+70h+var_50], 15Ah
0x18002ff9c  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002ffa3  lea     r8, aWinreagentRoll_3; "WinREAgent::RollbackHelper::GeneralClea"...
0x18002ffaa  mov     edx, edi
0x18002ffac  mov     ecx, 2
0x18002ffb1  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002ffb6  jmp     loc_18003047D
0x18002ffbb  mov     rax, [rbp+var_18]
0x18002ffbf  lea     rcx, [rbp+var_18]
0x18002ffc3  mov     rax, [rax+18h]
0x18002ffc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffcc  mov     rbx, rax
0x18002ffcf  lea     rdx, aDestnewwimpath; "DestNewWimPath"
0x18002ffd6  lea     rcx, [rbp+var_28]
0x18002ffda  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002ffdf  nop
0x18002ffe0  lea     r14, aGeneralinfo; "GeneralInfo"
0x18002ffe7  mov     rdx, r14
0x18002ffea  lea     rcx, [rbp+var_30]
0x18002ffee  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002fff3  nop
0x18002fff4  lea     r8, [rbp+var_28]
0x18002fff8  lea     rdx, [rbp+var_30]
0x18002fffc  mov     rcx, rbx
0x18002ffff  call    ?HasKey@IniFile@PushButtonReset@@QEBA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; PushButtonReset::IniFile::HasKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180030004  mov     bl, al
0x180030006  mov     rcx, [rbp+var_30]
0x18003000a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003000e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030013  nop
0x180030014  mov     rcx, [rbp+var_28]
0x180030018  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003001c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030021  test    bl, bl
0x180030023  jz      loc_18003015C
0x180030029  lea     rdx, aRollbackhelper_6; "RollbackHelper: Delete copied new WinRE"...
0x180030030  xor     ecx, ecx
0x180030032  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180030037  lea     rcx, [rbp+var_30]
0x18003003b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180030040  nop
0x180030041  mov     rax, [rbp+var_18]
0x180030045  lea     rcx, [rbp+var_18]
0x180030049  mov     rax, [rax+18h]
0x18003004d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030052  mov     rbx, rax
0x180030055  lea     rdx, aDestnewwimpath; "DestNewWimPath"
0x18003005c  lea     rcx, [rbp+var_20]
0x180030060  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180030065  nop
0x180030066  mov     rdx, r14
0x180030069  lea     rcx, [rbp+var_28]
0x18003006d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180030072  nop
0x180030073  lea     r9, [rbp+var_30]
0x180030077  lea     r8, [rbp+var_20]
0x18003007b  lea     rdx, [rbp+var_28]
0x18003007f  mov     rcx, rbx
0x180030082  call    ?GetValue@IniFile@PushButtonReset@@QEBAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::IniFile::GetValue(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180030087  mov     edi, eax
0x180030089  mov     rcx, [rbp+var_28]
0x18003008d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030091  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030096  nop
0x180030097  mov     rcx, [rbp+var_20]
0x18003009b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003009f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800300a4  test    edi, edi
0x1800300a6  jns     short loc_1800300E4
0x1800300a8  lea     rax, aFailedToGetNew_0; "Failed to get new WinRE wim destination"...
0x1800300af  mov     [rsp+70h+var_48], rax
0x1800300b4  mov     [rsp+70h+var_50], 162h
0x1800300bc  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800300c3  lea     r8, aWinreagentRoll_3; "WinREAgent::RollbackHelper::GeneralClea"...
0x1800300ca  mov     edx, edi
0x1800300cc  mov     ecx, 2
0x1800300d1  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800300d6  nop
0x1800300d7  mov     rcx, [rbp+var_30]
0x1800300db  add     rcx, 0FFFFFFFFFFFFFFE8h
0x1800300df  jmp     loc_180030477
0x1800300e4  lea     rcx, [rbp+var_30]
0x1800300e8  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800300ed  test    al, al
0x1800300ef  jz      short loc_18003013D
0x1800300f1  lea     rcx, [rbp+var_30]
0x1800300f5  call    ?Delete@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; PushButtonReset::File::Delete(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,int)
0x1800300fa  mov     edi, eax
0x1800300fc  mov     rbx, [rbp+var_30]
0x180030100  test    eax, eax
0x180030102  jns     short loc_180030153
0x180030104  mov     [rsp+70h+var_40], rbx
0x180030109  lea     rax, aFailedToDelete_12; "Failed to delete copied new winRE wim ["...
0x180030110  mov     [rsp+70h+var_48], rax
0x180030115  mov     [rsp+70h+var_50], 167h
0x18003011d  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180030124  lea     r8, aWinreagentRoll_3; "WinREAgent::RollbackHelper::GeneralClea"...
0x18003012b  mov     edx, edi
0x18003012d  mov     ecx, 2
0x180030132  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180030137  nop
0x180030138  jmp     loc_180030473
0x18003013d  mov     rbx, [rbp+var_30]
0x180030141  mov     r8, rbx
0x180030144  lea     rdx, aRollbackhelper_16; "RollbackHelper: Copied new WinRE wim [%"...
0x18003014b  xor     ecx, ecx
0x18003014d  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180030152  nop
0x180030153  lea     rcx, [rbx-18h]; this
0x180030157  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003015c  mov     rax, [rbp+var_18]
0x180030160  lea     rcx, [rbp+var_18]
0x180030164  mov     rax, [rax+18h]
0x180030168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003016d  mov     rbx, rax
0x180030170  lea     rdx, aCopiedwimpath; "CopiedWimPath"
0x180030177  lea     rcx, [rbp+var_28]
0x18003017b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180030180  nop
0x180030181  mov     rdx, r14
0x180030184  lea     rcx, [rbp+var_20]
0x180030188  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18003018d  nop
0x18003018e  lea     r8, [rbp+var_28]
0x180030192  lea     rdx, [rbp+var_20]
0x180030196  mov     rcx, rbx
0x180030199  call    ?HasKey@IniFile@PushButtonReset@@QEBA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; PushButtonReset::IniFile::HasKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18003019e  mov     bl, al
0x1800301a0  mov     rcx, [rbp+var_20]
0x1800301a4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800301a8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800301ad  nop
0x1800301ae  mov     rcx, [rbp+var_28]
0x1800301b2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800301b6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800301bb  test    bl, bl
0x1800301bd  jz      loc_1800302EE
0x1800301c3  lea     rdx, aRollbackhelper_14; "RollbackHelper: Delete copied WinRE wim"
0x1800301ca  xor     ecx, ecx
0x1800301cc  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800301d1  lea     rcx, [rbp+var_30]
0x1800301d5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800301da  nop
0x1800301db  mov     rax, [rbp+var_18]
0x1800301df  lea     rcx, [rbp+var_18]
0x1800301e3  mov     rax, [rax+18h]
0x1800301e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301ec  mov     rbx, rax
0x1800301ef  lea     rdx, aCopiedwimpath; "CopiedWimPath"
0x1800301f6  lea     rcx, [rbp+var_28]
0x1800301fa  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800301ff  nop
0x180030200  mov     rdx, r14
0x180030203  lea     rcx, [rbp+var_20]
0x180030207  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18003020c  nop
0x18003020d  lea     r9, [rbp+var_30]
0x180030211  lea     r8, [rbp+var_28]
0x180030215  lea     rdx, [rbp+var_20]
0x180030219  mov     rcx, rbx
0x18003021c  call    ?GetValue@IniFile@PushButtonReset@@QEBAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::IniFile::GetValue(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180030221  mov     edi, eax
0x180030223  mov     rcx, [rbp+var_20]
0x180030227  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003022b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030230  nop
0x180030231  mov     rcx, [rbp+var_28]
0x180030235  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030239  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003023e  test    edi, edi
0x180030240  jns     short loc_180030276
0x180030242  lea     rax, aFailedToGetCop; "Failed to get copied WinRE wim path fro"...
0x180030249  mov     [rsp+70h+var_48], rax
0x18003024e  mov     [rsp+70h+var_50], 175h
0x180030256  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18003025d  lea     r8, aWinreagentRoll_3; "WinREAgent::RollbackHelper::GeneralClea"...
0x180030264  mov     edx, edi
0x180030266  mov     ecx, 2
0x18003026b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180030270  nop
0x180030271  jmp     loc_1800300D7
0x180030276  lea     rcx, [rbp+var_30]
0x18003027a  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18003027f  test    al, al
0x180030281  jz      short loc_1800302CF
0x180030283  lea     rcx, [rbp+var_30]
0x180030287  call    ?Delete@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; PushButtonReset::File::Delete(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,int)
0x18003028c  mov     edi, eax
0x18003028e  mov     rbx, [rbp+var_30]
0x180030292  test    eax, eax
0x180030294  jns     short loc_1800302E5
0x180030296  mov     [rsp+70h+var_40], rbx
0x18003029b  lea     rax, aFailedToDelete_2; "Failed to delete copied winRE wim [%s]"
0x1800302a2  mov     [rsp+70h+var_48], rax
0x1800302a7  mov     [rsp+70h+var_50], 17Ah
0x1800302af  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800302b6  lea     r8, aWinreagentRoll_3; "WinREAgent::RollbackHelper::GeneralClea"...
0x1800302bd  mov     edx, edi
0x1800302bf  mov     ecx, 2
0x1800302c4  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800302c9  nop
0x1800302ca  jmp     loc_180030473
0x1800302cf  mov     rbx, [rbp+var_30]
0x1800302d3  mov     r8, rbx
0x1800302d6  lea     rdx, aRollbackhelper_4; "RollbackHelper: Copied WinRE wim [%s] d"...
0x1800302dd  xor     ecx, ecx
0x1800302df  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800302e4  nop
0x1800302e5  lea     rcx, [rbx-18h]; this
0x1800302e9  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800302ee  mov     rax, [rbp+var_18]
0x1800302f2  lea     rcx, [rbp+var_18]
0x1800302f6  mov     rax, [rax+18h]
0x1800302fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302ff  mov     rbx, rax
0x180030302  lea     rdx, aExportedwimpat; "ExportedWimPath"
0x180030309  lea     rcx, [rbp+var_28]
0x18003030d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180030312  nop
0x180030313  mov     rdx, r14
0x180030316  lea     rcx, [rbp+var_20]
0x18003031a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18003031f  nop
0x180030320  lea     r8, [rbp+var_28]
0x180030324  lea     rdx, [rbp+var_20]
0x180030328  mov     rcx, rbx
0x18003032b  call    ?HasKey@IniFile@PushButtonReset@@QEBA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; PushButtonReset::IniFile::HasKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180030330  mov     bl, al
0x180030332  mov     rcx, [rbp+var_20]
0x180030336  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003033a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003033f  nop
0x180030340  mov     rcx, [rbp+var_28]
0x180030344  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030348  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003034d  test    bl, bl
0x18003034f  jz      loc_18003047D
0x180030355  lea     rdx, aRollbackhelper_11; "RollbackHelper: Delete exported WinRE w"...
0x18003035c  xor     ecx, ecx
0x18003035e  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180030363  lea     rcx, [rbp+var_30]
0x180030367  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18003036c  nop
0x18003036d  mov     rax, [rbp+var_18]
0x180030371  lea     rcx, [rbp+var_18]
0x180030375  mov     rax, [rax+18h]
0x180030379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003037e  mov     rbx, rax
0x180030381  lea     rdx, aExportedwimpat; "ExportedWimPath"
0x180030388  lea     rcx, [rbp+var_28]
0x18003038c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180030391  nop
0x180030392  mov     rdx, r14
0x180030395  lea     rcx, [rbp+var_20]
0x180030399  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18003039e  nop
0x18003039f  lea     r9, [rbp+var_30]
0x1800303a3  lea     r8, [rbp+var_28]
0x1800303a7  lea     rdx, [rbp+var_20]
0x1800303ab  mov     rcx, rbx
0x1800303ae  call    ?GetValue@IniFile@PushButtonReset@@QEBAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::IniFile::GetValue(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
  ... truncated ...
```
