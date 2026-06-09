# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_on_demand_user_data(appv::shared::kernel::handle const &,kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)

- ea: `0x180015008`
- end: `0x18001514c`
- name: `?store_on_demand_user_data@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBVhandle@kernel@shared@appv@@AEBV?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `324`
- prototype: `__int64 __fastcall(void **, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180014acc`

## callees

- `0x18000b420`
- `0x18000ce10`
- `0x18000f994`
- `0x1800146ac`
- `0x180015008`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18001507f`
- `ntoskrnl!ZwClose` at `0x1800150dd`
- `ntoskrnl!ZwClose` at `0x180015130`
- `ntoskrnl!ZwClose` at `0x18001507f`
- `ntoskrnl!ZwClose` at `0x1800150dd`
- `ntoskrnl!ZwClose` at `0x180015130`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::store_on_demand_user_data(
        void **a1,
        __int64 *a2)
{
  __int64 v2; // r8
  unsigned int v6; // ecx
  __int16 v7; // dx
  __int16 v8; // ax
  const WCHAR *v9; // rdx
  NTSTATUS v10; // ebx
  HANDLE v11; // rbx
  signed int v12; // esi
  __int64 v13; // rdx
  unsigned int v14; // edi
  int v15; // [rsp+48h] [rbp+10h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp+18h] BYREF

  v2 = *a2;
  if ( !*(_BYTE *)(*a2 + 185) )
    return 3221225485LL;
  v6 = *(_DWORD *)(v2 + 48) >> 1;
  Handle = 0;
  if ( v6 > 0xFFFF )
    v7 = -1;
  else
    v7 = v6;
  v8 = 0;
  if ( v6 <= 0xFFFF )
    v8 = v7;
  v9 = 0;
  if ( v8 )
    v9 = *(const WCHAR **)(v2 + 56);
  v10 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(
          *a1,
          v9,
          &Handle);
  if ( v10 >= 0 )
  {
    v11 = Handle;
    if ( (int)registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(
                Handle,
                (__int64)L"OnDemand",
                &v15) < 0
      && (v12 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(
                  v11,
                  L"OnDemand",
                  *(_BYTE *)(*a2 + 185) != 0),
          v12 < 0)
      || (v12 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(
                  v11,
                  L"Global",
                  *(_BYTE *)(*a2 + 184) != 0),
          v12 < 0) )
    {
      if ( v11 )
        ZwClose(v11);
      return (unsigned int)v12;
    }
    else
    {
      v14 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(
              v11,
              v13,
              *(void **)(*a2 + 96),
              *(_DWORD *)(*a2 + 80));
      if ( v11 )
        ZwClose(v11);
      return v14;
    }
  }
  else
  {
    if ( Handle )
      ZwClose(Handle);
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x180015008  mov     [rsp+arg_0], rbx
0x18001500d  push    rbp
0x18001500e  push    rsi
0x18001500f  push    rdi
0x180015010  sub     rsp, 20h
0x180015014  mov     r8, [rdx]
0x180015017  xor     ebp, ebp
0x180015019  mov     rdi, rdx
0x18001501c  mov     r9, rcx
0x18001501f  cmp     [r8+0B9h], bpl
0x180015026  jnz     short loc_180015032
0x180015028  mov     eax, 0C000000Dh
0x18001502d  jmp     loc_18001513E
0x180015032  mov     ecx, [r8+30h]
0x180015036  mov     r10d, 0FFFFh
0x18001503c  shr     ecx, 1
0x18001503e  mov     [rsp+38h+Handle], rbp
0x180015043  cmp     ecx, r10d
0x180015046  ja      short loc_18001504D
0x180015048  movzx   edx, cx
0x18001504b  jmp     short loc_180015050
0x18001504d  mov     edx, r10d
0x180015050  mov     eax, ebp
0x180015052  cmovbe  ax, dx
0x180015056  mov     rdx, rbp
0x180015059  test    ax, ax
0x18001505c  jz      short loc_180015062
0x18001505e  mov     rdx, [r8+38h]
0x180015062  mov     rcx, [r9]
0x180015065  lea     r8, [rsp+38h+Handle]
0x18001506a  call    ?create_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::create_key(void *,wchar_t const *,appv::shared::kernel::handle &)
0x18001506f  mov     ebx, eax
0x180015071  test    eax, eax
0x180015073  jns     short loc_180015092
0x180015075  mov     rcx, [rsp+38h+Handle]; Handle
0x18001507a  test    rcx, rcx
0x18001507d  jz      short loc_18001508B
0x18001507f  call    cs:__imp_ZwClose
0x180015086  nop     dword ptr [rax+rax+00h]
0x18001508b  mov     eax, ebx
0x18001508d  jmp     loc_18001513E
0x180015092  mov     rbx, [rsp+38h+Handle]
0x180015097  lea     r8, [rsp+38h+arg_8]
0x18001509c  mov     rcx, rbx
0x18001509f  lea     rdx, aOndemand; "OnDemand"
0x1800150a6  call    ?get_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::get_value(void *,wchar_t const *,ulong &)
0x1800150ab  test    eax, eax
0x1800150ad  jns     short loc_1800150ED
0x1800150af  mov     rax, [rdi]
0x1800150b2  lea     rdx, aOndemand; "OnDemand"
0x1800150b9  mov     r8d, ebp
0x1800150bc  mov     rcx, rbx; KeyHandle
0x1800150bf  cmp     [rax+0B9h], bpl
0x1800150c6  setnz   r8b
0x1800150ca  call    ?set_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(void *,wchar_t const *,ulong)
0x1800150cf  mov     esi, eax
0x1800150d1  test    eax, eax
0x1800150d3  jns     short loc_1800150ED
0x1800150d5  test    rbx, rbx
0x1800150d8  jz      short loc_1800150E9
0x1800150da  mov     rcx, rbx; Handle
0x1800150dd  call    cs:__imp_ZwClose
0x1800150e4  nop     dword ptr [rax+rax+00h]
0x1800150e9  mov     eax, esi
0x1800150eb  jmp     short loc_18001513E
0x1800150ed  mov     rax, [rdi]
0x1800150f0  lea     rdx, aGlobal; "Global"
0x1800150f7  mov     r8d, ebp
0x1800150fa  mov     rcx, rbx; KeyHandle
0x1800150fd  cmp     [rax+0B8h], bpl
0x180015104  setnz   r8b
0x180015108  call    ?set_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WK@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(void *,wchar_t const *,ulong)
0x18001510d  mov     esi, eax
0x18001510f  test    eax, eax
0x180015111  js      short loc_1800150D5
0x180015113  mov     r8, [rdi]
0x180015116  mov     rcx, rbx
0x180015119  mov     r9d, [r8+50h]
0x18001511d  mov     r8, [r8+60h]
0x180015121  call    ?set_value@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_W0K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::set_value(void *,wchar_t const *,void *,ulong)
0x180015126  mov     edi, eax
0x180015128  test    rbx, rbx
0x18001512b  jz      short loc_18001513C
0x18001512d  mov     rcx, rbx; Handle
0x180015130  call    cs:__imp_ZwClose
0x180015137  nop     dword ptr [rax+rax+00h]
0x18001513c  mov     eax, edi
0x18001513e  mov     rbx, [rsp+38h+arg_0]
0x180015143  add     rsp, 20h
0x180015147  pop     rdi
0x180015148  pop     rsi
0x180015149  pop     rbp
0x18001514a  retn
```
