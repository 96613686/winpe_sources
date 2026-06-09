# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_user_data(appv::shared::kernel::handle const &,kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)

- ea: `0x1800153c8`
- end: `0x18001551c`
- name: `?store_user_data@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBVhandle@kernel@shared@appv@@AEBV?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(void **, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180014acc`

## callees

- `0x18000b420`
- `0x18000c9a8`
- `0x18000f994`
- `0x18000fa58`
- `0x1800146ac`
- `0x180014d1c`
- `0x1800153c8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x180015428`
- `ntoskrnl!ZwClose` at `0x180015504`
- `ntoskrnl!ZwClose` at `0x180015428`
- `ntoskrnl!ZwClose` at `0x180015504`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_user_data(
        void **a1,
        __int64 *a2)
{
  __int64 v2; // r9
  unsigned int v4; // edx
  bool v5; // cc
  __int16 v6; // r8
  __int16 v7; // ax
  const WCHAR *v8; // rdx
  __int64 v9; // rdx
  NTSTATUS v10; // ebx
  HANDLE v12; // rbx
  int vfs_volumes_list; // edi
  void *v14; // rdx
  __int64 v15; // rax
  _DWORD *v16; // rdx
  _DWORD *v17; // r8
  HANDLE Handle; // [rsp+50h] [rbp+8h] BYREF

  v2 = *a2;
  Handle = 0;
  v4 = *(_DWORD *)(v2 + 48) >> 1;
  v5 = v4 <= 0xFFFF;
  if ( v4 > 0xFFFF )
    v6 = -1;
  else
    v6 = *(_DWORD *)(v2 + 48) >> 1;
  v7 = 0;
  v8 = 0;
  if ( v5 )
    v7 = v6;
  if ( v7 )
    v8 = *(const WCHAR **)(v2 + 56);
  v10 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(
          *a1,
          v8,
          &Handle);
  if ( v10 >= 0 )
  {
    v12 = Handle;
    vfs_volumes_list = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(
                         Handle,
                         v9,
                         *(void **)(*a2 + 96),
                         *(_DWORD *)(*a2 + 80));
    if ( vfs_volumes_list >= 0 )
    {
      vfs_volumes_list = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(
                           v12,
                           L"Global",
                           *(_BYTE *)(*a2 + 184) != 0);
      if ( vfs_volumes_list >= 0 )
      {
        vfs_volumes_list = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(
                             v12,
                             L"OnDemand",
                             *(_BYTE *)(*a2 + 185) != 0);
        if ( vfs_volumes_list >= 0 )
        {
          vfs_volumes_list = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_mappings(
                               (__int64 *)&Handle,
                               v14,
                               *a2 + 104);
          if ( vfs_volumes_list >= 0 )
          {
            v15 = *a2;
            v16 = (_DWORD *)(*a2 + 144);
            if ( *v16
              || !*(_DWORD *)(v15 + 104)
              || (vfs_volumes_list = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::generate_vfs_volumes_list(
                                       v15 + 104,
                                       (__int64)v16),
                  vfs_volumes_list >= 0) )
            {
              v17 = (_DWORD *)(*a2 + 144);
              if ( *v17 )
                vfs_volumes_list = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_vfs_volumes_list(
                                     &Handle,
                                     v16,
                                     v17);
            }
          }
        }
      }
    }
    if ( v12 )
      ZwClose(v12);
    return (unsigned int)vfs_volumes_list;
  }
  else
  {
    if ( Handle )
      ZwClose(Handle);
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x1800153c8  push    rbx
0x1800153ca  push    rbp
0x1800153cb  push    rsi
0x1800153cc  push    rdi
0x1800153cd  sub     rsp, 28h
0x1800153d1  mov     r9, [rdx]
0x1800153d4  mov     rsi, rdx
0x1800153d7  xor     ebp, ebp
0x1800153d9  mov     r10d, 0FFFFh
0x1800153df  mov     [rsp+48h+Handle], rbp
0x1800153e4  mov     edx, [r9+30h]
0x1800153e8  shr     edx, 1
0x1800153ea  cmp     edx, r10d
0x1800153ed  ja      short loc_1800153F5
0x1800153ef  movzx   r8d, dx
0x1800153f3  jmp     short loc_1800153F8
0x1800153f5  mov     r8d, r10d
0x1800153f8  mov     eax, ebp
0x1800153fa  mov     rdx, rbp
0x1800153fd  cmovbe  ax, r8w
0x180015402  test    ax, ax
0x180015405  jz      short loc_18001540B
0x180015407  mov     rdx, [r9+38h]
0x18001540b  mov     rcx, [rcx]
0x18001540e  lea     r8, [rsp+48h+Handle]
0x180015413  call    ?create_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(void *,wchar_t const *,appv::shared::kernel::handle &)
0x180015418  mov     ebx, eax
0x18001541a  test    eax, eax
0x18001541c  jns     short loc_18001543B
0x18001541e  mov     rcx, [rsp+48h+Handle]; Handle
0x180015423  test    rcx, rcx
0x180015426  jz      short loc_180015434
0x180015428  call    cs:__imp_ZwClose
0x18001542f  nop     dword ptr [rax+rax+00h]
0x180015434  mov     eax, ebx
0x180015436  jmp     loc_180015512
0x18001543b  mov     r8, [rsi]
0x18001543e  mov     rbx, [rsp+48h+Handle]
0x180015443  mov     rcx, rbx
0x180015446  mov     r9d, [r8+50h]
0x18001544a  mov     r8, [r8+60h]
0x18001544e  call    ?set_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_W0K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(void *,wchar_t const *,void *,ulong)
0x180015453  mov     edi, eax
0x180015455  test    eax, eax
0x180015457  js      loc_1800154FC
0x18001545d  mov     rax, [rsi]
0x180015460  lea     rdx, aGlobal; "Global"
0x180015467  mov     r8d, ebp
0x18001546a  mov     rcx, rbx; KeyHandle
0x18001546d  cmp     [rax+0B8h], bpl
0x180015474  setnz   r8b
0x180015478  call    ?set_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(void *,wchar_t const *,ulong)
0x18001547d  mov     edi, eax
0x18001547f  test    eax, eax
0x180015481  js      short loc_1800154FC
0x180015483  mov     rax, [rsi]
0x180015486  lea     rdx, aOndemand; "OnDemand"
0x18001548d  mov     r8d, ebp
0x180015490  mov     rcx, rbx; KeyHandle
0x180015493  cmp     [rax+0B9h], bpl
0x18001549a  setnz   r8b
0x18001549e  call    ?set_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(void *,wchar_t const *,ulong)
0x1800154a3  mov     edi, eax
0x1800154a5  test    eax, eax
0x1800154a7  js      short loc_1800154FC
0x1800154a9  mov     r8, [rsi]
0x1800154ac  lea     rcx, [rsp+48h+Handle]
0x1800154b1  add     r8, 68h ; 'h'
0x1800154b5  call    ?store_mappings@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBVhandle@kernel@shared@appv@@PEB_WAEBV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@345@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_mappings(appv::shared::kernel::handle const &,wchar_t const *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &)
0x1800154ba  mov     edi, eax
0x1800154bc  test    eax, eax
0x1800154be  js      short loc_1800154FC
0x1800154c0  mov     rax, [rsi]
0x1800154c3  lea     rdx, [rax+90h]
0x1800154ca  cmp     [rdx], ebp
0x1800154cc  jnz     short loc_1800154E1
0x1800154ce  lea     rcx, [rax+68h]
0x1800154d2  cmp     [rcx], ebp
0x1800154d4  jz      short loc_1800154E1
0x1800154d6  call    ?generate_vfs_volumes_list@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@AEAV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@345@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::generate_vfs_volumes_list(appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)
0x1800154db  mov     edi, eax
0x1800154dd  test    eax, eax
0x1800154df  js      short loc_1800154FC
0x1800154e1  mov     r8, [rsi]
0x1800154e4  add     r8, 90h
0x1800154eb  cmp     [r8], ebp
0x1800154ee  jz      short loc_1800154FC
0x1800154f0  lea     rcx, [rsp+48h+Handle]
0x1800154f5  call    ?store_vfs_volumes_list@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBVhandle@kernel@shared@appv@@PEB_WAEBV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@345@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_vfs_volumes_list(appv::shared::kernel::handle const &,wchar_t const *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &)
0x1800154fa  mov     edi, eax
0x1800154fc  test    rbx, rbx
0x1800154ff  jz      short loc_180015510
0x180015501  mov     rcx, rbx; Handle
0x180015504  call    cs:__imp_ZwClose
0x18001550b  nop     dword ptr [rax+rax+00h]
0x180015510  mov     eax, edi
0x180015512  add     rsp, 28h
0x180015516  pop     rdi
0x180015517  pop     rsi
0x180015518  pop     rbp
0x180015519  pop     rbx
0x18001551a  retn
```
