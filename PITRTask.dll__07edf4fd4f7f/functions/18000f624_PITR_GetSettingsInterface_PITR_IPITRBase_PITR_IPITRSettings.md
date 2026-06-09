# PITR::GetSettingsInterface(PITR::IPITRBase *,PITR::IPITRSettings * *)

- ea: `0x18000f624`
- end: `0x18000f8ea`
- name: `?GetSettingsInterface@PITR@@YAJPEAUIPITRBase@1@PEAPEAUIPITRSettings@1@@Z`
- size: `710`
- prototype: `__int64 __fastcall(PITR *__hidden this, struct PITR::IPITRBase *, struct PITR::IPITRSettings **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000a4f0`

## callees

- `0x180004664`
- `0x18000bbd0`
- `0x18000ece8`
- `0x18000eec8`
- `0x18000f624`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f751`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f751`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000f673`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000f673`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f8b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f8b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f680`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f680`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f77b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f827`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f77b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f793`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f827`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f641`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f89b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f8bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f641`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f89b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000f8bd`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000f720`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000f895`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000f720`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000f895`
- `WDSCORE!CurrentIP` at `0x18000f6bd`
- `WDSCORE!CurrentIP` at `0x18000f79b`
- `WDSCORE!CurrentIP` at `0x18000f82f`
- `WDSCORE!CurrentIP` at `0x18000f6bd`
- `WDSCORE!CurrentIP` at `0x18000f79b`
- `WDSCORE!CurrentIP` at `0x18000f82f`

## string_xrefs

- `0x18000f6c3`: `PITR::GetSettingsInterface: Failed to find loaded PITR DLL`

## pseudocode

```c
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
    if ( !_InterlockedCompareExchange(&dword_18001BFB4, 1, 0) )
      InitializeCriticalSection(&stru_18001BFF0);
    EnterCriticalSection(&stru_18001BFF0);
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
    LeaveCriticalSection(&stru_18001BFF0);
    return (unsigned int)v9;
  }
  v25 = GetTickCount();
  PITRTelemetryLogSettingsInterfaceCreation(-2147024809, v25 - TickCount);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000f624  mov     [rsp+arg_8], rbx
0x18000f629  mov     [rsp+arg_10], rbp
0x18000f62e  push    rsi
0x18000f62f  push    rdi
0x18000f630  push    r12
0x18000f632  sub     rsp, 60h
0x18000f636  mov     rbx, rdx
0x18000f639  mov     rdi, rcx
0x18000f63c  call    ?PITRTelemetryInitialize@@YAJXZ; PITRTelemetryInitialize(void)
0x18000f641  call    cs:__imp_GetTickCount
0x18000f647  mov     ebp, eax
0x18000f649  test    rdi, rdi
0x18000f64c  jz      loc_18000F8BD
0x18000f652  test    rbx, rbx
0x18000f655  jz      loc_18000F8BD
0x18000f65b  xor     eax, eax
0x18000f65d  lea     r12d, [rax+1]
0x18000f661  lock cmpxchg cs:dword_18001BFB4, r12d
0x18000f66a  jnz     short loc_18000F679
0x18000f66c  lea     rcx, stru_18001BFF0; lpCriticalSection
0x18000f673  call    cs:__imp_InitializeCriticalSection
0x18000f679  lea     rcx, stru_18001BFF0; lpCriticalSection
0x18000f680  call    cs:__imp_EnterCriticalSection
0x18000f686  mov     rax, cs:?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x18000f68d  lea     rdx, [rsp+78h+arg_0]
0x18000f695  lea     rcx, ?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x18000f69c  mov     [rsp+78h+arg_0], 0
0x18000f6a8  mov     rax, [rax+38h]
0x18000f6ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6b1  test    al, al
0x18000f6b3  jz      short loc_18000F730
0x18000f6b5  call    cs:__imp_GetLastError
0x18000f6bb  mov     edi, eax
0x18000f6bd  call    cs:__imp_CurrentIP
0x18000f6c3  lea     rdx, aPitrGetsetting; "PITR::GetSettingsInterface: Failed to f"...
0x18000f6ca  mov     ecx, 2000000h; unsigned int
0x18000f6cf  mov     rbx, rax
0x18000f6d2  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000f6d7  mov     [rsp+78h+var_28], 0
0x18000f6df  lea     rcx, aPitrGetsetting_2; "PITR::GetSettingsInterface"
0x18000f6e6  mov     [rsp+78h+var_30], 0
0x18000f6ef  lea     r8, aD; "D"
0x18000f6f6  mov     [rsp+78h+var_38], edi
0x18000f6fa  xor     r9d, r9d
0x18000f6fd  mov     [rsp+78h+var_40], rbx
0x18000f702  xor     edx, edx
0x18000f704  mov     [rsp+78h+var_48], rcx
0x18000f709  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x18000f710  mov     [rsp+78h+var_50], rcx
0x18000f715  mov     rcx, rax
0x18000f718  mov     [rsp+78h+var_58], 216h
0x18000f720  call    cs:__imp_WdsSetupLogMessageW
0x18000f726  mov     esi, 8000FFFFh
0x18000f72b  jmp     loc_18000F89B
0x18000f730  mov     rax, cs:?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x18000f737  lea     rcx, ?g_PitrDll@@3VCAutoFreeLibrary@RAII@@A; RAII::CAutoFreeLibrary g_PitrDll
0x18000f73e  mov     rax, [rax+20h]
0x18000f742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f747  mov     rcx, rax; hModule
0x18000f74a  lea     rdx, aGetsettingsint; "GetSettingsInterface_Internal"
0x18000f751  call    cs:__imp_GetProcAddress
0x18000f757  mov     rsi, rax
0x18000f75a  test    rax, rax
0x18000f75d  jnz     loc_18000F7F7
0x18000f763  call    cs:__imp_GetLastError
0x18000f769  mov     ebx, 80070000h
0x18000f76e  test    eax, eax
0x18000f770  jle     short loc_18000F779
0x18000f772  movzx   eax, ax
0x18000f775  or      eax, ebx
0x18000f777  test    eax, eax
0x18000f779  jns     short loc_18000F78E
0x18000f77b  call    cs:__imp_GetLastError
0x18000f781  mov     esi, eax
0x18000f783  test    eax, eax
0x18000f785  jle     short loc_18000F793
0x18000f787  movzx   esi, ax
0x18000f78a  or      esi, ebx
0x18000f78c  jmp     short loc_18000F793
0x18000f78e  mov     esi, 80004005h
0x18000f793  call    cs:__imp_GetLastError
0x18000f799  mov     edi, eax
0x18000f79b  call    cs:__imp_CurrentIP
0x18000f7a1  mov     r8d, esi
0x18000f7a4  lea     rdx, aPitrGetsetting_0; "PITR::GetSettingsInterface: GetProcAddr"...
0x18000f7ab  mov     ecx, 2000000h; unsigned int
0x18000f7b0  mov     rbx, rax
0x18000f7b3  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000f7b8  mov     [rsp+78h+var_28], 0
0x18000f7c0  lea     rcx, aPitrGetsetting_2; "PITR::GetSettingsInterface"
0x18000f7c7  mov     [rsp+78h+var_30], 0
0x18000f7d0  mov     [rsp+78h+var_38], edi
0x18000f7d4  mov     [rsp+78h+var_40], rbx
0x18000f7d9  mov     [rsp+78h+var_48], rcx
0x18000f7de  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x18000f7e5  mov     [rsp+78h+var_50], rcx
0x18000f7ea  mov     [rsp+78h+var_58], 220h
0x18000f7f2  jmp     loc_18000F886
0x18000f7f7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x18000f7fe  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x18000f803  test    al, al
0x18000f805  mov     r8, rbx
0x18000f808  mov     rax, rsi
0x18000f80b  mov     rcx, rdi
0x18000f80e  mov     edx, 2
0x18000f813  jnz     short loc_18000F818
0x18000f815  mov     edx, r12d
0x18000f818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f81d  mov     esi, eax
0x18000f81f  test    eax, eax
0x18000f821  jns     loc_18000F8AC
0x18000f827  call    cs:__imp_GetLastError
0x18000f82d  mov     edi, eax
0x18000f82f  call    cs:__imp_CurrentIP
0x18000f835  mov     r8d, esi
0x18000f838  lea     rdx, aPitrGetsetting_1; "PITR::GetSettingsInterface: GetSettings"...
0x18000f83f  mov     ecx, 2000000h; unsigned int
0x18000f844  mov     rbx, rax
0x18000f847  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000f84c  mov     [rsp+78h+var_28], 0
0x18000f854  lea     rcx, aPitrGetsetting_2; "PITR::GetSettingsInterface"
0x18000f85b  mov     [rsp+78h+var_30], 0
0x18000f864  mov     [rsp+78h+var_38], edi
0x18000f868  mov     [rsp+78h+var_40], rbx
0x18000f86d  mov     [rsp+78h+var_48], rcx
0x18000f872  lea     rcx, aBaseDiagnosisS; "base\\diagnosis\\srt\\pitr\\lib\\src\\p"...
0x18000f879  mov     [rsp+78h+var_50], rcx
0x18000f87e  mov     [rsp+78h+var_58], 22Fh
0x18000f886  xor     r9d, r9d
0x18000f889  lea     r8, aD; "D"
0x18000f890  xor     edx, edx
0x18000f892  mov     rcx, rax
0x18000f895  call    cs:__imp_WdsSetupLogMessageW
0x18000f89b  call    cs:__imp_GetTickCount
0x18000f8a1  sub     eax, ebp
0x18000f8a3  mov     ecx, esi; int
0x18000f8a5  mov     edx, eax; unsigned int
0x18000f8a7  call    ?PITRTelemetryLogSettingsInterfaceCreation@@YAXJK@Z; PITRTelemetryLogSettingsInterfaceCreation(long,ulong)
0x18000f8ac  lea     rcx, stru_18001BFF0; lpCriticalSection
0x18000f8b3  call    cs:__imp_LeaveCriticalSection
0x18000f8b9  mov     eax, esi
0x18000f8bb  jmp     short loc_18000F8D5
0x18000f8bd  call    cs:__imp_GetTickCount
0x18000f8c3  sub     eax, ebp
0x18000f8c5  mov     ebx, 80070057h
0x18000f8ca  mov     edx, eax; unsigned int
0x18000f8cc  mov     ecx, ebx; int
0x18000f8ce  call    ?PITRTelemetryLogSettingsInterfaceCreation@@YAXJK@Z; PITRTelemetryLogSettingsInterfaceCreation(long,ulong)
0x18000f8d3  mov     eax, ebx
0x18000f8d5  lea     r11, [rsp+78h+var_18]
0x18000f8da  mov     rbx, [r11+28h]
0x18000f8de  mov     rbp, [r11+30h]
0x18000f8e2  mov     rsp, r11
0x18000f8e5  pop     r12
0x18000f8e7  pop     rdi
0x18000f8e8  pop     rsi
0x18000f8e9  retn
```
