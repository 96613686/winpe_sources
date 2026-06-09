# Wallet::WalletItem::GetCustomProperty(ushort const *,IWalletCustomProperty * *)

- ea: `0x1800269f0`
- end: `0x180026bf2`
- name: `?GetCustomProperty@WalletItem@Wallet@@UEAAJPEBGPEAPEAUIWalletCustomProperty@@@Z`
- size: `514`
- prototype: `__int64 __fastcall(Wallet::WalletItem *__hidden this, const unsigned __int16 *, struct IWalletCustomProperty **)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180003ae4`
- `0x1800043b8`
- `0x18000d620`
- `0x18000d8d8`
- `0x18000d944`
- `0x18000dab0`
- `0x180013f78`
- `0x180013fe4`
- `0x180016e78`
- `0x1800269f0`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026bcf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026bcf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180026b66`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180026b66`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180026ab6`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180026ab6`

## pseudocode

```c
__int64 __fastcall Wallet::WalletItem::GetCustomProperty(
        Wallet::WalletItem *this,
        const unsigned __int16 *a2,
        struct IWalletCustomProperty **a3)
{
  unsigned int (__fastcall ***v4)(_QWORD); // r15
  int v7; // edi
  const PROPVARIANT *v8; // rdx
  HRESULT v9; // eax
  __int64 v10; // rdx
  __int64 (__fastcall *v11)(PROPVARIANT, GUID *, __int64 *); // rbx
  __int64 *v12; // rax
  int v13; // eax
  int v14; // ebx
  _BYTE v16[16]; // [rsp+30h] [rbp-50h] BYREF
  PROPVARIANT pvarDest[2]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v18; // [rsp+50h] [rbp-30h]
  void *v19[5]; // [rsp+58h] [rbp-28h] BYREF
  struct IWalletCustomProperty *v20; // [rsp+C0h] [rbp+40h] BYREF
  char v21; // [rsp+C8h] [rbp+48h] BYREF

  v4 = (unsigned int (__fastcall ***)(_QWORD))(*((_QWORD *)this + 2) + 104LL);
  OrderedLockBase<enum WalletLockOrder>::lock(v4);
  Wallet::WalletStorageAttach::WalletStorageAttach(
    (Wallet::WalletStorageAttach *)v16,
    *(struct Wallet::IWalletStorage **)(*((_QWORD *)this + 2) + 56LL));
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>((__int64)v19);
  v18 = 0;
  v20 = 0;
  *(_OWORD *)pvarDest = 0;
  if ( !a2 || !a3 )
  {
    v7 = -2147467261;
    goto LABEL_23;
  }
  if ( !*a2 )
  {
    v7 = -2147024809;
    goto LABEL_23;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (__int64)v19,
                           (__int64)a2) )
  {
    v7 = -2147024882;
    goto LABEL_23;
  }
  v8 = *(const PROPVARIANT **)utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,0>::_FindFirst<utl::_HashTable<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::hash<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::equal_to<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,0>::_FindFirstFind,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>(
                                (char *)this + 128,
                                &v21,
                                v19);
  if ( v8 == (const PROPVARIANT *)((char *)this + 128) )
  {
    v7 = -2143682560;
  }
  else
  {
    v9 = PropVariantCopy(pvarDest, v8 + 7);
    v7 = v9;
    if ( v9 >= 0 )
    {
      v7 = 0;
      goto LABEL_16;
    }
    if ( v9 != -2143682560 )
    {
LABEL_16:
      if ( LOWORD(pvarDest[0]) )
      {
        if ( LOWORD(pvarDest[0]) == 13 )
        {
          v11 = **(__int64 (__fastcall ***)(PROPVARIANT, GUID *, __int64 *))pvarDest[1];
          v12 = ce::pointerTo<IWalletNotification>((__int64 *)&v20);
          v13 = v11(pvarDest[1], &GUID_21f1a452_9759_48a5_8d9b_bbd859ef89ee, v12);
          if ( v13 >= 0 )
          {
            *a3 = v20;
            v20 = 0;
          }
          else
          {
            v7 = v13;
          }
        }
        else
        {
          v7 = -2147418113;
        }
      }
      else
      {
        v7 = -2143682560;
      }
      goto LABEL_23;
    }
  }
  v10 = *((_QWORD *)this + 10);
  if ( !v10 )
    goto LABEL_16;
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, const unsigned __int16 *, PROPVARIANT *))(**(_QWORD **)(*((_QWORD *)this + 2) + 56LL)
                                                                                           + 104LL))(
         *(_QWORD *)(*((_QWORD *)this + 2) + 56LL),
         v10,
         a2,
         pvarDest);
  if ( v7 >= 0 )
    goto LABEL_16;
LABEL_23:
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&v20);
  PropVariantClear(pvarDest);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v19);
  Wallet::WalletStorageAttach::~WalletStorageAttach((Wallet::WalletStorageAttach *)v16);
  v14 = ((__int64 (__fastcall *)(void ***))g_LockOrderManagerImp[1])(&g_LockOrderManagerImp);
  if ( (**v4)(v4) != v14 )
    __int2c();
  ((void (__fastcall *)(void ***))g_LockOrderManagerImp[2])(&g_LockOrderManagerImp);
  LeaveCriticalSection((LPCRITICAL_SECTION)((unsigned __int64)(v4 + 1) & -(__int64)(v4 != 0)));
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800269f0  mov     [rsp-38h+arg_10], rbx
0x1800269f5  push    rbp
0x1800269f6  push    rsi
0x1800269f7  push    rdi
0x1800269f8  push    r12
0x1800269fa  push    r13
0x1800269fc  push    r14
0x1800269fe  push    r15
0x180026a00  mov     rbp, rsp
0x180026a03  sub     rsp, 80h
0x180026a0a  mov     r15, [rcx+10h]
0x180026a0e  mov     rsi, rcx
0x180026a11  add     r15, 68h ; 'h'
0x180026a15  mov     r12, r8
0x180026a18  mov     rcx, r15
0x180026a1b  mov     r14, rdx
0x180026a1e  call    ?lock@?$OrderedLockBase@W4WalletLockOrder@@@@QEAAXXZ; OrderedLockBase<WalletLockOrder>::lock(void)
0x180026a23  mov     rdx, [rsi+10h]
0x180026a27  lea     rcx, [rbp+var_50]; this
0x180026a2b  mov     rdx, [rdx+38h]; struct Wallet::IWalletStorage *
0x180026a2f  call    ??0WalletStorageAttach@Wallet@@QEAA@PEAUIWalletStorage@1@@Z; Wallet::WalletStorageAttach::WalletStorageAttach(Wallet::IWalletStorage *)
0x180026a34  lea     rcx, [rbp+var_28]
0x180026a38  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180026a3d  xor     eax, eax
0x180026a3f  xor     r13d, r13d
0x180026a42  mov     [rbp+var_30], rax
0x180026a46  xorps   xmm0, xmm0
0x180026a49  mov     [rbp+arg_0], r13
0x180026a4d  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180026a51  test    r14, r14
0x180026a54  jnz     short loc_180026A60
0x180026a56  mov     edi, 80004003h
0x180026a5b  jmp     loc_180026B59
0x180026a60  test    r12, r12
0x180026a63  jz      short loc_180026A56
0x180026a65  cmp     [r14], r13w
0x180026a69  jnz     short loc_180026A75
0x180026a6b  mov     edi, 80070057h
0x180026a70  jmp     loc_180026B59
0x180026a75  mov     rdx, r14
0x180026a78  lea     rcx, [rbp+var_28]
0x180026a7c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180026a81  test    al, al
0x180026a83  jnz     short loc_180026A8F
0x180026a85  mov     edi, 8007000Eh
0x180026a8a  jmp     loc_180026B59
0x180026a8f  lea     rbx, [rsi+80h]
0x180026a96  mov     rcx, rbx
0x180026a99  lea     r8, [rbp+var_28]
0x180026a9d  lea     rdx, [rbp+arg_8]
0x180026aa1  call    ??$_FindFirst@U_FindFirstFind@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@$0A@@utl@@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@3@@?$_HashTable@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@U?$hash@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@$0A@@utl@@AEBA?AU_FindFirstFind@01@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,0>::_FindFirst<utl::_HashTable<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::hash<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::equal_to<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,0>::_FindFirstFind,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180026aa6  mov     rdx, [rax]
0x180026aa9  cmp     rdx, rbx
0x180026aac  jz      short loc_180026AD0
0x180026aae  add     rdx, 38h ; '8'; pvarSrc
0x180026ab2  lea     rcx, [rbp+pvarDest]; pvarDest
0x180026ab6  call    cs:__imp_PropVariantCopy
0x180026abc  mov     edi, eax
0x180026abe  test    eax, eax
0x180026ac0  js      short loc_180026AC7
0x180026ac2  mov     edi, r13d
0x180026ac5  jmp     short loc_180026AFF
0x180026ac7  cmp     eax, 803A0000h
0x180026acc  jnz     short loc_180026AFF
0x180026ace  jmp     short loc_180026AD5
0x180026ad0  mov     edi, 803A0000h
0x180026ad5  mov     rdx, [rsi+50h]
0x180026ad9  test    rdx, rdx
0x180026adc  jz      short loc_180026AFF
0x180026ade  mov     rax, [rsi+10h]
0x180026ae2  lea     r9, [rbp+pvarDest]
0x180026ae6  mov     r8, r14
0x180026ae9  mov     rcx, [rax+38h]
0x180026aed  mov     rax, [rcx]
0x180026af0  mov     rax, [rax+68h]
0x180026af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026af9  mov     edi, eax
0x180026afb  test    eax, eax
0x180026afd  js      short loc_180026B59
0x180026aff  movzx   eax, word ptr [rbp+pvarDest]
0x180026b03  test    ax, ax
0x180026b06  jnz     short loc_180026B0F
0x180026b08  mov     edi, 803A0000h
0x180026b0d  jmp     short loc_180026B59
0x180026b0f  cmp     ax, 0Dh
0x180026b13  jz      short loc_180026B1C
0x180026b15  mov     edi, 8000FFFFh
0x180026b1a  jmp     short loc_180026B59
0x180026b1c  mov     rax, [rbp+pvarDest+8]
0x180026b20  mov     rcx, [rax]
0x180026b23  mov     rbx, [rcx]
0x180026b26  lea     rcx, [rbp+arg_0]
0x180026b2a  call    ??$pointerTo@UIWalletNotification@@@ce@@YAPEAPEAUIWalletNotification@@AEAV?$CComPtr@UIWalletNotification@@@ATL@@@Z; ce::pointerTo<IWalletNotification>(ATL::CComPtr<IWalletNotification> &)
0x180026b2f  mov     rcx, [rbp+pvarDest+8]
0x180026b33  lea     rdx, _GUID_21f1a452_9759_48a5_8d9b_bbd859ef89ee
0x180026b3a  mov     r8, rax
0x180026b3d  mov     rax, rbx
0x180026b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b45  test    eax, eax
0x180026b47  jns     short loc_180026B4D
0x180026b49  mov     edi, eax
0x180026b4b  jmp     short loc_180026B59
0x180026b4d  mov     rax, [rbp+arg_0]
0x180026b51  mov     [r12], rax
0x180026b55  mov     [rbp+arg_0], r13
0x180026b59  lea     rcx, [rbp+arg_0]
0x180026b5d  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180026b62  lea     rcx, [rbp+pvarDest]; pvar
0x180026b66  call    cs:__imp_PropVariantClear
0x180026b6c  lea     rcx, [rbp+var_28]
0x180026b70  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180026b75  lea     rcx, [rbp+var_50]; this
0x180026b79  call    ??1WalletStorageAttach@Wallet@@QEAA@XZ; Wallet::WalletStorageAttach::~WalletStorageAttach(void)
0x180026b7e  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180026b85  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180026b8c  mov     rax, [rax+8]
0x180026b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b95  mov     rcx, [r15]
0x180026b98  mov     ebx, eax
0x180026b9a  mov     rax, [rcx]
0x180026b9d  mov     rcx, r15
0x180026ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ba5  cmp     eax, ebx
0x180026ba7  jz      short loc_180026BAB
0x180026ba9  int     2Ch; Windows NT - assertion failure
0x180026bab  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180026bb2  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180026bb9  mov     rax, [rax+10h]
0x180026bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bc2  lea     rax, [r15+8]
0x180026bc6  neg     r15
0x180026bc9  sbb     rcx, rcx
0x180026bcc  and     rcx, rax; lpCriticalSection
0x180026bcf  call    cs:__imp_LeaveCriticalSection
0x180026bd5  mov     rbx, [rsp+80h+arg_10]
0x180026bdd  mov     eax, edi
0x180026bdf  add     rsp, 80h
0x180026be6  pop     r15
0x180026be8  pop     r14
0x180026bea  pop     r13
0x180026bec  pop     r12
0x180026bee  pop     rdi
0x180026bef  pop     rsi
0x180026bf0  pop     rbp
0x180026bf1  retn
```
