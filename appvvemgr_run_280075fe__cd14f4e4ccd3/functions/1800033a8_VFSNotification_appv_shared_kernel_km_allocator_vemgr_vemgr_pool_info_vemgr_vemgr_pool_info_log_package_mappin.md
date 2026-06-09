# VFSNotification<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::log_package_mappings<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &)

- ea: `0x1800033a8`
- end: `0x180003552`
- name: `??$log_package_mappings@V?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@U?$km_allocator@Uvemgr_pool_info@vemgr@@@234@@?$VFSNotification@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAXAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEBV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@234@@Z`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005890`

## callees

- `0x1800033a8`
- `0x18001b3cc`

## string_xrefs

- `0x1800034f7`: `Copy-on-write`

## pseudocode

```c
void __fastcall VFSNotification<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::log_package_mappings<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v3; // rbx
  _QWORD *v4; // r15
  __int64 v6; // r9
  __int64 v7; // rcx
  unsigned int v8; // edx
  __int16 v9; // r8
  __int16 v10; // ax
  __int64 v11; // rbp
  unsigned int v12; // edx
  __int16 v13; // r8
  __int16 v14; // ax
  __int64 v15; // rsi
  unsigned int v16; // edx
  __int16 v17; // r8
  __int16 v18; // ax
  __int64 v19; // rdi
  unsigned int v20; // edx
  __int16 v21; // r8
  __int16 v22; // ax
  __int64 v23; // r11
  unsigned int v24; // edx
  __int16 v25; // r8
  __int16 v26; // ax
  __int64 v27; // r10
  unsigned int v28; // edx
  __int16 v29; // r8
  __int16 v30; // ax
  __int64 v31; // r8
  unsigned int v32; // ecx
  __int16 v33; // dx
  __int16 v34; // ax
  __int64 v35; // [rsp+50h] [rbp-58h]

  v3 = *(_QWORD **)(a3 + 32);
  v4 = (_QWORD *)(a3 + 8);
  while ( 1 )
  {
    v6 = 0;
    if ( v3 == v4 )
      break;
    v7 = *v3;
    v8 = *(_DWORD *)(*v3 + 160LL) >> 1;
    if ( v8 > 0xFFFF )
      v9 = -1;
    else
      v9 = *(_DWORD *)(*v3 + 160LL) >> 1;
    v10 = 0;
    v11 = 0;
    if ( v8 <= 0xFFFF )
      v10 = v9;
    if ( v10 )
      v11 = *(_QWORD *)(v7 + 168);
    v12 = *(_DWORD *)(v7 + 128) >> 1;
    if ( v12 > 0xFFFF )
      v13 = -1;
    else
      v13 = *(_DWORD *)(v7 + 128) >> 1;
    v14 = 0;
    v15 = 0;
    if ( v12 <= 0xFFFF )
      v14 = v13;
    if ( v14 )
      v15 = *(_QWORD *)(v7 + 136);
    v16 = *(_DWORD *)(v7 + 96) >> 1;
    if ( v16 > 0xFFFF )
      v17 = -1;
    else
      v17 = *(_DWORD *)(v7 + 96) >> 1;
    v18 = 0;
    v19 = 0;
    if ( v16 <= 0xFFFF )
      v18 = v17;
    if ( v18 )
      v19 = *(_QWORD *)(v7 + 104);
    v20 = *(_DWORD *)(v7 + 64) >> 1;
    if ( v20 > 0xFFFF )
      v21 = -1;
    else
      v21 = *(_DWORD *)(v7 + 64) >> 1;
    v22 = 0;
    v23 = 0;
    if ( v20 <= 0xFFFF )
      v22 = v21;
    if ( v22 )
      v23 = *(_QWORD *)(v7 + 72);
    v24 = *(_DWORD *)(v7 + 32) >> 1;
    if ( v24 > 0xFFFF )
      v25 = -1;
    else
      v25 = *(_DWORD *)(v7 + 32) >> 1;
    v26 = 0;
    v27 = 0;
    if ( v24 <= 0xFFFF )
      v26 = v25;
    if ( v26 )
      v27 = *(_QWORD *)(v7 + 40);
    v28 = *(_DWORD *)v7 >> 1;
    if ( v28 > 0xFFFF )
      v29 = -1;
    else
      v29 = *(_DWORD *)v7 >> 1;
    v30 = 0;
    if ( v28 <= 0xFFFF )
      v30 = v29;
    v31 = 0;
    if ( v30 )
      v31 = *(_QWORD *)(v7 + 8);
    v32 = *(_DWORD *)a2 >> 1;
    if ( v32 > 0xFFFF )
      v33 = -1;
    else
      v33 = *(_DWORD *)a2 >> 1;
    v34 = 0;
    if ( v32 <= 0xFFFF )
      v34 = v33;
    if ( v34 )
      v6 = *(_QWORD *)(a2 + 8);
    LODWORD(v35) = *(_DWORD *)(*v3 + 192LL);
    LogWrite(
      3,
      0,
      L"VFSNotification::log_package_mappings() - VFS notification: add package mapping. Package moniker: %s. Source volum"
       "e name: %s. Source long name: %s. Source short name: %s. Target volume name: %s. Target long name: %s. Target sho"
       "rt name: %s. Flags: %d. Mapping type: %s.",
      v6,
      v31,
      v27,
      v23,
      v19,
      v15,
      v11,
      v35,
      L"Copy-on-write");
    v3 = (_QWORD *)v3[3];
  }
}

```

## disassembly

```asm
0x1800033a8  push    rbx
0x1800033aa  push    rbp
0x1800033ab  push    rsi
0x1800033ac  push    rdi
0x1800033ad  push    r12
0x1800033af  push    r13
0x1800033b1  push    r14
0x1800033b3  push    r15
0x1800033b5  sub     rsp, 68h
0x1800033b9  mov     rbx, [r8+20h]
0x1800033bd  lea     r15, [r8+8]
0x1800033c1  mov     r14, rdx
0x1800033c4  mov     r13d, 0FFFFh
0x1800033ca  xor     r9d, r9d
0x1800033cd  cmp     rbx, r15
0x1800033d0  jz      loc_180003540
0x1800033d6  mov     rcx, [rbx]
0x1800033d9  mov     edx, [rcx+0A0h]
0x1800033df  mov     r12d, [rcx+0C0h]
0x1800033e6  shr     edx, 1
0x1800033e8  cmp     edx, r13d
0x1800033eb  ja      short loc_1800033F3
0x1800033ed  movzx   r8d, dx
0x1800033f1  jmp     short loc_1800033F6
0x1800033f3  mov     r8d, r13d
0x1800033f6  mov     eax, r9d
0x1800033f9  mov     rbp, r9
0x1800033fc  cmovbe  ax, r8w
0x180003401  test    ax, ax
0x180003404  jz      short loc_18000340D
0x180003406  mov     rbp, [rcx+0A8h]
0x18000340d  mov     edx, [rcx+80h]
0x180003413  shr     edx, 1
0x180003415  cmp     edx, r13d
0x180003418  ja      short loc_180003420
0x18000341a  movzx   r8d, dx
0x18000341e  jmp     short loc_180003423
0x180003420  mov     r8d, r13d
0x180003423  mov     eax, r9d
0x180003426  mov     rsi, r9
0x180003429  cmovbe  ax, r8w
0x18000342e  test    ax, ax
0x180003431  jz      short loc_18000343A
0x180003433  mov     rsi, [rcx+88h]
0x18000343a  mov     edx, [rcx+60h]
0x18000343d  shr     edx, 1
0x18000343f  cmp     edx, r13d
0x180003442  ja      short loc_18000344A
0x180003444  movzx   r8d, dx
0x180003448  jmp     short loc_18000344D
0x18000344a  mov     r8d, r13d
0x18000344d  mov     eax, r9d
0x180003450  mov     rdi, r9
0x180003453  cmovbe  ax, r8w
0x180003458  test    ax, ax
0x18000345b  jz      short loc_180003461
0x18000345d  mov     rdi, [rcx+68h]
0x180003461  mov     edx, [rcx+40h]
0x180003464  shr     edx, 1
0x180003466  cmp     edx, r13d
0x180003469  ja      short loc_180003471
0x18000346b  movzx   r8d, dx
0x18000346f  jmp     short loc_180003474
0x180003471  mov     r8d, r13d
0x180003474  mov     eax, r9d
0x180003477  mov     r11, r9
0x18000347a  cmovbe  ax, r8w
0x18000347f  test    ax, ax
0x180003482  jz      short loc_180003488
0x180003484  mov     r11, [rcx+48h]
0x180003488  mov     edx, [rcx+20h]
0x18000348b  shr     edx, 1
0x18000348d  cmp     edx, r13d
0x180003490  ja      short loc_180003498
0x180003492  movzx   r8d, dx
0x180003496  jmp     short loc_18000349B
0x180003498  mov     r8d, r13d
0x18000349b  mov     eax, r9d
0x18000349e  mov     r10, r9
0x1800034a1  cmovbe  ax, r8w
0x1800034a6  test    ax, ax
0x1800034a9  jz      short loc_1800034AF
0x1800034ab  mov     r10, [rcx+28h]
0x1800034af  mov     edx, [rcx]
0x1800034b1  shr     edx, 1
0x1800034b3  cmp     edx, r13d
0x1800034b6  ja      short loc_1800034BE
0x1800034b8  movzx   r8d, dx
0x1800034bc  jmp     short loc_1800034C1
0x1800034be  mov     r8d, r13d
0x1800034c1  mov     eax, r9d
0x1800034c4  cmovbe  ax, r8w
0x1800034c9  mov     r8, r9
0x1800034cc  test    ax, ax
0x1800034cf  jz      short loc_1800034D5
0x1800034d1  mov     r8, [rcx+8]
0x1800034d5  mov     ecx, [r14]
0x1800034d8  shr     ecx, 1
0x1800034da  cmp     ecx, r13d
0x1800034dd  ja      short loc_1800034E4
0x1800034df  movzx   edx, cx
0x1800034e2  jmp     short loc_1800034E7
0x1800034e4  mov     edx, r13d
0x1800034e7  mov     eax, r9d
0x1800034ea  cmovbe  ax, dx
0x1800034ee  test    ax, ax
0x1800034f1  jz      short loc_1800034F7
0x1800034f3  mov     r9, [r14+8]
0x1800034f7  lea     rax, aCopyOnWrite; "Copy-on-write"
0x1800034fe  xor     edx, edx
0x180003500  mov     [rsp+0A8h+var_50], rax
0x180003505  mov     dword ptr [rsp+0A8h+var_58], r12d
0x18000350a  mov     [rsp+0A8h+var_60], rbp
0x18000350f  mov     [rsp+0A8h+var_68], rsi
0x180003514  lea     ecx, [rdx+3]
0x180003517  mov     [rsp+0A8h+var_70], rdi
0x18000351c  mov     [rsp+0A8h+var_78], r11
0x180003521  mov     [rsp+0A8h+var_80], r10
0x180003526  mov     [rsp+0A8h+var_88], r8
0x18000352b  lea     r8, aVfsnotificatio_5; "VFSNotification::log_package_mappings()"...
0x180003532  call    LogWrite
0x180003537  mov     rbx, [rbx+18h]
0x18000353b  jmp     loc_1800033CA
0x180003540  add     rsp, 68h
0x180003544  pop     r15
0x180003546  pop     r14
0x180003548  pop     r13
0x18000354a  pop     r12
0x18000354c  pop     rdi
0x18000354d  pop     rsi
0x18000354e  pop     rbp
0x18000354f  pop     rbx
0x180003550  retn
```
