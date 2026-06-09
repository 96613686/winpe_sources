# ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveUser<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)

- ea: `0x1800105f4`
- end: `0x1800107dc`
- name: `??$RemoveUser@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@00@Z`
- size: `488`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800130ec`

## callees

- `0x18000e960`
- `0x1800105f4`
- `0x180014470`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1800107b0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1800107b0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800107bc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800107bc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180010636`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180010636`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001061e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001061e`

## pseudocode

```c
__int64 __fastcall ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveUser<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  bool v8; // bp
  unsigned int v9; // ecx
  __int16 v10; // dx
  __int16 v11; // ax
  __int64 v12; // r8
  unsigned int v13; // ecx
  __int16 v14; // dx
  __int16 v15; // ax
  __int64 v16; // r10
  unsigned int v17; // ecx
  bool v18; // cc
  __int16 v19; // dx
  __int16 v20; // ax
  __int64 v21; // rcx
  int v22; // edi
  unsigned int v23; // ecx
  __int16 v24; // dx
  __int16 v25; // ax
  __int64 v26; // r8
  unsigned int v27; // ecx
  __int16 v28; // dx
  __int16 v29; // ax
  __int64 v30; // r9
  unsigned int v31; // ecx
  bool v32; // cc
  __int16 v33; // dx
  __int16 v34; // ax
  __int64 v35; // rcx
  volatile signed __int32 *v36; // rbx
  struct _ERESOURCE *v37; // rcx
  __int128 v39; // [rsp+20h] [rbp-58h] BYREF

  v8 = 0;
  if ( *(_QWORD *)(a1 + 88) )
  {
    KeEnterCriticalRegion();
    v8 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 88), 1u) == 1;
  }
  v9 = *(_DWORD *)a4 >> 1;
  v39 = 0;
  if ( v9 > 0xFFFF )
    v10 = -1;
  else
    v10 = v9;
  v11 = 0;
  v12 = 0;
  if ( v9 <= 0xFFFF )
    v11 = v10;
  if ( v11 )
    v12 = *(_QWORD *)(a4 + 8);
  v13 = *(_DWORD *)a3 >> 1;
  if ( v13 > 0xFFFF )
    v14 = -1;
  else
    v14 = *(_DWORD *)a3 >> 1;
  v15 = 0;
  v16 = 0;
  if ( v13 <= 0xFFFF )
    v15 = v14;
  if ( v15 )
    v16 = *(_QWORD *)(a3 + 8);
  v17 = *(_DWORD *)a2 >> 1;
  v18 = v17 <= 0xFFFF;
  if ( v17 > 0xFFFF )
    v19 = -1;
  else
    v19 = *(_DWORD *)a2 >> 1;
  v20 = 0;
  v21 = 0;
  if ( v18 )
    v20 = v19;
  if ( v20 )
    v21 = *(_QWORD *)(a2 + 8);
  v22 = ((__int64 (__fastcall *)(__int64, __int64, __int64, __int128 *))Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve)(
          v21,
          v16,
          v12,
          &v39);
  if ( v22 >= 0 )
  {
    v23 = *(_DWORD *)a4 >> 1;
    if ( v23 > 0xFFFF )
      v24 = -1;
    else
      v24 = *(_DWORD *)a4 >> 1;
    v25 = 0;
    v26 = 0;
    if ( v23 <= 0xFFFF )
      v25 = v24;
    if ( v25 )
      v26 = *(_QWORD *)(a4 + 8);
    v27 = *(_DWORD *)a3 >> 1;
    if ( v27 > 0xFFFF )
      v28 = -1;
    else
      v28 = *(_DWORD *)a3 >> 1;
    v29 = 0;
    v30 = 0;
    if ( v27 <= 0xFFFF )
      v29 = v28;
    if ( v29 )
      v30 = *(_QWORD *)(a3 + 8);
    v31 = *(_DWORD *)a2 >> 1;
    v32 = v31 <= 0xFFFF;
    if ( v31 > 0xFFFF )
      v33 = -1;
    else
      v33 = *(_DWORD *)a2 >> 1;
    v34 = 0;
    v35 = 0;
    if ( v32 )
      v34 = v33;
    if ( v34 )
      v35 = *(_QWORD *)(a2 + 8);
    v22 = Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_user(
            v35,
            v30,
            v26);
  }
  if ( v22 == -1073741772 || v22 == -1073741766 )
    v22 = 0;
  v36 = (volatile signed __int32 *)*((_QWORD *)&v39 + 1);
  if ( *((_QWORD *)&v39 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v39 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
      if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 16LL))(v36);
    }
  }
  if ( v8 )
  {
    v37 = *(struct _ERESOURCE **)(a1 + 88);
    if ( v37 )
    {
      ExReleaseResourceLite(v37);
      KeLeaveCriticalRegion();
    }
  }
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x1800105f4  push    rbx
0x1800105f6  push    rbp
0x1800105f7  push    rsi
0x1800105f8  push    rdi
0x1800105f9  push    r12
0x1800105fb  push    r13
0x1800105fd  push    r14
0x1800105ff  push    r15
0x180010601  sub     rsp, 38h
0x180010605  xor     r12d, r12d
0x180010608  mov     rbx, r9
0x18001060b  mov     rsi, r8
0x18001060e  mov     r14, rdx
0x180010611  mov     r15, rcx
0x180010614  movzx   ebp, r12b
0x180010618  cmp     [rcx+58h], r12
0x18001061c  jz      short loc_180010648
0x18001061e  call    cs:__imp_KeEnterCriticalRegion
0x180010625  nop     dword ptr [rax+rax+00h]
0x18001062a  mov     rcx, [r15+58h]; Resource
0x18001062e  lea     edi, [r12+1]
0x180010633  mov     dl, dil; Wait
0x180010636  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18001063d  nop     dword ptr [rax+rax+00h]
0x180010642  cmp     al, dil
0x180010645  cmovz   ebp, edi
0x180010648  mov     ecx, [rbx]
0x18001064a  mov     r13d, 0FFFFh
0x180010650  shr     ecx, 1
0x180010652  xorps   xmm0, xmm0
0x180010655  movdqu  [rsp+78h+var_58], xmm0
0x18001065b  cmp     ecx, r13d
0x18001065e  ja      short loc_180010665
0x180010660  movzx   edx, cx
0x180010663  jmp     short loc_180010668
0x180010665  mov     edx, r13d
0x180010668  mov     eax, r12d
0x18001066b  mov     r8, r12
0x18001066e  cmovbe  ax, dx
0x180010672  test    ax, ax
0x180010675  jz      short loc_18001067B
0x180010677  mov     r8, [rbx+8]
0x18001067b  mov     ecx, [rsi]
0x18001067d  shr     ecx, 1
0x18001067f  cmp     ecx, r13d
0x180010682  ja      short loc_180010689
0x180010684  movzx   edx, cx
0x180010687  jmp     short loc_18001068C
0x180010689  mov     edx, r13d
0x18001068c  mov     eax, r12d
0x18001068f  mov     r10, r12
0x180010692  cmovbe  ax, dx
0x180010696  test    ax, ax
0x180010699  jz      short loc_18001069F
0x18001069b  mov     r10, [rsi+8]
0x18001069f  mov     ecx, [r14]
0x1800106a2  shr     ecx, 1
0x1800106a4  cmp     ecx, r13d
0x1800106a7  ja      short loc_1800106AE
0x1800106a9  movzx   edx, cx
0x1800106ac  jmp     short loc_1800106B1
0x1800106ae  mov     edx, r13d
0x1800106b1  mov     eax, r12d
0x1800106b4  mov     rcx, r12
0x1800106b7  cmovbe  ax, dx
0x1800106bb  test    ax, ax
0x1800106be  jz      short loc_1800106C4
0x1800106c0  mov     rcx, [r14+8]
0x1800106c4  lea     r9, [rsp+78h+var_58]
0x1800106c9  mov     rdx, r10
0x1800106cc  call    ?retrieve@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_W00AEAV?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::retrieve(wchar_t const *,wchar_t const *,wchar_t const *,kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x1800106d1  mov     edi, eax
0x1800106d3  test    eax, eax
0x1800106d5  js      short loc_18001074E
0x1800106d7  mov     ecx, [rbx]
0x1800106d9  shr     ecx, 1
0x1800106db  cmp     ecx, r13d
0x1800106de  ja      short loc_1800106E5
0x1800106e0  movzx   edx, cx
0x1800106e3  jmp     short loc_1800106E8
0x1800106e5  mov     edx, r13d
0x1800106e8  mov     eax, r12d
0x1800106eb  mov     r8, r12
0x1800106ee  cmovbe  ax, dx
0x1800106f2  test    ax, ax
0x1800106f5  jz      short loc_1800106FB
0x1800106f7  mov     r8, [rbx+8]
0x1800106fb  mov     ecx, [rsi]
0x1800106fd  shr     ecx, 1
0x1800106ff  cmp     ecx, r13d
0x180010702  ja      short loc_180010709
0x180010704  movzx   edx, cx
0x180010707  jmp     short loc_18001070C
0x180010709  mov     edx, r13d
0x18001070c  mov     eax, r12d
0x18001070f  mov     r9, r12
0x180010712  cmovbe  ax, dx
0x180010716  test    ax, ax
0x180010719  jz      short loc_18001071F
0x18001071b  mov     r9, [rsi+8]
0x18001071f  mov     ecx, [r14]
0x180010722  shr     ecx, 1
0x180010724  cmp     ecx, r13d
0x180010727  ja      short loc_18001072E
0x180010729  movzx   edx, cx
0x18001072c  jmp     short loc_180010731
0x18001072e  mov     edx, r13d
0x180010731  mov     eax, r12d
0x180010734  mov     rcx, r12
0x180010737  cmovbe  ax, dx
0x18001073b  test    ax, ax
0x18001073e  jz      short loc_180010744
0x180010740  mov     rcx, [r14+8]
0x180010744  mov     rdx, r9
0x180010747  call    ?remove_user@?$Data_Store@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@SAJPEB_W00@Z; Data_Store<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::remove_user(wchar_t const *,wchar_t const *,wchar_t const *)
0x18001074c  mov     edi, eax
0x18001074e  cmp     edi, 0C0000034h
0x180010754  jz      short loc_18001075E
0x180010756  cmp     edi, 0C000003Ah
0x18001075c  jnz     short loc_180010761
0x18001075e  mov     edi, r12d
0x180010761  mov     rbx, qword ptr [rsp+78h+var_58+8]
0x180010766  test    rbx, rbx
0x180010769  jz      short loc_1800107A2
0x18001076b  or      esi, 0FFFFFFFFh
0x18001076e  mov     eax, esi
0x180010770  lock xadd [rbx+8], eax
0x180010775  add     eax, esi
0x180010777  jnz     short loc_1800107A2
0x180010779  mov     rax, [rbx]
0x18001077c  mov     rcx, rbx
0x18001077f  mov     rax, [rax+8]
0x180010783  call    _guard_dispatch_icall
0x180010788  mov     eax, esi
0x18001078a  lock xadd [rbx+0Ch], eax
0x18001078f  add     eax, esi
0x180010791  jnz     short loc_1800107A2
0x180010793  mov     rax, [rbx]
0x180010796  mov     rcx, rbx
0x180010799  mov     rax, [rax+10h]
0x18001079d  call    _guard_dispatch_icall
0x1800107a2  test    bpl, bpl
0x1800107a5  jz      short loc_1800107C8
0x1800107a7  mov     rcx, [r15+58h]; Resource
0x1800107ab  test    rcx, rcx
0x1800107ae  jz      short loc_1800107C8
0x1800107b0  call    cs:__imp_ExReleaseResourceLite
0x1800107b7  nop     dword ptr [rax+rax+00h]
0x1800107bc  call    cs:__imp_KeLeaveCriticalRegion
0x1800107c3  nop     dword ptr [rax+rax+00h]
0x1800107c8  mov     eax, edi
0x1800107ca  add     rsp, 38h
0x1800107ce  pop     r15
0x1800107d0  pop     r14
0x1800107d2  pop     r13
0x1800107d4  pop     r12
0x1800107d6  pop     rdi
0x1800107d7  pop     rsi
0x1800107d8  pop     rbp
0x1800107d9  pop     rbx
0x1800107da  retn
```
