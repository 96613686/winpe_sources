# LockOrderManagerImp<WalletLockOrder>::SetCurrentThreadLockOrder(WalletLockOrder)

- ea: `0x180019f60`
- end: `0x18001a041`
- name: `?SetCurrentThreadLockOrder@?$LockOrderManagerImp@W4WalletLockOrder@@@@UEAAXW4WalletLockOrder@@@Z`
- size: `225`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180002f70`
- `0x1800171d4`
- `0x1800172b0`
- `0x1800173b0`
- `0x180019f60`
- `0x18001a978`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a03a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019f84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019f84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019f74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019f74`

## pseudocode

```c
void __fastcall LockOrderManagerImp<enum WalletLockOrder>::SetCurrentThreadLockOrder(__int64 a1, int a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  __int64 v5; // rdi
  __int64 v6; // rcx
  void *v7; // rcx
  _QWORD *v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rcx
  _BYTE v11[16]; // [rsp+20h] [rbp-30h] BYREF
  void *v12[4]; // [rsp+30h] [rbp-20h] BYREF
  int v13; // [rsp+70h] [rbp+20h] BYREF
  int v14; // [rsp+74h] [rbp+24h]
  DWORD CurrentThreadId; // [rsp+78h] [rbp+28h] BYREF
  __int64 v16; // [rsp+80h] [rbp+30h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 48);
  CurrentThreadId = GetCurrentThreadId();
  EnterCriticalSection(v4);
  v5 = a1 + 8;
  utl::_HashTable<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::find<void>(
    v5,
    &v16,
    &CurrentThreadId);
  v13 = 0;
  if ( a2 > 0 )
  {
    v14 = a2;
    if ( v16 == v5 )
    {
      LockOrderManagerImp<enum WalletLockOrder>::LockOrderThreadData::LockOrderThreadData();
      v6 = *(_QWORD *)utl::_HashTable<unsigned long,utl::pair<unsigned long const,LockOrderManagerImp<enum WalletLockOrder>::LockOrderThreadData>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,LockOrderManagerImp<enum WalletLockOrder>::LockOrderThreadData>>,0>::emplace<unsigned long &,LockOrderManagerImp<enum WalletLockOrder>::LockOrderThreadData &,0>(
                        v5,
                        (__int64)v11,
                        &CurrentThreadId,
                        (__int64)v12)
         + 32LL;
      *(_DWORD *)(v6 + 24) = a2;
      utl::list<LockOrderManagerImp<enum WalletLockOrder>::LockOrderData,utl::allocator<LockOrderManagerImp<enum WalletLockOrder>::LockOrderData>>::push_back(
        v6,
        &v13);
      while ( 1 )
      {
        v7 = v12[0];
        if ( v12[0] == v12 )
          break;
        v8 = (_QWORD *)*((_QWORD *)v12[0] + 1);
        v9 = *(_QWORD *)v12[0];
        *v8 = *(_QWORD *)v12[0];
        *(_QWORD *)(v9 + 8) = v8;
        operator delete(v7, (const struct std::nothrow_t *)&std::nothrow);
      }
    }
    else
    {
      v10 = v16 + 32;
      v13 = *(_DWORD *)(v16 + 56);
      if ( a2 > v13 )
        *(_DWORD *)(v16 + 56) = a2;
      utl::list<LockOrderManagerImp<enum WalletLockOrder>::LockOrderData,utl::allocator<LockOrderManagerImp<enum WalletLockOrder>::LockOrderData>>::push_back(
        v10,
        &v13);
    }
  }
  LeaveCriticalSection(v4);
}

```

## disassembly

```asm
0x180019f60  mov     [rsp-18h+arg_18], rbx
0x180019f65  push    rbp
0x180019f66  push    rsi
0x180019f67  push    rdi
0x180019f68  mov     rbp, rsp
0x180019f6b  sub     rsp, 50h
0x180019f6f  mov     esi, edx
0x180019f71  mov     rdi, rcx
0x180019f74  call    cs:__imp_GetCurrentThreadId
0x180019f7a  lea     rbx, [rdi+30h]
0x180019f7e  mov     [rbp+arg_8], eax
0x180019f81  mov     rcx, rbx; lpCriticalSection
0x180019f84  call    cs:__imp_EnterCriticalSection
0x180019f8a  add     rdi, 8
0x180019f8e  lea     r8, [rbp+arg_8]
0x180019f92  mov     rcx, rdi
0x180019f95  lea     rdx, [rbp+arg_10]
0x180019f99  call    ??$find@X@?$_HashTable@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@3@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@utl@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@2@@1@AEBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Z; utl::_HashTable<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::find<void>(__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const &)
0x180019f9e  mov     [rbp+arg_0], 0
0x180019fa5  test    esi, esi
0x180019fa7  jle     short loc_18001A028
0x180019fa9  mov     rax, [rbp+arg_10]
0x180019fad  mov     [rbp+arg_4], esi
0x180019fb0  cmp     rax, rdi
0x180019fb3  jnz     short loc_18001A00E
0x180019fb5  lea     rcx, [rbp+var_20]
0x180019fb9  call    ??0LockOrderThreadData@?$LockOrderManagerImp@W4WalletLockOrder@@@@QEAA@XZ; LockOrderManagerImp<WalletLockOrder>::LockOrderThreadData::LockOrderThreadData(void)
0x180019fbe  lea     r9, [rbp+var_20]
0x180019fc2  mov     rcx, rdi
0x180019fc5  lea     r8, [rbp+arg_8]
0x180019fc9  lea     rdx, [rbp+var_30]
0x180019fcd  call    ??$emplace@AEAKAEAULockOrderThreadData@?$LockOrderManagerImp@W4WalletLockOrder@@@@$0A@@?$_HashTable@KU?$pair@$$CBKULockOrderThreadData@?$LockOrderManagerImp@W4WalletLockOrder@@@@@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKULockOrderThreadData@?$LockOrderManagerImp@W4WalletLockOrder@@@@@utl@@@2@$0A@@utl@@QEAA?AU?$pair@V?$_DlistIt@U?$_HashNode@U?$pair@$$CBKULockOrderThreadData@?$LockOrderManagerImp@W4WalletLockOrder@@@@@utl@@@utl@@U?$pair@$$CBKULockOrderThreadData@?$LockOrderManagerImp@W4WalletLockOrder@@@@@2@@utl@@_N@1@AEAKAEAULockOrderThreadData@?$LockOrderManagerImp@W4WalletLockOrder@@@@@Z; utl::_HashTable<ulong,utl::pair<ulong const,LockOrderManagerImp<WalletLockOrder>::LockOrderThreadData>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,LockOrderManagerImp<WalletLockOrder>::LockOrderThreadData>>,0>::emplace<ulong &,LockOrderManagerImp<WalletLockOrder>::LockOrderThreadData &,0>(ulong &,LockOrderManagerImp<WalletLockOrder>::LockOrderThreadData &)
0x180019fd2  lea     rdx, [rbp+arg_0]
0x180019fd6  mov     rcx, [rax]
0x180019fd9  add     rcx, 20h ; ' '
0x180019fdd  mov     [rcx+18h], esi
0x180019fe0  call    ?push_back@?$list@ULockOrderData@?$LockOrderManagerImp@W4WalletLockOrder@@@@V?$allocator@ULockOrderData@?$LockOrderManagerImp@W4WalletLockOrder@@@@@utl@@@utl@@QEAA_NAEBULockOrderData@?$LockOrderManagerImp@W4WalletLockOrder@@@@@Z; utl::list<LockOrderManagerImp<WalletLockOrder>::LockOrderData,utl::allocator<LockOrderManagerImp<WalletLockOrder>::LockOrderData>>::push_back(LockOrderManagerImp<WalletLockOrder>::LockOrderData const &)
0x180019fe5  mov     rcx, [rbp+var_20]; void *
0x180019fe9  lea     rax, [rbp+var_20]
0x180019fed  cmp     rcx, rax
0x180019ff0  jz      short loc_18001A028
0x180019ff2  mov     rdx, [rcx+8]
0x180019ff6  mov     rax, [rcx]
0x180019ff9  mov     [rdx], rax
0x180019ffc  mov     [rax+8], rdx
0x18001a000  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a007  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a00c  jmp     short loc_180019FE5
0x18001a00e  lea     rcx, [rax+20h]
0x18001a012  mov     edx, [rcx+18h]
0x18001a015  mov     [rbp+arg_0], edx
0x18001a018  cmp     esi, edx
0x18001a01a  jle     short loc_18001A01F
0x18001a01c  mov     [rax+38h], esi
0x18001a01f  lea     rdx, [rbp+arg_0]
0x18001a023  call    ?push_back@?$list@ULockOrderData@?$LockOrderManagerImp@W4WalletLockOrder@@@@V?$allocator@ULockOrderData@?$LockOrderManagerImp@W4WalletLockOrder@@@@@utl@@@utl@@QEAA_NAEBULockOrderData@?$LockOrderManagerImp@W4WalletLockOrder@@@@@Z; utl::list<LockOrderManagerImp<WalletLockOrder>::LockOrderData,utl::allocator<LockOrderManagerImp<WalletLockOrder>::LockOrderData>>::push_back(LockOrderManagerImp<WalletLockOrder>::LockOrderData const &)
0x18001a028  mov     rcx, rbx
0x18001a02b  mov     rbx, [rsp+50h+arg_18]
0x18001a033  add     rsp, 50h
0x18001a037  pop     rdi
0x18001a038  pop     rsi
0x18001a039  pop     rbp
0x18001a03a  jmp     cs:__imp_LeaveCriticalSection
```
