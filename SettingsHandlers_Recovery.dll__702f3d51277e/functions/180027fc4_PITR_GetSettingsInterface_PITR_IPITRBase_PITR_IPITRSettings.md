# PITR::GetSettingsInterface(PITR::IPITRBase *,PITR::IPITRSettings * *)

- ea: `0x180027fc4`
- end: `0x18002828a`
- name: `?GetSettingsInterface@PITR@@YAJPEAUIPITRBase@1@PEAPEAUIPITRSettings@1@@Z`
- size: `710`
- prototype: `__int64 __fastcall(PITR *__hidden this, struct PITR::IPITRBase *, struct PITR::IPITRSettings **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000bfe0`

## callees

- `0x18000bef4`
- `0x1800263d4`
- `0x180027fc4`
- `0x1800284c8`
- `0x180028634`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800280f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800280f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028253`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028253`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028020`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028020`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180028013`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180028013`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028055`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002811b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800281c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028055`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002811b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800281c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180027fe1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002823b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002825d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180027fe1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002823b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002825d`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800280c0`
- `WDSCORE!WdsSetupLogMessageW` at `0x180028235`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800280c0`
- `WDSCORE!WdsSetupLogMessageW` at `0x180028235`
- `WDSCORE!CurrentIP` at `0x18002805d`
- `WDSCORE!CurrentIP` at `0x18002813b`
- `WDSCORE!CurrentIP` at `0x1800281cf`
- `WDSCORE!CurrentIP` at `0x18002805d`
- `WDSCORE!CurrentIP` at `0x18002813b`
- `WDSCORE!CurrentIP` at `0x1800281cf`

## string_xrefs

- `0x180028063`: `PITR::GetSettingsInterface: Failed to find loaded PITR DLL`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PITR::GetSettingsInterface(PITR *this, struct PITR::IPITRBase *a2, struct PITR::IPITRSettings **a3)
{
  DWORD TickCount; // ebp
  DWORD LastError; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  signed int v9; // esi
  HMODULE v10; // rax
  FARPROC ProcAddress; // rsi
  signed int v12; // eax
  bool v13; // sf
  signed int v14; // eax
  DWORD v15; // edi
  __int64 v16; // rbx
  struct tagLOG_PARTIAL_MSG *v17; // rax
  bool v18; // zf
  __int64 v19; // rdx
  DWORD v20; // edi
  __int64 v21; // rbx
  struct tagLOG_PARTIAL_MSG *v22; // rax
  DWORD v23; // eax
  DWORD v25; // eax
  __int64 v26; // [rsp+80h] [rbp+8h] BYREF

  PITRTelemetryInitialize();
  TickCount = GetTickCount();
  if ( this && a2 )
  {
    if ( !_InterlockedCompareExchange(&dword_180059FC0, 1, 0) )
      InitializeCriticalSection(&stru_18005A210);
    EnterCriticalSection(&stru_18005A210);
    v26 = 0;
    if ( ((unsigned __int8 (__fastcall *)(void ***, __int64 *))g_PitrDll[7])(&g_PitrDll, &v26) )
    {
      LastError = GetLastError();
      v7 = CurrentIP();
      v8 = ConstructPartialMsgW(0x2000000u, "PITR::GetSettingsInterface: Failed to find loaded PITR DLL");
      WdsSetupLogMessageW(
        v8,
        0,
        L"D",
        0,
        534,
        L"base\\diagnosis\\srt\\pitr\\lib\\src\\pitr.cpp",
        L"PITR::GetSettingsInterface",
        v7,
        LastError,
        0,
        0);
      v9 = -2147418113;
    }
    else
    {
      v10 = (HMODULE)((__int64 (__fastcall *)(void ***))g_PitrDll[4])(&g_PitrDll);
      ProcAddress = GetProcAddress(v10, "GetSettingsInterface_Internal");
      if ( ProcAddress )
      {
        v18 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) == 0;
        v19 = 2;
        if ( v18 )
          v19 = 1;
        v9 = ((__int64 (__fastcall *)(PITR *, __int64, struct PITR::IPITRBase *))ProcAddress)(this, v19, a2);
        if ( v9 >= 0 )
          goto LABEL_20;
        v20 = GetLastError();
        v21 = CurrentIP();
        v22 = ConstructPartialMsgW(
                0x2000000u,
                "PITR::GetSettingsInterface: GetSettingsInterface_Internal failed. Error: 0x%08X",
                v9);
        WdsSetupLogMessageW(
          v22,
          0,
          L"D",
          0,
          559,
          L"base\\diagnosis\\srt\\pitr\\lib\\src\\pitr.cpp",
          L"PITR::GetSettingsInterface",
          v21,
          v20,
          0,
          0);
      }
      else
      {
        v12 = GetLastError();
        v13 = v12 < 0;
        if ( v12 > 0 )
          v13 = 1;
        if ( v13 )
        {
          v14 = GetLastError();
          v9 = v14;
          if ( v14 > 0 )
            v9 = (unsigned __int16)v14 | 0x80070000;
        }
        else
        {
          v9 = -2147467259;
        }
        v15 = GetLastError();
        v16 = CurrentIP();
        v17 = ConstructPartialMsgW(0x2000000u, "PITR::GetSettingsInterface: GetProcAddress failed. Error: 0x%08X", v9);
        WdsSetupLogMessageW(
          v17,
          0,
          L"D",
          0,
          544,
          L"base\\diagnosis\\srt\\pitr\\lib\\src\\pitr.cpp",
          L"PITR::GetSettingsInterface",
          v16,
          v15,
          0,
          0);
      }
    }
    v23 = GetTickCount();
    PITRTelemetryLogSettingsInterfaceCreation(v9, v23 - TickCount);
LABEL_20:
    LeaveCriticalSection(&stru_18005A210);
    return (unsigned int)v9;
  }
  v25 = GetTickCount();
  PITRTelemetryLogSettingsInterfaceCreation(-2147024809, v25 - TickCount);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180027fc4  mov     [rsp+arg_8], rbx
0x180027fc9  mov     [rsp+arg_10], rbp
0x180027fce  push    rsi
0x180027fcf  push    rdi
0x180027fd0  push    r12
0x180027fd2  sub     rsp, 60h
0x180027fd6  mov     rbx, rdx
0x180027fd9  mov     rdi, rcx
0x180027fdc  call    ?PITRTelemetryInitialize@@YAJXZ; PITRTelemetryInitialize(void)
0x180027fe1  call    cs:__imp_GetTickCount
0x180027fe7  mov     ebp, eax
0x180027fe9  test    rdi, rdi
0x180027fec  jz      loc_18002825D
0x180027ff2  test    rbx, rbx
0x180027ff5  jz      loc_18002825D
0x180027ffb  xor     eax, eax
0x180027ffd  lea     r12d, [rax+1]
0x180028001  lock cmpxchg cs:dword_180059FC0, r12d
0x18002800a  jnz     short loc_180028019
0x18002800c  lea     rcx, stru_18005A210; lpCriticalSection
0x180028013  call    cs:__imp_InitializeCriticalSection
0x180028019  lea     rcx, stru_18005A210; lpCriticalSection
0x180028020  call    cs:__imp_EnterCriticalSection
0x180028026  mov     rax, cs:?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x18002802d  lea     rdx, [rsp+78h+arg_0]
0x180028035  lea     rcx, ?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x18002803c  mov     [rsp+78h+arg_0], 0
0x180028048  mov     rax, [rax+38h]
0x18002804c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028051  test    al, al
0x180028053  jz      short loc_1800280D0
0x180028055  call    cs:__imp_GetLastError
0x18002805b  mov     edi, eax
0x18002805d  call    cs:__imp_CurrentIP
0x180028063  lea     rdx, aPitrGetsetting; "PITR::GetSettingsInterface: Failed to f"...
0x18002806a  mov     ecx, 2000000h; unsigned int
0x18002806f  mov     rbx, rax
0x180028072  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180028077  mov     [rsp+78h+var_28], 0
0x18002807f  lea     rcx, aPitrGetsetting_2; "PITR::GetSettingsInterface"
0x180028086  mov     [rsp+78h+var_30], 0
0x18002808f  lea     r8, aD; "D"
0x180028096  mov     [rsp+78h+var_38], edi
0x18002809a  xor     r9d, r9d
0x18002809d  mov     [rsp+78h+var_40], rbx
0x1800280a2  xor     edx, edx
0x1800280a4  mov     [rsp+78h+var_48], rcx
0x1800280a9  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x1800280b0  mov     [rsp+78h+var_50], rcx
0x1800280b5  mov     rcx, rax
0x1800280b8  mov     [rsp+78h+var_58], 216h
0x1800280c0  call    cs:__imp_WdsSetupLogMessageW
0x1800280c6  mov     esi, 8000FFFFh
0x1800280cb  jmp     loc_18002823B
0x1800280d0  mov     rax, cs:?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x1800280d7  lea     rcx, ?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x1800280de  mov     rax, [rax+20h]
0x1800280e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280e7  mov     rcx, rax; hModule
0x1800280ea  lea     rdx, aGetsettingsint; "GetSettingsInterface_Internal"
0x1800280f1  call    cs:__imp_GetProcAddress
0x1800280f7  mov     rsi, rax
0x1800280fa  test    rax, rax
0x1800280fd  jnz     loc_180028197
0x180028103  call    cs:__imp_GetLastError
0x180028109  mov     ebx, 80070000h
0x18002810e  test    eax, eax
0x180028110  jle     short loc_180028119
0x180028112  movzx   eax, ax
0x180028115  or      eax, ebx
0x180028117  test    eax, eax
0x180028119  jns     short loc_18002812E
0x18002811b  call    cs:__imp_GetLastError
0x180028121  mov     esi, eax
0x180028123  test    eax, eax
0x180028125  jle     short loc_180028133
0x180028127  movzx   esi, ax
0x18002812a  or      esi, ebx
0x18002812c  jmp     short loc_180028133
0x18002812e  mov     esi, 80004005h
0x180028133  call    cs:__imp_GetLastError
0x180028139  mov     edi, eax
0x18002813b  call    cs:__imp_CurrentIP
0x180028141  mov     r8d, esi
0x180028144  lea     rdx, aPitrGetsetting_0; "PITR::GetSettingsInterface: GetProcAddr"...
0x18002814b  mov     ecx, 2000000h; unsigned int
0x180028150  mov     rbx, rax
0x180028153  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180028158  mov     [rsp+78h+var_28], 0
0x180028160  lea     rcx, aPitrGetsetting_2; "PITR::GetSettingsInterface"
0x180028167  mov     [rsp+78h+var_30], 0
0x180028170  mov     [rsp+78h+var_38], edi
0x180028174  mov     [rsp+78h+var_40], rbx
0x180028179  mov     [rsp+78h+var_48], rcx
0x18002817e  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x180028185  mov     [rsp+78h+var_50], rcx
0x18002818a  mov     [rsp+78h+var_58], 220h
0x180028192  jmp     loc_180028226
0x180028197  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x18002819e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x1800281a3  test    al, al
0x1800281a5  mov     r8, rbx
0x1800281a8  mov     rax, rsi
0x1800281ab  mov     rcx, rdi
0x1800281ae  mov     edx, 2
0x1800281b3  jnz     short loc_1800281B8
0x1800281b5  mov     edx, r12d
0x1800281b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281bd  mov     esi, eax
0x1800281bf  test    eax, eax
0x1800281c1  jns     loc_18002824C
0x1800281c7  call    cs:__imp_GetLastError
0x1800281cd  mov     edi, eax
0x1800281cf  call    cs:__imp_CurrentIP
0x1800281d5  mov     r8d, esi
0x1800281d8  lea     rdx, aPitrGetsetting_1; "PITR::GetSettingsInterface: GetSettings"...
0x1800281df  mov     ecx, 2000000h; unsigned int
0x1800281e4  mov     rbx, rax
0x1800281e7  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800281ec  mov     [rsp+78h+var_28], 0
0x1800281f4  lea     rcx, aPitrGetsetting_2; "PITR::GetSettingsInterface"
0x1800281fb  mov     [rsp+78h+var_30], 0
0x180028204  mov     [rsp+78h+var_38], edi
0x180028208  mov     [rsp+78h+var_40], rbx
0x18002820d  mov     [rsp+78h+var_48], rcx
0x180028212  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x180028219  mov     [rsp+78h+var_50], rcx
0x18002821e  mov     [rsp+78h+var_58], 22Fh
0x180028226  xor     r9d, r9d
0x180028229  lea     r8, aD; "D"
0x180028230  xor     edx, edx
0x180028232  mov     rcx, rax
0x180028235  call    cs:__imp_WdsSetupLogMessageW
0x18002823b  call    cs:__imp_GetTickCount
0x180028241  sub     eax, ebp
0x180028243  mov     ecx, esi; int
0x180028245  mov     edx, eax; unsigned int
0x180028247  call    ?PITRTelemetryLogSettingsInterfaceCreation@@YAXJK@Z; PITRTelemetryLogSettingsInterfaceCreation(long,ulong)
0x18002824c  lea     rcx, stru_18005A210; lpCriticalSection
0x180028253  call    cs:__imp_LeaveCriticalSection
0x180028259  mov     eax, esi
0x18002825b  jmp     short loc_180028275
0x18002825d  call    cs:__imp_GetTickCount
0x180028263  sub     eax, ebp
0x180028265  mov     ebx, 80070057h
0x18002826a  mov     edx, eax; unsigned int
0x18002826c  mov     ecx, ebx; int
0x18002826e  call    ?PITRTelemetryLogSettingsInterfaceCreation@@YAXJK@Z; PITRTelemetryLogSettingsInterfaceCreation(long,ulong)
0x180028273  mov     eax, ebx
0x180028275  lea     r11, [rsp+78h+var_18]
0x18002827a  mov     rbx, [r11+28h]
0x18002827e  mov     rbp, [r11+30h]
0x180028282  mov     rsp, r11
0x180028285  pop     r12
0x180028287  pop     rdi
0x180028288  pop     rsi
0x180028289  retn
```
