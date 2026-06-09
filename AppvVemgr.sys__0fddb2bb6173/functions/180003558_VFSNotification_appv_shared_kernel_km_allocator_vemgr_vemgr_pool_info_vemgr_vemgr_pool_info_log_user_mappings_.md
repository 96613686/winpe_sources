# VFSNotification<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::log_user_mappings<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &)

- ea: `0x180003558`
- end: `0x180003748`
- name: `??$log_user_mappings@V?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@U?$km_allocator@Uvemgr_pool_info@vemgr@@@234@@?$VFSNotification@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAXAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@0AEBV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@234@@Z`
- size: `496`
- prototype: `void __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180006460`

## callees

- `0x180003558`
- `0x18001b3cc`

## string_xrefs

- `0x1800036e2`: `Copy-on-write`
- `0x180003721`: `VFSNotification::log_user_mappings() - VFS notification: add user mapping. Package moniker: %s. User sid: %s. Source volume name: %s. Source long name: %s. Source short name: %s. Target volume name: %s. Target long name: %s. Target short name: %s. Flags: %d. Mapping type: %s.`

## pseudocode

```c
void __fastcall VFSNotification<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::log_user_mappings<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _QWORD *v4; // rbx
  _QWORD *v5; // r13
  __int64 v8; // r10
  __int64 v9; // rcx
  unsigned int v10; // edx
  __int16 v11; // r8
  __int16 v12; // ax
  __int64 v13; // r14
  unsigned int v14; // edx
  __int16 v15; // r8
  __int16 v16; // ax
  __int64 v17; // rbp
  unsigned int v18; // edx
  __int16 v19; // r8
  __int16 v20; // ax
  __int64 v21; // rsi
  unsigned int v22; // edx
  __int16 v23; // r8
  __int16 v24; // ax
  __int64 v25; // rdi
  unsigned int v26; // edx
  __int16 v27; // r8
  __int16 v28; // ax
  __int64 v29; // r11
  unsigned int v30; // edx
  __int16 v31; // r8
  __int16 v32; // ax
  unsigned int v33; // ecx
  __int16 v34; // dx
  __int64 v35; // r8
  __int16 v36; // ax
  unsigned int v37; // ecx
  __int16 v38; // dx
  __int16 v39; // ax
  __int64 v40; // r9
  __int64 v41; // [rsp+58h] [rbp-60h]

  v4 = *(_QWORD **)(a4 + 32);
  v5 = (_QWORD *)(a4 + 8);
  while ( 1 )
  {
    v8 = 0;
    if ( v4 == v5 )
      break;
    v9 = *v4;
    v10 = *(_DWORD *)(*v4 + 160LL) >> 1;
    if ( v10 > 0xFFFF )
      v11 = -1;
    else
      v11 = *(_DWORD *)(*v4 + 160LL) >> 1;
    v12 = 0;
    v13 = 0;
    if ( v10 <= 0xFFFF )
      v12 = v11;
    if ( v12 )
      v13 = *(_QWORD *)(v9 + 168);
    v14 = *(_DWORD *)(v9 + 128) >> 1;
    if ( v14 > 0xFFFF )
      v15 = -1;
    else
      v15 = *(_DWORD *)(v9 + 128) >> 1;
    v16 = 0;
    v17 = 0;
    if ( v14 <= 0xFFFF )
      v16 = v15;
    if ( v16 )
      v17 = *(_QWORD *)(v9 + 136);
    v18 = *(_DWORD *)(v9 + 96) >> 1;
    if ( v18 > 0xFFFF )
      v19 = -1;
    else
      v19 = *(_DWORD *)(v9 + 96) >> 1;
    v20 = 0;
    v21 = 0;
    if ( v18 <= 0xFFFF )
      v20 = v19;
    if ( v20 )
      v21 = *(_QWORD *)(v9 + 104);
    v22 = *(_DWORD *)(v9 + 64) >> 1;
    if ( v22 > 0xFFFF )
      v23 = -1;
    else
      v23 = *(_DWORD *)(v9 + 64) >> 1;
    v24 = 0;
    v25 = 0;
    if ( v22 <= 0xFFFF )
      v24 = v23;
    if ( v24 )
      v25 = *(_QWORD *)(v9 + 72);
    v26 = *(_DWORD *)(v9 + 32) >> 1;
    if ( v26 > 0xFFFF )
      v27 = -1;
    else
      v27 = *(_DWORD *)(v9 + 32) >> 1;
    v28 = 0;
    v29 = 0;
    if ( v26 <= 0xFFFF )
      v28 = v27;
    if ( v28 )
      v29 = *(_QWORD *)(v9 + 40);
    v30 = *(_DWORD *)v9 >> 1;
    if ( v30 > 0xFFFF )
      v31 = -1;
    else
      v31 = *(_DWORD *)v9 >> 1;
    v32 = 0;
    if ( v30 <= 0xFFFF )
      v32 = v31;
    if ( v32 )
      v8 = *(_QWORD *)(v9 + 8);
    v33 = *(_DWORD *)a3 >> 1;
    if ( v33 > 0xFFFF )
      v34 = -1;
    else
      v34 = *(_DWORD *)a3 >> 1;
    v35 = 0;
    v36 = 0;
    if ( v33 <= 0xFFFF )
      v36 = v34;
    if ( v36 )
      v35 = *(_QWORD *)(a3 + 8);
    v37 = *(_DWORD *)a2 >> 1;
    if ( v37 > 0xFFFF )
      v38 = -1;
    else
      v38 = *(_DWORD *)a2 >> 1;
    v39 = 0;
    if ( v37 <= 0xFFFF )
      v39 = v38;
    v40 = 0;
    if ( v39 )
      v40 = *(_QWORD *)(a2 + 8);
    LODWORD(v41) = *(_DWORD *)(*v4 + 192LL);
    LogWrite(
      3,
      0,
      L"VFSNotification::log_user_mappings() - VFS notification: add user mapping. Package moniker: %s. User sid: %s. Sour"
       "ce volume name: %s. Source long name: %s. Source short name: %s. Target volume name: %s. Target long name: %s. Ta"
       "rget short name: %s. Flags: %d. Mapping type: %s.",
      v40,
      v35,
      v8,
      v29,
      v25,
      v21,
      v17,
      v13,
      v41,
      L"Copy-on-write");
    v4 = (_QWORD *)v4[3];
  }
}

```

## disassembly

```asm
0x180003558  mov     [rsp+arg_0], rcx
0x18000355d  push    rbx
0x18000355e  push    rbp
0x18000355f  push    rsi
0x180003560  push    rdi
0x180003561  push    r12
0x180003563  push    r13
0x180003565  push    r14
0x180003567  push    r15
0x180003569  sub     rsp, 78h
0x18000356d  mov     rbx, [r9+20h]
0x180003571  lea     r13, [r9+8]
0x180003575  mov     r15, r8
0x180003578  mov     r12, rdx
0x18000357b  xor     r10d, r10d
0x18000357e  mov     r9d, 0FFFFh
0x180003584  cmp     rbx, r13
0x180003587  jz      loc_180003736
0x18000358d  mov     rcx, [rbx]
0x180003590  mov     edx, [rcx+0A0h]
0x180003596  mov     eax, [rcx+0C0h]
0x18000359c  shr     edx, 1
0x18000359e  mov     dword ptr [rsp+0B8h+arg_0], eax
0x1800035a5  cmp     edx, r9d
0x1800035a8  ja      short loc_1800035B0
0x1800035aa  movzx   r8d, dx
0x1800035ae  jmp     short loc_1800035B3
0x1800035b0  mov     r8d, r9d
0x1800035b3  mov     eax, r10d
0x1800035b6  mov     r14, r10
0x1800035b9  cmovbe  ax, r8w
0x1800035be  test    ax, ax
0x1800035c1  jz      short loc_1800035CA
0x1800035c3  mov     r14, [rcx+0A8h]
0x1800035ca  mov     edx, [rcx+80h]
0x1800035d0  shr     edx, 1
0x1800035d2  cmp     edx, r9d
0x1800035d5  ja      short loc_1800035DD
0x1800035d7  movzx   r8d, dx
0x1800035db  jmp     short loc_1800035E0
0x1800035dd  mov     r8d, r9d
0x1800035e0  mov     eax, r10d
0x1800035e3  mov     rbp, r10
0x1800035e6  cmovbe  ax, r8w
0x1800035eb  test    ax, ax
0x1800035ee  jz      short loc_1800035F7
0x1800035f0  mov     rbp, [rcx+88h]
0x1800035f7  mov     edx, [rcx+60h]
0x1800035fa  shr     edx, 1
0x1800035fc  cmp     edx, r9d
0x1800035ff  ja      short loc_180003607
0x180003601  movzx   r8d, dx
0x180003605  jmp     short loc_18000360A
0x180003607  mov     r8d, r9d
0x18000360a  mov     eax, r10d
0x18000360d  mov     rsi, r10
0x180003610  cmovbe  ax, r8w
0x180003615  test    ax, ax
0x180003618  jz      short loc_18000361E
0x18000361a  mov     rsi, [rcx+68h]
0x18000361e  mov     edx, [rcx+40h]
0x180003621  shr     edx, 1
0x180003623  cmp     edx, r9d
0x180003626  ja      short loc_18000362E
0x180003628  movzx   r8d, dx
0x18000362c  jmp     short loc_180003631
0x18000362e  mov     r8d, r9d
0x180003631  mov     eax, r10d
0x180003634  mov     rdi, r10
0x180003637  cmovbe  ax, r8w
0x18000363c  test    ax, ax
0x18000363f  jz      short loc_180003645
0x180003641  mov     rdi, [rcx+48h]
0x180003645  mov     edx, [rcx+20h]
0x180003648  shr     edx, 1
0x18000364a  cmp     edx, r9d
0x18000364d  ja      short loc_180003655
0x18000364f  movzx   r8d, dx
0x180003653  jmp     short loc_180003658
0x180003655  mov     r8d, r9d
0x180003658  mov     eax, r10d
0x18000365b  mov     r11, r10
0x18000365e  cmovbe  ax, r8w
0x180003663  test    ax, ax
0x180003666  jz      short loc_18000366C
0x180003668  mov     r11, [rcx+28h]
0x18000366c  mov     edx, [rcx]
0x18000366e  shr     edx, 1
0x180003670  cmp     edx, r9d
0x180003673  ja      short loc_18000367B
0x180003675  movzx   r8d, dx
0x180003679  jmp     short loc_18000367E
0x18000367b  mov     r8d, r9d
0x18000367e  mov     eax, r10d
0x180003681  cmovbe  ax, r8w
0x180003686  test    ax, ax
0x180003689  jz      short loc_18000368F
0x18000368b  mov     r10, [rcx+8]
0x18000368f  mov     ecx, [r15]
0x180003692  shr     ecx, 1
0x180003694  cmp     ecx, r9d
0x180003697  ja      short loc_18000369E
0x180003699  movzx   edx, cx
0x18000369c  jmp     short loc_1800036A1
0x18000369e  mov     edx, r9d
0x1800036a1  xor     r8d, r8d
0x1800036a4  cmp     ecx, r9d
0x1800036a7  mov     eax, r8d
0x1800036aa  cmovbe  ax, dx
0x1800036ae  test    ax, ax
0x1800036b1  jz      short loc_1800036B7
0x1800036b3  mov     r8, [r15+8]
0x1800036b7  mov     ecx, [r12]
0x1800036bb  shr     ecx, 1
0x1800036bd  cmp     ecx, r9d
0x1800036c0  ja      short loc_1800036C7
0x1800036c2  movzx   edx, cx
0x1800036c5  jmp     short loc_1800036CA
0x1800036c7  mov     edx, r9d
0x1800036ca  xor     eax, eax
0x1800036cc  cmp     ecx, r9d
0x1800036cf  cmovbe  ax, dx
0x1800036d3  xor     ecx, ecx
0x1800036d5  mov     r9d, ecx
0x1800036d8  test    ax, ax
0x1800036db  jz      short loc_1800036E2
0x1800036dd  mov     r9, [r12+8]
0x1800036e2  lea     rax, aCopyOnWrite; "Copy-on-write"
0x1800036e9  xor     edx, edx
0x1800036eb  mov     [rsp+0B8h+var_58], rax
0x1800036f0  mov     eax, dword ptr [rsp+0B8h+arg_0]
0x1800036f7  mov     dword ptr [rsp+0B8h+var_60], eax
0x1800036fb  mov     [rsp+0B8h+var_68], r14
0x180003700  lea     ecx, [rdx+3]
0x180003703  mov     [rsp+0B8h+var_70], rbp
0x180003708  mov     [rsp+0B8h+var_78], rsi
0x18000370d  mov     [rsp+0B8h+var_80], rdi
0x180003712  mov     [rsp+0B8h+var_88], r11
0x180003717  mov     [rsp+0B8h+var_90], r10
0x18000371c  mov     [rsp+0B8h+var_98], r8
0x180003721  lea     r8, aVfsnotificatio_4; "VFSNotification::log_user_mappings() - "...
0x180003728  call    LogWrite
0x18000372d  mov     rbx, [rbx+18h]
0x180003731  jmp     loc_18000357B
0x180003736  add     rsp, 78h
0x18000373a  pop     r15
0x18000373c  pop     r14
0x18000373e  pop     r13
0x180003740  pop     r12
0x180003742  pop     rdi
0x180003743  pop     rsi
0x180003744  pop     rbp
0x180003745  pop     rbx
0x180003746  retn
```
