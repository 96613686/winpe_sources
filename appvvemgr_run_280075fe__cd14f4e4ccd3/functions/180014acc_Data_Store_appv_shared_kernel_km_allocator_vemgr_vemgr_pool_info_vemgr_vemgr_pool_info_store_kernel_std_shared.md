# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store(kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)

- ea: `0x180014acc`
- end: `0x180014d15`
- name: `?store@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJAEBV?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `585`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800124d0`

## callees

- `0x18000b420`
- `0x18000e354`
- `0x180013718`
- `0x180014470`
- `0x180014acc`
- `0x180015008`
- `0x1800153c8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x180014b92`
- `ntoskrnl!ZwClose` at `0x180014c2a`
- `ntoskrnl!ZwClose` at `0x180014c3e`
- `ntoskrnl!ZwClose` at `0x180014c74`
- `ntoskrnl!ZwClose` at `0x180014c88`
- `ntoskrnl!ZwClose` at `0x180014b92`
- `ntoskrnl!ZwClose` at `0x180014c2a`
- `ntoskrnl!ZwClose` at `0x180014c3e`
- `ntoskrnl!ZwClose` at `0x180014c74`
- `ntoskrnl!ZwClose` at `0x180014c88`

## string_xrefs

- `0x180014c0f`: `UserConfigEx`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store(
        _QWORD *a1)
{
  __int64 v2; // rax
  __int64 *v3; // rcx
  unsigned int v4; // eax
  _DWORD *v5; // r9
  unsigned int v6; // eax
  __int16 v7; // dx
  unsigned int v8; // edx
  __int64 v9; // r8
  __int64 v10; // rdx
  int v11; // ebx
  __int64 *v13; // rcx
  unsigned int v14; // eax
  __int16 v15; // dx
  unsigned int v16; // edx
  __int64 v17; // rdx
  __int64 v18; // rcx
  HANDLE v19; // rbx
  int v20; // esi
  unsigned int v21; // edi
  __int64 *v22; // rcx
  unsigned int v23; // edx
  __int64 v24; // r8
  unsigned int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rcx
  unsigned int v28; // eax
  __int64 v29; // rcx
  HANDLE v30; // [rsp+50h] [rbp+30h] BYREF
  HANDLE Handle; // [rsp+58h] [rbp+38h] BYREF

  if ( !*a1 )
    return 3221225485LL;
  v2 = a1[1];
  if ( !v2 )
    return 3221225485LL;
  if ( !*(_DWORD *)(v2 + 8) )
    return 3221225485LL;
  v3 = (__int64 *)*a1;
  v4 = *((_DWORD *)v3 + 12) >> 1;
  if ( v4 > 0xFFFF || !(_WORD)v4 )
    return 3221225485LL;
  v5 = (_DWORD *)*v3;
  v6 = *(_DWORD *)*v3 >> 1;
  v7 = v6 > 0xFFFF ? -1 : *(_DWORD *)*v3 >> 1;
  if ( v6 > 0xFFFF || !v7 )
    return 3221225485LL;
  v8 = *((_DWORD *)v3 + 4) >> 1;
  Handle = 0;
  if ( v8 <= 0xFFFF && (_WORD)v8 )
    v9 = v3[3];
  else
    v9 = 0;
  v10 = 0;
  if ( (_WORD)v6 )
    v10 = *((_QWORD *)v5 + 1);
  v11 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_package_key(
          &Handle,
          v10,
          v9,
          1);
  if ( v11 < 0
    || ((v13 = (__int64 *)*a1, v14 = *(_DWORD *)(*a1 + 16LL) >> 1, v14 > 0xFFFF)
      ? (v15 = -1)
      : (v15 = *(_DWORD *)(*a1 + 16LL) >> 1),
        v14 <= 0xFFFF && v15 && !*((_BYTE *)v13 + 184))
    && ((v16 = *((_DWORD *)v13 + 12) >> 1, v16 > 0xFFFF) || !(_WORD)v16 ? (v17 = 0) : (v17 = v13[7]),
        (_WORD)v14 ? (v18 = v13[3]) : (v18 = 0),
        v11 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::add_user_sid_to_group(
                v18,
                v17),
        v11 < 0) )
  {
    if ( Handle )
      ZwClose(Handle);
    return (unsigned int)v11;
  }
  v19 = Handle;
  v30 = 0;
  v20 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(
          Handle,
          L"UserConfigEx",
          &v30);
  if ( v20 < 0 )
    goto LABEL_36;
  if ( !*(_BYTE *)(*a1 + 185LL) )
  {
    v20 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_user_data(
            &v30,
            a1);
    if ( v20 < 0 )
    {
      v22 = (__int64 *)*a1;
      v23 = *(_DWORD *)(*a1 + 48LL) >> 1;
      if ( v23 <= 0xFFFF && (_WORD)v23 )
        v24 = v22[7];
      else
        v24 = 0;
      v25 = *((_DWORD *)v22 + 4) >> 1;
      if ( v25 <= 0xFFFF && (_WORD)v25 )
        v26 = v22[3];
      else
        v26 = 0;
      v27 = *v22;
      v28 = *(_DWORD *)v27 >> 1;
      if ( v28 <= 0xFFFF && (_WORD)v28 )
        v29 = *(_QWORD *)(v27 + 8);
      else
        v29 = 0;
      Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_user(
        v29,
        v26,
        v24);
    }
LABEL_36:
    if ( v30 )
      ZwClose(v30);
    if ( v19 )
      ZwClose(v19);
    return (unsigned int)v20;
  }
  v21 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_on_demand_user_data(
          &v30,
          a1);
  if ( v30 )
    ZwClose(v30);
  if ( v19 )
    ZwClose(v19);
  return v21;
}

```

## disassembly

```asm
0x180014acc  mov     [rsp-28h+arg_10], rbx
0x180014ad1  push    rbp
0x180014ad2  push    rsi
0x180014ad3  push    rdi
0x180014ad4  push    r14
0x180014ad6  push    r15
0x180014ad8  mov     rbp, rsp
0x180014adb  sub     rsp, 20h
0x180014adf  xor     r14d, r14d
0x180014ae2  mov     rdi, rcx
0x180014ae5  cmp     [rcx], r14
0x180014ae8  jz      loc_180014CFE
0x180014aee  mov     rax, [rcx+8]
0x180014af2  test    rax, rax
0x180014af5  jz      loc_180014CFE
0x180014afb  mov     eax, [rax+8]
0x180014afe  test    eax, eax
0x180014b00  jz      loc_180014CFE
0x180014b06  mov     rcx, [rcx]
0x180014b09  mov     r15d, 0FFFFh
0x180014b0f  mov     eax, [rcx+30h]
0x180014b12  shr     eax, 1
0x180014b14  cmp     eax, r15d
0x180014b17  ja      loc_180014CFE
0x180014b1d  test    ax, ax
0x180014b20  jz      loc_180014CFE
0x180014b26  mov     r9, [rcx]
0x180014b29  mov     eax, [r9]
0x180014b2c  shr     eax, 1
0x180014b2e  cmp     eax, r15d
0x180014b31  ja      short loc_180014B38
0x180014b33  movzx   edx, ax
0x180014b36  jmp     short loc_180014B3B
0x180014b38  mov     edx, r15d
0x180014b3b  ja      loc_180014CFE
0x180014b41  test    dx, dx
0x180014b44  jz      loc_180014CFE
0x180014b4a  mov     edx, [rcx+10h]
0x180014b4d  shr     edx, 1
0x180014b4f  mov     [rbp+Handle], r14
0x180014b53  cmp     edx, r15d
0x180014b56  ja      short loc_180014B63
0x180014b58  test    dx, dx
0x180014b5b  jz      short loc_180014B63
0x180014b5d  mov     r8, [rcx+18h]
0x180014b61  jmp     short loc_180014B66
0x180014b63  mov     r8, r14
0x180014b66  cmp     eax, r15d
0x180014b69  ja      short loc_180014B73
0x180014b6b  mov     rdx, r14
0x180014b6e  test    ax, ax
0x180014b71  jz      short loc_180014B77
0x180014b73  mov     rdx, [r9+8]
0x180014b77  mov     r9b, 1
0x180014b7a  lea     rcx, [rbp+Handle]
0x180014b7e  call    ?open_package_key@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEAVhandle@kernel@shared@appv@@PEB_W1_N@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_package_key(appv::shared::kernel::handle &,wchar_t const *,wchar_t const *,bool)
0x180014b83  mov     ebx, eax
0x180014b85  test    eax, eax
0x180014b87  jns     short loc_180014BA5
0x180014b89  mov     rcx, [rbp+Handle]; Handle
0x180014b8d  test    rcx, rcx
0x180014b90  jz      short loc_180014B9E
0x180014b92  call    cs:__imp_ZwClose
0x180014b99  nop     dword ptr [rax+rax+00h]
0x180014b9e  mov     eax, ebx
0x180014ba0  jmp     loc_180014D03
0x180014ba5  mov     rcx, [rdi]
0x180014ba8  mov     eax, [rcx+10h]
0x180014bab  shr     eax, 1
0x180014bad  cmp     eax, r15d
0x180014bb0  ja      short loc_180014BB7
0x180014bb2  movzx   edx, ax
0x180014bb5  jmp     short loc_180014BBA
0x180014bb7  mov     edx, r15d
0x180014bba  ja      short loc_180014C00
0x180014bbc  test    dx, dx
0x180014bbf  jz      short loc_180014C00
0x180014bc1  cmp     [rcx+0B8h], r14b
0x180014bc8  jnz     short loc_180014C00
0x180014bca  mov     edx, [rcx+30h]
0x180014bcd  shr     edx, 1
0x180014bcf  cmp     edx, r15d
0x180014bd2  ja      short loc_180014BDF
0x180014bd4  test    dx, dx
0x180014bd7  jz      short loc_180014BDF
0x180014bd9  mov     rdx, [rcx+38h]
0x180014bdd  jmp     short loc_180014BE2
0x180014bdf  mov     rdx, r14
0x180014be2  cmp     eax, r15d
0x180014be5  ja      short loc_180014BF1
0x180014be7  test    ax, ax
0x180014bea  jnz     short loc_180014BF1
0x180014bec  mov     rcx, r14
0x180014bef  jmp     short loc_180014BF5
0x180014bf1  mov     rcx, [rcx+18h]
0x180014bf5  call    ?add_user_sid_to_group@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_W0@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::add_user_sid_to_group(wchar_t const *,wchar_t const *)
0x180014bfa  mov     ebx, eax
0x180014bfc  test    eax, eax
0x180014bfe  js      short loc_180014B89
0x180014c00  mov     rbx, [rbp+Handle]
0x180014c04  lea     r8, [rbp+arg_0]
0x180014c08  mov     rcx, rbx
0x180014c0b  mov     [rbp+arg_0], r14
0x180014c0f  lea     rdx, aUserconfigex; "UserConfigEx"
0x180014c16  call    ?create_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(void *,wchar_t const *,appv::shared::kernel::handle &)
0x180014c1b  mov     esi, eax
0x180014c1d  test    eax, eax
0x180014c1f  jns     short loc_180014C51
0x180014c21  mov     rcx, [rbp+arg_0]; Handle
0x180014c25  test    rcx, rcx
0x180014c28  jz      short loc_180014C36
0x180014c2a  call    cs:__imp_ZwClose
0x180014c31  nop     dword ptr [rax+rax+00h]
0x180014c36  test    rbx, rbx
0x180014c39  jz      short loc_180014C4A
0x180014c3b  mov     rcx, rbx; Handle
0x180014c3e  call    cs:__imp_ZwClose
0x180014c45  nop     dword ptr [rax+rax+00h]
0x180014c4a  mov     eax, esi
0x180014c4c  jmp     loc_180014D03
0x180014c51  mov     rax, [rdi]
0x180014c54  lea     rcx, [rbp+arg_0]
0x180014c58  mov     rdx, rdi
0x180014c5b  cmp     [rax+0B9h], r14b
0x180014c62  jz      short loc_180014C98
0x180014c64  call    ?store_on_demand_user_data@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBVhandle@kernel@shared@appv@@AEBV?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_on_demand_user_data(appv::shared::kernel::handle const &,kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x180014c69  mov     rcx, [rbp+arg_0]; Handle
0x180014c6d  mov     edi, eax
0x180014c6f  test    rcx, rcx
0x180014c72  jz      short loc_180014C80
0x180014c74  call    cs:__imp_ZwClose
0x180014c7b  nop     dword ptr [rax+rax+00h]
0x180014c80  test    rbx, rbx
0x180014c83  jz      short loc_180014C94
0x180014c85  mov     rcx, rbx; Handle
0x180014c88  call    cs:__imp_ZwClose
0x180014c8f  nop     dword ptr [rax+rax+00h]
0x180014c94  mov     eax, edi
0x180014c96  jmp     short loc_180014D03
0x180014c98  call    ?store_user_data@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBVhandle@kernel@shared@appv@@AEBV?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_user_data(appv::shared::kernel::handle const &,kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x180014c9d  mov     esi, eax
0x180014c9f  test    eax, eax
0x180014ca1  jns     loc_180014C21
0x180014ca7  mov     rcx, [rdi]
0x180014caa  mov     edx, [rcx+30h]
0x180014cad  shr     edx, 1
0x180014caf  cmp     edx, r15d
0x180014cb2  ja      short loc_180014CBF
0x180014cb4  test    dx, dx
0x180014cb7  jz      short loc_180014CBF
0x180014cb9  mov     r8, [rcx+38h]
0x180014cbd  jmp     short loc_180014CC2
0x180014cbf  mov     r8, r14
0x180014cc2  mov     eax, [rcx+10h]
0x180014cc5  shr     eax, 1
0x180014cc7  cmp     eax, r15d
0x180014cca  ja      short loc_180014CD7
0x180014ccc  test    ax, ax
0x180014ccf  jz      short loc_180014CD7
0x180014cd1  mov     rdx, [rcx+18h]
0x180014cd5  jmp     short loc_180014CDA
0x180014cd7  mov     rdx, r14
0x180014cda  mov     rcx, [rcx]
0x180014cdd  mov     eax, [rcx]
0x180014cdf  shr     eax, 1
0x180014ce1  cmp     eax, r15d
0x180014ce4  ja      short loc_180014CF1
0x180014ce6  test    ax, ax
0x180014ce9  jz      short loc_180014CF1
0x180014ceb  mov     rcx, [rcx+8]
0x180014cef  jmp     short loc_180014CF4
0x180014cf1  mov     rcx, r14
0x180014cf4  call    ?remove_user@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_W00@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_user(wchar_t const *,wchar_t const *,wchar_t const *)
0x180014cf9  jmp     loc_180014C21
0x180014cfe  mov     eax, 0C000000Dh
0x180014d03  mov     rbx, [rsp+20h+arg_10]
0x180014d08  add     rsp, 20h
0x180014d0c  pop     r15
0x180014d0e  pop     r14
0x180014d10  pop     rdi
0x180014d11  pop     rsi
0x180014d12  pop     rbp
0x180014d13  retn
```
