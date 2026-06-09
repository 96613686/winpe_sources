# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_package_data(appv::shared::kernel::handle const &,kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)

- ea: `0x180015154`
- end: `0x18001526f`
- name: `?store_package_data@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBVhandle@kernel@shared@appv@@AEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `283`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800147fc`

## callees

- `0x18000b420`
- `0x18000f994`
- `0x180014700`
- `0x180014d1c`
- `0x180015154`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1800151b6`
- `ntoskrnl!ZwClose` at `0x1800151f2`
- `ntoskrnl!ZwClose` at `0x180015257`
- `ntoskrnl!ZwClose` at `0x1800151b6`
- `ntoskrnl!ZwClose` at `0x1800151f2`
- `ntoskrnl!ZwClose` at `0x180015257`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_package_data(
        void **a1,
        __int64 a2)
{
  _QWORD *v2; // rax
  _DWORD *v4; // r9
  unsigned int v5; // r8d
  __int16 v6; // dx
  __int16 v7; // ax
  const WCHAR *v8; // rdx
  NTSTATUS v9; // ebx
  HANDLE v11; // rbx
  int v12; // esi
  void *v13; // rdx
  unsigned int v14; // edi
  HANDLE Handle; // [rsp+50h] [rbp+8h] BYREF

  v2 = *(_QWORD **)a2;
  Handle = 0;
  v4 = (_DWORD *)*v2;
  v5 = *(_DWORD *)*v2 >> 1;
  if ( v5 > 0xFFFF )
    v6 = -1;
  else
    v6 = *(_DWORD *)*v2 >> 1;
  v7 = 0;
  if ( v5 <= 0xFFFF )
    v7 = v6;
  v8 = 0;
  if ( v7 )
    v8 = (const WCHAR *)*((_QWORD *)v4 + 1);
  v9 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(
         *a1,
         v8,
         &Handle);
  if ( v9 >= 0 )
  {
    v11 = Handle;
    v12 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(
            Handle,
            L"PackageRoot",
            *(_QWORD *)a2 + 16LL);
    if ( v12 < 0
      || (v12 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(
                  v11,
                  L"Packaged32",
                  *(unsigned __int8 *)(*(_QWORD *)a2 + 48LL)),
          v12 < 0)
      || (v12 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(
                  v11,
                  L"JITV",
                  *(unsigned __int8 *)(*(_QWORD *)a2 + 49LL)),
          v12 < 0) )
    {
      if ( v11 )
        ZwClose(v11);
      return (unsigned int)v12;
    }
    else
    {
      v14 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_mappings(
              (__int64 *)&Handle,
              v13,
              *(_QWORD *)a2 + 56LL);
      if ( v11 )
        ZwClose(v11);
      return v14;
    }
  }
  else
  {
    if ( Handle )
      ZwClose(Handle);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x180015154  push    rbx
0x180015156  push    rbp
0x180015157  push    rsi
0x180015158  push    rdi
0x180015159  sub     rsp, 28h
0x18001515d  mov     rax, [rdx]
0x180015160  xor     ebp, ebp
0x180015162  mov     r10d, 0FFFFh
0x180015168  mov     [rsp+48h+Handle], rbp
0x18001516d  mov     rdi, rdx
0x180015170  mov     r9, [rax]
0x180015173  mov     r8d, [r9]
0x180015176  shr     r8d, 1
0x180015179  cmp     r8d, r10d
0x18001517c  ja      short loc_180015184
0x18001517e  movzx   edx, r8w
0x180015182  jmp     short loc_180015187
0x180015184  mov     edx, r10d
0x180015187  mov     eax, ebp
0x180015189  cmovbe  ax, dx
0x18001518d  mov     rdx, rbp
0x180015190  test    ax, ax
0x180015193  jz      short loc_180015199
0x180015195  mov     rdx, [r9+8]
0x180015199  mov     rcx, [rcx]
0x18001519c  lea     r8, [rsp+48h+Handle]
0x1800151a1  call    ?create_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(void *,wchar_t const *,appv::shared::kernel::handle &)
0x1800151a6  mov     ebx, eax
0x1800151a8  test    eax, eax
0x1800151aa  jns     short loc_1800151C9
0x1800151ac  mov     rcx, [rsp+48h+Handle]; Handle
0x1800151b1  test    rcx, rcx
0x1800151b4  jz      short loc_1800151C2
0x1800151b6  call    cs:__imp_ZwClose
0x1800151bd  nop     dword ptr [rax+rax+00h]
0x1800151c2  mov     eax, ebx
0x1800151c4  jmp     loc_180015265
0x1800151c9  mov     r8, [rdi]
0x1800151cc  lea     rdx, aPackageroot; "PackageRoot"
0x1800151d3  mov     rbx, [rsp+48h+Handle]
0x1800151d8  add     r8, 10h
0x1800151dc  mov     rcx, rbx; KeyHandle
0x1800151df  call    ?set_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(void *,wchar_t const *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)
0x1800151e4  mov     esi, eax
0x1800151e6  test    eax, eax
0x1800151e8  jns     short loc_180015202
0x1800151ea  test    rbx, rbx
0x1800151ed  jz      short loc_1800151FE
0x1800151ef  mov     rcx, rbx; Handle
0x1800151f2  call    cs:__imp_ZwClose
0x1800151f9  nop     dword ptr [rax+rax+00h]
0x1800151fe  mov     eax, esi
0x180015200  jmp     short loc_180015265
0x180015202  mov     rax, [rdi]
0x180015205  lea     rdx, aPackaged32; "Packaged32"
0x18001520c  mov     rcx, rbx; KeyHandle
0x18001520f  movzx   r8d, byte ptr [rax+30h]
0x180015214  call    ?set_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(void *,wchar_t const *,ulong)
0x180015219  mov     esi, eax
0x18001521b  test    eax, eax
0x18001521d  js      short loc_1800151EA
0x18001521f  mov     rax, [rdi]
0x180015222  lea     rdx, aJitv; "JITV"
0x180015229  mov     rcx, rbx; KeyHandle
0x18001522c  movzx   r8d, byte ptr [rax+31h]
0x180015231  call    ?set_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(void *,wchar_t const *,ulong)
0x180015236  mov     esi, eax
0x180015238  test    eax, eax
0x18001523a  js      short loc_1800151EA
0x18001523c  mov     r8, [rdi]
0x18001523f  lea     rcx, [rsp+48h+Handle]
0x180015244  add     r8, 38h ; '8'
0x180015248  call    ?store_mappings@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBVhandle@kernel@shared@appv@@PEB_WAEBV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@345@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_mappings(appv::shared::kernel::handle const &,wchar_t const *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &)
0x18001524d  mov     edi, eax
0x18001524f  test    rbx, rbx
0x180015252  jz      short loc_180015263
0x180015254  mov     rcx, rbx; Handle
0x180015257  call    cs:__imp_ZwClose
0x18001525e  nop     dword ptr [rax+rax+00h]
0x180015263  mov     eax, edi
0x180015265  add     rsp, 28h
0x180015269  pop     rdi
0x18001526a  pop     rsi
0x18001526b  pop     rbp
0x18001526c  pop     rbx
0x18001526d  retn
```
