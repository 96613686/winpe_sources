# WinREAgent::DeleteOldWinREHash::Undo(WinREAgent::ExecutionContext *)

- ea: `0x18002abac`
- end: `0x18002ad60`
- name: `?Undo@DeleteOldWinREHash@WinREAgent@@SAJPEAVExecutionContext@2@@Z`
- size: `436`
- prototype: `__int64 __fastcall(struct WinREAgent::ExecutionContext *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002f978`

## callees

- `0x180005cc0`
- `0x18000d6f0`
- `0x18002abac`
- `0x1800361f4`
- `0x18003717c`
- `0x180037344`
- `0x180054b24`
- `0x1800636d0`
- `0x18006c690`
- `0x18006f010`

## string_xrefs

- `0x18002acf3`: `Failed to update WinRE hash`
- `0x18002ac52`: `base\diagnosis\srt\winreagent\lib\operations\src\deleteoldwinrehash.cpp`
- `0x18002acbd`: `base\diagnosis\srt\winreagent\lib\operations\src\deleteoldwinrehash.cpp`
- `0x18002ad07`: `base\diagnosis\srt\winreagent\lib\operations\src\deleteoldwinrehash.cpp`
- `0x18002abcd`: `DeleteOldWinREHash::Undo Start`
- `0x18002ac59`: `WinREAgent::DeleteOldWinREHash::Undo`
- `0x18002acc4`: `WinREAgent::DeleteOldWinREHash::Undo`
- `0x18002ad0e`: `WinREAgent::DeleteOldWinREHash::Undo`
- `0x18002acd7`: `Restore WinRE hash in config back to old WinRE`
- `0x18002ad23`: `DeleteOldWinREHash::Undo Completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WinREAgent::DeleteOldWinREHash::Undo(LPCWSTR *a1)
{
  __int64 v3; // rax
  int v4; // eax
  int updated; // ebx
  void *v6; // rax
  int v7; // eax
  size_t Size; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v9[2]; // [rsp+38h] [rbp-20h] BYREF

  PushButtonReset::Logging::Trace(0, L"DeleteOldWinREHash::Undo Start");
  if ( *((_DWORD *)a1[47] - 4) )
  {
    v9[1] = 0;
    v9[0] = &RAII::CAutoPbrHeapFree<unsigned char *>::`vftable';
    LODWORD(Size) = 0;
    v3 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v9);
    v4 = PushButtonReset::Encode::DecodeBase64(a1 + 47, v3, &Size);
    if ( v4 >= 0 )
    {
      PushButtonReset::Logging::Trace(0, L"Add old winRE hash");
      v6 = (void *)(*(__int64 (__fastcall **)(_QWORD *))(v9[0] + 32LL))(v9);
      v7 = FveAddTrustedWimData(a1[11], v6, (unsigned int)Size);
      if ( v7 < 0 )
        PushButtonReset::Logging::TraceErr(
          1,
          (unsigned int)v7,
          "WinREAgent::DeleteOldWinREHash::Undo",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\deleteoldwinrehash.cpp",
          129,
          L"Failed to add hash for old winre");
      PushButtonReset::Logging::Trace(0, L"Restore WinRE hash in config back to old WinRE");
      updated = WinREAgent::UpdateWinREHash(a1 + 47);
      if ( updated < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          1,
          (unsigned int)updated,
          "WinREAgent::DeleteOldWinREHash::Undo",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\deleteoldwinrehash.cpp",
          138,
          L"Failed to update WinRE hash");
        updated = 0;
      }
      PushButtonReset::Logging::Trace(0, L"DeleteOldWinREHash::Undo Completed");
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        1,
        (unsigned int)v4,
        "WinREAgent::DeleteOldWinREHash::Undo",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\deleteoldwinrehash.cpp",
        120,
        L"Failed to decode hash for old winre",
        Size);
      updated = 0;
    }
    v9[0] = &RAII::CAutoPbrHeapFree<unsigned char *>::`vftable';
    RAII::CAutoPbrHeapFree<unsigned short *>::Release(v9);
    return (unsigned int)updated;
  }
  else
  {
    PushButtonReset::Logging::Trace(0, L"No old WinRE hash");
    return 1;
  }
}

```

## disassembly

```asm
0x18002abac  mov     [rsp+arg_8], rbx
0x18002abb1  mov     [rsp+arg_10], rbp
0x18002abb6  push    rdi
0x18002abb7  sub     rsp, 50h
0x18002abbb  mov     rax, cs:__security_cookie
0x18002abc2  xor     rax, rsp
0x18002abc5  mov     [rsp+58h+var_10], rax
0x18002abca  mov     rdi, rcx
0x18002abcd  lea     rdx, aDeleteoldwinre_2; "DeleteOldWinREHash::Undo Start"
0x18002abd4  xor     ecx, ecx
0x18002abd6  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002abdb  lea     rbx, [rdi+178h]
0x18002abe2  mov     rax, [rbx]
0x18002abe5  cmp     dword ptr [rax-10h], 0
0x18002abe9  jnz     short loc_18002AC03
0x18002abeb  lea     rdx, aNoOldWinreHash; "No old WinRE hash"
0x18002abf2  xor     ecx, ecx
0x18002abf4  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002abf9  mov     eax, 1
0x18002abfe  jmp     loc_18002AD43
0x18002ac03  mov     [rsp+58h+var_18], 0
0x18002ac0c  lea     rbp, ??_7?$CAutoPbrHeapFree@PEAE@RAII@@6B@; const RAII::CAutoPbrHeapFree<uchar *>::`vftable'
0x18002ac13  mov     [rsp+58h+var_20], rbp
0x18002ac18  mov     dword ptr [rsp+58h+Size], 0
0x18002ac20  lea     rcx, [rsp+58h+var_20]
0x18002ac25  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18002ac2a  lea     r8, [rsp+58h+Size]
0x18002ac2f  mov     rdx, rax
0x18002ac32  mov     rcx, rbx
0x18002ac35  call    ?DecodeBase64@Encode@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAEPEAK@Z; PushButtonReset::Encode::DecodeBase64(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uchar * *,ulong *)
0x18002ac3a  test    eax, eax
0x18002ac3c  jns     short loc_18002AC73
0x18002ac3e  lea     rcx, aFailedToDecode; "Failed to decode hash for old winre"
0x18002ac45  mov     [rsp+58h+var_30], rcx
0x18002ac4a  mov     [rsp+58h+var_38], 78h ; 'x'
0x18002ac52  lea     r9, aBaseDiagnosisS_12; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002ac59  lea     r8, aWinreagentDele; "WinREAgent::DeleteOldWinREHash::Undo"
0x18002ac60  mov     edx, eax
0x18002ac62  mov     ecx, 1
0x18002ac67  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002ac6c  xor     ebx, ebx
0x18002ac6e  jmp     loc_18002AD32
0x18002ac73  lea     rdx, aAddOldWinreHas; "Add old winRE hash"
0x18002ac7a  xor     ecx, ecx
0x18002ac7c  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002ac81  mov     rax, [rsp+58h+var_20]
0x18002ac86  lea     rcx, [rsp+58h+var_20]
0x18002ac8b  mov     rax, [rax+20h]
0x18002ac8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac94  mov     r8d, dword ptr [rsp+58h+Size]; Size
0x18002ac99  mov     rdx, rax; Src
0x18002ac9c  mov     rcx, [rdi+58h]; lpFileName
0x18002aca0  call    FveAddTrustedWimData
0x18002aca5  test    eax, eax
0x18002aca7  jns     short loc_18002ACD7
0x18002aca9  lea     rcx, aFailedToAddHas; "Failed to add hash for old winre"
0x18002acb0  mov     [rsp+58h+var_30], rcx
0x18002acb5  mov     [rsp+58h+var_38], 81h
0x18002acbd  lea     r9, aBaseDiagnosisS_12; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002acc4  lea     r8, aWinreagentDele; "WinREAgent::DeleteOldWinREHash::Undo"
0x18002accb  mov     edx, eax
0x18002accd  mov     ecx, 1
0x18002acd2  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002acd7  lea     rdx, aRestoreWinreHa; "Restore WinRE hash in config back to ol"...
0x18002acde  xor     ecx, ecx
0x18002ace0  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002ace5  mov     rcx, rbx
0x18002ace8  call    ?UpdateWinREHash@WinREAgent@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WinREAgent::UpdateWinREHash(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002aced  mov     ebx, eax
0x18002acef  test    eax, eax
0x18002acf1  jns     short loc_18002AD23
0x18002acf3  lea     rax, aFailedToUpdate_0; "Failed to update WinRE hash"
0x18002acfa  mov     [rsp+58h+var_30], rax
0x18002acff  mov     [rsp+58h+var_38], 8Ah
0x18002ad07  lea     r9, aBaseDiagnosisS_12; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002ad0e  lea     r8, aWinreagentDele; "WinREAgent::DeleteOldWinREHash::Undo"
0x18002ad15  mov     edx, ebx
0x18002ad17  mov     ecx, 1
0x18002ad1c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002ad21  xor     ebx, ebx
0x18002ad23  lea     rdx, aDeleteoldwinre_1; "DeleteOldWinREHash::Undo Completed"
0x18002ad2a  xor     ecx, ecx
0x18002ad2c  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002ad31  nop
0x18002ad32  mov     [rsp+58h+var_20], rbp
0x18002ad37  lea     rcx, [rsp+58h+var_20]
0x18002ad3c  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x18002ad41  mov     eax, ebx
0x18002ad43  mov     rcx, [rsp+58h+var_10]
0x18002ad48  xor     rcx, rsp; StackCookie
0x18002ad4b  call    __security_check_cookie
0x18002ad50  mov     rbx, [rsp+58h+arg_8]
0x18002ad55  mov     rbp, [rsp+58h+arg_10]
0x18002ad5a  add     rsp, 50h
0x18002ad5e  pop     rdi
0x18002ad5f  retn
```
