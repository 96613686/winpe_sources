# WinREAgent::Repartition::UndoDeleteWinREPartition(WinREAgent::ExecutionContext *)

- ea: `0x180026ae0`
- end: `0x180026dd4`
- name: `?UndoDeleteWinREPartition@Repartition@WinREAgent@@SAJPEAVExecutionContext@2@@Z`
- size: `756`
- prototype: `__int64 __fastcall(struct WinREAgent::ExecutionContext *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002f978`

## callees

- `0x180004af8`
- `0x180005c00`
- `0x18000d900`
- `0x18000d92c`
- `0x180026ae0`
- `0x180027c6c`
- `0x180028220`
- `0x18003717c`
- `0x180037344`
- `0x18004d2ac`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180026c47`
- `KERNEL32!LoadLibraryExW` at `0x180026c47`
- `KERNEL32!GetProcAddress` at `0x180026ceb`
- `KERNEL32!GetProcAddress` at `0x180026ceb`
- `KERNEL32!GetLastError` at `0x180026c69`
- `KERNEL32!GetLastError` at `0x180026cab`
- `KERNEL32!GetLastError` at `0x180026cf9`
- `KERNEL32!GetLastError` at `0x180026d4b`
- `KERNEL32!GetLastError` at `0x180026c69`
- `KERNEL32!GetLastError` at `0x180026cab`
- `KERNEL32!GetLastError` at `0x180026cf9`
- `KERNEL32!GetLastError` at `0x180026d4b`

## string_xrefs

- `0x180026c40`: `ReAgent.dll`
- `0x180026c7d`: `Failed to load ReAgent.dll`
- `0x180026d0d`: `Failed to load function from DLL`
- `0x180026b2d`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180026b8f`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180026bcd`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180026c14`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180026c91`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180026d74`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180026ce4`: `WinReInstallTarget`
- `0x180026d60`: `Failed to install WinRE`
- `0x180026b19`: `Cannot execute undo without rollback object`
- `0x180026b01`: `Repartition::UndoDeleteWinREPartition Start`
- `0x180026b34`: `WinREAgent::Repartition::UndoDeleteWinREPartition`
- `0x180026b96`: `WinREAgent::Repartition::UndoDeleteWinREPartition`
- `0x180026bd4`: `WinREAgent::Repartition::UndoDeleteWinREPartition`
- `0x180026c1b`: `WinREAgent::Repartition::UndoDeleteWinREPartition`
- `0x180026c98`: `WinREAgent::Repartition::UndoDeleteWinREPartition`
- `0x180026d7b`: `WinREAgent::Repartition::UndoDeleteWinREPartition`
- `0x180026b7b`: `Failed to get WinRE partition for rollback`
- `0x180026bb9`: `Failed to copy backup WinRE to stage location`
- `0x180026d93`: `Repartition::UndoDeleteWinREPartition Completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WinREAgent::Repartition::UndoDeleteWinREPartition(struct WinREAgent::ExecutionContext *a1)
{
  int v3; // edi
  _QWORD *v4; // rsi
  __int64 v5; // rbx
  signed int v6; // eax
  signed int LastError; // eax
  signed int v8; // eax
  unsigned int v9; // esi
  HMODULE v10; // rax
  FARPROC ProcAddress; // r14
  signed int v12; // eax
  signed int v13; // eax
  __int64 v14; // [rsp+40h] [rbp-28h] BYREF
  __int64 v15[2]; // [rsp+48h] [rbp-20h] BYREF

  PushButtonReset::Logging::Trace(0, L"Repartition::UndoDeleteWinREPartition Start");
  if ( !*((_QWORD *)a1 + 56) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942487LL,
      "WinREAgent::Repartition::UndoDeleteWinREPartition",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
      1003,
      L"Cannot execute undo without rollback object");
    return 2147942487LL;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v14);
  v3 = WinREGetWinREPartition(a1, &v14);
  v4 = (_QWORD *)((char *)a1 + 312);
  v5 = v14;
  if ( v3 < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v3,
      "WinREAgent::Repartition::UndoDeleteWinREPartition",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
      1018,
      L"Failed to get WinRE partition for rollback");
    v6 = WinRECopyToStage(v4);
    if ( v6 < 0 )
      PushButtonReset::Logging::TraceErr(
        1,
        (unsigned int)v6,
        "WinREAgent::Repartition::UndoDeleteWinREPartition",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        1026,
        L"Failed to copy backup WinRE to stage location");
    goto LABEL_24;
  }
  if ( (unsigned __int8)PushButtonReset::File::Exists(v4) )
  {
    v15[1] = (__int64)LoadLibraryExW(L"ReAgent.dll", 0, 0);
    v15[0] = (__int64)&RAII::CAutoFreeLibrary::`vftable';
    if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(v15) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LastError,
        "WinREAgent::Repartition::UndoDeleteWinREPartition",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        1042,
        L"Failed to load ReAgent.dll");
    }
    else
    {
      v10 = (HMODULE)(*(__int64 (__fastcall **)(__int64 *))(v15[0] + 32))(v15);
      ProcAddress = GetProcAddress(v10, "WinReInstallTarget");
      if ( ProcAddress )
      {
        PushButtonReset::Logging::Trace(0, L"Repartition: Restore WinRE from [%s]", *v4);
        if ( ((unsigned int (__fastcall *)(_QWORD, _QWORD, __int64))ProcAddress)(0, *v4, v5) )
        {
          PushButtonReset::Logging::Trace(0, L"Repartition::UndoDeleteWinREPartition Completed");
          v15[0] = (__int64)&RAII::CAutoFreeLibrary::`vftable';
          RAII::CAutoFreeLibrary::Release((RAII::CAutoFreeLibrary *)v15);
          goto LABEL_24;
        }
        v13 = GetLastError();
        v9 = v13;
        if ( v13 > 0 )
          v9 = (unsigned __int16)v13 | 0x80070000;
        PushButtonReset::Logging::TraceErr(
          2,
          v9,
          "WinREAgent::Repartition::UndoDeleteWinREPartition",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
          1057,
          L"Failed to install WinRE");
        goto LABEL_14;
      }
      v12 = GetLastError();
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v12,
        "WinREAgent::Repartition::UndoDeleteWinREPartition",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        1050,
        L"Failed to load function from DLL");
    }
    v8 = GetLastError();
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
LABEL_14:
    v15[0] = (__int64)&RAII::CAutoFreeLibrary::`vftable';
    RAII::CAutoFreeLibrary::Release((RAII::CAutoFreeLibrary *)v15);
    v3 = v9;
    goto LABEL_24;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    2147942402LL,
    "WinREAgent::Repartition::UndoDeleteWinREPartition",
    "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
    1035,
    L"Failed to find backup WinRE [%s]",
    *v4);
  v3 = -2147024894;
LABEL_24:
  ATL::CStringData::Release((ATL::CStringData *)(v5 - 24));
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180026ae0  push    rbp
0x180026ae2  push    rbx
0x180026ae3  push    rsi
0x180026ae4  push    rdi
0x180026ae5  push    r14
0x180026ae7  push    r15
0x180026ae9  mov     rbp, rsp
0x180026aec  sub     rsp, 68h
0x180026af0  mov     rax, cs:__security_cookie
0x180026af7  xor     rax, rsp
0x180026afa  mov     [rbp+var_10], rax
0x180026afe  mov     rbx, rcx
0x180026b01  lea     rdx, aRepartitionUnd_0; "Repartition::UndoDeleteWinREPartition S"...
0x180026b08  xor     ecx, ecx
0x180026b0a  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180026b0f  cmp     qword ptr [rbx+1C0h], 0
0x180026b17  jnz     short loc_180026B54
0x180026b19  lea     rax, aCannotExecuteU; "Cannot execute undo without rollback ob"...
0x180026b20  mov     [rsp+68h+var_40], rax
0x180026b25  mov     [rsp+68h+var_48], 3EBh
0x180026b2d  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180026b34  lea     r8, aWinreagentRepa_7; "WinREAgent::Repartition::UndoDeleteWinR"...
0x180026b3b  mov     edx, 80070057h
0x180026b40  mov     ecx, 2
0x180026b45  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180026b4a  mov     eax, 80070057h
0x180026b4f  jmp     loc_180026DBB
0x180026b54  lea     rcx, [rbp+var_28]
0x180026b58  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180026b5d  nop
0x180026b5e  lea     rdx, [rbp+var_28]
0x180026b62  mov     rcx, rbx
0x180026b65  call    ?WinREGetWinREPartition@@YAJPEAVExecutionContext@WinREAgent@@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WinREGetWinREPartition(WinREAgent::ExecutionContext *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180026b6a  mov     edi, eax
0x180026b6c  lea     rsi, [rbx+138h]
0x180026b73  mov     rbx, [rbp+var_28]
0x180026b77  test    eax, eax
0x180026b79  jns     short loc_180026BEC
0x180026b7b  lea     rax, aFailedToGetWin_3; "Failed to get WinRE partition for rollb"...
0x180026b82  mov     [rsp+68h+var_40], rax
0x180026b87  mov     [rsp+68h+var_48], 3FAh
0x180026b8f  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180026b96  lea     r8, aWinreagentRepa_7; "WinREAgent::Repartition::UndoDeleteWinR"...
0x180026b9d  mov     edx, edi
0x180026b9f  mov     ecx, 2
0x180026ba4  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180026ba9  mov     rcx, rsi
0x180026bac  call    ?WinRECopyToStage@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WinRECopyToStage(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180026bb1  test    eax, eax
0x180026bb3  jns     loc_180026DB0
0x180026bb9  lea     rcx, aFailedToCopyBa; "Failed to copy backup WinRE to stage lo"...
0x180026bc0  mov     [rsp+68h+var_40], rcx
0x180026bc5  mov     [rsp+68h+var_48], 402h
0x180026bcd  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180026bd4  lea     r8, aWinreagentRepa_7; "WinREAgent::Repartition::UndoDeleteWinR"...
0x180026bdb  mov     edx, eax
0x180026bdd  mov     ecx, 1
0x180026be2  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180026be7  jmp     loc_180026DB0
0x180026bec  mov     rcx, rsi
0x180026bef  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180026bf4  test    al, al
0x180026bf6  jnz     short loc_180026C3B
0x180026bf8  mov     rax, [rsi]
0x180026bfb  mov     [rsp+68h+var_38], rax
0x180026c00  lea     rax, aFailedToFindBa; "Failed to find backup WinRE [%s]"
0x180026c07  mov     [rsp+68h+var_40], rax
0x180026c0c  mov     [rsp+68h+var_48], 40Bh
0x180026c14  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180026c1b  lea     r8, aWinreagentRepa_7; "WinREAgent::Repartition::UndoDeleteWinR"...
0x180026c22  mov     edx, 80070002h
0x180026c27  mov     ecx, 2
0x180026c2c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180026c31  mov     edi, 80070002h
0x180026c36  jmp     loc_180026DB0
0x180026c3b  xor     r8d, r8d; dwFlags
0x180026c3e  xor     edx, edx; hFile
0x180026c40  lea     rcx, LibFileName; "ReAgent.dll"
0x180026c47  call    cs:__imp_LoadLibraryExW
0x180026c4d  mov     [rbp+var_18], rax
0x180026c51  lea     r15, ??_7CAutoFreeLibrary@RAII@@6B@; const RAII::CAutoFreeLibrary::`vftable'
0x180026c58  mov     [rbp+var_20], r15
0x180026c5c  lea     rcx, [rbp+var_20]
0x180026c60  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x180026c65  test    al, al
0x180026c67  jz      short loc_180026CD0
0x180026c69  call    cs:__imp_GetLastError
0x180026c6f  mov     edi, 80070000h
0x180026c74  test    eax, eax
0x180026c76  jle     short loc_180026C7D
0x180026c78  movzx   eax, ax
0x180026c7b  or      eax, edi
0x180026c7d  lea     rcx, aFailedToLoadRe; "Failed to load ReAgent.dll"
0x180026c84  mov     [rsp+68h+var_40], rcx
0x180026c89  mov     [rsp+68h+var_48], 412h
0x180026c91  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180026c98  lea     r8, aWinreagentRepa_7; "WinREAgent::Repartition::UndoDeleteWinR"...
0x180026c9f  mov     edx, eax
0x180026ca1  mov     ecx, 2
0x180026ca6  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180026cab  call    cs:__imp_GetLastError
0x180026cb1  test    eax, eax
0x180026cb3  mov     esi, eax
0x180026cb5  jle     short loc_180026CBC
0x180026cb7  movzx   esi, ax
0x180026cba  or      esi, edi
0x180026cbc  mov     [rbp+var_20], r15
0x180026cc0  lea     rcx, [rbp+var_20]; this
0x180026cc4  call    ?Release@CAutoFreeLibrary@RAII@@UEAAXXZ; RAII::CAutoFreeLibrary::Release(void)
0x180026cc9  mov     edi, esi
0x180026ccb  jmp     loc_180026DB0
0x180026cd0  mov     rax, [rbp+var_20]
0x180026cd4  lea     rcx, [rbp+var_20]
0x180026cd8  mov     rax, [rax+20h]
0x180026cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ce1  mov     rcx, rax; hModule
0x180026ce4  lea     rdx, aWinreinstallta; "WinReInstallTarget"
0x180026ceb  call    cs:__imp_GetProcAddress
0x180026cf1  mov     r14, rax
0x180026cf4  test    rax, rax
0x180026cf7  jnz     short loc_180026D26
0x180026cf9  call    cs:__imp_GetLastError
0x180026cff  mov     edi, 80070000h
0x180026d04  test    eax, eax
0x180026d06  jle     short loc_180026D0D
0x180026d08  movzx   eax, ax
0x180026d0b  or      eax, edi
0x180026d0d  lea     rcx, aFailedToLoadFu; "Failed to load function from DLL"
0x180026d14  mov     [rsp+68h+var_40], rcx
0x180026d19  mov     [rsp+68h+var_48], 41Ah
0x180026d21  jmp     loc_180026C91
0x180026d26  mov     r8, [rsi]
0x180026d29  lea     rdx, aRepartitionRes; "Repartition: Restore WinRE from [%s]"
0x180026d30  xor     ecx, ecx
0x180026d32  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180026d37  mov     r8, rbx
0x180026d3a  mov     rdx, [rsi]
0x180026d3d  xor     ecx, ecx
0x180026d3f  mov     rax, r14
0x180026d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d47  test    eax, eax
0x180026d49  jnz     short loc_180026D93
0x180026d4b  call    cs:__imp_GetLastError
0x180026d51  mov     esi, eax
0x180026d53  test    eax, eax
0x180026d55  jle     short loc_180026D60
0x180026d57  movzx   esi, ax
0x180026d5a  or      esi, 80070000h
0x180026d60  lea     rax, aFailedToInstal_0; "Failed to install WinRE"
0x180026d67  mov     [rsp+68h+var_40], rax
0x180026d6c  mov     [rsp+68h+var_48], 421h
0x180026d74  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180026d7b  lea     r8, aWinreagentRepa_7; "WinREAgent::Repartition::UndoDeleteWinR"...
0x180026d82  mov     edx, esi
0x180026d84  mov     ecx, 2
0x180026d89  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180026d8e  jmp     loc_180026CBC
0x180026d93  lea     rdx, aRepartitionUnd_4; "Repartition::UndoDeleteWinREPartition C"...
0x180026d9a  xor     ecx, ecx
0x180026d9c  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180026da1  nop
0x180026da2  mov     [rbp+var_20], r15
0x180026da6  lea     rcx, [rbp+var_20]; this
0x180026daa  call    ?Release@CAutoFreeLibrary@RAII@@UEAAXXZ; RAII::CAutoFreeLibrary::Release(void)
0x180026daf  nop
0x180026db0  lea     rcx, [rbx-18h]; this
0x180026db4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180026db9  mov     eax, edi
0x180026dbb  mov     rcx, [rbp+var_10]
0x180026dbf  xor     rcx, rsp; StackCookie
0x180026dc2  call    __security_check_cookie
0x180026dc7  add     rsp, 68h
0x180026dcb  pop     r15
0x180026dcd  pop     r14
0x180026dcf  pop     rdi
0x180026dd0  pop     rsi
0x180026dd1  pop     rbx
0x180026dd2  pop     rbp
0x180026dd3  retn
```
