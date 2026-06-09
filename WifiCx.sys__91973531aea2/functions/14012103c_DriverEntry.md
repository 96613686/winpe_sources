# DriverEntry

- ea: `0x14012103c`
- end: `0x140121480`
- name: `DriverEntry`
- size: `1092`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting`

## callers

- `0x1400da144`

## callees

- `0x140004d48`
- `0x14000c778`
- `0x14001eed0`
- `0x1400357b0`
- `0x1400358a8`
- `0x1400358ec`
- `0x14004bc18`
- `0x14004bc8c`
- `0x1400d8f48`
- `0x1400d91ac`
- `0x1400d93f8`
- `0x1400dd4c0`
- `0x1400dfd00`
- `0x1400dfd40`
- `0x14011f664`
- `0x14011f710`
- `0x14011f744`
- `0x14011f7f8`
- `0x14011f8c0`
- `0x14011fd30`
- `0x140120a58`
- `0x140120b98`
- `0x14012103c`
- `0x140121488`

## import_xrefs

- `WDFLDR!WdfRegisterClassLibrary` at `0x14012135b`
- `WDFLDR!WdfRegisterClassLibrary` at `0x14012135b`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int IsEnabledDeviceUsageNoInline; // eax
  char v5; // di
  int v6; // edx
  int v7; // eax
  int v8; // edx
  NTSTATUS v9; // ebx
  int v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edx
  int v14; // r8d
  int v15; // eax
  int v16; // edx
  int v17; // r9d
  int v18; // eax
  struct _UNICODE_STRING *v19; // rdx
  struct _DRIVER_OBJECT *v20; // rcx
  int v21; // r8d
  int v22; // eax
  int v23; // edx
  __int64 v24; // rcx
  int v25; // r9d
  wificx::utils::power *v26; // rcx
  wificx::utils::power *v27; // rcx
  __int64 v29; // [rsp+28h] [rbp-D8h]
  __int64 v30; // [rsp+28h] [rbp-D8h]
  __int64 v31; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING v33; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v34; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v35; // [rsp+70h] [rbp-90h]
  char v36; // [rsp+80h] [rbp-80h] BYREF

  wil_InitializeFeatureStaging();
  IsEnabledDeviceUsageNoInline = Feature_MoveToWDFMemory__private_IsEnabledDeviceUsageNoInline();
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.NextDevice = 0;
  g_Feature_56544556_MoveToWDFMemory_IsEnabled = IsEnabledDeviceUsageNoInline != 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_WdiLibraryCtlGuid;
  WPP_MAIN_CB.CurrentIrp = 0;
  v5 = 1;
  WPP_MAIN_CB.DeviceType = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WPP_MAIN_CB.DeviceExtension = 0;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm(DriverObject, RegistryPath);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 4;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      1,
      10,
      (__int64)WPP_0a52b5e0107939a20782544ea4bfaf3b_Traceguids,
      131086);
  }
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_14010EC48);
  v7 = TlgRegisterAggregateProvider();
  v9 = v7;
  if ( v7 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v29) = v7;
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        1,
        11,
        (__int64)WPP_0a52b5e0107939a20782544ea4bfaf3b_Traceguids,
        v29);
    }
    goto LABEL_44;
  }
  wlan::parsers::g_wlanParsersLogger = (const struct _tlgProvider_t *const)&dword_14010EBA8;
  v10 = InitializeTelemetryAssertsKMByDriverObject((__int64)DriverObject);
  v9 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v29) = v10;
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        1,
        12,
        (__int64)WPP_0a52b5e0107939a20782544ea4bfaf3b_Traceguids,
        v29);
    }
    goto LABEL_43;
  }
  v34 = 0;
  v35 = 0;
  if ( WdfClientVersionHigherThanFramework )
  {
    if ( (unsigned int)WdfStructureCount <= 0x18 )
      LODWORD(v34) = -1;
    else
      LODWORD(v34) = *(_DWORD *)(WdfStructures + 192);
  }
  else
  {
    LODWORD(v34) = 32;
  }
  *((_QWORD *)&v34 + 1) = 0;
  *(_QWORD *)&v35 = EvtDriverUnload;
  DWORD2(v35) = 1;
  v32 = 0;
  v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _DRIVER_OBJECT *, PUNICODE_STRING, _QWORD, __int128 *, __int64 *))(WdfFunctions_01031 + 928))(
          WdfDriverGlobals,
          DriverObject,
          RegistryPath,
          0,
          &v34,
          &v32);
  v9 = v12;
  if ( v12 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        v14,
        13,
        (__int64)WPP_0a52b5e0107939a20782544ea4bfaf3b_Traceguids,
        (char)DriverObject,
        v12);
    }
    goto LABEL_42;
  }
  v31 = 0x100000008LL;
  v15 = ((__int64 (__fastcall *)(PNET_DRIVER_GLOBALS, __int64, __int64 *))qword_140110E40)(NetDriverGlobals, v32, &v31);
  v9 = v15;
  if ( v15 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_42:
      UninitializeTelemetryAssertsKM();
LABEL_43:
      TlgUnregisterAggregateProvider();
LABEL_44:
      TraceLoggingUnregister_EtwUnregister(&dword_14010EC48);
      WppCleanupKm(DriverObject);
      wil_UninitializeFeatureStaging();
      return v9;
    }
    v17 = 14;
LABEL_20:
    LODWORD(v30) = v15;
    LOBYTE(v16) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v16,
      1,
      v17,
      (__int64)WPP_0a52b5e0107939a20782544ea4bfaf3b_Traceguids,
      v30);
    goto LABEL_42;
  }
  *(_QWORD *)&v33.Length = 13107200;
  v33.Buffer = (wchar_t *)&v36;
  v15 = CreateControlDevice(&v33);
  v9 = v15;
  if ( v15 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_42;
    v17 = 15;
    goto LABEL_20;
  }
  v18 = WdfRegisterClassLibrary(&WdfClassLibraryInfo, RegistryPath, &v33);
  v9 = v18;
  if ( v18 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v19) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v19,
        v21,
        16,
        (__int64)WPP_0a52b5e0107939a20782544ea4bfaf3b_Traceguids,
        v32,
        v18);
    }
    goto LABEL_41;
  }
  v22 = WdiInitialize(v20, v19);
  v9 = v22;
  if ( v22 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v25 = 17;
LABEL_39:
      LODWORD(v30) = v22;
      LOBYTE(v23) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v23,
        1,
        v25,
        (__int64)WPP_0a52b5e0107939a20782544ea4bfaf3b_Traceguids,
        v30);
      goto LABEL_40;
    }
    goto LABEL_40;
  }
  if ( (unsigned int)Feature_55721363__private_IsEnabledDeviceUsageNoInline(v24) )
  {
    v22 = wificx::utils::power::InitializePowerHelper(v26);
    v9 = v22;
    if ( v22 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v25 = 18;
        goto LABEL_39;
      }
LABEL_40:
      WdiCleanup();
LABEL_41:
      DeleteControlDevice();
      goto LABEL_42;
    }
  }
  else
  {
    v5 = 0;
  }
  if ( !(unsigned int)Feature_55721363__private_IsEnabledDeviceUsageNoInline(v26) && v5 )
    wificx::utils::power::DeinitializePowerHelper(v27);
  return 0;
}

```

## disassembly

```asm
0x14012103c  mov     [rsp-8+arg_10], rbx
0x140121041  mov     [rsp-8+arg_18], rsi
0x140121046  push    rbp
0x140121047  push    rdi
0x140121048  push    r12
0x14012104a  push    r13
0x14012104c  push    r14
0x14012104e  lea     rbp, [rsp-60h]
0x140121053  sub     rsp, 160h
0x14012105a  mov     rax, cs:__security_cookie
0x140121061  xor     rax, rsp
0x140121064  mov     [rbp+80h+var_30], rax
0x140121068  mov     r14, rdx
0x14012106b  mov     rsi, rcx
0x14012106e  call    wil_InitializeFeatureStaging
0x140121073  call    Feature_MoveToWDFMemory__private_IsEnabledDeviceUsageNoInline
0x140121078  test    eax, eax
0x14012107a  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x140121085  lea     rax, WPP_ThisDir_CTLGUID_WdiLibraryCtlGuid
0x14012108c  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x140121097  setnz   cs:?g_Feature_56544556_MoveToWDFMemory_IsEnabled@@3_NA; bool g_Feature_56544556_MoveToWDFMemory_IsEnabled
0x14012109e  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1401210a5  xor     eax, eax
0x1401210a7  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x1401210b2  mov     edi, 1
0x1401210b7  mov     cs:WPP_MAIN_CB.DeviceType, eax
0x1401210bd  mov     cs:WPP_MAIN_CB.Timer, rdi
0x1401210c4  mov     cs:WPP_MAIN_CB.DeviceExtension, 0
0x1401210cf  call    WppLoadTracingSupport
0x1401210d4  mov     rdx, r14
0x1401210d7  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x1401210e2  mov     rcx, rsi
0x1401210e5  call    WppInitKm
0x1401210ea  lea     r12, WPP_RECORDER_INITIALIZED
0x1401210f1  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401210f8  lea     r13, WPP_0a52b5e0107939a20782544ea4bfaf3b_Traceguids
0x1401210ff  jz      short loc_140121127
0x140121101  mov     rcx, cs:WPP_GLOBAL_Control
0x140121108  lea     r9d, [rdi+9]
0x14012110c  mov     dword ptr [rsp+180h+var_158], 2000Eh
0x140121114  mov     r8d, edi
0x140121117  mov     dl, 4
0x140121119  mov     [rsp+180h+var_160], r13
0x14012111e  mov     rcx, [rcx+40h]
0x140121122  call    WPP_RECORDER_SF_d
0x140121127  xor     r8d, r8d
0x14012112a  lea     rcx, dword_14010EC48; CallbackContext
0x140121131  xor     edx, edx
0x140121133  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140121138  call    TlgRegisterAggregateProvider
0x14012113d  mov     ebx, eax
0x14012113f  test    eax, eax
0x140121141  jns     short loc_140121179
0x140121143  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14012114a  jz      loc_140121460
0x140121150  mov     rcx, cs:WPP_GLOBAL_Control
0x140121157  mov     r9d, 0Bh
0x14012115d  mov     dword ptr [rsp+180h+var_158], eax
0x140121161  mov     r8d, edi
0x140121164  mov     dl, 2
0x140121166  mov     [rsp+180h+var_160], r13
0x14012116b  mov     rcx, [rcx+40h]
0x14012116f  call    WPP_RECORDER_SF_d
0x140121174  jmp     loc_140121460
0x140121179  lea     rax, dword_14010EBA8
0x140121180  mov     rcx, rsi
0x140121183  mov     cs:?g_wlanParsersLogger@parsers@wlan@@3PEBU_tlgProvider_t@@EB, rax; _tlgProvider_t const * const wlan::parsers::g_wlanParsersLogger
0x14012118a  call    InitializeTelemetryAssertsKMByDriverObject
0x14012118f  mov     ebx, eax
0x140121191  test    eax, eax
0x140121193  jns     short loc_1401211CB
0x140121195  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14012119c  jz      loc_14012145B
0x1401211a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1401211a9  mov     r9d, 0Ch
0x1401211af  mov     dword ptr [rsp+180h+var_158], eax
0x1401211b3  mov     r8d, edi
0x1401211b6  mov     dl, 2
0x1401211b8  mov     [rsp+180h+var_160], r13
0x1401211bd  mov     rcx, [rcx+40h]
0x1401211c1  call    WPP_RECORDER_SF_d
0x1401211c6  jmp     loc_14012145B
0x1401211cb  cmp     cs:WdfClientVersionHigherThanFramework, 0
0x1401211d2  xorps   xmm0, xmm0
0x1401211d5  movups  [rsp+180h+var_120], xmm0
0x1401211da  movups  [rsp+180h+var_110], xmm0
0x1401211df  jz      short loc_140121207
0x1401211e1  cmp     cs:WdfStructureCount, 18h
0x1401211e8  jbe     short loc_1401211FD
0x1401211ea  mov     rax, cs:WdfStructures
0x1401211f1  mov     ecx, [rax+0C0h]
0x1401211f7  mov     dword ptr [rsp+180h+var_120], ecx
0x1401211fb  jmp     short loc_14012120F
0x1401211fd  mov     dword ptr [rsp+180h+var_120], 0FFFFFFFFh
0x140121205  jmp     short loc_14012120F
0x140121207  mov     dword ptr [rsp+180h+var_120], 20h ; ' '
0x14012120f  lea     rax, EvtDriverUnload
0x140121216  mov     qword ptr [rsp+180h+var_120+8], 0
0x14012121f  mov     qword ptr [rsp+180h+var_110], rax
0x140121224  lea     rcx, [rsp+180h+var_138]
0x140121229  mov     rax, cs:WdfFunctions_01031
0x140121230  xor     r9d, r9d
0x140121233  mov     [rsp+180h+var_158], rcx
0x140121238  mov     r8, r14
0x14012123b  lea     rcx, [rsp+180h+var_120]
0x140121240  mov     dword ptr [rsp+180h+var_110+8], edi
0x140121244  mov     [rsp+180h+var_138], 0
0x14012124d  mov     rdx, rsi
0x140121250  mov     rax, [rax+3A0h]
0x140121257  mov     [rsp+180h+var_160], rcx
0x14012125c  mov     rcx, cs:WdfDriverGlobals
0x140121263  call    _guard_dispatch_icall
0x140121268  mov     ebx, eax
0x14012126a  test    eax, eax
0x14012126c  jns     short loc_1401212A6
0x14012126e  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140121275  jz      loc_140121456
0x14012127b  mov     rcx, cs:WPP_GLOBAL_Control
0x140121282  mov     r9d, 0Dh
0x140121288  mov     [rsp+180h+var_150], eax
0x14012128c  mov     dl, 2
0x14012128e  mov     [rsp+180h+var_158], rsi
0x140121293  mov     [rsp+180h+var_160], r13
0x140121298  mov     rcx, [rcx+40h]
0x14012129c  call    WPP_RECORDER_SF_qD
0x1401212a1  jmp     loc_140121456
0x1401212a6  mov     rax, cs:qword_140110E40
0x1401212ad  lea     r8, [rsp+180h+var_140]
0x1401212b2  mov     rdx, [rsp+180h+var_138]
0x1401212b7  mov     rcx, cs:NetDriverGlobals
0x1401212be  mov     [rsp+180h+var_140], 0
0x1401212c7  mov     dword ptr [rsp+180h+var_140], 8
0x1401212cf  mov     byte ptr [rsp+180h+var_140+4], dil
0x1401212d4  call    _guard_dispatch_icall
0x1401212d9  mov     ebx, eax
0x1401212db  test    eax, eax
0x1401212dd  jns     short loc_140121315
0x1401212df  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401212e6  jz      loc_140121456
0x1401212ec  mov     r9d, 0Eh
0x1401212f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1401212f9  mov     r8d, edi
0x1401212fc  mov     dword ptr [rsp+180h+var_158], eax
0x140121300  mov     dl, 2
0x140121302  mov     [rsp+180h+var_160], r13
0x140121307  mov     rcx, [rcx+40h]
0x14012130b  call    WPP_RECORDER_SF_d
0x140121310  jmp     loc_140121456
0x140121315  lea     rax, [rbp+80h+var_100]
0x140121319  mov     qword ptr [rsp+180h+var_130.Length], 0C80000h
0x140121322  lea     rcx, [rsp+180h+var_130]; struct _UNICODE_STRING *
0x140121327  mov     [rsp+180h+var_130.Buffer], rax
0x14012132c  call    CreateControlDevice
0x140121331  mov     ebx, eax
0x140121333  test    eax, eax
0x140121335  jns     short loc_14012134C
0x140121337  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14012133e  jz      loc_140121456
0x140121344  mov     r9d, 0Fh
0x14012134a  jmp     short loc_1401212F2
0x14012134c  lea     r8, [rsp+180h+var_130]
0x140121351  mov     rdx, r14
0x140121354  lea     rcx, ?WdfClassLibraryInfo@@3U_WDF_CLASS_LIBRARY_INFO@@A; _WDF_CLASS_LIBRARY_INFO WdfClassLibraryInfo
0x14012135b  call    cs:__imp_WdfRegisterClassLibrary
0x140121362  nop     dword ptr [rax+rax+00h]
0x140121367  mov     ebx, eax
0x140121369  test    eax, eax
0x14012136b  jns     short loc_1401213AA
0x14012136d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140121374  jz      loc_140121451
0x14012137a  mov     rcx, [rsp+180h+var_138]
0x14012137f  mov     r9d, 10h
0x140121385  mov     [rsp+180h+var_150], eax
0x140121389  mov     dl, 2
0x14012138b  mov     [rsp+180h+var_158], rcx
0x140121390  mov     rcx, cs:WPP_GLOBAL_Control
0x140121397  mov     [rsp+180h+var_160], r13
0x14012139c  mov     rcx, [rcx+40h]
0x1401213a0  call    WPP_RECORDER_SF_qD
0x1401213a5  jmp     loc_140121451
0x1401213aa  call    ?WdiInitialize@@YAJPEAU_DRIVER_OBJECT@@PEAU_UNICODE_STRING@@@Z; WdiInitialize(_DRIVER_OBJECT *,_UNICODE_STRING *)
0x1401213af  mov     ebx, eax
0x1401213b1  test    eax, eax
0x1401213b3  jns     short loc_1401213CA
0x1401213b5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401213bc  jz      loc_14012144C
0x1401213c2  mov     r9d, 11h
0x1401213c8  jmp     short loc_14012142E
0x1401213ca  call    Feature_55721363__private_IsEnabledDeviceUsageNoInline
0x1401213cf  test    eax, eax
0x1401213d1  jnz     short loc_140121414
0x1401213d3  xor     dil, dil
0x1401213d6  call    Feature_55721363__private_IsEnabledDeviceUsageNoInline
0x1401213db  test    eax, eax
0x1401213dd  jnz     short loc_1401213E9
0x1401213df  test    dil, dil
0x1401213e2  jz      short loc_1401213E9
0x1401213e4  call    ?DeinitializePowerHelper@power@utils@wificx@@YAXXZ; wificx::utils::power::DeinitializePowerHelper(void)
0x1401213e9  xor     eax, eax
0x1401213eb  mov     rcx, [rbp+80h+var_30]
0x1401213ef  xor     rcx, rsp; StackCookie
0x1401213f2  call    __security_check_cookie
0x1401213f7  lea     r11, [rsp+180h+var_20]
0x1401213ff  mov     rbx, [r11+40h]
0x140121403  mov     rsi, [r11+48h]
0x140121407  mov     rsp, r11
0x14012140a  pop     r14
0x14012140c  pop     r13
0x14012140e  pop     r12
0x140121410  pop     rdi
0x140121411  pop     rbp
0x140121412  retn
0x140121414  call    ?InitializePowerHelper@power@utils@wificx@@YAJXZ; wificx::utils::power::InitializePowerHelper(void)
0x140121419  mov     ebx, eax
0x14012141b  test    eax, eax
0x14012141d  jns     short loc_1401213D6
0x14012141f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140121426  jz      short loc_14012144C
0x140121428  mov     r9d, 12h
0x14012142e  mov     rcx, cs:WPP_GLOBAL_Control
0x140121435  mov     r8d, edi
0x140121438  mov     dword ptr [rsp+180h+var_158], eax
0x14012143c  mov     dl, 2
0x14012143e  mov     [rsp+180h+var_160], r13
0x140121443  mov     rcx, [rcx+40h]
0x140121447  call    WPP_RECORDER_SF_d
0x14012144c  call    ?WdiCleanup@@YAXXZ; WdiCleanup(void)
0x140121451  call    DeleteControlDevice
0x140121456  call    UninitializeTelemetryAssertsKM
0x14012145b  call    TlgUnregisterAggregateProvider
0x140121460  lea     rcx, dword_14010EC48
0x140121467  call    TraceLoggingUnregister_EtwUnregister
0x14012146c  mov     rcx, rsi
0x14012146f  call    WppCleanupKm
0x140121474  call    wil_UninitializeFeatureStaging
0x140121479  mov     eax, ebx
0x14012147b  jmp     loc_1401213EB
```
