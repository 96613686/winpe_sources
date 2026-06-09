# DriverEntry

- ea: `0x1400c5dbc`
- end: `0x1400c5fee`
- name: `DriverEntry`
- size: `562`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x1400d6df4`

## callees

- `0x140034ec4`
- `0x14009a9f0`
- `0x14009eb4c`
- `0x1400c5dbc`
- `0x1400da680`
- `0x1401070cc`
- `0x140107180`
- `0x1401071b4`
- `0x140107268`
- `0x140107330`
- `0x14010771c`
- `0x14010903c`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x1400c5e19`
- `ntoskrnl!DbgPrintEx` at `0x1400c5e19`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int v5; // edx
  __int64 (__fastcall *DeferredContext)(_QWORD, _DRIVER_OBJECT *, PUNICODE_STRING, __int128 *, __int128 *, __int64 *); // rax
  int v7; // eax
  int v8; // edx
  NTSTATUS v9; // ebx
  int v10; // r9d
  __int64 v11; // [rsp+28h] [rbp-61h]
  __int128 v12; // [rsp+40h] [rbp-49h] BYREF
  __int128 v13; // [rsp+50h] [rbp-39h]
  __int128 v14; // [rsp+60h] [rbp-29h] BYREF
  __int128 v15; // [rsp+70h] [rbp-19h]
  __int128 v16; // [rsp+80h] [rbp-9h]
  __int64 v17; // [rsp+90h] [rbp+7h]
  __int64 v18; // [rsp+100h] [rbp+77h] BYREF

  wil_InitializeFeatureStaging();
  v17 = 0;
  v12 = 0;
  v18 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  if ( LODWORD(WPP_MAIN_CB.Queue.Wcb.DeviceObject) )
  {
    DbgPrintEx(0x4Du, 0, "WDIWiFi: FAILING DRIVER ENTRY\n");
    return -1073741823;
  }
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (_DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_WdiLibraryCtlGuid;
  WPP_MAIN_CB.Timer = (struct _IO_TIMER *)1;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.DeviceExtension = 0;
  WPP_MAIN_CB.DeviceType = 0;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm(DriverObject, RegistryPath);
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_1400F8790);
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 4;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      1,
      10,
      (__int64)WPP_7765bc77643034118208a2dd25c5654a_Traceguids,
      65805);
  }
  CSystem::Init();
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_1400F8758);
  v12 = 0x20u;
  *(_QWORD *)&v15 = 0;
  *((_QWORD *)&v13 + 1) = 1;
  *(_QWORD *)&v13 = EvtDriverUnload;
  v17 = 0;
  v14 = 0;
  v16 = 0;
  LODWORD(v14) = 56;
  *((_QWORD *)&v15 + 1) = 0x100000001LL;
  DeferredContext = (__int64 (__fastcall *)(_QWORD, _DRIVER_OBJECT *, PUNICODE_STRING, __int128 *, __int128 *, __int64 *))WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc[14].DeferredContext;
  WPP_MAIN_CB.Queue.Wcb.CurrentIrp = &dword_1400F8758;
  v7 = DeferredContext(*(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement, DriverObject, RegistryPath, &v14, &v12, &v18);
  v9 = v7;
  if ( v7 < 0 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v10 = 11;
LABEL_11:
      LODWORD(v11) = v7;
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        1,
        v10,
        (__int64)WPP_7765bc77643034118208a2dd25c5654a_Traceguids,
        v11);
      goto LABEL_12;
    }
    goto LABEL_12;
  }
  v7 = WdiInitialize(DriverObject, RegistryPath);
  v9 = v7;
  if ( v7 )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v10 = 12;
      goto LABEL_11;
    }
LABEL_12:
    TraceLoggingUnregister_EtwUnregister(&dword_1400F8790);
    WppCleanupKm(DriverObject);
    TraceLoggingUnregister_EtwUnregister(&dword_1400F8758);
    wil_UninitializeFeatureStaging();
  }
  return v9;
}

```

## disassembly

```asm
0x1400c5dbc  push    rbp
0x1400c5dbe  push    rbx
0x1400c5dbf  push    rsi
0x1400c5dc0  push    rdi
0x1400c5dc1  push    r12
0x1400c5dc3  push    r13
0x1400c5dc5  push    r14
0x1400c5dc7  push    r15
0x1400c5dc9  lea     rbp, [rsp-1Fh]
0x1400c5dce  sub     rsp, 0A8h
0x1400c5dd5  mov     rsi, rdx
0x1400c5dd8  mov     rdi, rcx
0x1400c5ddb  call    wil_InitializeFeatureStaging
0x1400c5de0  xorps   xmm0, xmm0
0x1400c5de3  xor     eax, eax
0x1400c5de5  xor     r14d, r14d
0x1400c5de8  mov     [rbp+57h+var_50], rax
0x1400c5dec  cmp     dword ptr cs:WPP_MAIN_CB.Queue+30h, r14d
0x1400c5df3  movups  [rbp+57h+var_A0], xmm0
0x1400c5df7  mov     [rbp+57h+arg_10], r14
0x1400c5dfb  movups  [rbp+57h+var_90], xmm0
0x1400c5dff  movups  [rbp+57h+var_80], xmm0
0x1400c5e03  movups  [rbp+57h+var_70], xmm0
0x1400c5e07  movups  [rbp+57h+var_60], xmm0
0x1400c5e0b  jz      short loc_1400C5E2F
0x1400c5e0d  lea     r8, aWdiwifiFailing; "WDIWiFi: FAILING DRIVER ENTRY\n"
0x1400c5e14  xor     edx, edx; Level
0x1400c5e16  lea     ecx, [rax+4Dh]; ComponentId
0x1400c5e19  call    cs:__imp_DbgPrintEx
0x1400c5e20  nop     dword ptr [rax+rax+00h]
0x1400c5e25  mov     eax, 0C0000001h
0x1400c5e2a  jmp     loc_1400C5FD9
0x1400c5e2f  lea     rax, WPP_ThisDir_CTLGUID_WdiLibraryCtlGuid
0x1400c5e36  mov     qword ptr cs:WPP_MAIN_CB.Type, r14
0x1400c5e3d  mov     r15d, 1
0x1400c5e43  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1400c5e4a  mov     cs:WPP_MAIN_CB.Timer, r15
0x1400c5e51  mov     cs:WPP_MAIN_CB.NextDevice, r14
0x1400c5e58  mov     cs:WPP_MAIN_CB.CurrentIrp, r14
0x1400c5e5f  mov     cs:WPP_MAIN_CB.DeviceExtension, r14
0x1400c5e66  mov     cs:WPP_MAIN_CB.DeviceType, r14d
0x1400c5e6d  call    WppLoadTracingSupport
0x1400c5e72  mov     rdx, rsi; __annotation("TMC:", "21BA7B61-05F8-41F1-9048-C09493DCFE38", "WdiLibraryCtlGuid", "DUMMY", "PUBLIC_TMF:")
0x1400c5e75  mov     cs:WPP_MAIN_CB.CurrentIrp, r14
0x1400c5e7c  mov     rcx, rdi
0x1400c5e7f  call    WppInitKm
0x1400c5e84  lea     rcx, dword_1400F8790; CallbackContext
0x1400c5e8b  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x1400c5e90  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400c5e97  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400c5e9e  lea     r13, WPP_7765bc77643034118208a2dd25c5654a_Traceguids
0x1400c5ea5  jz      short loc_1400C5ECD
0x1400c5ea7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c5eae  lea     r9d, [r15+9]
0x1400c5eb2  mov     dword ptr [rsp+0E0h+var_B8], 1010Dh
0x1400c5eba  mov     r8d, r15d
0x1400c5ebd  mov     dl, 4
0x1400c5ebf  mov     [rsp+0E0h+var_C0], r13
0x1400c5ec4  mov     rcx, [rcx+40h]
0x1400c5ec8  call    WPP_RECORDER_SF_D
0x1400c5ecd  call    ?Init@CSystem@@SAXXZ; CSystem::Init(void)
0x1400c5ed2  lea     rbx, dword_1400F8758
0x1400c5ed9  mov     rcx, rbx; CallbackContext
0x1400c5edc  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x1400c5ee1  xorps   xmm0, xmm0
0x1400c5ee4  mov     qword ptr [rbp+57h+var_A0], 20h ; ' '
0x1400c5eec  movups  [rbp+57h+var_70], xmm0
0x1400c5ef0  lea     rax, EvtDriverUnload
0x1400c5ef7  mov     qword ptr [rbp+57h+var_90+8], r15
0x1400c5efb  mov     qword ptr [rbp+57h+var_90], rax
0x1400c5eff  lea     rcx, [rbp+57h+arg_10]
0x1400c5f03  xor     eax, eax
0x1400c5f05  mov     [rsp+0E0h+var_B8], rcx
0x1400c5f0a  mov     [rbp+57h+var_50], rax
0x1400c5f0e  lea     rcx, [rbp+57h+var_A0]
0x1400c5f12  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x1400c5f19  lea     r9, [rbp+57h+var_80]
0x1400c5f1d  movups  [rbp+57h+var_80], xmm0
0x1400c5f21  mov     qword ptr [rbp+57h+var_A0+8], r14
0x1400c5f25  mov     r8, rsi
0x1400c5f28  movups  [rbp+57h+var_60], xmm0
0x1400c5f2c  mov     dword ptr [rbp+57h+var_80], 38h ; '8'
0x1400c5f33  mov     rdx, rdi
0x1400c5f36  mov     dword ptr [rbp+57h+var_70+8], r15d
0x1400c5f3a  mov     dword ptr [rbp+57h+var_70+0Ch], r15d
0x1400c5f3e  mov     rax, [rax+3A0h]
0x1400c5f45  mov     [rsp+0E0h+var_C0], rcx
0x1400c5f4a  mov     rcx, qword ptr cs:WPP_MAIN_CB.AlignmentRequirement
0x1400c5f51  mov     qword ptr cs:WPP_MAIN_CB.Queue+38h, rbx
0x1400c5f58  call    _guard_dispatch_icall
0x1400c5f5d  mov     ebx, eax
0x1400c5f5f  test    eax, eax
0x1400c5f61  jns     short loc_1400C5F74
0x1400c5f63  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400c5f6a  jz      short loc_1400C5FB2
0x1400c5f6c  mov     r9d, 0Bh
0x1400c5f72  jmp     short loc_1400C5F94
0x1400c5f74  mov     rdx, rsi; struct _UNICODE_STRING *
0x1400c5f77  mov     rcx, rdi; struct _DRIVER_OBJECT *
0x1400c5f7a  call    ?WdiInitialize@@YAJPEAU_DRIVER_OBJECT@@PEAU_UNICODE_STRING@@@Z; WdiInitialize(_DRIVER_OBJECT *,_UNICODE_STRING *)
0x1400c5f7f  mov     ebx, eax
0x1400c5f81  test    eax, eax
0x1400c5f83  jz      short loc_1400C5FD7
0x1400c5f85  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400c5f8c  jz      short loc_1400C5FB2
0x1400c5f8e  mov     r9d, 0Ch
0x1400c5f94  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c5f9b  mov     r8d, r15d
0x1400c5f9e  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1400c5fa2  mov     dl, 2
0x1400c5fa4  mov     [rsp+0E0h+var_C0], r13
0x1400c5fa9  mov     rcx, [rcx+40h]
0x1400c5fad  call    WPP_RECORDER_SF_D
0x1400c5fb2  lea     rcx, dword_1400F8790
0x1400c5fb9  call    TraceLoggingUnregister_EtwUnregister
0x1400c5fbe  mov     rcx, rdi
0x1400c5fc1  call    WppCleanupKm
0x1400c5fc6  lea     rcx, dword_1400F8758
0x1400c5fcd  call    TraceLoggingUnregister_EtwUnregister
0x1400c5fd2  call    wil_UninitializeFeatureStaging
0x1400c5fd7  mov     eax, ebx
0x1400c5fd9  add     rsp, 0A8h
0x1400c5fe0  pop     r15
0x1400c5fe2  pop     r14
0x1400c5fe4  pop     r13
0x1400c5fe6  pop     r12
0x1400c5fe8  pop     rdi
0x1400c5fe9  pop     rsi
0x1400c5fea  pop     rbx
0x1400c5feb  pop     rbp
0x1400c5fec  retn
```
