# Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::init(wchar_t const *,uint)

- ea: `0x18000d37c`
- end: `0x18000d426`
- name: `?init@?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA_NPEB_WI@Z`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000199c`
- `0x1800110e8`

## callees

- `0x180003f50`
- `0x18000a9e4`
- `0x18000d37c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000d3a8`
- `ntoskrnl!ExAllocatePool2` at `0x18000d3a8`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000d3c9`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000d3c9`

## pseudocode

```c
bool __fastcall Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::init(
        __int64 a1,
        __int64 a2,
        int a3)
{
  __int64 Pool2; // rax
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // r8

  if ( !a2 )
    return 0;
  *(_DWORD *)(a1 + 56) = a3;
  Pool2 = ExAllocatePool2(256, 32, 1733125462);
  v6 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)Pool2 = 0;
    *(_QWORD *)(Pool2 + 8) = 0;
    RtlInitUnicodeString((PUNICODE_STRING)(Pool2 + 16), 0);
  }
  else
  {
    v6 = 0;
  }
  kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
    a1,
    v6);
  if ( !*(_QWORD *)a1 )
    return 0;
  v7 = *(_QWORD *)(a1 + 8);
  if ( !v7 || !*(_DWORD *)(v7 + 8) )
    return 0;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)(a2 + 2 * v8) );
  return (int)appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
                *(_QWORD *)a1,
                a2,
                v8) >= 0;
}

```

## disassembly

```asm
0x18000d37c  push    rbx
0x18000d37e  push    rbp
0x18000d37f  push    rsi
0x18000d380  push    rdi
0x18000d381  sub     rsp, 28h
0x18000d385  xor     ebp, ebp
0x18000d387  mov     rsi, rdx
0x18000d38a  mov     rdi, rcx
0x18000d38d  test    rdx, rdx
0x18000d390  jz      loc_18000D41A
0x18000d396  mov     [rcx+38h], r8d
0x18000d39a  lea     edx, [rbp+20h]
0x18000d39d  mov     ecx, 100h
0x18000d3a2  mov     r8d, 674D6556h
0x18000d3a8  call    cs:__imp_ExAllocatePool2
0x18000d3af  nop     dword ptr [rax+rax+00h]
0x18000d3b4  mov     rbx, rax
0x18000d3b7  test    rax, rax
0x18000d3ba  jz      short loc_18000D3D7
0x18000d3bc  lea     rcx, [rax+10h]; DestinationString
0x18000d3c0  mov     [rax], rbp
0x18000d3c3  xor     edx, edx; SourceString
0x18000d3c5  mov     [rax+8], rbp
0x18000d3c9  call    cs:__imp_RtlInitUnicodeString
0x18000d3d0  nop     dword ptr [rax+rax+00h]
0x18000d3d5  jmp     short loc_18000D3DA
0x18000d3d7  mov     rbx, rbp
0x18000d3da  mov     rdx, rbx
0x18000d3dd  mov     rcx, rdi
0x18000d3e0  call    ??$reset@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@QEAAXPEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::reset<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> *)
0x18000d3e5  cmp     [rdi], rbp
0x18000d3e8  jz      short loc_18000D41A
0x18000d3ea  mov     rax, [rdi+8]
0x18000d3ee  test    rax, rax
0x18000d3f1  jz      short loc_18000D41A
0x18000d3f3  mov     eax, [rax+8]
0x18000d3f6  test    eax, eax
0x18000d3f8  jz      short loc_18000D41A
0x18000d3fa  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000d3fe  inc     r8
0x18000d401  cmp     [rsi+r8*2], bp
0x18000d406  jnz     short loc_18000D3FE
0x18000d408  mov     rcx, [rdi]
0x18000d40b  mov     rdx, rsi
0x18000d40e  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x18000d413  shr     eax, 1Fh
0x18000d416  xor     al, 1
0x18000d418  jmp     short loc_18000D41C
0x18000d41a  xor     al, al
0x18000d41c  add     rsp, 28h
0x18000d420  pop     rdi
0x18000d421  pop     rsi
0x18000d422  pop     rbp
0x18000d423  pop     rbx
0x18000d424  retn
```
