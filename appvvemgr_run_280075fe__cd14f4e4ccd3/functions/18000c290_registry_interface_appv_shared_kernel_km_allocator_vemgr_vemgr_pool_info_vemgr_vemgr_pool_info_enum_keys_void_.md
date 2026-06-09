# registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(void *,wchar_t const *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)

- ea: `0x18000c290`
- end: `0x18000c313`
- name: `?enum_keys@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z`
- size: `131`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000b478`
- `0x180019b1c`
- `0x180019cfc`

## callees

- `0x18000bfb8`
- `0x18000c290`
- `0x18000e23c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18000c2c5`
- `ntoskrnl!ZwClose` at `0x18000c2ef`
- `ntoskrnl!ZwClose` at `0x18000c2c5`
- `ntoskrnl!ZwClose` at `0x18000c2ef`

## pseudocode

```c
__int64 __fastcall registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(
        void *a1,
        __int64 a2,
        __int64 a3)
{
  NTSTATUS v4; // ebx
  HANDLE v6; // rbx
  unsigned int v7; // edi
  HANDLE Handle; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
    return registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(
             a1,
             a3);
  Handle = 0;
  v4 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
         a1,
         a2,
         &Handle);
  if ( v4 >= 0 )
  {
    v6 = Handle;
    v7 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(
           Handle,
           a3);
    if ( v6 )
      ZwClose(v6);
    return v7;
  }
  else
  {
    if ( Handle )
      ZwClose(Handle);
    return (unsigned int)v4;
  }
}

```

## disassembly

```asm
0x18000c290  mov     [rsp+arg_0], rbx
0x18000c295  push    rdi
0x18000c296  sub     rsp, 20h
0x18000c29a  mov     rdi, r8
0x18000c29d  test    rdx, rdx
0x18000c2a0  jz      short loc_18000C2FF
0x18000c2a2  lea     r8, [rsp+28h+Handle]
0x18000c2a7  mov     [rsp+28h+Handle], 0
0x18000c2b0  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x18000c2b5  mov     ebx, eax
0x18000c2b7  test    eax, eax
0x18000c2b9  jns     short loc_18000C2D5
0x18000c2bb  mov     rcx, [rsp+28h+Handle]; Handle
0x18000c2c0  test    rcx, rcx
0x18000c2c3  jz      short loc_18000C2D1
0x18000c2c5  call    cs:__imp_ZwClose
0x18000c2cc  nop     dword ptr [rax+rax+00h]
0x18000c2d1  mov     eax, ebx
0x18000c2d3  jmp     short loc_18000C307
0x18000c2d5  mov     rbx, [rsp+28h+Handle]
0x18000c2da  mov     rdx, rdi
0x18000c2dd  mov     rcx, rbx; KeyHandle
0x18000c2e0  call    ?enum_keys@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXAEAV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(void *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)
0x18000c2e5  mov     edi, eax
0x18000c2e7  test    rbx, rbx
0x18000c2ea  jz      short loc_18000C2FB
0x18000c2ec  mov     rcx, rbx; Handle
0x18000c2ef  call    cs:__imp_ZwClose
0x18000c2f6  nop     dword ptr [rax+rax+00h]
0x18000c2fb  mov     eax, edi
0x18000c2fd  jmp     short loc_18000C307
0x18000c2ff  mov     rdx, rdi
0x18000c302  call    ?enum_keys@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXAEAV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(void *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)
0x18000c307  mov     rbx, [rsp+28h+arg_0]
0x18000c30c  add     rsp, 20h
0x18000c310  pop     rdi
0x18000c311  retn
```
