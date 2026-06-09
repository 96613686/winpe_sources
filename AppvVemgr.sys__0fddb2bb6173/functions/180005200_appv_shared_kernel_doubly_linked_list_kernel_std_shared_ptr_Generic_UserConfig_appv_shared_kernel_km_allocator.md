# appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>(void)

- ea: `0x180005200`
- end: `0x1800052da`
- name: `??1?$doubly_linked_list@V?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004fc8`
- `0x1800071a0`

## callees

- `0x180005200`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180005277`
- `ntoskrnl!ExFreePoolWithTag` at `0x180005277`

## pseudocode

```c
void __fastcall appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>(
        __int64 a1)
{
  _QWORD *v1; // rbx
  _QWORD *v2; // r14
  __int64 v4; // rax
  _QWORD *v5; // rbp
  volatile signed __int32 *v6; // rdi
  volatile signed __int32 *v7; // rbx

  v1 = *(_QWORD **)(a1 + 32);
  v2 = (_QWORD *)(a1 + 8);
  while ( v1 != v2 )
  {
    v4 = v1[2];
    v5 = (_QWORD *)v1[3];
    *(_QWORD *)(v4 + 24) = v5;
    v5[2] = v4;
    v6 = (volatile signed __int32 *)v1[1];
    if ( v6 && _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 16LL))(v6);
    }
    ExFreePoolWithTag(v1, 0);
    --*(_DWORD *)a1;
    v1 = v5;
  }
  v7 = *(volatile signed __int32 **)(a1 + 16);
  if ( v7 )
  {
    if ( !_InterlockedDecrement(v7 + 2) )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      if ( !_InterlockedDecrement(v7 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
}

```

## disassembly

```asm
0x180005200  push    rbx
0x180005202  push    rbp
0x180005203  push    rsi
0x180005204  push    rdi
0x180005205  push    r14
0x180005207  push    r15
0x180005209  sub     rsp, 28h
0x18000520d  mov     rbx, [rcx+20h]
0x180005211  lea     r14, [rcx+8]
0x180005215  mov     rsi, rcx
0x180005218  or      r15d, 0FFFFFFFFh
0x18000521c  cmp     rbx, r14
0x18000521f  jz      short loc_18000528B
0x180005221  mov     rax, [rbx+10h]
0x180005225  mov     rbp, [rbx+18h]
0x180005229  mov     [rax+18h], rbp
0x18000522d  mov     [rbp+10h], rax
0x180005231  mov     rdi, [rbx+8]
0x180005235  test    rdi, rdi
0x180005238  jz      short loc_180005272
0x18000523a  mov     eax, r15d
0x18000523d  lock xadd [rdi+8], eax
0x180005242  add     eax, r15d
0x180005245  jnz     short loc_180005272
0x180005247  mov     rax, [rdi]
0x18000524a  mov     rcx, rdi
0x18000524d  mov     rax, [rax+8]
0x180005251  call    _guard_dispatch_icall
0x180005256  mov     eax, r15d
0x180005259  lock xadd [rdi+0Ch], eax
0x18000525e  add     eax, r15d
0x180005261  jnz     short loc_180005272
0x180005263  mov     rax, [rdi]
0x180005266  mov     rcx, rdi
0x180005269  mov     rax, [rax+10h]
0x18000526d  call    _guard_dispatch_icall
0x180005272  xor     edx, edx; Tag
0x180005274  mov     rcx, rbx; P
0x180005277  call    cs:__imp_ExFreePoolWithTag
0x18000527e  nop     dword ptr [rax+rax+00h]
0x180005283  add     [rsi], r15d
0x180005286  mov     rbx, rbp
0x180005289  jmp     short loc_18000521C
0x18000528b  mov     rbx, [rsi+10h]
0x18000528f  test    rbx, rbx
0x180005292  jz      short loc_1800052CC
0x180005294  mov     eax, r15d
0x180005297  lock xadd [rbx+8], eax
0x18000529c  add     eax, r15d
0x18000529f  jnz     short loc_1800052CC
0x1800052a1  mov     rax, [rbx]
0x1800052a4  mov     rcx, rbx
0x1800052a7  mov     rax, [rax+8]
0x1800052ab  call    _guard_dispatch_icall
0x1800052b0  mov     eax, r15d
0x1800052b3  lock xadd [rbx+0Ch], eax
0x1800052b8  add     eax, r15d
0x1800052bb  jnz     short loc_1800052CC
0x1800052bd  mov     rax, [rbx]
0x1800052c0  mov     rcx, rbx
0x1800052c3  mov     rax, [rax+10h]
0x1800052c7  call    _guard_dispatch_icall
0x1800052cc  add     rsp, 28h
0x1800052d0  pop     r15
0x1800052d2  pop     r14
0x1800052d4  pop     rdi
0x1800052d5  pop     rsi
0x1800052d6  pop     rbp
0x1800052d7  pop     rbx
0x1800052d8  retn
```
