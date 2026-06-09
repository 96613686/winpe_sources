# VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVolume(kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &)

- ea: `0x180009208`
- end: `0x18000942b`
- name: `?RemoveVolume@?$VfsVolumeManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@@Z`
- size: `547`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180006cac`
- `0x180008900`

## callees

- `0x1800052e0`
- `0x180009208`
- `0x18000c694`
- `0x18001b3cc`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x180009370`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x180009370`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x18000933b`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x18000933b`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x180009352`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x180009352`
- `FLTMGR!FltGetFilterFromName` at `0x180009268`
- `FLTMGR!FltGetFilterFromName` at `0x180009268`
- `FLTMGR!FltDetachVolume` at `0x180009286`
- `FLTMGR!FltDetachVolume` at `0x180009286`
- `FLTMGR!FltObjectDereference` at `0x180009383`
- `FLTMGR!FltObjectDereference` at `0x180009383`

## pseudocode

```c
__int64 __fastcall VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVolume(
        __int64 a1,
        _QWORD *a2)
{
  PRTL_AVL_TABLE *v2; // r14
  __int64 v5; // rdi
  int v6; // eax
  int v7; // eax
  PFLT_FILTER *v8; // rbx
  NTSTATUS v9; // eax
  unsigned int v10; // edx
  NTSTATUS v11; // r10d
  __int16 v12; // r8
  __int16 v13; // ax
  __int64 v14; // r9
  __int16 v15; // r8
  __int16 v16; // ax
  __int64 v17; // r9
  __int64 v18; // rax
  struct _RTL_AVL_TABLE *v19; // rcx
  PVOID v20; // rax
  volatile signed __int32 *v21; // rdi
  volatile signed __int32 *v23; // rdi
  __int128 v24; // [rsp+30h] [rbp-68h] BYREF
  _QWORD Buffer[2]; // [rsp+40h] [rbp-58h] BYREF
  __int128 v26; // [rsp+50h] [rbp-48h]

  v2 = (PRTL_AVL_TABLE *)(a1 + 16);
  v24 = 0;
  if ( (unsigned __int8)appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::iless_predicate,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVolume<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>>::find(
                          a1 + 16,
                          a2,
                          &v24) )
  {
    v5 = v24;
    v6 = *(_DWORD *)(v24 + 40);
    if ( !v6 || (v7 = v6 - 1, (*(_DWORD *)(v24 + 40) = v7) == 0) )
    {
      v8 = (PFLT_FILTER *)(a1 + 24);
      if ( *(_QWORD *)(a1 + 24) || FltGetFilterFromName((PCUNICODE_STRING)(a1 + 48), (PFLT_FILTER *)(a1 + 24)) >= 0 )
      {
        v9 = FltDetachVolume(*v8, *(PFLT_VOLUME *)(v5 + 32), 0);
        v10 = *(_DWORD *)v5 >> 1;
        v11 = v9;
        if ( v9 < 0 )
        {
          if ( v10 > 0xFFFF )
            v15 = -1;
          else
            v15 = *(_DWORD *)v5 >> 1;
          v16 = 0;
          v17 = 0;
          if ( v10 <= 0xFFFF )
            v16 = v15;
          if ( v16 )
            v17 = *(_QWORD *)(v5 + 8);
          LogWrite(
            2,
            0,
            L"VfsVolumeManager::DetachVFSVolume() - Failed to detach filter driver from volume. Volume: %s. Error: %d",
            v17,
            v11);
        }
        else
        {
          if ( v10 > 0xFFFF )
            v12 = -1;
          else
            v12 = *(_DWORD *)v5 >> 1;
          v13 = 0;
          v14 = 0;
          if ( v10 <= 0xFFFF )
            v13 = v12;
          if ( v13 )
            v14 = *(_QWORD *)(v5 + 8);
          LogWrite(
            3,
            0,
            L"VfsVolumeManager::DetachVFSVolume() - Successfully detached filter driver from volume. Volume: %s.",
            v14);
        }
      }
      Buffer[0] = *a2;
      v18 = a2[1];
      Buffer[1] = v18;
      if ( v18 )
        _InterlockedIncrement((volatile signed __int32 *)(v18 + 8));
      v19 = *v2;
      v26 = 0;
      if ( v19 )
      {
        v20 = RtlLookupElementGenericTableAvl(v19, Buffer);
        if ( v20 )
          RtlDeleteElementGenericTableAvl(*v2, v20);
      }
      appv::shared::kernel::pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>::~pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>(Buffer);
      if ( *v8 && !RtlNumberGenericTableElementsAvl(*v2) )
      {
        FltObjectDereference(*v8);
        *v8 = 0;
      }
    }
    v21 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
    if ( *((_QWORD *)&v24 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v24 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
      if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 16LL))(v21);
    }
    return 0;
  }
  else
  {
    v23 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
    if ( *((_QWORD *)&v24 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v24 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
        if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 16LL))(v23);
      }
    }
    return 3221225524LL;
  }
}

```

## disassembly

```asm
0x180009208  push    rbx
0x18000920a  push    rbp
0x18000920b  push    rsi
0x18000920c  push    rdi
0x18000920d  push    r14
0x18000920f  push    r15
0x180009211  sub     rsp, 68h
0x180009215  lea     r14, [rcx+10h]
0x180009219  mov     rsi, rcx
0x18000921c  xorps   xmm0, xmm0
0x18000921f  lea     r8, [rsp+98h+var_68]
0x180009224  mov     rcx, r14
0x180009227  mov     r15, rdx
0x18000922a  movdqu  [rsp+98h+var_68], xmm0
0x180009230  call    ?find@?$indexed_avl_tree@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uiless_predicate@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@234@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@V?$shared_ptr@V?$CountedVolume@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$VfsVolumeManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@8@@kernel@shared@appv@@QEAA_NAEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEAV?$shared_ptr@V?$CountedVolume@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$VfsVolumeManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@6@@Z; appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::iless_predicate,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVolume<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>>::find(kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,kernel_std::shared_ptr<VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVolume<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> &)
0x180009235  xor     ebp, ebp
0x180009237  test    al, al
0x180009239  jz      loc_1800093D7
0x18000923f  mov     rdi, qword ptr [rsp+98h+var_68]
0x180009244  mov     eax, [rdi+28h]
0x180009247  test    eax, eax
0x180009249  jz      short loc_180009258
0x18000924b  dec     eax
0x18000924d  mov     [rdi+28h], eax
0x180009250  test    eax, eax
0x180009252  jnz     loc_180009392
0x180009258  lea     rbx, [rsi+18h]
0x18000925c  cmp     [rbx], rbp
0x18000925f  jnz     short loc_18000927C
0x180009261  lea     rcx, [rsi+30h]; FilterName
0x180009265  mov     rdx, rbx; RetFilter
0x180009268  call    cs:__imp_FltGetFilterFromName
0x18000926f  nop     dword ptr [rax+rax+00h]
0x180009274  test    eax, eax
0x180009276  js      loc_18000930B
0x18000927c  mov     rdx, [rdi+20h]; Volume
0x180009280  xor     r8d, r8d; InstanceName
0x180009283  mov     rcx, [rbx]; Filter
0x180009286  call    cs:__imp_FltDetachVolume
0x18000928d  nop     dword ptr [rax+rax+00h]
0x180009292  mov     edx, [rdi]
0x180009294  mov     ecx, 0FFFFh
0x180009299  shr     edx, 1
0x18000929b  mov     r10d, eax
0x18000929e  test    eax, eax
0x1800092a0  js      short loc_1800092D5
0x1800092a2  cmp     edx, ecx
0x1800092a4  ja      short loc_1800092AC
0x1800092a6  movzx   r8d, dx
0x1800092aa  jmp     short loc_1800092AF
0x1800092ac  mov     r8d, ecx
0x1800092af  mov     eax, ebp
0x1800092b1  mov     r9, rbp
0x1800092b4  cmovbe  ax, r8w
0x1800092b9  test    ax, ax
0x1800092bc  jz      short loc_1800092C2
0x1800092be  mov     r9, [rdi+8]
0x1800092c2  xor     edx, edx
0x1800092c4  lea     r8, aVfsvolumemanag_10; "VfsVolumeManager::DetachVFSVolume() - S"...
0x1800092cb  lea     ecx, [rdx+3]
0x1800092ce  call    LogWrite
0x1800092d3  jmp     short loc_18000930B
0x1800092d5  cmp     edx, ecx
0x1800092d7  ja      short loc_1800092DF
0x1800092d9  movzx   r8d, dx
0x1800092dd  jmp     short loc_1800092E2
0x1800092df  mov     r8d, ecx
0x1800092e2  mov     eax, ebp
0x1800092e4  mov     r9, rbp
0x1800092e7  cmovbe  ax, r8w
0x1800092ec  test    ax, ax
0x1800092ef  jz      short loc_1800092F5
0x1800092f1  mov     r9, [rdi+8]
0x1800092f5  xor     edx, edx
0x1800092f7  mov     [rsp+98h+var_78], r10d
0x1800092fc  lea     r8, aVfsvolumemanag_4; "VfsVolumeManager::DetachVFSVolume() - F"...
0x180009303  lea     ecx, [rdx+2]
0x180009306  call    LogWrite
0x18000930b  mov     rax, [r15]
0x18000930e  mov     [rsp+98h+Buffer], rax
0x180009313  mov     rax, [r15+8]
0x180009317  mov     [rsp+98h+var_50], rax
0x18000931c  test    rax, rax
0x18000931f  jz      short loc_180009325
0x180009321  lock inc dword ptr [rax+8]
0x180009325  mov     rcx, [r14]; Table
0x180009328  xorps   xmm0, xmm0
0x18000932b  movdqu  [rsp+98h+var_48], xmm0
0x180009331  test    rcx, rcx
0x180009334  jz      short loc_18000935E
0x180009336  lea     rdx, [rsp+98h+Buffer]; Buffer
0x18000933b  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180009342  nop     dword ptr [rax+rax+00h]
0x180009347  test    rax, rax
0x18000934a  jz      short loc_18000935E
0x18000934c  mov     rcx, [r14]; Table
0x18000934f  mov     rdx, rax; Buffer
0x180009352  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180009359  nop     dword ptr [rax+rax+00h]
0x18000935e  lea     rcx, [rsp+98h+Buffer]
0x180009363  call    ??1?$pair@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@V?$shared_ptr@V?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@2@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>::~pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>(void)
0x180009368  cmp     [rbx], rbp
0x18000936b  jz      short loc_180009392
0x18000936d  mov     rcx, [r14]; Table
0x180009370  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x180009377  nop     dword ptr [rax+rax+00h]
0x18000937c  test    eax, eax
0x18000937e  jnz     short loc_180009392
0x180009380  mov     rcx, [rbx]; FltObject
0x180009383  call    cs:__imp_FltObjectDereference
0x18000938a  nop     dword ptr [rax+rax+00h]
0x18000938f  mov     [rbx], rbp
0x180009392  mov     rdi, qword ptr [rsp+98h+var_68+8]
0x180009397  test    rdi, rdi
0x18000939a  jz      short loc_1800093D3
0x18000939c  or      ebx, 0FFFFFFFFh
0x18000939f  mov     eax, ebx
0x1800093a1  lock xadd [rdi+8], eax
0x1800093a6  add     eax, ebx
0x1800093a8  jnz     short loc_1800093D3
0x1800093aa  mov     rax, [rdi]
0x1800093ad  mov     rcx, rdi
0x1800093b0  mov     rax, [rax+8]
0x1800093b4  call    _guard_dispatch_icall
0x1800093b9  mov     eax, ebx
0x1800093bb  lock xadd [rdi+0Ch], eax
0x1800093c0  add     eax, ebx
0x1800093c2  jnz     short loc_1800093D3
0x1800093c4  mov     rax, [rdi]
0x1800093c7  mov     rcx, rdi
0x1800093ca  mov     rax, [rax+10h]
0x1800093ce  call    _guard_dispatch_icall
0x1800093d3  xor     eax, eax
0x1800093d5  jmp     short loc_18000941D
0x1800093d7  mov     rdi, qword ptr [rsp+98h+var_68+8]
0x1800093dc  test    rdi, rdi
0x1800093df  jz      short loc_180009418
0x1800093e1  or      ebx, 0FFFFFFFFh
0x1800093e4  mov     eax, ebx
0x1800093e6  lock xadd [rdi+8], eax
0x1800093eb  add     eax, ebx
0x1800093ed  jnz     short loc_180009418
0x1800093ef  mov     rax, [rdi]
0x1800093f2  mov     rcx, rdi
0x1800093f5  mov     rax, [rax+8]
0x1800093f9  call    _guard_dispatch_icall
0x1800093fe  mov     eax, ebx
0x180009400  lock xadd [rdi+0Ch], eax
0x180009405  add     eax, ebx
0x180009407  jnz     short loc_180009418
0x180009409  mov     rax, [rdi]
0x18000940c  mov     rcx, rdi
0x18000940f  mov     rax, [rax+10h]
0x180009413  call    _guard_dispatch_icall
0x180009418  mov     eax, 0C0000034h
0x18000941d  add     rsp, 68h
0x180009421  pop     r15
0x180009423  pop     r14
0x180009425  pop     rdi
0x180009426  pop     rsi
0x180009427  pop     rbp
0x180009428  pop     rbx
0x180009429  retn
```
