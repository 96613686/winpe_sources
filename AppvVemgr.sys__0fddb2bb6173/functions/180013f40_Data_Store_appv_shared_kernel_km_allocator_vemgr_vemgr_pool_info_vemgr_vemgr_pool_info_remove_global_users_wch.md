# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_global_users(wchar_t const *,wchar_t const *)

- ea: `0x180013f40`
- end: `0x1800141c9`
- name: `?remove_global_users@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_W0@Z`
- size: `649`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800107e4`

## callees

- `0x180005178`
- `0x18000a864`
- `0x18000a958`
- `0x18000bfb8`
- `0x18000e23c`
- `0x18000e354`
- `0x180013e14`
- `0x180013f40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180014169`
- `ntoskrnl!ExFreePoolWithTag` at `0x180014169`
- `ntoskrnl!ZwClose` at `0x180013fa8`
- `ntoskrnl!ZwClose` at `0x180013ffb`
- `ntoskrnl!ZwClose` at `0x18001400f`
- `ntoskrnl!ZwClose` at `0x180014152`
- `ntoskrnl!ZwClose` at `0x1800141a2`
- `ntoskrnl!ZwClose` at `0x180013fa8`
- `ntoskrnl!ZwClose` at `0x180013ffb`
- `ntoskrnl!ZwClose` at `0x18001400f`
- `ntoskrnl!ZwClose` at `0x180014152`
- `ntoskrnl!ZwClose` at `0x1800141a2`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001408e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800140db`
- `ntoskrnl!RtlInitUnicodeString` at `0x18001408e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800140db`

## string_xrefs

- `0x180013fcf`: `UserConfigEx`
- `0x1800140fa`: `UserConfigEx`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_global_users(
        __int64 a1,
        __int64 a2)
{
  int v4; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v7; // ebx
  HANDLE v8; // rbx
  NTSTATUS v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v13; // edi
  int v14; // eax
  int v15; // esi
  bool v16; // zf
  __int128 *i; // rdi
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  wchar_t *Buffer; // rdx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  struct _UNICODE_STRING v26; // [rsp+20h] [rbp-60h] BYREF
  struct _UNICODE_STRING v27; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  int v29; // [rsp+50h] [rbp-30h] BYREF
  __int128 v30; // [rsp+58h] [rbp-28h] BYREF
  __int128 *v31; // [rsp+68h] [rbp-18h]
  __int128 *v32; // [rsp+70h] [rbp-10h]
  HANDLE v33; // [rsp+A0h] [rbp+20h] BYREF
  HANDLE Handle; // [rsp+B0h] [rbp+30h] BYREF

  if ( !a1 && !a2 )
    return 3221225485LL;
  Handle = 0;
  v4 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_package_key(
         &Handle,
         a1,
         a2,
         0);
  v7 = v4;
  if ( v4 < 0 )
  {
    if ( v4 == -1073741772 || v4 == -1073741766 )
      v7 = 0;
    if ( Handle )
      ZwClose(Handle);
    return v7;
  }
  v8 = Handle;
  if ( !a2 )
  {
    v33 = 0;
    v9 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
           Handle,
           (__int64)L"UserConfigEx",
           &v33);
    v13 = v9;
    if ( v9 >= 0 )
    {
      v13 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_global_users(
              &v33,
              v10,
              v11,
              v12);
    }
    else if ( v9 == -1073741772 || v9 == -1073741766 )
    {
      v13 = 0;
    }
    if ( v33 )
      ZwClose(v33);
    if ( v8 )
      ZwClose(v8);
    return v13;
  }
  v29 = 0;
  v32 = &v30;
  v31 = &v30;
  v30 = 0;
  v14 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(
          Handle,
          (__int64)&v29,
          v5,
          v6);
  v15 = v14;
  if ( v14 >= 0 )
  {
    for ( i = v32; i != &v30; i = (__int128 *)*((_QWORD *)i + 3) )
    {
      *(_QWORD *)&v27.Length = 0;
      v27.Buffer = 0;
      RtlInitUnicodeString(&DestinationString, 0);
      v18 = **(_DWORD **)i >> 1;
      if ( v18 <= 0xFFFF && (_WORD)v18 )
        v19 = *(_QWORD *)(*(_QWORD *)i + 8LL);
      else
        v19 = 0;
      v15 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(
              &v27,
              v19);
      if ( v15 >= 0 )
      {
        v26 = 0;
        RtlInitUnicodeString(&v26, L"\\");
        v15 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(
                &v27,
                (const void **)&v26,
                v20,
                v21);
        if ( v15 >= 0 )
        {
          v15 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(
                  &v27,
                  (__int64)L"UserConfigEx");
          if ( v15 >= 0 )
          {
            v33 = 0;
            if ( *(_DWORD *)&v27.Length >> 1 > 0xFFFFu
              || (Buffer = v27.Buffer, !(unsigned __int16)(*(_DWORD *)&v27.Length >> 1)) )
            {
              Buffer = 0;
            }
            v15 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
                    v8,
                    (__int64)Buffer,
                    &v33);
            if ( v15 >= 0 )
              v15 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_global_users(
                      &v33,
                      v23,
                      v24,
                      v25);
            if ( v33 )
              ZwClose(v33);
          }
        }
      }
      if ( v27.Buffer )
        ExFreePoolWithTag(v27.Buffer, 0);
    }
    if ( v15 == -1073741772 )
      goto LABEL_47;
    v16 = v15 == -1073741766;
  }
  else
  {
    if ( v14 == -1073741772 )
    {
LABEL_47:
      v15 = 0;
      goto LABEL_48;
    }
    v16 = v14 == -1073741766;
  }
  if ( v16 )
    goto LABEL_47;
LABEL_48:
  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)&v29);
  if ( v8 )
    ZwClose(v8);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180013f40  mov     [rsp-18h+arg_8], rbx
0x180013f45  mov     [rsp-18h+arg_18], rsi
0x180013f4a  push    rbp
0x180013f4b  push    rdi
0x180013f4c  push    r14
0x180013f4e  mov     rbp, rsp
0x180013f51  sub     rsp, 80h
0x180013f58  xor     r14d, r14d
0x180013f5b  mov     rdi, rdx
0x180013f5e  test    rcx, rcx
0x180013f61  jnz     short loc_180013F72
0x180013f63  test    rdx, rdx
0x180013f66  jnz     short loc_180013F72
0x180013f68  mov     eax, 0C000000Dh
0x180013f6d  jmp     loc_1800141B0
0x180013f72  mov     rdx, rcx
0x180013f75  mov     [rbp+Handle], r14
0x180013f79  lea     rcx, [rbp+Handle]
0x180013f7d  xor     r9d, r9d
0x180013f80  mov     r8, rdi
0x180013f83  call    ?open_package_key@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEAVhandle@kernel@shared@appv@@PEB_W1_N@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_package_key(appv::shared::kernel::handle &,wchar_t const *,wchar_t const *,bool)
0x180013f88  mov     ebx, eax
0x180013f8a  test    eax, eax
0x180013f8c  jns     short loc_180013FBB
0x180013f8e  cmp     eax, 0C0000034h
0x180013f93  jz      short loc_180013F9C
0x180013f95  cmp     eax, 0C000003Ah
0x180013f9a  jnz     short loc_180013F9F
0x180013f9c  mov     ebx, r14d
0x180013f9f  mov     rcx, [rbp+Handle]; Handle
0x180013fa3  test    rcx, rcx
0x180013fa6  jz      short loc_180013FB4
0x180013fa8  call    cs:__imp_ZwClose
0x180013faf  nop     dword ptr [rax+rax+00h]
0x180013fb4  mov     eax, ebx
0x180013fb6  jmp     loc_1800141B0
0x180013fbb  mov     rbx, [rbp+Handle]
0x180013fbf  mov     rcx, rbx; KeyHandle
0x180013fc2  test    rdi, rdi
0x180013fc5  jnz     short loc_18001402F
0x180013fc7  lea     r8, [rbp+arg_0]
0x180013fcb  mov     [rbp+arg_0], r14
0x180013fcf  lea     rdx, aUserconfigex; "UserConfigEx"
0x180013fd6  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x180013fdb  mov     edi, eax
0x180013fdd  test    eax, eax
0x180013fdf  jns     short loc_180014022
0x180013fe1  cmp     eax, 0C0000034h
0x180013fe6  jz      short loc_180013FEF
0x180013fe8  cmp     eax, 0C000003Ah
0x180013fed  jnz     short loc_180013FF2
0x180013fef  mov     edi, r14d
0x180013ff2  mov     rcx, [rbp+arg_0]; Handle
0x180013ff6  test    rcx, rcx
0x180013ff9  jz      short loc_180014007
0x180013ffb  call    cs:__imp_ZwClose
0x180014002  nop     dword ptr [rax+rax+00h]
0x180014007  test    rbx, rbx
0x18001400a  jz      short loc_18001401B
0x18001400c  mov     rcx, rbx; Handle
0x18001400f  call    cs:__imp_ZwClose
0x180014016  nop     dword ptr [rax+rax+00h]
0x18001401b  mov     eax, edi
0x18001401d  jmp     loc_1800141B0
0x180014022  lea     rcx, [rbp+arg_0]
0x180014026  call    ?remove_global_users@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBVhandle@kernel@shared@appv@@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_global_users(appv::shared::kernel::handle const &)
0x18001402b  mov     edi, eax
0x18001402d  jmp     short loc_180013FF2
0x18001402f  lea     rax, [rbp+var_28]
0x180014033  mov     [rbp+var_30], r14d
0x180014037  mov     [rbp+var_10], rax
0x18001403b  lea     rdx, [rbp+var_30]
0x18001403f  lea     rax, [rbp+var_28]
0x180014043  xorps   xmm0, xmm0
0x180014046  mov     [rbp+var_18], rax
0x18001404a  movdqu  [rbp+var_28], xmm0
0x18001404f  call    ?enum_keys@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXAEAV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(void *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)
0x180014054  mov     esi, eax
0x180014056  test    eax, eax
0x180014058  jns     short loc_18001406F
0x18001405a  cmp     eax, 0C0000034h
0x18001405f  jz      loc_18001418E
0x180014065  cmp     eax, 0C000003Ah
0x18001406a  jmp     loc_18001418C
0x18001406f  mov     rdi, [rbp+var_10]
0x180014073  lea     rax, [rbp+var_28]
0x180014077  cmp     rdi, rax
0x18001407a  jz      loc_18001417E
0x180014080  xor     edx, edx; SourceString
0x180014082  mov     [rbp+var_50], r14
0x180014086  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001408a  mov     [rbp+P], r14
0x18001408e  call    cs:__imp_RtlInitUnicodeString
0x180014095  nop     dword ptr [rax+rax+00h]
0x18001409a  mov     rdx, [rdi]
0x18001409d  mov     eax, [rdx]
0x18001409f  shr     eax, 1
0x1800140a1  cmp     eax, 0FFFFh
0x1800140a6  ja      short loc_1800140B3
0x1800140a8  test    ax, ax
0x1800140ab  jz      short loc_1800140B3
0x1800140ad  mov     rdx, [rdx+8]
0x1800140b1  jmp     short loc_1800140B6
0x1800140b3  mov     rdx, r14
0x1800140b6  lea     rcx, [rbp+var_50]
0x1800140ba  call    ?append@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJPEB_W@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(wchar_t const *)
0x1800140bf  mov     esi, eax
0x1800140c1  test    eax, eax
0x1800140c3  js      loc_18001415E
0x1800140c9  xorps   xmm0, xmm0
0x1800140cc  lea     rdx, asc_18002108C; "\\"
0x1800140d3  lea     rcx, [rbp+var_60]; DestinationString
0x1800140d7  movups  xmmword ptr [rbp+var_60.Length], xmm0
0x1800140db  call    cs:__imp_RtlInitUnicodeString
0x1800140e2  nop     dword ptr [rax+rax+00h]
0x1800140e7  lea     rdx, [rbp+var_60]
0x1800140eb  lea     rcx, [rbp+var_50]
0x1800140ef  call    ?append@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBU_UNICODE_STRING@@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(_UNICODE_STRING const &)
0x1800140f4  mov     esi, eax
0x1800140f6  test    eax, eax
0x1800140f8  js      short loc_18001415E
0x1800140fa  lea     rdx, aUserconfigex; "UserConfigEx"
0x180014101  lea     rcx, [rbp+var_50]
0x180014105  call    ?append@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJPEB_W@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::append(wchar_t const *)
0x18001410a  mov     esi, eax
0x18001410c  test    eax, eax
0x18001410e  js      short loc_18001415E
0x180014110  mov     eax, dword ptr [rbp+var_50]
0x180014113  shr     eax, 1
0x180014115  mov     [rbp+arg_0], r14
0x180014119  cmp     eax, 0FFFFh
0x18001411e  ja      short loc_180014129
0x180014120  mov     rdx, [rbp+P]
0x180014124  test    ax, ax
0x180014127  jnz     short loc_18001412C
0x180014129  mov     rdx, r14
0x18001412c  lea     r8, [rbp+arg_0]
0x180014130  mov     rcx, rbx
0x180014133  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x180014138  mov     esi, eax
0x18001413a  test    eax, eax
0x18001413c  js      short loc_180014149
0x18001413e  lea     rcx, [rbp+arg_0]
0x180014142  call    ?remove_global_users@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@CAJAEBVhandle@kernel@shared@appv@@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_global_users(appv::shared::kernel::handle const &)
0x180014147  mov     esi, eax
0x180014149  mov     rcx, [rbp+arg_0]; Handle
0x18001414d  test    rcx, rcx
0x180014150  jz      short loc_18001415E
0x180014152  call    cs:__imp_ZwClose
0x180014159  nop     dword ptr [rax+rax+00h]
0x18001415e  mov     rcx, [rbp+P]; P
0x180014162  test    rcx, rcx
0x180014165  jz      short loc_180014175
0x180014167  xor     edx, edx; Tag
0x180014169  call    cs:__imp_ExFreePoolWithTag
0x180014170  nop     dword ptr [rax+rax+00h]
0x180014175  mov     rdi, [rdi+18h]
0x180014179  jmp     loc_180014073
0x18001417e  cmp     esi, 0C0000034h
0x180014184  jz      short loc_18001418E
0x180014186  cmp     esi, 0C000003Ah
0x18001418c  jnz     short loc_180014191
0x18001418e  mov     esi, r14d
0x180014191  lea     rcx, [rbp+var_30]
0x180014195  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x18001419a  test    rbx, rbx
0x18001419d  jz      short loc_1800141AE
0x18001419f  mov     rcx, rbx; Handle
0x1800141a2  call    cs:__imp_ZwClose
0x1800141a9  nop     dword ptr [rax+rax+00h]
0x1800141ae  mov     eax, esi
0x1800141b0  lea     r11, [rsp+80h+var_s0]
0x1800141b8  mov     rbx, [r11+28h]
0x1800141bc  mov     rsi, [r11+38h]
0x1800141c0  mov     rsp, r11
0x1800141c3  pop     r14
0x1800141c5  pop     rdi
0x1800141c6  pop     rbp
0x1800141c7  retn
```
