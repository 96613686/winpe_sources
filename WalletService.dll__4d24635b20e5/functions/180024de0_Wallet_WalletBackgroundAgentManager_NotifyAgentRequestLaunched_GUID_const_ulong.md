# Wallet::WalletBackgroundAgentManager::NotifyAgentRequestLaunched(_GUID const *,ulong)

- ea: `0x180024de0`
- end: `0x180024f76`
- name: `?NotifyAgentRequestLaunched@WalletBackgroundAgentManager@Wallet@@UEAAJPEBU_GUID@@K@Z`
- size: `406`
- prototype: `__int64 __fastcall(Wallet::WalletBackgroundAgentManager *__hidden this, const struct _GUID *, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003ae4`
- `0x180008cc0`
- `0x18000d928`
- `0x180014328`
- `0x180016e78`
- `0x18001fea8`
- `0x180024de0`
- `0x180025164`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024e74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024ed4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024e74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024ed4`

## string_xrefs

- `0x180024f36`: `Wallet::WalletBackgroundAgentManager::NotifyAgentRequestLaunched`

## pseudocode

```c
__int64 __fastcall Wallet::WalletBackgroundAgentManager::NotifyAgentRequestLaunched(
        Wallet::WalletBackgroundAgentManager *this,
        const struct _GUID *a2,
        unsigned int a3)
{
  unsigned int (__fastcall ***v6)(char *); // rdi
  bool v7; // zf
  __int64 (__fastcall *v8)(void ***); // rax
  unsigned int v9; // ebp
  int v10; // ebx
  int v12; // ebx
  __int64 *i; // rbx
  const void *v14; // rdi
  int v15; // eax
  __int64 v16[11]; // [rsp+40h] [rbp-58h] BYREF
  const void *v17; // [rsp+A0h] [rbp+8h] BYREF

  utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::vector<unsigned __int64,utl::allocator<unsigned __int64>>(v16);
  v6 = (unsigned int (__fastcall ***)(char *))((char *)this + 56);
  OrderedLockBase<enum WalletLockOrder>::lock((char *)this + 56);
  v7 = utl::vector<ATL::CComPtr<IWalletBackgroundAgentListener>,utl::allocator<ATL::CComPtr<IWalletBackgroundAgentListener>>>::assign(
         v16,
         (_QWORD *)this + 4) == 0;
  v8 = (__int64 (__fastcall *)(void ***))g_LockOrderManagerImp[1];
  if ( v7 )
  {
    v9 = -2147024882;
    v10 = v8(&g_LockOrderManagerImp);
    if ( (**v6)((char *)this + 56) != v10 )
      __int2c();
    ((void (__fastcall *)(void ***))g_LockOrderManagerImp[2])(&g_LockOrderManagerImp);
    LeaveCriticalSection((LPCRITICAL_SECTION)(((unsigned __int64)this + 64) & -(__int64)(v6 != 0)));
  }
  else
  {
    v9 = 0;
    v12 = v8(&g_LockOrderManagerImp);
    if ( (**v6)((char *)this + 56) != v12 )
      __int2c();
    ((void (__fastcall *)(void ***))g_LockOrderManagerImp[2])(&g_LockOrderManagerImp);
    LeaveCriticalSection((LPCRITICAL_SECTION)(((unsigned __int64)this + 64) & -(__int64)(v6 != 0)));
    for ( i = (__int64 *)v16[0]; i != (__int64 *)v16[1]; ++i )
    {
      ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(&v17, *i);
      v14 = v17;
      if ( v17
        && (*(unsigned int (__fastcall **)(const void *, const struct _GUID *, _QWORD))(*(_QWORD *)v17 + 24LL))(
             v17,
             a2,
             a3) == -2147023174 )
      {
        v15 = (*(__int64 (__fastcall **)(Wallet::WalletBackgroundAgentManager *, const void *))(*(_QWORD *)this + 56LL))(
                this,
                v14);
        wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy(
          5,
          "Wallet::WalletBackgroundAgentManager::NotifyAgentRequestLaunched",
          137,
          this,
          "HRESULT was 0x%x when removing disconnected listener %p",
          v15,
          v14);
      }
      ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&v17);
    }
  }
  utl::vector<ATL::CComPtr<IWalletBackgroundAgentListener>,utl::allocator<ATL::CComPtr<IWalletBackgroundAgentListener>>>::_Uninit((__int64)v16);
  return v9;
}

```

## disassembly

```asm
0x180024de0  push    rbx
0x180024de2  push    rbp
0x180024de3  push    rsi
0x180024de4  push    rdi
0x180024de5  push    r14
0x180024de7  push    r15
0x180024de9  sub     rsp, 68h
0x180024ded  mov     rsi, rcx
0x180024df0  mov     r14d, r8d
0x180024df3  lea     rcx, [rsp+98h+var_58]
0x180024df8  mov     r15, rdx
0x180024dfb  call    ??0?$vector@_KV?$allocator@_K@utl@@@utl@@QEAA@XZ; utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::vector<unsigned __int64,utl::allocator<unsigned __int64>>(void)
0x180024e00  lea     rdi, [rsi+38h]
0x180024e04  mov     rcx, rdi
0x180024e07  call    ?lock@?$OrderedLockBase@W4WalletLockOrder@@@@QEAAXXZ; OrderedLockBase<WalletLockOrder>::lock(void)
0x180024e0c  lea     rdx, [rsi+20h]
0x180024e10  lea     rcx, [rsp+98h+var_58]
0x180024e15  call    ?assign@?$vector@V?$CComPtr@UIWalletBackgroundAgentListener@@@ATL@@V?$allocator@V?$CComPtr@UIWalletBackgroundAgentListener@@@ATL@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<ATL::CComPtr<IWalletBackgroundAgentListener>,utl::allocator<ATL::CComPtr<IWalletBackgroundAgentListener>>>::assign(utl::vector<ATL::CComPtr<IWalletBackgroundAgentListener>,utl::allocator<ATL::CComPtr<IWalletBackgroundAgentListener>>> const &)
0x180024e1a  test    al, al
0x180024e1c  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180024e23  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180024e2a  mov     rax, [rax+8]
0x180024e2e  jnz     short loc_180024E93
0x180024e30  mov     ebp, 8007000Eh
0x180024e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e3a  mov     rcx, [rdi]
0x180024e3d  mov     ebx, eax
0x180024e3f  mov     rax, [rcx]
0x180024e42  mov     rcx, rdi
0x180024e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e4a  cmp     eax, ebx
0x180024e4c  jz      short loc_180024E50
0x180024e4e  int     2Ch; Windows NT - assertion failure
0x180024e50  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180024e57  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180024e5e  mov     rax, [rax+10h]
0x180024e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e67  lea     rax, [rdi+8]
0x180024e6b  neg     rdi
0x180024e6e  sbb     rcx, rcx
0x180024e71  and     rcx, rax; lpCriticalSection
0x180024e74  call    cs:__imp_LeaveCriticalSection
0x180024e7a  lea     rcx, [rsp+98h+var_58]
0x180024e7f  call    ?_Uninit@?$vector@V?$CComPtr@UIWalletBackgroundAgentListener@@@ATL@@V?$allocator@V?$CComPtr@UIWalletBackgroundAgentListener@@@ATL@@@utl@@@utl@@AEAAXXZ; utl::vector<ATL::CComPtr<IWalletBackgroundAgentListener>,utl::allocator<ATL::CComPtr<IWalletBackgroundAgentListener>>>::_Uninit(void)
0x180024e84  mov     eax, ebp
0x180024e86  add     rsp, 68h
0x180024e8a  pop     r15
0x180024e8c  pop     r14
0x180024e8e  pop     rdi
0x180024e8f  pop     rsi
0x180024e90  pop     rbp
0x180024e91  pop     rbx
0x180024e92  retn
0x180024e93  xor     ebp, ebp
0x180024e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e9a  mov     rcx, [rdi]
0x180024e9d  mov     ebx, eax
0x180024e9f  mov     rax, [rcx]
0x180024ea2  mov     rcx, rdi
0x180024ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024eaa  cmp     eax, ebx
0x180024eac  jz      short loc_180024EB0
0x180024eae  int     2Ch; Windows NT - assertion failure
0x180024eb0  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180024eb7  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180024ebe  mov     rax, [rax+10h]
0x180024ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ec7  lea     rax, [rdi+8]
0x180024ecb  neg     rdi
0x180024ece  sbb     rcx, rcx
0x180024ed1  and     rcx, rax; lpCriticalSection
0x180024ed4  call    cs:__imp_LeaveCriticalSection
0x180024eda  mov     rbx, [rsp+98h+var_58]
0x180024edf  cmp     rbx, [rsp+98h+var_50]
0x180024ee4  jz      short loc_180024E7A
0x180024ee6  mov     rdx, [rbx]
0x180024ee9  lea     rcx, [rsp+98h+arg_0]
0x180024ef1  call    ??0?$CComPtrBase@UIWalletBackgroundAgentListener@@@ATL@@IEAA@PEAUIWalletBackgroundAgentListener@@@Z; ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(IWalletBackgroundAgentListener *)
0x180024ef6  mov     rdi, [rsp+98h+arg_0]
0x180024efe  test    rdi, rdi
0x180024f01  jz      short loc_180024F60
0x180024f03  mov     rax, [rdi]
0x180024f06  mov     r8d, r14d
0x180024f09  mov     rdx, r15
0x180024f0c  mov     rcx, rdi
0x180024f0f  mov     rax, [rax+18h]
0x180024f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f18  cmp     eax, 800706BAh
0x180024f1d  jnz     short loc_180024F60
0x180024f1f  mov     rax, [rsi]
0x180024f22  mov     rdx, rdi
0x180024f25  mov     rcx, rsi
0x180024f28  mov     rax, [rax+38h]
0x180024f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f31  mov     [rsp+98h+var_68], rdi
0x180024f36  lea     rdx, aWalletWalletba; "Wallet::WalletBackgroundAgentManager::N"...
0x180024f3d  mov     [rsp+98h+var_70], eax
0x180024f41  mov     r9, rsi
0x180024f44  lea     rax, aHresultWas0xXW; "HRESULT was 0x%x when removing disconne"...
0x180024f4b  mov     r8d, 89h
0x180024f51  mov     ecx, 5
0x180024f56  mov     [rsp+98h+var_78], rax
0x180024f5b  call    ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180024f60  lea     rcx, [rsp+98h+arg_0]
0x180024f68  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180024f6d  add     rbx, 8
0x180024f71  jmp     loc_180024EDF
```
