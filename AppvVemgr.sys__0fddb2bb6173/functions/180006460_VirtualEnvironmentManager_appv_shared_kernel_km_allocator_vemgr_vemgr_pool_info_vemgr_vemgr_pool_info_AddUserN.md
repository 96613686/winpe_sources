# VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddUserNotification(appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info> const &)

- ea: `0x180006460`
- end: `0x1800066a5`
- name: `?AddUserNotification@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAXAEBV?$doubly_linked_list@V?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z`
- size: `581`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800062bc`

## callees

- `0x180003558`
- `0x1800040dc`
- `0x180006460`
- `0x180007f88`
- `0x18001b3cc`

## string_xrefs

- `0x1800065c7`: `VFSNotification::AddUser() - VFS notification: add user configuration. package moniker %s. group moniker %s. user sid %s. Number of mappings %d. Result %d.`
- `0x18000668d`: `VFSNotification::AddUser() - Failed: VFS notification: add user configuration. package moniker %s. group moniker %s. user sid %s. Number of mappings %d. Result %d.`

## pseudocode

```c
void __fastcall VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddUserNotification(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rcx
  __int64 **v5; // rbx
  __int64 **v6; // r12
  __int64 *v7; // rdi
  int v8; // r11d
  _DWORD *v9; // r14
  __int64 v10; // rax
  _DWORD *v11; // rdx
  unsigned int v12; // ecx
  __int16 v13; // dx
  __int16 v14; // ax
  __int64 v15; // r10
  unsigned int v16; // ecx
  __int16 v17; // dx
  __int64 v18; // r8
  __int16 v19; // ax
  unsigned int v20; // ecx
  __int16 v21; // dx
  __int16 v22; // ax
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rdx
  __int16 v27; // dx
  __int16 v28; // ax
  __int64 v29; // r10
  unsigned int v30; // ecx
  __int16 v31; // dx
  __int16 v32; // ax
  __int64 v33; // r8
  unsigned int v34; // ecx
  __int16 v35; // dx
  __int16 v36; // ax
  __int64 v37; // r9
  int v38; // [rsp+28h] [rbp-60h]
  char v39; // [rsp+90h] [rbp+8h] BYREF

  v4 = *(_QWORD *)(a1 + 56);
  v39 = 0;
  if ( (int)ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsVfsStateDisabled(
              v4,
              &v39) >= 0
    && v39 )
  {
    LogWrite(
      4,
      0,
      L"VirtualEnvironmentManager::AddUserNotification() - User add operation not sent to VFS because the VFS has been set to disabled.");
  }
  else
  {
    v5 = *(__int64 ***)(a2 + 32);
    v6 = (__int64 **)(a2 + 8);
    while ( v5 != v6 )
    {
      v7 = *v5;
      v8 = 0;
      v9 = *v5 + 13;
      if ( *v9 )
      {
        if ( *((_DWORD *)v7 + 4) > 2u || (v10 = v7[1]) == 0 || !*(_DWORD *)(v10 + 8) || (v11 = (_DWORD *)*v7) == 0 )
          v11 = v7 + 2;
        v8 = VFSNotification<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::send_add_ioctl<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const>(
               *(_QWORD *)(a1 + 32),
               (__int64)v11,
               (const void *)v7[12],
               *((_DWORD *)v7 + 20),
               (__int64)(*v5 + 13),
               v38);
      }
      v12 = *((_DWORD *)v7 + 12) >> 1;
      if ( v8 < 0 )
      {
        if ( v12 > 0xFFFF )
          v27 = -1;
        else
          v27 = *((_DWORD *)v7 + 12) >> 1;
        v28 = 0;
        LODWORD(v29) = 0;
        if ( v12 <= 0xFFFF )
          v28 = v27;
        if ( v28 )
          v29 = v7[7];
        v30 = *((_DWORD *)v7 + 4) >> 1;
        if ( v30 > 0xFFFF )
          v31 = -1;
        else
          v31 = *((_DWORD *)v7 + 4) >> 1;
        v32 = 0;
        v33 = 0;
        if ( v30 <= 0xFFFF )
          v32 = v31;
        if ( v32 )
          v33 = v7[3];
        v34 = *(_DWORD *)*v7 >> 1;
        if ( v34 > 0xFFFF )
          v35 = -1;
        else
          v35 = *(_DWORD *)*v7 >> 1;
        v36 = 0;
        if ( v34 <= 0xFFFF )
          v36 = v35;
        if ( v36 )
          v37 = *(_QWORD *)(*v7 + 8);
        else
          v37 = 0;
        v38 = v29;
        LogWrite(
          1,
          0,
          L"VFSNotification::AddUser() - Failed: VFS notification: add user configuration. package moniker %s. group monik"
           "er %s. user sid %s. Number of mappings %d. Result %d.",
          v37,
          v33);
      }
      else
      {
        if ( v12 > 0xFFFF )
          v13 = -1;
        else
          v13 = *((_DWORD *)v7 + 12) >> 1;
        v14 = 0;
        LODWORD(v15) = 0;
        if ( v12 <= 0xFFFF )
          v14 = v13;
        if ( v14 )
          v15 = v7[7];
        v16 = *((_DWORD *)v7 + 4) >> 1;
        if ( v16 > 0xFFFF )
          v17 = -1;
        else
          v17 = *((_DWORD *)v7 + 4) >> 1;
        v18 = 0;
        v19 = 0;
        if ( v16 <= 0xFFFF )
          v19 = v17;
        if ( v19 )
          v18 = v7[3];
        v20 = *(_DWORD *)*v7 >> 1;
        if ( v20 > 0xFFFF )
          v21 = -1;
        else
          v21 = *(_DWORD *)*v7 >> 1;
        v22 = 0;
        if ( v20 <= 0xFFFF )
          v22 = v21;
        if ( v22 )
          v23 = *(_QWORD *)(*v7 + 8);
        else
          v23 = 0;
        v38 = v15;
        LogWrite(
          3,
          0,
          L"VFSNotification::AddUser() - VFS notification: add user configuration. package moniker %s. group moniker %s. u"
           "ser sid %s. Number of mappings %d. Result %d.",
          v23,
          v18);
        if ( *((_DWORD *)v7 + 4) > 2u || (v25 = v7[1]) == 0 || !*(_DWORD *)(v25 + 8) || (v26 = *v7) == 0 )
          v26 = (__int64)(v7 + 2);
        VFSNotification<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::log_user_mappings<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
          v24,
          v26,
          (__int64)(v7 + 6),
          (__int64)v9);
      }
      v5 = (__int64 **)v5[3];
    }
  }
}

```

## disassembly

```asm
0x180006460  mov     rax, rsp
0x180006463  push    rbx
0x180006464  push    rbp
0x180006465  push    rsi
0x180006466  push    rdi
0x180006467  push    r12
0x180006469  push    r13
0x18000646b  push    r14
0x18000646d  push    r15
0x18000646f  sub     rsp, 48h
0x180006473  mov     rdi, rdx
0x180006476  mov     r13, rcx
0x180006479  mov     rcx, [rcx+38h]
0x18000647d  lea     rdx, [rax+8]
0x180006481  xor     esi, esi
0x180006483  mov     [rax+8], sil
0x180006487  call    ?IsVfsStateDisabled@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEA_N@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsVfsStateDisabled(bool &)
0x18000648c  test    eax, eax
0x18000648e  js      short loc_1800064BD
0x180006490  cmp     [rsp+88h+arg_0], sil
0x180006498  jz      short loc_1800064BD
0x18000649a  lea     r8, aVirtualenviron_8; "VirtualEnvironmentManager::AddUserNotif"...
0x1800064a1  xor     edx, edx
0x1800064a3  lea     ecx, [rsi+4]
0x1800064a6  call    LogWrite
0x1800064ab  add     rsp, 48h
0x1800064af  pop     r15
0x1800064b1  pop     r14
0x1800064b3  pop     r13
0x1800064b5  pop     r12
0x1800064b7  pop     rdi
0x1800064b8  pop     rsi
0x1800064b9  pop     rbp
0x1800064ba  pop     rbx
0x1800064bb  retn
0x1800064bd  mov     rbx, [rdi+20h]
0x1800064c1  lea     r12, [rdi+8]
0x1800064c5  mov     r9d, 0FFFFh
0x1800064cb  cmp     rbx, r12
0x1800064ce  jz      short loc_1800064AB
0x1800064d0  mov     rdi, [rbx]
0x1800064d3  mov     r11d, esi
0x1800064d6  lea     r14, [rdi+68h]
0x1800064da  cmp     [r14], esi
0x1800064dd  jz      short loc_180006523
0x1800064df  cmp     dword ptr [rdi+10h], 2
0x1800064e3  mov     r10, [r13+20h]
0x1800064e7  mov     r9d, [rdi+50h]
0x1800064eb  mov     r8, [rdi+60h]
0x1800064ef  ja      short loc_180006509
0x1800064f1  mov     rax, [rdi+8]
0x1800064f5  test    rax, rax
0x1800064f8  jz      short loc_180006509
0x1800064fa  mov     eax, [rax+8]
0x1800064fd  test    eax, eax
0x1800064ff  jz      short loc_180006509
0x180006501  mov     rdx, [rdi]
0x180006504  test    rdx, rdx
0x180006507  jnz     short loc_18000650D
0x180006509  lea     rdx, [rdi+10h]
0x18000650d  mov     rcx, r10
0x180006510  mov     [rsp+88h+var_68], r14
0x180006515  call    ??$send_add_ioctl@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@$$CBV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@234@@?$VFSNotification@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@PEAXKAEBV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@234@G@Z; VFSNotification<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::send_add_ioctl<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,void *,ulong,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &,ushort)
0x18000651a  mov     r11d, eax
0x18000651d  mov     r9d, 0FFFFh
0x180006523  mov     ecx, [rdi+30h]
0x180006526  mov     ebp, [r14]
0x180006529  shr     ecx, 1
0x18000652b  test    r11d, r11d
0x18000652e  js      loc_180006609
0x180006534  cmp     ecx, r9d
0x180006537  ja      short loc_18000653E
0x180006539  movzx   edx, cx
0x18000653c  jmp     short loc_180006541
0x18000653e  mov     edx, r9d
0x180006541  mov     eax, esi
0x180006543  mov     r10, rsi
0x180006546  cmovbe  ax, dx
0x18000654a  test    ax, ax
0x18000654d  jz      short loc_180006553
0x18000654f  mov     r10, [rdi+38h]
0x180006553  lea     rsi, [rdi+10h]
0x180006557  mov     ecx, [rsi]
0x180006559  shr     ecx, 1
0x18000655b  cmp     ecx, r9d
0x18000655e  ja      short loc_180006565
0x180006560  movzx   edx, cx
0x180006563  jmp     short loc_180006568
0x180006565  mov     edx, r9d
0x180006568  xor     r8d, r8d
0x18000656b  cmp     ecx, r9d
0x18000656e  mov     eax, r8d
0x180006571  cmovbe  ax, dx
0x180006575  test    ax, ax
0x180006578  jz      short loc_18000657E
0x18000657a  mov     r8, [rsi+8]
0x18000657e  mov     r9, [rdi]
0x180006581  mov     eax, 0FFFFh
0x180006586  mov     ecx, [r9]
0x180006589  shr     ecx, 1
0x18000658b  cmp     ecx, eax
0x18000658d  ja      short loc_180006594
0x18000658f  movzx   edx, cx
0x180006592  jmp     short loc_180006596
0x180006594  mov     edx, eax
0x180006596  xor     eax, eax
0x180006598  cmp     ecx, 0FFFFh
0x18000659e  cmovbe  ax, dx
0x1800065a2  xor     ecx, ecx
0x1800065a4  test    ax, ax
0x1800065a7  jnz     short loc_1800065AE
0x1800065a9  mov     r9d, ecx
0x1800065ac  jmp     short loc_1800065B2
0x1800065ae  mov     r9, [r9+8]
0x1800065b2  mov     [rsp+88h+var_50], r11d
0x1800065b7  xor     edx, edx
0x1800065b9  mov     [rsp+88h+var_58], ebp
0x1800065bd  mov     [rsp+88h+var_60], r10
0x1800065c2  mov     [rsp+88h+var_68], r8
0x1800065c7  lea     r8, aVfsnotificatio_3; "VFSNotification::AddUser() - VFS notifi"...
0x1800065ce  lea     ecx, [rdx+3]
0x1800065d1  call    LogWrite
0x1800065d6  cmp     dword ptr [rsi], 2
0x1800065d9  ja      short loc_1800065F3
0x1800065db  mov     rax, [rdi+8]
0x1800065df  test    rax, rax
0x1800065e2  jz      short loc_1800065F3
0x1800065e4  mov     eax, [rax+8]
0x1800065e7  test    eax, eax
0x1800065e9  jz      short loc_1800065F3
0x1800065eb  mov     rdx, [rdi]
0x1800065ee  test    rdx, rdx
0x1800065f1  jnz     short loc_1800065F6
0x1800065f3  mov     rdx, rsi
0x1800065f6  mov     r9, r14
0x1800065f9  lea     r8, [rdi+30h]
0x1800065fd  call    ??$log_user_mappings@V?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@U?$km_allocator@Uvemgr_pool_info@vemgr@@@234@@?$VFSNotification@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAXAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@0AEBV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@234@@Z; VFSNotification<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::log_user_mappings<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &)
0x180006602  xor     esi, esi
0x180006604  jmp     loc_18000669C
0x180006609  cmp     ecx, r9d
0x18000660c  ja      short loc_180006613
0x18000660e  movzx   edx, cx
0x180006611  jmp     short loc_180006616
0x180006613  mov     edx, r9d
0x180006616  mov     eax, esi
0x180006618  mov     r10, rsi
0x18000661b  cmovbe  ax, dx
0x18000661f  test    ax, ax
0x180006622  jz      short loc_180006628
0x180006624  mov     r10, [rdi+38h]
0x180006628  mov     ecx, [rdi+10h]
0x18000662b  shr     ecx, 1
0x18000662d  cmp     ecx, r9d
0x180006630  ja      short loc_180006637
0x180006632  movzx   edx, cx
0x180006635  jmp     short loc_18000663A
0x180006637  mov     edx, r9d
0x18000663a  mov     eax, esi
0x18000663c  mov     r8, rsi
0x18000663f  cmovbe  ax, dx
0x180006643  test    ax, ax
0x180006646  jz      short loc_18000664C
0x180006648  mov     r8, [rdi+18h]
0x18000664c  mov     r9, [rdi]
0x18000664f  mov     edi, 0FFFFh
0x180006654  mov     ecx, [r9]
0x180006657  shr     ecx, 1
0x180006659  cmp     ecx, edi
0x18000665b  ja      short loc_180006662
0x18000665d  movzx   edx, cx
0x180006660  jmp     short loc_180006664
0x180006662  mov     edx, edi
0x180006664  mov     eax, esi
0x180006666  cmovbe  ax, dx
0x18000666a  test    ax, ax
0x18000666d  jnz     short loc_180006674
0x18000666f  mov     r9, rsi
0x180006672  jmp     short loc_180006678
0x180006674  mov     r9, [r9+8]
0x180006678  mov     [rsp+88h+var_50], r11d
0x18000667d  xor     edx, edx
0x18000667f  mov     [rsp+88h+var_58], ebp
0x180006683  mov     [rsp+88h+var_60], r10
0x180006688  mov     [rsp+88h+var_68], r8
0x18000668d  lea     r8, aVfsnotificatio; "VFSNotification::AddUser() - Failed: VF"...
0x180006694  lea     ecx, [rdx+1]
0x180006697  call    LogWrite
0x18000669c  mov     rbx, [rbx+18h]
0x1800066a0  jmp     loc_1800064C5
```
