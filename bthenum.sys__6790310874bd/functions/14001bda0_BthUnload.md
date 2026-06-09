# BthUnload

- ea: `0x14001bda0`
- end: `0x14001bfc0`
- name: `BthUnload`
- size: `544`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x140020078`

## callees

- `0x140001008`
- `0x140001328`
- `0x140004578`
- `0x1400070b8`
- `0x140007d00`
- `0x140007d40`
- `0x14001bda0`

## import_xrefs

- `ntoskrnl!IoWMIRegistrationControl` at `0x14001bf4a`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14001bf4a`
- `ntoskrnl!EtwUnregister` at `0x14001be96`
- `ntoskrnl!EtwUnregister` at `0x14001be96`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14001befe`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14001befe`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14001bedb`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14001bedb`
- `ntoskrnl!ExFreePool` at `0x14001beb3`
- `ntoskrnl!ExFreePool` at `0x14001beb3`
- `WppRecorder!WppAutoLogStop` at `0x14001bf60`
- `WppRecorder!WppAutoLogStop` at `0x14001bf60`

## pseudocode

```c
__int64 __fastcall BthUnload(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  REGHANDLE v5; // rcx
  __int64 result; // rax
  PDEVICE_OBJECT v7; // rbx
  __int64 v8; // [rsp+30h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+40h] [rbp-78h] BYREF
  __int64 *v10; // [rsp+60h] [rbp-58h]
  __int64 v11; // [rsp+68h] [rbp-50h]
  const wchar_t *v12; // [rsp+70h] [rbp-48h]
  __int64 v13; // [rsp+78h] [rbp-40h]

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      25,
      (__int64)WPP_c8568bf54bc733d6f91a7ac4a8ca9399_Traceguids);
  if ( (unsigned int)dword_140015010 > 5
    && (qword_140015020 & 0x400000000000LL) != 0
    && (*(_QWORD *)&qword_140015028 & 0x400000000000LL) == *(_QWORD *)&qword_140015028 )
  {
    v8 = 33556480;
    v10 = &v8;
    v11 = 8;
    v12 = L"BthEnum.sys";
    v13 = 24;
    tlgWriteTransfer_EtwWriteTransfer(*(__int64 *)&qword_140015028, (unsigned __int8 *)&byte_140013991, a3, a4, 4u, &v9);
  }
  v5 = RegHandle;
  dword_140015010 = 0;
  RegHandle = 0;
  EtwUnregister(v5);
  BthLib_Unload();
  if ( WPP_MAIN_CB.DeviceQueue.1 )
  {
    ExFreePool(*(PVOID *)&WPP_MAIN_CB.DeviceQueue.32);
    WPP_MAIN_CB.DeviceQueue.1 = 0;
  }
  result = BthPolicyDestroy();
  if ( g_wil_details_featureChangeNotification )
  {
    result = RtlUnregisterFeatureConfigurationChangeNotification();
    g_wil_details_featureChangeNotification = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    result = RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  v7 = WPP_GLOBAL_Control;
  g_wil_details_isFeatureStagingInitialized = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( WPPTraceSuite == 4 )
    {
      while ( v7 )
      {
        if ( v7->Vpb )
        {
          ((void (*)(void))pfnEtwUnregister)();
          v7->Vpb = 0;
        }
        v7 = v7->NextDevice;
      }
    }
    else if ( WPPTraceSuite == 2 )
    {
      IoWMIRegistrationControl(WPP_GLOBAL_Control, 0x80000002);
    }
    result = WppAutoLogStop(WPP_GLOBAL_Control, a1);
    WPP_RECORDER_INITIALIZED = &WPP_RECORDER_INITIALIZED;
    WPP_GLOBAL_Control = (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
  }
  return result;
}

```

## disassembly

```asm
0x14001bda0  push    rbx
0x14001bda2  push    rbp
0x14001bda3  push    rdi
0x14001bda4  push    r14
0x14001bda6  sub     rsp, 98h
0x14001bdad  mov     rax, cs:__security_cookie
0x14001bdb4  xor     rax, rsp
0x14001bdb7  mov     [rsp+0B8h+var_38], rax
0x14001bdbf  mov     rdi, rcx
0x14001bdc2  lea     r14, WPP_RECORDER_INITIALIZED
0x14001bdc9  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14001bdd0  jz      short loc_14001BDF8
0x14001bdd2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bdd9  lea     rax, WPP_c8568bf54bc733d6f91a7ac4a8ca9399_Traceguids
0x14001bde0  mov     r9d, 19h
0x14001bde6  mov     qword ptr [rsp+0B8h+var_98], rax
0x14001bdeb  mov     rcx, [rcx+40h]
0x14001bdef  lea     r8d, [r9-16h]
0x14001bdf3  call    WPP_RECORDER_SF_
0x14001bdf8  mov     eax, cs:dword_140015010
0x14001bdfe  cmp     eax, 5
0x14001be01  jbe     short loc_14001BE7A
0x14001be03  mov     rcx, cs:qword_140015028; int
0x14001be0a  mov     rdx, 400000000000h
0x14001be14  mov     rax, cs:qword_140015020
0x14001be1b  test    rdx, rax
0x14001be1e  jz      short loc_14001BE7A
0x14001be20  mov     rax, rcx
0x14001be23  and     rax, rdx
0x14001be26  cmp     rax, rcx
0x14001be29  jnz     short loc_14001BE7A
0x14001be2b  lea     rax, [rsp+0B8h+var_88]
0x14001be30  mov     [rsp+0B8h+var_88], 2000800h
0x14001be39  mov     [rsp+0B8h+var_58], rax
0x14001be3e  lea     rdx, byte_140013991; int
0x14001be45  lea     rax, aBthenumSys; "BthEnum.sys"
0x14001be4c  mov     [rsp+0B8h+var_50], 8
0x14001be55  mov     [rsp+0B8h+var_48], rax
0x14001be5a  lea     rax, [rsp+0B8h+var_78]
0x14001be5f  mov     [rsp+0B8h+var_90], rax; __int64
0x14001be64  mov     [rsp+0B8h+var_98], 4; ULONG
0x14001be6c  mov     [rsp+0B8h+var_40], 18h
0x14001be75  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001be7a  mov     rcx, cs:RegHandle; RegHandle
0x14001be81  mov     cs:dword_140015010, 0
0x14001be8b  mov     cs:RegHandle, 0
0x14001be96  call    cs:__imp_EtwUnregister
0x14001be9d  nop     dword ptr [rax+rax+00h]
0x14001bea2  call    BthLib_Unload
0x14001bea7  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.___u4; P
0x14001beae  test    rcx, rcx
0x14001beb1  jz      short loc_14001BECA
0x14001beb3  call    cs:__imp_ExFreePool
0x14001beba  nop     dword ptr [rax+rax+00h]
0x14001bebf  mov     qword ptr cs:WPP_MAIN_CB.DeviceQueue.___u4, 0
0x14001beca  call    BthPolicyDestroy
0x14001becf  mov     rcx, cs:g_wil_details_featureChangeNotification
0x14001bed6  test    rcx, rcx
0x14001bed9  jz      short loc_14001BEF2
0x14001bedb  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14001bee2  nop     dword ptr [rax+rax+00h]
0x14001bee7  mov     cs:g_wil_details_featureChangeNotification, 0
0x14001bef2  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14001bef9  test    rcx, rcx
0x14001befc  jz      short loc_14001BF15
0x14001befe  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14001bf05  nop     dword ptr [rax+rax+00h]
0x14001bf0a  mov     cs:g_wil_details_featureUsageProvider, 0
0x14001bf15  mov     rbx, cs:WPP_GLOBAL_Control
0x14001bf1c  lea     rbp, WPP_GLOBAL_Control
0x14001bf23  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x14001bf2d  cmp     rbx, rbp
0x14001bf30  jz      short loc_14001BF7A
0x14001bf32  mov     eax, cs:WPPTraceSuite
0x14001bf38  cmp     eax, 4
0x14001bf3b  jz      short loc_14001BFB9
0x14001bf3d  cmp     eax, 2
0x14001bf40  jnz     short loc_14001BF56
0x14001bf42  mov     edx, 80000002h; Action
0x14001bf47  mov     rcx, rbx; DeviceObject
0x14001bf4a  call    cs:__imp_IoWMIRegistrationControl
0x14001bf51  nop     dword ptr [rax+rax+00h]
0x14001bf56  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bf5d  mov     rdx, rdi
0x14001bf60  call    cs:__imp_WppAutoLogStop
0x14001bf67  nop     dword ptr [rax+rax+00h]
0x14001bf6c  mov     cs:WPP_RECORDER_INITIALIZED, r14
0x14001bf73  mov     cs:WPP_GLOBAL_Control, rbp
0x14001bf7a  mov     rcx, [rsp+0B8h+var_38]
0x14001bf82  xor     rcx, rsp; StackCookie
0x14001bf85  call    __security_check_cookie
0x14001bf8a  add     rsp, 98h
0x14001bf91  pop     r14
0x14001bf93  pop     rdi
0x14001bf94  pop     rbp
0x14001bf95  pop     rbx
0x14001bf96  retn
0x14001bf98  mov     rcx, [rbx+38h]
0x14001bf9c  test    rcx, rcx
0x14001bf9f  jz      short loc_14001BFB5
0x14001bfa1  mov     rax, cs:pfnEtwUnregister
0x14001bfa8  call    _guard_dispatch_icall
0x14001bfad  mov     qword ptr [rbx+38h], 0
0x14001bfb5  mov     rbx, [rbx+10h]
0x14001bfb9  test    rbx, rbx
0x14001bfbc  jnz     short loc_14001BF98
0x14001bfbe  jmp     short loc_14001BF56
```
