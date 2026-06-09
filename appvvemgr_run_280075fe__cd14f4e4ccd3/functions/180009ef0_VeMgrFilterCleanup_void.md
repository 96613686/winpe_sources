# VeMgrFilterCleanup(void)

- ea: `0x180009ef0`
- end: `0x18000a02b`
- name: `?VeMgrFilterCleanup@@YAXXZ`
- size: `315`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18000a1d0`
- `0x180015fa4`

## callees

- `0x180005388`
- `0x180009ef0`
- `0x18000bb18`
- `0x180015f6c`
- `0x18001948c`
- `0x18001b2b4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180009f99`
- `ntoskrnl!ExFreePoolWithTag` at `0x180009f99`
- `ntoskrnl!IoDeleteDevice` at `0x180009ffb`
- `ntoskrnl!IoDeleteDevice` at `0x180009ffb`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x180009fda`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x180009fda`
- `ntoskrnl!RtlInitUnicodeString` at `0x180009fc9`
- `ntoskrnl!RtlInitUnicodeString` at `0x180009fc9`
- `FLTMGR!FltCloseCommunicationPort` at `0x180009f1f`
- `FLTMGR!FltCloseCommunicationPort` at `0x180009f52`
- `FLTMGR!FltCloseCommunicationPort` at `0x180009f1f`
- `FLTMGR!FltCloseCommunicationPort` at `0x180009f52`
- `FLTMGR!FltUnregisterFilter` at `0x180009f74`
- `FLTMGR!FltUnregisterFilter` at `0x180009f74`

## pseudocode

```c
void __fastcall VeMgrFilterCleanup(struct _FLT_FILTER *a1)
{
  PFLT_PORT *v1; // rbx
  PFLT_PORT *v2; // rbx
  PVOID v3; // rbx
  struct _DEVICE_OBJECT *v4; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  if ( g_VeMgrFltData )
  {
    v1 = (PFLT_PORT *)*((_QWORD *)g_VeMgrFltData + 1);
    if ( v1 )
    {
      appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::disconnect_client(v1);
      if ( *v1 )
      {
        FltCloseCommunicationPort(*v1);
        *v1 = 0;
      }
    }
    v2 = (PFLT_PORT *)*((_QWORD *)g_VeMgrFltData + 3);
    if ( v2 )
    {
      appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::disconnect_client(*((_QWORD *)g_VeMgrFltData + 3));
      if ( *v2 )
      {
        FltCloseCommunicationPort(*v2);
        *v2 = 0;
      }
    }
    a1 = *(struct _FLT_FILTER **)g_VeMgrFltData;
    if ( *(_QWORD *)g_VeMgrFltData )
      FltUnregisterFilter(a1);
    v3 = g_VeMgrFltData;
    if ( g_VeMgrFltData )
    {
      VeMgrFilterData::~VeMgrFilterData((VeMgrFilterData *)g_VeMgrFltData);
      ExFreePoolWithTag(v3, 0);
    }
    g_VeMgrFltData = 0;
  }
  vemgr::Uninitialize(a1);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\DosDevices\\AppvVemgr");
  IoDeleteSymbolicLink(&DestinationString);
  if ( vemgr::g_pDeviceExtn )
  {
    v4 = (struct _DEVICE_OBJECT *)*((_QWORD *)vemgr::g_pDeviceExtn + 1);
    if ( v4 )
      IoDeleteDevice(v4);
  }
  McGenEventUnregister_EtwUnregister(PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context);
  LogUninitialize();
  McGenEventUnregister_EtwUnregister(PROVIDER_MICROSOFT_APPV_CLIENT_Context);
}

```

## disassembly

```asm
0x180009ef0  push    rbx
0x180009ef2  sub     rsp, 30h
0x180009ef6  mov     rbx, cs:?g_VeMgrFltData@@3PEAUVeMgrFilterData@@EA; VeMgrFilterData * g_VeMgrFltData
0x180009efd  test    rbx, rbx
0x180009f00  jz      loc_180009FB0
0x180009f06  mov     rbx, [rbx+8]
0x180009f0a  test    rbx, rbx
0x180009f0d  jz      short loc_180009F32
0x180009f0f  mov     rcx, rbx
0x180009f12  call    ?disconnect_client@?$flt_connection@Vvemgr_listener_connection_manager@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::disconnect_client(void)
0x180009f17  mov     rcx, [rbx]; ServerPort
0x180009f1a  test    rcx, rcx
0x180009f1d  jz      short loc_180009F32
0x180009f1f  call    cs:__imp_FltCloseCommunicationPort
0x180009f26  nop     dword ptr [rax+rax+00h]
0x180009f2b  mov     qword ptr [rbx], 0
0x180009f32  mov     rax, cs:?g_VeMgrFltData@@3PEAUVeMgrFilterData@@EA; VeMgrFilterData * g_VeMgrFltData
0x180009f39  mov     rbx, [rax+18h]
0x180009f3d  test    rbx, rbx
0x180009f40  jz      short loc_180009F65
0x180009f42  mov     rcx, rbx
0x180009f45  call    ?disconnect_client@?$flt_connection@Vvemgr_listener_connection_manager@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::disconnect_client(void)
0x180009f4a  mov     rcx, [rbx]; ServerPort
0x180009f4d  test    rcx, rcx
0x180009f50  jz      short loc_180009F65
0x180009f52  call    cs:__imp_FltCloseCommunicationPort
0x180009f59  nop     dword ptr [rax+rax+00h]
0x180009f5e  mov     qword ptr [rbx], 0
0x180009f65  mov     rax, cs:?g_VeMgrFltData@@3PEAUVeMgrFilterData@@EA; VeMgrFilterData * g_VeMgrFltData
0x180009f6c  mov     rcx, [rax]; Filter
0x180009f6f  test    rcx, rcx
0x180009f72  jz      short loc_180009F80
0x180009f74  call    cs:__imp_FltUnregisterFilter
0x180009f7b  nop     dword ptr [rax+rax+00h]
0x180009f80  mov     rbx, cs:?g_VeMgrFltData@@3PEAUVeMgrFilterData@@EA; VeMgrFilterData * g_VeMgrFltData
0x180009f87  test    rbx, rbx
0x180009f8a  jz      short loc_180009FA5
0x180009f8c  mov     rcx, rbx; this
0x180009f8f  call    ??1VeMgrFilterData@@QEAA@XZ; VeMgrFilterData::~VeMgrFilterData(void)
0x180009f94  xor     edx, edx; Tag
0x180009f96  mov     rcx, rbx; P
0x180009f99  call    cs:__imp_ExFreePoolWithTag
0x180009fa0  nop     dword ptr [rax+rax+00h]
0x180009fa5  mov     cs:?g_VeMgrFltData@@3PEAUVeMgrFilterData@@EA, 0; VeMgrFilterData * g_VeMgrFltData
0x180009fb0  call    ?Uninitialize@vemgr@@YAJXZ; vemgr::Uninitialize(void)
0x180009fb5  xorps   xmm0, xmm0
0x180009fb8  lea     rdx, aDosdevicesAppv; "\\DosDevices\\AppvVemgr"
0x180009fbf  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x180009fc4  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x180009fc9  call    cs:__imp_RtlInitUnicodeString
0x180009fd0  nop     dword ptr [rax+rax+00h]
0x180009fd5  lea     rcx, [rsp+38h+DestinationString]; SymbolicLinkName
0x180009fda  call    cs:__imp_IoDeleteSymbolicLink
0x180009fe1  nop     dword ptr [rax+rax+00h]
0x180009fe6  mov     rcx, cs:?g_pDeviceExtn@vemgr@@3PEAUDEVICE_EXTENSION@1@EA; vemgr::DEVICE_EXTENSION * vemgr::g_pDeviceExtn
0x180009fed  test    rcx, rcx
0x180009ff0  jz      short loc_18000A007
0x180009ff2  mov     rcx, [rcx+8]; DeviceObject
0x180009ff6  test    rcx, rcx
0x180009ff9  jz      short loc_18000A007
0x180009ffb  call    cs:__imp_IoDeleteDevice
0x18000a002  nop     dword ptr [rax+rax+00h]
0x18000a007  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_SHAREDPERFORMANCEEVENTS_Context
0x18000a00e  call    McGenEventUnregister_EtwUnregister
0x18000a013  call    LogUninitialize
0x18000a018  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x18000a01f  call    McGenEventUnregister_EtwUnregister
0x18000a024  add     rsp, 30h
0x18000a028  pop     rbx
0x18000a029  retn
```
