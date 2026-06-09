# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve_vfs_volumes_list(appv::shared::kernel::handle const &,wchar_t const *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)

- ea: `0x18000f718`
- end: `0x18000f7e5`
- name: `?retrieve_vfs_volumes_list@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBVhandle@kernel@shared@appv@@PEB_WAEBV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@345@AEAV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@345@@Z`
- size: `205`
- prototype: `__int64 __fastcall(void **, __int64, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000e960`

## callees

- `0x18000c31c`
- `0x18000c9a8`
- `0x18000e23c`
- `0x18000f718`
- `0x18000fa58`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18000f768`
- `ntoskrnl!ZwClose` at `0x18000f793`
- `ntoskrnl!ZwClose` at `0x18000f7cc`
- `ntoskrnl!ZwClose` at `0x18000f768`
- `ntoskrnl!ZwClose` at `0x18000f793`
- `ntoskrnl!ZwClose` at `0x18000f7cc`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve_vfs_volumes_list(
        void **a1,
        __int64 a2,
        _DWORD *a3,
        __int64 a4)
{
  NTSTATUS v7; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  int vfs_volumes_list; // ebx
  __int64 v12; // rdx
  HANDLE v13; // rbx
  unsigned int v14; // edi
  HANDLE Handle; // [rsp+58h] [rbp+10h] BYREF

  Handle = 0;
  v7 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
         *a1,
         (__int64)L"Volumes",
         &Handle);
  vfs_volumes_list = v7;
  if ( v7 >= 0 )
  {
    v13 = Handle;
    v14 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_values(
            Handle,
            a4,
            v8,
            v9);
    if ( v13 )
      ZwClose(v13);
    return v14;
  }
  else
  {
    if ( v7 == -1073741772 )
    {
      if ( !*a3 )
      {
        if ( Handle )
          ZwClose(Handle);
        return 0;
      }
      vfs_volumes_list = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::generate_vfs_volumes_list(
                           (__int64)a3,
                           a4);
      if ( vfs_volumes_list >= 0 )
        vfs_volumes_list = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_vfs_volumes_list(
                             a1,
                             v12,
                             a4);
    }
    if ( Handle )
      ZwClose(Handle);
    return (unsigned int)vfs_volumes_list;
  }
}

```

## disassembly

```asm
0x18000f718  mov     [rsp+Handle], rdx
0x18000f71d  push    rbx
0x18000f71e  push    rsi
0x18000f71f  push    rdi
0x18000f720  push    r14
0x18000f722  sub     rsp, 28h
0x18000f726  mov     rsi, r8
0x18000f729  mov     [rsp+48h+Handle], 0
0x18000f732  mov     r14, rcx
0x18000f735  lea     r8, [rsp+48h+Handle]
0x18000f73a  mov     rcx, [rcx]
0x18000f73d  lea     rdx, aVolumes; "Volumes"
0x18000f744  mov     rdi, r9
0x18000f747  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x18000f74c  mov     ebx, eax
0x18000f74e  test    eax, eax
0x18000f750  jns     short loc_18000F7B2
0x18000f752  cmp     eax, 0C0000034h
0x18000f757  jnz     short loc_18000F789
0x18000f759  cmp     dword ptr [rsi], 0
0x18000f75c  jnz     short loc_18000F778
0x18000f75e  mov     rcx, [rsp+48h+Handle]; Handle
0x18000f763  test    rcx, rcx
0x18000f766  jz      short loc_18000F774
0x18000f768  call    cs:__imp_ZwClose
0x18000f76f  nop     dword ptr [rax+rax+00h]
0x18000f774  xor     eax, eax
0x18000f776  jmp     short loc_18000F7DA
0x18000f778  mov     rdx, rdi
0x18000f77b  mov     rcx, rsi
0x18000f77e  call    ?generate_vfs_volumes_list@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@AEAV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@345@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::generate_vfs_volumes_list(appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)
0x18000f783  mov     ebx, eax
0x18000f785  test    eax, eax
0x18000f787  jns     short loc_18000F7A3
0x18000f789  mov     rcx, [rsp+48h+Handle]; Handle
0x18000f78e  test    rcx, rcx
0x18000f791  jz      short loc_18000F79F
0x18000f793  call    cs:__imp_ZwClose
0x18000f79a  nop     dword ptr [rax+rax+00h]
0x18000f79f  mov     eax, ebx
0x18000f7a1  jmp     short loc_18000F7DA
0x18000f7a3  mov     r8, rdi
0x18000f7a6  mov     rcx, r14
0x18000f7a9  call    ?store_vfs_volumes_list@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBVhandle@kernel@shared@appv@@PEB_WAEBV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@345@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_vfs_volumes_list(appv::shared::kernel::handle const &,wchar_t const *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &)
0x18000f7ae  mov     ebx, eax
0x18000f7b0  jmp     short loc_18000F789
0x18000f7b2  mov     rbx, [rsp+48h+Handle]
0x18000f7b7  mov     rdx, rdi
0x18000f7ba  mov     rcx, rbx; KeyHandle
0x18000f7bd  call    ?enum_values@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXAEAV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_values(void *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)
0x18000f7c2  mov     edi, eax
0x18000f7c4  test    rbx, rbx
0x18000f7c7  jz      short loc_18000F7D8
0x18000f7c9  mov     rcx, rbx; Handle
0x18000f7cc  call    cs:__imp_ZwClose
0x18000f7d3  nop     dword ptr [rax+rax+00h]
0x18000f7d8  mov     eax, edi
0x18000f7da  add     rsp, 28h
0x18000f7de  pop     r14
0x18000f7e0  pop     rdi
0x18000f7e1  pop     rsi
0x18000f7e2  pop     rbx
0x18000f7e3  retn
```
