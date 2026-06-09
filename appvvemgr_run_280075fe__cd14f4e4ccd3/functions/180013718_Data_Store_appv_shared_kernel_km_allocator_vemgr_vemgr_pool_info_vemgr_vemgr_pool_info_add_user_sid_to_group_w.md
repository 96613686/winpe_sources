# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::add_user_sid_to_group(wchar_t const *,wchar_t const *)

- ea: `0x180013718`
- end: `0x1800137f1`
- name: `?add_user_sid_to_group@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_W0@Z`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180010058`
- `0x180014acc`

## callees

- `0x18000e354`
- `0x18000f994`
- `0x180013718`
- `0x18001b3cc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x180013781`
- `ntoskrnl!ZwClose` at `0x1800137d2`
- `ntoskrnl!ZwClose` at `0x180013781`
- `ntoskrnl!ZwClose` at `0x1800137d2`

## string_xrefs

- `0x180013768`: `Data_Store::add_user_sid_to_group() - Cannot open key to group moniker %s for user %s. Error = 0x%08X`
- `0x1800137bb`: `Data_Store::add_user_sid_to_group() - Error setting mapping count on group moniker %s for user %s. Error = 0x%08X`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::add_user_sid_to_group(
        __int64 a1,
        __int64 a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  HANDLE v7; // rbx
  int v8; // eax
  unsigned int v9; // edi
  int v10; // [rsp+28h] [rbp-30h]
  int v11; // [rsp+28h] [rbp-30h]
  HANDLE Handle; // [rsp+60h] [rbp+8h] BYREF

  if ( !a1 || !a2 )
    return 3221225485LL;
  Handle = 0;
  v4 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_package_key(
         &Handle,
         0,
         a1,
         0);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v7 = Handle;
    v8 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(Handle);
    v9 = v8;
    if ( v8 < 0 )
    {
      v11 = v8;
      LogWrite(
        2,
        0,
        L"Data_Store::add_user_sid_to_group() - Error setting mapping count on group moniker %s for user %s. Error = 0x%08X",
        a1,
        a2,
        v11);
    }
    if ( v7 )
      ZwClose(v7);
    return v9;
  }
  else
  {
    v10 = v4;
    LogWrite(
      2,
      0,
      L"Data_Store::add_user_sid_to_group() - Cannot open key to group moniker %s for user %s. Error = 0x%08X",
      a1,
      a2,
      v10);
    if ( Handle )
      ZwClose(Handle);
    return v5;
  }
}

```

## disassembly

```asm
0x180013718  push    rbx
0x18001371a  push    rbp
0x18001371b  push    rsi
0x18001371c  push    rdi
0x18001371d  sub     rsp, 38h
0x180013721  mov     rsi, rdx
0x180013724  mov     rbp, rcx
0x180013727  test    rcx, rcx
0x18001372a  jz      loc_1800137E2
0x180013730  test    rdx, rdx
0x180013733  jz      loc_1800137E2
0x180013739  mov     r8, rcx
0x18001373c  mov     [rsp+58h+Handle], 0
0x180013745  lea     rcx, [rsp+58h+Handle]
0x18001374a  xor     r9d, r9d
0x18001374d  xor     edx, edx
0x18001374f  call    ?open_package_key@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEAVhandle@kernel@shared@appv@@PEB_W1_N@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_package_key(appv::shared::kernel::handle &,wchar_t const *,wchar_t const *,bool)
0x180013754  mov     ebx, eax
0x180013756  test    eax, eax
0x180013758  jns     short loc_180013791
0x18001375a  xor     edx, edx
0x18001375c  mov     [rsp+58h+var_30], eax
0x180013760  mov     r9, rbp
0x180013763  mov     [rsp+58h+var_38], rsi
0x180013768  lea     r8, aDataStoreAddUs_0; "Data_Store::add_user_sid_to_group() - C"...
0x18001376f  lea     ecx, [rdx+2]
0x180013772  call    LogWrite
0x180013777  mov     rcx, [rsp+58h+Handle]; Handle
0x18001377c  test    rcx, rcx
0x18001377f  jz      short loc_18001378D
0x180013781  call    cs:__imp_ZwClose
0x180013788  nop     dword ptr [rax+rax+00h]
0x18001378d  mov     eax, ebx
0x18001378f  jmp     short loc_1800137E7
0x180013791  mov     rbx, [rsp+58h+Handle]
0x180013796  mov     r8d, 1
0x18001379c  mov     rcx, rbx; KeyHandle
0x18001379f  mov     rdx, rsi
0x1800137a2  call    ?set_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(void *,wchar_t const *,ulong)
0x1800137a7  mov     edi, eax
0x1800137a9  test    eax, eax
0x1800137ab  jns     short loc_1800137CA
0x1800137ad  xor     edx, edx
0x1800137af  mov     [rsp+58h+var_30], eax
0x1800137b3  mov     r9, rbp
0x1800137b6  mov     [rsp+58h+var_38], rsi
0x1800137bb  lea     r8, aDataStoreAddUs; "Data_Store::add_user_sid_to_group() - E"...
0x1800137c2  lea     ecx, [rdx+2]
0x1800137c5  call    LogWrite
0x1800137ca  test    rbx, rbx
0x1800137cd  jz      short loc_1800137DE
0x1800137cf  mov     rcx, rbx; Handle
0x1800137d2  call    cs:__imp_ZwClose
0x1800137d9  nop     dword ptr [rax+rax+00h]
0x1800137de  mov     eax, edi
0x1800137e0  jmp     short loc_1800137E7
0x1800137e2  mov     eax, 0C000000Dh
0x1800137e7  add     rsp, 38h
0x1800137eb  pop     rdi
0x1800137ec  pop     rsi
0x1800137ed  pop     rbp
0x1800137ee  pop     rbx
0x1800137ef  retn
```
