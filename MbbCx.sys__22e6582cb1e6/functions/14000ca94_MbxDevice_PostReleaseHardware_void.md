# MbxDevice::PostReleaseHardware(void)

- ea: `0x14000ca94`
- end: `0x14000cc85`
- name: `?PostReleaseHardware@MbxDevice@@QEAAXXZ`
- size: `497`
- prototype: `void __fastcall(MbxDevice *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14000a840`

## callees

- `0x140001b34`
- `0x140001ea4`
- `0x140001f90`
- `0x14000ca94`
- `0x140026378`
- `0x140041664`
- `0x140047e90`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14000cbdc`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14000cbdc`
- `ntoskrnl!ExRundownCompleted` at `0x14000cbec`
- `ntoskrnl!ExRundownCompleted` at `0x14000cbec`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000cbad`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000cbad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cb43`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cb43`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cbc8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000cbc8`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x14000caca`
- `ntoskrnl!ExUnsubscribeWnfStateChange` at `0x14000caca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cb5e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000cb5e`

## pseudocode

```c
void __fastcall MbxDevice::PostReleaseHardware(MbxDevice *this)
{
  char *v1; // rdi
  unsigned int i; // ebx
  __int64 v4; // rsi
  void *v5; // rcx
  _OWORD *v6; // rax
  __int64 v7; // rdx
  char v8; // bl
  _QWORD *v9; // r8
  int v10; // edx
  int v11; // [rsp+50h] [rbp+8h] BYREF
  int v12; // [rsp+58h] [rbp+10h] BYREF

  v1 = (char *)this + 64;
  v11 = 0;
  v12 = *((_DWORD *)this + 24);
  McGenEventUnregister_EtwUnregister();
  if ( *((_QWORD *)this + 217) )
  {
    ExUnsubscribeWnfStateChange();
    *((_QWORD *)this + 217) = 0;
  }
  for ( i = 0; i < *((_DWORD *)v1 + 10); ++i )
  {
    v4 = *(_QWORD *)(*((_QWORD *)v1 + 143) + 16LL * i);
    if ( MbbWwanRemoveSessionFromAdapterList((PKSPIN_LOCK)v1, (struct _MINIPORT_INTERFACE_CONTEXT *)v4) )
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 1664))(
        WdfDriverGlobals,
        *(_QWORD *)(v4 + 8));
  }
  FreeDeviceServiceState((struct _MBB_DS_STATE *)(v1 + 1104));
  v5 = (void *)*((_QWORD *)v1 + 9);
  if ( v5 )
  {
    ExFreePoolWithTag(v5, 0);
    *((_QWORD *)v1 + 9) = 0;
  }
  LOBYTE(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue);
  v6 = v1 + 48;
  v7 = *((_QWORD *)v1 + 6);
  if ( v7 || (v8 = 0, *((_QWORD *)v1 + 7)) )
  {
    if ( *(_OWORD **)(v7 + 8) != v6 || (v9 = (_QWORD *)*((_QWORD *)v1 + 7), (_OWORD *)*v9 != v6) )
      __fastfail(3u);
    *v9 = v7;
    *(_QWORD *)(v7 + 8) = v9;
    *v6 = 0;
    ExReleaseRundownProtection((PEX_RUNDOWN_REF)v1 + 2);
    v8 = 1;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.DeviceQueue, (KIRQL)WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink);
  if ( v8 )
  {
    ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)v1 + 2);
    ExRundownCompleted((PEX_RUNDOWN_REF)v1 + 2);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = 4;
    WPP_RECORDER_SF_i(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      1,
      81,
      (__int64)WPP_87eee639879b3392f87380bbab0baecf_Traceguids,
      (char)v1);
  }
  MbbWriteEvent(&HALT_EXIT_EVENT, 0, 0, 2u, &v12, 4, &v11, 4);
}

```

## disassembly

```asm
0x14000ca94  mov     [rsp+arg_10], rbx
0x14000ca99  mov     [rsp+arg_18], rsi
0x14000ca9e  push    rdi
0x14000ca9f  sub     rsp, 40h
0x14000caa3  lea     rdi, [rcx+40h]
0x14000caa7  mov     [rsp+48h+arg_0], 0
0x14000caaf  mov     eax, [rdi+20h]
0x14000cab2  mov     rbx, rcx
0x14000cab5  mov     [rsp+48h+arg_8], eax
0x14000cab9  call    McGenEventUnregister_EtwUnregister
0x14000cabe  mov     rcx, [rbx+6C8h]
0x14000cac5  test    rcx, rcx
0x14000cac8  jz      short loc_14000CAE1
0x14000caca  call    cs:__imp_ExUnsubscribeWnfStateChange
0x14000cad1  nop     dword ptr [rax+rax+00h]
0x14000cad6  mov     qword ptr [rbx+6C8h], 0
0x14000cae1  xor     ebx, ebx
0x14000cae3  cmp     [rdi+28h], ebx
0x14000cae6  jbe     short loc_14000CB2C
0x14000cae8  mov     rax, [rdi+478h]
0x14000caef  mov     ecx, ebx
0x14000caf1  add     rcx, rcx
0x14000caf4  mov     rsi, [rax+rcx*8]
0x14000caf8  mov     rcx, rdi; SpinLock
0x14000cafb  mov     rdx, rsi; struct _MINIPORT_INTERFACE_CONTEXT *
0x14000cafe  call    ?MbbWwanRemoveSessionFromAdapterList@@YA_NPEAU_MINIPORT_ADAPTER_CONTEXT@@PEAU_MINIPORT_INTERFACE_CONTEXT@@@Z; MbbWwanRemoveSessionFromAdapterList(_MINIPORT_ADAPTER_CONTEXT *,_MINIPORT_INTERFACE_CONTEXT *)
0x14000cb03  test    al, al
0x14000cb05  jz      short loc_14000CB25
0x14000cb07  mov     rax, cs:WdfFunctions_01031
0x14000cb0e  mov     rdx, [rsi+8]
0x14000cb12  mov     rcx, cs:WdfDriverGlobals
0x14000cb19  mov     rax, [rax+680h]
0x14000cb20  call    _guard_dispatch_icall
0x14000cb25  inc     ebx
0x14000cb27  cmp     ebx, [rdi+28h]
0x14000cb2a  jb      short loc_14000CAE8
0x14000cb2c  lea     rcx, [rdi+450h]; struct _MBB_DS_STATE *
0x14000cb33  call    ?FreeDeviceServiceState@@YAXPEAU_MBB_DS_STATE@@@Z; FreeDeviceServiceState(_MBB_DS_STATE *)
0x14000cb38  mov     rcx, [rdi+48h]; P
0x14000cb3c  test    rcx, rcx
0x14000cb3f  jz      short loc_14000CB57
0x14000cb41  xor     edx, edx; Tag
0x14000cb43  call    cs:__imp_ExFreePoolWithTag
0x14000cb4a  nop     dword ptr [rax+rax+00h]
0x14000cb4f  mov     qword ptr [rdi+48h], 0
0x14000cb57  lea     rcx, WPP_MAIN_CB.DeviceQueue; SpinLock
0x14000cb5e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000cb65  nop     dword ptr [rax+rax+00h]
0x14000cb6a  mov     byte ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink, al
0x14000cb70  lea     rax, [rdi+30h]
0x14000cb74  mov     rdx, [rax]
0x14000cb77  test    rdx, rdx
0x14000cb7a  jnz     short loc_14000CB84
0x14000cb7c  xor     bl, bl
0x14000cb7e  cmp     [rdi+38h], rdx
0x14000cb82  jz      short loc_14000CBBB
0x14000cb84  cmp     [rdx+8], rax
0x14000cb88  jnz     loc_14000CC7E
0x14000cb8e  mov     r8, [rax+8]
0x14000cb92  cmp     [r8], rax
0x14000cb95  jnz     loc_14000CC7E
0x14000cb9b  mov     [r8], rdx
0x14000cb9e  lea     rcx, [rdi+10h]; RunRef
0x14000cba2  xorps   xmm0, xmm0
0x14000cba5  mov     [rdx+8], r8
0x14000cba9  movdqu  xmmword ptr [rax], xmm0
0x14000cbad  call    cs:__imp_ExReleaseRundownProtection
0x14000cbb4  nop     dword ptr [rax+rax+00h]
0x14000cbb9  mov     bl, 1
0x14000cbbb  mov     dl, byte ptr cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink; NewIrql
0x14000cbc1  lea     rcx, WPP_MAIN_CB.DeviceQueue; SpinLock
0x14000cbc8  call    cs:__imp_KeReleaseSpinLock
0x14000cbcf  nop     dword ptr [rax+rax+00h]
0x14000cbd4  test    bl, bl
0x14000cbd6  jz      short loc_14000CBF8
0x14000cbd8  lea     rcx, [rdi+10h]; RunRef
0x14000cbdc  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14000cbe3  nop     dword ptr [rax+rax+00h]
0x14000cbe8  lea     rcx, [rdi+10h]; RunRef
0x14000cbec  call    cs:__imp_ExRundownCompleted
0x14000cbf3  nop     dword ptr [rax+rax+00h]
0x14000cbf8  lea     rax, WPP_RECORDER_INITIALIZED
0x14000cbff  mov     ebx, 4
0x14000cc04  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000cc0b  jz      short loc_14000CC38
0x14000cc0d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cc14  lea     rax, WPP_87eee639879b3392f87380bbab0baecf_Traceguids
0x14000cc1b  lea     r9d, [rbx+4Dh]
0x14000cc1f  mov     [rsp+48h+var_20], rdi
0x14000cc24  lea     r8d, [rbx-3]
0x14000cc28  mov     [rsp+48h+var_28], rax
0x14000cc2d  mov     dl, bl
0x14000cc2f  mov     rcx, [rcx+40h]
0x14000cc33  call    WPP_RECORDER_SF_i
0x14000cc38  mov     [rsp+48h+var_10], rbx
0x14000cc3d  lea     rax, [rsp+48h+arg_0]
0x14000cc42  mov     [rsp+48h+var_18], rax
0x14000cc47  lea     rcx, HALT_EXIT_EVENT; EventDescriptor
0x14000cc4e  lea     rax, [rsp+48h+arg_8]
0x14000cc53  mov     [rsp+48h+var_20], rbx
0x14000cc58  mov     r9d, 2; unsigned __int16
0x14000cc5e  mov     [rsp+48h+var_28], rax
0x14000cc63  xor     r8d, r8d; RelatedActivityId
0x14000cc66  xor     edx, edx; ActivityId
0x14000cc68  call    ?MbbWriteEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@1GZZ; MbbWriteEvent(_EVENT_DESCRIPTOR const *,_GUID *,_GUID *,ushort,...)
0x14000cc6d  mov     rbx, [rsp+48h+arg_10]
0x14000cc72  mov     rsi, [rsp+48h+arg_18]
0x14000cc77  add     rsp, 40h
0x14000cc7b  pop     rdi
0x14000cc7c  retn
0x14000cc7e  mov     ecx, 3
0x14000cc83  int     29h; Win8: RtlFailFast(ecx)
```
