# Wallet::WalletWebServiceManager::Refresh(IWalletWebServiceManagerCallback *,unsigned __int64,int)

- ea: `0x180033a20`
- end: `0x180033c10`
- name: `?Refresh@WalletWebServiceManager@Wallet@@UEAAJPEAUIWalletWebServiceManagerCallback@@_KH@Z`
- size: `496`
- prototype: `int(Wallet::WalletWebServiceManager *__hidden this, struct IWalletWebServiceManagerCallback *, unsigned __int64, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002214`
- `0x180003ae4`
- `0x180003b40`
- `0x180014328`
- `0x180016e78`
- `0x180033420`
- `0x180033540`
- `0x180033a20`
- `0x1800342a8`
- `0x180038f74`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033b1e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033b1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033b9b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180033b6c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180033b6c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180033b83`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180033b83`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180033bbb`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180033bbb`

## pseudocode

```c
__int64 __fastcall Wallet::WalletWebServiceManager::Refresh(
        Wallet::WalletWebServiceManager *this,
        struct IWalletWebServiceManagerCallback *a2,
        __int64 a3,
        unsigned int a4)
{
  unsigned int v4; // edi
  _QWORD *v9; // rbx
  unsigned int v10; // edx
  int WalletItem; // eax
  unsigned int (__fastcall ***v12)(_QWORD); // r15
  int v13; // ebx
  struct _TP_WORK *v14; // rdx
  PTP_WORK ThreadpoolWork; // rax
  struct _TP_WORK *v16; // rcx
  struct _TP_WORK *v17; // rcx
  signed int LastError; // eax
  __int64 v20[3]; // [rsp+20h] [rbp-18h] BYREF
  struct _TP_WORK *v21; // [rsp+90h] [rbp+58h] BYREF

  v4 = 0;
  v20[0] = 0;
  if ( a3 )
  {
    v9 = 0;
    if ( (int)Wallet::Utils::GetWalletItem(a3, v20) >= 0 )
    {
      v21 = a2;
      if ( a2 )
        (*(void (__fastcall **)(struct IWalletWebServiceManagerCallback *))(*(_QWORD *)a2 + 8LL))(a2);
      WalletItem = Wallet::WalletWebService::BeginGetWalletItem(*((_QWORD *)this + 13), v20, a4, (__int64)&v21);
      if ( WalletItem >= 0 )
      {
        ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&v21);
        goto LABEL_29;
      }
      v4 = WalletItem;
      ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&v21);
    }
  }
  else
  {
    if ( a2 )
    {
      v12 = (unsigned int (__fastcall ***)(_QWORD))((char *)this + 56);
      OrderedLockBase<enum WalletLockOrder>::lock((char *)this + 56);
      if ( *((struct IWalletWebServiceManagerCallback **)this + 14) != a2 )
        ATL::AtlComPtrAssign((struct IUnknown **)this + 14, (struct IUnknown *)a2);
      v13 = ((__int64 (__fastcall *)(void ***))g_LockOrderManagerImp[1])(&g_LockOrderManagerImp);
      if ( (**v12)(v12) != v13 )
        __int2c();
      ((void (__fastcall *)(void ***))g_LockOrderManagerImp[2])(&g_LockOrderManagerImp);
      LeaveCriticalSection((LPCRITICAL_SECTION)((unsigned __int64)(v12 + 1) & -(__int64)(v12 != 0)));
    }
    v9 = operator new(0x10u);
    if ( v9 )
    {
      ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(&v21, (__int64)this);
      v14 = v21;
      *(_DWORD *)v9 = a4;
      ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(
        v9 + 1,
        (__int64)v14);
      ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&v21);
      ThreadpoolWork = CreateThreadpoolWork(Wallet::WalletWebServiceManager::RefreshAllCallback, v9, 0);
      v16 = (struct _TP_WORK *)*((_QWORD *)this + 15);
      v21 = 0;
      *((_QWORD *)this + 15) = ThreadpoolWork;
      if ( v16 )
        CloseThreadpoolWork(v16);
      tlx::unique_any<tlx::handle_traits<_TP_WORK *,void (*)(_TP_WORK *),&void CloseThreadpoolWork(_TP_WORK *),0>>::~unique_any<tlx::handle_traits<_TP_WORK *,void (*)(_TP_WORK *),&void CloseThreadpoolWork(_TP_WORK *),0>>(&v21);
      v17 = (struct _TP_WORK *)*((_QWORD *)this + 15);
      if ( v17 )
      {
        SubmitThreadpoolWork(v17);
        goto LABEL_29;
      }
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v4 = -2143748092;
      }
    }
    else
    {
      v4 = -2147024882;
      v9 = 0;
    }
  }
  if ( a2 )
    (*(void (__fastcall **)(struct IWalletWebServiceManagerCallback *, _QWORD, __int64))(*(_QWORD *)a2 + 24LL))(
      a2,
      v4,
      a3);
  if ( (v4 & 0x80000000) != 0 && v9 )
    RefreshData::`scalar deleting destructor'((RefreshData *)v9, v10);
LABEL_29:
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(v20);
  return v4;
}

```

## disassembly

```asm
0x180033a20  push    rbp
0x180033a22  push    rbx
0x180033a23  push    rsi
0x180033a24  push    rdi
0x180033a25  push    r12
0x180033a27  push    r13
0x180033a29  push    r14
0x180033a2b  push    r15
0x180033a2d  mov     rbp, rsp
0x180033a30  sub     rsp, 38h
0x180033a34  xor     edi, edi
0x180033a36  mov     r13d, r9d
0x180033a39  mov     [rbp+var_18], rdi
0x180033a3d  mov     r12, r8
0x180033a40  mov     rsi, rdx
0x180033a43  mov     r14, rcx
0x180033a46  test    r8, r8
0x180033a49  jz      short loc_180033AAB
0x180033a4b  lea     rdx, [rbp+var_18]
0x180033a4f  mov     rcx, r8
0x180033a52  xor     ebx, ebx
0x180033a54  call    ?GetWalletItem@Utils@Wallet@@YAJ_KAEAV?$CComPtr@UIWalletItem@@@ATL@@@Z; Wallet::Utils::GetWalletItem(unsigned __int64,ATL::CComPtr<IWalletItem> &)
0x180033a59  test    eax, eax
0x180033a5b  js      loc_180033BCA
0x180033a61  mov     [rbp+arg_10], rsi
0x180033a65  test    rsi, rsi
0x180033a68  jz      short loc_180033A79
0x180033a6a  mov     rax, [rsi]
0x180033a6d  mov     rcx, rsi
0x180033a70  mov     rax, [rax+8]
0x180033a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a79  mov     rcx, [r14+68h]
0x180033a7d  lea     r9, [rbp+arg_10]
0x180033a81  mov     r8d, r13d
0x180033a84  lea     rdx, [rbp+var_18]
0x180033a88  call    ?BeginGetWalletItem@WalletWebService@Wallet@@QEAAJAEAV?$CComPtr@UIWalletItem@@@ATL@@HAEAV?$CComPtr@UIWalletWebServiceManagerCallback@@@4@@Z; Wallet::WalletWebService::BeginGetWalletItem(ATL::CComPtr<IWalletItem> &,int,ATL::CComPtr<IWalletWebServiceManagerCallback> &)
0x180033a8d  lea     rcx, [rbp+arg_10]
0x180033a91  test    eax, eax
0x180033a93  jns     short loc_180033AA1
0x180033a95  mov     edi, eax
0x180033a97  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180033a9c  jmp     loc_180033BCA
0x180033aa1  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180033aa6  jmp     loc_180033BF4
0x180033aab  test    rsi, rsi
0x180033aae  jz      short loc_180033B24
0x180033ab0  lea     r15, [rcx+38h]
0x180033ab4  mov     rcx, r15
0x180033ab7  call    ?lock@?$OrderedLockBase@W4WalletLockOrder@@@@QEAAXXZ; OrderedLockBase<WalletLockOrder>::lock(void)
0x180033abc  lea     rcx, [r14+70h]; struct IUnknown **
0x180033ac0  cmp     [rcx], rsi
0x180033ac3  jz      short loc_180033ACD
0x180033ac5  mov     rdx, rsi; struct IUnknown *
0x180033ac8  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180033acd  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180033ad4  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180033adb  mov     rax, [rax+8]
0x180033adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ae4  mov     rcx, [r15]
0x180033ae7  mov     ebx, eax
0x180033ae9  mov     rax, [rcx]
0x180033aec  mov     rcx, r15
0x180033aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033af4  cmp     eax, ebx
0x180033af6  jz      short loc_180033AFA
0x180033af8  int     2Ch; Windows NT - assertion failure
0x180033afa  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180033b01  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180033b08  mov     rax, [rax+10h]
0x180033b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b11  lea     rax, [r15+8]
0x180033b15  neg     r15
0x180033b18  sbb     rcx, rcx
0x180033b1b  and     rcx, rax; lpCriticalSection
0x180033b1e  call    cs:__imp_LeaveCriticalSection
0x180033b24  mov     ecx, 10h; Size
0x180033b29  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033b2e  mov     rbx, rax
0x180033b31  test    rax, rax
0x180033b34  jz      loc_180033BC3
0x180033b3a  mov     rdx, r14
0x180033b3d  lea     rcx, [rbp+arg_10]
0x180033b41  call    ??0?$CComPtrBase@UIWalletBackgroundAgentListener@@@ATL@@IEAA@PEAUIWalletBackgroundAgentListener@@@Z; ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(IWalletBackgroundAgentListener *)
0x180033b46  mov     rdx, [rbp+arg_10]
0x180033b4a  lea     rcx, [rbx+8]
0x180033b4e  mov     [rbx], r13d
0x180033b51  call    ??0?$CComPtrBase@UIWalletBackgroundAgentListener@@@ATL@@IEAA@PEAUIWalletBackgroundAgentListener@@@Z; ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(IWalletBackgroundAgentListener *)
0x180033b56  lea     rcx, [rbp+arg_10]
0x180033b5a  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180033b5f  xor     r8d, r8d; pcbe
0x180033b62  lea     rcx, ?RefreshAllCallback@WalletWebServiceManager@Wallet@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180033b69  mov     rdx, rbx; pv
0x180033b6c  call    cs:__imp_CreateThreadpoolWork
0x180033b72  mov     rcx, [r14+78h]; pwk
0x180033b76  mov     [rbp+arg_10], rdi
0x180033b7a  mov     [r14+78h], rax
0x180033b7e  test    rcx, rcx
0x180033b81  jz      short loc_180033B89
0x180033b83  call    cs:__imp_CloseThreadpoolWork
0x180033b89  lea     rcx, [rbp+arg_10]
0x180033b8d  call    ??1?$unique_any@U?$handle_traits@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?CloseThreadpoolWork@@YAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<_TP_WORK *,void (*)(_TP_WORK *),&CloseThreadpoolWork(_TP_WORK *),0>>::~unique_any<tlx::handle_traits<_TP_WORK *,void (*)(_TP_WORK *),&CloseThreadpoolWork(_TP_WORK *),0>>(void)
0x180033b92  mov     rcx, [r14+78h]; pwk
0x180033b96  test    rcx, rcx
0x180033b99  jnz     short loc_180033BBB
0x180033b9b  call    cs:__imp_GetLastError
0x180033ba1  mov     edi, eax
0x180033ba3  test    eax, eax
0x180033ba5  jz      short loc_180033BB4
0x180033ba7  jle     short loc_180033BCA
0x180033ba9  movzx   edi, ax
0x180033bac  or      edi, 80070000h
0x180033bb2  jmp     short loc_180033BCA
0x180033bb4  mov     edi, 80390004h
0x180033bb9  jmp     short loc_180033BCA
0x180033bbb  call    cs:__imp_SubmitThreadpoolWork
0x180033bc1  jmp     short loc_180033BF4
0x180033bc3  mov     edi, 8007000Eh
0x180033bc8  xor     ebx, ebx
0x180033bca  test    rsi, rsi
0x180033bcd  jz      short loc_180033BE3
0x180033bcf  mov     rax, [rsi]
0x180033bd2  mov     r8, r12
0x180033bd5  mov     edx, edi
0x180033bd7  mov     rcx, rsi
0x180033bda  mov     rax, [rax+18h]
0x180033bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033be3  test    edi, edi
0x180033be5  jns     short loc_180033BF4
0x180033be7  test    rbx, rbx
0x180033bea  jz      short loc_180033BF4
0x180033bec  mov     rcx, rbx; this
0x180033bef  call    ??_GRefreshData@@QEAAPEAXI@Z; RefreshData::`scalar deleting destructor'(uint)
0x180033bf4  lea     rcx, [rbp+var_18]
0x180033bf8  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180033bfd  mov     eax, edi
0x180033bff  add     rsp, 38h
0x180033c03  pop     r15
0x180033c05  pop     r14
0x180033c07  pop     r13
0x180033c09  pop     r12
0x180033c0b  pop     rdi
0x180033c0c  pop     rsi
0x180033c0d  pop     rbx
0x180033c0e  pop     rbp
0x180033c0f  retn
```
