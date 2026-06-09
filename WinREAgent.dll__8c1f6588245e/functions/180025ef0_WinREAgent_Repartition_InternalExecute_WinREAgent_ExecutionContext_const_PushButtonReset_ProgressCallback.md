# WinREAgent::Repartition::InternalExecute(WinREAgent::ExecutionContext const *,PushButtonReset::ProgressCallback *)

- ea: `0x180025ef0`
- end: `0x180026218`
- name: `?InternalExecute@Repartition@WinREAgent@@MEAAJPEBVExecutionContext@2@PEAUProgressCallback@PushButtonReset@@@Z`
- size: `808`
- prototype: `__int64 __fastcall(WinREAgent::Repartition *__hidden this, const struct WinREAgent::ExecutionContext *, struct PushButtonReset::ProgressCallback *)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update`

## callees

- `0x180004af8`
- `0x180005c00`
- `0x18000d900`
- `0x18000d92c`
- `0x180025180`
- `0x1800258b8`
- `0x180025c74`
- `0x180025ef0`
- `0x180027a60`
- `0x18003717c`
- `0x180037344`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180025f31`
- `KERNEL32!LoadLibraryExW` at `0x180025f31`
- `KERNEL32!GetProcAddress` at `0x180025fca`
- `KERNEL32!GetProcAddress` at `0x180025fca`
- `KERNEL32!GetLastError` at `0x180025f53`
- `KERNEL32!GetLastError` at `0x180025f95`
- `KERNEL32!GetLastError` at `0x180025fd8`
- `KERNEL32!GetLastError` at `0x18002601a`
- `KERNEL32!GetLastError` at `0x18002619a`
- `KERNEL32!GetLastError` at `0x180025f53`
- `KERNEL32!GetLastError` at `0x180025f95`
- `KERNEL32!GetLastError` at `0x180025fd8`
- `KERNEL32!GetLastError` at `0x18002601a`
- `KERNEL32!GetLastError` at `0x18002619a`

## string_xrefs

- `0x180025f2a`: `ReAgent.dll`
- `0x180025f67`: `Failed to load ReAgent.dll`
- `0x180025fec`: `Failed to load function from DLL`
- `0x180025f7b`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180026000`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x18002605d`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180026096`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180026144`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x1800261c3`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180025f82`: `WinREAgent::Repartition::InternalExecute`
- `0x180026007`: `WinREAgent::Repartition::InternalExecute`
- `0x180026064`: `WinREAgent::Repartition::InternalExecute`
- `0x18002609d`: `WinREAgent::Repartition::InternalExecute`
- `0x18002614b`: `WinREAgent::Repartition::InternalExecute`
- `0x1800261ca`: `WinREAgent::Repartition::InternalExecute`
- `0x180025fc3`: `WinReInstallTarget`
- `0x180026049`: `Failed to verify the scheduled method`
- `0x180026082`: `Cannot execute the scheduled method`
- `0x1800260f8`: `Failed to delete WinRE partition`
- `0x180026130`: `Failed to create new WinRE partition`
- `0x180026170`: `Repartition: Install WinRE from [%s]`
- `0x1800261af`: `Failed to install WinRE`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WinREAgent::Repartition::InternalExecute(
        WinREAgent::Repartition *this,
        const struct WinREAgent::ExecutionContext *a2,
        struct PushButtonReset::ProgressCallback *a3)
{
  signed int LastError; // eax
  signed int v6; // eax
  unsigned int v7; // ebx
  HMODULE v8; // rax
  FARPROC ProcAddress; // r14
  signed int v10; // eax
  signed int v11; // eax
  signed int v12; // esi
  ATL::CStringData *v13; // rcx
  __int64 v14; // rbx
  signed int v15; // eax
  bool v17; // [rsp+30h] [rbp-30h] BYREF
  __int64 v18; // [rsp+38h] [rbp-28h] BYREF
  __int64 v19[2]; // [rsp+40h] [rbp-20h] BYREF

  PushButtonReset::Logging::Trace(0, L"Repartition: Repartition to extend WinRE partition", a3);
  v19[1] = (__int64)LoadLibraryExW(L"ReAgent.dll", 0, 0);
  v19[0] = (__int64)&RAII::CAutoFreeLibrary::`vftable';
  if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(v19) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)LastError,
      "WinREAgent::Repartition::InternalExecute",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
      692,
      L"Failed to load ReAgent.dll");
    v6 = GetLastError();
    v7 = v6;
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
  }
  else
  {
    v8 = (HMODULE)(*(__int64 (__fastcall **)(__int64 *))(v19[0] + 32))(v19);
    ProcAddress = GetProcAddress(v8, "WinReInstallTarget");
    if ( ProcAddress )
    {
      v17 = 0;
      v12 = WinREAgent::Repartition::VerifyScheduledMethod(this, a2, &v17);
      if ( v12 >= 0 )
      {
        if ( !v17 )
        {
          PushButtonReset::Logging::TraceErr(
            2,
            2147500037LL,
            "WinREAgent::Repartition::InternalExecute",
            "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
            710,
            L"Cannot execute the scheduled method");
          v7 = -2147467259;
          goto LABEL_30;
        }
        v12 = WinREAgent::Repartition::ExecuteShrink(this, a2);
        if ( v12 >= 0 )
        {
          v12 = WinREAgent::Repartition::ExecuteDeleteWinREPartition(this, a2);
          if ( v12 >= 0 )
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v18);
            v12 = WinREAgent::Repartition::ExecuteCreateWinREPartition(this, a2, &v18);
            if ( v12 >= 0 )
            {
              PushButtonReset::Logging::Trace(0, L"Repartition: Install WinRE from [%s]", *((_QWORD *)a2 + 35));
              v14 = v18;
              if ( !((unsigned int (__fastcall *)(_QWORD, _QWORD, __int64))ProcAddress)(0, *((_QWORD *)a2 + 35), v18) )
              {
                v15 = GetLastError();
                v12 = v15;
                if ( v15 > 0 )
                  v12 = (unsigned __int16)v15 | 0x80070000;
                PushButtonReset::Logging::TraceErr(
                  2,
                  (unsigned int)v12,
                  "WinREAgent::Repartition::InternalExecute",
                  "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
                  731,
                  L"Failed to install WinRE");
              }
              v13 = (ATL::CStringData *)(v14 - 24);
            }
            else
            {
              PushButtonReset::Logging::TraceErr(
                2,
                (unsigned int)v12,
                "WinREAgent::Repartition::InternalExecute",
                "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
                724,
                L"Failed to create new WinRE partition");
              v13 = (ATL::CStringData *)(v18 - 24);
            }
            ATL::CStringData::Release(v13);
          }
          else
          {
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)v12,
              "WinREAgent::Repartition::InternalExecute",
              "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
              719,
              L"Failed to delete WinRE partition");
          }
        }
        else
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)v12,
            "WinREAgent::Repartition::InternalExecute",
            "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
            715,
            L"Failed to shrink OS");
        }
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v12,
          "WinREAgent::Repartition::InternalExecute",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
          706,
          L"Failed to verify the scheduled method");
      }
      v7 = v12;
      goto LABEL_30;
    }
    v10 = GetLastError();
    if ( v10 > 0 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v10,
      "WinREAgent::Repartition::InternalExecute",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
      700,
      L"Failed to load function from DLL");
    v11 = GetLastError();
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    v7 = v11;
  }
LABEL_30:
  v19[0] = (__int64)&RAII::CAutoFreeLibrary::`vftable';
  RAII::CAutoFreeLibrary::Release((RAII::CAutoFreeLibrary *)v19);
  return v7;
}

```

## disassembly

```asm
0x180025ef0  mov     [rsp-28h+arg_10], rbx
0x180025ef5  push    rbp
0x180025ef6  push    rsi
0x180025ef7  push    rdi
0x180025ef8  push    r14
0x180025efa  push    r15
0x180025efc  mov     rbp, rsp
0x180025eff  sub     rsp, 60h
0x180025f03  mov     rax, cs:__security_cookie
0x180025f0a  xor     rax, rsp
0x180025f0d  mov     [rbp+var_10], rax
0x180025f11  mov     rdi, rdx
0x180025f14  mov     rbx, rcx
0x180025f17  lea     rdx, aRepartitionRep; "Repartition: Repartition to extend WinR"...
0x180025f1e  xor     ecx, ecx
0x180025f20  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180025f25  xor     r8d, r8d; dwFlags
0x180025f28  xor     edx, edx; hFile
0x180025f2a  lea     rcx, LibFileName; "ReAgent.dll"
0x180025f31  call    cs:__imp_LoadLibraryExW
0x180025f37  mov     [rbp+var_18], rax
0x180025f3b  lea     r15, ??_7CAutoFreeLibrary@RAII@@6B@; const RAII::CAutoFreeLibrary::`vftable'
0x180025f42  mov     [rbp+var_20], r15
0x180025f46  lea     rcx, [rbp+var_20]
0x180025f4a  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x180025f4f  test    al, al
0x180025f51  jz      short loc_180025FAF
0x180025f53  call    cs:__imp_GetLastError
0x180025f59  mov     edi, 80070000h
0x180025f5e  test    eax, eax
0x180025f60  jle     short loc_180025F67
0x180025f62  movzx   eax, ax
0x180025f65  or      eax, edi
0x180025f67  lea     rcx, aFailedToLoadRe; "Failed to load ReAgent.dll"
0x180025f6e  mov     [rsp+60h+var_38], rcx
0x180025f73  mov     [rsp+60h+var_40], 2B4h
0x180025f7b  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180025f82  lea     r8, aWinreagentRepa_1; "WinREAgent::Repartition::InternalExecut"...
0x180025f89  mov     edx, eax
0x180025f8b  mov     ecx, 2
0x180025f90  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180025f95  call    cs:__imp_GetLastError
0x180025f9b  mov     ebx, eax
0x180025f9d  test    eax, eax
0x180025f9f  jle     loc_1800261E9
0x180025fa5  movzx   ebx, ax
0x180025fa8  or      ebx, edi
0x180025faa  jmp     loc_1800261E9
0x180025faf  mov     rax, [rbp+var_20]
0x180025fb3  lea     rcx, [rbp+var_20]
0x180025fb7  mov     rax, [rax+20h]
0x180025fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025fc0  mov     rcx, rax; hModule
0x180025fc3  lea     rdx, aWinreinstallta; "WinReInstallTarget"
0x180025fca  call    cs:__imp_GetProcAddress
0x180025fd0  mov     r14, rax
0x180025fd3  test    rax, rax
0x180025fd6  jnz     short loc_180026030
0x180025fd8  call    cs:__imp_GetLastError
0x180025fde  mov     edi, 80070000h
0x180025fe3  test    eax, eax
0x180025fe5  jle     short loc_180025FEC
0x180025fe7  movzx   eax, ax
0x180025fea  or      eax, edi
0x180025fec  lea     rcx, aFailedToLoadFu; "Failed to load function from DLL"
0x180025ff3  mov     [rsp+60h+var_38], rcx
0x180025ff8  mov     [rsp+60h+var_40], 2BCh
0x180026000  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180026007  lea     r8, aWinreagentRepa_1; "WinREAgent::Repartition::InternalExecut"...
0x18002600e  mov     edx, eax
0x180026010  mov     ecx, 2
0x180026015  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002601a  call    cs:__imp_GetLastError
0x180026020  test    eax, eax
0x180026022  jle     short loc_180026029
0x180026024  movzx   eax, ax
0x180026027  or      eax, edi
0x180026029  mov     ebx, eax
0x18002602b  jmp     loc_1800261E9
0x180026030  mov     [rbp+var_30], 0
0x180026034  lea     r8, [rbp+var_30]; bool *
0x180026038  mov     rdx, rdi; struct WinREAgent::ExecutionContext *
0x18002603b  mov     rcx, rbx; this
0x18002603e  call    ?VerifyScheduledMethod@Repartition@WinREAgent@@AEAAJPEBVExecutionContext@2@AEA_N@Z; WinREAgent::Repartition::VerifyScheduledMethod(WinREAgent::ExecutionContext const *,bool &)
0x180026043  mov     esi, eax
0x180026045  test    eax, eax
0x180026047  jns     short loc_18002607C
0x180026049  lea     rax, aFailedToVerify_0; "Failed to verify the scheduled method"
0x180026050  mov     [rsp+60h+var_38], rax
0x180026055  mov     [rsp+60h+var_40], 2C2h
0x18002605d  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180026064  lea     r8, aWinreagentRepa_1; "WinREAgent::Repartition::InternalExecut"...
0x18002606b  mov     edx, esi
0x18002606d  mov     ecx, 2
0x180026072  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180026077  jmp     loc_1800261E7
0x18002607c  cmp     [rbp+var_30], 0
0x180026080  jnz     short loc_1800260BD
0x180026082  lea     rax, aCannotExecuteT_1; "Cannot execute the scheduled method"
0x180026089  mov     [rsp+60h+var_38], rax
0x18002608e  mov     [rsp+60h+var_40], 2C6h
0x180026096  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002609d  lea     r8, aWinreagentRepa_1; "WinREAgent::Repartition::InternalExecut"...
0x1800260a4  mov     edx, 80004005h
0x1800260a9  mov     ecx, 2
0x1800260ae  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800260b3  mov     ebx, 80004005h
0x1800260b8  jmp     loc_1800261E9
0x1800260bd  mov     rdx, rdi; struct WinREAgent::ExecutionContext *
0x1800260c0  mov     rcx, rbx; this
0x1800260c3  call    ?ExecuteShrink@Repartition@WinREAgent@@AEAAJPEBVExecutionContext@2@@Z; WinREAgent::Repartition::ExecuteShrink(WinREAgent::ExecutionContext const *)
0x1800260c8  mov     esi, eax
0x1800260ca  test    eax, eax
0x1800260cc  jns     short loc_1800260E7
0x1800260ce  lea     rax, aFailedToShrink_0; "Failed to shrink OS"
0x1800260d5  mov     [rsp+60h+var_38], rax
0x1800260da  mov     [rsp+60h+var_40], 2CBh
0x1800260e2  jmp     loc_18002605D
0x1800260e7  mov     rdx, rdi; struct WinREAgent::ExecutionContext *
0x1800260ea  mov     rcx, rbx; this
0x1800260ed  call    ?ExecuteDeleteWinREPartition@Repartition@WinREAgent@@AEAAJPEBVExecutionContext@2@@Z; WinREAgent::Repartition::ExecuteDeleteWinREPartition(WinREAgent::ExecutionContext const *)
0x1800260f2  mov     esi, eax
0x1800260f4  test    eax, eax
0x1800260f6  jns     short loc_180026111
0x1800260f8  lea     rax, aFailedToDelete_10; "Failed to delete WinRE partition"
0x1800260ff  mov     [rsp+60h+var_38], rax
0x180026104  mov     [rsp+60h+var_40], 2CFh
0x18002610c  jmp     loc_18002605D
0x180026111  lea     rcx, [rbp+var_28]
0x180026115  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002611a  nop
0x18002611b  lea     r8, [rbp+var_28]
0x18002611f  mov     rdx, rdi
0x180026122  mov     rcx, rbx
0x180026125  call    ?ExecuteCreateWinREPartition@Repartition@WinREAgent@@AEAAJPEBVExecutionContext@2@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WinREAgent::Repartition::ExecuteCreateWinREPartition(WinREAgent::ExecutionContext const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18002612a  mov     esi, eax
0x18002612c  test    eax, eax
0x18002612e  jns     short loc_180026169
0x180026130  lea     rax, aFailedToCreate_23; "Failed to create new WinRE partition"
0x180026137  mov     [rsp+60h+var_38], rax
0x18002613c  mov     [rsp+60h+var_40], 2D4h
0x180026144  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002614b  lea     r8, aWinreagentRepa_1; "WinREAgent::Repartition::InternalExecut"...
0x180026152  mov     edx, esi
0x180026154  mov     ecx, 2
0x180026159  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002615e  nop
0x18002615f  mov     rcx, [rbp+var_28]
0x180026163  add     rcx, 0FFFFFFFFFFFFFFE8h
0x180026167  jmp     short loc_1800261E2
0x180026169  mov     r8, [rdi+118h]
0x180026170  lea     rdx, aRepartitionIns; "Repartition: Install WinRE from [%s]"
0x180026177  xor     ecx, ecx
0x180026179  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002617e  mov     rbx, [rbp+var_28]
0x180026182  mov     r8, rbx
0x180026185  mov     rdx, [rdi+118h]
0x18002618c  xor     ecx, ecx
0x18002618e  mov     rax, r14
0x180026191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026196  test    eax, eax
0x180026198  jnz     short loc_1800261DE
0x18002619a  call    cs:__imp_GetLastError
0x1800261a0  mov     esi, eax
0x1800261a2  test    eax, eax
0x1800261a4  jle     short loc_1800261AF
0x1800261a6  movzx   esi, ax
0x1800261a9  or      esi, 80070000h
0x1800261af  lea     rax, aFailedToInstal_0; "Failed to install WinRE"
0x1800261b6  mov     [rsp+60h+var_38], rax
0x1800261bb  mov     [rsp+60h+var_40], 2DBh
0x1800261c3  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800261ca  lea     r8, aWinreagentRepa_1; "WinREAgent::Repartition::InternalExecut"...
0x1800261d1  mov     edx, esi
0x1800261d3  mov     ecx, 2
0x1800261d8  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800261dd  nop
0x1800261de  lea     rcx, [rbx-18h]; this
0x1800261e2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800261e7  mov     ebx, esi
0x1800261e9  mov     [rbp+var_20], r15
0x1800261ed  lea     rcx, [rbp+var_20]; this
0x1800261f1  call    ?Release@CAutoFreeLibrary@RAII@@UEAAXXZ; RAII::CAutoFreeLibrary::Release(void)
0x1800261f6  mov     eax, ebx
0x1800261f8  mov     rcx, [rbp+var_10]
0x1800261fc  xor     rcx, rsp; StackCookie
0x1800261ff  call    __security_check_cookie
0x180026204  mov     rbx, [rsp+60h+arg_10]
0x18002620c  add     rsp, 60h
0x180026210  pop     r15
0x180026212  pop     r14
0x180026214  pop     rdi
0x180026215  pop     rsi
0x180026216  pop     rbp
0x180026217  retn
```
