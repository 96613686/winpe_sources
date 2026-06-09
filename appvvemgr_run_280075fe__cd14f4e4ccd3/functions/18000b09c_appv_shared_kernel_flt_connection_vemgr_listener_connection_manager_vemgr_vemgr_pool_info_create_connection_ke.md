# appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::create_connection(kernel_std::shared_ptr<appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>> &,_FLT_FILTER *,_UNICODE_STRING &,bool const &,ulong const &)

- ea: `0x18000b09c`
- end: `0x18000b348`
- name: `?create_connection@?$flt_connection@Vvemgr_listener_connection_manager@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@SAJAEAV?$shared_ptr@V?$flt_connection@Vvemgr_listener_connection_manager@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel_std@@PEAU_FLT_FILTER@@AEAU_UNICODE_STRING@@AEB_NAEBK@Z`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000a050`

## callees

- `0x18000b09c`
- `0x18000bb18`
- `0x18000d534`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000b0d0`
- `ntoskrnl!ExAllocatePool2` at `0x18000b0fd`
- `ntoskrnl!ExAllocatePool2` at `0x18000b147`
- `ntoskrnl!ExAllocatePool2` at `0x18000b0d0`
- `ntoskrnl!ExAllocatePool2` at `0x18000b0fd`
- `ntoskrnl!ExAllocatePool2` at `0x18000b147`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000b314`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000b325`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000b314`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000b325`
- `ntoskrnl!ExInitializeResourceLite` at `0x18000b11c`
- `ntoskrnl!ExInitializeResourceLite` at `0x18000b11c`
- `ntoskrnl!ExDeleteResourceLite` at `0x18000b2fd`
- `ntoskrnl!ExDeleteResourceLite` at `0x18000b2fd`
- `FLTMGR!FltCloseCommunicationPort` at `0x18000b2e5`
- `FLTMGR!FltCloseCommunicationPort` at `0x18000b2e5`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::create_connection(
        __int64 *a1,
        struct _FLT_FILTER *a2,
        struct _UNICODE_STRING *a3,
        char *a4,
        ACCESS_MASK *a5)
{
  __int64 Pool2; // rax
  __int64 v9; // rbx
  struct _ERESOURCE *v10; // rax
  NTSTATUS v11; // ebp
  __int64 v12; // rax
  volatile signed __int32 *v13; // rdi
  volatile signed __int32 *v14; // r14
  int v16; // esi
  volatile signed __int32 *v17; // rsi
  struct _ERESOURCE *v18; // rcx
  void *v19; // rcx

  Pool2 = ExAllocatePool2(256, 48, 1733125462);
  v9 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)Pool2 = 0;
    *(_QWORD *)(Pool2 + 8) = 0;
    *(_QWORD *)(Pool2 + 24) = 0;
    *(_DWORD *)(Pool2 + 16) = 1733125462;
    v10 = (struct _ERESOURCE *)ExAllocatePool2(64, 104, 1733125462);
    *(_QWORD *)(v9 + 24) = v10;
    if ( v10 )
      v11 = ExInitializeResourceLite(v10);
    else
      v11 = -1073741670;
    *(_BYTE *)(v9 + 32) = 0;
    *(_QWORD *)(v9 + 40) = 0;
  }
  else
  {
    v11 = 0;
    v9 = 0;
  }
  v12 = ExAllocatePool2(256, 24, 1715758931);
  v13 = (volatile signed __int32 *)v12;
  if ( !v12 )
  {
    if ( v9 )
    {
      appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::disconnect_client(v9);
      if ( *(_QWORD *)v9 )
      {
        FltCloseCommunicationPort(*(PFLT_PORT *)v9);
        *(_QWORD *)v9 = 0;
      }
      v18 = *(struct _ERESOURCE **)(v9 + 24);
      if ( v18 )
      {
        ExDeleteResourceLite(v18);
        v19 = *(void **)(v9 + 24);
        if ( v19 )
          ExFreePoolWithTag(v19, 0);
      }
      ExFreePoolWithTag((PVOID)v9, 0);
    }
    return 3221225626LL;
  }
  *(_QWORD *)(v12 + 16) = v9;
  *(_DWORD *)(v12 + 8) = 1;
  v14 = (volatile signed __int32 *)(v12 + 8);
  *(_DWORD *)(v12 + 12) = 1;
  *(_QWORD *)v12 = &kernel_std::detail::sp_counted_impl_p<appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>>::`vftable';
  if ( !*(_DWORD *)(v12 + 8) || !v9 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v12 + 8), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return 3221225626LL;
  }
  if ( v11 >= 0 )
  {
    v16 = appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::initialize(
            (PFLT_PORT *)v9,
            a2,
            a3,
            *a4,
            *a5);
    if ( v16 >= 0 )
    {
      v17 = (volatile signed __int32 *)a1[1];
      *a1 = v9;
      a1[1] = (__int64)v13;
      if ( v17 )
      {
        if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
          if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 16LL))(v17);
        }
      }
      return 0;
    }
    else
    {
      if ( _InterlockedExchangeAdd(v14, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 16LL))(v13);
      }
      return (unsigned int)v16;
    }
  }
  else
  {
    if ( _InterlockedExchangeAdd(v14, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return (unsigned int)v11;
  }
}

```

## disassembly

```asm
0x18000b09c  mov     [rsp+Filter], rdx
0x18000b0a1  push    rbx
0x18000b0a2  push    rbp
0x18000b0a3  push    rsi
0x18000b0a4  push    rdi
0x18000b0a5  push    r12
0x18000b0a7  push    r13
0x18000b0a9  push    r14
0x18000b0ab  push    r15
0x18000b0ad  sub     rsp, 38h
0x18000b0b1  mov     r13, r8
0x18000b0b4  mov     r15, rcx
0x18000b0b7  mov     edi, 674D6556h
0x18000b0bc  mov     r14d, 100h
0x18000b0c2  mov     r8d, edi
0x18000b0c5  mov     ecx, r14d
0x18000b0c8  mov     edx, 30h ; '0'
0x18000b0cd  mov     r12, r9
0x18000b0d0  call    cs:__imp_ExAllocatePool2
0x18000b0d7  nop     dword ptr [rax+rax+00h]
0x18000b0dc  xor     esi, esi
0x18000b0de  mov     rbx, rax
0x18000b0e1  test    rax, rax
0x18000b0e4  jz      short loc_18000B134
0x18000b0e6  mov     [rax], rsi
0x18000b0e9  lea     edx, [rsi+68h]
0x18000b0ec  mov     [rax+8], rsi
0x18000b0f0  lea     ecx, [rsi+40h]
0x18000b0f3  mov     r8d, edi
0x18000b0f6  mov     [rax+18h], rsi
0x18000b0fa  mov     [rax+10h], edi
0x18000b0fd  call    cs:__imp_ExAllocatePool2
0x18000b104  nop     dword ptr [rax+rax+00h]
0x18000b109  mov     [rbx+18h], rax
0x18000b10d  test    rax, rax
0x18000b110  jnz     short loc_18000B119
0x18000b112  mov     ebp, 0C000009Ah
0x18000b117  jmp     short loc_18000B12A
0x18000b119  mov     rcx, rax; Resource
0x18000b11c  call    cs:__imp_ExInitializeResourceLite
0x18000b123  nop     dword ptr [rax+rax+00h]
0x18000b128  mov     ebp, eax
0x18000b12a  mov     [rbx+20h], sil
0x18000b12e  mov     [rbx+28h], rsi
0x18000b132  jmp     short loc_18000B139
0x18000b134  mov     ebp, esi
0x18000b136  mov     rbx, rsi
0x18000b139  mov     edx, 18h
0x18000b13e  mov     r8d, 66446753h
0x18000b144  mov     rcx, r14
0x18000b147  call    cs:__imp_ExAllocatePool2
0x18000b14e  nop     dword ptr [rax+rax+00h]
0x18000b153  mov     rdi, rax
0x18000b156  test    rax, rax
0x18000b159  jz      loc_18000B2D0
0x18000b15f  mov     eax, 1
0x18000b164  mov     [rdi+10h], rbx
0x18000b168  mov     [rdi+8], eax
0x18000b16b  lea     r14, [rdi+8]
0x18000b16f  mov     [rdi+0Ch], eax
0x18000b172  mov     rcx, r14
0x18000b175  lea     rax, ??_7?$sp_counted_impl_p@V?$flt_connection@Vvemgr_listener_connection_manager@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@detail@kernel_std@@6B@; const kernel_std::detail::sp_counted_impl_p<appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>>::`vftable'
0x18000b17c  mov     rsi, rdi
0x18000b17f  mov     [rdi], rax
0x18000b182  mov     eax, [r14]
0x18000b185  test    eax, eax
0x18000b187  jz      short loc_18000B197
0x18000b189  test    rbx, rbx
0x18000b18c  jnz     short loc_18000B1DA
0x18000b18e  test    rdi, rdi
0x18000b191  jz      loc_18000B331
0x18000b197  or      ebx, 0FFFFFFFFh
0x18000b19a  mov     eax, ebx
0x18000b19c  lock xadd [rcx], eax
0x18000b1a0  add     eax, ebx
0x18000b1a2  jnz     loc_18000B331
0x18000b1a8  mov     rax, [rsi]
0x18000b1ab  mov     rcx, rsi
0x18000b1ae  mov     rax, [rax+8]
0x18000b1b2  call    _guard_dispatch_icall
0x18000b1b7  mov     eax, ebx
0x18000b1b9  lock xadd [rsi+0Ch], eax
0x18000b1be  add     eax, ebx
0x18000b1c0  jnz     loc_18000B331
0x18000b1c6  mov     rax, [rsi]
0x18000b1c9  mov     rcx, rsi
0x18000b1cc  mov     rax, [rax+10h]
0x18000b1d0  call    _guard_dispatch_icall
0x18000b1d5  jmp     loc_18000B331
0x18000b1da  test    ebp, ebp
0x18000b1dc  jns     short loc_18000B21C
0x18000b1de  or      ebx, 0FFFFFFFFh
0x18000b1e1  mov     eax, ebx
0x18000b1e3  lock xadd [r14], eax
0x18000b1e8  add     eax, ebx
0x18000b1ea  jnz     short loc_18000B215
0x18000b1ec  mov     rax, [rdi]
0x18000b1ef  mov     rcx, rdi
0x18000b1f2  mov     rax, [rax+8]
0x18000b1f6  call    _guard_dispatch_icall
0x18000b1fb  mov     eax, ebx
0x18000b1fd  lock xadd [rdi+0Ch], eax
0x18000b202  add     eax, ebx
0x18000b204  jnz     short loc_18000B215
0x18000b206  mov     rax, [rdi]
0x18000b209  mov     rcx, rdi
0x18000b20c  mov     rax, [rax+10h]
0x18000b210  call    _guard_dispatch_icall
0x18000b215  mov     eax, ebp
0x18000b217  jmp     loc_18000B336
0x18000b21c  mov     rax, [rsp+78h+arg_20]
0x18000b224  mov     r8, r13
0x18000b227  mov     r9b, [r12]
0x18000b22b  mov     rdx, [rsp+78h+Filter]; Filter
0x18000b233  mov     ecx, [rax]
0x18000b235  mov     [rsp+78h+DesiredAccess], ecx; DesiredAccess
0x18000b239  mov     rcx, rbx; ServerPortCookie
0x18000b23c  call    ?initialize@?$flt_connection@Vvemgr_listener_connection_manager@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@AEAAJPEAU_FLT_FILTER@@AEAU_UNICODE_STRING@@_NK@Z; appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::initialize(_FLT_FILTER *,_UNICODE_STRING &,bool,ulong)
0x18000b241  mov     esi, eax
0x18000b243  test    eax, eax
0x18000b245  jns     short loc_18000B285
0x18000b247  or      ebx, 0FFFFFFFFh
0x18000b24a  mov     eax, ebx
0x18000b24c  lock xadd [r14], eax
0x18000b251  add     eax, ebx
0x18000b253  jnz     short loc_18000B27E
0x18000b255  mov     rax, [rdi]
0x18000b258  mov     rcx, rdi
0x18000b25b  mov     rax, [rax+8]
0x18000b25f  call    _guard_dispatch_icall
0x18000b264  mov     eax, ebx
0x18000b266  lock xadd [rdi+0Ch], eax
0x18000b26b  add     eax, ebx
0x18000b26d  jnz     short loc_18000B27E
0x18000b26f  mov     rax, [rdi]
0x18000b272  mov     rcx, rdi
0x18000b275  mov     rax, [rax+10h]
0x18000b279  call    _guard_dispatch_icall
0x18000b27e  mov     eax, esi
0x18000b280  jmp     loc_18000B336
0x18000b285  mov     rsi, [r15+8]
0x18000b289  mov     [r15], rbx
0x18000b28c  mov     [r15+8], rdi
0x18000b290  test    rsi, rsi
0x18000b293  jz      short loc_18000B2CC
0x18000b295  or      ebx, 0FFFFFFFFh
0x18000b298  mov     eax, ebx
0x18000b29a  lock xadd [rsi+8], eax
0x18000b29f  add     eax, ebx
0x18000b2a1  jnz     short loc_18000B2CC
0x18000b2a3  mov     rax, [rsi]
0x18000b2a6  mov     rcx, rsi
0x18000b2a9  mov     rax, [rax+8]
0x18000b2ad  call    _guard_dispatch_icall
0x18000b2b2  mov     eax, ebx
0x18000b2b4  lock xadd [rsi+0Ch], eax
0x18000b2b9  add     eax, ebx
0x18000b2bb  jnz     short loc_18000B2CC
0x18000b2bd  mov     rax, [rsi]
0x18000b2c0  mov     rcx, rsi
0x18000b2c3  mov     rax, [rax+10h]
0x18000b2c7  call    _guard_dispatch_icall
0x18000b2cc  xor     eax, eax
0x18000b2ce  jmp     short loc_18000B336
0x18000b2d0  test    rbx, rbx
0x18000b2d3  jz      short loc_18000B331
0x18000b2d5  mov     rcx, rbx
0x18000b2d8  call    ?disconnect_client@?$flt_connection@Vvemgr_listener_connection_manager@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::disconnect_client(void)
0x18000b2dd  mov     rcx, [rbx]; ServerPort
0x18000b2e0  test    rcx, rcx
0x18000b2e3  jz      short loc_18000B2F4
0x18000b2e5  call    cs:__imp_FltCloseCommunicationPort
0x18000b2ec  nop     dword ptr [rax+rax+00h]
0x18000b2f1  mov     [rbx], rsi
0x18000b2f4  mov     rcx, [rbx+18h]; Resource
0x18000b2f8  test    rcx, rcx
0x18000b2fb  jz      short loc_18000B320
0x18000b2fd  call    cs:__imp_ExDeleteResourceLite
0x18000b304  nop     dword ptr [rax+rax+00h]
0x18000b309  mov     rcx, [rbx+18h]; P
0x18000b30d  test    rcx, rcx
0x18000b310  jz      short loc_18000B320
0x18000b312  xor     edx, edx; Tag
0x18000b314  call    cs:__imp_ExFreePoolWithTag
0x18000b31b  nop     dword ptr [rax+rax+00h]
0x18000b320  xor     edx, edx; Tag
0x18000b322  mov     rcx, rbx; P
0x18000b325  call    cs:__imp_ExFreePoolWithTag
0x18000b32c  nop     dword ptr [rax+rax+00h]
0x18000b331  mov     eax, 0C000009Ah
0x18000b336  add     rsp, 38h
0x18000b33a  pop     r15
0x18000b33c  pop     r14
0x18000b33e  pop     r13
0x18000b340  pop     r12
0x18000b342  pop     rdi
0x18000b343  pop     rsi
0x18000b344  pop     rbp
0x18000b345  pop     rbx
0x18000b346  retn
```
