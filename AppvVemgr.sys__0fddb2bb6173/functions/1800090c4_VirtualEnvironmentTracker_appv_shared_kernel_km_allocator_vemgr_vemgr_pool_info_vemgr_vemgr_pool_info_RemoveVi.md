# VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVirtualProcess(kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &,ulong,VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVEDisposition &)

- ea: `0x1800090c4`
- end: `0x180009202`
- name: `?RemoveVirtualProcess@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@KAEAW4RemoveVEDisposition@1@@Z`
- size: `318`
- prototype: `__int64 __fastcall(struct _RTL_AVL_TABLE **, __int64 *, int, _DWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800062bc`
- `0x180008900`

## callees

- `0x1800090c4`
- `0x18000e6c0`
- `0x18001b3cc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180009162`
- `ntoskrnl!ExFreePoolWithTag` at `0x180009162`

## string_xrefs

- `0x1800091cd`: `VirtualEnvironmentTracker::RemoveVirtualProcess() - Failed to remove process from VE. Package %s, user %s, pid %d, error %d`

## pseudocode

```c
__int64 __fastcall VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVirtualProcess(
        struct _RTL_AVL_TABLE **a1,
        __int64 *a2,
        int a3,
        _DWORD *a4)
{
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // r10
  int v11; // r9d
  _DWORD *v12; // rax
  _QWORD *i; // rcx
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rbx
  unsigned int v17; // eax
  __int64 v18; // rax
  unsigned int v19; // r8d
  __int64 v20; // r9

  if ( !*a2 )
    return 3221225485LL;
  v8 = a2[1];
  if ( !v8 )
    return 3221225485LL;
  if ( !*(_DWORD *)(v8 + 8) )
    return 3221225485LL;
  v9 = *a2;
  v10 = *(_QWORD *)(*a2 + 120);
  if ( *(_DWORD *)v10 <= 2u )
    return 3221225485LL;
  v11 = *(_DWORD *)(v9 + 40);
  v12 = (_DWORD *)(v11 ? **(_QWORD **)(v9 + 72) + 48LL : v9 + 136);
  if ( *v12 <= 2u )
    return 3221225485LL;
  for ( i = *(_QWORD **)(v9 + 104); i != (_QWORD *)(v9 + 88); i = (_QWORD *)i[2] )
  {
    v14 = i[2];
    if ( *(_DWORD *)i == a3 )
    {
      v15 = i[1];
      *(_QWORD *)(v15 + 16) = v14;
      *(_QWORD *)(v14 + 8) = v15;
      ExFreePoolWithTag(i, 0);
      --*(_DWORD *)(v9 + 80);
      return VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_or_decrement_ve(
               a1,
               a2,
               a4);
    }
  }
  if ( v11 )
    v16 = **(_QWORD **)(v9 + 72) + 48LL;
  else
    v16 = v9 + 136;
  v17 = *(_DWORD *)v16 >> 1;
  if ( v17 <= 0xFFFF && (_WORD)v17 )
    v18 = *(_QWORD *)(v16 + 8);
  else
    v18 = 0;
  v19 = *(_DWORD *)v10 >> 1;
  if ( v19 <= 0xFFFF && (_WORD)v19 )
    v20 = *(_QWORD *)(v10 + 8);
  else
    v20 = 0;
  LogWrite(
    1,
    0,
    L"VirtualEnvironmentTracker::RemoveVirtualProcess() - Failed to remove process from VE. Package %s, user %s, pid %d, error %d",
    v20,
    v18,
    a3,
    -1073741772);
  return VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_or_decrement_ve(
           a1,
           a2,
           a4);
}

```

## disassembly

```asm
0x1800090c4  push    rbx
0x1800090c6  push    rbp
0x1800090c7  push    rsi
0x1800090c8  push    rdi
0x1800090c9  push    r14
0x1800090cb  sub     rsp, 40h
0x1800090cf  xor     r14d, r14d
0x1800090d2  mov     rsi, r9
0x1800090d5  mov     r11d, r8d
0x1800090d8  mov     rdi, rdx
0x1800090db  mov     rbp, rcx
0x1800090de  cmp     [rdx], r14
0x1800090e1  jz      loc_1800091F1
0x1800090e7  mov     rax, [rdx+8]
0x1800090eb  test    rax, rax
0x1800090ee  jz      loc_1800091F1
0x1800090f4  mov     eax, [rax+8]
0x1800090f7  test    eax, eax
0x1800090f9  jz      loc_1800091F1
0x1800090ff  mov     rbx, [rdx]
0x180009102  mov     r10, [rbx+78h]
0x180009106  mov     r8d, [r10]
0x180009109  cmp     r8d, 2
0x18000910d  jbe     loc_1800091F1
0x180009113  mov     r9d, [rbx+28h]
0x180009117  test    r9d, r9d
0x18000911a  jnz     short loc_180009125
0x18000911c  lea     rax, [rbx+88h]
0x180009123  jmp     short loc_180009130
0x180009125  mov     rax, [rbx+48h]
0x180009129  mov     rax, [rax]
0x18000912c  add     rax, 30h ; '0'
0x180009130  cmp     dword ptr [rax], 2
0x180009133  jbe     loc_1800091F1
0x180009139  mov     rcx, [rbx+68h]; P
0x18000913d  lea     rax, [rbx+58h]
0x180009141  cmp     rcx, rax
0x180009144  jz      short loc_180009173
0x180009146  mov     rdx, [rcx+10h]
0x18000914a  cmp     [rcx], r11d
0x18000914d  jz      short loc_180009154
0x18000914f  mov     rcx, rdx
0x180009152  jmp     short loc_180009141
0x180009154  mov     rax, [rcx+8]
0x180009158  mov     [rax+10h], rdx
0x18000915c  mov     [rdx+8], rax
0x180009160  xor     edx, edx; Tag
0x180009162  call    cs:__imp_ExFreePoolWithTag
0x180009169  nop     dword ptr [rax+rax+00h]
0x18000916e  dec     dword ptr [rbx+50h]
0x180009171  jmp     short loc_1800091E1
0x180009173  test    r9d, r9d
0x180009176  jnz     short loc_180009181
0x180009178  add     rbx, 88h
0x18000917f  jmp     short loc_18000918C
0x180009181  mov     rax, [rbx+48h]
0x180009185  mov     rbx, [rax]
0x180009188  add     rbx, 30h ; '0'
0x18000918c  mov     eax, [rbx]
0x18000918e  mov     ecx, 0FFFFh
0x180009193  shr     eax, 1
0x180009195  cmp     eax, ecx
0x180009197  ja      short loc_1800091A4
0x180009199  test    ax, ax
0x18000919c  jz      short loc_1800091A4
0x18000919e  mov     rax, [rbx+8]
0x1800091a2  jmp     short loc_1800091A7
0x1800091a4  mov     rax, r14
0x1800091a7  shr     r8d, 1
0x1800091aa  cmp     r8d, ecx
0x1800091ad  ja      short loc_1800091BB
0x1800091af  test    r8w, r8w
0x1800091b3  jz      short loc_1800091BB
0x1800091b5  mov     r9, [r10+8]
0x1800091b9  jmp     short loc_1800091BE
0x1800091bb  mov     r9, r14
0x1800091be  xor     edx, edx
0x1800091c0  mov     [rsp+68h+var_38], 0C0000034h
0x1800091c8  mov     [rsp+68h+var_40], r11d
0x1800091cd  lea     r8, aVirtualenviron_20; "VirtualEnvironmentTracker::RemoveVirtua"...
0x1800091d4  mov     [rsp+68h+var_48], rax
0x1800091d9  lea     ecx, [rdx+1]
0x1800091dc  call    LogWrite
0x1800091e1  mov     r8, rsi
0x1800091e4  mov     rdx, rdi
0x1800091e7  mov     rcx, rbp
0x1800091ea  call    ?remove_or_decrement_ve@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEBV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@AEAW4RemoveVEDisposition@1@@Z; VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_or_decrement_ve(kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &,VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVEDisposition &)
0x1800091ef  jmp     short loc_1800091F6
0x1800091f1  mov     eax, 0C000000Dh
0x1800091f6  add     rsp, 40h
0x1800091fa  pop     r14
0x1800091fc  pop     rdi
0x1800091fd  pop     rsi
0x1800091fe  pop     rbp
0x1800091ff  pop     rbx
0x180009200  retn
```
