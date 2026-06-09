# ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindUser(wchar_t const *,wchar_t const *,wchar_t const *,kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)

- ea: `0x180007d54`
- end: `0x180007e0a`
- name: `?FindUser@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJPEB_W00AEAV?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `182`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180001bec`
- `0x1800021d0`

## callees

- `0x180007d54`
- `0x18000e960`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x180007ddb`
- `ntoskrnl!ExReleaseResourceLite` at `0x180007ddb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180007de7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180007de7`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180007d9e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180007d9e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180007d85`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180007d85`

## pseudocode

```c
__int64 __fastcall ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindUser(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  bool v9; // di
  unsigned int v10; // esi
  struct _ERESOURCE *v11; // rcx

  if ( !a2 || !a4 )
    return 3221225485LL;
  v9 = 0;
  if ( *(_QWORD *)(a1 + 88) )
  {
    KeEnterCriticalRegion();
    v9 = ExAcquireResourceSharedLite(*(PERESOURCE *)(a1 + 88), 1u) == 1;
  }
  v10 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve(
          a2,
          a3,
          a4,
          a5);
  if ( v9 )
  {
    v11 = *(struct _ERESOURCE **)(a1 + 88);
    if ( v11 )
    {
      ExReleaseResourceLite(v11);
      KeLeaveCriticalRegion();
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180007d54  push    rbx
0x180007d56  push    rbp
0x180007d57  push    rsi
0x180007d58  push    rdi
0x180007d59  push    r14
0x180007d5b  push    r15
0x180007d5d  sub     rsp, 28h
0x180007d61  mov     rsi, r9
0x180007d64  mov     r14, r8
0x180007d67  mov     rbp, rdx
0x180007d6a  mov     rbx, rcx
0x180007d6d  test    rdx, rdx
0x180007d70  jz      loc_180007DF7
0x180007d76  test    r9, r9
0x180007d79  jz      short loc_180007DF7
0x180007d7b  xor     dil, dil
0x180007d7e  cmp     qword ptr [rcx+58h], 0
0x180007d83  jz      short loc_180007DB5
0x180007d85  call    cs:__imp_KeEnterCriticalRegion
0x180007d8c  nop     dword ptr [rax+rax+00h]
0x180007d91  mov     rcx, [rbx+58h]; Resource
0x180007d95  mov     r15d, 1
0x180007d9b  mov     dl, r15b; Wait
0x180007d9e  call    cs:__imp_ExAcquireResourceSharedLite
0x180007da5  nop     dword ptr [rax+rax+00h]
0x180007daa  cmp     al, r15b
0x180007dad  movzx   edi, dil
0x180007db1  cmovz   edi, r15d
0x180007db5  mov     r9, [rsp+58h+arg_20]
0x180007dbd  mov     r8, rsi
0x180007dc0  mov     rdx, r14
0x180007dc3  mov     rcx, rbp
0x180007dc6  call    ?retrieve@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_W00AEAV?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve(wchar_t const *,wchar_t const *,wchar_t const *,kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x180007dcb  mov     esi, eax
0x180007dcd  test    dil, dil
0x180007dd0  jz      short loc_180007DF3
0x180007dd2  mov     rcx, [rbx+58h]; Resource
0x180007dd6  test    rcx, rcx
0x180007dd9  jz      short loc_180007DF3
0x180007ddb  call    cs:__imp_ExReleaseResourceLite
0x180007de2  nop     dword ptr [rax+rax+00h]
0x180007de7  call    cs:__imp_KeLeaveCriticalRegion
0x180007dee  nop     dword ptr [rax+rax+00h]
0x180007df3  mov     eax, esi
0x180007df5  jmp     short loc_180007DFC
0x180007df7  mov     eax, 0C000000Dh
0x180007dfc  add     rsp, 28h
0x180007e00  pop     r15
0x180007e02  pop     r14
0x180007e04  pop     rdi
0x180007e05  pop     rsi
0x180007e06  pop     rbp
0x180007e07  pop     rbx
0x180007e08  retn
```
