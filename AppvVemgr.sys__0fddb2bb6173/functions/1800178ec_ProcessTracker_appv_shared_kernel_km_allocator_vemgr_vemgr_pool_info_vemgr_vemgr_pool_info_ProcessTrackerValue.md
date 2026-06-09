# ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue::FindJitvThread(ulong,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)

- ea: `0x1800178ec`
- end: `0x180017a5b`
- name: `?FindJitvThread@ProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJKAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `367`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180019624`

## callees

- `0x180005430`
- `0x1800178ec`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x18001792b`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x18001792b`

## pseudocode

```c
__int64 __fastcall ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue::FindJitvThread(
        __int64 a1,
        int a2,
        __int64 a3)
{
  struct _RTL_AVL_TABLE *v3; // rcx
  char v5; // di
  char v6; // si
  PVOID v7; // rax
  volatile signed __int32 *v8; // rbx
  volatile signed __int32 *v9; // rbx
  volatile signed __int32 *v10; // rbx
  __int128 v12; // [rsp+28h] [rbp-30h] BYREF
  int Buffer; // [rsp+38h] [rbp-20h] BYREF
  __int128 v14; // [rsp+40h] [rbp-18h]

  v3 = *(struct _RTL_AVL_TABLE **)(a1 + 48);
  Buffer = a2;
  v5 = 1;
  v12 = 0;
  v14 = 0;
  if ( v3 && (v7 = RtlLookupElementGenericTableAvl(v3, &Buffer)) != 0 )
  {
    *(_QWORD *)&v12 = *((_QWORD *)v7 + 1);
    kernel_std::detail::shared_count::operator=(
      (volatile signed __int32 **)&v12 + 1,
      (volatile signed __int32 **)v7 + 2);
    v6 = 1;
  }
  else
  {
    v6 = 0;
  }
  v8 = (volatile signed __int32 *)*((_QWORD *)&v14 + 1);
  if ( *((_QWORD *)&v14 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v14 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 16LL))(v8);
    }
  }
  if ( v6 )
  {
    *(_QWORD *)a3 = v12;
    kernel_std::detail::shared_count::operator=(
      (volatile signed __int32 **)(a3 + 8),
      (volatile signed __int32 **)&v12 + 1);
    v10 = (volatile signed __int32 *)*((_QWORD *)&v12 + 1);
    if ( *((_QWORD *)&v12 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v12 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 16LL))(v10);
      }
    }
  }
  else
  {
    v9 = (volatile signed __int32 *)*((_QWORD *)&v12 + 1);
    if ( *((_QWORD *)&v12 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v12 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
      }
    }
    v5 = 0;
  }
  return v5 == 0 ? 0xC0000034 : 0;
}

```

## disassembly

```asm
0x1800178ec  push    rbp
0x1800178ee  push    rbx
0x1800178ef  push    rsi
0x1800178f0  push    rdi
0x1800178f1  push    r14
0x1800178f3  push    r15
0x1800178f5  mov     rbp, rsp
0x1800178f8  sub     rsp, 58h
0x1800178fc  mov     rcx, [rcx+30h]; Table
0x180017900  xorps   xmm0, xmm0
0x180017903  mov     [rbp+var_38], 0
0x18001790a  mov     r14, r8
0x18001790d  mov     [rbp+Buffer], edx
0x180017910  mov     dil, 1
0x180017913  movdqu  [rbp+var_30], xmm0
0x180017918  movdqu  [rbp+var_18], xmm0
0x18001791d  test    rcx, rcx
0x180017920  jnz     short loc_180017927
0x180017922  xor     sil, sil
0x180017925  jmp     short loc_18001795C
0x180017927  lea     rdx, [rbp+Buffer]; Buffer
0x18001792b  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180017932  nop     dword ptr [rax+rax+00h]
0x180017937  mov     rdx, rax
0x18001793a  test    rax, rax
0x18001793d  jz      short loc_180017922
0x18001793f  mov     eax, [rax]
0x180017941  lea     rcx, [rbp+var_30+8]
0x180017945  mov     [rbp+var_38], eax
0x180017948  mov     rax, [rdx+8]
0x18001794c  add     rdx, 10h
0x180017950  mov     qword ptr [rbp+var_30], rax
0x180017954  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x180017959  mov     sil, dil
0x18001795c  mov     rbx, qword ptr [rbp+var_18+8]
0x180017960  or      r15d, 0FFFFFFFFh
0x180017964  test    rbx, rbx
0x180017967  jz      short loc_1800179A1
0x180017969  mov     eax, r15d
0x18001796c  lock xadd [rbx+8], eax
0x180017971  add     eax, r15d
0x180017974  jnz     short loc_1800179A1
0x180017976  mov     rax, [rbx]
0x180017979  mov     rcx, rbx
0x18001797c  mov     rax, [rax+8]
0x180017980  call    _guard_dispatch_icall
0x180017985  mov     eax, r15d
0x180017988  lock xadd [rbx+0Ch], eax
0x18001798d  add     eax, r15d
0x180017990  jnz     short loc_1800179A1
0x180017992  mov     rax, [rbx]
0x180017995  mov     rcx, rbx
0x180017998  mov     rax, [rax+10h]
0x18001799c  call    _guard_dispatch_icall
0x1800179a1  test    sil, sil
0x1800179a4  jnz     short loc_1800179EC
0x1800179a6  mov     rbx, qword ptr [rbp+var_30+8]
0x1800179aa  test    rbx, rbx
0x1800179ad  jz      short loc_1800179E7
0x1800179af  mov     eax, r15d
0x1800179b2  lock xadd [rbx+8], eax
0x1800179b7  add     eax, r15d
0x1800179ba  jnz     short loc_1800179E7
0x1800179bc  mov     rax, [rbx]
0x1800179bf  mov     rcx, rbx
0x1800179c2  mov     rax, [rax+8]
0x1800179c6  call    _guard_dispatch_icall
0x1800179cb  mov     eax, r15d
0x1800179ce  lock xadd [rbx+0Ch], eax
0x1800179d3  add     eax, r15d
0x1800179d6  jnz     short loc_1800179E7
0x1800179d8  mov     rax, [rbx]
0x1800179db  mov     rcx, rbx
0x1800179de  mov     rax, [rax+10h]
0x1800179e2  call    _guard_dispatch_icall
0x1800179e7  xor     dil, dil
0x1800179ea  jmp     short loc_180017A41
0x1800179ec  mov     rax, qword ptr [rbp+var_30]
0x1800179f0  lea     rcx, [r14+8]
0x1800179f4  lea     rdx, [rbp+var_30+8]
0x1800179f8  mov     [r14], rax
0x1800179fb  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x180017a00  mov     rbx, qword ptr [rbp+var_30+8]
0x180017a04  test    rbx, rbx
0x180017a07  jz      short loc_180017A41
0x180017a09  mov     eax, r15d
0x180017a0c  lock xadd [rbx+8], eax
0x180017a11  add     eax, r15d
0x180017a14  jnz     short loc_180017A41
0x180017a16  mov     rax, [rbx]
0x180017a19  mov     rcx, rbx
0x180017a1c  mov     rax, [rax+8]
0x180017a20  call    _guard_dispatch_icall
0x180017a25  mov     eax, r15d
0x180017a28  lock xadd [rbx+0Ch], eax
0x180017a2d  add     eax, r15d
0x180017a30  jnz     short loc_180017A41
0x180017a32  mov     rax, [rbx]
0x180017a35  mov     rcx, rbx
0x180017a38  mov     rax, [rax+10h]
0x180017a3c  call    _guard_dispatch_icall
0x180017a41  neg     dil
0x180017a44  sbb     eax, eax
0x180017a46  not     eax
0x180017a48  and     eax, 0C0000034h
0x180017a4d  add     rsp, 58h
0x180017a51  pop     r15
0x180017a53  pop     r14
0x180017a55  pop     rdi
0x180017a56  pop     rsi
0x180017a57  pop     rbx
0x180017a58  pop     rbp
0x180017a59  retn
```
