# CRDPWDUMXStack::TerminateInstance(void)

- ea: `0x18012b9b0`
- end: `0x18012bb9e`
- name: `?TerminateInstance@CRDPWDUMXStack@@UEAAJXZ`
- size: `494`
- prototype: `__int64 __fastcall(CRDPWDUMXStack *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001308`
- `0x18000ce04`
- `0x18000ce34`
- `0x18012b9b0`
- `0x18012c964`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012bb83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012bb83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012bac2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012bac2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18012bb7a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18012bb7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012ba35`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012ba35`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18012bb60`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18012bb60`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18012bb69`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18012bb69`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18012bb52`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18012bb52`

## pseudocode

```c
__int64 __fastcall CRDPWDUMXStack::TerminateInstance(CRDPWDUMXStack *this, __int64 a2, int a3, int a4)
{
  void *v5; // rdi
  struct _TP_TIMER *v6; // rsi
  int v7; // r14d
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  const char *v16; // [rsp+50h] [rbp+8h] BYREF

  if ( (*((_BYTE *)this + 44) & 1) != 0 )
  {
    v5 = 0;
    v6 = 0;
    v7 = 0;
    if ( (unsigned int)CallbackContext > 4 )
    {
      v16 = "Terminating stack instance";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)this,
        (unsigned int)&dword_18028FEA4,
        a3,
        a4,
        (__int64)&v16);
    }
    *((_DWORD *)this + 8) = 1;
    *((_DWORD *)this + 154) = 0;
    CRDPWDUMXStack::WDCloseStack((CRDPWDUMXStack *)((char *)this - 64), 0);
    v8 = *((_QWORD *)this + 97);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 104LL))(v8);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    v9 = *((_DWORD *)this + 11);
    if ( (v9 & 0x20) == 0 )
    {
      v10 = *((_QWORD *)this + 7);
      *((_DWORD *)this + 11) = v9 | 0x20;
      v7 = 1;
      if ( v10 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        *((_QWORD *)this + 7) = 0;
      }
      if ( *((_QWORD *)this + 55) )
      {
        TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 440);
        *((_QWORD *)this + 55) = 0;
        TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 440);
      }
      v5 = (void *)*((_QWORD *)this + 28);
      v11 = *((_QWORD *)this + 93);
      *((_QWORD *)this + 28) = 0;
      v6 = (struct _TP_TIMER *)*((_QWORD *)this + 68);
      *((_QWORD *)this + 68) = 0;
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 72LL))(v11);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    if ( v7 )
    {
      v12 = *((_QWORD *)this + 53);
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 48LL))(v12);
      v13 = *((_QWORD *)this + 90);
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 40LL))(v13);
      v14 = *((_QWORD *)this + 58);
      if ( v14 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 48LL))(v14);
        if ( *((_QWORD *)this + 58) )
        {
          TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 464);
          *((_QWORD *)this + 58) = 0;
          TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 464);
        }
      }
    }
    if ( v6 )
    {
      SetThreadpoolTimer(v6, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v6, 1);
      CloseThreadpoolTimer(v6);
    }
    if ( v5 )
    {
      WaitForSingleObject(v5, 0xFFFFFFFF);
      CloseHandle(v5);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18012b9b0  mov     r11, rsp
0x18012b9b3  mov     [r11+10h], rbx
0x18012b9b7  mov     [r11+18h], rbp
0x18012b9bb  push    rsi
0x18012b9bc  push    rdi
0x18012b9bd  push    r14
0x18012b9bf  sub     rsp, 30h
0x18012b9c3  test    byte ptr [rcx+2Ch], 1
0x18012b9c7  mov     rbx, rcx
0x18012b9ca  jz      loc_18012BB89
0x18012b9d0  mov     eax, cs:CallbackContext
0x18012b9d6  xor     edi, edi
0x18012b9d8  xor     esi, esi
0x18012b9da  xor     r14d, r14d
0x18012b9dd  cmp     eax, 4
0x18012b9e0  jbe     short loc_18012BA01
0x18012b9e2  lea     rax, aTerminatingSta; "Terminating stack instance"
0x18012b9e9  mov     [r11+8], rax
0x18012b9ed  lea     rdx, dword_18028FEA4
0x18012b9f4  lea     rax, [r11+8]
0x18012b9f8  mov     [r11-28h], rax
0x18012b9fc  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18012ba01  xor     edx, edx; int
0x18012ba03  mov     dword ptr [rbx+20h], 1
0x18012ba0a  lea     rcx, [rbx-40h]; this
0x18012ba0e  mov     [rbx+268h], esi
0x18012ba14  call    ?WDCloseStack@CRDPWDUMXStack@@IEAAXJ@Z; CRDPWDUMXStack::WDCloseStack(long)
0x18012ba19  mov     rcx, [rbx+308h]
0x18012ba20  test    rcx, rcx
0x18012ba23  jz      short loc_18012BA31
0x18012ba25  mov     rax, [rcx]
0x18012ba28  mov     rax, [rax+68h]
0x18012ba2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012ba31  lea     rcx, [rbx+68h]; lpCriticalSection
0x18012ba35  call    cs:__imp_EnterCriticalSection
0x18012ba3b  mov     eax, [rbx+2Ch]
0x18012ba3e  test    al, 20h
0x18012ba40  jnz     short loc_18012BABE
0x18012ba42  mov     rcx, [rbx+38h]
0x18012ba46  or      eax, 20h
0x18012ba49  mov     [rbx+2Ch], eax
0x18012ba4c  mov     r14d, 1
0x18012ba52  test    rcx, rcx
0x18012ba55  jz      short loc_18012BA67
0x18012ba57  mov     rax, [rcx]
0x18012ba5a  mov     rax, [rax+10h]
0x18012ba5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012ba63  mov     [rbx+38h], rsi
0x18012ba67  lea     rdi, [rbx+1B8h]
0x18012ba6e  cmp     [rdi], rsi
0x18012ba71  jz      short loc_18012BA86
0x18012ba73  mov     rcx, rdi
0x18012ba76  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18012ba7b  mov     rcx, rdi
0x18012ba7e  mov     [rdi], rsi
0x18012ba81  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18012ba86  mov     rdi, [rbx+0E0h]
0x18012ba8d  mov     rcx, [rbx+2E8h]
0x18012ba94  mov     [rbx+0E0h], rsi
0x18012ba9b  mov     rsi, [rbx+220h]
0x18012baa2  mov     qword ptr [rbx+220h], 0
0x18012baad  test    rcx, rcx
0x18012bab0  jz      short loc_18012BABE
0x18012bab2  mov     rax, [rcx]
0x18012bab5  mov     rax, [rax+48h]
0x18012bab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012babe  lea     rcx, [rbx+68h]; lpCriticalSection
0x18012bac2  call    cs:__imp_LeaveCriticalSection
0x18012bac8  test    r14d, r14d
0x18012bacb  jz      short loc_18012BB42
0x18012bacd  mov     rcx, [rbx+1A8h]
0x18012bad4  test    rcx, rcx
0x18012bad7  jz      short loc_18012BAE5
0x18012bad9  mov     rax, [rcx]
0x18012badc  mov     rax, [rax+30h]
0x18012bae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012bae5  mov     rcx, [rbx+2D0h]
0x18012baec  test    rcx, rcx
0x18012baef  jz      short loc_18012BAFD
0x18012baf1  mov     rax, [rcx]
0x18012baf4  mov     rax, [rax+28h]
0x18012baf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012bafd  mov     rcx, [rbx+1D0h]
0x18012bb04  test    rcx, rcx
0x18012bb07  jz      short loc_18012BB42
0x18012bb09  mov     rax, [rcx]
0x18012bb0c  mov     rax, [rax+30h]
0x18012bb10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012bb15  cmp     qword ptr [rbx+1D0h], 0
0x18012bb1d  jz      short loc_18012BB42
0x18012bb1f  lea     rcx, [rbx+1D0h]
0x18012bb26  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x18012bb2b  lea     rcx, [rbx+1D0h]
0x18012bb32  mov     qword ptr [rbx+1D0h], 0
0x18012bb3d  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x18012bb42  test    rsi, rsi
0x18012bb45  jz      short loc_18012BB6F
0x18012bb47  xor     r9d, r9d; msWindowLength
0x18012bb4a  xor     r8d, r8d; msPeriod
0x18012bb4d  xor     edx, edx; pftDueTime
0x18012bb4f  mov     rcx, rsi; pti
0x18012bb52  call    cs:__imp_SetThreadpoolTimer
0x18012bb58  mov     edx, 1; fCancelPendingCallbacks
0x18012bb5d  mov     rcx, rsi; pti
0x18012bb60  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18012bb66  mov     rcx, rsi; pti
0x18012bb69  call    cs:__imp_CloseThreadpoolTimer
0x18012bb6f  test    rdi, rdi
0x18012bb72  jz      short loc_18012BB89
0x18012bb74  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18012bb77  mov     rcx, rdi; hHandle
0x18012bb7a  call    cs:__imp_WaitForSingleObject
0x18012bb80  mov     rcx, rdi; hObject
0x18012bb83  call    cs:__imp_CloseHandle
0x18012bb89  mov     rbx, [rsp+48h+arg_8]
0x18012bb8e  xor     eax, eax
0x18012bb90  mov     rbp, [rsp+48h+arg_10]
0x18012bb95  add     rsp, 30h
0x18012bb99  pop     r14
0x18012bb9b  pop     rdi
0x18012bb9c  pop     rsi
0x18012bb9d  retn
```
