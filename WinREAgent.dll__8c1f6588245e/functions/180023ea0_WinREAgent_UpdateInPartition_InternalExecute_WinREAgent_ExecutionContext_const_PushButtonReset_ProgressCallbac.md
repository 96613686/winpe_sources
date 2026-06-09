# WinREAgent::UpdateInPartition::InternalExecute(WinREAgent::ExecutionContext const *,PushButtonReset::ProgressCallback *)

- ea: `0x180023ea0`
- end: `0x1800240e7`
- name: `?InternalExecute@UpdateInPartition@WinREAgent@@MEAAJPEBVExecutionContext@2@PEAUProgressCallback@PushButtonReset@@@Z`
- size: `583`
- prototype: `__int64 __fastcall(WinREAgent::UpdateInPartition *__hidden this, const struct WinREAgent::ExecutionContext *, struct PushButtonReset::ProgressCallback *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task, installer_update`

## callees

- `0x180023ea0`
- `0x1800242d4`
- `0x18003207c`
- `0x18003717c`
- `0x180037344`
- `0x18004b35c`
- `0x18004c418`
- `0x18004d2ac`

## string_xrefs

- `0x180024001`: `Failed to delete [%s]`
- `0x1800240bc`: `Failed to delete [%s]`
- `0x180023f8b`: `Failed to copy [%s] to [%s]`
- `0x180023ecb`: `base\diagnosis\srt\winreagent\lib\operations\src\updateinpartition.cpp`
- `0x180023f97`: `base\diagnosis\srt\winreagent\lib\operations\src\updateinpartition.cpp`
- `0x180023fee`: `base\diagnosis\srt\winreagent\lib\operations\src\updateinpartition.cpp`
- `0x18002406a`: `base\diagnosis\srt\winreagent\lib\operations\src\updateinpartition.cpp`
- `0x1800240a9`: `base\diagnosis\srt\winreagent\lib\operations\src\updateinpartition.cpp`
- `0x180023f4f`: `UpdateInPartition: Current WinRE [%s] doesn't exist`
- `0x180023ed4`: `WinREAgent::UpdateInPartition::InternalExecute`
- `0x180023fa1`: `WinREAgent::UpdateInPartition::InternalExecute`
- `0x180023ffa`: `WinREAgent::UpdateInPartition::InternalExecute`
- `0x18002407c`: `WinREAgent::UpdateInPartition::InternalExecute`
- `0x1800240b5`: `WinREAgent::UpdateInPartition::InternalExecute`
- `0x180023efb`: `UpdateInPartition: Add checkpoint [%u]`
- `0x180024037`: `UpdateInPartition: Add checkpoint [%u]`
- `0x180023f20`: `Failed to set checkpoint for UpdateInPartition`
- `0x18002405c`: `Failed to set checkpoint for UpdateInPartition`
- `0x180023fcd`: `UpdateInPartition: Delete Current WinRE`
- `0x180023f5b`: `UpdateInPartition: Copy the updated WinRE`
- `0x18002408c`: `UpdateInPartition: Delete the updated WinRE`

## pseudocode

```c
__int64 __fastcall WinREAgent::UpdateInPartition::InternalExecute(
        WinREAgent::UpdateInPartition *this,
        const struct WinREAgent::ExecutionContext *a2,
        struct PushButtonReset::ProgressCallback *a3)
{
  int v4; // edi
  __int64 result; // rax
  _QWORD *v6; // rdi
  _QWORD *v7; // rsi
  int v8; // ebp
  int v9; // eax
  unsigned int v10; // esi
  int v11; // eax
  unsigned int v12; // ebx

  v4 = WinREAgent::UpdateInPartition::ValidateRequirement(this, a2);
  if ( v4 < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v4,
      "WinREAgent::UpdateInPartition::InternalExecute",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\updateinpartition.cpp",
      194,
      L"Failed to validate execution requirement");
    return (unsigned int)v4;
  }
  if ( *((_QWORD *)a2 + 56) )
  {
    PushButtonReset::Logging::Trace(0, L"UpdateInPartition: Add checkpoint [%u]", 4);
    v4 = WinREAgent::RollbackHelper::SetCheckpoint(*((_QWORD *)a2 + 56), 4);
    if ( v4 < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v4,
        "WinREAgent::UpdateInPartition::InternalExecute",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\updateinpartition.cpp",
        204,
        L"Failed to set checkpoint for UpdateInPartition");
      return (unsigned int)v4;
    }
  }
  v6 = (_QWORD *)((char *)a2 + 120);
  if ( (unsigned __int8)PushButtonReset::File::Exists((char *)a2 + 120) )
  {
    PushButtonReset::Logging::Trace(0, L"UpdateInPartition: Delete Current WinRE");
    v9 = PushButtonReset::File::Delete((char *)a2 + 120);
    v10 = v9;
    if ( v9 < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v9,
        "WinREAgent::UpdateInPartition::InternalExecute",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\updateinpartition.cpp",
        216,
        L"Failed to delete [%s]",
        *v6);
      return v10;
    }
  }
  else
  {
    PushButtonReset::Logging::Trace(0, L"UpdateInPartition: Current WinRE [%s] doesn't exist", *v6);
  }
  PushButtonReset::Logging::Trace(0, L"UpdateInPartition: Copy the updated WinRE");
  v7 = (_QWORD *)((char *)a2 + 280);
  v8 = PushButtonReset::File::Copy((_QWORD *)a2 + 35, (_QWORD *)a2 + 15, 0);
  if ( v8 >= 0 )
  {
    if ( *((_QWORD *)a2 + 56)
      && (PushButtonReset::Logging::Trace(0, L"UpdateInPartition: Add checkpoint [%u]", 5),
          v11 = WinREAgent::RollbackHelper::SetCheckpoint(*((_QWORD *)a2 + 56), 5),
          v12 = v11,
          v11 < 0) )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v11,
        "WinREAgent::UpdateInPartition::InternalExecute",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\updateinpartition.cpp",
        231,
        L"Failed to set checkpoint for UpdateInPartition");
      return v12;
    }
    else
    {
      PushButtonReset::Logging::Trace(0, L"UpdateInPartition: Delete the updated WinRE");
      result = PushButtonReset::File::Delete(v7);
      if ( (int)result < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          1,
          (unsigned int)result,
          "WinREAgent::UpdateInPartition::InternalExecute",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\updateinpartition.cpp",
          238,
          L"Failed to delete [%s]",
          *v7);
        return 0;
      }
    }
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v8,
      "WinREAgent::UpdateInPartition::InternalExecute",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\updateinpartition.cpp",
      224,
      L"Failed to copy [%s] to [%s]",
      *v7,
      *v6);
    return (unsigned int)v8;
  }
  return result;
}

```

## disassembly

```asm
0x180023ea0  push    rbx
0x180023ea2  push    rbp
0x180023ea3  push    rsi
0x180023ea4  push    rdi
0x180023ea5  sub     rsp, 48h
0x180023ea9  mov     rbx, rdx
0x180023eac  call    ?ValidateRequirement@UpdateInPartition@WinREAgent@@AEAAJPEBVExecutionContext@2@@Z; WinREAgent::UpdateInPartition::ValidateRequirement(WinREAgent::ExecutionContext const *)
0x180023eb1  mov     edi, eax
0x180023eb3  test    eax, eax
0x180023eb5  jns     short loc_180023EEC
0x180023eb7  lea     rax, aFailedToValida; "Failed to validate execution requiremen"...
0x180023ebe  mov     [rsp+68h+var_40], rax
0x180023ec3  mov     [rsp+68h+var_48], 0C2h
0x180023ecb  lea     r9, aBaseDiagnosisS_25; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180023ed2  mov     edx, edi
0x180023ed4  lea     r8, aWinreagentUpda; "WinREAgent::UpdateInPartition::Internal"...
0x180023edb  mov     ecx, 2
0x180023ee0  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180023ee5  mov     eax, edi
0x180023ee7  jmp     loc_1800240DE
0x180023eec  cmp     qword ptr [rbx+1C0h], 0
0x180023ef4  jz      short loc_180023F36
0x180023ef6  mov     edi, 4
0x180023efb  lea     rdx, aUpdateinpartit_7; "UpdateInPartition: Add checkpoint [%u]"
0x180023f02  mov     r8d, edi
0x180023f05  xor     ecx, ecx
0x180023f07  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180023f0c  mov     rcx, [rbx+1C0h]
0x180023f13  mov     edx, edi
0x180023f15  call    ?SetCheckpoint@RollbackHelper@WinREAgent@@QEAAJW4RollbackCheckpoint@2@@Z; WinREAgent::RollbackHelper::SetCheckpoint(WinREAgent::RollbackCheckpoint)
0x180023f1a  mov     edi, eax
0x180023f1c  test    eax, eax
0x180023f1e  jns     short loc_180023F36
0x180023f20  lea     rcx, aFailedToSetChe_1; "Failed to set checkpoint for UpdateInPa"...
0x180023f27  mov     [rsp+68h+var_40], rcx
0x180023f2c  mov     [rsp+68h+var_48], 0CCh
0x180023f34  jmp     short loc_180023ECB
0x180023f36  lea     rdi, [rbx+78h]
0x180023f3a  mov     rcx, rdi
0x180023f3d  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180023f42  xor     ecx, ecx
0x180023f44  test    al, al
0x180023f46  jnz     loc_180023FCD
0x180023f4c  mov     r8, [rdi]
0x180023f4f  lea     rdx, aUpdateinpartit_9; "UpdateInPartition: Current WinRE [%s] d"...
0x180023f56  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180023f5b  lea     rdx, aUpdateinpartit_4; "UpdateInPartition: Copy the updated Win"...
0x180023f62  xor     ecx, ecx
0x180023f64  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180023f69  lea     rsi, [rbx+118h]
0x180023f70  xor     r8d, r8d
0x180023f73  mov     rcx, rsi
0x180023f76  mov     rdx, rdi
0x180023f79  call    ?Copy@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAUProgressCallback@2@_N@Z; PushButtonReset::File::Copy(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::ProgressCallback *,bool)
0x180023f7e  mov     ebp, eax
0x180023f80  test    eax, eax
0x180023f82  jns     loc_180024028
0x180023f88  mov     rcx, [rdi]
0x180023f8b  lea     rax, aFailedToCopyST; "Failed to copy [%s] to [%s]"
0x180023f92  mov     [rsp+68h+var_30], rcx
0x180023f97  lea     r9, aBaseDiagnosisS_25; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180023f9e  mov     rcx, [rsi]
0x180023fa1  lea     r8, aWinreagentUpda; "WinREAgent::UpdateInPartition::Internal"...
0x180023fa8  mov     [rsp+68h+var_38], rcx
0x180023fad  mov     edx, ebp
0x180023faf  mov     [rsp+68h+var_40], rax
0x180023fb4  mov     ecx, 2
0x180023fb9  mov     [rsp+68h+var_48], 0E0h
0x180023fc1  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180023fc6  mov     eax, ebp
0x180023fc8  jmp     loc_1800240DE
0x180023fcd  lea     rdx, aUpdateinpartit_6; "UpdateInPartition: Delete Current WinRE"
0x180023fd4  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180023fd9  mov     rcx, rdi
0x180023fdc  call    ?Delete@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; PushButtonReset::File::Delete(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,int)
0x180023fe1  mov     esi, eax
0x180023fe3  test    eax, eax
0x180023fe5  jns     loc_180023F5B
0x180023feb  mov     rcx, [rdi]
0x180023fee  lea     r9, aBaseDiagnosisS_25; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180023ff5  mov     [rsp+68h+var_38], rcx
0x180023ffa  lea     r8, aWinreagentUpda; "WinREAgent::UpdateInPartition::Internal"...
0x180024001  lea     rcx, aFailedToDelete_19; "Failed to delete [%s]"
0x180024008  mov     edx, eax
0x18002400a  mov     [rsp+68h+var_40], rcx
0x18002400f  mov     ecx, 2
0x180024014  mov     [rsp+68h+var_48], 0D8h
0x18002401c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180024021  mov     eax, esi
0x180024023  jmp     loc_1800240DE
0x180024028  cmp     qword ptr [rbx+1C0h], 0
0x180024030  jz      short loc_18002408C
0x180024032  mov     edi, 5
0x180024037  lea     rdx, aUpdateinpartit_7; "UpdateInPartition: Add checkpoint [%u]"
0x18002403e  mov     r8d, edi
0x180024041  xor     ecx, ecx
0x180024043  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180024048  mov     rcx, [rbx+1C0h]
0x18002404f  mov     edx, edi
0x180024051  call    ?SetCheckpoint@RollbackHelper@WinREAgent@@QEAAJW4RollbackCheckpoint@2@@Z; WinREAgent::RollbackHelper::SetCheckpoint(WinREAgent::RollbackCheckpoint)
0x180024056  mov     ebx, eax
0x180024058  test    eax, eax
0x18002405a  jns     short loc_18002408C
0x18002405c  lea     rcx, aFailedToSetChe_1; "Failed to set checkpoint for UpdateInPa"...
0x180024063  mov     edx, eax
0x180024065  mov     [rsp+68h+var_40], rcx
0x18002406a  lea     r9, aBaseDiagnosisS_25; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180024071  lea     ecx, [rdi-3]
0x180024074  mov     [rsp+68h+var_48], 0E7h
0x18002407c  lea     r8, aWinreagentUpda; "WinREAgent::UpdateInPartition::Internal"...
0x180024083  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180024088  mov     eax, ebx
0x18002408a  jmp     short loc_1800240DE
0x18002408c  lea     rdx, aUpdateinpartit_2; "UpdateInPartition: Delete the updated W"...
0x180024093  xor     ecx, ecx
0x180024095  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002409a  mov     rcx, rsi
0x18002409d  call    ?Delete@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; PushButtonReset::File::Delete(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,int)
0x1800240a2  test    eax, eax
0x1800240a4  jns     short loc_1800240DE
0x1800240a6  mov     rcx, [rsi]
0x1800240a9  lea     r9, aBaseDiagnosisS_25; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800240b0  mov     [rsp+68h+var_38], rcx
0x1800240b5  lea     r8, aWinreagentUpda; "WinREAgent::UpdateInPartition::Internal"...
0x1800240bc  lea     rcx, aFailedToDelete_19; "Failed to delete [%s]"
0x1800240c3  mov     edx, eax
0x1800240c5  mov     [rsp+68h+var_40], rcx
0x1800240ca  mov     ecx, 1
0x1800240cf  mov     [rsp+68h+var_48], 0EEh
0x1800240d7  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800240dc  xor     eax, eax
0x1800240de  add     rsp, 48h
0x1800240e2  pop     rdi
0x1800240e3  pop     rsi
0x1800240e4  pop     rbp
0x1800240e5  pop     rbx
0x1800240e6  retn
```
