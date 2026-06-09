# unpack_vfs_mappings<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::unpack_mappings<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>>(uchar const *,ulong,ushort,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)

- ea: `0x180011e9c`
- end: `0x180011ffe`
- name: `??$unpack_mappings@V?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$unpack_vfs_mappings@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEBEKGAEAV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z`
- size: `354`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180010b50`
- `0x180011538`

## callees

- `0x18000ad50`
- `0x18000e588`
- `0x180011e9c`
- `0x180015524`
- `0x18001bb30`

## pseudocode

```c
__int64 __fastcall unpack_vfs_mappings<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::unpack_mappings<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>>(
        __int64 a1,
        unsigned int a2,
        unsigned __int16 a3,
        __int64 a4)
{
  unsigned int v7; // r12d
  unsigned int v8; // ebx
  int v9; // ebp
  int v10; // esi
  volatile signed __int32 *v11; // rbx
  volatile signed __int32 *v13; // rbx
  _OWORD v14[5]; // [rsp+20h] [rbp-58h] BYREF
  int v15; // [rsp+90h] [rbp+18h] BYREF

  if ( !a3 )
    return 0;
  if ( a1 && a2 )
  {
    v7 = a3;
    v8 = 0;
    v9 = 0;
    v14[0] = 0;
    while ( 1 )
    {
      if ( v8 > a2 )
      {
        v10 = -1073741811;
LABEL_17:
        appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(a4);
LABEL_18:
        v13 = (volatile signed __int32 *)*((_QWORD *)&v14[0] + 1);
        if ( *((_QWORD *)&v14[0] + 1)
          && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v14[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
          if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 16LL))(v13);
        }
        return (unsigned int)v10;
      }
      v15 = 0;
      v10 = ((__int64 (__fastcall *)(__int64, _QWORD, _OWORD *, int *))unpack_vfs_mappings<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::unpack_mapping)(
              a1 + v8,
              a2 - v8,
              v14,
              &v15);
      if ( v10 < 0 )
        goto LABEL_17;
      v10 = appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
              a4,
              v14);
      if ( v10 < 0 )
        goto LABEL_17;
      if ( !v15 )
        break;
      v8 += v15;
      if ( ++v9 >= v7 )
        goto LABEL_18;
    }
    v11 = (volatile signed __int32 *)*((_QWORD *)&v14[0] + 1);
    if ( *((_QWORD *)&v14[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v14[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
        if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 16LL))(v11);
      }
    }
    return 0;
  }
  return 3221225990LL;
}

```

## disassembly

```asm
0x180011e9c  push    rbx
0x180011e9e  push    rbp
0x180011e9f  push    rsi
0x180011ea0  push    rdi
0x180011ea1  push    r12
0x180011ea3  push    r13
0x180011ea5  push    r14
0x180011ea7  push    r15
0x180011ea9  sub     rsp, 38h
0x180011ead  xor     r13d, r13d
0x180011eb0  mov     r14, r9
0x180011eb3  mov     edi, edx
0x180011eb5  mov     r15, rcx
0x180011eb8  test    r8w, r8w
0x180011ebc  jz      loc_180011F91
0x180011ec2  test    rcx, rcx
0x180011ec5  jz      loc_180011FF7
0x180011ecb  test    edx, edx
0x180011ecd  jz      loc_180011FF7
0x180011ed3  movzx   r12d, r8w
0x180011ed7  xorps   xmm0, xmm0
0x180011eda  mov     esi, r13d
0x180011edd  mov     ebx, r13d
0x180011ee0  mov     ebp, r13d
0x180011ee3  movdqu  [rsp+78h+var_58], xmm0
0x180011ee9  test    r12d, r12d
0x180011eec  jz      loc_180011FB2
0x180011ef2  cmp     ebx, edi
0x180011ef4  ja      loc_180011FA5
0x180011efa  mov     edx, edi
0x180011efc  mov     ecx, ebx
0x180011efe  sub     edx, ebx
0x180011f00  mov     [rsp+78h+arg_10], r13d
0x180011f08  add     rcx, r15
0x180011f0b  lea     r9, [rsp+78h+arg_10]
0x180011f13  lea     r8, [rsp+78h+var_58]
0x180011f18  call    ?unpack_mapping@?$unpack_vfs_mappings@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEBEKAEAV?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@AEAK@Z; unpack_vfs_mappings<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::unpack_mapping(uchar const *,ulong,kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> &,ulong &)
0x180011f1d  mov     esi, eax
0x180011f1f  test    eax, eax
0x180011f21  js      loc_180011FAA
0x180011f27  lea     rdx, [rsp+78h+var_58]
0x180011f2c  mov     rcx, r14
0x180011f2f  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x180011f34  mov     esi, eax
0x180011f36  test    eax, eax
0x180011f38  js      short loc_180011FAA
0x180011f3a  mov     eax, [rsp+78h+arg_10]
0x180011f41  test    eax, eax
0x180011f43  jz      short loc_180011F50
0x180011f45  add     ebx, eax
0x180011f47  inc     ebp
0x180011f49  cmp     ebp, r12d
0x180011f4c  jb      short loc_180011EF2
0x180011f4e  jmp     short loc_180011FB2
0x180011f50  mov     rbx, qword ptr [rsp+78h+var_58+8]
0x180011f55  test    rbx, rbx
0x180011f58  jz      short loc_180011F91
0x180011f5a  or      edi, 0FFFFFFFFh
0x180011f5d  mov     eax, edi
0x180011f5f  lock xadd [rbx+8], eax
0x180011f64  add     eax, edi
0x180011f66  jnz     short loc_180011F91
0x180011f68  mov     rax, [rbx]
0x180011f6b  mov     rcx, rbx
0x180011f6e  mov     rax, [rax+8]
0x180011f72  call    _guard_dispatch_icall
0x180011f77  mov     eax, edi
0x180011f79  lock xadd [rbx+0Ch], eax
0x180011f7e  add     eax, edi
0x180011f80  jnz     short loc_180011F91
0x180011f82  mov     rax, [rbx]
0x180011f85  mov     rcx, rbx
0x180011f88  mov     rax, [rax+10h]
0x180011f8c  call    _guard_dispatch_icall
0x180011f91  xor     eax, eax
0x180011f93  add     rsp, 38h
0x180011f97  pop     r15
0x180011f99  pop     r14
0x180011f9b  pop     r13
0x180011f9d  pop     r12
0x180011f9f  pop     rdi
0x180011fa0  pop     rsi
0x180011fa1  pop     rbp
0x180011fa2  pop     rbx
0x180011fa3  retn
0x180011fa5  mov     esi, 0C000000Dh
0x180011faa  mov     rcx, r14
0x180011fad  call    ?clear@?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(void)
0x180011fb2  mov     rbx, qword ptr [rsp+78h+var_58+8]
0x180011fb7  test    rbx, rbx
0x180011fba  jz      short loc_180011FF3
0x180011fbc  or      edi, 0FFFFFFFFh
0x180011fbf  mov     eax, edi
0x180011fc1  lock xadd [rbx+8], eax
0x180011fc6  add     eax, edi
0x180011fc8  jnz     short loc_180011FF3
0x180011fca  mov     rax, [rbx]
0x180011fcd  mov     rcx, rbx
0x180011fd0  mov     rax, [rax+8]
0x180011fd4  call    _guard_dispatch_icall
0x180011fd9  mov     eax, edi
0x180011fdb  lock xadd [rbx+0Ch], eax
0x180011fe0  add     eax, edi
0x180011fe2  jnz     short loc_180011FF3
0x180011fe4  mov     rax, [rbx]
0x180011fe7  mov     rcx, rbx
0x180011fea  mov     rax, [rax+10h]
0x180011fee  call    _guard_dispatch_icall
0x180011ff3  mov     eax, esi
0x180011ff5  jmp     short loc_180011F93
0x180011ff7  mov     eax, 0C0000206h
0x180011ffc  jmp     short loc_180011F93
```
