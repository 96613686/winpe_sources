# VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveAllProcesses(kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &,appv::shared::kernel::doubly_linked_list<ulong,vemgr::vemgr_pool_info> &)

- ea: `0x180008164`
- end: `0x180008352`
- name: `?RemoveAllProcesses@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@AEAV?$doubly_linked_list@KUvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z`
- size: `494`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800099b4`
- `0x180015978`

## callees

- `0x180008164`
- `0x180008778`
- `0x18001b3cc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800081a0`
- `ntoskrnl!ExAllocatePool2` at `0x1800081a0`

## string_xrefs

- `0x180008274`: `VirtualEnvironmentManager::RemoveAllProcesses() - Forcfully terminating process %d. Package %s, User %s`
- `0x180008331`: `VirtualEnvironmentManager::RemoveAllProcesses() - Forcfully terminating VE: Package %s, User %s. VE object still has processes.`

## pseudocode

```c
__int64 __fastcall VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveAllProcesses(
        __int64 a1,
        __int64 *a2,
        __int64 a3)
{
  __int64 v6; // rbx
  __int64 v7; // rbp
  __int64 Pool2; // rax
  __int64 v9; // rdx
  unsigned int *v11; // rbx
  unsigned int *v12; // rdi
  __int64 v13; // r8
  __int64 v14; // rcx
  unsigned int v15; // edx
  __int16 v16; // r9
  __int16 v17; // ax
  __int64 v18; // r10
  __int64 v19; // r9
  unsigned int v20; // ecx
  __int16 v21; // dx
  __int16 v22; // ax
  bool v23; // zf
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rdx
  unsigned int v28; // r8d
  __int16 v29; // r9
  __int16 v30; // ax
  __int64 v31; // rdx
  __int64 v32; // r9
  unsigned int v33; // ecx
  __int16 v34; // r8
  __int16 v35; // ax
  __int64 v36; // r9
  int v37; // [rsp+78h] [rbp+10h] BYREF

  v6 = *(_QWORD *)(*a2 + 104);
  v7 = *a2 + 88;
  while ( v6 != v7 )
  {
    Pool2 = ExAllocatePool2(256, 24, 1733125462);
    if ( !Pool2 )
      return 3221225626LL;
    *(_DWORD *)Pool2 = *(_DWORD *)v6;
    *(_QWORD *)(Pool2 + 16) = Pool2;
    *(_QWORD *)(Pool2 + 8) = Pool2;
    ++*(_DWORD *)a3;
    v9 = *(_QWORD *)(a3 + 16);
    *(_QWORD *)(Pool2 + 16) = a3 + 8;
    *(_QWORD *)(Pool2 + 8) = v9;
    *(_QWORD *)(v9 + 16) = Pool2;
    *(_QWORD *)(a3 + 16) = Pool2;
    v6 = *(_QWORD *)(v6 + 16);
  }
  v11 = *(unsigned int **)(a3 + 24);
  v12 = (unsigned int *)(a3 + 8);
  while ( v11 != v12 )
  {
    v13 = *a2;
    if ( *(_DWORD *)(*a2 + 40) )
      v14 = **(_QWORD **)(v13 + 72) + 48LL;
    else
      v14 = v13 + 136;
    v15 = *(_DWORD *)v14 >> 1;
    if ( v15 > 0xFFFF )
      v16 = -1;
    else
      v16 = *(_DWORD *)v14 >> 1;
    v17 = 0;
    v18 = 0;
    if ( v15 <= 0xFFFF )
      v17 = v16;
    if ( v17 )
      v18 = *(_QWORD *)(v14 + 8);
    v19 = *(_QWORD *)(v13 + 120);
    v20 = *(_DWORD *)v19 >> 1;
    if ( v20 > 0xFFFF )
      v21 = -1;
    else
      v21 = *(_DWORD *)v19 >> 1;
    v22 = 0;
    if ( v20 <= 0xFFFF )
      v22 = v21;
    v23 = v22 == 0;
    v24 = 0;
    if ( !v23 )
      v24 = *(_QWORD *)(v19 + 8);
    LogWrite(
      3,
      0,
      L"VirtualEnvironmentManager::RemoveAllProcesses() - Forcfully terminating process %d. Package %s, User %s",
      *v11,
      v24,
      v18);
    v25 = *v11;
    v37 = 0;
    VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessFromVEInternal_Unlocked(
      a1,
      v25,
      a2,
      &v37);
    v11 = (unsigned int *)*((_QWORD *)v11 + 2);
  }
  v26 = *a2;
  if ( *(_DWORD *)(*a2 + 80) )
  {
    if ( *(_DWORD *)(v26 + 40) )
      v27 = **(_QWORD **)(v26 + 72) + 48LL;
    else
      v27 = v26 + 136;
    v28 = *(_DWORD *)v27 >> 1;
    if ( v28 > 0xFFFF )
      v29 = -1;
    else
      v29 = *(_DWORD *)v27 >> 1;
    v30 = 0;
    if ( v28 <= 0xFFFF )
      v30 = v29;
    if ( v30 )
      v31 = *(_QWORD *)(v27 + 8);
    else
      v31 = 0;
    v32 = *(_QWORD *)(v26 + 120);
    v33 = *(_DWORD *)v32 >> 1;
    if ( v33 > 0xFFFF )
      v34 = -1;
    else
      v34 = *(_DWORD *)v32 >> 1;
    v35 = 0;
    if ( v33 <= 0xFFFF )
      v35 = v34;
    if ( v35 )
      v36 = *(_QWORD *)(v32 + 8);
    else
      v36 = 0;
    LogWrite(
      1,
      0,
      L"VirtualEnvironmentManager::RemoveAllProcesses() - Forcfully terminating VE: Package %s, User %s. VE object still has processes.",
      v36,
      v31);
  }
  return 0;
}

```

## disassembly

```asm
0x180008164  push    rbx
0x180008166  push    rbp
0x180008167  push    rsi
0x180008168  push    rdi
0x180008169  push    r14
0x18000816b  push    r15
0x18000816d  sub     rsp, 38h
0x180008171  mov     rax, [rdx]
0x180008174  mov     rdi, r8
0x180008177  mov     rsi, rdx
0x18000817a  mov     r14, rcx
0x18000817d  xor     r15d, r15d
0x180008180  mov     rbx, [rax+68h]
0x180008184  lea     rbp, [rax+58h]
0x180008188  mov     r8d, r15d
0x18000818b  cmp     rbx, rbp
0x18000818e  jz      short loc_1800081E5
0x180008190  mov     edx, 18h
0x180008195  mov     ecx, 100h
0x18000819a  mov     r8d, 674D6556h
0x1800081a0  call    cs:__imp_ExAllocatePool2
0x1800081a7  nop     dword ptr [rax+rax+00h]
0x1800081ac  test    rax, rax
0x1800081af  jz      short loc_1800081DD
0x1800081b1  mov     ecx, [rbx]
0x1800081b3  mov     [rax], ecx
0x1800081b5  lea     rcx, [rdi+8]
0x1800081b9  mov     [rax+10h], rax
0x1800081bd  mov     [rax+8], rax
0x1800081c1  inc     dword ptr [rdi]
0x1800081c3  mov     rdx, [rdi+10h]
0x1800081c7  mov     [rax+10h], rcx
0x1800081cb  mov     [rax+8], rdx
0x1800081cf  mov     [rdx+10h], rax
0x1800081d3  mov     [rdi+10h], rax
0x1800081d7  mov     rbx, [rbx+10h]
0x1800081db  jmp     short loc_180008188
0x1800081dd  mov     r8d, 0C000009Ah
0x1800081e3  jmp     short loc_1800081EA
0x1800081e5  test    r8d, r8d
0x1800081e8  jns     short loc_1800081F2
0x1800081ea  mov     eax, r8d
0x1800081ed  jmp     loc_180008344
0x1800081f2  mov     rbx, [rdi+18h]
0x1800081f6  mov     ebp, 0FFFFh
0x1800081fb  add     rdi, 8
0x1800081ff  cmp     rbx, rdi
0x180008202  jz      loc_1800082AF
0x180008208  mov     r8, [rsi]
0x18000820b  cmp     [r8+28h], r15d
0x18000820f  jnz     short loc_18000821A
0x180008211  lea     rcx, [r8+88h]
0x180008218  jmp     short loc_180008225
0x18000821a  mov     rax, [r8+48h]
0x18000821e  mov     rcx, [rax]
0x180008221  add     rcx, 30h ; '0'
0x180008225  mov     edx, [rcx]
0x180008227  shr     edx, 1
0x180008229  cmp     edx, ebp
0x18000822b  ja      short loc_180008233
0x18000822d  movzx   r9d, dx
0x180008231  jmp     short loc_180008236
0x180008233  mov     r9d, ebp
0x180008236  mov     eax, r15d
0x180008239  mov     r10, r15
0x18000823c  cmovbe  ax, r9w
0x180008241  test    ax, ax
0x180008244  jz      short loc_18000824A
0x180008246  mov     r10, [rcx+8]
0x18000824a  mov     r9, [r8+78h]
0x18000824e  mov     ecx, [r9]
0x180008251  shr     ecx, 1
0x180008253  cmp     ecx, ebp
0x180008255  ja      short loc_18000825C
0x180008257  movzx   edx, cx
0x18000825a  jmp     short loc_18000825E
0x18000825c  mov     edx, ebp
0x18000825e  mov     eax, r15d
0x180008261  cmovbe  ax, dx
0x180008265  test    ax, ax
0x180008268  mov     rax, r15
0x18000826b  jz      short loc_180008271
0x18000826d  mov     rax, [r9+8]
0x180008271  mov     r9d, [rbx]
0x180008274  lea     r8, aVirtualenviron_22; "VirtualEnvironmentManager::RemoveAllPro"...
0x18000827b  xor     edx, edx
0x18000827d  mov     [rsp+68h+var_40], r10
0x180008282  mov     [rsp+68h+var_48], rax
0x180008287  lea     ecx, [rdx+3]
0x18000828a  call    LogWrite
0x18000828f  mov     edx, [rbx]
0x180008291  lea     r9, [rsp+68h+arg_8]
0x180008296  mov     r8, rsi
0x180008299  mov     [rsp+68h+arg_8], r15d
0x18000829e  mov     rcx, r14
0x1800082a1  call    ?RemoveProcessFromVEInternal_Unlocked@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJKAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@AEAW4RemoveVEDisposition@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessFromVEInternal_Unlocked(ulong,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &,VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVEDisposition &)
0x1800082a6  mov     rbx, [rbx+10h]
0x1800082aa  jmp     loc_1800081FF
0x1800082af  mov     rcx, [rsi]
0x1800082b2  cmp     [rcx+50h], r15d
0x1800082b6  jz      loc_180008342
0x1800082bc  cmp     [rcx+28h], r15d
0x1800082c0  jnz     short loc_1800082CB
0x1800082c2  lea     rdx, [rcx+88h]
0x1800082c9  jmp     short loc_1800082D6
0x1800082cb  mov     rax, [rcx+48h]
0x1800082cf  mov     rdx, [rax]
0x1800082d2  add     rdx, 30h ; '0'
0x1800082d6  mov     r8d, [rdx]
0x1800082d9  shr     r8d, 1
0x1800082dc  cmp     r8d, ebp
0x1800082df  ja      short loc_1800082E7
0x1800082e1  movzx   r9d, r8w
0x1800082e5  jmp     short loc_1800082EA
0x1800082e7  mov     r9d, ebp
0x1800082ea  mov     eax, r15d
0x1800082ed  cmovbe  ax, r9w
0x1800082f2  test    ax, ax
0x1800082f5  jnz     short loc_1800082FC
0x1800082f7  mov     rdx, r15
0x1800082fa  jmp     short loc_180008300
0x1800082fc  mov     rdx, [rdx+8]
0x180008300  mov     r9, [rcx+78h]
0x180008304  mov     ecx, [r9]
0x180008307  shr     ecx, 1
0x180008309  cmp     ecx, ebp
0x18000830b  ja      short loc_180008313
0x18000830d  movzx   r8d, cx
0x180008311  jmp     short loc_180008316
0x180008313  mov     r8d, ebp
0x180008316  mov     eax, r15d
0x180008319  cmovbe  ax, r8w
0x18000831e  test    ax, ax
0x180008321  jnz     short loc_180008328
0x180008323  mov     r9, r15
0x180008326  jmp     short loc_18000832C
0x180008328  mov     r9, [r9+8]
0x18000832c  mov     [rsp+68h+var_48], rdx
0x180008331  lea     r8, aVirtualenviron_16; "VirtualEnvironmentManager::RemoveAllPro"...
0x180008338  xor     edx, edx
0x18000833a  lea     ecx, [rdx+1]
0x18000833d  call    LogWrite
0x180008342  xor     eax, eax
0x180008344  add     rsp, 38h
0x180008348  pop     r15
0x18000834a  pop     r14
0x18000834c  pop     rdi
0x18000834d  pop     rsi
0x18000834e  pop     rbp
0x18000834f  pop     rbx
0x180008350  retn
```
