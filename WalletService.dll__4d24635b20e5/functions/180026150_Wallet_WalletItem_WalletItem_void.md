# Wallet::WalletItem::~WalletItem(void)

- ea: `0x180026150`
- end: `0x18002623a`
- name: `??1WalletItem@Wallet@@UEAA@XZ`
- size: `234`
- prototype: `void __fastcall(Wallet::WalletItem *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026240`

## callees

- `0x180003ae4`
- `0x180006034`
- `0x180012fbc`
- `0x180014414`
- `0x1800247c8`
- `0x180025ad4`
- `0x180026150`
- `0x180028f0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800261c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800261c0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800261b6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800261b6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800261cb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800261cb`

## pseudocode

```c
void __fastcall Wallet::WalletItem::~WalletItem(Wallet::WalletItem *this)
{
  char *v2; // rsi
  __int64 v3; // rbx
  int v4; // r8d
  LPCWSTR lpFileName[2]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v6; // [rsp+30h] [rbp-18h]

  *(_QWORD *)this = &Wallet::WalletItem::`vftable'{for `IWalletItem'};
  v2 = (char *)this + 88;
  v3 = 0;
  *((_QWORD *)this + 1) = &Wallet::WalletItem::`vftable'{for `IFastRundown'};
  do
  {
    v4 = *((_DWORD *)&Wallet::WalletItem::sc_rgImagePropertyTypes + v3);
    *(_OWORD *)lpFileName = 0;
    v6 = 0;
    if ( (int)Wallet::WalletItem::TGetPropertyValue<utl::unordered_map<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>>,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>(
                (__int64)this,
                (__int64)v2,
                v4,
                (PROPVARIANT *)lpFileName) >= 0
      && LOWORD(lpFileName[0])
      && !DeleteFileW(lpFileName[1]) )
    {
      GetLastError();
    }
    PropVariantClear((PROPVARIANT *)lpFileName);
    ++v3;
  }
  while ( v3 != 9 );
  DecrementServerReferenceCount();
  utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,ce::WrappedPropVariant>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,ce::WrappedPropVariant>>,0>::_ClearList((char *)this + 128);
  utl::_HashTable<unsigned long,utl::pair<unsigned long const,LockOrderManagerImp<enum WalletLockOrder>::LockOrderThreadData>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,LockOrderManagerImp<enum WalletLockOrder>::LockOrderThreadData>>,0>::_FreeBuckets((char *)this + 128);
  utl::_HashTable<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::_ClearList(v2);
  utl::_HashTable<unsigned long,utl::pair<unsigned long const,LockOrderManagerImp<enum WalletLockOrder>::LockOrderThreadData>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,LockOrderManagerImp<enum WalletLockOrder>::LockOrderThreadData>>,0>::_FreeBuckets(v2);
  *((_QWORD *)this + 4) = &OrderedLock<enum WalletLockOrder,0>::`vftable';
  OrderedLockBase<enum WalletLockOrder>::~OrderedLockBase<enum WalletLockOrder>((_QWORD *)this + 4);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)this + 3);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)this + 2);
}

```

## disassembly

```asm
0x180026150  mov     [rsp+arg_0], rbx
0x180026155  mov     [rsp+arg_8], rsi
0x18002615a  push    rdi
0x18002615b  sub     rsp, 40h
0x18002615f  lea     rax, ??_7WalletItem@Wallet@@6BIWalletItem@@@; const Wallet::WalletItem::`vftable'{for `IWalletItem'}
0x180026166  mov     rdi, rcx
0x180026169  mov     [rcx], rax
0x18002616c  lea     rsi, [rcx+58h]
0x180026170  lea     rax, ??_7WalletItem@Wallet@@6BIFastRundown@@@; const Wallet::WalletItem::`vftable'{for `IFastRundown'}
0x180026177  xor     ebx, ebx
0x180026179  mov     [rcx+8], rax
0x18002617d  lea     r8, ?sc_rgImagePropertyTypes@WalletItem@Wallet@@2QBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@B; __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const near * const Wallet::WalletItem::sc_rgImagePropertyTypes
0x180026184  xorps   xmm0, xmm0
0x180026187  mov     r8d, [r8+rbx*4]
0x18002618b  lea     r9, [rsp+48h+lpFileName]
0x180026190  xor     eax, eax
0x180026192  mov     rdx, rsi
0x180026195  movups  xmmword ptr [rsp+48h+lpFileName], xmm0
0x18002619a  mov     [rsp+48h+var_18], rax
0x18002619f  call    ??$TGetPropertyValue@V?$unordered_map@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@utl@@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@5@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@5@@utl@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@WalletItem@Wallet@@QEBAJAEBV?$unordered_map@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@utl@@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@5@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@5@@utl@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEAUtagPROPVARIANT@@@Z; Wallet::WalletItem::TGetPropertyValue<utl::unordered_map<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>>,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(utl::unordered_map<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>> const &,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,tagPROPVARIANT *)
0x1800261a4  test    eax, eax
0x1800261a6  js      short loc_1800261C6
0x1800261a8  xor     eax, eax
0x1800261aa  cmp     ax, word ptr [rsp+48h+lpFileName]
0x1800261af  jz      short loc_1800261C6
0x1800261b1  mov     rcx, [rsp+48h+lpFileName+8]; lpFileName
0x1800261b6  call    cs:__imp_DeleteFileW
0x1800261bc  test    eax, eax
0x1800261be  jnz     short loc_1800261C6
0x1800261c0  call    cs:__imp_GetLastError
0x1800261c6  lea     rcx, [rsp+48h+lpFileName]; pvar
0x1800261cb  call    cs:__imp_PropVariantClear
0x1800261d1  inc     rbx
0x1800261d4  cmp     rbx, 9
0x1800261d8  jnz     short loc_18002617D
0x1800261da  call    ?DecrementServerReferenceCount@@YAJXZ; DecrementServerReferenceCount(void)
0x1800261df  lea     rbx, [rdi+80h]
0x1800261e6  mov     rcx, rbx
0x1800261e9  call    ?_ClearList@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@VWrappedPropVariant@ce@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@VWrappedPropVariant@ce@@@utl@@@2@$0A@@utl@@AEAAXXZ; utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ce::WrappedPropVariant>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ce::WrappedPropVariant>>,0>::_ClearList(void)
0x1800261ee  mov     rcx, rbx
0x1800261f1  call    ?_FreeBuckets@?$_HashTable@KU?$pair@$$CBKULockOrderThreadData@?$LockOrderManagerImp@W4WalletLockOrder@@@@@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKULockOrderThreadData@?$LockOrderManagerImp@W4WalletLockOrder@@@@@utl@@@2@$0A@@utl@@AEAAXXZ; utl::_HashTable<ulong,utl::pair<ulong const,LockOrderManagerImp<WalletLockOrder>::LockOrderThreadData>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,LockOrderManagerImp<WalletLockOrder>::LockOrderThreadData>>,0>::_FreeBuckets(void)
0x1800261f6  mov     rcx, rsi
0x1800261f9  call    ?_ClearList@?$_HashTable@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::_ClearList(void)
0x1800261fe  mov     rcx, rsi
0x180026201  call    ?_FreeBuckets@?$_HashTable@KU?$pair@$$CBKULockOrderThreadData@?$LockOrderManagerImp@W4WalletLockOrder@@@@@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKULockOrderThreadData@?$LockOrderManagerImp@W4WalletLockOrder@@@@@utl@@@2@$0A@@utl@@AEAAXXZ; utl::_HashTable<ulong,utl::pair<ulong const,LockOrderManagerImp<WalletLockOrder>::LockOrderThreadData>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,LockOrderManagerImp<WalletLockOrder>::LockOrderThreadData>>,0>::_FreeBuckets(void)
0x180026206  lea     rcx, [rdi+20h]
0x18002620a  lea     rax, ??_7?$OrderedLock@W4WalletLockOrder@@$0A@@@6B@; const OrderedLock<WalletLockOrder,0>::`vftable'
0x180026211  mov     [rcx], rax
0x180026214  call    ??1?$OrderedLockBase@W4WalletLockOrder@@@@UEAA@XZ; OrderedLockBase<WalletLockOrder>::~OrderedLockBase<WalletLockOrder>(void)
0x180026219  lea     rcx, [rdi+18h]
0x18002621d  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180026222  lea     rcx, [rdi+10h]
0x180026226  mov     rbx, [rsp+48h+arg_0]
0x18002622b  mov     rsi, [rsp+48h+arg_8]
0x180026230  add     rsp, 40h
0x180026234  pop     rdi
0x180026235  jmp     ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
```
