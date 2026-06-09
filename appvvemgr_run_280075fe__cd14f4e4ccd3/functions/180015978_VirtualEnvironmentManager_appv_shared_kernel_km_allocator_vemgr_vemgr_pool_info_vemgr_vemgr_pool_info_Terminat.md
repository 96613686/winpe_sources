# VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::TerminateAll(void)

- ea: `0x180015978`
- end: `0x180015dc6`
- name: `?TerminateAll@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJXZ`
- size: `1102`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180015dd0`

## callees

- `0x180003034`
- `0x180008164`
- `0x1800098d8`
- `0x18000c5f4`
- `0x18000c8cc`
- `0x180015828`
- `0x180015978`
- `0x18001b3cc`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180015d9e`
- `ntoskrnl!KeReleaseMutex` at `0x180015d9e`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x180015d11`
- `ntoskrnl!RtlNumberGenericTableElementsAvl` at `0x180015d11`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x180015d46`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x180015d46`
- `ntoskrnl!ExFreePoolWithTag` at `0x180015cee`
- `ntoskrnl!ExFreePoolWithTag` at `0x180015cee`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800159b7`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800159b7`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x180015d35`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x180015d35`

## string_xrefs

- `0x180015ba1`: `VirtualEnvironmentManager::TerminateAll() - Failed to remove processes from virtual enviornment. moniker %s. user %s. error %d.`

## pseudocode

```c
__int64 __fastcall VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::TerminateAll(
        __int64 *a1)
{
  void *v2; // rcx
  __int64 v4; // rcx
  unsigned int v5; // r15d
  int v6; // eax
  __int64 v7; // rbx
  int v8; // r14d
  _DWORD *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdi
  union _LARGE_INTEGER v12; // rax
  volatile signed __int32 *v13; // rdi
  __int64 v14; // rdx
  unsigned int v15; // ecx
  __int16 v16; // r8
  __int16 v17; // ax
  __int64 v18; // r8
  __int64 v19; // r9
  unsigned int v20; // ecx
  __int16 v21; // dx
  __int16 v22; // ax
  __int64 v23; // r9
  __int64 v24; // rdx
  unsigned int v25; // ecx
  __int16 v26; // r8
  __int16 v27; // ax
  __int64 v28; // r9
  __int64 v29; // r8
  unsigned int v30; // ecx
  __int16 v31; // dx
  __int16 v32; // ax
  __int64 v33; // r8
  __int64 v34; // rdx
  unsigned int v35; // ecx
  __int16 v36; // r8
  __int16 v37; // ax
  __int64 v38; // r8
  __int64 v39; // r9
  unsigned int v40; // ecx
  __int16 v41; // dx
  __int16 v42; // ax
  __int64 v43; // r9
  int v44; // eax
  char *v45; // rcx
  int v46; // edi
  __int64 v47; // rdx
  char *v48; // rbx
  PRTL_AVL_TABLE *v49; // rbx
  struct _RTL_AVL_TABLE *v50; // rcx
  PVOID v51; // rax
  volatile signed __int32 *v52; // rbx
  __int64 v53; // [rsp+28h] [rbp-48h]
  __int128 v54; // [rsp+30h] [rbp-40h] BYREF
  __int128 v55; // [rsp+40h] [rbp-30h] BYREF
  int v56; // [rsp+50h] [rbp-20h] BYREF
  char v57; // [rsp+58h] [rbp-18h] BYREF
  char *v58; // [rsp+60h] [rbp-10h]
  PVOID P; // [rsp+68h] [rbp-8h]
  union _LARGE_INTEGER Timeout; // [rsp+B0h] [rbp+40h] BYREF
  union _LARGE_INTEGER v61; // [rsp+B8h] [rbp+48h] BYREF
  char v62; // [rsp+C0h] [rbp+50h] BYREF

  v2 = (void *)a1[9];
  if ( v2 )
  {
    Timeout.QuadPart = -300000000;
    if ( KeWaitForSingleObject(v2, Executive, 0, 0, &Timeout) )
      return 3221225653LL;
  }
  v4 = *a1;
  v5 = 0;
  v54 = 0;
  if ( (int)VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FirstVirtualEnvironment(
              v4,
              &v54) >= 0 )
  {
    do
    {
      v56 = 0;
      P = &v57;
      v58 = &v57;
      v6 = VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveAllProcesses(
             a1,
             &v54,
             &v56);
      v7 = v54;
      v8 = v6;
      if ( v6 >= 0 )
      {
        if ( *(_DWORD *)(v54 + 40) )
          v24 = **(_QWORD **)(v54 + 72) + 48LL;
        else
          v24 = v54 + 136;
        v25 = *(_DWORD *)v24 >> 1;
        if ( v25 > 0xFFFF )
          v26 = -1;
        else
          v26 = *(_DWORD *)v24 >> 1;
        v27 = 0;
        LODWORD(v28) = 0;
        if ( v25 <= 0xFFFF )
          v27 = v26;
        if ( v27 )
          v28 = *(_QWORD *)(v24 + 8);
        v29 = *(_QWORD *)(v54 + 120);
        v30 = *(_DWORD *)v29 >> 1;
        if ( v30 > 0xFFFF )
          v31 = -1;
        else
          v31 = *(_DWORD *)v29 >> 1;
        v32 = 0;
        if ( v30 <= 0xFFFF )
          v32 = v31;
        if ( v32 )
          v33 = *(_QWORD *)(v29 + 8);
        else
          LODWORD(v33) = 0;
        v8 = VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::TerminateProcesses(
               v30,
               (unsigned int)&v56,
               v33,
               v28,
               0);
        if ( v8 < 0 )
        {
          if ( *(_DWORD *)(v7 + 40) )
            v34 = **(_QWORD **)(v7 + 72) + 48LL;
          else
            v34 = v7 + 136;
          v35 = *(_DWORD *)v34 >> 1;
          if ( v35 > 0xFFFF )
            v36 = -1;
          else
            v36 = *(_DWORD *)v34 >> 1;
          v37 = 0;
          if ( v35 <= 0xFFFF )
            v37 = v36;
          v38 = 0;
          if ( v37 )
            v38 = *(_QWORD *)(v34 + 8);
          v39 = *(_QWORD *)(v7 + 120);
          v40 = *(_DWORD *)v39 >> 1;
          if ( v40 > 0xFFFF )
            v41 = -1;
          else
            v41 = *(_DWORD *)v39 >> 1;
          v42 = 0;
          if ( v40 <= 0xFFFF )
            v42 = v41;
          if ( v42 )
            v43 = *(_QWORD *)(v39 + 8);
          else
            v43 = 0;
          LODWORD(v53) = v8;
          LogWrite(
            1,
            0,
            L"VirtualEnvironmentManager::TerminateAll() - Failed to terminate processes in the virtual enviornment. monike"
             "r %s. user %s. error %d.",
            v43,
            v38,
            v53);
        }
      }
      else
      {
        if ( (_QWORD)v54
          && *((_QWORD *)&v54 + 1)
          && *(_DWORD *)(*((_QWORD *)&v54 + 1) + 8LL)
          && **(_DWORD **)(v54 + 120) > 2u )
        {
          v9 = (_DWORD *)(*(_DWORD *)(v54 + 40) ? **(_QWORD **)(v54 + 72) + 48LL : v54 + 136);
          if ( *v9 > 2u )
          {
            v10 = *a1;
            v55 = 0;
            if ( (int)VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_ve_list(
                        v10,
                        v54 + 120,
                        &v55) >= 0 )
            {
              v11 = v55;
              v12.QuadPart = *(_DWORD *)(v7 + 40) ? **(_QWORD **)(v7 + 72) + 64LL : v7 + 152;
              Timeout = v12;
              appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::find_first_element<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_predecate>(
                v55,
                &v61,
                &Timeout);
              if ( v61.QuadPart != v11 + 8 )
              {
                Timeout = v61;
                appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(
                  v11,
                  &v62,
                  &Timeout);
              }
            }
            v13 = (volatile signed __int32 *)*((_QWORD *)&v55 + 1);
            if ( *((_QWORD *)&v55 + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v55 + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
                if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 16LL))(v13);
              }
            }
          }
        }
        if ( *(_DWORD *)(v7 + 40) )
          v14 = **(_QWORD **)(v7 + 72) + 48LL;
        else
          v14 = v7 + 136;
        v15 = *(_DWORD *)v14 >> 1;
        if ( v15 > 0xFFFF )
          v16 = -1;
        else
          v16 = *(_DWORD *)v14 >> 1;
        v17 = 0;
        if ( v15 <= 0xFFFF )
          v17 = v16;
        v18 = 0;
        if ( v17 )
          v18 = *(_QWORD *)(v14 + 8);
        v19 = *(_QWORD *)(v7 + 120);
        v20 = *(_DWORD *)v19 >> 1;
        if ( v20 > 0xFFFF )
          v21 = -1;
        else
          v21 = *(_DWORD *)v19 >> 1;
        v22 = 0;
        if ( v20 <= 0xFFFF )
          v22 = v21;
        if ( v22 )
          v23 = *(_QWORD *)(v19 + 8);
        else
          v23 = 0;
        LODWORD(v53) = v8;
        LogWrite(
          1,
          0,
          L"VirtualEnvironmentManager::TerminateAll() - Failed to remove processes from virtual enviornment. moniker %s. u"
           "ser %s. error %d.",
          v23,
          v18,
          v53);
      }
      if ( v8 >= 0 )
        v8 = v5;
      v5 = v8;
      v44 = VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FirstVirtualEnvironment(
              *a1,
              &v54);
      v45 = (char *)P;
      v46 = v44;
      while ( v45 != &v57 )
      {
        v47 = *((_QWORD *)v45 + 1);
        v48 = (char *)*((_QWORD *)v45 + 2);
        *(_QWORD *)(v47 + 16) = v48;
        *((_QWORD *)v48 + 1) = v47;
        ExFreePoolWithTag(v45, 0);
        --v56;
        v45 = v48;
      }
    }
    while ( v46 >= 0 );
  }
  if ( RtlNumberGenericTableElementsAvl(*(PRTL_AVL_TABLE *)a1[2]) )
  {
    v49 = (PRTL_AVL_TABLE *)a1[2];
    v50 = *v49;
    if ( *v49 )
    {
      while ( 1 )
      {
        v51 = RtlEnumerateGenericTableAvl(v50, 1u);
        if ( !v51 )
          break;
        RtlDeleteElementGenericTableAvl(*v49, v51);
        v50 = *v49;
      }
    }
  }
  v52 = (volatile signed __int32 *)*((_QWORD *)&v54 + 1);
  if ( *((_QWORD *)&v54 + 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v54 + 1) + 8LL), 0xFFFFFFFF) == 1 )
  {
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 8LL))(v52);
    if ( _InterlockedExchangeAdd(v52 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 16LL))(v52);
  }
  KeReleaseMutex((PRKMUTEX)a1[9], 0);
  return v5;
}

```

## disassembly

```asm
0x180015978  mov     [rsp-38h+arg_18], rbx
0x18001597d  push    rbp
0x18001597e  push    rsi
0x18001597f  push    rdi
0x180015980  push    r12
0x180015982  push    r13
0x180015984  push    r14
0x180015986  push    r15
0x180015988  mov     rbp, rsp
0x18001598b  sub     rsp, 70h
0x18001598f  mov     rsi, rcx
0x180015992  xor     r12d, r12d
0x180015995  mov     rcx, [rcx+48h]; Object
0x180015999  test    rcx, rcx
0x18001599c  jz      short loc_1800159D1
0x18001599e  lea     rax, [rbp+arg_0]
0x1800159a2  mov     qword ptr [rbp+arg_0], 0FFFFFFFFEE1E5D00h
0x1800159aa  xor     r9d, r9d; Alertable
0x1800159ad  mov     [rsp+70h+Timeout], rax; Timeout
0x1800159b2  xor     r8d, r8d; WaitMode
0x1800159b5  xor     edx, edx; WaitReason
0x1800159b7  call    cs:__imp_KeWaitForSingleObject
0x1800159be  nop     dword ptr [rax+rax+00h]
0x1800159c3  test    eax, eax
0x1800159c5  jz      short loc_1800159D1
0x1800159c7  mov     eax, 0C00000B5h
0x1800159cc  jmp     loc_180015DAD
0x1800159d1  mov     rcx, [rsi]
0x1800159d4  lea     rdx, [rbp+var_40]
0x1800159d8  xorps   xmm0, xmm0
0x1800159db  mov     r15d, r12d
0x1800159de  movdqu  [rbp+var_40], xmm0
0x1800159e3  call    ?FirstVirtualEnvironment@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FirstVirtualEnvironment(kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x1800159e8  test    eax, eax
0x1800159ea  js      loc_180015D0A
0x1800159f0  mov     r13d, 0FFFFh
0x1800159f6  lea     rax, [rbp+var_18]
0x1800159fa  mov     [rbp+var_20], r12d
0x1800159fe  mov     [rbp+P], rax
0x180015a02  lea     r8, [rbp+var_20]
0x180015a06  lea     rax, [rbp+var_18]
0x180015a0a  mov     rcx, rsi
0x180015a0d  lea     rdx, [rbp+var_40]
0x180015a11  mov     [rbp+var_10], rax
0x180015a15  call    ?RemoveAllProcesses@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@AEAV?$doubly_linked_list@KUvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveAllProcesses(kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &,appv::shared::kernel::doubly_linked_list<ulong,vemgr::vemgr_pool_info> &)
0x180015a1a  mov     rbx, qword ptr [rbp+var_40]
0x180015a1e  mov     r14d, eax
0x180015a21  test    eax, eax
0x180015a23  jns     loc_180015BAD
0x180015a29  test    rbx, rbx
0x180015a2c  jz      loc_180015B2C
0x180015a32  mov     rcx, qword ptr [rbp+var_40+8]
0x180015a36  test    rcx, rcx
0x180015a39  jz      loc_180015B2C
0x180015a3f  mov     ecx, [rcx+8]
0x180015a42  mov     r9, [rsi]
0x180015a45  test    ecx, ecx
0x180015a47  jz      loc_180015B2C
0x180015a4d  lea     rdx, [rbx+78h]
0x180015a51  mov     rax, [rdx]
0x180015a54  cmp     dword ptr [rax], 2
0x180015a57  jbe     loc_180015B2C
0x180015a5d  cmp     [rbx+28h], r12d
0x180015a61  jnz     short loc_180015A6C
0x180015a63  lea     rax, [rbx+88h]
0x180015a6a  jmp     short loc_180015A77
0x180015a6c  mov     rax, [rbx+48h]
0x180015a70  mov     rax, [rax]
0x180015a73  add     rax, 30h ; '0'
0x180015a77  cmp     dword ptr [rax], 2
0x180015a7a  jbe     loc_180015B2C
0x180015a80  xorps   xmm0, xmm0
0x180015a83  lea     r8, [rbp+var_30]
0x180015a87  mov     rcx, r9
0x180015a8a  movdqu  [rbp+var_30], xmm0
0x180015a8f  call    ?find_ve_list@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEAV?$shared_ptr@V?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@3@@Z; VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_ve_list(kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>> &)
0x180015a94  test    eax, eax
0x180015a96  js      short loc_180015AEB
0x180015a98  mov     rdi, qword ptr [rbp+var_30]
0x180015a9c  cmp     [rbx+28h], r12d
0x180015aa0  jnz     short loc_180015AAB
0x180015aa2  lea     rax, [rbx+98h]
0x180015aa9  jmp     short loc_180015AB6
0x180015aab  mov     rax, [rbx+48h]
0x180015aaf  mov     rax, [rax]
0x180015ab2  add     rax, 40h ; '@'
0x180015ab6  lea     r8, [rbp+arg_0]
0x180015aba  mov     qword ptr [rbp+arg_0], rax
0x180015abe  lea     rdx, [rbp+arg_8]
0x180015ac2  mov     rcx, rdi
0x180015ac5  call    ??$find_first_element@Ufind_predecate@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEBA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@123@AEAUfind_predecate@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::find_first_element<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_predecate>(VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::find_predecate &)
0x180015aca  mov     rax, [rbp+arg_8]
0x180015ace  lea     rcx, [rdi+8]
0x180015ad2  cmp     rax, rcx
0x180015ad5  jz      short loc_180015AEB
0x180015ad7  lea     r8, [rbp+arg_0]
0x180015adb  mov     qword ptr [rbp+arg_0], rax
0x180015adf  lea     rdx, [rbp+arg_10]
0x180015ae3  mov     rcx, rdi
0x180015ae6  call    ?erase@?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@234@V5234@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(appv::shared::kernel::bidirectional_list_iterator<appv::shared::kernel::dl_node_t<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>>>)
0x180015aeb  mov     rdi, qword ptr [rbp+var_30+8]
0x180015aef  test    rdi, rdi
0x180015af2  jz      short loc_180015B2C
0x180015af4  or      eax, 0FFFFFFFFh
0x180015af7  lock xadd [rdi+8], eax
0x180015afc  cmp     eax, 1
0x180015aff  jnz     short loc_180015B2C
0x180015b01  mov     rax, [rdi]
0x180015b04  mov     rcx, rdi
0x180015b07  mov     rax, [rax+8]
0x180015b0b  call    _guard_dispatch_icall
0x180015b10  or      eax, 0FFFFFFFFh
0x180015b13  lock xadd [rdi+0Ch], eax
0x180015b18  cmp     eax, 1
0x180015b1b  jnz     short loc_180015B2C
0x180015b1d  mov     rax, [rdi]
0x180015b20  mov     rcx, rdi
0x180015b23  mov     rax, [rax+10h]
0x180015b27  call    _guard_dispatch_icall
0x180015b2c  cmp     [rbx+28h], r12d
0x180015b30  jnz     short loc_180015B3B
0x180015b32  lea     rdx, [rbx+88h]
0x180015b39  jmp     short loc_180015B46
0x180015b3b  mov     rax, [rbx+48h]
0x180015b3f  mov     rdx, [rax]
0x180015b42  add     rdx, 30h ; '0'
0x180015b46  mov     ecx, [rdx]
0x180015b48  shr     ecx, 1
0x180015b4a  cmp     ecx, r13d
0x180015b4d  ja      short loc_180015B55
0x180015b4f  movzx   r8d, cx
0x180015b53  jmp     short loc_180015B58
0x180015b55  mov     r8d, r13d
0x180015b58  mov     eax, r12d
0x180015b5b  cmovbe  ax, r8w
0x180015b60  mov     r8, r12
0x180015b63  test    ax, ax
0x180015b66  jz      short loc_180015B6C
0x180015b68  mov     r8, [rdx+8]
0x180015b6c  mov     r9, [rbx+78h]
0x180015b70  mov     ecx, [r9]
0x180015b73  shr     ecx, 1
0x180015b75  cmp     ecx, r13d
0x180015b78  ja      short loc_180015B7F
0x180015b7a  movzx   edx, cx
0x180015b7d  jmp     short loc_180015B82
0x180015b7f  mov     edx, r13d
0x180015b82  mov     eax, r12d
0x180015b85  cmovbe  ax, dx
0x180015b89  test    ax, ax
0x180015b8c  jnz     short loc_180015B93
0x180015b8e  mov     r9, r12
0x180015b91  jmp     short loc_180015B97
0x180015b93  mov     r9, [r9+8]
0x180015b97  mov     dword ptr [rsp+70h+var_48], r14d
0x180015b9c  mov     [rsp+70h+Timeout], r8
0x180015ba1  lea     r8, aVirtualenviron_7; "VirtualEnvironmentManager::TerminateAll"...
0x180015ba8  jmp     loc_180015CAD
0x180015bad  cmp     [rbx+28h], r12d
0x180015bb1  jnz     short loc_180015BBC
0x180015bb3  lea     rdx, [rbx+88h]
0x180015bba  jmp     short loc_180015BC7
0x180015bbc  mov     rax, [rbx+48h]
0x180015bc0  mov     rdx, [rax]
0x180015bc3  add     rdx, 30h ; '0'
0x180015bc7  mov     ecx, [rdx]
0x180015bc9  shr     ecx, 1
0x180015bcb  cmp     ecx, r13d
0x180015bce  ja      short loc_180015BD6
0x180015bd0  movzx   r8d, cx
0x180015bd4  jmp     short loc_180015BD9
0x180015bd6  mov     r8d, r13d
0x180015bd9  mov     eax, r12d
0x180015bdc  mov     r9, r12
0x180015bdf  cmovbe  ax, r8w
0x180015be4  test    ax, ax
0x180015be7  jz      short loc_180015BED
0x180015be9  mov     r9, [rdx+8]
0x180015bed  mov     r8, [rbx+78h]
0x180015bf1  mov     ecx, [r8]
0x180015bf4  shr     ecx, 1
0x180015bf6  cmp     ecx, r13d
0x180015bf9  ja      short loc_180015C00
0x180015bfb  movzx   edx, cx
0x180015bfe  jmp     short loc_180015C03
0x180015c00  mov     edx, r13d
0x180015c03  mov     eax, r12d
0x180015c06  cmovbe  ax, dx
0x180015c0a  test    ax, ax
0x180015c0d  jnz     short loc_180015C14
0x180015c0f  mov     r8, r12
0x180015c12  jmp     short loc_180015C18
0x180015c14  mov     r8, [r8+8]
0x180015c18  lea     rdx, [rbp+var_20]
0x180015c1c  mov     dword ptr [rsp+70h+Timeout], r12d
0x180015c21  call    ?TerminateProcesses@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEBV?$doubly_linked_list@KUvemgr_pool_info@vemgr@@@kernel@shared@appv@@PEB_W1K@Z; VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::TerminateProcesses(appv::shared::kernel::doubly_linked_list<ulong,vemgr::vemgr_pool_info> const &,wchar_t const *,wchar_t const *,ulong)
0x180015c26  mov     r14d, eax
0x180015c29  test    eax, eax
0x180015c2b  jns     loc_180015CB7
0x180015c31  cmp     [rbx+28h], r12d
0x180015c35  jnz     short loc_180015C40
0x180015c37  lea     rdx, [rbx+88h]
0x180015c3e  jmp     short loc_180015C4B
0x180015c40  mov     rax, [rbx+48h]
0x180015c44  mov     rdx, [rax]
0x180015c47  add     rdx, 30h ; '0'
0x180015c4b  mov     ecx, [rdx]
0x180015c4d  shr     ecx, 1
0x180015c4f  cmp     ecx, r13d
0x180015c52  ja      short loc_180015C5A
0x180015c54  movzx   r8d, cx
0x180015c58  jmp     short loc_180015C5D
0x180015c5a  mov     r8d, r13d
0x180015c5d  mov     eax, r12d
0x180015c60  cmovbe  ax, r8w
0x180015c65  mov     r8, r12
0x180015c68  test    ax, ax
0x180015c6b  jz      short loc_180015C71
0x180015c6d  mov     r8, [rdx+8]
0x180015c71  mov     r9, [rbx+78h]
0x180015c75  mov     ecx, [r9]
0x180015c78  shr     ecx, 1
0x180015c7a  cmp     ecx, r13d
0x180015c7d  ja      short loc_180015C84
0x180015c7f  movzx   edx, cx
0x180015c82  jmp     short loc_180015C87
0x180015c84  mov     edx, r13d
0x180015c87  mov     eax, r12d
0x180015c8a  cmovbe  ax, dx
0x180015c8e  test    ax, ax
0x180015c91  jnz     short loc_180015C98
0x180015c93  mov     r9, r12
0x180015c96  jmp     short loc_180015C9C
0x180015c98  mov     r9, [r9+8]
0x180015c9c  mov     dword ptr [rsp+70h+var_48], r14d
0x180015ca1  mov     [rsp+70h+Timeout], r8
0x180015ca6  lea     r8, aVirtualenviron_3; "VirtualEnvironmentManager::TerminateAll"...
0x180015cad  xor     edx, edx
0x180015caf  lea     ecx, [rdx+1]
0x180015cb2  call    LogWrite
0x180015cb7  mov     rcx, [rsi]
0x180015cba  lea     rdx, [rbp+var_40]
0x180015cbe  test    r14d, r14d
0x180015cc1  cmovns  r14d, r15d
0x180015cc5  mov     r15d, r14d
0x180015cc8  call    ?FirstVirtualEnvironment@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FirstVirtualEnvironment(kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x180015ccd  mov     rcx, [rbp+P]; P
0x180015cd1  mov     edi, eax
0x180015cd3  lea     rax, [rbp+var_18]
0x180015cd7  cmp     rcx, rax
0x180015cda  jz      short loc_180015D02
0x180015cdc  mov     rdx, [rcx+8]
0x180015ce0  mov     rbx, [rcx+10h]
0x180015ce4  mov     [rdx+10h], rbx
0x180015ce8  mov     [rbx+8], rdx
0x180015cec  xor     edx, edx; Tag
0x180015cee  call    cs:__imp_ExFreePoolWithTag
0x180015cf5  nop     dword ptr [rax+rax+00h]
0x180015cfa  dec     [rbp+var_20]
0x180015cfd  mov     rcx, rbx
0x180015d00  jmp     short loc_180015CD3
0x180015d02  test    edi, edi
0x180015d04  jns     loc_1800159F6
0x180015d0a  mov     rcx, [rsi+10h]
0x180015d0e  mov     rcx, [rcx]; Table
0x180015d11  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x180015d18  nop     dword ptr [rax+rax+00h]
0x180015d1d  test    eax, eax
0x180015d1f  jz      short loc_180015D57
0x180015d21  mov     rbx, [rsi+10h]
0x180015d25  mov     rcx, [rbx]
0x180015d28  test    rcx, rcx
0x180015d2b  jz      short loc_180015D57
0x180015d2d  jmp     short loc_180015D44
0x180015d2f  mov     rcx, [rbx]; Table
0x180015d32  mov     rdx, rax; Buffer
0x180015d35  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180015d3c  nop     dword ptr [rax+rax+00h]
0x180015d41  mov     rcx, [rbx]; Table
0x180015d44  mov     dl, 1; Restart
0x180015d46  call    cs:__imp_RtlEnumerateGenericTableAvl
0x180015d4d  nop     dword ptr [rax+rax+00h]
0x180015d52  test    rax, rax
0x180015d55  jnz     short loc_180015D2F
0x180015d57  mov     rbx, qword ptr [rbp+var_40+8]
0x180015d5b  test    rbx, rbx
0x180015d5e  jz      short loc_180015D98
0x180015d60  or      eax, 0FFFFFFFFh
0x180015d63  lock xadd [rbx+8], eax
0x180015d68  cmp     eax, 1
0x180015d6b  jnz     short loc_180015D98
0x180015d6d  mov     rax, [rbx]
0x180015d70  mov     rcx, rbx
0x180015d73  mov     rax, [rax+8]
0x180015d77  call    _guard_dispatch_icall
0x180015d7c  or      edx, 0FFFFFFFFh
0x180015d7f  lock xadd [rbx+0Ch], edx
0x180015d84  cmp     edx, 1
0x180015d87  jnz     short loc_180015D98
0x180015d89  mov     rdx, [rbx]
  ... truncated ...
```
