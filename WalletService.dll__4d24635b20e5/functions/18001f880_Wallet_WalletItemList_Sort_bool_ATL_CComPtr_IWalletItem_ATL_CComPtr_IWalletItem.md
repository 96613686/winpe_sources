# Wallet::WalletItemList::Sort(bool (*)(ATL::CComPtr<IWalletItem> &,ATL::CComPtr<IWalletItem> &))

- ea: `0x18001f880`
- end: `0x18001fada`
- name: `?Sort@WalletItemList@Wallet@@QEAAJP6A_NAEAV?$CComPtr@UIWalletItem@@@ATL@@0@Z@Z`
- size: `602`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800216f8`
- `0x180022e80`

## callees

- `0x180003ae4`
- `0x180014328`
- `0x180016e78`
- `0x18001e754`
- `0x18001e7f8`
- `0x18001e8a8`
- `0x18001f880`
- `0x18001fea8`
- `0x18001feec`
- `0x18001ff18`
- `0x180038f74`
- `0x180039058`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fab9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fab9`

## pseudocode

```c
__int64 __fastcall Wallet::WalletItemList::Sort(
        __int64 a1,
        unsigned __int8 (__fastcall *a2)(struct IUnknown **, struct IUnknown **))
{
  __int64 v2; // rsi
  unsigned int v4; // r15d
  struct IWalletItem *v5; // rdx
  __int64 v6; // rcx
  __int64 *v7; // rbx
  __int64 v8; // r14
  struct IUnknown **v9; // rdi
  __int64 v10; // r13
  unsigned __int64 *v11; // r12
  unsigned __int64 v12; // rcx
  int WalletItem; // eax
  __int64 v14; // r8
  Wallet::Utils **v15; // rbx
  unsigned __int64 *v16; // r14
  unsigned __int64 WalletItemId; // rax
  unsigned __int64 *i; // rbx
  int v19; // ebx
  __m128i v21; // [rsp+20h] [rbp-50h] BYREF
  __int64 v22; // [rsp+30h] [rbp-40h]
  __m128i v23; // [rsp+38h] [rbp-38h] BYREF
  __int64 v24; // [rsp+48h] [rbp-28h]
  __m128i si128; // [rsp+50h] [rbp-20h] BYREF
  __int64 v26; // [rsp+60h] [rbp-10h]
  unsigned __int64 v27; // [rsp+B0h] [rbp+40h] BYREF
  unsigned __int8 (__fastcall *v28)(struct IUnknown **, struct IUnknown **); // [rsp+B8h] [rbp+48h]
  __int64 v29; // [rsp+C0h] [rbp+50h]

  v28 = a2;
  v2 = a1 + 64;
  v4 = 0;
  OrderedLockBase<enum WalletLockOrder>::lock(a1 + 64);
  v6 = a1 + 40;
  v7 = *(__int64 **)(a1 + 40);
  v8 = -1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v9 = (struct IUnknown **)si128.m128i_i64[1];
  v10 = -1;
  v23 = si128;
  v11 = (unsigned __int64 *)si128.m128i_i64[1];
  v26 = -1;
  v21 = si128;
  v22 = -1;
  v24 = -1;
  v29 = v6;
  while ( v7 != *(__int64 **)(v6 + 8) )
  {
    v12 = *v7;
    v27 = 0;
    WalletItem = Wallet::Utils::GetWalletItem(v12, &v27);
    v4 = WalletItem;
    if ( WalletItem == -2143682560 )
    {
      if ( v11 == (unsigned __int64 *)v24 )
      {
        utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::_PushBackOne2<unsigned __int64 const &>(
          &v23,
          v7);
        v11 = (unsigned __int64 *)v23.m128i_i64[1];
      }
      else
      {
        *v11++ = *v7;
        v23.m128i_i64[1] = (__int64)v11;
      }
      v4 = 0;
    }
    else
    {
      if ( WalletItem < 0 )
      {
        ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&v27);
        goto LABEL_30;
      }
      if ( v9 == (struct IUnknown **)v8 )
      {
        utl::vector<ATL::CComPtr<IWalletItemListener>,utl::allocator<ATL::CComPtr<IWalletItemListener>>>::_PushBackOne2<ATL::CComPtr<IWalletItemListener>>(
          si128.m128i_i64,
          &v27,
          v14);
        v8 = v26;
        v9 = (struct IUnknown **)si128.m128i_i64[1];
      }
      else
      {
        ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(v9++, v27);
        si128.m128i_i64[1] = (__int64)v9;
      }
    }
    ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&v27);
    v6 = v29;
    ++v7;
  }
  v15 = (Wallet::Utils **)si128.m128i_i64[0];
  if ( (unsigned __int64)(((__int64)v9 - si128.m128i_i64[0]) >> 3) > 1 )
    std::_Sort<utl::_ArrayIt<ATL::CComPtr<IWalletItem>>,__int64,bool (*)(ATL::CComPtr<IWalletItem> &,ATL::CComPtr<IWalletItem> &)>(
      (struct IUnknown **)si128.m128i_i64[0],
      v9,
      ((__int64)v9 - si128.m128i_i64[0]) >> 3,
      v28);
  v16 = (unsigned __int64 *)v21.m128i_i64[1];
  while ( v15 != (Wallet::Utils **)v9 )
  {
    WalletItemId = Wallet::Utils::GetWalletItemId(*v15, v5);
    v27 = WalletItemId;
    if ( v16 == (unsigned __int64 *)v10 )
    {
      utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::_PushBackOne2<unsigned __int64 const &>(
        &v21,
        &v27);
      v10 = v22;
      v16 = (unsigned __int64 *)v21.m128i_i64[1];
    }
    else
    {
      *v16++ = WalletItemId;
      v21.m128i_i64[1] = (__int64)v16;
    }
    ++v15;
  }
  for ( i = (unsigned __int64 *)v23.m128i_i64[0]; i != v11; ++i )
  {
    if ( v16 == (unsigned __int64 *)v10 )
    {
      utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::_PushBackOne2<unsigned __int64 const &>(&v21, i);
      v10 = v22;
      v16 = (unsigned __int64 *)v21.m128i_i64[1];
    }
    else
    {
      *v16++ = *i;
      v21.m128i_i64[1] = (__int64)v16;
    }
  }
  if ( !(unsigned __int8)utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::assign(v29, &v21) )
    v4 = -2147024882;
LABEL_30:
  utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::_Uninit(&v23);
  utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::_Uninit(&v21);
  utl::vector<ATL::CComPtr<IWalletBackgroundAgentListener>,utl::allocator<ATL::CComPtr<IWalletBackgroundAgentListener>>>::_Uninit((__int64)&si128);
  v19 = ((__int64 (__fastcall *)(void ***))g_LockOrderManagerImp[1])(&g_LockOrderManagerImp);
  if ( (**(unsigned int (__fastcall ***)(__int64))v2)(v2) != v19 )
    __int2c();
  ((void (__fastcall *)(void ***))g_LockOrderManagerImp[2])(&g_LockOrderManagerImp);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 8));
  return v4;
}

```

## disassembly

```asm
0x18001f880  mov     [rsp-38h+arg_18], rbx
0x18001f885  mov     [rsp-38h+arg_8], rdx
0x18001f88a  push    rbp
0x18001f88b  push    rsi
0x18001f88c  push    rdi
0x18001f88d  push    r12
0x18001f88f  push    r13
0x18001f891  push    r14
0x18001f893  push    r15
0x18001f895  mov     rbp, rsp
0x18001f898  sub     rsp, 70h
0x18001f89c  lea     rsi, [rcx+40h]
0x18001f8a0  mov     rbx, rcx
0x18001f8a3  mov     rcx, rsi
0x18001f8a6  xor     r15d, r15d
0x18001f8a9  call    ?lock@?$OrderedLockBase@W4WalletLockOrder@@@@QEAAXXZ; OrderedLockBase<WalletLockOrder>::lock(void)
0x18001f8ae  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18001f8b6  lea     rcx, [rbx+28h]
0x18001f8ba  mov     rbx, [rcx]
0x18001f8bd  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001f8c1  movdqu  [rbp+var_20], xmm0
0x18001f8c6  mov     rdi, qword ptr [rbp+var_20+8]
0x18001f8ca  mov     r13, r14
0x18001f8cd  movdqu  [rbp+var_38], xmm0
0x18001f8d2  mov     r12, qword ptr [rbp+var_38+8]
0x18001f8d6  mov     [rbp+var_10], r14
0x18001f8da  movdqu  [rbp+var_50], xmm0
0x18001f8df  mov     [rbp+var_40], r14
0x18001f8e3  mov     [rbp+var_28], r14
0x18001f8e7  mov     [rbp+arg_10], rcx
0x18001f8eb  cmp     rbx, [rcx+8]
0x18001f8ef  jz      loc_18001F997
0x18001f8f5  mov     rcx, [rbx]
0x18001f8f8  lea     rdx, [rbp+arg_0]
0x18001f8fc  mov     [rbp+arg_0], 0
0x18001f904  call    ?GetWalletItem@Utils@Wallet@@YAJ_KAEAV?$CComPtr@UIWalletItem@@@ATL@@@Z; Wallet::Utils::GetWalletItem(unsigned __int64,ATL::CComPtr<IWalletItem> &)
0x18001f909  mov     r15d, eax
0x18001f90c  cmp     eax, 803A0000h
0x18001f911  jnz     short loc_18001F93F
0x18001f913  cmp     r12, [rbp+var_28]
0x18001f917  jz      short loc_18001F92A
0x18001f919  mov     rax, [rbx]
0x18001f91c  mov     [r12], rax
0x18001f920  add     r12, 8
0x18001f924  mov     qword ptr [rbp+var_38+8], r12
0x18001f928  jmp     short loc_18001F93A
0x18001f92a  mov     rdx, rbx
0x18001f92d  lea     rcx, [rbp+var_38]
0x18001f931  call    ??$_PushBackOne2@AEB_K@?$vector@_KV?$allocator@_K@utl@@@utl@@AEAA_NAEB_K@Z; utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::_PushBackOne2<unsigned __int64 const &>(unsigned __int64 const &)
0x18001f936  mov     r12, qword ptr [rbp+var_38+8]
0x18001f93a  xor     r15d, r15d
0x18001f93d  jmp     short loc_18001F973
0x18001f93f  test    eax, eax
0x18001f941  js      short loc_18001F989
0x18001f943  cmp     rdi, r14
0x18001f946  jz      short loc_18001F95E
0x18001f948  mov     rdx, [rbp+arg_0]
0x18001f94c  mov     rcx, rdi
0x18001f94f  call    ??0?$CComPtrBase@UIWalletBackgroundAgentListener@@@ATL@@IEAA@PEAUIWalletBackgroundAgentListener@@@Z; ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(IWalletBackgroundAgentListener *)
0x18001f954  add     rdi, 8
0x18001f958  mov     qword ptr [rbp+var_20+8], rdi
0x18001f95c  jmp     short loc_18001F973
0x18001f95e  lea     rdx, [rbp+arg_0]
0x18001f962  lea     rcx, [rbp+var_20]
0x18001f966  call    ??$_PushBackOne2@V?$CComPtr@UIWalletItemListener@@@ATL@@@?$vector@V?$CComPtr@UIWalletItemListener@@@ATL@@V?$allocator@V?$CComPtr@UIWalletItemListener@@@ATL@@@utl@@@utl@@AEAA_N$$QEAV?$CComPtr@UIWalletItemListener@@@ATL@@@Z; utl::vector<ATL::CComPtr<IWalletItemListener>,utl::allocator<ATL::CComPtr<IWalletItemListener>>>::_PushBackOne2<ATL::CComPtr<IWalletItemListener>>(ATL::CComPtr<IWalletItemListener> &&)
0x18001f96b  mov     r14, [rbp+var_10]
0x18001f96f  mov     rdi, qword ptr [rbp+var_20+8]
0x18001f973  lea     rcx, [rbp+arg_0]
0x18001f977  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18001f97c  mov     rcx, [rbp+arg_10]
0x18001f980  add     rbx, 8
0x18001f984  jmp     loc_18001F8EB
0x18001f989  lea     rcx, [rbp+arg_0]
0x18001f98d  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18001f992  jmp     loc_18001FA56
0x18001f997  mov     rbx, qword ptr [rbp+var_20]
0x18001f99b  mov     rax, rdi
0x18001f99e  sub     rax, rbx
0x18001f9a1  sar     rax, 3
0x18001f9a5  cmp     rax, 1
0x18001f9a9  jbe     short loc_18001F9C4
0x18001f9ab  mov     r9, [rbp+arg_8]
0x18001f9af  mov     r8, rdi
0x18001f9b2  sub     r8, rbx
0x18001f9b5  mov     rdx, rdi
0x18001f9b8  sar     r8, 3
0x18001f9bc  mov     rcx, rbx
0x18001f9bf  call    ??$_Sort@V?$_ArrayIt@V?$CComPtr@UIWalletItem@@@ATL@@@utl@@_JP6A_NAEAV?$CComPtr@UIWalletItem@@@ATL@@0@Z@std@@YAXV?$_ArrayIt@V?$CComPtr@UIWalletItem@@@ATL@@@utl@@0_JP6A_NAEAV?$CComPtr@UIWalletItem@@@ATL@@2@Z@Z; std::_Sort<utl::_ArrayIt<ATL::CComPtr<IWalletItem>>,__int64,bool (*)(ATL::CComPtr<IWalletItem> &,ATL::CComPtr<IWalletItem> &)>(utl::_ArrayIt<ATL::CComPtr<IWalletItem>>,utl::_ArrayIt<ATL::CComPtr<IWalletItem>>,__int64,bool (*)(ATL::CComPtr<IWalletItem> &,ATL::CComPtr<IWalletItem> &))
0x18001f9c4  mov     r14, qword ptr [rbp+var_50+8]
0x18001f9c8  cmp     rbx, rdi
0x18001f9cb  jz      short loc_18001FA06
0x18001f9cd  mov     rcx, [rbx]; this
0x18001f9d0  call    ?GetWalletItemId@Utils@Wallet@@YA_KPEAUIWalletItem@@@Z; Wallet::Utils::GetWalletItemId(IWalletItem *)
0x18001f9d5  mov     [rbp+arg_0], rax
0x18001f9d9  cmp     r14, r13
0x18001f9dc  jz      short loc_18001F9EB
0x18001f9de  mov     [r14], rax
0x18001f9e1  add     r14, 8
0x18001f9e5  mov     qword ptr [rbp+var_50+8], r14
0x18001f9e9  jmp     short loc_18001FA00
0x18001f9eb  lea     rdx, [rbp+arg_0]
0x18001f9ef  lea     rcx, [rbp+var_50]
0x18001f9f3  call    ??$_PushBackOne2@AEB_K@?$vector@_KV?$allocator@_K@utl@@@utl@@AEAA_NAEB_K@Z; utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::_PushBackOne2<unsigned __int64 const &>(unsigned __int64 const &)
0x18001f9f8  mov     r13, [rbp+var_40]
0x18001f9fc  mov     r14, qword ptr [rbp+var_50+8]
0x18001fa00  add     rbx, 8
0x18001fa04  jmp     short loc_18001F9C8
0x18001fa06  mov     rbx, qword ptr [rbp+var_38]
0x18001fa0a  cmp     rbx, r12
0x18001fa0d  jz      short loc_18001FA3E
0x18001fa0f  cmp     r14, r13
0x18001fa12  jz      short loc_18001FA24
0x18001fa14  mov     rax, [rbx]
0x18001fa17  mov     [r14], rax
0x18001fa1a  add     r14, 8
0x18001fa1e  mov     qword ptr [rbp+var_50+8], r14
0x18001fa22  jmp     short loc_18001FA38
0x18001fa24  mov     rdx, rbx
0x18001fa27  lea     rcx, [rbp+var_50]
0x18001fa2b  call    ??$_PushBackOne2@AEB_K@?$vector@_KV?$allocator@_K@utl@@@utl@@AEAA_NAEB_K@Z; utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::_PushBackOne2<unsigned __int64 const &>(unsigned __int64 const &)
0x18001fa30  mov     r13, [rbp+var_40]
0x18001fa34  mov     r14, qword ptr [rbp+var_50+8]
0x18001fa38  add     rbx, 8
0x18001fa3c  jmp     short loc_18001FA0A
0x18001fa3e  mov     rcx, [rbp+arg_10]
0x18001fa42  lea     rdx, [rbp+var_50]
0x18001fa46  call    ?assign@?$vector@_KV?$allocator@_K@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::assign(utl::vector<unsigned __int64,utl::allocator<unsigned __int64>> const &)
0x18001fa4b  test    al, al
0x18001fa4d  mov     ecx, 8007000Eh
0x18001fa52  cmovz   r15d, ecx
0x18001fa56  lea     rcx, [rbp+var_38]
0x18001fa5a  call    ?_Uninit@?$vector@_KV?$allocator@_K@utl@@@utl@@AEAAXXZ; utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::_Uninit(void)
0x18001fa5f  lea     rcx, [rbp+var_50]
0x18001fa63  call    ?_Uninit@?$vector@_KV?$allocator@_K@utl@@@utl@@AEAAXXZ; utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::_Uninit(void)
0x18001fa68  lea     rcx, [rbp+var_20]
0x18001fa6c  call    ?_Uninit@?$vector@V?$CComPtr@UIWalletBackgroundAgentListener@@@ATL@@V?$allocator@V?$CComPtr@UIWalletBackgroundAgentListener@@@ATL@@@utl@@@utl@@AEAAXXZ; utl::vector<ATL::CComPtr<IWalletBackgroundAgentListener>,utl::allocator<ATL::CComPtr<IWalletBackgroundAgentListener>>>::_Uninit(void)
0x18001fa71  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x18001fa78  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x18001fa7f  mov     rax, [rax+8]
0x18001fa83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa88  mov     rcx, [rsi]
0x18001fa8b  mov     ebx, eax
0x18001fa8d  mov     rax, [rcx]
0x18001fa90  mov     rcx, rsi
0x18001fa93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa98  cmp     eax, ebx
0x18001fa9a  jz      short loc_18001FA9E
0x18001fa9c  int     2Ch; Windows NT - assertion failure
0x18001fa9e  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x18001faa5  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x18001faac  mov     rax, [rax+10h]
0x18001fab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fab5  lea     rcx, [rsi+8]; lpCriticalSection
0x18001fab9  call    cs:__imp_LeaveCriticalSection
0x18001fabf  mov     rbx, [rsp+70h+arg_18]
0x18001fac7  mov     eax, r15d
0x18001faca  add     rsp, 70h
0x18001face  pop     r15
0x18001fad0  pop     r14
0x18001fad2  pop     r13
0x18001fad4  pop     r12
0x18001fad6  pop     rdi
0x18001fad7  pop     rsi
0x18001fad8  pop     rbp
0x18001fad9  retn
```
