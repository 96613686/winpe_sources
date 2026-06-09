# A2DP_Device::AVDT_StreamEstablishment_Completed(void *,void *,void *,ulong,ulong)

- ea: `0x140030350`
- end: `0x14003047f`
- name: `?AVDT_StreamEstablishment_Completed@A2DP_Device@@CAXPEAX00KK@Z`
- size: `303`
- prototype: `static void(void *, void *, void *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140007374`
- `0x14000e240`
- `0x140014bd0`
- `0x14002c340`
- `0x14002e378`
- `0x14002e5fc`
- `0x140030350`
- `0x140033620`
- `0x140035678`

## import_xrefs

- `ntoskrnl!IoQueueWorkItemEx` at `0x140030469`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140030469`
- `ntoskrnl!IoAllocateWorkItem` at `0x14003042e`
- `ntoskrnl!IoAllocateWorkItem` at `0x14003042e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400303b7`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400303b7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030381`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030381`

## string_xrefs

- `0x140030447`: `AVDT_StreamEstablishment_Completed`

## pseudocode

```c
void __fastcall A2DP_Device::AVDT_StreamEstablishment_Completed(
        void *a1,
        void *a2,
        void *a3,
        unsigned int a4,
        unsigned int a5)
{
  struct A2DP_Device *v7; // rdi
  KIRQL v8; // bp
  struct _IO_WORKITEM *WorkItem; // rbx
  __int64 v10; // [rsp+60h] [rbp+18h]

  v7 = A2DP_Device::CheckCallbackParms(a1, a2);
  A2dpRole::SetCodecMtu(*((A2dpRole **)v7 + 1), a4, a5);
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v7 + 87);
  A2dpRole::SetOpenStatus(*((A2DP_Device ***)v7 + 1), 1);
  if ( !*((_DWORD *)v7 + 708) )
    A2DP_Device::SetStreamingState(v7, 5);
  KeReleaseSpinLock((PKSPIN_LOCK)v7 + 87, v8);
  A2DP_Device::SetOpenCompleteEvent(v7);
  *((_QWORD *)v7 + 353) = a3;
  v10 = (unsigned int)Feature_A2dpAptxAdaptive__private_featureState;
  if ( (Feature_A2dpAptxAdaptive__private_featureState & 0x10) == 0 )
  {
    LODWORD(v10) = Feature_A2dpAptxAdaptive__private_featureState | 1;
    wil_details_FeatureReporting_ReportUsageToService(Feature_A2dpAptxAdaptive__private_descriptor, v10, 3);
    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v10, 3, Feature_A2dpAptxAdaptive__private_descriptor);
  }
  WorkItem = IoAllocateWorkItem(*((PDEVICE_OBJECT *)v7 + 48));
  if ( WorkItem )
  {
    A2DP_Device::AddRef(v7, 13, "AVDT_StreamEstablishment_Completed");
    IoQueueWorkItemEx(WorkItem, A2DP_Device::UpdateMtuSizeSiopWorker, DelayedWorkQueue, v7);
  }
}

```

## disassembly

```asm
0x140030350  push    rbx
0x140030352  push    rbp
0x140030353  push    rsi
0x140030354  push    rdi
0x140030355  sub     rsp, 28h
0x140030359  mov     ebx, r9d
0x14003035c  mov     rsi, r8
0x14003035f  call    ?CheckCallbackParms@A2DP_Device@@CAPEAV1@PEAX0@Z; A2DP_Device::CheckCallbackParms(void *,void *)
0x140030364  mov     r8d, [rsp+48h+arg_20]; unsigned int
0x140030369  mov     edx, ebx; unsigned int
0x14003036b  mov     rdi, rax
0x14003036e  mov     rcx, [rax+8]; this
0x140030372  call    ?SetCodecMtu@A2dpRole@@QEAAXKK@Z; A2dpRole::SetCodecMtu(ulong,ulong)
0x140030377  lea     rbx, [rdi+2B8h]
0x14003037e  mov     rcx, rbx; SpinLock
0x140030381  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140030388  nop     dword ptr [rax+rax+00h]
0x14003038d  mov     rcx, [rdi+8]; Context
0x140030391  mov     dl, 1; bool
0x140030393  mov     bpl, al
0x140030396  call    ?SetOpenStatus@A2dpRole@@QEAAX_N@Z; A2dpRole::SetOpenStatus(bool)
0x14003039b  cmp     dword ptr [rdi+0B10h], 0
0x1400303a2  jnz     short loc_1400303B1
0x1400303a4  mov     edx, 5
0x1400303a9  mov     rcx, rdi
0x1400303ac  call    ?SetStreamingState@A2DP_Device@@AEAAXW4StreamingState@@@Z; A2DP_Device::SetStreamingState(StreamingState)
0x1400303b1  mov     dl, bpl; NewIrql
0x1400303b4  mov     rcx, rbx; SpinLock
0x1400303b7  call    cs:__imp_KeReleaseSpinLock
0x1400303be  nop     dword ptr [rax+rax+00h]
0x1400303c3  mov     rcx, rdi; this
0x1400303c6  call    ?SetOpenCompleteEvent@A2DP_Device@@AEAAXXZ; A2DP_Device::SetOpenCompleteEvent(void)
0x1400303cb  mov     [rdi+0B08h], rsi
0x1400303d2  mov     ecx, cs:Feature_A2dpAptxAdaptive__private_featureState
0x1400303d8  mov     [rsp+48h+arg_10], 0
0x1400303e1  mov     dword ptr [rsp+48h+arg_10], ecx
0x1400303e5  test    cl, 10h
0x1400303e8  jnz     short loc_140030427
0x1400303ea  mov     rax, [rsp+48h+arg_10]
0x1400303ef  or      ecx, 1
0x1400303f2  mov     [rsp+48h+arg_10], rax
0x1400303f7  mov     ebx, 3
0x1400303fc  mov     dword ptr [rsp+48h+arg_10], ecx
0x140030400  mov     r8d, ebx
0x140030403  mov     rdx, [rsp+48h+arg_10]
0x140030408  lea     rcx, Feature_A2dpAptxAdaptive__private_descriptor
0x14003040f  call    wil_details_FeatureReporting_ReportUsageToService
0x140030414  mov     rcx, [rsp+48h+arg_10]
0x140030419  lea     r8, Feature_A2dpAptxAdaptive__private_descriptor
0x140030420  mov     edx, ebx
0x140030422  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x140030427  mov     rcx, [rdi+180h]; DeviceObject
0x14003042e  call    cs:__imp_IoAllocateWorkItem
0x140030435  nop     dword ptr [rax+rax+00h]
0x14003043a  mov     rbx, rax
0x14003043d  test    rax, rax
0x140030440  jz      short loc_140030475
0x140030442  mov     edx, 0Dh; __int16
0x140030447  lea     r8, aAvdtStreamesta; "AVDT_StreamEstablishment_Completed"
0x14003044e  mov     rcx, rdi; this
0x140030451  call    ?AddRef@A2DP_Device@@QEAAXFPEBD@Z; A2DP_Device::AddRef(short,char const *)
0x140030456  mov     r9, rdi; Context
0x140030459  lea     rdx, ?UpdateMtuSizeSiopWorker@A2DP_Device@@_C2PAGE@@AXPEAX0PEAU_IO_WORKITEM@@@Z; WorkerRoutine
0x140030460  mov     r8d, 1; QueueType
0x140030466  mov     rcx, rbx; IoWorkItem
0x140030469  call    cs:__imp_IoQueueWorkItemEx
0x140030470  nop     dword ptr [rax+rax+00h]
0x140030475  add     rsp, 28h
0x140030479  pop     rdi
0x14003047a  pop     rsi
0x14003047b  pop     rbp
0x14003047c  pop     rbx
0x14003047d  retn
```
