# WinREAgent::UpdateInPartition::Undo(WinREAgent::ExecutionContext *)

- ea: `0x1800240fc`
- end: `0x1800242cd`
- name: `?Undo@UpdateInPartition@WinREAgent@@SAJPEAVExecutionContext@2@@Z`
- size: `465`
- prototype: `__int64 __fastcall(struct WinREAgent::ExecutionContext *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x18002f978`

## callees

- `0x1800240fc`
- `0x18003717c`
- `0x180037344`
- `0x18004b35c`
- `0x18004c418`
- `0x18004d2ac`

## string_xrefs

- `0x180024207`: `Failed to delete [%s]`
- `0x180024270`: `Failed to copy [%s] to [%s]`
- `0x180024140`: `base\diagnosis\srt\winreagent\lib\operations\src\updateinpartition.cpp`
- `0x180024176`: `base\diagnosis\srt\winreagent\lib\operations\src\updateinpartition.cpp`
- `0x180024213`: `base\diagnosis\srt\winreagent\lib\operations\src\updateinpartition.cpp`
- `0x18002427c`: `base\diagnosis\srt\winreagent\lib\operations\src\updateinpartition.cpp`
- `0x18002410e`: `UpdateInPartition::Undo Start`
- `0x18002412c`: `No backup WinRE wim path`
- `0x18002414c`: `WinREAgent::UpdateInPartition::Undo`
- `0x180024182`: `WinREAgent::UpdateInPartition::Undo`
- `0x18002421f`: `WinREAgent::UpdateInPartition::Undo`
- `0x180024286`: `WinREAgent::UpdateInPartition::Undo`
- `0x1800241c3`: `No WinRE wim path`
- `0x1800241ea`: `Delete new WinRE`
- `0x18002424b`: `Copy Backup WinRE`
- `0x1800242ad`: `UpdateInPartition::Undo Completed`

## pseudocode

```c
__int64 __fastcall WinREAgent::UpdateInPartition::Undo(struct WinREAgent::ExecutionContext *a1)
{
  _QWORD *v2; // rdi
  _QWORD *v4; // rbx
  int v5; // esi

  PushButtonReset::Logging::Trace(0, L"UpdateInPartition::Undo Start");
  v2 = (_QWORD *)((char *)a1 + 312);
  if ( !*(_DWORD *)(*((_QWORD *)a1 + 39) - 16LL) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147500037LL,
      "WinREAgent::UpdateInPartition::Undo",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\updateinpartition.cpp",
      271,
      L"No backup WinRE wim path");
    return 2147500037LL;
  }
  if ( !(unsigned __int8)PushButtonReset::File::Exists((char *)a1 + 312) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147943568LL,
      "WinREAgent::UpdateInPartition::Undo",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\updateinpartition.cpp",
      278,
      L"Backup WinRE [%s] doesn't exist",
      *v2);
    return 2147943568LL;
  }
  v4 = (_QWORD *)((char *)a1 + 120);
  if ( !*(_DWORD *)(*v4 - 16LL) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147500037LL,
      "WinREAgent::UpdateInPartition::Undo",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\updateinpartition.cpp",
      284,
      L"No WinRE wim path");
    return 2147500037LL;
  }
  if ( !(unsigned __int8)PushButtonReset::File::Exists(v4) )
  {
    PushButtonReset::Logging::Trace(0, L"WinRE [%s] doesn't exist", *v4);
LABEL_12:
    PushButtonReset::Logging::Trace(0, L"Copy Backup WinRE");
    v5 = PushButtonReset::File::Copy(v2, v4, 0);
    if ( v5 >= 0 )
      PushButtonReset::Logging::Trace(0, L"UpdateInPartition::Undo Completed");
    else
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v5,
        "WinREAgent::UpdateInPartition::Undo",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\updateinpartition.cpp",
        304,
        L"Failed to copy [%s] to [%s]",
        *v2,
        *v4);
    return (unsigned int)v5;
  }
  PushButtonReset::Logging::Trace(0, L"Delete new WinRE");
  v5 = PushButtonReset::File::Delete(v4);
  if ( v5 >= 0 )
    goto LABEL_12;
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)v5,
    "WinREAgent::UpdateInPartition::Undo",
    "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\updateinpartition.cpp",
    292,
    L"Failed to delete [%s]",
    *v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800240fc  mov     [rsp+arg_0], rbx
0x180024101  mov     [rsp+arg_8], rsi
0x180024106  push    rdi
0x180024107  sub     rsp, 40h
0x18002410b  mov     rbx, rcx
0x18002410e  lea     rdx, aUpdateinpartit_5; "UpdateInPartition::Undo Start"
0x180024115  xor     ecx, ecx
0x180024117  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002411c  lea     rdi, [rbx+138h]
0x180024123  mov     rax, [rdi]
0x180024126  cmp     dword ptr [rax-10h], 0
0x18002412a  jnz     short loc_180024167
0x18002412c  lea     rax, aNoBackupWinreW; "No backup WinRE wim path"
0x180024133  mov     [rsp+48h+var_20], rax
0x180024138  mov     [rsp+48h+var_28], 10Fh
0x180024140  lea     r9, aBaseDiagnosisS_25; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180024147  mov     edx, 80004005h
0x18002414c  lea     r8, aWinreagentUpda_0; "WinREAgent::UpdateInPartition::Undo"
0x180024153  mov     ecx, 2
0x180024158  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002415d  mov     eax, 80004005h
0x180024162  jmp     loc_1800242BD
0x180024167  mov     rcx, rdi
0x18002416a  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002416f  test    al, al
0x180024171  jnz     short loc_1800241B6
0x180024173  mov     rax, [rdi]
0x180024176  lea     r9, aBaseDiagnosisS_25; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002417d  mov     [rsp+48h+var_18], rax
0x180024182  lea     r8, aWinreagentUpda_0; "WinREAgent::UpdateInPartition::Undo"
0x180024189  lea     rax, aBackupWinreSDo; "Backup WinRE [%s] doesn't exist"
0x180024190  mov     edx, 80070490h
0x180024195  mov     [rsp+48h+var_20], rax
0x18002419a  mov     ecx, 2
0x18002419f  mov     [rsp+48h+var_28], 116h
0x1800241a7  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800241ac  mov     eax, 80070490h
0x1800241b1  jmp     loc_1800242BD
0x1800241b6  add     rbx, 78h ; 'x'
0x1800241ba  mov     rax, [rbx]
0x1800241bd  cmp     dword ptr [rax-10h], 0
0x1800241c1  jnz     short loc_1800241DC
0x1800241c3  lea     rax, aNoWinreWimPath; "No WinRE wim path"
0x1800241ca  mov     [rsp+48h+var_20], rax
0x1800241cf  mov     [rsp+48h+var_28], 11Ch
0x1800241d7  jmp     loc_180024140
0x1800241dc  mov     rcx, rbx
0x1800241df  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800241e4  xor     ecx, ecx
0x1800241e6  test    al, al
0x1800241e8  jz      short loc_18002423C
0x1800241ea  lea     rdx, aDeleteNewWinre; "Delete new WinRE"
0x1800241f1  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800241f6  mov     rcx, rbx
0x1800241f9  call    ?Delete@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; PushButtonReset::File::Delete(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,int)
0x1800241fe  mov     esi, eax
0x180024200  test    eax, eax
0x180024202  jns     short loc_18002424B
0x180024204  mov     rcx, [rbx]
0x180024207  lea     rax, aFailedToDelete_19; "Failed to delete [%s]"
0x18002420e  mov     [rsp+48h+var_18], rcx
0x180024213  lea     r9, aBaseDiagnosisS_25; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002421a  mov     [rsp+48h+var_20], rax
0x18002421f  lea     r8, aWinreagentUpda_0; "WinREAgent::UpdateInPartition::Undo"
0x180024226  mov     ecx, 2
0x18002422b  mov     [rsp+48h+var_28], 124h
0x180024233  mov     edx, esi
0x180024235  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002423a  jmp     short loc_1800242BB
0x18002423c  mov     r8, [rbx]
0x18002423f  lea     rdx, aWinreSDoesnTEx; "WinRE [%s] doesn't exist"
0x180024246  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002424b  lea     rdx, aCopyBackupWinr_0; "Copy Backup WinRE"
0x180024252  xor     ecx, ecx
0x180024254  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180024259  xor     r8d, r8d
0x18002425c  mov     rdx, rbx
0x18002425f  mov     rcx, rdi
0x180024262  call    ?Copy@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAUProgressCallback@2@_N@Z; PushButtonReset::File::Copy(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::ProgressCallback *,bool)
0x180024267  mov     esi, eax
0x180024269  test    eax, eax
0x18002426b  jns     short loc_1800242AD
0x18002426d  mov     rcx, [rbx]
0x180024270  lea     rax, aFailedToCopyST; "Failed to copy [%s] to [%s]"
0x180024277  mov     [rsp+48h+var_10], rcx
0x18002427c  lea     r9, aBaseDiagnosisS_25; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180024283  mov     rcx, [rdi]
0x180024286  lea     r8, aWinreagentUpda_0; "WinREAgent::UpdateInPartition::Undo"
0x18002428d  mov     [rsp+48h+var_18], rcx
0x180024292  mov     edx, esi
0x180024294  mov     [rsp+48h+var_20], rax
0x180024299  mov     ecx, 2
0x18002429e  mov     [rsp+48h+var_28], 130h
0x1800242a6  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800242ab  jmp     short loc_1800242BB
0x1800242ad  lea     rdx, aUpdateinpartit_3; "UpdateInPartition::Undo Completed"
0x1800242b4  xor     ecx, ecx
0x1800242b6  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800242bb  mov     eax, esi
0x1800242bd  mov     rbx, [rsp+48h+arg_0]
0x1800242c2  mov     rsi, [rsp+48h+arg_8]
0x1800242c7  add     rsp, 40h
0x1800242cb  pop     rdi
0x1800242cc  retn
```
