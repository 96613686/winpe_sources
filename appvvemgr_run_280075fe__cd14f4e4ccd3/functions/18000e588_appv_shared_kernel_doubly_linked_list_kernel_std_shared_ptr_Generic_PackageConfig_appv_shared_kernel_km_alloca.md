# appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)

- ea: `0x18000e588`
- end: `0x18000e60a`
- name: `?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `130`
- prototype: ``
- caller_count: `20`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000199c`
- `0x180001d4c`
- `0x1800048d8`
- `0x180004a90`
- `0x1800071a0`
- `0x180009710`
- `0x18000b478`
- `0x18000bfb8`
- `0x18000c31c`
- `0x18000c9a8`
- `0x18000d184`
- `0x18000d250`
- `0x18000f300`
- `0x180011e9c`
- `0x1800134a8`
- `0x180013668`
- `0x180013b78`
- `0x180016474`
- `0x180018270`
- `0x18001a024`

## callees

- `0x18000e588`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000e5a8`
- `ntoskrnl!ExAllocatePool2` at `0x18000e5a8`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *Pool2; // rax
  _QWORD *v5; // r9
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 result; // rax

  Pool2 = (_QWORD *)ExAllocatePool2(256, 32, 1733125462);
  v5 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  *Pool2 = *a2;
  v6 = a2[1];
  v5[1] = v6;
  if ( v6 )
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
  v5[3] = v5;
  v5[2] = v5;
  v7 = *(_QWORD *)(a1 + 24);
  ++*(_DWORD *)a1;
  v5[3] = a1 + 8;
  result = 0;
  v5[2] = v7;
  *(_QWORD *)(v7 + 24) = v5;
  *(_QWORD *)(a1 + 24) = v5;
  return result;
}

```

## disassembly

```asm
0x18000e588  mov     [rsp+arg_0], rbx
0x18000e58d  push    rdi
0x18000e58e  sub     rsp, 20h
0x18000e592  mov     rdi, rdx
0x18000e595  mov     rbx, rcx
0x18000e598  mov     edx, 20h ; ' '
0x18000e59d  mov     ecx, 100h
0x18000e5a2  mov     r8d, 674D6556h
0x18000e5a8  call    cs:__imp_ExAllocatePool2
0x18000e5af  nop     dword ptr [rax+rax+00h]
0x18000e5b4  mov     r9, rax
0x18000e5b7  test    rax, rax
0x18000e5ba  jz      short loc_18000E5F9
0x18000e5bc  mov     r8, [rdi]
0x18000e5bf  mov     [rax], r8
0x18000e5c2  mov     rax, [rdi+8]
0x18000e5c6  mov     [r9+8], rax
0x18000e5ca  test    rax, rax
0x18000e5cd  jz      short loc_18000E5D3
0x18000e5cf  lock inc dword ptr [rax+8]
0x18000e5d3  mov     [r9+18h], r9
0x18000e5d7  lea     rax, [rbx+8]
0x18000e5db  mov     [r9+10h], r9
0x18000e5df  mov     rcx, [rax+10h]
0x18000e5e3  inc     dword ptr [rbx]
0x18000e5e5  mov     [r9+18h], rax
0x18000e5e9  xor     eax, eax
0x18000e5eb  mov     [r9+10h], rcx
0x18000e5ef  mov     [rcx+18h], r9
0x18000e5f3  mov     [rbx+18h], r9
0x18000e5f7  jmp     short loc_18000E5FE
0x18000e5f9  mov     eax, 0C000009Ah
0x18000e5fe  mov     rbx, [rsp+28h+arg_0]
0x18000e603  add     rsp, 20h
0x18000e607  pop     rdi
0x18000e608  retn
```
