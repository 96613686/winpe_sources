# VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CreateVEObject(kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,bool,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)

- ea: `0x1800071a0`
- end: `0x180007837`
- name: `?CreateVEObject@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@_NAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@3@@Z`
- size: `1687`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x1800062bc`

## callees

- `0x180001598`
- `0x18000199c`
- `0x180001bec`
- `0x180003e74`
- `0x1800048d8`
- `0x180004a90`
- `0x180005178`
- `0x180005200`
- `0x1800071a0`
- `0x18000e588`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180007338`
- `ntoskrnl!ExAllocatePool2` at `0x180007608`
- `ntoskrnl!ExAllocatePool2` at `0x180007338`
- `ntoskrnl!ExAllocatePool2` at `0x180007608`
- `ntoskrnl!ExFreePoolWithTag` at `0x180007290`
- `ntoskrnl!ExFreePoolWithTag` at `0x180007290`
- `ntoskrnl!RtlInitUnicodeString` at `0x180007257`
- `ntoskrnl!RtlInitUnicodeString` at `0x180007257`

## pseudocode

```c
__int64 __fastcall VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CreateVEObject(
        __int64 a1,
        __int64 *a2,
        int a3,
        char a4,
        _QWORD *a5)
{
  __int64 v6; // rdx
  __int64 v8; // rcx
  int v10; // esi
  volatile signed __int32 *v11; // rbx
  bool v12; // zf
  __int64 v14; // rbx
  int v15; // r14d
  volatile signed __int32 *v16; // rbx
  volatile signed __int32 *v17; // rbx
  __int64 v18; // rax
  volatile signed __int32 *v19; // rbx
  volatile signed __int32 *v20; // rsi
  __int64 v21; // rax
  _QWORD *v22; // r15
  __int64 v23; // rax
  volatile signed __int32 *v24; // rbx
  char *v25; // r15
  char *i; // rbx
  int v27; // eax
  volatile signed __int32 *v28; // rbx
  volatile signed __int32 *v29; // rbx
  __int64 Pool2; // rax
  __int64 v31; // rax
  _QWORD *v32; // rbx
  __int64 v33; // rax
  volatile signed __int32 *v34; // rbx
  volatile signed __int32 *v35; // rbx
  volatile signed __int32 *v36; // rbx
  __int128 v37; // [rsp+30h] [rbp-71h] BYREF
  __int128 v38; // [rsp+40h] [rbp-61h] BYREF
  PVOID P[2]; // [rsp+50h] [rbp-51h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-41h] BYREF
  int v41; // [rsp+70h] [rbp-31h] BYREF
  __int128 v42; // [rsp+78h] [rbp-29h] BYREF
  __int128 *v43; // [rsp+88h] [rbp-19h]
  __int128 *v44; // [rsp+90h] [rbp-11h]
  int v45; // [rsp+98h] [rbp-9h] BYREF
  __int128 v46; // [rsp+A0h] [rbp-1h] BYREF
  __int128 *v47; // [rsp+B0h] [rbp+Fh]
  __int128 *v48; // [rsp+B8h] [rbp+17h]
  int v50; // [rsp+118h] [rbp+77h] BYREF

  v6 = *a2;
  v8 = *(_QWORD *)(a1 + 56);
  v38 = 0;
  v37 = 0;
  if ( !a4 )
  {
    v45 = 0;
    v48 = &v46;
    v41 = 0;
    v47 = &v46;
    v44 = &v42;
    v43 = &v42;
    v46 = 0;
    v42 = 0;
    *(_OWORD *)P = 0;
    v50 = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindPackageGroup<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
            v8,
            v6,
            P);
    v15 = v50;
    if ( v50 < 0 )
    {
      v24 = (volatile signed __int32 *)P[1];
      if ( P[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)P[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
          if ( !_InterlockedDecrement(v24 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 16LL))(v24);
        }
      }
      appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>(&v41);
      appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)&v45);
      return (unsigned int)v15;
    }
    v25 = (char *)P[0];
    for ( i = (char *)*((_QWORD *)P[0] + 6); i != v25 + 24; i = (char *)*((_QWORD *)i + 3) )
    {
      v10 = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindPackage<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
              *(_QWORD *)(a1 + 56),
              *(_QWORD *)i,
              &v38);
      if ( v10 < 0 )
        goto LABEL_47;
      v27 = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindUser<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
              *(_QWORD *)(a1 + 56),
              *(_QWORD *)i,
              *a2,
              a3,
              (__int64)&v37);
      v10 = v27;
      if ( v27 >= 0 )
      {
        v10 = appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
                &v45,
                &v38);
        if ( v10 < 0
          || (v10 = appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
                      &v41,
                      &v37),
              v10 < 0) )
        {
LABEL_47:
          v28 = (volatile signed __int32 *)P[1];
          if ( P[1] )
          {
            if ( !_InterlockedDecrement((volatile signed __int32 *)P[1] + 2) )
            {
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
              if ( !_InterlockedDecrement(v28 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 16LL))(v28);
            }
          }
          appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>(&v41);
          appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)&v45);
          v29 = (volatile signed __int32 *)*((_QWORD *)&v37 + 1);
          if ( *((_QWORD *)&v37 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v37 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
              if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 16LL))(v29);
            }
          }
          v11 = (volatile signed __int32 *)*((_QWORD *)&v38 + 1);
          if ( *((_QWORD *)&v38 + 1) )
          {
            v12 = _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v38 + 1) + 8LL), 0xFFFFFFFF) == 1;
            goto LABEL_5;
          }
          return (unsigned int)v10;
        }
      }
      else if ( v27 != -1073741772 )
      {
        goto LABEL_47;
      }
    }
    Pool2 = ExAllocatePool2(256, 208, 1733125462);
    if ( Pool2 )
    {
      v31 = VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(
              Pool2,
              (_DWORD)a2,
              (unsigned int)&v45,
              (unsigned int)&v41,
              (__int64)&v50);
      v15 = v50;
    }
    else
    {
      v31 = 0;
    }
    v32 = a5;
    kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::reset<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(
      a5,
      v31);
    if ( *v32 )
    {
      v33 = v32[1];
      if ( v33 )
      {
        if ( *(_DWORD *)(v33 + 8) && v15 >= 0 )
        {
          v34 = (volatile signed __int32 *)P[1];
          if ( P[1] )
          {
            if ( !_InterlockedDecrement((volatile signed __int32 *)P[1] + 2) )
            {
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
              if ( !_InterlockedDecrement(v34 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 16LL))(v34);
            }
          }
          appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>(&v41);
          appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)&v45);
          v19 = (volatile signed __int32 *)*((_QWORD *)&v38 + 1);
          v20 = (volatile signed __int32 *)*((_QWORD *)&v37 + 1);
          goto LABEL_72;
        }
      }
    }
    v35 = (volatile signed __int32 *)P[1];
    if ( P[1] )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)P[1] + 2) )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
        if ( !_InterlockedDecrement(v35 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 16LL))(v35);
      }
    }
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>(&v41);
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)&v45);
    v36 = (volatile signed __int32 *)*((_QWORD *)&v37 + 1);
    if ( *((_QWORD *)&v37 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v37 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
        if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 16LL))(v36);
      }
    }
    v19 = (volatile signed __int32 *)*((_QWORD *)&v38 + 1);
LABEL_90:
    if ( v19 )
    {
      if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 16LL))(v19);
      }
    }
    return 3221225626LL;
  }
  v10 = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindPackage<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
          v8,
          v6,
          &v38);
  if ( v10 >= 0 )
  {
    v14 = *(_QWORD *)(a1 + 56);
    P[0] = 0;
    P[1] = 0;
    RtlInitUnicodeString(&DestinationString, 0);
    v15 = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindUser<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
            v14,
            *a2,
            (unsigned int)P,
            a3,
            (__int64)&v37);
    v50 = v15;
    if ( P[1] )
      ExFreePoolWithTag(P[1], 0);
    if ( v15 < 0 )
    {
      v16 = (volatile signed __int32 *)*((_QWORD *)&v37 + 1);
      if ( *((_QWORD *)&v37 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v37 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
          if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 16LL))(v16);
        }
      }
      v17 = (volatile signed __int32 *)*((_QWORD *)&v38 + 1);
      if ( *((_QWORD *)&v38 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v38 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
          if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 16LL))(v17);
        }
      }
      return (unsigned int)v15;
    }
    v18 = ExAllocatePool2(256, 208, 1733125462);
    v19 = (volatile signed __int32 *)*((_QWORD *)&v38 + 1);
    v20 = (volatile signed __int32 *)*((_QWORD *)&v37 + 1);
    if ( v18 )
    {
      *(_OWORD *)P = v37;
      if ( *((_QWORD *)&v37 + 1) )
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v37 + 1) + 8LL));
      *(_QWORD *)&v37 = v38;
      *((_QWORD *)&v37 + 1) = v19;
      if ( v19 )
        _InterlockedIncrement(v19 + 2);
      v21 = VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(
              v18,
              &v37,
              P,
              &v50);
      v15 = v50;
    }
    else
    {
      v21 = 0;
    }
    v22 = a5;
    kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::reset<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(
      a5,
      v21);
    if ( *v22 )
    {
      v23 = v22[1];
      if ( v23 )
      {
        if ( *(_DWORD *)(v23 + 8) && v15 >= 0 )
        {
LABEL_72:
          if ( v20 )
          {
            if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
            {
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
              if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 16LL))(v20);
            }
          }
          if ( v19 )
          {
            if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
            {
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
              if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 16LL))(v19);
            }
          }
          return 0;
        }
      }
    }
    if ( v20 )
    {
      if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
        if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 16LL))(v20);
      }
    }
    goto LABEL_90;
  }
  v11 = (volatile signed __int32 *)*((_QWORD *)&v38 + 1);
  if ( *((_QWORD *)&v38 + 1) )
  {
    v12 = _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v38 + 1) + 8LL), 0xFFFFFFFF) == 1;
LABEL_5:
    if ( v12 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 16LL))(v11);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800071a0  mov     [rsp-8+arg_0], rbx
0x1800071a5  mov     [rsp-8+arg_10], r8
0x1800071aa  push    rbp
0x1800071ab  push    rsi
0x1800071ac  push    rdi
0x1800071ad  push    r12
0x1800071af  push    r13
0x1800071b1  push    r14
0x1800071b3  push    r15
0x1800071b5  lea     rbp, [rsp-1Fh]
0x1800071ba  sub     rsp, 0C0h
0x1800071c1  or      edi, 0FFFFFFFFh
0x1800071c4  xorps   xmm0, xmm0
0x1800071c7  xorps   xmm1, xmm1
0x1800071ca  mov     r12, rdx
0x1800071cd  mov     rdx, [rdx]
0x1800071d0  mov     r13, rcx
0x1800071d3  mov     rcx, [rcx+38h]
0x1800071d7  mov     r14, r8
0x1800071da  movdqu  [rbp+4Fh+var_B0], xmm0
0x1800071df  movdqu  [rbp+4Fh+var_C0], xmm1
0x1800071e4  test    r9b, r9b
0x1800071e7  jz      loc_180007415
0x1800071ed  lea     r8, [rbp+4Fh+var_B0]
0x1800071f1  call    ??$FindPackage@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindPackage<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x1800071f6  mov     esi, eax
0x1800071f8  test    eax, eax
0x1800071fa  jns     short loc_180007242
0x1800071fc  mov     rbx, qword ptr [rbp+4Fh+var_B0+8]
0x180007200  test    rbx, rbx
0x180007203  jz      short loc_18000723B
0x180007205  or      edi, edi
0x180007207  mov     ecx, edi
0x180007209  lock xadd [rbx+8], ecx
0x18000720e  add     ecx, edi
0x180007210  jnz     short loc_18000723B
0x180007212  mov     rax, [rbx]
0x180007215  mov     rcx, rbx
0x180007218  mov     rax, [rax+8]
0x18000721c  call    _guard_dispatch_icall
0x180007221  mov     eax, edi
0x180007223  lock xadd [rbx+0Ch], eax
0x180007228  add     eax, edi
0x18000722a  jnz     short loc_18000723B
0x18000722c  mov     rax, [rbx]
0x18000722f  mov     rcx, rbx
0x180007232  mov     rax, [rax+10h]
0x180007236  call    _guard_dispatch_icall
0x18000723b  mov     eax, esi
0x18000723d  jmp     loc_18000781B
0x180007242  mov     rbx, [r13+38h]
0x180007246  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x18000724a  xor     r13d, r13d
0x18000724d  xor     edx, edx; SourceString
0x18000724f  mov     [rbp+4Fh+P], r13
0x180007253  mov     [rbp+4Fh+P+8], r13
0x180007257  call    cs:__imp_RtlInitUnicodeString
0x18000725e  nop     dword ptr [rax+rax+00h]
0x180007263  mov     rdx, [r12]
0x180007267  lea     rax, [rbp+4Fh+var_C0]
0x18000726b  mov     r9, r14
0x18000726e  mov     [rsp+0F0h+var_D0], rax
0x180007273  lea     r8, [rbp+4Fh+P]
0x180007277  mov     rcx, rbx
0x18000727a  call    ??$FindUser@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@00AEAV?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindUser<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x18000727f  mov     rcx, [rbp+4Fh+P+8]; P
0x180007283  mov     r14d, eax
0x180007286  mov     [rbp+4Fh+arg_18], eax
0x180007289  test    rcx, rcx
0x18000728c  jz      short loc_18000729C
0x18000728e  xor     edx, edx; Tag
0x180007290  call    cs:__imp_ExFreePoolWithTag
0x180007297  nop     dword ptr [rax+rax+00h]
0x18000729c  test    r14d, r14d
0x18000729f  jns     loc_18000732A
0x1800072a5  mov     rbx, qword ptr [rbp+4Fh+var_C0+8]
0x1800072a9  or      edi, 0FFFFFFFFh
0x1800072ac  test    rbx, rbx
0x1800072af  jz      short loc_1800072E5
0x1800072b1  mov     eax, edi
0x1800072b3  lock xadd [rbx+8], eax
0x1800072b8  add     eax, edi
0x1800072ba  jnz     short loc_1800072E5
0x1800072bc  mov     rax, [rbx]
0x1800072bf  mov     rcx, rbx
0x1800072c2  mov     rax, [rax+8]
0x1800072c6  call    _guard_dispatch_icall
0x1800072cb  mov     eax, edi
0x1800072cd  lock xadd [rbx+0Ch], eax
0x1800072d2  add     eax, edi
0x1800072d4  jnz     short loc_1800072E5
0x1800072d6  mov     rax, [rbx]
0x1800072d9  mov     rcx, rbx
0x1800072dc  mov     rax, [rax+10h]
0x1800072e0  call    _guard_dispatch_icall
0x1800072e5  mov     rbx, qword ptr [rbp+4Fh+var_B0+8]
0x1800072e9  test    rbx, rbx
0x1800072ec  jz      short loc_180007322
0x1800072ee  mov     eax, edi
0x1800072f0  lock xadd [rbx+8], eax
0x1800072f5  add     eax, edi
0x1800072f7  jnz     short loc_180007322
0x1800072f9  mov     rax, [rbx]
0x1800072fc  mov     rcx, rbx
0x1800072ff  mov     rax, [rax+8]
0x180007303  call    _guard_dispatch_icall
0x180007308  mov     eax, edi
0x18000730a  lock xadd [rbx+0Ch], eax
0x18000730f  add     eax, edi
0x180007311  jnz     short loc_180007322
0x180007313  mov     rax, [rbx]
0x180007316  mov     rcx, rbx
0x180007319  mov     rax, [rax+10h]
0x18000731d  call    _guard_dispatch_icall
0x180007322  mov     eax, r14d
0x180007325  jmp     loc_18000781B
0x18000732a  mov     edx, 0D0h
0x18000732f  mov     r8d, 674D6556h
0x180007335  lea     ecx, [rdx+30h]
0x180007338  call    cs:__imp_ExAllocatePool2
0x18000733f  nop     dword ptr [rax+rax+00h]
0x180007344  mov     rbx, qword ptr [rbp+4Fh+var_B0+8]
0x180007348  mov     r10, rax
0x18000734b  mov     rsi, qword ptr [rbp+4Fh+var_C0+8]
0x18000734f  test    rax, rax
0x180007352  jz      short loc_180007398
0x180007354  mov     rcx, qword ptr [rbp+4Fh+var_C0]
0x180007358  mov     [rbp+4Fh+P], rcx
0x18000735c  mov     [rbp+4Fh+P+8], rsi
0x180007360  test    rsi, rsi
0x180007363  jz      short loc_180007369
0x180007365  lock inc dword ptr [rsi+8]
0x180007369  mov     rax, qword ptr [rbp+4Fh+var_B0]
0x18000736d  mov     qword ptr [rbp+4Fh+var_C0], rax
0x180007371  mov     qword ptr [rbp+4Fh+var_C0+8], rbx
0x180007375  test    rbx, rbx
0x180007378  jz      short loc_18000737E
0x18000737a  lock inc dword ptr [rbx+8]
0x18000737e  lea     r9, [rbp+4Fh+arg_18]
0x180007382  mov     rcx, r10
0x180007385  lea     r8, [rbp+4Fh+P]
0x180007389  lea     rdx, [rbp+4Fh+var_C0]
0x18000738d  call    ??0?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@V?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@2@AEAJ@Z; VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,long &)
0x180007392  mov     r14d, [rbp+4Fh+arg_18]
0x180007396  jmp     short loc_18000739B
0x180007398  mov     rax, r13
0x18000739b  mov     r15, [rbp+4Fh+arg_20]
0x18000739f  mov     rdx, rax
0x1800073a2  mov     rcx, r15
0x1800073a5  call    ??$reset@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@QEAAXPEAV?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::reset<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info> *)
0x1800073aa  cmp     [r15], r13
0x1800073ad  jz      short loc_1800073C8
0x1800073af  mov     rax, [r15+8]
0x1800073b3  test    rax, rax
0x1800073b6  jz      short loc_1800073C8
0x1800073b8  mov     eax, [rax+8]
0x1800073bb  test    eax, eax
0x1800073bd  jz      short loc_1800073C8
0x1800073bf  test    r14d, r14d
0x1800073c2  jns     loc_1800076D1
0x1800073c8  or      edi, 0FFFFFFFFh
0x1800073cb  test    rsi, rsi
0x1800073ce  jz      loc_1800077DD
0x1800073d4  mov     eax, edi
0x1800073d6  lock xadd [rsi+8], eax
0x1800073db  add     eax, edi
0x1800073dd  jnz     loc_1800077DD
0x1800073e3  mov     rax, [rsi]
0x1800073e6  mov     rcx, rsi
0x1800073e9  mov     rax, [rax+8]
0x1800073ed  call    _guard_dispatch_icall
0x1800073f2  mov     eax, edi
0x1800073f4  lock xadd [rsi+0Ch], eax
0x1800073f9  add     eax, edi
0x1800073fb  jnz     loc_1800077DD
0x180007401  mov     rax, [rsi]
0x180007404  mov     rcx, rsi
0x180007407  mov     rax, [rax+10h]
0x18000740b  call    _guard_dispatch_icall
0x180007410  jmp     loc_1800077DD
0x180007415  lea     rax, [rbp+4Fh+var_50]
0x180007419  mov     [rbp+4Fh+var_58], 0
0x180007420  mov     [rbp+4Fh+var_38], rax
0x180007424  lea     r8, [rbp+4Fh+P]
0x180007428  lea     rax, [rbp+4Fh+var_50]
0x18000742c  mov     [rbp+4Fh+var_80], 0
0x180007433  mov     [rbp+4Fh+var_40], rax
0x180007437  lea     rax, [rbp+4Fh+var_78]
0x18000743b  mov     [rbp+4Fh+var_60], rax
0x18000743f  lea     rax, [rbp+4Fh+var_78]
0x180007443  mov     [rbp+4Fh+var_68], rax
0x180007447  movdqu  [rbp+4Fh+var_50], xmm0
0x18000744c  movdqu  [rbp+4Fh+var_78], xmm0
0x180007451  movdqu  xmmword ptr [rbp+4Fh+P], xmm0
0x180007456  call    ??$FindPackageGroup@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindPackageGroup<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x18000745b  mov     [rbp+4Fh+arg_18], eax
0x18000745e  mov     r14d, eax
0x180007461  test    eax, eax
0x180007463  jns     short loc_1800074BC
0x180007465  mov     rbx, [rbp+4Fh+P+8]
0x180007469  test    rbx, rbx
0x18000746c  jz      short loc_1800074A5
0x18000746e  or      edi, 0FFFFFFFFh
0x180007471  mov     ecx, edi
0x180007473  lock xadd [rbx+8], ecx
0x180007478  add     ecx, edi
0x18000747a  jnz     short loc_1800074A5
0x18000747c  mov     rax, [rbx]
0x18000747f  mov     rcx, rbx
0x180007482  mov     rax, [rax+8]
0x180007486  call    _guard_dispatch_icall
0x18000748b  mov     eax, edi
0x18000748d  lock xadd [rbx+0Ch], eax
0x180007492  add     eax, edi
0x180007494  jnz     short loc_1800074A5
0x180007496  mov     rax, [rbx]
0x180007499  mov     rcx, rbx
0x18000749c  mov     rax, [rax+10h]
0x1800074a0  call    _guard_dispatch_icall
0x1800074a5  lea     rcx, [rbp+4Fh+var_80]
0x1800074a9  call    ??1?$doubly_linked_list@V?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>(void)
0x1800074ae  lea     rcx, [rbp+4Fh+var_58]
0x1800074b2  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x1800074b7  jmp     loc_180007322
0x1800074bc  mov     r15, [rbp+4Fh+P]
0x1800074c0  mov     rbx, [r15+30h]
0x1800074c4  lea     rax, [r15+18h]
0x1800074c8  cmp     rbx, rax
0x1800074cb  jz      loc_1800075FA
0x1800074d1  mov     rdx, [rbx]
0x1800074d4  lea     r8, [rbp+4Fh+var_B0]
0x1800074d8  mov     rcx, [r13+38h]
0x1800074dc  call    ??$FindPackage@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindPackage<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x1800074e1  mov     esi, eax
0x1800074e3  test    eax, eax
0x1800074e5  js      short loc_180007519
0x1800074e7  mov     r9, [rbp+4Fh+arg_10]
0x1800074eb  lea     rax, [rbp+4Fh+var_C0]
0x1800074ef  mov     r8, [r12]
0x1800074f3  mov     rdx, [rbx]
0x1800074f6  mov     rcx, [r13+38h]
0x1800074fa  mov     [rsp+0F0h+var_D0], rax
0x1800074ff  call    ??$FindUser@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@00AEAV?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindUser<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x180007504  mov     esi, eax
0x180007506  test    eax, eax
0x180007508  jns     loc_1800075C3
0x18000750e  cmp     eax, 0C0000034h
0x180007513  jz      loc_1800075F1
0x180007519  mov     rbx, [rbp+4Fh+P+8]
0x18000751d  or      edi, 0FFFFFFFFh
0x180007520  test    rbx, rbx
0x180007523  jz      short loc_180007559
0x180007525  mov     eax, edi
0x180007527  lock xadd [rbx+8], eax
0x18000752c  add     eax, edi
0x18000752e  jnz     short loc_180007559
0x180007530  mov     rax, [rbx]
0x180007533  mov     rcx, rbx
0x180007536  mov     rax, [rax+8]
0x18000753a  call    _guard_dispatch_icall
0x18000753f  mov     eax, edi
0x180007541  lock xadd [rbx+0Ch], eax
0x180007546  add     eax, edi
0x180007548  jnz     short loc_180007559
0x18000754a  mov     rax, [rbx]
0x18000754d  mov     rcx, rbx
0x180007550  mov     rax, [rax+10h]
0x180007554  call    _guard_dispatch_icall
0x180007559  lea     rcx, [rbp+4Fh+var_80]
0x18000755d  call    ??1?$doubly_linked_list@V?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>(void)
0x180007562  lea     rcx, [rbp+4Fh+var_58]
0x180007566  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x18000756b  mov     rbx, qword ptr [rbp+4Fh+var_C0+8]
0x18000756f  test    rbx, rbx
0x180007572  jz      short loc_1800075A8
0x180007574  mov     eax, edi
0x180007576  lock xadd [rbx+8], eax
0x18000757b  add     eax, edi
0x18000757d  jnz     short loc_1800075A8
0x18000757f  mov     rax, [rbx]
0x180007582  mov     rcx, rbx
0x180007585  mov     rax, [rax+8]
0x180007589  call    _guard_dispatch_icall
0x18000758e  mov     eax, edi
0x180007590  lock xadd [rbx+0Ch], eax
0x180007595  add     eax, edi
0x180007597  jnz     short loc_1800075A8
0x180007599  mov     rax, [rbx]
0x18000759c  mov     rcx, rbx
0x18000759f  mov     rax, [rax+10h]
0x1800075a3  call    _guard_dispatch_icall
0x1800075a8  mov     rbx, qword ptr [rbp+4Fh+var_B0+8]
0x1800075ac  test    rbx, rbx
0x1800075af  jz      loc_18000723B
0x1800075b5  mov     eax, edi
0x1800075b7  lock xadd [rbx+8], eax
0x1800075bc  add     eax, edi
0x1800075be  jmp     loc_180007210
0x1800075c3  lea     rdx, [rbp+4Fh+var_B0]
0x1800075c7  lea     rcx, [rbp+4Fh+var_58]
  ... truncated ...
```
