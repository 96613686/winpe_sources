# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::is_group_entitled_to_user(wchar_t const *,wchar_t const *)

- ea: `0x18000d72c`
- end: `0x18000d83e`
- name: `?is_group_entitled_to_user@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_W0@Z`
- size: `274`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800021d0`

## callees

- `0x18000ce10`
- `0x18000d72c`
- `0x18000e354`
- `0x18001b3cc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18000d798`
- `ntoskrnl!ZwClose` at `0x18000d80a`
- `ntoskrnl!ZwClose` at `0x18000d798`
- `ntoskrnl!ZwClose` at `0x18000d80a`

## string_xrefs

- `0x18000d77f`: `Data_Store::is_group_entitled_to_user() - Error opening group moniker %s for user %s. Error = 0x%08X`
- `0x18000d7f3`: `Data_Store::is_group_entitled_to_user() - Error opening User key under group moniker %s for user %s. Error = 0x%08X`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::is_group_entitled_to_user(
        __int64 a1,
        __int64 a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  HANDLE v7; // rbx
  int value; // eax
  unsigned int v9; // edi
  int v10; // [rsp+28h] [rbp-20h]
  int v11; // [rsp+28h] [rbp-20h]
  int v12; // [rsp+50h] [rbp+8h] BYREF
  HANDLE Handle; // [rsp+60h] [rbp+18h] BYREF

  if ( a1 && a2 )
  {
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
      v12 = 0;
      value = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(
                Handle,
                a2,
                &v12);
      v9 = value;
      if ( value < 0 )
      {
        if ( value != -1073741772 )
        {
          v11 = value;
          LogWrite(
            2,
            0,
            L"Data_Store::is_group_entitled_to_user() - Error opening User key under group moniker %s for user %s. Error = 0x%08X",
            a1,
            a2,
            v11);
        }
      }
      else
      {
        v9 = -1073741772;
        if ( v12 )
          v9 = 0;
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
        L"Data_Store::is_group_entitled_to_user() - Error opening group moniker %s for user %s. Error = 0x%08X",
        a1,
        a2,
        v10);
      if ( Handle )
        ZwClose(Handle);
      return v5;
    }
  }
  else
  {
    LogWrite(2, 0, L"Data_Store::is_group_entitled_to_user() - Error invalid parameters");
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x18000d72c  mov     [rsp+arg_8], rbx
0x18000d731  push    rbp
0x18000d732  push    rsi
0x18000d733  push    rdi
0x18000d734  sub     rsp, 30h
0x18000d738  mov     rsi, rdx
0x18000d73b  mov     rbp, rcx
0x18000d73e  test    rcx, rcx
0x18000d741  jz      loc_18000D81A
0x18000d747  test    rdx, rdx
0x18000d74a  jz      loc_18000D81A
0x18000d750  mov     r8, rcx
0x18000d753  mov     [rsp+48h+Handle], 0
0x18000d75c  lea     rcx, [rsp+48h+Handle]
0x18000d761  xor     r9d, r9d
0x18000d764  xor     edx, edx
0x18000d766  call    ?open_package_key@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEAVhandle@kernel@shared@appv@@PEB_W1_N@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_package_key(appv::shared::kernel::handle &,wchar_t const *,wchar_t const *,bool)
0x18000d76b  mov     ebx, eax
0x18000d76d  test    eax, eax
0x18000d76f  jns     short loc_18000D7AB
0x18000d771  xor     edx, edx
0x18000d773  mov     [rsp+48h+var_20], eax
0x18000d777  mov     r9, rbp
0x18000d77a  mov     [rsp+48h+var_28], rsi
0x18000d77f  lea     r8, aDataStoreIsGro_0; "Data_Store::is_group_entitled_to_user()"...
0x18000d786  lea     ecx, [rdx+2]
0x18000d789  call    LogWrite
0x18000d78e  mov     rcx, [rsp+48h+Handle]; Handle
0x18000d793  test    rcx, rcx
0x18000d796  jz      short loc_18000D7A4
0x18000d798  call    cs:__imp_ZwClose
0x18000d79f  nop     dword ptr [rax+rax+00h]
0x18000d7a4  mov     eax, ebx
0x18000d7a6  jmp     loc_18000D830
0x18000d7ab  mov     rbx, [rsp+48h+Handle]
0x18000d7b0  lea     r8, [rsp+48h+arg_0]
0x18000d7b5  mov     rcx, rbx
0x18000d7b8  mov     [rsp+48h+arg_0], 0
0x18000d7c0  mov     rdx, rsi
0x18000d7c3  call    ?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,ulong &)
0x18000d7c8  mov     edi, eax
0x18000d7ca  test    eax, eax
0x18000d7cc  js      short loc_18000D7DE
0x18000d7ce  xor     eax, eax
0x18000d7d0  mov     edi, 0C0000034h
0x18000d7d5  cmp     [rsp+48h+arg_0], eax
0x18000d7d9  cmova   edi, eax
0x18000d7dc  jmp     short loc_18000D802
0x18000d7de  cmp     eax, 0C0000034h
0x18000d7e3  jz      short loc_18000D802
0x18000d7e5  xor     edx, edx
0x18000d7e7  mov     [rsp+48h+var_20], eax
0x18000d7eb  mov     r9, rbp
0x18000d7ee  mov     [rsp+48h+var_28], rsi
0x18000d7f3  lea     r8, aDataStoreIsGro_1; "Data_Store::is_group_entitled_to_user()"...
0x18000d7fa  lea     ecx, [rdx+2]
0x18000d7fd  call    LogWrite
0x18000d802  test    rbx, rbx
0x18000d805  jz      short loc_18000D816
0x18000d807  mov     rcx, rbx; Handle
0x18000d80a  call    cs:__imp_ZwClose
0x18000d811  nop     dword ptr [rax+rax+00h]
0x18000d816  mov     eax, edi
0x18000d818  jmp     short loc_18000D830
0x18000d81a  xor     edx, edx
0x18000d81c  lea     r8, aDataStoreIsGro; "Data_Store::is_group_entitled_to_user()"...
0x18000d823  lea     ecx, [rdx+2]
0x18000d826  call    LogWrite
0x18000d82b  mov     eax, 0C000000Dh
0x18000d830  mov     rbx, [rsp+48h+arg_8]
0x18000d835  add     rsp, 30h
0x18000d839  pop     rdi
0x18000d83a  pop     rsi
0x18000d83b  pop     rbp
0x18000d83c  retn
```
