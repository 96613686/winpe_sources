# appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::find_first_element<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_predecate>(VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_predecate &)

- ea: `0x180003034`
- end: `0x1800030eb`
- name: `??$find_first_element@Ufind_predecate@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEBA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@123@AEAUfind_predecate@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z`
- size: `183`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800030f4`
- `0x18000e6c0`
- `0x180015978`

## callees

- `0x180003034`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1800030bb`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800030bb`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::find_first_element<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_predecate>(
        __int64 a1,
        __int64 a2,
        PCUNICODE_STRING *a3)
{
  __int64 **v3; // rsi
  __int64 **v4; // r9
  __int64 *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rcx
  const UNICODE_STRING *v10; // rcx

  *(_QWORD *)a2 = 0;
  v3 = (__int64 **)(a1 + 8);
  v4 = *(__int64 ***)(a1 + 32);
  for ( *(_QWORD *)a2 = v4; v4 != v3; *(_QWORD *)a2 = v4 )
  {
    if ( *a3 )
    {
      if ( *v4 )
      {
        v7 = v4[1];
        if ( v7 )
        {
          if ( *((_DWORD *)v7 + 2) )
          {
            if ( **v4 )
            {
              v8 = (*v4)[1];
              if ( v8 )
              {
                if ( *(_DWORD *)(v8 + 8) )
                {
                  v9 = **v4;
                  v10 = (const UNICODE_STRING *)(*(_DWORD *)(v9 + 40) ? **(_QWORD **)(v9 + 72) + 64LL : v9 + 152);
                  if ( !RtlCompareUnicodeString(v10, *a3, 1u) )
                    break;
                }
              }
            }
          }
        }
      }
    }
    v4 = *(__int64 ***)(*(_QWORD *)a2 + 24LL);
  }
  return a2;
}

```

## disassembly

```asm
0x180003034  mov     [rsp+arg_0], rbx
0x180003039  mov     [rsp+arg_8], rsi
0x18000303e  push    rdi
0x18000303f  sub     rsp, 20h
0x180003043  mov     qword ptr [rdx], 0
0x18000304a  lea     rsi, [rcx+8]
0x18000304e  mov     r9, [rcx+20h]
0x180003052  mov     rdi, r8
0x180003055  mov     [rdx], r9
0x180003058  mov     rbx, rdx
0x18000305b  cmp     r9, rsi
0x18000305e  jz      short loc_1800030D7
0x180003060  cmp     qword ptr [rdi], 0
0x180003064  jz      short loc_1800030CB
0x180003066  cmp     qword ptr [r9], 0
0x18000306a  jz      short loc_1800030CB
0x18000306c  mov     rax, [r9+8]
0x180003070  test    rax, rax
0x180003073  jz      short loc_1800030CB
0x180003075  mov     eax, [rax+8]
0x180003078  test    eax, eax
0x18000307a  jz      short loc_1800030CB
0x18000307c  mov     rax, [r9]
0x18000307f  cmp     qword ptr [rax], 0
0x180003083  jz      short loc_1800030CB
0x180003085  mov     rax, [rax+8]
0x180003089  test    rax, rax
0x18000308c  jz      short loc_1800030CB
0x18000308e  mov     eax, [rax+8]
0x180003091  test    eax, eax
0x180003093  jz      short loc_1800030CB
0x180003095  mov     rax, [r9]
0x180003098  mov     rcx, [rax]
0x18000309b  cmp     dword ptr [rcx+28h], 0
0x18000309f  jz      short loc_1800030AE
0x1800030a1  mov     rax, [rcx+48h]
0x1800030a5  mov     rcx, [rax]
0x1800030a8  add     rcx, 40h ; '@'
0x1800030ac  jmp     short loc_1800030B5
0x1800030ae  add     rcx, 98h; String1
0x1800030b5  mov     rdx, [rdi]; String2
0x1800030b8  mov     r8b, 1; CaseInSensitive
0x1800030bb  call    cs:__imp_RtlCompareUnicodeString
0x1800030c2  nop     dword ptr [rax+rax+00h]
0x1800030c7  test    eax, eax
0x1800030c9  jz      short loc_1800030D7
0x1800030cb  mov     rax, [rbx]
0x1800030ce  mov     r9, [rax+18h]
0x1800030d2  mov     [rbx], r9
0x1800030d5  jmp     short loc_18000305B
0x1800030d7  mov     rsi, [rsp+28h+arg_8]
0x1800030dc  mov     rax, rbx
0x1800030df  mov     rbx, [rsp+28h+arg_0]
0x1800030e4  add     rsp, 20h
0x1800030e8  pop     rdi
0x1800030e9  retn
```
