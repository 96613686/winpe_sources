# registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)

- ea: `0x18000cf74`
- end: `0x18000d04d`
- name: `?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z`
- size: `217`
- prototype: `__int64 __fastcall(void *, __int64, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000f300`
- `0x180017c7c`
- `0x180019014`
- `0x18001a79c`

## callees

- `0x18000a9e4`
- `0x18000cf74`
- `0x18000d054`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18000cfae`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000cfd6`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000cffb`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000d033`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000cfae`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000cfd6`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000cffb`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000d033`

## pseudocode

```c
__int64 __fastcall registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(
        void *a1,
        __int64 a2,
        __int64 a3)
{
  int value_in_buffer; // ebx
  __int64 v5; // r9

  value_in_buffer = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value_in_buffer(a1);
  if ( value_in_buffer < 0 )
    return (unsigned int)value_in_buffer;
  if ( MEMORY[4] != 1 )
    return 3221225534LL;
  if ( MEMORY[0xC] >= 2u )
    return (unsigned int)appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
                           a3,
                           (const void *)MEMORY[8],
                           (unsigned __int16)(((unsigned __int64)MEMORY[0xC] - 2) >> 1),
                           v5);
  return 3221225701LL;
}

```

## disassembly

```asm
0x18000cf74  mov     rax, rsp
0x18000cf77  mov     [rax+8], rbx
0x18000cf7b  push    rdi
0x18000cf7c  sub     rsp, 30h
0x18000cf80  mov     rdi, r8
0x18000cf83  mov     qword ptr [rax-18h], 0
0x18000cf8b  lea     r8, [rax-18h]
0x18000cf8f  mov     qword ptr [rax-10h], 0
0x18000cf97  call    ?get_value_in_buffer@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJPEAXPEB_WAEAV?$buffer@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value_in_buffer(void *,wchar_t const *,appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x18000cf9c  mov     ebx, eax
0x18000cf9e  test    eax, eax
0x18000cfa0  jns     short loc_18000CFC1
0x18000cfa2  mov     rcx, [rsp+38h+P]; P
0x18000cfa7  test    rcx, rcx
0x18000cfaa  jz      short loc_18000CFBA
0x18000cfac  xor     edx, edx; Tag
0x18000cfae  call    cs:__imp_ExFreePoolWithTag
0x18000cfb5  nop     dword ptr [rax+rax+00h]
0x18000cfba  mov     eax, ebx
0x18000cfbc  jmp     loc_18000D041
0x18000cfc1  mov     rbx, [rsp+38h+P]
0x18000cfc6  cmp     dword ptr [rbx+4], 1
0x18000cfca  jz      short loc_18000CFE9
0x18000cfcc  test    rbx, rbx
0x18000cfcf  jz      short loc_18000CFE2
0x18000cfd1  xor     edx, edx; Tag
0x18000cfd3  mov     rcx, rbx; P
0x18000cfd6  call    cs:__imp_ExFreePoolWithTag
0x18000cfdd  nop     dword ptr [rax+rax+00h]
0x18000cfe2  mov     eax, 0C000003Eh
0x18000cfe7  jmp     short loc_18000D041
0x18000cfe9  mov     eax, [rbx+0Ch]
0x18000cfec  cmp     eax, 2
0x18000cfef  jnb     short loc_18000D00E
0x18000cff1  test    rbx, rbx
0x18000cff4  jz      short loc_18000D007
0x18000cff6  xor     edx, edx; Tag
0x18000cff8  mov     rcx, rbx; P
0x18000cffb  call    cs:__imp_ExFreePoolWithTag
0x18000d002  nop     dword ptr [rax+rax+00h]
0x18000d007  mov     eax, 0C00000E5h
0x18000d00c  jmp     short loc_18000D041
0x18000d00e  mov     edx, [rbx+8]
0x18000d011  add     rax, 0FFFFFFFFFFFFFFFEh
0x18000d015  shr     rax, 1
0x18000d018  add     rdx, rbx
0x18000d01b  movzx   r8d, ax
0x18000d01f  mov     rcx, rdi
0x18000d022  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x18000d027  mov     edi, eax
0x18000d029  test    rbx, rbx
0x18000d02c  jz      short loc_18000D03F
0x18000d02e  xor     edx, edx; Tag
0x18000d030  mov     rcx, rbx; P
0x18000d033  call    cs:__imp_ExFreePoolWithTag
0x18000d03a  nop     dword ptr [rax+rax+00h]
0x18000d03f  mov     eax, edi
0x18000d041  mov     rbx, [rsp+38h+arg_0]
0x18000d046  add     rsp, 30h
0x18000d04a  pop     rdi
0x18000d04b  retn
```
