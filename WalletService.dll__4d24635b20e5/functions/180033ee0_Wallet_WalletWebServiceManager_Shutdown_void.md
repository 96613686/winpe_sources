# Wallet::WalletWebServiceManager::Shutdown(void)

- ea: `0x180033ee0`
- end: `0x180033fbd`
- name: `?Shutdown@WalletWebServiceManager@Wallet@@QEAAJXZ`
- size: `221`
- prototype: `__int64 __fastcall(Wallet::WalletWebServiceManager *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017680`
- `0x180033440`

## callees

- `0x180003b40`
- `0x180016e78`
- `0x180033ee0`
- `0x180034e2c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033fa5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033fa5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180033f1c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180033f1c`

## pseudocode

```c
__int64 __fastcall Wallet::WalletWebServiceManager::Shutdown(Wallet::WalletWebServiceManager *this)
{
  unsigned int (__fastcall ***v1)(_QWORD); // rdi
  struct _TP_WORK *v3; // rcx
  Wallet::WalletWebService *v4; // rcx
  int v5; // ebx

  v1 = (unsigned int (__fastcall ***)(_QWORD))((char *)this + 56);
  OrderedLockBase<enum WalletLockOrder>::lock((char *)this + 56);
  if ( *((_DWORD *)this + 4) )
  {
    *((_DWORD *)this + 4) = 0;
    v3 = (struct _TP_WORK *)*((_QWORD *)this + 15);
    *((_QWORD *)this + 15) = 0;
    if ( v3 )
      CloseThreadpoolWork(v3);
    v4 = (Wallet::WalletWebService *)*((_QWORD *)this + 13);
    if ( v4 )
    {
      Wallet::WalletWebService::Shutdown(v4);
      if ( *((_QWORD *)this + 13) )
        ATL::AtlComPtrAssign((struct IUnknown **)this + 13, 0);
    }
    if ( *((_QWORD *)this + 3) )
      ATL::AtlComPtrAssign((struct IUnknown **)this + 3, 0);
  }
  v5 = ((__int64 (__fastcall *)(void ***))g_LockOrderManagerImp[1])(&g_LockOrderManagerImp);
  if ( (**v1)(v1) != v5 )
    __int2c();
  ((void (__fastcall *)(void ***))g_LockOrderManagerImp[2])(&g_LockOrderManagerImp);
  LeaveCriticalSection((LPCRITICAL_SECTION)((unsigned __int64)(v1 + 1) & -(__int64)(v1 != 0)));
  return 0;
}

```

## disassembly

```asm
0x180033ee0  mov     [rsp+arg_0], rbx
0x180033ee5  mov     [rsp+arg_8], rsi
0x180033eea  push    rdi
0x180033eeb  sub     rsp, 20h
0x180033eef  lea     rdi, [rcx+38h]
0x180033ef3  mov     rbx, rcx
0x180033ef6  mov     rcx, rdi
0x180033ef9  call    ?lock@?$OrderedLockBase@W4WalletLockOrder@@@@QEAAXXZ; OrderedLockBase<WalletLockOrder>::lock(void)
0x180033efe  cmp     dword ptr [rbx+10h], 0
0x180033f02  jz      short loc_180033F54
0x180033f04  mov     dword ptr [rbx+10h], 0
0x180033f0b  mov     rcx, [rbx+78h]; pwk
0x180033f0f  mov     qword ptr [rbx+78h], 0
0x180033f17  test    rcx, rcx
0x180033f1a  jz      short loc_180033F22
0x180033f1c  call    cs:__imp_CloseThreadpoolWork
0x180033f22  lea     rsi, [rbx+68h]
0x180033f26  mov     rcx, [rsi]; this
0x180033f29  test    rcx, rcx
0x180033f2c  jz      short loc_180033F43
0x180033f2e  call    ?Shutdown@WalletWebService@Wallet@@QEAAJXZ; Wallet::WalletWebService::Shutdown(void)
0x180033f33  cmp     qword ptr [rsi], 0
0x180033f37  jz      short loc_180033F43
0x180033f39  xor     edx, edx; struct IUnknown *
0x180033f3b  mov     rcx, rsi; struct IUnknown **
0x180033f3e  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180033f43  lea     rcx, [rbx+18h]; struct IUnknown **
0x180033f47  cmp     qword ptr [rcx], 0
0x180033f4b  jz      short loc_180033F54
0x180033f4d  xor     edx, edx; struct IUnknown *
0x180033f4f  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180033f54  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180033f5b  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180033f62  mov     rax, [rax+8]
0x180033f66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f6b  mov     rcx, [rdi]
0x180033f6e  mov     ebx, eax
0x180033f70  mov     rax, [rcx]
0x180033f73  mov     rcx, rdi
0x180033f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f7b  cmp     eax, ebx
0x180033f7d  jz      short loc_180033F81
0x180033f7f  int     2Ch; Windows NT - assertion failure
0x180033f81  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180033f88  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180033f8f  mov     rax, [rax+10h]
0x180033f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033f98  lea     rax, [rdi+8]
0x180033f9c  neg     rdi
0x180033f9f  sbb     rcx, rcx
0x180033fa2  and     rcx, rax; lpCriticalSection
0x180033fa5  call    cs:__imp_LeaveCriticalSection
0x180033fab  mov     rbx, [rsp+28h+arg_0]
0x180033fb0  xor     eax, eax
0x180033fb2  mov     rsi, [rsp+28h+arg_8]
0x180033fb7  add     rsp, 20h
0x180033fbb  pop     rdi
0x180033fbc  retn
```
