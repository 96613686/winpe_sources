# VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddProcessToVETracker(ulong,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,bool,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &,VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddVEDisposition &)

- ea: `0x1800062bc`
- end: `0x18000645a`
- name: `?AddProcessToVETracker@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJKAEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@_NAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@3@AEAW4AddVEDisposition@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z`
- size: `414`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int, __int64, __int64, char, __int64 *, _DWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180005ec4`

## callees

- `0x180001c98`
- `0x180005890`
- `0x1800062bc`
- `0x180006460`
- `0x180006764`
- `0x180006cac`
- `0x1800071a0`
- `0x180007f88`
- `0x1800090c4`
- `0x18001b3cc`

## string_xrefs

- `0x180006435`: `VirtualEnvironmentManager::AddProcessToVETracker() - Virtual Environment created. Package moniker %s. User SID %d.`

## pseudocode

```c
__int64 __fastcall VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddProcessToVETracker(
        _QWORD *a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        char a5,
        __int64 *a6,
        _DWORD *a7)
{
  __int64 *v7; // rdi
  int v12; // r9d
  __int64 result; // rax
  _DWORD *v14; // rsi
  __int64 v15; // rcx
  unsigned int v16; // ecx
  __int16 v17; // dx
  int v18; // ebp
  __int64 v19; // rcx
  __int16 v20; // ax
  __int64 v21; // rdx
  unsigned int v22; // ecx
  __int16 v23; // r8
  __int16 v24; // ax
  __int64 v25; // r9
  int v26; // [rsp+80h] [rbp+8h] BYREF

  v7 = a6;
  if ( (int)VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindVirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
              *a1,
              a3,
              a4,
              a6) >= 0
    || (LOBYTE(v12) = a5,
        result = VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CreateVEObject(
                   (_DWORD)a1,
                   a3,
                   a4,
                   v12,
                   (__int64)v7),
        (int)result >= 0) )
  {
    v14 = a7;
    result = VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddVirtualProcess(
               *a1,
               v7,
               a2,
               a7);
    if ( (int)result >= 0 )
    {
      if ( *v14 )
      {
        v15 = a1[7];
        LOBYTE(v26) = 0;
        if ( (int)ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsVfsStateDisabled(
                    v15,
                    &v26) >= 0
          && (_BYTE)v26 )
        {
          LogWrite(
            4,
            0,
            L"VirtualEnvironmentManager::AddProcessToVETracker() - Add volume operation not sent to VFS because the VFS ha"
             "s been set to disabled.");
        }
        else
        {
          v18 = VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddVolumes(
                  a1[6],
                  *v7 + 168);
          if ( v18 < 0 )
          {
            v19 = *a1;
            v26 = 0;
            VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVirtualProcess(
              v19,
              v7,
              a2,
              &v26);
            return (unsigned int)v18;
          }
        }
        if ( *v14 == 2 )
          VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddPackageNotification(
            (__int64)a1,
            *v7);
        VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddUserNotification(
          a1,
          *v7 + 40);
        v16 = *(_DWORD *)a4 >> 1;
        if ( v16 > 0xFFFF )
          v17 = -1;
        else
          v17 = *(_DWORD *)a4 >> 1;
        v20 = 0;
        if ( v16 <= 0xFFFF )
          v20 = v17;
        v21 = 0;
        if ( v20 )
          v21 = *(_QWORD *)(a4 + 8);
        v22 = **(_DWORD **)a3 >> 1;
        if ( v22 > 0xFFFF )
          v23 = -1;
        else
          v23 = **(_DWORD **)a3 >> 1;
        v24 = 0;
        if ( v22 <= 0xFFFF )
          v24 = v23;
        if ( v24 )
          v25 = *(_QWORD *)(*(_QWORD *)a3 + 8LL);
        else
          v25 = 0;
        LogWrite(
          3,
          0,
          L"VirtualEnvironmentManager::AddProcessToVETracker() - Virtual Environment created. Package moniker %s. User SID %d.",
          v25,
          v21);
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800062bc  push    rbx
0x1800062be  push    rbp
0x1800062bf  push    rsi
0x1800062c0  push    rdi
0x1800062c1  push    r12
0x1800062c3  push    r13
0x1800062c5  push    r14
0x1800062c7  push    r15
0x1800062c9  sub     rsp, 38h
0x1800062cd  mov     rdi, [rsp+78h+arg_28]
0x1800062d5  mov     r14, r9
0x1800062d8  mov     r12, r8
0x1800062db  mov     r15d, edx
0x1800062de  mov     rbx, rcx
0x1800062e1  mov     r9, rdi
0x1800062e4  mov     rcx, [rcx]
0x1800062e7  mov     r8, r14
0x1800062ea  mov     rdx, r12
0x1800062ed  call    ??$FindVirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@2@@Z; VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindVirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x1800062f2  xor     r13d, r13d
0x1800062f5  test    eax, eax
0x1800062f7  jns     short loc_18000631C
0x1800062f9  mov     r9b, [rsp+78h+arg_20]
0x180006301  mov     r8, r14
0x180006304  mov     rdx, r12
0x180006307  mov     [rsp+78h+var_58], rdi
0x18000630c  mov     rcx, rbx
0x18000630f  call    ?CreateVEObject@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@_NAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@3@@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CreateVEObject(kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,bool,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x180006314  test    eax, eax
0x180006316  js      loc_180006448
0x18000631c  mov     rsi, [rsp+78h+arg_30]
0x180006324  mov     r8d, r15d
0x180006327  mov     rcx, [rbx]
0x18000632a  mov     r9, rsi
0x18000632d  mov     rdx, rdi
0x180006330  call    ?AddVirtualProcess@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@KAEAW4AddVEDisposition@1@@Z; VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddVirtualProcess(kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &,ulong,VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddVEDisposition &)
0x180006335  test    eax, eax
0x180006337  js      loc_180006448
0x18000633d  cmp     [rsi], r13d
0x180006340  jz      loc_180006446
0x180006346  mov     rcx, [rbx+38h]
0x18000634a  lea     rdx, [rsp+78h+arg_0]
0x180006352  mov     byte ptr [rsp+78h+arg_0], r13b
0x18000635a  call    ?IsVfsStateDisabled@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEA_N@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsVfsStateDisabled(bool &)
0x18000635f  test    eax, eax
0x180006361  js      short loc_1800063B2
0x180006363  cmp     byte ptr [rsp+78h+arg_0], r13b
0x18000636b  jz      short loc_1800063B2
0x18000636d  xor     edx, edx
0x18000636f  lea     r8, aVirtualenviron_26; "VirtualEnvironmentManager::AddProcessTo"...
0x180006376  lea     ecx, [rdx+4]
0x180006379  call    LogWrite
0x18000637e  cmp     dword ptr [rsi], 2
0x180006381  jnz     short loc_18000638E
0x180006383  mov     rdx, [rdi]
0x180006386  mov     rcx, rbx
0x180006389  call    ?AddPackageNotification@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAXAEBV?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddPackageNotification(appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info> const &)
0x18000638e  mov     rdx, [rdi]
0x180006391  mov     rcx, rbx
0x180006394  add     rdx, 28h ; '('
0x180006398  call    ?AddUserNotification@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAXAEBV?$doubly_linked_list@V?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddUserNotification(appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info> const &)
0x18000639d  mov     ecx, [r14]
0x1800063a0  mov     r10d, 0FFFFh
0x1800063a6  shr     ecx, 1
0x1800063a8  cmp     ecx, r10d
0x1800063ab  ja      short loc_1800063ED
0x1800063ad  movzx   edx, cx
0x1800063b0  jmp     short loc_1800063F0
0x1800063b2  mov     rdx, [rdi]
0x1800063b5  mov     rcx, [rbx+30h]
0x1800063b9  add     rdx, 0A8h
0x1800063c0  call    ?AddVolumes@?$VfsVolumeManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddVolumes(appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &)
0x1800063c5  mov     ebp, eax
0x1800063c7  test    eax, eax
0x1800063c9  jns     short loc_18000637E
0x1800063cb  mov     rcx, [rbx]
0x1800063ce  lea     r9, [rsp+78h+arg_0]
0x1800063d6  mov     r8d, r15d
0x1800063d9  mov     [rsp+78h+arg_0], r13d
0x1800063e1  mov     rdx, rdi
0x1800063e4  call    ?RemoveVirtualProcess@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@KAEAW4RemoveVEDisposition@1@@Z; VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVirtualProcess(kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &,ulong,VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVEDisposition &)
0x1800063e9  mov     eax, ebp
0x1800063eb  jmp     short loc_180006448
0x1800063ed  mov     edx, r10d
0x1800063f0  mov     eax, r13d
0x1800063f3  cmovbe  ax, dx
0x1800063f7  mov     rdx, r13
0x1800063fa  test    ax, ax
0x1800063fd  jz      short loc_180006403
0x1800063ff  mov     rdx, [r14+8]
0x180006403  mov     r9, [r12]
0x180006407  mov     ecx, [r9]
0x18000640a  shr     ecx, 1
0x18000640c  cmp     ecx, r10d
0x18000640f  ja      short loc_180006417
0x180006411  movzx   r8d, cx
0x180006415  jmp     short loc_18000641A
0x180006417  mov     r8d, r10d
0x18000641a  mov     eax, r13d
0x18000641d  cmovbe  ax, r8w
0x180006422  test    ax, ax
0x180006425  jnz     short loc_18000642C
0x180006427  mov     r9, r13
0x18000642a  jmp     short loc_180006430
0x18000642c  mov     r9, [r9+8]
0x180006430  mov     [rsp+78h+var_58], rdx
0x180006435  lea     r8, aVirtualenviron_2; "VirtualEnvironmentManager::AddProcessTo"...
0x18000643c  xor     edx, edx
0x18000643e  lea     ecx, [rdx+3]
0x180006441  call    LogWrite
0x180006446  xor     eax, eax
0x180006448  add     rsp, 38h
0x18000644c  pop     r15
0x18000644e  pop     r14
0x180006450  pop     r13
0x180006452  pop     r12
0x180006454  pop     rdi
0x180006455  pop     rsi
0x180006456  pop     rbp
0x180006457  pop     rbx
0x180006458  retn
```
