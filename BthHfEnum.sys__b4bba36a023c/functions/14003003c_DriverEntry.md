# DriverEntry

- ea: `0x14003003c`
- end: `0x1400302a4`
- name: `DriverEntry`
- size: `616`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting`

## callers

- `0x1400157c4`

## callees

- `0x140001010`
- `0x1400010c4`
- `0x140002458`
- `0x14001a05c`
- `0x14001aafc`
- `0x14001ae00`
- `0x1400285d4`
- `0x140029918`
- `0x140029a00`
- `0x140029ab4`
- `0x140029b7c`
- `0x14002a0b4`
- `0x14003003c`
- `0x1400302ac`

## import_xrefs

- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Initialize` at `0x14003021b`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Initialize` at `0x14003021b`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS RoleConfigurationState; // ebx
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  __int128 v9; // [rsp+40h] [rbp-59h] BYREF
  __int128 v10; // [rsp+50h] [rbp-49h]
  const wchar_t *v11; // [rsp+60h] [rbp-39h] BYREF
  __int64 v12; // [rsp+68h] [rbp-31h] BYREF
  __int128 v13; // [rsp+70h] [rbp-29h] BYREF
  __int128 v14; // [rsp+80h] [rbp-19h]
  __int128 v15; // [rsp+90h] [rbp-9h]
  __int64 v16; // [rsp+A0h] [rbp+7h]
  __int128 v17; // [rsp+A8h] [rbp+Fh] BYREF
  __int64 v18; // [rsp+B8h] [rbp+1Fh]
  __int64 v19; // [rsp+C0h] [rbp+27h]
  __int128 v20; // [rsp+C8h] [rbp+2Fh]
  __int64 *v21; // [rsp+D8h] [rbp+3Fh]
  __int64 v22; // [rsp+110h] [rbp+77h] BYREF
  struct HfpRoleConfigurationSet *v23; // [rsp+118h] [rbp+7Fh] BYREF

  v16 = 0;
  v9 = 0;
  v22 = 0;
  v10 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  RoleConfigurationState = wil_InitializeFeatureStaging();
  if ( RoleConfigurationState >= 0 )
  {
    *(_QWORD *)&WPP_MAIN_CB.Type = 0;
    WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_CtlGuid;
    WPP_MAIN_CB.NextDevice = 0;
    WPP_MAIN_CB.CurrentIrp = 0;
    WPP_MAIN_CB.Timer = (PIO_TIMER)1;
    WPP_MAIN_CB.DeviceExtension = 0;
    WPP_MAIN_CB.DeviceType = 0;
    WppLoadTracingSupport();
    WPP_MAIN_CB.CurrentIrp = 0;
    WppInitKm(DriverObject, RegistryPath);
    InitializeTelemetryAssertsKMByDriverObject((__int64)DriverObject);
    InitializeGlobalContext(DriverObject);
    *(_QWORD *)&v9 = 32;
    *(_QWORD *)&v10 = 0;
    *((_QWORD *)&v9 + 1) = Bus_EvtDeviceAdd;
    v16 = 0;
    *(_QWORD *)&v14 = 0;
    *((_QWORD *)&v10 + 1) = 0x4648544200000000LL;
    *((_QWORD *)&v13 + 1) = Bus_EvtDriverCleanup;
    v15 = 0;
    *(_QWORD *)&v13 = 56;
    *((_QWORD *)&v14 + 1) = 0x100000001LL;
    RoleConfigurationState = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _DRIVER_OBJECT *, PUNICODE_STRING, __int128 *, __int128 *, __int64 *))(WdfFunctions_01015 + 928))(
                               WdfDriverGlobals,
                               DriverObject,
                               RegistryPath,
                               &v13,
                               &v9,
                               &v22);
    if ( RoleConfigurationState < 0 )
    {
      UninitializeTelemetryAssertsKM();
      WppCleanupKm(DriverObject);
      wil_UninitializeFeatureStaging();
    }
  }
  v23 = 0;
  if ( RoleConfigurationState >= 0 )
  {
    v18 = 0;
    v21 = off_140022050;
    v17 = 0;
    LODWORD(v17) = 56;
    v20 = 0;
    v19 = 0x100000001LL;
    RoleConfigurationState = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *, struct HfpRoleConfigurationSet **))(WdfFunctions_01015 + 1624))(
                               WdfDriverGlobals,
                               v22,
                               &v17,
                               &v23);
    if ( RoleConfigurationState >= 0 )
    {
      RoleConfigurationState = GetRoleConfigurationState((GUID *)v23);
      if ( RoleConfigurationState >= 0 )
      {
        SleepstudyHelper_Initialize(&qword_140022628, DriverObject);
        TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140022000);
        if ( (unsigned int)dword_140022000 > 5 )
        {
          if ( (unsigned __int8)tlgKeywordOn(&dword_140022000, 0x400000000000LL) )
          {
            v12 = 33556480;
            v11 = L"BthHfEnum.sys";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
              v5,
              (unsigned int)&byte_14001EDCF,
              v6,
              v7,
              (__int64)&v12,
              (__int64)&v11);
          }
        }
      }
    }
  }
  return RoleConfigurationState;
}

```

## disassembly

```asm
0x14003003c  mov     [rsp-8+arg_0], rbx
0x140030041  mov     [rsp-8+arg_8], rsi
0x140030046  push    rbp
0x140030047  push    rdi
0x140030048  push    r14
0x14003004a  lea     rbp, [rsp-47h]
0x14003004f  sub     rsp, 0E0h
0x140030056  xorps   xmm0, xmm0
0x140030059  xor     eax, eax
0x14003005b  xor     r14d, r14d
0x14003005e  mov     [rbp+57h+var_50], rax
0x140030062  movups  [rbp+57h+var_B0], xmm0
0x140030066  mov     [rbp+57h+arg_10], r14
0x14003006a  mov     rsi, rdx
0x14003006d  movups  [rbp+57h+var_A0], xmm0
0x140030071  mov     rdi, rcx
0x140030074  movups  [rbp+57h+var_80], xmm0
0x140030078  movups  [rbp+57h+var_70], xmm0
0x14003007c  movups  [rbp+57h+var_60], xmm0
0x140030080  call    wil_InitializeFeatureStaging
0x140030085  mov     ebx, eax
0x140030087  test    eax, eax
0x140030089  js      loc_140030197
0x14003008f  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x140030096  mov     qword ptr cs:WPP_MAIN_CB.Type, r14
0x14003009d  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1400300a4  mov     cs:WPP_MAIN_CB.NextDevice, r14
0x1400300ab  mov     cs:WPP_MAIN_CB.CurrentIrp, r14
0x1400300b2  mov     cs:WPP_MAIN_CB.Timer, 1
0x1400300bd  mov     cs:WPP_MAIN_CB.DeviceExtension, r14
0x1400300c4  mov     cs:WPP_MAIN_CB.DeviceType, r14d
0x1400300cb  call    WppLoadTracingSupport
0x1400300d0  mov     rdx, rsi
0x1400300d3  mov     cs:WPP_MAIN_CB.CurrentIrp, r14
0x1400300da  mov     rcx, rdi
0x1400300dd  call    WppInitKm
0x1400300e2  mov     rcx, rdi
0x1400300e5  call    InitializeTelemetryAssertsKMByDriverObject
0x1400300ea  mov     rcx, rdi; struct _DRIVER_OBJECT *
0x1400300ed  call    ?InitializeGlobalContext@@YAXPEAU_DRIVER_OBJECT@@@Z; InitializeGlobalContext(_DRIVER_OBJECT *)
0x1400300f2  xorps   xmm0, xmm0
0x1400300f5  mov     qword ptr [rbp+57h+var_B0], 20h ; ' '
0x1400300fd  movups  [rbp+57h+var_80], xmm0
0x140030101  lea     rax, Bus_EvtDeviceAdd
0x140030108  mov     qword ptr [rbp+57h+var_A0], r14
0x14003010c  mov     qword ptr [rbp+57h+var_B0+8], rax
0x140030110  lea     rcx, [rbp+57h+arg_10]
0x140030114  xor     eax, eax
0x140030116  mov     [rsp+0F0h+var_C8], rcx
0x14003011b  mov     [rbp+57h+var_50], rax
0x14003011f  lea     rcx, [rbp+57h+var_B0]
0x140030123  movups  [rbp+57h+var_70], xmm0
0x140030127  lea     rax, Bus_EvtDriverCleanup
0x14003012e  mov     dword ptr [rbp+57h+var_A0+8], r14d
0x140030132  mov     qword ptr [rbp+57h+var_80+8], rax
0x140030136  lea     r9, [rbp+57h+var_80]
0x14003013a  mov     rax, cs:WdfFunctions_01015
0x140030141  mov     r8, rsi
0x140030144  mov     dword ptr [rbp+57h+var_A0+0Ch], 46485442h
0x14003014b  mov     rdx, rdi
0x14003014e  movups  [rbp+57h+var_60], xmm0
0x140030152  mov     dword ptr [rbp+57h+var_80], 38h ; '8'
0x140030159  mov     dword ptr [rbp+57h+var_70+8], 1
0x140030160  mov     dword ptr [rbp+57h+var_70+0Ch], 1
0x140030167  mov     rax, [rax+3A0h]
0x14003016e  mov     [rsp+0F0h+var_D0], rcx
0x140030173  mov     rcx, cs:WdfDriverGlobals
0x14003017a  call    _guard_dispatch_icall
0x14003017f  mov     ebx, eax
0x140030181  test    eax, eax
0x140030183  jns     short loc_140030197
0x140030185  call    UninitializeTelemetryAssertsKM
0x14003018a  mov     rcx, rdi
0x14003018d  call    WppCleanupKm
0x140030192  call    wil_UninitializeFeatureStaging
0x140030197  mov     [rbp+57h+arg_18], r14
0x14003019b  test    ebx, ebx
0x14003019d  js      loc_140030289
0x1400301a3  mov     rax, cs:off_140022050
0x1400301aa  lea     r9, [rbp+57h+arg_18]
0x1400301ae  mov     rdx, [rbp+57h+arg_10]
0x1400301b2  lea     r8, [rbp+57h+var_48]
0x1400301b6  mov     rcx, cs:WdfDriverGlobals
0x1400301bd  xorps   xmm0, xmm0
0x1400301c0  movups  [rbp+57h+var_38], xmm0
0x1400301c4  mov     [rbp+57h+var_18], rax
0x1400301c8  mov     rax, cs:WdfFunctions_01015
0x1400301cf  movups  [rbp+57h+var_48], xmm0
0x1400301d3  mov     dword ptr [rbp+57h+var_48], 38h ; '8'
0x1400301da  movups  [rbp+57h+var_28], xmm0
0x1400301de  mov     dword ptr [rbp+57h+var_38+8], 1
0x1400301e5  mov     dword ptr [rbp+57h+var_38+0Ch], 1
0x1400301ec  mov     rax, [rax+658h]
0x1400301f3  call    _guard_dispatch_icall
0x1400301f8  mov     ebx, eax
0x1400301fa  test    eax, eax
0x1400301fc  js      loc_140030289
0x140030202  mov     rcx, [rbp+57h+arg_18]; struct HfpRoleConfigurationSet *
0x140030206  call    ?GetRoleConfigurationState@@YAJPEAUHfpRoleConfigurationSet@@@Z; GetRoleConfigurationState(HfpRoleConfigurationSet *)
0x14003020b  mov     ebx, eax
0x14003020d  test    eax, eax
0x14003020f  js      short loc_140030289
0x140030211  mov     rdx, rdi
0x140030214  lea     rcx, qword_140022628
0x14003021b  call    cs:__imp_SleepstudyHelper_Initialize
0x140030222  nop     dword ptr [rax+rax+00h]
0x140030227  lea     rcx, dword_140022000; CallbackContext
0x14003022e  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140030233  mov     eax, cs:dword_140022000
0x140030239  cmp     eax, 5
0x14003023c  jbe     short loc_140030289
0x14003023e  mov     rdx, 400000000000h
0x140030248  lea     rcx, dword_140022000
0x14003024f  call    _tlgKeywordOn
0x140030254  test    al, al
0x140030256  jz      short loc_140030289
0x140030258  lea     rax, aBthhfenumSys; "BthHfEnum.sys"
0x14003025f  mov     [rbp+57h+var_88], 2000800h
0x140030267  mov     [rbp+57h+var_90], rax
0x14003026b  lea     rdx, byte_14001EDCF
0x140030272  lea     rax, [rbp+57h+var_90]
0x140030276  mov     [rsp+0F0h+var_C8], rax
0x14003027b  lea     rax, [rbp+57h+var_88]
0x14003027f  mov     [rsp+0F0h+var_D0], rax
0x140030284  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x140030289  lea     r11, [rsp+0F0h+var_10]
0x140030291  mov     eax, ebx
0x140030293  mov     rbx, [r11+20h]
0x140030297  mov     rsi, [r11+28h]
0x14003029b  mov     rsp, r11
0x14003029e  pop     r14
0x1400302a0  pop     rdi
0x1400302a1  pop     rbp
0x1400302a2  retn
```
