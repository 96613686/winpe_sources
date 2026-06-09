# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_packages(appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info> &,bool &)

- ea: `0x18001a1f4`
- end: `0x18001a2e0`
- name: `?enum_packages@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJAEAV?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@AEA_N@Z`
- size: `236`
- prototype: `__int64 __fastcall(__int64, _BYTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018270`

## callees

- `0x180005178`
- `0x18000bfb8`
- `0x18000e23c`
- `0x180016474`
- `0x18001a1f4`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18001a25d`
- `ntoskrnl!ZwClose` at `0x18001a281`
- `ntoskrnl!ZwClose` at `0x18001a29c`
- `ntoskrnl!ZwClose` at `0x18001a25d`
- `ntoskrnl!ZwClose` at `0x18001a281`
- `ntoskrnl!ZwClose` at `0x18001a29c`

## string_xrefs

- `0x18001a22a`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\AppV\MAV\Configuration\Packages`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_packages(
        __int64 a1,
        _BYTE *a2)
{
  int v4; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  int v7; // edi
  _QWORD v9[2]; // [rsp+20h] [rbp-48h] BYREF
  int v10; // [rsp+30h] [rbp-38h]
  int v11; // [rsp+38h] [rbp-30h] BYREF
  __int128 v12; // [rsp+40h] [rbp-28h] BYREF
  __int128 *v13; // [rsp+50h] [rbp-18h]
  __int128 *v14; // [rsp+58h] [rbp-10h]
  HANDLE Handle; // [rsp+A0h] [rbp+38h] BYREF

  v11 = 0;
  v14 = &v12;
  Handle = 0;
  v13 = &v12;
  v12 = 0;
  v4 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
         0,
         L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\AppV\\MAV\\Configuration\\Packages",
         &Handle);
  v7 = v4;
  if ( v4 == -1073741772 || v4 == -1073741766 )
  {
    if ( Handle )
      ZwClose(Handle);
    goto LABEL_12;
  }
  if ( v4 < 0 )
  {
    if ( Handle )
      ZwClose(Handle);
    goto LABEL_13;
  }
  v7 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(
         Handle,
         (__int64)&v11,
         v5,
         v6);
  if ( Handle )
    ZwClose(Handle);
  if ( v7 >= 0 )
  {
LABEL_12:
    *a2 = 0;
    v9[0] = a1;
    v9[1] = a2;
    v10 = 0;
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::for_each<Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve_package>(
      (__int64)&v11,
      (__int64)v9);
    v7 = v10;
  }
LABEL_13:
  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)&v11);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001a1f4  push    rbp
0x18001a1f6  push    rsi
0x18001a1f7  push    rdi
0x18001a1f8  push    r14
0x18001a1fa  mov     rbp, rsp
0x18001a1fd  sub     rsp, 68h
0x18001a201  lea     rax, [rbp+var_28]
0x18001a205  mov     [rbp+var_30], 0
0x18001a20c  mov     [rbp+var_10], rax
0x18001a210  lea     r8, [rbp+Handle]
0x18001a214  lea     rax, [rbp+var_28]
0x18001a218  mov     [rbp+Handle], 0
0x18001a220  mov     rsi, rdx
0x18001a223  mov     [rbp+var_18], rax
0x18001a227  mov     r14, rcx
0x18001a22a  lea     rdx, aRegistryMachin_4; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x18001a231  xorps   xmm0, xmm0
0x18001a234  xor     ecx, ecx
0x18001a236  movdqu  [rbp+var_28], xmm0
0x18001a23b  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x18001a240  mov     edi, eax
0x18001a242  cmp     eax, 0C0000034h
0x18001a247  jz      short loc_18001A293
0x18001a249  cmp     eax, 0C000003Ah
0x18001a24e  jz      short loc_18001A293
0x18001a250  mov     rcx, [rbp+Handle]; KeyHandle
0x18001a254  test    eax, eax
0x18001a256  jns     short loc_18001A26B
0x18001a258  test    rcx, rcx
0x18001a25b  jz      short loc_18001A2CA
0x18001a25d  call    cs:__imp_ZwClose
0x18001a264  nop     dword ptr [rax+rax+00h]
0x18001a269  jmp     short loc_18001A2CA
0x18001a26b  lea     rdx, [rbp+var_30]
0x18001a26f  call    ?enum_keys@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXAEAV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(void *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)
0x18001a274  cmp     [rbp+Handle], 0
0x18001a279  mov     edi, eax
0x18001a27b  jz      short loc_18001A28D
0x18001a27d  mov     rcx, [rbp+Handle]; Handle
0x18001a281  call    cs:__imp_ZwClose
0x18001a288  nop     dword ptr [rax+rax+00h]
0x18001a28d  test    edi, edi
0x18001a28f  jns     short loc_18001A2A8
0x18001a291  jmp     short loc_18001A2CA
0x18001a293  mov     rcx, [rbp+Handle]; Handle
0x18001a297  test    rcx, rcx
0x18001a29a  jz      short loc_18001A2A8
0x18001a29c  call    cs:__imp_ZwClose
0x18001a2a3  nop     dword ptr [rax+rax+00h]
0x18001a2a8  lea     rdx, [rbp+var_48]
0x18001a2ac  mov     byte ptr [rsi], 0
0x18001a2af  lea     rcx, [rbp+var_30]
0x18001a2b3  mov     [rbp+var_48], r14
0x18001a2b7  mov     [rbp+var_40], rsi
0x18001a2bb  mov     [rbp+var_38], 0
0x18001a2c2  call    ??$for_each@Uretrieve_package@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAXAEAUretrieve_package@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::for_each<Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve_package>(Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve_package &)
0x18001a2c7  mov     edi, [rbp+var_38]
0x18001a2ca  lea     rcx, [rbp+var_30]
0x18001a2ce  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x18001a2d3  mov     eax, edi
0x18001a2d5  add     rsp, 68h
0x18001a2d9  pop     r14
0x18001a2db  pop     rdi
0x18001a2dc  pop     rsi
0x18001a2dd  pop     rbp
0x18001a2de  retn
```
