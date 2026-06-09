# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_user_configurations(appv::shared::kernel::handle const &)

- ea: `0x180019cfc`
- end: `0x180019e3d`
- name: `?delete_user_configurations@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBVhandle@kernel@shared@appv@@@Z`
- size: `321`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180019b1c`

## callees

- `0x180005178`
- `0x18000b478`
- `0x18000c290`
- `0x18000e23c`
- `0x180019cfc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x180019dd9`
- `ntoskrnl!ZwClose` at `0x180019df6`
- `ntoskrnl!ZwClose` at `0x180019e24`
- `ntoskrnl!ZwClose` at `0x180019dd9`
- `ntoskrnl!ZwClose` at `0x180019df6`
- `ntoskrnl!ZwClose` at `0x180019e24`

## string_xrefs

- `0x180019dbc`: `UserConfigEx`
- `0x180019da7`: `UserConfig`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_user_configurations(
        _QWORD *a1)
{
  __int64 v2; // rcx
  int v3; // esi
  __int128 *i; // rdi
  __int64 v5; // rdx
  unsigned int v6; // ecx
  __int16 v7; // r8
  __int16 v8; // ax
  __int64 v9; // rdx
  int v10; // ebx
  HANDLE v11; // rbx
  int v13; // [rsp+20h] [rbp-38h] BYREF
  __int128 v14; // [rsp+28h] [rbp-30h] BYREF
  __int128 *v15; // [rsp+38h] [rbp-20h]
  __int128 *v16; // [rsp+40h] [rbp-18h]
  HANDLE Handle; // [rsp+90h] [rbp+38h] BYREF

  v2 = *a1;
  v16 = &v14;
  v15 = &v14;
  v13 = 0;
  v14 = 0;
  v3 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(
         v2,
         &dword_18001E3EC,
         &v13);
  if ( v3 >= 0 )
  {
    for ( i = v16; i != &v14; i = (__int128 *)*((_QWORD *)i + 3) )
    {
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
      if ( v8 )
        v9 = *(_QWORD *)(v5 + 8);
      else
        v9 = 0;
      v10 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
              *a1,
              v9,
              &Handle);
      if ( v10 < 0 )
      {
        if ( Handle )
          ZwClose(Handle);
        appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)&v13);
        return (unsigned int)v10;
      }
      v11 = Handle;
      v3 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_key(
             (__int64)Handle,
             L"UserConfig");
      if ( v3 < 0
        || (v3 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_key(
                   (__int64)v11,
                   L"UserConfigEx"),
            v3 < 0) )
      {
        if ( v11 )
          ZwClose(v11);
        break;
      }
      if ( v11 )
        ZwClose(v11);
    }
  }
  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)&v13);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180019cfc  push    rbp
0x180019cfe  push    rbx
0x180019cff  push    rsi
0x180019d00  push    rdi
0x180019d01  push    r14
0x180019d03  push    r15
0x180019d05  mov     rbp, rsp
0x180019d08  sub     rsp, 58h
0x180019d0c  lea     rax, [rbp+var_30]
0x180019d10  mov     r14, rcx
0x180019d13  mov     rcx, [rcx]
0x180019d16  lea     r8, [rbp+var_38]
0x180019d1a  mov     [rbp+var_18], rax
0x180019d1e  lea     rdx, dword_18001E3EC
0x180019d25  lea     rax, [rbp+var_30]
0x180019d29  xorps   xmm0, xmm0
0x180019d2c  xor     r15d, r15d
0x180019d2f  mov     [rbp+var_20], rax
0x180019d33  mov     [rbp+var_38], r15d
0x180019d37  movdqu  [rbp+var_30], xmm0
0x180019d3c  call    ?enum_keys@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(void *,wchar_t const *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)
0x180019d41  mov     esi, eax
0x180019d43  test    eax, eax
0x180019d45  js      loc_180019E02
0x180019d4b  mov     rdi, [rbp+var_18]
0x180019d4f  lea     rax, [rbp+var_30]
0x180019d53  cmp     rdi, rax
0x180019d56  jz      loc_180019E02
0x180019d5c  mov     rdx, [rdi]
0x180019d5f  mov     [rbp+Handle], r15
0x180019d63  mov     ecx, [rdx]
0x180019d65  shr     ecx, 1
0x180019d67  cmp     ecx, 0FFFFh
0x180019d6d  ja      short loc_180019D75
0x180019d6f  movzx   r8d, cx
0x180019d73  jmp     short loc_180019D7B
0x180019d75  mov     r8d, 0FFFFh
0x180019d7b  mov     eax, r15d
0x180019d7e  cmovbe  ax, r8w
0x180019d83  test    ax, ax
0x180019d86  jnz     short loc_180019D8D
0x180019d88  mov     rdx, r15
0x180019d8b  jmp     short loc_180019D91
0x180019d8d  mov     rdx, [rdx+8]
0x180019d91  mov     rcx, [r14]
0x180019d94  lea     r8, [rbp+Handle]
0x180019d98  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x180019d9d  mov     ebx, eax
0x180019d9f  test    eax, eax
0x180019da1  js      short loc_180019E1B
0x180019da3  mov     rbx, [rbp+Handle]
0x180019da7  lea     rdx, aUserconfig; "UserConfig"
0x180019dae  mov     rcx, rbx
0x180019db1  call    ?delete_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_W_N@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_key(void *,wchar_t const *,bool)
0x180019db6  mov     esi, eax
0x180019db8  test    eax, eax
0x180019dba  js      short loc_180019DEE
0x180019dbc  lea     rdx, aUserconfigex; "UserConfigEx"
0x180019dc3  mov     rcx, rbx
0x180019dc6  call    ?delete_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_W_N@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_key(void *,wchar_t const *,bool)
0x180019dcb  mov     esi, eax
0x180019dcd  test    eax, eax
0x180019dcf  js      short loc_180019DEE
0x180019dd1  test    rbx, rbx
0x180019dd4  jz      short loc_180019DE5
0x180019dd6  mov     rcx, rbx; Handle
0x180019dd9  call    cs:__imp_ZwClose
0x180019de0  nop     dword ptr [rax+rax+00h]
0x180019de5  mov     rdi, [rdi+18h]
0x180019de9  jmp     loc_180019D4F
0x180019dee  test    rbx, rbx
0x180019df1  jz      short loc_180019E02
0x180019df3  mov     rcx, rbx; Handle
0x180019df6  call    cs:__imp_ZwClose
0x180019dfd  nop     dword ptr [rax+rax+00h]
0x180019e02  lea     rcx, [rbp+var_38]
0x180019e06  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x180019e0b  mov     eax, esi
0x180019e0d  add     rsp, 58h
0x180019e11  pop     r15
0x180019e13  pop     r14
0x180019e15  pop     rdi
0x180019e16  pop     rsi
0x180019e17  pop     rbx
0x180019e18  pop     rbp
0x180019e19  retn
0x180019e1b  mov     rcx, [rbp+Handle]; Handle
0x180019e1f  test    rcx, rcx
0x180019e22  jz      short loc_180019E30
0x180019e24  call    cs:__imp_ZwClose
0x180019e2b  nop     dword ptr [rax+rax+00h]
0x180019e30  lea     rcx, [rbp+var_38]
0x180019e34  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x180019e39  mov     eax, ebx
0x180019e3b  jmp     short loc_180019E0D
```
