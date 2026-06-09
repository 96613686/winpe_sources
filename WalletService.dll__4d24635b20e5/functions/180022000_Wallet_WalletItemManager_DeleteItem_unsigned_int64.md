# Wallet::WalletItemManager::DeleteItem(unsigned __int64)

- ea: `0x180022000`
- end: `0x1800222b6`
- name: `?DeleteItem@WalletItemManager@Wallet@@UEAAJ_K@Z`
- size: `694`
- prototype: `__int64 __fastcall(struct Wallet::IWalletStorage **this, unsigned __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180002214`
- `0x180003ae4`
- `0x1800043b8`
- `0x18000d944`
- `0x180016e78`
- `0x1800212dc`
- `0x180022000`
- `0x18002403c`
- `0x180024804`
- `0x180037bd8`
- `0x1800398f8`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022293`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022293`

## pseudocode

```c
__int64 __fastcall Wallet::WalletItemManager::DeleteItem(struct Wallet::IWalletStorage **this, unsigned __int64 a2)
{
  struct Wallet::IWalletStorage *v2; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // r14d
  unsigned int (__fastcall ***v8)(char *); // rbx
  bool v9; // zf
  int v10; // edi
  Wallet::WalletStorageAttach *v11; // rax
  int v12; // edi
  __int64 (__fastcall *v13)(Wallet::WalletItemManager *, unsigned __int64, __int64); // rdi
  __int64 v14; // rax
  int v15; // edi
  __int64 i; // rdi
  int v17; // edi
  int v18; // edi
  __int64 v20; // [rsp+50h] [rbp+30h] BYREF
  __int64 v21; // [rsp+60h] [rbp+40h] BYREF
  Wallet::WalletStorageAttach *v22; // [rsp+68h] [rbp+48h] BYREF

  v2 = *this;
  v21 = 0;
  v7 = (*((__int64 (__fastcall **)(struct Wallet::IWalletStorage **))v2 + 6))(this);
  if ( v7 >= 0 )
  {
    Wallet::WalletItemManager::NotifyListeners(this, 3, a2);
    v8 = (unsigned int (__fastcall ***)(char *))(this + 13);
    OrderedLockBase<enum WalletLockOrder>::lock(this + 13);
    v9 = *((_DWORD *)this + 12) == 0;
    v20 = 0;
    if ( v9 )
    {
      v7 = -2143682555;
      std::unique_ptr<Wallet::WalletStorageAttach>::_Delete(&v20);
      v10 = ((__int64 (__fastcall *)(void ***))g_LockOrderManagerImp[1])(&g_LockOrderManagerImp);
      if ( (**v8)((char *)this + 104) != v10 )
LABEL_4:
        __int2c();
LABEL_22:
      ((void (__fastcall *)(void ***))g_LockOrderManagerImp[2])(&g_LockOrderManagerImp);
      LeaveCriticalSection((LPCRITICAL_SECTION)((unsigned __int64)(this + 14) & -(__int64)(v8 != 0)));
      goto LABEL_23;
    }
    v11 = (Wallet::WalletStorageAttach *)operator new(0x10u);
    if ( v11 )
      v11 = (Wallet::WalletStorageAttach *)Wallet::WalletStorageAttach::WalletStorageAttach(v11, this[7]);
    v22 = v11;
    std::unique_ptr<Wallet::WalletStorageAttach>::operator=(&v20, &v22);
    std::unique_ptr<Wallet::WalletStorageAttach>::_Delete(&v22);
    if ( !v20 )
    {
      v7 = -2147024882;
      std::unique_ptr<Wallet::WalletStorageAttach>::_Delete(&v20);
      v12 = ((__int64 (__fastcall *)(void ***))g_LockOrderManagerImp[1])(&g_LockOrderManagerImp);
      if ( (**v8)((char *)this + 104) == v12 )
        goto LABEL_22;
      goto LABEL_4;
    }
    if ( (unsigned int)Wallet::Utils::IsStandardItemType(HIDWORD(a2)) )
    {
      v13 = (__int64 (__fastcall *)(Wallet::WalletItemManager *, unsigned __int64, __int64))*((_QWORD *)*this + 8);
      v14 = ce::pointerTo<IWalletNotification>(&v21);
      v7 = v13((Wallet::WalletItemManager *)this, a2, v14);
      if ( v7 < 0 )
      {
        std::unique_ptr<Wallet::WalletStorageAttach>::_Delete(&v20);
        v15 = ((__int64 (__fastcall *)(void ***))g_LockOrderManagerImp[1])(&g_LockOrderManagerImp);
        if ( (**v8)((char *)this + 104) == v15 )
          goto LABEL_22;
        goto LABEL_4;
      }
      for ( i = 0; i != 9; ++i )
        Wallet::Utils::DeleteItemImage(*((_DWORD *)&Wallet::WalletItem::sc_rgImagePropertyTypes + i), v21);
    }
    v7 = (*(__int64 (__fastcall **)(struct Wallet::IWalletStorage *, unsigned __int64))(*(_QWORD *)this[7] + 72LL))(
           this[7],
           a2);
    if ( v7 >= 0 )
    {
      v7 = 0;
      std::unique_ptr<Wallet::WalletStorageAttach>::_Delete(&v20);
      v18 = ((__int64 (__fastcall *)(void ***))g_LockOrderManagerImp[1])(&g_LockOrderManagerImp);
      if ( (**v8)((char *)this + 104) == v18 )
        goto LABEL_22;
    }
    else
    {
      std::unique_ptr<Wallet::WalletStorageAttach>::_Delete(&v20);
      v17 = ((__int64 (__fastcall *)(void ***))g_LockOrderManagerImp[1])(&g_LockOrderManagerImp);
      if ( (**v8)((char *)this + 104) == v17 )
        goto LABEL_22;
    }
    __int2c();
    goto LABEL_22;
  }
LABEL_23:
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v21, v5, v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180022000  mov     [rsp-28h+arg_8], rbx
0x180022005  push    rbp
0x180022006  push    rsi
0x180022007  push    rdi
0x180022008  push    r14
0x18002200a  push    r15
0x18002200c  mov     rbp, rsp
0x18002200f  sub     rsp, 20h
0x180022013  mov     rax, [rcx]
0x180022016  mov     r15, rdx
0x180022019  mov     rsi, rcx
0x18002201c  mov     [rbp+arg_10], 0
0x180022024  mov     rax, [rax+30h]
0x180022028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002202d  mov     r14d, eax
0x180022030  test    eax, eax
0x180022032  js      loc_180022299
0x180022038  mov     r8, r15
0x18002203b  mov     edx, 3
0x180022040  mov     rcx, rsi
0x180022043  call    ?NotifyListeners@WalletItemManager@Wallet@@QEAAXW4__MIDL___MIDL_itf_wallettypes_0000_0000_0013@@_K@Z; Wallet::WalletItemManager::NotifyListeners(__MIDL___MIDL_itf_wallettypes_0000_0000_0013,unsigned __int64)
0x180022048  lea     rbx, [rsi+68h]
0x18002204c  mov     rcx, rbx
0x18002204f  call    ?lock@?$OrderedLockBase@W4WalletLockOrder@@@@QEAAXXZ; OrderedLockBase<WalletLockOrder>::lock(void)
0x180022054  cmp     dword ptr [rsi+30h], 0
0x180022058  mov     [rbp+arg_0], 0
0x180022060  jnz     short loc_1800220C7
0x180022062  lea     rcx, [rbp+arg_0]
0x180022066  mov     r14d, 803A0005h
0x18002206c  call    ?_Delete@?$unique_ptr@VWalletStorageAttach@Wallet@@U?$default_delete@VWalletStorageAttach@Wallet@@@std@@@std@@AEAAXXZ; std::unique_ptr<Wallet::WalletStorageAttach>::_Delete(void)
0x180022071  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180022078  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x18002207f  mov     rax, [rax+8]
0x180022083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022088  mov     rcx, [rbx]
0x18002208b  mov     edi, eax
0x18002208d  mov     rax, [rcx]
0x180022090  mov     rcx, rbx
0x180022093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022098  cmp     eax, edi
0x18002209a  jz      short loc_18002209E
0x18002209c  int     2Ch; Windows NT - assertion failure
0x18002209e  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x1800220a5  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x1800220ac  mov     rax, [rax+10h]
0x1800220b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220b5  lea     rax, [rbx+8]
0x1800220b9  neg     rbx
0x1800220bc  sbb     rcx, rcx
0x1800220bf  and     rcx, rax
0x1800220c2  jmp     loc_180022293
0x1800220c7  mov     ecx, 10h; Size
0x1800220cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800220d1  test    rax, rax
0x1800220d4  jz      short loc_1800220E2
0x1800220d6  mov     rdx, [rsi+38h]; struct Wallet::IWalletStorage *
0x1800220da  mov     rcx, rax; this
0x1800220dd  call    ??0WalletStorageAttach@Wallet@@QEAA@PEAUIWalletStorage@1@@Z; Wallet::WalletStorageAttach::WalletStorageAttach(Wallet::IWalletStorage *)
0x1800220e2  lea     rdx, [rbp+arg_18]
0x1800220e6  mov     [rbp+arg_18], rax
0x1800220ea  lea     rcx, [rbp+arg_0]
0x1800220ee  call    ??4?$unique_ptr@VWalletStorageAttach@Wallet@@U?$default_delete@VWalletStorageAttach@Wallet@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Wallet::WalletStorageAttach>::operator=(std::unique_ptr<Wallet::WalletStorageAttach> &&)
0x1800220f3  lea     rcx, [rbp+arg_18]
0x1800220f7  call    ?_Delete@?$unique_ptr@VWalletStorageAttach@Wallet@@U?$default_delete@VWalletStorageAttach@Wallet@@@std@@@std@@AEAAXXZ; std::unique_ptr<Wallet::WalletStorageAttach>::_Delete(void)
0x1800220fc  cmp     [rbp+arg_0], 0
0x180022101  jnz     short loc_180022148
0x180022103  lea     rcx, [rbp+arg_0]
0x180022107  mov     r14d, 8007000Eh
0x18002210d  call    ?_Delete@?$unique_ptr@VWalletStorageAttach@Wallet@@U?$default_delete@VWalletStorageAttach@Wallet@@@std@@@std@@AEAAXXZ; std::unique_ptr<Wallet::WalletStorageAttach>::_Delete(void)
0x180022112  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180022119  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180022120  mov     rax, [rax+8]
0x180022124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022129  mov     rcx, [rbx]
0x18002212c  mov     edi, eax
0x18002212e  mov     rax, [rcx]
0x180022131  mov     rcx, rbx
0x180022134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022139  cmp     eax, edi
0x18002213b  jz      loc_18002209E
0x180022141  int     2Ch; Windows NT - assertion failure
0x180022143  jmp     loc_18002209E
0x180022148  mov     rcx, r15
0x18002214b  shr     rcx, 20h
0x18002214f  call    ?IsStandardItemType@Utils@Wallet@@YAHW4__MIDL___MIDL_itf_wallettypes_0000_0000_0001@@@Z; Wallet::Utils::IsStandardItemType(__MIDL___MIDL_itf_wallettypes_0000_0000_0001)
0x180022154  test    eax, eax
0x180022156  jz      loc_1800221E1
0x18002215c  mov     rax, [rsi]
0x18002215f  lea     rcx, [rbp+arg_10]
0x180022163  mov     rdi, [rax+40h]
0x180022167  call    ??$pointerTo@UIWalletNotification@@@ce@@YAPEAPEAUIWalletNotification@@AEAV?$CComPtr@UIWalletNotification@@@ATL@@@Z; ce::pointerTo<IWalletNotification>(ATL::CComPtr<IWalletNotification> &)
0x18002216c  mov     r8, rax
0x18002216f  mov     rdx, r15
0x180022172  mov     rax, rdi
0x180022175  mov     rcx, rsi
0x180022178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002217d  mov     r14d, eax
0x180022180  test    eax, eax
0x180022182  jns     short loc_1800221C3
0x180022184  lea     rcx, [rbp+arg_0]
0x180022188  call    ?_Delete@?$unique_ptr@VWalletStorageAttach@Wallet@@U?$default_delete@VWalletStorageAttach@Wallet@@@std@@@std@@AEAAXXZ; std::unique_ptr<Wallet::WalletStorageAttach>::_Delete(void)
0x18002218d  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180022194  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x18002219b  mov     rax, [rax+8]
0x18002219f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221a4  mov     rcx, [rbx]
0x1800221a7  mov     edi, eax
0x1800221a9  mov     rax, [rcx]
0x1800221ac  mov     rcx, rbx
0x1800221af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221b4  cmp     eax, edi
0x1800221b6  jz      loc_18002209E
0x1800221bc  int     2Ch; Windows NT - assertion failure
0x1800221be  jmp     loc_18002209E
0x1800221c3  xor     edi, edi
0x1800221c5  mov     rdx, [rbp+arg_10]
0x1800221c9  lea     rcx, ?sc_rgImagePropertyTypes@WalletItem@Wallet@@2QBW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@B; __MIDL___MIDL_itf_wallettypes_0000_0000_0010 const near * const Wallet::WalletItem::sc_rgImagePropertyTypes
0x1800221d0  mov     ecx, [rcx+rdi*4]
0x1800221d3  call    ?DeleteItemImage@Utils@Wallet@@YAJW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEAUIWalletItem@@@Z; Wallet::Utils::DeleteItemImage(__MIDL___MIDL_itf_wallettypes_0000_0000_0010,IWalletItem *)
0x1800221d8  inc     rdi
0x1800221db  cmp     rdi, 9
0x1800221df  jnz     short loc_1800221C5
0x1800221e1  mov     rcx, [rsi+38h]
0x1800221e5  mov     rdx, r15
0x1800221e8  mov     rax, [rcx]
0x1800221eb  mov     rax, [rax+48h]
0x1800221ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221f4  lea     rcx, [rbp+arg_0]
0x1800221f8  mov     r14d, eax
0x1800221fb  test    eax, eax
0x1800221fd  jns     short loc_18002223A
0x1800221ff  call    ?_Delete@?$unique_ptr@VWalletStorageAttach@Wallet@@U?$default_delete@VWalletStorageAttach@Wallet@@@std@@@std@@AEAAXXZ; std::unique_ptr<Wallet::WalletStorageAttach>::_Delete(void)
0x180022204  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x18002220b  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180022212  mov     rax, [rax+8]
0x180022216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002221b  mov     rcx, [rbx]
0x18002221e  mov     edi, eax
0x180022220  mov     rax, [rcx]
0x180022223  mov     rcx, rbx
0x180022226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002222b  cmp     eax, edi
0x18002222d  jz      loc_18002209E
0x180022233  int     2Ch; Windows NT - assertion failure
0x180022235  jmp     loc_18002209E
0x18002223a  xor     r14d, r14d
0x18002223d  call    ?_Delete@?$unique_ptr@VWalletStorageAttach@Wallet@@U?$default_delete@VWalletStorageAttach@Wallet@@@std@@@std@@AEAAXXZ; std::unique_ptr<Wallet::WalletStorageAttach>::_Delete(void)
0x180022242  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180022249  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180022250  mov     rax, [rax+8]
0x180022254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022259  mov     rcx, [rbx]
0x18002225c  mov     edi, eax
0x18002225e  mov     rax, [rcx]
0x180022261  mov     rcx, rbx
0x180022264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022269  cmp     eax, edi
0x18002226b  jz      short loc_18002226F
0x18002226d  int     2Ch; Windows NT - assertion failure
0x18002226f  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180022276  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x18002227d  mov     rax, [rax+10h]
0x180022281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022286  lea     rdx, [rbx+8]
0x18002228a  neg     rbx
0x18002228d  sbb     rcx, rcx
0x180022290  and     rcx, rdx; lpCriticalSection
0x180022293  call    cs:__imp_LeaveCriticalSection
0x180022299  lea     rcx, [rbp+arg_10]
0x18002229d  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x1800222a2  mov     rbx, [rsp+20h+arg_8]
0x1800222a7  mov     eax, r14d
0x1800222aa  add     rsp, 20h
0x1800222ae  pop     r15
0x1800222b0  pop     r14
0x1800222b2  pop     rdi
0x1800222b3  pop     rsi
0x1800222b4  pop     rbp
0x1800222b5  retn
```
