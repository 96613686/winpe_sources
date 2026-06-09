# WinREAgent::Executor::GetCreatedWinRE(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180008f2c`
- end: `0x1800091fb`
- name: `?GetCreatedWinRE@Executor@WinREAgent@@CAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `719`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180011118`

## callees

- `0x180004af8`
- `0x180005cc0`
- `0x1800074b8`
- `0x180008f2c`
- `0x18000d5c0`
- `0x18000d740`
- `0x18000d92c`
- `0x180011ef4`
- `0x18003717c`
- `0x180037344`
- `0x180037e48`
- `0x180038434`
- `0x18004d2ac`
- `0x18006f010`

## string_xrefs

- `0x180008f94`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180009028`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180009071`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x1800090da`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180009136`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180008f48`: `Get the path of the created WinRE from regsitry key`
- `0x180008f80`: `Failed to open System hive for current OS`
- `0x180008f9b`: `WinREAgent::Executor::GetCreatedWinRE`
- `0x18000902f`: `WinREAgent::Executor::GetCreatedWinRE`
- `0x180009078`: `WinREAgent::Executor::GetCreatedWinRE`
- `0x1800090e1`: `WinREAgent::Executor::GetCreatedWinRE`
- `0x18000913d`: `WinREAgent::Executor::GetCreatedWinRE`
- `0x180009014`: `Failed to get registry value for created WinRE path`
- `0x1800090c6`: `Failed to get WinRE path from registry value`
- `0x180009107`: `Created WinRE path [%s]`
- `0x180009122`: `WinRE path does not exist`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WinREAgent::Executor::GetCreatedWinRE(_QWORD *a1)
{
  __int64 v2; // rax
  __int64 v3; // rcx
  int v4; // ebx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, const wchar_t *, const wchar_t *, __int64); // rbx
  __int64 v7; // rax
  __int64 v8; // rax
  int String; // r14d
  ATL::CStringData *v10; // rcx
  ATL::CStringData *v11; // rsi
  int *v12; // rdi
  __int64 v13; // rbx
  _QWORD v15[2]; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v16[2]; // [rsp+40h] [rbp-10h] BYREF
  __int64 v17; // [rsp+88h] [rbp+38h] BYREF

  PushButtonReset::Logging::Trace(0, L"Get the path of the created WinRE from regsitry key");
  v16[1] = 0;
  v16[0] = &RAII::CAutoPbrDelete<PushButtonReset::RegKey *>::`vftable';
  v2 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v16);
  v4 = PushButtonReset::RegHive::OpenSystemHive(v3, v2);
  if ( v4 >= 0 )
  {
    v15[1] = 0;
    v15[0] = &RAII::CAutoPbrDelete<PushButtonReset::RegValue *>::`vftable';
    v5 = (*(__int64 (__fastcall **)(_QWORD *))(v16[0] + 24LL))(v16);
    v6 = *(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64))(*(_QWORD *)v5 + 80LL);
    v7 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v15);
    v4 = v6(v5, L"Setup\\Recovery", L"RecoveryOS", v7);
    if ( v4 >= 0 )
    {
      if ( *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD *))(v15[0] + 24LL))(v15) == 1 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v17);
        v8 = (*(__int64 (__fastcall **)(_QWORD *))(v15[0] + 24LL))(v15);
        String = PushButtonReset::RegValue::GetString(v8, &v17);
        if ( String >= 0 )
        {
          PushButtonReset::Logging::Trace(0, L"Created WinRE path [%s]", v17);
          if ( !(unsigned __int8)PushButtonReset::File::Exists(&v17) )
          {
            PushButtonReset::Logging::TraceErr(
              2,
              2147942402LL,
              "WinREAgent::Executor::GetCreatedWinRE",
              "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
              1360,
              L"WinRE path does not exist");
            ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
            v4 = -2147024894;
            goto LABEL_18;
          }
          v11 = (ATL::CStringData *)(v17 - 24);
          v12 = (int *)(*a1 - 24LL);
          if ( (int *)(v17 - 24) != v12 )
          {
            if ( v12[4] >= 0 && *(_QWORD *)v11 == *(_QWORD *)v12 )
            {
              v13 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v17 - 24);
              ATL::CStringData::Release((ATL::CStringData *)v12);
              *a1 = v13 + 24;
            }
            else
            {
              ATL::CSimpleStringT<unsigned short,0>::SetString(a1, v17, *(unsigned int *)(v17 - 16));
            }
          }
          v10 = v11;
        }
        else
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)String,
            "WinREAgent::Executor::GetCreatedWinRE",
            "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
            1355,
            L"Failed to get WinRE path from registry value");
          v10 = (ATL::CStringData *)(v17 - 24);
        }
        ATL::CStringData::Release(v10);
        v4 = String;
        goto LABEL_18;
      }
      PushButtonReset::Logging::TraceErr(
        2,
        2147942413LL,
        "WinREAgent::Executor::GetCreatedWinRE",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        1349,
        L"Target value is not a REG_SZ value");
      v4 = -2147024883;
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v4,
        "WinREAgent::Executor::GetCreatedWinRE",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        1344,
        L"Failed to get registry value for created WinRE path");
    }
LABEL_18:
    v15[0] = &RAII::CAutoPbrDelete<PushButtonReset::RegValue *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::RegValue *>::Release(v15);
    goto LABEL_19;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)v4,
    "WinREAgent::Executor::GetCreatedWinRE",
    "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
    1339,
    L"Failed to open System hive for current OS");
LABEL_19:
  v16[0] = &RAII::CAutoPbrDelete<PushButtonReset::RegKey *>::`vftable';
  RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(v16);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180008f2c  mov     [rsp-28h+arg_0], rbx
0x180008f31  mov     [rsp-28h+arg_10], rsi
0x180008f36  push    rbp
0x180008f37  push    rdi
0x180008f38  push    r13
0x180008f3a  push    r14
0x180008f3c  push    r15
0x180008f3e  mov     rbp, rsp
0x180008f41  sub     rsp, 50h
0x180008f45  mov     r15, rcx
0x180008f48  lea     rdx, aGetThePathOfTh; "Get the path of the created WinRE from "...
0x180008f4f  xor     ecx, ecx
0x180008f51  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180008f56  mov     [rbp+var_8], 0
0x180008f5e  lea     r13, ??_7?$CAutoPbrDelete@PEAVRegKey@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::RegKey *>::`vftable'
0x180008f65  mov     [rbp+var_10], r13
0x180008f69  lea     rcx, [rbp+var_10]
0x180008f6d  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180008f72  mov     rdx, rax
0x180008f75  call    ?OpenSystemHive@RegHive@PushButtonReset@@SAJW4SystemHive@2@PEAPEAVRegKey@2@@Z; PushButtonReset::RegHive::OpenSystemHive(PushButtonReset::SystemHive,PushButtonReset::RegKey * *)
0x180008f7a  mov     ebx, eax
0x180008f7c  test    eax, eax
0x180008f7e  jns     short loc_180008FB3
0x180008f80  lea     rax, aFailedToOpenSy_0; "Failed to open System hive for current "...
0x180008f87  mov     [rsp+50h+var_28], rax
0x180008f8c  mov     [rsp+50h+var_30], 53Bh
0x180008f94  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180008f9b  lea     r8, aWinreagentExec_7; "WinREAgent::Executor::GetCreatedWinRE"
0x180008fa2  mov     edx, ebx
0x180008fa4  mov     ecx, 2
0x180008fa9  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180008fae  jmp     loc_1800091D3
0x180008fb3  mov     [rbp+var_18], 0
0x180008fbb  lea     rax, ??_7?$CAutoPbrDelete@PEAVRegValue@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::RegValue *>::`vftable'
0x180008fc2  mov     [rbp+var_20], rax
0x180008fc6  mov     rax, [rbp+var_10]
0x180008fca  lea     rcx, [rbp+var_10]
0x180008fce  mov     rax, [rax+18h]
0x180008fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fd7  mov     rdi, rax
0x180008fda  mov     rcx, [rax]
0x180008fdd  mov     rbx, [rcx+50h]
0x180008fe1  mov     rcx, [rbp+var_20]
0x180008fe5  mov     rax, [rcx+8]
0x180008fe9  lea     rcx, [rbp+var_20]
0x180008fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ff2  mov     r9, rax
0x180008ff5  lea     r8, aRecoveryos; "RecoveryOS"
0x180008ffc  lea     rdx, aSetupRecovery; "Setup\\Recovery"
0x180009003  mov     rcx, rdi
0x180009006  mov     rax, rbx
0x180009009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000900e  mov     ebx, eax
0x180009010  test    eax, eax
0x180009012  jns     short loc_180009047
0x180009014  lea     rax, aFailedToGetReg; "Failed to get registry value for create"...
0x18000901b  mov     [rsp+50h+var_28], rax
0x180009020  mov     [rsp+50h+var_30], 540h
0x180009028  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000902f  lea     r8, aWinreagentExec_7; "WinREAgent::Executor::GetCreatedWinRE"
0x180009036  mov     edx, ebx
0x180009038  mov     ecx, 2
0x18000903d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180009042  jmp     loc_1800091BE
0x180009047  mov     rax, [rbp+var_20]
0x18000904b  lea     rcx, [rbp+var_20]
0x18000904f  mov     rax, [rax+18h]
0x180009053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009058  cmp     dword ptr [rax], 1
0x18000905b  jz      short loc_180009098
0x18000905d  lea     rax, aTargetValueIsN; "Target value is not a REG_SZ value"
0x180009064  mov     [rsp+50h+var_28], rax
0x180009069  mov     [rsp+50h+var_30], 545h
0x180009071  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180009078  lea     r8, aWinreagentExec_7; "WinREAgent::Executor::GetCreatedWinRE"
0x18000907f  mov     edx, 8007000Dh
0x180009084  mov     ecx, 2
0x180009089  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000908e  mov     ebx, 8007000Dh
0x180009093  jmp     loc_1800091BE
0x180009098  lea     rcx, [rbp+arg_8]
0x18000909c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800090a1  nop
0x1800090a2  mov     rax, [rbp+var_20]
0x1800090a6  lea     rcx, [rbp+var_20]
0x1800090aa  mov     rax, [rax+18h]
0x1800090ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090b3  lea     rdx, [rbp+arg_8]
0x1800090b7  mov     rcx, rax
0x1800090ba  call    ?GetString@RegValue@PushButtonReset@@QEAAJPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::RegValue::GetString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x1800090bf  mov     r14d, eax
0x1800090c2  test    eax, eax
0x1800090c4  jns     short loc_180009103
0x1800090c6  lea     rax, aFailedToGetWin_1; "Failed to get WinRE path from registry "...
0x1800090cd  mov     [rsp+50h+var_28], rax
0x1800090d2  mov     [rsp+50h+var_30], 54Bh
0x1800090da  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x1800090e1  lea     r8, aWinreagentExec_7; "WinREAgent::Executor::GetCreatedWinRE"
0x1800090e8  mov     edx, r14d
0x1800090eb  mov     ecx, 2
0x1800090f0  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800090f5  nop
0x1800090f6  mov     rcx, [rbp+arg_8]
0x1800090fa  add     rcx, 0FFFFFFFFFFFFFFE8h
0x1800090fe  jmp     loc_1800091B6
0x180009103  mov     r8, [rbp+arg_8]
0x180009107  lea     rdx, aCreatedWinrePa; "Created WinRE path [%s]"
0x18000910e  xor     ecx, ecx
0x180009110  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180009115  lea     rcx, [rbp+arg_8]
0x180009119  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000911e  test    al, al
0x180009120  jnz     short loc_180009168
0x180009122  lea     rax, aWinrePathDoesN; "WinRE path does not exist"
0x180009129  mov     [rsp+50h+var_28], rax
0x18000912e  mov     [rsp+50h+var_30], 550h
0x180009136  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000913d  lea     r8, aWinreagentExec_7; "WinREAgent::Executor::GetCreatedWinRE"
0x180009144  mov     edx, 80070002h
0x180009149  mov     ecx, 2
0x18000914e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180009153  nop
0x180009154  mov     rcx, [rbp+arg_8]
0x180009158  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000915c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180009161  mov     ebx, 80070002h
0x180009166  jmp     short loc_1800091BE
0x180009168  mov     rdx, [rbp+arg_8]
0x18000916c  lea     rsi, [rdx-18h]
0x180009170  mov     rdi, [r15]
0x180009173  add     rdi, 0FFFFFFFFFFFFFFE8h
0x180009177  cmp     rsi, rdi
0x18000917a  jz      short loc_1800091B3
0x18000917c  cmp     dword ptr [rdi+10h], 0
0x180009180  jl      short loc_1800091A6
0x180009182  mov     rax, [rdi]
0x180009185  cmp     [rsi], rax
0x180009188  jnz     short loc_1800091A6
0x18000918a  mov     rcx, rsi
0x18000918d  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180009192  mov     rbx, rax
0x180009195  mov     rcx, rdi; this
0x180009198  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000919d  lea     rax, [rbx+18h]
0x1800091a1  mov     [r15], rax
0x1800091a4  jmp     short loc_1800091B3
0x1800091a6  mov     r8d, [rdx-10h]
0x1800091aa  mov     rcx, r15
0x1800091ad  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800091b2  nop
0x1800091b3  mov     rcx, rsi; this
0x1800091b6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800091bb  mov     ebx, r14d
0x1800091be  lea     rax, ??_7?$CAutoPbrDelete@PEAVRegValue@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::RegValue *>::`vftable'
0x1800091c5  mov     [rbp+var_20], rax
0x1800091c9  lea     rcx, [rbp+var_20]
0x1800091cd  call    ?Release@?$CAutoPbrDelete@PEAVRegValue@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::RegValue *>::Release(void)
0x1800091d2  nop
0x1800091d3  mov     [rbp+var_10], r13
0x1800091d7  lea     rcx, [rbp+var_10]
0x1800091db  call    ?Release@?$CAutoPbrDelete@PEAVPrepareWinRE@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(void)
0x1800091e0  mov     eax, ebx
0x1800091e2  lea     r11, [rsp+50h+var_s0]
0x1800091e7  mov     rbx, [r11+30h]
0x1800091eb  mov     rsi, [r11+40h]
0x1800091ef  mov     rsp, r11
0x1800091f2  pop     r15
0x1800091f4  pop     r14
0x1800091f6  pop     r13
0x1800091f8  pop     rdi
0x1800091f9  pop     rbp
0x1800091fa  retn
```
