# registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)

- ea: `0x18000ce9c`
- end: `0x18000cf6c`
- name: `?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAV?$buffer@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z`
- size: `208`
- prototype: `__int64 __fastcall(void *, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000e960`

## callees

- `0x18000ce9c`
- `0x18000d054`
- `0x18000e8d4`
- `0x18001bc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18000cedd`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000cf02`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000cf54`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000cedd`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000cf02`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000cf54`

## string_xrefs

- `0x18000cebf`: `UserSid`

## pseudocode

```c
__int64 __fastcall registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(
        void *a1,
        __int64 a2,
        __int64 a3)
{
  int value_in_buffer; // ebx
  __int64 v5; // r8
  __int64 v6; // r9
  size_t v8; // rdi
  const void *v9; // rbp

  value_in_buffer = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value_in_buffer(a1);
  if ( value_in_buffer < 0 )
    return (unsigned int)value_in_buffer;
  if ( MEMORY[4] != 3 )
    return 3221225534LL;
  v8 = MEMORY[0xC];
  v9 = (const void *)MEMORY[8];
  if ( (appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(
          a3,
          MEMORY[0xC],
          v5,
          v6)
      & 0xC0000000) == 0xC0000000 )
  {
    return (unsigned int)-1073741670;
  }
  else
  {
    memmove(*(void **)(a3 + 8), v9, v8);
    return 0;
  }
}

```

## disassembly

```asm
0x18000ce9c  push    rbx
0x18000ce9e  push    rbp
0x18000ce9f  push    rsi
0x18000cea0  push    rdi
0x18000cea1  sub     rsp, 38h
0x18000cea5  mov     rsi, r8
0x18000cea8  mov     [rsp+58h+var_38], 0
0x18000ceb1  lea     r8, [rsp+58h+var_38]
0x18000ceb6  mov     [rsp+58h+P], 0
0x18000cebf  lea     rdx, aUsersid; "UserSid"
0x18000cec6  call    ?get_value_in_buffer@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJPEAXPEB_WAEAV?$buffer@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value_in_buffer(void *,wchar_t const *,appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x18000cecb  mov     ebx, eax
0x18000cecd  test    eax, eax
0x18000cecf  jns     short loc_18000CEED
0x18000ced1  mov     rcx, [rsp+58h+P]; P
0x18000ced6  test    rcx, rcx
0x18000ced9  jz      short loc_18000CEE9
0x18000cedb  xor     edx, edx; Tag
0x18000cedd  call    cs:__imp_ExFreePoolWithTag
0x18000cee4  nop     dword ptr [rax+rax+00h]
0x18000cee9  mov     eax, ebx
0x18000ceeb  jmp     short loc_18000CF62
0x18000ceed  mov     rbx, [rsp+58h+P]
0x18000cef2  cmp     dword ptr [rbx+4], 3
0x18000cef6  jz      short loc_18000CF15
0x18000cef8  test    rbx, rbx
0x18000cefb  jz      short loc_18000CF0E
0x18000cefd  xor     edx, edx; Tag
0x18000ceff  mov     rcx, rbx; P
0x18000cf02  call    cs:__imp_ExFreePoolWithTag
0x18000cf09  nop     dword ptr [rax+rax+00h]
0x18000cf0e  mov     eax, 0C000003Eh
0x18000cf13  jmp     short loc_18000CF62
0x18000cf15  movzx   edi, word ptr [rbx+0Ch]
0x18000cf19  mov     rcx, rsi
0x18000cf1c  mov     ebp, [rbx+8]
0x18000cf1f  mov     edx, edi
0x18000cf21  call    ?resize@?$buffer@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z; appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(ulong)
0x18000cf26  mov     ecx, 0C0000000h
0x18000cf2b  and     eax, ecx
0x18000cf2d  cmp     eax, ecx
0x18000cf2f  jnz     short loc_18000CF38
0x18000cf31  mov     edi, 0C000009Ah
0x18000cf36  jmp     short loc_18000CF4A
0x18000cf38  mov     rcx, [rsi+8]; void *
0x18000cf3c  lea     rdx, [rbx+rbp]; Src
0x18000cf40  mov     r8, rdi; Size
0x18000cf43  call    memmove
0x18000cf48  xor     edi, edi
0x18000cf4a  test    rbx, rbx
0x18000cf4d  jz      short loc_18000CF60
0x18000cf4f  xor     edx, edx; Tag
0x18000cf51  mov     rcx, rbx; P
0x18000cf54  call    cs:__imp_ExFreePoolWithTag
0x18000cf5b  nop     dword ptr [rax+rax+00h]
0x18000cf60  mov     eax, edi
0x18000cf62  add     rsp, 38h
0x18000cf66  pop     rdi
0x18000cf67  pop     rsi
0x18000cf68  pop     rbp
0x18000cf69  pop     rbx
0x18000cf6a  retn
```
