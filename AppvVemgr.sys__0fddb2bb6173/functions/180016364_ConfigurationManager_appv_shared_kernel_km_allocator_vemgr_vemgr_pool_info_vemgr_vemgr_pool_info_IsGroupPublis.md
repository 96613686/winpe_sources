# ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsGroupPublishedForUser<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ulong)

- ea: `0x180016364`
- end: `0x18001646c`
- name: `??$IsGroupPublishedForUser@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA_NAEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@K@Z`
- size: `264`
- prototype: `char __fastcall(__int64, const UNICODE_STRING **, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180018964`

## callees

- `0x18000199c`
- `0x1800021d0`
- `0x180016364`
- `0x18001bb30`

## pseudocode

```c
char __fastcall ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsGroupPublishedForUser<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
        __int64 a1,
        const UNICODE_STRING **a2,
        int a3,
        int a4)
{
  int v6; // ebx
  int v7; // edi
  const UNICODE_STRING *v8; // rax
  const UNICODE_STRING *v9; // rdx
  char v10; // al
  volatile signed __int32 *v11; // rbx
  char v12; // si
  volatile signed __int32 *v14; // rbx
  __int128 v15; // [rsp+30h] [rbp-38h] BYREF

  v6 = (int)a2;
  v7 = a1;
  if ( !*a2 )
    return 0;
  v8 = a2[1];
  if ( !v8 || !LODWORD(v8->Buffer) )
    return 0;
  v9 = *a2;
  v15 = 0;
  if ( (int)ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindPackageGroup<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
              a1,
              v9,
              (__int64 *)&v15) < 0
    || !*(_DWORD *)(v15 + 16) )
  {
    v14 = (volatile signed __int32 *)*((_QWORD *)&v15 + 1);
    if ( *((_QWORD *)&v15 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v15 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
        if ( !_InterlockedDecrement(v14 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 16LL))(v14);
      }
    }
    return 0;
  }
  v10 = ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPublishedForUser_Internal<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
          v7,
          *(_QWORD *)(v15 + 48),
          v6,
          a3,
          a4);
  v11 = (volatile signed __int32 *)*((_QWORD *)&v15 + 1);
  v12 = v10;
  if ( *((_QWORD *)&v15 + 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v15 + 1) + 8LL), 0xFFFFFFFF) == 1 )
  {
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    if ( !_InterlockedDecrement(v11 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return v12;
}

```

## disassembly

```asm
0x180016364  push    rbx
0x180016366  push    rbp
0x180016367  push    rsi
0x180016368  push    rdi
0x180016369  sub     rsp, 48h
0x18001636d  cmp     qword ptr [rdx], 0
0x180016371  mov     esi, r9d
0x180016374  mov     rbp, r8
0x180016377  mov     rbx, rdx
0x18001637a  mov     rdi, rcx
0x18001637d  jz      loc_180016460
0x180016383  mov     rax, [rdx+8]
0x180016387  test    rax, rax
0x18001638a  jz      loc_180016460
0x180016390  mov     eax, [rax+8]
0x180016393  test    eax, eax
0x180016395  jz      loc_180016460
0x18001639b  mov     rdx, [rdx]
0x18001639e  lea     r8, [rsp+68h+var_38]
0x1800163a3  xorps   xmm0, xmm0
0x1800163a6  movdqu  [rsp+68h+var_38], xmm0
0x1800163ac  call    ??$FindPackageGroup@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindPackageGroup<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x1800163b1  test    eax, eax
0x1800163b3  js      short loc_18001641F
0x1800163b5  mov     rdx, qword ptr [rsp+68h+var_38]
0x1800163ba  cmp     dword ptr [rdx+10h], 0
0x1800163be  jz      short loc_18001641F
0x1800163c0  mov     rdx, [rdx+30h]
0x1800163c4  mov     r9, rbp
0x1800163c7  mov     r8, rbx
0x1800163ca  mov     [rsp+68h+var_48], esi
0x1800163ce  mov     rcx, rdi
0x1800163d1  call    ??$IsPublishedForUser_Internal@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAA_NAEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@0AEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@K@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsPublishedForUser_Internal<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ulong)
0x1800163d6  mov     rbx, qword ptr [rsp+68h+var_38+8]
0x1800163db  mov     sil, al
0x1800163de  test    rbx, rbx
0x1800163e1  jz      short loc_18001641A
0x1800163e3  or      edi, 0FFFFFFFFh
0x1800163e6  mov     ecx, edi
0x1800163e8  lock xadd [rbx+8], ecx
0x1800163ed  add     ecx, edi
0x1800163ef  jnz     short loc_18001641A
0x1800163f1  mov     rdx, [rbx]
0x1800163f4  mov     rcx, rbx
0x1800163f7  mov     rax, [rdx+8]
0x1800163fb  call    _guard_dispatch_icall
0x180016400  mov     eax, edi
0x180016402  lock xadd [rbx+0Ch], eax
0x180016407  add     eax, edi
0x180016409  jnz     short loc_18001641A
0x18001640b  mov     rax, [rbx]
0x18001640e  mov     rcx, rbx
0x180016411  mov     rax, [rax+10h]
0x180016415  call    _guard_dispatch_icall
0x18001641a  mov     al, sil
0x18001641d  jmp     short loc_180016462
0x18001641f  mov     rbx, qword ptr [rsp+68h+var_38+8]
0x180016424  test    rbx, rbx
0x180016427  jz      short loc_180016460
0x180016429  or      edi, 0FFFFFFFFh
0x18001642c  mov     eax, edi
0x18001642e  lock xadd [rbx+8], eax
0x180016433  add     eax, edi
0x180016435  jnz     short loc_180016460
0x180016437  mov     rax, [rbx]
0x18001643a  mov     rcx, rbx
0x18001643d  mov     rax, [rax+8]
0x180016441  call    _guard_dispatch_icall
0x180016446  mov     eax, edi
0x180016448  lock xadd [rbx+0Ch], eax
0x18001644d  add     eax, edi
0x18001644f  jnz     short loc_180016460
0x180016451  mov     rax, [rbx]
0x180016454  mov     rcx, rbx
0x180016457  mov     rax, [rax+10h]
0x18001645b  call    _guard_dispatch_icall
0x180016460  xor     al, al
0x180016462  add     rsp, 48h
0x180016466  pop     rdi
0x180016467  pop     rsi
0x180016468  pop     rbp
0x180016469  pop     rbx
0x18001646a  retn
```
