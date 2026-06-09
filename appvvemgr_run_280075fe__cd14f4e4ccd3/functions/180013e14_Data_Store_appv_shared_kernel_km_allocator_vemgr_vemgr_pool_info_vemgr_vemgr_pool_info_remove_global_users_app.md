# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_global_users(appv::shared::kernel::handle const &)

- ea: `0x180013e14`
- end: `0x180013f38`
- name: `?remove_global_users@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBVhandle@kernel@shared@appv@@@Z`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180013f40`

## callees

- `0x180005178`
- `0x18000b478`
- `0x18000bfb8`
- `0x18000ce10`
- `0x18000e23c`
- `0x180013e14`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x180013f01`
- `ntoskrnl!ZwClose` at `0x180013f01`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_global_users(
        void **a1)
{
  void *v2; // rcx
  int value; // edi
  __int128 *i; // rbx
  __int64 v5; // rdx
  unsigned int v6; // ecx
  __int16 v7; // r8
  __int16 v8; // ax
  __int64 v9; // rdx
  NTSTATUS v10; // eax
  HANDLE v11; // rcx
  int v13; // [rsp+20h] [rbp-30h] BYREF
  __int128 v14; // [rsp+28h] [rbp-28h] BYREF
  __int128 *v15; // [rsp+38h] [rbp-18h]
  __int128 *v16; // [rsp+40h] [rbp-10h]
  int v17; // [rsp+70h] [rbp+20h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp+28h] BYREF

  v2 = *a1;
  v16 = &v14;
  v15 = &v14;
  v13 = 0;
  v14 = 0;
  value = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(
            v2,
            (__int64)&v13);
  if ( value >= 0 )
  {
    for ( i = v16; ; i = (__int128 *)*((_QWORD *)i + 3) )
    {
      if ( i == &v14 )
        goto LABEL_22;
      v5 = *(_QWORD *)i;
      Handle = 0;
      v6 = *(_DWORD *)v5 >> 1;
      if ( v6 > 0xFFFF )
        v7 = -1;
      else
        v7 = *(_DWORD *)v5 >> 1;
      v8 = 0;
      if ( v6 <= 0xFFFF )
        v8 = v7;
      v9 = v8 ? *(_QWORD *)(v5 + 8) : 0LL;
      v10 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
              *a1,
              v9,
              &Handle);
      v11 = Handle;
      value = v10;
      if ( v10 < 0 )
        break;
      v17 = 0;
      value = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(
                Handle,
                (__int64)L"Global",
                &v17);
      if ( value >= 0 )
      {
        if ( v17 )
          value = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_key(
                    Handle,
                    (__int64)&dword_18001E3EC);
      }
      if ( Handle )
      {
        v11 = Handle;
LABEL_20:
        ZwClose(v11);
        continue;
      }
LABEL_21:
      ;
    }
    if ( !Handle )
      goto LABEL_21;
    goto LABEL_20;
  }
LABEL_22:
  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)&v13);
  return (unsigned int)value;
}

```

## disassembly

```asm
0x180013e14  mov     [rsp-18h+arg_10], rbx
0x180013e19  mov     [rsp-18h+arg_18], rdi
0x180013e1e  push    rbp
0x180013e1f  push    r14
0x180013e21  push    r15
0x180013e23  mov     rbp, rsp
0x180013e26  sub     rsp, 50h
0x180013e2a  lea     rax, [rbp+var_28]
0x180013e2e  mov     r14, rcx
0x180013e31  mov     rcx, [rcx]; KeyHandle
0x180013e34  lea     rdx, [rbp+var_30]
0x180013e38  mov     [rbp+var_10], rax
0x180013e3c  xorps   xmm0, xmm0
0x180013e3f  lea     rax, [rbp+var_28]
0x180013e43  xor     r15d, r15d
0x180013e46  mov     [rbp+var_18], rax
0x180013e4a  mov     [rbp+var_30], r15d
0x180013e4e  movdqu  [rbp+var_28], xmm0
0x180013e53  call    ?enum_keys@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXAEAV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(void *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)
0x180013e58  mov     edi, eax
0x180013e5a  test    eax, eax
0x180013e5c  js      loc_180013F16
0x180013e62  mov     rbx, [rbp+var_10]
0x180013e66  lea     rax, [rbp+var_28]
0x180013e6a  cmp     rbx, rax
0x180013e6d  jz      loc_180013F16
0x180013e73  mov     rdx, [rbx]
0x180013e76  mov     [rbp+Handle], r15
0x180013e7a  mov     ecx, [rdx]
0x180013e7c  shr     ecx, 1
0x180013e7e  cmp     ecx, 0FFFFh
0x180013e84  ja      short loc_180013E8C
0x180013e86  movzx   r8d, cx
0x180013e8a  jmp     short loc_180013E92
0x180013e8c  mov     r8d, 0FFFFh
0x180013e92  mov     eax, r15d
0x180013e95  cmovbe  ax, r8w
0x180013e9a  test    ax, ax
0x180013e9d  jnz     short loc_180013EA4
0x180013e9f  mov     rdx, r15
0x180013ea2  jmp     short loc_180013EA8
0x180013ea4  mov     rdx, [rdx+8]
0x180013ea8  mov     rcx, [r14]
0x180013eab  lea     r8, [rbp+Handle]
0x180013eaf  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x180013eb4  mov     rcx, [rbp+Handle]
0x180013eb8  mov     edi, eax
0x180013eba  test    eax, eax
0x180013ebc  jns     short loc_180013EC5
0x180013ebe  test    rcx, rcx
0x180013ec1  jz      short loc_180013F0D
0x180013ec3  jmp     short loc_180013F01
0x180013ec5  lea     r8, [rbp+arg_0]
0x180013ec9  mov     [rbp+arg_0], r15d
0x180013ecd  lea     rdx, aGlobal; "Global"
0x180013ed4  call    ?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,ulong &)
0x180013ed9  mov     edi, eax
0x180013edb  test    eax, eax
0x180013edd  js      short loc_180013EF7
0x180013edf  cmp     [rbp+arg_0], r15d
0x180013ee3  jbe     short loc_180013EF7
0x180013ee5  mov     rcx, [rbp+Handle]
0x180013ee9  lea     rdx, dword_18001E3EC
0x180013ef0  call    ?delete_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_W_N@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_key(void *,wchar_t const *,bool)
0x180013ef5  mov     edi, eax
0x180013ef7  cmp     [rbp+Handle], r15
0x180013efb  jz      short loc_180013F0D
0x180013efd  mov     rcx, [rbp+Handle]; Handle
0x180013f01  call    cs:__imp_ZwClose
0x180013f08  nop     dword ptr [rax+rax+00h]
0x180013f0d  mov     rbx, [rbx+18h]
0x180013f11  jmp     loc_180013E66
0x180013f16  lea     rcx, [rbp+var_30]
0x180013f1a  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x180013f1f  lea     r11, [rsp+50h+var_s0]
0x180013f24  mov     eax, edi
0x180013f26  mov     rbx, [r11+30h]
0x180013f2a  mov     rdi, [r11+38h]
0x180013f2e  mov     rsp, r11
0x180013f31  pop     r15
0x180013f33  pop     r14
0x180013f35  pop     rbp
0x180013f36  retn
```
