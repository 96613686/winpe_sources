# WinREAgent::DeleteOldWinREHash::InternalExecute(WinREAgent::ExecutionContext const *,PushButtonReset::ProgressCallback *)

- ea: `0x18002a950`
- end: `0x18002aba3`
- name: `?InternalExecute@DeleteOldWinREHash@WinREAgent@@MEAAJPEBVExecutionContext@2@PEAUProgressCallback@PushButtonReset@@@Z`
- size: `595`
- prototype: `__int64 __fastcall(WinREAgent::DeleteOldWinREHash *__hidden this, const struct WinREAgent::ExecutionContext *, struct PushButtonReset::ProgressCallback *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180005cc0`
- `0x18000d6f0`
- `0x18002a90c`
- `0x18002a950`
- `0x18002e06c`
- `0x18003207c`
- `0x1800361f4`
- `0x18003717c`
- `0x180037344`
- `0x180054b24`
- `0x180063d80`
- `0x18006c690`
- `0x18006f010`

## string_xrefs

- `0x18002aa47`: `Delete old WinRE hash`
- `0x18002a99e`: `Update WinRE hash in config for new WinRE`
- `0x18002a9c0`: `UpdateWinREHashResult`
- `0x18002a9d7`: `Failed to update WinRE hash`
- `0x18002a9eb`: `base\diagnosis\srt\winreagent\lib\operations\src\deleteoldwinrehash.cpp`
- `0x18002aa9f`: `base\diagnosis\srt\winreagent\lib\operations\src\deleteoldwinrehash.cpp`
- `0x18002aaeb`: `base\diagnosis\srt\winreagent\lib\operations\src\deleteoldwinrehash.cpp`
- `0x18002ab49`: `base\diagnosis\srt\winreagent\lib\operations\src\deleteoldwinrehash.cpp`
- `0x18002a9f2`: `WinREAgent::DeleteOldWinREHash::InternalExecute`
- `0x18002aaa6`: `WinREAgent::DeleteOldWinREHash::InternalExecute`
- `0x18002aaf2`: `WinREAgent::DeleteOldWinREHash::InternalExecute`
- `0x18002ab50`: `WinREAgent::DeleteOldWinREHash::InternalExecute`
- `0x18002ab12`: `DeleteOldWinREHash: Add checkpoint [%u]`
- `0x18002ab35`: `Failed to set checkpoint for DeleteOldWinREHash`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WinREAgent::DeleteOldWinREHash::InternalExecute(
        WinREAgent::DeleteOldWinREHash *this,
        const struct WinREAgent::ExecutionContext *a2,
        struct PushButtonReset::ProgressCallback *a3)
{
  _QWORD *v5; // r14
  int v6; // ebx
  unsigned int updated; // eax
  WinREAgent::TelemetrySession *v8; // rcx
  __int64 v9; // rax
  int v10; // eax
  int v11; // eax
  __int64 v13; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v14[2]; // [rsp+38h] [rbp-18h] BYREF

  v5 = (_QWORD *)((char *)a2 + 408);
  if ( *(_DWORD *)(*((_QWORD *)a2 + 51) - 16LL) )
  {
    PushButtonReset::Logging::Trace(0, L"Update WinRE hash in config for new WinRE", a3);
    updated = WinREAgent::UpdateWinREHash(v5);
    v6 = updated;
    v8 = (WinREAgent::TelemetrySession *)*((_QWORD *)this + 14);
    if ( v8 )
      WinREAgent::TelemetrySession::TraceDataPoint(v8, L"ServicingInfoGroup", L"UpdateWinREHashResult", updated);
    if ( v6 < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        1,
        (unsigned int)v6,
        "WinREAgent::DeleteOldWinREHash::InternalExecute",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\deleteoldwinrehash.cpp",
        53,
        L"Failed to update WinRE hash");
      v6 = 0;
    }
  }
  else
  {
    v6 = 0;
    PushButtonReset::Logging::Trace(0, L"No new WinRE hash", a3);
  }
  if ( *((_BYTE *)a2 + 344) && *(_DWORD *)(*((_QWORD *)a2 + 47) - 16LL) )
  {
    if ( !*(_DWORD *)(*v5 - 16LL)
      || (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Compare((char *)a2 + 376) )
    {
      PushButtonReset::Logging::Trace(0, L"Delete old WinRE hash");
      v14[1] = 0;
      v14[0] = &RAII::CAutoPbrHeapFree<unsigned char *>::`vftable';
      LODWORD(v13) = 0;
      v9 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v14);
      v10 = PushButtonReset::Encode::DecodeBase64((char *)a2 + 376, v9, &v13);
      if ( v10 < 0 )
        PushButtonReset::Logging::TraceErr(
          1,
          (unsigned int)v10,
          "WinREAgent::DeleteOldWinREHash::InternalExecute",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\deleteoldwinrehash.cpp",
          79,
          L"Failed to decode old wim hash",
          v13);
      (*(void (__fastcall **)(_QWORD *))(v14[0] + 32LL))(v14);
      v11 = FveRemoveTrustedWimData(*((LPCWSTR *)a2 + 11));
      v6 = v11;
      if ( v11 < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          1,
          (unsigned int)v11,
          "WinREAgent::DeleteOldWinREHash::InternalExecute",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\deleteoldwinrehash.cpp",
          86,
          L"Failed to decode old wim hash");
        v6 = 0;
      }
      if ( *((_QWORD *)a2 + 56) )
      {
        PushButtonReset::Logging::Trace(0, L"DeleteOldWinREHash: Add checkpoint [%u]", 1);
        v6 = WinREAgent::RollbackHelper::SetCheckpoint(*((_QWORD *)a2 + 56), 1);
        if ( v6 < 0 )
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)v6,
            "WinREAgent::DeleteOldWinREHash::InternalExecute",
            "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\deleteoldwinrehash.cpp",
            95,
            L"Failed to set checkpoint for DeleteOldWinREHash");
      }
      v14[0] = &RAII::CAutoPbrHeapFree<unsigned char *>::`vftable';
      RAII::CAutoPbrHeapFree<unsigned short *>::Release(v14);
    }
    else
    {
      PushButtonReset::Logging::Trace(0, L"Old WinRE hash is the same as new WinRE hash, skip deletion");
    }
  }
  else
  {
    PushButtonReset::Logging::Trace(0, L"Old WinRE hash is not trusted or empty, skip deletion");
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002a950  mov     [rsp-28h+arg_10], rbx
0x18002a955  push    rbp
0x18002a956  push    rsi
0x18002a957  push    rdi
0x18002a958  push    r12
0x18002a95a  push    r14
0x18002a95c  mov     rbp, rsp
0x18002a95f  sub     rsp, 50h
0x18002a963  mov     rax, cs:__security_cookie
0x18002a96a  xor     rax, rsp
0x18002a96d  mov     [rbp+var_8], rax
0x18002a971  mov     rdi, rdx
0x18002a974  mov     rsi, rcx
0x18002a977  lea     r14, [rdx+198h]
0x18002a97e  mov     rax, [r14]
0x18002a981  mov     r12d, 1
0x18002a987  xor     ecx, ecx
0x18002a989  cmp     [rax-10h], ecx
0x18002a98c  jnz     short loc_18002A99E
0x18002a98e  xor     ebx, ebx
0x18002a990  lea     rdx, aNoNewWinreHash; "No new WinRE hash"
0x18002a997  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002a99c  jmp     short loc_18002AA05
0x18002a99e  lea     rdx, aUpdateWinreHas_1; "Update WinRE hash in config for new Win"...
0x18002a9a5  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002a9aa  mov     rcx, r14
0x18002a9ad  call    ?UpdateWinREHash@WinREAgent@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WinREAgent::UpdateWinREHash(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002a9b2  mov     ebx, eax
0x18002a9b4  mov     rcx, [rsi+70h]; this
0x18002a9b8  test    rcx, rcx
0x18002a9bb  jz      short loc_18002A9D3
0x18002a9bd  mov     r9d, eax; unsigned int
0x18002a9c0  lea     r8, aUpdatewinrehas; "UpdateWinREHashResult"
0x18002a9c7  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x18002a9ce  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ulong)
0x18002a9d3  test    ebx, ebx
0x18002a9d5  jns     short loc_18002AA05
0x18002a9d7  lea     rax, aFailedToUpdate_0; "Failed to update WinRE hash"
0x18002a9de  mov     [rsp+50h+var_28], rax
0x18002a9e3  mov     [rsp+50h+var_30], 35h ; '5'
0x18002a9eb  lea     r9, aBaseDiagnosisS_12; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002a9f2  lea     r8, aWinreagentDele_0; "WinREAgent::DeleteOldWinREHash::Interna"...
0x18002a9f9  mov     edx, ebx
0x18002a9fb  mov     ecx, r12d
0x18002a9fe  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002aa03  xor     ebx, ebx
0x18002aa05  cmp     byte ptr [rdi+158h], 0
0x18002aa0c  jz      loc_18002AB73
0x18002aa12  lea     rsi, [rdi+178h]
0x18002aa19  mov     rax, [rsi]
0x18002aa1c  cmp     dword ptr [rax-10h], 0
0x18002aa20  jz      loc_18002AB73
0x18002aa26  mov     rdx, [r14]
0x18002aa29  cmp     dword ptr [rdx-10h], 0
0x18002aa2d  jz      short loc_18002AA47
0x18002aa2f  mov     rcx, rsi
0x18002aa32  call    ?Compare@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Compare(ushort const *)
0x18002aa37  test    eax, eax
0x18002aa39  jnz     short loc_18002AA47
0x18002aa3b  lea     rdx, aOldWinreHashIs_0; "Old WinRE hash is the same as new WinRE"...
0x18002aa42  jmp     loc_18002AB7A
0x18002aa47  lea     rdx, aDeleteOldWinre_0; "Delete old WinRE hash"
0x18002aa4e  xor     ecx, ecx
0x18002aa50  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002aa55  mov     [rbp+var_10], 0
0x18002aa5d  lea     r14, ??_7?$CAutoPbrHeapFree@PEAE@RAII@@6B@; const RAII::CAutoPbrHeapFree<uchar *>::`vftable'
0x18002aa64  mov     [rbp+var_18], r14
0x18002aa68  mov     dword ptr [rbp+var_20], 0
0x18002aa6f  lea     rcx, [rbp+var_18]
0x18002aa73  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18002aa78  lea     r8, [rbp+var_20]
0x18002aa7c  mov     rdx, rax
0x18002aa7f  mov     rcx, rsi
0x18002aa82  call    ?DecodeBase64@Encode@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAEPEAK@Z; PushButtonReset::Encode::DecodeBase64(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,uchar * *,ulong *)
0x18002aa87  lea     rsi, aFailedToDecode_0; "Failed to decode old wim hash"
0x18002aa8e  test    eax, eax
0x18002aa90  jns     short loc_18002AAB7
0x18002aa92  mov     [rsp+50h+var_28], rsi
0x18002aa97  mov     [rsp+50h+var_30], 4Fh ; 'O'
0x18002aa9f  lea     r9, aBaseDiagnosisS_12; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002aaa6  lea     r8, aWinreagentDele_0; "WinREAgent::DeleteOldWinREHash::Interna"...
0x18002aaad  mov     edx, eax
0x18002aaaf  mov     ecx, r12d
0x18002aab2  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002aab7  mov     rax, [rbp+var_18]
0x18002aabb  lea     rcx, [rbp+var_18]
0x18002aabf  mov     rax, [rax+20h]
0x18002aac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aac8  mov     r8d, dword ptr [rbp+var_20]
0x18002aacc  mov     rdx, rax
0x18002aacf  mov     rcx, [rdi+58h]; lpFileName
0x18002aad3  call    FveRemoveTrustedWimData
0x18002aad8  mov     ebx, eax
0x18002aada  test    eax, eax
0x18002aadc  jns     short loc_18002AB05
0x18002aade  mov     [rsp+50h+var_28], rsi
0x18002aae3  mov     [rsp+50h+var_30], 56h ; 'V'
0x18002aaeb  lea     r9, aBaseDiagnosisS_12; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002aaf2  lea     r8, aWinreagentDele_0; "WinREAgent::DeleteOldWinREHash::Interna"...
0x18002aaf9  mov     edx, eax
0x18002aafb  mov     ecx, r12d
0x18002aafe  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002ab03  xor     ebx, ebx
0x18002ab05  cmp     qword ptr [rdi+1C0h], 0
0x18002ab0d  jz      short loc_18002AB64
0x18002ab0f  mov     r8d, r12d
0x18002ab12  lea     rdx, aDeleteoldwinre; "DeleteOldWinREHash: Add checkpoint [%u]"
0x18002ab19  xor     ecx, ecx
0x18002ab1b  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002ab20  mov     edx, r12d
0x18002ab23  mov     rcx, [rdi+1C0h]
0x18002ab2a  call    ?SetCheckpoint@RollbackHelper@WinREAgent@@QEAAJW4RollbackCheckpoint@2@@Z; WinREAgent::RollbackHelper::SetCheckpoint(WinREAgent::RollbackCheckpoint)
0x18002ab2f  mov     ebx, eax
0x18002ab31  test    eax, eax
0x18002ab33  jns     short loc_18002AB64
0x18002ab35  lea     rax, aFailedToSetChe_0; "Failed to set checkpoint for DeleteOldW"...
0x18002ab3c  mov     [rsp+50h+var_28], rax
0x18002ab41  mov     [rsp+50h+var_30], 5Fh ; '_'
0x18002ab49  lea     r9, aBaseDiagnosisS_12; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002ab50  lea     r8, aWinreagentDele_0; "WinREAgent::DeleteOldWinREHash::Interna"...
0x18002ab57  mov     edx, ebx
0x18002ab59  mov     ecx, 2
0x18002ab5e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002ab63  nop
0x18002ab64  mov     [rbp+var_18], r14
0x18002ab68  lea     rcx, [rbp+var_18]
0x18002ab6c  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x18002ab71  jmp     short loc_18002AB81
0x18002ab73  lea     rdx, aOldWinreHashIs_1; "Old WinRE hash is not trusted or empty,"...
0x18002ab7a  xor     ecx, ecx
0x18002ab7c  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002ab81  mov     eax, ebx
0x18002ab83  mov     rcx, [rbp+var_8]
0x18002ab87  xor     rcx, rsp; StackCookie
0x18002ab8a  call    __security_check_cookie
0x18002ab8f  mov     rbx, [rsp+50h+arg_10]
0x18002ab97  add     rsp, 50h
0x18002ab9b  pop     r14
0x18002ab9d  pop     r12
0x18002ab9f  pop     rdi
0x18002aba0  pop     rsi
0x18002aba1  pop     rbp
0x18002aba2  retn
```
