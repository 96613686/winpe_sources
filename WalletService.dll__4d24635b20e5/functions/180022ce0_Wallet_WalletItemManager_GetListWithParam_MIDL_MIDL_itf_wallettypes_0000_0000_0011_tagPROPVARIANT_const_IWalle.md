# Wallet::WalletItemManager::GetListWithParam(__MIDL___MIDL_itf_wallettypes_0000_0000_0011,tagPROPVARIANT const *,IWalletItemList * *)

- ea: `0x180022ce0`
- end: `0x180022e73`
- name: `?GetListWithParam@WalletItemManager@Wallet@@UEAAJW4__MIDL___MIDL_itf_wallettypes_0000_0000_0011@@PEBUtagPROPVARIANT@@PEAPEAUIWalletItemList@@@Z`
- size: `403`
- prototype: `int __high(enum __MIDL___MIDL_itf_wallettypes_0000_0000_0011, const struct tagPROPVARIANT *, struct IWalletItemList **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002214`
- `0x180003ae4`
- `0x1800043b8`
- `0x18000d944`
- `0x180016e78`
- `0x1800212dc`
- `0x180022ce0`
- `0x180024804`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022e49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022e49`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180022de9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180022de9`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180022d91`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180022d91`

## pseudocode

```c
__int64 __fastcall Wallet::WalletItemManager::GetListWithParam(
        __int64 a1,
        unsigned int a2,
        const PROPVARIANT *a3,
        _QWORD *a4)
{
  unsigned int (__fastcall ***v4)(_QWORD); // rsi
  bool v9; // zf
  HRESULT v10; // edi
  Wallet::WalletStorageAttach *v11; // rax
  __int64 (__fastcall *v12)(__int64, _QWORD, PROPVARIANT *, __int64, __int64 *); // rbx
  __int64 *v13; // rax
  __int64 v14; // rcx
  int v15; // ebx
  __int64 v17; // [rsp+30h] [rbp-30h] BYREF
  Wallet::WalletStorageAttach *v18; // [rsp+38h] [rbp-28h] BYREF
  PROPVARIANT pvarDest[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v20; // [rsp+50h] [rbp-10h]
  Wallet::WalletStorageAttach *v21; // [rsp+90h] [rbp+30h] BYREF

  v4 = (unsigned int (__fastcall ***)(_QWORD))(a1 + 104);
  v20 = 0;
  v17 = 0;
  *(_OWORD *)pvarDest = 0;
  OrderedLockBase<enum WalletLockOrder>::lock(a1 + 104);
  v9 = *(_DWORD *)(a1 + 48) == 0;
  v21 = 0;
  if ( v9 )
  {
    v10 = -2143682555;
  }
  else
  {
    v11 = (Wallet::WalletStorageAttach *)operator new(0x10u);
    if ( v11 )
      v11 = Wallet::WalletStorageAttach::WalletStorageAttach(v11, *(struct Wallet::IWalletStorage **)(a1 + 56));
    v18 = v11;
    std::unique_ptr<Wallet::WalletStorageAttach>::operator=((__int64 *)&v21, (__int64 *)&v18);
    std::unique_ptr<Wallet::WalletStorageAttach>::_Delete(&v18);
    if ( v21 )
    {
      if ( a4 )
      {
        v10 = PropVariantCopy(pvarDest, a3);
        if ( v10 >= 0 )
        {
          v12 = *(__int64 (__fastcall **)(__int64, _QWORD, PROPVARIANT *, __int64, __int64 *))(*(_QWORD *)a1 + 88LL);
          v13 = ce::pointerTo<IWalletNotification>(&v17);
          v10 = v12(a1, a2, pvarDest, 1, v13);
          if ( v10 >= 0 )
          {
            v14 = v17;
            v10 = 0;
            *a4 = v17;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
          }
        }
      }
      else
      {
        v10 = -2147467261;
      }
    }
    else
    {
      v10 = -2147024882;
    }
  }
  PropVariantClear(pvarDest);
  std::unique_ptr<Wallet::WalletStorageAttach>::_Delete(&v21);
  v15 = ((__int64 (__fastcall *)(void ***))g_LockOrderManagerImp[1])(&g_LockOrderManagerImp);
  if ( (**v4)(v4) != v15 )
    __int2c();
  ((void (__fastcall *)(void ***))g_LockOrderManagerImp[2])(&g_LockOrderManagerImp);
  LeaveCriticalSection((LPCRITICAL_SECTION)((unsigned __int64)(v4 + 1) & -(__int64)(v4 != 0)));
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v17);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180022ce0  mov     [rsp-28h+arg_8], rbx
0x180022ce5  mov     [rsp-28h+arg_10], rsi
0x180022cea  push    rbp
0x180022ceb  push    rdi
0x180022cec  push    r12
0x180022cee  push    r14
0x180022cf0  push    r15
0x180022cf2  mov     rbp, rsp
0x180022cf5  sub     rsp, 60h
0x180022cf9  xor     eax, eax
0x180022cfb  lea     rsi, [rcx+68h]
0x180022cff  mov     r14, rcx
0x180022d02  mov     [rbp+var_10], rax
0x180022d06  xorps   xmm0, xmm0
0x180022d09  mov     [rbp+var_30], rax
0x180022d0d  mov     rcx, rsi
0x180022d10  mov     r15, r9
0x180022d13  mov     rbx, r8
0x180022d16  mov     r12d, edx
0x180022d19  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180022d1d  call    ?lock@?$OrderedLockBase@W4WalletLockOrder@@@@QEAAXXZ; OrderedLockBase<WalletLockOrder>::lock(void)
0x180022d22  cmp     dword ptr [r14+30h], 0
0x180022d27  mov     [rbp+arg_0], 0
0x180022d2f  jnz     short loc_180022D3B
0x180022d31  mov     edi, 803A0005h
0x180022d36  jmp     loc_180022DE5
0x180022d3b  mov     ecx, 10h; Size
0x180022d40  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022d45  test    rax, rax
0x180022d48  jz      short loc_180022D56
0x180022d4a  mov     rdx, [r14+38h]; struct Wallet::IWalletStorage *
0x180022d4e  mov     rcx, rax; this
0x180022d51  call    ??0WalletStorageAttach@Wallet@@QEAA@PEAUIWalletStorage@1@@Z; Wallet::WalletStorageAttach::WalletStorageAttach(Wallet::IWalletStorage *)
0x180022d56  lea     rdx, [rbp+var_28]
0x180022d5a  mov     [rbp+var_28], rax
0x180022d5e  lea     rcx, [rbp+arg_0]
0x180022d62  call    ??4?$unique_ptr@VWalletStorageAttach@Wallet@@U?$default_delete@VWalletStorageAttach@Wallet@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Wallet::WalletStorageAttach>::operator=(std::unique_ptr<Wallet::WalletStorageAttach> &&)
0x180022d67  lea     rcx, [rbp+var_28]
0x180022d6b  call    ?_Delete@?$unique_ptr@VWalletStorageAttach@Wallet@@U?$default_delete@VWalletStorageAttach@Wallet@@@std@@@std@@AEAAXXZ; std::unique_ptr<Wallet::WalletStorageAttach>::_Delete(void)
0x180022d70  cmp     [rbp+arg_0], 0
0x180022d75  jnz     short loc_180022D7E
0x180022d77  mov     edi, 8007000Eh
0x180022d7c  jmp     short loc_180022DE5
0x180022d7e  test    r15, r15
0x180022d81  jnz     short loc_180022D8A
0x180022d83  mov     edi, 80004003h
0x180022d88  jmp     short loc_180022DE5
0x180022d8a  mov     rdx, rbx; pvarSrc
0x180022d8d  lea     rcx, [rbp+pvarDest]; pvarDest
0x180022d91  call    cs:__imp_PropVariantCopy
0x180022d97  mov     edi, eax
0x180022d99  test    eax, eax
0x180022d9b  js      short loc_180022DE5
0x180022d9d  mov     rax, [r14]
0x180022da0  lea     rcx, [rbp+var_30]
0x180022da4  mov     rbx, [rax+58h]
0x180022da8  call    ??$pointerTo@UIWalletNotification@@@ce@@YAPEAPEAUIWalletNotification@@AEAV?$CComPtr@UIWalletNotification@@@ATL@@@Z; ce::pointerTo<IWalletNotification>(ATL::CComPtr<IWalletNotification> &)
0x180022dad  mov     [rsp+60h+var_40], rax
0x180022db2  lea     r8, [rbp+pvarDest]
0x180022db6  mov     rax, rbx
0x180022db9  mov     r9d, 1
0x180022dbf  mov     edx, r12d
0x180022dc2  mov     rcx, r14
0x180022dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022dca  mov     edi, eax
0x180022dcc  test    eax, eax
0x180022dce  js      short loc_180022DE5
0x180022dd0  mov     rcx, [rbp+var_30]
0x180022dd4  xor     edi, edi
0x180022dd6  mov     [r15], rcx
0x180022dd9  mov     rax, [rcx]
0x180022ddc  mov     rax, [rax+8]
0x180022de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022de5  lea     rcx, [rbp+pvarDest]; pvar
0x180022de9  call    cs:__imp_PropVariantClear
0x180022def  lea     rcx, [rbp+arg_0]
0x180022df3  call    ?_Delete@?$unique_ptr@VWalletStorageAttach@Wallet@@U?$default_delete@VWalletStorageAttach@Wallet@@@std@@@std@@AEAAXXZ; std::unique_ptr<Wallet::WalletStorageAttach>::_Delete(void)
0x180022df8  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180022dff  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180022e06  mov     rax, [rax+8]
0x180022e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e0f  mov     ebx, eax
0x180022e11  mov     rcx, rsi
0x180022e14  mov     rax, [rsi]
0x180022e17  mov     rax, [rax]
0x180022e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e1f  cmp     eax, ebx
0x180022e21  jz      short loc_180022E25
0x180022e23  int     2Ch; Windows NT - assertion failure
0x180022e25  mov     rdx, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180022e2c  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180022e33  mov     rax, [rdx+10h]
0x180022e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e3c  lea     rdx, [rsi+8]
0x180022e40  neg     rsi
0x180022e43  sbb     rcx, rcx
0x180022e46  and     rcx, rdx; lpCriticalSection
0x180022e49  call    cs:__imp_LeaveCriticalSection
0x180022e4f  lea     rcx, [rbp+var_30]
0x180022e53  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180022e58  lea     r11, [rsp+60h+var_s0]
0x180022e5d  mov     eax, edi
0x180022e5f  mov     rbx, [r11+38h]
0x180022e63  mov     rsi, [r11+40h]
0x180022e67  mov     rsp, r11
0x180022e6a  pop     r15
0x180022e6c  pop     r14
0x180022e6e  pop     r12
0x180022e70  pop     rdi
0x180022e71  pop     rbp
0x180022e72  retn
```
