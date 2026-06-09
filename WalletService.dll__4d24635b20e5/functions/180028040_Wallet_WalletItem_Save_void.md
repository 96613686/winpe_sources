# Wallet::WalletItem::Save(void)

- ea: `0x180028040`
- end: `0x180028379`
- name: `?Save@WalletItem@Wallet@@UEAAJXZ`
- size: `825`
- prototype: `__int64 __fastcall(Wallet::WalletItem *__hidden this)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003ae4`
- `0x18000d8d8`
- `0x18000d910`
- `0x18000d944`
- `0x18000dab0`
- `0x180012fbc`
- `0x1800135e0`
- `0x180013f78`
- `0x180016e78`
- `0x18002403c`
- `0x1800247c8`
- `0x180025ad4`
- `0x180027038`
- `0x180028040`
- `0x180028b2c`
- `0x180028cfc`
- `0x180028e48`
- `0x180028f0c`
- `0x180039058`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002831e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002831e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002826a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002826a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180028260`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180028260`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028274`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180028274`

## pseudocode

```c
__int64 __fastcall Wallet::WalletItem::Save(Wallet::WalletItem *this)
{
  unsigned int (__fastcall ***v2)(_QWORD); // r14
  struct Wallet::IWalletStorage *v3; // r12
  int DoesNotExceedMaximum; // r15d
  int v5; // ebx
  struct IWalletItem *v6; // rdx
  Wallet::Utils *v7; // rcx
  unsigned int v8; // ebx
  unsigned __int64 WalletItemId; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  int v12; // edi
  unsigned int *i; // rbx
  _QWORD *j; // rsi
  __int64 v15; // rcx
  __int64 k; // rsi
  __int64 v17; // r8
  int v18; // ebx
  __int64 v19; // rdx
  LPCWSTR lpFileName[2]; // [rsp+30h] [rbp-59h] BYREF
  __int64 v22; // [rsp+40h] [rbp-49h]
  _BYTE v23[16]; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v24[40]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v25[88]; // [rsp+88h] [rbp-1h] BYREF
  int v26; // [rsp+F0h] [rbp+67h]
  __int64 v27; // [rsp+F8h] [rbp+6Fh] BYREF
  __int64 v28; // [rsp+100h] [rbp+77h] BYREF

  v2 = (unsigned int (__fastcall ***)(_QWORD))(*((_QWORD *)this + 2) + 104LL);
  v27 = *((_QWORD *)this + 10);
  OrderedLockBase<enum WalletLockOrder>::lock(v2);
  Wallet::WalletStorageAttach::WalletStorageAttach(
    (Wallet::WalletStorageAttach *)v23,
    *(struct Wallet::IWalletStorage **)(*((_QWORD *)this + 2) + 56LL));
  utl::unordered_map<unsigned __int64,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>>>::unordered_map<unsigned __int64,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>>>(v24);
  v3 = *(struct Wallet::IWalletStorage **)(*((_QWORD *)this + 2) + 56LL);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v25);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpFileName);
  if ( !*((_QWORD *)this + 3)
    || (DoesNotExceedMaximum = Wallet::WalletItem::SetParentWalletItemId(this), DoesNotExceedMaximum >= 0) )
  {
    DoesNotExceedMaximum = 0;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpFileName);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v25);
  if ( DoesNotExceedMaximum < 0 )
  {
    v12 = 0;
    goto LABEL_44;
  }
  if ( v27 )
  {
    v5 = 0;
    v26 = 0;
    Wallet::WalletItem::GetPreviousImagePaths(this, v24);
  }
  else
  {
    v5 = 1;
    v26 = 1;
  }
  DoesNotExceedMaximum = (*(__int64 (__fastcall **)(struct Wallet::IWalletStorage *))(*(_QWORD *)v3 + 40LL))(v3);
  if ( DoesNotExceedMaximum < 0 )
    goto LABEL_13;
  if ( v5 )
  {
    v7 = (Wallet::Utils *)*((_QWORD *)this + 3);
    v28 = 0;
    if ( !v7
      || (v8 = *((_DWORD *)this + 42),
          WalletItemId = Wallet::Utils::GetWalletItemId(v7, v6),
          DoesNotExceedMaximum = Wallet::WalletItem::VerifyChildItemsDoNotExceedMax(WalletItemId, v8),
          DoesNotExceedMaximum >= 0) )
    {
      DoesNotExceedMaximum = (*(__int64 (__fastcall **)(struct Wallet::IWalletStorage *, _QWORD, __int64 *))(*(_QWORD *)v3 + 64LL))(
                               v3,
                               *((unsigned int *)this + 42),
                               &v27);
      if ( DoesNotExceedMaximum >= 0 )
      {
        ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v28, v10, v11);
        goto LABEL_16;
      }
    }
    ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v28, v10, v11);
LABEL_13:
    v12 = v26;
LABEL_44:
    (*(void (__fastcall **)(struct Wallet::IWalletStorage *))(*(_QWORD *)v3 + 56LL))(v3);
    goto LABEL_36;
  }
LABEL_16:
  for ( i = (unsigned int *)*((_QWORD *)this + 11); i != (unsigned int *)((char *)this + 88); i = *(unsigned int **)i )
  {
    DoesNotExceedMaximum = (*(__int64 (__fastcall **)(struct Wallet::IWalletStorage *, __int64, _QWORD, unsigned int *))(*(_QWORD *)v3 + 80LL))(
                             v3,
                             v27,
                             i[6],
                             i + 8);
    if ( DoesNotExceedMaximum < 0 )
      goto LABEL_13;
  }
  for ( j = (_QWORD *)*((_QWORD *)this + 16); j != (_QWORD *)((char *)this + 128); j = (_QWORD *)*j )
  {
    DoesNotExceedMaximum = (*(__int64 (__fastcall **)(struct Wallet::IWalletStorage *, __int64, _QWORD, _QWORD *))(*(_QWORD *)v3 + 96LL))(
                             v3,
                             v27,
                             j[3],
                             j + 7);
    if ( DoesNotExceedMaximum < 0 )
      goto LABEL_13;
  }
  *((_QWORD *)this + 10) = v27;
  DoesNotExceedMaximum = Wallet::WalletItem::VerifyCustomPropertyCountDoesNotExceedMaximum(this, v3);
  if ( DoesNotExceedMaximum < 0 )
    goto LABEL_13;
  DoesNotExceedMaximum = (*(__int64 (__fastcall **)(struct Wallet::IWalletStorage *))(*(_QWORD *)v3 + 48LL))(v3);
  if ( DoesNotExceedMaximum < 0 )
    goto LABEL_13;
  DoesNotExceedMaximum = 0;
  for ( k = 0; k != 9; ++k )
  {
    v17 = *((unsigned int *)&Wallet::WalletItem::sc_rgImagePropertyTypes + k);
    *(_OWORD *)lpFileName = 0;
    v22 = 0;
    if ( (int)Wallet::WalletItem::TGetPropertyValue<utl::unordered_map<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>>,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>(
                v15,
                v24,
                v17,
                lpFileName) >= 0
      && !DeleteFileW(lpFileName[1]) )
    {
      GetLastError();
    }
    PropVariantClear((PROPVARIANT *)lpFileName);
  }
  utl::_HashTable<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::_ClearList((char *)this + 88);
  if ( *((_QWORD *)this + 13) )
    utl::_HashTable<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::_InitBuckets((char *)this + 88);
  utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,ce::WrappedPropVariant>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,ce::WrappedPropVariant>>,0>::_ClearList((char *)this + 128);
  if ( *((_QWORD *)this + 18) )
    utl::_HashTable<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::_InitBuckets((char *)this + 128);
  v12 = v26;
LABEL_36:
  utl::_HashTable<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::_ClearList(v24);
  utl::_HashTable<unsigned long,utl::pair<unsigned long const,LockOrderManagerImp<enum WalletLockOrder>::LockOrderThreadData>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,LockOrderManagerImp<enum WalletLockOrder>::LockOrderThreadData>>,0>::_FreeBuckets(v24);
  Wallet::WalletStorageAttach::~WalletStorageAttach((Wallet::WalletStorageAttach *)v23);
  v18 = ((__int64 (__fastcall *)(void ***))g_LockOrderManagerImp[1])(&g_LockOrderManagerImp);
  if ( (**v2)(v2) != v18 )
    __int2c();
  ((void (__fastcall *)(void ***))g_LockOrderManagerImp[2])(&g_LockOrderManagerImp);
  LeaveCriticalSection((LPCRITICAL_SECTION)((unsigned __int64)(v2 + 1) & -(__int64)(v2 != 0)));
  if ( DoesNotExceedMaximum >= 0 )
  {
    v19 = 1;
    if ( !v12 )
      v19 = 2;
    Wallet::WalletItemManager::NotifyListeners(*((_QWORD *)this + 2), v19, v27);
  }
  return (unsigned int)DoesNotExceedMaximum;
}

```

## disassembly

```asm
0x180028040  mov     [rsp-8+arg_18], rbx
0x180028045  push    rbp
0x180028046  push    rsi
0x180028047  push    rdi
0x180028048  push    r12
0x18002804a  push    r13
0x18002804c  push    r14
0x18002804e  push    r15
0x180028050  lea     rbp, [rsp-27h]
0x180028055  sub     rsp, 0B0h
0x18002805c  mov     r14, [rcx+10h]
0x180028060  mov     r13, rcx
0x180028063  mov     rax, [rcx+50h]
0x180028067  add     r14, 68h ; 'h'
0x18002806b  mov     rcx, r14
0x18002806e  mov     [rbp+57h+arg_8], rax
0x180028072  call    ?lock@?$OrderedLockBase@W4WalletLockOrder@@@@QEAAXXZ; OrderedLockBase<WalletLockOrder>::lock(void)
0x180028077  mov     rdx, [r13+10h]
0x18002807b  lea     rcx, [rbp+57h+var_90]; this
0x18002807f  mov     rdx, [rdx+38h]; struct Wallet::IWalletStorage *
0x180028083  call    ??0WalletStorageAttach@Wallet@@QEAA@PEAUIWalletStorage@1@@Z; Wallet::WalletStorageAttach::WalletStorageAttach(Wallet::IWalletStorage *)
0x180028088  lea     rcx, [rbp+57h+var_80]
0x18002808c  call    ??0?$unordered_map@_KW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@U?$hash@_K@utl@@U?$equal_to@_K@3@V?$allocator@U?$pair@$$CB_KW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@utl@@@3@@utl@@QEAA@XZ; utl::unordered_map<unsigned __int64,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>>>::unordered_map<unsigned __int64,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>>>(void)
0x180028091  mov     rcx, [r13+10h]
0x180028095  mov     r12, [rcx+38h]
0x180028099  lea     rcx, [rbp+57h+var_58]
0x18002809d  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800280a2  lea     rcx, [rbp+57h+lpFileName]
0x1800280a6  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800280ab  cmp     qword ptr [r13+18h], 0
0x1800280b0  jz      short loc_1800280C1
0x1800280b2  mov     rcx, r13; this
0x1800280b5  call    ?SetParentWalletItemId@WalletItem@Wallet@@AEAAJXZ; Wallet::WalletItem::SetParentWalletItemId(void)
0x1800280ba  mov     r15d, eax
0x1800280bd  test    eax, eax
0x1800280bf  js      short loc_1800280C4
0x1800280c1  xor     r15d, r15d
0x1800280c4  lea     rcx, [rbp+57h+lpFileName]
0x1800280c8  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800280cd  lea     rcx, [rbp+57h+var_58]
0x1800280d1  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800280d6  test    r15d, r15d
0x1800280d9  js      loc_180028362
0x1800280df  cmp     [rbp+57h+arg_8], 0
0x1800280e4  jnz     short loc_1800280F0
0x1800280e6  mov     ebx, 1
0x1800280eb  mov     [rbp+57h+arg_0], ebx
0x1800280ee  jmp     short loc_180028101
0x1800280f0  xor     ebx, ebx
0x1800280f2  lea     rdx, [rbp+57h+var_80]
0x1800280f6  mov     rcx, r13
0x1800280f9  mov     [rbp+57h+arg_0], ebx
0x1800280fc  call    ?GetPreviousImagePaths@WalletItem@Wallet@@AEAAJAEAV?$unordered_map@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@utl@@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@5@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@5@@utl@@@Z; Wallet::WalletItem::GetPreviousImagePaths(utl::unordered_map<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>> &)
0x180028101  mov     rax, [r12]
0x180028105  mov     rcx, r12
0x180028108  mov     rax, [rax+28h]
0x18002810c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028111  mov     r15d, eax
0x180028114  test    eax, eax
0x180028116  js      short loc_180028153
0x180028118  test    ebx, ebx
0x18002811a  jz      short loc_180028186
0x18002811c  mov     rcx, [r13+18h]; this
0x180028120  mov     [rbp+57h+arg_10], 0
0x180028128  test    rcx, rcx
0x18002812b  jz      short loc_18002815B
0x18002812d  mov     ebx, [r13+0A8h]
0x180028134  call    ?GetWalletItemId@Utils@Wallet@@YA_KPEAUIWalletItem@@@Z; Wallet::Utils::GetWalletItemId(IWalletItem *)
0x180028139  mov     edx, ebx
0x18002813b  mov     rcx, rax
0x18002813e  call    ?VerifyChildItemsDoNotExceedMax@WalletItem@Wallet@@CAJ_KW4__MIDL___MIDL_itf_wallettypes_0000_0000_0001@@@Z; Wallet::WalletItem::VerifyChildItemsDoNotExceedMax(unsigned __int64,__MIDL___MIDL_itf_wallettypes_0000_0000_0001)
0x180028143  mov     r15d, eax
0x180028146  test    eax, eax
0x180028148  jns     short loc_18002815B
0x18002814a  lea     rcx, [rbp+57h+arg_10]
0x18002814e  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180028153  mov     edi, [rbp+57h+arg_0]
0x180028156  jmp     loc_180028364
0x18002815b  mov     rax, [r12]
0x18002815f  lea     r8, [rbp+57h+arg_8]
0x180028163  mov     edx, [r13+0A8h]
0x18002816a  mov     rcx, r12
0x18002816d  mov     rax, [rax+40h]
0x180028171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028176  lea     rcx, [rbp+57h+arg_10]
0x18002817a  mov     r15d, eax
0x18002817d  test    eax, eax
0x18002817f  js      short loc_18002814E
0x180028181  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180028186  lea     rdi, [r13+58h]
0x18002818a  mov     rbx, [rdi]
0x18002818d  cmp     rbx, rdi
0x180028190  jz      short loc_1800281BA
0x180028192  mov     rax, [r12]
0x180028196  lea     r9, [rbx+20h]
0x18002819a  mov     r8d, [rbx+18h]
0x18002819e  mov     rcx, r12
0x1800281a1  mov     rdx, [rbp+57h+arg_8]
0x1800281a5  mov     rax, [rax+50h]
0x1800281a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281ae  mov     r15d, eax
0x1800281b1  test    eax, eax
0x1800281b3  js      short loc_180028153
0x1800281b5  mov     rbx, [rbx]
0x1800281b8  jmp     short loc_18002818D
0x1800281ba  lea     rbx, [r13+80h]
0x1800281c1  mov     rsi, [rbx]
0x1800281c4  cmp     rsi, rbx
0x1800281c7  jz      short loc_1800281F5
0x1800281c9  mov     rax, [r12]
0x1800281cd  lea     r9, [rsi+38h]
0x1800281d1  mov     r8, [rsi+18h]
0x1800281d5  mov     rcx, r12
0x1800281d8  mov     rdx, [rbp+57h+arg_8]
0x1800281dc  mov     rax, [rax+60h]
0x1800281e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281e5  mov     r15d, eax
0x1800281e8  test    eax, eax
0x1800281ea  js      loc_180028153
0x1800281f0  mov     rsi, [rsi]
0x1800281f3  jmp     short loc_1800281C4
0x1800281f5  mov     rax, [rbp+57h+arg_8]
0x1800281f9  mov     rdx, r12; struct Wallet::IWalletStorage *
0x1800281fc  mov     rcx, r13; this
0x1800281ff  mov     [r13+50h], rax
0x180028203  call    ?VerifyCustomPropertyCountDoesNotExceedMaximum@WalletItem@Wallet@@AEAAJPEAUIWalletStorage@2@@Z; Wallet::WalletItem::VerifyCustomPropertyCountDoesNotExceedMaximum(Wallet::IWalletStorage *)
0x180028208  mov     r15d, eax
0x18002820b  test    eax, eax
0x18002820d  js      loc_180028153
0x180028213  mov     rax, [r12]
0x180028217  mov     rcx, r12
0x18002821a  mov     rax, [rax+30h]
0x18002821e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028223  mov     r15d, eax
0x180028226  test    eax, eax
0x180028228  js      loc_180028153
0x18002822e  xor     r15d, r15d
0x180028231  xor     esi, esi
0x180028233  lea     r8, ?sc_rgImagePropertyTypes@WalletItem@Wallet@@2QBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@B; __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const near * const Wallet::WalletItem::sc_rgImagePropertyTypes
0x18002823a  xorps   xmm0, xmm0
0x18002823d  mov     r8d, [r8+rsi*4]
0x180028241  lea     r9, [rbp+57h+lpFileName]
0x180028245  xor     eax, eax
0x180028247  lea     rdx, [rbp+57h+var_80]
0x18002824b  movups  xmmword ptr [rbp+57h+lpFileName], xmm0
0x18002824f  mov     [rbp+57h+var_A0], rax
0x180028253  call    ??$TGetPropertyValue@V?$unordered_map@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@utl@@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@5@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@5@@utl@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@WalletItem@Wallet@@QEBAJAEBV?$unordered_map@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@utl@@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@5@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@5@@utl@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEAUtagPROPVARIANT@@@Z; Wallet::WalletItem::TGetPropertyValue<utl::unordered_map<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>>,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(utl::unordered_map<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ce::WrappedPropVariant,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>> const &,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,tagPROPVARIANT *)
0x180028258  test    eax, eax
0x18002825a  js      short loc_180028270
0x18002825c  mov     rcx, [rbp+57h+lpFileName+8]; lpFileName
0x180028260  call    cs:__imp_DeleteFileW
0x180028266  test    eax, eax
0x180028268  jnz     short loc_180028270
0x18002826a  call    cs:__imp_GetLastError
0x180028270  lea     rcx, [rbp+57h+lpFileName]; pvar
0x180028274  call    cs:__imp_PropVariantClear
0x18002827a  inc     rsi
0x18002827d  cmp     rsi, 9
0x180028281  jnz     short loc_180028233
0x180028283  mov     rcx, rdi
0x180028286  call    ?_ClearList@?$_HashTable@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::_ClearList(void)
0x18002828b  cmp     [rdi+10h], r15
0x18002828f  jz      short loc_180028299
0x180028291  mov     rcx, rdi
0x180028294  call    ?_InitBuckets@?$_HashTable@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::_InitBuckets(void)
0x180028299  mov     rcx, rbx
0x18002829c  call    ?_ClearList@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@VWrappedPropVariant@ce@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@VWrappedPropVariant@ce@@@utl@@@2@$0A@@utl@@AEAAXXZ; utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ce::WrappedPropVariant>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,ce::WrappedPropVariant>>,0>::_ClearList(void)
0x1800282a1  cmp     [rbx+10h], r15
0x1800282a5  jz      short loc_1800282AF
0x1800282a7  mov     rcx, rbx
0x1800282aa  call    ?_InitBuckets@?$_HashTable@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::_InitBuckets(void)
0x1800282af  mov     edi, [rbp+57h+arg_0]
0x1800282b2  lea     rcx, [rbp+57h+var_80]
0x1800282b6  call    ?_ClearList@?$_HashTable@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@U?$hash@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@U?$equal_to@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@3@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@VWrappedPropVariant@ce@@@utl@@@3@$0A@@utl@@AEAAXXZ; utl::_HashTable<__MIDL___MIDL_itf_wallettypes_0000_0000_0010,utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>,utl::hash<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::equal_to<__MIDL___MIDL_itf_wallettypes_0000_0000_0010>,utl::allocator<utl::pair<__MIDL___MIDL_itf_wallettypes_0000_0000_0010 const,ce::WrappedPropVariant>>,0>::_ClearList(void)
0x1800282bb  lea     rcx, [rbp+57h+var_80]
0x1800282bf  call    ?_FreeBuckets@?$_HashTable@KU?$pair@$$CBKULockOrderThreadData@?$LockOrderManagerImp@W4WalletLockOrder@@@@@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKULockOrderThreadData@?$LockOrderManagerImp@W4WalletLockOrder@@@@@utl@@@2@$0A@@utl@@AEAAXXZ; utl::_HashTable<ulong,utl::pair<ulong const,LockOrderManagerImp<WalletLockOrder>::LockOrderThreadData>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,LockOrderManagerImp<WalletLockOrder>::LockOrderThreadData>>,0>::_FreeBuckets(void)
0x1800282c4  lea     rcx, [rbp+57h+var_90]; this
0x1800282c8  call    ??1WalletStorageAttach@Wallet@@QEAA@XZ; Wallet::WalletStorageAttach::~WalletStorageAttach(void)
0x1800282cd  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x1800282d4  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x1800282db  mov     rax, [rax+8]
0x1800282df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282e4  mov     rcx, [r14]
0x1800282e7  mov     ebx, eax
0x1800282e9  mov     rax, [rcx]
0x1800282ec  mov     rcx, r14
0x1800282ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282f4  cmp     eax, ebx
0x1800282f6  jz      short loc_1800282FA
0x1800282f8  int     2Ch; Windows NT - assertion failure
0x1800282fa  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180028301  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180028308  mov     rax, [rax+10h]
0x18002830c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028311  lea     rax, [r14+8]
0x180028315  neg     r14
0x180028318  sbb     rcx, rcx
0x18002831b  and     rcx, rax; lpCriticalSection
0x18002831e  call    cs:__imp_LeaveCriticalSection
0x180028324  test    r15d, r15d
0x180028327  js      short loc_180028344
0x180028329  mov     rcx, [r13+10h]
0x18002832d  mov     edx, 1
0x180028332  mov     r8, [rbp+57h+arg_8]
0x180028336  test    edi, edi
0x180028338  jnz     short loc_18002833F
0x18002833a  mov     edx, 2
0x18002833f  call    ?NotifyListeners@WalletItemManager@Wallet@@QEAAXW4__MIDL___MIDL_itf_wallettypes_0000_0000_0013@@_K@Z; Wallet::WalletItemManager::NotifyListeners(__MIDL___MIDL_itf_wallettypes_0000_0000_0013,unsigned __int64)
0x180028344  mov     rbx, [rsp+0E0h+arg_18]
0x18002834c  mov     eax, r15d
0x18002834f  add     rsp, 0B0h
0x180028356  pop     r15
0x180028358  pop     r14
0x18002835a  pop     r13
0x18002835c  pop     r12
0x18002835e  pop     rdi
0x18002835f  pop     rsi
0x180028360  pop     rbp
0x180028361  retn
0x180028362  xor     edi, edi
0x180028364  mov     rax, [r12]
0x180028368  mov     rcx, r12
0x18002836b  mov     rax, [rax+38h]
0x18002836f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028374  jmp     loc_1800282B2
```
