# VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveUserNotification(appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info> const &)

- ea: `0x180008fc8`
- end: `0x1800090bd`
- name: `?RemoveUserNotification@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAAXAEBV?$doubly_linked_list@V?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z`
- size: `245`
- prototype: `__int64 __fastcall(__int64, __int64)`
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
__int64 __fastcall VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveUserNotification(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rcx
  __int64 result; // rax
  __int64 **v5; // rcx
  __int64 *v6; // rcx
  __int64 v7; // rax
  __int64 *v8; // r8
  unsigned int v9; // edx
  bool v10; // cc
  __int16 v11; // r9
  __int16 v12; // ax
  __int64 v13; // rdx
  unsigned int v14; // ecx
  __int16 v15; // r9
  __int16 v16; // ax
  __int64 v17; // r9
  char v18; // [rsp+40h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 56);
  v18 = 0;
  if ( (int)ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::IsVfsStateDisabled(
              v2,
              &v18) >= 0
    && v18 )
  {
    return LogWrite(
             4,
             0,
             L"VirtualEnvironmentManager::RemoveUserNotification() - User remove operation not sent to VFS because the VFS"
              " has been set to disabled.");
  }
  result = a2 + 8;
  v5 = *(__int64 ***)(a2 + 32);
  if ( v5 != (__int64 **)(a2 + 8) )
  {
    v6 = *v5;
    if ( *((_DWORD *)v6 + 4) > 2u || (v7 = v6[1]) == 0 || !*(_DWORD *)(v7 + 8) || (v8 = (__int64 *)*v6) == 0 )
      v8 = v6 + 2;
    v9 = *((_DWORD *)v6 + 12) >> 1;
    v10 = v9 <= 0xFFFF;
    if ( v9 > 0xFFFF )
      v11 = -1;
    else
      v11 = *((_DWORD *)v6 + 12) >> 1;
    v12 = 0;
    v13 = 0;
    if ( v10 )
      v12 = v11;
    if ( v12 )
      v13 = v6[7];
    v14 = *(_DWORD *)v8 >> 1;
    if ( v14 > 0xFFFF )
      v15 = -1;
    else
      v15 = *(_DWORD *)v8 >> 1;
    v16 = 0;
    if ( v14 <= 0xFFFF )
      v16 = v15;
    v17 = 0;
    if ( v16 )
      v17 = v8[1];
    return LogWrite(
             3,
             0,
             L"VFSNotification::RemoveUser() - VFS notification: remove user configuration. Package moniker %s. User sid %s. Result %d.",
             v17,
             v13,
             -1073741822);
  }
  return result;
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
