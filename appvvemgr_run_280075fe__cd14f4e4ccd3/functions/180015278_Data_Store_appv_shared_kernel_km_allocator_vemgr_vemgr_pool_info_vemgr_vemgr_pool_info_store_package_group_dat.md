# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_package_group_data(appv::shared::kernel::handle const &,kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)

- ea: `0x180015278`
- end: `0x1800153bf`
- name: `?store_package_group_data@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBVhandle@kernel@shared@appv@@AEBV?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180014964`

## callees

- `0x18000b420`
- `0x18000f994`
- `0x180015278`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1800152e1`
- `ntoskrnl!ZwClose` at `0x180015378`
- `ntoskrnl!ZwClose` at `0x18001538f`
- `ntoskrnl!ZwClose` at `0x1800153a3`
- `ntoskrnl!ZwClose` at `0x1800152e1`
- `ntoskrnl!ZwClose` at `0x180015378`
- `ntoskrnl!ZwClose` at `0x18001538f`
- `ntoskrnl!ZwClose` at `0x1800153a3`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_package_group_data(
        void **a1,
        __int64 a2)
{
  _QWORD *v2; // rax
  _DWORD *v4; // rdx
  unsigned int v5; // r8d
  __int16 v6; // r9
  __int16 v7; // ax
  const WCHAR *v8; // rdx
  NTSTATUS v9; // ebx
  HANDLE v11; // rbx
  int v12; // esi
  __int64 *i; // rdi
  __int64 v14; // rdx
  unsigned int v15; // ecx
  __int16 v16; // r8
  __int16 v17; // ax
  const WCHAR *v18; // rdx
  HANDLE Handle; // [rsp+60h] [rbp+8h] BYREF

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
  if ( v7 )
    v8 = (const WCHAR *)*((_QWORD *)v4 + 1);
  else
    v8 = 0;
  v9 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(
         *a1,
         v8,
         &Handle);
  if ( v9 >= 0 )
  {
    v11 = Handle;
    v12 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(
            Handle,
            L"Priority",
            *(_DWORD *)(*(_QWORD *)a2 + 56LL));
    if ( v12 >= 0 )
    {
      for ( i = *(__int64 **)(*(_QWORD *)a2 + 48LL); i != (__int64 *)(*(_QWORD *)a2 + 24LL); i = (__int64 *)i[3] )
      {
        v14 = *i;
        Handle = 0;
        v15 = *(_DWORD *)v14 >> 1;
        if ( v15 > 0xFFFF )
          v16 = -1;
        else
          v16 = *(_DWORD *)v14 >> 1;
        v17 = 0;
        if ( v15 <= 0xFFFF )
          v17 = v16;
        if ( v17 )
          v18 = *(const WCHAR **)(v14 + 8);
        else
          v18 = 0;
        v12 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(
                v11,
                v18,
                &Handle);
        if ( v12 < 0 )
        {
          if ( Handle )
            ZwClose(Handle);
          break;
        }
        if ( Handle )
          ZwClose(Handle);
      }
    }
    if ( v11 )
      ZwClose(v11);
    return (unsigned int)v12;
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
0x180015278  push    rbx
0x18001527a  push    rbp
0x18001527b  push    rsi
0x18001527c  push    rdi
0x18001527d  push    r14
0x18001527f  push    r15
0x180015281  sub     rsp, 28h
0x180015285  mov     rax, [rdx]
0x180015288  xor     ebp, ebp
0x18001528a  mov     r14, rdx
0x18001528d  mov     [rsp+58h+Handle], rbp
0x180015292  mov     r15d, 0FFFFh
0x180015298  mov     rdx, [rax]
0x18001529b  mov     r8d, [rdx]
0x18001529e  shr     r8d, 1
0x1800152a1  cmp     r8d, r15d
0x1800152a4  ja      short loc_1800152AC
0x1800152a6  movzx   r9d, r8w
0x1800152aa  jmp     short loc_1800152AF
0x1800152ac  mov     r9d, r15d
0x1800152af  mov     eax, ebp
0x1800152b1  cmovbe  ax, r9w
0x1800152b6  test    ax, ax
0x1800152b9  jnz     short loc_1800152C0
0x1800152bb  mov     rdx, rbp
0x1800152be  jmp     short loc_1800152C4
0x1800152c0  mov     rdx, [rdx+8]
0x1800152c4  mov     rcx, [rcx]
0x1800152c7  lea     r8, [rsp+58h+Handle]
0x1800152cc  call    ?create_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(void *,wchar_t const *,appv::shared::kernel::handle &)
0x1800152d1  mov     ebx, eax
0x1800152d3  test    eax, eax
0x1800152d5  jns     short loc_1800152F4
0x1800152d7  mov     rcx, [rsp+58h+Handle]; Handle
0x1800152dc  test    rcx, rcx
0x1800152df  jz      short loc_1800152ED
0x1800152e1  call    cs:__imp_ZwClose
0x1800152e8  nop     dword ptr [rax+rax+00h]
0x1800152ed  mov     eax, ebx
0x1800152ef  jmp     loc_1800153B1
0x1800152f4  mov     r8, [r14]
0x1800152f7  lea     rdx, aPriority; "Priority"
0x1800152fe  mov     rbx, [rsp+58h+Handle]
0x180015303  mov     rcx, rbx; KeyHandle
0x180015306  mov     r8d, [r8+38h]
0x18001530a  call    ?set_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(void *,wchar_t const *,ulong)
0x18001530f  mov     esi, eax
0x180015311  test    eax, eax
0x180015313  js      loc_18001539B
0x180015319  mov     rdi, [r14]
0x18001531c  mov     rdi, [rdi+30h]
0x180015320  mov     rax, [r14]
0x180015323  add     rax, 18h
0x180015327  cmp     rdi, rax
0x18001532a  jz      short loc_18001539B
0x18001532c  mov     rdx, [rdi]
0x18001532f  mov     [rsp+58h+Handle], rbp
0x180015334  mov     ecx, [rdx]
0x180015336  shr     ecx, 1
0x180015338  cmp     ecx, r15d
0x18001533b  ja      short loc_180015343
0x18001533d  movzx   r8d, cx
0x180015341  jmp     short loc_180015346
0x180015343  mov     r8d, r15d
0x180015346  mov     eax, ebp
0x180015348  cmovbe  ax, r8w
0x18001534d  test    ax, ax
0x180015350  jnz     short loc_180015357
0x180015352  mov     rdx, rbp
0x180015355  jmp     short loc_18001535B
0x180015357  mov     rdx, [rdx+8]
0x18001535b  lea     r8, [rsp+58h+Handle]
0x180015360  mov     rcx, rbx
0x180015363  call    ?create_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(void *,wchar_t const *,appv::shared::kernel::handle &)
0x180015368  mov     rcx, [rsp+58h+Handle]; Handle
0x18001536d  mov     esi, eax
0x18001536f  test    eax, eax
0x180015371  js      short loc_18001538A
0x180015373  test    rcx, rcx
0x180015376  jz      short loc_180015384
0x180015378  call    cs:__imp_ZwClose
0x18001537f  nop     dword ptr [rax+rax+00h]
0x180015384  mov     rdi, [rdi+18h]
0x180015388  jmp     short loc_180015320
0x18001538a  test    rcx, rcx
0x18001538d  jz      short loc_18001539B
0x18001538f  call    cs:__imp_ZwClose
0x180015396  nop     dword ptr [rax+rax+00h]
0x18001539b  test    rbx, rbx
0x18001539e  jz      short loc_1800153AF
0x1800153a0  mov     rcx, rbx; Handle
0x1800153a3  call    cs:__imp_ZwClose
0x1800153aa  nop     dword ptr [rax+rax+00h]
0x1800153af  mov     eax, esi
0x1800153b1  add     rsp, 28h
0x1800153b5  pop     r15
0x1800153b7  pop     r14
0x1800153b9  pop     rdi
0x1800153ba  pop     rsi
0x1800153bb  pop     rbp
0x1800153bc  pop     rbx
0x1800153bd  retn
```
