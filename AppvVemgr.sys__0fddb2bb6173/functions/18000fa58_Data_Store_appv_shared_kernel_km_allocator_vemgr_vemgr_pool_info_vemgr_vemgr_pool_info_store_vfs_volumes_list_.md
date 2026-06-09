# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_vfs_volumes_list(appv::shared::kernel::handle const &,wchar_t const *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &)

- ea: `0x18000fa58`
- end: `0x18000fb4f`
- name: `?store_vfs_volumes_list@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBVhandle@kernel@shared@appv@@PEB_WAEBV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@345@@Z`
- size: `247`
- prototype: `__int64 __fastcall(__int64 *, void *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000f718`
- `0x1800153c8`

## callees

- `0x18000b420`
- `0x18000b478`
- `0x18000f994`
- `0x18000fa58`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18000fb33`
- `ntoskrnl!ZwClose` at `0x18000fb33`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_vfs_volumes_list(
        __int64 *a1,
        void *a2,
        __int64 a3)
{
  __int64 result; // rax
  void *v6; // rcx
  int v7; // esi
  HANDLE v8; // rcx
  _QWORD *v9; // rdi
  _QWORD *v10; // rbp
  HANDLE v11; // rbx
  unsigned int v12; // ecx
  __int16 v13; // dx
  __int16 v14; // ax
  wchar_t *v15; // rdx
  HANDLE Handle; // [rsp+68h] [rbp+10h] BYREF

  Handle = a2;
  result = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_key(
             *a1,
             L"Volumes");
  if ( (int)(result + 0x80000000) < 0 || (_DWORD)result == -1073741772 )
  {
    v6 = (void *)*a1;
    Handle = 0;
    v7 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(
           v6,
           L"Volumes",
           &Handle);
    if ( v7 >= 0 )
    {
      v9 = *(_QWORD **)(a3 + 32);
      v10 = (_QWORD *)(a3 + 8);
      v11 = Handle;
      while ( v9 != v10 )
      {
        v12 = *(_DWORD *)*v9 >> 1;
        if ( v12 > 0xFFFF )
          v13 = -1;
        else
          v13 = *(_DWORD *)*v9 >> 1;
        v14 = 0;
        if ( v12 <= 0xFFFF )
          v14 = v13;
        v15 = 0;
        if ( v14 )
          v15 = *(wchar_t **)(*v9 + 8LL);
        v7 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(
               v11,
               v15,
               1);
        if ( v7 < 0 )
        {
          registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_key(
            *a1,
            L"Volumes");
          break;
        }
        v9 = (_QWORD *)v9[3];
      }
      if ( !v11 )
        return (unsigned int)v7;
      v8 = v11;
    }
    else
    {
      v8 = Handle;
      if ( !Handle )
        return (unsigned int)v7;
    }
    ZwClose(v8);
    return (unsigned int)v7;
  }
  return result;
}

```

## disassembly

```asm
0x18000fa58  mov     [rsp+Handle], rdx
0x18000fa5d  push    rbx
0x18000fa5e  push    rbp
0x18000fa5f  push    rsi
0x18000fa60  push    rdi
0x18000fa61  push    r14
0x18000fa63  push    r15
0x18000fa65  sub     rsp, 28h
0x18000fa69  mov     r14, rcx
0x18000fa6c  lea     rdx, aVolumes; "Volumes"
0x18000fa73  mov     rcx, [rcx]
0x18000fa76  mov     rbx, r8
0x18000fa79  call    ?delete_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_W_N@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_key(void *,wchar_t const *,bool)
0x18000fa7e  mov     ecx, 80000000h
0x18000fa83  lea     edx, [rax+rcx]
0x18000fa86  test    ecx, edx
0x18000fa88  jnz     short loc_18000FA95
0x18000fa8a  cmp     eax, 0C0000034h
0x18000fa8f  jnz     loc_18000FB41
0x18000fa95  mov     rcx, [r14]
0x18000fa98  lea     r8, [rsp+58h+Handle]
0x18000fa9d  xor     r15d, r15d
0x18000faa0  lea     rdx, aVolumes; "Volumes"
0x18000faa7  mov     [rsp+58h+Handle], r15
0x18000faac  call    ?create_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(void *,wchar_t const *,appv::shared::kernel::handle &)
0x18000fab1  mov     esi, eax
0x18000fab3  test    eax, eax
0x18000fab5  jns     short loc_18000FAC3
0x18000fab7  mov     rcx, [rsp+58h+Handle]
0x18000fabc  test    rcx, rcx
0x18000fabf  jz      short loc_18000FB3F
0x18000fac1  jmp     short loc_18000FB33
0x18000fac3  mov     rdi, [rbx+20h]
0x18000fac7  lea     rbp, [rbx+8]
0x18000facb  mov     rbx, [rsp+58h+Handle]
0x18000fad0  cmp     rdi, rbp
0x18000fad3  jz      short loc_18000FB2B
0x18000fad5  mov     r8, [rdi]
0x18000fad8  mov     ecx, [r8]
0x18000fadb  shr     ecx, 1
0x18000fadd  cmp     ecx, 0FFFFh
0x18000fae3  ja      short loc_18000FAEA
0x18000fae5  movzx   edx, cx
0x18000fae8  jmp     short loc_18000FAEF
0x18000faea  mov     edx, 0FFFFh
0x18000faef  mov     eax, r15d
0x18000faf2  cmovbe  ax, dx
0x18000faf6  mov     rdx, r15
0x18000faf9  test    ax, ax
0x18000fafc  jz      short loc_18000FB02
0x18000fafe  mov     rdx, [r8+8]
0x18000fb02  mov     r8d, 1
0x18000fb08  mov     rcx, rbx; KeyHandle
0x18000fb0b  call    ?set_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(void *,wchar_t const *,ulong)
0x18000fb10  mov     esi, eax
0x18000fb12  test    eax, eax
0x18000fb14  js      short loc_18000FB1C
0x18000fb16  mov     rdi, [rdi+18h]
0x18000fb1a  jmp     short loc_18000FAD0
0x18000fb1c  mov     rcx, [r14]
0x18000fb1f  lea     rdx, aVolumes; "Volumes"
0x18000fb26  call    ?delete_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_W_N@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_key(void *,wchar_t const *,bool)
0x18000fb2b  test    rbx, rbx
0x18000fb2e  jz      short loc_18000FB3F
0x18000fb30  mov     rcx, rbx; Handle
0x18000fb33  call    cs:__imp_ZwClose
0x18000fb3a  nop     dword ptr [rax+rax+00h]
0x18000fb3f  mov     eax, esi
0x18000fb41  add     rsp, 28h
0x18000fb45  pop     r15
0x18000fb47  pop     r14
0x18000fb49  pop     rdi
0x18000fb4a  pop     rsi
0x18000fb4b  pop     rbp
0x18000fb4c  pop     rbx
0x18000fb4d  retn
```
