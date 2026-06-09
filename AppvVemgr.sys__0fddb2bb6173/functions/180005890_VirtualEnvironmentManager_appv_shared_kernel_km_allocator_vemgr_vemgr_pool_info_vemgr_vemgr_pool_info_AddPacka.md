# VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddPackageNotification(appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info> const &)

- ea: `0x180005890`
- end: `0x180005a2a`
- name: `?AddPackageNotification@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAXAEBV?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z`
- size: `410`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800062bc`

## callees

- `0x1800033a8`
- `0x1800040dc`
- `0x180005890`
- `0x180007f88`
- `0x18001b3cc`

## string_xrefs

- `0x18000599b`: `VFSNotification::AddPackage() - VFS notification: add package configuration. package moniker %s. package root %s. Number of mappings %d. Result %d.`
- `0x180005a12`: `VFSNotification::AddPackage() - Failed: VFS notification: add package configuration. package moniker %s. package root %s. Number of mappings %d. Result %d.`

## pseudocode

```c
void __fastcall VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddPackageNotification(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rcx
  _QWORD *v5; // rbx
  _QWORD *v6; // r14
  __int64 v7; // rdi
  int v8; // r10d
  int *v9; // rsi
  unsigned int v10; // ecx
  __int16 v11; // dx
  __int16 v12; // ax
  __int64 v13; // r8
  unsigned int v14; // ecx
  __int16 v15; // dx
  __int16 v16; // ax
  __int64 v17; // r9
  __int64 v18; // rcx
  __int16 v19; // dx
  __int16 v20; // ax
  __int64 v21; // r8
  unsigned int v22; // ecx
  __int16 v23; // dx
  __int16 v24; // ax
  __int64 v25; // r9
  int v26; // [rsp+28h] [rbp-40h]
  char v27; // [rsp+70h] [rbp+8h] BYREF

  v4 = *(_QWORD *)(a1 + 56);
  v27 = 0;
  if ( (int)ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsVfsStateDisabled(
              v4,
              &v27) >= 0
    && v27 )
  {
    LogWrite(
      4,
      0,
      L"VirtualEnvironmentManager::AddPackageNotification() - Package add operation not sent to VFS because the VFS has be"
       "en set to disabled.");
  }
  else
  {
    v5 = *(_QWORD **)(a2 + 32);
    v6 = (_QWORD *)(a2 + 8);
    while ( v5 != v6 )
    {
      v7 = *v5;
      v8 = 0;
      v9 = (int *)(*v5 + 56LL);
      if ( *v9 )
        v8 = VFSNotification<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::send_add_ioctl<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const>(
               *(_QWORD *)(a1 + 32),
               *(_QWORD *)v7,
               0,
               0,
               *v5 + 56LL,
               v26);
      v10 = *(_DWORD *)(v7 + 16) >> 1;
      if ( v8 < 0 )
      {
        if ( v10 > 0xFFFF )
          v19 = -1;
        else
          v19 = *(_DWORD *)(v7 + 16) >> 1;
        v20 = 0;
        v21 = 0;
        if ( v10 <= 0xFFFF )
          v20 = v19;
        if ( v20 )
          v21 = *(_QWORD *)(v7 + 24);
        v22 = **(_DWORD **)v7 >> 1;
        if ( v22 > 0xFFFF )
          v23 = -1;
        else
          v23 = **(_DWORD **)v7 >> 1;
        v24 = 0;
        if ( v22 <= 0xFFFF )
          v24 = v23;
        if ( v24 )
          v25 = *(_QWORD *)(*(_QWORD *)v7 + 8LL);
        else
          v25 = 0;
        v26 = *v9;
        LogWrite(
          1,
          0,
          L"VFSNotification::AddPackage() - Failed: VFS notification: add package configuration. package moniker %s. packa"
           "ge root %s. Number of mappings %d. Result %d.",
          v25,
          v21);
      }
      else
      {
        if ( v10 > 0xFFFF )
          v11 = -1;
        else
          v11 = *(_DWORD *)(v7 + 16) >> 1;
        v12 = 0;
        v13 = 0;
        if ( v10 <= 0xFFFF )
          v12 = v11;
        if ( v12 )
          v13 = *(_QWORD *)(v7 + 24);
        v14 = **(_DWORD **)v7 >> 1;
        if ( v14 > 0xFFFF )
          v15 = -1;
        else
          v15 = **(_DWORD **)v7 >> 1;
        v16 = 0;
        if ( v14 <= 0xFFFF )
          v16 = v15;
        if ( v16 )
          v17 = *(_QWORD *)(*(_QWORD *)v7 + 8LL);
        else
          v17 = 0;
        v26 = *v9;
        LogWrite(
          3,
          0,
          L"VFSNotification::AddPackage() - VFS notification: add package configuration. package moniker %s. package root "
           "%s. Number of mappings %d. Result %d.",
          v17,
          v13);
        VFSNotification<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::log_package_mappings<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
          v18,
          *(_QWORD *)v7,
          (__int64)v9);
      }
      v5 = (_QWORD *)v5[3];
    }
  }
}

```

## disassembly

```asm
0x180005890  mov     rax, rsp
0x180005893  mov     [rax+10h], rbx
0x180005897  mov     [rax+18h], rbp
0x18000589b  push    rsi
0x18000589c  push    rdi
0x18000589d  push    r12
0x18000589f  push    r14
0x1800058a1  push    r15
0x1800058a3  sub     rsp, 40h
0x1800058a7  mov     rdi, rdx
0x1800058aa  mov     rbp, rcx
0x1800058ad  mov     rcx, [rcx+38h]
0x1800058b1  lea     rdx, [rax+8]
0x1800058b5  xor     r15d, r15d
0x1800058b8  mov     [rax+8], r15b
0x1800058bc  call    ?IsVfsStateDisabled@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEA_N@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsVfsStateDisabled(bool &)
0x1800058c1  test    eax, eax
0x1800058c3  js      short loc_1800058F7
0x1800058c5  cmp     [rsp+68h+arg_0], r15b
0x1800058ca  jz      short loc_1800058F7
0x1800058cc  xor     edx, edx
0x1800058ce  lea     r8, aVirtualenviron_6; "VirtualEnvironmentManager::AddPackageNo"...
0x1800058d5  lea     ecx, [rdx+4]
0x1800058d8  call    LogWrite
0x1800058dd  lea     r11, [rsp+68h+var_28]
0x1800058e2  mov     rbx, [r11+38h]
0x1800058e6  mov     rbp, [r11+40h]
0x1800058ea  mov     rsp, r11
0x1800058ed  pop     r15
0x1800058ef  pop     r14
0x1800058f1  pop     r12
0x1800058f3  pop     rdi
0x1800058f4  pop     rsi
0x1800058f5  retn
0x1800058f7  mov     rbx, [rdi+20h]
0x1800058fb  lea     r14, [rdi+8]
0x1800058ff  mov     r12d, 0FFFFh
0x180005905  cmp     rbx, r14
0x180005908  jz      short loc_1800058DD
0x18000590a  mov     rdi, [rbx]
0x18000590d  mov     r10d, r15d
0x180005910  lea     rsi, [rdi+38h]
0x180005914  cmp     [rsi], r15d
0x180005917  jz      short loc_180005933
0x180005919  mov     rdx, [rdi]
0x18000591c  xor     r9d, r9d
0x18000591f  mov     rcx, [rbp+20h]
0x180005923  xor     r8d, r8d
0x180005926  mov     [rsp+68h+var_48], rsi
0x18000592b  call    ??$send_add_ioctl@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@$$CBV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@234@@?$VFSNotification@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@PEAXKAEBV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@234@G@Z; VFSNotification<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::send_add_ioctl<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,void *,ulong,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &,ushort)
0x180005930  mov     r10d, eax
0x180005933  mov     ecx, [rdi+10h]
0x180005936  mov     r11d, [rsi]
0x180005939  shr     ecx, 1
0x18000593b  test    r10d, r10d
0x18000593e  js      short loc_1800059B7
0x180005940  cmp     ecx, r12d
0x180005943  ja      short loc_18000594A
0x180005945  movzx   edx, cx
0x180005948  jmp     short loc_18000594D
0x18000594a  mov     edx, r12d
0x18000594d  mov     eax, r15d
0x180005950  mov     r8, r15
0x180005953  cmovbe  ax, dx
0x180005957  test    ax, ax
0x18000595a  jz      short loc_180005960
0x18000595c  mov     r8, [rdi+18h]
0x180005960  mov     r9, [rdi]
0x180005963  mov     ecx, [r9]
0x180005966  shr     ecx, 1
0x180005968  cmp     ecx, r12d
0x18000596b  ja      short loc_180005972
0x18000596d  movzx   edx, cx
0x180005970  jmp     short loc_180005975
0x180005972  mov     edx, r12d
0x180005975  mov     eax, r15d
0x180005978  cmovbe  ax, dx
0x18000597c  test    ax, ax
0x18000597f  jnz     short loc_180005986
0x180005981  mov     r9, r15
0x180005984  jmp     short loc_18000598A
0x180005986  mov     r9, [r9+8]
0x18000598a  mov     [rsp+68h+var_38], r10d
0x18000598f  xor     edx, edx
0x180005991  mov     [rsp+68h+var_40], r11d
0x180005996  mov     [rsp+68h+var_48], r8
0x18000599b  lea     r8, aVfsnotificatio_1; "VFSNotification::AddPackage() - VFS not"...
0x1800059a2  lea     ecx, [rdx+3]
0x1800059a5  call    LogWrite
0x1800059aa  mov     rdx, [rdi]
0x1800059ad  mov     r8, rsi
0x1800059b0  call    ??$log_package_mappings@V?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@U?$km_allocator@Uvemgr_pool_info@vemgr@@@234@@?$VFSNotification@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAXAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEBV?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@234@@Z; VFSNotification<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::log_package_mappings<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> const &)
0x1800059b5  jmp     short loc_180005A21
0x1800059b7  cmp     ecx, r12d
0x1800059ba  ja      short loc_1800059C1
0x1800059bc  movzx   edx, cx
0x1800059bf  jmp     short loc_1800059C4
0x1800059c1  mov     edx, r12d
0x1800059c4  mov     eax, r15d
0x1800059c7  mov     r8, r15
0x1800059ca  cmovbe  ax, dx
0x1800059ce  test    ax, ax
0x1800059d1  jz      short loc_1800059D7
0x1800059d3  mov     r8, [rdi+18h]
0x1800059d7  mov     r9, [rdi]
0x1800059da  mov     ecx, [r9]
0x1800059dd  shr     ecx, 1
0x1800059df  cmp     ecx, r12d
0x1800059e2  ja      short loc_1800059E9
0x1800059e4  movzx   edx, cx
0x1800059e7  jmp     short loc_1800059EC
0x1800059e9  mov     edx, r12d
0x1800059ec  mov     eax, r15d
0x1800059ef  cmovbe  ax, dx
0x1800059f3  test    ax, ax
0x1800059f6  jnz     short loc_1800059FD
0x1800059f8  mov     r9, r15
0x1800059fb  jmp     short loc_180005A01
0x1800059fd  mov     r9, [r9+8]
0x180005a01  mov     [rsp+68h+var_38], r10d
0x180005a06  xor     edx, edx
0x180005a08  mov     [rsp+68h+var_40], r11d
0x180005a0d  mov     [rsp+68h+var_48], r8
0x180005a12  lea     r8, aVfsnotificatio_2; "VFSNotification::AddPackage() - Failed:"...
0x180005a19  lea     ecx, [rdx+1]
0x180005a1c  call    LogWrite
0x180005a21  mov     rbx, [rbx+18h]
0x180005a25  jmp     loc_180005905
```
