# ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindUser<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)

- ea: `0x180001bec`
- end: `0x180001c92`
- name: `??$FindUser@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@00AEAV?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800071a0`

## callees

- `0x180001bec`
- `0x180007d54`

## pseudocode

```c
__int64 __fastcall ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindUser<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5)
{
  unsigned int v5; // r10d
  __int16 v8; // r11
  __int16 v9; // ax
  __int64 v10; // r9
  unsigned int v11; // ecx
  __int16 v12; // dx
  __int16 v13; // ax
  __int64 v14; // r8
  unsigned int v15; // ecx
  __int16 v16; // dx
  __int16 v17; // ax
  __int64 v18; // rdx

  v5 = *(_DWORD *)a4 >> 1;
  if ( v5 > 0xFFFF )
    v8 = -1;
  else
    v8 = *(_DWORD *)a4 >> 1;
  v9 = 0;
  if ( v5 <= 0xFFFF )
    v9 = v8;
  if ( v9 )
    v10 = *(_QWORD *)(a4 + 8);
  else
    v10 = 0;
  v11 = *(_DWORD *)a3 >> 1;
  if ( v11 > 0xFFFF )
    v12 = -1;
  else
    v12 = *(_DWORD *)a3 >> 1;
  v13 = 0;
  if ( v11 <= 0xFFFF )
    v13 = v12;
  if ( v13 )
    v14 = *(_QWORD *)(a3 + 8);
  else
    v14 = 0;
  v15 = *(_DWORD *)a2 >> 1;
  if ( v15 > 0xFFFF )
    v16 = -1;
  else
    v16 = *(_DWORD *)a2 >> 1;
  v17 = 0;
  if ( v15 <= 0xFFFF )
    v17 = v16;
  v18 = 0;
  if ( v17 )
    v18 = *(_QWORD *)(a2 + 8);
  return ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindUser(
           a1,
           v18,
           v14,
           v10,
           a5);
}

```

## disassembly

```asm
0x180001bec  push    rbx
0x180001bee  push    rbp
0x180001bef  push    rsi
0x180001bf0  push    rdi
0x180001bf1  sub     rsp, 38h
0x180001bf5  mov     r10d, [r9]
0x180001bf8  mov     ebp, 0FFFFh
0x180001bfd  shr     r10d, 1
0x180001c00  mov     rbx, rdx
0x180001c03  mov     rdi, rcx
0x180001c06  cmp     r10d, ebp
0x180001c09  ja      short loc_180001C11
0x180001c0b  movzx   r11d, r10w
0x180001c0f  jmp     short loc_180001C14
0x180001c11  mov     r11d, ebp
0x180001c14  xor     esi, esi
0x180001c16  cmp     r10d, ebp
0x180001c19  mov     eax, esi
0x180001c1b  cmovbe  ax, r11w
0x180001c20  test    ax, ax
0x180001c23  jnz     short loc_180001C2A
0x180001c25  mov     r9d, esi
0x180001c28  jmp     short loc_180001C2E
0x180001c2a  mov     r9, [r9+8]
0x180001c2e  mov     ecx, [r8]
0x180001c31  shr     ecx, 1
0x180001c33  cmp     ecx, ebp
0x180001c35  ja      short loc_180001C3C
0x180001c37  movzx   edx, cx
0x180001c3a  jmp     short loc_180001C3E
0x180001c3c  mov     edx, ebp
0x180001c3e  mov     eax, esi
0x180001c40  cmovbe  ax, dx
0x180001c44  test    ax, ax
0x180001c47  jnz     short loc_180001C4E
0x180001c49  mov     r8, rsi
0x180001c4c  jmp     short loc_180001C52
0x180001c4e  mov     r8, [r8+8]
0x180001c52  mov     ecx, [rbx]
0x180001c54  shr     ecx, 1
0x180001c56  cmp     ecx, ebp
0x180001c58  ja      short loc_180001C5F
0x180001c5a  movzx   edx, cx
0x180001c5d  jmp     short loc_180001C61
0x180001c5f  mov     edx, ebp
0x180001c61  mov     eax, esi
0x180001c63  cmovbe  ax, dx
0x180001c67  mov     rdx, rsi
0x180001c6a  test    ax, ax
0x180001c6d  jz      short loc_180001C73
0x180001c6f  mov     rdx, [rbx+8]
0x180001c73  mov     rax, [rsp+58h+arg_20]
0x180001c7b  mov     rcx, rdi
0x180001c7e  mov     [rsp+58h+var_38], rax
0x180001c83  call    ?FindUser@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJPEB_W00AEAV?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindUser(wchar_t const *,wchar_t const *,wchar_t const *,kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x180001c88  add     rsp, 38h
0x180001c8c  pop     rdi
0x180001c8d  pop     rsi
0x180001c8e  pop     rbp
0x180001c8f  pop     rbx
0x180001c90  retn
```
