# Wallet::WalletItemManager::GetPropertyValue(__MIDL___MIDL_itf_wallettypes_0000_0000_0010,tagPROPVARIANT *)

- ea: `0x180023cc0`
- end: `0x180023e6c`
- name: `?GetPropertyValue@WalletItemManager@Wallet@@UEAAJW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEAUtagPROPVARIANT@@@Z`
- size: `428`
- prototype: `int __high(enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002214`
- `0x18000d944`
- `0x180016e78`
- `0x1800172b0`
- `0x1800210d4`
- `0x1800212dc`
- `0x180023cc0`
- `0x180024804`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023e55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023e55`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180023df5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180023df5`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180023d7c`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180023de5`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180023d7c`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180023de5`

## pseudocode

```c
__int64 __fastcall Wallet::WalletItemManager::GetPropertyValue(__int64 a1, unsigned int a2, PROPVARIANT *a3)
{
  unsigned int (__fastcall ***v3)(_QWORD); // rsi
  bool v7; // zf
  unsigned int v8; // edi
  Wallet::WalletStorageAttach *v9; // rax
  __int64 v10; // rax
  HRESULT v11; // eax
  __int64 v12; // rcx
  HRESULT v13; // eax
  int v14; // ebx
  _BYTE v16[16]; // [rsp+30h] [rbp-30h] BYREF
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v18; // [rsp+50h] [rbp-10h]
  Wallet::WalletStorageAttach *v19; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v20; // [rsp+A8h] [rbp+48h] BYREF
  Wallet::WalletStorageAttach *v21; // [rsp+B8h] [rbp+58h] BYREF

  v20 = a2;
  v3 = (unsigned int (__fastcall ***)(_QWORD))(a1 + 104);
  OrderedLockBase<enum WalletLockOrder>::lock(a1 + 104);
  v7 = *(_DWORD *)(a1 + 48) == 0;
  v19 = 0;
  if ( v7 )
  {
    v8 = -2143682555;
    goto LABEL_18;
  }
  v9 = (Wallet::WalletStorageAttach *)operator new(0x10u);
  if ( v9 )
    v9 = Wallet::WalletStorageAttach::WalletStorageAttach(v9, *(struct Wallet::IWalletStorage **)(a1 + 56));
  v21 = v9;
  std::unique_ptr<Wallet::WalletStorageAttach>::operator=((__int64 *)&v19, (__int64 *)&v21);
  std::unique_ptr<Wallet::WalletStorageAttach>::_Delete(&v21);
  if ( !v19 )
  {
    v8 = -2147024882;
    goto LABEL_18;
  }
  v10 = utl::_HashTable<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::find<void>(
          a1 + 64,
          &v21,
          &v20);
  if ( !a3 )
  {
    v8 = -2147467261;
    goto LABEL_18;
  }
  v8 = 0;
  if ( *(_QWORD *)v10 != a1 + 64 )
  {
    v11 = PropVariantCopy(a3, (const PROPVARIANT *)(*(_QWORD *)v10 + 32LL));
    if ( v11 >= 0 )
      goto LABEL_18;
    goto LABEL_11;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, PROPVARIANT *))(**(_QWORD **)(a1 + 56) + 88LL))(
          *(_QWORD *)(a1 + 56),
          0xFFFFFFFFFLL,
          a2,
          a3);
  if ( v11 < 0 )
  {
LABEL_11:
    v8 = v11;
    goto LABEL_18;
  }
  v18 = 0;
  *(_OWORD *)pvar = 0;
  v12 = *(_QWORD *)utl::_HashTable<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::emplace<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 &,ce::WrappedPropVariant &,0>(
                     a1 + 64,
                     v16,
                     &v20,
                     pvar);
  if ( v12 )
  {
    v13 = PropVariantCopy((PROPVARIANT *)(v12 + 32), a3);
    if ( v13 < 0 )
      v8 = v13;
  }
  else
  {
    v8 = -2147024882;
  }
  PropVariantClear(pvar);
LABEL_18:
  std::unique_ptr<Wallet::WalletStorageAttach>::_Delete(&v19);
  v14 = ((__int64 (__fastcall *)(void ***))g_LockOrderManagerImp[1])(&g_LockOrderManagerImp);
  if ( (**v3)(v3) != v14 )
    __int2c();
  ((void (__fastcall *)(void ***))g_LockOrderManagerImp[2])(&g_LockOrderManagerImp);
  LeaveCriticalSection((LPCRITICAL_SECTION)((unsigned __int64)(v3 + 1) & -(__int64)(v3 != 0)));
  return v8;
}

```

## disassembly

```asm
0x180023cc0  mov     [rsp-38h+arg_8], edx
0x180023cc4  push    rbp
0x180023cc5  push    rbx
0x180023cc6  push    rsi
0x180023cc7  push    rdi
0x180023cc8  push    r12
0x180023cca  push    r14
0x180023ccc  push    r15
0x180023cce  mov     rbp, rsp
0x180023cd1  sub     rsp, 60h
0x180023cd5  lea     rsi, [rcx+68h]
0x180023cd9  mov     rbx, rcx
0x180023cdc  mov     rcx, rsi
0x180023cdf  mov     r14, r8
0x180023ce2  mov     r12d, edx
0x180023ce5  call    ?lock@?$OrderedLockBase@W4WalletLockOrder@@@@QEAAXXZ; OrderedLockBase<WalletLockOrder>::lock(void)
0x180023cea  cmp     dword ptr [rbx+30h], 0
0x180023cee  mov     [rbp+arg_0], 0
0x180023cf6  jnz     short loc_180023D02
0x180023cf8  mov     edi, 803A0005h
0x180023cfd  jmp     loc_180023DFB
0x180023d02  mov     ecx, 10h; Size
0x180023d07  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023d0c  test    rax, rax
0x180023d0f  jz      short loc_180023D1D
0x180023d11  mov     rdx, [rbx+38h]; struct Wallet::IWalletStorage *
0x180023d15  mov     rcx, rax; this
0x180023d18  call    ??0WalletStorageAttach@Wallet@@QEAA@PEAUIWalletStorage@1@@Z; Wallet::WalletStorageAttach::WalletStorageAttach(Wallet::IWalletStorage *)
0x180023d1d  lea     rdx, [rbp+arg_18]
0x180023d21  mov     [rbp+arg_18], rax
0x180023d25  lea     rcx, [rbp+arg_0]
0x180023d29  call    ??4?$unique_ptr@VWalletStorageAttach@Wallet@@U?$default_delete@VWalletStorageAttach@Wallet@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Wallet::WalletStorageAttach>::operator=(std::unique_ptr<Wallet::WalletStorageAttach> &&)
0x180023d2e  lea     rcx, [rbp+arg_18]
0x180023d32  call    ?_Delete@?$unique_ptr@VWalletStorageAttach@Wallet@@U?$default_delete@VWalletStorageAttach@Wallet@@@std@@@std@@AEAAXXZ; std::unique_ptr<Wallet::WalletStorageAttach>::_Delete(void)
0x180023d37  cmp     [rbp+arg_0], 0
0x180023d3c  jnz     short loc_180023D48
0x180023d3e  mov     edi, 8007000Eh
0x180023d43  jmp     loc_180023DFB
0x180023d48  lea     r15, [rbx+40h]
0x180023d4c  mov     rcx, r15
0x180023d4f  lea     r8, [rbp+arg_8]
0x180023d53  lea     rdx, [rbp+arg_18]
0x180023d57  call    ??$find@X@?$_HashTable@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@3@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@utl@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@2@@1@AEBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Z; utl::_HashTable<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::find<void>(__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const &)
0x180023d5c  test    r14, r14
0x180023d5f  jnz     short loc_180023D6B
0x180023d61  mov     edi, 80004003h
0x180023d66  jmp     loc_180023DFB
0x180023d6b  mov     rdx, [rax]
0x180023d6e  xor     edi, edi
0x180023d70  cmp     rdx, r15
0x180023d73  jz      short loc_180023D8A
0x180023d75  add     rdx, 20h ; ' '; pvarSrc
0x180023d79  mov     rcx, r14; pvarDest
0x180023d7c  call    cs:__imp_PropVariantCopy
0x180023d82  test    eax, eax
0x180023d84  jns     short loc_180023DFB
0x180023d86  mov     edi, eax
0x180023d88  jmp     short loc_180023DFB
0x180023d8a  mov     rcx, [rbx+38h]
0x180023d8e  mov     r9, r14
0x180023d91  mov     r8d, r12d
0x180023d94  mov     rdx, 0FFFFFFFFFh
0x180023d9e  mov     rax, [rcx]
0x180023da1  mov     rax, [rax+58h]
0x180023da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023daa  test    eax, eax
0x180023dac  js      short loc_180023D86
0x180023dae  xorps   xmm0, xmm0
0x180023db1  lea     r9, [rbp+pvar]
0x180023db5  xor     eax, eax
0x180023db7  lea     r8, [rbp+arg_8]
0x180023dbb  lea     rdx, [rbp+var_30]
0x180023dbf  mov     [rbp+var_10], rax
0x180023dc3  mov     rcx, r15
0x180023dc6  movups  xmmword ptr [rbp+pvar], xmm0
0x180023dca  call    ??$emplace@AEAW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@AEAVWrappedPropVariant@ce@@$0A@@?$_HashTable@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@3@$0A@@utl@@QEAA?AU?$pair@V?$_DlistIt@U?$_HashNode@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@utl@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@2@@utl@@_N@1@AEAW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@AEAVWrappedPropVariant@ce@@@Z; utl::_HashTable<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::emplace<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 &,ce::WrappedPropVariant &,0>(__MIDL___MIDL_itf_wallettypes_0000_0000_0010 &,ce::WrappedPropVariant &)
0x180023dcf  mov     rcx, [rax]
0x180023dd2  test    rcx, rcx
0x180023dd5  jnz     short loc_180023DDE
0x180023dd7  mov     edi, 8007000Eh
0x180023ddc  jmp     short loc_180023DF1
0x180023dde  add     rcx, 20h ; ' '; pvarDest
0x180023de2  mov     rdx, r14; pvarSrc
0x180023de5  call    cs:__imp_PropVariantCopy
0x180023deb  test    eax, eax
0x180023ded  jns     short loc_180023DF1
0x180023def  mov     edi, eax
0x180023df1  lea     rcx, [rbp+pvar]; pvar
0x180023df5  call    cs:__imp_PropVariantClear
0x180023dfb  lea     rcx, [rbp+arg_0]
0x180023dff  call    ?_Delete@?$unique_ptr@VWalletStorageAttach@Wallet@@U?$default_delete@VWalletStorageAttach@Wallet@@@std@@@std@@AEAAXXZ; std::unique_ptr<Wallet::WalletStorageAttach>::_Delete(void)
0x180023e04  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180023e0b  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180023e12  mov     rax, [rax+8]
0x180023e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e1b  mov     ebx, eax
0x180023e1d  mov     rcx, rsi
0x180023e20  mov     rax, [rsi]
0x180023e23  mov     rax, [rax]
0x180023e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e2b  cmp     eax, ebx
0x180023e2d  jz      short loc_180023E31
0x180023e2f  int     2Ch; Windows NT - assertion failure
0x180023e31  mov     rdx, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180023e38  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180023e3f  mov     rax, [rdx+10h]
0x180023e43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e48  lea     rdx, [rsi+8]
0x180023e4c  neg     rsi
0x180023e4f  sbb     rcx, rcx
0x180023e52  and     rcx, rdx; lpCriticalSection
0x180023e55  call    cs:__imp_LeaveCriticalSection
0x180023e5b  mov     eax, edi
0x180023e5d  add     rsp, 60h
0x180023e61  pop     r15
0x180023e63  pop     r14
0x180023e65  pop     r12
0x180023e67  pop     rdi
0x180023e68  pop     rsi
0x180023e69  pop     rbx
0x180023e6a  pop     rbp
0x180023e6b  retn
```
