# vemgr::CreateProcessCallback<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::process_destroy_notification(void *)

- ea: `0x18001a594`
- end: `0x18001a795`
- name: `?process_destroy_notification@?$CreateProcessCallback@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@vemgr@@QEAAJPEAX@Z`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180018ea0`

## callees

- `0x180005178`
- `0x18000855c`
- `0x18000fd5c`
- `0x180017a64`
- `0x18001a594`
- `0x18001ab60`
- `0x18001b3cc`

## string_xrefs

- `0x18001a72c`: `VirtualEnvironmentManager::RemoveProcessFromVE() - Failed to remove process from VolumeManager. Package %s, user %s, pid %d, error %d`
- `0x18001a6da`: `VirtualEnvironmentManager::ProcessTerminatedNotificationUpcall() - Process destroyed notification failed. Package moniker %s. User SID %s. Process %d. Error %d.`

## pseudocode

```c
__int64 __fastcall vemgr::CreateProcessCallback<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::process_destroy_notification(
        __int64 *a1,
        unsigned int a2,
        __int64 a3)
{
  __int64 v5; // r13
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  int ProcessVEList; // esi
  __int64 v10; // r8
  int v11; // r9d
  __int128 *v12; // rbx
  int v13; // edi
  __int64 v14; // rsi
  __int64 v15; // r14
  int v16; // r15d
  unsigned int v17; // ecx
  __int16 v18; // dx
  __int16 v19; // ax
  __int64 v20; // r8
  __int64 v21; // r9
  unsigned int v22; // ecx
  __int16 v23; // dx
  __int16 v24; // ax
  __int64 v25; // r9
  int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v30; // [rsp+28h] [rbp-90h]
  __int64 v31; // [rsp+30h] [rbp-88h]
  int v32; // [rsp+40h] [rbp-78h] BYREF
  __int128 v33; // [rsp+48h] [rbp-70h] BYREF
  __int128 *v34; // [rsp+58h] [rbp-60h]
  __int128 *v35; // [rsp+60h] [rbp-58h]

  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0q_EtwWriteTransfer(a1, VEMGR_Process_Shutdown_Start, a3, a2);
  v5 = *a1;
  v35 = &v33;
  v34 = &v33;
  v6 = *(_QWORD *)(v5 + 16);
  v32 = 0;
  v33 = 0;
  ProcessVEList = ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindProcessVEList(
                    v6,
                    a2,
                    &v32);
  if ( ProcessVEList >= 0 )
  {
    if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
      McTemplateK0q_EtwWriteTransfer(v8, VEMGR_Virtual_Process_Shutdown_Start, v10, a2);
    v12 = v34;
    v13 = 0;
    while ( v12 != &v33 )
    {
      v14 = *(_QWORD *)v12;
      if ( *(_DWORD *)(*(_QWORD *)v12 + 40LL) )
        v15 = **(_QWORD **)(v14 + 72) + 48LL;
      else
        v15 = v14 + 136;
      v16 = synchrozined_vemgr_notifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::synchronous_vemgr_notification_on_new_thread(
              *(_DWORD *)(*(_QWORD *)v12 + 112LL),
              v7,
              a2,
              v11,
              *(_QWORD *)(v14 + 120),
              v15,
              *(_DWORD *)(*(_QWORD *)v12 + 112LL));
      if ( v16 < 0 )
      {
        v17 = *(_DWORD *)v15 >> 1;
        if ( v17 > 0xFFFF )
          v18 = -1;
        else
          v18 = *(_DWORD *)v15 >> 1;
        v19 = 0;
        v20 = 0;
        if ( v17 <= 0xFFFF )
          v19 = v18;
        if ( v19 )
          v20 = *(_QWORD *)(v15 + 8);
        v21 = *(_QWORD *)(v14 + 120);
        v22 = *(_DWORD *)v21 >> 1;
        if ( v22 > 0xFFFF )
          v23 = -1;
        else
          v23 = *(_DWORD *)v21 >> 1;
        v24 = 0;
        if ( v22 <= 0xFFFF )
          v24 = v23;
        if ( v24 )
          v25 = *(_QWORD *)(v21 + 8);
        else
          v25 = 0;
        LODWORD(v31) = v16;
        LODWORD(v30) = a2;
        LogWrite(
          1,
          0,
          L"VirtualEnvironmentManager::ProcessTerminatedNotificationUpcall() - Process destroyed notification failed. Pack"
           "age moniker %s. User SID %s. Process %d. Error %d.",
          v25,
          v20,
          v30,
          v31);
        if ( v13 >= 0 )
          v13 = v16;
      }
      v26 = VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessFromVE(
              v5,
              a2,
              v12);
      ProcessVEList = v26;
      if ( v26 < 0 && v13 >= 0 )
        v13 = v26;
      if ( v12 == v35 )
        break;
      v12 = (__int128 *)*((_QWORD *)v12 + 2);
    }
    if ( ProcessVEList < 0 )
    {
      LogWrite(
        1,
        0,
        L"VirtualEnvironmentManager::RemoveProcessFromVE() - Failed to remove process from VolumeManager. Package %s, user"
         " %s, pid %d, error %d");
      if ( v13 >= 0 )
        v13 = ProcessVEList;
    }
    if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
      McTemplateK0q_EtwWriteTransfer(v8, VEMGR_Virtual_Process_Shutdown_Finish, v10, a2);
    ProcessVEList = v13;
  }
  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(
    &v32,
    v7,
    v10);
  if ( (Microsoft_AppV_SharedPerformanceEnableBits & 1) != 0 )
    McTemplateK0q_EtwWriteTransfer(v27, VEMGR_Process_Shutdown_Finish, v28, a2);
  return (unsigned int)ProcessVEList;
}

```

## disassembly

```asm
0x18001a594  push    rbx
0x18001a596  push    rbp
0x18001a597  push    rsi
0x18001a598  push    rdi
0x18001a599  push    r12
0x18001a59b  push    r13
0x18001a59d  push    r14
0x18001a59f  push    r15
0x18001a5a1  sub     rsp, 78h
0x18001a5a5  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x18001a5ac  mov     rbp, rdx
0x18001a5af  mov     rbx, rcx
0x18001a5b2  jz      short loc_18001A5C3
0x18001a5b4  mov     r9d, ebp
0x18001a5b7  lea     rdx, VEMGR_Process_Shutdown_Start
0x18001a5be  call    McTemplateK0q_EtwWriteTransfer
0x18001a5c3  mov     r13, [rbx]
0x18001a5c6  lea     rax, [rsp+0B8h+var_70]
0x18001a5cb  mov     [rsp+0B8h+var_58], rax
0x18001a5d0  lea     r8, [rsp+0B8h+var_78]
0x18001a5d5  xorps   xmm0, xmm0
0x18001a5d8  lea     rax, [rsp+0B8h+var_70]
0x18001a5dd  xor     r12d, r12d
0x18001a5e0  mov     [rsp+0B8h+var_60], rax
0x18001a5e5  mov     rcx, [r13+10h]
0x18001a5e9  mov     edx, ebp
0x18001a5eb  mov     [rsp+0B8h+var_78], r12d
0x18001a5f0  movdqu  [rsp+0B8h+var_70], xmm0
0x18001a5f6  call    ?FindProcessVEList@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJKAEAV?$doubly_linked_list@V?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindProcessVEList(ulong,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info> &)
0x18001a5fb  mov     esi, eax
0x18001a5fd  test    eax, eax
0x18001a5ff  js      loc_18001A75F
0x18001a605  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x18001a60c  jz      short loc_18001A61D
0x18001a60e  mov     r9d, ebp
0x18001a611  lea     rdx, VEMGR_Virtual_Process_Shutdown_Start
0x18001a618  call    McTemplateK0q_EtwWriteTransfer
0x18001a61d  mov     rbx, [rsp+0B8h+var_60]
0x18001a622  mov     edi, r12d
0x18001a625  lea     rax, [rsp+0B8h+var_70]
0x18001a62a  cmp     rbx, rax
0x18001a62d  jz      loc_18001A717
0x18001a633  mov     rsi, [rbx]
0x18001a636  mov     ecx, [rsi+70h]
0x18001a639  cmp     [rsi+28h], r12d
0x18001a63d  jz      short loc_18001A64C
0x18001a63f  mov     rax, [rsi+48h]
0x18001a643  mov     r14, [rax]
0x18001a646  add     r14, 30h ; '0'
0x18001a64a  jmp     short loc_18001A653
0x18001a64c  lea     r14, [rsi+88h]
0x18001a653  mov     rax, [rsi+78h]
0x18001a657  mov     r8d, ebp
0x18001a65a  mov     [rsp+0B8h+var_88], ecx
0x18001a65e  mov     [rsp+0B8h+var_90], r14
0x18001a663  mov     [rsp+0B8h+var_98], rax
0x18001a668  call    ?synchronous_vemgr_notification_on_new_thread@?$synchrozined_vemgr_notifications@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJKKKAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@0KK@Z; synchrozined_vemgr_notifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::synchronous_vemgr_notification_on_new_thread(ulong,ulong,ulong,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ulong,ulong)
0x18001a66d  mov     r15d, eax
0x18001a670  test    eax, eax
0x18001a672  jns     short loc_18001A6EF
0x18001a674  mov     ecx, [r14]
0x18001a677  mov     r10d, 0FFFFh
0x18001a67d  shr     ecx, 1
0x18001a67f  cmp     ecx, r10d
0x18001a682  ja      short loc_18001A689
0x18001a684  movzx   edx, cx
0x18001a687  jmp     short loc_18001A68C
0x18001a689  mov     edx, r10d
0x18001a68c  mov     eax, r12d
0x18001a68f  mov     r8, r12
0x18001a692  cmovbe  ax, dx
0x18001a696  test    ax, ax
0x18001a699  jz      short loc_18001A69F
0x18001a69b  mov     r8, [r14+8]
0x18001a69f  mov     r9, [rsi+78h]
0x18001a6a3  mov     ecx, [r9]
0x18001a6a6  shr     ecx, 1
0x18001a6a8  cmp     ecx, r10d
0x18001a6ab  ja      short loc_18001A6B2
0x18001a6ad  movzx   edx, cx
0x18001a6b0  jmp     short loc_18001A6B5
0x18001a6b2  mov     edx, r10d
0x18001a6b5  mov     eax, r12d
0x18001a6b8  cmovbe  ax, dx
0x18001a6bc  test    ax, ax
0x18001a6bf  jnz     short loc_18001A6C6
0x18001a6c1  mov     r9, r12
0x18001a6c4  jmp     short loc_18001A6CA
0x18001a6c6  mov     r9, [r9+8]
0x18001a6ca  xor     edx, edx
0x18001a6cc  mov     [rsp+0B8h+var_88], r15d
0x18001a6d1  mov     dword ptr [rsp+0B8h+var_90], ebp
0x18001a6d5  mov     [rsp+0B8h+var_98], r8
0x18001a6da  lea     r8, aVirtualenviron_11; "VirtualEnvironmentManager::ProcessTermi"...
0x18001a6e1  lea     ecx, [rdx+1]
0x18001a6e4  call    LogWrite
0x18001a6e9  test    edi, edi
0x18001a6eb  cmovns  edi, r15d
0x18001a6ef  mov     r8, rbx
0x18001a6f2  mov     edx, ebp
0x18001a6f4  mov     rcx, r13
0x18001a6f7  call    ?RemoveProcessFromVE@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJKAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessFromVE(ulong,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x18001a6fc  mov     esi, eax
0x18001a6fe  test    eax, eax
0x18001a700  jns     short loc_18001A707
0x18001a702  test    edi, edi
0x18001a704  cmovns  edi, eax
0x18001a707  cmp     rbx, [rsp+0B8h+var_58]
0x18001a70c  jz      short loc_18001A717
0x18001a70e  mov     rbx, [rbx+10h]
0x18001a712  jmp     loc_18001A625
0x18001a717  test    esi, esi
0x18001a719  jns     short loc_18001A745
0x18001a71b  xor     edx, edx
0x18001a71d  mov     [rsp+0B8h+var_88], esi
0x18001a721  lea     r9, dword_18001E3EC
0x18001a728  mov     dword ptr [rsp+0B8h+var_90], ebp
0x18001a72c  lea     r8, aVirtualenviron_9; "VirtualEnvironmentManager::RemoveProces"...
0x18001a733  mov     [rsp+0B8h+var_98], r9
0x18001a738  lea     ecx, [rdx+1]
0x18001a73b  call    LogWrite
0x18001a740  test    edi, edi
0x18001a742  cmovns  edi, esi
0x18001a745  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x18001a74c  jz      short loc_18001A75D
0x18001a74e  mov     r9d, ebp
0x18001a751  lea     rdx, VEMGR_Virtual_Process_Shutdown_Finish
0x18001a758  call    McTemplateK0q_EtwWriteTransfer
0x18001a75d  mov     esi, edi
0x18001a75f  lea     rcx, [rsp+0B8h+var_78]
0x18001a764  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x18001a769  test    cs:Microsoft_AppV_SharedPerformanceEnableBits, 1
0x18001a770  jz      short loc_18001A781
0x18001a772  mov     r9d, ebp
0x18001a775  lea     rdx, VEMGR_Process_Shutdown_Finish
0x18001a77c  call    McTemplateK0q_EtwWriteTransfer
0x18001a781  mov     eax, esi
0x18001a783  add     rsp, 78h
0x18001a787  pop     r15
0x18001a789  pop     r14
0x18001a78b  pop     r13
0x18001a78d  pop     r12
0x18001a78f  pop     rdi
0x18001a790  pop     rsi
0x18001a791  pop     rbp
0x18001a792  pop     rbx
0x18001a793  retn
```
