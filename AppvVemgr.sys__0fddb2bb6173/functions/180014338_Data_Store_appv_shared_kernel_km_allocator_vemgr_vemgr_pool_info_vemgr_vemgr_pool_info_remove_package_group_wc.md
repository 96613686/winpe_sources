# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_package_group(wchar_t const *)

- ea: `0x180014338`
- end: `0x18001446a`
- name: `?remove_package_group@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_W@Z`
- size: `306`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010374`
- `0x180014964`

## callees

- `0x18000b478`
- `0x18000e23c`
- `0x180013af0`
- `0x180014338`
- `0x18001b3cc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x180014375`
- `ntoskrnl!ZwClose` at `0x1800143c1`
- `ntoskrnl!ZwClose` at `0x1800143d5`
- `ntoskrnl!ZwClose` at `0x180014437`
- `ntoskrnl!ZwClose` at `0x18001444b`
- `ntoskrnl!ZwClose` at `0x180014375`
- `ntoskrnl!ZwClose` at `0x1800143c1`
- `ntoskrnl!ZwClose` at `0x1800143d5`
- `ntoskrnl!ZwClose` at `0x180014437`
- `ntoskrnl!ZwClose` at `0x18001444b`

## string_xrefs

- `0x180014359`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\AppV\MAV\Configuration\Groups`
- `0x18001440c`: `Data_Store::remove_package_group() - Removing package group %s. Package group has not been unpublished.`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_package_group(
        __int64 a1)
{
  NTSTATUS v2; // ebx
  HANDLE v4; // rbx
  NTSTATUS v5; // edi
  HANDLE v6; // rdi
  unsigned int v7; // esi
  HANDLE Handle; // [rsp+38h] [rbp+10h] BYREF
  HANDLE v9; // [rsp+40h] [rbp+18h] BYREF

  Handle = 0;
  v2 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
         0,
         (__int64)L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\AppV\\MAV\\Configuration\\Groups",
         &Handle);
  if ( v2 >= 0 )
  {
    v4 = Handle;
    v9 = 0;
    v5 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
           Handle,
           a1,
           &v9);
    if ( v5 >= 0 )
    {
      v6 = v9;
      LODWORD(Handle) = 0;
      if ( (int)registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_subkey_count(
                  v9,
                  &Handle) >= 0
        && (_DWORD)Handle )
      {
        LogWrite(
          3,
          0,
          L"Data_Store::remove_package_group() - Removing package group %s. Package group has not been unpublished.",
          a1);
      }
      v7 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_key(
             (__int64)v6,
             &dword_18001E3EC);
      if ( v6 )
        ZwClose(v6);
      if ( v4 )
        ZwClose(v4);
      return v7;
    }
    else
    {
      if ( v5 == -1073741772 )
        v5 = 0;
      if ( v9 )
        ZwClose(v9);
      if ( v4 )
        ZwClose(v4);
      return (unsigned int)v5;
    }
  }
  else
  {
    if ( Handle )
      ZwClose(Handle);
    return (unsigned int)v2;
  }
}

```

## disassembly

```asm
0x180014338  mov     rax, rsp
0x18001433b  mov     [rax+8], rbx
0x18001433f  mov     [rax+20h], rsi
0x180014343  push    rdi
0x180014344  sub     rsp, 20h
0x180014348  mov     rsi, rcx
0x18001434b  mov     qword ptr [rax+10h], 0
0x180014353  xor     ecx, ecx
0x180014355  lea     r8, [rax+10h]
0x180014359  lea     rdx, aRegistryMachin; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x180014360  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x180014365  mov     ebx, eax
0x180014367  test    eax, eax
0x180014369  jns     short loc_180014388
0x18001436b  mov     rcx, [rsp+28h+Handle]; Handle
0x180014370  test    rcx, rcx
0x180014373  jz      short loc_180014381
0x180014375  call    cs:__imp_ZwClose
0x18001437c  nop     dword ptr [rax+rax+00h]
0x180014381  mov     eax, ebx
0x180014383  jmp     loc_180014459
0x180014388  mov     rbx, [rsp+28h+Handle]
0x18001438d  lea     r8, [rsp+28h+arg_10]
0x180014392  mov     rcx, rbx
0x180014395  mov     [rsp+28h+arg_10], 0
0x18001439e  mov     rdx, rsi
0x1800143a1  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x1800143a6  mov     edi, eax
0x1800143a8  test    eax, eax
0x1800143aa  jns     short loc_1800143E5
0x1800143ac  mov     rcx, [rsp+28h+arg_10]; Handle
0x1800143b1  xor     eax, eax
0x1800143b3  cmp     edi, 0C0000034h
0x1800143b9  cmovz   edi, eax
0x1800143bc  test    rcx, rcx
0x1800143bf  jz      short loc_1800143CD
0x1800143c1  call    cs:__imp_ZwClose
0x1800143c8  nop     dword ptr [rax+rax+00h]
0x1800143cd  test    rbx, rbx
0x1800143d0  jz      short loc_1800143E1
0x1800143d2  mov     rcx, rbx; Handle
0x1800143d5  call    cs:__imp_ZwClose
0x1800143dc  nop     dword ptr [rax+rax+00h]
0x1800143e1  mov     eax, edi
0x1800143e3  jmp     short loc_180014459
0x1800143e5  mov     rdi, [rsp+28h+arg_10]
0x1800143ea  lea     rdx, [rsp+28h+Handle]
0x1800143ef  mov     rcx, rdi
0x1800143f2  mov     dword ptr [rsp+28h+Handle], 0
0x1800143fa  call    ?get_subkey_count@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXAEAK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_subkey_count(void *,ulong &)
0x1800143ff  test    eax, eax
0x180014401  js      short loc_18001441E
0x180014403  cmp     dword ptr [rsp+28h+Handle], 0
0x180014408  jbe     short loc_18001441E
0x18001440a  xor     edx, edx
0x18001440c  lea     r8, aDataStoreRemov_0; "Data_Store::remove_package_group() - Re"...
0x180014413  mov     r9, rsi
0x180014416  lea     ecx, [rdx+3]
0x180014419  call    LogWrite
0x18001441e  lea     rdx, dword_18001E3EC
0x180014425  mov     rcx, rdi
0x180014428  call    ?delete_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_W_N@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_key(void *,wchar_t const *,bool)
0x18001442d  mov     esi, eax
0x18001442f  test    rdi, rdi
0x180014432  jz      short loc_180014443
0x180014434  mov     rcx, rdi; Handle
0x180014437  call    cs:__imp_ZwClose
0x18001443e  nop     dword ptr [rax+rax+00h]
0x180014443  test    rbx, rbx
0x180014446  jz      short loc_180014457
0x180014448  mov     rcx, rbx; Handle
0x18001444b  call    cs:__imp_ZwClose
0x180014452  nop     dword ptr [rax+rax+00h]
0x180014457  mov     eax, esi
0x180014459  mov     rbx, [rsp+28h+arg_0]
0x18001445e  mov     rsi, [rsp+28h+arg_18]
0x180014463  add     rsp, 20h
0x180014467  pop     rdi
0x180014468  retn
```
