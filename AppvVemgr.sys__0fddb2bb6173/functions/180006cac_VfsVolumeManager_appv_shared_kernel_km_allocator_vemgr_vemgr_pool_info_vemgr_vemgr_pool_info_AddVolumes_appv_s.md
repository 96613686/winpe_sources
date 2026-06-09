# VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddVolumes(appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &)

- ea: `0x180006cac`
- end: `0x180006ee4`
- name: `?AddVolumes@?$VfsVolumeManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(PRKMUTEX *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800062bc`

## callees

- `0x180006880`
- `0x180006cac`
- `0x180009208`
- `0x18000c694`
- `0x18001b3cc`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x180006ec4`
- `ntoskrnl!KeReleaseMutex` at `0x180006ec4`
- `ntoskrnl!KeWaitForSingleObject` at `0x180006ce8`
- `ntoskrnl!KeWaitForSingleObject` at `0x180006ce8`

## string_xrefs

- `0x180006eb3`: `VfsVolumeManager::AddVolumes() - Failed to remove volume reference from tracker. Volume: %s. Error: %d`

## pseudocode

```c
__int64 __fastcall VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddVolumes(
        PRKMUTEX *a1,
        __int64 a2)
{
  PRKMUTEX v3; // rcx
  _QWORD *v6; // rbx
  _QWORD *v7; // rbp
  int v8; // esi
  volatile signed __int32 *v9; // rdi
  unsigned int v10; // ecx
  __int16 v11; // dx
  __int16 v12; // ax
  __int64 v13; // r9
  volatile signed __int32 *v14; // rdi
  unsigned int v15; // ecx
  __int16 v16; // dx
  __int16 v17; // ax
  __int64 v18; // r9
  int v19; // r8d
  unsigned int v20; // ecx
  __int16 v21; // dx
  __int16 v22; // ax
  __int64 v23; // r9
  __int64 v24; // [rsp+20h] [rbp-68h]
  __int64 v25; // [rsp+20h] [rbp-68h]
  __int64 v26; // [rsp+20h] [rbp-68h]
  __int128 v27; // [rsp+30h] [rbp-58h] BYREF
  union _LARGE_INTEGER v28; // [rsp+90h] [rbp+8h] BYREF

  v3 = *a1;
  if ( v3 )
  {
    v28.QuadPart = -300000000;
    if ( KeWaitForSingleObject(v3, Executive, 0, 0, &v28) )
      return 3221225653LL;
  }
  v6 = *(_QWORD **)(a2 + 32);
  v7 = (_QWORD *)(a2 + 8);
  while ( 1 )
  {
    if ( v6 == v7 )
    {
      v8 = 0;
      goto LABEL_46;
    }
    v27 = 0;
    if ( !(unsigned __int8)appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::iless_predicate,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVolume<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>>::find(
                             a1 + 2,
                             v6,
                             &v27) )
      break;
    ++*(_DWORD *)(v27 + 40);
LABEL_9:
    v9 = (volatile signed __int32 *)*((_QWORD *)&v27 + 1);
    if ( *((_QWORD *)&v27 + 1) && !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v27 + 1) + 8LL)) )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
      if ( !_InterlockedDecrement(v9 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
    }
    v6 = (_QWORD *)v6[3];
  }
  v8 = VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddVolumeImpl(
         a1,
         *v6);
  if ( v8 >= 0 )
    goto LABEL_9;
  v10 = *(_DWORD *)*v6 >> 1;
  if ( v10 > 0xFFFF )
    v11 = -1;
  else
    v11 = *(_DWORD *)*v6 >> 1;
  v12 = 0;
  if ( v10 <= 0xFFFF )
    v12 = v11;
  if ( v12 )
    v13 = *(_QWORD *)(*v6 + 8LL);
  else
    v13 = 0;
  LODWORD(v24) = 1;
  LogWrite(
    1,
    0,
    L"VfsVolumeManager::AddVolume() - Failed to add volume reference to tracker. Volume: %s. Reference Count: %d. Error: %d",
    v13,
    v24,
    v8);
  v14 = (volatile signed __int32 *)*((_QWORD *)&v27 + 1);
  if ( *((_QWORD *)&v27 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v27 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
  v15 = *(_DWORD *)*v6 >> 1;
  if ( v15 > 0xFFFF )
    v16 = -1;
  else
    v16 = *(_DWORD *)*v6 >> 1;
  v17 = 0;
  if ( v15 <= 0xFFFF )
    v17 = v16;
  if ( v17 )
    v18 = *(_QWORD *)(*v6 + 8LL);
  else
    v18 = 0;
  LODWORD(v25) = v8;
  LogWrite(
    1,
    0,
    L"VfsVolumeManager::AddVolumes() - Failed to add volume reference to tracker. Volume: %s. Error: %d",
    v18,
    v25);
  while ( 1 )
  {
    v6 = (_QWORD *)v6[2];
    if ( v6 == v7 )
      break;
    v19 = VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVolume(
            a1,
            v6);
    v20 = *(_DWORD *)*v6 >> 1;
    if ( v20 > 0xFFFF )
      v21 = -1;
    else
      v21 = *(_DWORD *)*v6 >> 1;
    v22 = 0;
    if ( v20 <= 0xFFFF )
      v22 = v21;
    if ( v22 )
      v23 = *(_QWORD *)(*v6 + 8LL);
    else
      v23 = 0;
    LODWORD(v26) = v19;
    LogWrite(
      1,
      0,
      L"VfsVolumeManager::AddVolumes() - Failed to remove volume reference from tracker. Volume: %s. Error: %d",
      v23,
      v26);
  }
LABEL_46:
  KeReleaseMutex(*a1, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180006cac  mov     r11, rsp
0x180006caf  push    rbx
0x180006cb0  push    rbp
0x180006cb1  push    rsi
0x180006cb2  push    rdi
0x180006cb3  push    r12
0x180006cb5  push    r13
0x180006cb7  push    r14
0x180006cb9  push    r15
0x180006cbb  sub     rsp, 48h
0x180006cbf  mov     r14, rcx
0x180006cc2  xor     r15d, r15d
0x180006cc5  mov     rcx, [rcx]; Object
0x180006cc8  mov     rdi, rdx
0x180006ccb  test    rcx, rcx
0x180006cce  jz      short loc_180006D02
0x180006cd0  lea     rax, [r11+8]
0x180006cd4  mov     qword ptr [r11+8], 0FFFFFFFFEE1E5D00h
0x180006cdc  xor     r9d, r9d; Alertable
0x180006cdf  mov     [r11-68h], rax
0x180006ce3  xor     r8d, r8d; WaitMode
0x180006ce6  xor     edx, edx; WaitReason
0x180006ce8  call    cs:__imp_KeWaitForSingleObject
0x180006cef  nop     dword ptr [rax+rax+00h]
0x180006cf4  test    eax, eax
0x180006cf6  jz      short loc_180006D02
0x180006cf8  mov     eax, 0C00000B5h
0x180006cfd  jmp     loc_180006ED2
0x180006d02  mov     rbx, [rdi+20h]
0x180006d06  lea     rbp, [rdi+8]
0x180006d0a  or      r12d, 0FFFFFFFFh
0x180006d0e  cmp     rbx, rbp
0x180006d11  jz      loc_180006EBC
0x180006d17  xorps   xmm0, xmm0
0x180006d1a  lea     rcx, [r14+10h]
0x180006d1e  lea     r8, [rsp+88h+var_58]
0x180006d23  mov     rdx, rbx
0x180006d26  movdqu  [rsp+88h+var_58], xmm0
0x180006d2c  call    ?find@?$indexed_avl_tree@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uiless_predicate@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@234@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@V?$shared_ptr@V?$CountedVolume@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$VfsVolumeManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@8@@kernel@shared@appv@@QEAA_NAEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEAV?$shared_ptr@V?$CountedVolume@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$VfsVolumeManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@6@@Z; appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::iless_predicate,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVolume<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>>::find(kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &,kernel_std::shared_ptr<VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVolume<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> &)
0x180006d31  test    al, al
0x180006d33  jz      short loc_180006D3F
0x180006d35  mov     rax, qword ptr [rsp+88h+var_58]
0x180006d3a  inc     dword ptr [rax+28h]
0x180006d3d  jmp     short loc_180006D50
0x180006d3f  mov     rdx, [rbx]
0x180006d42  mov     rcx, r14
0x180006d45  call    ?AddVolumeImpl@?$VfsVolumeManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddVolumeImpl(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)
0x180006d4a  mov     esi, eax
0x180006d4c  test    eax, eax
0x180006d4e  js      short loc_180006D9B
0x180006d50  mov     rdi, qword ptr [rsp+88h+var_58+8]
0x180006d55  test    rdi, rdi
0x180006d58  jz      short loc_180006D92
0x180006d5a  mov     eax, r12d
0x180006d5d  lock xadd [rdi+8], eax
0x180006d62  add     eax, r12d
0x180006d65  jnz     short loc_180006D92
0x180006d67  mov     rax, [rdi]
0x180006d6a  mov     rcx, rdi
0x180006d6d  mov     rax, [rax+8]
0x180006d71  call    _guard_dispatch_icall
0x180006d76  mov     eax, r12d
0x180006d79  lock xadd [rdi+0Ch], eax
0x180006d7e  add     eax, r12d
0x180006d81  jnz     short loc_180006D92
0x180006d83  mov     rax, [rdi]
0x180006d86  mov     rcx, rdi
0x180006d89  mov     rax, [rax+10h]
0x180006d8d  call    _guard_dispatch_icall
0x180006d92  mov     rbx, [rbx+18h]
0x180006d96  jmp     loc_180006D0E
0x180006d9b  mov     r9, [rbx]
0x180006d9e  mov     r13d, 0FFFFh
0x180006da4  mov     ecx, [r9]
0x180006da7  shr     ecx, 1
0x180006da9  cmp     ecx, r13d
0x180006dac  ja      short loc_180006DB3
0x180006dae  movzx   edx, cx
0x180006db1  jmp     short loc_180006DB6
0x180006db3  mov     edx, r13d
0x180006db6  mov     eax, r15d
0x180006db9  cmovbe  ax, dx
0x180006dbd  test    ax, ax
0x180006dc0  jnz     short loc_180006DC7
0x180006dc2  mov     r9, r15
0x180006dc5  jmp     short loc_180006DCB
0x180006dc7  mov     r9, [r9+8]
0x180006dcb  xor     edx, edx
0x180006dcd  mov     [rsp+88h+var_60], esi
0x180006dd1  lea     r8, aVfsvolumemanag_9; "VfsVolumeManager::AddVolume() - Failed "...
0x180006dd8  mov     dword ptr [rsp+88h+var_68], 1
0x180006de0  lea     ecx, [rdx+1]
0x180006de3  call    LogWrite
0x180006de8  mov     rdi, qword ptr [rsp+88h+var_58+8]
0x180006ded  test    rdi, rdi
0x180006df0  jz      short loc_180006E2A
0x180006df2  mov     eax, r12d
0x180006df5  lock xadd [rdi+8], eax
0x180006dfa  add     eax, r12d
0x180006dfd  jnz     short loc_180006E2A
0x180006dff  mov     rax, [rdi]
0x180006e02  mov     rcx, rdi
0x180006e05  mov     rax, [rax+8]
0x180006e09  call    _guard_dispatch_icall
0x180006e0e  mov     eax, r12d
0x180006e11  lock xadd [rdi+0Ch], eax
0x180006e16  add     eax, r12d
0x180006e19  jnz     short loc_180006E2A
0x180006e1b  mov     rax, [rdi]
0x180006e1e  mov     rcx, rdi
0x180006e21  mov     rax, [rax+10h]
0x180006e25  call    _guard_dispatch_icall
0x180006e2a  mov     r9, [rbx]
0x180006e2d  mov     ecx, [r9]
0x180006e30  shr     ecx, 1
0x180006e32  cmp     ecx, r13d
0x180006e35  ja      short loc_180006E3C
0x180006e37  movzx   edx, cx
0x180006e3a  jmp     short loc_180006E3F
0x180006e3c  mov     edx, r13d
0x180006e3f  mov     eax, r15d
0x180006e42  cmovbe  ax, dx
0x180006e46  test    ax, ax
0x180006e49  jnz     short loc_180006E50
0x180006e4b  mov     r9, r15
0x180006e4e  jmp     short loc_180006E54
0x180006e50  mov     r9, [r9+8]
0x180006e54  mov     dword ptr [rsp+88h+var_68], esi
0x180006e58  lea     r8, aVfsvolumemanag_6; "VfsVolumeManager::AddVolumes() - Failed"...
0x180006e5f  mov     edi, 1
0x180006e64  xor     edx, edx
0x180006e66  mov     ecx, edi
0x180006e68  call    LogWrite
0x180006e6d  mov     rbx, [rbx+10h]
0x180006e71  cmp     rbx, rbp
0x180006e74  jz      short loc_180006EBF
0x180006e76  mov     rdx, rbx
0x180006e79  mov     rcx, r14
0x180006e7c  call    ?RemoveVolume@?$VfsVolumeManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEBV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@@Z; VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveVolume(kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> const &)
0x180006e81  mov     r9, [rbx]
0x180006e84  mov     r8d, eax
0x180006e87  mov     ecx, [r9]
0x180006e8a  shr     ecx, 1
0x180006e8c  cmp     ecx, r13d
0x180006e8f  ja      short loc_180006E96
0x180006e91  movzx   edx, cx
0x180006e94  jmp     short loc_180006E99
0x180006e96  mov     edx, r13d
0x180006e99  mov     eax, r15d
0x180006e9c  cmovbe  ax, dx
0x180006ea0  test    ax, ax
0x180006ea3  jnz     short loc_180006EAA
0x180006ea5  mov     r9, r15
0x180006ea8  jmp     short loc_180006EAE
0x180006eaa  mov     r9, [r9+8]
0x180006eae  mov     dword ptr [rsp+88h+var_68], r8d
0x180006eb3  lea     r8, aVfsvolumemanag_0; "VfsVolumeManager::AddVolumes() - Failed"...
0x180006eba  jmp     short loc_180006E64
0x180006ebc  mov     esi, r15d
0x180006ebf  mov     rcx, [r14]; Mutex
0x180006ec2  xor     edx, edx; Wait
0x180006ec4  call    cs:__imp_KeReleaseMutex
0x180006ecb  nop     dword ptr [rax+rax+00h]
0x180006ed0  mov     eax, esi
0x180006ed2  add     rsp, 48h
0x180006ed6  pop     r15
0x180006ed8  pop     r14
0x180006eda  pop     r13
0x180006edc  pop     r12
0x180006ede  pop     rdi
0x180006edf  pop     rsi
0x180006ee0  pop     rbp
0x180006ee1  pop     rbx
0x180006ee2  retn
```
