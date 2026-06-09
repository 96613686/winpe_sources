# Broker::SystemTimer::SystemTimer(std::function<void (void)>,bool)

- ea: `0x180017e64`
- end: `0x180018076`
- name: `??0SystemTimer@Broker@@QEAA@V?$function@$$A6AXXZ@std@@_N@Z`
- size: `530`
- prototype: `struct _RTL_SRWLOCK *__fastcall(struct _RTL_SRWLOCK *pv, __int64, unsigned __int8)`
- caller_count: `3`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800126ec`
- `0x1800127cc`
- `0x180012878`

## callees

- `0x18000106c`
- `0x180003800`
- `0x18000bba0`
- `0x18000d1d4`
- `0x18000e70c`
- `0x18000ee60`
- `0x1800111f4`
- `0x18001181c`
- `0x180013978`
- `0x180013eb0`
- `0x180013f0c`
- `0x180017e24`
- `0x180017e64`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x180017ed0`
- `ntdll!RtlInitializeSRWLock` at `0x180017ed0`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180017efd`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x180017efd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180017f1c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180017f1c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180017f38`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180017f38`

## pseudocode

```c
struct _RTL_SRWLOCK *__fastcall Broker::SystemTimer::SystemTimer(
        struct _RTL_SRWLOCK *pv,
        __int64 a2,
        unsigned __int8 a3)
{
  int v3; // r14d
  __int64 v6; // rcx
  bool v7; // r8
  unsigned int v8; // ecx
  HANDLE IRTimer; // rax
  struct _TP_WAIT *ThreadpoolWait; // rax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rdx
  __int64 v15; // rcx
  _BYTE v17[16]; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v18[32]; // [rsp+40h] [rbp-19h] BYREF
  unsigned int v19; // [rsp+60h] [rbp+7h]
  _BYTE pExceptionObject[72]; // [rsp+68h] [rbp+Fh] BYREF
  struct _RTL_SRWLOCK *Ptr; // [rsp+C0h] [rbp+67h] BYREF
  __int64 v22; // [rsp+C8h] [rbp+6Fh]
  int v23; // [rsp+D0h] [rbp+77h] BYREF

  v22 = a2;
  Ptr = pv;
  v3 = a3;
  pv[2].Ptr = 0;
  LOBYTE(pv[3].Ptr) = a3;
  std::function<void (void)>::function<void (void)>(&pv[4]);
  if ( (unsigned int)dword_180026058 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180026058, 1) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v6,
      &dword_180020A64);
  RtlInitializeSRWLock(&pv[12]);
  Broker::ScopedWriteLock::ScopedWriteLock((Broker::ScopedWriteLock *)v17, pv + 12, v7);
  if ( (_BYTE)v3 )
    IRTimer = BciCreateIRTimer(v8);
  else
    IRTimer = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
  pv->Ptr = IRTimer;
  if ( !IRTimer )
  {
    Broker::Win32Error::Win32Error((Broker::Win32Error *)v18);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_3dffd7de185a340ed95b82f28f39c2f4_Traceguids, v19);
    Broker::Win32Error::Win32Error(pExceptionObject, v18);
    throw (Broker::Win32Error *)pExceptionObject;
  }
  ThreadpoolWait = CreateThreadpoolWait(Broker::SystemTimer::WaitCallback, pv, 0);
  pv[1].Ptr = ThreadpoolWait;
  if ( !ThreadpoolWait )
  {
    BciCloseWaitableTimer(pv->Ptr);
    Broker::Win32Error::Win32Error((Broker::Win32Error *)v18);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_3dffd7de185a340ed95b82f28f39c2f4_Traceguids, v19);
    Broker::Win32Error::Win32Error(pExceptionObject, v18);
    throw (Broker::Win32Error *)pExceptionObject;
  }
  SetThreadpoolWait(ThreadpoolWait, pv->Ptr, 0);
  if ( (unsigned int)dword_180026058 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180026058, 1) )
  {
    v23 = v3;
    Ptr = (struct _RTL_SRWLOCK *)pv->Ptr;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v11,
      (unsigned int)byte_180020A13,
      v12,
      v13,
      (__int64)&Ptr,
      (__int64)&v23);
  }
  Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)v17);
  v15 = *(_QWORD *)(a2 + 56);
  if ( v15 )
  {
    LOBYTE(v14) = v15 != a2;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 32LL))(v15, v14);
    *(_QWORD *)(a2 + 56) = 0;
  }
  return pv;
}

```

## disassembly

```asm
0x180017e64  mov     [rsp-8+arg_8], rdx
0x180017e69  mov     [rsp-8+arg_0], rcx
0x180017e6e  push    rbp
0x180017e6f  push    rbx
0x180017e70  push    rsi
0x180017e71  push    rdi
0x180017e72  push    r14
0x180017e74  lea     rbp, [rsp-37h]
0x180017e79  sub     rsp, 90h
0x180017e80  movzx   r14d, r8b
0x180017e84  mov     rsi, rdx
0x180017e87  mov     rdi, rcx
0x180017e8a  mov     qword ptr [rcx+10h], 0
0x180017e92  mov     [rcx+18h], r14b
0x180017e96  add     rcx, 20h ; ' '
0x180017e9a  call    ??0?$function@$$A6AXXZ@std@@QEAA@AEBV01@@Z; std::function<void (void)>::function<void (void)>(std::function<void (void)> const &)
0x180017e9f  nop
0x180017ea0  mov     eax, cs:dword_180026058
0x180017ea6  cmp     eax, 5
0x180017ea9  jbe     short loc_180017ECC
0x180017eab  mov     edx, 1
0x180017eb0  lea     rcx, dword_180026058
0x180017eb7  call    _tlgKeywordOn
0x180017ebc  test    al, al
0x180017ebe  jz      short loc_180017ECC
0x180017ec0  lea     rdx, dword_180020A64
0x180017ec7  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180017ecc  lea     rcx, [rdi+60h]
0x180017ed0  call    cs:__imp_RtlInitializeSRWLock
0x180017ed6  lea     rdx, [rdi+60h]; struct _RTL_SRWLOCK *
0x180017eda  lea     rcx, [rbp+57h+var_80]; this
0x180017ede  call    ??0ScopedWriteLock@Broker@@QEAA@AEAU_RTL_SRWLOCK@@_N@Z; Broker::ScopedWriteLock::ScopedWriteLock(_RTL_SRWLOCK &,bool)
0x180017ee3  nop
0x180017ee4  test    r14b, r14b
0x180017ee7  jz      short loc_180017EF0
0x180017ee9  call    ?BciCreateIRTimer@@YAPEAXK@Z; BciCreateIRTimer(ulong)
0x180017eee  jmp     short loc_180017F03
0x180017ef0  mov     r9d, 1F0003h; dwDesiredAccess
0x180017ef6  xor     r8d, r8d; dwFlags
0x180017ef9  xor     edx, edx; lpTimerName
0x180017efb  xor     ecx, ecx; lpTimerAttributes
0x180017efd  call    cs:__imp_CreateWaitableTimerExW
0x180017f03  mov     [rdi], rax
0x180017f06  test    rax, rax
0x180017f09  jz      loc_180018022
0x180017f0f  xor     r8d, r8d; pcbe
0x180017f12  mov     rdx, rdi; pv
0x180017f15  lea     rcx, ?WaitCallback@SystemTimer@Broker@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180017f1c  call    cs:__imp_CreateThreadpoolWait
0x180017f22  mov     [rdi+8], rax
0x180017f26  test    rax, rax
0x180017f29  jz      loc_180017FC6
0x180017f2f  xor     r8d, r8d; pftTimeout
0x180017f32  mov     rdx, [rdi]; h
0x180017f35  mov     rcx, rax; pwa
0x180017f38  call    cs:__imp_SetThreadpoolWait
0x180017f3e  mov     eax, cs:dword_180026058
0x180017f44  cmp     eax, 5
0x180017f47  jbe     short loc_180017F88
0x180017f49  mov     edx, 1
0x180017f4e  lea     rcx, dword_180026058
0x180017f55  call    _tlgKeywordOn
0x180017f5a  test    al, al
0x180017f5c  jz      short loc_180017F88
0x180017f5e  mov     [rbp+57h+arg_10], r14d
0x180017f62  mov     rax, [rdi]
0x180017f65  mov     [rbp+57h+arg_0], rax
0x180017f69  lea     rax, [rbp+57h+arg_10]
0x180017f6d  mov     [rsp+0B0h+var_88], rax
0x180017f72  lea     rax, [rbp+57h+arg_0]
0x180017f76  mov     [rsp+0B0h+var_90], rax
0x180017f7b  lea     rdx, byte_180020A13
0x180017f82  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180017f87  nop
0x180017f88  lea     rcx, [rbp+57h+var_80]; this
0x180017f8c  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x180017f91  nop
0x180017f92  mov     rcx, [rsi+38h]
0x180017f96  test    rcx, rcx
0x180017f99  jz      short loc_180017FB5
0x180017f9b  mov     rax, [rcx]
0x180017f9e  cmp     rcx, rsi
0x180017fa1  setnz   dl
0x180017fa4  mov     rax, [rax+20h]
0x180017fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fad  mov     qword ptr [rsi+38h], 0
0x180017fb5  mov     rax, rdi
0x180017fb8  add     rsp, 90h
0x180017fbf  pop     r14
0x180017fc1  pop     rdi
0x180017fc2  pop     rsi
0x180017fc3  pop     rbx
0x180017fc4  pop     rbp
0x180017fc5  retn
0x180017fc6  mov     rcx, [rdi]; void *
0x180017fc9  call    ?BciCloseWaitableTimer@@YAHPEAX@Z; BciCloseWaitableTimer(void *)
0x180017fce  lea     rcx, [rbp+57h+var_70]; this
0x180017fd2  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x180017fd7  nop
0x180017fd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180017fdf  test    byte ptr [rcx+1Ch], 4
0x180017fe3  jz      short loc_180018004
0x180017fe5  cmp     byte ptr [rcx+19h], 2
0x180017fe9  jb      short loc_180018004
0x180017feb  mov     edx, 0Bh
0x180017ff0  mov     r9d, [rbp+57h+var_50]
0x180017ff4  lea     r8, WPP_3dffd7de185a340ed95b82f28f39c2f4_Traceguids
0x180017ffb  mov     rcx, [rcx+10h]
0x180017fff  call    WPP_SF_d
0x180018004  lea     rdx, [rbp+57h+var_70]
0x180018008  lea     rcx, [rbp+57h+pExceptionObject]
0x18001800c  call    ??0Win32Error@Broker@@QEAA@$$QEAU01@@Z; Broker::Win32Error::Win32Error(Broker::Win32Error &&)
0x180018011  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180018018  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001801c  call    _CxxThrowException_0
0x180018022  lea     rcx, [rbp+57h+var_70]; this
0x180018026  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x18001802b  nop
0x18001802c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018033  test    byte ptr [rcx+1Ch], 4
0x180018037  jz      short loc_180018058
0x180018039  cmp     byte ptr [rcx+19h], 2
0x18001803d  jb      short loc_180018058
0x18001803f  mov     edx, 0Ah
0x180018044  mov     r9d, [rbp+57h+var_50]
0x180018048  lea     r8, WPP_3dffd7de185a340ed95b82f28f39c2f4_Traceguids
0x18001804f  mov     rcx, [rcx+10h]
0x180018053  call    WPP_SF_d
0x180018058  lea     rdx, [rbp+57h+var_70]
0x18001805c  lea     rcx, [rbp+57h+pExceptionObject]
0x180018060  call    ??0Win32Error@Broker@@QEAA@$$QEAU01@@Z; Broker::Win32Error::Win32Error(Broker::Win32Error &&)
0x180018065  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18001806c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180018070  call    _CxxThrowException_0
```
