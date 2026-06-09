# Wallet::WalletWebService::RequestCompletedCallback(ATL::CComPtr<Wallet::IWalletWebServiceRequest> const &,long,ulong)

- ea: `0x1800349f0`
- end: `0x180034c3f`
- name: `?RequestCompletedCallback@WalletWebService@Wallet@@UEAAXAEBV?$CComPtr@UIWalletWebServiceRequest@Wallet@@@ATL@@JK@Z`
- size: `591`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003ae4`
- `0x180003b40`
- `0x1800043b8`
- `0x1800048e8`
- `0x180016e78`
- `0x18001e480`
- `0x180033fc4`
- `0x1800349f0`
- `0x180034c48`
- `0x180039058`
- `0x180039088`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034c14`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034c14`

## pseudocode

```c
__int64 __fastcall Wallet::WalletWebService::RequestCompletedCallback(__int64 a1, _QWORD *a2, int a3, unsigned int a4)
{
  unsigned int (__fastcall ***v4)(_QWORD); // r14
  unsigned int v9; // r15d
  __int64 v10; // rax
  Wallet::Utils **v11; // rax
  struct IWalletItem *v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rdi
  int (__fastcall *v25)(__int64, __int64, __int64 *); // rbx
  __int64 *v26; // rax
  struct IWalletItemList *v27; // rdx
  int v28; // ebx
  _QWORD v30[7]; // [rsp+20h] [rbp-38h] BYREF
  Wallet::Utils *v31; // [rsp+60h] [rbp+8h] BYREF
  unsigned __int64 WalletItemId; // [rsp+68h] [rbp+10h] BYREF

  v4 = (unsigned int (__fastcall ***)(_QWORD))(a1 + 64);
  v31 = 0;
  OrderedLockBase<enum WalletLockOrder>::lock(a1 + 64);
  v9 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 48LL))(*a2);
  if ( !*(_DWORD *)(a1 + 112)
    || a3 >= 0
    && (v10 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 40LL))(*a2),
        (int)Wallet::WalletWebService::SaveResultToDatabase(a1, a4, v9, v10) < 0)
    || (v11 = (Wallet::Utils **)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 40LL))(*a2),
        WalletItemId = Wallet::Utils::GetWalletItemId(*v11, v12),
        v13 = *utl::_HashTable<unsigned __int64,utl::pair<unsigned __int64 const,ATL::CComPtr<Wallet::IWalletWebServiceRequest>>,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,ATL::CComPtr<Wallet::IWalletWebServiceRequest>>>,0>::_FindFirst<utl::_HashTable<unsigned __int64,utl::pair<unsigned __int64 const,ATL::CComPtr<Wallet::IWalletWebServiceRequest>>,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,ATL::CComPtr<Wallet::IWalletWebServiceRequest>>>,0>::_FindFirstFind,unsigned __int64>(
                 a1 + 176,
                 v30,
                 (__int64 *)&WalletItemId),
        a1 + 176 == v13) )
  {
LABEL_19:
    v31 = *(Wallet::Utils **)(a1 + 168);
    *(_QWORD *)(a1 + 168) = 0;
    goto LABEL_20;
  }
  v14 = *(_QWORD *)v13;
  v15 = *(_QWORD **)(v13 + 8);
  v16 = (8LL << *(_BYTE *)(a1 + 208)) - 1;
  *v15 = *(_QWORD *)v13;
  *(_QWORD *)(v14 + 8) = v15;
  v17 = v16 & *(_QWORD *)(v13 + 16);
  v18 = *(_QWORD *)(a1 + 192);
  v19 = 2 * v17;
  if ( *(_QWORD *)(v18 + 8 * v19) == v13 )
  {
    if ( *(_QWORD *)(v18 + 8 * v19 + 8) == v13 )
    {
      *(_QWORD *)(v18 + 8 * v19 + 8) = 0;
      v20 = 0;
    }
    else
    {
      v20 = *(_QWORD *)v13;
    }
    *(_QWORD *)(v18 + 8 * v19) = v20;
  }
  else if ( *(_QWORD *)(v18 + 8 * v19 + 8) == v13 )
  {
    *(_QWORD *)(v18 + 8 * v19 + 8) = *(_QWORD *)(v13 + 8);
  }
  --*(_QWORD *)(a1 + 200);
  utl::_ContainerBase<utl::pair<unsigned __int64 const,ATL::CComPtr<Wallet::IWalletWebServiceRequest>>,utl::allocator<utl::pair<unsigned __int64 const,ATL::CComPtr<Wallet::IWalletWebServiceRequest>>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned __int64 const,ATL::CComPtr<Wallet::IWalletWebServiceRequest>>>>(
    v19,
    (char *)v13,
    v13);
  if ( !*(_QWORD *)(a1 + 200) )
  {
    v21 = *(_QWORD *)(a1 + 136);
    v22 = *(_QWORD *)(v21 + 112);
    if ( v22 )
    {
      (*(void (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v22 + 24LL))(v22, 0, 0);
      if ( *(_QWORD *)(v21 + 112) )
        ATL::AtlComPtrAssign((struct IUnknown **)(v21 + 112), 0);
    }
    v23 = *(_QWORD *)(a1 + 136);
    v31 = 0;
    v24 = *(_QWORD *)(v23 + 24);
    v25 = *(int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v24 + 72LL);
    v26 = ce::pointerTo<IWalletNotification>((__int64 *)&v31);
    if ( v25(v24, 57, v26) >= 0 )
      Wallet::Utils::GetWalletItemListCount(v31, v27);
    ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&v31);
    goto LABEL_19;
  }
LABEL_20:
  v28 = ((__int64 (__fastcall *)(void ***))g_LockOrderManagerImp[1])(&g_LockOrderManagerImp);
  if ( (**v4)(v4) != v28 )
    __int2c();
  ((void (__fastcall *)(void ***))g_LockOrderManagerImp[2])(&g_LockOrderManagerImp);
  LeaveCriticalSection((LPCRITICAL_SECTION)((unsigned __int64)(v4 + 1) & -(__int64)(v4 != 0)));
  ATL::CComPtrBase<IWallet>::Release(&v31);
  return ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&v31);
}

```

## disassembly

```asm
0x1800349f0  mov     [rsp+arg_10], rbx
0x1800349f5  push    rbp
0x1800349f6  push    rsi
0x1800349f7  push    rdi
0x1800349f8  push    r14
0x1800349fa  push    r15
0x1800349fc  sub     rsp, 30h
0x180034a00  lea     r14, [rcx+40h]
0x180034a04  mov     [rsp+58h+arg_0], 0
0x180034a0d  mov     rsi, rcx
0x180034a10  mov     ebp, r9d
0x180034a13  mov     rcx, r14
0x180034a16  mov     ebx, r8d
0x180034a19  mov     rdi, rdx
0x180034a1c  call    ?lock@?$OrderedLockBase@W4WalletLockOrder@@@@QEAAXXZ; OrderedLockBase<WalletLockOrder>::lock(void)
0x180034a21  mov     rcx, [rdi]
0x180034a24  mov     rax, [rcx]
0x180034a27  mov     rax, [rax+30h]
0x180034a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034a30  cmp     dword ptr [rsi+70h], 0
0x180034a34  mov     r15d, eax
0x180034a37  jz      loc_180034BAC
0x180034a3d  test    ebx, ebx
0x180034a3f  js      short loc_180034A68
0x180034a41  mov     rcx, [rdi]
0x180034a44  mov     rdx, [rcx]
0x180034a47  mov     rax, [rdx+28h]
0x180034a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034a50  mov     r9, rax
0x180034a53  mov     r8d, r15d
0x180034a56  mov     edx, ebp
0x180034a58  mov     rcx, rsi
0x180034a5b  call    ?SaveResultToDatabase@WalletWebService@Wallet@@AEAAJKW4__MIDL___MIDL_itf_wallettypes_0000_0000_0009@@AEAV?$CComPtr@UIWalletItem@@@ATL@@@Z; Wallet::WalletWebService::SaveResultToDatabase(ulong,__MIDL___MIDL_itf_wallettypes_0000_0000_0009,ATL::CComPtr<IWalletItem> &)
0x180034a60  test    eax, eax
0x180034a62  js      loc_180034BAC
0x180034a68  mov     rcx, [rdi]
0x180034a6b  mov     rax, [rcx]
0x180034a6e  mov     rax, [rax+28h]
0x180034a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034a77  mov     rcx, [rax]; this
0x180034a7a  call    ?GetWalletItemId@Utils@Wallet@@YA_KPEAUIWalletItem@@@Z; Wallet::Utils::GetWalletItemId(IWalletItem *)
0x180034a7f  lea     rbx, [rsi+0B0h]
0x180034a86  mov     [rsp+58h+arg_8], rax
0x180034a8b  mov     rcx, rbx
0x180034a8e  lea     r8, [rsp+58h+arg_8]
0x180034a93  lea     rdx, [rsp+58h+var_38]
0x180034a98  call    ??$_FindFirst@U_FindFirstFind@?$_HashTable@_KU?$pair@$$CB_KV?$CComPtr@UIWalletWebServiceRequest@Wallet@@@ATL@@@utl@@U?$hash@_K@2@U?$equal_to@_K@2@V?$allocator@U?$pair@$$CB_KV?$CComPtr@UIWalletWebServiceRequest@Wallet@@@ATL@@@utl@@@2@$0A@@utl@@_K@?$_HashTable@_KU?$pair@$$CB_KV?$CComPtr@UIWalletWebServiceRequest@Wallet@@@ATL@@@utl@@U?$hash@_K@2@U?$equal_to@_K@2@V?$allocator@U?$pair@$$CB_KV?$CComPtr@UIWalletWebServiceRequest@Wallet@@@ATL@@@utl@@@2@$0A@@utl@@AEBA?AU_FindFirstFind@01@AEB_K@Z; utl::_HashTable<unsigned __int64,utl::pair<unsigned __int64 const,ATL::CComPtr<Wallet::IWalletWebServiceRequest>>,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,ATL::CComPtr<Wallet::IWalletWebServiceRequest>>>,0>::_FindFirst<utl::_HashTable<unsigned __int64,utl::pair<unsigned __int64 const,ATL::CComPtr<Wallet::IWalletWebServiceRequest>>,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,ATL::CComPtr<Wallet::IWalletWebServiceRequest>>>,0>::_FindFirstFind,unsigned __int64>(unsigned __int64 const &)
0x180034a9d  mov     r8, [rax]
0x180034aa0  cmp     rbx, r8
0x180034aa3  jz      loc_180034BAC
0x180034aa9  mov     cl, [rsi+0D0h]
0x180034aaf  mov     edx, 8
0x180034ab4  mov     rax, [r8]
0x180034ab7  shl     rdx, cl
0x180034aba  mov     rcx, [r8+8]
0x180034abe  dec     rdx
0x180034ac1  mov     [rcx], rax
0x180034ac4  mov     [rax+8], rcx
0x180034ac8  mov     rcx, [r8+10h]
0x180034acc  and     rcx, rdx
0x180034acf  mov     rdx, [rsi+0C0h]
0x180034ad6  add     rcx, rcx
0x180034ad9  cmp     [rdx+rcx*8], r8
0x180034add  jnz     short loc_180034AFC
0x180034adf  cmp     [rdx+rcx*8+8], r8
0x180034ae4  jnz     short loc_180034AF3
0x180034ae6  mov     qword ptr [rdx+rcx*8+8], 0
0x180034aef  xor     eax, eax
0x180034af1  jmp     short loc_180034AF6
0x180034af3  mov     rax, [r8]
0x180034af6  mov     [rdx+rcx*8], rax
0x180034afa  jmp     short loc_180034B0C
0x180034afc  cmp     [rdx+rcx*8+8], r8
0x180034b01  jnz     short loc_180034B0C
0x180034b03  mov     rax, [r8+8]
0x180034b07  mov     [rdx+rcx*8+8], rax
0x180034b0c  dec     qword ptr [rsi+0C8h]
0x180034b13  mov     rdx, r8
0x180034b16  call    ??$_DeleteNode@U?$_HashNode@U?$pair@$$CB_KV?$CComPtr@UIWalletWebServiceRequest@Wallet@@@ATL@@@utl@@@utl@@@?$_ContainerBase@U?$pair@$$CB_KV?$CComPtr@UIWalletWebServiceRequest@Wallet@@@ATL@@@utl@@V?$allocator@U?$pair@$$CB_KV?$CComPtr@UIWalletWebServiceRequest@Wallet@@@ATL@@@utl@@@2@@utl@@IEAAXPEAU?$_HashNode@U?$pair@$$CB_KV?$CComPtr@UIWalletWebServiceRequest@Wallet@@@ATL@@@utl@@@1@@Z; utl::_ContainerBase<utl::pair<unsigned __int64 const,ATL::CComPtr<Wallet::IWalletWebServiceRequest>>,utl::allocator<utl::pair<unsigned __int64 const,ATL::CComPtr<Wallet::IWalletWebServiceRequest>>>>::_DeleteNode<utl::_HashNode<utl::pair<unsigned __int64 const,ATL::CComPtr<Wallet::IWalletWebServiceRequest>>>>(utl::_HashNode<utl::pair<unsigned __int64 const,ATL::CComPtr<Wallet::IWalletWebServiceRequest>>> *)
0x180034b1b  cmp     qword ptr [rsi+0C8h], 0
0x180034b23  jnz     loc_180034BC3
0x180034b29  mov     rbx, [rsi+88h]
0x180034b30  mov     rcx, [rbx+70h]
0x180034b34  test    rcx, rcx
0x180034b37  jz      short loc_180034B5C
0x180034b39  mov     rax, [rcx]
0x180034b3c  xor     r8d, r8d
0x180034b3f  xor     edx, edx
0x180034b41  mov     rax, [rax+18h]
0x180034b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b4a  cmp     qword ptr [rbx+70h], 0
0x180034b4f  jz      short loc_180034B5C
0x180034b51  xor     edx, edx; struct IUnknown *
0x180034b53  lea     rcx, [rbx+70h]; struct IUnknown **
0x180034b57  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180034b5c  mov     rax, [rsi+88h]
0x180034b63  lea     rcx, [rsp+58h+arg_0]
0x180034b68  mov     [rsp+58h+arg_0], 0
0x180034b71  mov     rdi, [rax+18h]
0x180034b75  mov     rax, [rdi]
0x180034b78  mov     rbx, [rax+48h]
0x180034b7c  call    ??$pointerTo@UIWalletNotification@@@ce@@YAPEAPEAUIWalletNotification@@AEAV?$CComPtr@UIWalletNotification@@@ATL@@@Z; ce::pointerTo<IWalletNotification>(ATL::CComPtr<IWalletNotification> &)
0x180034b81  mov     r8, rax
0x180034b84  mov     edx, 39h ; '9'
0x180034b89  mov     rax, rbx
0x180034b8c  mov     rcx, rdi
0x180034b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b94  test    eax, eax
0x180034b96  js      short loc_180034BA2
0x180034b98  mov     rcx, [rsp+58h+arg_0]; this
0x180034b9d  call    ?GetWalletItemListCount@Utils@Wallet@@YAIPEAUIWalletItemList@@@Z; Wallet::Utils::GetWalletItemListCount(IWalletItemList *)
0x180034ba2  lea     rcx, [rsp+58h+arg_0]
0x180034ba7  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180034bac  mov     rax, [rsi+0A8h]
0x180034bb3  mov     [rsp+58h+arg_0], rax
0x180034bb8  mov     qword ptr [rsi+0A8h], 0
0x180034bc3  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180034bca  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180034bd1  mov     rax, [rax+8]
0x180034bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034bda  mov     rcx, [r14]
0x180034bdd  mov     ebx, eax
0x180034bdf  mov     rax, [rcx]
0x180034be2  mov     rcx, r14
0x180034be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034bea  cmp     eax, ebx
0x180034bec  jz      short loc_180034BF0
0x180034bee  int     2Ch; Windows NT - assertion failure
0x180034bf0  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180034bf7  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180034bfe  mov     rax, [rax+10h]
0x180034c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c07  lea     rax, [r14+8]
0x180034c0b  neg     r14
0x180034c0e  sbb     rcx, rcx
0x180034c11  and     rcx, rax; lpCriticalSection
0x180034c14  call    cs:__imp_LeaveCriticalSection
0x180034c1a  lea     rcx, [rsp+58h+arg_0]
0x180034c1f  call    ?Release@?$CComPtrBase@UIWallet@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IWallet>::Release(void)
0x180034c24  lea     rcx, [rsp+58h+arg_0]
0x180034c29  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180034c2e  mov     rbx, [rsp+58h+arg_10]
0x180034c33  add     rsp, 30h
0x180034c37  pop     r15
0x180034c39  pop     r14
0x180034c3b  pop     rdi
0x180034c3c  pop     rsi
0x180034c3d  pop     rbp
0x180034c3e  retn
```
