# ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::add_package_group_to_package_configuration(kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)

- ea: `0x180013668`
- end: `0x180013711`
- name: `?add_package_group_to_package_configuration@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEBV?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012264`
- `0x180018270`

## callees

- `0x18000e588`
- `0x180013668`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1800136c6`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800136c6`

## pseudocode

```c
__int64 __fastcall ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::add_package_group_to_package_configuration(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbx
  __int64 v3; // r12
  unsigned int v5; // ebp
  __int64 v6; // r14
  __int64 v7; // rdi
  const UNICODE_STRING *v8; // rsi
  __int64 i; // rcx
  __int64 v10; // rax
  __int64 result; // rax

  v2 = *(_QWORD *)(a1 + 32);
  v3 = a1 + 8;
  v5 = 0;
  while ( v2 != v3 )
  {
    v6 = *(_QWORD *)a2 + 24LL;
    v7 = *(_QWORD *)(*(_QWORD *)a2 + 48LL);
    v8 = **(const UNICODE_STRING ***)v2;
    for ( i = v7; i != v6; v7 = i )
    {
      if ( *(_QWORD *)i )
      {
        v10 = *(_QWORD *)(i + 8);
        if ( v10 )
        {
          if ( *(_DWORD *)(v10 + 8) && !RtlCompareUnicodeString((PCUNICODE_STRING)(*(_QWORD *)i + 16LL), v8 + 1, 1u) )
            break;
        }
      }
      i = *(_QWORD *)(v7 + 24);
    }
    if ( v7 != v6 )
    {
      result = appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
                 *(_QWORD *)v2 + 96LL,
                 a2);
      v5 = result;
      if ( (int)result < 0 )
        return result;
    }
    v2 = *(_QWORD *)(v2 + 24);
  }
  return v5;
}

```

## disassembly

```asm
0x180013668  push    rbx
0x18001366a  push    rbp
0x18001366b  push    rsi
0x18001366c  push    rdi
0x18001366d  push    r12
0x18001366f  push    r14
0x180013671  push    r15
0x180013673  sub     rsp, 20h
0x180013677  mov     rbx, [rcx+20h]
0x18001367b  lea     r12, [rcx+8]
0x18001367f  mov     r15, rdx
0x180013682  xor     ebp, ebp
0x180013684  cmp     rbx, r12
0x180013687  jz      short loc_1800136FF
0x180013689  mov     rdi, [r15]
0x18001368c  mov     rsi, [rbx]
0x18001368f  lea     r14, [rdi+18h]
0x180013693  mov     rdi, [rdi+30h]
0x180013697  mov     rsi, [rsi]
0x18001369a  mov     rcx, rdi
0x18001369d  cmp     rcx, r14
0x1800136a0  jz      short loc_1800136DF
0x1800136a2  cmp     qword ptr [rcx], 0
0x1800136a6  jz      short loc_1800136D6
0x1800136a8  mov     rax, [rcx+8]
0x1800136ac  test    rax, rax
0x1800136af  jz      short loc_1800136D6
0x1800136b1  mov     eax, [rax+8]
0x1800136b4  test    eax, eax
0x1800136b6  jz      short loc_1800136D6
0x1800136b8  mov     rcx, [rcx]
0x1800136bb  lea     rdx, [rsi+10h]; String2
0x1800136bf  add     rcx, 10h; String1
0x1800136c3  mov     r8b, 1; CaseInSensitive
0x1800136c6  call    cs:__imp_RtlCompareUnicodeString
0x1800136cd  nop     dword ptr [rax+rax+00h]
0x1800136d2  test    eax, eax
0x1800136d4  jz      short loc_1800136DF
0x1800136d6  mov     rcx, [rdi+18h]
0x1800136da  mov     rdi, rcx
0x1800136dd  jmp     short loc_18001369D
0x1800136df  cmp     rdi, r14
0x1800136e2  jz      short loc_1800136F9
0x1800136e4  mov     rcx, [rbx]
0x1800136e7  mov     rdx, r15
0x1800136ea  add     rcx, 60h ; '`'
0x1800136ee  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x1800136f3  mov     ebp, eax
0x1800136f5  test    eax, eax
0x1800136f7  js      short loc_180013701
0x1800136f9  mov     rbx, [rbx+18h]
0x1800136fd  jmp     short loc_180013684
0x1800136ff  mov     eax, ebp
0x180013701  add     rsp, 20h
0x180013705  pop     r15
0x180013707  pop     r14
0x180013709  pop     r12
0x18001370b  pop     rdi
0x18001370c  pop     rsi
0x18001370d  pop     rbp
0x18001370e  pop     rbx
0x18001370f  retn
```
