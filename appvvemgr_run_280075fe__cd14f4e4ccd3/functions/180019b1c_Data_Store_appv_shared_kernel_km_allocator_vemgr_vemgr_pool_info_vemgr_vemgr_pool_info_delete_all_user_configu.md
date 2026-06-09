# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_all_user_configurations(void)

- ea: `0x180019b1c`
- end: `0x180019cf5`
- name: `?delete_all_user_configurations@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJXZ`
- size: `473`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018270`

## callees

- `0x180005178`
- `0x18000b478`
- `0x18000c290`
- `0x18000e23c`
- `0x180019b1c`
- `0x180019cfc`
- `0x18001b3cc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x180019c08`
- `ntoskrnl!ZwClose` at `0x180019c23`
- `ntoskrnl!ZwClose` at `0x180019c40`
- `ntoskrnl!ZwClose` at `0x180019cbd`
- `ntoskrnl!ZwClose` at `0x180019cd1`
- `ntoskrnl!ZwClose` at `0x180019c08`
- `ntoskrnl!ZwClose` at `0x180019c23`
- `ntoskrnl!ZwClose` at `0x180019c40`
- `ntoskrnl!ZwClose` at `0x180019cbd`
- `ntoskrnl!ZwClose` at `0x180019cd1`

## string_xrefs

- `0x180019c64`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\AppV\MAV\Configuration\Packages`
- `0x180019b49`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\AppV\MAV\Configuration\Groups`
- `0x180019ca4`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\AppV\MAV\Configuration\Volumes`
- `0x180019b33`: `Data_Store::delete_all_user_configurations() - There are invalid or missing volumes in cached mappings. Wiping volume mappings.`

## pseudocode

```c
__int64 Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_all_user_configurations()
{
  NTSTATUS v0; // eax
  HANDLE v1; // rbx
  NTSTATUS v2; // edi
  __int64 v3; // rdx
  __int64 v4; // r8
  __int128 *i; // rdi
  __int64 v6; // rdx
  unsigned int v7; // ecx
  __int16 v8; // r8
  __int16 v9; // ax
  __int64 v10; // rdx
  NTSTATUS v11; // esi
  HANDLE v13; // rcx
  int v14; // [rsp+20h] [rbp-30h] BYREF
  __int128 v15; // [rsp+28h] [rbp-28h] BYREF
  __int128 *v16; // [rsp+38h] [rbp-18h]
  __int128 *v17; // [rsp+40h] [rbp-10h]
  HANDLE Handle; // [rsp+70h] [rbp+20h] BYREF

  LogWrite(
    2,
    0,
    L"Data_Store::delete_all_user_configurations() - There are invalid or missing volumes in cached mappings. Wiping volume mappings.");
  Handle = 0;
  v0 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
         0,
         (__int64)L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\AppV\\MAV\\Configuration\\Groups",
         &Handle);
  v1 = Handle;
  v2 = v0;
  if ( v0 < 0 )
  {
    if ( v0 != -1073741772 )
    {
      v13 = Handle;
      if ( !Handle )
        return (unsigned int)v2;
LABEL_35:
      ZwClose(v13);
      return (unsigned int)v2;
    }
LABEL_23:
    Handle = 0;
    v2 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
           0,
           (__int64)L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\AppV\\MAV\\Configuration\\Packages",
           &Handle);
    if ( v2 < 0 )
    {
      if ( v2 != -1073741772 )
      {
LABEL_31:
        if ( Handle )
          ZwClose(Handle);
        if ( !v1 )
          return (unsigned int)v2;
        v13 = v1;
        goto LABEL_35;
      }
    }
    else
    {
      v2 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_user_configurations(&Handle);
      if ( v2 < 0 )
        goto LABEL_31;
    }
    v2 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_key(
           0,
           L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\AppV\\MAV\\Configuration\\Volumes");
    goto LABEL_31;
  }
  v14 = 0;
  v17 = &v15;
  v16 = &v15;
  v15 = 0;
  registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(
    Handle,
    &dword_18001E3EC,
    &v14);
  for ( i = v17; ; i = (__int128 *)*((_QWORD *)i + 3) )
  {
    if ( i == &v15 )
    {
      appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(
        &v14,
        v3,
        v4);
      goto LABEL_23;
    }
    v6 = *(_QWORD *)i;
    Handle = 0;
    v7 = *(_DWORD *)v6 >> 1;
    if ( v7 > 0xFFFF )
      v8 = -1;
    else
      v8 = *(_DWORD *)v6 >> 1;
    v9 = 0;
    if ( v7 <= 0xFFFF )
      v9 = v8;
    v10 = v9 ? *(_QWORD *)(v6 + 8) : 0LL;
    v11 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
            v1,
            v10,
            &Handle);
    if ( v11 < 0 )
      break;
    v11 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_user_configurations(&Handle);
    if ( v11 < 0 )
      break;
    if ( Handle )
      ZwClose(Handle);
  }
  if ( Handle )
    ZwClose(Handle);
  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(
    &v14,
    v3,
    v4);
  if ( v1 )
    ZwClose(v1);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180019b1c  mov     [rsp-18h+arg_8], rbx
0x180019b21  mov     [rsp-18h+arg_10], rsi
0x180019b26  push    rbp
0x180019b27  push    rdi
0x180019b28  push    r14
0x180019b2a  mov     rbp, rsp
0x180019b2d  sub     rsp, 50h
0x180019b31  xor     edx, edx
0x180019b33  lea     r8, aDataStoreDelet; "Data_Store::delete_all_user_configurati"...
0x180019b3a  lea     ecx, [rdx+2]
0x180019b3d  call    LogWrite
0x180019b42  xor     r14d, r14d
0x180019b45  lea     r8, [rbp+Handle]
0x180019b49  lea     rdx, aRegistryMachin; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x180019b50  mov     [rbp+Handle], r14
0x180019b54  xor     ecx, ecx
0x180019b56  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x180019b5b  mov     rbx, [rbp+Handle]
0x180019b5f  mov     edi, eax
0x180019b61  test    eax, eax
0x180019b63  js      loc_180019C89
0x180019b69  lea     rax, [rbp+var_28]
0x180019b6d  mov     [rbp+var_30], r14d
0x180019b71  mov     [rbp+var_10], rax
0x180019b75  lea     r8, [rbp+var_30]
0x180019b79  lea     rax, [rbp+var_28]
0x180019b7d  xorps   xmm0, xmm0
0x180019b80  lea     rdx, dword_18001E3EC
0x180019b87  mov     [rbp+var_18], rax
0x180019b8b  mov     rcx, rbx
0x180019b8e  movdqu  [rbp+var_28], xmm0
0x180019b93  call    ?enum_keys@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(void *,wchar_t const *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)
0x180019b98  mov     rdi, [rbp+var_10]
0x180019b9c  lea     rax, [rbp+var_28]
0x180019ba0  cmp     rdi, rax
0x180019ba3  jz      loc_180019C53
0x180019ba9  mov     rdx, [rdi]
0x180019bac  mov     [rbp+Handle], r14
0x180019bb0  mov     ecx, [rdx]
0x180019bb2  shr     ecx, 1
0x180019bb4  cmp     ecx, 0FFFFh
0x180019bba  ja      short loc_180019BC2
0x180019bbc  movzx   r8d, cx
0x180019bc0  jmp     short loc_180019BC8
0x180019bc2  mov     r8d, 0FFFFh
0x180019bc8  mov     eax, r14d
0x180019bcb  cmovbe  ax, r8w
0x180019bd0  test    ax, ax
0x180019bd3  jnz     short loc_180019BDA
0x180019bd5  mov     rdx, r14
0x180019bd8  jmp     short loc_180019BDE
0x180019bda  mov     rdx, [rdx+8]
0x180019bde  lea     r8, [rbp+Handle]
0x180019be2  mov     rcx, rbx
0x180019be5  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x180019bea  mov     esi, eax
0x180019bec  test    eax, eax
0x180019bee  js      short loc_180019C1A
0x180019bf0  lea     rcx, [rbp+Handle]
0x180019bf4  call    ?delete_user_configurations@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBVhandle@kernel@shared@appv@@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_user_configurations(appv::shared::kernel::handle const &)
0x180019bf9  mov     esi, eax
0x180019bfb  test    eax, eax
0x180019bfd  js      short loc_180019C1A
0x180019bff  mov     rcx, [rbp+Handle]; Handle
0x180019c03  test    rcx, rcx
0x180019c06  jz      short loc_180019C14
0x180019c08  call    cs:__imp_ZwClose
0x180019c0f  nop     dword ptr [rax+rax+00h]
0x180019c14  mov     rdi, [rdi+18h]
0x180019c18  jmp     short loc_180019B9C
0x180019c1a  mov     rcx, [rbp+Handle]; Handle
0x180019c1e  test    rcx, rcx
0x180019c21  jz      short loc_180019C2F
0x180019c23  call    cs:__imp_ZwClose
0x180019c2a  nop     dword ptr [rax+rax+00h]
0x180019c2f  lea     rcx, [rbp+var_30]
0x180019c33  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x180019c38  test    rbx, rbx
0x180019c3b  jz      short loc_180019C4C
0x180019c3d  mov     rcx, rbx; Handle
0x180019c40  call    cs:__imp_ZwClose
0x180019c47  nop     dword ptr [rax+rax+00h]
0x180019c4c  mov     eax, esi
0x180019c4e  jmp     loc_180019CDF
0x180019c53  lea     rcx, [rbp+var_30]
0x180019c57  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x180019c5c  lea     r8, [rbp+Handle]
0x180019c60  mov     [rbp+Handle], r14
0x180019c64  lea     rdx, aRegistryMachin_4; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x180019c6b  xor     ecx, ecx
0x180019c6d  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x180019c72  mov     edi, eax
0x180019c74  test    eax, eax
0x180019c76  js      short loc_180019C9C
0x180019c78  lea     rcx, [rbp+Handle]
0x180019c7c  call    ?delete_user_configurations@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBVhandle@kernel@shared@appv@@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_user_configurations(appv::shared::kernel::handle const &)
0x180019c81  mov     edi, eax
0x180019c83  test    eax, eax
0x180019c85  jns     short loc_180019CA4
0x180019c87  jmp     short loc_180019CB4
0x180019c89  cmp     edi, 0C0000034h
0x180019c8f  jz      short loc_180019C5C
0x180019c91  mov     rcx, [rbp+Handle]
0x180019c95  test    rcx, rcx
0x180019c98  jz      short loc_180019CDD
0x180019c9a  jmp     short loc_180019CD1
0x180019c9c  cmp     edi, 0C0000034h
0x180019ca2  jnz     short loc_180019CB4
0x180019ca4  lea     rdx, aRegistryMachin_6; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x180019cab  xor     ecx, ecx
0x180019cad  call    ?delete_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_W_N@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_key(void *,wchar_t const *,bool)
0x180019cb2  mov     edi, eax
0x180019cb4  mov     rcx, [rbp+Handle]; Handle
0x180019cb8  test    rcx, rcx
0x180019cbb  jz      short loc_180019CC9
0x180019cbd  call    cs:__imp_ZwClose
0x180019cc4  nop     dword ptr [rax+rax+00h]
0x180019cc9  test    rbx, rbx
0x180019ccc  jz      short loc_180019CDD
0x180019cce  mov     rcx, rbx; Handle
0x180019cd1  call    cs:__imp_ZwClose
0x180019cd8  nop     dword ptr [rax+rax+00h]
0x180019cdd  mov     eax, edi
0x180019cdf  lea     r11, [rsp+50h+var_s0]
0x180019ce4  mov     rbx, [r11+28h]
0x180019ce8  mov     rsi, [r11+30h]
0x180019cec  mov     rsp, r11
0x180019cef  pop     r14
0x180019cf1  pop     rdi
0x180019cf2  pop     rbp
0x180019cf3  retn
```
