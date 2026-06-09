# appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::find_first_element<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &)

- ea: `0x180002e94`
- end: `0x180002f1a`
- name: `??$find_first_element@U?$find_by_group_moniker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEBA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@123@AEAU?$find_by_group_moniker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z`
- size: `134`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001598`
- `0x18000199c`
- `0x1800101e4`
- `0x180010374`
- `0x180012004`
- `0x180012264`

## callees

- `0x180002e94`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x180002eea`
- `ntoskrnl!RtlCompareUnicodeString` at `0x180002eea`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::find_first_element<ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_by_group_moniker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
        __int64 a1,
        __int64 a2,
        const UNICODE_STRING **a3)
{
  __int64 v3; // rdi
  __int64 v4; // r9
  __int64 v7; // rax

  *(_QWORD *)a2 = 0;
  v3 = a1 + 8;
  v4 = *(_QWORD *)(a1 + 32);
  for ( *(_QWORD *)a2 = v4; v4 != v3; *(_QWORD *)a2 = v4 )
  {
    if ( *(_QWORD *)v4 )
    {
      v7 = *(_QWORD *)(v4 + 8);
      if ( v7 )
      {
        if ( *(_DWORD *)(v7 + 8) && !RtlCompareUnicodeString((PCUNICODE_STRING)(**(_QWORD **)v4 + 16LL), *a3 + 1, 1u) )
          break;
      }
    }
    v4 = *(_QWORD *)(*(_QWORD *)a2 + 24LL);
  }
  return a2;
}

```

## disassembly

```asm
0x180002e94  mov     [rsp+arg_0], rbx
0x180002e99  mov     [rsp+arg_8], rsi
0x180002e9e  push    rdi
0x180002e9f  sub     rsp, 20h
0x180002ea3  mov     qword ptr [rdx], 0
0x180002eaa  lea     rdi, [rcx+8]
0x180002eae  mov     r9, [rcx+20h]
0x180002eb2  mov     rsi, r8
0x180002eb5  mov     [rdx], r9
0x180002eb8  mov     rbx, rdx
0x180002ebb  cmp     r9, rdi
0x180002ebe  jz      short loc_180002F06
0x180002ec0  cmp     qword ptr [r9], 0
0x180002ec4  jz      short loc_180002EFA
0x180002ec6  mov     rax, [r9+8]
0x180002eca  test    rax, rax
0x180002ecd  jz      short loc_180002EFA
0x180002ecf  mov     eax, [rax+8]
0x180002ed2  test    eax, eax
0x180002ed4  jz      short loc_180002EFA
0x180002ed6  mov     rax, [r9]
0x180002ed9  mov     r8b, 1; CaseInSensitive
0x180002edc  mov     rdx, [rsi]
0x180002edf  add     rdx, 10h; String2
0x180002ee3  mov     rcx, [rax]
0x180002ee6  add     rcx, 10h; String1
0x180002eea  call    cs:__imp_RtlCompareUnicodeString
0x180002ef1  nop     dword ptr [rax+rax+00h]
0x180002ef6  test    eax, eax
0x180002ef8  jz      short loc_180002F06
0x180002efa  mov     rax, [rbx]
0x180002efd  mov     r9, [rax+18h]
0x180002f01  mov     [rbx], r9
0x180002f04  jmp     short loc_180002EBB
0x180002f06  mov     rsi, [rsp+28h+arg_8]
0x180002f0b  mov     rax, rbx
0x180002f0e  mov     rbx, [rsp+28h+arg_0]
0x180002f13  add     rsp, 20h
0x180002f17  pop     rdi
0x180002f18  retn
```
