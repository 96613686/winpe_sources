# BthUsb_DriverUnload(_DRIVER_OBJECT *)

- ea: `0x140017008`
- end: `0x140017209`
- name: `?BthUsb_DriverUnload@@YAXPEAU_DRIVER_OBJECT@@@Z`
- size: `513`
- prototype: `void __fastcall(struct _DRIVER_OBJECT *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x140017c30`
- `0x14001d03c`

## callees

- `0x140001008`
- `0x14000175c`
- `0x14000d338`
- `0x14000d580`
- `0x14000de00`
- `0x140017008`

## import_xrefs

- `ntoskrnl!EtwUnregister` at `0x1400170e5`
- `ntoskrnl!EtwUnregister` at `0x140017102`
- `ntoskrnl!EtwUnregister` at `0x1400170e5`
- `ntoskrnl!EtwUnregister` at `0x140017102`
- `ntoskrnl!IoWMIRegistrationControl` at `0x140017199`
- `ntoskrnl!IoWMIRegistrationControl` at `0x140017199`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14001714d`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14001714d`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14001712a`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14001712a`
- `WppRecorder!WppAutoLogStop` at `0x1400171af`
- `WppRecorder!WppAutoLogStop` at `0x1400171af`

## pseudocode

```c
void __fastcall BthUsb_DriverUnload(struct _DRIVER_OBJECT *a1, __int64 a2, int a3)
{
  bool v4; // dl
  int v5; // r8d
  int v6; // r9d
  REGHANDLE v7; // rcx
  PDEVICE_OBJECT v8; // rbx
  const wchar_t *v9; // [rsp+58h] [rbp+10h] BYREF
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  v4 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v4,
    a3,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    2,
    16,
    (__int64)WPP_1f9a50d1de1b36addda1af3e8dc29e49_Traceguids);
  if ( (unsigned int)dword_140013000 > 5
    && (qword_140013010 & 0x400000000000LL) != 0
    && (qword_140013018 & 0x400000000000LL) == qword_140013018 )
  {
    v10 = 33556480;
    v9 = L"BthUsb.sys";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      qword_140013018,
      (unsigned int)byte_140010D11,
      v5,
      v6,
      (__int64)&v10,
      (__int64)&v9);
  }
  v7 = qword_140013020;
  dword_140013000 = 0;
  qword_140013020 = 0;
  EtwUnregister(v7);
  UninitializeTelemetryAssertsKM();
  if ( g_EtwRegHandle )
  {
    EtwUnregister(g_EtwRegHandle);
    g_EtwRegHandle = 0;
  }
  BthLib_Unload();
  if ( g_wil_details_featureChangeNotification )
  {
    RtlUnregisterFeatureConfigurationChangeNotification();
    g_wil_details_featureChangeNotification = 0;
  }
  if ( *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type )
  {
    RtlUnregisterFeatureUsageProvider();
    *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.Type = 0;
  }
  v8 = WPP_GLOBAL_Control;
  g_wil_details_isFeatureStagingInitialized = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.SortKey == 4 )
    {
      while ( v8 )
      {
        if ( v8->Vpb )
        {
          (*(void (**)(void))&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters)();
          v8->Vpb = 0;
        }
        v8 = v8->NextDevice;
      }
    }
    else if ( WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.SortKey == 2 )
    {
      IoWMIRegistrationControl(WPP_GLOBAL_Control, 0x80000002);
    }
    WppAutoLogStop(WPP_GLOBAL_Control, a1);
    WPP_GLOBAL_Control = (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
    WPP_RECORDER_INITIALIZED = &WPP_RECORDER_INITIALIZED;
  }
}

```

## disassembly

```asm
0x140017008  mov     [rsp+arg_0], rbx
0x14001700d  mov     [rsp+arg_18], rbp
0x140017012  push    rdi
0x140017013  sub     rsp, 40h
0x140017017  mov     rdi, rcx
0x14001701a  mov     rcx, cs:WPP_GLOBAL_Control
0x140017021  mov     eax, [rcx+2Ch]
0x140017024  test    al, 2
0x140017026  jz      short loc_140017032
0x140017028  cmp     byte ptr [rcx+29h], 4
0x14001702c  jb      short loc_140017032
0x14001702e  mov     dl, 1
0x140017030  jmp     short loc_140017034
0x140017032  xor     dl, dl
0x140017034  mov     r9, [rcx+40h]
0x140017038  lea     rax, WPP_1f9a50d1de1b36addda1af3e8dc29e49_Traceguids
0x14001703f  mov     rcx, [rcx+18h]
0x140017043  mov     [rsp+48h+var_10], rax
0x140017048  mov     [rsp+48h+var_18], 10h
0x14001704f  mov     dword ptr [rsp+48h+var_20], 2
0x140017057  mov     byte ptr [rsp+48h+var_28], 4
0x14001705c  call    WPP_RECORDER_AND_TRACE_SF_
0x140017061  mov     eax, cs:dword_140013000
0x140017067  cmp     eax, 5
0x14001706a  jbe     short loc_1400170C9
0x14001706c  mov     rcx, cs:qword_140013018
0x140017073  mov     rdx, 400000000000h
0x14001707d  mov     rax, cs:qword_140013010
0x140017084  test    rdx, rax
0x140017087  jz      short loc_1400170C9
0x140017089  mov     rax, rcx
0x14001708c  and     rax, rdx
0x14001708f  cmp     rax, rcx
0x140017092  jnz     short loc_1400170C9
0x140017094  lea     rax, aBthusbSys; "BthUsb.sys"
0x14001709b  mov     [rsp+48h+arg_10], 2000800h
0x1400170a4  mov     [rsp+48h+arg_8], rax
0x1400170a9  lea     rdx, byte_140010D11
0x1400170b0  lea     rax, [rsp+48h+arg_8]
0x1400170b5  mov     [rsp+48h+var_20], rax
0x1400170ba  lea     rax, [rsp+48h+arg_10]
0x1400170bf  mov     [rsp+48h+var_28], rax
0x1400170c4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x1400170c9  mov     rcx, cs:qword_140013020; RegHandle
0x1400170d0  mov     cs:dword_140013000, 0
0x1400170da  mov     cs:qword_140013020, 0
0x1400170e5  call    cs:__imp_EtwUnregister
0x1400170ec  nop     dword ptr [rax+rax+00h]
0x1400170f1  call    UninitializeTelemetryAssertsKM
0x1400170f6  mov     rcx, cs:?g_EtwRegHandle@@3_KA; RegHandle
0x1400170fd  test    rcx, rcx
0x140017100  jz      short loc_140017119
0x140017102  call    cs:__imp_EtwUnregister
0x140017109  nop     dword ptr [rax+rax+00h]
0x14001710e  mov     cs:?g_EtwRegHandle@@3_KA, 0; unsigned __int64 g_EtwRegHandle
0x140017119  call    BthLib_Unload
0x14001711e  mov     rcx, cs:g_wil_details_featureChangeNotification
0x140017125  test    rcx, rcx
0x140017128  jz      short loc_140017141
0x14001712a  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x140017131  nop     dword ptr [rax+rax+00h]
0x140017136  mov     cs:g_wil_details_featureChangeNotification, 0
0x140017141  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type
0x140017148  test    rcx, rcx
0x14001714b  jz      short loc_140017164
0x14001714d  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x140017154  nop     dword ptr [rax+rax+00h]
0x140017159  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.Type, 0
0x140017164  mov     rbx, cs:WPP_GLOBAL_Control
0x14001716b  lea     rbp, WPP_GLOBAL_Control
0x140017172  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14001717c  cmp     rbx, rbp
0x14001717f  jz      short loc_1400171D0
0x140017181  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+10h
0x140017187  cmp     eax, 4
0x14001718a  jz      short loc_140017202
0x14001718c  cmp     eax, 2
0x14001718f  jnz     short loc_1400171A5
0x140017191  mov     edx, 80000002h; Action
0x140017196  mov     rcx, rbx; DeviceObject
0x140017199  call    cs:__imp_IoWMIRegistrationControl
0x1400171a0  nop     dword ptr [rax+rax+00h]
0x1400171a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400171ac  mov     rdx, rdi
0x1400171af  call    cs:__imp_WppAutoLogStop
0x1400171b6  nop     dword ptr [rax+rax+00h]
0x1400171bb  lea     rax, WPP_RECORDER_INITIALIZED
0x1400171c2  mov     cs:WPP_GLOBAL_Control, rbp
0x1400171c9  mov     cs:WPP_RECORDER_INITIALIZED, rax
0x1400171d0  mov     rbx, [rsp+48h+arg_0]
0x1400171d5  mov     rbp, [rsp+48h+arg_18]
0x1400171da  add     rsp, 40h
0x1400171de  pop     rdi
0x1400171df  retn
0x1400171e1  mov     rcx, [rbx+38h]
0x1400171e5  test    rcx, rcx
0x1400171e8  jz      short loc_1400171FE
0x1400171ea  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+28h
0x1400171f1  call    _guard_dispatch_icall
0x1400171f6  mov     qword ptr [rbx+38h], 0
0x1400171fe  mov     rbx, [rbx+10h]
0x140017202  test    rbx, rbx
0x140017205  jnz     short loc_1400171E1
0x140017207  jmp     short loc_1400171A5
```
