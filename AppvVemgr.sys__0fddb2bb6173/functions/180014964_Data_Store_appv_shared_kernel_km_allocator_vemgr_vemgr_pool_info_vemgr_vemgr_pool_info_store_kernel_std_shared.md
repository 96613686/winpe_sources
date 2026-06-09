# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store(kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)

- ea: `0x180014964`
- end: `0x180014ac4`
- name: `?store@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJAEBV?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `352`
- prototype: `__int64 __fastcall(__int64 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180012264`

## callees

- `0x18000e23c`
- `0x1800137f8`
- `0x180014338`
- `0x180014964`
- `0x180015278`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1800149fa`
- `ntoskrnl!ZwClose` at `0x180014a53`
- `ntoskrnl!ZwClose` at `0x180014a67`
- `ntoskrnl!ZwClose` at `0x1800149fa`
- `ntoskrnl!ZwClose` at `0x180014a53`
- `ntoskrnl!ZwClose` at `0x180014a67`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store(
        __int64 **a1)
{
  __int64 *v2; // rax
  __int64 v3; // rax
  unsigned int v4; // eax
  int v5; // ebx
  __int64 *v7; // rax
  _DWORD *v8; // rdx
  unsigned int v9; // eax
  __int64 v10; // rdx
  HANDLE v11; // rbx
  NTSTATUS v12; // esi
  __int64 v13; // rax
  unsigned int v14; // ecx
  __int64 v15; // rcx
  HANDLE Handle; // [rsp+40h] [rbp+8h] BYREF
  HANDLE v17; // [rsp+48h] [rbp+10h] BYREF

  if ( !*a1 )
    return 3221225485LL;
  v2 = a1[1];
  if ( !v2 )
    return 3221225485LL;
  if ( !*((_DWORD *)v2 + 2) )
    return 3221225485LL;
  if ( !**a1 )
    return 3221225485LL;
  v3 = (*a1)[1];
  if ( !v3 )
    return 3221225485LL;
  if ( !*(_DWORD *)(v3 + 8) )
    return 3221225485LL;
  v4 = *(_DWORD *)**a1 >> 1;
  if ( v4 > 0xFFFF || !(_WORD)v4 )
    return 3221225485LL;
  Handle = 0;
  v5 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_root_key(
         &Handle,
         1);
  if ( v5 >= 0 )
  {
    v7 = *a1;
    v17 = 0;
    v8 = (_DWORD *)*v7;
    v9 = *(_DWORD *)*v7 >> 1;
    if ( v9 <= 0xFFFF && (_WORD)v9 )
      v10 = *((_QWORD *)v8 + 1);
    else
      v10 = 0;
    v11 = Handle;
    v12 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
            Handle,
            v10,
            &v17);
    if ( v12 < 0 )
    {
      v12 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_package_group_data(
              &Handle,
              a1);
      if ( v12 < 0 )
      {
        v13 = **a1;
        v14 = *(_DWORD *)v13 >> 1;
        if ( v14 <= 0xFFFF && (_WORD)v14 )
          v15 = *(_QWORD *)(v13 + 8);
        else
          v15 = 0;
        Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_package_group(v15);
      }
    }
    if ( v17 )
      ZwClose(v17);
    if ( v11 )
      ZwClose(v11);
    return (unsigned int)v12;
  }
  else
  {
    if ( Handle )
      ZwClose(Handle);
    return (unsigned int)v5;
  }
}

```

## disassembly

```asm
0x180014964  mov     [rsp+arg_10], rbx
0x180014969  push    rbp
0x18001496a  push    rsi
0x18001496b  push    rdi
0x18001496c  sub     rsp, 20h
0x180014970  xor     ebp, ebp
0x180014972  mov     rdi, rcx
0x180014975  cmp     [rcx], rbp
0x180014978  jz      loc_180014AB1
0x18001497e  mov     rax, [rcx+8]
0x180014982  test    rax, rax
0x180014985  jz      loc_180014AB1
0x18001498b  mov     eax, [rax+8]
0x18001498e  test    eax, eax
0x180014990  jz      loc_180014AB1
0x180014996  mov     rax, [rcx]
0x180014999  cmp     [rax], rbp
0x18001499c  jz      loc_180014AB1
0x1800149a2  mov     rax, [rax+8]
0x1800149a6  test    rax, rax
0x1800149a9  jz      loc_180014AB1
0x1800149af  mov     eax, [rax+8]
0x1800149b2  test    eax, eax
0x1800149b4  jz      loc_180014AB1
0x1800149ba  mov     rax, [rcx]
0x1800149bd  mov     rcx, [rax]
0x1800149c0  mov     eax, [rcx]
0x1800149c2  shr     eax, 1
0x1800149c4  cmp     eax, 0FFFFh
0x1800149c9  ja      loc_180014AB1
0x1800149cf  test    ax, ax
0x1800149d2  jz      loc_180014AB1
0x1800149d8  lea     edx, [rbp+1]
0x1800149db  mov     [rsp+38h+Handle], rbp
0x1800149e0  lea     rcx, [rsp+38h+Handle]
0x1800149e5  call    ?create_root_key@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEAVhandle@kernel@shared@appv@@W4ConfigurationType@1@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_root_key(appv::shared::kernel::handle &,Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ConfigurationType)
0x1800149ea  mov     ebx, eax
0x1800149ec  test    eax, eax
0x1800149ee  jns     short loc_180014A0D
0x1800149f0  mov     rcx, [rsp+38h+Handle]; Handle
0x1800149f5  test    rcx, rcx
0x1800149f8  jz      short loc_180014A06
0x1800149fa  call    cs:__imp_ZwClose
0x180014a01  nop     dword ptr [rax+rax+00h]
0x180014a06  mov     eax, ebx
0x180014a08  jmp     loc_180014AB6
0x180014a0d  mov     rax, [rdi]
0x180014a10  mov     [rsp+38h+arg_8], rbp
0x180014a15  mov     rdx, [rax]
0x180014a18  mov     eax, [rdx]
0x180014a1a  shr     eax, 1
0x180014a1c  cmp     eax, 0FFFFh
0x180014a21  ja      short loc_180014A2E
0x180014a23  test    ax, ax
0x180014a26  jz      short loc_180014A2E
0x180014a28  mov     rdx, [rdx+8]
0x180014a2c  jmp     short loc_180014A31
0x180014a2e  mov     rdx, rbp
0x180014a31  mov     rbx, [rsp+38h+Handle]
0x180014a36  lea     r8, [rsp+38h+arg_8]
0x180014a3b  mov     rcx, rbx
0x180014a3e  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x180014a43  mov     esi, eax
0x180014a45  test    eax, eax
0x180014a47  js      short loc_180014A77
0x180014a49  mov     rcx, [rsp+38h+arg_8]; Handle
0x180014a4e  test    rcx, rcx
0x180014a51  jz      short loc_180014A5F
0x180014a53  call    cs:__imp_ZwClose
0x180014a5a  nop     dword ptr [rax+rax+00h]
0x180014a5f  test    rbx, rbx
0x180014a62  jz      short loc_180014A73
0x180014a64  mov     rcx, rbx; Handle
0x180014a67  call    cs:__imp_ZwClose
0x180014a6e  nop     dword ptr [rax+rax+00h]
0x180014a73  mov     eax, esi
0x180014a75  jmp     short loc_180014AB6
0x180014a77  mov     rdx, rdi
0x180014a7a  lea     rcx, [rsp+38h+Handle]
0x180014a7f  call    ?store_package_group_data@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBVhandle@kernel@shared@appv@@AEBV?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_package_group_data(appv::shared::kernel::handle const &,kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x180014a84  mov     esi, eax
0x180014a86  test    eax, eax
0x180014a88  jns     short loc_180014A49
0x180014a8a  mov     rcx, [rdi]
0x180014a8d  mov     rax, [rcx]
0x180014a90  mov     ecx, [rax]
0x180014a92  shr     ecx, 1
0x180014a94  cmp     ecx, 0FFFFh
0x180014a9a  ja      short loc_180014AA7
0x180014a9c  test    cx, cx
0x180014a9f  jz      short loc_180014AA7
0x180014aa1  mov     rcx, [rax+8]
0x180014aa5  jmp     short loc_180014AAA
0x180014aa7  mov     rcx, rbp
0x180014aaa  call    ?remove_package_group@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_W@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_package_group(wchar_t const *)
0x180014aaf  jmp     short loc_180014A49
0x180014ab1  mov     eax, 0C000000Dh
0x180014ab6  mov     rbx, [rsp+38h+arg_10]
0x180014abb  add     rsp, 20h
0x180014abf  pop     rdi
0x180014ac0  pop     rsi
0x180014ac1  pop     rbp
0x180014ac2  retn
```
