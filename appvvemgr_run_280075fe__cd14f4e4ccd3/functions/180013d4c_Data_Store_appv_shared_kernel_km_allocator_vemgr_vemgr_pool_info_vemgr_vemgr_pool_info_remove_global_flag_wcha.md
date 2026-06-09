# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_global_flag(wchar_t const *,wchar_t const *)

- ea: `0x180013d4c`
- end: `0x180013e0e`
- name: `?remove_global_flag@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_W0@Z`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800107e4`

## callees

- `0x18000ce10`
- `0x18000e354`
- `0x180013a50`
- `0x180013d4c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x180013d82`
- `ntoskrnl!ZwClose` at `0x180013dc8`
- `ntoskrnl!ZwClose` at `0x180013df4`
- `ntoskrnl!ZwClose` at `0x180013d82`
- `ntoskrnl!ZwClose` at `0x180013dc8`
- `ntoskrnl!ZwClose` at `0x180013df4`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_global_flag(
        __int64 a1,
        __int64 a2)
{
  int v2; // ebx
  HANDLE v4; // rbx
  int value; // edi
  int v6; // [rsp+40h] [rbp+18h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp+20h] BYREF

  Handle = 0;
  v2 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_package_key(
         &Handle,
         a1,
         a2,
         0);
  if ( v2 < 0 )
  {
    if ( Handle )
      ZwClose(Handle);
    return (unsigned int)v2;
  }
  v4 = Handle;
  v6 = 0;
  value = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(
            Handle,
            (__int64)L"Global",
            &v6);
  if ( value >= 0 )
  {
    if ( !v6 )
    {
      if ( v4 )
        ZwClose(v4);
      return 3221225524LL;
    }
    value = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_value(
              v4,
              L"Global");
  }
  if ( v4 )
    ZwClose(v4);
  return (unsigned int)value;
}

```

## disassembly

```asm
0x180013d4c  mov     [rsp+arg_0], rbx
0x180013d51  push    rdi
0x180013d52  sub     rsp, 20h
0x180013d56  mov     r8, rdx
0x180013d59  mov     [rsp+28h+Handle], 0
0x180013d62  mov     rdx, rcx
0x180013d65  xor     r9d, r9d
0x180013d68  lea     rcx, [rsp+28h+Handle]
0x180013d6d  call    ?open_package_key@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEAVhandle@kernel@shared@appv@@PEB_W1_N@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_package_key(appv::shared::kernel::handle &,wchar_t const *,wchar_t const *,bool)
0x180013d72  mov     ebx, eax
0x180013d74  test    eax, eax
0x180013d76  jns     short loc_180013D92
0x180013d78  mov     rcx, [rsp+28h+Handle]; Handle
0x180013d7d  test    rcx, rcx
0x180013d80  jz      short loc_180013D8E
0x180013d82  call    cs:__imp_ZwClose
0x180013d89  nop     dword ptr [rax+rax+00h]
0x180013d8e  mov     eax, ebx
0x180013d90  jmp     short loc_180013E02
0x180013d92  mov     rbx, [rsp+28h+Handle]
0x180013d97  lea     r8, [rsp+28h+arg_10]
0x180013d9c  mov     rcx, rbx
0x180013d9f  mov     [rsp+28h+arg_10], 0
0x180013da7  lea     rdx, aGlobal; "Global"
0x180013dae  call    ?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,ulong &)
0x180013db3  mov     edi, eax
0x180013db5  test    eax, eax
0x180013db7  js      short loc_180013DEC
0x180013db9  cmp     [rsp+28h+arg_10], 0
0x180013dbe  jnz     short loc_180013DDB
0x180013dc0  test    rbx, rbx
0x180013dc3  jz      short loc_180013DD4
0x180013dc5  mov     rcx, rbx; Handle
0x180013dc8  call    cs:__imp_ZwClose
0x180013dcf  nop     dword ptr [rax+rax+00h]
0x180013dd4  mov     eax, 0C0000034h
0x180013dd9  jmp     short loc_180013E02
0x180013ddb  lea     rdx, aGlobal; "Global"
0x180013de2  mov     rcx, rbx; KeyHandle
0x180013de5  call    ?delete_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_W@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_value(void *,wchar_t const *)
0x180013dea  mov     edi, eax
0x180013dec  test    rbx, rbx
0x180013def  jz      short loc_180013E00
0x180013df1  mov     rcx, rbx; Handle
0x180013df4  call    cs:__imp_ZwClose
0x180013dfb  nop     dword ptr [rax+rax+00h]
0x180013e00  mov     eax, edi
0x180013e02  mov     rbx, [rsp+28h+arg_0]
0x180013e07  add     rsp, 20h
0x180013e0b  pop     rdi
0x180013e0c  retn
```
