# appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)

- ea: `0x180005178`
- end: `0x1800051fa`
- name: `??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ`
- size: `130`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `26`
- callee_count: `3`
- tags: ``

## callers

- `0x1800010f4`
- `0x18000129c`
- `0x180001f78`
- `0x180004d50`
- `0x180004e20`
- `0x180004fc8`
- `0x1800071a0`
- `0x18000a218`
- `0x18000b478`
- `0x18000bc10`
- `0x18000bd30`
- `0x18000be30`
- `0x18000f300`
- `0x180011538`
- `0x180013e14`
- `0x180013f40`
- `0x180016570`
- `0x180016e38`
- `0x180018270`
- `0x180019014`
- `0x180019b1c`
- `0x180019cfc`
- `0x180019e50`
- `0x18001a024`
- `0x18001a1f4`
- `0x18001a594`

## callees

- `0x180005178`
- `0x18000c5f4`
- `0x18001bb30`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(
        __int64 a1)
{
  __int64 result; // rax
  __int64 v2; // rdi
  volatile signed __int32 *v4; // rbx
  signed __int32 v5; // eax
  bool v6; // zf
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  char v8; // [rsp+38h] [rbp+10h] BYREF

  result = *(_QWORD *)(a1 + 32);
  v2 = a1 + 8;
  while ( result != v2 )
  {
    v7 = result;
    result = *(_QWORD *)appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(
                          a1,
                          &v8,
                          &v7);
  }
  v4 = *(volatile signed __int32 **)(a1 + 16);
  if ( v4 )
  {
    v5 = _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF);
    v6 = v5 == 1;
    result = (unsigned int)(v5 - 1);
    if ( v6 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
      result = (unsigned int)_InterlockedDecrement(v4 + 3);
      if ( !(_DWORD)result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 16LL))(v4);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005178  mov     [rsp+arg_10], rbx
0x18000517d  push    rdi
0x18000517e  sub     rsp, 20h
0x180005182  mov     rax, [rcx+20h]
0x180005186  lea     rdi, [rcx+8]
0x18000518a  mov     rbx, rcx
0x18000518d  cmp     rax, rdi
0x180005190  jz      short loc_1800051AE
0x180005192  lea     r8, [rsp+28h+arg_0]
0x180005197  mov     [rsp+28h+arg_0], rax
0x18000519c  lea     rdx, [rsp+28h+arg_8]
0x1800051a1  mov     rcx, rbx
0x1800051a4  call    ?erase@?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@234@V5234@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(appv::shared::kernel::bidirectional_list_iterator<appv::shared::kernel::dl_node_t<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>>>)
0x1800051a9  mov     rax, [rax]
0x1800051ac  jmp     short loc_18000518D
0x1800051ae  mov     rbx, [rbx+10h]
0x1800051b2  test    rbx, rbx
0x1800051b5  jz      short loc_1800051EE
0x1800051b7  or      edi, 0FFFFFFFFh
0x1800051ba  mov     eax, edi
0x1800051bc  lock xadd [rbx+8], eax
0x1800051c1  add     eax, edi
0x1800051c3  jnz     short loc_1800051EE
0x1800051c5  mov     rax, [rbx]
0x1800051c8  mov     rcx, rbx
0x1800051cb  mov     rax, [rax+8]
0x1800051cf  call    _guard_dispatch_icall
0x1800051d4  mov     eax, edi
0x1800051d6  lock xadd [rbx+0Ch], eax
0x1800051db  add     eax, edi
0x1800051dd  jnz     short loc_1800051EE
0x1800051df  mov     rax, [rbx]
0x1800051e2  mov     rcx, rbx
0x1800051e5  mov     rax, [rax+10h]
0x1800051e9  call    _guard_dispatch_icall
0x1800051ee  mov     rbx, [rsp+28h+arg_10]
0x1800051f3  add     rsp, 20h
0x1800051f7  pop     rdi
0x1800051f8  retn
```
