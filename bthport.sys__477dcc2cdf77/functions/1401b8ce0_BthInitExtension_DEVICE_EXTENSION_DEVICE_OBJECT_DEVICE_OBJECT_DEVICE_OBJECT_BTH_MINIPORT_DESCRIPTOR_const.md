# BthInitExtension(DEVICE_EXTENSION *,_DEVICE_OBJECT *,_DEVICE_OBJECT *,_DEVICE_OBJECT *,_BTH_MINIPORT_DESCRIPTOR const *)

- ea: `0x1401b8ce0`
- end: `0x1401b8fb8`
- name: `?BthInitExtension@@YAJPEAUDEVICE_EXTENSION@@PEAU_DEVICE_OBJECT@@11PEBU_BTH_MINIPORT_DESCRIPTOR@@@Z`
- size: `728`
- prototype: `__int64 __fastcall(struct DEVICE_EXTENSION *, struct _DEVICE_OBJECT *, struct _DEVICE_OBJECT *, struct _DEVICE_OBJECT *, const struct _BTH_MINIPORT_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002a5b8`

## callees

- `0x140005690`
- `0x1400bc400`
- `0x14016281c`
- `0x1401b8ce0`

## import_xrefs

- `ntoskrnl!IoInitializeRemoveLockEx` at `0x1401b8d72`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x1401b8d72`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1401b8e34`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1401b8e34`
- `ntoskrnl!EtwActivityIdControl` at `0x1401b8f50`
- `ntoskrnl!EtwActivityIdControl` at `0x1401b8f50`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401b8d41`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401b8d9d`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401b8db3`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401b8d41`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401b8d9d`
- `ntoskrnl!KeInitializeSpinLock` at `0x1401b8db3`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1401b8ec2`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1401b8ec2`

## pseudocode

```c
NTSTATUS __fastcall BthInitExtension(
        struct DEVICE_EXTENSION *a1,
        struct _DEVICE_OBJECT *a2,
        struct _DEVICE_OBJECT *a3,
        struct _DEVICE_OBJECT *a4,
        const struct _BTH_MINIPORT_DESCRIPTOR *a5)
{
  unsigned int BipExtraLength; // eax
  int v10; // edx
  NTSTATUS v11; // esi
  int v12; // r8d
  PDEVICE_OBJECT v13; // r10
  NTSTATUS result; // eax
  int v15; // edx
  int v16; // r8d
  __int16 Tag; // [rsp+30h] [rbp-48h]
  char v18; // [rsp+40h] [rbp-38h]

  a1->GlobalListEntry.Blink = &a1->GlobalListEntry;
  a1->GlobalListEntry.Flink = &a1->GlobalListEntry;
  a1->AllChildPdoList.Blink = &a1->AllChildPdoList;
  a1->AllChildPdoList.Flink = &a1->AllChildPdoList;
  a1->ClientRbTree.Root = 0;
  a1->ClientRbTree.Min = 0;
  a1->ScoRbTree.Root = 0;
  a1->ScoRbTree.Min = 0;
  KeInitializeSpinLock(&a1->AllChildPdoLock);
  a1->PendingChildPdoCallbackList.Blink = &a1->PendingChildPdoCallbackList;
  a1->PendingChildPdoCallbackList.Flink = &a1->PendingChildPdoCallbackList;
  IoInitializeRemoveLockEx(&a1->RemoveLock, 0x50485442u, 0, 0, 0x20u);
  a1->MpDispatch = a5;
  a1->BtDevice.FunctionalDeviceObject = a2;
  a1->BtDevice.PhysicalDeviceObject = a3;
  a1->BtDevice.NextDeviceObject = a4;
  KeInitializeSpinLock(&a1->BipCancelLock);
  KeInitializeSpinLock(&a1->ExtensionLock);
  IrpList_InitEx(
    &a1->PassiveRequestQueue,
    &a1->ExtensionLock,
    HCI_WriteScanEnableCancelRoutine,
    BthCompleteRequestExternal);
  IrpList_InitEx(
    &a1->AuthenticateList,
    &a1->ExtensionLock,
    HCI_WriteScanEnableCancelRoutine,
    BthCompleteAuthenticateRequest);
  BipExtraLength = L2CapInt_GetBipExtraLength();
  a1->BipExtraLength = BipExtraLength;
  v11 = ExInitializeLookasideListEx(
          &a1->BipLookasideList,
          0,
          0,
          NonPagedPoolNx,
          0,
          BipExtraLength + 232LL,
          0x50485442u,
          0);
  if ( v11 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    LOBYTE(v10) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    v18 = v11;
    Tag = 73;
LABEL_7:
    LOBYTE(v12) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      v13->AttachedDevice,
      v10,
      v12,
      v13->DeviceExtension,
      2,
      6,
      Tag,
      (__int64)WPP_70f807cd943530ae8ba584e42371a91c_Traceguids,
      v18);
    return v11;
  }
  a1->IsBipLookasideListInitialized = 1;
  v11 = BCryptOpenAlgorithmProvider(&a1->HContainerIdHashAlg, L"SHA256", 0, 1u);
  if ( v11 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    LOBYTE(v10) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    v18 = v11;
    Tag = 74;
    goto LABEL_7;
  }
  *(_DWORD *)&a1->SdpDidInfo.VendorId = 65542;
  *(_DWORD *)&a1->SdpDidInfo.Version = 68096;
  a1->SdpDidSupportLevel = 259;
  a1->IsSmpEnabled = 1;
  a1->IsLESupported = 0;
  a1->HostSupportedFeatures = 3;
  result = EtwActivityIdControl(3u, &a1->DeviceExtensionSessionId);
  if ( result < 0 )
  {
    LOBYTE(v15) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    LOBYTE(v16) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v15,
      v16,
      WPP_GLOBAL_Control->DeviceExtension,
      3,
      6,
      75,
      (__int64)WPP_70f807cd943530ae8ba584e42371a91c_Traceguids,
      result);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1401b8ce0  push    rbx
0x1401b8ce2  push    rbp
0x1401b8ce3  push    rsi
0x1401b8ce4  push    rdi
0x1401b8ce5  sub     rsp, 58h
0x1401b8ce9  lea     rax, [rcx+20h]
0x1401b8ced  mov     rbp, rcx
0x1401b8cf0  mov     [rax+8], rax
0x1401b8cf4  mov     rsi, r9
0x1401b8cf7  mov     [rax], rax
0x1401b8cfa  mov     rdi, r8
0x1401b8cfd  lea     rax, [rcx+100h]
0x1401b8d04  mov     rbx, rdx
0x1401b8d07  mov     [rax+8], rax
0x1401b8d0b  mov     [rax], rax
0x1401b8d0e  mov     qword ptr [rcx+0E0h], 0
0x1401b8d19  mov     qword ptr [rcx+0E8h], 0
0x1401b8d24  mov     qword ptr [rcx+0F0h], 0
0x1401b8d2f  mov     qword ptr [rcx+0F8h], 0
0x1401b8d3a  add     rcx, 110h; SpinLock
0x1401b8d41  call    cs:__imp_KeInitializeSpinLock
0x1401b8d48  nop     dword ptr [rax+rax+00h]
0x1401b8d4d  lea     rax, [rbp+118h]
0x1401b8d54  mov     [rsp+78h+RemlockSize], 20h ; ' '; RemlockSize
0x1401b8d5c  lea     rcx, [rbp+38h]; Lock
0x1401b8d60  mov     [rax+8], rax
0x1401b8d64  xor     r9d, r9d; HighWatermark
0x1401b8d67  mov     [rax], rax
0x1401b8d6a  xor     r8d, r8d; MaxLockedMinutes
0x1401b8d6d  mov     edx, 50485442h; AllocateTag
0x1401b8d72  call    cs:__imp_IoInitializeRemoveLockEx
0x1401b8d79  nop     dword ptr [rax+rax+00h]
0x1401b8d7e  mov     rax, [rsp+78h+arg_20]
0x1401b8d86  lea     rcx, [rbp+168h]; SpinLock
0x1401b8d8d  mov     [rbp+58h], rax
0x1401b8d91  mov     [rbp+8], rbx
0x1401b8d95  mov     [rbp+10h], rdi
0x1401b8d99  mov     [rbp+18h], rsi
0x1401b8d9d  call    cs:__imp_KeInitializeSpinLock
0x1401b8da4  nop     dword ptr [rax+rax+00h]
0x1401b8da9  lea     rbx, [rbp+128h]
0x1401b8db0  mov     rcx, rbx; SpinLock
0x1401b8db3  call    cs:__imp_KeInitializeSpinLock
0x1401b8dba  nop     dword ptr [rax+rax+00h]
0x1401b8dbf  lea     rcx, [rbp+130h]
0x1401b8dc6  mov     rdx, rbx
0x1401b8dc9  lea     r9, ?BthCompleteRequestExternal@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@J@Z; BthCompleteRequestExternal(_DEVICE_OBJECT *,_IRP *,long)
0x1401b8dd0  lea     r8, ?HCI_WriteScanEnableCancelRoutine@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; HCI_WriteScanEnableCancelRoutine(_DEVICE_OBJECT *,_IRP *)
0x1401b8dd7  call    IrpList_InitEx
0x1401b8ddc  lea     rcx, [rbp+1A0h]
0x1401b8de3  mov     rdx, rbx
0x1401b8de6  lea     r9, ?BthCompleteAuthenticateRequest@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@J@Z; BthCompleteAuthenticateRequest(_DEVICE_OBJECT *,_IRP *,long)
0x1401b8ded  lea     r8, ?HCI_WriteScanEnableCancelRoutine@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; HCI_WriteScanEnableCancelRoutine(_DEVICE_OBJECT *,_IRP *)
0x1401b8df4  call    IrpList_InitEx
0x1401b8df9  call    ?L2CapInt_GetBipExtraLength@@YAKXZ; L2CapInt_GetBipExtraLength(void)
0x1401b8dfe  mov     edx, eax
0x1401b8e00  lea     rcx, [rbp+70h]; Lookaside
0x1401b8e04  xor     eax, eax
0x1401b8e06  mov     [rbp+0D4h], edx
0x1401b8e0c  mov     [rsp+78h+Depth], ax; Depth
0x1401b8e11  add     rdx, 0E8h
0x1401b8e18  mov     dword ptr [rsp+78h+Tag], 50485442h; Tag
0x1401b8e20  mov     r9d, 200h; PoolType
0x1401b8e26  mov     [rsp+78h+Size], rdx; Size
0x1401b8e2b  xor     r8d, r8d; Free
0x1401b8e2e  xor     edx, edx; Allocate
0x1401b8e30  mov     [rsp+78h+RemlockSize], eax; Flags
0x1401b8e34  call    cs:__imp_ExInitializeLookasideListEx
0x1401b8e3b  nop     dword ptr [rax+rax+00h]
0x1401b8e40  mov     esi, eax
0x1401b8e42  test    eax, eax
0x1401b8e44  jns     short loc_1401B8EA3
0x1401b8e46  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401b8e4d  mov     ebx, 1
0x1401b8e52  mov     ecx, [r10+2Ch]
0x1401b8e56  test    cl, 20h
0x1401b8e59  jz      short loc_1401B8E66
0x1401b8e5b  cmp     byte ptr [r10+29h], 2
0x1401b8e60  jb      short loc_1401B8E66
0x1401b8e62  mov     dl, bl
0x1401b8e64  jmp     short loc_1401B8E68
0x1401b8e66  xor     dl, dl
0x1401b8e68  mov     dword ptr [rsp+78h+var_38], esi
0x1401b8e6c  lea     rax, WPP_70f807cd943530ae8ba584e42371a91c_Traceguids
0x1401b8e73  mov     qword ptr [rsp+78h+Depth], rax
0x1401b8e78  mov     [rsp+78h+Tag], 49h ; 'I'
0x1401b8e7f  mov     r9, [r10+40h]
0x1401b8e83  mov     r8b, bl
0x1401b8e86  mov     rcx, [r10+18h]
0x1401b8e8a  mov     dword ptr [rsp+78h+Size], 6
0x1401b8e92  mov     byte ptr [rsp+78h+RemlockSize], 2
0x1401b8e97  call    WPP_RECORDER_AND_TRACE_SF_d
0x1401b8e9c  mov     eax, esi
0x1401b8e9e  jmp     loc_1401B8FAE
0x1401b8ea3  mov     ebx, 1
0x1401b8ea8  lea     rcx, [rbp+1E0h]; phAlgorithm
0x1401b8eaf  mov     r9d, ebx; dwFlags
0x1401b8eb2  mov     [rbp+0D0h], bl
0x1401b8eb8  xor     r8d, r8d; pszImplementation
0x1401b8ebb  lea     rdx, aSha256; "SHA256"
0x1401b8ec2  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1401b8ec9  nop     dword ptr [rax+rax+00h]
0x1401b8ece  mov     esi, eax
0x1401b8ed0  test    eax, eax
0x1401b8ed2  jns     short loc_1401B8F0D
0x1401b8ed4  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401b8edb  mov     ecx, [r10+2Ch]
0x1401b8edf  test    cl, 20h
0x1401b8ee2  jz      short loc_1401B8EEF
0x1401b8ee4  cmp     byte ptr [r10+29h], 2
0x1401b8ee9  jb      short loc_1401B8EEF
0x1401b8eeb  mov     dl, bl
0x1401b8eed  jmp     short loc_1401B8EF1
0x1401b8eef  xor     dl, dl
0x1401b8ef1  mov     dword ptr [rsp+78h+var_38], esi
0x1401b8ef5  lea     rax, WPP_70f807cd943530ae8ba584e42371a91c_Traceguids
0x1401b8efc  mov     qword ptr [rsp+78h+Depth], rax
0x1401b8f01  mov     [rsp+78h+Tag], 4Ah ; 'J'
0x1401b8f08  jmp     loc_1401B8E7F
0x1401b8f0d  mov     edi, 6
0x1401b8f12  mov     dword ptr [rbp+1E8h], 10006h
0x1401b8f1c  lea     rdx, [rbp+2D0h]; ActivityId
0x1401b8f23  mov     dword ptr [rbp+1ECh], 10A00h
0x1401b8f2d  mov     dword ptr [rbp+1F0h], 103h
0x1401b8f37  mov     [rbp+190h], bl
0x1401b8f3d  lea     esi, [rdi-3]
0x1401b8f40  mov     byte ptr [rbp+230h], 0
0x1401b8f47  mov     ecx, esi; ControlCode
0x1401b8f49  mov     [rbp+1F8h], rsi
0x1401b8f50  call    cs:__imp_EtwActivityIdControl
0x1401b8f57  nop     dword ptr [rax+rax+00h]
0x1401b8f5c  test    eax, eax
0x1401b8f5e  jns     short loc_1401B8FAE
0x1401b8f60  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1401b8f67  mov     ecx, [r10+2Ch]
0x1401b8f6b  test    cl, 20h
0x1401b8f6e  jz      short loc_1401B8F7A
0x1401b8f70  cmp     [r10+29h], sil
0x1401b8f74  jb      short loc_1401B8F7A
0x1401b8f76  mov     dl, bl
0x1401b8f78  jmp     short loc_1401B8F7C
0x1401b8f7a  xor     dl, dl
0x1401b8f7c  mov     r9, [r10+40h]
0x1401b8f80  mov     r8b, bl
0x1401b8f83  mov     rcx, [r10+18h]
0x1401b8f87  mov     dword ptr [rsp+78h+var_38], eax
0x1401b8f8b  lea     rax, WPP_70f807cd943530ae8ba584e42371a91c_Traceguids
0x1401b8f92  mov     qword ptr [rsp+78h+Depth], rax
0x1401b8f97  mov     [rsp+78h+Tag], 4Bh ; 'K'
0x1401b8f9e  mov     dword ptr [rsp+78h+Size], edi
0x1401b8fa2  mov     byte ptr [rsp+78h+RemlockSize], sil
0x1401b8fa7  call    WPP_RECORDER_AND_TRACE_SF_d
0x1401b8fac  xor     eax, eax
0x1401b8fae  add     rsp, 58h
0x1401b8fb2  pop     rdi
0x1401b8fb3  pop     rsi
0x1401b8fb4  pop     rbp
0x1401b8fb5  pop     rbx
0x1401b8fb6  retn
```
