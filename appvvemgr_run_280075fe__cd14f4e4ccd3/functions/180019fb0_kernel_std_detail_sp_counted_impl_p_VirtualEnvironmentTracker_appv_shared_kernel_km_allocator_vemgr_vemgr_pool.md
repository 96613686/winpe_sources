# kernel_std::detail::sp_counted_impl_p<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::dispose(void)

- ea: `0x180019fb0`
- end: `0x18001a01c`
- name: `?dispose@?$sp_counted_impl_p@V?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@detail@kernel_std@@UEAAXXZ`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180019fb0`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x180019fdd`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x180019fdd`
- `ntoskrnl!ExFreePoolWithTag` at `0x180019ff8`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001a009`
- `ntoskrnl!ExFreePoolWithTag` at `0x180019ff8`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001a009`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x180019fcc`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x180019fcc`

## pseudocode

```c
void __fastcall kernel_std::detail::sp_counted_impl_p<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::dispose(
        __int64 a1)
{
  struct _RTL_AVL_TABLE **v1; // rbx
  struct _RTL_AVL_TABLE *v2; // rcx
  PVOID v3; // rax
  struct _RTL_AVL_TABLE *v4; // rcx

  v1 = *(struct _RTL_AVL_TABLE ***)(a1 + 16);
  if ( v1 )
  {
    v2 = *v1;
    if ( *v1 )
    {
      while ( 1 )
      {
        v3 = RtlEnumerateGenericTableAvl(v2, 1u);
        v4 = *v1;
        if ( !v3 )
          break;
        RtlDeleteElementGenericTableAvl(v4, v3);
        v2 = *v1;
      }
      if ( v4 )
        ExFreePoolWithTag(v4, 0);
    }
    ExFreePoolWithTag(v1, 0);
  }
}

```

## disassembly

```asm
0x180019fb0  push    rbx
0x180019fb2  sub     rsp, 20h
0x180019fb6  mov     rbx, [rcx+10h]
0x180019fba  test    rbx, rbx
0x180019fbd  jz      short loc_18001A015
0x180019fbf  mov     rcx, [rbx]
0x180019fc2  test    rcx, rcx
0x180019fc5  jz      short loc_18001A004
0x180019fc7  jmp     short loc_180019FDB
0x180019fc9  mov     rdx, rax; Buffer
0x180019fcc  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180019fd3  nop     dword ptr [rax+rax+00h]
0x180019fd8  mov     rcx, [rbx]; Table
0x180019fdb  mov     dl, 1; Restart
0x180019fdd  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180019fe4  nop     dword ptr [rax+rax+00h]
0x180019fe9  mov     rcx, [rbx]; P
0x180019fec  test    rax, rax
0x180019fef  jnz     short loc_180019FC9
0x180019ff1  test    rcx, rcx
0x180019ff4  jz      short loc_18001A004
0x180019ff6  xor     edx, edx; Tag
0x180019ff8  call    cs:__imp_ExFreePoolWithTag
0x180019fff  nop     dword ptr [rax+rax+00h]
0x18001a004  xor     edx, edx; Tag
0x18001a006  mov     rcx, rbx; P
0x18001a009  call    cs:__imp_ExFreePoolWithTag
0x18001a010  nop     dword ptr [rax+rax+00h]
0x18001a015  add     rsp, 20h
0x18001a019  pop     rbx
0x18001a01a  retn
```
