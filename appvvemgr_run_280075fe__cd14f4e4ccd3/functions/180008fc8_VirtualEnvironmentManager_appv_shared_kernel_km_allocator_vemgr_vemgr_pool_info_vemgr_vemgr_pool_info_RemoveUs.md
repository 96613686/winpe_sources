# VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveUserNotification(appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info> const &)

- ea: `0x180008fc8`
- end: `0x1800090bd`
- name: `?RemoveUserNotification@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAXAEBV?$doubly_linked_list@V?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x180008900`

## callees

- `0x180007f88`
- `0x180008fc8`
- `0x18001b3cc`

## string_xrefs

- `0x180008ff5`: `VirtualEnvironmentManager::RemoveUserNotification() - User remove operation not sent to VFS because the VFS has been set to disabled.`
- `0x18000909b`: `VFSNotification::RemoveUser() - VFS notification: remove user configuration. Package moniker %s. User sid %s. Result %d.`

## pseudocode

```c
void __fastcall VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveUserNotification(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rcx
  __int64 **v4; // rcx
  __int64 *v5; // rcx
  __int64 v6; // rax
  __int64 *v7; // r8
  unsigned int v8; // edx
  bool v9; // cc
  __int16 v10; // r9
  __int16 v11; // ax
  __int64 v12; // rdx
  unsigned int v13; // ecx
  __int16 v14; // r9
  __int16 v15; // ax
  __int64 v16; // r9
  char v17; // [rsp+40h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 56);
  v17 = 0;
  if ( (int)ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsVfsStateDisabled(
              v2,
              &v17) >= 0
    && v17 )
  {
    LogWrite(
      4,
      0,
      L"VirtualEnvironmentManager::RemoveUserNotification() - User remove operation not sent to VFS because the VFS has be"
       "en set to disabled.");
  }
  else
  {
    v4 = *(__int64 ***)(a2 + 32);
    if ( v4 != (__int64 **)(a2 + 8) )
    {
      v5 = *v4;
      if ( *((_DWORD *)v5 + 4) > 2u || (v6 = v5[1]) == 0 || !*(_DWORD *)(v6 + 8) || (v7 = (__int64 *)*v5) == 0 )
        v7 = v5 + 2;
      v8 = *((_DWORD *)v5 + 12) >> 1;
      v9 = v8 <= 0xFFFF;
      if ( v8 > 0xFFFF )
        v10 = -1;
      else
        v10 = *((_DWORD *)v5 + 12) >> 1;
      v11 = 0;
      v12 = 0;
      if ( v9 )
        v11 = v10;
      if ( v11 )
        v12 = v5[7];
      v13 = *(_DWORD *)v7 >> 1;
      if ( v13 > 0xFFFF )
        v14 = -1;
      else
        v14 = *(_DWORD *)v7 >> 1;
      v15 = 0;
      if ( v13 <= 0xFFFF )
        v15 = v14;
      v16 = 0;
      if ( v15 )
        v16 = v7[1];
      LogWrite(
        3,
        0,
        L"VFSNotification::RemoveUser() - VFS notification: remove user configuration. Package moniker %s. User sid %s. Result %d.",
        v16,
        v12,
        -1073741822);
    }
  }
}

```

## disassembly

```asm
0x180008fc8  mov     [rsp+arg_8], rbx
0x180008fcd  push    rdi
0x180008fce  sub     rsp, 30h
0x180008fd2  mov     rcx, [rcx+38h]
0x180008fd6  mov     rbx, rdx
0x180008fd9  xor     edi, edi
0x180008fdb  lea     rdx, [rsp+38h+arg_0]
0x180008fe0  mov     [rsp+38h+arg_0], dil
0x180008fe5  call    ?IsVfsStateDisabled@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEA_N@Z; ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsVfsStateDisabled(bool &)
0x180008fea  test    eax, eax
0x180008fec  js      short loc_18000900B
0x180008fee  cmp     [rsp+38h+arg_0], dil
0x180008ff3  jz      short loc_18000900B
0x180008ff5  lea     r8, aVirtualenviron_21; "VirtualEnvironmentManager::RemoveUserNo"...
0x180008ffc  xor     edx, edx
0x180008ffe  lea     ecx, [rdi+4]
0x180009001  call    LogWrite
0x180009006  jmp     loc_1800090B1
0x18000900b  lea     rax, [rbx+8]
0x18000900f  mov     rcx, [rax+18h]
0x180009013  cmp     rcx, rax
0x180009016  jz      loc_1800090B1
0x18000901c  mov     rcx, [rcx]
0x18000901f  cmp     dword ptr [rcx+10h], 2
0x180009023  ja      short loc_18000903D
0x180009025  mov     rax, [rcx+8]
0x180009029  test    rax, rax
0x18000902c  jz      short loc_18000903D
0x18000902e  mov     eax, [rax+8]
0x180009031  test    eax, eax
0x180009033  jz      short loc_18000903D
0x180009035  mov     r8, [rcx]
0x180009038  test    r8, r8
0x18000903b  jnz     short loc_180009041
0x18000903d  lea     r8, [rcx+10h]
0x180009041  mov     edx, [rcx+30h]
0x180009044  mov     r10d, 0FFFFh
0x18000904a  shr     edx, 1
0x18000904c  cmp     edx, r10d
0x18000904f  ja      short loc_180009057
0x180009051  movzx   r9d, dx
0x180009055  jmp     short loc_18000905A
0x180009057  mov     r9d, r10d
0x18000905a  mov     eax, edi
0x18000905c  mov     rdx, rdi
0x18000905f  cmovbe  ax, r9w
0x180009064  test    ax, ax
0x180009067  jz      short loc_18000906D
0x180009069  mov     rdx, [rcx+38h]
0x18000906d  mov     ecx, [r8]
0x180009070  shr     ecx, 1
0x180009072  cmp     ecx, r10d
0x180009075  ja      short loc_18000907D
0x180009077  movzx   r9d, cx
0x18000907b  jmp     short loc_180009080
0x18000907d  mov     r9d, r10d
0x180009080  mov     eax, edi
0x180009082  cmovbe  ax, r9w
0x180009087  mov     r9, rdi
0x18000908a  test    ax, ax
0x18000908d  jz      short loc_180009093
0x18000908f  mov     r9, [r8+8]
0x180009093  mov     [rsp+38h+var_10], 0C0000002h
0x18000909b  lea     r8, aVfsnotificatio_6; "VFSNotification::RemoveUser() - VFS not"...
0x1800090a2  mov     [rsp+38h+var_18], rdx
0x1800090a7  xor     edx, edx
0x1800090a9  lea     ecx, [rdx+3]
0x1800090ac  call    LogWrite
0x1800090b1  mov     rbx, [rsp+38h+arg_8]
0x1800090b6  add     rsp, 30h
0x1800090ba  pop     rdi
0x1800090bb  retn
```
