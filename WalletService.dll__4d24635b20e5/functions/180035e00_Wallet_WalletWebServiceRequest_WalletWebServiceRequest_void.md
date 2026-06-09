# Wallet::WalletWebServiceRequest::~WalletWebServiceRequest(void)

- ea: `0x180035e00`
- end: `0x180035e70`
- name: `??1WalletWebServiceRequest@Wallet@@MEAA@XZ`
- size: `112`
- prototype: `void __fastcall(Wallet::WalletWebServiceRequest *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180035dc0`
- `0x180035ec0`

## callees

- `0x180003ae4`
- `0x180006034`
- `0x180013f78`
- `0x180035e00`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180035e1f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180035e1f`

## pseudocode

```c
void __fastcall Wallet::WalletWebServiceRequest::~WalletWebServiceRequest(Wallet::WalletWebServiceRequest *this)
{
  struct _TP_WORK *v2; // rcx

  *(_QWORD *)this = &Wallet::WalletWebServiceRequest::`vftable';
  v2 = (struct _TP_WORK *)*((_QWORD *)this + 17);
  if ( v2 )
  {
    CloseThreadpoolWork(v2);
    *((_QWORD *)this + 17) = 0;
  }
  DecrementServerReferenceCount();
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)this + 15);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((char *)this + 80);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)this + 9);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((char *)this + 40);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)this + 4);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)this + 3);
}

```

## disassembly

```asm
0x180035e00  push    rbx
0x180035e02  sub     rsp, 20h
0x180035e06  lea     rax, ??_7WalletWebServiceRequest@Wallet@@6B@; const Wallet::WalletWebServiceRequest::`vftable'
0x180035e0d  mov     rbx, rcx
0x180035e10  mov     [rcx], rax
0x180035e13  mov     rcx, [rcx+88h]; pwk
0x180035e1a  test    rcx, rcx
0x180035e1d  jz      short loc_180035E30
0x180035e1f  call    cs:__imp_CloseThreadpoolWork
0x180035e25  mov     qword ptr [rbx+88h], 0
0x180035e30  call    ?DecrementServerReferenceCount@@YAJXZ; DecrementServerReferenceCount(void)
0x180035e35  lea     rcx, [rbx+78h]
0x180035e39  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180035e3e  lea     rcx, [rbx+50h]
0x180035e42  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180035e47  lea     rcx, [rbx+48h]
0x180035e4b  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180035e50  lea     rcx, [rbx+28h]
0x180035e54  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180035e59  lea     rcx, [rbx+20h]
0x180035e5d  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180035e62  lea     rcx, [rbx+18h]
0x180035e66  add     rsp, 20h
0x180035e6a  pop     rbx
0x180035e6b  jmp     ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
```
