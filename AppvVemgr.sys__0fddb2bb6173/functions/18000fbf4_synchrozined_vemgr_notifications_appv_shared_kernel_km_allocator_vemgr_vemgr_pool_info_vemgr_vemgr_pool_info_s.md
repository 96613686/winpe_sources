# synchrozined_vemgr_notifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::synchronous_vemgr_notification_on_same_thread(ulong,ulong,ulong,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,ulong,ulong,bool)

- ea: `0x18000fbf4`
- end: `0x18000fcac`
- name: `?synchronous_vemgr_notification_on_same_thread@?$synchrozined_vemgr_notifications@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJKKKAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@0KK_N@Z`
- size: `184`
- prototype: `__int64 __fastcall(__int64, int, int, int, __int64, __int64, int, int, char)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180005ec4`
- `0x180016f64`

## callees

- `0x180009434`
- `0x18000fbf4`

## pseudocode

```c
__int64 __fastcall synchrozined_vemgr_notifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::synchronous_vemgr_notification_on_same_thread(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        int a7,
        int a8,
        char a9)
{
  unsigned int v12; // ecx
  __int16 v13; // r10
  __int16 v14; // ax
  void *v15; // r8
  unsigned int v16; // ecx
  __int16 v17; // dx
  __int16 v18; // ax
  _WORD *v19; // r9

  v12 = *(_DWORD *)a6 >> 1;
  if ( v12 > 0xFFFF )
    v13 = -1;
  else
    v13 = *(_DWORD *)a6 >> 1;
  v14 = 0;
  v15 = 0;
  if ( v12 <= 0xFFFF )
    v14 = v13;
  if ( v14 )
    v15 = *(void **)(a6 + 8);
  v16 = *(_DWORD *)a5 >> 1;
  if ( v16 > 0xFFFF )
    v17 = -1;
  else
    v17 = *(_DWORD *)a5 >> 1;
  v18 = 0;
  if ( v16 <= 0xFFFF )
    v18 = v17;
  if ( v18 )
    v19 = *(_WORD **)(a5 + 8);
  else
    v19 = 0;
  return VEMgrNotifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::SendNotification(
           a2,
           a3,
           a4,
           v19,
           v15,
           a7,
           a8,
           a9);
}

```

## disassembly

```asm
0x18000fbf4  push    rbx
0x18000fbf6  push    rbp
0x18000fbf7  push    rsi
0x18000fbf8  push    rdi
0x18000fbf9  push    r14
0x18000fbfb  sub     rsp, 40h
0x18000fbff  mov     r11, [rsp+68h+arg_28]
0x18000fc07  mov     r14d, 0FFFFh
0x18000fc0d  mov     ebx, r9d
0x18000fc10  mov     edi, r8d
0x18000fc13  mov     esi, edx
0x18000fc15  mov     ecx, [r11]
0x18000fc18  shr     ecx, 1
0x18000fc1a  cmp     ecx, r14d
0x18000fc1d  ja      short loc_18000FC25
0x18000fc1f  movzx   r10d, cx
0x18000fc23  jmp     short loc_18000FC28
0x18000fc25  mov     r10d, r14d
0x18000fc28  xor     ebp, ebp
0x18000fc2a  cmp     ecx, r14d
0x18000fc2d  mov     eax, ebp
0x18000fc2f  mov     r8d, ebp
0x18000fc32  cmovbe  ax, r10w
0x18000fc37  test    ax, ax
0x18000fc3a  jz      short loc_18000FC40
0x18000fc3c  mov     r8, [r11+8]
0x18000fc40  mov     r9, [rsp+68h+arg_20]
0x18000fc48  mov     ecx, [r9]
0x18000fc4b  shr     ecx, 1
0x18000fc4d  cmp     ecx, r14d
0x18000fc50  ja      short loc_18000FC57
0x18000fc52  movzx   edx, cx
0x18000fc55  jmp     short loc_18000FC5A
0x18000fc57  mov     edx, r14d
0x18000fc5a  mov     eax, ebp
0x18000fc5c  cmovbe  ax, dx
0x18000fc60  test    ax, ax
0x18000fc63  jnz     short loc_18000FC6A
0x18000fc65  mov     r9, rbp
0x18000fc68  jmp     short loc_18000FC6E
0x18000fc6a  mov     r9, [r9+8]
0x18000fc6e  mov     al, [rsp+68h+arg_40]
0x18000fc75  mov     edx, edi
0x18000fc77  mov     [rsp+68h+var_30], al
0x18000fc7b  mov     ecx, esi
0x18000fc7d  mov     eax, [rsp+68h+arg_38]
0x18000fc84  mov     [rsp+68h+var_38], eax
0x18000fc88  mov     eax, [rsp+68h+arg_30]
0x18000fc8f  mov     [rsp+68h+var_40], eax
0x18000fc93  mov     [rsp+68h+var_48], r8
0x18000fc98  mov     r8d, ebx
0x18000fc9b  call    ?SendNotification@?$VEMgrNotifications@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJKKKPEB_W0KK_N@Z; VEMgrNotifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::SendNotification(ulong,ulong,ulong,wchar_t const *,wchar_t const *,ulong,ulong,bool)
0x18000fca0  add     rsp, 40h
0x18000fca4  pop     r14
0x18000fca6  pop     rdi
0x18000fca7  pop     rsi
0x18000fca8  pop     rbp
0x18000fca9  pop     rbx
0x18000fcaa  retn
```
