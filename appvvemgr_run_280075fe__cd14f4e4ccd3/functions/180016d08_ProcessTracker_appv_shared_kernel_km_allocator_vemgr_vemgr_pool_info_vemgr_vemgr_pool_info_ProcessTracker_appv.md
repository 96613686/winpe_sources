# ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::~ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(void)

- ea: `0x180016d08`
- end: `0x180016d89`
- name: `??1?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA@XZ`
- size: `129`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800168b0`
- `0x180019ef0`

## callees

- `0x180016d08`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x180016d5b`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x180016d5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x180016d31`
- `ntoskrnl!ExFreePoolWithTag` at `0x180016d76`
- `ntoskrnl!ExFreePoolWithTag` at `0x180016d31`
- `ntoskrnl!ExFreePoolWithTag` at `0x180016d76`
- `ntoskrnl!ExDeleteResourceLite` at `0x180016d1a`
- `ntoskrnl!ExDeleteResourceLite` at `0x180016d1a`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x180016d4a`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x180016d4a`

## pseudocode

```c
void __fastcall ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::~ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(
        __int64 a1)
{
  struct _ERESOURCE *v2; // rcx
  void *v3; // rcx
  struct _RTL_AVL_TABLE *v4; // rcx
  PVOID v5; // rax
  struct _RTL_AVL_TABLE *v6; // rcx

  v2 = *(struct _ERESOURCE **)(a1 + 16);
  if ( v2 )
  {
    ExDeleteResourceLite(v2);
    v3 = *(void **)(a1 + 16);
    if ( v3 )
      ExFreePoolWithTag(v3, 0);
  }
  v4 = *(struct _RTL_AVL_TABLE **)a1;
  if ( *(_QWORD *)a1 )
  {
    while ( 1 )
    {
      v5 = RtlEnumerateGenericTableAvl(v4, 1u);
      v6 = *(struct _RTL_AVL_TABLE **)a1;
      if ( !v5 )
        break;
      RtlDeleteElementGenericTableAvl(v6, v5);
      v4 = *(struct _RTL_AVL_TABLE **)a1;
    }
    if ( v6 )
      ExFreePoolWithTag(v6, 0);
  }
}

```

## disassembly

```asm
0x180016d08  push    rbx
0x180016d0a  sub     rsp, 20h
0x180016d0e  mov     rbx, rcx
0x180016d11  mov     rcx, [rcx+10h]; Resource
0x180016d15  test    rcx, rcx
0x180016d18  jz      short loc_180016D3D
0x180016d1a  call    cs:__imp_ExDeleteResourceLite
0x180016d21  nop     dword ptr [rax+rax+00h]
0x180016d26  mov     rcx, [rbx+10h]; P
0x180016d2a  test    rcx, rcx
0x180016d2d  jz      short loc_180016D3D
0x180016d2f  xor     edx, edx; Tag
0x180016d31  call    cs:__imp_ExFreePoolWithTag
0x180016d38  nop     dword ptr [rax+rax+00h]
0x180016d3d  mov     rcx, [rbx]
0x180016d40  test    rcx, rcx
0x180016d43  jz      short loc_180016D82
0x180016d45  jmp     short loc_180016D59
0x180016d47  mov     rdx, rax; Buffer
0x180016d4a  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180016d51  nop     dword ptr [rax+rax+00h]
0x180016d56  mov     rcx, [rbx]; Table
0x180016d59  mov     dl, 1; Restart
0x180016d5b  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180016d62  nop     dword ptr [rax+rax+00h]
0x180016d67  mov     rcx, [rbx]; P
0x180016d6a  test    rax, rax
0x180016d6d  jnz     short loc_180016D47
0x180016d6f  test    rcx, rcx
0x180016d72  jz      short loc_180016D82
0x180016d74  xor     edx, edx; Tag
0x180016d76  call    cs:__imp_ExFreePoolWithTag
0x180016d7d  nop     dword ptr [rax+rax+00h]
0x180016d82  add     rsp, 20h
0x180016d86  pop     rbx
0x180016d87  retn
```
