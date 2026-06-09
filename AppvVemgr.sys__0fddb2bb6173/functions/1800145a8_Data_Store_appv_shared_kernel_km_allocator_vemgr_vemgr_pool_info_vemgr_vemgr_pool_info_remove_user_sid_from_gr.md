# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_user_sid_from_group(wchar_t const *,wchar_t const *)

- ea: `0x1800145a8`
- end: `0x1800146a3`
- name: `?remove_user_sid_from_group@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_W0@Z`
- size: `251`
- prototype: `__int64 __fastcall(__int64, wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800109c4`

## callees

- `0x18000e354`
- `0x180013a50`
- `0x1800145a8`
- `0x18001b3cc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x180014611`
- `ntoskrnl!ZwClose` at `0x18001466c`
- `ntoskrnl!ZwClose` at `0x180014684`
- `ntoskrnl!ZwClose` at `0x180014611`
- `ntoskrnl!ZwClose` at `0x18001466c`
- `ntoskrnl!ZwClose` at `0x180014684`

## string_xrefs

- `0x1800145f8`: `Data_Store::remove_user_sid_from_group() - Error opening group moniker %s for user %s. Error = 0x%08X`
- `0x180014655`: `Data_Store::remove_user_sid_from_group() - Error deleting the mapping count on group moniker %s for user %s. Error = 0x%08X`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_user_sid_from_group(
        __int64 a1,
        wchar_t *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  HANDLE v7; // rbx
  unsigned int v8; // edi
  int v9; // [rsp+28h] [rbp-30h]
  unsigned int v10; // [rsp+28h] [rbp-30h]
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
    v8 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_value(
           Handle,
           a2);
    if ( (int)(v8 + 0x80000000) < 0 || v8 == -1073741772 )
    {
      if ( v7 )
        ZwClose(v7);
      return 0;
    }
    else
    {
      v10 = v8;
      LogWrite(
        2,
        0,
        L"Data_Store::remove_user_sid_from_group() - Error deleting the mapping count on group moniker %s for user %s. Error = 0x%08X",
        a1,
        a2,
        v10);
      if ( v7 )
        ZwClose(v7);
      return v8;
    }
  }
  else
  {
    v9 = v4;
    LogWrite(
      2,
      0,
      L"Data_Store::remove_user_sid_from_group() - Error opening group moniker %s for user %s. Error = 0x%08X",
      a1,
      a2,
      v9);
    if ( Handle )
      ZwClose(Handle);
    return v5;
  }
}

```

## disassembly

```asm
0x1800145a8  push    rbx
0x1800145aa  push    rbp
0x1800145ab  push    rsi
0x1800145ac  push    rdi
0x1800145ad  sub     rsp, 38h
0x1800145b1  mov     rsi, rdx
0x1800145b4  mov     rbp, rcx
0x1800145b7  test    rcx, rcx
0x1800145ba  jz      loc_180014694
0x1800145c0  test    rdx, rdx
0x1800145c3  jz      loc_180014694
0x1800145c9  mov     r8, rcx
0x1800145cc  mov     [rsp+58h+Handle], 0
0x1800145d5  lea     rcx, [rsp+58h+Handle]
0x1800145da  xor     r9d, r9d
0x1800145dd  xor     edx, edx
0x1800145df  call    ?open_package_key@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEAVhandle@kernel@shared@appv@@PEB_W1_N@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_package_key(appv::shared::kernel::handle &,wchar_t const *,wchar_t const *,bool)
0x1800145e4  mov     ebx, eax
0x1800145e6  test    eax, eax
0x1800145e8  jns     short loc_180014621
0x1800145ea  xor     edx, edx
0x1800145ec  mov     [rsp+58h+var_30], eax
0x1800145f0  mov     r9, rbp
0x1800145f3  mov     [rsp+58h+var_38], rsi
0x1800145f8  lea     r8, aDataStoreRemov_2; "Data_Store::remove_user_sid_from_group("...
0x1800145ff  lea     ecx, [rdx+2]
0x180014602  call    LogWrite
0x180014607  mov     rcx, [rsp+58h+Handle]; Handle
0x18001460c  test    rcx, rcx
0x18001460f  jz      short loc_18001461D
0x180014611  call    cs:__imp_ZwClose
0x180014618  nop     dword ptr [rax+rax+00h]
0x18001461d  mov     eax, ebx
0x18001461f  jmp     short loc_180014699
0x180014621  mov     rbx, [rsp+58h+Handle]
0x180014626  mov     rdx, rsi
0x180014629  mov     rcx, rbx; KeyHandle
0x18001462c  call    ?delete_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_W@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::delete_value(void *,wchar_t const *)
0x180014631  mov     edi, eax
0x180014633  mov     eax, 80000000h
0x180014638  lea     ecx, [rdi+rax]
0x18001463b  test    eax, ecx
0x18001463d  jnz     short loc_18001467C
0x18001463f  cmp     edi, 0C0000034h
0x180014645  jz      short loc_18001467C
0x180014647  xor     edx, edx
0x180014649  mov     [rsp+58h+var_30], edi
0x18001464d  mov     r9, rbp
0x180014650  mov     [rsp+58h+var_38], rsi
0x180014655  lea     r8, aDataStoreRemov; "Data_Store::remove_user_sid_from_group("...
0x18001465c  lea     ecx, [rdx+2]
0x18001465f  call    LogWrite
0x180014664  test    rbx, rbx
0x180014667  jz      short loc_180014678
0x180014669  mov     rcx, rbx; Handle
0x18001466c  call    cs:__imp_ZwClose
0x180014673  nop     dword ptr [rax+rax+00h]
0x180014678  mov     eax, edi
0x18001467a  jmp     short loc_180014699
0x18001467c  test    rbx, rbx
0x18001467f  jz      short loc_180014690
0x180014681  mov     rcx, rbx; Handle
0x180014684  call    cs:__imp_ZwClose
0x18001468b  nop     dword ptr [rax+rax+00h]
0x180014690  xor     eax, eax
0x180014692  jmp     short loc_180014699
0x180014694  mov     eax, 0C000000Dh
0x180014699  add     rsp, 38h
0x18001469d  pop     rdi
0x18001469e  pop     rsi
0x18001469f  pop     rbp
0x1800146a0  pop     rbx
0x1800146a1  retn
```
