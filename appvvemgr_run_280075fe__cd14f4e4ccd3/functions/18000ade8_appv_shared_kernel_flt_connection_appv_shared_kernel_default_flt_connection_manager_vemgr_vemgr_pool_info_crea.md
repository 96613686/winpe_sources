# appv::shared::kernel::flt_connection<appv::shared::kernel::default_flt_connection_manager,vemgr::vemgr_pool_info>::create_connection(kernel_std::shared_ptr<appv::shared::kernel::flt_connection<appv::shared::kernel::default_flt_connection_manager,vemgr::vemgr_pool_info>> &,_FLT_FILTER *,_UNICODE_STRING &,bool const &,ulong const &)

- ea: `0x18000ade8`
- end: `0x18000b094`
- name: `?create_connection@?$flt_connection@Vdefault_flt_connection_manager@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@SAJAEAV?$shared_ptr@V?$flt_connection@Vdefault_flt_connection_manager@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel_std@@PEAU_FLT_FILTER@@AEAU_UNICODE_STRING@@AEB_NAEBK@Z`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000a050`

## callees

- `0x18000ade8`
- `0x18000bb18`
- `0x18000d42c`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000ae1c`
- `ntoskrnl!ExAllocatePool2` at `0x18000ae49`
- `ntoskrnl!ExAllocatePool2` at `0x18000ae93`
- `ntoskrnl!ExAllocatePool2` at `0x18000ae1c`
- `ntoskrnl!ExAllocatePool2` at `0x18000ae49`
- `ntoskrnl!ExAllocatePool2` at `0x18000ae93`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000b060`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000b071`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000b060`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000b071`
- `ntoskrnl!ExInitializeResourceLite` at `0x18000ae68`
- `ntoskrnl!ExInitializeResourceLite` at `0x18000ae68`
- `ntoskrnl!ExDeleteResourceLite` at `0x18000b049`
- `ntoskrnl!ExDeleteResourceLite` at `0x18000b049`
- `FLTMGR!FltCloseCommunicationPort` at `0x18000b031`
- `FLTMGR!FltCloseCommunicationPort` at `0x18000b031`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::flt_connection<appv::shared::kernel::default_flt_connection_manager,vemgr::vemgr_pool_info>::create_connection(
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
    v16 = appv::shared::kernel::flt_connection<appv::shared::kernel::default_flt_connection_manager,vemgr::vemgr_pool_info>::initialize(
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
0x18000ade8  mov     [rsp+Filter], rdx
0x18000aded  push    rbx
0x18000adee  push    rbp
0x18000adef  push    rsi
0x18000adf0  push    rdi
0x18000adf1  push    r12
0x18000adf3  push    r13
0x18000adf5  push    r14
0x18000adf7  push    r15
0x18000adf9  sub     rsp, 38h
0x18000adfd  mov     r13, r8
0x18000ae00  mov     r15, rcx
0x18000ae03  mov     edi, 674D6556h
0x18000ae08  mov     r14d, 100h
0x18000ae0e  mov     r8d, edi
0x18000ae11  mov     ecx, r14d
0x18000ae14  mov     edx, 30h ; '0'
0x18000ae19  mov     r12, r9
0x18000ae1c  call    cs:__imp_ExAllocatePool2
0x18000ae23  nop     dword ptr [rax+rax+00h]
0x18000ae28  xor     esi, esi
0x18000ae2a  mov     rbx, rax
0x18000ae2d  test    rax, rax
0x18000ae30  jz      short loc_18000AE80
0x18000ae32  mov     [rax], rsi
0x18000ae35  lea     edx, [rsi+68h]
0x18000ae38  mov     [rax+8], rsi
0x18000ae3c  lea     ecx, [rsi+40h]
0x18000ae3f  mov     r8d, edi
0x18000ae42  mov     [rax+18h], rsi
0x18000ae46  mov     [rax+10h], edi
0x18000ae49  call    cs:__imp_ExAllocatePool2
0x18000ae50  nop     dword ptr [rax+rax+00h]
0x18000ae55  mov     [rbx+18h], rax
0x18000ae59  test    rax, rax
0x18000ae5c  jnz     short loc_18000AE65
0x18000ae5e  mov     ebp, 0C000009Ah
0x18000ae63  jmp     short loc_18000AE76
0x18000ae65  mov     rcx, rax; Resource
0x18000ae68  call    cs:__imp_ExInitializeResourceLite
0x18000ae6f  nop     dword ptr [rax+rax+00h]
0x18000ae74  mov     ebp, eax
0x18000ae76  mov     [rbx+20h], sil
0x18000ae7a  mov     [rbx+28h], rsi
0x18000ae7e  jmp     short loc_18000AE85
0x18000ae80  mov     ebp, esi
0x18000ae82  mov     rbx, rsi
0x18000ae85  mov     edx, 18h
0x18000ae8a  mov     r8d, 66446753h
0x18000ae90  mov     rcx, r14
0x18000ae93  call    cs:__imp_ExAllocatePool2
0x18000ae9a  nop     dword ptr [rax+rax+00h]
0x18000ae9f  mov     rdi, rax
0x18000aea2  test    rax, rax
0x18000aea5  jz      loc_18000B01C
0x18000aeab  mov     eax, 1
0x18000aeb0  mov     [rdi+10h], rbx
0x18000aeb4  mov     [rdi+8], eax
0x18000aeb7  lea     r14, [rdi+8]
0x18000aebb  mov     [rdi+0Ch], eax
0x18000aebe  mov     rcx, r14
0x18000aec1  lea     rax, ??_7?$sp_counted_impl_p@V?$flt_connection@Vvemgr_listener_connection_manager@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@detail@kernel_std@@6B@; const kernel_std::detail::sp_counted_impl_p<appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>>::`vftable'
0x18000aec8  mov     rsi, rdi
0x18000aecb  mov     [rdi], rax
0x18000aece  mov     eax, [r14]
0x18000aed1  test    eax, eax
0x18000aed3  jz      short loc_18000AEE3
0x18000aed5  test    rbx, rbx
0x18000aed8  jnz     short loc_18000AF26
0x18000aeda  test    rdi, rdi
0x18000aedd  jz      loc_18000B07D
0x18000aee3  or      ebx, 0FFFFFFFFh
0x18000aee6  mov     eax, ebx
0x18000aee8  lock xadd [rcx], eax
0x18000aeec  add     eax, ebx
0x18000aeee  jnz     loc_18000B07D
0x18000aef4  mov     rax, [rsi]
0x18000aef7  mov     rcx, rsi
0x18000aefa  mov     rax, [rax+8]
0x18000aefe  call    _guard_dispatch_icall
0x18000af03  mov     eax, ebx
0x18000af05  lock xadd [rsi+0Ch], eax
0x18000af0a  add     eax, ebx
0x18000af0c  jnz     loc_18000B07D
0x18000af12  mov     rax, [rsi]
0x18000af15  mov     rcx, rsi
0x18000af18  mov     rax, [rax+10h]
0x18000af1c  call    _guard_dispatch_icall
0x18000af21  jmp     loc_18000B07D
0x18000af26  test    ebp, ebp
0x18000af28  jns     short loc_18000AF68
0x18000af2a  or      ebx, 0FFFFFFFFh
0x18000af2d  mov     eax, ebx
0x18000af2f  lock xadd [r14], eax
0x18000af34  add     eax, ebx
0x18000af36  jnz     short loc_18000AF61
0x18000af38  mov     rax, [rdi]
0x18000af3b  mov     rcx, rdi
0x18000af3e  mov     rax, [rax+8]
0x18000af42  call    _guard_dispatch_icall
0x18000af47  mov     eax, ebx
0x18000af49  lock xadd [rdi+0Ch], eax
0x18000af4e  add     eax, ebx
0x18000af50  jnz     short loc_18000AF61
0x18000af52  mov     rax, [rdi]
0x18000af55  mov     rcx, rdi
0x18000af58  mov     rax, [rax+10h]
0x18000af5c  call    _guard_dispatch_icall
0x18000af61  mov     eax, ebp
0x18000af63  jmp     loc_18000B082
0x18000af68  mov     rax, [rsp+78h+arg_20]
0x18000af70  mov     r8, r13
0x18000af73  mov     r9b, [r12]
0x18000af77  mov     rdx, [rsp+78h+Filter]; Filter
0x18000af7f  mov     ecx, [rax]
0x18000af81  mov     [rsp+78h+DesiredAccess], ecx; DesiredAccess
0x18000af85  mov     rcx, rbx; ServerPortCookie
0x18000af88  call    ?initialize@?$flt_connection@Vdefault_flt_connection_manager@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@AEAAJPEAU_FLT_FILTER@@AEAU_UNICODE_STRING@@_NK@Z; appv::shared::kernel::flt_connection<appv::shared::kernel::default_flt_connection_manager,vemgr::vemgr_pool_info>::initialize(_FLT_FILTER *,_UNICODE_STRING &,bool,ulong)
0x18000af8d  mov     esi, eax
0x18000af8f  test    eax, eax
0x18000af91  jns     short loc_18000AFD1
0x18000af93  or      ebx, 0FFFFFFFFh
0x18000af96  mov     eax, ebx
0x18000af98  lock xadd [r14], eax
0x18000af9d  add     eax, ebx
0x18000af9f  jnz     short loc_18000AFCA
0x18000afa1  mov     rax, [rdi]
0x18000afa4  mov     rcx, rdi
0x18000afa7  mov     rax, [rax+8]
0x18000afab  call    _guard_dispatch_icall
0x18000afb0  mov     eax, ebx
0x18000afb2  lock xadd [rdi+0Ch], eax
0x18000afb7  add     eax, ebx
0x18000afb9  jnz     short loc_18000AFCA
0x18000afbb  mov     rax, [rdi]
0x18000afbe  mov     rcx, rdi
0x18000afc1  mov     rax, [rax+10h]
0x18000afc5  call    _guard_dispatch_icall
0x18000afca  mov     eax, esi
0x18000afcc  jmp     loc_18000B082
0x18000afd1  mov     rsi, [r15+8]
0x18000afd5  mov     [r15], rbx
0x18000afd8  mov     [r15+8], rdi
0x18000afdc  test    rsi, rsi
0x18000afdf  jz      short loc_18000B018
0x18000afe1  or      ebx, 0FFFFFFFFh
0x18000afe4  mov     eax, ebx
0x18000afe6  lock xadd [rsi+8], eax
0x18000afeb  add     eax, ebx
0x18000afed  jnz     short loc_18000B018
0x18000afef  mov     rax, [rsi]
0x18000aff2  mov     rcx, rsi
0x18000aff5  mov     rax, [rax+8]
0x18000aff9  call    _guard_dispatch_icall
0x18000affe  mov     eax, ebx
0x18000b000  lock xadd [rsi+0Ch], eax
0x18000b005  add     eax, ebx
0x18000b007  jnz     short loc_18000B018
0x18000b009  mov     rax, [rsi]
0x18000b00c  mov     rcx, rsi
0x18000b00f  mov     rax, [rax+10h]
0x18000b013  call    _guard_dispatch_icall
0x18000b018  xor     eax, eax
0x18000b01a  jmp     short loc_18000B082
0x18000b01c  test    rbx, rbx
0x18000b01f  jz      short loc_18000B07D
0x18000b021  mov     rcx, rbx
0x18000b024  call    ?disconnect_client@?$flt_connection@Vvemgr_listener_connection_manager@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::flt_connection<vemgr_listener_connection_manager,vemgr::vemgr_pool_info>::disconnect_client(void)
0x18000b029  mov     rcx, [rbx]; ServerPort
0x18000b02c  test    rcx, rcx
0x18000b02f  jz      short loc_18000B040
0x18000b031  call    cs:__imp_FltCloseCommunicationPort
0x18000b038  nop     dword ptr [rax+rax+00h]
0x18000b03d  mov     [rbx], rsi
0x18000b040  mov     rcx, [rbx+18h]; Resource
0x18000b044  test    rcx, rcx
0x18000b047  jz      short loc_18000B06C
0x18000b049  call    cs:__imp_ExDeleteResourceLite
0x18000b050  nop     dword ptr [rax+rax+00h]
0x18000b055  mov     rcx, [rbx+18h]; P
0x18000b059  test    rcx, rcx
0x18000b05c  jz      short loc_18000B06C
0x18000b05e  xor     edx, edx; Tag
0x18000b060  call    cs:__imp_ExFreePoolWithTag
0x18000b067  nop     dword ptr [rax+rax+00h]
0x18000b06c  xor     edx, edx; Tag
0x18000b06e  mov     rcx, rbx; P
0x18000b071  call    cs:__imp_ExFreePoolWithTag
0x18000b078  nop     dword ptr [rax+rax+00h]
0x18000b07d  mov     eax, 0C000009Ah
0x18000b082  add     rsp, 38h
0x18000b086  pop     r15
0x18000b088  pop     r14
0x18000b08a  pop     r13
0x18000b08c  pop     r12
0x18000b08e  pop     rdi
0x18000b08f  pop     rsi
0x18000b090  pop     rbp
0x18000b091  pop     rbx
0x18000b092  retn
```
