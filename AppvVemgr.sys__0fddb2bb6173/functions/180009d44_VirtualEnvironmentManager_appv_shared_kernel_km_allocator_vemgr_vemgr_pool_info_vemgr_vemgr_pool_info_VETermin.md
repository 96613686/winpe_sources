# VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::VETerminatedNotificationUpcall(ulong,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ulong)

- ea: `0x180009d44`
- end: `0x180009ee7`
- name: `?VETerminatedNotificationUpcall@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJKAEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@K@Z`
- size: `419`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180005ec4`
- `0x18000855c`

## callees

- `0x180004c6c`
- `0x180009d44`
- `0x18001b3cc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180009d77`
- `ntoskrnl!ExAllocatePool2` at `0x180009d77`
- `ntoskrnl!ExFreePoolWithTag` at `0x180009e22`
- `ntoskrnl!ExFreePoolWithTag` at `0x180009e39`
- `ntoskrnl!ExFreePoolWithTag` at `0x180009e4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x180009e22`
- `ntoskrnl!ExFreePoolWithTag` at `0x180009e39`
- `ntoskrnl!ExFreePoolWithTag` at `0x180009e4a`
- `FLTMGR!FltQueueGenericWorkItem` at `0x180009df0`
- `FLTMGR!FltQueueGenericWorkItem` at `0x180009df0`
- `FLTMGR!FltFreeGenericWorkItem` at `0x180009e0b`
- `FLTMGR!FltFreeGenericWorkItem` at `0x180009e0b`

## string_xrefs

- `0x180009eb9`: `VirtualEnvironmentManager::VETerminatedNotificationUpcall() - VE removed notification failed. Package moniker %s. User SID %s. Error %d.`

## pseudocode

```c
__int64 __fastcall VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::VETerminatedNotificationUpcall(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5)
{
  _DWORD *v5; // rdi
  __int64 Pool2; // rax
  int v10; // r9d
  PFLT_GENERIC_WORKITEM *Context; // rax
  PFLT_GENERIC_WORKITEM *v12; // rbx
  NTSTATUS v13; // edi
  struct _FLT_GENERIC_WORKITEM *v14; // rcx
  PFLT_GENERIC_WORKITEM v15; // rcx
  PFLT_GENERIC_WORKITEM v16; // rcx
  unsigned int v17; // ecx
  __int16 v18; // dx
  __int16 v19; // ax
  __int64 v20; // rdx
  unsigned int v21; // ecx
  __int16 v22; // r8
  __int16 v23; // ax
  __int64 v24; // r9
  __int64 v26; // [rsp+28h] [rbp-40h]

  v5 = *(_DWORD **)a3;
  Pool2 = ExAllocatePool2(64, 104, 1715758931);
  if ( !Pool2
    || (Context = (PFLT_GENERIC_WORKITEM *)synchrozined_vemgr_notifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::VEMGR_NOTIFICATION_CONTEXT::VEMGR_NOTIFICATION_CONTEXT(
                                             Pool2,
                                             16,
                                             a2,
                                             v10,
                                             (__int64)v5,
                                             a4,
                                             a5),
        (v12 = Context) == 0) )
  {
    v13 = -1073741670;
LABEL_14:
    v17 = *(_DWORD *)a4 >> 1;
    if ( v17 > 0xFFFF )
      v18 = -1;
    else
      v18 = *(_DWORD *)a4 >> 1;
    v19 = 0;
    if ( v17 <= 0xFFFF )
      v19 = v18;
    v20 = 0;
    if ( v19 )
      v20 = *(_QWORD *)(a4 + 8);
    v21 = **(_DWORD **)a3 >> 1;
    if ( v21 > 0xFFFF )
      v22 = -1;
    else
      v22 = **(_DWORD **)a3 >> 1;
    v23 = 0;
    if ( v21 <= 0xFFFF )
      v23 = v22;
    if ( v23 )
      v24 = *(_QWORD *)(*(_QWORD *)a3 + 8LL);
    else
      v24 = 0;
    LODWORD(v26) = v13;
    LogWrite(
      1,
      0,
      L"VirtualEnvironmentManager::VETerminatedNotificationUpcall() - VE removed notification failed. Package moniker %s. "
       "User SID %s. Error %d.",
      v24,
      v20,
      v26);
    return (unsigned int)v13;
  }
  v13 = FltQueueGenericWorkItem(
          Context[11],
          *(PVOID *)g_VeMgrFltData,
          synchrozined_vemgr_notifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::notification_workitem,
          DelayedWorkQueue,
          Context);
  if ( v13 < 0 )
  {
    v14 = v12[11];
    if ( v14 )
      FltFreeGenericWorkItem(v14);
    v15 = v12[7];
    if ( v15 )
      ExFreePoolWithTag(v15, 0);
    v16 = v12[3];
    if ( v16 )
      ExFreePoolWithTag(v16, 0);
    ExFreePoolWithTag(v12, 0);
  }
  if ( v13 < 0 )
    goto LABEL_14;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180009d44  mov     rax, rsp
0x180009d47  mov     [rax+10h], rbx
0x180009d4b  mov     [rax+18h], rbp
0x180009d4f  mov     [rax+8], rcx
0x180009d53  push    rsi
0x180009d54  push    rdi
0x180009d55  push    r14
0x180009d57  sub     rsp, 50h
0x180009d5b  mov     rdi, [r8]
0x180009d5e  xor     ebp, ebp
0x180009d60  mov     r14, r8
0x180009d63  mov     [rax+8], ebp
0x180009d66  mov     ebx, edx
0x180009d68  mov     r8d, 66446753h
0x180009d6e  mov     rsi, r9
0x180009d71  lea     edx, [rbp+68h]
0x180009d74  lea     ecx, [rbp+40h]
0x180009d77  call    cs:__imp_ExAllocatePool2
0x180009d7e  nop     dword ptr [rax+rax+00h]
0x180009d83  test    rax, rax
0x180009d86  jz      loc_180009E5C
0x180009d8c  lea     rcx, [rsp+68h+arg_0]
0x180009d91  mov     r8d, ebx
0x180009d94  mov     [rsp+68h+var_20], rcx
0x180009d99  lea     edx, [rbp+10h]
0x180009d9c  mov     ecx, [rsp+68h+arg_20]
0x180009da3  mov     [rsp+68h+var_28], rbp
0x180009da8  mov     [rsp+68h+var_38], ecx
0x180009dac  mov     rcx, rax
0x180009daf  mov     [rsp+68h+var_40], rsi
0x180009db4  mov     [rsp+68h+Context], rdi
0x180009db9  call    ??0VEMGR_NOTIFICATION_CONTEXT@?$synchrozined_vemgr_notifications@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA@KKKAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@0KKPEAVevent@345@AEAJ@Z; synchrozined_vemgr_notifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::VEMGR_NOTIFICATION_CONTEXT::VEMGR_NOTIFICATION_CONTEXT(ulong,ulong,ulong,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ulong,ulong,appv::shared::kernel::event *,long &)
0x180009dbe  mov     rbx, rax
0x180009dc1  test    rax, rax
0x180009dc4  jz      loc_180009E5C
0x180009dca  mov     edi, [rsp+68h+arg_0]
0x180009dce  mov     rcx, [rax+58h]; FltWorkItem
0x180009dd2  test    edi, edi
0x180009dd4  js      short loc_180009E06
0x180009dd6  mov     rdx, cs:?g_VeMgrFltData@@3PEAUVeMgrFilterData@@EA; VeMgrFilterData * g_VeMgrFltData
0x180009ddd  lea     r9d, [rbp+1]; QueueType
0x180009de1  lea     r8, ?notification_workitem@?$synchrozined_vemgr_notifications@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAXPEAU_FLT_GENERIC_WORKITEM@@PEAX1@Z; WorkerRoutine
0x180009de8  mov     [rsp+68h+Context], rax; Context
0x180009ded  mov     rdx, [rdx]; FltObject
0x180009df0  call    cs:__imp_FltQueueGenericWorkItem
0x180009df7  nop     dword ptr [rax+rax+00h]
0x180009dfc  mov     edi, eax
0x180009dfe  test    eax, eax
0x180009e00  jns     short loc_180009E56
0x180009e02  mov     rcx, [rbx+58h]; FltWorkItem
0x180009e06  test    rcx, rcx
0x180009e09  jz      short loc_180009E17
0x180009e0b  call    cs:__imp_FltFreeGenericWorkItem
0x180009e12  nop     dword ptr [rax+rax+00h]
0x180009e17  mov     rcx, [rbx+38h]; P
0x180009e1b  test    rcx, rcx
0x180009e1e  jz      short loc_180009E2E
0x180009e20  xor     edx, edx; Tag
0x180009e22  call    cs:__imp_ExFreePoolWithTag
0x180009e29  nop     dword ptr [rax+rax+00h]
0x180009e2e  mov     rcx, [rbx+18h]; P
0x180009e32  test    rcx, rcx
0x180009e35  jz      short loc_180009E45
0x180009e37  xor     edx, edx; Tag
0x180009e39  call    cs:__imp_ExFreePoolWithTag
0x180009e40  nop     dword ptr [rax+rax+00h]
0x180009e45  xor     edx, edx; Tag
0x180009e47  mov     rcx, rbx; P
0x180009e4a  call    cs:__imp_ExFreePoolWithTag
0x180009e51  nop     dword ptr [rax+rax+00h]
0x180009e56  test    edi, edi
0x180009e58  jns     short loc_180009ECF
0x180009e5a  jmp     short loc_180009E61
0x180009e5c  mov     edi, 0C000009Ah
0x180009e61  mov     ecx, [rsi]
0x180009e63  mov     r10d, 0FFFFh
0x180009e69  shr     ecx, 1
0x180009e6b  cmp     ecx, r10d
0x180009e6e  ja      short loc_180009E75
0x180009e70  movzx   edx, cx
0x180009e73  jmp     short loc_180009E78
0x180009e75  mov     edx, r10d
0x180009e78  mov     eax, ebp
0x180009e7a  cmovbe  ax, dx
0x180009e7e  mov     rdx, rbp
0x180009e81  test    ax, ax
0x180009e84  jz      short loc_180009E8A
0x180009e86  mov     rdx, [rsi+8]
0x180009e8a  mov     r9, [r14]
0x180009e8d  mov     ecx, [r9]
0x180009e90  shr     ecx, 1
0x180009e92  cmp     ecx, r10d
0x180009e95  ja      short loc_180009E9D
0x180009e97  movzx   r8d, cx
0x180009e9b  jmp     short loc_180009EA0
0x180009e9d  mov     r8d, r10d
0x180009ea0  mov     eax, ebp
0x180009ea2  cmovbe  ax, r8w
0x180009ea7  test    ax, ax
0x180009eaa  jnz     short loc_180009EB1
0x180009eac  mov     r9, rbp
0x180009eaf  jmp     short loc_180009EB5
0x180009eb1  mov     r9, [r9+8]
0x180009eb5  mov     dword ptr [rsp+68h+var_40], edi
0x180009eb9  lea     r8, aVirtualenviron_12; "VirtualEnvironmentManager::VETerminated"...
0x180009ec0  mov     [rsp+68h+Context], rdx
0x180009ec5  xor     edx, edx
0x180009ec7  lea     ecx, [rdx+1]
0x180009eca  call    LogWrite
0x180009ecf  lea     r11, [rsp+68h+var_18]
0x180009ed4  mov     eax, edi
0x180009ed6  mov     rbx, [r11+28h]
0x180009eda  mov     rbp, [r11+30h]
0x180009ede  mov     rsp, r11
0x180009ee1  pop     r14
0x180009ee3  pop     rdi
0x180009ee4  pop     rsi
0x180009ee5  retn
```
