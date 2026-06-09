# Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_package_groups(appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info> &)

- ea: `0x18001a024`
- end: `0x18001a1ed`
- name: `?enum_package_groups@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJAEAV?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z`
- size: `457`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018270`

## callees

- `0x180005178`
- `0x18000bfb8`
- `0x18000e23c`
- `0x18000e588`
- `0x18000ef74`
- `0x18001a024`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x18001a07f`
- `ntoskrnl!ZwClose` at `0x18001a1aa`
- `ntoskrnl!ZwClose` at `0x18001a1c4`
- `ntoskrnl!ZwClose` at `0x18001a07f`
- `ntoskrnl!ZwClose` at `0x18001a1aa`
- `ntoskrnl!ZwClose` at `0x18001a1c4`

## string_xrefs

- `0x18001a048`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\AppV\MAV\Configuration\Groups`

## pseudocode

```c
__int64 __fastcall Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_package_groups(
        __int64 a1)
{
  NTSTATUS v2; // eax
  unsigned int v3; // ebx
  HANDLE v4; // rcx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int128 *v8; // rbx
  unsigned int v9; // r14d
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned int v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  volatile signed __int32 *v15; // rsi
  __int128 v16; // [rsp+20h] [rbp-40h] BYREF
  int v17; // [rsp+30h] [rbp-30h] BYREF
  __int128 v18; // [rsp+38h] [rbp-28h] BYREF
  __int128 *v19; // [rsp+48h] [rbp-18h]
  __int128 *v20; // [rsp+50h] [rbp-10h]
  HANDLE Handle; // [rsp+98h] [rbp+38h] BYREF

  Handle = 0;
  v2 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(
         0,
         (__int64)L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\AppV\\MAV\\Configuration\\Groups",
         &Handle);
  v3 = v2;
  if ( v2 == -1073741772 || v2 == -1073741766 )
  {
    if ( Handle )
      ZwClose(Handle);
    return 0;
  }
  else
  {
    v4 = Handle;
    if ( v2 < 0 )
    {
      if ( !Handle )
        return v3;
LABEL_5:
      ZwClose(v4);
      return v3;
    }
    v17 = 0;
    v20 = &v18;
    v19 = &v18;
    v18 = 0;
    v3 = registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(Handle);
    if ( (v3 & 0x80000000) != 0 )
    {
      appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(
        &v17,
        v6,
        v7);
      if ( !Handle )
        return v3;
      v4 = Handle;
      goto LABEL_5;
    }
    v8 = v20;
    v9 = 0;
    while ( v8 != &v18 )
    {
      if ( *(_QWORD *)v8 )
      {
        v10 = *((_QWORD *)v8 + 1);
        if ( v10 )
        {
          if ( *(_DWORD *)(v10 + 8) )
          {
            v11 = *(_QWORD *)v8;
            v16 = 0;
            v12 = *(_DWORD *)v11 >> 1;
            if ( v12 <= 0xFFFF && (_WORD)v12 )
              v13 = *(_QWORD *)(v11 + 8);
            else
              v13 = 0;
            v14 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve(
                    v13,
                    &v16);
            if ( v14 >= 0 )
              appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(
                a1,
                &v16);
            else
              v9 = v14;
            v15 = (volatile signed __int32 *)*((_QWORD *)&v16 + 1);
            if ( *((_QWORD *)&v16 + 1)
              && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v16 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
              if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 16LL))(v15);
            }
          }
        }
      }
      v8 = (__int128 *)*((_QWORD *)v8 + 3);
    }
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(
      &v17,
      v6,
      v7);
    if ( Handle )
      ZwClose(Handle);
    return v9;
  }
}

```

## disassembly

```asm
0x18001a024  mov     [rsp-28h+arg_0], rbx
0x18001a029  mov     [rsp-28h+arg_10], rsi
0x18001a02e  push    rbp
0x18001a02f  push    r12
0x18001a031  push    r13
0x18001a033  push    r14
0x18001a035  push    r15
0x18001a037  mov     rbp, rsp
0x18001a03a  sub     rsp, 60h
0x18001a03e  mov     r15, rcx
0x18001a041  lea     r8, [rbp+Handle]
0x18001a045  xor     r12d, r12d
0x18001a048  lea     rdx, aRegistryMachin; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x18001a04f  xor     ecx, ecx
0x18001a051  mov     [rbp+Handle], r12
0x18001a055  call    ?open_key@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXPEB_WAEAVhandle@kernel@shared@appv@@K@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::open_key(void *,wchar_t const *,appv::shared::kernel::handle &,ulong)
0x18001a05a  mov     ebx, eax
0x18001a05c  cmp     eax, 0C0000034h
0x18001a061  jz      loc_18001A1BB
0x18001a067  cmp     eax, 0C000003Ah
0x18001a06c  jz      loc_18001A1BB
0x18001a072  mov     rcx, [rbp+Handle]; KeyHandle
0x18001a076  test    eax, eax
0x18001a078  jns     short loc_18001A092
0x18001a07a  test    rcx, rcx
0x18001a07d  jz      short loc_18001A08B
0x18001a07f  call    cs:__imp_ZwClose
0x18001a086  nop     dword ptr [rax+rax+00h]
0x18001a08b  mov     eax, ebx
0x18001a08d  jmp     loc_18001A1D2
0x18001a092  lea     rax, [rbp+var_28]
0x18001a096  mov     [rbp+var_30], r12d
0x18001a09a  mov     [rbp+var_10], rax
0x18001a09e  lea     rdx, [rbp+var_30]
0x18001a0a2  lea     rax, [rbp+var_28]
0x18001a0a6  xorps   xmm0, xmm0
0x18001a0a9  mov     [rbp+var_18], rax
0x18001a0ad  movdqu  [rbp+var_28], xmm0
0x18001a0b2  call    ?enum_keys@?$registry_interface@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEAXAEAV?$doubly_linked_list@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z; registry_interface<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::enum_keys(void *,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info> &)
0x18001a0b7  mov     ebx, eax
0x18001a0b9  test    eax, eax
0x18001a0bb  jns     short loc_18001A0D2
0x18001a0bd  lea     rcx, [rbp+var_30]
0x18001a0c1  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x18001a0c6  cmp     [rbp+Handle], r12
0x18001a0ca  jz      short loc_18001A08B
0x18001a0cc  mov     rcx, [rbp+Handle]
0x18001a0d0  jmp     short loc_18001A07F
0x18001a0d2  mov     rbx, [rbp+var_10]
0x18001a0d6  mov     r14d, r12d
0x18001a0d9  or      r13d, 0FFFFFFFFh
0x18001a0dd  lea     rax, [rbp+var_28]
0x18001a0e1  cmp     rbx, rax
0x18001a0e4  jz      loc_18001A197
0x18001a0ea  cmp     [rbx], r12
0x18001a0ed  jz      loc_18001A18E
0x18001a0f3  mov     rax, [rbx+8]
0x18001a0f7  test    rax, rax
0x18001a0fa  jz      loc_18001A18E
0x18001a100  mov     eax, [rax+8]
0x18001a103  test    eax, eax
0x18001a105  jz      loc_18001A18E
0x18001a10b  mov     rcx, [rbx]
0x18001a10e  xorps   xmm0, xmm0
0x18001a111  movdqu  [rbp+var_40], xmm0
0x18001a116  mov     eax, [rcx]
0x18001a118  shr     eax, 1
0x18001a11a  cmp     eax, 0FFFFh
0x18001a11f  ja      short loc_18001A12C
0x18001a121  test    ax, ax
0x18001a124  jz      short loc_18001A12C
0x18001a126  mov     rcx, [rcx+8]
0x18001a12a  jmp     short loc_18001A12F
0x18001a12c  mov     rcx, r12
0x18001a12f  lea     rdx, [rbp+var_40]
0x18001a133  call    ?retrieve@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_WAEAV?$shared_ptr@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve(wchar_t const *,kernel_std::shared_ptr<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x18001a138  test    eax, eax
0x18001a13a  jns     short loc_18001A141
0x18001a13c  mov     r14d, eax
0x18001a13f  jmp     short loc_18001A14D
0x18001a141  lea     rdx, [rbp+var_40]
0x18001a145  mov     rcx, r15
0x18001a148  call    ?push_back@?$doubly_linked_list@V?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAJAEBV?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info>::push_back(kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x18001a14d  mov     rsi, qword ptr [rbp+var_40+8]
0x18001a151  test    rsi, rsi
0x18001a154  jz      short loc_18001A18E
0x18001a156  mov     eax, r13d
0x18001a159  lock xadd [rsi+8], eax
0x18001a15e  add     eax, r13d
0x18001a161  jnz     short loc_18001A18E
0x18001a163  mov     rax, [rsi]
0x18001a166  mov     rcx, rsi
0x18001a169  mov     rax, [rax+8]
0x18001a16d  call    _guard_dispatch_icall
0x18001a172  mov     eax, r13d
0x18001a175  lock xadd [rsi+0Ch], eax
0x18001a17a  add     eax, r13d
0x18001a17d  jnz     short loc_18001A18E
0x18001a17f  mov     rax, [rsi]
0x18001a182  mov     rcx, rsi
0x18001a185  mov     rax, [rax+10h]
0x18001a189  call    _guard_dispatch_icall
0x18001a18e  mov     rbx, [rbx+18h]
0x18001a192  jmp     loc_18001A0DD
0x18001a197  lea     rcx, [rbp+var_30]
0x18001a19b  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x18001a1a0  cmp     [rbp+Handle], r12
0x18001a1a4  jz      short loc_18001A1B6
0x18001a1a6  mov     rcx, [rbp+Handle]; Handle
0x18001a1aa  call    cs:__imp_ZwClose
0x18001a1b1  nop     dword ptr [rax+rax+00h]
0x18001a1b6  mov     eax, r14d
0x18001a1b9  jmp     short loc_18001A1D2
0x18001a1bb  mov     rcx, [rbp+Handle]; Handle
0x18001a1bf  test    rcx, rcx
0x18001a1c2  jz      short loc_18001A1D0
0x18001a1c4  call    cs:__imp_ZwClose
0x18001a1cb  nop     dword ptr [rax+rax+00h]
0x18001a1d0  xor     eax, eax
0x18001a1d2  lea     r11, [rsp+60h+var_s0]
0x18001a1d7  mov     rbx, [r11+30h]
0x18001a1db  mov     rsi, [r11+40h]
0x18001a1df  mov     rsp, r11
0x18001a1e2  pop     r15
0x18001a1e4  pop     r14
0x18001a1e6  pop     r13
0x18001a1e8  pop     r12
0x18001a1ea  pop     rbp
0x18001a1eb  retn
```
