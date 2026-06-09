# registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,ulong &)

- ea: `0x18000ce10`
- end: `0x18000ce95`
- name: `?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAK@Z`
- size: `133`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002b48`
- `0x180006eec`
- `0x18000d72c`
- `0x18000e960`
- `0x18000ef74`
- `0x18000f300`
- `0x180013d4c`
- `0x180013e14`
- `0x180015008`
- `0x180016f64`
- `0x18001a79c`

## callees

- `0x18000ce10`
- `0x18000d054`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18000ce4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000ce78`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000ce4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000ce78`

## pseudocode

```c
__int64 __fastcall registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(
        void *a1,
        __int64 a2,
        _DWORD *a3)
{
  int value_in_buffer; // ebx

  value_in_buffer = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value_in_buffer(a1);
  if ( value_in_buffer < 0 )
    return (unsigned int)value_in_buffer;
  if ( MEMORY[4] == 4 && MEMORY[0xC] >= 4u )
  {
    *a3 = *(unsigned __int8 *)MEMORY[8];
    return (unsigned int)value_in_buffer;
  }
  return 3221225534LL;
}

```

## disassembly

```asm
0x18000ce10  mov     rax, rsp
0x18000ce13  mov     [rax+8], rbx
0x18000ce17  push    rdi
0x18000ce18  sub     rsp, 30h
0x18000ce1c  mov     rdi, r8
0x18000ce1f  mov     qword ptr [rax-18h], 0
0x18000ce27  lea     r8, [rax-18h]
0x18000ce2b  mov     qword ptr [rax-10h], 0
0x18000ce33  call    ?get_value_in_buffer@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJPEAXPEB_WAEAV?$buffer@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value_in_buffer(void *,wchar_t const *,appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)
0x18000ce38  mov     rcx, [rsp+38h+P]; P
0x18000ce3d  mov     ebx, eax
0x18000ce3f  test    eax, eax
0x18000ce41  jns     short loc_18000CE5A
0x18000ce43  test    rcx, rcx
0x18000ce46  jz      short loc_18000CE56
0x18000ce48  xor     edx, edx; Tag
0x18000ce4a  call    cs:__imp_ExFreePoolWithTag
0x18000ce51  nop     dword ptr [rax+rax+00h]
0x18000ce56  mov     eax, ebx
0x18000ce58  jmp     short loc_18000CE89
0x18000ce5a  cmp     dword ptr [rcx+4], 4
0x18000ce5e  jnz     short loc_18000CE71
0x18000ce60  cmp     dword ptr [rcx+0Ch], 4
0x18000ce64  jb      short loc_18000CE71
0x18000ce66  mov     eax, [rcx+8]
0x18000ce69  movzx   edx, byte ptr [rax+rcx]
0x18000ce6d  mov     [rdi], edx
0x18000ce6f  jmp     short loc_18000CE43
0x18000ce71  test    rcx, rcx
0x18000ce74  jz      short loc_18000CE84
0x18000ce76  xor     edx, edx; Tag
0x18000ce78  call    cs:__imp_ExFreePoolWithTag
0x18000ce7f  nop     dword ptr [rax+rax+00h]
0x18000ce84  mov     eax, 0C000003Eh
0x18000ce89  mov     rbx, [rsp+38h+arg_0]
0x18000ce8e  add     rsp, 30h
0x18000ce92  pop     rdi
0x18000ce93  retn
```
