# Wallet::WalletBackgroundAgentManager::NotifyAgentRequestCompleted(_GUID const *,ulong,long)

- ea: `0x180024bf0`
- end: `0x180024dcd`
- name: `?NotifyAgentRequestCompleted@WalletBackgroundAgentManager@Wallet@@UEAAJPEBU_GUID@@KJ@Z`
- size: `477`
- prototype: `__int64 __fastcall(Wallet::WalletBackgroundAgentManager *__hidden this, const struct _GUID *, unsigned int, int)`
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
- `0x180024bf0`
- `0x180025164`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024c9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024ce6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024c9c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024ce6`

## string_xrefs

- `0x180024d4f`: `Wallet::WalletBackgroundAgentManager::NotifyAgentRequestCompleted`

## pseudocode

```c
__int64 __fastcall Wallet::WalletBackgroundAgentManager::NotifyAgentRequestCompleted(
        Wallet::WalletBackgroundAgentManager *this,
        const struct _GUID *a2,
        unsigned int a3,
        unsigned int a4)
{
  unsigned int v4; // ebp
  unsigned int (__fastcall ***v9)(char *); // rdi
  bool v10; // zf
  __int64 (__fastcall *v11)(void ***); // rax
  int v12; // ebx
  int v13; // ebx
  __int64 *i; // rbx
  const void *v15; // rdi
  int v16; // eax
  int v17; // eax
  __int64 v19[4]; // [rsp+40h] [rbp-48h] BYREF
  const void *v20; // [rsp+90h] [rbp+8h] BYREF

  v4 = 0;
  if ( *((_QWORD *)this + 2) )
  {
    utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::vector<unsigned __int64,utl::allocator<unsigned __int64>>(v19);
    v9 = (unsigned int (__fastcall ***)(char *))((char *)this + 56);
    OrderedLockBase<enum WalletLockOrder>::lock((char *)this + 56);
    v10 = utl::vector<ATL::CComPtr<IWalletBackgroundAgentListener>,utl::allocator<ATL::CComPtr<IWalletBackgroundAgentListener>>>::assign(
            v19,
            (_QWORD *)this + 4) == 0;
    v11 = (__int64 (__fastcall *)(void ***))g_LockOrderManagerImp[1];
    if ( v10 )
    {
      v4 = -2147024882;
      v12 = v11(&g_LockOrderManagerImp);
      if ( (**v9)((char *)this + 56) != v12 )
        __int2c();
      ((void (__fastcall *)(void ***))g_LockOrderManagerImp[2])(&g_LockOrderManagerImp);
      LeaveCriticalSection((LPCRITICAL_SECTION)(((unsigned __int64)this + 64) & -(__int64)(v9 != 0)));
    }
    else
    {
      v13 = v11(&g_LockOrderManagerImp);
      if ( (**v9)((char *)this + 56) != v13 )
        __int2c();
      ((void (__fastcall *)(void ***))g_LockOrderManagerImp[2])(&g_LockOrderManagerImp);
      LeaveCriticalSection((LPCRITICAL_SECTION)(((unsigned __int64)this + 64) & -(__int64)(v9 != 0)));
      for ( i = (__int64 *)v19[0]; i != (__int64 *)v19[1]; ++i )
      {
        ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(&v20, *i);
        v15 = v20;
        if ( v20
          && (*(unsigned int (__fastcall **)(const void *, const struct _GUID *, _QWORD, _QWORD))(*(_QWORD *)v20 + 32LL))(
               v20,
               a2,
               a3,
               a4) == -2147023174 )
        {
          v16 = (*(__int64 (__fastcall **)(Wallet::WalletBackgroundAgentManager *, const void *))(*(_QWORD *)this + 56LL))(
                  this,
                  v15);
          wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy(
            5,
            "Wallet::WalletBackgroundAgentManager::NotifyAgentRequestCompleted",
            196,
            this,
            "HRESULT was 0x%x when removing disconnected listener %p",
            v16,
            v15);
        }
        ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&v20);
      }
      v17 = (*(__int64 (__fastcall **)(_QWORD, const struct _GUID *))(**((_QWORD **)this + 2) + 48LL))(
              *((_QWORD *)this + 2),
              a2);
      if ( v17 < 0 )
        v4 = v17;
    }
    utl::vector<ATL::CComPtr<IWalletBackgroundAgentListener>,utl::allocator<ATL::CComPtr<IWalletBackgroundAgentListener>>>::_Uninit((__int64)v19);
  }
  return v4;
}

```

## disassembly

```asm
0x180024bf0  mov     [rsp+arg_8], rbx
0x180024bf5  mov     [rsp+arg_10], rbp
0x180024bfa  push    rsi
0x180024bfb  push    rdi
0x180024bfc  push    r12
0x180024bfe  push    r14
0x180024c00  push    r15
0x180024c02  sub     rsp, 60h
0x180024c06  xor     ebp, ebp
0x180024c08  mov     r15d, r9d
0x180024c0b  mov     r12d, r8d
0x180024c0e  mov     r14, rdx
0x180024c11  mov     rsi, rcx
0x180024c14  cmp     [rcx+10h], rbp
0x180024c18  jz      loc_180024DB2
0x180024c1e  lea     rcx, [rsp+88h+var_48]
0x180024c23  call    ??0?$vector@_KV?$allocator@_K@utl@@@utl@@QEAA@XZ; utl::vector<unsigned __int64,utl::allocator<unsigned __int64>>::vector<unsigned __int64,utl::allocator<unsigned __int64>>(void)
0x180024c28  lea     rdi, [rsi+38h]
0x180024c2c  mov     rcx, rdi
0x180024c2f  call    ?lock@?$OrderedLockBase@W4WalletLockOrder@@@@QEAAXXZ; OrderedLockBase<WalletLockOrder>::lock(void)
0x180024c34  lea     rdx, [rsi+20h]
0x180024c38  lea     rcx, [rsp+88h+var_48]
0x180024c3d  call    ?assign@?$vector@V?$CComPtr@UIWalletBackgroundAgentListener@@@ATL@@V?$allocator@V?$CComPtr@UIWalletBackgroundAgentListener@@@ATL@@@utl@@@utl@@QEAA_NAEBV12@@Z; utl::vector<ATL::CComPtr<IWalletBackgroundAgentListener>,utl::allocator<ATL::CComPtr<IWalletBackgroundAgentListener>>>::assign(utl::vector<ATL::CComPtr<IWalletBackgroundAgentListener>,utl::allocator<ATL::CComPtr<IWalletBackgroundAgentListener>>> const &)
0x180024c42  test    al, al
0x180024c44  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180024c4b  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180024c52  mov     rax, [rax+8]
0x180024c56  jnz     short loc_180024CA7
0x180024c58  mov     ebp, 8007000Eh
0x180024c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c62  mov     rcx, [rdi]
0x180024c65  mov     ebx, eax
0x180024c67  mov     rax, [rcx]
0x180024c6a  mov     rcx, rdi
0x180024c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c72  cmp     eax, ebx
0x180024c74  jz      short loc_180024C78
0x180024c76  int     2Ch; Windows NT - assertion failure
0x180024c78  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180024c7f  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180024c86  mov     rax, [rax+10h]
0x180024c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c8f  lea     rax, [rdi+8]
0x180024c93  neg     rdi
0x180024c96  sbb     rcx, rcx
0x180024c99  and     rcx, rax; lpCriticalSection
0x180024c9c  call    cs:__imp_LeaveCriticalSection
0x180024ca2  jmp     loc_180024DA8
0x180024ca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cac  mov     rcx, [rdi]
0x180024caf  mov     ebx, eax
0x180024cb1  mov     rax, [rcx]
0x180024cb4  mov     rcx, rdi
0x180024cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cbc  cmp     eax, ebx
0x180024cbe  jz      short loc_180024CC2
0x180024cc0  int     2Ch; Windows NT - assertion failure
0x180024cc2  mov     rax, cs:?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180024cc9  lea     rcx, ?g_LockOrderManagerImp@@3V?$LockOrderManagerImp@W4WalletLockOrder@@@@A; LockOrderManagerImp<WalletLockOrder> g_LockOrderManagerImp
0x180024cd0  mov     rax, [rax+10h]
0x180024cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cd9  lea     rax, [rdi+8]
0x180024cdd  neg     rdi
0x180024ce0  sbb     rcx, rcx
0x180024ce3  and     rcx, rax; lpCriticalSection
0x180024ce6  call    cs:__imp_LeaveCriticalSection
0x180024cec  mov     rbx, [rsp+88h+var_48]
0x180024cf1  cmp     rbx, [rsp+88h+var_40]
0x180024cf6  jz      loc_180024D8F
0x180024cfc  mov     rdx, [rbx]
0x180024cff  lea     rcx, [rsp+88h+arg_0]
0x180024d07  call    ??0?$CComPtrBase@UIWalletBackgroundAgentListener@@@ATL@@IEAA@PEAUIWalletBackgroundAgentListener@@@Z; ATL::CComPtrBase<IWalletBackgroundAgentListener>::CComPtrBase<IWalletBackgroundAgentListener>(IWalletBackgroundAgentListener *)
0x180024d0c  mov     rdi, [rsp+88h+arg_0]
0x180024d14  test    rdi, rdi
0x180024d17  jz      short loc_180024D79
0x180024d19  mov     rax, [rdi]
0x180024d1c  mov     r9d, r15d
0x180024d1f  mov     r8d, r12d
0x180024d22  mov     rdx, r14
0x180024d25  mov     rcx, rdi
0x180024d28  mov     rax, [rax+20h]
0x180024d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d31  cmp     eax, 800706BAh
0x180024d36  jnz     short loc_180024D79
0x180024d38  mov     rax, [rsi]
0x180024d3b  mov     rdx, rdi
0x180024d3e  mov     rcx, rsi
0x180024d41  mov     rax, [rax+38h]
0x180024d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d4a  mov     [rsp+88h+var_58], rdi
0x180024d4f  lea     rdx, aWalletWalletba_0; "Wallet::WalletBackgroundAgentManager::N"...
0x180024d56  mov     [rsp+88h+var_60], eax
0x180024d5a  mov     r9, rsi
0x180024d5d  lea     rax, aHresultWas0xXW; "HRESULT was 0x%x when removing disconne"...
0x180024d64  mov     r8d, 0C4h
0x180024d6a  mov     ecx, 5
0x180024d6f  mov     [rsp+88h+var_68], rax
0x180024d74  call    ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x180024d79  lea     rcx, [rsp+88h+arg_0]
0x180024d81  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180024d86  add     rbx, 8
0x180024d8a  jmp     loc_180024CF1
0x180024d8f  mov     rcx, [rsi+10h]
0x180024d93  mov     rdx, r14
0x180024d96  mov     rax, [rcx]
0x180024d99  mov     rax, [rax+30h]
0x180024d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024da2  test    eax, eax
0x180024da4  jns     short loc_180024DA8
0x180024da6  mov     ebp, eax
0x180024da8  lea     rcx, [rsp+88h+var_48]
0x180024dad  call    ?_Uninit@?$vector@V?$CComPtr@UIWalletBackgroundAgentListener@@@ATL@@V?$allocator@V?$CComPtr@UIWalletBackgroundAgentListener@@@ATL@@@utl@@@utl@@AEAAXXZ; utl::vector<ATL::CComPtr<IWalletBackgroundAgentListener>,utl::allocator<ATL::CComPtr<IWalletBackgroundAgentListener>>>::_Uninit(void)
0x180024db2  lea     r11, [rsp+88h+var_28]
0x180024db7  mov     eax, ebp
0x180024db9  mov     rbx, [r11+38h]
0x180024dbd  mov     rbp, [r11+40h]
0x180024dc1  mov     rsp, r11
0x180024dc4  pop     r15
0x180024dc6  pop     r14
0x180024dc8  pop     r12
0x180024dca  pop     rdi
0x180024dcb  pop     rsi
0x180024dcc  retn
```
