# vfs_mapping_packer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::pack_mappings<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>>(appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &,uchar *,ulong,ulong &)

- ea: `0x180003bd8`
- end: `0x180003d6c`
- name: `??$pack_mappings@V?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$vfs_mapping_packer@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@SA_NAEBV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@PEAEKAEAK@Z`
- size: `404`
- prototype: `char __fastcall(int *, __int64, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800040dc`

## callees

- `0x180003b0c`
- `0x180003bd8`

## pseudocode

```c
char __fastcall vfs_mapping_packer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::pack_mappings<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>>(
        int *a1,
        __int64 a2,
        unsigned int a3,
        unsigned int *a4)
{
  _QWORD *v4; // rbx
  _QWORD *v5; // r12
  int v6; // r15d
  unsigned int v7; // r10d
  __int64 v12; // r8
  __int64 v13; // rax
  int v14; // ecx
  _DWORD *v15; // rax
  _QWORD v17[2]; // [rsp+20h] [rbp-28h] BYREF
  int v18; // [rsp+30h] [rbp-18h]
  int v19; // [rsp+34h] [rbp-14h]
  int v20; // [rsp+90h] [rbp+48h]

  v4 = (_QWORD *)*((_QWORD *)a1 + 4);
  v5 = a1 + 2;
  v6 = 0;
  *a4 = 0;
  v7 = 0;
  while ( v4 != v5 )
  {
    if ( v7 > a3 )
      return 0;
    v19 = 0;
    v12 = a2 + v7;
    if ( !v12 )
      return 0;
    if ( a3 - v7 < 0x28 )
      return 0;
    v20 = *a1;
    v17[1] = v12 + 40;
    v18 = a3 - v7 - 40;
    v13 = *v4;
    v17[0] = a2 + v7;
    *(_DWORD *)(v12 + 4) = *(_DWORD *)(v13 + 192);
    if ( !(unsigned __int8)appv::vemgr::packed_struct_wrapper<_VFS_MAPPING_ENTRY_MESSAGE,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::pack<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>,unsigned short>(
                             v17,
                             *v4,
                             v12 + 8,
                             v12 + 16)
      || !(unsigned __int8)appv::vemgr::packed_struct_wrapper<_VFS_MAPPING_ENTRY_MESSAGE,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::pack<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>,unsigned short>(
                             v17,
                             *v4 + 32LL,
                             v17[0] + 10LL,
                             v17[0] + 18LL)
      || !(unsigned __int8)appv::vemgr::packed_struct_wrapper<_VFS_MAPPING_ENTRY_MESSAGE,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::pack<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>,unsigned short>(
                             v17,
                             *v4 + 64LL,
                             v17[0] + 12LL,
                             v17[0] + 20LL)
      || !(unsigned __int8)appv::vemgr::packed_struct_wrapper<_VFS_MAPPING_ENTRY_MESSAGE,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::pack<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>,unsigned short>(
                             v17,
                             *v4 + 96LL,
                             v17[0] + 24LL,
                             v17[0] + 32LL)
      || !(unsigned __int8)appv::vemgr::packed_struct_wrapper<_VFS_MAPPING_ENTRY_MESSAGE,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::pack<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>,unsigned short>(
                             v17,
                             *v4 + 128LL,
                             v17[0] + 26LL,
                             v17[0] + 34LL)
      || !(unsigned __int8)appv::vemgr::packed_struct_wrapper<_VFS_MAPPING_ENTRY_MESSAGE,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::pack<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>,unsigned short>(
                             v17,
                             *v4 + 160LL,
                             v17[0] + 28LL,
                             v17[0] + 36LL) )
    {
      return 0;
    }
    ++v6;
    v14 = v19 + 40;
    if ( v6 == v20 )
      v14 = 0;
    v15 = (_DWORD *)v17[0];
    *a4 += v19 + 40;
    v7 = *a4;
    *v15 = v14;
    v4 = (_QWORD *)v4[3];
  }
  return 1;
}

```

## disassembly

```asm
0x180003bd8  push    rbp
0x180003bda  push    rbx
0x180003bdb  push    rsi
0x180003bdc  push    rdi
0x180003bdd  push    r12
0x180003bdf  push    r13
0x180003be1  push    r14
0x180003be3  push    r15
0x180003be5  mov     rbp, rsp
0x180003be8  sub     rsp, 48h
0x180003bec  mov     rbx, [rcx+20h]
0x180003bf0  lea     r12, [rcx+8]
0x180003bf4  xor     r15d, r15d
0x180003bf7  mov     dword ptr [r9], 0
0x180003bfe  xor     r10d, r10d
0x180003c01  mov     rdi, r9
0x180003c04  mov     esi, r8d
0x180003c07  mov     r13, rdx
0x180003c0a  mov     r14, rcx
0x180003c0d  cmp     rbx, r12
0x180003c10  jz      loc_180003D58
0x180003c16  cmp     r10d, esi
0x180003c19  ja      loc_180003D54
0x180003c1f  mov     r8d, r10d
0x180003c22  mov     [rbp+var_14], 0
0x180003c29  add     r8, r13
0x180003c2c  jz      loc_180003D54
0x180003c32  mov     ecx, esi
0x180003c34  sub     ecx, r10d
0x180003c37  cmp     ecx, 28h ; '('
0x180003c3a  jb      loc_180003D54
0x180003c40  mov     eax, [r14]
0x180003c43  lea     r9, [r8+10h]
0x180003c47  mov     [rbp+arg_0], eax
0x180003c4a  lea     rax, [r8+28h]
0x180003c4e  mov     [rbp+var_20], rax
0x180003c52  lea     eax, [rcx-28h]
0x180003c55  mov     [rbp+var_18], eax
0x180003c58  mov     rax, [rbx]
0x180003c5b  mov     [rbp+var_28], r8
0x180003c5f  mov     ecx, [rax+0C0h]
0x180003c65  mov     [r8+4], ecx
0x180003c69  add     r8, 8
0x180003c6d  mov     rdx, [rbx]
0x180003c70  lea     rcx, [rbp+var_28]
0x180003c74  call    ??$pack@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@G@?$packed_struct_wrapper@U_VFS_MAPPING_ENTRY_MESSAGE@@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@vemgr@appv@@QEAA_NAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@2@AEAG1@Z; appv::vemgr::packed_struct_wrapper<_VFS_MAPPING_ENTRY_MESSAGE,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::pack<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>,ushort>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ushort &,ushort &)
0x180003c79  test    al, al
0x180003c7b  jz      loc_180003D54
0x180003c81  mov     r8, [rbp+var_28]
0x180003c85  lea     rcx, [rbp+var_28]
0x180003c89  mov     rdx, [rbx]
0x180003c8c  add     rdx, 20h ; ' '
0x180003c90  lea     r9, [r8+12h]
0x180003c94  add     r8, 0Ah
0x180003c98  call    ??$pack@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@G@?$packed_struct_wrapper@U_VFS_MAPPING_ENTRY_MESSAGE@@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@vemgr@appv@@QEAA_NAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@2@AEAG1@Z; appv::vemgr::packed_struct_wrapper<_VFS_MAPPING_ENTRY_MESSAGE,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::pack<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>,ushort>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ushort &,ushort &)
0x180003c9d  test    al, al
0x180003c9f  jz      loc_180003D54
0x180003ca5  mov     r8, [rbp+var_28]
0x180003ca9  lea     rcx, [rbp+var_28]
0x180003cad  mov     rdx, [rbx]
0x180003cb0  add     rdx, 40h ; '@'
0x180003cb4  lea     r9, [r8+14h]
0x180003cb8  add     r8, 0Ch
0x180003cbc  call    ??$pack@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@G@?$packed_struct_wrapper@U_VFS_MAPPING_ENTRY_MESSAGE@@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@vemgr@appv@@QEAA_NAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@2@AEAG1@Z; appv::vemgr::packed_struct_wrapper<_VFS_MAPPING_ENTRY_MESSAGE,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::pack<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>,ushort>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ushort &,ushort &)
0x180003cc1  test    al, al
0x180003cc3  jz      loc_180003D54
0x180003cc9  mov     r8, [rbp+var_28]
0x180003ccd  lea     rcx, [rbp+var_28]
0x180003cd1  mov     rdx, [rbx]
0x180003cd4  add     rdx, 60h ; '`'
0x180003cd8  lea     r9, [r8+20h]
0x180003cdc  add     r8, 18h
0x180003ce0  call    ??$pack@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@G@?$packed_struct_wrapper@U_VFS_MAPPING_ENTRY_MESSAGE@@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@vemgr@appv@@QEAA_NAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@2@AEAG1@Z; appv::vemgr::packed_struct_wrapper<_VFS_MAPPING_ENTRY_MESSAGE,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::pack<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>,ushort>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ushort &,ushort &)
0x180003ce5  test    al, al
0x180003ce7  jz      short loc_180003D54
0x180003ce9  mov     r8, [rbp+var_28]
0x180003ced  lea     rcx, [rbp+var_28]
0x180003cf1  mov     rdx, [rbx]
0x180003cf4  sub     rdx, 0FFFFFFFFFFFFFF80h
0x180003cf8  lea     r9, [r8+22h]
0x180003cfc  add     r8, 1Ah
0x180003d00  call    ??$pack@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@G@?$packed_struct_wrapper@U_VFS_MAPPING_ENTRY_MESSAGE@@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@vemgr@appv@@QEAA_NAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@2@AEAG1@Z; appv::vemgr::packed_struct_wrapper<_VFS_MAPPING_ENTRY_MESSAGE,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::pack<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>,ushort>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ushort &,ushort &)
0x180003d05  test    al, al
0x180003d07  jz      short loc_180003D54
0x180003d09  mov     r8, [rbp+var_28]
0x180003d0d  lea     rcx, [rbp+var_28]
0x180003d11  mov     rdx, [rbx]
0x180003d14  add     rdx, 0A0h
0x180003d1b  lea     r9, [r8+24h]
0x180003d1f  add     r8, 1Ch
0x180003d23  call    ??$pack@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@G@?$packed_struct_wrapper@U_VFS_MAPPING_ENTRY_MESSAGE@@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@vemgr@appv@@QEAA_NAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@2@AEAG1@Z; appv::vemgr::packed_struct_wrapper<_VFS_MAPPING_ENTRY_MESSAGE,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::pack<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>,ushort>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ushort &,ushort &)
0x180003d28  test    al, al
0x180003d2a  jz      short loc_180003D54
0x180003d2c  mov     edx, [rbp+var_14]
0x180003d2f  xor     eax, eax
0x180003d31  add     edx, 28h ; '('
0x180003d34  inc     r15d
0x180003d37  cmp     r15d, [rbp+arg_0]
0x180003d3b  mov     ecx, edx
0x180003d3d  cmovz   ecx, eax
0x180003d40  mov     rax, [rbp+var_28]
0x180003d44  add     [rdi], edx
0x180003d46  mov     r10d, [rdi]
0x180003d49  mov     [rax], ecx
0x180003d4b  mov     rbx, [rbx+18h]
0x180003d4f  jmp     loc_180003C0D
0x180003d54  xor     al, al
0x180003d56  jmp     short loc_180003D5A
0x180003d58  mov     al, 1
0x180003d5a  add     rsp, 48h
0x180003d5e  pop     r15
0x180003d60  pop     r14
0x180003d62  pop     r13
0x180003d64  pop     r12
0x180003d66  pop     rdi
0x180003d67  pop     rsi
0x180003d68  pop     rbx
0x180003d69  pop     rbp
0x180003d6a  retn
```
