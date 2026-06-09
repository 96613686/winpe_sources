# VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddProcessToVE(ulong,ulong,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &,bool,int)

- ea: `0x180005ec4`
- end: `0x1800062b6`
- name: `?AddProcessToVE@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJKKAEAV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@_NH@Z`
- size: `1010`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x1800054e8`
- `0x180016f64`

## callees

- `0x180005a30`
- `0x180005ec4`
- `0x1800062bc`
- `0x1800086a0`
- `0x180008900`
- `0x1800099b4`
- `0x180009d44`
- `0x18000fbf4`
- `0x18001b3cc`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180005f6e`
- `ntoskrnl!KeReleaseMutex` at `0x180005fb6`
- `ntoskrnl!KeReleaseMutex` at `0x180005f6e`
- `ntoskrnl!KeReleaseMutex` at `0x180005fb6`
- `ntoskrnl!KeWaitForSingleObject` at `0x180005f1a`
- `ntoskrnl!KeWaitForSingleObject` at `0x180005f1a`

## string_xrefs

- `0x1800061f7`: `VirtualEnvironmentManager::ProcessCreatedNotificationUpcall() - Process created notification failed. Package moniker %s. User SID %s. Process %d. Error %d.`
- `0x1800060a9`: `VirtualEnvironmentManager::VECreatedNotificationUpcall() - VE created notification failed. Package moniker %s. User SID %s. Error %d.`

## pseudocode

```c
__int64 __fastcall VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddProcessToVE(
        __int64 a1,
        unsigned int a2,
        int a3,
        __int64 *a4,
        __int64 a5,
        char a6,
        unsigned int a7)
{
  void *v8; // rcx
  int v11; // esi
  __int64 v12; // rbx
  char v13; // r13
  int v14; // ecx
  volatile signed __int32 *v15; // rdi
  int v16; // r12d
  int v17; // r9d
  unsigned int v18; // eax
  __int64 v19; // rcx
  unsigned int v20; // eax
  __int64 v21; // r9
  int v22; // r12d
  unsigned int v23; // ecx
  __int64 v24; // rcx
  int v25; // edx
  int v26; // ecx
  unsigned int v27; // ecx
  __int64 v28; // rcx
  unsigned int v29; // eax
  __int64 v30; // r9
  unsigned int v31; // eax
  __int64 v32; // r9
  __int64 v34; // [rsp+28h] [rbp-48h]
  __int64 v35; // [rsp+28h] [rbp-48h]
  __int64 v36; // [rsp+30h] [rbp-40h]
  union _LARGE_INTEGER Timeout; // [rsp+50h] [rbp-20h] BYREF
  __int64 v38[3]; // [rsp+58h] [rbp-18h] BYREF
  int v39; // [rsp+B0h] [rbp+40h] BYREF
  int v40; // [rsp+C0h] [rbp+50h]

  v40 = a3;
  v8 = *(void **)(a1 + 72);
  v39 = 0;
  *(_OWORD *)v38 = 0;
  if ( v8 )
  {
    Timeout.QuadPart = -300000000;
    if ( KeWaitForSingleObject(v8, Executive, 0, 0, &Timeout) )
    {
      v11 = -1073741643;
      goto LABEL_9;
    }
  }
  v12 = a5;
  v11 = VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddProcessToVETracker(
          a1,
          a2,
          (_DWORD)a4,
          a5,
          a6,
          (__int64)v38,
          (__int64)&v39);
  if ( v11 < 0 )
  {
    KeReleaseMutex(*(PRKMUTEX *)(a1 + 72), 0);
    goto LABEL_9;
  }
  v13 = a7;
  v11 = ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddProcess(
          *(_QWORD *)(a1 + 16),
          a2,
          v38,
          a7);
  if ( v11 < 0 )
  {
    Timeout.LowPart = 0;
    VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessFromVETracker(
      (_QWORD *)a1,
      a2,
      v38,
      &Timeout);
  }
  KeReleaseMutex(*(PRKMUTEX *)(a1 + 72), 0);
  if ( v11 >= 0 )
  {
    v16 = v13 & 2;
    if ( v39 )
    {
      LOBYTE(v39) = v16 == 0;
      v11 = synchrozined_vemgr_notifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::synchronous_vemgr_notification_on_same_thread(
              v16 != 0 ? 8 : 0,
              1,
              a2,
              v40,
              *a4,
              v12,
              *(_DWORD *)(v38[0] + 112),
              v16 != 0 ? 8 : 0,
              v16 == 0);
      if ( v11 < 0 )
      {
        v18 = *(_DWORD *)v12 >> 1;
        if ( v18 <= 0xFFFF && (_WORD)v18 )
          v19 = *(_QWORD *)(v12 + 8);
        else
          v19 = 0;
        v20 = *(_DWORD *)*a4 >> 1;
        if ( v20 <= 0xFFFF && (_WORD)v20 )
          v21 = *(_QWORD *)(*a4 + 8);
        else
          v21 = 0;
        LODWORD(v34) = v11;
        LogWrite(
          1,
          0,
          L"VirtualEnvironmentManager::VECreatedNotificationUpcall() - VE created notification failed. Package moniker %s."
           " User SID %s. Error %d.",
          v21,
          v19,
          v34);
      }
      if ( v11 == -1073741749 )
      {
        v11 = 0;
      }
      else if ( v11 < 0 )
      {
        v25 = VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::TerminateVE(
                a1,
                a2,
                (_DWORD)a4,
                v17,
                v39);
        if ( v25 < 0 )
        {
          v27 = *(_DWORD *)v12 >> 1;
          if ( v27 <= 0xFFFF && (_WORD)v27 )
            v28 = *(_QWORD *)(v12 + 8);
          else
            v28 = 0;
          v29 = *(_DWORD *)*a4 >> 1;
          if ( v29 <= 0xFFFF && (_WORD)v29 )
            v30 = *(_QWORD *)(*a4 + 8);
          else
            v30 = 0;
          LODWORD(v34) = v25;
          LogWrite(
            1,
            0,
            L"VirtualEnvironmentManager::AddProcessToVE() - TerminateVE failed. Package %s, user %s, error %d",
            v30,
            v28,
            v34);
        }
        VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::VETerminatedNotificationUpcall(
          v26,
          a2,
          (_DWORD)a4,
          v12,
          *(_DWORD *)(v38[0] + 112));
        goto LABEL_9;
      }
    }
    if ( (v13 & 2) == 0 )
    {
      v22 = synchrozined_vemgr_notifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::synchronous_vemgr_notification_on_same_thread(
              v14,
              2,
              a2,
              v40,
              *a4,
              v12,
              *(_DWORD *)(v38[0] + 112),
              v13 & 1,
              1);
      if ( v22 < 0 )
      {
        v23 = *(_DWORD *)v12 >> 1;
        if ( v23 <= 0xFFFF && (_WORD)v23 )
          v24 = *(_QWORD *)(v12 + 8);
        else
          v24 = 0;
        v31 = *(_DWORD *)*a4 >> 1;
        if ( v31 <= 0xFFFF && (_WORD)v31 )
          v32 = *(_QWORD *)(*a4 + 8);
        else
          v32 = 0;
        LODWORD(v36) = v22;
        LODWORD(v35) = a2;
        LogWrite(
          1,
          0,
          L"VirtualEnvironmentManager::ProcessCreatedNotificationUpcall() - Process created notification failed. Package m"
           "oniker %s. User SID %s. Process %d. Error %d.",
          v32,
          v24,
          v35,
          v36);
      }
      v11 = 0;
      if ( v22 != -1073741749 )
        v11 = v22;
      if ( v11 >= 0 )
        goto LABEL_9;
      v39 = 0;
      if ( (int)VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessFromVEInternal(
                  a1,
                  a2,
                  v38,
                  &v39) >= 0
        && v39 )
      {
        VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::VETerminatedNotificationUpcall(
          *(_DWORD *)(v38[0] + 112),
          a2,
          (_DWORD)a4,
          v12,
          *(_DWORD *)(v38[0] + 112));
      }
    }
    v15 = (volatile signed __int32 *)v38[1];
    if ( v38[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v38[1] + 8), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          goto LABEL_58;
      }
    }
    return (unsigned int)v11;
  }
LABEL_9:
  v15 = (volatile signed __int32 *)v38[1];
  if ( v38[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v38[1] + 8), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
LABEL_58:
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 16LL))(v15);
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180005ec4  mov     [rsp-38h+arg_8], rbx
0x180005ec9  mov     [rsp-38h+arg_10], r8d
0x180005ece  push    rbp
0x180005ecf  push    rsi
0x180005ed0  push    rdi
0x180005ed1  push    r12
0x180005ed3  push    r13
0x180005ed5  push    r14
0x180005ed7  push    r15
0x180005ed9  mov     rbp, rsp
0x180005edc  sub     rsp, 70h
0x180005ee0  xor     r12d, r12d
0x180005ee3  mov     rdi, rcx
0x180005ee6  mov     rcx, [rcx+48h]; Object
0x180005eea  xorps   xmm0, xmm0
0x180005eed  mov     [rbp+arg_0], r12d
0x180005ef1  mov     r15, r9
0x180005ef4  mov     r14d, edx
0x180005ef7  movdqu  xmmword ptr [rbp+var_18], xmm0
0x180005efc  test    rcx, rcx
0x180005eff  jz      short loc_180005F34
0x180005f01  lea     rax, [rbp+var_20]
0x180005f05  mov     qword ptr [rbp+var_20], 0FFFFFFFFEE1E5D00h
0x180005f0d  xor     r9d, r9d; Alertable
0x180005f10  mov     [rsp+70h+Timeout], rax; Timeout
0x180005f15  xor     r8d, r8d; WaitMode
0x180005f18  xor     edx, edx; WaitReason
0x180005f1a  call    cs:__imp_KeWaitForSingleObject
0x180005f21  nop     dword ptr [rax+rax+00h]
0x180005f26  test    eax, eax
0x180005f28  jz      short loc_180005F34
0x180005f2a  mov     esi, 0C00000B5h
0x180005f2f  jmp     loc_180005FC6
0x180005f34  mov     rbx, [rbp+arg_20]
0x180005f38  lea     rax, [rbp+arg_0]
0x180005f3c  mov     [rsp+70h+var_40], rax
0x180005f41  mov     r9, rbx
0x180005f44  lea     rax, [rbp+var_18]
0x180005f48  mov     r8, r15
0x180005f4b  mov     [rsp+70h+var_48], rax
0x180005f50  mov     edx, r14d
0x180005f53  mov     al, [rbp+arg_28]
0x180005f56  mov     rcx, rdi
0x180005f59  mov     byte ptr [rsp+70h+Timeout], al
0x180005f5d  call    ?AddProcessToVETracker@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJKAEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@_NAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@3@AEAW4AddVEDisposition@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddProcessToVETracker(ulong,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,bool,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &,VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddVEDisposition &)
0x180005f62  mov     esi, eax
0x180005f64  test    eax, eax
0x180005f66  jns     short loc_180005F7C
0x180005f68  mov     rcx, [rdi+48h]; Mutex
0x180005f6c  xor     edx, edx; Wait
0x180005f6e  call    cs:__imp_KeReleaseMutex
0x180005f75  nop     dword ptr [rax+rax+00h]
0x180005f7a  jmp     short loc_180005FC6
0x180005f7c  mov     r13d, [rbp+arg_30]
0x180005f80  lea     r8, [rbp+var_18]
0x180005f84  mov     rcx, [rdi+10h]
0x180005f88  mov     r9d, r13d
0x180005f8b  mov     edx, r14d
0x180005f8e  call    ?AddProcess@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJKAEBV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@H@Z; ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddProcess(ulong,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &,int)
0x180005f93  mov     esi, eax
0x180005f95  test    eax, eax
0x180005f97  jns     short loc_180005FB0
0x180005f99  lea     r9, [rbp+var_20]
0x180005f9d  mov     dword ptr [rbp+var_20], r12d
0x180005fa1  lea     r8, [rbp+var_18]
0x180005fa5  mov     edx, r14d
0x180005fa8  mov     rcx, rdi
0x180005fab  call    ?RemoveProcessFromVETracker@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJKAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@AEAW4RemoveVEDisposition@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessFromVETracker(ulong,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &,VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVEDisposition &)
0x180005fb0  mov     rcx, [rdi+48h]; Mutex
0x180005fb4  xor     edx, edx; Wait
0x180005fb6  call    cs:__imp_KeReleaseMutex
0x180005fbd  nop     dword ptr [rax+rax+00h]
0x180005fc2  test    esi, esi
0x180005fc4  jns     short loc_18000600F
0x180005fc6  mov     rdi, [rbp+var_18+8]
0x180005fca  test    rdi, rdi
0x180005fcd  jz      loc_18000629B
0x180005fd3  or      ebx, 0FFFFFFFFh
0x180005fd6  mov     eax, ebx
0x180005fd8  lock xadd [rdi+8], eax
0x180005fdd  add     eax, ebx
0x180005fdf  jnz     loc_18000629B
0x180005fe5  mov     rax, [rdi]
0x180005fe8  mov     rcx, rdi
0x180005feb  mov     rax, [rax+8]
0x180005fef  call    _guard_dispatch_icall
0x180005ff4  mov     eax, ebx
0x180005ff6  lock xadd [rdi+0Ch], eax
0x180005ffb  add     eax, ebx
0x180005ffd  jnz     loc_18000629B
0x180006003  mov     rax, [rdi]
0x180006006  mov     rax, [rax+10h]
0x18000600a  jmp     loc_180006293
0x18000600f  mov     r12d, r13d
0x180006012  xor     edx, edx
0x180006014  and     r12d, 2
0x180006018  cmp     [rbp+arg_0], edx
0x18000601b  jz      loc_1800060CB
0x180006021  mov     r9d, [rbp+arg_10]
0x180006025  test    r12d, r12d
0x180006028  mov     eax, r12d
0x18000602b  mov     r8d, r14d
0x18000602e  setz    dl
0x180006031  neg     eax
0x180006033  mov     rax, [rbp+var_18]
0x180006037  mov     [rsp+70h+var_30], dl
0x18000603b  sbb     ecx, ecx
0x18000603d  and     ecx, 8
0x180006040  mov     byte ptr [rbp+arg_0], dl
0x180006043  mov     [rsp+70h+var_38], ecx
0x180006047  mov     edx, 1
0x18000604c  mov     eax, [rax+70h]
0x18000604f  mov     dword ptr [rsp+70h+var_40], eax
0x180006053  mov     rax, [r15]
0x180006056  mov     [rsp+70h+var_48], rbx
0x18000605b  mov     [rsp+70h+Timeout], rax
0x180006060  call    ?synchronous_vemgr_notification_on_same_thread@?$synchrozined_vemgr_notifications@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJKKKAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@0KK_N@Z; synchrozined_vemgr_notifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::synchronous_vemgr_notification_on_same_thread(ulong,ulong,ulong,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ulong,ulong,bool)
0x180006065  xor     edx, edx
0x180006067  mov     esi, eax
0x180006069  test    eax, eax
0x18000606b  jns     short loc_1800060C1
0x18000606d  mov     eax, [rbx]
0x18000606f  mov     r8d, 0FFFFh
0x180006075  shr     eax, 1
0x180006077  cmp     eax, r8d
0x18000607a  ja      short loc_180006087
0x18000607c  test    ax, ax
0x18000607f  jz      short loc_180006087
0x180006081  mov     rcx, [rbx+8]
0x180006085  jmp     short loc_18000608A
0x180006087  mov     rcx, rdx
0x18000608a  mov     r9, [r15]
0x18000608d  mov     eax, [r9]
0x180006090  shr     eax, 1
0x180006092  cmp     eax, r8d
0x180006095  ja      short loc_1800060A2
0x180006097  test    ax, ax
0x18000609a  jz      short loc_1800060A2
0x18000609c  mov     r9, [r9+8]
0x1800060a0  jmp     short loc_1800060A5
0x1800060a2  mov     r9, rdx
0x1800060a5  mov     dword ptr [rsp+70h+var_48], esi
0x1800060a9  lea     r8, aVirtualenviron_25; "VirtualEnvironmentManager::VECreatedNot"...
0x1800060b0  mov     [rsp+70h+Timeout], rcx
0x1800060b5  mov     ecx, 1
0x1800060ba  call    LogWrite
0x1800060bf  xor     edx, edx
0x1800060c1  cmp     esi, 0C000004Bh
0x1800060c7  jnz     short loc_18000613C
0x1800060c9  mov     esi, edx
0x1800060cb  test    r12d, r12d
0x1800060ce  jnz     loc_18000625B
0x1800060d4  mov     rax, [rbp+var_18]
0x1800060d8  lea     edx, [r12+2]
0x1800060dd  mov     r9d, [rbp+arg_10]
0x1800060e1  and     r13d, 1
0x1800060e5  mov     [rsp+70h+var_30], 1
0x1800060ea  mov     r8d, r14d
0x1800060ed  mov     [rsp+70h+var_38], r13d
0x1800060f2  mov     eax, [rax+70h]
0x1800060f5  mov     dword ptr [rsp+70h+var_40], eax
0x1800060f9  mov     rax, [r15]
0x1800060fc  mov     [rsp+70h+var_48], rbx
0x180006101  mov     [rsp+70h+Timeout], rax
0x180006106  call    ?synchronous_vemgr_notification_on_same_thread@?$synchrozined_vemgr_notifications@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJKKKAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@0KK_N@Z; synchrozined_vemgr_notifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::synchronous_vemgr_notification_on_same_thread(ulong,ulong,ulong,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ulong,ulong,bool)
0x18000610b  xor     r13d, r13d
0x18000610e  mov     r12d, eax
0x180006111  test    eax, eax
0x180006113  jns     loc_18000620B
0x180006119  mov     ecx, [rbx]
0x18000611b  mov     edx, 0FFFFh
0x180006120  shr     ecx, 1
0x180006122  cmp     ecx, edx
0x180006124  ja      loc_1800061CE
0x18000612a  test    cx, cx
0x18000612d  jz      loc_1800061CE
0x180006133  mov     rcx, [rbx+8]
0x180006137  jmp     loc_1800061D1
0x18000613c  test    esi, esi
0x18000613e  jns     short loc_1800060CB
0x180006140  mov     al, byte ptr [rbp+arg_0]
0x180006143  mov     r8, r15
0x180006146  mov     edx, r14d
0x180006149  mov     byte ptr [rsp+70h+Timeout], al
0x18000614d  mov     rcx, rdi
0x180006150  call    ?TerminateVE@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJKAEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@_N@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::TerminateVE(ulong,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,bool)
0x180006155  xor     r12d, r12d
0x180006158  mov     edx, eax
0x18000615a  test    eax, eax
0x18000615c  jns     short loc_1800061B0
0x18000615e  mov     ecx, [rbx]
0x180006160  mov     r8d, 0FFFFh
0x180006166  shr     ecx, 1
0x180006168  cmp     ecx, r8d
0x18000616b  ja      short loc_180006178
0x18000616d  test    cx, cx
0x180006170  jz      short loc_180006178
0x180006172  mov     rcx, [rbx+8]
0x180006176  jmp     short loc_18000617B
0x180006178  mov     rcx, r12
0x18000617b  mov     r9, [r15]
0x18000617e  mov     eax, [r9]
0x180006181  shr     eax, 1
0x180006183  cmp     eax, r8d
0x180006186  ja      short loc_180006193
0x180006188  test    ax, ax
0x18000618b  jz      short loc_180006193
0x18000618d  mov     r9, [r9+8]
0x180006191  jmp     short loc_180006196
0x180006193  mov     r9, r12
0x180006196  mov     dword ptr [rsp+70h+var_48], edx
0x18000619a  lea     r8, aVirtualenviron_18; "VirtualEnvironmentManager::AddProcessTo"...
0x1800061a1  xor     edx, edx
0x1800061a3  mov     [rsp+70h+Timeout], rcx
0x1800061a8  lea     ecx, [rdx+1]
0x1800061ab  call    LogWrite
0x1800061b0  mov     rax, [rbp+var_18]
0x1800061b4  mov     r9, rbx
0x1800061b7  mov     r8, r15
0x1800061ba  mov     edx, r14d
0x1800061bd  mov     eax, [rax+70h]
0x1800061c0  mov     dword ptr [rsp+70h+Timeout], eax
0x1800061c4  call    ?VETerminatedNotificationUpcall@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJKAEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@K@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::VETerminatedNotificationUpcall(ulong,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ulong)
0x1800061c9  jmp     loc_180005FC6
0x1800061ce  mov     rcx, r13
0x1800061d1  mov     r9, [r15]
0x1800061d4  mov     eax, [r9]
0x1800061d7  shr     eax, 1
0x1800061d9  cmp     eax, edx
0x1800061db  ja      short loc_1800061E8
0x1800061dd  test    ax, ax
0x1800061e0  jz      short loc_1800061E8
0x1800061e2  mov     r9, [r9+8]
0x1800061e6  jmp     short loc_1800061EB
0x1800061e8  mov     r9, r13
0x1800061eb  xor     edx, edx
0x1800061ed  mov     dword ptr [rsp+70h+var_40], r12d
0x1800061f2  mov     dword ptr [rsp+70h+var_48], r14d
0x1800061f7  lea     r8, aVirtualenviron_13; "VirtualEnvironmentManager::ProcessCreat"...
0x1800061fe  mov     [rsp+70h+Timeout], rcx
0x180006203  lea     ecx, [rdx+1]
0x180006206  call    LogWrite
0x18000620b  cmp     r12d, 0C000004Bh
0x180006212  mov     esi, r13d
0x180006215  cmovnz  esi, r12d
0x180006219  test    esi, esi
0x18000621b  jns     loc_180005FC6
0x180006221  lea     r9, [rbp+arg_0]
0x180006225  mov     [rbp+arg_0], r13d
0x180006229  lea     r8, [rbp+var_18]
0x18000622d  mov     edx, r14d
0x180006230  mov     rcx, rdi
0x180006233  call    ?RemoveProcessFromVEInternal@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJKAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@AEAW4RemoveVEDisposition@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessFromVEInternal(ulong,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &,VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVEDisposition &)
0x180006238  test    eax, eax
0x18000623a  js      short loc_18000625B
0x18000623c  cmp     [rbp+arg_0], r13d
0x180006240  jz      short loc_18000625B
0x180006242  mov     rax, [rbp+var_18]
0x180006246  mov     r9, rbx
0x180006249  mov     r8, r15
0x18000624c  mov     edx, r14d
0x18000624f  mov     ecx, [rax+70h]
0x180006252  mov     dword ptr [rsp+70h+Timeout], ecx
0x180006256  call    ?VETerminatedNotificationUpcall@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJKAEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@K@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::VETerminatedNotificationUpcall(ulong,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ulong)
0x18000625b  mov     rdi, [rbp+var_18+8]
0x18000625f  test    rdi, rdi
0x180006262  jz      short loc_18000629B
0x180006264  or      ebx, 0FFFFFFFFh
0x180006267  mov     eax, ebx
0x180006269  lock xadd [rdi+8], eax
0x18000626e  add     eax, ebx
0x180006270  jnz     short loc_18000629B
0x180006272  mov     rax, [rdi]
0x180006275  mov     rcx, rdi
0x180006278  mov     rax, [rax+8]
0x18000627c  call    _guard_dispatch_icall
0x180006281  mov     edx, ebx
0x180006283  lock xadd [rdi+0Ch], edx
0x180006288  add     edx, ebx
0x18000628a  jnz     short loc_18000629B
0x18000628c  mov     rdx, [rdi]
0x18000628f  mov     rax, [rdx+10h]
0x180006293  mov     rcx, rdi
0x180006296  call    _guard_dispatch_icall
0x18000629b  mov     rbx, [rsp+70h+arg_8]
0x1800062a3  mov     eax, esi
0x1800062a5  add     rsp, 70h
0x1800062a9  pop     r15
0x1800062ab  pop     r14
0x1800062ad  pop     r13
0x1800062af  pop     r12
0x1800062b1  pop     rdi
0x1800062b2  pop     rsi
0x1800062b3  pop     rbp
0x1800062b4  retn
```
