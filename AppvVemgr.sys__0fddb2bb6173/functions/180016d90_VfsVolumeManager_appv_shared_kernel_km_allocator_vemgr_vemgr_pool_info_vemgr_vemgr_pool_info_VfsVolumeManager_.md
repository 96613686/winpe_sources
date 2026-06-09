# VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::~VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(void)

- ea: `0x180016d90`
- end: `0x180016e31`
- name: `??1?$VfsVolumeManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA@XZ`
- size: `161`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180017334`
- `0x180019f30`

## callees

- `0x180016d90`

## import_xrefs

- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x180016de5`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x180016de5`
- `ntoskrnl!ExFreePoolWithTag` at `0x180016db9`
- `ntoskrnl!ExFreePoolWithTag` at `0x180016e01`
- `ntoskrnl!ExFreePoolWithTag` at `0x180016e17`
- `ntoskrnl!ExFreePoolWithTag` at `0x180016db9`
- `ntoskrnl!ExFreePoolWithTag` at `0x180016e01`
- `ntoskrnl!ExFreePoolWithTag` at `0x180016e17`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x180016dd3`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x180016dd3`
- `FLTMGR!FltObjectDereference` at `0x180016da2`
- `FLTMGR!FltObjectDereference` at `0x180016da2`

## pseudocode

```c
void __fastcall VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::~VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(
        __int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx
  struct _RTL_AVL_TABLE *v4; // rcx
  PVOID v5; // rax
  struct _RTL_AVL_TABLE *v6; // rcx

  v2 = *(void **)(a1 + 24);
  if ( v2 )
    FltObjectDereference(v2);
  v3 = *(void **)(a1 + 40);
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  v4 = *(struct _RTL_AVL_TABLE **)(a1 + 16);
  if ( v4 )
  {
    while ( 1 )
    {
      v5 = RtlEnumerateGenericTableAvl(v4, 1u);
      v6 = *(struct _RTL_AVL_TABLE **)(a1 + 16);
      if ( !v5 )
        break;
      RtlDeleteElementGenericTableAvl(v6, v5);
      v4 = *(struct _RTL_AVL_TABLE **)(a1 + 16);
    }
    if ( v6 )
      ExFreePoolWithTag(v6, 0);
  }
  if ( *(_QWORD *)a1 )
  {
    ExFreePoolWithTag(*(PVOID *)a1, 0);
    *(_QWORD *)a1 = 0;
  }
}

```

## disassembly

```asm
0x180016d90  push    rbx
0x180016d92  sub     rsp, 20h
0x180016d96  mov     rbx, rcx
0x180016d99  mov     rcx, [rcx+18h]; FltObject
0x180016d9d  test    rcx, rcx
0x180016da0  jz      short loc_180016DAE
0x180016da2  call    cs:__imp_FltObjectDereference
0x180016da9  nop     dword ptr [rax+rax+00h]
0x180016dae  mov     rcx, [rbx+28h]; P
0x180016db2  test    rcx, rcx
0x180016db5  jz      short loc_180016DC5
0x180016db7  xor     edx, edx; Tag
0x180016db9  call    cs:__imp_ExFreePoolWithTag
0x180016dc0  nop     dword ptr [rax+rax+00h]
0x180016dc5  mov     rcx, [rbx+10h]
0x180016dc9  test    rcx, rcx
0x180016dcc  jz      short loc_180016E0D
0x180016dce  jmp     short loc_180016DE3
0x180016dd0  mov     rdx, rax; Buffer
0x180016dd3  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180016dda  nop     dword ptr [rax+rax+00h]
0x180016ddf  mov     rcx, [rbx+10h]; Table
0x180016de3  mov     dl, 1; Restart
0x180016de5  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180016dec  nop     dword ptr [rax+rax+00h]
0x180016df1  mov     rcx, [rbx+10h]; P
0x180016df5  test    rax, rax
0x180016df8  jnz     short loc_180016DD0
0x180016dfa  test    rcx, rcx
0x180016dfd  jz      short loc_180016E0D
0x180016dff  xor     edx, edx; Tag
0x180016e01  call    cs:__imp_ExFreePoolWithTag
0x180016e08  nop     dword ptr [rax+rax+00h]
0x180016e0d  mov     rcx, [rbx]; P
0x180016e10  test    rcx, rcx
0x180016e13  jz      short loc_180016E2A
0x180016e15  xor     edx, edx; Tag
0x180016e17  call    cs:__imp_ExFreePoolWithTag
0x180016e1e  nop     dword ptr [rax+rax+00h]
0x180016e23  mov     qword ptr [rbx], 0
0x180016e2a  add     rsp, 20h
0x180016e2e  pop     rbx
0x180016e2f  retn
```
