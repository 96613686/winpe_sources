# appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::for_each<Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve_package>(Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve_package &)

- ea: `0x180016474`
- end: `0x180016569`
- name: `??$for_each@Uretrieve_package@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAXAEAUretrieve_package@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001a1f4`

## callees

- `0x18000e588`
- `0x180016474`
- `0x18001a79c`
- `0x18001bb30`

## pseudocode

```c
void __fastcall appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::for_each<Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve_package>(
        __int64 a1,
        __int64 a2)
{
  __int64 *v2; // rbx
  __int64 *v3; // rbp
  __int64 v5; // rax
  __int64 v6; // rcx
  unsigned int v7; // eax
  __int64 v8; // rcx
  int v9; // eax
  volatile signed __int32 *v10; // rdi
  _OWORD v11[4]; // [rsp+20h] [rbp-48h] BYREF

  v2 = *(__int64 **)(a1 + 32);
  v3 = (__int64 *)(a1 + 8);
  while ( v2 != v3 )
  {
    if ( *v2 )
    {
      v5 = v2[1];
      if ( v5 )
      {
        if ( *(_DWORD *)(v5 + 8) )
        {
          v6 = *v2;
          v11[0] = 0;
          v7 = *(_DWORD *)v6 >> 1;
          if ( v7 <= 0xFFFF && (_WORD)v7 )
            v8 = *(_QWORD *)(v6 + 8);
          else
            v8 = 0;
          v9 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve(
                 v8,
                 v11);
          if ( v9 >= 0 )
          {
            appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
              *(_QWORD *)a2,
              v11);
            **(_BYTE **)(a2 + 8) |= *(_BYTE *)(*(_QWORD *)&v11[0] + 49LL);
          }
          else
          {
            *(_DWORD *)(a2 + 16) = v9;
          }
          v10 = (volatile signed __int32 *)*((_QWORD *)&v11[0] + 1);
          if ( *((_QWORD *)&v11[0] + 1)
            && !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v11[0] + 1) + 8LL)) )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
            if ( !_InterlockedDecrement(v10 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 16LL))(v10);
          }
        }
      }
    }
    v2 = (__int64 *)v2[3];
  }
}

```

## disassembly

```asm
0x180016474  push    rbx
0x180016476  push    rbp
0x180016477  push    rsi
0x180016478  push    rdi
0x180016479  push    r14
0x18001647b  push    r15
0x18001647d  sub     rsp, 38h
0x180016481  mov     rbx, [rcx+20h]
0x180016485  lea     rbp, [rcx+8]
0x180016489  xor     r14d, r14d
0x18001648c  mov     rsi, rdx
0x18001648f  or      r15d, 0FFFFFFFFh
0x180016493  cmp     rbx, rbp
0x180016496  jz      loc_18001655B
0x18001649c  cmp     [rbx], r14
0x18001649f  jz      loc_180016552
0x1800164a5  mov     rax, [rbx+8]
0x1800164a9  test    rax, rax
0x1800164ac  jz      loc_180016552
0x1800164b2  mov     eax, [rax+8]
0x1800164b5  test    eax, eax
0x1800164b7  jz      loc_180016552
0x1800164bd  mov     rcx, [rbx]
0x1800164c0  xorps   xmm0, xmm0
0x1800164c3  movdqu  [rsp+68h+var_48], xmm0
0x1800164c9  mov     eax, [rcx]
0x1800164cb  shr     eax, 1
0x1800164cd  cmp     eax, 0FFFFh
0x1800164d2  ja      short loc_1800164DF
0x1800164d4  test    ax, ax
0x1800164d7  jz      short loc_1800164DF
0x1800164d9  mov     rcx, [rcx+8]
0x1800164dd  jmp     short loc_1800164E2
0x1800164df  mov     rcx, r14
0x1800164e2  lea     rdx, [rsp+68h+var_48]
0x1800164e7  call    ?retrieve@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_WAEAV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve(wchar_t const *,kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x1800164ec  test    eax, eax
0x1800164ee  jns     short loc_1800164F5
0x1800164f0  mov     [rsi+10h], eax
0x1800164f3  jmp     short loc_180016510
0x1800164f5  mov     rcx, [rsi]
0x1800164f8  lea     rdx, [rsp+68h+var_48]
0x1800164fd  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x180016502  mov     rax, qword ptr [rsp+68h+var_48]
0x180016507  mov     rdx, [rsi+8]
0x18001650b  mov     cl, [rax+31h]
0x18001650e  or      [rdx], cl
0x180016510  mov     rdi, qword ptr [rsp+68h+var_48+8]
0x180016515  test    rdi, rdi
0x180016518  jz      short loc_180016552
0x18001651a  mov     eax, r15d
0x18001651d  lock xadd [rdi+8], eax
0x180016522  add     eax, r15d
0x180016525  jnz     short loc_180016552
0x180016527  mov     rax, [rdi]
0x18001652a  mov     rcx, rdi
0x18001652d  mov     rax, [rax+8]
0x180016531  call    _guard_dispatch_icall
0x180016536  mov     eax, r15d
0x180016539  lock xadd [rdi+0Ch], eax
0x18001653e  add     eax, r15d
0x180016541  jnz     short loc_180016552
0x180016543  mov     rax, [rdi]
0x180016546  mov     rcx, rdi
0x180016549  mov     rax, [rax+10h]
0x18001654d  call    _guard_dispatch_icall
0x180016552  mov     rbx, [rbx+18h]
0x180016556  jmp     loc_180016493
0x18001655b  add     rsp, 38h
0x18001655f  pop     r15
0x180016561  pop     r14
0x180016563  pop     rdi
0x180016564  pop     rsi
0x180016565  pop     rbp
0x180016566  pop     rbx
0x180016567  retn
```
