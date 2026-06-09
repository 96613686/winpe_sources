# RWService::OnStopping(int)

- ea: `0x180008f60`
- end: `0x180009076`
- name: `?OnStopping@RWService@@UEAAJH@Z`
- size: `278`
- prototype: `__int64 __fastcall(RWService *this, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003b40`
- `0x180008f60`
- `0x18000bcd4`
- `0x1800172d8`
- `0x180017560`
- `0x18001a048`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008fb4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008fb4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000902f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000902f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000903c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000903c`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180009018`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180009018`

## pseudocode

```c
__int64 __fastcall RWService::OnStopping(RWService *this, __int64 a2)
{
  struct IUnknown **v2; // rdi
  __int64 v4; // rcx
  TheWallet *v5; // rcx
  struct _TP_WAIT *v6; // rcx
  _BYTE v8[24]; // [rsp+40h] [rbp-18h] BYREF

  v2 = (struct IUnknown **)((char *)this + 200);
  v4 = *((_QWORD *)this + 25);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *, int, _QWORD))(*(_QWORD *)v4 + 24LL))(
      v4,
      RevokeClassObjectsCallback,
      0,
      &GUID_000001da_0000_0000_c000_000000000046,
      5,
      0);
    WaitForSingleObject(g_hCOMReg, 0xFFFFFFFF);
  }
  if ( *v2 )
    ATL::AtlComPtrAssign(v2, 0);
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(v8, a2);
  if ( TheWallet::s_pInstance )
  {
    TheWallet::ShutdownThreadpools(TheWallet::s_pInstance);
    v5 = TheWallet::s_pInstance;
    if ( TheWallet::s_pInstance )
    {
      while ( (*(unsigned int (__fastcall **)(TheWallet *))(*(_QWORD *)v5 + 16LL))(v5) )
        v5 = TheWallet::s_pInstance;
    }
  }
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(v8);
  CoRegisterServerShutdownDelay(0, 0);
  v6 = (struct _TP_WAIT *)*((_QWORD *)this + 23);
  if ( v6 )
  {
    WaitForThreadpoolWaitCallbacks(v6, 1);
    CloseThreadpoolWait(*((PTP_WAIT *)this + 23));
    *((_QWORD *)this + 23) = 0;
  }
  tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 192, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&g_hCOMReg, 0);
  return 0;
}

```

## disassembly

```asm
0x180008f60  mov     [rsp+arg_0], rbx
0x180008f65  push    rdi
0x180008f66  sub     rsp, 50h
0x180008f6a  lea     rdi, [rcx+0C8h]
0x180008f71  mov     rbx, rcx
0x180008f74  mov     rcx, [rdi]
0x180008f77  test    rcx, rcx
0x180008f7a  jz      short loc_180008FBA
0x180008f7c  mov     rax, [rcx]
0x180008f7f  lea     r9, _GUID_000001da_0000_0000_c000_000000000046
0x180008f86  mov     [rsp+58h+var_30], 0
0x180008f8f  lea     rdx, ?RevokeClassObjectsCallback@@YAJPEAUtagComCallData@@@Z; RevokeClassObjectsCallback(tagComCallData *)
0x180008f96  xor     r8d, r8d
0x180008f99  mov     [rsp+58h+var_38], 5
0x180008fa1  mov     rax, [rax+18h]
0x180008fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008faa  mov     rcx, cs:?g_hCOMReg@@3V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@A; hHandle
0x180008fb1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008fb4  call    cs:__imp_WaitForSingleObject
0x180008fba  cmp     qword ptr [rdi], 0
0x180008fbe  jz      short loc_180008FCA
0x180008fc0  xor     edx, edx; struct IUnknown *
0x180008fc2  mov     rcx, rdi; struct IUnknown **
0x180008fc5  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180008fca  lea     rcx, [rsp+58h+var_18]
0x180008fcf  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x180008fd4  mov     rcx, cs:?s_pInstance@TheWallet@@1PEAV1@EA; this
0x180008fdb  test    rcx, rcx
0x180008fde  jz      short loc_18000900A
0x180008fe0  call    ?ShutdownThreadpools@TheWallet@@AEAAJXZ; TheWallet::ShutdownThreadpools(void)
0x180008fe5  mov     rcx, cs:?s_pInstance@TheWallet@@1PEAV1@EA; TheWallet * TheWallet::s_pInstance
0x180008fec  test    rcx, rcx
0x180008fef  jz      short loc_18000900A
0x180008ff1  mov     rax, [rcx]
0x180008ff4  mov     rax, [rax+10h]
0x180008ff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ffd  test    eax, eax
0x180008fff  jz      short loc_18000900A
0x180009001  mov     rcx, cs:?s_pInstance@TheWallet@@1PEAV1@EA; TheWallet * TheWallet::s_pInstance
0x180009008  jmp     short loc_180008FF1
0x18000900a  lea     rcx, [rsp+58h+var_18]
0x18000900f  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x180009014  xor     edx, edx
0x180009016  xor     ecx, ecx
0x180009018  call    cs:__imp_CoRegisterServerShutdownDelay
0x18000901e  mov     rcx, [rbx+0B8h]; pwa
0x180009025  test    rcx, rcx
0x180009028  jz      short loc_18000904D
0x18000902a  mov     edx, 1; fCancelPendingCallbacks
0x18000902f  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180009035  mov     rcx, [rbx+0B8h]; pwa
0x18000903c  call    cs:__imp_CloseThreadpoolWait
0x180009042  mov     qword ptr [rbx+0B8h], 0
0x18000904d  lea     rcx, [rbx+0C0h]
0x180009054  xor     edx, edx
0x180009056  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18000905b  xor     edx, edx
0x18000905d  lea     rcx, ?g_hCOMReg@@3V?$unique_any@Ufile_handle_traits@tlx@@@tlx@@A; tlx::unique_any<tlx::file_handle_traits> g_hCOMReg
0x180009064  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180009069  mov     rbx, [rsp+58h+arg_0]
0x18000906e  xor     eax, eax
0x180009070  add     rsp, 50h
0x180009074  pop     rdi
0x180009075  retn
```
