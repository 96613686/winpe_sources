# Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(void)

- ea: `0x1800046d4`
- end: `0x18000475c`
- name: `??0?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA@XZ`
- size: `136`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180001598`
- `0x180001788`
- `0x180010b50`
- `0x18001a79c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180004702`
- `ntoskrnl!RtlInitUnicodeString` at `0x180004702`

## pseudocode

```c
__int64 __fastcall Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(
        __int64 a1)
{
  __int64 result; // rax

  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  RtlInitUnicodeString((PUNICODE_STRING)(a1 + 32), 0);
  *(_DWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 88) = a1 + 64;
  *(_QWORD *)(a1 + 80) = a1 + 64;
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 128) = a1 + 104;
  *(_QWORD *)(a1 + 120) = a1 + 104;
  result = a1;
  *(_DWORD *)(a1 + 96) = 0;
  return result;
}

```

## disassembly

```asm
0x1800046d4  push    rbx
0x1800046d6  sub     rsp, 20h
0x1800046da  mov     rbx, rcx
0x1800046dd  mov     qword ptr [rcx], 0
0x1800046e4  mov     qword ptr [rcx+8], 0
0x1800046ec  xor     edx, edx; SourceString
0x1800046ee  mov     qword ptr [rcx+10h], 0
0x1800046f6  mov     qword ptr [rcx+18h], 0
0x1800046fe  add     rcx, 20h ; ' '; DestinationString
0x180004702  call    cs:__imp_RtlInitUnicodeString
0x180004709  nop     dword ptr [rax+rax+00h]
0x18000470e  lea     rax, [rbx+40h]
0x180004712  mov     dword ptr [rbx+38h], 0
0x180004719  mov     qword ptr [rax], 0
0x180004720  mov     qword ptr [rax+8], 0
0x180004728  mov     [rax+18h], rax
0x18000472c  mov     [rax+10h], rax
0x180004730  lea     rax, [rbx+68h]
0x180004734  mov     qword ptr [rax], 0
0x18000473b  mov     qword ptr [rax+8], 0
0x180004743  mov     [rax+18h], rax
0x180004747  mov     [rax+10h], rax
0x18000474b  mov     rax, rbx
0x18000474e  mov     dword ptr [rbx+60h], 0
0x180004755  add     rsp, 20h
0x180004759  pop     rbx
0x18000475a  retn
```
