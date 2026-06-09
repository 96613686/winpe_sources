# ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPackagePublished<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ulong,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> &,bool &)

- ea: `0x180001f78`
- end: `0x1800021c7`
- name: `??$IsPackagePublished@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA_NAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@K1AEAV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@2@AEA_N@Z`
- size: `591`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007840`
- `0x180018964`
- `0x180018b9c`

## callees

- `0x180001d4c`
- `0x180001f78`
- `0x1800021d0`
- `0x18000324c`
- `0x180005178`
- `0x180005430`
- `0x18000fdc0`
- `0x18001b3cc`
- `0x18001baf0`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x180002036`
- `ntoskrnl!EtwActivityIdControl` at `0x180002036`

## string_xrefs

- `0x180002045`: `ConfigurationManager::IsPackagePublished() - Failed to retrieve list of published package groups. Error %d.`

## pseudocode

```c
char __fastcall ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPackagePublished<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
        __int64 a1,
        const UNICODE_STRING ***a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        const UNICODE_STRING **a6,
        _BYTE *a7)
{
  const UNICODE_STRING **v8; // rdx
  __int64 v10; // r14
  const UNICODE_STRING **v11; // r12
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // r14d
  __int64 v15; // rdx
  __int64 v16; // r8
  int v18; // eax
  char v19; // bl
  __int64 v20; // r8
  const UNICODE_STRING ***v21; // rdx
  unsigned int v22; // ecx
  __int16 v23; // dx
  __int16 v24; // ax
  __int64 v25; // r9
  const UNICODE_STRING **v26; // rdx
  __int64 v27; // rdx
  char v28; // al
  volatile signed __int32 *v29; // rbx
  char v30; // di
  int v32; // [rsp+38h] [rbp-59h] BYREF
  __int128 v33; // [rsp+40h] [rbp-51h] BYREF
  __int128 *v34; // [rsp+50h] [rbp-41h]
  const UNICODE_STRING ***v35; // [rsp+58h] [rbp-39h]
  __int128 v36; // [rsp+60h] [rbp-31h] BYREF
  GUID ActivityId; // [rsp+70h] [rbp-21h] BYREF

  v8 = *a2;
  v10 = a3;
  v11 = a6 + 1;
  *a6 = *v8;
  *(_QWORD *)&v36 = a3;
  kernel_std::detail::shared_count::operator=(a6 + 1, v8 + 1);
  if ( *((_DWORD *)*a2 + 24) )
  {
    v32 = 0;
    v35 = (const UNICODE_STRING ***)&v33;
    v34 = &v33;
    v33 = 0;
    v14 = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::GetPublishedPackageGroups<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
            a1,
            (_DWORD)a2,
            v10,
            (unsigned int)&v32,
            a4);
    if ( v14 < 0 )
    {
      ActivityId = GUID_NULL;
      EtwActivityIdControl(1u, &ActivityId);
      LogWrite(
        1,
        0,
        L"ConfigurationManager::IsPackagePublished() - Failed to retrieve list of published package groups. Error %d.",
        (unsigned int)v14);
      appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(
        &v32,
        v15,
        v16);
      return 0;
    }
    v18 = v32;
    if ( v32 )
    {
      v19 = 1;
      *a7 = 0;
      if ( v18 <= 1 )
      {
        v21 = v35;
      }
      else
      {
        appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::insertion_sort<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_by_group_priority>(&v32);
        v21 = v35;
        if ( *((_DWORD *)*v35 + 14) == LODWORD((*v35[3])[3].Buffer) )
        {
          if ( (byte_180027405 & 4) != 0 )
          {
            v22 = *(_DWORD *)a5 >> 1;
            if ( v22 > 0xFFFF )
              v23 = -1;
            else
              v23 = *(_DWORD *)a5 >> 1;
            v24 = 0;
            v25 = 0;
            if ( v22 <= 0xFFFF )
              v24 = v23;
            if ( v24 )
              v25 = *(_QWORD *)(a5 + 8);
            McTemplateK0z_EtwWriteTransfer(
              PROVIDER_MICROSOFT_APPV_CLIENT_Context,
              APPV_CLIENT_Evt_AppLaunchFailedAmbiguousVE,
              &GUID_NULL,
              v25);
          }
          v19 = 0;
          goto LABEL_19;
        }
      }
      v26 = *v21;
      *a6 = *v26;
      kernel_std::detail::shared_count::operator=(v11, v26 + 1);
LABEL_19:
      appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(
        &v32,
        v21,
        v20);
      return v19;
    }
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(
      &v32,
      v12,
      v13);
    v10 = v36;
  }
  *a7 = 1;
  v27 = (__int64)(*a2 + 1);
  *a6 = **a2;
  kernel_std::detail::shared_count::operator=(v11, v27);
  v36 = 0;
  v28 = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPublishedForUser_Internal<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
          a1,
          a6,
          &v36,
          v10,
          a4);
  v29 = (volatile signed __int32 *)*((_QWORD *)&v36 + 1);
  v30 = v28;
  if ( *((_QWORD *)&v36 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v36 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
      if ( !_InterlockedDecrement(v29 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 16LL))(v29);
    }
  }
  return v30;
}

```

## disassembly

```asm
0x180001f78  push    rbp
0x180001f7a  push    rbx
0x180001f7b  push    rsi
0x180001f7c  push    rdi
0x180001f7d  push    r12
0x180001f7f  push    r13
0x180001f81  push    r14
0x180001f83  push    r15
0x180001f85  lea     rbp, [rsp-7]
0x180001f8a  sub     rsp, 98h
0x180001f91  mov     rax, cs:__security_cookie
0x180001f98  xor     rax, rsp
0x180001f9b  mov     [rbp+3Fh+var_50], rax
0x180001f9f  mov     rsi, [rbp+3Fh+arg_28]
0x180001fa3  mov     r13, rdx
0x180001fa6  mov     rdx, [rdx]
0x180001fa9  mov     rbx, rcx
0x180001fac  mov     rdi, [rbp+3Fh+arg_20]
0x180001fb0  mov     r14, r8
0x180001fb3  mov     r15, [rbp+3Fh+arg_30]
0x180001fb7  lea     r12, [rsi+8]
0x180001fbb  mov     [rbp+3Fh+var_A0], r9d
0x180001fbf  mov     rax, [rdx]
0x180001fc2  mov     rcx, r12
0x180001fc5  add     rdx, 8
0x180001fc9  mov     [rsi], rax
0x180001fcc  mov     qword ptr [rbp+3Fh+var_70], r8
0x180001fd0  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x180001fd5  mov     rax, [r13+0]
0x180001fd9  xor     ecx, ecx
0x180001fdb  cmp     [rax+60h], ecx
0x180001fde  jz      loc_180002125
0x180001fe4  lea     rax, [rbp+3Fh+var_90]
0x180001fe8  mov     [rbp+3Fh+var_98], ecx
0x180001feb  mov     [rbp+3Fh+var_78], rax
0x180001fef  lea     r9, [rbp+3Fh+var_98]
0x180001ff3  lea     rax, [rbp+3Fh+var_90]
0x180001ff7  xorps   xmm0, xmm0
0x180001ffa  mov     [rbp+3Fh+var_80], rax
0x180001ffe  mov     r8, r14
0x180002001  mov     eax, [rbp+3Fh+var_A0]
0x180002004  mov     rdx, r13
0x180002007  mov     rcx, rbx
0x18000200a  mov     [rsp+0D0h+var_B0], eax
0x18000200e  movdqu  [rbp+3Fh+var_90], xmm0
0x180002013  call    ??$GetPublishedPackageGroups@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@456@K@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::GetPublishedPackageGroups<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info> &,ulong)
0x180002018  mov     r14d, eax
0x18000201b  test    eax, eax
0x18000201d  jns     short loc_180002065
0x18000201f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180002026  mov     ebx, 1
0x18000202b  lea     rdx, [rbp+3Fh+ActivityId]; ActivityId
0x18000202f  mov     ecx, ebx; ControlCode
0x180002031  movdqu  xmmword ptr [rbp+3Fh+ActivityId.Data1], xmm0
0x180002036  call    cs:__imp_EtwActivityIdControl
0x18000203d  nop     dword ptr [rax+rax+00h]
0x180002042  mov     r9d, r14d
0x180002045  lea     r8, aConfigurationm_4; "ConfigurationManager::IsPackagePublishe"...
0x18000204c  xor     edx, edx
0x18000204e  mov     ecx, ebx
0x180002050  call    LogWrite
0x180002055  lea     rcx, [rbp+3Fh+var_98]
0x180002059  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x18000205e  xor     al, al
0x180002060  jmp     loc_1800021A6
0x180002065  mov     eax, [rbp+3Fh+var_98]
0x180002068  xor     r14d, r14d
0x18000206b  test    eax, eax
0x18000206d  jz      loc_180002118
0x180002073  lea     ebx, [r14+1]
0x180002077  mov     [r15], r14b
0x18000207a  cmp     eax, ebx
0x18000207c  jle     short loc_1800020EF
0x18000207e  lea     rcx, [rbp+3Fh+var_98]
0x180002082  call    ??$insertion_sort@Uless_by_group_priority@?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAXAEAUless_by_group_priority@?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::insertion_sort<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_by_group_priority>(Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_by_group_priority &)
0x180002087  mov     rdx, [rbp+3Fh+var_78]
0x18000208b  mov     rax, [rdx+18h]
0x18000208f  mov     rcx, [rdx]
0x180002092  mov     rax, [rax]
0x180002095  mov     eax, [rax+38h]
0x180002098  cmp     [rcx+38h], eax
0x18000209b  jnz     short loc_1800020F3
0x18000209d  test    cs:byte_180027405, 4
0x1800020a4  jz      short loc_1800020EA
0x1800020a6  mov     ecx, [rdi]
0x1800020a8  mov     r8d, 0FFFFh
0x1800020ae  shr     ecx, 1
0x1800020b0  cmp     ecx, r8d
0x1800020b3  ja      short loc_1800020BA
0x1800020b5  movzx   edx, cx
0x1800020b8  jmp     short loc_1800020BD
0x1800020ba  mov     edx, r8d
0x1800020bd  mov     eax, r14d
0x1800020c0  mov     r9, r14
0x1800020c3  cmovbe  ax, dx
0x1800020c7  test    ax, ax
0x1800020ca  jz      short loc_1800020D0
0x1800020cc  mov     r9, [rdi+8]
0x1800020d0  lea     r8, GUID_NULL
0x1800020d7  lea     rdx, APPV_CLIENT_Evt_AppLaunchFailedAmbiguousVE
0x1800020de  lea     rcx, PROVIDER_MICROSOFT_APPV_CLIENT_Context
0x1800020e5  call    McTemplateK0z_EtwWriteTransfer
0x1800020ea  mov     bl, r14b
0x1800020ed  jmp     short loc_180002108
0x1800020ef  mov     rdx, [rbp+3Fh+var_78]
0x1800020f3  mov     rdx, [rdx]
0x1800020f6  mov     rcx, r12
0x1800020f9  mov     rax, [rdx]
0x1800020fc  add     rdx, 8
0x180002100  mov     [rsi], rax
0x180002103  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x180002108  lea     rcx, [rbp+3Fh+var_98]
0x18000210c  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x180002111  mov     al, bl
0x180002113  jmp     loc_1800021A6
0x180002118  lea     rcx, [rbp+3Fh+var_98]
0x18000211c  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x180002121  mov     r14, qword ptr [rbp+3Fh+var_70]
0x180002125  mov     byte ptr [r15], 1
0x180002129  mov     rcx, r12
0x18000212c  mov     rdx, [r13+0]
0x180002130  mov     rax, [rdx]
0x180002133  add     rdx, 8
0x180002137  mov     [rsi], rax
0x18000213a  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x18000213f  mov     eax, [rbp+3Fh+var_A0]
0x180002142  lea     r8, [rbp+3Fh+var_70]
0x180002146  xorps   xmm0, xmm0
0x180002149  mov     [rsp+0D0h+var_B0], eax
0x18000214d  mov     r9, r14
0x180002150  mov     rdx, rsi
0x180002153  mov     rcx, rbx
0x180002156  movdqu  [rbp+3Fh+var_70], xmm0
0x18000215b  call    ??$IsPublishedForUser_Internal@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAA_NAEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@0AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@K@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPublishedForUser_Internal<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ulong)
0x180002160  mov     rbx, qword ptr [rbp+3Fh+var_70+8]
0x180002164  mov     dil, al
0x180002167  test    rbx, rbx
0x18000216a  jz      short loc_1800021A3
0x18000216c  or      esi, 0FFFFFFFFh
0x18000216f  mov     ecx, esi
0x180002171  lock xadd [rbx+8], ecx
0x180002176  add     ecx, esi
0x180002178  jnz     short loc_1800021A3
0x18000217a  mov     rdx, [rbx]
0x18000217d  mov     rcx, rbx
0x180002180  mov     rax, [rdx+8]
0x180002184  call    _guard_dispatch_icall
0x180002189  mov     eax, esi
0x18000218b  lock xadd [rbx+0Ch], eax
0x180002190  add     eax, esi
0x180002192  jnz     short loc_1800021A3
0x180002194  mov     rax, [rbx]
0x180002197  mov     rcx, rbx
0x18000219a  mov     rax, [rax+10h]
0x18000219e  call    _guard_dispatch_icall
0x1800021a3  mov     al, dil
0x1800021a6  mov     rcx, [rbp+3Fh+var_50]
0x1800021aa  xor     rcx, rsp; StackCookie
0x1800021ad  call    __security_check_cookie
0x1800021b2  add     rsp, 98h
0x1800021b9  pop     r15
0x1800021bb  pop     r14
0x1800021bd  pop     r13
0x1800021bf  pop     r12
0x1800021c1  pop     rdi
0x1800021c2  pop     rsi
0x1800021c3  pop     rbx
0x1800021c4  pop     rbp
0x1800021c5  retn
```
