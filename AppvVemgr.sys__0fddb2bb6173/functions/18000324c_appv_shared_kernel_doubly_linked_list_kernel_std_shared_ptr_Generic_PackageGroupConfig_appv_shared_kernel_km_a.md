# appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::insertion_sort<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_by_group_priority>(Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_by_group_priority &)

- ea: `0x18000324c`
- end: `0x1800033a0`
- name: `??$insertion_sort@Uless_by_group_priority@?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAXAEAUless_by_group_priority@?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z`
- size: `340`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180001f78`

## callees

- `0x18000324c`
- `0x18001bb30`

## pseudocode

```c
void __fastcall appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::insertion_sort<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_by_group_priority>(
        __int64 a1)
{
  _QWORD *v1; // rbx
  _QWORD *v2; // rbp
  _QWORD *v3; // rdi
  _QWORD *i; // rsi
  volatile signed __int32 *v5; // r14
  __int64 v6; // rdx
  volatile signed __int32 *v7; // r15
  __int64 v8; // rax
  __int64 v9; // rcx
  unsigned int v10; // r12d
  unsigned int v11; // r13d
  __int64 v12; // rcx
  __int64 v13; // rcx

  if ( *(_DWORD *)a1 > 1u )
  {
    v1 = *(_QWORD **)(a1 + 32);
    v2 = (_QWORD *)(a1 + 8);
    while ( v1 != v2 )
    {
      v3 = v1;
      for ( i = v1; i != v2; i = (_QWORD *)i[3] )
      {
        v5 = (volatile signed __int32 *)v3[1];
        v6 = *v3;
        if ( v5 )
          _InterlockedIncrement(v5 + 2);
        v7 = (volatile signed __int32 *)i[1];
        v8 = *i;
        if ( v7 )
        {
          v9 = (__int64)(v7 + 2);
          _InterlockedIncrement(v7 + 2);
        }
        else
        {
          v9 = 8;
        }
        v10 = *(_DWORD *)(v8 + 56);
        v11 = *(_DWORD *)(v6 + 56);
        if ( v7 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v9, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
            if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 16LL))(v7);
          }
        }
        if ( v5 )
        {
          if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
          {
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
            if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 16LL))(v5);
          }
        }
        if ( v10 < v11 )
          v3 = i;
      }
      if ( v1 != v3 )
      {
        v12 = v1[2];
        v1[2] = v3[2];
        v3[2] = v12;
        *(_QWORD *)(v12 + 24) = v3;
        *(_QWORD *)(v1[2] + 24LL) = v1;
        v13 = v1[3];
        v1[3] = v3[3];
        v3[3] = v13;
        *(_QWORD *)(v13 + 16) = v3;
        *(_QWORD *)(v1[3] + 16LL) = v1;
        v1 = v3;
      }
      v1 = (_QWORD *)v1[3];
    }
  }
}

```

## disassembly

```asm
0x18000324c  push    rbx
0x18000324e  push    rbp
0x18000324f  push    rsi
0x180003250  push    rdi
0x180003251  push    r12
0x180003253  push    r13
0x180003255  push    r14
0x180003257  push    r15
0x180003259  sub     rsp, 28h
0x18000325d  cmp     dword ptr [rcx], 1
0x180003260  jbe     loc_18000338E
0x180003266  mov     rbx, [rcx+20h]
0x18000326a  lea     rbp, [rcx+8]
0x18000326e  cmp     rbx, rbp
0x180003271  jz      loc_18000338E
0x180003277  mov     rdi, rbx
0x18000327a  mov     rsi, rbx
0x18000327d  cmp     rsi, rbp
0x180003280  jz      loc_180003345
0x180003286  mov     r14, [rdi+8]
0x18000328a  mov     rdx, [rdi]
0x18000328d  test    r14, r14
0x180003290  jz      short loc_180003297
0x180003292  lock inc dword ptr [r14+8]
0x180003297  mov     r15, [rsi+8]
0x18000329b  mov     rax, [rsi]
0x18000329e  test    r15, r15
0x1800032a1  jz      short loc_1800032AC
0x1800032a3  lea     rcx, [r15+8]
0x1800032a7  lock inc dword ptr [rcx]
0x1800032aa  jmp     short loc_1800032B1
0x1800032ac  mov     ecx, 8
0x1800032b1  mov     r12d, [rax+38h]
0x1800032b5  mov     r13d, [rdx+38h]
0x1800032b9  test    r15, r15
0x1800032bc  jz      short loc_1800032F6
0x1800032be  or      eax, 0FFFFFFFFh
0x1800032c1  lock xadd [rcx], eax
0x1800032c5  cmp     eax, 1
0x1800032c8  jnz     short loc_1800032F6
0x1800032ca  mov     rax, [r15]
0x1800032cd  mov     rcx, r15
0x1800032d0  mov     rax, [rax+8]
0x1800032d4  call    _guard_dispatch_icall
0x1800032d9  or      eax, 0FFFFFFFFh
0x1800032dc  lock xadd [r15+0Ch], eax
0x1800032e2  cmp     eax, 1
0x1800032e5  jnz     short loc_1800032F6
0x1800032e7  mov     rax, [r15]
0x1800032ea  mov     rcx, r15
0x1800032ed  mov     rax, [rax+10h]
0x1800032f1  call    _guard_dispatch_icall
0x1800032f6  test    r14, r14
0x1800032f9  jz      short loc_180003335
0x1800032fb  or      eax, 0FFFFFFFFh
0x1800032fe  lock xadd [r14+8], eax
0x180003304  cmp     eax, 1
0x180003307  jnz     short loc_180003335
0x180003309  mov     rax, [r14]
0x18000330c  mov     rcx, r14
0x18000330f  mov     rax, [rax+8]
0x180003313  call    _guard_dispatch_icall
0x180003318  or      eax, 0FFFFFFFFh
0x18000331b  lock xadd [r14+0Ch], eax
0x180003321  cmp     eax, 1
0x180003324  jnz     short loc_180003335
0x180003326  mov     rax, [r14]
0x180003329  mov     rcx, r14
0x18000332c  mov     rax, [rax+10h]
0x180003330  call    _guard_dispatch_icall
0x180003335  cmp     r12d, r13d
0x180003338  cmovb   rdi, rsi
0x18000333c  mov     rsi, [rsi+18h]
0x180003340  jmp     loc_18000327D
0x180003345  cmp     rbx, rdi
0x180003348  jz      short loc_180003385
0x18000334a  mov     rcx, [rbx+10h]
0x18000334e  mov     rax, [rdi+10h]
0x180003352  mov     [rbx+10h], rax
0x180003356  mov     [rdi+10h], rcx
0x18000335a  mov     [rcx+18h], rdi
0x18000335e  mov     rax, [rbx+10h]
0x180003362  mov     [rax+18h], rbx
0x180003366  mov     rcx, [rbx+18h]
0x18000336a  mov     rax, [rdi+18h]
0x18000336e  mov     [rbx+18h], rax
0x180003372  mov     [rdi+18h], rcx
0x180003376  mov     [rcx+10h], rdi
0x18000337a  mov     rax, [rbx+18h]
0x18000337e  mov     [rax+10h], rbx
0x180003382  mov     rbx, rdi
0x180003385  mov     rbx, [rbx+18h]
0x180003389  jmp     loc_18000326E
0x18000338e  add     rsp, 28h
0x180003392  pop     r15
0x180003394  pop     r14
0x180003396  pop     r13
0x180003398  pop     r12
0x18000339a  pop     rdi
0x18000339b  pop     rsi
0x18000339c  pop     rbp
0x18000339d  pop     rbx
0x18000339e  retn
```
