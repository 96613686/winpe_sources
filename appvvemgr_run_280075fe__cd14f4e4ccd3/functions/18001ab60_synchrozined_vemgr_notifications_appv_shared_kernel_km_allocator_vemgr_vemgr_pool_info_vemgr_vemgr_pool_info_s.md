# synchrozined_vemgr_notifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::synchronous_vemgr_notification_on_new_thread(ulong,ulong,ulong,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ulong,ulong)

- ea: `0x18001ab60`
- end: `0x18001ad6e`
- name: `?synchronous_vemgr_notification_on_new_thread@?$synchrozined_vemgr_notifications@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJKKKAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@0KK@Z`
- size: `526`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001a594`

## callees

- `0x180004c6c`
- `0x18001ab60`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18001ab96`
- `ntoskrnl!ExAllocatePool2` at `0x18001abd5`
- `ntoskrnl!ExAllocatePool2` at `0x18001ab96`
- `ntoskrnl!ExAllocatePool2` at `0x18001abd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001ac5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001ac71`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001ac82`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001ac9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001ad35`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001ac5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001ac71`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001ac82`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001ac9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001ad35`
- `ntoskrnl!KeInitializeEvent` at `0x18001abb7`
- `ntoskrnl!KeInitializeEvent` at `0x18001abb7`
- `ntoskrnl!KeWaitForSingleObject` at `0x18001ad0a`
- `ntoskrnl!KeWaitForSingleObject` at `0x18001ad0a`
- `ntoskrnl!ZwClose` at `0x18001acb4`
- `ntoskrnl!ZwClose` at `0x18001ad4a`
- `ntoskrnl!ZwClose` at `0x18001acb4`
- `ntoskrnl!ZwClose` at `0x18001ad4a`
- `FLTMGR!FltQueueGenericWorkItem` at `0x18001ace3`
- `FLTMGR!FltQueueGenericWorkItem` at `0x18001ace3`
- `FLTMGR!FltFreeGenericWorkItem` at `0x18001ac43`
- `FLTMGR!FltFreeGenericWorkItem` at `0x18001ac43`

## pseudocode

```c
__int64 __fastcall synchrozined_vemgr_notifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::synchronous_vemgr_notification_on_new_thread(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7)
{
  struct _KEVENT *Pool2; // rax
  __int64 v9; // rax
  int v10; // r9d
  PFLT_GENERIC_WORKITEM *Context; // rax
  PFLT_GENERIC_WORKITEM *v12; // rbx
  PFLT_GENERIC_WORKITEM v13; // rcx
  PFLT_GENERIC_WORKITEM v14; // rcx
  NTSTATUS v16; // edi
  struct _FLT_GENERIC_WORKITEM *v17; // rcx
  PVOID P[3]; // [rsp+58h] [rbp-18h]

  *(_OWORD *)P = 0;
  Pool2 = (struct _KEVENT *)ExAllocatePool2(64, 24, 1733125462);
  P[0] = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  KeInitializeEvent(Pool2, NotificationEvent, 0);
  v9 = ExAllocatePool2(64, 104, 1715758931);
  if ( !v9
    || (Context = (PFLT_GENERIC_WORKITEM *)synchrozined_vemgr_notifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::VEMGR_NOTIFICATION_CONTEXT::VEMGR_NOTIFICATION_CONTEXT(
                                             v9,
                                             32,
                                             a3,
                                             v10,
                                             a5,
                                             a6,
                                             a7),
        (v12 = Context) == 0) )
  {
    if ( P[0] )
    {
      ExFreePoolWithTag(P[0], 0);
      if ( P[1] )
        ZwClose(P[1]);
    }
    return 3221225626LL;
  }
  v16 = FltQueueGenericWorkItem(
          Context[11],
          *(PVOID *)g_VeMgrFltData,
          synchrozined_vemgr_notifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::notification_workitem,
          DelayedWorkQueue,
          Context);
  if ( v16 < 0 )
  {
    v17 = v12[11];
    if ( v17 )
      FltFreeGenericWorkItem(v17);
    v13 = v12[7];
    if ( v13 )
      ExFreePoolWithTag(v13, 0);
    v14 = v12[3];
    if ( v14 )
      ExFreePoolWithTag(v14, 0);
    ExFreePoolWithTag(v12, 0);
  }
  else
  {
    KeWaitForSingleObject(P[0], Executive, 0, 0, 0);
  }
  if ( P[0] )
  {
    ExFreePoolWithTag(P[0], 0);
    if ( P[1] )
      ZwClose(P[1]);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18001ab60  mov     [rsp-8+arg_0], rbx
0x18001ab65  mov     [rsp-8+arg_8], rdi
0x18001ab6a  mov     [rsp-8+arg_18], r9d
0x18001ab6f  push    rbp
0x18001ab70  mov     rbp, rsp
0x18001ab73  sub     rsp, 70h
0x18001ab77  mov     edx, 18h
0x18001ab7c  mov     [rbp+var_20], 1
0x18001ab80  mov     ebx, r8d
0x18001ab83  xorps   xmm0, xmm0
0x18001ab86  mov     r8d, 674D6556h
0x18001ab8c  movdqu  xmmword ptr [rbp+P], xmm0
0x18001ab91  lea     edi, [rdx+28h]
0x18001ab94  mov     ecx, edi
0x18001ab96  call    cs:__imp_ExAllocatePool2
0x18001ab9d  nop     dword ptr [rax+rax+00h]
0x18001aba2  mov     [rbp+P], rax
0x18001aba6  test    rax, rax
0x18001aba9  jz      loc_18001AD56
0x18001abaf  xor     r8d, r8d; State
0x18001abb2  xor     edx, edx; Type
0x18001abb4  mov     rcx, rax; Event
0x18001abb7  call    cs:__imp_KeInitializeEvent
0x18001abbe  nop     dword ptr [rax+rax+00h]
0x18001abc3  lea     edx, [rdi+28h]
0x18001abc6  mov     [rbp+arg_18], 0
0x18001abcd  mov     r8d, 66446753h
0x18001abd3  mov     ecx, edi
0x18001abd5  call    cs:__imp_ExAllocatePool2
0x18001abdc  nop     dword ptr [rax+rax+00h]
0x18001abe1  test    rax, rax
0x18001abe4  jz      loc_18001AD24
0x18001abea  lea     rcx, [rbp+arg_18]
0x18001abee  mov     r8d, ebx
0x18001abf1  mov     [rsp+70h+var_28], rcx
0x18001abf6  lea     edx, [rdi-20h]
0x18001abf9  lea     rcx, [rbp+var_20]
0x18001abfd  mov     [rsp+70h+var_30], rcx
0x18001ac02  mov     ecx, [rbp+arg_30]
0x18001ac05  mov     [rsp+70h+var_40], ecx
0x18001ac09  mov     rcx, [rbp+arg_28]
0x18001ac0d  mov     [rsp+70h+var_48], rcx
0x18001ac12  mov     rcx, [rbp+arg_20]
0x18001ac16  mov     [rsp+70h+Context], rcx
0x18001ac1b  mov     rcx, rax
0x18001ac1e  call    ??0VEMGR_NOTIFICATION_CONTEXT@?$synchrozined_vemgr_notifications@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA@KKKAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@0KKPEAVevent@345@AEAJ@Z; synchrozined_vemgr_notifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::VEMGR_NOTIFICATION_CONTEXT::VEMGR_NOTIFICATION_CONTEXT(ulong,ulong,ulong,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ulong,ulong,appv::shared::kernel::event *,long &)
0x18001ac23  mov     rbx, rax
0x18001ac26  test    rax, rax
0x18001ac29  jz      loc_18001AD24
0x18001ac2f  mov     edi, [rbp+arg_18]
0x18001ac32  mov     rcx, [rax+58h]; FltWorkItem
0x18001ac36  test    edi, edi
0x18001ac38  jns     loc_18001ACC7
0x18001ac3e  test    rcx, rcx
0x18001ac41  jz      short loc_18001AC4F
0x18001ac43  call    cs:__imp_FltFreeGenericWorkItem
0x18001ac4a  nop     dword ptr [rax+rax+00h]
0x18001ac4f  mov     rcx, [rbx+38h]; P
0x18001ac53  test    rcx, rcx
0x18001ac56  jz      short loc_18001AC66
0x18001ac58  xor     edx, edx; Tag
0x18001ac5a  call    cs:__imp_ExFreePoolWithTag
0x18001ac61  nop     dword ptr [rax+rax+00h]
0x18001ac66  mov     rcx, [rbx+18h]; P
0x18001ac6a  test    rcx, rcx
0x18001ac6d  jz      short loc_18001AC7D
0x18001ac6f  xor     edx, edx; Tag
0x18001ac71  call    cs:__imp_ExFreePoolWithTag
0x18001ac78  nop     dword ptr [rax+rax+00h]
0x18001ac7d  xor     edx, edx; Tag
0x18001ac7f  mov     rcx, rbx; P
0x18001ac82  call    cs:__imp_ExFreePoolWithTag
0x18001ac89  nop     dword ptr [rax+rax+00h]
0x18001ac8e  mov     rcx, [rbp+P]; P
0x18001ac92  test    rcx, rcx
0x18001ac95  jz      short loc_18001ACC0
0x18001ac97  cmp     [rbp+var_20], 0
0x18001ac9b  jz      short loc_18001ACAB
0x18001ac9d  xor     edx, edx; Tag
0x18001ac9f  call    cs:__imp_ExFreePoolWithTag
0x18001aca6  nop     dword ptr [rax+rax+00h]
0x18001acab  mov     rcx, [rbp+P+8]; Handle
0x18001acaf  test    rcx, rcx
0x18001acb2  jz      short loc_18001ACC0
0x18001acb4  call    cs:__imp_ZwClose
0x18001acbb  nop     dword ptr [rax+rax+00h]
0x18001acc0  mov     eax, edi
0x18001acc2  jmp     loc_18001AD5B
0x18001acc7  mov     rdx, cs:?g_VeMgrFltData@@3PEAUVeMgrFilterData@@EA; VeMgrFilterData * g_VeMgrFltData
0x18001acce  lea     r8, ?notification_workitem@?$synchrozined_vemgr_notifications@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAXPEAU_FLT_GENERIC_WORKITEM@@PEAX1@Z; WorkerRoutine
0x18001acd5  mov     r9d, 1; QueueType
0x18001acdb  mov     [rsp+70h+Context], rbx; Context
0x18001ace0  mov     rdx, [rdx]; FltObject
0x18001ace3  call    cs:__imp_FltQueueGenericWorkItem
0x18001acea  nop     dword ptr [rax+rax+00h]
0x18001acef  mov     edi, eax
0x18001acf1  test    eax, eax
0x18001acf3  js      short loc_18001AD1B
0x18001acf5  mov     rcx, [rbp+P]; Object
0x18001acf9  xor     r9d, r9d; Alertable
0x18001acfc  xor     r8d, r8d; WaitMode
0x18001acff  mov     [rsp+70h+Context], 0; Timeout
0x18001ad08  xor     edx, edx; WaitReason
0x18001ad0a  call    cs:__imp_KeWaitForSingleObject
0x18001ad11  nop     dword ptr [rax+rax+00h]
0x18001ad16  jmp     loc_18001AC8E
0x18001ad1b  mov     rcx, [rbx+58h]
0x18001ad1f  jmp     loc_18001AC3E
0x18001ad24  mov     rcx, [rbp+P]; P
0x18001ad28  test    rcx, rcx
0x18001ad2b  jz      short loc_18001AD56
0x18001ad2d  cmp     [rbp+var_20], 0
0x18001ad31  jz      short loc_18001AD41
0x18001ad33  xor     edx, edx; Tag
0x18001ad35  call    cs:__imp_ExFreePoolWithTag
0x18001ad3c  nop     dword ptr [rax+rax+00h]
0x18001ad41  mov     rcx, [rbp+P+8]; Handle
0x18001ad45  test    rcx, rcx
0x18001ad48  jz      short loc_18001AD56
0x18001ad4a  call    cs:__imp_ZwClose
0x18001ad51  nop     dword ptr [rax+rax+00h]
0x18001ad56  mov     eax, 0C000009Ah
0x18001ad5b  lea     r11, [rsp+70h+var_s0]
0x18001ad60  mov     rbx, [r11+10h]
0x18001ad64  mov     rdi, [r11+18h]
0x18001ad68  mov     rsp, r11
0x18001ad6b  pop     rbp
0x18001ad6c  retn
```
